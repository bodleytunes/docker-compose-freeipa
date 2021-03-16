### FreeIPA via docker-compose containers

This setup requires routed containers, each of these networks `10.20.65.0/24` and `10.21.65.0/24` are advertised over ZeroTier to allow the remote hosts to talk to each other over.

Swap out ZT for any other overlay/vpn, e.g. nebula, wireguard, tailscale etc.

Also note the docker bridge MTU size is reduced to 1300 bytes to allow for the encrypted overhead, otherwise can cause all sorts of problems particularly with SSL if the containers run their vnics at the default 1500.

### Install Vault
on both nodes:

`ipa-kra-install -p my_admin_password`

`ipa vault-add`