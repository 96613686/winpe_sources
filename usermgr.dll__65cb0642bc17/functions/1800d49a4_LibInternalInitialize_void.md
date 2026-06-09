# LibInternalInitialize(void)

- ea: `0x1800d49a4`
- end: `0x1800d4b23`
- name: `?LibInternalInitialize@@YAXXZ`
- size: `383`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d40a0`

## callees

- `0x1800d49a4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d4a8d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d4a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d4a97`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800d4a12`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800d4a3b`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800d4a57`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800d4a73`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800d4a12`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800d4a3b`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800d4a57`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800d4a73`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800d4abd`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800d4ae1`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800d4abd`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800d4ae1`
- `ntdll!RtlNtStatusToDosError` at `0x1800d4a1e`
- `ntdll!RtlNtStatusToDosError` at `0x1800d4a1e`

## string_xrefs

- `0x1800d49e0`: `sessionImpersonation`
- `0x1800d49c6`: `constrainedImpersonation`

## pseudocode

```c
void LibInternalInitialize(void)
{
  NTSTATUS v0; // eax
  ULONG LastError; // eax
  _QWORD v2[2]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v3[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v4[2]; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v5[2]; // [rsp+60h] [rbp-10h] BYREF
  DWORD cbSid; // [rsp+80h] [rbp+10h] BYREF

  cbSid = 68;
  v2[1] = L"activateAsUser";
  v2[0] = 1966108;
  v3[1] = L"constrainedImpersonation";
  v3[0] = 3276848;
  v4[1] = L"sessionImpersonation";
  v4[0] = 2752552;
  v5[1] = L"muma";
  v5[0] = 655368;
  v0 = RtlDeriveCapabilitySidsFromName(v2, &CapActivateGroupSidBuffer, &CapActivateSidBuffer);
  if ( v0 < 0
    || (v0 = RtlDeriveCapabilitySidsFromName(
               v3,
               &CapConstrainedImpersonationGroupSidBuffer,
               &CapConstrainedImpersonationSidBuffer),
        v0 < 0)
    || (v0 = RtlDeriveCapabilitySidsFromName(
               v4,
               &CapSessionImpersonationGroupSidBuffer,
               &CapSessionImpersonationSidBuffer),
        v0 < 0)
    || (v0 = RtlDeriveCapabilitySidsFromName(v5, &CapMumaGroupSidBuffer, &CapMumaSidBuffer), v0 < 0) )
  {
    LastError = RtlNtStatusToDosError(v0);
  }
  else if ( CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, &DefaultAliasWellKnownSid, &cbSid) )
  {
    RtlQueryRegistryValuesEx(2, L"Session Manager\\NamespaceSeparation", &qword_1800FA850);
    RtlQueryRegistryValuesEx(2, L"Session Manager\\Kernel", &qword_1800FA930);
    if ( InteractiveUserNameSpaceSeparation )
      AppcontainerUserNameSpaceSeparation = 1;
    if ( DefaultAccountNameSpaceSeparation && !InteractiveUserNameSpaceSeparation )
      DefaultAccountNameSpaceSeparation = 0;
    SuccessfulInit = 1;
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  LODWORD(InitializeError) = LastError;
}

```

## disassembly

```asm
0x1800d49a4  push    rbp
0x1800d49a6  mov     rbp, rsp
0x1800d49a9  sub     rsp, 70h
0x1800d49ad  lea     rax, aActivateasuser; "activateAsUser"
0x1800d49b4  mov     [rbp+cbSid], 44h ; 'D'
0x1800d49bb  mov     [rbp+var_38], rax
0x1800d49bf  lea     r8, ?CapActivateSidBuffer@@3PAEA; uchar near * CapActivateSidBuffer
0x1800d49c6  lea     rax, aConstrainedimp; "constrainedImpersonation"
0x1800d49cd  mov     [rbp+var_40], 1E001Ch
0x1800d49d5  mov     [rbp+var_28], rax
0x1800d49d9  lea     rdx, ?CapActivateGroupSidBuffer@@3PAEA; uchar near * CapActivateGroupSidBuffer
0x1800d49e0  lea     rax, aSessionimperso; "sessionImpersonation"
0x1800d49e7  mov     [rbp+var_30], 320030h
0x1800d49ef  mov     [rbp+var_18], rax
0x1800d49f3  lea     rcx, [rbp+var_40]
0x1800d49f7  lea     rax, aMuma; "muma"
0x1800d49fe  mov     [rbp+var_20], 2A0028h
0x1800d4a06  mov     [rbp+var_8], rax
0x1800d4a0a  mov     [rbp+var_10], 0A0008h
0x1800d4a12  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800d4a18  test    eax, eax
0x1800d4a1a  jns     short loc_1800D4A29
0x1800d4a1c  mov     ecx, eax; Status
0x1800d4a1e  call    cs:__imp_RtlNtStatusToDosError
0x1800d4a24  jmp     loc_1800D4B17
0x1800d4a29  lea     r8, ?CapConstrainedImpersonationSidBuffer@@3PAEA; uchar near * CapConstrainedImpersonationSidBuffer
0x1800d4a30  lea     rdx, ?CapConstrainedImpersonationGroupSidBuffer@@3PAEA; uchar near * CapConstrainedImpersonationGroupSidBuffer
0x1800d4a37  lea     rcx, [rbp+var_30]
0x1800d4a3b  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800d4a41  test    eax, eax
0x1800d4a43  js      short loc_1800D4A1C
0x1800d4a45  lea     r8, ?CapSessionImpersonationSidBuffer@@3PAEA; uchar near * CapSessionImpersonationSidBuffer
0x1800d4a4c  lea     rdx, ?CapSessionImpersonationGroupSidBuffer@@3PAEA; uchar near * CapSessionImpersonationGroupSidBuffer
0x1800d4a53  lea     rcx, [rbp+var_20]
0x1800d4a57  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800d4a5d  test    eax, eax
0x1800d4a5f  js      short loc_1800D4A1C
0x1800d4a61  lea     r8, ?CapMumaSidBuffer@@3PAEA; uchar near * CapMumaSidBuffer
0x1800d4a68  lea     rdx, ?CapMumaGroupSidBuffer@@3PAEA; uchar near * CapMumaGroupSidBuffer
0x1800d4a6f  lea     rcx, [rbp+var_10]
0x1800d4a73  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800d4a79  test    eax, eax
0x1800d4a7b  js      short loc_1800D4A1C
0x1800d4a7d  xor     edx, edx; DomainSid
0x1800d4a7f  lea     r9, [rbp+cbSid]; cbSid
0x1800d4a83  lea     r8, ?DefaultAliasWellKnownSid@@3PAEA; pSid
0x1800d4a8a  lea     ecx, [rdx+6Fh]; WellKnownSidType
0x1800d4a8d  call    cs:__imp_CreateWellKnownSid
0x1800d4a93  test    eax, eax
0x1800d4a95  jnz     short loc_1800D4A9F
0x1800d4a97  call    cs:__imp_GetLastError
0x1800d4a9d  jmp     short loc_1800D4B17
0x1800d4a9f  xor     r9d, r9d
0x1800d4aa2  mov     [rsp+70h+var_50], 0
0x1800d4aab  lea     r8, qword_1800FA850
0x1800d4ab2  lea     rdx, aSessionManager; "Session Manager\\NamespaceSeparation"
0x1800d4ab9  lea     ecx, [r9+2]
0x1800d4abd  call    cs:__imp_RtlQueryRegistryValuesEx
0x1800d4ac3  xor     r9d, r9d
0x1800d4ac6  mov     [rsp+70h+var_50], 0
0x1800d4acf  lea     r8, qword_1800FA930
0x1800d4ad6  lea     rdx, aSessionManager_0; "Session Manager\\Kernel"
0x1800d4add  lea     ecx, [r9+2]
0x1800d4ae1  call    cs:__imp_RtlQueryRegistryValuesEx
0x1800d4ae7  mov     eax, cs:?InteractiveUserNameSpaceSeparation@@3KA; ulong InteractiveUserNameSpaceSeparation
0x1800d4aed  mov     ecx, 1
0x1800d4af2  test    eax, eax
0x1800d4af4  jz      short loc_1800D4AFC
0x1800d4af6  mov     cs:?AppcontainerUserNameSpaceSeparation@@3KA, ecx; ulong AppcontainerUserNameSpaceSeparation
0x1800d4afc  cmp     cs:?DefaultAccountNameSpaceSeparation@@3KA, 0; ulong DefaultAccountNameSpaceSeparation
0x1800d4b03  jz      short loc_1800D4B0F
0x1800d4b05  test    eax, eax
0x1800d4b07  jnz     short loc_1800D4B0F
0x1800d4b09  mov     cs:?DefaultAccountNameSpaceSeparation@@3KA, eax; ulong DefaultAccountNameSpaceSeparation
0x1800d4b0f  mov     cs:?SuccessfulInit@@3KA, ecx; ulong SuccessfulInit
0x1800d4b15  xor     eax, eax
0x1800d4b17  mov     cs:?InitializeError@@3KA, eax; ulong InitializeError
0x1800d4b1d  add     rsp, 70h
0x1800d4b21  pop     rbp
0x1800d4b22  retn
```
