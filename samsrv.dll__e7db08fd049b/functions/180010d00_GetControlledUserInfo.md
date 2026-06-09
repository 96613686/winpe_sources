# GetControlledUserInfo

- ea: `0x180010d00`
- end: `0x180011807`
- name: `GetControlledUserInfo`
- size: `2823`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ed50`
- `0x18005e5c0`

## callees

- `0x180009030`
- `0x180010d00`
- `0x180011810`
- `0x18001b4e0`
- `0x180024a34`
- `0x180027e24`
- `0x18002cd80`
- `0x180037284`
- `0x1800372ac`
- `0x180059a74`
- `0x1800bb77c`
- `0x1800bc010`

## import_xrefs

- `ntdll!RtlIdentifierAuthoritySid` at `0x1800116fb`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180011707`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800116fb`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180011707`
- `ntdll!RtlSubAuthorityCountSid` at `0x180010d77`
- `ntdll!RtlSubAuthorityCountSid` at `0x180010dc1`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800116dd`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800116e9`
- `ntdll!RtlSubAuthorityCountSid` at `0x180011724`
- `ntdll!RtlSubAuthorityCountSid` at `0x180010d77`
- `ntdll!RtlSubAuthorityCountSid` at `0x180010dc1`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800116dd`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800116e9`
- `ntdll!RtlSubAuthorityCountSid` at `0x180011724`
- `ntdll!RtlSubAuthoritySid` at `0x180010dcf`
- `ntdll!RtlSubAuthoritySid` at `0x180011736`
- `ntdll!RtlSubAuthoritySid` at `0x180011744`
- `ntdll!RtlSubAuthoritySid` at `0x180010dcf`
- `ntdll!RtlSubAuthoritySid` at `0x180011736`
- `ntdll!RtlSubAuthoritySid` at `0x180011744`
- `ntdll!RtlLengthRequiredSid` at `0x180010d87`
- `ntdll!RtlLengthRequiredSid` at `0x180010d87`
- `ntdll!RtlCopySid` at `0x180010db8`
- `ntdll!RtlCopySid` at `0x180010db8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010d96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010d96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800112f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800115df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800112f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800115df`

## pseudocode

```c
__int64 __fastcall GetControlledUserInfo(struct _SAMP_OBJECT *a1, int *a2, _QWORD *a3)
{
  __int64 v4; // rax
  int v5; // ecx
  void *v6; // rdi
  ULONG v7; // r14d
  ULONG v8; // ebx
  SIZE_T v9; // rsi
  HLOCAL v10; // rax
  void *v11; // r13
  unsigned int v12; // ebx
  PULONG v13; // rax
  PUNICODE_STRING v14; // rcx
  char v16; // r12
  int v17; // r15d
  unsigned __int8 v18; // bl
  __int64 v19; // rdi
  __int64 v20; // r14
  PUNICODE_STRING v21; // r10
  __int64 v22; // rax
  __int64 v23; // rbx
  unsigned int *v24; // rdx
  int v25; // esi
  int v26; // ebx
  __int64 v27; // rdx
  char v28; // si
  int *v29; // r14
  _BYTE *v30; // rdi
  unsigned int v31; // eax
  char v32; // di
  PUNICODE_STRING v33; // rcx
  PUNICODE_STRING v34; // rcx
  __int64 v35; // rdx
  unsigned int v36; // esi
  PUNICODE_STRING v37; // rcx
  int AliasMembershipWorker; // eax
  HLOCAL v39; // r14
  unsigned int v40; // edi
  unsigned int i; // ecx
  PUNICODE_STRING v42; // rcx
  int v43; // r14d
  __int64 v44; // rdx
  void *v45; // rsi
  int v46; // ebx
  PSID_IDENTIFIER_AUTHORITY v47; // rbx
  PSID_IDENTIFIER_AUTHORITY v48; // rax
  int v49; // ecx
  size_t v50; // rdi
  PULONG v51; // rbx
  PULONG v52; // rax
  HLOCAL v53; // [rsp+30h] [rbp-89h] BYREF
  int *v54; // [rsp+38h] [rbp-81h]
  HLOCAL hMem[2]; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v56[2]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD *v57; // [rsp+60h] [rbp-59h]
  unsigned int v58[2]; // [rsp+70h] [rbp-49h] BYREF
  PSID v59; // [rsp+78h] [rbp-41h]
  PSID v60; // [rsp+80h] [rbp-39h]
  __int64 v61; // [rsp+88h] [rbp-31h]
  __int64 v62; // [rsp+90h] [rbp-29h]
  __int64 v63; // [rsp+98h] [rbp-21h]
  __int64 v64; // [rsp+A0h] [rbp-19h]

  v57 = a3;
  *a3 = 0;
  *a2 = 0;
  v4 = *((unsigned int *)a1 + 50);
  v5 = *((_DWORD *)a1 + 4);
  v54 = a2;
  v6 = (void *)*((_QWORD *)SampDefinedDomains + 170 * v4 + 1);
  if ( v5 == 2 || (v7 = 0, (unsigned int)(v5 - 3) <= 1) )
    v7 = *((_DWORD *)a1 + 62);
  v8 = (unsigned __int8)(*RtlSubAuthorityCountSid(*((PSID *)SampDefinedDomains + 170 * v4 + 1)) + 1);
  v9 = RtlLengthRequiredSid(v8);
  v10 = LocalAlloc(0x40u, v9);
  v53 = v10;
  v11 = v10;
  if ( v10 )
  {
    RtlCopySid(v9, v10, v6);
    *RtlSubAuthorityCountSid(v11) = v8;
    v13 = RtlSubAuthoritySid(v11, v8 - 1);
    v12 = 0;
    *v13 = v7;
  }
  else
  {
    v12 = -1073741670;
  }
  v14 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 126, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v12, v12);
    v14 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 127, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v12, v12);
      v14 = WPP_GLOBAL_Control;
    }
  }
  if ( (v12 & 0x80000000) != 0 )
  {
    if ( (*(_BYTE *)(&v14[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v14[4].Length) >= 2u )
    {
      WPP_SF_d(v14[3].Buffer, 19, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, v12);
      v14 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(&v14[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(v14[3].Buffer, 20, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, v12, v12);
    if ( v11 )
      LocalFree(v11);
    return v12;
  }
  v16 = *((_BYTE *)a1 + 20);
  *(_OWORD *)hMem = 0;
  if ( (*(_DWORD *)(&v14[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_d(v14[3].Buffer, 73, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, SampUseDsData);
    v14 = WPP_GLOBAL_Control;
  }
  if ( SampUseDsData )
  {
    if ( (*(_DWORD *)(&v14[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(v14[3].Buffer, 343, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, 0, 0);
    goto LABEL_24;
  }
  *((_BYTE *)a1 + 20) |= 0x20u;
  LODWORD(v19) = 1;
  v20 = *((int *)a1 + 4);
  v21 = WPP_GLOBAL_Control;
  v22 = 2LL * (*((_DWORD *)a1 + 48) & 2);
  v58[0] = 29;
  v23 = 0;
  v56[0] = *(&funcs_180001EF0 + v22);
  while ( (unsigned int)v23 < (unsigned int)v19 )
  {
    v24 = &v58[v23];
    if ( (*((_BYTE *)a1 + 24 * (*v24 - dword_1800BD00C[4 * v20]) + 864) & 1) != 0 )
    {
      v19 = (unsigned int)(v19 - 1);
      LODWORD(v23) = v23 - 1;
      *v24 = v58[v19];
    }
    else
    {
      v25 = *(_DWORD *)(*((_QWORD *)&SampObjectExtendedAttributesProperties + 2 * *((int *)a1 + 4))
                      + 32LL * (v58[v23] - dword_1800BD00C[4 * v20])
                      + 4)
          & (((*((_BYTE *)a1 + 192) & 2) != 0) + 1);
      if ( (*(_DWORD *)(&v21[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_d(v21[3].Buffer, 40, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v25 != 0);
        v21 = WPP_GLOBAL_Control;
      }
      if ( !v25 )
      {
        v26 = -1073741149;
        if ( (*(_DWORD *)(&v21[4].MaximumLength + 1) & 0x20000) == 0 )
          goto LABEL_44;
        WPP_SF_Dd(v21[3].Buffer, 82, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221226147LL, -1073741149);
        goto LABEL_43;
      }
    }
    v23 = (unsigned int)(v23 + 1);
  }
  if ( (*(_DWORD *)(&v21[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(v21[3].Buffer, 83, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 0, 0);
    v21 = WPP_GLOBAL_Control;
  }
  if ( !(_DWORD)v19 )
  {
    v26 = 0;
    goto LABEL_44;
  }
  v26 = ((__int64 (__fastcall *)(struct _SAMP_OBJECT *, unsigned int *, _QWORD))v56[0])(a1, v58, (unsigned int)v19);
LABEL_43:
  v21 = WPP_GLOBAL_Control;
LABEL_44:
  if ( (*(_BYTE *)(&v21[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v21[4].Length) >= 5u )
  {
    WPP_SF_Dd(v21[3].Buffer, 86, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 1, v26);
    v21 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v21[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(v21[3].Buffer, 87, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, (unsigned int)v26, v26);
    v21 = WPP_GLOBAL_Control;
  }
  if ( v26 < 0 )
    goto LABEL_68;
  v27 = 4LL * *((int *)a1 + 4);
  v28 = 0;
  v29 = (int *)(*(char **)((char *)&SampObjectExtendedAttributesProperties + v27 * 4)
              + 32 * (unsigned int)(29 - dword_1800BD00C[v27]));
  v30 = (char *)a1 + 24 * (unsigned int)(29 - dword_1800BD00C[v27]) + 864;
  if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
  {
    v28 = *v30 >> 2;
    *v30 |= 4u;
    v21 = WPP_GLOBAL_Control;
  }
  if ( (*v30 & 4) != 0 )
  {
    v31 = ((__int64 (__fastcall *)(_BYTE *, HLOCAL *))qword_1800BD430[2 * *v29])(v30 + 8, hMem);
    v26 = v31;
    v21 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      goto LABEL_58;
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 66, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, v31, v31);
  }
  else
  {
    v26 = -1073741790;
    if ( (*(_DWORD *)(&v21[4].MaximumLength + 1) & 0x20000) == 0 )
      goto LABEL_58;
    WPP_SF_Dd(v21[3].Buffer, 65, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, 3221225506LL, -1073741790);
  }
  v21 = WPP_GLOBAL_Control;
LABEL_58:
  if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
  {
    *v30 ^= (*v30 ^ (4 * v28)) & 4;
    v21 = WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)(&v21[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v21[4].Length) >= 4u )
  {
    WPP_SF_ZD(v21[3].Buffer, 67, (unsigned int)WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, (_DWORD)v29 + 8, v26);
    v21 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v21[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v21[3].Buffer, 68, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids, (unsigned int)v26, v26);
  if ( v26 >= 0 && hMem[1] )
  {
    v32 = 1;
    LocalFree(hMem[1]);
    goto LABEL_69;
  }
LABEL_68:
  v32 = 0;
LABEL_69:
  *((_BYTE *)a1 + 20) ^= (*((_BYTE *)a1 + 20) ^ v16 & 0xE0) & 0x20;
  v33 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      344,
      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
      (unsigned int)v26,
      v26);
    v33 = WPP_GLOBAL_Control;
  }
  if ( v26 >= 0 )
  {
    if ( v32 )
    {
      *v54 = 0;
      v34 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v35 = 23;
LABEL_141:
        WPP_SF_Dd(v34[3].Buffer, v35, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, 0, 0);
      }
LABEL_142:
      SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v53);
      return 0;
    }
LABEL_24:
    v59 = SampWorldSid;
    v17 = 0;
    v60 = SampAuthenticatedUsersSid;
    v61 = SampInteractiveSid;
    v62 = SampLocalLogonSid;
    v63 = SampRemoteInteractiveSid;
    v64 = SampTerminalServerSid;
    v56[1] = v58;
    *(_QWORD *)v58 = v11;
    v56[0] = 7;
    *(_OWORD *)hMem = 0;
    if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
      v18 = SampTransactionWithinDomainGlobal;
    }
    else
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
      v18 = 0;
    }
    v36 = SampTransactionDomainIndexGlobal;
    if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
    {
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
      SampTransactionWithinDomainGlobal = 0;
    }
    else
    {
      v37 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
        v37 = WPP_GLOBAL_Control;
      }
      if ( (*(_BYTE *)(&v37[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v37[4].Length) >= 2u )
        WPP_SF_(v37[3].Buffer, 10, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
    }
    SampSetTransactionDomain(0);
    AliasMembershipWorker = SampGetAliasMembershipWorker(
                              *(void **)SampDefinedDomains,
                              (struct _SAMPR_PSID_ARRAY *)v56,
                              1,
                              (struct _SAMPR_ULONG_ARRAY *)hMem);
    v39 = hMem[1];
    v40 = AliasMembershipWorker;
    if ( AliasMembershipWorker >= 0 )
    {
      for ( i = 0; i < LODWORD(hMem[0]); ++i )
      {
        if ( *((_DWORD *)hMem[1] + i) == 544 )
        {
          v17 = 1;
          break;
        }
      }
    }
    else if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
           && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[3].Buffer,
        15,
        WPP_da2026cb803030835d407f26f8ebde50_Traceguids,
        (unsigned int)AliasMembershipWorker);
    }
    if ( SampLock.OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
    {
      v42 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 209, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 1);
        v42 = WPP_GLOBAL_Control;
      }
      SampTransactionWithinDomainGlobal = 0;
    }
    else
    {
      v42 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 210, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, 0);
        v42 = WPP_GLOBAL_Control;
      }
      if ( (*(_BYTE *)(&v42[4].MaximumLength + 1) & 4) != 0 && HIBYTE(v42[4].Length) >= 2u )
      {
        WPP_SF_(v42[3].Buffer, 10, WPP_48bf36016493398285a8dbc678e80a21_Traceguids);
        v42 = WPP_GLOBAL_Control;
      }
    }
    if ( v18 )
    {
      SampSetTransactionDomain(v36);
      v42 = WPP_GLOBAL_Control;
    }
    if ( v39 )
    {
      LocalFree(v39);
      v42 = WPP_GLOBAL_Control;
    }
    if ( (*(_DWORD *)(&v42[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      WPP_SF_Dd(v42[3].Buffer, 16, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, v40, v40);
      v42 = WPP_GLOBAL_Control;
    }
    if ( (v40 & 0x80000000) != 0 )
    {
      if ( (*(_BYTE *)(&v42[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v42[4].Length) >= 2u )
      {
        WPP_SF_d(v42[3].Buffer, 24, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, v40);
        v42 = WPP_GLOBAL_Control;
      }
      if ( (*(_DWORD *)(&v42[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(v42[3].Buffer, 25, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, v40, v40);
      SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v53);
      return v40;
    }
    if ( v17 == 1 )
    {
      *v54 = 1;
      v34 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v35 = 26;
        goto LABEL_141;
      }
      goto LABEL_142;
    }
    v43 = 0;
    if ( SampIsMachineJoinedToDomain )
    {
      v45 = (void *)*((_QWORD *)SampDefinedDomains + 171);
      v46 = *RtlSubAuthorityCountSid(v11);
      if ( *RtlSubAuthorityCountSid(v45) + 1 != v46 )
        goto LABEL_135;
      v47 = RtlIdentifierAuthoritySid(v11);
      v48 = RtlIdentifierAuthoritySid(v45);
      v49 = *(_DWORD *)v48->Value - *(_DWORD *)v47->Value;
      if ( *(_DWORD *)v48->Value == *(_DWORD *)v47->Value )
        v49 = *(unsigned __int16 *)&v48->Value[4] - *(unsigned __int16 *)&v47->Value[4];
      if ( v49
        || (v50 = 4LL * *RtlSubAuthorityCountSid(v45),
            v51 = RtlSubAuthoritySid(v11, 0),
            v52 = RtlSubAuthoritySid(v45, 0),
            memcmp_0(v52, v51, v50)) )
      {
LABEL_135:
        v43 = 1;
      }
      v42 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      {
LABEL_139:
        v53 = 0;
        *v57 = v11;
        *v54 = v43 ^ 1;
        v34 = WPP_GLOBAL_Control;
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        {
          v35 = 29;
          goto LABEL_141;
        }
        goto LABEL_142;
      }
      v44 = 18;
    }
    else
    {
      if ( (*(_DWORD *)(&v42[4].MaximumLength + 1) & 0x20000) == 0 )
        goto LABEL_139;
      v44 = 17;
    }
    WPP_SF_Dd(v42[3].Buffer, v44, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, 0, 0);
    goto LABEL_139;
  }
  if ( (*(_BYTE *)(&v33[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v33[4].Length) >= 2u )
  {
    WPP_SF_d(v33[3].Buffer, 21, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, (unsigned int)v26);
    v33 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v33[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v33[3].Buffer, 22, WPP_da2026cb803030835d407f26f8ebde50_Traceguids, (unsigned int)v26, v26);
  SP<unsigned char,SP_HLOCAL<unsigned char>>::Reset(&v53);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x180010d00  mov     [rsp-8+arg_18], rbx
0x180010d05  push    rbp
0x180010d06  push    rsi
0x180010d07  push    rdi
0x180010d08  push    r12
0x180010d0a  push    r13
0x180010d0c  push    r14
0x180010d0e  push    r15
0x180010d10  lea     rbp, [rsp-27h]
0x180010d15  sub     rsp, 0E0h
0x180010d1c  mov     rax, cs:__security_cookie
0x180010d23  xor     rax, rsp
0x180010d26  mov     [rbp+57h+var_40], rax
0x180010d2a  xor     r12d, r12d
0x180010d2d  mov     [rbp+57h+var_B0], r8
0x180010d31  mov     [r8], r12
0x180010d34  mov     r15, rcx
0x180010d37  mov     [rdx], r12d
0x180010d3a  mov     eax, [rcx+0C8h]
0x180010d40  mov     ecx, [rcx+10h]
0x180010d43  imul    r9, rax, 550h
0x180010d4a  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180010d51  mov     [rsp+110h+var_D8], rdx
0x180010d56  mov     rdi, [r9+rax+8]
0x180010d5b  cmp     ecx, 2
0x180010d5e  jz      short loc_180010D6D
0x180010d60  mov     r14d, r12d
0x180010d63  sub     ecx, 3
0x180010d66  jz      short loc_180010D6D
0x180010d68  cmp     ecx, 1
0x180010d6b  jnz     short loc_180010D74
0x180010d6d  mov     r14d, [r15+0F8h]
0x180010d74  mov     rcx, rdi; Sid
0x180010d77  call    cs:__imp_RtlSubAuthorityCountSid
0x180010d7d  movzx   ecx, byte ptr [rax]
0x180010d80  inc     cl
0x180010d82  movzx   ebx, cl
0x180010d85  mov     ecx, ebx; SubAuthorityCount
0x180010d87  call    cs:__imp_RtlLengthRequiredSid
0x180010d8d  mov     edx, eax; uBytes
0x180010d8f  mov     ecx, 40h ; '@'; uFlags
0x180010d94  mov     esi, eax
0x180010d96  call    cs:__imp_LocalAlloc
0x180010d9c  mov     [rsp+110h+var_E0], rax
0x180010da1  mov     r13, rax
0x180010da4  test    rax, rax
0x180010da7  jnz     short loc_180010DB0
0x180010da9  mov     ebx, 0C000009Ah
0x180010dae  jmp     short loc_180010DDA
0x180010db0  mov     r8, rdi; SourceSid
0x180010db3  mov     rdx, r13; DestinationSid
0x180010db6  mov     ecx, esi; DestinationSidLength
0x180010db8  call    cs:__imp_RtlCopySid
0x180010dbe  mov     rcx, r13; Sid
0x180010dc1  call    cs:__imp_RtlSubAuthorityCountSid
0x180010dc7  lea     edx, [rbx-1]; SubAuthority
0x180010dca  mov     rcx, r13; Sid
0x180010dcd  mov     [rax], bl
0x180010dcf  call    cs:__imp_RtlSubAuthoritySid
0x180010dd5  xor     ebx, ebx
0x180010dd7  mov     [rax], r14d
0x180010dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180010de1  test    dword ptr [rcx+44h], 20000h
0x180010de8  jz      short loc_180010E39
0x180010dea  mov     rcx, [rcx+38h]
0x180010dee  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180010df5  mov     edx, 7Eh ; '~'
0x180010dfa  mov     [rsp+110h+var_F0], ebx
0x180010dfe  mov     r9d, ebx
0x180010e01  call    WPP_SF_Dd
0x180010e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e0d  test    dword ptr [rcx+44h], 20000h
0x180010e14  jz      short loc_180010E39
0x180010e16  mov     rcx, [rcx+38h]
0x180010e1a  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180010e21  mov     edx, 7Fh
0x180010e26  mov     [rsp+110h+var_F0], ebx
0x180010e2a  mov     r9d, ebx
0x180010e2d  call    WPP_SF_Dd
0x180010e32  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e39  test    ebx, ebx
0x180010e3b  jns     short loc_180010EA2
0x180010e3d  test    byte ptr [rcx+44h], 20h
0x180010e41  jz      short loc_180010E68
0x180010e43  cmp     byte ptr [rcx+41h], 2
0x180010e47  jb      short loc_180010E68
0x180010e49  mov     rcx, [rcx+38h]
0x180010e4d  lea     r8, WPP_da2026cb803030835d407f26f8ebde50_Traceguids
0x180010e54  mov     edx, 13h
0x180010e59  mov     r9d, ebx
0x180010e5c  call    WPP_SF_d
0x180010e61  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e68  test    dword ptr [rcx+44h], 20000h
0x180010e6f  jz      short loc_180010E8D
0x180010e71  mov     rcx, [rcx+38h]
0x180010e75  lea     r8, WPP_da2026cb803030835d407f26f8ebde50_Traceguids
0x180010e7c  mov     edx, 14h
0x180010e81  mov     [rsp+110h+var_F0], ebx
0x180010e85  mov     r9d, ebx
0x180010e88  call    WPP_SF_Dd
0x180010e8d  test    r13, r13
0x180010e90  jz      short loc_180010E9B
0x180010e92  mov     rcx, r13; hMem
0x180010e95  call    cs:__imp_LocalFree
0x180010e9b  mov     eax, ebx
0x180010e9d  jmp     loc_1800117E0
0x180010ea2  movzx   r12d, byte ptr [r15+14h]
0x180010ea7  xorps   xmm0, xmm0
0x180010eaa  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180010eae  test    dword ptr [rcx+44h], 20000h
0x180010eb5  jz      short loc_180010EDB
0x180010eb7  movzx   r9d, cs:?SampUseDsData@@3EA; uchar SampUseDsData
0x180010ebf  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180010ec6  mov     rcx, [rcx+38h]
0x180010eca  mov     edx, 49h ; 'I'
0x180010ecf  call    WPP_SF_d
0x180010ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180010edb  cmp     cs:?SampUseDsData@@3EA, 0; uchar SampUseDsData
0x180010ee2  jz      loc_180010FC5
0x180010ee8  test    dword ptr [rcx+44h], 20000h
0x180010eef  jz      short loc_180010F11
0x180010ef1  mov     rcx, [rcx+38h]
0x180010ef5  lea     r8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x180010efc  mov     edx, 157h
0x180010f01  mov     [rsp+110h+var_F0], 0
0x180010f09  xor     r9d, r9d
0x180010f0c  call    WPP_SF_Dd
0x180010f11  mov     rax, cs:SampWorldSid
0x180010f18  xor     r12d, r12d
0x180010f1b  mov     [rbp+57h+var_98], rax
0x180010f1f  xorps   xmm0, xmm0
0x180010f22  mov     rax, cs:SampAuthenticatedUsersSid
0x180010f29  mov     r15d, r12d
0x180010f2c  mov     [rbp+57h+var_90], rax
0x180010f30  mov     rax, cs:SampInteractiveSid
0x180010f37  mov     [rbp+57h+var_88], rax
0x180010f3b  mov     rax, cs:SampLocalLogonSid
0x180010f42  mov     [rbp+57h+var_80], rax
0x180010f46  mov     rax, cs:SampRemoteInteractiveSid
0x180010f4d  mov     [rbp+57h+var_78], rax
0x180010f51  mov     rax, cs:SampTerminalServerSid
0x180010f58  mov     [rbp+57h+var_70], rax
0x180010f5c  lea     rax, [rbp+57h+var_A0]
0x180010f60  mov     [rbp+57h+var_B8], rax
0x180010f64  mov     qword ptr [rbp+57h+var_A0], r13
0x180010f68  mov     rax, gs:30h
0x180010f71  mov     [rbp+57h+var_C0], 7
0x180010f79  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180010f7d  mov     rax, [rax+48h]
0x180010f81  cmp     cs:?SampLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, rax; _RTL_CRITICAL_SECTION SampLock ...
0x180010f88  jnz     loc_1800113DA
0x180010f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f95  test    dword ptr [rcx+44h], 20000h
0x180010f9c  jz      short loc_180010FB9
0x180010f9e  mov     rcx, [rcx+38h]
0x180010fa2  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180010fa9  mov     edx, 0D1h
0x180010fae  mov     r9d, 1
0x180010fb4  call    WPP_SF_d
0x180010fb9  movzx   ebx, cs:?SampTransactionWithinDomainGlobal@@3EA; uchar SampTransactionWithinDomainGlobal
0x180010fc0  jmp     loc_180011404
0x180010fc5  or      byte ptr [r15+14h], 20h
0x180010fca  lea     r9, __ImageBase
0x180010fd1  mov     eax, [r15+0C0h]
0x180010fd8  mov     edi, 1
0x180010fdd  movsxd  r14, dword ptr [r15+10h]
0x180010fe1  and     eax, 2
0x180010fe4  mov     r10, cs:WPP_GLOBAL_Control
0x180010feb  add     rax, rax
0x180010fee  mov     [rbp+57h+var_A0], 1Dh
0x180010ff5  xor     ebx, ebx
0x180010ff7  mov     rax, ds:(funcs_180001EF0 - 180000000h)[r9+rax*8]
0x180010fff  mov     [rbp+57h+var_C0], rax
0x180011003  cmp     ebx, edi
0x180011005  jnb     loc_1800110E5
0x18001100b  mov     rcx, r14
0x18001100e  lea     rdx, [rbp+57h+var_A0]
0x180011012  mov     eax, [rdx+rbx*4]
0x180011015  lea     rdx, [rdx+rbx*4]
0x180011019  shl     rcx, 4
0x18001101d  sub     eax, [rcx+r9+0BD00Ch]
0x180011025  mov     r8d, eax
0x180011028  lea     rax, [rax+rax*2]
0x18001102c  test    byte ptr [r15+rax*8+360h], 1
0x180011035  jnz     loc_1800110D4
0x18001103b  movsxd  rax, dword ptr [r15+10h]
0x18001103f  mov     esi, 0
0x180011044  add     rax, rax
0x180011047  shl     r8, 5
0x18001104b  test    byte ptr [r15+0C0h], 2
0x180011053  setnz   sil
0x180011057  mov     rdx, ds:rva ?SampObjectExtendedAttributesProperties@@3QBU_SAMP_OBJECT_EXTENDED_ATTRIBUTES@@B[r9+rax*8]; _SAMP_OBJECT_EXTENDED_ATTRIBUTES const near * const SampObjectExtendedAttributesProperties ...
0x18001105f  inc     esi
0x180011061  and     esi, [rdx+r8+4]
0x180011066  test    dword ptr [r10+44h], 20000h
0x18001106e  jz      short loc_18001109C
0x180011070  mov     rcx, [r10+38h]
0x180011074  lea     r8, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids
0x18001107b  xor     r9d, r9d
0x18001107e  mov     edx, 28h ; '('
0x180011083  test    esi, esi
0x180011085  setnz   r9b
0x180011089  call    WPP_SF_d
0x18001108e  mov     r10, cs:WPP_GLOBAL_Control
0x180011095  lea     r9, __ImageBase
0x18001109c  test    esi, esi
0x18001109e  jnz     short loc_1800110DE
0x1800110a0  test    dword ptr [r10+44h], 20000h
0x1800110a8  mov     ebx, 0C00002A3h
0x1800110ad  jz      loc_18001113A
0x1800110b3  mov     rcx, [r10+38h]
0x1800110b7  lea     r8, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids
0x1800110be  mov     edx, 52h ; 'R'
0x1800110c3  mov     [rsp+110h+var_F0], ebx
0x1800110c7  mov     r9d, 0C00002A3h
0x1800110cd  call    WPP_SF_Dd
0x1800110d2  jmp     short loc_180011133
0x1800110d4  dec     edi
0x1800110d6  dec     ebx
0x1800110d8  mov     eax, [rbp+rdi*4+57h+var_A0]
0x1800110dc  mov     [rdx], eax
0x1800110de  inc     ebx
0x1800110e0  jmp     loc_180011003
0x1800110e5  test    dword ptr [r10+44h], 20000h
0x1800110ed  jz      short loc_180011116
0x1800110ef  mov     rcx, [r10+38h]
0x1800110f3  lea     r8, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids
0x1800110fa  mov     edx, 53h ; 'S'
0x1800110ff  mov     [rsp+110h+var_F0], 0
0x180011107  xor     r9d, r9d
0x18001110a  call    WPP_SF_Dd
0x18001110f  mov     r10, cs:WPP_GLOBAL_Control
0x180011116  test    edi, edi
0x180011118  jnz     short loc_18001111E
0x18001111a  xor     ebx, ebx
0x18001111c  jmp     short loc_18001113A
0x18001111e  mov     rax, [rbp+57h+var_C0]
0x180011122  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x180011126  mov     r8d, edi; unsigned int
0x180011129  mov     rcx, r15; struct _SAMP_OBJECT *
0x18001112c  call    _guard_dispatch_icall$thunk$10345483385596137414; SampRegReadExtendedAttributes(_SAMP_OBJECT *,ulong *,ulong) ...
0x180011131  mov     ebx, eax
0x180011133  mov     r10, cs:WPP_GLOBAL_Control
0x18001113a  test    byte ptr [r10+44h], 20h
0x18001113f  jz      short loc_18001116E
0x180011141  cmp     byte ptr [r10+41h], 5
0x180011146  jb      short loc_18001116E
0x180011148  mov     rcx, [r10+38h]
0x18001114c  lea     r8, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids
0x180011153  mov     edx, 56h ; 'V'
0x180011158  mov     [rsp+110h+var_F0], ebx
0x18001115c  mov     r9d, 1
0x180011162  call    WPP_SF_Dd
0x180011167  mov     r10, cs:WPP_GLOBAL_Control
0x18001116e  test    dword ptr [r10+44h], 20000h
0x180011176  jz      short loc_18001119B
0x180011178  mov     rcx, [r10+38h]
0x18001117c  lea     r8, WPP_f17891e1a0d73dd9c1e570044cf3bb9e_Traceguids
0x180011183  mov     edx, 57h ; 'W'
0x180011188  mov     [rsp+110h+var_F0], ebx
0x18001118c  mov     r9d, ebx
0x18001118f  call    WPP_SF_Dd
0x180011194  mov     r10, cs:WPP_GLOBAL_Control
0x18001119b  test    ebx, ebx
0x18001119d  js      loc_1800112FD
0x1800111a3  movsxd  rdx, dword ptr [r15+10h]
0x1800111a7  lea     r8, __ImageBase
0x1800111ae  shl     rdx, 4
0x1800111b2  mov     eax, 1Dh
0x1800111b7  xor     sil, sil
0x1800111ba  sub     eax, [rdx+r8+0BD00Ch]
0x1800111c2  mov     r14, [rdx+r8+0BD000h]
0x1800111ca  mov     ecx, eax
0x1800111cc  add     rax, 24h ; '$'
0x1800111d0  shl     rcx, 5
0x1800111d4  add     r14, rcx
0x1800111d7  test    byte ptr [r15+14h], 20h
0x1800111dc  lea     rax, [rax+rax*2]
0x1800111e0  lea     rdi, [r15+rax*8]
0x1800111e4  jz      short loc_1800111FB
0x1800111e6  movzx   eax, byte ptr [rdi]
0x1800111e9  movzx   esi, al
0x1800111ec  shr     sil, 2
0x1800111f0  or      al, 4
0x1800111f2  mov     [rdi], al
0x1800111f4  mov     r10, cs:WPP_GLOBAL_Control
0x1800111fb  test    byte ptr [rdi], 4
0x1800111fe  jnz     short loc_180011220
0x180011200  test    dword ptr [r10+44h], 20000h
0x180011208  mov     ebx, 0C0000022h
0x18001120d  jz      short loc_180011271
0x18001120f  mov     edx, 41h ; 'A'
0x180011214  mov     [rsp+110h+var_F0], ebx
0x180011218  mov     r9d, 0C0000022h
0x18001121e  jmp     short loc_18001125A
0x180011220  movsxd  rax, dword ptr [r14]
0x180011223  lea     rcx, [rdi+8]
0x180011227  add     rax, rax
0x18001122a  lea     rdx, [rbp+57h+hMem]
0x18001122e  mov     rax, ds:rva qword_1800BD430[r8+rax*8]
  ... truncated ...
```
