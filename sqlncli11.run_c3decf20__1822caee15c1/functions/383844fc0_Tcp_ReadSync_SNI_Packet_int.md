# Tcp::ReadSync(SNI_Packet * *,int)

- ea: `0x383844fc0`
- end: `0x38384517e`
- name: `?ReadSync@Tcp@@UEAAKPEAPEAVSNI_Packet@@H@Z`
- size: `446`
- prototype: `unsigned int(Tcp *__hidden this, struct SNI_Packet **, int)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x383842d70`
- `0x383843bc0`
- `0x383844fc0`
- `0x383846430`
- `0x38391ac40`
- `0x38391ade0`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x3838450f2`
- `KERNEL32!GetOverlappedResult` at `0x3838450f2`
- `KERNEL32!GetLastError` at `0x3838fd00b`
- `KERNEL32!GetLastError` at `0x3838fd00b`
- `KERNEL32!GetTickCount` at `0x3838450ad`
- `KERNEL32!GetTickCount` at `0x3838fd041`
- `KERNEL32!GetTickCount` at `0x3838450ad`
- `KERNEL32!GetTickCount` at `0x3838fd041`
- `KERNEL32!WaitForSingleObject` at `0x3838450c4`
- `KERNEL32!WaitForSingleObject` at `0x3838450c4`
- `WS2_32!WSARecv` at `0x38384508d`
- `WS2_32!WSARecv` at `0x38384508d`
- `WS2_32!__imp_WSAGetLastError` at `0x383845098`
- `WS2_32!__imp_WSAGetLastError` at `0x383845098`

## pseudocode

```c

```
