# InitGlobalState

- ea: `0x180003320`
- end: `0x180003449`
- name: `InitGlobalState`
- size: `297`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003150`

## callees

- `0x180003320`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180003373`
- `ntdll!RtlAdjustPrivilege` at `0x1800033c5`
- `ntdll!RtlAdjustPrivilege` at `0x180003373`
- `ntdll!RtlAdjustPrivilege` at `0x1800033c5`
- `ntdll!RtlInitString` at `0x180003385`
- `ntdll!RtlInitString` at `0x1800033d7`
- `ntdll!RtlInitString` at `0x180003406`
- `ntdll!RtlInitString` at `0x180003385`
- `ntdll!RtlInitString` at `0x1800033d7`
- `ntdll!RtlInitString` at `0x180003406`
- `ntdll!RtlNtStatusToDosError` at `0x1800033a8`
- `ntdll!RtlNtStatusToDosError` at `0x1800033a8`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800033f0`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18000341f`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800033f0`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x18000341f`
- `SspiCli!LsaRegisterLogonProcess` at `0x18000339c`
- `SspiCli!LsaRegisterLogonProcess` at `0x18000339c`

## string_xrefs

- `0x180003379`: `Secondary Logon Service`

## pseudocode

```c
ULONG InitGlobalState()
{
  int v0; // eax
  struct _STRING v2; // [rsp+20h] [rbp-28h] BYREF
  struct _STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int8 OldValue; // [rsp+50h] [rbp+8h] BYREF
  ULONG SecurityMode; // [rsp+58h] [rbp+10h] BYREF

  OldValue = 0;
  SecurityMode = 0;
  DestinationString = 0;
  v2 = 0;
  *(_OWORD *)&g_state.dwServiceType = 0;
  *(_OWORD *)&g_state.dwServiceSpecificExitCode = 0;
  *(_OWORD *)&hServiceStatus = 0;
  *(_OWORD *)&AuthenticationPackage = 0;
  xmmword_1800096E0 = 0;
  RtlAdjustPrivilege(7u, 1u, 0, &OldValue);
  RtlInitString(&DestinationString, "Secondary Logon Service");
  v0 = LsaRegisterLogonProcess((PLSA_STRING)&DestinationString, (PHANDLE)&hServiceStatus + 1, &SecurityMode);
  if ( v0 < 0 )
    return RtlNtStatusToDosError(v0);
  RtlAdjustPrivilege(7u, OldValue, 0, &OldValue);
  RtlInitString(&v2, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
  v0 = LsaLookupAuthenticationPackage(*(&hServiceStatus + 1), (PLSA_STRING)&v2, &AuthenticationPackage);
  if ( v0 < 0 )
    return RtlNtStatusToDosError(v0);
  RtlInitString(&v2, "Negotiate");
  v0 = LsaLookupAuthenticationPackage(*(&hServiceStatus + 1), (PLSA_STRING)&v2, &AuthenticationPackage + 1);
  if ( v0 < 0 )
    return RtlNtStatusToDosError(v0);
  *((_QWORD *)&xmmword_1800096E0 + 1) = &xmmword_1800096E0;
  *(_QWORD *)&xmmword_1800096E0 = &xmmword_1800096E0;
  return 0;
}

```

## disassembly

```asm
0x180003320  sub     rsp, 48h
0x180003324  xorps   xmm0, xmm0
0x180003327  mov     [rsp+48h+OldValue], 0
0x18000332c  xorps   xmm1, xmm1
0x18000332f  mov     [rsp+48h+SecurityMode], 0
0x180003337  lea     r9, [rsp+48h+OldValue]; OldValue
0x18000333c  xor     r8d, r8d; ForThread
0x18000333f  mov     dl, 1; NewValue
0x180003341  mov     ecx, 7; Privilege
0x180003346  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18000334b  movups  xmmword ptr [rsp+48h+var_28.Length], xmm1
0x180003350  movups  xmmword ptr cs:g_state.dwServiceType, xmm0
0x180003357  movups  xmmword ptr cs:g_state.dwServiceSpecificExitCode, xmm0
0x18000335e  movups  cs:hServiceStatus, xmm0
0x180003365  movups  cs:AuthenticationPackage, xmm0
0x18000336c  movups  cs:xmmword_1800096E0, xmm0
0x180003373  call    cs:__imp_RtlAdjustPrivilege
0x180003379  lea     rdx, aSecondaryLogon; "Secondary Logon Service"
0x180003380  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180003385  call    cs:__imp_RtlInitString
0x18000338b  lea     r8, [rsp+48h+SecurityMode]; SecurityMode
0x180003390  lea     rdx, hServiceStatus+8; LsaHandle
0x180003397  lea     rcx, [rsp+48h+DestinationString]; LogonProcessName
0x18000339c  call    cs:__imp_LsaRegisterLogonProcess
0x1800033a2  test    eax, eax
0x1800033a4  jns     short loc_1800033B3
0x1800033a6  mov     ecx, eax; Status
0x1800033a8  call    cs:__imp_RtlNtStatusToDosError
0x1800033ae  add     rsp, 48h
0x1800033b2  retn
0x1800033b3  movzx   edx, [rsp+48h+OldValue]; NewValue
0x1800033b8  lea     r9, [rsp+48h+OldValue]; OldValue
0x1800033bd  xor     r8d, r8d; ForThread
0x1800033c0  mov     ecx, 7; Privilege
0x1800033c5  call    cs:__imp_RtlAdjustPrivilege
0x1800033cb  lea     rdx, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x1800033d2  lea     rcx, [rsp+48h+var_28]; DestinationString
0x1800033d7  call    cs:__imp_RtlInitString
0x1800033dd  mov     rcx, qword ptr cs:hServiceStatus+8; LsaHandle
0x1800033e4  lea     r8, AuthenticationPackage; AuthenticationPackage
0x1800033eb  lea     rdx, [rsp+48h+var_28]; PackageName
0x1800033f0  call    cs:__imp_LsaLookupAuthenticationPackage
0x1800033f6  test    eax, eax
0x1800033f8  js      short loc_1800033A6
0x1800033fa  lea     rdx, aNegotiate; "Negotiate"
0x180003401  lea     rcx, [rsp+48h+var_28]; DestinationString
0x180003406  call    cs:__imp_RtlInitString
0x18000340c  mov     rcx, qword ptr cs:hServiceStatus+8; LsaHandle
0x180003413  lea     r8, AuthenticationPackage+4; AuthenticationPackage
0x18000341a  lea     rdx, [rsp+48h+var_28]; PackageName
0x18000341f  call    cs:__imp_LsaLookupAuthenticationPackage
0x180003425  test    eax, eax
0x180003427  js      loc_1800033A6
0x18000342d  lea     rax, xmmword_1800096E0
0x180003434  mov     qword ptr cs:xmmword_1800096E0+8, rax
0x18000343b  mov     qword ptr cs:xmmword_1800096E0, rax
0x180003442  xor     eax, eax
0x180003444  jmp     loc_1800033AE
```
