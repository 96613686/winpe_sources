# FindFiles(ushort const *,gsl::span<ushort const * const,-1>,gsl::span<ushort const * const,-1>,bool)

- ea: `0x180057b04`
- end: `0x180057f25`
- name: `?FindFiles@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGV?$span@QEBG$0?0@gsl@@1_N@Z`
- size: `1057`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800582a8`
- `0x18005a8c8`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180006660`
- `0x180022d10`
- `0x180024ae4`
- `0x180025228`
- `0x18002d68c`
- `0x18002f94c`
- `0x180057b04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057d9d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180057d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057e61`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180057e8d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180057e8d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180057dc3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180057dc3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180057c76`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180057c76`

## string_xrefs

- `0x180057ef1`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x180057f0d`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`

## pseudocode

```c

```
