# Tcp::CreateSocket(int,int,int,_WSAPROTOCOL_INFOW *,ulong,ulong *)

- ea: `0x100435790`
- end: `0x1004359b2`
- name: `?CreateSocket@Tcp@@SA_KHHHPEAU_WSAPROTOCOL_INFOW@@KPEAK@Z`
- size: `546`
- prototype: `unsigned __int64 __fastcall(int af, int type, int protocol, LPWSAPROTOCOL_INFOW lpProtocolInfo, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100436430`
- `0x1004510d0`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x100435790`

## import_xrefs

- `KERNEL32!SetHandleInformation` at `0x1004358d2`
- `KERNEL32!SetHandleInformation` at `0x1004358d2`
- `KERNEL32!GetLastError` at `0x1004358dc`
- `KERNEL32!GetLastError` at `0x1004358dc`
- `WS2_32!WSASocketW` at `0x10043583a`
- `WS2_32!WSASocketW` at `0x10043583a`
- `WS2_32!__imp_closesocket` at `0x10043590c`
- `WS2_32!__imp_closesocket` at `0x10043590c`
- `WS2_32!__imp_socket` at `0x10043587f`
- `WS2_32!__imp_socket` at `0x10043587f`
- `WS2_32!__imp_WSAGetLastError` at `0x100435849`
- `WS2_32!__imp_WSAGetLastError` at `0x10043588e`
- `WS2_32!__imp_WSAGetLastError` at `0x100435917`
- `WS2_32!__imp_WSAGetLastError` at `0x100435849`
- `WS2_32!__imp_WSAGetLastError` at `0x10043588e`
- `WS2_32!__imp_WSAGetLastError` at `0x100435917`

## string_xrefs

- `0x1004357be`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004357c9`: `Tcp::CreateSocket`
- `0x1004357fa`: `API|SNIaf: %d{int}, type: %d{int}, protocol: %d{int}, pdwError: %p{DWORD*}\n`

## pseudocode

```c

```
