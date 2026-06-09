# EmailHelper::SetupResponseMessage(EmailOperationContext *,IMsgStore *,IMessage *,IMessage *,int,UdmEmailMessageResponseKind,ushort const *,ushort const *,UdmEmailMessageBodyKind,ushort const *,ulong,UdmEmailParticipant const *,int)

- ea: `0x18007065c`
- end: `0x180070c09`
- name: `?SetupResponseMessage@EmailHelper@@YAJPEAVEmailOperationContext@@PEAUIMsgStore@@PEAUIMessage@@2HW4UdmEmailMessageResponseKind@@PEBG4W4UdmEmailMessageBodyKind@@4KPEBUUdmEmailParticipant@@H@Z`
- size: `1453`
- prototype: `int __high(struct EmailOperationContext *, struct IMsgStore *, struct IMessage *, struct IMessage *, int, enum UdmEmailMessageResponseKind, const unsigned __int16 *, const unsigned __int16 *, enum UdmEmailMessageBodyKind, const unsigned __int16 *, unsigned int, const struct UdmEmailParticipant *, int)`
- caller_count: `2`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x180085e80`
- `0x18008a490`

## callees

- `0x1800049f0`
- `0x180008ee8`
- `0x18000e1f8`
- `0x180012200`
- `0x18001283c`
- `0x1800128e0`
- `0x180018c20`
- `0x18001b340`
- `0x1800615c0`
- `0x18006f444`
- `0x180070254`
- `0x18007065c`
- `0x180071228`
- `0x180071278`
- `0x1800713e4`
- `0x180071b80`
- `0x18007b878`
- `0x18007ba18`
- `0x18008ce40`
- `0x1800b6288`
- `0x1800f72e4`
- `0x1800f7bbc`
- `0x1800f8918`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!CreateAttendeeList` at `0x180070a55`
- `PIMSTORE!CreateAttendeeList` at `0x180070a55`
- `CEMAPI!HrSetOneProp` at `0x180070977`
- `CEMAPI!HrSetOneProp` at `0x180070977`
- `CEMAPI!SetConversationId` at `0x180070b9d`
- `CEMAPI!SetConversationId` at `0x180070b9d`
- `CEMAPI!HrGetOneProp` at `0x1800706fd`
- `CEMAPI!HrGetOneProp` at `0x1800706fd`
- `CEMAPI!MAPIFreeBuffer` at `0x180070729`
- `CEMAPI!MAPIFreeBuffer` at `0x180070b20`
- `CEMAPI!MAPIFreeBuffer` at `0x180070bd6`
- `CEMAPI!MAPIFreeBuffer` at `0x180070729`
- `CEMAPI!MAPIFreeBuffer` at `0x180070b20`
- `CEMAPI!MAPIFreeBuffer` at `0x180070bd6`
- `UserDataTypeHelperUtil!MapiIdToEmailUdmId` at `0x180070745`
- `UserDataTypeHelperUtil!MapiIdToEmailUdmId` at `0x180070745`

## pseudocode

```c

```
