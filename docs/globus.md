=Globus File Transfer=
[https://www.globus.org/Globus] is a standard free open-source software for robust transfer of large amounts without having to monitor the connection, and can work transparently through firewalls. It is also convenient service [https://www.globus.org/our-story from the University of Chicago], which provides access to a network of computers running the Globus software, free for personal use.

==Globus basics==

Globus data transfer runs between two software installations, called [https://docs.globus.org/faq/globus-connect-endpoints endpoints]. The transfer is initiated and can be monitored from a web interface. There are two kinds of endpoints, ''Server'' and ''Personal''. A subscription is required to run a Server endpoint or for transfer between two Personal endpoints. Without subscription, at least one of the endpoints needs to be a Server endpoint. Users gain access to a Server endpoint by existing login credentials to that endpoint, such as system login and password, federated login, or a token. A Personal endpoint runs as the user and does not require any additional authentication. 

With a subscription, you can set up your own Globus Server endpoints connecting to your own account at a cloud platform, such as {{wp|Google Drive}} or {{wp|Amazon S3}}, but there seem to be no general, publicly accessible Globus endpoints on such cloud platforms.

==How to connect to Globus==

CU Denver does not have Globus subscription and thus we do not have any [https://www.globus.org/globus-connect-server Globus Connect Server]  endpoints. But you can install Globus Personal endpoint in your account on our Linux servers.

* Create the name and key for your endpoint: Log into [https://globus.org globus.org], make an account if you need to. Click Endpoints -> Add Globus Connect Personal Endpoint -> Display name. Choose  a name and press the Copy button to copy the key. 

* Log into your account on the `math-alderaan` or `clas-compute, Install the endpoint from command line, following the [https://docs.globus.org/how-to/globus-connect-personal-linux/#globus-connect-personal-cli instructions from globus.org] with a grain of salt:
<pre>
mkdir globus; cd globus
wget https://s3.amazonaws.com/connect.globusonline.org/linux/stable/globusconnectpersonal-latest.tgz
tar xvfz globusconnectpersonal-latest.tgz
cd globusconnectpersonal-2.3.3  # replace the numbers by the version from the downloaded file
./globusconnectpersonal -setup the-key-you-copied-above # use your Paste keyboard shortcut
</pre>
* Run the endpoint:
<pre>
screen -S globus
./globusconnectpersonal -start
</pre>
* Kill the terminal window or detach from the terminal session by Ctrl-A d. Your endpoint now runs in a virtual terminal until system reboot. You can reconnect to the virtual terminal if you need to by <tt>screen -r globus</tt>

* Go to your account on globus.org and search for your personal endpoint name. You can now transfer data between this endpoint and any Server endpoint you have credentials for.

* Optional: Make a Personal endpoint on your computer. Log into [https://globus.org globus.org], click Endpoints -> Add Globus Connect Personal Endpoint -> Display name. Copy the key, click the download link for your computer type, and follow instructions. You can now transfer data between any Server endpoint and your computer.

==Security notes==
* Personal endpoint makes an outgoing connection which is typically not blocked by firewalls and does not need any incoming ports open. 
* Personal endpoint runs as you and in principle it has access to any files on the computer that you have. 
* Personal endpoint seems to refuse access to files outside of your home directory, even if they are owned by you, such as on another disk.
* Your personal endpoint is visible to anyone but it is accessible from your own Globus account only.

==Works with==
This guide was tested in the following environments. It should work in other cases too.

* Globus connect software and servers as of December 2017
* CENTOS 6.5, 6.8, 6.9, OSX 10.11

==Some Globus Connect Server endpoints==
* [https://hpc.nih.gov/docs/globus_endpoint.html NIH]
* [https://portal.xsede.org/software/globus XSEDE]
* [https://www.rc.colorado.edu/support/user-guide/file-transfer.html CU Boulder]
* [https://www.chpc.utah.edu/documentation/software/globus.php University of Utah]
* [https://www2.cisl.ucar.edu/resources/storage-and-file-systems/globus-file-transfers NCAR]

==External links==

https://docs.globus.org/how-to/globus-connect-personal-windows/

https://www2.cisl.ucar.edu/resources/storage-and-file-systems/globus-file-transfers

https://nar.ucar.edu/2014/cisl/ncar%E2%80%99s-data-sharing-service-globus-plus  "dropbox for big data"

https://www.globus.org/globus-connect-server

https://www.globus.org/subscriptions

https://www2.vrdc.cornell.edu/news/repost-ecco-important-changes-to-globus-web-site-and-products/

https://docs.globus.org/faq/globus-connect-endpoints/ : Globus Connect Personal can execute a transfer as long as either the source or destination endpoint has a routable IP address (which is the case for almost all Globus Connect Server endpoints).

http://help.unc.edu/help/globus-connect-file-transfer/ Example

https://docs.globus.org/how-to/access-google-drive/

https://ci.uchicago.edu/press-releases/globus-expands-data-services-accelerate-secure-cancer-research ''...expect to become eligible for HIPAA business associate agreements in mid-2018.''

