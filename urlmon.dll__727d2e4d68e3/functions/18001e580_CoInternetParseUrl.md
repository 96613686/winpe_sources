# CoInternetParseUrl

- ea: `0x18001e580`
- end: `0x18001ea94`
- name: `CoInternetParseUrl`
- size: `1300`
- prototype: `HRESULT __stdcall(LPCWSTR pwzUrl, PARSEACTION ParseAction, DWORD dwFlags, LPWSTR pszResult, DWORD cchResult, DWORD *pcchResult, DWORD dwReserved)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c0c0`
- `0x18001eaa0`
- `0x18001fca0`
- `0x1800fa834`

## callees

- `0x18001e4d0`
- `0x18001e580`
- `0x18001fc10`
- `0x180024ea0`
- `0x180077a40`
- `0x18012862e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001e881`
- `msvcrt!memcpy_s` at `0x18001e8ad`
- `msvcrt!memcpy_s` at `0x18001e881`
- `msvcrt!memcpy_s` at `0x18001e8ad`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x18001e69e`
- `api-ms-win-core-url-l1-1-0!UrlCanonicalizeW` at `0x18001e69e`
- `api-ms-win-core-url-l1-1-0!UrlGetLocationW` at `0x18001e9a3`
- `api-ms-win-core-url-l1-1-0!UrlGetLocationW` at `0x18001e9a3`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18001e95c`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18001e95c`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x18001e6cf`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x18001e837`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x18001e6cf`
- `api-ms-win-core-url-l1-1-0!UrlGetPartW` at `0x18001e837`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x18001e986`
- `api-ms-win-core-url-l1-1-0!UrlCreateFromPathW` at `0x18001e986`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x18001e908`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x18001e908`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18001e7e0`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18001e7e0`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x18001e932`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x18001e932`

## pseudocode

```c

```
