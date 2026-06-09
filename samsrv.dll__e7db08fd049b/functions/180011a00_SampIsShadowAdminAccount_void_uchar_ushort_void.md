# SampIsShadowAdminAccount(void *,uchar *,ushort * *,void * *)

- ea: `0x180011a00`
- end: `0x180011fda`
- name: `?SampIsShadowAdminAccount@@YAJPEAXPEAEPEAPEAGPEAPEAX@Z`
- size: `1498`
- prototype: `__int64 __fastcall(void *Src, unsigned __int8 *, unsigned __int16 **, void **)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800261c0`
- `0x18008fcd8`

## callees

- `0x180002360`
- `0x180003860`
- `0x180006170`
- `0x180008590`
- `0x180011810`
- `0x180011a00`
- `0x180012a28`
- `0x1800198a0`
- `0x18001cfa0`
- `0x18001d960`
- `0x180023760`
- `0x1800270b4`
- `0x180027e24`
- `0x1800372ac`
- `0x180078fb4`
- `0x18008ecd0`
- `0x1800ab48c`
- `0x1800bb794`

## import_xrefs

- `ntdll!NtCloseObjectAuditAlarm` at `0x180011ecd`
- `ntdll!NtCloseObjectAuditAlarm` at `0x180011ecd`
- `ntdll!RtlSubAuthorityCountSid` at `0x180011a57`
- `ntdll!RtlSubAuthorityCountSid` at `0x180011ab0`
- `ntdll!RtlSubAuthorityCountSid` at `0x180011a57`
- `ntdll!RtlSubAuthorityCountSid` at `0x180011ab0`
- `ntdll!RtlSubAuthoritySid` at `0x180011abe`
- `ntdll!RtlSubAuthoritySid` at `0x180011abe`
- `ntdll!RtlLeaveCriticalSection` at `0x180011f58`
- `ntdll!RtlLeaveCriticalSection` at `0x180011f58`
- `ntdll!RtlEnterCriticalSection` at `0x180011bea`
- `ntdll!RtlEnterCriticalSection` at `0x180011f20`
- `ntdll!RtlEnterCriticalSection` at `0x180011bea`
- `ntdll!RtlEnterCriticalSection` at `0x180011f20`
- `ntdll!RtlLengthSid` at `0x180011a75`
- `ntdll!RtlLengthSid` at `0x180011a75`
- `ntdll!RtlEqualSid` at `0x180011b4f`
- `ntdll!RtlEqualSid` at `0x180011b4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011a84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011f84`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011bd4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011bf7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011bd4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011bf7`
- `RPCRT4!RpcRevertToSelf` at `0x180011efa`
- `RPCRT4!RpcRevertToSelf` at `0x180011efa`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x180011c60`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x180011c60`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x180011eeb`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x180011eeb`

## pseudocode

```c
__int64 __fastcall SampIsShadowAdminAccount(void *Src, unsigned __int8 *a2, HLOCAL *a3, void **a4)
{
  void *v4; // r14
  int v9; // ebx
  HLOCAL v10; // rax
  unsigned int v11; // esi
  SIZE_T v12; // rsi
  PUCHAR v13; // rax
  PUNICODE_STRING v14; // rcx
  DWORD TickCount; // ebx
  DWORD v16; // eax
  unsigned int v17; // ecx
  DWORD v18; // eax
  ULONG v19; // edi
  unsigned int AccountContext2; // eax
  PUNICODE_STRING v21; // rcx
  PVOID v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // r9
  int v25; // eax
  int ExtendedAttribute; // eax
  int UnicodeStringAttribute; // eax
  int v28; // eax
  int v29; // eax
  bool v30; // zf
  ULONG v31; // edi
  char v32; // al
  PVOID *v33; // rcx
  PVOID *v34; // rax
  void *v36; // [rsp+70h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-11h] BYREF
  PVOID HandleId; // [rsp+80h] [rbp-9h] BYREF
  void *v39[2]; // [rsp+88h] [rbp-1h] BYREF
  struct _UNICODE_STRING v40; // [rsp+98h] [rbp+Fh] BYREF
  ULONG v41; // [rsp+F8h] [rbp+6Fh] BYREF
  int v42; // [rsp+100h] [rbp+77h] BYREF
  PSID Sid; // [rsp+108h] [rbp+7Fh]

  v42 = 39;
  hMem = 0;
  v36 = 0;
  v4 = 0;
  HandleId = 0;
  *(_OWORD *)v39 = 0;
  *a2 = 0;
  v40 = 0;
  *a3 = 0;
  *a4 = 0;
  v9 = *RtlSubAuthorityCountSid(Src);
  if ( !(_BYTE)v9 )
  {
    v10 = 0;
    v11 = -1073741704;
    Sid = 0;
LABEL_5:
    v41 = 0;
    goto LABEL_7;
  }
  v12 = RtlLengthSid(Src);
  v10 = LocalAlloc(0x40u, v12);
  Sid = v10;
  if ( !v10 )
  {
    v11 = -1073741670;
    goto LABEL_5;
  }
  memmove_0(v10, Src, v12);
  v13 = RtlSubAuthorityCountSid(Sid);
  --*v13;
  v11 = 0;
  v41 = *RtlSubAuthoritySid(Src, v9 - 1);
  v10 = Sid;
LABEL_7:
  v14 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 128, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v11, v11);
    v14 = WPP_GLOBAL_Control;
    v10 = Sid;
  }
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( (*(_DWORD *)(&v14[4].MaximumLength + 1) & 0x400) != 0 && HIBYTE(v14[4].Length) >= 2u )
      WPP_SF_d(v14[3].Buffer, 17, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, v11);
    goto LABEL_82;
  }
  if ( !RtlEqualSid(v10, *((PSID *)SampDefinedDomains + 171)) )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
    {
      WPP_SF__sid_(WPP_GLOBAL_Control[3].Buffer, 18, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, Src);
    }
    v11 = -1073741724;
    goto LABEL_82;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
  if ( !SampUseDsData || !(unsigned int)SampExtIsWriteLockHeldByDs() )
  {
    TickCount = GetTickCount();
    _InterlockedIncrement((volatile signed __int32 *)&SamLockQueueLength);
    RtlEnterCriticalSection(&SampLock);
    _InterlockedDecrement((volatile signed __int32 *)&SamLockQueueLength);
    v16 = GetTickCount();
    v17 = SamLockTotalAquisitions + 1;
    SamLockCurrentHoldStartTime = v16;
    ++SamLockTotalAquisitions;
    v18 = v16 - TickCount;
    if ( v18 && v17 )
      SamCumulativeWaitTime += v18;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    if ( SampUseDsData && (int)SampShouldCallNtdsaApiSet() >= 0 )
      NtdsaExtSetGlobalTransactionType(0);
  }
  SampSetTransactionDomain(1);
  v19 = 0;
  AccountContext2 = SampCreateAccountContext2(0, 4, v41, 0, 0, 1, 1, 0, 0, 1, 0, 0, 0, (__int64)&HandleId);
  v11 = AccountContext2;
  v21 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      123,
      WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
      AccountContext2,
      AccountContext2);
    v21 = WPP_GLOBAL_Control;
  }
  v22 = HandleId;
  if ( (v11 & 0x80000000) != 0 )
  {
    if ( (*(_DWORD *)(&v21[4].MaximumLength + 1) & 0x400) == 0 || HIBYTE(v21[4].Length) < 2u )
      goto LABEL_61;
    v23 = 19;
    v24 = v11;
    goto LABEL_36;
  }
  v25 = SampReadExtendedAttributes((struct _SAMP_OBJECT *)HandleId, 0, &v42, 1u);
  v11 = v25;
  if ( v25 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_61;
    }
    v23 = 20;
    v24 = (unsigned int)v25;
    goto LABEL_36;
  }
  ExtendedAttribute = SampGetExtendedAttribute((__int64)v22, 39, (__int64)v39);
  v11 = ExtendedAttribute;
  if ( ExtendedAttribute < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_61;
    }
    v23 = 21;
    v24 = (unsigned int)ExtendedAttribute;
    goto LABEL_36;
  }
  if ( !LODWORD(v39[0]) )
  {
    v11 = 0;
    goto LABEL_61;
  }
  UnicodeStringAttribute = SampGetUnicodeStringAttribute((struct _SAMP_OBJECT *)v22);
  v11 = UnicodeStringAttribute;
  if ( UnicodeStringAttribute < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) == 0
      || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
    {
      goto LABEL_61;
    }
    v23 = 22;
    v24 = (unsigned int)UnicodeStringAttribute;
    goto LABEL_36;
  }
  v28 = SampCopyUnicodeString(&v40, (unsigned __int16 **)&hMem);
  v11 = v28;
  if ( v28 >= 0 )
  {
    v29 = SampCopySid(&v36, v39[1]);
    v11 = v29;
    if ( v29 >= 0 )
    {
      *a3 = hMem;
      *a4 = v36;
      *a2 = 1;
      hMem = 0;
    }
    else
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
        && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 24, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, (unsigned int)v29);
      }
      v4 = v36;
    }
    goto LABEL_61;
  }
  v21 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x400) != 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    v23 = 23;
    v24 = (unsigned int)v28;
LABEL_36:
    WPP_SF_d(v21[3].Buffer, v23, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, v24);
  }
LABEL_61:
  if ( v22 )
  {
    *((_BYTE *)v22 + 20) |= 0x10u;
    v30 = (*((_BYTE *)v22 + 20) & 0x20) == 0;
    v41 = 0;
    if ( v30 )
    {
      SampImpersonateClient(&v41);
      v19 = v41;
    }
    NtCloseObjectAuditAlarm(&SampSamSubsystem, v22, *((_BYTE *)v22 + 208));
    if ( v19 == 2 )
    {
      RpcRevertToSelf();
    }
    else
    {
      v31 = v19 - 1;
      if ( v31 )
      {
        if ( v31 == 2 && (int)SampShouldCallNtdsaApiSet() >= 0 )
          NtdsaExtUnImpersonateAnyClient();
      }
      else
      {
        SamIRevertNullSession();
      }
    }
    *((_BYTE *)v22 + 21) &= ~1u;
    v32 = *((_BYTE *)v22 + 28);
    if ( ((v32 & 1) == 0 || (*((_BYTE *)v22 + 192) & 2) == 0) && v32 >= 0 )
    {
      RtlEnterCriticalSection(&SampContextListCritSect);
      v33 = *(PVOID **)v22;
      if ( *(_QWORD *)v22 )
      {
        v34 = (PVOID *)*((_QWORD *)v22 + 1);
        if ( v34 )
        {
          if ( v33[1] != v22 || *v34 != v22 )
            __fastfail(3u);
          *v34 = v33;
          v33[1] = v34;
        }
      }
      RtlLeaveCriticalSection(&SampContextListCritSect);
    }
    SampDeReferenceContext(v22, 0);
  }
  SampReleaseReadLock();
LABEL_82:
  LocalFree(v4);
  LocalFree(hMem);
  LocalFree(Sid);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 25, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids, v11, v11);
  return v11;
}

```

## disassembly

```asm
0x180011a00  mov     [rsp-8+arg_0], rbx
0x180011a05  push    rbp
0x180011a06  push    rsi
0x180011a07  push    rdi
0x180011a08  push    r12
0x180011a0a  push    r13
0x180011a0c  push    r14
0x180011a0e  push    r15
0x180011a10  lea     rbp, [rsp-27h]
0x180011a15  sub     rsp, 0B0h
0x180011a1c  xor     esi, esi
0x180011a1e  mov     [rbp+57h+arg_10], 27h ; '''
0x180011a25  xorps   xmm0, xmm0
0x180011a28  mov     [rbp+57h+hMem], rsi
0x180011a2c  xorps   xmm1, xmm1
0x180011a2f  mov     [rbp+57h+var_70], rsi
0x180011a33  mov     r14d, esi
0x180011a36  mov     [rbp+57h+HandleId], rsi
0x180011a3a  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180011a3e  mov     [rdx], sil
0x180011a41  mov     r15, r9
0x180011a44  movups  xmmword ptr [rbp+57h+var_48.Length], xmm1
0x180011a48  mov     [r8], rsi
0x180011a4b  mov     r12, r8
0x180011a4e  mov     [r9], rsi
0x180011a51  mov     r13, rdx
0x180011a54  mov     rdi, rcx
0x180011a57  call    cs:__imp_RtlSubAuthorityCountSid
0x180011a5d  movzx   ebx, byte ptr [rax]
0x180011a60  cmp     bl, 1
0x180011a63  jnb     short loc_180011A72
0x180011a65  mov     eax, esi
0x180011a67  mov     esi, 0C0000078h
0x180011a6c  mov     [rbp+57h+Sid], rax
0x180011a70  jmp     short loc_180011A98
0x180011a72  mov     rcx, rdi; Sid
0x180011a75  call    cs:__imp_RtlLengthSid
0x180011a7b  mov     edx, eax; uBytes
0x180011a7d  mov     ecx, 40h ; '@'; uFlags
0x180011a82  mov     esi, eax
0x180011a84  call    cs:__imp_LocalAlloc
0x180011a8a  mov     [rbp+57h+Sid], rax
0x180011a8e  test    rax, rax
0x180011a91  jnz     short loc_180011A9E
0x180011a93  mov     esi, 0C000009Ah
0x180011a98  mov     [rbp+57h+arg_8], r14d
0x180011a9c  jmp     short loc_180011ACF
0x180011a9e  mov     r8, rsi; Size
0x180011aa1  mov     rdx, rdi; Src
0x180011aa4  mov     rcx, rax; void *
0x180011aa7  call    memmove_0
0x180011aac  mov     rcx, [rbp+57h+Sid]; Sid
0x180011ab0  call    cs:__imp_RtlSubAuthorityCountSid
0x180011ab6  lea     edx, [rbx-1]; SubAuthority
0x180011ab9  mov     rcx, rdi; Sid
0x180011abc  dec     byte ptr [rax]
0x180011abe  call    cs:__imp_RtlSubAuthoritySid
0x180011ac4  xor     esi, esi
0x180011ac6  mov     eax, [rax]
0x180011ac8  mov     [rbp+57h+arg_8], eax
0x180011acb  mov     rax, [rbp+57h+Sid]
0x180011acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ad6  test    dword ptr [rcx+44h], 20000h
0x180011add  jz      short loc_180011B06
0x180011adf  mov     rcx, [rcx+38h]
0x180011ae3  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180011aea  mov     edx, 80h
0x180011aef  mov     dword ptr [rsp+0E0h+var_C0], esi
0x180011af3  mov     r9d, esi
0x180011af6  call    WPP_SF_Dd
0x180011afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b02  mov     rax, [rbp+57h+Sid]
0x180011b06  test    esi, esi
0x180011b08  jns     short loc_180011B3E
0x180011b0a  test    dword ptr [rcx+44h], 400h
0x180011b11  jz      loc_180011F6D
0x180011b17  cmp     byte ptr [rcx+41h], 2
0x180011b1b  jb      loc_180011F6D
0x180011b21  mov     rcx, [rcx+38h]
0x180011b25  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x180011b2c  mov     edx, 11h
0x180011b31  mov     r9d, esi
0x180011b34  call    WPP_SF_d
0x180011b39  jmp     loc_180011F6D
0x180011b3e  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180011b45  mov     rcx, rax; Sid1
0x180011b48  mov     rdx, [rdx+558h]; Sid2
0x180011b4f  call    cs:__imp_RtlEqualSid
0x180011b55  test    al, al
0x180011b57  jnz     short loc_180011B91
0x180011b59  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b60  test    dword ptr [rcx+44h], 400h
0x180011b67  jz      short loc_180011B87
0x180011b69  cmp     byte ptr [rcx+41h], 3
0x180011b6d  jb      short loc_180011B87
0x180011b6f  mov     rcx, [rcx+38h]
0x180011b73  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x180011b7a  mov     edx, 12h
0x180011b7f  mov     r9, rdi
0x180011b82  call    WPP_SF__sid_
0x180011b87  mov     esi, 0C0000064h
0x180011b8c  jmp     loc_180011F6D
0x180011b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b98  test    dword ptr [rcx+44h], 20000h
0x180011b9f  jz      short loc_180011BBE
0x180011ba1  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180011ba9  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180011bb0  mov     rcx, [rcx+38h]
0x180011bb4  mov     edx, 49h ; 'I'
0x180011bb9  call    WPP_SF_d
0x180011bbe  cmp     cs:?SampUseDsData@@3EA, r14b; uchar SampUseDsData
0x180011bc5  jz      short loc_180011BD4
0x180011bc7  call    ?SampExtIsWriteLockHeldByDs@@YAHXZ; SampExtIsWriteLockHeldByDs(void)
0x180011bcc  test    eax, eax
0x180011bce  jnz     loc_180011C66
0x180011bd4  call    cs:__imp_GetTickCount
0x180011bda  mov     ebx, eax
0x180011bdc  lock inc cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x180011be3  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180011bea  call    cs:__imp_RtlEnterCriticalSection
0x180011bf0  lock dec cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x180011bf7  call    cs:__imp_GetTickCount
0x180011bfd  mov     ecx, cs:?SamLockTotalAquisitions@@3KA; ulong SamLockTotalAquisitions
0x180011c03  inc     ecx
0x180011c05  mov     cs:?SamLockCurrentHoldStartTime@@3KA, eax; ulong SamLockCurrentHoldStartTime
0x180011c0b  mov     cs:?SamLockTotalAquisitions@@3KA, ecx; ulong SamLockTotalAquisitions
0x180011c11  sub     eax, ebx
0x180011c13  jz      short loc_180011C1F
0x180011c15  test    ecx, ecx
0x180011c17  jz      short loc_180011C1F
0x180011c19  add     cs:?SamCumulativeWaitTime@@3KA, eax; ulong SamCumulativeWaitTime
0x180011c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c26  test    dword ptr [rcx+44h], 20000h
0x180011c2d  jz      short loc_180011C4C
0x180011c2f  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180011c37  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180011c3e  mov     rcx, [rcx+38h]
0x180011c42  mov     edx, 49h ; 'I'
0x180011c47  call    WPP_SF_d
0x180011c4c  cmp     cs:?SampUseDsData@@3EA, r14b; uchar SampUseDsData
0x180011c53  jz      short loc_180011C66
0x180011c55  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x180011c5a  test    eax, eax
0x180011c5c  js      short loc_180011C66
0x180011c5e  xor     ecx, ecx
0x180011c60  call    cs:__imp_NtdsaExtSetGlobalTransactionType
0x180011c66  mov     ecx, 1
0x180011c6b  call    SampSetTransactionDomain
0x180011c70  mov     r8d, [rbp+57h+arg_8]
0x180011c74  lea     rax, [rbp+57h+HandleId]
0x180011c78  mov     [rsp+0E0h+var_78], rax
0x180011c7d  xor     edi, edi
0x180011c7f  mov     [rsp+0E0h+var_80], rdi
0x180011c84  xor     r9d, r9d
0x180011c87  mov     [rsp+0E0h+var_88], dil
0x180011c8c  mov     edx, 4
0x180011c91  mov     [rsp+0E0h+var_90], dil
0x180011c96  xor     ecx, ecx
0x180011c98  mov     [rsp+0E0h+var_98], 1
0x180011c9d  mov     [rsp+0E0h+var_A0], dil
0x180011ca2  mov     [rsp+0E0h+var_A8], dil
0x180011ca7  mov     [rsp+0E0h+var_B0], 1
0x180011cac  mov     [rsp+0E0h+var_B8], 1
0x180011cb4  mov     [rsp+0E0h+var_C0], rdi
0x180011cb9  call    SampCreateAccountContext2
0x180011cbe  mov     esi, eax
0x180011cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cc7  test    dword ptr [rcx+44h], 20000h
0x180011cce  jz      short loc_180011CF3
0x180011cd0  mov     rcx, [rcx+38h]
0x180011cd4  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180011cdb  mov     edx, 7Bh ; '{'
0x180011ce0  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180011ce4  mov     r9d, eax
0x180011ce7  call    WPP_SF_Dd
0x180011cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cf3  mov     rbx, [rbp+57h+HandleId]
0x180011cf7  test    esi, esi
0x180011cf9  jns     short loc_180011D2F
0x180011cfb  test    dword ptr [rcx+44h], 400h
0x180011d02  jz      loc_180011E99
0x180011d08  cmp     byte ptr [rcx+41h], 2
0x180011d0c  jb      loc_180011E99
0x180011d12  mov     edx, 13h
0x180011d17  mov     r9d, esi
0x180011d1a  mov     rcx, [rcx+38h]
0x180011d1e  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x180011d25  call    WPP_SF_d
0x180011d2a  jmp     loc_180011E99
0x180011d2f  mov     r9d, 1
0x180011d35  lea     r8, [rbp+57h+arg_10]
0x180011d39  xor     edx, edx
0x180011d3b  mov     rcx, rbx
0x180011d3e  call    SampReadExtendedAttributes
0x180011d43  mov     esi, eax
0x180011d45  test    eax, eax
0x180011d47  jns     short loc_180011D71
0x180011d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d50  test    dword ptr [rcx+44h], 400h
0x180011d57  jz      loc_180011E99
0x180011d5d  cmp     byte ptr [rcx+41h], 2
0x180011d61  jb      loc_180011E99
0x180011d67  mov     edx, 14h
0x180011d6c  mov     r9d, eax
0x180011d6f  jmp     short loc_180011D1A
0x180011d71  lea     r8, [rbp+57h+var_58]
0x180011d75  mov     edx, 27h ; '''
0x180011d7a  mov     rcx, rbx
0x180011d7d  call    SampGetExtendedAttribute
0x180011d82  mov     esi, eax
0x180011d84  test    eax, eax
0x180011d86  jns     short loc_180011DB3
0x180011d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d8f  test    dword ptr [rcx+44h], 400h
0x180011d96  jz      loc_180011E99
0x180011d9c  cmp     byte ptr [rcx+41h], 2
0x180011da0  jb      loc_180011E99
0x180011da6  mov     edx, 15h
0x180011dab  mov     r9d, eax
0x180011dae  jmp     loc_180011D1A
0x180011db3  cmp     dword ptr [rbp+57h+var_58], edi
0x180011db6  jnz     short loc_180011DBF
0x180011db8  mov     esi, edi
0x180011dba  jmp     loc_180011E99
0x180011dbf  lea     r9, [rbp+57h+var_48]
0x180011dc3  xor     r8d, r8d
0x180011dc6  mov     edx, 1
0x180011dcb  mov     rcx, rbx; struct _SAMP_OBJECT *
0x180011dce  call    SampGetUnicodeStringAttribute
0x180011dd3  mov     esi, eax
0x180011dd5  test    eax, eax
0x180011dd7  jns     short loc_180011E04
0x180011dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180011de0  test    dword ptr [rcx+44h], 400h
0x180011de7  jz      loc_180011E99
0x180011ded  cmp     byte ptr [rcx+41h], 2
0x180011df1  jb      loc_180011E99
0x180011df7  mov     edx, 16h
0x180011dfc  mov     r9d, eax
0x180011dff  jmp     loc_180011D1A
0x180011e04  lea     rdx, [rbp+57h+hMem]; unsigned __int16 **
0x180011e08  lea     rcx, [rbp+57h+var_48]; struct _UNICODE_STRING *
0x180011e0c  call    ?SampCopyUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAPEAG@Z; SampCopyUnicodeString(_UNICODE_STRING *,ushort * *)
0x180011e11  mov     esi, eax
0x180011e13  test    eax, eax
0x180011e15  jns     short loc_180011E3A
0x180011e17  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e1e  test    dword ptr [rcx+44h], 400h
0x180011e25  jz      short loc_180011E99
0x180011e27  cmp     byte ptr [rcx+41h], 2
0x180011e2b  jb      short loc_180011E99
0x180011e2d  mov     edx, 17h
0x180011e32  mov     r9d, eax
0x180011e35  jmp     loc_180011D1A
0x180011e3a  mov     rdx, [rbp+57h+var_58+8]; void *
0x180011e3e  lea     rcx, [rbp+57h+var_70]; void **
0x180011e42  call    ?SampCopySid@@YAJPEAPEAXPEAX@Z; SampCopySid(void * *,void *)
0x180011e47  mov     esi, eax
0x180011e49  test    eax, eax
0x180011e4b  jns     short loc_180011E81
0x180011e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e54  test    dword ptr [rcx+44h], 400h
0x180011e5b  jz      short loc_180011E7B
0x180011e5d  cmp     byte ptr [rcx+41h], 2
0x180011e61  jb      short loc_180011E7B
0x180011e63  mov     rcx, [rcx+38h]
0x180011e67  lea     r8, WPP_93028685eca730797a8a21ecee3f4be1_Traceguids
0x180011e6e  mov     edx, 18h
0x180011e73  mov     r9d, eax
0x180011e76  call    WPP_SF_d
0x180011e7b  mov     r14, [rbp+57h+var_70]
0x180011e7f  jmp     short loc_180011E99
0x180011e81  mov     rax, [rbp+57h+hMem]
0x180011e85  mov     [r12], rax
0x180011e89  mov     rax, [rbp+57h+var_70]
0x180011e8d  mov     [r15], rax
0x180011e90  mov     byte ptr [r13+0], 1
0x180011e95  mov     [rbp+57h+hMem], rdi
0x180011e99  test    rbx, rbx
0x180011e9c  jz      loc_180011F68
0x180011ea2  or      byte ptr [rbx+14h], 10h
0x180011ea6  test    byte ptr [rbx+14h], 20h
0x180011eaa  mov     [rbp+57h+arg_8], edi
0x180011ead  jnz     short loc_180011EBB
0x180011eaf  lea     rcx, [rbp+57h+arg_8]
0x180011eb3  call    SampImpersonateClient
0x180011eb8  mov     edi, [rbp+57h+arg_8]
0x180011ebb  movzx   r8d, byte ptr [rbx+0D0h]; GenerateOnClose
0x180011ec3  lea     rcx, ?SampSamSubsystem@@3U_UNICODE_STRING@@A; SubsystemName
0x180011eca  mov     rdx, rbx; HandleId
0x180011ecd  call    cs:__imp_NtCloseObjectAuditAlarm
0x180011ed3  cmp     edi, 2
0x180011ed6  jz      short loc_180011EFA
0x180011ed8  sub     edi, 1
0x180011edb  jz      short loc_180011EF3
0x180011edd  cmp     edi, 2
0x180011ee0  jnz     short loc_180011F00
0x180011ee2  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x180011ee7  test    eax, eax
0x180011ee9  js      short loc_180011F00
  ... truncated ...
```
