# Created by: Hye-Shik Chang
# $FreeBSD$

PORTNAME=	io
PORTVERSION=	2015.11.11
PORTREVISION=	6
CATEGORIES=	lang

MAINTAINER=	gahr@FreeBSD.org
COMMENT=	Small prototype-based programming language

LICENSE=	BSD3CLAUSE

BROKEN_armv6=		fails to compile: ucontext.h: expected parameter declarator

USE_GITHUB=	yes
GH_ACCOUNT=	stevedekorte
GH_TAGNAME=	23afbcc

USES=		cmake:outsource,noninja compiler:c11
MAKE_JOBS_UNSAFE=yes
USE_LDCONFIG=	yes

PORTDOCS=	*
PORTEXAMPLES=	*

OPTIONS_DEFINE=	DOCS EXAMPLES
OPTIONS_GROUP=	ADDONS
OPTIONS_SUB=	yes

.include "${.CURDIR}/Makefile.addons"

post-patch:
	${REINPLACE_CMD} -e 's/^[ ]*add_subdirectory/#&/' \
		${WRKSRC}/addons/CMakeLists.txt
	${RM} ${WRKSRC}/modules/FindFreetype.cmake
.for addon in ${ADDONS}
	${ECHO} "add_subdirectory(${addon})" >> ${WRKSRC}/addons/CMakeLists.txt
.endfor
	${FIND} ${WRKSRC}/addons -name "*.bak" -o -name "*.orig" -delete

post-install:
	${FIND} -d ${STAGEDIR}${PREFIX}/lib/io/addons -type d -empty -delete
	${FIND} ${STAGEDIR}${PREFIX}/lib/io/addons -type f -name "*.so" -exec \
		${STRIP_CMD} {} \;
	${MKDIR}  ${STAGEDIR}${DOCSDIR}
	cd ${WRKSRC}/docs && ${COPYTREE_SHARE} . ${STAGEDIR}${DOCSDIR}
	${MKDIR}  ${STAGEDIR}${EXAMPLESDIR}
	cd ${WRKSRC}/samples && ${COPYTREE_SHARE} . ${STAGEDIR}${EXAMPLESDIR}

.include <bsd.port.mk>
