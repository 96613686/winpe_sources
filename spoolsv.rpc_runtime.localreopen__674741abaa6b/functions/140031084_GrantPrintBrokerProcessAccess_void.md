# GrantPrintBrokerProcessAccess(void)

- ea: `0x140031084`
- end: `0x140031291`
- name: `?GrantPrintBrokerProcessAccess@@YAHXZ`
- size: `525`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140031894`

## callees

- `0x14001748c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140031084`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x140031135`
- `ntdll!RtlAllocateAndInitializeSid` at `0x140031135`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400310a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400310a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140031254`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003126a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140031254`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003126a`
- `ADVAPI32!GetSecurityInfo` at `0x140031190`
- `ADVAPI32!GetSecurityInfo` at `0x140031190`
- `ADVAPI32!SetSecurityInfo` at `0x140031229`
- `ADVAPI32!SetSecurityInfo` at `0x140031229`
- `ADVAPI32!SetEntriesInAclW` at `0x1400311ee`
- `ADVAPI32!SetEntriesInAclW` at `0x1400311ee`

## string_xrefs

- `0x140031148`: `Failed to setup PrintScan Broker SID %d`
- `0x14003114f`: `GrantPrintBrokerProcessAccess`
- `0x1400311aa`: `GrantPrintBrokerProcessAccess`
- `0x1400311a0`: `GetSecurityInfo failed %d`
- `0x1400311fe`: `SetEntriesInAcl failed to add PrintScan Broker ACE %d`
- `0x140031239`: `SetSecurityInfo failed %d`

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
0x140031084  push    rbp
0x140031086  push    rbx
0x140031087  push    rsi
0x140031088  push    rdi
0x140031089  lea     rbp, [rsp-28h]
0x14003108e  sub     rsp, 128h
0x140031095  mov     rax, cs:__security_cookie
0x14003109c  xor     rax, rsp
0x14003109f  mov     [rbp+40h+var_30], rax
0x1400310a3  call    cs:__imp_GetCurrentProcess
0x1400310aa  nop     dword ptr [rax+rax+00h]
0x1400310af  xorps   xmm0, xmm0
0x1400310b2  lea     rcx, [rbp+40h+var_80]; void *
0x1400310b6  xor     esi, esi
0x1400310b8  xor     edx, edx; Val
0x1400310ba  mov     rdi, rax
0x1400310bd  mov     [rsp+140h+ppDacl], rsi
0x1400310c2  mov     [rsp+140h+ppSecurityDescriptor], rsi
0x1400310c7  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x1400310cb  lea     r8d, [rsi+44h]; Size
0x1400310cf  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x1400310d3  movups  xmmword ptr [rbp+40h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1400310d7  call    memset_0
0x1400310dc  lea     rax, [rbp+40h+var_80]
0x1400310e0  mov     [rsp+140h+NewAcl], rsi
0x1400310e5  mov     [rsp+140h+var_D8], rax
0x1400310ea  lea     r8d, [rsi+50h]; SubAuthority0
0x1400310ee  lea     rax, [rsp+140h+var_D8]
0x1400310f3  mov     dword ptr [rbp+40h+IdentifierAuthority.Value], esi
0x1400310f6  mov     [rsp+140h+Sid], rax; Sid
0x1400310fb  lea     rcx, [rbp+40h+IdentifierAuthority]; IdentifierAuthority
0x1400310ff  mov     [rsp+140h+SubAuthority7], esi; SubAuthority7
0x140031103  mov     r9d, 10185D4Dh; SubAuthority1
0x140031109  mov     [rsp+140h+SubAuthority6], esi; SubAuthority6
0x14003110d  mov     dl, 6; SubAuthorityCount
0x14003110f  mov     [rsp+140h+SubAuthority5], 0D10E9DDFh; SubAuthority5
0x140031117  mov     [rsp+140h+SubAuthority4], 1FA2CE07h; SubAuthority4
0x14003111f  mov     [rsp+140h+SubAuthority3], 93E3A09h; SubAuthority3
0x140031127  mov     [rsp+140h+SubAuthority2], 6025C496h; SubAuthority2
0x14003112f  mov     word ptr [rbp+40h+IdentifierAuthority.Value+4], 500h
0x140031135  call    cs:__imp_RtlAllocateAndInitializeSid
0x14003113c  nop     dword ptr [rax+rax+00h]
0x140031141  test    eax, eax
0x140031143  jns     short loc_140031162
0x140031145  mov     r8d, eax
0x140031148  lea     rdx, aFailedToSetupP; "Failed to setup PrintScan Broker SID %d"
0x14003114f  lea     rcx, aGrantprintbrok; "GrantPrintBrokerProcessAccess"
0x140031156  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003115b  xor     eax, eax
0x14003115d  jmp     loc_140031278
0x140031162  xor     r9d, r9d; ppsidOwner
0x140031165  lea     rax, [rsp+140h+ppSecurityDescriptor]
0x14003116a  mov     qword ptr [rsp+140h+SubAuthority5], rax; ppSecurityDescriptor
0x14003116f  mov     rcx, rdi; handle
0x140031172  lea     rax, [rsp+140h+ppDacl]
0x140031177  mov     qword ptr [rsp+140h+SubAuthority4], rsi; ppSacl
0x14003117c  mov     qword ptr [rsp+140h+SubAuthority3], rax; ppDacl
0x140031181  mov     ebx, esi
0x140031183  lea     edx, [r9+6]; ObjectType
0x140031187  mov     qword ptr [rsp+140h+SubAuthority2], rsi; ppsidGroup
0x14003118c  lea     r8d, [r9+4]; SecurityInfo
0x140031190  call    cs:__imp_GetSecurityInfo
0x140031197  nop     dword ptr [rax+rax+00h]
0x14003119c  test    eax, eax
0x14003119e  jz      short loc_1400311BB
0x1400311a0  lea     rdx, aGetsecurityinf; "GetSecurityInfo failed %d"
0x1400311a7  mov     r8d, eax
0x1400311aa  lea     rcx, aGrantprintbrok; "GrantPrintBrokerProcessAccess"
0x1400311b1  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400311b6  jmp     loc_14003124A
0x1400311bb  mov     rax, [rsp+140h+var_D8]
0x1400311c0  lea     r9, [rsp+140h+NewAcl]; NewAcl
0x1400311c5  mov     r8, [rsp+140h+ppDacl]; OldAcl
0x1400311ca  lea     rdx, [rbp+40h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1400311ce  mov     ecx, 1; cCountOfExplicitEntries
0x1400311d3  mov     [rbp+40h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1400311d7  mov     [rbp+40h+pListOfExplicitEntries.grfAccessPermissions], 440h
0x1400311de  mov     qword ptr [rbp+40h+pListOfExplicitEntries.grfAccessMode], 1
0x1400311e6  mov     [rbp+40h+pListOfExplicitEntries.Trustee.pMultipleTrustee], rsi
0x1400311ea  mov     qword ptr [rbp+40h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], rsi
0x1400311ee  call    cs:__imp_SetEntriesInAclW
0x1400311f5  nop     dword ptr [rax+rax+00h]
0x1400311fa  test    eax, eax
0x1400311fc  jz      short loc_140031207
0x1400311fe  lea     rdx, aSetentriesinac; "SetEntriesInAcl failed to add PrintScan"...
0x140031205  jmp     short loc_1400311A7
0x140031207  mov     rax, [rsp+140h+NewAcl]
0x14003120c  xor     r9d, r9d; psidOwner
0x14003120f  mov     qword ptr [rsp+140h+SubAuthority4], rsi; pSacl
0x140031214  mov     rcx, rdi; handle
0x140031217  mov     qword ptr [rsp+140h+SubAuthority3], rax; pDacl
0x14003121c  mov     qword ptr [rsp+140h+SubAuthority2], rsi; psidGroup
0x140031221  lea     edx, [r9+6]; ObjectType
0x140031225  lea     r8d, [r9+4]; SecurityInfo
0x140031229  call    cs:__imp_SetSecurityInfo
0x140031230  nop     dword ptr [rax+rax+00h]
0x140031235  test    eax, eax
0x140031237  jz      short loc_140031245
0x140031239  lea     rdx, aSetsecurityinf; "SetSecurityInfo failed %d"
0x140031240  jmp     loc_1400311A7
0x140031245  mov     ebx, 1
0x14003124a  mov     rcx, [rsp+140h+NewAcl]; hMem
0x14003124f  test    rcx, rcx
0x140031252  jz      short loc_140031260
0x140031254  call    cs:__imp_LocalFree
0x14003125b  nop     dword ptr [rax+rax+00h]
0x140031260  mov     rcx, [rsp+140h+ppSecurityDescriptor]; hMem
0x140031265  test    rcx, rcx
0x140031268  jz      short loc_140031276
0x14003126a  call    cs:__imp_LocalFree
0x140031271  nop     dword ptr [rax+rax+00h]
0x140031276  mov     eax, ebx
0x140031278  mov     rcx, [rbp+40h+var_30]
0x14003127c  xor     rcx, rsp; StackCookie
0x14003127f  call    __security_check_cookie
0x140031284  add     rsp, 128h
0x14003128b  pop     rdi
0x14003128c  pop     rsi
0x14003128d  pop     rbx
0x14003128e  pop     rbp
0x14003128f  retn
```
