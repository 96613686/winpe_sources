# SpAcceptCredentials

- ea: `0x180009f00`
- end: `0x18000ab5b`
- name: `SpAcceptCredentials`
- size: `3163`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting`

## callees

- `0x180009f00`
- `0x18000ab70`
- `0x18000ad50`
- `0x18000bc00`
- `0x180011fec`
- `0x180013304`
- `0x1800185b8`
- `0x18001874c`
- `0x1800187bc`
- `0x180018b18`
- `0x1800192a8`
- `0x18001a2dc`
- `0x180032ec8`
- `0x1800377bc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a5fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a6d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a728`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a777`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a7c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a5fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a6d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a728`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a777`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a7c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5e7`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x180009fc9`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x180009fc9`

## pseudocode

```c
__int64 __fastcall SpAcceptCredentials(unsigned int a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  unsigned int v8; // esi
  _OWORD *v9; // rbx
  __int64 v10; // rdx
  PVOID *v11; // rcx
  _OWORD *v12; // rax
  _WORD *v13; // rdi
  int v14; // eax
  unsigned int v15; // ebp
  void *v16; // rax
  void *v17; // rsi
  _WORD *v18; // rdi
  int v19; // eax
  unsigned int v20; // ebp
  void *v21; // rax
  void *v22; // rsi
  _WORD *v23; // rdi
  int v24; // eax
  unsigned int v25; // ebp
  void *v26; // rax
  void *v27; // rsi
  _WORD *v28; // rdi
  int v29; // ebp
  int v30; // eax
  unsigned int v31; // ebp
  void *v32; // rax
  void *v33; // rsi
  _BYTE *v34; // xmm6_8
  __int64 v35; // rdx
  _BYTE *v36; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r9
  HLOCAL v41; // rax
  HLOCAL v42; // rax
  HLOCAL v43; // rax
  HLOCAL v44; // rax
  __int64 v45; // [rsp+30h] [rbp-78h] BYREF
  const WCHAR *v46; // [rsp+38h] [rbp-70h]
  __int128 v47; // [rsp+40h] [rbp-68h]
  int v48; // [rsp+B8h] [rbp+10h] BYREF

  v45 = 1048590;
  v47 = 0;
  v48 = 0;
  v46 = L"WDigest";
  v8 = 0;
  v9 = 0;
  v10 = 14;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      v10 = 14;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
    {
      WPP_SF_d(v11[2], 11, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids, a1);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      v10 = 14;
    }
  }
  if ( a2 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
    {
      WPP_SF_Z(v11[2], 12, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids, a2);
LABEL_126:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      v10 = 14;
    }
  }
  else if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
  {
    WPP_SF_(v11[2], 13, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids);
    goto LABEL_126;
  }
  if ( !a3 )
  {
    if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 4) == 0 )
      goto LABEL_73;
    WPP_SF_(v11[2], 20, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids);
LABEL_175:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_73;
  }
  if ( v11 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
    {
      WPP_SF_ZZ(v11[2], 14, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids, a3 + 6, a3 + 2);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
      {
        WPP_SF_ZZ(v11[2], 15, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids, a3 + 26, a3 + 22);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
        WPP_SF_DLD(v11[2], v10, a3, (unsigned int)a3[1], *a3, a3[20], v45, v46, v47, *((_QWORD *)&v47 + 1));
    }
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDigestSSO>::__private_IsEnabledPreCheck(
    `wil::Feature<__WilFeatureTraits_Feature_DisableDigestSSO>::GetImpl'::`2'::impl,
    v10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids);
  LsaIEventWritePackageNotCacheLogonUser(&v45, a3 + 2, a3 + 6, 1);
  if ( a4 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids,
        *(unsigned int *)(a4 + 16));
      goto LABEL_105;
    }
  }
  else
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids);
LABEL_105:
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( (a3[20] & 4) != 0 )
    goto LABEL_73;
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
    WPP_SF_(v11[2], 27, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids);
  if ( g_NtDigestState != 1 )
  {
    v12 = LocalAlloc(0x40u, 0x80u);
    v9 = v12;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_19;
    v38 = 29;
LABEL_115:
    WPP_SF_Lq(v11[2], v38, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, 128, v12);
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  v12 = (_OWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)&g_LsaFunctions + 40LL))(128);
  v9 = v12;
  if ( v12 )
  {
    *v12 = 0;
    v12[1] = 0;
    v12[2] = 0;
    v12[3] = 0;
    v12[4] = 0;
    v12[5] = 0;
    v12[6] = 0;
    v12[7] = 0;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v38 = 28;
    goto LABEL_115;
  }
LABEL_19:
  if ( !v9 )
  {
    v8 = -2146893056;
    if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
      goto LABEL_73;
    v39 = 28;
    v40 = 2148074240LL;
    goto LABEL_146;
  }
  *v9 = 0;
  v9[1] = 0;
  v9[2] = 0;
  v9[3] = 0;
  v9[4] = 0;
  v9[5] = 0;
  v9[6] = 0;
  v9[7] = 0;
  *((_QWORD *)v9 + 3) = v9;
  *((_DWORD *)v9 + 4) = 1;
  *((_DWORD *)v9 + 11) = a1;
  *((_QWORD *)v9 + 4) = *(_QWORD *)a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids,
      (unsigned int)a3[1],
      *a3);
  v13 = a3 + 2;
  *((_QWORD *)v9 + 7) = 0;
  *((_DWORD *)v9 + 12) = 0;
  if ( a3 != (_DWORD *)-8LL && *((_QWORD *)a3 + 2) )
  {
    v14 = (unsigned __int16)*v13;
    if ( (unsigned __int16)v14 > 0xFFFDu )
    {
      v8 = -1073741811;
    }
    else
    {
      v15 = v14 + 2;
      if ( g_NtDigestState == 1 )
      {
        v16 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)&g_LsaFunctions + 40LL))(v15);
        v17 = v16;
        if ( v16 )
          memset_0(v16, 0, v15);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v15, v17);
      }
      else
      {
        v41 = LocalAlloc(0x40u, v15);
        v17 = v41;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v15, v41);
      }
      *((_QWORD *)v9 + 7) = v17;
      if ( v17 )
      {
        *((_WORD *)v9 + 24) = *v13;
        *((_WORD *)v9 + 25) = *v13 + 2;
        memcpy_0(v17, *((const void **)a3 + 2), (unsigned __int16)*v13);
        *(_WORD *)(*((_QWORD *)v9 + 7) + 2 * ((unsigned __int64)(unsigned __int16)*v13 >> 1)) = 0;
        goto LABEL_34;
      }
      v8 = -2146893056;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_73;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_118:
        if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
          goto LABEL_73;
        v39 = 30;
        v40 = v8;
        goto LABEL_146;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_118;
  }
LABEL_34:
  v18 = a3 + 6;
  *((_QWORD *)v9 + 9) = 0;
  *((_DWORD *)v9 + 16) = 0;
  if ( a3 != (_DWORD *)-24LL && *((_QWORD *)a3 + 4) )
  {
    v19 = (unsigned __int16)*v18;
    if ( (unsigned __int16)v19 > 0xFFFDu )
    {
      v8 = -1073741811;
    }
    else
    {
      v20 = v19 + 2;
      if ( g_NtDigestState == 1 )
      {
        v21 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)&g_LsaFunctions + 40LL))(v20);
        v22 = v21;
        if ( v21 )
          memset_0(v21, 0, v20);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v20, v22);
      }
      else
      {
        v42 = LocalAlloc(0x40u, v20);
        v22 = v42;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v20, v42);
      }
      *((_QWORD *)v9 + 9) = v22;
      if ( v22 )
      {
        *((_WORD *)v9 + 32) = *v18;
        *((_WORD *)v9 + 33) = *v18 + 2;
        memcpy_0(v22, *((const void **)a3 + 4), (unsigned __int16)*v18);
        *(_WORD *)(*((_QWORD *)v9 + 9) + 2 * ((unsigned __int64)(unsigned __int16)*v18 >> 1)) = 0;
        goto LABEL_45;
      }
      v8 = -2146893056;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_73;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_155:
        if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
          goto LABEL_73;
        v39 = 31;
        v40 = v8;
        goto LABEL_146;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_155;
  }
LABEL_45:
  v23 = a3 + 22;
  *((_QWORD *)v9 + 13) = 0;
  *((_DWORD *)v9 + 24) = 0;
  if ( a3 != (_DWORD *)-88LL && *((_QWORD *)a3 + 12) )
  {
    v24 = (unsigned __int16)*v23;
    if ( (unsigned __int16)v24 > 0xFFFDu )
    {
      v8 = -1073741811;
    }
    else
    {
      v25 = v24 + 2;
      if ( g_NtDigestState == 1 )
      {
        v26 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)&g_LsaFunctions + 40LL))(v25);
        v27 = v26;
        if ( v26 )
          memset_0(v26, 0, v25);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v25, v27);
      }
      else
      {
        v43 = LocalAlloc(0x40u, v25);
        v27 = v43;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v25, v43);
      }
      *((_QWORD *)v9 + 13) = v27;
      if ( v27 )
      {
        *((_WORD *)v9 + 48) = *v23;
        *((_WORD *)v9 + 49) = *v23 + 2;
        memcpy_0(v27, *((const void **)a3 + 12), (unsigned __int16)*v23);
        *(_WORD *)(*((_QWORD *)v9 + 13) + 2 * ((unsigned __int64)(unsigned __int16)*v23 >> 1)) = 0;
        goto LABEL_56;
      }
      v8 = -2146893056;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_73;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_163:
        if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
          goto LABEL_73;
        v39 = 32;
        v40 = v8;
        goto LABEL_146;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_163;
  }
LABEL_56:
  v28 = a3 + 26;
  *((_QWORD *)v9 + 15) = 0;
  *((_DWORD *)v9 + 28) = 0;
  v29 = 0;
  if ( a3 == (_DWORD *)-104LL || !*((_QWORD *)a3 + 14) )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v30 = (unsigned __int16)*v28;
    if ( (unsigned __int16)v30 > 0xFFFDu )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      v8 = -1073741811;
      v29 = -1073741811;
      goto LABEL_170;
    }
    v31 = v30 + 2;
    if ( g_NtDigestState == 1 )
    {
      v32 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)&g_LsaFunctions + 40LL))(v31);
      v33 = v32;
      if ( v32 )
        memset_0(v32, 0, v31);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v31, v33);
    }
    else
    {
      v44 = LocalAlloc(0x40u, v31);
      v33 = v44;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_Lq(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v31, v44);
    }
    *((_QWORD *)v9 + 15) = v33;
    if ( v33 )
    {
      *((_WORD *)v9 + 56) = *v28;
      *((_WORD *)v9 + 57) = *v28 + 2;
      memcpy_0(v33, *((const void **)a3 + 14), (unsigned __int16)*v28);
      v8 = 0;
      *(_WORD *)(*((_QWORD *)v9 + 15) + 2 * ((unsigned __int64)(unsigned __int16)*v28 >> 1)) = 0;
      goto LABEL_67;
    }
    v8 = -2146893056;
    v29 = -2146893056;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_170;
    }
  }
  v8 = v29;
  if ( v29 < 0 )
  {
LABEL_170:
    if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
      goto LABEL_73;
    v39 = 33;
    v40 = (unsigned int)v29;
LABEL_146:
    WPP_SF_d(v11[2], v39, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids, v40);
    goto LABEL_175;
  }
LABEL_67:
  *((_DWORD *)v9 + 10) = a3[20];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids);
  LogSessHandlerNoPasswordInsert(v9, &v48);
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( v48 == 1 )
    v9 = 0;
LABEL_73:
  v34 = (_BYTE *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v34 )
  {
    if ( WORD1(v47) )
    {
      v35 = WORD1(v47);
      v36 = v34;
      do
      {
        *v36++ = 0;
        --v35;
      }
      while ( v35 );
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( g_NtDigestState == 1 )
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x100) != 0 )
        WPP_SF_q(v11[2], 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v34);
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)&g_LsaFunctions + 48LL))(v34);
    }
    else
    {
      if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x100) != 0 )
        WPP_SF_q(v11[2], 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v34);
      LocalFree(v34);
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    LogonSessionFree(v9);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && *((char *)v11 + 28) < 0 )
    WPP_SF_d(v11[2], 39, &WPP_cb7bfd1b4d253ebba43e86b9224572dc_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180009f00  mov     rax, rsp
0x180009f03  push    rbx
0x180009f04  push    rbp
0x180009f05  push    rsi
0x180009f06  push    rdi
0x180009f07  push    r12
0x180009f09  push    r13
0x180009f0b  push    r14
0x180009f0d  push    r15
0x180009f0f  sub     rsp, 68h
0x180009f13  xor     r13d, r13d
0x180009f16  movaps  xmmword ptr [rax-58h], xmm6
0x180009f1a  mov     qword ptr [rax-78h], 10000Eh
0x180009f22  xorps   xmm6, xmm6
0x180009f25  movups  xmmword ptr [rax-68h], xmm6
0x180009f29  mov     [rax+10h], r13d
0x180009f2d  mov     rdi, rdx
0x180009f30  lea     rax, aWdigest; "WDigest"
0x180009f37  mov     rbp, r9
0x180009f3a  mov     [rsp+0A8h+var_70], rax
0x180009f3f  mov     r14, r8
0x180009f42  mov     r15d, ecx
0x180009f45  mov     esi, r13d
0x180009f48  mov     ebx, r13d
0x180009f4b  mov     edx, 0Eh
0x180009f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f57  lea     r12, WPP_GLOBAL_Control
0x180009f5e  cmp     rcx, r12
0x180009f61  jz      short loc_180009F76
0x180009f63  test    byte ptr [rcx+1Ch], 80h
0x180009f67  jnz     loc_18000A824
0x180009f6d  cmp     rcx, r12
0x180009f70  jnz     loc_18000A4B4
0x180009f76  test    rdi, rdi
0x180009f79  jnz     loc_18000A538
0x180009f7f  cmp     rcx, r12
0x180009f82  jnz     loc_18000A6A2
0x180009f88  test    r14, r14
0x180009f8b  jz      loc_18000A3EF
0x180009f91  cmp     rcx, r12
0x180009f94  jnz     loc_18000A4E7
0x180009f9a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DisableDigestSSO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DisableDigestSSO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDigestSSO> `wil::Feature<__WilFeatureTraits_Feature_DisableDigestSSO>::GetImpl(void)'::`2'::impl
0x180009fa1  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_DisableDigestSSO@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DisableDigestSSO>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180009fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fad  cmp     rcx, r12
0x180009fb0  jnz     loc_18000A5B7
0x180009fb6  lea     r8, [r14+18h]
0x180009fba  mov     r9d, 1
0x180009fc0  lea     rdx, [r14+8]
0x180009fc4  lea     rcx, [rsp+0A8h+var_78]
0x180009fc9  call    cs:__imp_LsaIEventWritePackageNotCacheLogonUser
0x180009fcf  test    rbp, rbp
0x180009fd2  jnz     loc_18000A8A1
0x180009fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fdf  cmp     rcx, r12
0x180009fe2  jnz     loc_18000A568
0x180009fe8  test    byte ptr [r14+50h], 4
0x180009fed  jnz     loc_18000A3F8
0x180009ff3  cmp     rcx, r12
0x180009ff6  jnz     loc_18000A593
0x180009ffc  cmp     cs:g_NtDigestState, 1
0x18000a003  jnz     loc_18000A5F2
0x18000a009  mov     rax, cs:g_LsaFunctions
0x18000a010  mov     ecx, 80h
0x18000a015  mov     rax, [rax+28h]
0x18000a019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a01e  mov     rbx, rax
0x18000a021  test    rax, rax
0x18000a024  jz      short loc_18000A048
0x18000a026  xorps   xmm0, xmm0
0x18000a029  movups  xmmword ptr [rax], xmm0
0x18000a02c  movups  xmmword ptr [rax+10h], xmm0
0x18000a030  movups  xmmword ptr [rax+20h], xmm0
0x18000a034  movups  xmmword ptr [rax+30h], xmm0
0x18000a038  movups  xmmword ptr [rax+40h], xmm0
0x18000a03c  movups  xmmword ptr [rax+50h], xmm0
0x18000a040  movups  xmmword ptr [rax+60h], xmm0
0x18000a044  movups  xmmword ptr [rax+70h], xmm0
0x18000a048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a04f  cmp     rcx, r12
0x18000a052  jz      short loc_18000A061
0x18000a054  test    dword ptr [rcx+1Ch], 100h
0x18000a05b  jnz     loc_18000A8D9
0x18000a061  test    rbx, rbx
0x18000a064  jz      loc_18000A67A
0x18000a06a  xorps   xmm0, xmm0
0x18000a06d  movups  xmmword ptr [rbx], xmm0
0x18000a070  movups  xmmword ptr [rbx+10h], xmm0
0x18000a074  movups  xmmword ptr [rbx+20h], xmm0
0x18000a078  movups  xmmword ptr [rbx+30h], xmm0
0x18000a07c  movups  xmmword ptr [rbx+40h], xmm0
0x18000a080  movups  xmmword ptr [rbx+50h], xmm0
0x18000a084  movups  xmmword ptr [rbx+60h], xmm0
0x18000a088  movups  xmmword ptr [rbx+70h], xmm0
0x18000a08c  mov     [rbx+18h], rbx
0x18000a090  mov     dword ptr [rbx+10h], 1
0x18000a097  mov     [rbx+2Ch], r15d
0x18000a09b  mov     rax, [r14]
0x18000a09e  mov     [rbx+20h], rax
0x18000a0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0a9  cmp     rcx, r12
0x18000a0ac  jz      short loc_18000A0B8
0x18000a0ae  test    byte ptr [rcx+1Ch], 4
0x18000a0b2  jnz     loc_18000A900
0x18000a0b8  lea     rdi, [r14+8]
0x18000a0bc  mov     [rbx+38h], r13
0x18000a0c0  mov     [rbx+30h], r13d
0x18000a0c4  mov     r15d, 0FFFDh
0x18000a0ca  test    rdi, rdi
0x18000a0cd  jz      loc_18000A178
0x18000a0d3  cmp     [rdi+8], rsi
0x18000a0d7  jz      loc_18000A178
0x18000a0dd  movzx   eax, word ptr [rdi]
0x18000a0e0  cmp     ax, r15w
0x18000a0e4  ja      loc_18000A64E
0x18000a0ea  cmp     cs:g_NtDigestState, 1
0x18000a0f1  lea     ebp, [rax+2]
0x18000a0f4  jnz     loc_18000A6D2
0x18000a0fa  mov     rax, cs:g_LsaFunctions
0x18000a101  mov     ecx, ebp
0x18000a103  mov     rax, [rax+28h]
0x18000a107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a10c  mov     rsi, rax
0x18000a10f  test    rax, rax
0x18000a112  jz      short loc_18000A121
0x18000a114  mov     r8d, ebp; Size
0x18000a117  xor     edx, edx; Val
0x18000a119  mov     rcx, rax; void *
0x18000a11c  call    memset_0
0x18000a121  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a128  cmp     rcx, r12
0x18000a12b  jz      short loc_18000A13A
0x18000a12d  test    dword ptr [rcx+1Ch], 100h
0x18000a134  jnz     loc_18000A925
0x18000a13a  mov     [rbx+38h], rsi
0x18000a13e  test    rsi, rsi
0x18000a141  jz      loc_18000A934
0x18000a147  movzx   eax, word ptr [rdi]
0x18000a14a  mov     rcx, rsi; void *
0x18000a14d  mov     [rbx+30h], ax
0x18000a151  movzx   eax, word ptr [rdi]
0x18000a154  add     ax, 2
0x18000a158  mov     [rbx+32h], ax
0x18000a15c  movzx   r8d, word ptr [rdi]; Size
0x18000a160  mov     rdx, [rdi+8]; Src
0x18000a164  call    memcpy_0
0x18000a169  movzx   edx, word ptr [rdi]
0x18000a16c  mov     rcx, [rbx+38h]
0x18000a170  shr     rdx, 1
0x18000a173  mov     [rcx+rdx*2], r13w
0x18000a178  lea     rdi, [r14+18h]
0x18000a17c  mov     [rbx+48h], r13
0x18000a180  mov     [rbx+40h], r13d
0x18000a184  test    rdi, rdi
0x18000a187  jz      loc_18000A232
0x18000a18d  cmp     [rdi+8], r13
0x18000a191  jz      loc_18000A232
0x18000a197  movzx   eax, word ptr [rdi]
0x18000a19a  cmp     ax, r15w
0x18000a19e  ja      loc_18000A96D
0x18000a1a4  cmp     cs:g_NtDigestState, 1
0x18000a1ab  lea     ebp, [rax+2]
0x18000a1ae  jnz     loc_18000A721
0x18000a1b4  mov     rax, cs:g_LsaFunctions
0x18000a1bb  mov     ecx, ebp
0x18000a1bd  mov     rax, [rax+28h]
0x18000a1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c6  mov     rsi, rax
0x18000a1c9  test    rax, rax
0x18000a1cc  jz      short loc_18000A1DB
0x18000a1ce  mov     r8d, ebp; Size
0x18000a1d1  xor     edx, edx; Val
0x18000a1d3  mov     rcx, rax; void *
0x18000a1d6  call    memset_0
0x18000a1db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1e2  cmp     rcx, r12
0x18000a1e5  jz      short loc_18000A1F4
0x18000a1e7  test    dword ptr [rcx+1Ch], 100h
0x18000a1ee  jnz     loc_18000A974
0x18000a1f4  mov     [rbx+48h], rsi
0x18000a1f8  test    rsi, rsi
0x18000a1fb  jz      loc_18000A983
0x18000a201  movzx   eax, word ptr [rdi]
0x18000a204  mov     rcx, rsi; void *
0x18000a207  mov     [rbx+40h], ax
0x18000a20b  movzx   eax, word ptr [rdi]
0x18000a20e  add     ax, 2
0x18000a212  mov     [rbx+42h], ax
0x18000a216  movzx   r8d, word ptr [rdi]; Size
0x18000a21a  mov     rdx, [rdi+8]; Src
0x18000a21e  call    memcpy_0
0x18000a223  movzx   edx, word ptr [rdi]
0x18000a226  mov     rcx, [rbx+48h]
0x18000a22a  shr     rdx, 1
0x18000a22d  mov     [rcx+rdx*2], r13w
0x18000a232  lea     rdi, [r14+58h]
0x18000a236  mov     [rbx+68h], r13
0x18000a23a  mov     [rbx+60h], r13d
0x18000a23e  test    rdi, rdi
0x18000a241  jz      loc_18000A2EC
0x18000a247  cmp     [rdi+8], r13
0x18000a24b  jz      loc_18000A2EC
0x18000a251  movzx   eax, word ptr [rdi]
0x18000a254  cmp     ax, r15w
0x18000a258  ja      loc_18000A9DA
0x18000a25e  cmp     cs:g_NtDigestState, 1
0x18000a265  lea     ebp, [rax+2]
0x18000a268  jnz     loc_18000A770
0x18000a26e  mov     rax, cs:g_LsaFunctions
0x18000a275  mov     ecx, ebp
0x18000a277  mov     rax, [rax+28h]
0x18000a27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a280  mov     rsi, rax
0x18000a283  test    rax, rax
0x18000a286  jz      short loc_18000A295
0x18000a288  mov     r8d, ebp; Size
0x18000a28b  xor     edx, edx; Val
0x18000a28d  mov     rcx, rax; void *
0x18000a290  call    memset_0
0x18000a295  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a29c  cmp     rcx, r12
0x18000a29f  jz      short loc_18000A2AE
0x18000a2a1  test    dword ptr [rcx+1Ch], 100h
0x18000a2a8  jnz     loc_18000A9E1
0x18000a2ae  mov     [rbx+68h], rsi
0x18000a2b2  test    rsi, rsi
0x18000a2b5  jz      loc_18000A9F0
0x18000a2bb  movzx   eax, word ptr [rdi]
0x18000a2be  mov     rcx, rsi; void *
0x18000a2c1  mov     [rbx+60h], ax
0x18000a2c5  movzx   eax, word ptr [rdi]
0x18000a2c8  add     ax, 2
0x18000a2cc  mov     [rbx+62h], ax
0x18000a2d0  movzx   r8d, word ptr [rdi]; Size
0x18000a2d4  mov     rdx, [rdi+8]; Src
0x18000a2d8  call    memcpy_0
0x18000a2dd  movzx   edx, word ptr [rdi]
0x18000a2e0  mov     rcx, [rbx+68h]
0x18000a2e4  shr     rdx, 1
0x18000a2e7  mov     [rcx+rdx*2], r13w
0x18000a2ec  lea     rdi, [r14+68h]
0x18000a2f0  mov     [rbx+78h], r13
0x18000a2f4  mov     [rbx+70h], r13d
0x18000a2f8  mov     ebp, r13d
0x18000a2fb  test    rdi, rdi
0x18000a2fe  jz      loc_18000A80E
0x18000a304  cmp     [rdi+8], rbp
0x18000a308  jz      loc_18000A80E
0x18000a30e  movzx   eax, word ptr [rdi]
0x18000a311  cmp     ax, r15w
0x18000a315  ja      loc_18000AA47
0x18000a31b  cmp     cs:g_NtDigestState, 1
0x18000a322  lea     ebp, [rax+2]
0x18000a325  jnz     loc_18000A7BF
0x18000a32b  mov     rax, cs:g_LsaFunctions
0x18000a332  mov     ecx, ebp
0x18000a334  mov     rax, [rax+28h]
0x18000a338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a33d  mov     rsi, rax
0x18000a340  test    rax, rax
0x18000a343  jz      short loc_18000A352
0x18000a345  mov     r8d, ebp; Size
0x18000a348  xor     edx, edx; Val
0x18000a34a  mov     rcx, rax; void *
0x18000a34d  call    memset_0
0x18000a352  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a359  cmp     rcx, r12
0x18000a35c  jz      short loc_18000A36B
0x18000a35e  test    dword ptr [rcx+1Ch], 100h
0x18000a365  jnz     loc_18000AA57
0x18000a36b  mov     [rbx+78h], rsi
0x18000a36f  test    rsi, rsi
0x18000a372  jz      loc_18000AA66
0x18000a378  movzx   eax, word ptr [rdi]
0x18000a37b  mov     rcx, rsi; void *
0x18000a37e  mov     [rbx+70h], ax
0x18000a382  movzx   eax, word ptr [rdi]
0x18000a385  add     ax, 2
0x18000a389  mov     [rbx+72h], ax
0x18000a38d  movzx   r8d, word ptr [rdi]; Size
0x18000a391  mov     rdx, [rdi+8]; Src
0x18000a395  call    memcpy_0
0x18000a39a  movzx   edx, word ptr [rdi]
0x18000a39d  mov     esi, r13d
0x18000a3a0  mov     rcx, [rbx+78h]
0x18000a3a4  shr     rdx, 1
0x18000a3a7  mov     [rcx+rdx*2], r13w
0x18000a3ac  mov     eax, [r14+50h]
0x18000a3b0  mov     [rbx+28h], eax
0x18000a3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3ba  cmp     rcx, r12
0x18000a3bd  jz      short loc_18000A3C9
0x18000a3bf  test    byte ptr [rcx+1Ch], 4
0x18000a3c3  jnz     loc_18000AABB
0x18000a3c9  lea     rdx, [rsp+0A8h+arg_8]
0x18000a3d1  mov     rcx, rbx
0x18000a3d4  call    LogSessHandlerNoPasswordInsert
0x18000a3d9  cmp     [rsp+0A8h+arg_8], 1
0x18000a3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3e8  jnz     short loc_18000A3F8
  ... truncated ...
```
