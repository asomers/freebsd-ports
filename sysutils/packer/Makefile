# $FreeBSD$

PORTNAME=	packer
PORTVERSION=	1.0.3
DISTVERSIONPREFIX=	v
CATEGORIES=	sysutils

MAINTAINER=	lifanov@FreeBSD.org
COMMENT=	Tool for creating machine images

LICENSE=	MPL
LICENSE_FILE=	${WRKSRC}/LICENSE

PLIST_FILES=	bin/${PORTNAME}

USE_GITHUB=	yes
GH_ACCOUNT=	hashicorp

USES=	go

GO_PKGNAME=	github.com/${GH_ACCOUNT}/${PORTNAME}

.include <bsd.port.mk>
