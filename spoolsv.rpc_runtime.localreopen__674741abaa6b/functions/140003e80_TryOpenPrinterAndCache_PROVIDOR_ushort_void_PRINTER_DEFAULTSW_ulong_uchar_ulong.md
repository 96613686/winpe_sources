# TryOpenPrinterAndCache(_PROVIDOR *,ushort *,void * *,_PRINTER_DEFAULTSW *,ulong *,uchar *,ulong)

- ea: `0x140003e80`
- end: `0x140003f67`
- name: `?TryOpenPrinterAndCache@@YAKPEAU_PROVIDOR@@PEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAKPEAEK@Z`
- size: `231`
- prototype: `unsigned int __usercall@<eax>(struct _PROVIDOR *@<rcx>, NRouter *this@<rdx>, void **@<r8>, struct _PRINTER_DEFAULTSW *@<r9>, unsigned int *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005630`

## callees

- `0x140003e80`
- `0x140003f70`
- `0x1400131fc`
- `0x140072f1c`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003f2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003f2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003f02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003f02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f3e`

## pseudocode

```c

```
