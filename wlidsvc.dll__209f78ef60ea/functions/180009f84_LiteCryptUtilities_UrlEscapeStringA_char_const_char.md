# LiteCryptUtilities::UrlEscapeStringA(char const *,char * *)

- ea: `0x180009f84`
- end: `0x18000a34e`
- name: `?UrlEscapeStringA@LiteCryptUtilities@@YAJPEBDPEAPEAD@Z`
- size: `970`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, const char *, char **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180112bd0`
- `0x180113d7c`

## callees

- `0x180009f00`
- `0x180009f84`
- `0x18000a354`
- `0x18000a36c`
- `0x18000c050`
- `0x18001a9c0`
- `0x18001ad00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a0e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a16e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a238`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a0e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a16e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a28a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a0a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a28a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a098`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a126`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a098`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a126`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a1f0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a280`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a1f0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a280`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x18000a1a8`
- `api-ms-win-core-url-l1-1-0!UrlEscapeW` at `0x18000a1a8`

## string_xrefs

- `0x18000a1b5`: `hr = UrlEscapeW(spInputWideCharBuffer, spEscapedWideCharBuffer, &escapedWideCharBufferLength, URL_ESCAPE_PERCENT|URL_ESCAPE_ASCII_URI_COMPONENT|URL_ESCAPE_AS_UTF8|URL_ESCAPE_SEGMENT_ONLY )`

## pseudocode

```c

```
