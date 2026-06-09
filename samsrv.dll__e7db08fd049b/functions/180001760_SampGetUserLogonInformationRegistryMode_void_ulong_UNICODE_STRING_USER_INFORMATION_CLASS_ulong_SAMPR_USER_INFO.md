# SampGetUserLogonInformationRegistryMode(void *,ulong,_UNICODE_STRING *,_USER_INFORMATION_CLASS,ulong,_SAMPR_USER_INFO_BUFFER * *,_SID_AND_ATTRIBUTES_LIST *,void * *)

- ea: `0x180001760`
- end: `0x18000228d`
- name: `?SampGetUserLogonInformationRegistryMode@@YAJPEAXKPEAU_UNICODE_STRING@@W4_USER_INFORMATION_CLASS@@KPEAPEAT_SAMPR_USER_INFO_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAPEAX@Z`
- size: `2861`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x1800244d4`

## callees

- `0x180001760`
- `0x1800022a0`
- `0x180002360`
- `0x180002b40`
- `0x180003860`
- `0x180006170`
- `0x1800066f0`
- `0x180008590`
- `0x1800096c0`
- `0x18000b150`
- `0x18000e180`
- `0x180012a28`
- `0x180013ee0`
- `0x1800158c0`
- `0x18001b4e0`
- `0x18001d960`
- `0x180022530`
- `0x180023760`
- `0x1800238e0`
- `0x180024160`
- `0x1800270b4`
- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`
- `0x180059a74`
- `0x1800ac954`
- `0x1800bb794`
- `0x1800bc010`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180001935`
- `ntdll!RtlSubAuthorityCountSid` at `0x180001983`
- `ntdll!RtlSubAuthorityCountSid` at `0x180001935`
- `ntdll!RtlSubAuthorityCountSid` at `0x180001983`
- `ntdll!RtlSubAuthoritySid` at `0x180001991`
- `ntdll!RtlSubAuthoritySid` at `0x180001991`
- `ntdll!RtlEnterCriticalSection` at `0x180001845`
- `ntdll!RtlEnterCriticalSection` at `0x180001845`
- `ntdll!RtlLengthSid` at `0x18000194e`
- `ntdll!RtlLengthSid` at `0x18000194e`
- `ntdll!RtlEqualSid` at `0x1800019f0`
- `ntdll!RtlEqualSid` at `0x1800019f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000195d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001c53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000195d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001c53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002128`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000222a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002239`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002128`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000222a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002239`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000182f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001852`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000182f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001852`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x1800018bb`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtSetGlobalTransactionType` at `0x1800018bb`

## pseudocode

```c
__int64 __fastcall SampGetUserLogonInformationRegistryMode(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        _QWORD *a6,
        unsigned int *a7,
        _QWORD *a8)
{
  _QWORD *v8; // r12
  __int64 v11; // r14
  int *v12; // r15
  void *v13; // r13
  DWORD TickCount; // ebx
  DWORD v15; // eax
  unsigned int v16; // ecx
  DWORD v17; // eax
  unsigned int v18; // eax
  int InformationUserInternal; // ebx
  PUNICODE_STRING v20; // rcx
  void *v21; // rbx
  int v22; // edi
  SIZE_T v23; // rsi
  HLOCAL v24; // rax
  PUCHAR v25; // rax
  PULONG v26; // rax
  ULONG v27; // r8d
  int v28; // eax
  unsigned int AccountContext2; // eax
  char v30; // r12
  char v31; // si
  PUNICODE_STRING v32; // rcx
  unsigned int v33; // ebx
  unsigned int v34; // eax
  unsigned int *v35; // rdi
  HLOCAL v36; // rax
  unsigned int *v37; // rdx
  __int64 v38; // rdi
  int FullSid; // eax
  HLOCAL v40; // rsi
  __int64 v41; // rdi
  __int64 v42; // rdi
  __int64 v43; // r14
  PUNICODE_STRING v44; // r10
  __int64 v45; // rax
  __int64 v46; // rbx
  unsigned int *v47; // r8
  int v48; // esi
  __int64 v49; // rdx
  int *v50; // r14
  int *v51; // rdi
  unsigned int v52; // eax
  unsigned int v53; // eax
  ULONG v55; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v56; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+84h] [rbp-7Ch] BYREF
  PVOID HandleId; // [rsp+88h] [rbp-78h] BYREF
  int v60; // [rsp+90h] [rbp-70h] BYREF
  int v61; // [rsp+94h] [rbp-6Ch] BYREF
  struct _GROUP_MEMBERSHIP *v62; // [rsp+98h] [rbp-68h] BYREF
  __int64 v63; // [rsp+A0h] [rbp-60h]
  __int64 v64; // [rsp+A8h] [rbp-58h]
  HLOCAL hMem[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v66; // [rsp+C0h] [rbp-40h]
  HLOCAL v67[2]; // [rsp+C8h] [rbp-38h] BYREF
  HLOCAL v68[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v69[24]; // [rsp+F0h] [rbp-10h] BYREF

  v8 = a6;
  v66 = a8;
  v11 = a1;
  v56 = a4;
  v60 = 0;
  v12 = 0;
  v58 = 0;
  v13 = 0;
  v55 = 0;
  HandleId = 0;
  v57 = 0;
  v62 = 0;
  v63 = a1;
  v64 = (__int64)a6;
  *(_OWORD *)v67 = 0;
  v61 = 1;
  *(_OWORD *)v68 = 0;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
  if ( !SampUseDsData || !(unsigned int)SampExtIsWriteLockHeldByDs() )
  {
    TickCount = GetTickCount();
    _InterlockedIncrement((volatile signed __int32 *)&SamLockQueueLength);
    RtlEnterCriticalSection(&SampLock);
    _InterlockedDecrement((volatile signed __int32 *)&SamLockQueueLength);
    v15 = GetTickCount();
    v16 = SamLockTotalAquisitions + 1;
    SamLockCurrentHoldStartTime = v15;
    ++SamLockTotalAquisitions;
    v17 = v15 - TickCount;
    if ( v17 && v16 )
      SamCumulativeWaitTime += v17;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    if ( SampUseDsData && (int)SampShouldCallNtdsaApiSet() >= 0 )
      NtdsaExtSetGlobalTransactionType(0);
  }
  *a6 = 0;
  *(_OWORD *)a7 = 0;
  v18 = SampLookupContextEx(v11, 0x20284u, 0, 1, &v60);
  InformationUserInternal = v18;
  v20 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v18, v18);
  if ( InformationUserInternal < 0 )
  {
    v35 = a7;
LABEL_126:
    if ( *((_QWORD *)v35 + 1) )
      SamIFreeSidAndAttributesList(v35);
    *v35 = 0;
    if ( *v8 )
    {
      SamIFree_SAMPR_USER_INFO_BUFFER(*v8, 21);
      *v8 = 0;
    }
    if ( v12 )
      SampDeleteContext(v12);
    goto LABEL_132;
  }
  if ( (a2 & 0x80u) != 0 )
  {
    v21 = *(void **)(a3 + 8);
    v22 = *RtlSubAuthorityCountSid(v21);
    if ( (_BYTE)v22 )
    {
      v23 = RtlLengthSid(v21);
      v24 = LocalAlloc(0x40u, v23);
      v13 = v24;
      if ( v24 )
      {
        memmove_0(v24, v21, v23);
        v25 = RtlSubAuthorityCountSid(v13);
        --*v25;
        v26 = RtlSubAuthoritySid(v21, v22 - 1);
        InformationUserInternal = 0;
        v55 = *v26;
      }
      else
      {
        InformationUserInternal = -1073741670;
      }
    }
    else
    {
      InformationUserInternal = -1073741704;
    }
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        128,
        WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
        (unsigned int)InformationUserInternal,
        InformationUserInternal);
    if ( InformationUserInternal < 0 )
      goto LABEL_117;
    if ( !RtlEqualSid(v13, *((PSID *)SampDefinedDomains + 170 * *(unsigned int *)(v11 + 200) + 1)) )
    {
      InformationUserInternal = -1073741724;
LABEL_117:
      v35 = a7;
      goto LABEL_118;
    }
    goto LABEL_34;
  }
  if ( (a2 & 0x4000) == 0 )
  {
    if ( (a2 & 0x8000) != 0 )
      v28 = SampRegistryLookupIdByKey(v20, a2, a3, &v55, &v58, &v61);
    else
      v28 = SampLookupAccountRid(v11, 4, a3, 3221225572LL, &v55, &v58);
    InformationUserInternal = v28;
    if ( v28 < 0 )
      goto LABEL_117;
LABEL_34:
    v27 = v55;
    goto LABEL_35;
  }
  InformationUserInternal = SampLookupNamesInDomain(
                              (struct _SAMP_OBJECT *)v11,
                              1u,
                              a2,
                              1u,
                              (struct _RPC_UNICODE_STRING *const)a3,
                              (struct _SAMPR_ULONG_ARRAY *)v67,
                              (struct _SAMPR_ULONG_ARRAY *)v68);
  if ( InformationUserInternal < 0 )
    goto LABEL_117;
  v27 = *(_DWORD *)v67[1];
  v55 = *(_DWORD *)v67[1];
LABEL_35:
  AccountContext2 = SampCreateAccountContext2(0, 4, v27, 0, 0, 1, 1, 0, 0, 1, 0, 0, 0, (__int64)&HandleId);
  InformationUserInternal = AccountContext2;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      123,
      WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
      AccountContext2,
      AccountContext2);
  v12 = (int *)HandleId;
  if ( InformationUserInternal < 0 )
    goto LABEL_117;
  *((_BYTE *)HandleId + 28) |= 8u;
  v30 = *((_BYTE *)v12 + 20);
  v31 = 0;
  *(_OWORD *)hMem = 0;
  v32 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    v32 = WPP_GLOBAL_Control;
  }
  if ( SampUseDsData )
  {
    if ( (*(_DWORD *)(&v32[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(v32[3].Buffer, 343, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, 0, 0);
    goto LABEL_43;
  }
  *((_BYTE *)v12 + 20) |= 0x20u;
  LODWORD(v42) = 1;
  v43 = v12[4];
  v44 = WPP_GLOBAL_Control;
  v45 = 2LL * (v12[48] & 2);
  v69[0] = 29;
  v46 = 0;
  HandleId = *(&funcs_180001EF0 + v45);
  while ( (unsigned int)v46 < (unsigned int)v42 )
  {
    v47 = &v69[v46];
    if ( (v12[6 * (*v47 - dword_1800BD00C[4 * v43]) + 216] & 1) != 0 )
    {
      v42 = (unsigned int)(v42 - 1);
      LODWORD(v46) = v46 - 1;
      *v47 = v69[v42];
    }
    else
    {
      v48 = *(_DWORD *)(*((_QWORD *)&SampObjectExtendedAttributesProperties + 2 * v12[4])
                      + 32LL * (v69[v46] - dword_1800BD00C[4 * v43])
                      + 4)
          & (((v12[48] & 2) != 0) + 1);
      if ( (*(_DWORD *)(&v44[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_d(v44[3].Buffer, 40, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v48 != 0);
        v44 = WPP_GLOBAL_Control;
      }
      if ( !v48 )
      {
        InformationUserInternal = -1073741149;
        if ( (*(_DWORD *)(&v44[4].MaximumLength + 1) & 0x20000) == 0 )
          goto LABEL_78;
        WPP_SF_Dd(v44[3].Buffer, 82, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221226147LL, -1073741149);
        goto LABEL_77;
      }
    }
    v46 = (unsigned int)(v46 + 1);
  }
  if ( (*(_DWORD *)(&v44[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(v44[3].Buffer, 83, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 0, 0);
    v44 = WPP_GLOBAL_Control;
  }
  if ( !(_DWORD)v42 )
  {
    InformationUserInternal = 0;
    goto LABEL_78;
  }
  InformationUserInternal = ((__int64 (__fastcall *)(int *, unsigned int *, _QWORD))HandleId)(
                              v12,
                              v69,
                              (unsigned int)v42);
LABEL_77:
  v44 = WPP_GLOBAL_Control;
LABEL_78:
  if ( (*(_BYTE *)(&v44[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v44[4].Length) >= 5u )
  {
    WPP_SF_Dd(v44[3].Buffer, 86, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 1, InformationUserInternal);
    v44 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v44[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(
      v44[3].Buffer,
      87,
      WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
      (unsigned int)InformationUserInternal,
      InformationUserInternal);
    v44 = WPP_GLOBAL_Control;
  }
  v31 = 0;
  if ( InformationUserInternal >= 0 )
  {
    v49 = 4LL * v12[4];
    v50 = (int *)(*(char **)((char *)&SampObjectExtendedAttributesProperties + v49 * 4)
                + 32 * (unsigned int)(29 - dword_1800BD00C[v49]));
    v51 = &v12[6 * (29 - dword_1800BD00C[v49]) + 216];
    if ( (v12[5] & 0x20) != 0 )
    {
      v31 = *(_BYTE *)v51 >> 2;
      *(_BYTE *)v51 |= 4u;
      v44 = WPP_GLOBAL_Control;
    }
    if ( (*(_BYTE *)v51 & 4) != 0 )
    {
      v52 = ((__int64 (__fastcall *)(int *, HLOCAL *))qword_1800BD430[2 * *v50])(v51 + 2, hMem);
      InformationUserInternal = v52;
      v44 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 66, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v52, v52);
        goto LABEL_91;
      }
    }
    else
    {
      InformationUserInternal = -1073741790;
      if ( (*(_DWORD *)(&v44[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_Dd(v44[3].Buffer, 65, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221225506LL, -1073741790);
LABEL_91:
        v44 = WPP_GLOBAL_Control;
      }
    }
    if ( (v12[5] & 0x20) != 0 )
    {
      *(_BYTE *)v51 ^= (*(_BYTE *)v51 ^ (4 * v31)) & 4;
      v44 = WPP_GLOBAL_Control;
    }
    if ( (*(_BYTE *)(&v44[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v44[4].Length) >= 4u )
    {
      WPP_SF_ZD(
        v44[3].Buffer,
        67,
        (unsigned int)WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
        (_DWORD)v50 + 8,
        InformationUserInternal);
      v44 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(&v44[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        v44[3].Buffer,
        68,
        WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
        (unsigned int)InformationUserInternal,
        InformationUserInternal);
    if ( InformationUserInternal >= 0 && hMem[1] )
    {
      v31 = 1;
      LocalFree(hMem[1]);
    }
    else
    {
      v31 = 0;
    }
  }
  *((_BYTE *)v12 + 20) ^= (*((_BYTE *)v12 + 20) ^ v30 & 0xE0) & 0x20;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      344,
      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
      (unsigned int)InformationUserInternal,
      InformationUserInternal);
  v11 = v63;
  if ( InformationUserInternal < 0 )
  {
    v8 = (_QWORD *)v64;
    goto LABEL_117;
  }
  if ( v31 )
  {
    v33 = a5 | 0x100000;
    goto LABEL_44;
  }
LABEL_43:
  v33 = a5;
LABEL_44:
  SampSetTransactionWithinDomain(0);
  v8 = (_QWORD *)v64;
  InformationUserInternal = SampQueryInformationUserInternal((struct _SAMP_OBJECT *)v12, v33, v64);
  if ( InformationUserInternal < 0 )
    goto LABEL_117;
  InformationUserInternal = SampUpdateAccountDisabledFlag((struct _SAMP_OBJECT *)v12);
  if ( InformationUserInternal < 0 )
    goto LABEL_117;
  InformationUserInternal = SampRetrieveUserMembership((struct _SAMP_OBJECT *)v12, 0, &v57, &v56, &v62);
  if ( InformationUserInternal < 0 )
    goto LABEL_117;
  v34 = v57;
  if ( !v57 )
    goto LABEL_117;
  if ( v31 )
    v34 = ++v57;
  v35 = a7;
  *a7 = v34;
  v36 = LocalAlloc(0x40u, 16LL * v34);
  *((_QWORD *)a7 + 1) = v36;
  if ( !v36 )
  {
    InformationUserInternal = -1073741670;
    goto LABEL_118;
  }
  memset_0(v36, 0, 16LL * *a7);
  if ( v31 )
    --*a7;
  v37 = a7;
  v38 = 0;
  if ( *a7 )
  {
    while ( InformationUserInternal >= 0 )
    {
      *(_DWORD *)(16LL * (unsigned int)v38 + *((_QWORD *)v37 + 1) + 8) = *((_DWORD *)v62 + 2 * v38 + 1);
      FullSid = SampCreateFullSid(*((PSID *)SampDefinedDomains + 170 * SampTransactionDomainIndexGlobal + 1));
      v37 = a7;
      v38 = (unsigned int)(v38 + 1);
      InformationUserInternal = FullSid;
      if ( (unsigned int)v38 >= *a7 )
      {
        if ( FullSid >= 0 )
          goto LABEL_57;
        v35 = a7;
        goto LABEL_112;
      }
    }
    goto LABEL_111;
  }
LABEL_57:
  if ( !v31
    || (v56 = 29,
        *(_OWORD *)hMem = 0,
        InformationUserInternal = SampReadExtendedAttributes((struct _SAMP_OBJECT *)v12, 0, &v56, 1u),
        InformationUserInternal < 0)
    || (InformationUserInternal = SampGetExtendedAttribute((__int64)v12, 29, (__int64)hMem), InformationUserInternal < 0) )
  {
LABEL_111:
    v35 = a7;
    goto LABEL_112;
  }
  v40 = hMem[1];
  v41 = 16 * v38;
  InformationUserInternal = SampCopySid((void **)(v41 + *((_QWORD *)a7 + 1)), hMem[1]);
  if ( InformationUserInternal < 0 )
  {
    v35 = a7;
  }
  else
  {
    *(_DWORD *)(v41 + *((_QWORD *)a7 + 1) + 8) = 4;
    v35 = a7;
    ++*a7;
  }
  LocalFree(v40);
LABEL_112:
  if ( v66 && InformationUserInternal >= 0 )
    *v66 = v12;
LABEL_118:
  if ( (*(_BYTE *)(v11 + 192) & 2) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v11 + 144));
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 33, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, 0, 0);
  }
  else
  {
    v53 = SampDeReferenceContext(v11, 0);
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 32, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v53, v53);
  }
  if ( InformationUserInternal < 0 )
    goto LABEL_126;
LABEL_132:
  if ( v13 )
    LocalFree(v13);
  SampReleaseReadLock();
  if ( v67[1] )
    LocalFree(v67[1]);
  if ( v68[1] )
    LocalFree(v68[1]);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      14,
      WPP_88ec5fb48460398ff276a1700e0df4bf_Traceguids,
      (unsigned int)InformationUserInternal,
      InformationUserInternal);
  return (unsigned int)InformationUserInternal;
}

```

## disassembly

```asm
0x180001760  push    rbp
0x180001762  push    rbx
0x180001763  push    rsi
0x180001764  push    rdi
0x180001765  push    r12
0x180001767  push    r13
0x180001769  push    r14
0x18000176b  push    r15
0x18000176d  lea     rbp, [rsp-68h]
0x180001772  sub     rsp, 168h
0x180001779  mov     rax, cs:__security_cookie
0x180001780  xor     rax, rsp
0x180001783  mov     [rbp+0A0h+var_50], rax
0x180001787  mov     rax, [rbp+0A0h+arg_30]
0x18000178e  xorps   xmm0, xmm0
0x180001791  mov     r12, [rbp+0A0h+arg_28]
0x180001798  xorps   xmm1, xmm1
0x18000179b  mov     [rsp+1A0h+var_130], rax
0x1800017a0  mov     rsi, r8
0x1800017a3  mov     rax, [rbp+0A0h+arg_38]
0x1800017aa  mov     edi, edx
0x1800017ac  mov     [rbp+0A0h+var_E0], rax
0x1800017b0  mov     r14, rcx
0x1800017b3  xor     eax, eax
0x1800017b5  mov     [rsp+1A0h+var_124], r9d
0x1800017ba  mov     [rbp+0A0h+var_110], eax
0x1800017bd  mov     r15d, eax
0x1800017c0  mov     [rbp+0A0h+var_11C], eax
0x1800017c3  mov     r13d, eax
0x1800017c6  mov     [rsp+1A0h+var_128], eax
0x1800017ca  mov     [rbp+0A0h+HandleId], rax
0x1800017ce  mov     [rbp+0A0h+var_120], eax
0x1800017d1  mov     [rbp+0A0h+var_108], rax
0x1800017d5  mov     [rbp+0A0h+var_100], rcx
0x1800017d9  mov     [rbp+0A0h+var_F8], r12
0x1800017dd  movups  xmmword ptr [rbp+0A0h+var_D8], xmm0
0x1800017e1  mov     [rbp+0A0h+var_10C], 1
0x1800017e8  movups  xmmword ptr [rbp+0A0h+var_C8], xmm1
0x1800017ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017f3  test    dword ptr [rcx+44h], 20000h
0x1800017fa  jz      short loc_180001819
0x1800017fc  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180001804  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18000180b  mov     rcx, [rcx+38h]
0x18000180f  mov     edx, 49h ; 'I'
0x180001814  call    WPP_SF_d
0x180001819  cmp     cs:?SampUseDsData@@3EA, r13b; uchar SampUseDsData
0x180001820  jz      short loc_18000182F
0x180001822  call    ?SampExtIsWriteLockHeldByDs@@YAHXZ; SampExtIsWriteLockHeldByDs(void)
0x180001827  test    eax, eax
0x180001829  jnz     loc_1800018C1
0x18000182f  call    cs:__imp_GetTickCount
0x180001835  mov     ebx, eax
0x180001837  lock inc cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x18000183e  lea     rcx, ?SampLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180001845  call    cs:__imp_RtlEnterCriticalSection
0x18000184b  lock dec cs:?SamLockQueueLength@@3KA; ulong SamLockQueueLength
0x180001852  call    cs:__imp_GetTickCount
0x180001858  mov     ecx, cs:?SamLockTotalAquisitions@@3KA; ulong SamLockTotalAquisitions
0x18000185e  inc     ecx
0x180001860  mov     cs:?SamLockCurrentHoldStartTime@@3KA, eax; ulong SamLockCurrentHoldStartTime
0x180001866  mov     cs:?SamLockTotalAquisitions@@3KA, ecx; ulong SamLockTotalAquisitions
0x18000186c  sub     eax, ebx
0x18000186e  jz      short loc_18000187A
0x180001870  test    ecx, ecx
0x180001872  jz      short loc_18000187A
0x180001874  add     cs:?SamCumulativeWaitTime@@3KA, eax; ulong SamCumulativeWaitTime
0x18000187a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001881  test    dword ptr [rcx+44h], 20000h
0x180001888  jz      short loc_1800018A7
0x18000188a  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180001892  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180001899  mov     rcx, [rcx+38h]
0x18000189d  mov     edx, 49h ; 'I'
0x1800018a2  call    WPP_SF_d
0x1800018a7  cmp     cs:?SampUseDsData@@3EA, r13b; uchar SampUseDsData
0x1800018ae  jz      short loc_1800018C1
0x1800018b0  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x1800018b5  test    eax, eax
0x1800018b7  js      short loc_1800018C1
0x1800018b9  xor     ecx, ecx
0x1800018bb  call    cs:__imp_NtdsaExtSetGlobalTransactionType
0x1800018c1  mov     rax, [rsp+1A0h+var_130]
0x1800018c6  xorps   xmm0, xmm0
0x1800018c9  mov     [r12], r13
0x1800018cd  mov     r9d, 1
0x1800018d3  xor     r8d, r8d
0x1800018d6  mov     edx, 20284h
0x1800018db  mov     rcx, r14
0x1800018de  movups  xmmword ptr [rax], xmm0
0x1800018e1  lea     rax, [rbp+0A0h+var_110]
0x1800018e5  mov     [rsp+1A0h+var_180], rax
0x1800018ea  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x1800018ef  mov     ebx, eax
0x1800018f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018f8  test    dword ptr [rcx+44h], 20000h
0x1800018ff  jz      short loc_18000191D
0x180001901  mov     rcx, [rcx+38h]
0x180001905  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18000190c  mov     edx, 10h
0x180001911  mov     dword ptr [rsp+1A0h+var_180], eax
0x180001915  mov     r9d, eax
0x180001918  call    WPP_SF_Dd
0x18000191d  test    ebx, ebx
0x18000191f  js      loc_1800021CC
0x180001925  test    dil, dil
0x180001928  jns     loc_180001A08
0x18000192e  mov     rbx, [rsi+8]
0x180001932  mov     rcx, rbx; Sid
0x180001935  call    cs:__imp_RtlSubAuthorityCountSid
0x18000193b  movzx   edi, byte ptr [rax]
0x18000193e  cmp     dil, 1
0x180001942  jnb     short loc_18000194B
0x180001944  mov     ebx, 0C0000078h
0x180001949  jmp     short loc_18000199F
0x18000194b  mov     rcx, rbx; Sid
0x18000194e  call    cs:__imp_RtlLengthSid
0x180001954  mov     edx, eax; uBytes
0x180001956  mov     ecx, 40h ; '@'; uFlags
0x18000195b  mov     esi, eax
0x18000195d  call    cs:__imp_LocalAlloc
0x180001963  mov     r13, rax
0x180001966  test    rax, rax
0x180001969  jnz     short loc_180001972
0x18000196b  mov     ebx, 0C000009Ah
0x180001970  jmp     short loc_18000199F
0x180001972  mov     r8, rsi; Size
0x180001975  mov     rdx, rbx; Src
0x180001978  mov     rcx, r13; void *
0x18000197b  call    memmove_0
0x180001980  mov     rcx, r13; Sid
0x180001983  call    cs:__imp_RtlSubAuthorityCountSid
0x180001989  lea     edx, [rdi-1]; SubAuthority
0x18000198c  mov     rcx, rbx; Sid
0x18000198f  dec     byte ptr [rax]
0x180001991  call    cs:__imp_RtlSubAuthoritySid
0x180001997  xor     ebx, ebx
0x180001999  mov     ecx, [rax]
0x18000199b  mov     [rsp+1A0h+var_128], ecx
0x18000199f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019a6  test    dword ptr [rcx+44h], 20000h
0x1800019ad  jz      short loc_1800019CB
0x1800019af  mov     rcx, [rcx+38h]
0x1800019b3  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800019ba  mov     edx, 80h
0x1800019bf  mov     dword ptr [rsp+1A0h+var_180], ebx
0x1800019c3  mov     r9d, ebx
0x1800019c6  call    WPP_SF_Dd
0x1800019cb  test    ebx, ebx
0x1800019cd  js      loc_180002157
0x1800019d3  mov     eax, [r14+0C8h]
0x1800019da  mov     rdx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x1800019e1  imul    rcx, rax, 550h
0x1800019e8  mov     rdx, [rcx+rdx+8]; Sid2
0x1800019ed  mov     rcx, r13; Sid1
0x1800019f0  call    cs:__imp_RtlEqualSid
0x1800019f6  test    al, al
0x1800019f8  jnz     loc_180001AAB
0x1800019fe  mov     ebx, 0C0000064h
0x180001a03  jmp     loc_180002157
0x180001a08  bt      edi, 0Eh
0x180001a0c  jnb     short loc_180001A52
0x180001a0e  lea     rax, [rbp+0A0h+var_C8]
0x180001a12  mov     r9d, 1; unsigned int
0x180001a18  mov     [rsp+1A0h+var_170], rax; struct _SAMPR_ULONG_ARRAY *
0x180001a1d  mov     r8d, edi; unsigned int
0x180001a20  lea     rax, [rbp+0A0h+var_D8]
0x180001a24  movzx   edx, r9b; unsigned __int8
0x180001a28  mov     [rsp+1A0h+var_178], rax; struct _SAMPR_ULONG_ARRAY *
0x180001a2d  mov     rcx, r14; struct _SAMP_OBJECT *
0x180001a30  mov     [rsp+1A0h+var_180], rsi; struct _RPC_UNICODE_STRING *
0x180001a35  call    ?SampLookupNamesInDomain@@YAJPEAU_SAMP_OBJECT@@EKKQEAU_RPC_UNICODE_STRING@@PEAU_SAMPR_ULONG_ARRAY@@2@Z; SampLookupNamesInDomain(_SAMP_OBJECT *,uchar,ulong,ulong,_RPC_UNICODE_STRING * const,_SAMPR_ULONG_ARRAY *,_SAMPR_ULONG_ARRAY *)
0x180001a3a  mov     ebx, eax
0x180001a3c  test    eax, eax
0x180001a3e  js      loc_180002157
0x180001a44  mov     rax, [rbp+0A0h+var_D8+8]
0x180001a48  mov     r8d, [rax]
0x180001a4b  mov     [rsp+1A0h+var_128], r8d
0x180001a50  jmp     short loc_180001AB0
0x180001a52  mov     r8, rsi
0x180001a55  bt      edi, 0Fh
0x180001a59  jnb     short loc_180001A7B
0x180001a5b  lea     rax, [rbp+0A0h+var_10C]
0x180001a5f  mov     edx, edi
0x180001a61  mov     [rsp+1A0h+var_178], rax
0x180001a66  lea     r9, [rsp+1A0h+var_128]
0x180001a6b  lea     rax, [rbp+0A0h+var_11C]
0x180001a6f  mov     [rsp+1A0h+var_180], rax
0x180001a74  call    SampRegistryLookupIdByKey
0x180001a79  jmp     short loc_180001AA1
0x180001a7b  lea     rax, [rbp+0A0h+var_11C]
0x180001a7f  mov     r9d, 0C0000064h
0x180001a85  mov     [rsp+1A0h+var_178], rax
0x180001a8a  mov     edx, 4
0x180001a8f  lea     rax, [rsp+1A0h+var_128]
0x180001a94  mov     rcx, r14
0x180001a97  mov     [rsp+1A0h+var_180], rax
0x180001a9c  call    ?SampLookupAccountRid@@YAJPEAU_SAMP_OBJECT@@W4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@JPEAKPEAW4_SID_NAME_USE@@@Z; SampLookupAccountRid(_SAMP_OBJECT *,_SAMP_OBJECT_TYPE,_UNICODE_STRING *,long,ulong *,_SID_NAME_USE *)
0x180001aa1  mov     ebx, eax
0x180001aa3  test    eax, eax
0x180001aa5  js      loc_180002157
0x180001aab  mov     r8d, [rsp+1A0h+var_128]
0x180001ab0  lea     rax, [rbp+0A0h+HandleId]
0x180001ab4  xor     r9d, r9d
0x180001ab7  mov     [rsp+1A0h+var_138], rax
0x180001abc  mov     edx, 4
0x180001ac1  mov     [rsp+1A0h+var_140], r15
0x180001ac6  xor     ecx, ecx
0x180001ac8  mov     [rsp+1A0h+var_148], r15b
0x180001acd  mov     [rsp+1A0h+var_150], r15b
0x180001ad2  mov     [rsp+1A0h+var_158], 1
0x180001ad7  mov     [rsp+1A0h+var_160], r15b
0x180001adc  mov     [rsp+1A0h+var_168], r15b
0x180001ae1  mov     byte ptr [rsp+1A0h+var_170], 1
0x180001ae6  mov     dword ptr [rsp+1A0h+var_178], 1
0x180001aee  mov     [rsp+1A0h+var_180], r15
0x180001af3  call    SampCreateAccountContext2
0x180001af8  mov     ebx, eax
0x180001afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b01  test    dword ptr [rcx+44h], 20000h
0x180001b08  jz      short loc_180001B26
0x180001b0a  mov     rcx, [rcx+38h]
0x180001b0e  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180001b15  mov     edx, 7Bh ; '{'
0x180001b1a  mov     dword ptr [rsp+1A0h+var_180], eax
0x180001b1e  mov     r9d, eax
0x180001b21  call    WPP_SF_Dd
0x180001b26  mov     r15, [rbp+0A0h+HandleId]
0x180001b2a  test    ebx, ebx
0x180001b2c  js      loc_180002157
0x180001b32  or      byte ptr [r15+1Ch], 8
0x180001b37  xorps   xmm0, xmm0
0x180001b3a  movzx   r12d, byte ptr [r15+14h]
0x180001b3f  xor     sil, sil
0x180001b42  movups  xmmword ptr [rbp+0A0h+hMem], xmm0
0x180001b46  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b4d  test    dword ptr [rcx+44h], 20000h
0x180001b54  jz      short loc_180001B7A
0x180001b56  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180001b5e  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180001b65  mov     rcx, [rcx+38h]
0x180001b69  mov     edx, 49h ; 'I'
0x180001b6e  call    WPP_SF_d
0x180001b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b7a  cmp     cs:?SampUseDsData@@3EA, sil; uchar SampUseDsData
0x180001b81  jz      loc_180001D89
0x180001b87  test    dword ptr [rcx+44h], 20000h
0x180001b8e  jz      short loc_180001BB0
0x180001b90  mov     rcx, [rcx+38h]
0x180001b94  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x180001b9b  mov     edx, 157h
0x180001ba0  mov     dword ptr [rsp+1A0h+var_180], 0
0x180001ba8  xor     r9d, r9d
0x180001bab  call    WPP_SF_Dd
0x180001bb0  mov     ebx, [rbp+0A0h+arg_20]
0x180001bb6  xor     ecx, ecx
0x180001bb8  call    SampSetTransactionWithinDomain
0x180001bbd  mov     r12, [rbp+0A0h+var_F8]
0x180001bc1  mov     r9d, 1FFFFFFFh
0x180001bc7  mov     edx, [rsp+1A0h+var_124]
0x180001bcb  mov     r8b, 1
0x180001bce  mov     [rsp+1A0h+var_178], r12; __int64
0x180001bd3  mov     rcx, r15; struct _SAMP_OBJECT *
0x180001bd6  mov     dword ptr [rsp+1A0h+var_180], ebx; unsigned int
0x180001bda  call    SampQueryInformationUserInternal
0x180001bdf  mov     ebx, eax
0x180001be1  test    eax, eax
0x180001be3  js      loc_180002157
0x180001be9  mov     rdx, [r12]
0x180001bed  mov     rcx, r15
0x180001bf0  add     rdx, 118h
0x180001bf7  call    SampUpdateAccountDisabledFlag
0x180001bfc  mov     ebx, eax
0x180001bfe  test    eax, eax
0x180001c00  js      loc_180002157
0x180001c06  lea     rax, [rbp+0A0h+var_108]
0x180001c0a  xor     edx, edx; unsigned __int8
0x180001c0c  lea     r9, [rsp+1A0h+var_124]; unsigned int *
0x180001c11  mov     [rsp+1A0h+var_180], rax; struct _GROUP_MEMBERSHIP **
0x180001c16  lea     r8, [rbp+0A0h+var_120]; unsigned int *
0x180001c1a  mov     rcx, r15; struct _SAMP_OBJECT *
0x180001c1d  call    ?SampRetrieveUserMembership@@YAJPEAU_SAMP_OBJECT@@EPEAK1PEAPEAU_GROUP_MEMBERSHIP@@@Z; SampRetrieveUserMembership(_SAMP_OBJECT *,uchar,ulong *,ulong *,_GROUP_MEMBERSHIP * *)
0x180001c22  mov     ebx, eax
0x180001c24  test    eax, eax
0x180001c26  js      loc_180002157
0x180001c2c  mov     eax, [rbp+0A0h+var_120]
0x180001c2f  test    eax, eax
0x180001c31  jz      loc_180002157
0x180001c37  test    sil, sil
0x180001c3a  jz      short loc_180001C41
0x180001c3c  inc     eax
0x180001c3e  mov     [rbp+0A0h+var_120], eax
0x180001c41  mov     rdi, [rsp+1A0h+var_130]
0x180001c46  mov     ecx, 40h ; '@'; uFlags
0x180001c4b  mov     edx, eax
0x180001c4d  mov     [rdi], edx
0x180001c4f  shl     rdx, 4; uBytes
0x180001c53  call    cs:__imp_LocalAlloc
0x180001c59  mov     [rdi+8], rax
0x180001c5d  test    rax, rax
  ... truncated ...
```
