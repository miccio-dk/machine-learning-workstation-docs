# X forwarding \(running software with GUI\)

X forwarding allows you to remotely run software with graphical interface, but visualize it in your local machine. This may be useful to run a browser \(and download content directly on the workstation\), MATLAB, a file viewer, or any other piece of software that can't be accessed from the command line. Please keep in mind that this should be adopted as a last resort only, as running graphical application through the network is considerably slow.

On Linux, all you have to do is connect to the workstation with the following command:

```bash
ssh -X ml_workstation
```

On OS X, you have to make sure to have [XQuartz](https://www.xquartz.org/) installed and be using its terminal app to run the command.

Once you are connected, simply launch the graphical application from the terminal \(e.g. type `firefox`\) and it will appear on a new window.

For more information, including how to get this to work on Windows, please refer to [this guide](https://uisapp2.iu.edu/confluence-prd/pages/viewpage.action?pageId=280461906)

