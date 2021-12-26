# Plex Media Server Overview
> *By TitaniumCoder477, mrd0sgpe9@mozmail.com*

Sometimes it's great to try something before you put the time (and money) into it! With Linux and Plex and an old computer, you can accomplish this!

## Try out Linux and Plex with an old computer:
For this, you'll need and old computer with at least 2 cores, 6GB RAM, and 30GB hard drive space. You can use a laptop or a desktop.
1. You would install Ubuntu Desktop 21.04 on your old computer: https://ubuntu.com/download/desktop
2. You would install Plex Media Server: https://snapcraft.io/plexmediaserver
3. You would setup an DHCP reservation on your router for the computer so that the IP doesn't change or get reused by another device. If you are not sure how to do this, you can google your router's make & model plus "DHCP reservation" keywords and usually find the info you need.

At this point, you could easily test Plex on your local network, i.e. from another computer connected to the same hardwire or wireless at your home. However, if you also want to test the apps and streaming from a remote location, then you'll need to follow this step as well:
1. You would also configure a port forward rule on router to this new IP, which will facilitate use of the apps from any location and from playing from any location via your https://plex.tv web account. This shows how to do that: https://portforward.com/plex/. And this database may have your router make & model and provide specific steps for it: https://portforward.com/router.htmYou would add a local library path and put a move or two on it (whatever you have space for)

You should keep in mind that Plex might run slower than desired on an old computer. The point of this section is to test the interface and how it works etc. so you can then decide if it's worth setting up a better system.

The minimum system requirements for Ubuntu Desktop are: 2Ghz, dual core; 4GB RAM, 25GB hard drive
The minimum system requirements for Plex Media Server are: i3 or equivalent, 2GB of RAM
So the total minimum system requirements would be: 2 cores, 6GB RAM, 25GB hard drive + more for video storage

Now, if you test and like everything, then you might want to setup a better system!

## Setup a "legit" Plex Media Server

If all you're using Plex for is the TV, movies, podcasts, et.c then you may not have any of your own data, for example your home videos, to store on your Plex Media Server. In this case, you could probably skip the NAS hardware below. However, if you do plan to store your home video data, or other movies you might convert from DVD to MPEG files to stream from your Plex Media Server, then you really should invest in a NAS or "Network Attached Storage" device. The main reason is because it will spread your data across 2 or more hard drives in a "RAID" array which provides fault tolerance in the event that one drive dies. Basically, if one drive does, you don't lose everything, as long as you replace that drive before any of the other dies! This doesn't replace a good "backup" of your data, but it does help to avoid loss from drive failure.

*Again, NEVER store your important data on just a single hard drive UNLESS you are also backing that data up to another drive or location!*

### Synology NAS
This is my brand of choice simply because of the quality of hardware and operating system. You buy the unit, and you get a limited 1 or 2 year hardware warranty and lifetime software support. There is no monthly cost (i.e. no subscription fee or anything). There are quite a few "apps" that you can use on the Synology NAS with varying degrees of usefulness and quality. I recommend the product based on none of these, only on the hardware and operating system quality.

- The benefit of storing your videos and pictures on this device is that it uses RAID technology to ensure that if one or more hard drives fail, you don't lose all the data.
- You can browse the models at https://www.synology.com/en-us/products?chassis=Desktop.
- Towards the bottom you'll find the Value and J Series, both of which are inexpensive options for home use.
- I have the DS220j which is the cheapest NAS that has two bays. It serves my purposes fine. I would recommend a 2-bay or 4-bay such as that model, DS218 or DS418.
- (If you started out with an inexpensive 2-bay model and really liked it but eventually wanted to upgrade, you could migrate your data to a 4-bay model and then give the 2-bay to one of your kids)
- With a Synology NAS, you can optionally sync your data to the Backblaze B2 cloud storage for an inexpensive offsite copy (approx $5 per TB of cloud storage). Backblaze is a publicly traded US company which means they are 100% subject to SEC regulations concerning privacy and security.
- Once you settle on a model, you can purchase it directly from Amazon.com.

### Hard drives for the NAS
The NAS unit doesn't come with any drives, so that the new owner can "build out the space" according to need and desire. Virtually any 3.5" SATA drives will work, but you always want to have the same model and size drives (usually a requirement for RAID).
- Keep in mind that drives are pretty expensive, so if you get a 4-bay NAS, you'll end up with more drive cost!
- If you want new drives, I recommend Western Digital Red or Red Pro. Some "Red" modules have the acronym "SMR." Avoid these. It's a long story, but they are not good NAS drives. Only get WD drives that have the "CMR" acronym.
- New drives will have warranties, either 3 or 5 years, but they are more expensive than refurbished drives.
- You also have lots of drive size options. For example, if you bought a 2-bay NAS and you wanted approx 10TB of storage, then you would get 2 x 10TB Western Digital Red or Red Pro drives. In a RAID1 array, the drives are mirrored so that if you lose one drive, the other drive still contains the exact same data. You have time to replace the failed drive, and the NAS will automatically mirror the contents from the remaining drive to the new drive, "rebuilding" the RAID1 and restoring health.
- If you would like to get a 4-bay unit out the gate and either partially or fully populate it with drives, you'll end up using RAID1 or RAID5 and need to use a calculator like this one to do the math: https://raidcalculators.com/usable-capacity.php. For example, if you get a 4-bay unit and three or four hard drives, then you'll use RAID5. But if you get a 4-bay unit and only populate two drives, leaving two bays empty for future expansion, you'll use RAID1 (same as if you got a 2-bay unit with 2 drives).

*Technically, you can run Plex Media Server on a NAS, but it can be very convoluted and difficult to setup and update. I recommend the NAS remain just the "storage location" of your data, and that you have a separate device that operates as the Plex Media Server.*

### Plex Media Server
#### Option 1: You could continue using your old computer, as long as it's performing fine for you
1. I would need to help you or provide you with guidance on how to map the Synology NAS file system to your Plex Media Server so that it "sees" the content as local.The Plex Media Server would then continue offering this content to any clients, just like your test did.
2. The actual content would remain on the NAS, which would protect it with RAID and (optionally) sync it offsite as a backup.
3. If your old computer died, you could easily setup a new Plex Media Server and just point it to your NAS once again.

#### Option 2: Raspberry Pi media server (+- $170)
**PRO:** Cheaper
**CON:** Less "power" so may not handle multiple people watching different things at the same time
1. You would purchase a Raspberry Pi 4 kit on Amazon.com (one with 8GB RAM). For example: https://www.amazon.com/dp/B08B6F1FV5/ref=twister_B08B6F6N34?_encoding=UTF8&psc=1
2. You would install Ubuntu Desktop 21.04: https://ubuntu.com/download/raspberry-pi
3. You would install Plex Media Server: https://snapcraft.io/plexmediaserver
4. You would setup a new DHCP reservation on your router for this device OR adjust the existing reservation to point to this instead of the new computer.
5. You would adjust the port forward rule on router to the new DHCP reservation (or if you adjusted the reservation to point to the new device, then no change would be needed here)
6. You would map the NAS to your media server

#### Option 3: Dell OptiPlex micro media server (+- $300)
**PRO:** Much more powerful
**CON:** More expensive

I am a big refurbished guy, as in I really like refurb hardware when done right. You can get amazing performance at a super low price. And you typically get plenty of mileage out of it too.

1. You would purchase a refurb like this one which is an i5 with 16TB RAM and a 256GB SSD (plenty to run Linux and Plex): https://www.amazon.com/dp/B07F2TW48L/ref=cm_sw_r_tw_dp_7NTCGDH154Q52MP1BKBV?_encoding=UTF8&psc=1
2. You would install Ubuntu Desktop 21.04: https://ubuntu.com/download/desktop
3. You would install Plex Media Server: https://snapcraft.io/plexmediaserver
4. You would adjust the port forward rule on router to the new DHCP reservation (or if you adjusted the reservation to point to the new device, then no change would be needed here)
5. You would map the NAS to your media server

## Conclusion

Hopefully the video overview and these details will get you on the right path to setting up your own Plex Media Server! It's a great project and not too difficult to setup. Enjoy!

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.