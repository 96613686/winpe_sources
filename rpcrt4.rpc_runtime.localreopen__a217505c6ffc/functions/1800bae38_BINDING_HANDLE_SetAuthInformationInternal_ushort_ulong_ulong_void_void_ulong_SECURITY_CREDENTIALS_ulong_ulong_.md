# BINDING_HANDLE::SetAuthInformationInternal(ushort *,ulong,ulong,void *,void *,ulong,SECURITY_CREDENTIALS *,ulong,ulong,ulong,ulong,ulong,void *,void *,int,int,void *,int)

- ea: `0x1800bae38`
- end: `0x1800bb525`
- name: `?SetAuthInformationInternal@BINDING_HANDLE@@AEAAJPEAGKKPEAX1KPEAVSECURITY_CREDENTIALS@@KKKKK11HH1H@Z`
- size: `1773`
- prototype: `int(BINDING_HANDLE *__hidden this, unsigned __int16 *, unsigned int, unsigned int, void *, void *, unsigned int, struct SECURITY_CREDENTIALS *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void *, void *, int, int, void *, int)`
- caller_count: `2`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bad70`
- `0x1800bb650`

## callees

- `0x18000add8`
- `0x180012f68`
- `0x180023020`
- `0x180023a40`
- `0x18002e750`
- `0x1800307e0`
- `0x180031a64`
- `0x18005775c`
- `0x18006c6e8`
- `0x180093944`
- `0x180093efc`
- `0x18009b57c`
- `0x18009d3a8`
- `0x18009d838`
- `0x1800a01f0`
- `0x1800a7374`
- `0x1800a9178`
- `0x1800aadd0`
- `0x1800ade40`
- `0x1800ba8c0`
- `0x1800ba8f0`
- `0x1800ba914`
- `0x1800bae38`
- `0x1800bb8a0`
- `0x1800ce6e4`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800bb01e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bb3c4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bb4d6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bb01e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bb3c4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bb4d6`
- `ntdll!RtlEnterCriticalSection` at `0x1800baff9`
- `ntdll!RtlEnterCriticalSection` at `0x1800bb329`
- `ntdll!RtlEnterCriticalSection` at `0x1800bb398`
- `ntdll!RtlEnterCriticalSection` at `0x1800bb4b1`
- `ntdll!RtlEnterCriticalSection` at `0x1800baff9`
- `ntdll!RtlEnterCriticalSection` at `0x1800bb329`
- `ntdll!RtlEnterCriticalSection` at `0x1800bb398`
- `ntdll!RtlEnterCriticalSection` at `0x1800bb4b1`
- `ext-ms-win-rpc-ssl-l1-1-0!ValidatePrincipalName` at `0x1800bb2cb`
- `ext-ms-win-rpc-ssl-l1-1-0!ValidatePrincipalName` at `0x1800bb2cb`

## pseudocode

```c

```
