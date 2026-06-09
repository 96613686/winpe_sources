# SampEnumerateAccountNamesRegistry(_SAMP_OBJECT_TYPE,ulong *,ulong,_SAMPR_ENUMERATION_BUFFER * *,ulong,ulong,ulong *,uchar)

- ea: `0x180003d40`
- end: `0x180004996`
- name: `?SampEnumerateAccountNamesRegistry@@YAJW4_SAMP_OBJECT_TYPE@@PEAKKPEAPEAU_SAMPR_ENUMERATION_BUFFER@@KK1E@Z`
- size: `3158`
- prototype: ``
- caller_count: `5`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800031c0`
- `0x180003a40`
- `0x18001dc50`
- `0x180020f98`
- `0x180028bec`

## callees

- `0x180002360`
- `0x180002960`
- `0x180003d40`
- `0x1800049a0`
- `0x180004fa0`
- `0x180006170`
- `0x180008590`
- `0x18000e180`
- `0x180012a28`
- `0x18001b4e0`
- `0x18001cfa0`
- `0x1800213d0`
- `0x180024ee8`
- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`
- `0x180059a74`
- `0x18008ecd0`
- `0x1800bb77c`
- `0x1800bc010`

## import_xrefs

- `ntdll!RtlpNtEnumerateSubKey` at `0x180003f94`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180004015`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180003f94`
- `ntdll!RtlpNtEnumerateSubKey` at `0x180004015`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18000466d`
- `ntdll!NtCloseObjectAuditAlarm` at `0x18000466d`
- `ntdll!RtlLeaveCriticalSection` at `0x180004700`
- `ntdll!RtlLeaveCriticalSection` at `0x180004700`
- `ntdll!RtlEnterCriticalSection` at `0x1800046c6`
- `ntdll!RtlEnterCriticalSection` at `0x1800046c6`
- `ntdll!NtClose` at `0x180004820`
- `ntdll!NtClose` at `0x180004820`
- `ntdll!RtlpNtOpenKey` at `0x180003f01`
- `ntdll!RtlpNtOpenKey` at `0x180003f01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003f6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003fee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000402f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004867`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004898`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003f6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003fee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000402f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004867`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004898`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003fac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004834`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800048b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800048f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004919`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004922`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003fac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800047a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004834`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800048b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800048f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004919`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004922`
- `api-ms-win-security-lsalookup-l1-1-1!EnumerateIdentityProviders` at `0x180003e42`
- `api-ms-win-security-lsalookup-l1-1-1!EnumerateIdentityProviders` at `0x180003e42`
- `api-ms-win-security-lsalookup-l1-1-1!ReleaseIdentityProviderEnumContext` at `0x180003e53`
- `api-ms-win-security-lsalookup-l1-1-1!ReleaseIdentityProviderEnumContext` at `0x180003e53`
- `RPCRT4!RpcRevertToSelf` at `0x18000469a`
- `RPCRT4!RpcRevertToSelf` at `0x18000469a`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18000468b`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18000468b`

## pseudocode

```c
__int64 __fastcall SampEnumerateAccountNamesRegistry(
        unsigned int a1,
        ULONG *a2,
        int a3,
        HLOCAL *a4,
        unsigned int a5,
        int a6,
        _DWORD *a7,
        char a8)
{
  _DWORD *v8; // rdi
  int v9; // r15d
  ULONG *v10; // rsi
  unsigned int v11; // r12d
  HLOCAL *v12; // r13
  int FixedAttributes; // ebx
  char v14; // bl
  unsigned int *v15; // r14
  int v16; // edi
  int v17; // r13d
  bool v18; // di
  int v19; // ebx
  unsigned int v20; // ecx
  unsigned int v21; // eax
  WCHAR *v22; // rax
  NTSTATUS v23; // edi
  unsigned int v24; // edx
  SIZE_T Length; // rdx
  WCHAR *v26; // rax
  unsigned int *v27; // rax
  unsigned int *v28; // rsi
  char v29; // r13
  unsigned int AccountContext2; // eax
  PUNICODE_STRING v31; // r10
  int *v32; // r12
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int64 v37; // rsi
  __int64 v38; // rax
  bool v39; // zf
  int v40; // eax
  __int64 v41; // r15
  __int64 v42; // rbx
  unsigned int *v43; // r8
  int v44; // edi
  int v45; // eax
  __int64 v46; // rdx
  char v47; // si
  int *v48; // r14
  int *v49; // rdi
  unsigned int v50; // eax
  BOOL v51; // ecx
  int v52; // edi
  int v53; // edi
  char v54; // al
  int **v55; // rdx
  PVOID *v56; // rax
  PUNICODE_STRING v57; // rcx
  _DWORD *v58; // rax
  _QWORD *v59; // rsi
  __int64 v60; // rdi
  unsigned int *v61; // rcx
  __int64 v62; // rdx
  void *v63; // rcx
  unsigned int *v64; // rdi
  bool v66; // [rsp+71h] [rbp-8Fh]
  unsigned int *v67; // [rsp+78h] [rbp-88h] BYREF
  int v68; // [rsp+80h] [rbp-80h]
  _OWORD *v69; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v70; // [rsp+90h] [rbp-70h]
  int v71; // [rsp+98h] [rbp-68h]
  int v72; // [rsp+9Ch] [rbp-64h]
  struct _UNICODE_STRING SubKeyName; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v74; // [rsp+B0h] [rbp-50h]
  unsigned int i; // [rsp+B4h] [rbp-4Ch]
  HANDLE KeyHandle; // [rsp+B8h] [rbp-48h] BYREF
  ULONG *v77; // [rsp+C0h] [rbp-40h]
  _DWORD *v78; // [rsp+C8h] [rbp-38h]
  PVOID HandleId; // [rsp+D0h] [rbp-30h] BYREF
  ULONG Unused[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v81; // [rsp+E0h] [rbp-20h]
  HLOCAL *v82; // [rsp+E8h] [rbp-18h]
  HLOCAL hMem[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 Buf2; // [rsp+100h] [rbp+0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v86[3]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v87; // [rsp+170h] [rbp+70h]
  __int128 v88; // [rsp+180h] [rbp+80h]
  __int128 v89; // [rsp+190h] [rbp+90h] BYREF
  __int128 Buf1; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v91[24]; // [rsp+1B0h] [rbp+B0h] BYREF

  v8 = a7;
  v9 = a3;
  v68 = a3;
  v10 = a2;
  v77 = a2;
  v11 = a1;
  v74 = a1;
  v78 = a7;
  v82 = a4;
  v12 = a4;
  memset_0(v86, 0, 0x50u);
  KeyHandle = 0;
  HandleId = 0;
  *(_QWORD *)Unused = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_OWORD *)hMem = 0;
  if ( SampProductType == NtProductLanManNt && (v9 & 4) != 0 )
  {
    FixedAttributes = -1073741811;
    goto LABEL_173;
  }
  v14 = 0;
  v67 = 0;
  v15 = 0;
  v89 = 0;
  if ( SampProductType != NtProductLanManNt )
    goto LABEL_179;
  v16 = dword_1800EF468;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 88, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, 0, 0);
  if ( v16 )
  {
LABEL_179:
    if ( !(unsigned int)EnumerateIdentityProviders(&v67, 1, &v89) )
      v14 = 1;
  }
  ReleaseIdentityProviderEnumContext(v67);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 208, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0, 0);
  if ( v14 && !v9 )
  {
    v9 = 3;
    if ( gfShowShadowAdminAccounts )
      v9 = 7;
    v68 = v9;
  }
  FixedAttributes = SampBuildAccountKeyName(v11, hMem, 0);
  if ( FixedAttributes < 0 )
  {
LABEL_167:
    v8 = v78;
    goto LABEL_168;
  }
  ObjectAttributes.RootDirectory = SampKey;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)hMem;
  ObjectAttributes.Attributes = 64;
  v17 = 0;
  v18 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FixedAttributes = RtlpNtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0);
  if ( FixedAttributes < 0 )
    goto LABEL_154;
  v19 = 0;
  v81 = 0;
  v20 = -1;
  v66 = 1;
  if ( !a8 )
    v20 = 0x1000000;
  v72 = 0;
  for ( i = v20; ; v20 = i )
  {
    v70 = v15;
    v71 = v17;
    v21 = v19 + 48;
    SubKeyName = 0;
    if ( v19 && v21 >= a5 || v21 > v20 )
    {
LABEL_152:
      FixedAttributes = 0;
      goto LABEL_153;
    }
    SubKeyName.MaximumLength = 32;
    v22 = (WCHAR *)LocalAlloc(0x40u, 0x20u);
    SubKeyName.Buffer = v22;
    if ( !v22 )
    {
      v57 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        goto LABEL_151;
      goto LABEL_150;
    }
    *v22 = 0;
    v23 = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, *v10, (ULONG)Unused);
    if ( v23 == -2147483643 )
    {
      if ( SubKeyName.Buffer )
      {
        LocalFree(SubKeyName.Buffer);
        SubKeyName.Buffer = 0;
      }
      v24 = v19 + SubKeyName.Length + 16;
      if ( v19 && v24 >= a5 || v24 > i )
        goto LABEL_152;
      SubKeyName.MaximumLength = SubKeyName.Length;
      Length = SubKeyName.Length;
      SubKeyName.Length = 0;
      v26 = (WCHAR *)LocalAlloc(0x40u, Length);
      SubKeyName.Buffer = v26;
      if ( !v26 )
      {
        v57 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        {
LABEL_151:
          FixedAttributes = -1073741670;
          goto LABEL_153;
        }
LABEL_150:
        WPP_SF_Dd(v57[3].Buffer, 59, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 3221225626LL, -1073741670);
        goto LABEL_151;
      }
      *v26 = 0;
      v23 = RtlpNtEnumerateSubKey(KeyHandle, &SubKeyName, *v10, (ULONG)Unused);
    }
    if ( v23 < 0 )
      break;
    v27 = (unsigned int *)LocalAlloc(0x40u, 0x20u);
    v67 = v27;
    v28 = v27;
    if ( !v27 )
    {
      FixedAttributes = -1073741670;
      goto LABEL_145;
    }
    *((struct _UNICODE_STRING *)v27 + 1) = SubKeyName;
    FixedAttributes = SampLookupAccountRidRegistry(v11, (__int64)(v27 + 4), -1073741596, v27 + 2, &v69);
    if ( FixedAttributes < 0 )
    {
      LocalFree(v28);
LABEL_145:
      SampFreeUnicodeString(&SubKeyName);
      v10 = v77;
      goto LABEL_153;
    }
    v29 = 1;
    if ( v11 == 4 && (a6 || v9) )
    {
      AccountContext2 = SampCreateAccountContext2(0, 4u, v28[2], 0, 0, 1, 1u, 0, 0, 1, 0, 0, 0, (__int64 *)&HandleId);
      FixedAttributes = AccountContext2;
      v31 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[3].Buffer,
          123,
          WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
          AccountContext2,
          AccountContext2);
        v31 = WPP_GLOBAL_Control;
      }
      v32 = (int *)HandleId;
      if ( FixedAttributes < 0 )
        goto LABEL_108;
      if ( a6 )
      {
        v69 = 0;
        FixedAttributes = SampGetFixedAttributes(HandleId, 0, &v69);
        if ( FixedAttributes >= 0 )
        {
          v33 = v69[1];
          v86[0] = *v69;
          v34 = v69[2];
          v86[1] = v33;
          v35 = v69[3];
          v86[2] = v34;
          v36 = v69[4];
          v87 = v35;
          v88 = v36;
        }
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            211,
            WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
            (unsigned int)FixedAttributes,
            FixedAttributes);
        if ( FixedAttributes < 0 )
          goto LABEL_108;
        FixedAttributes = SampUpdateAccountDisabledFlag((struct _SAMP_OBJECT *)v32);
        if ( FixedAttributes < 0 )
          goto LABEL_108;
        if ( (a6 & DWORD2(v87)) == 0 )
        {
          v29 = 0;
          goto LABEL_108;
        }
        v31 = WPP_GLOBAL_Control;
      }
      if ( !v9 )
        goto LABEL_108;
      v91[0] = 27;
      Buf1 = 0;
      v91[1] = 39;
      LODWORD(v37) = 2;
      v89 = 0;
      v38 = v32[48] & 2;
      LODWORD(v69) = 2;
      v39 = (v32[5] & 0x20) == 0;
      *(_QWORD *)&Buf2 = *(&funcs_180001EF0 + 2 * v38);
      if ( v39 )
      {
        v40 = SampCheckExtendedAttributesForReadAccess((__int64)(v32 + 216), v32[4], 0, (__int64)v91, &v69);
        v31 = WPP_GLOBAL_Control;
        FixedAttributes = v40;
        if ( v40 >= 0 )
        {
          LODWORD(v37) = (_DWORD)v69;
          goto LABEL_57;
        }
      }
      else
      {
LABEL_57:
        v41 = v32[4];
        v42 = 0;
        while ( (unsigned int)v42 < (unsigned int)v37 )
        {
          v43 = &v91[v42];
          if ( (v32[6 * (*v43 - dword_1800BD00C[4 * v41]) + 216] & 1) != 0 )
          {
            v37 = (unsigned int)(v37 - 1);
            v42 = (unsigned int)v42;
            *v43 = v91[v37];
          }
          else
          {
            v44 = *(_DWORD *)(*((_QWORD *)&SampObjectExtendedAttributesProperties + 2 * v32[4])
                            + 32LL * (v91[v42] - dword_1800BD00C[4 * v41])
                            + 4)
                & (((v32[48] & 2) != 0) + 1);
            if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x20000) != 0 )
            {
              WPP_SF_d(v31[3].Buffer, 40, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v44 != 0);
              v31 = WPP_GLOBAL_Control;
            }
            if ( !v44 )
            {
              if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x20000) != 0 )
              {
                WPP_SF_Dd(v31[3].Buffer, 82, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221226147LL, -1073741149);
                v31 = WPP_GLOBAL_Control;
              }
              FixedAttributes = -1073741149;
              goto LABEL_73;
            }
            v42 = (unsigned int)(v42 + 1);
          }
        }
        if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          WPP_SF_Dd(v31[3].Buffer, 83, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 0, 0);
          v31 = WPP_GLOBAL_Control;
        }
        if ( (_DWORD)v37 )
        {
          v45 = ((__int64 (__fastcall *)(int *, unsigned int *, _QWORD))Buf2)(v32, v91, (unsigned int)v37);
          v31 = WPP_GLOBAL_Control;
          FixedAttributes = v45;
        }
        else
        {
          FixedAttributes = 0;
        }
LABEL_73:
        v9 = v68;
      }
      if ( (*(_BYTE *)(&v31[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v31[4].Length) >= 5u )
      {
        WPP_SF_Dd(v31[3].Buffer, 86, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 2, FixedAttributes);
        v31 = WPP_GLOBAL_Control;
      }
      if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_Dd(
          v31[3].Buffer,
          87,
          WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
          (unsigned int)FixedAttributes,
          FixedAttributes);
        v31 = WPP_GLOBAL_Control;
      }
      if ( FixedAttributes >= 0 )
      {
        v46 = 4LL * v32[4];
        v47 = 0;
        v48 = (int *)(*(char **)((char *)&SampObjectExtendedAttributesProperties + v46 * 4)
                    + 32 * (unsigned int)(27 - dword_1800BD00C[v46]));
        v49 = &v32[6 * (27 - dword_1800BD00C[v46]) + 216];
        if ( (v32[5] & 0x20) != 0 )
        {
          v47 = *(_BYTE *)v49 >> 2;
          *(_BYTE *)v49 |= 4u;
          v31 = WPP_GLOBAL_Control;
        }
        if ( (*(_BYTE *)v49 & 4) != 0 )
        {
          v50 = ((__int64 (__fastcall *)(int *, __int128 *))qword_1800BD430[2 * *v48])(v49 + 2, &Buf1);
          FixedAttributes = v50;
          v31 = WPP_GLOBAL_Control;
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 66, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v50, v50);
            v31 = WPP_GLOBAL_Control;
          }
        }
        else
        {
          if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x20000) != 0 )
          {
            WPP_SF_Dd(v31[3].Buffer, 65, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221225506LL, -1073741790);
            v31 = WPP_GLOBAL_Control;
          }
          FixedAttributes = -1073741790;
        }
        if ( (v32[5] & 0x20) != 0 )
        {
          *(_BYTE *)v49 ^= (*(_BYTE *)v49 ^ (4 * v47)) & 4;
          v31 = WPP_GLOBAL_Control;
        }
        if ( (*(_BYTE *)(&v31[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v31[4].Length) >= 4u )
        {
          WPP_SF_ZD(
            v31[3].Buffer,
            67,
            (unsigned int)WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
            (_DWORD)v48 + 8,
            FixedAttributes);
          v31 = WPP_GLOBAL_Control;
        }
        if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            v31[3].Buffer,
            68,
            WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids,
            (unsigned int)FixedAttributes,
            FixedAttributes);
        if ( FixedAttributes >= 0 )
        {
          FixedAttributes = SampGetExtendedAttribute((__int64)v32, 39, (__int64)&v89);
          if ( FixedAttributes >= 0 )
          {
            Buf2 = 0;
            v51 = memcmp_0(&Buf1, &Buf2, 0x10u) == 0;
            if ( (v9 & 1) != 0 && v51 || (v9 & 2) != 0 && !v51 )
            {
              if ( (v9 & 4) == 0 )
              {
                v15 = v70;
                v28 = v67;
                if ( (_DWORD)v89 )
                  v29 = 0;
                goto LABEL_108;
              }
            }
            else if ( (v9 & 4) == 0 || !(_DWORD)v89 )
            {
              v29 = 0;
            }
          }
        }
      }
      v28 = v67;
      v15 = v70;
LABEL_108:
      if ( v32 )
      {
        *((_BYTE *)v32 + 20) |= 0x10u;
        v52 = 0;
        v39 = (v32[5] & 0x20) == 0;
        LODWORD(v69) = 0;
        if ( v39 )
        {
          SampImpersonateClient(&v69);
          v52 = (int)v69;
        }
        NtCloseObjectAuditAlarm(&SampSamSubsystem, v32, *((_BYTE *)v32 + 208));
        if ( v52 == 2 )
        {
          RpcRevertToSelf();
        }
        else
        {
          v53 = v52 - 1;
          if ( v53 )
          {
            if ( v53 == 2 && (int)SampShouldCallNtdsaApiSet() >= 0 )
              NtdsaExtUnImpersonateAnyClient();
          }
          else
          {
            SamIRevertNullSession();
          }
        }
        *((_BYTE *)v32 + 21) &= ~1u;
        v54 = *((_BYTE *)v32 + 28);
        if ( ((v54 & 1) == 0 || (v32[48] & 2) == 0) && v54 >= 0 )
        {
          RtlEnterCriticalSection(&SampContextListCritSect);
          v55 = *(int ***)v32;
          if ( *(_QWORD *)v32 )
          {
            v56 = (PVOID *)*((_QWORD *)v32 + 1);
            if ( v56 )
            {
              if ( v55[1] != v32 || *v56 != v32 )
                __fastfail(3u);
              *v56 = v55;
              v55[1] = (int *)v56;
            }
          }
          RtlLeaveCriticalSection(&SampContextListCritSect);
        }
        SampDeReferenceContext(v32, 0);
        HandleId = 0;
      }
      if ( !v29 )
        SampFreeUnicodeString(&SubKeyName);
      v11 = v74;
    }
    ++*v77;
    if ( FixedAttributes >= 0 && v29 )
    {
      v17 = v71 + 1;
      v72 += *((unsigned __int16 *)v28 + 9);
      *(_QWORD *)v28 = 0;
      if ( v15 )
        *v81 = v28;
      else
        v15 = v28;
      v81 = v28;
    }
    else
    {
      LocalFree(v28);
      v17 = v71;
    }
    if ( FixedAttributes < 0 )
      goto LABEL_145;
    v10 = v77;
    v19 = v72;
  }
  SampFreeUnicodeString(&SubKeyName);
  FixedAttributes = 0;
  v66 = v23 != -2147483622;
  if ( v23 != -2147483622 )
    FixedAttributes = v23;
LABEL_153:
  NtClose(KeyHandle);
  v18 = v66;
LABEL_154:
  if ( hMem[1] )
  {
    LocalFree(hMem[1]);
    hMem[1] = 0;
  }
  if ( FixedAttributes < 0 )
  {
    v12 = v82;
    goto LABEL_167;
  }
  if ( v18 )
    FixedAttributes = 261;
  v8 = v78;
  *v78 = v17;
  v58 = LocalAlloc(0x40u, 0x10u);
  v12 = v82;
  *v82 = v58;
  if ( v58 )
  {
    *v58 = *v8;
    v59 = LocalAlloc(0x40u, (unsigned int)(24 * *v8));
    *((_QWORD *)*v12 + 1) = v59;
    if ( !v59 )
    {
      FixedAttributes = -1073741670;
      LocalFree(*v12);
      v10 = v77;
      goto LABEL_168;
    }
    v60 = 0;
    while ( v15 )
    {
      v61 = v15;
      v62 = 3 * v60;
      v15 = *(unsigned int **)v15;
      v60 = (unsigned int)(v60 + 1);
      *(_OWORD *)&v59[v62] = *(_OWORD *)(v61 + 2);
      v59[v62 + 2] = *((_QWORD *)v61 + 3);
      LocalFree(v61);
    }
  }
  else
  {
    FixedAttributes = -1073741670;
LABEL_168:
    if ( v15 )
    {
      do
      {
        v63 = (void *)*((_QWORD *)v15 + 3);
        v64 = v15;
        v15 = *(unsigned int **)v15;
        if ( v63 )
          LocalFree(v63);
        LocalFree(v64);
      }
      while ( v15 );
      v8 = v78;
    }
LABEL_173:
    *v10 = 0;
    *v8 = 0;
    *v12 = 0;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      14,
      WPP_35556bb4c1df35c2a329f76602f997a4_Traceguids,
      (unsigned int)FixedAttributes,
      FixedAttributes);
  return (unsigned int)FixedAttributes;
}

```

## disassembly

```asm
0x180003d40  mov     [rsp-8+arg_10], rbx
0x180003d45  push    rbp
0x180003d46  push    rsi
0x180003d47  push    rdi
0x180003d48  push    r12
0x180003d4a  push    r13
0x180003d4c  push    r14
0x180003d4e  push    r15
0x180003d50  lea     rbp, [rsp-120h]
0x180003d58  sub     rsp, 220h
0x180003d5f  mov     rax, cs:__security_cookie
0x180003d66  xor     rax, rsp
0x180003d69  mov     [rbp+150h+var_40], rax
0x180003d70  mov     rdi, [rbp+150h+arg_30]
0x180003d77  mov     r15d, r8d
0x180003d7a  mov     [rbp+150h+var_1D0], r8d
0x180003d7e  mov     rsi, rdx
0x180003d81  mov     [rbp+150h+var_190], rdx
0x180003d85  mov     r12d, ecx
0x180003d88  mov     [rbp+150h+var_1A0], ecx
0x180003d8b  xor     edx, edx; Val
0x180003d8d  mov     r8d, 50h ; 'P'; Size
0x180003d93  mov     [rbp+150h+var_188], rdi
0x180003d97  lea     rcx, [rbp+150h+var_110]; void *
0x180003d9b  mov     [rbp+150h+var_168], r9
0x180003d9f  mov     r13, r9
0x180003da2  call    memset_0
0x180003da7  mov     ecx, cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A; _NT_PRODUCT_TYPE SampProductType
0x180003dad  xor     r8d, r8d
0x180003db0  mov     [rbp+150h+KeyHandle], r8
0x180003db4  xorps   xmm0, xmm0
0x180003db7  mov     [rbp+150h+HandleId], r8
0x180003dbb  mov     qword ptr [rbp+150h+Unused], r8
0x180003dbf  movups  xmmword ptr [rbp+150h+ObjectAttributes.Length], xmm0
0x180003dc3  movups  xmmword ptr [rbp+150h+ObjectAttributes.ObjectName], xmm0
0x180003dc7  movups  xmmword ptr [rbp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003dcb  movups  xmmword ptr [rbp+150h+hMem], xmm0
0x180003dcf  cmp     ecx, 2
0x180003dd2  jnz     short loc_180003DE4
0x180003dd4  test    r15b, 4
0x180003dd8  jz      short loc_180003DE4
0x180003dda  mov     ebx, 0C000000Dh
0x180003ddf  jmp     loc_180004934
0x180003de4  xor     bl, bl
0x180003de6  mov     [rsp+250h+var_1D8], r8
0x180003deb  mov     r14, r8
0x180003dee  movups  [rbp+150h+var_C0], xmm0
0x180003df5  cmp     ecx, 2
0x180003df8  jnz     short loc_180003E31
0x180003dfa  mov     edi, cs:dword_1800EF468
0x180003e00  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e07  test    dword ptr [rcx+44h], 20000h
0x180003e0e  jz      short loc_180003E2D
0x180003e10  mov     rcx, [rcx+38h]
0x180003e14  mov     edx, 58h ; 'X'
0x180003e19  mov     dword ptr [rsp+250h+var_230], r8d
0x180003e1e  xor     r9d, r9d
0x180003e21  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180003e28  call    WPP_SF_Dd
0x180003e2d  test    edi, edi
0x180003e2f  jz      short loc_180003E4E
0x180003e31  lea     r8, [rbp+150h+var_C0]
0x180003e38  mov     edx, 1
0x180003e3d  lea     rcx, [rsp+250h+var_1D8]
0x180003e42  call    cs:__imp_EnumerateIdentityProviders
0x180003e48  test    eax, eax
0x180003e4a  jnz     short loc_180003E4E
0x180003e4c  mov     bl, 1
0x180003e4e  mov     rcx, [rsp+250h+var_1D8]
0x180003e53  call    cs:__imp_ReleaseIdentityProviderEnumContext
0x180003e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e60  test    dword ptr [rcx+44h], 20000h
0x180003e67  jz      short loc_180003E86
0x180003e69  mov     rcx, [rcx+38h]
0x180003e6d  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180003e74  mov     edx, 0D0h
0x180003e79  mov     dword ptr [rsp+250h+var_230], r14d
0x180003e7e  xor     r9d, r9d
0x180003e81  call    WPP_SF_Dd
0x180003e86  test    bl, bl
0x180003e88  jz      short loc_180003EA9
0x180003e8a  test    r15d, r15d
0x180003e8d  jnz     short loc_180003EA9
0x180003e8f  cmp     cs:?gfShowShadowAdminAccounts@@3HA, r14d; int gfShowShadowAdminAccounts
0x180003e96  mov     eax, 7
0x180003e9b  mov     r15d, 3
0x180003ea1  cmovnz  r15d, eax
0x180003ea5  mov     [rbp+150h+var_1D0], r15d
0x180003ea9  xor     r8d, r8d
0x180003eac  lea     rdx, [rbp+150h+hMem]
0x180003eb0  mov     ecx, r12d
0x180003eb3  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180003eb8  mov     ebx, eax
0x180003eba  test    eax, eax
0x180003ebc  js      loc_180004901
0x180003ec2  mov     rax, cs:SampKey
0x180003ec9  lea     r8, [rbp+150h+ObjectAttributes]; ObjectAttributes
0x180003ecd  mov     [rbp+150h+ObjectAttributes.RootDirectory], rax
0x180003ed1  lea     rcx, [rbp+150h+KeyHandle]; KeyHandle
0x180003ed5  lea     rax, [rbp+150h+hMem]
0x180003ed9  mov     [rbp+150h+ObjectAttributes.Length], 30h ; '0'
0x180003ee0  xorps   xmm0, xmm0
0x180003ee3  mov     [rbp+150h+ObjectAttributes.ObjectName], rax
0x180003ee7  xor     r9d, r9d; Unused
0x180003eea  mov     [rbp+150h+ObjectAttributes.Attributes], 40h ; '@'
0x180003ef1  mov     edx, 20019h; DesiredAccess
0x180003ef6  xor     r13d, r13d
0x180003ef9  xor     dil, dil
0x180003efc  movdqu  xmmword ptr [rbp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003f01  call    cs:__imp_RtlpNtOpenKey
0x180003f07  mov     ebx, eax
0x180003f09  test    eax, eax
0x180003f0b  js      loc_18000482B
0x180003f11  xor     ebx, ebx
0x180003f13  mov     [rbp+150h+var_170], r13
0x180003f17  cmp     [rbp+150h+arg_38], bl
0x180003f1d  mov     ecx, 0FFFFFFFFh
0x180003f22  mov     eax, 1000000h
0x180003f27  mov     [rsp+250h+var_1DF], 1
0x180003f2c  cmovz   ecx, eax
0x180003f2f  mov     [rbp+150h+var_1B4], ebx
0x180003f32  mov     [rbp+150h+var_19C], ecx
0x180003f35  mov     [rbp+150h+var_1C0], r14
0x180003f39  xorps   xmm0, xmm0
0x180003f3c  mov     [rbp+150h+var_1B8], r13d
0x180003f40  mov     edx, 20h ; ' '; uBytes
0x180003f45  lea     eax, [rbx+30h]
0x180003f48  movups  xmmword ptr [rbp+150h+SubKeyName.Length], xmm0
0x180003f4c  test    ebx, ebx
0x180003f4e  jz      short loc_180003F5C
0x180003f50  cmp     eax, [rbp+150h+arg_20]
0x180003f56  jnb     loc_18000481A
0x180003f5c  cmp     eax, ecx
0x180003f5e  ja      loc_18000481A
0x180003f64  mov     ecx, 40h ; '@'; uFlags
0x180003f69  mov     [rbp+150h+SubKeyName.MaximumLength], dx
0x180003f6d  call    cs:__imp_LocalAlloc
0x180003f73  mov     [rbp+150h+SubKeyName.Buffer], rax
0x180003f77  test    rax, rax
0x180003f7a  jz      loc_1800047E0
0x180003f80  xor     ecx, ecx
0x180003f82  lea     r9, [rbp+150h+Unused]; Unused
0x180003f86  mov     [rax], cx
0x180003f89  lea     rdx, [rbp+150h+SubKeyName]; SubKeyName
0x180003f8d  mov     r8d, [rsi]; Index
0x180003f90  mov     rcx, [rbp+150h+KeyHandle]; KeyHandle
0x180003f94  call    cs:__imp_RtlpNtEnumerateSubKey
0x180003f9a  mov     edi, eax
0x180003f9c  cmp     eax, 80000005h
0x180003fa1  jnz     short loc_18000401D
0x180003fa3  mov     rcx, [rbp+150h+SubKeyName.Buffer]; hMem
0x180003fa7  test    rcx, rcx
0x180003faa  jz      short loc_180003FBA
0x180003fac  call    cs:__imp_LocalFree
0x180003fb2  mov     [rbp+150h+SubKeyName.Buffer], 0
0x180003fba  movzx   ecx, [rbp+150h+SubKeyName.Length]
0x180003fbe  lea     edx, [rcx+10h]
0x180003fc1  add     edx, ebx
0x180003fc3  test    ebx, ebx
0x180003fc5  jz      short loc_180003FD3
0x180003fc7  cmp     edx, [rbp+150h+arg_20]
0x180003fcd  jnb     loc_18000481A
0x180003fd3  cmp     edx, [rbp+150h+var_19C]
0x180003fd6  ja      loc_18000481A
0x180003fdc  xor     eax, eax
0x180003fde  mov     [rbp+150h+SubKeyName.MaximumLength], cx
0x180003fe2  mov     rdx, rcx; uBytes
0x180003fe5  mov     [rbp+150h+SubKeyName.Length], ax
0x180003fe9  mov     ecx, 40h ; '@'; uFlags
0x180003fee  call    cs:__imp_LocalAlloc
0x180003ff4  mov     [rbp+150h+SubKeyName.Buffer], rax
0x180003ff8  test    rax, rax
0x180003ffb  jz      loc_180004785
0x180004001  xor     ecx, ecx
0x180004003  lea     r9, [rbp+150h+Unused]; Unused
0x180004007  mov     [rax], cx
0x18000400a  lea     rdx, [rbp+150h+SubKeyName]; SubKeyName
0x18000400e  mov     r8d, [rsi]; Index
0x180004011  mov     rcx, [rbp+150h+KeyHandle]; KeyHandle
0x180004015  call    cs:__imp_RtlpNtEnumerateSubKey
0x18000401b  mov     edi, eax
0x18000401d  test    edi, edi
0x18000401f  js      loc_1800047BD
0x180004025  mov     edx, 20h ; ' '; uBytes
0x18000402a  mov     ecx, 40h ; '@'; uFlags
0x18000402f  call    cs:__imp_LocalAlloc
0x180004035  mov     [rsp+250h+var_1D8], rax
0x18000403a  mov     rsi, rax
0x18000403d  test    rax, rax
0x180004040  jz      loc_1800047A9
0x180004046  movups  xmm0, xmmword ptr [rbp+150h+SubKeyName.Length]
0x18000404a  lea     rdx, [rax+10h]
0x18000404e  mov     r8d, 0C00000E4h
0x180004054  lea     rax, [rbp+150h+var_1C8]
0x180004058  mov     ecx, r12d
0x18000405b  lea     r9, [rsi+8]
0x18000405f  mov     [rsp+250h+var_230], rax
0x180004064  movups  xmmword ptr [rdx], xmm0
0x180004067  call    ?SampLookupAccountRidRegistry@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@JPEAKPEAW4_SID_NAME_USE@@@Z; SampLookupAccountRidRegistry(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,long,ulong *,_SID_NAME_USE *)
0x18000406c  mov     ebx, eax
0x18000406e  test    eax, eax
0x180004070  js      loc_18000479E
0x180004076  mov     r13b, 1
0x180004079  cmp     r12d, 4
0x18000407d  jnz     loc_18000472A
0x180004083  cmp     [rbp+150h+arg_28], 0
0x18000408a  jnz     short loc_180004095
0x18000408c  test    r15d, r15d
0x18000408f  jz      loc_18000472A
0x180004095  mov     r8d, [rsi+8]
0x180004099  lea     rax, [rbp+150h+HandleId]
0x18000409d  mov     [rsp+250h+var_1E8], rax
0x1800040a2  xor     r9d, r9d
0x1800040a5  xor     eax, eax
0x1800040a7  mov     edx, 4
0x1800040ac  mov     [rsp+250h+var_1F0], rax
0x1800040b1  xor     ecx, ecx
0x1800040b3  mov     [rsp+250h+var_1F8], al
0x1800040b7  mov     [rsp+250h+var_200], al
0x1800040bb  mov     [rsp+250h+var_208], r13b
0x1800040c0  mov     [rsp+250h+var_210], al
0x1800040c4  mov     [rsp+250h+var_218], al
0x1800040c8  mov     [rsp+250h+var_220], r13b
0x1800040cd  mov     [rsp+250h+var_228], 1
0x1800040d5  mov     [rsp+250h+var_230], rax
0x1800040da  call    SampCreateAccountContext2
0x1800040df  mov     ebx, eax
0x1800040e1  mov     r10, cs:WPP_GLOBAL_Control
0x1800040e8  test    dword ptr [r10+44h], 20000h
0x1800040f0  jz      short loc_180004115
0x1800040f2  mov     rcx, [r10+38h]
0x1800040f6  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800040fd  mov     edx, 7Bh ; '{'
0x180004102  mov     dword ptr [rsp+250h+var_230], eax
0x180004106  mov     r9d, eax
0x180004109  call    WPP_SF_Dd
0x18000410e  mov     r10, cs:WPP_GLOBAL_Control
0x180004115  mov     r12, [rbp+150h+HandleId]
0x180004119  test    ebx, ebx
0x18000411b  js      loc_180004632
0x180004121  mov     edi, [rbp+150h+arg_28]
0x180004127  test    edi, edi
0x180004129  jz      loc_1800041D7
0x18000412f  lea     r8, [rbp+150h+var_1C8]
0x180004133  mov     [rbp+150h+var_1C8], 0
0x18000413b  xor     edx, edx
0x18000413d  mov     rcx, r12
0x180004140  call    SampGetFixedAttributes
0x180004145  mov     ebx, eax
0x180004147  test    eax, eax
0x180004149  js      short loc_180004179
0x18000414b  mov     rax, [rbp+150h+var_1C8]
0x18000414f  movups  xmm0, xmmword ptr [rax]
0x180004152  movups  xmm1, xmmword ptr [rax+10h]
0x180004156  movaps  [rbp+150h+var_110], xmm0
0x18000415a  movups  xmm0, xmmword ptr [rax+20h]
0x18000415e  movaps  [rbp+150h+var_100], xmm1
0x180004162  movups  xmm1, xmmword ptr [rax+30h]
0x180004166  movaps  [rbp+150h+var_F0], xmm0
0x18000416a  movups  xmm0, xmmword ptr [rax+40h]
0x18000416e  movaps  [rbp+150h+var_E0], xmm1
0x180004172  movaps  [rbp+150h+var_D0], xmm0
0x180004179  mov     rcx, cs:WPP_GLOBAL_Control
0x180004180  test    dword ptr [rcx+44h], 20000h
0x180004187  jz      short loc_1800041A5
0x180004189  mov     rcx, [rcx+38h]
0x18000418d  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x180004194  mov     edx, 0D3h
0x180004199  mov     dword ptr [rsp+250h+var_230], ebx
0x18000419d  mov     r9d, ebx
0x1800041a0  call    WPP_SF_Dd
0x1800041a5  test    ebx, ebx
0x1800041a7  js      loc_180004632
0x1800041ad  lea     rdx, [rbp+150h+var_E0+8]
0x1800041b1  mov     rcx, r12
0x1800041b4  call    SampUpdateAccountDisabledFlag
0x1800041b9  mov     ebx, eax
0x1800041bb  test    eax, eax
0x1800041bd  js      loc_180004632
0x1800041c3  test    dword ptr [rbp+150h+var_E0+8], edi
0x1800041c6  jnz     short loc_1800041D0
0x1800041c8  xor     r13b, r13b
0x1800041cb  jmp     loc_180004632
0x1800041d0  mov     r10, cs:WPP_GLOBAL_Control
0x1800041d7  test    r15d, r15d
0x1800041da  jz      loc_180004632
0x1800041e0  xorps   xmm0, xmm0
0x1800041e3  mov     [rbp+150h+var_A0], 1Bh
0x1800041ed  movups  [rbp+150h+Buf1], xmm0
0x1800041f4  mov     [rbp+150h+var_9C], 27h ; '''
0x1800041fe  lea     rdi, __ImageBase
0x180004205  xorps   xmm1, xmm1
0x180004208  mov     esi, 2
0x18000420d  movups  [rbp+150h+var_C0], xmm1
0x180004214  mov     eax, [r12+0C0h]
0x18000421c  and     eax, 2
0x18000421f  mov     dword ptr [rbp+150h+var_1C8], esi
0x180004222  add     rax, rax
0x180004225  test    byte ptr [r12+14h], 20h
0x18000422b  mov     rax, ds:(funcs_180001EF0 - 180000000h)[rdi+rax*8]
  ... truncated ...
```
