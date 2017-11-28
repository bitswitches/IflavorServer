# IflavorServer

## prerequsites
- virtualbox ?
- vagrant
  - vagrant proxy plugin: `vagrant plugin install vagrant-proxyconf`
    - type this `VAGRANT_DISABLE_STRICT_DEPENDENCY_ENFORCEMENT=1 vagrant plugin install vagrant-proxyconf`, if dependency error occur

## How to Start
- vagrant up
- etc

## programming language
- PHP

## framework
- Laravel

## Environment Variables

### Vagrant

#### static ip
- VAGRANT_STATIC_IP (optional)
  - default static ip address : `192.168.33.10`

#### proxy

- VAGRANT_HTTP_PROXY (optional)
- VAGRANT_HTTPS_PROXY (optional)
- VAGRANT_FTP_PROXY (optional)
- VAGRANT_NO_PROXY (optional) (recommended value contain `localhost,127.0.0.1`)

### MySQL

- comming soon


## License

The Laravel framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT).
