# WFDSvc::ASPCoordination::CSocketPeerInstance::CSocketPeerInstance(WFDSvc::ASPCoordination::ISocketWrapperManager &,WFDSvc::ASPCoordination::CSocketWrapper *,sockaddr_storage const &,bool)

- ea: `0x180217d64`
- end: `0x180217f25`
- name: `??0CSocketPeerInstance@ASPCoordination@WFDSvc@@IEAA@AEAVISocketWrapperManager@12@PEAVCSocketWrapper@12@AEBUsockaddr_storage@@_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(WFDSvc::ASPCoordination::CSocketPeerInstance *__hidden this, struct WFDSvc::ASPCoordination::ISocketWrapperManager *, struct WFDSvc::ASPCoordination::CSocketWrapper *, const struct sockaddr_storage *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180218a1c`

## callees

- `0x18000a704`
- `0x1800bd620`
- `0x180217d64`
- `0x18021b6cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180217e0f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180217e0f`
- `WS2_32!WSACreateEvent` at `0x180217e16`
- `WS2_32!WSACreateEvent` at `0x180217e16`
- `WS2_32!__imp_ntohs` at `0x180217ec6`
- `WS2_32!__imp_ntohs` at `0x180217edd`
- `WS2_32!__imp_ntohs` at `0x180217ec6`
- `WS2_32!__imp_ntohs` at `0x180217edd`
- `WS2_32!__imp_WSAGetLastError` at `0x180217e47`
- `WS2_32!__imp_WSAGetLastError` at `0x180217e47`

## string_xrefs

- `0x180217e70`: `WSACreateEvent failed, cannot initialize ASP Coordination Protocol`

## pseudocode

```c

```
