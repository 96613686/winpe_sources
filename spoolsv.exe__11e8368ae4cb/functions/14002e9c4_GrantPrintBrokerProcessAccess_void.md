# GrantPrintBrokerProcessAccess(void)

- ea: `0x14002e9c4`
- end: `0x14002eba6`
- name: `?GrantPrintBrokerProcessAccess@@YAHXZ`
- size: `482`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14002f198`

## callees

- `0x1400160a0`
- `0x14002abc0`
- `0x14002b810`
- `0x14002e9c4`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x14002ea6f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x14002ea6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002e9e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002e9e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002eb76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002eb86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002eb76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002eb86`
- `ADVAPI32!GetSecurityInfo` at `0x14002eac4`
- `ADVAPI32!GetSecurityInfo` at `0x14002eac4`
- `ADVAPI32!SetSecurityInfo` at `0x14002eb51`
- `ADVAPI32!SetSecurityInfo` at `0x14002eb51`
- `ADVAPI32!SetEntriesInAclW` at `0x14002eb1c`
- `ADVAPI32!SetEntriesInAclW` at `0x14002eb1c`

## string_xrefs

- `0x14002ea7c`: `Failed to setup PrintScan Broker SID %d`
- `0x14002ea83`: `GrantPrintBrokerProcessAccess`
- `0x14002ead8`: `GrantPrintBrokerProcessAccess`
- `0x14002eace`: `GetSecurityInfo failed %d`
- `0x14002eb26`: `SetEntriesInAcl failed to add PrintScan Broker ACE %d`
- `0x14002eb5b`: `SetSecurityInfo failed %d`

## pseudocode

```c
__int64 GrantPrintBrokerProcessAccess(void)
{
  HANDLE CurrentProcess; // rdi
  NTSTATUS v1; // eax
  unsigned int v3; // ebx
  DWORD SecurityInfo; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  PACL NewAcl; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  PACL ppDacl; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+78h] [rbp-88h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v13[80]; // [rsp+C0h] [rbp-40h] BYREF

  CurrentProcess = GetCurrentProcess();
  ppDacl = 0;
  ppSecurityDescriptor = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  memset_0(v13, 0, 0x44u);
  NewAcl = 0;
  Sid = v13;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v1 = RtlAllocateAndInitializeSid(
         &IdentifierAuthority,
         6u,
         0x50u,
         0x10185D4Du,
         0x6025C496u,
         0x93E3A09u,
         0x1FA2CE07u,
         0xD10E9DDF,
         0,
         0,
         &Sid);
  if ( v1 >= 0 )
  {
    v3 = 0;
    SecurityInfo = GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor);
    if ( SecurityInfo )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "GrantPrintBrokerProcessAccess",
        L"GetSecurityInfo failed %d",
        SecurityInfo);
    }
    else
    {
      pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
      pListOfExplicitEntries.grfAccessPermissions = 1088;
      *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
      pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
      *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
      v5 = SetEntriesInAclW(1u, &pListOfExplicitEntries, ppDacl, &NewAcl);
      if ( v5 )
      {
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "GrantPrintBrokerProcessAccess",
          L"SetEntriesInAcl failed to add PrintScan Broker ACE %d",
          v5);
      }
      else
      {
        v6 = SetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, NewAcl, 0);
        if ( v6 )
          SpoolerServiceTelemetry::WriteDbgTraceError("GrantPrintBrokerProcessAccess", L"SetSecurityInfo failed %d", v6);
        else
          v3 = 1;
      }
    }
    if ( NewAcl )
      LocalFree(NewAcl);
    if ( ppSecurityDescriptor )
      LocalFree(ppSecurityDescriptor);
    return v3;
  }
  else
  {
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "GrantPrintBrokerProcessAccess",
      L"Failed to setup PrintScan Broker SID %d",
      (unsigned int)v1);
    return 0;
  }
}

```

## disassembly

```asm
0x14002e9c4  push    rbp
0x14002e9c6  push    rbx
0x14002e9c7  push    rsi
0x14002e9c8  push    rdi
0x14002e9c9  lea     rbp, [rsp-28h]
0x14002e9ce  sub     rsp, 128h
0x14002e9d5  mov     rax, cs:__security_cookie
0x14002e9dc  xor     rax, rsp
0x14002e9df  mov     [rbp+40h+var_30], rax
0x14002e9e3  call    cs:__imp_GetCurrentProcess
0x14002e9e9  xorps   xmm0, xmm0
0x14002e9ec  lea     rcx, [rbp+40h+var_80]; void *
0x14002e9f0  xor     esi, esi
0x14002e9f2  xor     edx, edx; Val
0x14002e9f4  mov     rdi, rax
0x14002e9f7  mov     [rsp+140h+ppDacl], rsi
0x14002e9fc  mov     [rsp+140h+ppSecurityDescriptor], rsi
0x14002ea01  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x14002ea05  lea     r8d, [rsi+44h]; Size
0x14002ea09  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x14002ea0d  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x14002ea11  call    memset_0
0x14002ea16  lea     rax, [rbp+40h+var_80]
0x14002ea1a  mov     [rsp+140h+NewAcl], rsi
0x14002ea1f  mov     [rsp+140h+var_D8], rax
0x14002ea24  lea     r8d, [rsi+50h]; SubAuthority0
0x14002ea28  lea     rax, [rsp+140h+var_D8]
0x14002ea2d  mov     dword ptr [rbp+40h+IdentifierAuthority.Value], esi
0x14002ea30  mov     [rsp+140h+Sid], rax; Sid
0x14002ea35  lea     rcx, [rbp+40h+IdentifierAuthority]; IdentifierAuthority
0x14002ea39  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x14002ea3d  mov     r9d, 10185D4Dh; SubAuthority1
0x14002ea43  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x14002ea47  mov     dl, 6; SubAuthorityCount
0x14002ea49  mov     [rsp+140h+SubAuthority5], 0D10E9DDFh; SubAuthority5
0x14002ea51  mov     [rsp+140h+SubAuthority4], 1FA2CE07h; SubAuthority4
0x14002ea59  mov     [rsp+140h+SubAuthority3], 93E3A09h; SubAuthority3
0x14002ea61  mov     [rsp+140h+SubAuthority2], 6025C496h; SubAuthority2
0x14002ea69  mov     word ptr [rbp+40h+IdentifierAuthority.Value+4], 500h
0x14002ea6f  call    cs:__imp_RtlAllocateAndInitializeSid
0x14002ea75  test    eax, eax
0x14002ea77  jns     short loc_14002EA96
0x14002ea79  mov     r8d, eax
0x14002ea7c  lea     rdx, aFailedToSetupP; "Failed to setup PrintScan Broker SID %d"
0x14002ea83  lea     rcx, aGrantprintbrok; "GrantPrintBrokerProcessAccess"
0x14002ea8a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14002ea8f  xor     eax, eax
0x14002ea91  jmp     loc_14002EB8E
0x14002ea96  xor     r9d, r9d; ppsidOwner
0x14002ea99  lea     rax, [rsp+140h+ppSecurityDescriptor]
0x14002ea9e  mov     qword ptr [rsp+140h+SubAuthority5], rax; ppSecurityDescriptor
0x14002eaa3  mov     rcx, rdi; handle
0x14002eaa6  lea     rax, [rsp+140h+ppDacl]
0x14002eaab  mov     qword ptr [rsp+140h+SubAuthority4], rsi; ppSacl
0x14002eab0  mov     qword ptr [rsp+140h+SubAuthority3], rax; ppDacl
0x14002eab5  mov     ebx, esi
0x14002eab7  lea     edx, [r9+6]; ObjectType
0x14002eabb  mov     qword ptr [rsp+140h+SubAuthority2], rsi; ppsidGroup
0x14002eac0  lea     r8d, [r9+4]; SecurityInfo
0x14002eac4  call    cs:__imp_GetSecurityInfo
0x14002eaca  test    eax, eax
0x14002eacc  jz      short loc_14002EAE9
0x14002eace  lea     rdx, aGetsecurityinf; "GetSecurityInfo failed %d"
0x14002ead5  mov     r8d, eax
0x14002ead8  lea     rcx, aGrantprintbrok; "GrantPrintBrokerProcessAccess"
0x14002eadf  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14002eae4  jmp     loc_14002EB6C
0x14002eae9  mov     rax, [rsp+140h+var_D8]
0x14002eaee  lea     r9, [rsp+140h+NewAcl]; NewAcl
0x14002eaf3  mov     r8, [rsp+140h+ppDacl]; OldAcl
0x14002eaf8  lea     rdx, [rbp+40h+pListOfExplicitEntries]; pListOfExplicitEntries
0x14002eafc  mov     ecx, 1; cCountOfExplicitEntries
0x14002eb01  mov     [rbp+40h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x14002eb05  mov     [rbp+40h+pListOfExplicitEntries.grfAccessPermissions], 440h
0x14002eb0c  mov     qword ptr [rbp+40h+pListOfExplicitEntries.grfAccessMode], 1
0x14002eb14  mov     [rbp+40h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x14002eb18  mov     qword ptr [rbp+40h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rsi
0x14002eb1c  call    cs:__imp_SetEntriesInAclW
0x14002eb22  test    eax, eax
0x14002eb24  jz      short loc_14002EB2F
0x14002eb26  lea     rdx, aSetentriesinac; "SetEntriesInAcl failed to add PrintScan"...
0x14002eb2d  jmp     short loc_14002EAD5
0x14002eb2f  mov     rax, [rsp+140h+NewAcl]
0x14002eb34  xor     r9d, r9d; psidOwner
0x14002eb37  mov     qword ptr [rsp+140h+SubAuthority4], rsi; pSacl
0x14002eb3c  mov     rcx, rdi; handle
0x14002eb3f  mov     qword ptr [rsp+140h+SubAuthority3], rax; pDacl
0x14002eb44  mov     qword ptr [rsp+140h+SubAuthority2], rsi; psidGroup
0x14002eb49  lea     edx, [r9+6]; ObjectType
0x14002eb4d  lea     r8d, [r9+4]; SecurityInfo
0x14002eb51  call    cs:__imp_SetSecurityInfo
0x14002eb57  test    eax, eax
0x14002eb59  jz      short loc_14002EB67
0x14002eb5b  lea     rdx, aSetsecurityinf; "SetSecurityInfo failed %d"
0x14002eb62  jmp     loc_14002EAD5
0x14002eb67  mov     ebx, 1
0x14002eb6c  mov     rcx, [rsp+140h+NewAcl]; hMem
0x14002eb71  test    rcx, rcx
0x14002eb74  jz      short loc_14002EB7C
0x14002eb76  call    cs:__imp_LocalFree
0x14002eb7c  mov     rcx, [rsp+140h+ppSecurityDescriptor]; hMem
0x14002eb81  test    rcx, rcx
0x14002eb84  jz      short loc_14002EB8C
0x14002eb86  call    cs:__imp_LocalFree
0x14002eb8c  mov     eax, ebx
0x14002eb8e  mov     rcx, [rbp+40h+var_30]
0x14002eb92  xor     rcx, rsp; StackCookie
0x14002eb95  call    __security_check_cookie
0x14002eb9a  add     rsp, 128h
0x14002eba1  pop     rdi
0x14002eba2  pop     rsi
0x14002eba3  pop     rbx
0x14002eba4  pop     rbp
0x14002eba5  retn
```
