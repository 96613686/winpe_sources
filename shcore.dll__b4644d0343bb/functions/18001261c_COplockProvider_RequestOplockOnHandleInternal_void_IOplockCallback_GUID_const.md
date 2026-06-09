# COplockProvider::RequestOplockOnHandleInternal(void *,IOplockCallback *,_GUID const &)

- ea: `0x18001261c`
- end: `0x1800128fb`
- name: `?RequestOplockOnHandleInternal@COplockProvider@@AEAAJPEAXPEAUIOplockCallback@@AEBU_GUID@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(COplockProvider *__hidden this, HANDLE hSourceHandle, struct IOplockCallback *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180023d40`
- `0x180051380`

## callees

- `0x180011ae8`
- `0x180011bf0`
- `0x18001261c`
- `0x180012904`
- `0x180012b00`
- `0x180012e68`
- `0x18003f05c`
- `0x18003f6f4`
- `0x180053bd8`
- `0x180054410`
- `0x18005a810`
- `0x1800836b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012723`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012723`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800126bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800126c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800126bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800126c6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800126f3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800126f3`

## pseudocode

```c

```
