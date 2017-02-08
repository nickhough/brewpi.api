# BrewPi API

This is a _very_ basic API to enable remote access to your BrewPi data.

## Modern Brewer App

The Modern Brewer app relies on this API for the BrewPi integration.

## Installation

Assuming a standard BrewPi installation, you'll do the following:

1. Create an `api` directory in your web root: `mkdir /var/www/html/api`
2. Change into your new `api` directory: `cd /var/www/html/api`
3. Clone this repository into that directory: `git clone https://github.com/nickhough/brewpi.api.git .`

## Endpoints

The following endpoints will now be available at the IP address you normally access your BrewPi interface from, such as `http://192.168.1.200`.

| Request Type | Endpoint | Required Arguments |
| ------------ | -------- | --------- |
| GET          | `/api/user-settings.php` |  |
| POST         | `/api/beer-data.php` | `beername` |

## Remote Access

Remote access to your new BrewPi API can be done several ways.

1. You can forward a port on your router to your BrewPi. [Read about port forwarding.](http://www.howtogeek.com/66214/how-to-forward-ports-on-your-router/)
2. You can create a VPN. [Read about creating a VPN.](https://openvpn.net/index.php/open-source/documentation/howto.html)

## Security

Now you've enabled remote access, but anyone can access your BrewPi interface. Let's add Basic Auth to prevent that. These instructions are written by the team at [Digital Ocean](https://digitalocean.com), but they'll work fine on an RPi: [Instructions](https://www.digitalocean.com/community/tutorials/how-to-set-up-password-authentication-with-apache-on-ubuntu-14-04).

## Dynamic IP

If you're like me and you have a rotating IP at home, you may be interested in a service like [NO-IP](https://www.noip.com/). My router even allows me to configure it to push IP changes to NO-IP automatically. With this service, you can create a free domain name to go along with your remote access, such as `http://mychamber.ddns.net`.
