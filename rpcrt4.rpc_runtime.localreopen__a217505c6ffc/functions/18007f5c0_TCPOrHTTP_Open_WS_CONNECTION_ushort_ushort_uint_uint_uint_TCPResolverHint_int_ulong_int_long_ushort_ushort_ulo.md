# TCPOrHTTP_Open(WS_CONNECTION *,ushort *,ushort,uint,uint,uint,TCPResolverHint *,int,ulong,int,long (*)(ushort *,ushort *,ulong))

- ea: `0x18007f5c0`
- end: `0x18007fc53`
- name: `?TCPOrHTTP_Open@@YAJPEAVWS_CONNECTION@@PEAGGIIIPEAVTCPResolverHint@@HKHP6AJ11K@Z@Z`
- size: `1683`
- prototype: `__int64 __fastcall(struct WS_CONNECTION *this, unsigned __int16 *, u_short, unsigned int, unsigned int, char, struct TCPResolverHint *, int, unsigned int, int, int (*)(unsigned __int16 *, unsigned __int16 *, unsigned int))`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x18007f030`

## callees

- `0x1800167d8`
- `0x18006d460`
- `0x18006f7e8`
- `0x18007f14c`
- `0x18007f5c0`
- `0x18007fc74`
- `0x18009c514`
- `0x1800a1b60`
- `0x1800aa300`
- `0x1800b8b60`
- `0x1800b8c14`
- `0x1800ceca9`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `KERNELBASE!lstrlenW` at `0x18007f9d4`
- `KERNELBASE!lstrlenW` at `0x18007f9d4`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007fafc`
- `ntdll!RtlUnicodeToMultiByteN` at `0x18007fafc`
- `WS2_32!getnameinfo` at `0x18007fb4f`
- `WS2_32!getnameinfo` at `0x18007fb4f`
- `WS2_32!GetNameInfoW` at `0x18007fb90`
- `WS2_32!GetNameInfoW` at `0x18007fb90`
- `WS2_32!FreeAddrInfoW` at `0x18007f7f7`
- `WS2_32!FreeAddrInfoW` at `0x18007f9f0`
- `WS2_32!FreeAddrInfoW` at `0x18007f7f7`
- `WS2_32!FreeAddrInfoW` at `0x18007f9f0`
- `WS2_32!__imp_htons` at `0x18007f634`
- `WS2_32!__imp_htons` at `0x18007f634`

## pseudocode

```c

```
