# Created by: Anton Berezin <tobez@FreeBSD.org>
# $FreeBSD$

PORTNAME=	Data-Random
PORTVERSION=	0.12
PORTREVISION=	1
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl module for generating random data

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

BUILD_DEPENDS=	p5-YAML-Tiny>=0:textproc/p5-YAML-Tiny

OPTIONS_DEFINE=	GD
GD_DESC=	Support for rand_image()

NO_ARCH=	yes
USES=		perl5
USE_PERL5=	configure

GD_BUILD_DEPENDS=	p5-GD>=0:graphics/p5-GD
GD_RUN_DEPENDS=		p5-GD>=0:graphics/p5-GD

.include <bsd.port.mk>
