VERSION = 1.1
PLUGIN = chrony
all: $(PLUGIN)-$(VERSION).mkp

$(PLUGIN)-$(VERSION).mkp: agents.tar checks.tar info
	tar -czvf $(PLUGIN)-$(VERSION).mkp agents.tar checks.tar info

info: Makefile info.template
	sed -re 's/%VERSION%/$(VERSION)/' info.template >info

agents.tar: plugins/$(PLUGIN)
	tar -cf agents.tar plugins/$(PLUGIN)

checks.tar: checks/$(PLUGIN)
	tar -cf checks.tar -C checks $(PLUGIN)

clean:
	rm -f checks.tar agents.tar info 

all-clean: clean
	rm -f $(PLUGIN)-$(VERSION).mkp 
