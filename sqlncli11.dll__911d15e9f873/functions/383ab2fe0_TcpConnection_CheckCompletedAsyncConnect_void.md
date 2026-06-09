# TcpConnection::CheckCompletedAsyncConnect(void)

- ea: `0x383ab2fe0`
- end: `0x383ab311e`
- name: `?CheckCompletedAsyncConnect@TcpConnection@@QEAAKXZ`
- size: `318`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x383ab3450`
- `0x383ab4360`

## callees

- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab2fe0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x383ab303c`
- `KERNEL32!GetOverlappedResult` at `0x383ab303c`
- `KERNEL32!GetLastError` at `0x383ab307d`
- `KERNEL32!GetLastError` at `0x383ab307d`
- `WS2_32!__imp_setsockopt` at `0x383ab305e`
- `WS2_32!__imp_setsockopt` at `0x383ab305e`
- `WS2_32!__imp_WSAGetLastError` at `0x383ab3069`
- `WS2_32!__imp_WSAGetLastError` at `0x383ab3069`

## pseudocode

```c

```
