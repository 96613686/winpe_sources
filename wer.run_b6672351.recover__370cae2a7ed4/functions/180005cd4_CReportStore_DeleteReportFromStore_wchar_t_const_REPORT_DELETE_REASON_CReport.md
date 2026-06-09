# CReportStore::DeleteReportFromStore(wchar_t const *,REPORT_DELETE_REASON,CReport *)

- ea: `0x180005cd4`
- end: `0x180006163`
- name: `?DeleteReportFromStore@CReportStore@@QEAAJPEB_WW4REPORT_DELETE_REASON@@PEAVCReport@@@Z`
- size: `1167`
- prototype: `int __high(const wchar_t *, enum REPORT_DELETE_REASON, struct CReport *)`
- caller_count: `4`
- callee_count: `25`
- tags: `loader_planting`

## callers

- `0x1800053e0`
- `0x18006a600`
- `0x18006ac00`
- `0x18006df10`

## callees

- `0x180005cd4`
- `0x18000616c`
- `0x1800062bc`
- `0x18000753c`
- `0x180007848`
- `0x180008164`
- `0x18000cf50`
- `0x18000cf6c`
- `0x18000da00`
- `0x18000db80`
- `0x180020680`
- `0x18002219c`
- `0x180025848`
- `0x18002d96c`
- `0x1800318c8`
- `0x18003fb94`
- `0x18004208c`
- `0x1800424e8`
- `0x1800479ac`
- `0x18004cfc0`
- `0x1800544c0`
- `0x180074268`
- `0x180075690`
- `0x180076de4`
- `0x1800a9768`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006103`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006103`
- `ext-ms-win-wer-xbox-l1-2-1!XerCleanupInternalFile` at `0x180005ea2`
- `ext-ms-win-wer-xbox-l1-2-1!XerCleanupInternalFile` at `0x180005ea2`

## string_xrefs

- `0x180005d3c`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180005d66`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

## pseudocode

```c

```
