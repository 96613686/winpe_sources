# _InternetCrackUrlA(char const *,ulong,ulong,URL_COMPONENTSA *,int,int,char * *)

- ea: `0x180073ec0`
- end: `0x180074754`
- name: `?_InternetCrackUrlA@@YAHPEBDKKPEAUURL_COMPONENTSA@@HHPEAPEAD@Z`
- size: `2196`
- prototype: `__int64 __usercall@<rax>(LPCSTR pszStr2@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct URL_COMPONENTSA *@<r9>, int, int, char **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180073230`
- `0x180073e20`

## callees

- `0x180017a70`
- `0x18006e170`
- `0x180073ec0`
- `0x18007475c`
- `0x1800c7560`
- `0x18014a7a0`
- `0x180154882`
- `0x1801d09dc`
- `0x1801e1790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007419b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007419b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074513`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074620`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074513`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074620`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074406`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074692`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800746ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074406`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074692`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800746ac`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18007463c`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18007463c`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeA` at `0x1800746e1`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeA` at `0x18007471b`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeA` at `0x1800746e1`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeA` at `0x18007471b`

## pseudocode

```c

```
