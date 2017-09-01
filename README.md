# NugetMonoCrash

Steps to reproduce crash:

1: Download TeamCity 2017.1.3 (build 46961) from https://www.jetbrains.com/teamcity/ 

2: Setup a teamcity server on localhost and intall Nuget 4.3.0 inside http://localhost:8111/admin/admin.html?item=toolInstallTab

3: Make a new project inside teamcity, and call it 'Test'
4: Connect this repo to VSC
5: Create a new 'Build configuration'
6: Attach NugetMonoCrash repo
7: Configure mannually build steps
8: Add a commandline with the following skript

cd Xamarin.InAppPurchase/Xamarin.InAppPurchase.Droid
msbuild /p:Configuration=Release

9: add a Nuget Pack
10: Set Specification files = Xamarin.InAppPurchase/Xamarin.InAppPurchase.Droid/Xamarin.InAppPurchase.Droid.csproj
11: set Output Directory = nuget
12: Enable 'Publish created packages to build artifacts'
13: run and see the crash

