# LsaLogonUser

- ea: `0x18000aaa0`
- end: `0x18000ab28`
- name: `LsaLogonUser`
- size: `136`
- prototype: `NTSTATUS __stdcall(HANDLE LsaHandle, PLSA_STRING OriginName, SECURITY_LOGON_TYPE LogonType, ULONG AuthenticationPackage, PVOID AuthenticationInformation, ULONG AuthenticationInformationLength, PTOKEN_GROUPS LocalGroups, PTOKEN_SOURCE SourceContext, PVOID *ProfileBuffer, PULONG ProfileBufferLength, PLUID LogonId, PHANDLE Token, PQUOTA_LIMITS Quotas, PNTSTATUS SubStatus)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b1f0`

## pseudocode

```c
NTSTATUS __stdcall LsaLogonUser(
        HANDLE LsaHandle,
        PLSA_STRING OriginName,
        SECURITY_LOGON_TYPE LogonType,
        ULONG AuthenticationPackage,
        PVOID AuthenticationInformation,
        ULONG AuthenticationInformationLength,
        PTOKEN_GROUPS LocalGroups,
        PTOKEN_SOURCE SourceContext,
        PVOID *ProfileBuffer,
        PULONG ProfileBufferLength,
        PLUID LogonId,
        PHANDLE Token,
        PQUOTA_LIMITS Quotas,
        PNTSTATUS SubStatus)
{
  return SspipLogonUser(
           (__int64)LsaHandle,
           (__int64)OriginName,
           LogonType,
           AuthenticationPackage,
           (__int64)AuthenticationInformation,
           AuthenticationInformationLength,
           (__int64)LocalGroups,
           (__int64)SourceContext,
           ProfileBuffer,
           (__int64)ProfileBufferLength,
           (__int64)LogonId,
           Token,
           Quotas,
           (__int64)SubStatus);
}

```

## disassembly

```asm
0x18000aaa0  mov     r11, rsp
0x18000aaa3  sub     rsp, 78h
0x18000aaa7  mov     rax, [rsp+78h+SubStatus]
0x18000aaaf  mov     [r11-10h], rax
0x18000aab3  mov     rax, [rsp+78h+Quotas]
0x18000aabb  mov     [r11-18h], rax
0x18000aabf  mov     rax, [rsp+78h+Token]
0x18000aac7  mov     [r11-20h], rax
0x18000aacb  mov     rax, [rsp+78h+LogonId]
0x18000aad3  mov     [r11-28h], rax
0x18000aad7  mov     rax, [rsp+78h+ProfileBufferLength]
0x18000aadf  mov     [r11-30h], rax
0x18000aae3  mov     rax, [rsp+78h+ProfileBuffer]
0x18000aaeb  mov     [r11-38h], rax
0x18000aaef  mov     rax, [rsp+78h+SourceContext]
0x18000aaf7  mov     [r11-40h], rax
0x18000aafb  mov     rax, [rsp+78h+LocalGroups]
0x18000ab03  mov     [r11-48h], rax
0x18000ab07  mov     eax, [rsp+78h+AuthenticationInformationLength]
0x18000ab0e  mov     [rsp+78h+var_50], eax
0x18000ab12  mov     rax, [rsp+78h+AuthenticationInformation]
0x18000ab1a  mov     [r11-58h], rax
0x18000ab1e  call    SspipLogonUser
0x18000ab23  add     rsp, 78h
0x18000ab27  retn
```
