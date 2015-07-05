Gatech Android Printing
=========================
##Goal
The goal for this app is to help you using georgia tech's printing Service at ease
with you android phone.

##Usage
* If you print from the within Georgia Tech network, you can print directly once you have printer configured.(TODO)

* Otherwise, you have to install [AnyConnect](https://play.google.com/store/apps/details?id=com.cisco.anyconnect.vpn.android.avf) first,
and choose Add New VPN Connection with Server Address anyc.vpn.gatech.edu, and then start Connection to Georgia Tech network. Once connected,
you can print as you are on campus.

##Notes
This plugin unpacks minimal Debian installation with CUPS included, and launches it using PRoot, then uses it for actual printing.
PRoot can be downlaoded from http://proot.me/
There is no JNI - Java code just calls lp, lpinfo, lpadmin etc commandline tools.

TODO:
=====
-   Add gatech printer to the CUPS server\( now you can do it manually through advanced interface with the help from [here](https://faq.oit.gatech.edu/content/how-install-oit-laptop-printing-linux)\). One thing need to mention is on configuring the queue,
instead of doing lpd://pharosQ3.ad.gatech.edu/laptop_black_xerox5550, you should add you gatech id like this lpd://wli345@pharosQ3.ad.gatech.edu/laptop_black_xerox5550.\)


-   Remove redundancy of this app.
-   Add status update once sent to printer.
-   Add support for 64-bit architectures.
-   Implement AdvancedPrintOptionsActivity:
-    Page margins
-    Collate copies
-    Resize print content to fit into less amount of pages, by reporting bigger paper size and rescaling it back when printing
-    All options configurable by lpoptions:
-     Paper type
-     Printer tray select
-     Print resolution
-    Booklet print
-   Print preview:
-    Show or hide print preview in advanced options
-    Change page margins inside print preview
-    Select and de-select pages for print preview
-   USB printers support, by forwaring calls from libusb to Java
-   Print on older devices and from older apps, using 'Share' button
-   Connect to non-local CUPS server: https://www.cups.org/documentation.php/doc-1.7/ref-client-conf.html
-   Command-line interface into CUPS installation
-   Add non-Samba printer by URL, share non-Samba printer
-   Search for IPP and Bonjour printers using cups-browsed
-   When printing to CUPS server, [CUPS web interface shows an error: "Failed to connect to system bus"](screenshots/cups-android-error.jpg)
-   Set LANG to make CUPS print localized error messages
-   When printing page range and multiple copies, CUPS collates pages and we don't want that
