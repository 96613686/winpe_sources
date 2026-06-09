# WspiapiQueryDNS

- ea: `0x383ab6800`
- end: `0x383ab6905`
- name: `WspiapiQueryDNS`
- size: `261`
- prototype: `int __stdcall(const char *pszNodeName, int iSocketType, int iProtocol, WORD wPort, char pszAlias[1025], struct addrinfo **pptResult)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x383ab6990`

## callees

- `0x383ab6800`
- `0x383ab6b40`

## import_xrefs

- `MSVCR100!strncpy_s` at `0x383ab68ab`
- `MSVCR100!strncpy_s` at `0x383ab68ab`
- `WS2_32!__imp_gethostbyname` at `0x383ab6839`
- `WS2_32!__imp_gethostbyname` at `0x383ab6839`
- `WS2_32!__imp_WSAGetLastError` at `0x383ab68d9`
- `WS2_32!__imp_WSAGetLastError` at `0x383ab68d9`

## pseudocode

```c

```
