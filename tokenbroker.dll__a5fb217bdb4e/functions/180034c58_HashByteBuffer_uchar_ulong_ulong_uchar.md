# HashByteBuffer(uchar *,ulong,ulong *,uchar * *)

- ea: `0x180034c58`
- end: `0x180034e13`
- name: `?HashByteBuffer@@YAJPEAEKPEAKPEAPEAE@Z`
- size: `443`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180070660`

## callees

- `0x180034c58`
- `0x180034e20`
- `0x180034e8c`
- `0x18007f4cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034df8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034df8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034d15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034d15`
- `bcrypt!BCryptHashData` at `0x180034d53`
- `bcrypt!BCryptHashData` at `0x180034d53`
- `bcrypt!BCryptCreateHash` at `0x180034cb6`
- `bcrypt!BCryptCreateHash` at `0x180034cb6`
- `bcrypt!BCryptFinishHash` at `0x180034dd1`
- `bcrypt!BCryptFinishHash` at `0x180034dd1`
- `bcrypt!BCryptDestroyHash` at `0x180034cf8`
- `bcrypt!BCryptDestroyHash` at `0x180034cf8`
- `bcrypt!BCryptGetProperty` at `0x180034d98`
- `bcrypt!BCryptGetProperty` at `0x180034d98`

## string_xrefs

- `0x180034cd9`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x180034daf`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x180034ddf`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`

## pseudocode

```c

```
