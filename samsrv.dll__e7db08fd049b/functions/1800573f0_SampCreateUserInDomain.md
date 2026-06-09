# SampCreateUserInDomain

- ea: `0x1800573f0`
- end: `0x1800581f4`
- name: `SampCreateUserInDomain`
- size: `3588`
- prototype: `__int64 __usercall@<rax>(struct _SAMP_OBJECT *@<rcx>, PUNICODE_STRING DestinationString@<rdx>, char, char, __int64, __int64, __int64, unsigned __int8, char)`
- caller_count: `5`
- callee_count: `50`
- tags: `loader_planting`

## callers

- `0x1800586f0`
- `0x1800588d0`
- `0x18005bc50`
- `0x18006b0e0`
- `0x180091598`

## callees

- `0x180004fa0`
- `0x180006170`
- `0x1800066f0`
- `0x180008590`
- `0x18000ae10`
- `0x180012a28`
- `0x18001c0e0`
- `0x18001cc00`
- `0x1800213d0`
- `0x180022440`
- `0x180022678`
- `0x180022b30`
- `0x180024360`
- `0x180027e24`
- `0x180028040`
- `0x1800290f0`
- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`
- `0x18003aaf8`
- `0x18003ab98`
- `0x18003cd20`
- `0x180051930`
- `0x1800531e0`
- `0x180053278`
- `0x180053408`
- `0x1800535ec`
- `0x1800536f0`
- `0x1800553a0`
- `0x1800555b4`
- `0x1800573f0`
- `0x180059a74`
- `0x180063830`
- `0x180064050`
- `0x1800655e4`
- `0x180065a2c`
- `0x180065af4`
- `0x18006a9cc`
- `0x18006ae14`
- `0x180074b5c`
- `0x180076b14`
- `0x180076c04`
- `0x180077198`
- `0x18008a688`
- `0x18008ac58`
- `0x18009d178`
- `0x1800a5620`
- `0x1800aa26c`
- `0x1800acb78`
- `0x1800ae670`

## import_xrefs

- `ntdll!RtlMapGenericMask` at `0x1800579e5`
- `ntdll!RtlMapGenericMask` at `0x1800579e5`
- `ntdll!RtlSetBits` at `0x180057db2`
- `ntdll!RtlSetBits` at `0x180057db2`
- `ntdll!RtlAddActionToRXact` at `0x1800578d7`
- `ntdll!RtlAddActionToRXact` at `0x1800578d7`
- `ntdll!RtlInitUnicodeString` at `0x180057ba9`
- `ntdll!RtlInitUnicodeString` at `0x180057bb5`
- `ntdll!RtlInitUnicodeString` at `0x18005816a`
- `ntdll!RtlInitUnicodeString` at `0x180057ba9`
- `ntdll!RtlInitUnicodeString` at `0x180057bb5`
- `ntdll!RtlInitUnicodeString` at `0x18005816a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057b3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057c71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057d6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005815f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057b3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057c71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057d6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005815f`
- `NETLOGON!I_NetNotifyMachineAccount` at `0x180058082`
- `NETLOGON!I_NetNotifyMachineAccount` at `0x180058082`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtAllocateKrbTgtId` at `0x1800577f8`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtAllocateKrbTgtId` at `0x1800577f8`

## pseudocode

```c

```
