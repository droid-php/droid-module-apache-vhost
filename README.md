# Droid Module: apache-vhost

Configure Apache 2 Virtual Hosts. For more information on Droid, please see
[droidphp.com](http://droidphp.com).

The steps involved are:-

1. Write a virtual host configuration file for each defined website, to each of
   the hosts.
2. Create the document root directory of each website on each of the hosts.
3. Write a placeholder index page to the document root of each website on each
   of the hosts.
4. Enable each virtual host on each of the hosts.
5. Instruct Apache to reload its configuration on each of the hosts.


## Assumptions

1. The platform is Debian-based.
2. Each of the machines is to host the same set of Apache virtual hosts.


## Limitations

1. One virtual host configuration template is used as the basis for all of the
   virtual hosts.
2. The variability of the virtual host configuration template is limited to the
   following directives:-
   - The virtual host socket on which to listen
   - `ServerName`
   - `DocumentRoot`
   - A list of zero or more `SetEnv` directives


## Information required by the module

A list of virtual host configurations as `module_apache_vhost_items`, each with
the following elements:-

- `name`: A name for the configuration; used in the config and log file names.
- `socket`: A socket string, suitable for Apache's
  [`<VirtualHost>`][VirtualHost] directive.
- `servername`: A value for the [`ServerName`][ServerName] directive.
- `docroot`: A value for the [`DocumentRoot`][DocumentRoot] and the
  [`<Directory>`][Directory] directory-path.


## Optional information

Members of `module_apache_vhost_items` may also contain the following
elements:-

- `env`: A list of strings suitable as arguments to the [`SetEnv`][SetEnv]
  directive.


[Directory]: <https://httpd.apache.org/docs/2.4/mod/core.html#directory>
[DocumentRoot]: <https://httpd.apache.org/docs/2.4/mod/core.html#documentroot>
[ServerName]: <https://httpd.apache.org/docs/2.4/mod/core.html#servername>
[SetEnv]: <https://httpd.apache.org/docs/2.4/mod/mod_env.html#setenv>
[VirtualHost]: <https://httpd.apache.org/docs/2.4/mod/core.html#virtualhost>
