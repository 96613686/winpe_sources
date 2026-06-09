# WFDSvc::ASPCoordination::CSocketWrapper::SetConnResetIoctl(bool)

- ea: `0x18021b088`
- end: `0x18021b2fb`
- name: `?SetConnResetIoctl@CSocketWrapper@ASPCoordination@WFDSvc@@AEAAX_N@Z`
- size: `627`
- prototype: `void __fastcall(WFDSvc::ASPCoordination::CSocketWrapper *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180218140`

## callees

- `0x18000a704`
- `0x18000aa0c`
- `0x1800bd620`
- `0x180218378`
- `0x18021b088`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x18021b1de`
- `WS2_32!WSAIoctl` at `0x18021b1de`
- `WS2_32!WSAGetOverlappedResult` at `0x18021b26c`
- `WS2_32!WSAGetOverlappedResult` at `0x18021b26c`
- `WS2_32!WSACreateEvent` at `0x18021b111`
- `WS2_32!WSACreateEvent` at `0x18021b111`
- `WS2_32!__imp_WSAGetLastError` at `0x18021b138`
- `WS2_32!__imp_WSAGetLastError` at `0x18021b1e9`
- `WS2_32!__imp_WSAGetLastError` at `0x18021b28e`
- `WS2_32!__imp_WSAGetLastError` at `0x18021b138`
- `WS2_32!__imp_WSAGetLastError` at `0x18021b1e9`
- `WS2_32!__imp_WSAGetLastError` at `0x18021b28e`

## string_xrefs

- `0x18021b161`: `WSACreateEvent failed, cannot initialize ASP Coordination Protocol`

## pseudocode

```c

```
