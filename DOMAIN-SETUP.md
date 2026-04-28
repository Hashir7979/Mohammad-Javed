## Custom Domain: whysmartpeoplestaybroke.com

1. Purchase the domain from Namecheap, Google Domains, or Cloudflare Registrar.
2. In Netlify → Site settings → Domain management → Add custom domain.
3. Enter: whysmartpeoplestaybroke.com
4. At your registrar, set DNS:
   - CNAME record: www → [your-netlify-subdomain].netlify.app
   - A record: @ → 75.2.60.5 (Netlify load balancer)
   - Or use Netlify DNS (easier): change nameservers to dns1.p01.nsone.net, dns2.p01.nsone.net, dns3.p01.nsone.net, dns4.p01.nsone.net
5. In Netlify → Enable HTTPS (automatic via Let's Encrypt).
6. Set "Force HTTPS" to on.
7. Verify: visit https://whysmartpeoplestaybroke.com — should load with padlock.
