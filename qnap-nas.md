## Set up pi-hole on qnap nas

You can set up a pi-hole in a qnap nas with the container appliation. I basically followed these [instructions](https://discourse.pi-hole.net/t/pi-hole-docker-container-on-qnap-nas/34278).

## Allow access via external networks

If you have VLANS and the pi-hole serves as DNS on different networks, then you need to allow access on different networks. You will get a DNSMASQ warning if these setting are not changes. 

This [reddit thread comment](https://www.reddit.com/r/pihole/comments/rvpl2g/dnsmasq_warn_ignoring_query_from_nonlocal_network/) describes the fix:
```
This also helped me. I have a UDM Pro with several vLANs and last night I started getting "ignoring query from non-local network 192.168.0.xx..." on all vLANs but the one the RPi was assigned an IP address on (10.0.1.0). After reading your post I went to the pi-hole web gui under http://10.0.1.xx/admin/settings.php?tab=dns and set the Interface settings check box from "Allow only local requests to Bind only" to "Bind only to interface eth0" hit save and the problem went away. Thanks a lot for your post.
```


## References

- <https://discourse.pi-hole.net/t/pi-hole-docker-container-on-qnap-nas/34278>
- -<https://www.reddit.com/r/pihole/comments/rvpl2g/dnsmasq_warn_ignoring_query_from_nonlocal_network/>