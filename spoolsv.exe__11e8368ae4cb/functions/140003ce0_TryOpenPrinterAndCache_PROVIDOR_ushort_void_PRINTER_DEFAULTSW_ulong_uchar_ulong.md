# TryOpenPrinterAndCache(_PROVIDOR *,ushort *,void * *,_PRINTER_DEFAULTSW *,ulong *,uchar *,ulong)

- ea: `0x140003ce0`
- end: `0x140003dae`
- name: `?TryOpenPrinterAndCache@@YAKPEAU_PROVIDOR@@PEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAKPEAEK@Z`
- size: `206`
- prototype: `unsigned int __usercall@<eax>(struct _PROVIDOR *@<rcx>, NRouter *this@<rdx>, void **@<r8>, struct _PRINTER_DEFAULTSW *@<r9>, unsigned int *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004e90`

## callees

- `0x140003ce0`
- `0x140003db4`
- `0x140011f1c`
- `0x14006c280`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003d81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003d81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003d5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d8c`

## pseudocode

```c

```
