#
# crypto/ecdh/Makefile
#

DIR=	ecdh
TOP=	../..
CC=	cc
INCLUDES= -I.. -I$(TOP) -I../../include
CFLAG=-g -Wall
MAKEFILE=	Makefile
AR=		ar r

CFLAGS= $(INCLUDES) $(CFLAG)

GENERAL=Makefile

LIB=$(TOP)/libcrypto.a
LIBSRC=	ech_lib.c ech_ossl.c ech_key.c ech_err.c ech_kdf.c

LIBOBJ=	ech_lib.o ech_ossl.o ech_key.o ech_err.o ech_kdf.o

SRC= $(LIBSRC)

HEADER=	ech_locl.h

ALL=    $(GENERAL) $(SRC) $(HEADER)

top:
	(cd ../..; $(MAKE) DIRS=crypto SDIRS=$(DIR) sub_all)

all:	lib

lib:	$(LIBOBJ)
	$(AR) $(LIB) $(LIBOBJ)
	$(RANLIB) $(LIB) || echo Never mind.
	@touch lib

files:
	$(PERL) $(TOP)/util/files.pl Makefile >> $(TOP)/MINFO

tags:
	ctags $(SRC)

tests:

lint:
	lint -DLINT $(INCLUDES) $(SRC)>fluff

update: depend

depend:
	@[ -n "$(MAKEDEPEND)" ] # should be set by upper Makefile...
	$(MAKEDEPEND) -- $(CFLAG) $(INCLUDES) $(DEPFLAG) -- $(PROGS) $(LIBSRC)

dclean:
	$(PERL) -pe 'if (/^# DO NOT DELETE THIS LINE/) {print; exit(0);}' $(MAKEFILE) >Makefile.new
	mv -f Makefile.new $(MAKEFILE)

clean:
	rm -f *.o */*.o *.obj lib tags core .pure .nfs* *.old *.bak fluff

# DO NOT DELETE THIS LINE -- make depend depends on it.

ech_err.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
ech_err.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
ech_err.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
ech_err.o: ../../include/openssl/err.h ../../include/openssl/lhash.h
ech_err.o: ../../include/openssl/opensslconf.h ../../include/openssl/opensslv.h
ech_err.o: ../../include/openssl/ossl_typ.h ../../include/openssl/safestack.h
ech_err.o: ../../include/openssl/stack.h ../../include/openssl/symhacks.h
ech_err.o: ech_err.c
ech_kdf.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
ech_kdf.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
ech_kdf.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
ech_kdf.o: ../../include/openssl/evp.h ../../include/openssl/obj_mac.h
ech_kdf.o: ../../include/openssl/objects.h ../../include/openssl/opensslconf.h
ech_kdf.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
ech_kdf.o: ../../include/openssl/safestack.h ../../include/openssl/stack.h
ech_kdf.o: ../../include/openssl/symhacks.h ech_kdf.c
ech_key.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
ech_key.o: ../../include/openssl/crypto.h ../../include/openssl/e_os2.h
ech_key.o: ../../include/openssl/ec.h ../../include/openssl/ecdh.h
ech_key.o: ../../include/openssl/opensslconf.h ../../include/openssl/opensslv.h
ech_key.o: ../../include/openssl/ossl_typ.h ../../include/openssl/safestack.h
ech_key.o: ../../include/openssl/stack.h ../../include/openssl/symhacks.h
ech_key.o: ech_key.c ech_locl.h
ech_lib.o: ../../include/openssl/asn1.h ../../include/openssl/bio.h
ech_lib.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
ech_lib.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
ech_lib.o: ../../include/openssl/ecdh.h ../../include/openssl/ecdsa.h
ech_lib.o: ../../include/openssl/engine.h ../../include/openssl/err.h
ech_lib.o: ../../include/openssl/evp.h ../../include/openssl/lhash.h
ech_lib.o: ../../include/openssl/obj_mac.h ../../include/openssl/objects.h
ech_lib.o: ../../include/openssl/opensslconf.h ../../include/openssl/opensslv.h
ech_lib.o: ../../include/openssl/ossl_typ.h ../../include/openssl/pkcs7.h
ech_lib.o: ../../include/openssl/safestack.h ../../include/openssl/sha.h
ech_lib.o: ../../include/openssl/stack.h ../../include/openssl/symhacks.h
ech_lib.o: ../../include/openssl/x509.h ../../include/openssl/x509_vfy.h
ech_lib.o: ech_lib.c ech_locl.h
ech_ossl.o: ../../e_os.h ../../include/openssl/asn1.h
ech_ossl.o: ../../include/openssl/bio.h ../../include/openssl/bn.h
ech_ossl.o: ../../include/openssl/buffer.h ../../include/openssl/crypto.h
ech_ossl.o: ../../include/openssl/e_os2.h ../../include/openssl/ec.h
ech_ossl.o: ../../include/openssl/ecdh.h ../../include/openssl/err.h
ech_ossl.o: ../../include/openssl/lhash.h ../../include/openssl/obj_mac.h
ech_ossl.o: ../../include/openssl/opensslconf.h
ech_ossl.o: ../../include/openssl/opensslv.h ../../include/openssl/ossl_typ.h
ech_ossl.o: ../../include/openssl/safestack.h ../../include/openssl/sha.h
ech_ossl.o: ../../include/openssl/stack.h ../../include/openssl/symhacks.h
ech_ossl.o: ../include/internal/cryptlib.h ech_locl.h ech_ossl.c
