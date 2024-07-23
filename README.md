# WooCommerce for .NET

This project builds WooCommerce from sources to .NET. It can be used as a dependency by regular ASP.NET Core application and self-hosted.

## Background

First, we have created project called [WpDotNet](https://github.com/iolevel/wpdotnet-sdk) - WpDotNet is entire [WordPress](https://wordpress.org/download/) compiled to .NET `.dll` using the [PeachPie](https://peachpie.io) - the PHP to .NET Compiler. In addition it provides a few APIs written purely in C# to add _WordPress_ as a [middleware](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/middleware/?view=aspnetcore-8.0) to new or existing ASP.NET Core application.

Once there is WordPress as a .NET assembly, with all the functions and classes compiled in a strongly typed metadata, we wraped it in a NuGet package, and using this as a dependency we can build WordPress plugins separately as .NET assemblies as well.

See [PeachPie](https://www.peachpie.io/) for more details, and consider supporting us on [Patreon](https://www.patreon.com/pchpcompiler) 😊

## Sample App

See the `app` folder with minimal ASP.NET Core application. It references WpDotNet package and WooCommerce project.

The sample app requires you to start MySql by yourself, port 3306, having database `wordpress`.

## How to use WooCommerce on .NET?

> TBD

## Structure

- `woocommerce`

    Copy of [WooCommerce](https://woocommerce.com/download/) sources
    
- `woocommerce/woocommerce.msbuildproj`

    MSBuild project file that utilizes [PeachPie](https://peachpie.io) compiler to compile `.php` source files to .NET `.dll` assembly. The project references the entire WordPress from NuGet package (see [WpDotNet](https://github.com/iolevel/wpdotnet-sdk)).

- `global.json`

    Versions of [PeachPie](https://peachpie.io) and [WpDotNet](https://github.com/iolevel/wpdotnet-sdk) used for compilation. Versions need to correspond to each other.

- `app`

    Sample ASP.NET Core application. Run `dotnet run` within the directory to launch WordPress with WooCommerce. Open the app on http://localhost:5004 .

## Disclaimer

**Work in progress**. Based on our discussion on [discord/peachpie.io](https://discord.com/channels/1198334116182102177/1198335586222743594).