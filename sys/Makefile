MODULE = sys
ifneq (,$(filter auto_init,$(USEMODULE)))
    DIRS += auto_init
endif
ifneq (,$(filter config,$(USEMODULE)))
    DIRS += config
endif
ifneq (,$(filter lib,$(USEMODULE)))
    DIRS += lib
endif
ifneq (,$(filter ping,$(USEMODULE)))
    DIRS += ping
endif
ifneq (,$(filter ps,$(USEMODULE)))
    DIRS += ps
endif
ifneq (,$(filter posix,$(USEMODULE)))
	INCLUDES += -I$(RIOTBASE)/sys/posix/include
    DIRS += posix
endif
ifneq (,$(filter pnet,$(USEMODULE)))
    DIRS += posix/pnet
endif
ifneq (,$(filter pthread,$(USEMODULE)))
    DIRS += posix/pthread
endif
ifneq (,$(filter shell,$(USEMODULE)))
    DIRS += shell
endif
ifneq (,$(filter shell_commands,$(USEMODULE)))
    DIRS += shell/commands
endif
ifneq (,$(filter timex,$(USEMODULE)))
    DIRS += timex
endif
ifneq (,$(filter transceiver,$(USEMODULE)))
    DIRS += transceiver
endif
ifneq (,$(filter uart0,$(USEMODULE)))
    DIRS += uart0
endif
ifneq (,$(filter vtimer,$(USEMODULE)))
    DIRS += vtimer
endif
ifneq (,$(filter net_if,$(USEMODULE)))
    DIRS += net/link_layer/net_if
endif
ifneq (,$(filter destiny,$(USEMODULE)))
    DIRS += net/transport_layer/destiny
endif
ifneq (,$(filter net_help,$(USEMODULE)))
    DIRS += net/crosslayer/net_help
endif
ifneq (,$(filter protocol_multiplex,$(USEMODULE)))
    DIRS += net/link_layer/protocol-multiplex
endif
ifneq (,$(filter sixlowpan,$(USEMODULE)))
    DIRS += net/network_layer/sixlowpan
endif
ifneq (,$(filter sixlowborder,$(USEMODULE)))
    DIRS += net/network_layer/sixlowpan/border
endif
ifneq (,$(filter rpl,$(USEMODULE)))
    DIRS += net/routing/rpl
endif
ifneq (,$(filter ieee802154,$(USEMODULE)))
    DIRS += net/link_layer/ieee802154
endif
ifneq (,$(filter bloom,$(USEMODULE)))
    DIRS += bloom
endif
ifneq (,$(filter crypto_3des,$(USEMODULE)))
    DIRS += crypto/3des
endif
ifneq (,$(filter crypto_aes,$(USEMODULE)))
    DIRS += crypto/aes
endif
ifneq (,$(filter crypto_rc5,$(USEMODULE)))
    DIRS += crypto/rc5
endif
ifneq (,$(filter crypto_sha256,$(USEMODULE)))
    DIRS += crypto/sha256
endif
ifneq (,$(filter crypto_skipjack,$(USEMODULE)))
    DIRS += crypto/skipjack
endif
ifneq (,$(filter crypto_twofish,$(USEMODULE)))
    DIRS += crypto/twofish
endif
ifneq (,$(filter random,$(USEMODULE)))
    DIRS += random
endif
ifneq (,$(filter hashes,$(USEMODULE)))
    DIRS += hashes
endif
ifneq (,$(filter semaphore,$(USEMODULE)))
    DIRS += semaphore
endif
ifneq (,$(filter ccn_lite,$(USEMODULE)))
    DIRS += net/ccn_lite
endif
ifneq (,$(filter ccn_lite_client,$(USEMODULE)))
    DIRS += net/ccn_lite/util
endif
ifneq (,$(findstring quad_math,$(USEMODULE)))
    DIRS += quad_math
endif

all: $(BINDIR)$(MODULE).a
	@for i in $(DIRS) ; do "$(MAKE)" -C $$i || exit 1; done ;

include $(RIOTBASE)/Makefile.base

# remove compilation products
clean::
	@for i in $(DIRS) ; do "$(MAKE)" -C $$i clean || exit 1; done ;
