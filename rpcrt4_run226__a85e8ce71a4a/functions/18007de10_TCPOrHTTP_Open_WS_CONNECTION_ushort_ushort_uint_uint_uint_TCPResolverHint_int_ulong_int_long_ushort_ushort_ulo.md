# TCPOrHTTP_Open(WS_CONNECTION *,ushort *,ushort,uint,uint,uint,TCPResolverHint *,int,ulong,int,long (*)(ushort *,ushort *,ulong))

- ea: `0x18007de10`
- end: `0x18007e478`
- name: `?TCPOrHTTP_Open@@YAJPEAVWS_CONNECTION@@PEAGGIIIPEAVTCPResolverHint@@HKHP6AJ11K@Z@Z`
- size: `1640`
- prototype: `__int64 __usercall@<rax>(struct WS_CONNECTION *this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16@<r8w>, unsigned int@<r9d>, unsigned int, char, struct TCPResolverHint *, int, unsigned int, int, int (*)(unsigned __int16 *, unsigned __int16 *, unsigned int))`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18007d890`

## callees

- `0x1800183bc`
- `0x18005ceb0`
- `0x18007d5e0`
- `0x18007d9a8`
- `0x18007de10`
- `0x18007e494`
- `0x1800996e4`
- `0x18009e238`
- `0x1800a6a40`
- `0x1800b4a5c`
- `0x1800b4b0c`
- `0x1800ca049`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `KERNELBASE!lstrlenW` at `0x18007e217`
- `KERNELBASE!lstrlenW` at `0x18007e217`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e333`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007e333`
- `WS2_32!getnameinfo` at `0x18007e380`
- `WS2_32!getnameinfo` at `0x18007e380`
- `WS2_32!GetNameInfoW` at `0x18007e3bb`
- `WS2_32!GetNameInfoW` at `0x18007e3bb`
- `WS2_32!FreeAddrInfoW` at `0x18007e041`
- `WS2_32!FreeAddrInfoW` at `0x18007e22d`
- `WS2_32!FreeAddrInfoW` at `0x18007e041`
- `WS2_32!FreeAddrInfoW` at `0x18007e22d`
- `WS2_32!__imp_htons` at `0x18007de84`
- `WS2_32!__imp_htons` at `0x18007de84`

## pseudocode

```c

```
