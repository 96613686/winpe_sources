# LRPC_BINDING_HANDLE::SetAuthInformation(ushort *,ulong,ulong,void *,void *,ulong,SECURITY_CREDENTIALS *,ulong,ulong,ulong,ulong,ulong,void *,void *,int,int,void *)

- ea: `0x18002ed80`
- end: `0x18002ef8f`
- name: `?SetAuthInformation@LRPC_BINDING_HANDLE@@UEAAJPEAGKKPEAX1KPEAVSECURITY_CREDENTIALS@@KKKKK11HH1@Z`
- size: `527`
- prototype: `__int64 __fastcall(LRPC_BINDING_HANDLE *__hidden this, unsigned __int16 *, unsigned int, unsigned int, PSEC_WINNT_AUTH_IDENTITY_OPAQUE, void *, unsigned int, struct SECURITY_CREDENTIALS *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void *, PSID, int, int, PSECURITY_DESCRIPTOR)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002ed80`
- `0x18002f480`
- `0x1800303d0`
- `0x180030878`
- `0x180031efc`
- `0x1800bb77c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002ee0a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002eeeb`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ee0a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002eeeb`
- `ntdll!RtlEnterCriticalSection` at `0x18002edcc`
- `ntdll!RtlEnterCriticalSection` at `0x18002ede5`
- `ntdll!RtlEnterCriticalSection` at `0x18002edcc`
- `ntdll!RtlEnterCriticalSection` at `0x18002ede5`

## pseudocode

```c

```
