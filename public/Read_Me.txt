
Instructions:

(Assumptions, using the same server for web page hosting and reverse-proxy - but this can easily be adjusted if these are different servers).

API-Widget_v0.1.0.html
  [add this html code to a webserver - use the reverse proxy port 80 to bypass tls/certificates, etc.]
  

nodeapp.conf
  [update 'seerver_name' with reverse-proxy ip address and 'proxy_pass' with https://proxmox ip address:8006]
  [add this configuration file/or block to existing file to your reverse-proxy] - this will eliminat the CORS 'cross-origin-resource-sharing' errors that arise from web-browser based API calls

In summary:

web server/reverse-proxy -> hosts API-Widget web page -> use web form to request keys/tokens from reverse-proxy address on port 80 -> web page API endpoint - Send API request -> reverse proxy which sends -> to Proxmox and back to web page to display the response

