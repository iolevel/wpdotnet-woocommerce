# WooCommerce for .NET

This project builds WooCommerce from the sources on top of .NET. It can be used as a dependency by a regular ASP.NET Core application or self-hosted.

## Background

First, we created a project called [WpDotNet](https://github.com/iolevel/wpdotnet-sdk) - WpDotNet is the entire [WordPress](https://wordpress.org/download/) compiled to a .NET `.dll` using [PeachPie](https://peachpie.io) - the PHP to .NET compiler. In addition, it provides a few APIs written purely in C# to add _WordPress_ as [middleware](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/middleware/?view=aspnetcore-8.0) to a new or existing ASP.NET Core application.

With WordPress compiled to a .NET assembly, including all the functions and classes compiled along with strongly typed metadata, we wrapped it in a NuGet package. We can then use this as a dependency to build WordPress plugins separately as .NET assemblies, as well.

See [PeachPie](https://www.peachpie.io/) for more details, and please consider supporting us on [Patreon](https://www.patreon.com/pchpcompiler) to get access to release builds and nightly builds, a private forum, custom tutorials and blogs and much more 😊

## Sample App

See the `app` folder with a minimal ASP.NET Core application. It references the WpDotNet package and WooCommerce project.

The sample app requires you to start MySql by yourself, port 3306, having database `wordpress`.

## How to use WooCommerce on .NET?

> TBD

## Structure

- `woocommerce`

    Copy of [WooCommerce](https://woocommerce.com/download/) sources
    
- `woocommerce/woocommerce.msbuildproj`

    MSBuild project file that utilizes [PeachPie](https://peachpie.io) compiler to compile `.php` source files to a .NET `.dll` assembly. The project references all of WordPress from a NuGet package (see [WpDotNet](https://github.com/iolevel/wpdotnet-sdk)).

- `global.json`

    Versions of [PeachPie](https://peachpie.io) and [WpDotNet](https://github.com/iolevel/wpdotnet-sdk) used for compilation. Versions need to correspond to each other.

- `app`

    Sample ASP.NET Core application. Run `dotnet run` within the directory to launch WordPress with WooCommerce. Open the app on http://localhost:5004 .

## Disclaimer

**Work in progress**. Based on our discussion on [discord/peachpie.io](https://discord.com/channels/1198334116182102177/1198335586222743594).
