# CUserTileValidator::_TranscodeVideoAndReset(IStream *,uint,IStream * *)

- ea: `0x180043c68`
- end: `0x180043e86`
- name: `?_TranscodeVideoAndReset@CUserTileValidator@@AEAAJPEAUIStream@@IPEAPEAU2@@Z`
- size: `542`
- prototype: `int(CUserTileValidator *__hidden this, struct IStream *, unsigned int, struct IStream **)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180044a40`
- `0x180044b80`

## callees

- `0x180013f14`
- `0x1800343ec`
- `0x18003ff34`
- `0x180043c68`
- `0x180043e8c`
- `0x18004401c`
- `0x180044054`
- `0x18004413c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180043e37`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180043e46`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180043e37`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180043e46`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180043dc1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x180043dc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180043d46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180043d46`

## string_xrefs

- `0x180043cb9`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180043cf9`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x180043e26`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c

```
