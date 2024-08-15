Web Widget for Proxmox API calls, but should be adaptable to other platforms

Instructions:

(Assumptions, using the same server for web page hosting and reverse-proxy - but this can easily be adjusted if these are different servers).

API-Widget_v0.1.0.html
  [add this html code to a webserver - use the reverse proxy port 80 to bypass tls/certificates, etc.]
    [ also, update the proxmox node name in the html file list of endpoint to your specific proxmox node, it may aleady be 'proxmox' by default.  There are 7 example VM/LXC example endpoints the list which can be adjusted]
    [access for this API-Widget is set in the nodeapp.conf file below to port 3003, ex. http://192.168.1.2:3003, adjust per your preferences]
  

nodeapp.conf
  [update 'server_name' with reverse-proxy ip address and 'proxy_pass' with https://proxmox ip address:8006]
  [add this configuration file/or block to existing file to your reverse-proxy] - this will eliminate the CORS 'cross-origin-resource-sharing' errors that arise from web-browser based API calls

In summary:

web server/reverse-proxy -> hosts API-Widget web page -> use web form to request keys/tokens from reverse-proxy address on port 80, then use the lower section of the web page API endpoint -> Send API request (drop-down or custom typed endpoint -> reverse proxy which sends -> to Proxmox and back to web page to display the response

