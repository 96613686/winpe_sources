# ComposingStatusChangedEventSink::RaiseRemoteParticipantComposing(ushort const *,UdmObjectId,ushort const *,int)

- ea: `0x1800833f0`
- end: `0x1800835ca`
- name: `?RaiseRemoteParticipantComposing@ComposingStatusChangedEventSink@@QEAAJPEBGUUdmObjectId@@0H@Z`
- size: `474`
- prototype: `int __high(const unsigned __int16 *, struct UdmObjectId, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800d3474`

## callees

- `0x180004ce4`
- `0x18006f0a8`
- `0x1800833f0`
- `0x1800835d0`
- `0x1800977ac`
- `0x1800ca4ac`
- `0x1800cbfb0`
- `0x18012c76a`

## import_xrefs

- `msvcrt!_wtoi` at `0x180083413`
- `msvcrt!_wtoi` at `0x180083413`
- `MessagingDataModel2!Messaging_IsCustomAppProviderId` at `0x18008341e`
- `MessagingDataModel2!Messaging_IsCustomAppProviderId` at `0x18008341e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083509`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180083509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008356b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180083594`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008356b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180083594`
- `UserDataTypeHelperUtil!DupString` at `0x18008345a`
- `UserDataTypeHelperUtil!DupString` at `0x18008345a`

## pseudocode

```c

```
