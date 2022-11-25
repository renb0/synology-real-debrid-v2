# Synology : real-debrid v2 host
Original repo by [max13fr](https://github.com/max13fr/synology-real-debrid-v2)

## What is this?
[Realdebrid](http://real-debrid.com/?id=7413222) is a premium downloader for many supported file host/sharing sites, it's much cheaper and economic than paying for multiple file sharing services.

**real-debrid v2 host** helps you download files using [Realdebrid](http://real-debrid.com/?id=7413222) with absolute ease, simply paste your file host/sharing links into the Download Station and wait for them to download.

## Getting Started
- Login to your Synology DiskStation, then launch **Download Station**
- Open **Settings** using the ⚙️ icon at the bottom left
- From the menu on the left, click **File Hosting**
- Click the **Add** button
- Click **Browse**, and add the **real_debrid_v2.host** file then click add
- Scroll the list to find **realdebrid_v2**, click it, then click the **Edit** button at the top
- For the form:
  - **Username** : Grab your token from [real-debrid.com/apitoken](http://real-debrid.com/apitoken) and paste into the Username field
  - **Password** : Enter anything - just make sure it isn't empty to avoid errors
- Click the **Verify** button, we should get **This is a premium account.** in the bottom left
- Click **Ok** for both windows

## Usage
In the **Download Station** you can now add your links by clicking the second icon in the top menu (Globe with a plus)
Any file host URLs will be detected and managed by the realdebrid host

## Contributing
Many file hosts have short URLs that go unnoticed by the script, my aim is to try to collect and update these URLs.

If you notice a URL missing, please add a comment to the [contribution issue here](https://github.com/renb0/synology-real-debrid-v2/issues/1)

## Editing

Add your own URLs to the `INFO` file
```json
{
    "authentication": "yes",
    "class": "RealDebridV2FileHost",
    "description": "Real-Debrid.com",
    "displayname": "Real-Debrid V2",
    "hostprefix": "1fichier.co,2shared.com, ...", /* Add your own */
    "module": "realdebrid_v2.php",
    "name": "realdebrid_v2",
    "version": "1"
}

```

`realdebrid_v2.php` negotiates with the realdebrid API, only needs modifying if realdebrid API changes

After modifying either `INFO` or `realdebrid_v2.php`, the files must be gzipped for upload:

`tar zcf realdebrid_v2.host INFO realdebrid_v2.php`

then upload the resulting file `realrebrid_v2.host`, as described in [Getting Started](#getting-started)
