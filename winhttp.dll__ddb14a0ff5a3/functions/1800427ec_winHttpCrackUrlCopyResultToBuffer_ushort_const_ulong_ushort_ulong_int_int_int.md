# winHttpCrackUrlCopyResultToBuffer(ushort const *,ulong,ushort * *,ulong *,int,int,int *)

- ea: `0x1800427ec`
- end: `0x180042b18`
- name: `?winHttpCrackUrlCopyResultToBuffer@@YAKPEBGKPEAPEAGPEAKHHPEAH@Z`
- size: `812`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *Src@<rcx>, unsigned int@<edx>, unsigned __int16 **@<r8>, unsigned int *@<r9>, int, int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180041f20`

## callees

- `0x18002acec`
- `0x180041eb0`
- `0x1800427ec`
- `0x180048cc0`
- `0x18007c288`
- `0x1800a3da8`
- `0x1800cdd7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042a48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042a48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042b0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042b0d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180042978`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800429af`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180042978`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800429af`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x1800428e2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x1800428e2`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeA` at `0x180042902`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeA` at `0x180042902`

## pseudocode

```c

```
