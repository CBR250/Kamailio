first_rule: all

all: build install

PACKAGE_VERSION := kamailio
PACKAGE_DIR := kamailio

# Configuration
PACKAGE_CONF := \
    --prefix=$(CURDIR)/../../OBJ/ \

test_directory: 
	if [ ! -d $(CURDIR)/../../TARGET ]; then \
	   mkdir $(CURDIR)/../../TARGET/; \
	fi
	if [ -d $(CURDIR)/../../TARGET/$(PACKAGE_DIR) ]; then \
	       echo "Folder existed"; \
	else \
	       tar xvf $(CURDIR)/$(PACKAGE_DIR).tar.bz2 -C $(CURDIR)/../../TARGET/; \
	fi
	
build: test_directory
	$(MAKE) -C $(CURDIR)/../../TARGET/$(PACKAGE_DIR) prefix=$(CURDIR)/../../OBJ/bin include_modules="db_mysql tls"

pre_install_check:
	if [ ! -d $(CURDIR)/../../OBJ/bin ]; then \
	    mkdir -p $(CURDIR)/../../OBJ/bin; \
	fi


install: pre_install_check
	$(MAKE) -C $(CURDIR)/../../TARGET/$(PACKAGE_DIR) install; \

config_rule:

clean_rule:

uninstall_rule:

