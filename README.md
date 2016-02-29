# SYDI-Server_to_Dokuwki
Automated process to use SYDI-Server to gather server information and send it directly to an instance of Dokuwiki

## Requirements
- an istalation of Dokuwiki with rpcxml allowed and a user that can use it. From [Douwiki](https://www.dokuwiki.org/devel:xmlrpc#get_it_working "dokuwiki devel"):

> - You need at least the 2008-03-31 release of DokuWiki.
> - Enable the XML-RPC interface in the “Authentication Settings” section
> - Set the remoteuser option
> - For security reasons it's safer to allow access to the XML-RPC over HTTPS only. DokuWiki's .htaccess.dist contains some rewrite rules to do that.

- cURL [from here](https://curl.haxx.se/download.html)

## Installation
 - copy files to local directory and update settings in `sydi-wrapper_DW.vbs`
  - `SYSIROOT` => `path\to\instalation\location`
  - `doku_rpc` => `http://[dokuWikiLocation]/lib/exe/xmlrpc.php`
  - `doku_ns` => `servers:`
  - `doku_user` => `myUser`
  - `doku_pass` => `myPassword`
- Create your list of servers
 - SERVERS.txt ...
```
servername.domain
servername.domain|username|password
```
## Running 
 - Run via `cscript.exe`:
  - `cscript sydi-wrapper_DW.vbs -tSERVERS.txt`
