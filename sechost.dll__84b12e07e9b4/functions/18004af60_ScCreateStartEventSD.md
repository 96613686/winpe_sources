# ScCreateStartEventSD

- ea: `0x18004af60`
- end: `0x18004b169`
- name: `ScCreateStartEventSD`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b9a0`

## callees

- `0x18004ac10`
- `0x18004af60`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18004b10d`
- `ntdll!RtlNtStatusToDosError` at `0x18004b10d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004b145`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004b145`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004b00f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004b00f`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18004b101`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18004b101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b051`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004b047`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004b091`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004b0d2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004b047`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004b091`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004b0d2`

## pseudocode

```c
__int64 __fastcall ScCreateStartEventSD(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  ULONG LastError; // eax
  ULONG v6; // ebx
  NTSTATUS v7; // eax
  struct _ACL *v9; // [rsp+60h] [rbp-49h] BYREF
  __int16 v10; // [rsp+70h] [rbp-39h] BYREF
  char v11; // [rsp+72h] [rbp-37h]
  int v12; // [rsp+74h] [rbp-35h]
  PSID *v13; // [rsp+78h] [rbp-31h]
  __int16 v14; // [rsp+80h] [rbp-29h]
  char v15; // [rsp+82h] [rbp-27h]
  int v16; // [rsp+84h] [rbp-25h]
  PSID *v17; // [rsp+88h] [rbp-21h]
  __int16 v18; // [rsp+90h] [rbp-19h]
  char v19; // [rsp+92h] [rbp-17h]
  int v20; // [rsp+94h] [rbp-15h]
  PSID *v21; // [rsp+98h] [rbp-11h]
  __int16 v22; // [rsp+A0h] [rbp-9h]
  char v23; // [rsp+A2h] [rbp-7h]
  int v24; // [rsp+A4h] [rbp-5h]
  __int64 *v25; // [rsp+A8h] [rbp-1h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B0h] [rbp+7h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v27; // [rsp+B8h] [rbp+Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v28; // [rsp+C0h] [rbp+17h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  v9 = 0;
  v12 = 0x100000;
  v20 = 0x100000;
  v24 = 0x100000;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v25 = &LpacServicesManagementCapabilitySid;
  *(_DWORD *)v27.Value = 0;
  *(_WORD *)&v27.Value[4] = 1280;
  *(_DWORD *)v28.Value = 0;
  *(_WORD *)&v28.Value[4] = 3840;
  v10 = 0;
  v11 = 0;
  v13 = &WorldSid;
  v14 = 0;
  v15 = 0;
  v16 = 0x10000000;
  v17 = &LocalSystemSid;
  v18 = 0;
  v19 = 0;
  v21 = &AnyPackageSid;
  v22 = 0;
  v23 = 0;
  RtlAcquireSRWLockExclusive(&qword_18007C6A8);
  if ( (WorldSid || AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &WorldSid))
    && (LocalSystemSid || AllocateAndInitializeSid(&v27, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &LocalSystemSid))
    && (AnyPackageSid || AllocateAndInitializeSid(&v28, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &AnyPackageSid)) )
  {
    if ( !LpacServicesManagementCapabilitySid )
    {
      v7 = RtlDeriveCapabilitySidsFromName(
             L",.",
             &LpacServicesManagementCapabilityGroupSidBuffer,
             &LpacServicesManagementCapabilitySidBuffer);
      if ( v7 < 0 )
      {
LABEL_11:
        LastError = RtlNtStatusToDosError(v7);
        goto LABEL_4;
      }
      LpacServicesManagementCapabilitySid = (__int64)&LpacServicesManagementCapabilitySidBuffer;
    }
    v7 = ScCreateAndSetSD((__int64)&v10, v2, v3, v4, &v9);
    if ( v7 >= 0 )
    {
      *a1 = v9;
      v6 = 0;
      goto LABEL_15;
    }
    goto LABEL_11;
  }
  LastError = GetLastError();
LABEL_4:
  v6 = LastError;
LABEL_15:
  RtlReleaseSRWLockExclusive(&qword_18007C6A8);
  return v6;
}

```

## disassembly

```asm
0x18004af60  push    rbp
0x18004af62  push    rbx
0x18004af63  push    rsi
0x18004af64  push    rdi
0x18004af65  push    r14
0x18004af67  push    r15
0x18004af69  lea     rbp, [rsp-2Fh]
0x18004af6e  sub     rsp, 0D8h
0x18004af75  mov     rax, cs:__security_cookie
0x18004af7c  xor     rax, rsp
0x18004af7f  mov     [rbp+57h+var_38], rax
0x18004af83  xor     edi, edi
0x18004af85  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 100h
0x18004af8b  mov     eax, 100000h
0x18004af90  mov     [rbp+57h+var_A0], rdi
0x18004af94  mov     [rbp+57h+var_8C], eax
0x18004af97  lea     rsi, WorldSid
0x18004af9e  mov     [rbp+57h+var_6C], eax
0x18004afa1  lea     r14, LocalSystemSid
0x18004afa8  mov     [rbp+57h+var_5C], eax
0x18004afab  lea     r15, AnyPackageSid
0x18004afb2  lea     rax, LpacServicesManagementCapabilitySid
0x18004afb9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18004afbc  mov     rbx, rcx
0x18004afbf  mov     [rbp+57h+var_58], rax
0x18004afc3  lea     rcx, qword_18007C6A8
0x18004afca  mov     dword ptr [rbp+57h+var_48.Value], edi
0x18004afcd  mov     word ptr [rbp+57h+var_48.Value+4], 500h
0x18004afd3  mov     dword ptr [rbp+57h+var_40.Value], edi
0x18004afd6  mov     word ptr [rbp+57h+var_40.Value+4], 0F00h
0x18004afdc  mov     [rbp+57h+var_90], di
0x18004afe0  mov     [rbp+57h+var_8E], dil
0x18004afe4  mov     [rbp+57h+var_88], rsi
0x18004afe8  mov     [rbp+57h+var_80], di
0x18004afec  mov     [rbp+57h+var_7E], dil
0x18004aff0  mov     [rbp+57h+var_7C], 10000000h
0x18004aff7  mov     [rbp+57h+var_78], r14
0x18004affb  mov     [rbp+57h+var_70], di
0x18004afff  mov     [rbp+57h+var_6E], dil
0x18004b003  mov     [rbp+57h+var_68], r15
0x18004b007  mov     [rbp+57h+var_60], di
0x18004b00b  mov     [rbp+57h+var_5E], dil
0x18004b00f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18004b015  cmp     cs:WorldSid, rdi
0x18004b01c  jnz     short loc_18004B05E
0x18004b01e  mov     [rsp+100h+pSid], rsi; pSid
0x18004b023  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18004b027  mov     [rsp+100h+nSubAuthority7], edi; nSubAuthority7
0x18004b02b  xor     r9d, r9d; nSubAuthority1
0x18004b02e  mov     [rsp+100h+nSubAuthority6], edi; nSubAuthority6
0x18004b032  xor     r8d, r8d; nSubAuthority0
0x18004b035  mov     [rsp+100h+nSubAuthority5], edi; nSubAuthority5
0x18004b039  mov     dl, 1; nSubAuthorityCount
0x18004b03b  mov     [rsp+100h+nSubAuthority4], edi; nSubAuthority4
0x18004b03f  mov     [rsp+100h+nSubAuthority3], edi; nSubAuthority3
0x18004b043  mov     [rsp+100h+nSubAuthority2], edi; nSubAuthority2
0x18004b047  call    cs:__imp_AllocateAndInitializeSid
0x18004b04d  test    eax, eax
0x18004b04f  jnz     short loc_18004B05E
0x18004b051  call    cs:__imp_GetLastError
0x18004b057  mov     ebx, eax
0x18004b059  jmp     loc_18004B13E
0x18004b05e  cmp     cs:LocalSystemSid, rdi
0x18004b065  jnz     short loc_18004B09B
0x18004b067  mov     [rsp+100h+pSid], r14; pSid
0x18004b06c  lea     rcx, [rbp+57h+var_48]; pIdentifierAuthority
0x18004b070  mov     [rsp+100h+nSubAuthority7], edi; nSubAuthority7
0x18004b074  xor     r9d, r9d; nSubAuthority1
0x18004b077  mov     [rsp+100h+nSubAuthority6], edi; nSubAuthority6
0x18004b07b  mov     dl, 1; nSubAuthorityCount
0x18004b07d  mov     [rsp+100h+nSubAuthority5], edi; nSubAuthority5
0x18004b081  mov     [rsp+100h+nSubAuthority4], edi; nSubAuthority4
0x18004b085  mov     [rsp+100h+nSubAuthority3], edi; nSubAuthority3
0x18004b089  lea     r8d, [r9+12h]; nSubAuthority0
0x18004b08d  mov     [rsp+100h+nSubAuthority2], edi; nSubAuthority2
0x18004b091  call    cs:__imp_AllocateAndInitializeSid
0x18004b097  test    eax, eax
0x18004b099  jz      short loc_18004B051
0x18004b09b  cmp     cs:AnyPackageSid, rdi
0x18004b0a2  jnz     short loc_18004B0E0
0x18004b0a4  mov     [rsp+100h+pSid], r15; pSid
0x18004b0a9  lea     rcx, [rbp+57h+var_40]; pIdentifierAuthority
0x18004b0ad  mov     [rsp+100h+nSubAuthority7], edi; nSubAuthority7
0x18004b0b1  mov     r9d, 1; nSubAuthority1
0x18004b0b7  mov     [rsp+100h+nSubAuthority6], edi; nSubAuthority6
0x18004b0bb  mov     [rsp+100h+nSubAuthority5], edi; nSubAuthority5
0x18004b0bf  mov     [rsp+100h+nSubAuthority4], edi; nSubAuthority4
0x18004b0c3  lea     r8d, [r9+1]; nSubAuthority0
0x18004b0c7  mov     [rsp+100h+nSubAuthority3], edi; nSubAuthority3
0x18004b0cb  mov     dl, r8b; nSubAuthorityCount
0x18004b0ce  mov     [rsp+100h+nSubAuthority2], edi; nSubAuthority2
0x18004b0d2  call    cs:__imp_AllocateAndInitializeSid
0x18004b0d8  test    eax, eax
0x18004b0da  jz      loc_18004B051
0x18004b0e0  cmp     cs:LpacServicesManagementCapabilitySid, rdi
0x18004b0e7  jnz     short loc_18004B11F
0x18004b0e9  lea     rsi, ?LpacServicesManagementCapabilitySidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilitySidBuffer
0x18004b0f0  mov     r8, rsi
0x18004b0f3  lea     rdx, ?LpacServicesManagementCapabilityGroupSidBuffer@@3PAEA; uchar near * LpacServicesManagementCapabilityGroupSidBuffer
0x18004b0fa  lea     rcx, asc_18005E8B0; ",."
0x18004b101  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18004b107  test    eax, eax
0x18004b109  jns     short loc_18004B118
0x18004b10b  mov     ecx, eax; Status
0x18004b10d  call    cs:__imp_RtlNtStatusToDosError
0x18004b113  jmp     loc_18004B057
0x18004b118  mov     cs:LpacServicesManagementCapabilitySid, rsi
0x18004b11f  lea     rax, [rbp+57h+var_A0]
0x18004b123  lea     rcx, [rbp+57h+var_90]
0x18004b127  mov     qword ptr [rsp+100h+nSubAuthority2], rax
0x18004b12c  call    ScCreateAndSetSD
0x18004b131  test    eax, eax
0x18004b133  js      short loc_18004B10B
0x18004b135  mov     rax, [rbp+57h+var_A0]
0x18004b139  mov     [rbx], rax
0x18004b13c  mov     ebx, edi
0x18004b13e  lea     rcx, qword_18007C6A8
0x18004b145  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18004b14b  mov     eax, ebx
0x18004b14d  mov     rcx, [rbp+57h+var_38]
0x18004b151  xor     rcx, rsp; StackCookie
0x18004b154  call    __security_check_cookie
0x18004b159  add     rsp, 0D8h
0x18004b160  pop     r15
0x18004b162  pop     r14
0x18004b164  pop     rdi
0x18004b165  pop     rsi
0x18004b166  pop     rbx
0x18004b167  pop     rbp
0x18004b168  retn
```
