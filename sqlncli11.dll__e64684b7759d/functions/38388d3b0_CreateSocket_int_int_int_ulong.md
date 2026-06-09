# CreateSocket(int,int,int,ulong *)

- ea: `0x38388d3b0`
- end: `0x38388d47a`
- name: `?CreateSocket@@YA_KHHHPEAK@Z`
- size: `202`
- prototype: `unsigned __int64 __fastcall(int af, int type, int protocol, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x38388d270`

## callees

- `0x38388d3b0`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`

## import_xrefs

- `KERNEL32!SetHandleInformation` at `0x38388d431`
- `KERNEL32!SetHandleInformation` at `0x38388d431`
- `KERNEL32!GetLastError` at `0x3838fb04b`
- `KERNEL32!GetLastError` at `0x3838fb04b`
- `WS2_32!WSASocketA` at `0x38388d410`
- `WS2_32!WSASocketA` at `0x38388d410`
- `WS2_32!__imp_closesocket` at `0x3838fb086`
- `WS2_32!__imp_closesocket` at `0x3838fb086`
- `WS2_32!__imp_socket` at `0x3838faff0`
- `WS2_32!__imp_socket` at `0x3838faff0`
- `WS2_32!__imp_WSAGetLastError` at `0x3838fafab`
- `WS2_32!__imp_WSAGetLastError` at `0x3838fafff`
- `WS2_32!__imp_WSAGetLastError` at `0x3838fb091`
- `WS2_32!__imp_WSAGetLastError` at `0x3838fafab`
- `WS2_32!__imp_WSAGetLastError` at `0x3838fafff`
- `WS2_32!__imp_WSAGetLastError` at `0x3838fb091`

## pseudocode

```c

```
