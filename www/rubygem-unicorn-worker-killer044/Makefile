# $FreeBSD$

PORTNAME=	unicorn-worker-killer
PORTVERSION=	0.4.4
CATEGORIES=	www rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	044

MAINTAINER=	mfechner@FreeBSD.org
COMMENT=	Kill unicorn workers by memory and request counts

LICENSE=	GPLv2+ RUBY
LICENSE_COMB=	dual
LICENSE_FILE_RUBY=	${WRKSRC}/LICENSE

RUN_DEPENDS=	rubygem-get_process_mem>=0:devel/rubygem-get_process_mem \
		rubygem-unicorn51>=4:www/rubygem-unicorn51

PORTSCOUT=	limit:^0\.4\.4

NO_ARCH=	yes
USES=		gem
USE_RUBY=	yes

.include <bsd.port.mk>
