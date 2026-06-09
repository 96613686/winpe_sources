# GetMailSyncHandler(IMsgStore *,HINSTANCE__ * *,IMailSyncHandler * *)

- ea: `0x18007892c`
- end: `0x180078b81`
- name: `?GetMailSyncHandler@@YAJPEAUIMsgStore@@PEAPEAUHINSTANCE__@@PEAPEAVIMailSyncHandler@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(struct IMsgStore *, HINSTANCE *, struct IMailSyncHandler **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180078588`
- `0x1800bbf54`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18007892c`
- `0x180078b94`
- `0x180078bb4`
- `0x18007ba18`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180078a2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180078a2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078a8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180078a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a96`
- `CEMAPI!MAPIFreeBuffer` at `0x1800789e5`
- `CEMAPI!MAPIFreeBuffer` at `0x180078b59`
- `CEMAPI!MAPIFreeBuffer` at `0x1800789e5`
- `CEMAPI!MAPIFreeBuffer` at `0x180078b59`

## string_xrefs

- `0x1800789c9`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x180078a63`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`
- `0x180078ad8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\onesynchelper.cpp`

## pseudocode

```c

```
