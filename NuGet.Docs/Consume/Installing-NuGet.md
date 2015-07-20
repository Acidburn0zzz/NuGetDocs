# Installing and Updating NuGet Client
NuGet is available for the following clients:

1. **Visual Studio 2013**: [Visual Studio Extension Gallery](http://visualstudiogallery.msdn.microsoft.com/4ec1526c-4a8c-4a84-b702-b21a8f5293ca)
1. **Visual Studio 2010 and 2012**: [Visual Studio Extension Gallery](http://visualstudiogallery.msdn.microsoft.com/27077b70-9dad-4c64-adcf-c7cf6bc9970c)
1. **Visual Studio 2015**: [Visual Studio Extension Gallery](https://visualstudiogallery.msdn.microsoft.com/5d345edc-2e2d-4a9c-b73b-d53956dc458d)
1. **Command-Line Utility**: [Direct Download](https://nuget.org/nuget.exe)

## Visual Studio 2010, 2012 and 2013
For Visual Studio 2010, NuGet is available through the Visual Studio Extension Manager.  The extension can be installed into the Professional, Premium, and Ultimate editions.  Additionally, the extension can be installed into Visual Web Developer 2010 Express

Starting with Visual Studio 2012, NuGet is included in every edition (except Team Foundation Server) by default.  Updates to NuGet can be found through the Extension Manager.

To check if your copy of Visual Studio already has the NuGet extension, look for *Library Package Manager* in the Tools menu of Visual Studio.  If your copy of Visual Studio does not already have the Library Package Manager (NuGet) extension, you can install it using the Extension Manager.

To download the extension for Visual Studio 2010 and 2012 directly, it can be found on the [Visual Studio Extension Gallery](http://visualstudiogallery.msdn.microsoft.com/27077b70-9dad-4c64-adcf-c7cf6bc9970c)
and for Visual Studio 2013 directly, it can be found here on the [Visual Studio Extension Gallery](http://visualstudiogallery.msdn.microsoft.com/4ec1526c-4a8c-4a84-b702-b21a8f5293ca).

## Command-Line Utility
A command-line NuGet utility is also available.  This utility can be used to create, publish, and download packages.  This utility is also used for NuGet Package Restore which allows packages to be omitted from source control but downloaded as part of your build.

The latest version of the nuget.exe command-line tool is always available from [https://nuget.org/nuget.exe](https://nuget.org/nuget.exe).

# Using the Visual Studio Extension Manager

In Visual Studio, click **Tools** and then **Extension Manager**.  Naviging to **Online**, find the **NuGet Package Manager** extension and click **Download**.

![Extension Manager showing NuGet](/images/consume/extension-manager-with-nuget.png)

In the **Installer** dialog box, click **Install**.

![Visual Studio Extension Installer](/images/consume/visual-studio-extension-installer.png)

When installation is complete, close and re-open Visual Studio.

![Visual Studio Extension Installer Complete](/images/consume/visual-studio-extension-installer-complete.png)

NuGet is now ready to use.

# Updating NuGet in Visual Studio
You can update NuGet using the Visual Studio *Extension Manager*.  Navigate to the Extension Manager and click on the Updates tab to check for updates.

If there is a new version of NuGet you will see it in the list of available updates.

![Extension Manager showing a new version of NuGet available](/images/consume/visual-studio-extension-update-check.png)

Select NuGet in the list and click **Update**.  When the update is complete, close and re-open all open instances of Visual Studio.

# Installing a CI build

If you want to run the very latest unreleased build of NuGet, you can
[install it from the Build Server](http://build.nuget.org/NuGet.Tools.vsix).

**Important note**: the official NuGet build is signed by Microsoft, while the one from the Build Server is not. For that reason, Visual Studio will not let you
install a CI build if you already have an official build installed. If you do, you'll get an error that looks like:

*The installed version of 'NuGet Package Manager' is signed, but the update version is not signed. Therefore Extension Manager cannot install the update.*

To avoid this issue, you need to uninstall the official build (from the VS extension manager) before installing the unsigned build. Likewise, please uninstall the unsigned build
before going back to an official build. However, you don't need to do this from going to a unsigned build to a newer unsigned build. If Visual Studio won't allow you to uninstall the extension (the Uninstall button is disabled), then you likely need to restart Visual Studio using "Run as Administrator."
