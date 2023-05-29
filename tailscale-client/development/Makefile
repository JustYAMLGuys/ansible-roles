.PHONY: clean ping tailscale

clean:
	rm -f *.retry

ping:
	ansible all -m ping

tailscale:
	ansible-playbook tailscale-client.yml