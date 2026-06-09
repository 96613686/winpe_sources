# Microsoft::Diagnostics::TdhFacade::GetEventInformation(_EVENT_RECORD &,Performance::TdhTools::CEventInformation &,std::unique_ptr<gsl::byte [0],std::default_delete<gsl::byte [0]>> &,Microsoft::Diagnostics::EtwDecodingFailureSite *)

- ea: `0x180314f48`
- end: `0x1803155ac`
- name: `?GetEventInformation@TdhFacade@Diagnostics@Microsoft@@QEAAJAEAU_EVENT_RECORD@@AEAUCEventInformation@TdhTools@Performance@@AEAV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@PEAVEtwDecodingFailureSite@23@@Z`
- size: `1636`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, struct _EVENT_RECORD *, Performance::TdhTools::CEventInformation *, struct std::nothrow_t *, int *)`
- caller_count: `2`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cda1c`
- `0x1800d03a8`

## callees

- `0x180010420`
- `0x18001d160`
- `0x18001dcf8`
- `0x180024ef8`
- `0x180026ecc`
- `0x180027be0`
- `0x180032688`
- `0x18004f774`
- `0x180057260`
- `0x18005d050`
- `0x1800708bc`
- `0x18007fae8`
- `0x1800aac70`
- `0x1800b0628`
- `0x1800d0d7c`
- `0x1800d0df0`
- `0x18011b7c4`
- `0x18012de40`
- `0x18012e324`
- `0x180170014`
- `0x18020b6e0`
- `0x180290790`
- `0x1802bbb14`
- `0x1802bbf28`
- `0x1802bc104`
- `0x180314c9c`
- `0x180314f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180315345`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180315345`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180314fb2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180314fb2`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetEventInformation` at `0x1803153b3`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetEventInformation` at `0x180315400`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetEventInformation` at `0x1803153b3`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetEventInformation` at `0x180315400`

## string_xrefs

- `0x180315423`: `onecore\base\telemetry\utc\service\tdhfacade\tdhfacade.cpp`
- `0x180315477`: `onecore\base\telemetry\utc\service\tdhfacade\tdhfacade.cpp`
- `0x18031550d`: `onecore\base\telemetry\utc\service\tdhfacade\tdhfacade.cpp`
- `0x18031556a`: `onecore\base\telemetry\utc\service\tdhfacade\tdhfacade.cpp`

## pseudocode

```c

```
