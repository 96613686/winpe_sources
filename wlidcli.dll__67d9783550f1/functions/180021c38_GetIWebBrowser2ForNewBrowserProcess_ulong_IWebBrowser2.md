# GetIWebBrowser2ForNewBrowserProcess(ulong,IWebBrowser2 * *)

- ea: `0x180021c38`
- end: `0x180021e12`
- name: `?GetIWebBrowser2ForNewBrowserProcess@@YAJKPEAPEAUIWebBrowser2@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(unsigned int, struct IWebBrowser2 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180022180`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x180013638`
- `0x180021c38`
- `0x1800530e4`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021ce9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021ce9`
- `USER32!EnumWindows` at `0x180021ccc`
- `USER32!EnumWindows` at `0x180021ccc`
- `USER32!SendMessageTimeoutW` at `0x180021d19`
- `USER32!SendMessageTimeoutW` at `0x180021d19`
- `USER32!RegisterWindowMessageW` at `0x180021c85`
- `USER32!RegisterWindowMessageW` at `0x180021c85`
- `ext-ms-win-oleacc-l1-1-1!ObjectFromLresult` at `0x180021d3a`
- `ext-ms-win-oleacc-l1-1-1!ObjectFromLresult` at `0x180021d3a`

## string_xrefs

- `0x180021de9`: `Could not find Internet Explorer Window in 20 attempts, giving up...`

## pseudocode

```c

```
