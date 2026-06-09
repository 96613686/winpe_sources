# CMDEContentServer::IsSuitableMDEProfile(_WMCResElementParams const *,ATL::CRBMultiMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>> const *,MDEProfile const *)

- ea: `0x140004fe0`
- end: `0x140005b30`
- name: `?IsSuitableMDEProfile@CMDEContentServer@@AEAAHPEBU_WMCResElementParams@@PEBV?$CRBMultiMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@PEBUMDEProfile@@@Z`
- size: `2896`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x14001a1c0`

## callees

- `0x140003750`
- `0x140003940`
- `0x140003f50`
- `0x140004ae0`
- `0x140004fe0`
- `0x1400065e0`
- `0x140006d70`
- `0x140007020`
- `0x14000b3f0`
- `0x14000c920`
- `0x14000c9cc`
- `0x140014f90`
- `0x140015230`
- `0x1400195f0`
- `0x14001b560`
- `0x14001b620`
- `0x1400395c0`
- `0x1400396dc`
- `0x140046c32`
- `0x140046d00`
- `0x1400476ac`
- `0x14004a834`
- `0x140057bc4`
- `0x14009ad10`
- `0x14009ad1c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x14000585c`
- `KERNEL32!CompareStringOrdinal` at `0x14000585c`
- `KERNEL32!CompareStringW` at `0x14000506a`
- `KERNEL32!CompareStringW` at `0x1400050a1`
- `KERNEL32!CompareStringW` at `0x1400050d8`
- `KERNEL32!CompareStringW` at `0x14000525c`
- `KERNEL32!CompareStringW` at `0x140005415`
- `KERNEL32!CompareStringW` at `0x140005a58`
- `KERNEL32!CompareStringW` at `0x14000506a`
- `KERNEL32!CompareStringW` at `0x1400050a1`
- `KERNEL32!CompareStringW` at `0x1400050d8`
- `KERNEL32!CompareStringW` at `0x14000525c`
- `KERNEL32!CompareStringW` at `0x140005415`
- `KERNEL32!CompareStringW` at `0x140005a58`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000554b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005ac6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000554b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005ac6`

## pseudocode

```c
__int64 __fastcall CMDEContentServer::IsSuitableMDEProfile(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  const WCHAR *v6; // r8
  unsigned int v7; // edi
  int v8; // esi
  int v9; // r12d
  const WCHAR *v10; // r8
  const WCHAR *v11; // rdx
  const WCHAR *v12; // r8
  __int64 v13; // rcx
  int v14; // r15d
  int HighestProfileInGroup; // ebx
  int v16; // ecx
  __int64 v17; // rcx
  int v18; // r12d
  int v19; // esi
  int v20; // ecx
  int LowestProfileInGroup; // eax
  const WCHAR *lpString2; // rax
  __int64 v24; // rax
  unsigned int ValueFromStringList; // esi
  __int64 v26; // rax
  char *v27; // rdx
  LPCWCH v28; // rdi
  _DWORD *v29; // rbx
  char *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned int v33; // ebx
  __int64 v34; // rax
  char *v35; // rdi
  __int64 v36; // rsi
  unsigned int *v37; // rax
  char *v38; // r8
  char *v39; // r15
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  const WCHAR *v43; // rdi
  LPCWCH v44; // rax
  WCHAR v45; // dx
  unsigned int v46; // r9d
  LPCWCH i; // r8
  const wchar_t *j; // rcx
  __int64 v49; // r15
  volatile signed __int32 *v50; // rbx
  _QWORD *v51; // rcx
  __int64 v52; // rsi
  int v53; // eax
  int v54; // r8d
  int *v55; // r15
  int v56; // ebx
  int v57; // eax
  __int64 v58; // rdx
  int v59; // ecx
  int v60; // r12d
  _QWORD *v61; // rbx
  __int64 (__fastcall ***v62)(_QWORD, _QWORD, __int64); // rcx
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rcx
  size_t v66; // r8
  __int64 v67; // rax
  ATL::CStringData *v68; // rcx
  __int64 v69; // rdi
  __int64 v70; // rbx
  unsigned __int64 v71; // rdx
  int v72; // ecx
  int v73; // eax
  __int64 v74; // r12
  unsigned __int64 v75; // rcx
  _QWORD *v76; // rax
  int v77; // r8d
  _QWORD *v78; // rax
  char *v79; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v80; // [rsp+48h] [rbp-11h]
  int v81; // [rsp+4Ch] [rbp-Dh]
  int v82; // [rsp+50h] [rbp-9h]
  LPCWCH lpString1; // [rsp+58h] [rbp-1h] BYREF
  __int64 v84; // [rsp+60h] [rbp+7h] BYREF
  __int64 v85; // [rsp+68h] [rbp+Fh] BYREF
  void *Src; // [rsp+70h] [rbp+17h]
  __int64 v87; // [rsp+78h] [rbp+1Fh] BYREF
  _DWORD *v88; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v89; // [rsp+D0h] [rbp+77h]
  int v90; // [rsp+D8h] [rbp+7Fh]

  v89 = a3;
  v88 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, a2, a3, a4);
  }
  v6 = *(const WCHAR **)(a4 + 32);
  v7 = 0;
  v8 = 1;
  v82 = 0;
  v90 = 0;
  v9 = 0;
  LODWORD(v88) = 0;
  if ( CompareStringW(0x7Fu, 1u, v6, 6, L"image/", -1) == 2 )
  {
    lpString2 = *(const WCHAR **)a2;
    v81 = 1;
    if ( !lpString2 || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a4 + 32), -1, lpString2, -1) != 2 )
      goto LABEL_11;
    v24 = *(_QWORD *)(a4 + 40);
    v9 = 1;
    LODWORD(v88) = 1;
    if ( *(int *)(v24 - 16) <= 0 && *(_DWORD *)(a4 + 108) == -1 && *(_DWORD *)(a4 + 104) == -1 )
    {
      if ( *(_DWORD *)(a2 + 72) > 0x800u || *(_DWORD *)(a2 + 76) > 0x800u )
        goto LABEL_11;
      ValueFromStringList = 0;
      while ( ValueFromStringList != -1 )
      {
        v88 = (_DWORD *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
        v26 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
        v27 = *(char **)(a2 + 8);
        v28 = (LPCWCH)(v26 + 24);
        lpString1 = (LPCWCH)(v26 + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          (void **)&v79,
          v27);
        ValueFromStringList = GetValueFromStringList(&v79, ValueFromStringList, &v88);
        ATL::CStringData::Release((ATL::CStringData *)(v79 - 24));
        v29 = v88;
        if ( (int)*(v88 - 4) > 0 )
        {
          v30 = (char *)v88;
          if ( v88 )
          {
            while ( 1 )
            {
              if ( !*(_WORD *)v30 )
                goto LABEL_155;
              if ( *(_WORD *)v30 == 61 )
                break;
              v30 += 2;
            }
            if ( (unsigned int)((v30 - (char *)v88) >> 1) != -1 )
            {
              v76 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
                                &v88,
                                &v84,
                                L"=");
              ATL::CSimpleStringT<unsigned short,0>::operator=(&lpString1, v76);
              ATL::CStringData::Release((ATL::CStringData *)(v84 - 24));
              v28 = lpString1;
              v77 = *((_DWORD *)lpString1 - 4);
              if ( v77 )
              {
                v78 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
                                  &v88,
                                  &v85,
                                  (unsigned int)(v77 + 1));
                ATL::CSimpleStringT<unsigned short,0>::operator=(&v88, v78);
                ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
                v29 = v88;
              }
              if ( *(v29 - 4) )
              {
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString1);
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v88);
                v14 = 1;
                HighestProfileInGroup = 0;
                goto LABEL_41;
              }
            }
          }
        }
LABEL_155:
        ATL::CStringData::Release((ATL::CStringData *)(v28 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v29 - 6));
      }
      v14 = v81;
      v9 = 0;
      HighestProfileInGroup = 0;
LABEL_41:
      v16 = v90;
      goto LABEL_42;
    }
  }
  else
  {
    v10 = *(const WCHAR **)(a4 + 32);
    v81 = 0;
    if ( CompareStringW(0x7Fu, 1u, v10, 6, L"audio/", -1) == 2 )
    {
      v12 = *(const WCHAR **)(a4 + 32);
      v82 = 1;
      v90 = CompareStringW(0x7Fu, 1u, v12, 9, L"audio/L16", -1) == 2;
      if ( *(_DWORD *)(a4 + 172) )
      {
        v9 = 1;
        LODWORD(v88) = 1;
      }
      else
      {
        v11 = *(const WCHAR **)GUID_NULL.Data4;
        v13 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)(a2 + 96);
        if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)(a2 + 96) )
          v13 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)(a2 + 104);
        if ( !v13 )
          goto LABEL_176;
        v40 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)(a4 + 140);
        if ( !v40 )
          v40 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)(a4 + 148);
        if ( v40 )
        {
          v41 = *(_QWORD *)(a2 + 96) - *(_QWORD *)(a4 + 140);
          if ( !v41 )
            v41 = *(_QWORD *)(a2 + 104) - *(_QWORD *)(a4 + 148);
          if ( !v41 )
          {
            v9 = 1;
            LODWORD(v88) = 1;
          }
        }
        else
        {
LABEL_176:
          if ( *(_QWORD *)a2 )
          {
            if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a4 + 32), -1, *(PCNZWCH *)a2, -1) == 2 )
              v9 = 1;
            LODWORD(v88) = v9;
          }
        }
      }
      if ( !v9 )
        goto LABEL_11;
    }
    else
    {
      if ( !*(_DWORD *)(a4 + 176) )
      {
        v11 = *(const WCHAR **)GUID_NULL.Data4;
        v31 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)(a2 + 112);
        if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)(a2 + 112) )
          v31 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)(a2 + 120);
        if ( !v31 )
          goto LABEL_52;
        v32 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)(a4 + 156);
        if ( !v32 )
          v32 = *(_QWORD *)GUID_NULL.Data4 - *(_QWORD *)(a4 + 164);
        if ( v32 )
        {
          v42 = *(_QWORD *)(a2 + 112) - *(_QWORD *)(a4 + 156);
          if ( !v42 )
            v42 = *(_QWORD *)(a2 + 120) - *(_QWORD *)(a4 + 164);
          if ( v42 )
            goto LABEL_11;
        }
        else
        {
LABEL_52:
          if ( !*(_QWORD *)a2 || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(a4 + 32), -1, *(PCNZWCH *)a2, -1) != 2 )
            goto LABEL_11;
        }
      }
      LODWORD(v88) = 1;
    }
  }
  v33 = 0;
  v80 = 0;
  while ( v33 != -1 )
  {
    lpString1 = (LPCWCH)(((__int64 (__fastcall *)(void ***, const WCHAR *))ATL::g_strmgr[3])(&ATL::g_strmgr, v11) + 24);
    v34 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
    v35 = *(char **)(a2 + 8);
    v36 = v34 + 24;
    v84 = v34 + 24;
    v37 = (unsigned int *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
    v38 = (char *)(v37 + 6);
    Src = v37 + 6;
    v39 = (char *)(v37 + 6);
    v79 = (char *)(v37 + 6);
    if ( !v35 )
      goto LABEL_57;
    if ( (unsigned __int64)v35 < 0x10000 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::LoadStringW(
        &v79,
        (unsigned __int16)v35);
      goto LABEL_58;
    }
    v70 = -1;
    do
      ++v70;
    while ( *(_WORD *)&v35[2 * v70] );
    if ( !(_DWORD)v70 )
    {
      v33 = v80;
LABEL_57:
      ATL::CSimpleStringT<unsigned short,0>::Empty(&v79);
LABEL_58:
      v39 = v79;
      goto LABEL_77;
    }
    v71 = v37[2];
    v72 = 1 - v37[4];
    v73 = v37[3] - v70;
    LODWORD(v85) = *((_DWORD *)v38 - 4);
    if ( (v73 | v72) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v79, (unsigned int)v70);
      v71 = (unsigned int)v85;
      v38 = (char *)Src;
      v39 = v79;
    }
    v74 = 2LL * (int)v70;
    if ( v74 )
    {
      v75 = (v35 - v38) >> 1;
      if ( v75 <= (unsigned int)v71 )
      {
        if ( !v39 || (v71 = (unsigned __int64)&v39[2 * v75]) == 0 )
        {
LABEL_73:
          *(_DWORD *)_o__errno(v75, v71, v38) = 22;
          invalid_parameter_noinfo();
          goto LABEL_74;
        }
        memmove_0(v39, (const void *)v71, 2LL * (int)v70);
      }
      else
      {
        if ( !v39 )
          goto LABEL_73;
        memcpy_0(v39, v35, 2LL * (int)v70);
      }
    }
LABEL_74:
    if ( (int)v70 < 0 || (int)v70 > *((_DWORD *)v39 - 3) )
      goto LABEL_166;
    *((_DWORD *)v39 - 4) = v70;
    v33 = v80;
    *(_WORD *)&v39[v74] = 0;
LABEL_77:
    v33 = GetValueFromStringList(&v79, v33, &lpString1);
    v80 = v33;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v39 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v39 - 3) + 8LL))(*((_QWORD *)v39 - 3));
    v43 = lpString1;
    if ( *((int *)lpString1 - 4) <= 0 )
      goto LABEL_85;
    v44 = lpString1;
    if ( !lpString1 )
      goto LABEL_85;
    while ( 1 )
    {
      if ( !*v44 )
        goto LABEL_85;
      if ( *v44 == 61 )
        break;
      ++v44;
    }
    if ( (unsigned int)(v44 - lpString1) == -1 )
      goto LABEL_85;
    v45 = *lpString1;
    v46 = 0;
    for ( i = lpString1; v45; ++v46 )
    {
      for ( j = L"="; *j; ++j )
      {
        if ( *j == v45 )
          goto LABEL_97;
      }
      if ( !v45 )
        break;
      v45 = i[1];
      ++i;
    }
LABEL_97:
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
      &lpString1,
      &v87,
      v46);
    v49 = v87;
    v50 = (volatile signed __int32 *)(v36 - 24);
    v51 = (_QWORD *)(v87 - 24);
    if ( v87 - 24 != v36 - 24 )
    {
      if ( *((int *)v50 + 4) >= 0 && *v51 == *(_QWORD *)v50 )
      {
        v52 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v51);
        if ( _InterlockedExchangeAdd(v50 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v50 + 8LL))(*(_QWORD *)v50, v50);
        v36 = v52 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v84, v87, *(unsigned int *)(v87 - 16));
        v36 = v84;
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v49 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v49 - 24) + 8LL))(*(_QWORD *)(v49 - 24));
    v53 = *(_DWORD *)(v36 - 16);
    if ( v53 )
    {
      v54 = *((_DWORD *)v43 - 4);
      v55 = (int *)(v43 - 12);
      v56 = 0;
      v57 = v53 + 1;
      if ( v57 >= 0 )
        v56 = v57;
      v58 = 0;
      v59 = *((_DWORD *)v43 - 4) - v57;
      if ( v59 >= 0 )
        v58 = (unsigned int)v59;
      if ( 0x7FFFFFFF - v56 < (int)v58 )
LABEL_166:
        ATL::AtlThrowImpl(-2147024809);
      if ( v56 + (int)v58 > v54 )
        v58 = (unsigned int)(v54 - v56);
      v60 = 0;
      if ( v56 <= v54 )
        v60 = v58;
      if ( !v56 && v60 == v54 )
      {
        v61 = (_QWORD *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(v43 - 12) + 24);
LABEL_128:
        if ( v61 - 3 != (_QWORD *)v55 )
        {
          if ( v55[4] >= 0 && *(v61 - 3) == *(_QWORD *)v55 )
          {
            v67 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v61 - 3);
            v68 = (ATL::CStringData *)(v43 - 12);
            v69 = v67;
            ATL::CStringData::Release(v68);
            v43 = (const WCHAR *)(v69 + 24);
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&lpString1, v61, *((unsigned int *)v61 - 4));
            v43 = lpString1;
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)(v61 - 3));
        goto LABEL_133;
      }
      if ( !*(_QWORD *)v55
        || (v62 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v55 + 32LL))(
                                                                       *(_QWORD *)v55,
                                                                       v58)) == 0 )
      {
        v62 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))((__int64 (__fastcall *)(void ***, __int64))ATL::g_strmgr[4])(
                                                                   &ATL::g_strmgr,
                                                                   v58);
        if ( !v62 )
          ATL::AtlThrowImpl(-2147467259);
      }
      Src = (void *)&v43[v56];
      if ( !Src && v60 )
        goto LABEL_166;
      v63 = (**v62)(v62, (unsigned int)v60, 2);
      if ( !v63 )
        ATL::CSimpleStringT<char,0>::ThrowMemoryException();
      if ( v60 < 0 )
        goto LABEL_166;
      v61 = (_QWORD *)(v63 + 24);
      if ( v60 > *(_DWORD *)(v63 + 12) )
        goto LABEL_166;
      *(_DWORD *)(v63 + 8) = v60;
      v66 = 2LL * v60;
      *(_WORD *)((char *)v61 + v66) = 0;
      if ( !v66 )
        goto LABEL_128;
      if ( v63 != -24 )
      {
        if ( Src )
        {
          memcpy_0(v61, Src, v66);
          goto LABEL_128;
        }
        memset_0(v61, 0, v66);
      }
      *(_DWORD *)_o__errno(v65, v64, v66) = 22;
      invalid_parameter_noinfo();
      goto LABEL_128;
    }
LABEL_133:
    if ( CompareStringOrdinal(v43, -1, *(LPCWCH *)(a4 + 40), -1, 1) == 2 )
    {
      ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v43 - 12));
      v9 = (int)v88;
      v7 = 0;
      goto LABEL_135;
    }
    v33 = v80;
LABEL_85:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v36 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v36 - 24) + 8LL))(*(_QWORD *)(v36 - 24));
    v11 = v43 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  }
  v7 = 0;
  v9 = 0;
LABEL_135:
  v8 = 1;
LABEL_11:
  v14 = v81;
  HighestProfileInGroup = 0;
  if ( v81 )
    goto LABEL_41;
  v16 = v90;
  if ( v90 || (*(_DWORD *)(a2 + 128) & 0x8000) != 0 || !*(_DWORD *)(*(_QWORD *)(a4 + 48) - 16LL) )
  {
LABEL_42:
    v8 = 0;
    v7 = IsMDEProfileSuitableForResElement(
           (const struct MDEProfile *)a4,
           (const struct _WMCResElementParams *)a2,
           v14,
           v82,
           v16,
           v9);
    if ( !v7 )
      goto LABEL_15;
    goto LABEL_23;
  }
LABEL_15:
  if ( !v9 )
  {
    v17 = *(_QWORD *)(a4 + 48);
    if ( *(_DWORD *)(v17 - 16) )
    {
      v88 = 0;
      if ( v8 )
      {
        v18 = v89;
        v19 = v82;
        HighestProfileInGroup = CMDEProfileCollection::FindHighestProfileInGroup(
                                  v17,
                                  v89,
                                  a4,
                                  a2,
                                  v14,
                                  v82,
                                  (__int64)&v88);
        if ( HighestProfileInGroup < 0 )
        {
          LowestProfileInGroup = CMDEProfileCollection::FindLowestProfileInGroup(
                                   v20,
                                   v18,
                                   a4,
                                   a2,
                                   v14,
                                   v19,
                                   (__int64)&v88);
          goto LABEL_20;
        }
        goto LABEL_21;
      }
      LowestProfileInGroup = CMDEProfileCollection::FindLowestProfileInGroup(v17, v89, a4, a2, v14, v82, (__int64)&v88);
LABEL_20:
      HighestProfileInGroup = LowestProfileInGroup;
      if ( LowestProfileInGroup < 0 )
      {
LABEL_22:
        HighestProfileInGroup = 0;
      }
      else
      {
LABEL_21:
        if ( *v88 != *(_DWORD *)a4 )
          goto LABEL_22;
        v7 = 1;
      }
    }
  }
LABEL_23:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)HighestProfileInGroup);
  }
  return v7;
}

```

## disassembly

```asm
0x140004fe0  mov     [rsp-8+arg_10], r8
0x140004fe5  mov     [rsp-8+arg_0], rcx
0x140004fea  push    rbp
0x140004feb  push    rsi
0x140004fec  push    rdi
0x140004fed  push    r12
0x140004fef  push    r13
0x140004ff1  push    r14
0x140004ff3  lea     rbp, [rsp-2Fh]
0x140004ff8  sub     rsp, 88h
0x140004fff  mov     r14, r9
0x140005002  mov     r13, rdx
0x140005005  mov     rcx, cs:WPP_GLOBAL_Control
0x14000500c  lea     rdx, WPP_GLOBAL_Control
0x140005013  cmp     rcx, rdx
0x140005016  jz      short loc_140005022
0x140005018  test    byte ptr [rcx+1Ch], 1
0x14000501c  jnz     loc_140005A09
0x140005022  mov     r8, [r14+20h]; lpString1
0x140005026  lea     rax, aImage; "image/"
0x14000502d  xor     edi, edi
0x14000502f  mov     [rsp+0B0h+arg_8], rbx
0x140005037  mov     esi, 1
0x14000503c  mov     [rsp+0B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x140005044  mov     edx, esi; dwCmpFlags
0x140005046  mov     [rsp+0B0h+var_30], r15
0x14000504e  mov     r9d, 6; cchCount1
0x140005054  mov     [rbp+57h+var_60], edi
0x140005057  mov     ecx, 7Fh; Locale
0x14000505c  mov     [rbp+57h+arg_18], edi
0x14000505f  mov     r12d, edi
0x140005062  mov     dword ptr [rbp+57h+arg_0], edi
0x140005065  mov     [rsp+0B0h+lpString2], rax; lpString2
0x14000506a  call    cs:__imp_CompareStringW
0x140005070  cmp     eax, 2
0x140005073  jz      loc_14000522E
0x140005079  mov     r8, [r14+20h]; lpString1
0x14000507d  lea     rax, aAudio_0; "audio/"
0x140005084  mov     [rsp+0B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x14000508c  mov     r9d, 6; cchCount1
0x140005092  mov     edx, esi; dwCmpFlags
0x140005094  mov     [rsp+0B0h+lpString2], rax; lpString2
0x140005099  mov     ecx, 7Fh; Locale
0x14000509e  mov     [rbp+57h+var_64], edi
0x1400050a1  call    cs:__imp_CompareStringW
0x1400050a7  cmp     eax, 2
0x1400050aa  jnz     loc_1400053A2
0x1400050b0  mov     r8, [r14+20h]; lpString1
0x1400050b4  lea     rax, aAudioL16_1; "audio/L16"
0x1400050bb  mov     [rsp+0B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400050c3  mov     r9d, 9; cchCount1
0x1400050c9  mov     edx, esi; dwCmpFlags
0x1400050cb  mov     [rsp+0B0h+lpString2], rax; lpString2
0x1400050d0  mov     ecx, 7Fh; Locale
0x1400050d5  mov     [rbp+57h+var_60], esi
0x1400050d8  call    cs:__imp_CompareStringW
0x1400050de  cmp     eax, 2
0x1400050e1  mov     ecx, edi
0x1400050e3  setz    cl
0x1400050e6  mov     [rbp+57h+arg_18], ecx
0x1400050e9  cmp     [r14+0ACh], edi
0x1400050f0  jnz     loc_14000550A
0x1400050f6  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1400050fd  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x140005104  mov     rcx, rax
0x140005107  sub     rcx, [r13+60h]
0x14000510b  jnz     short loc_140005114
0x14000510d  mov     rcx, rdx
0x140005110  sub     rcx, [r13+68h]
0x140005114  test    rcx, rcx
0x140005117  jnz     loc_1400054B8
0x14000511d  mov     rax, [r13+0]
0x140005121  test    rax, rax
0x140005124  jnz     loc_140005A3A
0x14000512a  test    r12d, r12d
0x14000512d  jnz     loc_140005427
0x140005133  mov     r15d, [rbp+57h+var_64]
0x140005137  mov     ebx, edi
0x140005139  test    r15d, r15d
0x14000513c  jnz     loc_140005373
0x140005142  mov     ecx, [rbp+57h+arg_18]
0x140005145  test    ecx, ecx
0x140005147  jnz     loc_140005376
0x14000514d  test    dword ptr [r13+80h], 8000h
0x140005158  jnz     loc_140005376
0x14000515e  mov     rax, [r14+30h]
0x140005162  cmp     [rax-10h], ecx
0x140005165  jz      loc_140005376
0x14000516b  test    r12d, r12d
0x14000516e  jnz     short loc_1400051EE
0x140005170  mov     rcx, [r14+30h]
0x140005174  cmp     [rcx-10h], r12d
0x140005178  jz      short loc_1400051EE
0x14000517a  mov     [rbp+57h+arg_0], 0
0x140005182  lea     rax, [rbp+57h+arg_0]
0x140005186  mov     [rsp+0B0h+var_80], rax
0x14000518b  mov     r9, r13
0x14000518e  mov     r8, r14
0x140005191  test    esi, esi
0x140005193  jz      loc_140005515
0x140005199  mov     r12, [rbp+57h+arg_10]
0x14000519d  mov     esi, [rbp+57h+var_60]
0x1400051a0  mov     rdx, r12
0x1400051a3  mov     [rsp+0B0h+cchCount2], esi
0x1400051a7  mov     dword ptr [rsp+0B0h+lpString2], r15d
0x1400051ac  call    ?FindHighestProfileInGroup@CMDEProfileCollection@@QEAAJPEBV?$CRBMultiMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@PEBUMDEProfile@@PEBU_WMCResElementParams@@HHPEAPEBU4@@Z; CMDEProfileCollection::FindHighestProfileInGroup(ATL::CRBMultiMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>> const *,MDEProfile const *,_WMCResElementParams const *,int,int,MDEProfile const * *)
0x1400051b1  mov     ebx, eax
0x1400051b3  test    eax, eax
0x1400051b5  jns     short loc_1400051DD
0x1400051b7  lea     rax, [rbp+57h+arg_0]
0x1400051bb  mov     r9, r13
0x1400051be  mov     [rsp+0B0h+var_80], rax
0x1400051c3  mov     r8, r14
0x1400051c6  mov     [rsp+0B0h+cchCount2], esi
0x1400051ca  mov     rdx, r12
0x1400051cd  mov     dword ptr [rsp+0B0h+lpString2], r15d
0x1400051d2  call    ?FindLowestProfileInGroup@CMDEProfileCollection@@QEAAJPEBV?$CRBMultiMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@PEBUMDEProfile@@PEBU_WMCResElementParams@@HHPEAPEBU4@@Z; CMDEProfileCollection::FindLowestProfileInGroup(ATL::CRBMultiMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>> const *,MDEProfile const *,_WMCResElementParams const *,int,int,MDEProfile const * *)
0x1400051d7  mov     ebx, eax
0x1400051d9  test    eax, eax
0x1400051db  js      short loc_1400051EC
0x1400051dd  mov     rax, [rbp+57h+arg_0]
0x1400051e1  mov     ecx, [r14]
0x1400051e4  cmp     [rax], ecx
0x1400051e6  jz      loc_140005500
0x1400051ec  xor     ebx, ebx
0x1400051ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400051f5  lea     rax, WPP_GLOBAL_Control
0x1400051fc  cmp     rcx, rax
0x1400051ff  jz      short loc_14000520B
0x140005201  test    byte ptr [rcx+1Ch], 1
0x140005205  jnz     loc_140005B05
0x14000520b  mov     r15, [rsp+0B0h+var_30]
0x140005213  mov     eax, edi
0x140005215  mov     rbx, [rsp+0B0h+arg_8]
0x14000521d  add     rsp, 88h
0x140005224  pop     r14
0x140005226  pop     r13
0x140005228  pop     r12
0x14000522a  pop     rdi
0x14000522b  pop     rsi
0x14000522c  pop     rbp
0x14000522d  retn
0x14000522e  mov     rax, [r13+0]
0x140005232  mov     [rbp+57h+var_64], esi
0x140005235  test    rax, rax
0x140005238  jz      loc_140005133
0x14000523e  mov     r8, [r14+20h]; lpString1
0x140005242  mov     r9d, 0FFFFFFFFh; cchCount1
0x140005248  mov     [rsp+0B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x140005250  mov     edx, esi; dwCmpFlags
0x140005252  mov     ecx, 7Fh; Locale
0x140005257  mov     [rsp+0B0h+lpString2], rax; lpString2
0x14000525c  call    cs:__imp_CompareStringW
0x140005262  cmp     eax, 2
0x140005265  jnz     loc_140005133
0x14000526b  mov     rax, [r14+28h]
0x14000526f  mov     r12d, esi
0x140005272  mov     dword ptr [rbp+57h+arg_0], esi
0x140005275  cmp     [rax-10h], edi
0x140005278  jg      loc_140005427
0x14000527e  cmp     dword ptr [r14+6Ch], 0FFFFFFFFh
0x140005283  jnz     loc_140005427
0x140005289  cmp     dword ptr [r14+68h], 0FFFFFFFFh
0x14000528e  jnz     loc_140005427
0x140005294  cmp     dword ptr [r13+48h], 800h
0x14000529c  ja      loc_140005133
0x1400052a2  cmp     dword ptr [r13+4Ch], 800h
0x1400052aa  ja      loc_140005133
0x1400052b0  mov     esi, edi
0x1400052b2  cmp     esi, 0FFFFFFFFh
0x1400052b5  jz      loc_140005966
0x1400052bb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400052c2  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400052c9  mov     rax, [rax+18h]
0x1400052cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052d2  add     rax, 18h
0x1400052d6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400052dd  mov     [rbp+57h+arg_0], rax
0x1400052e1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400052e8  mov     rax, [rax+18h]
0x1400052ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052f1  mov     rdx, [r13+8]
0x1400052f5  lea     rcx, [rbp+57h+var_70]
0x1400052f9  lea     rdi, [rax+18h]
0x1400052fd  mov     [rbp+57h+lpString1], rdi
0x140005301  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140005306  lea     r8, [rbp+57h+arg_0]
0x14000530a  mov     edx, esi
0x14000530c  lea     rcx, [rbp+57h+var_70]
0x140005310  call    ?GetValueFromStringList@@YAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@HAEAV12@G@Z; GetValueFromStringList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ushort)
0x140005315  mov     rcx, [rbp+57h+var_70]
0x140005319  mov     esi, eax
0x14000531b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14000531f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140005324  mov     rbx, [rbp+57h+arg_0]
0x140005328  cmp     dword ptr [rbx-10h], 0
0x14000532c  jle     loc_1400059F2
0x140005332  mov     rax, rbx
0x140005335  test    rbx, rbx
0x140005338  jz      loc_1400059F2
0x14000533e  movzx   ecx, word ptr [rax]
0x140005341  test    cx, cx
0x140005344  jz      loc_1400059F2
0x14000534a  cmp     cx, 3Dh ; '='
0x14000534e  jz      loc_140005976
0x140005354  add     rax, 2
0x140005358  jmp     short loc_14000533E
0x14000535a  lea     rcx, [rbp+57h+lpString1]
0x14000535e  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140005363  lea     rcx, [rbp+57h+arg_0]
0x140005367  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14000536c  xor     edi, edi
0x14000536e  mov     r15d, r12d
0x140005371  mov     ebx, edi
0x140005373  mov     ecx, [rbp+57h+arg_18]
0x140005376  mov     r9d, [rbp+57h+var_60]; int
0x14000537a  mov     r8d, r15d; int
0x14000537d  mov     [rsp+0B0h+cchCount2], r12d; int
0x140005382  mov     rdx, r13; struct _WMCResElementParams *
0x140005385  mov     dword ptr [rsp+0B0h+lpString2], ecx; int
0x140005389  mov     esi, edi
0x14000538b  mov     rcx, r14; struct MDEProfile *
0x14000538e  call    ?IsMDEProfileSuitableForResElement@@YAHPEBUMDEProfile@@PEBU_WMCResElementParams@@HHHH@Z; IsMDEProfileSuitableForResElement(MDEProfile const *,_WMCResElementParams const *,int,int,int,int)
0x140005393  mov     edi, eax
0x140005395  test    eax, eax
0x140005397  jnz     loc_1400051EE
0x14000539d  jmp     loc_14000516B
0x1400053a2  cmp     [r14+0B0h], edi
0x1400053a9  jnz     short loc_140005424
0x1400053ab  mov     rax, qword ptr cs:GUID_NULL.Data1
0x1400053b2  mov     rdx, qword ptr cs:GUID_NULL.Data4
0x1400053b9  mov     rcx, rax
0x1400053bc  sub     rcx, [r13+70h]
0x1400053c0  jnz     short loc_1400053C9
0x1400053c2  mov     rcx, rdx
0x1400053c5  sub     rcx, [r13+78h]
0x1400053c9  test    rcx, rcx
0x1400053cc  jz      short loc_1400053EA
0x1400053ce  sub     rax, [r14+9Ch]
0x1400053d5  jnz     short loc_1400053E1
0x1400053d7  mov     rax, rdx
0x1400053da  sub     rax, [r14+0A4h]
0x1400053e1  test    rax, rax
0x1400053e4  jnz     loc_140005525
0x1400053ea  mov     rax, [r13+0]
0x1400053ee  test    rax, rax
0x1400053f1  jz      loc_140005133
0x1400053f7  mov     r8, [r14+20h]; lpString1
0x1400053fb  mov     r9d, 0FFFFFFFFh; cchCount1
0x140005401  mov     [rsp+0B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x140005409  mov     edx, esi; dwCmpFlags
0x14000540b  mov     ecx, 7Fh; Locale
0x140005410  mov     [rsp+0B0h+lpString2], rax; lpString2
0x140005415  call    cs:__imp_CompareStringW
0x14000541b  cmp     eax, 2
0x14000541e  jnz     loc_140005133
0x140005424  mov     dword ptr [rbp+57h+arg_0], esi
0x140005427  mov     ebx, edi
0x140005429  mov     [rbp+57h+var_68], ebx
0x14000542c  cmp     ebx, 0FFFFFFFFh
0x14000542f  jz      loc_140005AFB
0x140005435  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000543c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005443  mov     rax, [rax+18h]
0x140005447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000544c  add     rax, 18h
0x140005450  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005457  mov     [rbp+57h+lpString1], rax
0x14000545b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005462  mov     rax, [rax+18h]
0x140005466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000546b  mov     rdi, [r13+8]
0x14000546f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005476  lea     rsi, [rax+18h]
0x14000547a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005481  mov     [rbp+57h+var_50], rsi
0x140005485  mov     rax, [rax+18h]
0x140005489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000548e  lea     r8, [rax+18h]
0x140005492  mov     [rbp+57h+Src], r8
0x140005496  mov     r15, r8
0x140005499  mov     [rbp+57h+var_70], r8
0x14000549d  test    rdi, rdi
0x1400054a0  jnz     loc_140005A6E
0x1400054a6  lea     rcx, [rbp+57h+var_70]
0x1400054aa  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1400054af  mov     r15, [rbp+57h+var_70]
0x1400054b3  jmp     loc_14000557C
0x1400054b8  sub     rax, [r14+8Ch]
0x1400054bf  jnz     short loc_1400054CB
0x1400054c1  mov     rax, rdx
0x1400054c4  sub     rax, [r14+94h]
0x1400054cb  test    rax, rax
0x1400054ce  jz      loc_14000511D
0x1400054d4  mov     rax, [r13+60h]
0x1400054d8  sub     rax, [r14+8Ch]
0x1400054df  jnz     short loc_1400054EC
0x1400054e1  mov     rax, [r13+68h]
0x1400054e5  sub     rax, [r14+94h]
0x1400054ec  test    rax, rax
  ... truncated ...
```
