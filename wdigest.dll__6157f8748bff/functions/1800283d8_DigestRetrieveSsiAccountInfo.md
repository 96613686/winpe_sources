# DigestRetrieveSsiAccountInfo

- ea: `0x1800283d8`
- end: `0x180028eee`
- name: `DigestRetrieveSsiAccountInfo`
- size: `2838`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002940c`

## callees

- `0x180003520`
- `0x1800061a0`
- `0x1800087f4`
- `0x18000cb00`
- `0x180011fec`
- `0x1800185b8`
- `0x180018b18`
- `0x1800283d8`
- `0x180033564`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180028413`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180028413`
- `ntdll!RtlLengthSid` at `0x180028990`
- `ntdll!RtlLengthSid` at `0x180028a80`
- `ntdll!RtlLengthSid` at `0x180028b11`
- `ntdll!RtlLengthSid` at `0x180028c1b`
- `ntdll!RtlLengthSid` at `0x180028990`
- `ntdll!RtlLengthSid` at `0x180028a80`
- `ntdll!RtlLengthSid` at `0x180028b11`
- `ntdll!RtlLengthSid` at `0x180028c1b`
- `ntdll!RtlCopySid` at `0x180028a91`
- `ntdll!RtlCopySid` at `0x180028b6d`
- `ntdll!RtlCopySid` at `0x180028c77`
- `ntdll!RtlCopySid` at `0x180028a91`
- `ntdll!RtlCopySid` at `0x180028b6d`
- `ntdll!RtlCopySid` at `0x180028c77`

## pseudocode

```c
__int64 __fastcall DigestRetrieveSsiAccountInfo(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  int v6; // eax
  NTSTATUS v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int v11; // eax
  PVOID *v12; // rcx
  __int64 v13; // r9
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  _QWORD *v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rdx
  __int16 *v26; // rsi
  __int64 v27; // rax
  unsigned __int16 v28; // si
  __m128 v29; // xmm0
  __int64 v30; // rdx
  __int64 v31; // rbx
  int v32; // r15d
  unsigned int v33; // r14d
  __int64 v34; // rcx
  __int64 v35; // rsi
  ULONG v36; // eax
  unsigned int *Memory; // rax
  unsigned int *v38; // rsi
  unsigned int v39; // r12d
  char *v40; // r14
  __int64 v41; // r15
  __int64 v42; // rax
  ULONG v43; // eax
  __int64 v44; // rbx
  __int64 v45; // rax
  ULONG v46; // ebx
  void *v47; // rax
  __int64 v48; // rdx
  ULONG v49; // ebx
  void *v50; // rax
  __int128 v52; // [rsp+40h] [rbp-18h] BYREF
  __int64 v54; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v55; // [rsp+B0h] [rbp+58h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp+60h] BYREF

  v3 = a1;
  v55 = 0;
  v54 = 0;
  SystemTimeAsFileTime = 0;
  v52 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
  UserCredentialsFree(a3);
  v6 = UnicodeStringDuplicate(a3, a2 + 472);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v9 = 143;
    goto LABEL_8;
  }
  v6 = UnicodeStringDuplicate(a3 + 16, a2 + 456);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v9 = 144;
    goto LABEL_8;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _SSI_ATTRIBUTE near **, __int64 *, __int64 *))(*(_QWORD *)(*(_QWORD *)(v3 + 624) + 24LL) + 48LL))(
          *(_QWORD *)(v3 + 632),
          0,
          l_ulRequestCount,
          &l_RequestAttr,
          &v55,
          &v54);
  if ( v11 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v11);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v13 = v55;
    v7 = -1073741595;
    v14 = HIDWORD(v55);
    if ( (_DWORD)v55 == 3 )
      v7 = HIDWORD(v55);
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    {
      v15 = 146;
LABEL_22:
      WPP_SF_dd(v12[2], v15, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v13, v14);
LABEL_60:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_61;
    }
    goto LABEL_61;
  }
  v13 = v55;
  if ( (_DWORD)v55 )
  {
    v14 = HIDWORD(v55);
    if ( (_DWORD)v55 != 3 )
    {
      v7 = -1073741595;
      goto LABEL_28;
    }
    if ( HIDWORD(v55) )
    {
      v7 = HIDWORD(v55);
LABEL_28:
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 147;
        goto LABEL_22;
      }
LABEL_61:
      if ( v7 >= 0 )
        goto LABEL_180;
      goto LABEL_177;
    }
  }
  if ( *(_DWORD *)v54 != 9 )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 148;
    goto LABEL_176;
  }
  v17 = *(_DWORD **)(v54 + 8);
  if ( v17[6] )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 151;
    goto LABEL_176;
  }
  v18 = *(_QWORD **)(v54 + 16);
  v19 = v18[15];
  if ( *(_DWORD *)v19 != 4 )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 150;
    goto LABEL_176;
  }
  if ( **(_DWORD **)(v19 + 8) == 1 )
  {
    v7 = -1073741710;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 149;
    goto LABEL_176;
  }
  if ( v17[12] )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 154;
    goto LABEL_176;
  }
  v20 = v18[27];
  if ( *(_DWORD *)v20 != 4 )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 153;
    goto LABEL_176;
  }
  if ( **(_DWORD **)(v20 + 8) == 1 )
  {
    v7 = -1073741260;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 152;
    goto LABEL_176;
  }
  if ( v17[8] )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 157;
    goto LABEL_176;
  }
  v21 = v18[19];
  if ( *(_DWORD *)v21 != 8 )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 156;
    goto LABEL_176;
  }
  v22 = **(_QWORD **)(v21 + 8);
  if ( v22 && v22 < *(_QWORD *)&SystemTimeAsFileTime )
  {
    v7 = -1073741421;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 155;
    goto LABEL_176;
  }
  if ( v17[10] )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 160;
    goto LABEL_176;
  }
  v23 = v18[23];
  if ( *(_DWORD *)v23 != 8 )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 159;
    goto LABEL_176;
  }
  v24 = *(_QWORD **)(v23 + 8);
  if ( *v24 < *(__int64 *)&SystemTimeAsFileTime )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v7 = *v24 != 0 ? -1073741711 : -1073741276;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        158,
        &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids,
        (unsigned int)v7);
      goto LABEL_60;
    }
    goto LABEL_61;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
  v25 = v54;
  *(_QWORD *)(a3 + 32) = 0;
  if ( !**(_DWORD **)(v25 + 8) )
  {
    v26 = *(__int16 **)(*(_QWORD *)(v25 + 16) + 24LL);
    if ( (unsigned int)(*(_DWORD *)v26 - 16) > 0xFFEE )
    {
      v7 = -1073741595;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_177;
      v16 = 163;
      goto LABEL_176;
    }
    v27 = *((_QWORD *)v26 + 1);
    v28 = *v26;
    WORD1(v52) = v28;
    LOWORD(v52) = v28;
    *((_QWORD *)&v52 + 1) = v27;
    v6 = StringDuplicate(a3 + 128, &v52);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_177;
      v9 = 162;
      goto LABEL_8;
    }
    *(_WORD *)(a3 + 144) = (v28 >> 4) - 1;
    v29 = _mm_movelh_ps((__m128)0x1000100010001uLL, (__m128)0x1000100010001uLL);
    *(__m128 *)(a3 + 46) = v29;
    *(__m128 *)(a3 + 62) = v29;
    *(__m128 *)(a3 + 78) = v29;
    *(__m128 *)(a3 + 90) = v29;
    *(_DWORD *)(a3 + 36) = 1;
    goto LABEL_79;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
LABEL_79:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(*(_QWORD *)(v54 + 8) + 8LL) )
  {
    if ( *(_DWORD *)(a3 + 36) )
      goto LABEL_89;
    v7 = -1073741718;
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 168;
LABEL_176:
    WPP_SF_(v8[2], v16, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
    goto LABEL_177;
  }
  v30 = *(_QWORD *)(*(_QWORD *)(v54 + 16) + 56LL);
  if ( (unsigned int)(*(_DWORD *)v30 - 1) > 0xFFFD )
  {
    v7 = -1073741595;
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 167;
    goto LABEL_176;
  }
  v6 = UnicodeStringByteDuplicate(a3 + 112, *(_QWORD *)(v30 + 8));
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v9 = 165;
LABEL_8:
    v10 = (unsigned int)v6;
LABEL_126:
    WPP_SF_d(v8[2], v9, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v10);
LABEL_177:
    UserCredentialsFree(a3);
    goto LABEL_178;
  }
  *(_DWORD *)(a3 + 32) = 1;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_89:
  if ( *(_DWORD *)(*(_QWORD *)(v54 + 8) + 16LL) )
  {
    v7 = -1073741595;
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 172;
    goto LABEL_176;
  }
  v31 = *(unsigned int *)(*(_QWORD *)(v54 + 16) + 80LL);
  if ( (_DWORD)v31 )
  {
    v32 = 24;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      WPP_SF_d(v8[2], 169, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, (unsigned int)v31);
    v33 = 0;
    v34 = *(_QWORD *)(v54 + 16);
    v35 = *(_QWORD *)(v34 + 88);
    if ( *(_DWORD *)(v34 + 80) )
    {
      do
      {
        v36 = RtlLengthSid(*(PSID *)(v35 + 8));
        ++v33;
        v35 += 16;
        v32 += v36;
      }
      while ( v33 < *(_DWORD *)(*(_QWORD *)(v54 + 16) + 80LL) );
    }
    Memory = (unsigned int *)DigestAllocateMemory((unsigned int)(v32 + 16 * (v31 - 1)));
    v38 = Memory;
    if ( !Memory )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
      v7 = -2146893056;
      goto LABEL_177;
    }
    *Memory = v31;
    v39 = 0;
    v40 = (char *)&Memory[4 * v31 + 2];
    v41 = *(_QWORD *)(*(_QWORD *)(v54 + 16) + 88LL);
    do
    {
      v42 = 2LL * v39;
      v38[2 * v42 + 4] = 7;
      *(_QWORD *)&v38[2 * v42 + 2] = v40;
      v43 = RtlLengthSid(*(PSID *)(v41 + 8));
      v44 = v43;
      RtlCopySid(v43, v40, *(PSID *)(v41 + 8));
      v40 += v44;
      v41 += 16;
      ++v39;
    }
    while ( v39 < *v38 );
    *(_QWORD *)(a3 + 152) = v38;
    goto LABEL_114;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
  {
    WPP_SF_(v8[2], 171, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
LABEL_114:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(*(_QWORD *)(v54 + 8) + 56LL) )
  {
    v7 = -1073741595;
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 176;
    goto LABEL_176;
  }
  v45 = *(_QWORD *)(v54 + 16);
  if ( !*(_DWORD *)(v45 + 240) )
  {
    v7 = -1073741595;
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_177;
    v9 = 175;
LABEL_125:
    v10 = 3221225701LL;
    goto LABEL_126;
  }
  v46 = RtlLengthSid(*(PSID *)(*(_QWORD *)(v45 + 248) + 8LL));
  v47 = (void *)DigestAllocateMemory(v46);
  *(_QWORD *)(a3 + 160) = v47;
  if ( !v47 )
  {
    v7 = -2146893056;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v16 = 173;
    goto LABEL_176;
  }
  v7 = RtlCopySid(v46, v47, *(PSID *)(*(_QWORD *)(*(_QWORD *)(v54 + 16) + 248LL) + 8LL));
  if ( v7 < 0 )
  {
    v7 = -1073741595;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_177;
    v9 = 174;
    goto LABEL_125;
  }
  if ( *(_DWORD *)(*(_QWORD *)(v54 + 8) + 64LL) )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_179;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
  }
  else
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        177,
        &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids,
        *(unsigned int *)(*(_QWORD *)(v54 + 16) + 272LL));
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    v48 = *(_QWORD *)(v54 + 16);
    if ( !*(_DWORD *)(v48 + 272) )
      goto LABEL_179;
    v49 = RtlLengthSid(*(PSID *)(*(_QWORD *)(v48 + 280) + 8LL));
    v50 = (void *)DigestAllocateMemory(v49);
    *(_QWORD *)(a3 + 168) = v50;
    if ( !v50 )
    {
      v7 = -2146893056;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_177;
      v16 = 178;
      goto LABEL_176;
    }
    v7 = RtlCopySid(v49, v50, *(PSID *)(*(_QWORD *)(*(_QWORD *)(v54 + 16) + 280LL) + 8LL));
    if ( v7 < 0 )
    {
      v7 = -1073741595;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_177;
      v9 = 179;
      goto LABEL_125;
    }
  }
LABEL_178:
  v12 = (PVOID *)WPP_GLOBAL_Control;
LABEL_179:
  v3 = a1;
LABEL_180:
  if ( v54 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(*(_QWORD *)(v3 + 624) + 24LL) + 80LL))(*(_QWORD *)(v3 + 632));
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v54 = 0;
  }
  if ( v12 != &WPP_GLOBAL_Control && *((char *)v12 + 28) < 0 )
    WPP_SF_d(v12[2], 181, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800283d8  mov     [rsp-40h+arg_0], rcx
0x1800283dd  push    rbp
0x1800283de  push    rbx
0x1800283df  push    rsi
0x1800283e0  push    rdi
0x1800283e1  push    r12
0x1800283e3  push    r13
0x1800283e5  push    r14
0x1800283e7  push    r15
0x1800283e9  mov     rbp, rsp
0x1800283ec  sub     rsp, 58h
0x1800283f0  xor     r15d, r15d
0x1800283f3  mov     rsi, rcx
0x1800283f6  xorps   xmm0, xmm0
0x1800283f9  mov     [rbp+arg_10], r15
0x1800283fd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180028401  mov     [rbp+arg_8], r15
0x180028405  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r15
0x180028409  mov     r13, r8
0x18002840c  movups  [rbp+var_18], xmm0
0x180028410  mov     rdi, rdx
0x180028413  call    cs:__imp_GetSystemTimeAsFileTime
0x180028419  mov     rcx, cs:WPP_GLOBAL_Control
0x180028420  lea     r12, WPP_GLOBAL_Control
0x180028427  lea     r14, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002842e  cmp     rcx, r12
0x180028431  jz      short loc_18002844A
0x180028433  test    byte ptr [rcx+1Ch], 80h
0x180028437  jz      short loc_18002844A
0x180028439  mov     rcx, [rcx+10h]
0x18002843d  mov     edx, 8Eh
0x180028442  mov     r8, r14
0x180028445  call    WPP_SF_
0x18002844a  mov     rcx, r13
0x18002844d  call    UserCredentialsFree
0x180028452  lea     rdx, [rdi+1D8h]
0x180028459  mov     rcx, r13
0x18002845c  call    UnicodeStringDuplicate
0x180028461  mov     ebx, eax
0x180028463  test    eax, eax
0x180028465  jns     short loc_180028493
0x180028467  mov     rcx, cs:WPP_GLOBAL_Control
0x18002846e  cmp     rcx, r12
0x180028471  jz      loc_180028E76
0x180028477  mov     edi, 1
0x18002847c  test    [rcx+1Ch], dil
0x180028480  jz      loc_180028E76
0x180028486  mov     edx, 8Fh
0x18002848b  mov     r9d, eax
0x18002848e  jmp     loc_180028BA3
0x180028493  lea     rdx, [rdi+1C8h]
0x18002849a  lea     rcx, [r13+10h]
0x18002849e  call    UnicodeStringDuplicate
0x1800284a3  mov     ebx, eax
0x1800284a5  test    eax, eax
0x1800284a7  jns     short loc_1800284CF
0x1800284a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284b0  cmp     rcx, r12
0x1800284b3  jz      loc_180028E76
0x1800284b9  mov     edi, 1
0x1800284be  test    [rcx+1Ch], dil
0x1800284c2  jz      loc_180028E76
0x1800284c8  mov     edx, 90h
0x1800284cd  jmp     short loc_18002848B
0x1800284cf  mov     rax, [rsi+270h]
0x1800284d6  lea     r9, ?l_RequestAttr@@3PAU_SSI_ATTRIBUTE@@A; _SSI_ATTRIBUTE near * l_RequestAttr
0x1800284dd  mov     r8d, cs:?l_ulRequestCount@@3KA; ulong l_ulRequestCount
0x1800284e4  xor     edx, edx
0x1800284e6  mov     rcx, [rax+18h]
0x1800284ea  mov     rax, [rcx+30h]
0x1800284ee  lea     rcx, [rbp+arg_8]
0x1800284f2  mov     [rsp+58h+var_30], rcx
0x1800284f7  lea     rcx, [rbp+arg_10]
0x1800284fb  mov     [rsp+58h+var_38], rcx
0x180028500  mov     rcx, [rsi+278h]
0x180028507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002850c  test    eax, eax
0x18002850e  jz      short loc_180028582
0x180028510  mov     rcx, cs:WPP_GLOBAL_Control
0x180028517  mov     edi, 1
0x18002851c  cmp     rcx, r12
0x18002851f  jz      short loc_180028542
0x180028521  test    [rcx+1Ch], dil
0x180028525  jz      short loc_180028542
0x180028527  mov     rcx, [rcx+10h]
0x18002852b  mov     edx, 91h
0x180028530  mov     r9d, eax
0x180028533  mov     r8, r14
0x180028536  call    WPP_SF_d
0x18002853b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028542  mov     r9, [rbp+arg_10]
0x180028546  mov     ebx, 0C00000E5h
0x18002854b  mov     eax, dword ptr [rbp+arg_10+4]
0x18002854e  cmp     r9d, 3
0x180028552  cmovz   ebx, eax
0x180028555  cmp     rcx, r12
0x180028558  jz      loc_18002875C
0x18002855e  test    [rcx+1Ch], dil
0x180028562  jz      loc_18002875C
0x180028568  mov     edx, 92h
0x18002856d  mov     rcx, [rcx+10h]
0x180028571  mov     r8, r14
0x180028574  mov     dword ptr [rsp+58h+var_38], eax
0x180028578  call    WPP_SF_dd
0x18002857d  jmp     loc_180028755
0x180028582  mov     r9, [rbp+arg_10]
0x180028586  test    r9d, r9d
0x180028589  jz      short loc_1800285C7
0x18002858b  mov     eax, dword ptr [rbp+arg_10+4]
0x18002858e  cmp     r9d, 3
0x180028592  jnz     short loc_18002859C
0x180028594  test    eax, eax
0x180028596  jz      short loc_1800285C7
0x180028598  mov     ebx, eax
0x18002859a  jmp     short loc_1800285A1
0x18002859c  mov     ebx, 0C00000E5h
0x1800285a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285a8  cmp     rcx, r12
0x1800285ab  jz      loc_18002875C
0x1800285b1  mov     edi, 1
0x1800285b6  test    [rcx+1Ch], dil
0x1800285ba  jz      loc_18002875C
0x1800285c0  mov     edx, 93h
0x1800285c5  jmp     short loc_18002856D
0x1800285c7  mov     rax, [rbp+arg_8]
0x1800285cb  cmp     dword ptr [rax], 9
0x1800285ce  jz      short loc_1800285FE
0x1800285d0  mov     ebx, 0C00000E5h
0x1800285d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285dc  cmp     rcx, r12
0x1800285df  jz      loc_180028E76
0x1800285e5  mov     edi, 1
0x1800285ea  test    [rcx+1Ch], dil
0x1800285ee  jz      loc_180028E76
0x1800285f4  mov     edx, 94h
0x1800285f9  jmp     loc_180028E6A
0x1800285fe  mov     rdx, [rbp+arg_8]
0x180028602  mov     rcx, [rdx+8]
0x180028606  cmp     [rcx+18h], r15d
0x18002860a  jnz     loc_180028E49
0x180028610  mov     r8, [rdx+10h]
0x180028614  mov     rax, [r8+78h]
0x180028618  cmp     dword ptr [rax], 4
0x18002861b  jnz     loc_180028E26
0x180028621  mov     rax, [rax+8]
0x180028625  mov     edi, 1
0x18002862a  cmp     [rax], edi
0x18002862c  jnz     short loc_180028657
0x18002862e  mov     ebx, 0C0000072h
0x180028633  mov     rcx, cs:WPP_GLOBAL_Control
0x18002863a  cmp     rcx, r12
0x18002863d  jz      loc_180028E76
0x180028643  test    [rcx+1Ch], dil
0x180028647  jz      loc_180028E76
0x18002864d  mov     edx, 95h
0x180028652  jmp     loc_180028E6A
0x180028657  cmp     [rcx+30h], r15d
0x18002865b  jnz     loc_180028E08
0x180028661  mov     rax, [r8+0D8h]
0x180028668  cmp     dword ptr [rax], 4
0x18002866b  jnz     loc_180028DEA
0x180028671  mov     rax, [rax+8]
0x180028675  cmp     [rax], edi
0x180028677  jnz     short loc_1800286A2
0x180028679  mov     ebx, 0C0000234h
0x18002867e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028685  cmp     rcx, r12
0x180028688  jz      loc_180028E76
0x18002868e  test    [rcx+1Ch], dil
0x180028692  jz      loc_180028E76
0x180028698  mov     edx, 98h
0x18002869d  jmp     loc_180028E6A
0x1800286a2  cmp     [rcx+20h], r15d
0x1800286a6  jnz     loc_180028DC1
0x1800286ac  mov     rax, [r8+98h]
0x1800286b3  cmp     dword ptr [rax], 8
0x1800286b6  jnz     loc_180028D98
0x1800286bc  mov     rax, [rax+8]
0x1800286c0  mov     rdx, [rax]
0x1800286c3  test    rdx, rdx
0x1800286c6  jz      short loc_1800286F7
0x1800286c8  cmp     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800286cc  jge     short loc_1800286F7
0x1800286ce  mov     ebx, 0C0000193h
0x1800286d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286da  cmp     rcx, r12
0x1800286dd  jz      loc_180028E76
0x1800286e3  test    [rcx+1Ch], dil
0x1800286e7  jz      loc_180028E76
0x1800286ed  mov     edx, 9Bh
0x1800286f2  jmp     loc_180028E6A
0x1800286f7  cmp     [rcx+28h], r15d
0x1800286fb  jnz     loc_180028D6F
0x180028701  mov     rax, [r8+0B8h]
0x180028708  cmp     dword ptr [rax], 8
0x18002870b  jnz     loc_180028D46
0x180028711  mov     rax, [rax+8]
0x180028715  mov     rcx, [rax]
0x180028718  cmp     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002871c  jge     short loc_180028769
0x18002871e  neg     rcx
0x180028721  mov     rcx, cs:WPP_GLOBAL_Control
0x180028728  sbb     ebx, ebx
0x18002872a  and     ebx, 0FFFFFE4Dh
0x180028730  add     ebx, 0C0000224h
0x180028736  cmp     rcx, r12
0x180028739  jz      short loc_18002875C
0x18002873b  test    [rcx+1Ch], dil
0x18002873f  jz      short loc_18002875C
0x180028741  mov     rcx, [rcx+10h]
0x180028745  mov     edx, 9Eh
0x18002874a  mov     r9d, ebx
0x18002874d  mov     r8, r14
0x180028750  call    WPP_SF_d
0x180028755  mov     rcx, cs:WPP_GLOBAL_Control
0x18002875c  test    ebx, ebx
0x18002875e  jns     loc_180028E89
0x180028764  jmp     loc_180028E76
0x180028769  mov     rcx, cs:WPP_GLOBAL_Control
0x180028770  cmp     rcx, r12
0x180028773  jz      short loc_18002878C
0x180028775  test    byte ptr [rcx+1Ch], 4
0x180028779  jz      short loc_18002878C
0x18002877b  mov     rcx, [rcx+10h]
0x18002877f  mov     edx, 0A1h
0x180028784  mov     r8, r14
0x180028787  call    WPP_SF_
0x18002878c  mov     rdx, [rbp+arg_8]
0x180028790  mov     [r13+20h], r15
0x180028794  mov     rax, [rdx+8]
0x180028798  cmp     [rax], r15d
0x18002879b  jnz     loc_180028876
0x1800287a1  mov     rax, [rdx+10h]
0x1800287a5  mov     rsi, [rax+18h]
0x1800287a9  mov     eax, [rsi]
0x1800287ab  sub     eax, 10h
0x1800287ae  cmp     eax, 0FFEEh
0x1800287b3  ja      loc_18002884D
0x1800287b9  mov     rax, [rsi+8]
0x1800287bd  lea     rcx, [r13+80h]
0x1800287c4  movzx   esi, word ptr [rsi]
0x1800287c7  lea     rdx, [rbp+var_18]
0x1800287cb  mov     word ptr [rbp+var_18+2], si
0x1800287cf  mov     word ptr [rbp+var_18], si
0x1800287d3  mov     qword ptr [rbp+var_18+8], rax
0x1800287d7  call    StringDuplicate
0x1800287dc  mov     ebx, eax
0x1800287de  test    eax, eax
0x1800287e0  jns     short loc_180028806
0x1800287e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287e9  cmp     rcx, r12
0x1800287ec  jz      loc_180028E76
0x1800287f2  test    [rcx+1Ch], dil
0x1800287f6  jz      loc_180028E76
0x1800287fc  mov     edx, 0A2h
0x180028801  jmp     loc_18002848B
0x180028806  movzx   ecx, di
0x180028809  mov     eax, ecx
0x18002880b  shr     si, 4
0x18002880f  shl     rcx, 10h
0x180028813  sub     si, di
0x180028816  mov     [r13+90h], si
0x18002881e  or      rcx, rax
0x180028821  mov     rax, rcx
0x180028824  shl     rcx, 20h
0x180028828  or      rcx, rax
0x18002882b  movq    xmm0, rcx
0x180028830  movlhps xmm0, xmm0
0x180028833  movups  xmmword ptr [r13+2Eh], xmm0
0x180028838  movups  xmmword ptr [r13+3Eh], xmm0
0x18002883d  movups  xmmword ptr [r13+4Eh], xmm0
0x180028842  movups  xmmword ptr [r13+5Ah], xmm0
0x180028847  mov     [r13+24h], edi
0x18002884b  jmp     short loc_180028899
0x18002884d  mov     ebx, 0C00000E5h
0x180028852  mov     rcx, cs:WPP_GLOBAL_Control
0x180028859  cmp     rcx, r12
0x18002885c  jz      loc_180028E76
0x180028862  test    [rcx+1Ch], dil
0x180028866  jz      loc_180028E76
0x18002886c  mov     edx, 0A3h
0x180028871  jmp     loc_180028E6A
0x180028876  mov     rcx, cs:WPP_GLOBAL_Control
0x18002887d  cmp     rcx, r12
0x180028880  jz      short loc_1800288A0
0x180028882  test    byte ptr [rcx+1Ch], 2
0x180028886  jz      short loc_1800288A0
0x180028888  mov     rcx, [rcx+10h]
0x18002888c  mov     edx, 0A4h
0x180028891  mov     r8, r14
0x180028894  call    WPP_SF_
0x180028899  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288a0  mov     rdx, [rbp+arg_8]
0x1800288a4  mov     rax, [rdx+8]
0x1800288a8  cmp     [rax+8], r15d
0x1800288ac  jnz     loc_180028A1A
0x1800288b2  mov     rax, [rdx+10h]
0x1800288b6  mov     rdx, [rax+38h]
0x1800288ba  mov     r8d, [rdx]
0x1800288bd  lea     eax, [r8-1]
  ... truncated ...
```
