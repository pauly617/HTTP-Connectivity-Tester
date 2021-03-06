# macOS update connectivity tests

## Usage

1. Import this file: `Import-Module .\MacOSUpdateConnectivity.psm1`
1. Run one of the following:
    * `$connectivity = Get-MacOSUpdateConnectivity`
    * `$connectivity = Get-MacOSUpdateConnectivity -Verbose`
    * `$connectivity = Get-MacOSUpdateConnectivity -PerformBlueCoatLookup`
    * `$connectivity = Get-MacOSUpdateConnectivity -Verbose -PerformBlueCoatLookup`
1. Filter results: `$connectivity | Format-List -Property Blocked,TestUrl,UnblockUrl,DnsAliases,IpAddresses,Description,Resolved,ActualStatusCode,ExpectedStatusCode,UnexpectedStatus`
1. Save results to a file: `Save-HttpConnectivity -Objects $connectivity -FileName ('MacOSUpdateConnectivity_{0:yyyyMMdd_HHmmss}' -f (Get-Date))`

## Tested URLs

| Test URL | URL to Unblock | Description |
| -- | -- | -- |
| <https://swscan.apple.com> | <https://swscan.apple.com> | |
| <https://swcdnlocator.apple.com> | <https://swcdnlocator.apple.com> | |
| <https://swdownload.apple.com> | <https://swdownload.apple.com> | |
| <https://swcdn.apple.com> | <https://swcdn.apple.com> | |
| <https://swdist.apple.com> | <https://swdist.apple.com> | |

## References

* [Requirements for Software Update service](https://support.apple.com/en-us/HT200149)
* [OS X: Server addresses used by Software Update](https://support.apple.com/en-us/HT202943)
* [OSX Apple Updates?](https://github.com/bntjah/lancache/issues/36)
* [Apple 17.0.0.0/8 Services](https://www.richard-purves.com/2016/09/10/apple-services/)
* [If you aren't getting Apple push notifications](https://support.apple.com/en-us/HT203609)