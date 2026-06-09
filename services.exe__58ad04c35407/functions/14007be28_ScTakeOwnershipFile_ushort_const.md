# ScTakeOwnershipFile(ushort const *)

- ea: `0x14007be28`
- end: `0x14007bff3`
- name: `?ScTakeOwnershipFile@@YAKPEBG@Z`
- size: `459`
- prototype: `unsigned int __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400790e4`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140016318`
- `0x14002b304`
- `0x140036514`
- `0x14007be28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bf4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bfa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bf4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007bfa1`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x14007bf42`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x14007bf97`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x14007bf42`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x14007bf97`
- `ntdll!RtlNtStatusToDosError` at `0x14007bed7`
- `ntdll!RtlNtStatusToDosError` at `0x14007bed7`
- `ntdll!RtlDeleteSecurityObject` at `0x14007bfdb`
- `ntdll!RtlDeleteSecurityObject` at `0x14007bfdb`

## pseudocode

```c
__int64 __fastcall ScTakeOwnershipFile(LPCWSTR lpFileName)
{
  int v2; // eax
  NTSTATUS v3; // ebx
  ULONG v4; // ebx
  ULONG Privilege; // eax
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v7; // rcx
  int v8; // edx
  __int16 v10; // [rsp+30h] [rbp-20h] BYREF
  char v11; // [rsp+32h] [rbp-1Eh]
  int v12; // [rsp+34h] [rbp-1Ch]
  PSID *v13; // [rsp+38h] [rbp-18h]
  unsigned int v14[4]; // [rsp+40h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp+18h] BYREF

  v13 = &LocalSystemSid;
  pSecurityDescriptor = 0;
  v14[0] = 17;
  v14[1] = 18;
  v14[2] = 8;
  v14[3] = 9;
  v10 = 0;
  v11 = 0;
  v12 = 0x10000000;
  v2 = ScCreateAndSetSD((__int64)&v10, 1u, LocalSystemSid, LocalSystemSid, (struct _ACL **)&pSecurityDescriptor);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 352, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v2);
    v4 = RtlNtStatusToDosError(v3);
    goto LABEL_21;
  }
  Privilege = ScGetPrivilege(4u, v14);
  v4 = Privilege;
  if ( !Privilege )
  {
    if ( SetFileSecurityW(lpFileName, 1u, pSecurityDescriptor) )
    {
      if ( SetFileSecurityW(lpFileName, 0xCu, pSecurityDescriptor) )
      {
        v4 = 0;
        goto LABEL_20;
      }
      LastError = GetLastError();
      v4 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_20;
      v8 = 355;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_20;
      v8 = 354;
    }
    WPP_SF_Sd(
      v7->StubInfo,
      v8,
      (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
      (_DWORD)lpFileName,
      LastError);
LABEL_20:
    ScReleasePrivilege();
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 353, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, Privilege);
LABEL_21:
  if ( pSecurityDescriptor )
    RtlDeleteSecurityObject(&pSecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x14007be28  mov     [rsp-8+arg_0], rbx
0x14007be2d  mov     [rsp-8+arg_10], rdi
0x14007be32  push    rbp
0x14007be33  mov     rbp, rsp
0x14007be36  sub     rsp, 50h
0x14007be3a  mov     r8, cs:LocalSystemSid
0x14007be41  lea     rax, LocalSystemSid
0x14007be48  mov     [rbp+var_18], rax
0x14007be4c  mov     rdi, rcx
0x14007be4f  lea     rax, [rbp+pSecurityDescriptor]
0x14007be53  mov     [rbp+pSecurityDescriptor], 0
0x14007be5b  mov     r9, r8
0x14007be5e  mov     [rsp+50h+var_30], rax
0x14007be63  mov     edx, 1
0x14007be68  mov     [rbp+var_10], 11h
0x14007be6f  lea     rcx, [rbp+var_20]
0x14007be73  mov     [rbp+var_C], 12h
0x14007be7a  mov     [rbp+var_8], 8
0x14007be81  mov     [rbp+var_4], 9
0x14007be88  mov     [rbp+var_20], 0
0x14007be8e  mov     [rbp+var_1E], 0
0x14007be92  mov     [rbp+var_1C], 10000000h
0x14007be99  call    ScCreateAndSetSD
0x14007be9e  mov     ebx, eax
0x14007bea0  test    eax, eax
0x14007bea2  jns     short loc_14007BEE4
0x14007bea4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007beab  lea     rdx, WPP_GLOBAL_Control
0x14007beb2  cmp     rcx, rdx
0x14007beb5  jz      short loc_14007BED5
0x14007beb7  test    byte ptr [rcx+1Ch], 1
0x14007bebb  jz      short loc_14007BED5
0x14007bebd  mov     rcx, [rcx+10h]
0x14007bec1  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007bec8  mov     edx, 160h
0x14007becd  mov     r9d, eax
0x14007bed0  call    WPP_SF_d
0x14007bed5  mov     ecx, ebx; Status
0x14007bed7  call    cs:__imp_RtlNtStatusToDosError
0x14007bedd  mov     ebx, eax
0x14007bedf  jmp     loc_14007BFD0
0x14007bee4  lea     rdx, [rbp+var_10]; unsigned int *
0x14007bee8  mov     ecx, 4; unsigned int
0x14007beed  call    ?ScGetPrivilege@@YAKKPEAK@Z; ScGetPrivilege(ulong,ulong *)
0x14007bef2  mov     ebx, eax
0x14007bef4  test    eax, eax
0x14007bef6  jz      short loc_14007BF36
0x14007bef8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007beff  lea     rdx, WPP_GLOBAL_Control
0x14007bf06  cmp     rcx, rdx
0x14007bf09  jz      loc_14007BFD0
0x14007bf0f  test    byte ptr [rcx+1Ch], 1
0x14007bf13  jz      loc_14007BFD0
0x14007bf19  mov     rcx, [rcx+10h]
0x14007bf1d  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007bf24  mov     edx, 161h
0x14007bf29  mov     r9d, eax
0x14007bf2c  call    WPP_SF_d
0x14007bf31  jmp     loc_14007BFD0
0x14007bf36  mov     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x14007bf3a  mov     edx, 1; SecurityInformation
0x14007bf3f  mov     rcx, rdi; lpFileName
0x14007bf42  call    cs:__imp_SetFileSecurityW
0x14007bf48  test    eax, eax
0x14007bf4a  jnz     short loc_14007BF8B
0x14007bf4c  call    cs:__imp_GetLastError
0x14007bf52  mov     ebx, eax
0x14007bf54  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bf5b  lea     rdx, WPP_GLOBAL_Control
0x14007bf62  cmp     rcx, rdx
0x14007bf65  jz      short loc_14007BFCB
0x14007bf67  test    byte ptr [rcx+1Ch], 1
0x14007bf6b  jz      short loc_14007BFCB
0x14007bf6d  mov     edx, 162h
0x14007bf72  mov     rcx, [rcx+10h]
0x14007bf76  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007bf7d  mov     r9, rdi
0x14007bf80  mov     dword ptr [rsp+50h+var_30], eax
0x14007bf84  call    WPP_SF_Sd
0x14007bf89  jmp     short loc_14007BFCB
0x14007bf8b  mov     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x14007bf8f  mov     edx, 0Ch; SecurityInformation
0x14007bf94  mov     rcx, rdi; lpFileName
0x14007bf97  call    cs:__imp_SetFileSecurityW
0x14007bf9d  test    eax, eax
0x14007bf9f  jnz     short loc_14007BFC9
0x14007bfa1  call    cs:__imp_GetLastError
0x14007bfa7  mov     ebx, eax
0x14007bfa9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bfb0  lea     rdx, WPP_GLOBAL_Control
0x14007bfb7  cmp     rcx, rdx
0x14007bfba  jz      short loc_14007BFCB
0x14007bfbc  test    byte ptr [rcx+1Ch], 1
0x14007bfc0  jz      short loc_14007BFCB
0x14007bfc2  mov     edx, 163h
0x14007bfc7  jmp     short loc_14007BF72
0x14007bfc9  xor     ebx, ebx
0x14007bfcb  call    ?ScReleasePrivilege@@YAKXZ; ScReleasePrivilege(void)
0x14007bfd0  cmp     [rbp+pSecurityDescriptor], 0
0x14007bfd5  jz      short loc_14007BFE1
0x14007bfd7  lea     rcx, [rbp+pSecurityDescriptor]; ObjectDescriptor
0x14007bfdb  call    cs:__imp_RtlDeleteSecurityObject
0x14007bfe1  mov     rdi, [rsp+50h+arg_10]
0x14007bfe6  mov     eax, ebx
0x14007bfe8  mov     rbx, [rsp+50h+arg_0]
0x14007bfed  add     rsp, 50h
0x14007bff1  pop     rbp
0x14007bff2  retn
```
