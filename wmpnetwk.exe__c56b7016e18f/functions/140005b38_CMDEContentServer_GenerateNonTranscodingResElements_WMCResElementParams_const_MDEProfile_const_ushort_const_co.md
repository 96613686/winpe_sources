# CMDEContentServer::GenerateNonTranscodingResElements(_WMCResElementParams const *,MDEProfile const *,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>> *)

- ea: `0x140005b38`
- end: `0x1400065cf`
- name: `?GenerateNonTranscodingResElements@CMDEContentServer@@AEAAJPEBU_WMCResElementParams@@PEBUMDEProfile@@QEBG2222PEAV?$CAtlList@PEAU_WMCResElement@@V?$CElementTraits@PEAU_WMCResElement@@@ATL@@@ATL@@@Z`
- size: `2711`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14001b850`
- `0x14001c430`

## callees

- `0x140003610`
- `0x140003690`
- `0x140005b38`
- `0x1400065e0`
- `0x140006d70`
- `0x140008e0c`
- `0x14000b3f0`
- `0x14000c780`
- `0x14000c920`
- `0x14000c9cc`
- `0x14000cb08`
- `0x14000dd98`
- `0x14000e134`
- `0x140013a20`
- `0x140014f90`
- `0x140017450`
- `0x140019590`
- `0x1400195f0`
- `0x140019af8`
- `0x14001b560`
- `0x14001b620`
- `0x14002f644`
- `0x140030750`
- `0x14003b2b8`
- `0x14003b610`
- `0x140054624`
- `0x14005480c`
- `0x1400912c0`
- `0x14009ad04`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140005db5`
- `KERNEL32!CompareStringW` at `0x140005de3`
- `KERNEL32!CompareStringW` at `0x1400061f7`
- `KERNEL32!CompareStringW` at `0x140005db5`
- `KERNEL32!CompareStringW` at `0x140005de3`
- `KERNEL32!CompareStringW` at `0x1400061f7`
- `KERNEL32!RaiseException` at `0x14000655d`
- `KERNEL32!RaiseException` at `0x14000655d`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x14000627d`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1400062dd`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140006352`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140006389`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x14000627d`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1400062dd`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140006352`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140006389`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006173`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140006173`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CMDEContentServer::GenerateNonTranscodingResElements(
        const WCHAR *a1,
        __int64 a2,
        const struct MDEProfile *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        void *Src,
        __int64 a9)
{
  char v11; // di
  _WORD *v12; // rcx
  unsigned __int8 v13; // r8
  char *v14; // rsi
  int v15; // r13d
  __int64 v16; // r8
  char v17; // r14
  unsigned int ValueFromStringList; // r15d
  int v19; // r12d
  const WCHAR *v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // r8
  _WORD *v23; // rax
  _QWORD *v24; // rcx
  volatile signed __int32 *v25; // r14
  __int64 v26; // rsi
  unsigned int WMCResElement; // r15d
  int v28; // ecx
  bool v29; // bl
  int v30; // r12d
  int v31; // edi
  __int64 v32; // r13
  __int64 v33; // rdx
  _QWORD *v34; // rcx
  int *v35; // r14
  __int64 v36; // rbx
  __int64 v37; // rbx
  __int64 v38; // r8
  unsigned int v39; // eax
  __int64 v40; // r8
  unsigned int v41; // r14d
  __int64 i; // rbx
  _QWORD *v43; // rax
  int v44; // r8d
  _QWORD *v45; // rax
  _QWORD *v46; // rcx
  __int64 v47; // rbx
  unsigned int v49; // ebx
  __int64 v50; // rax
  _QWORD *v51; // rcx
  __int64 v52; // rdi
  unsigned int v53; // ebx
  void *v54; // rax
  _DWORD *v55; // rcx
  int v56; // r14d
  char v57; // di
  _QWORD *v58; // rax
  int *v59; // rax
  __int64 v60; // r8
  __int64 v61; // r8
  __int64 v62; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v63; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  __int64 v65; // [rsp+78h] [rbp-88h]
  _QWORD *v66; // [rsp+80h] [rbp-80h] BYREF
  __int64 v67; // [rsp+88h] [rbp-78h]
  int v68; // [rsp+90h] [rbp-70h]
  char *v69; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *v70; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v71; // [rsp+A8h] [rbp-58h] BYREF
  char *v72; // [rsp+B0h] [rbp-50h] BYREF
  PCNZWCH lpString2; // [rsp+B8h] [rbp-48h] BYREF
  void *v74[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v75[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E4h] [rbp-1Ch]
  int v78; // [rsp+E8h] [rbp-18h]
  int v79; // [rsp+ECh] [rbp-14h]
  __int64 v80; // [rsp+F0h] [rbp-10h]
  __int64 v81; // [rsp+F8h] [rbp-8h]
  int v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+104h] [rbp+4h]
  __int64 v84; // [rsp+108h] [rbp+8h]
  __int64 v85; // [rsp+110h] [rbp+10h]
  __int64 v86; // [rsp+120h] [rbp+20h] BYREF
  __int64 v87; // [rsp+130h] [rbp+30h] BYREF
  char v88[104]; // [rsp+138h] [rbp+38h] BYREF
  const WCHAR *v89; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v90; // [rsp+1B8h] [rbp+B8h]
  __int64 v91; // [rsp+1C8h] [rbp+C8h]

  v91 = a4;
  v90 = a2;
  v89 = a1;
  v11 = a9;
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x80u) != 0 )
  {
    if ( a9 )
      v60 = *(unsigned int *)(a9 + 16);
    else
      v60 = 0xFFFFFFFFLL;
    McTemplateU0qq_EventWriteTransfer(a1, MDE_Generate_Nontrans_Res_Element_Start, v60, 0);
    a4 = v91;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqSSSSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)a3, a4, a5, a6, a7, (__int64)Src, v11);
  }
  v75[0] = 0;
  v75[1] = 0;
  v76 = 17;
  v80 = 0xFFFFFFFFLL;
  v81 = 0;
  v82 = 0;
  v83 = 10;
  v84 = 0;
  v85 = 0;
  v77 = 1061158912;
  v78 = 1048576000;
  v79 = 1074790400;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(v75);
  v12 = *(_WORD **)(a2 + 48);
  if ( !v12 || (v13 = 0, !*v12) )
    v13 = 1;
  CDlnaContentFeaturesWriter::CDlnaContentFeaturesWriter((CDlnaContentFeaturesWriter *)&v87, a3, v13);
  ATL::CSimpleStringT<unsigned short,0>::SetString(v88, *(_QWORD *)a2);
  v72 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v71 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v14 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v69 = v14;
  v68 = -1;
  LODWORD(v89) = -1;
  LODWORD(v63) = -1;
  v66 = 0;
  v67 = 0;
  v15 = 0;
  Block = 0;
  v65 = 0;
  LOBYTE(v16) = 1;
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::InitHashTable(
    v75,
    2,
    v16);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    v74,
    *(char **)(a2 + 8));
  v17 = 0;
  ValueFromStringList = 0;
  v19 = -1;
  do
  {
    v62 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    ++v19;
    v20 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v70 = v20;
    ValueFromStringList = GetValueFromStringList(v74, ValueFromStringList, &v62);
    v21 = v62;
    v22 = *(unsigned int *)(v62 - 16);
    if ( (int)v22 > 0 )
    {
      v23 = (_WORD *)v62;
      if ( v62 )
      {
        while ( *v23 )
        {
          if ( *v23 == 61 )
          {
            if ( !v23 || (unsigned int)(((__int64)v23 - v62) >> 1) == -1 )
              break;
            v43 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
                              &v62,
                              &v86,
                              L"=");
            ATL::CSimpleStringT<unsigned short,0>::operator=(&v70, v43);
            ATL::CStringData::Release((ATL::CStringData *)(v86 - 24));
            v20 = v70;
            v44 = *((_DWORD *)v70 - 4);
            if ( v44 )
            {
              v45 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
                                &v62,
                                &lpString2,
                                (unsigned int)(v44 + 1));
              ATL::CSimpleStringT<unsigned short,0>::operator=(&v62, v45);
              ATL::CStringData::Release((ATL::CStringData *)(lpString2 - 12));
              v21 = v62;
            }
            goto LABEL_20;
          }
          ++v23;
        }
      }
    }
    v24 = (_QWORD *)(v62 - 24);
    v25 = (volatile signed __int32 *)(v14 - 24);
    if ( (char *)(v62 - 24) != v14 - 24 )
    {
      if ( *((int *)v25 + 4) >= 0 && *v24 == *(_QWORD *)v25 )
      {
        v26 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v24);
        if ( _InterlockedExchangeAdd(v25 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v25 + 8LL))(*(_QWORD *)v25, v25);
        v14 = (char *)(v26 + 24);
        v69 = v14;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v69, v62, v22);
        v14 = v69;
      }
    }
    LODWORD(v63) = v19;
    v17 = 1;
LABEL_20:
    if ( CompareStringW(0x7Fu, 1u, v20, -1, L"v1.5", -1) == 2 )
    {
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v72, &v62);
      v68 = v19;
    }
    else if ( CompareStringW(0x7Fu, 1u, v20, -1, L"v1.0", -1) == 2 )
    {
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v71, &v62);
      LODWORD(v89) = v19;
    }
    else if ( !v17 )
    {
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v70);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v62);
      v17 = 0;
      continue;
    }
    v17 = 0;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v20 - 3) + 8LL))(*((_QWORD *)v20 - 3));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v21 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v21 - 24) + 8LL))(*(_QWORD *)(v21 - 24));
  }
  while ( ValueFromStringList != -1 );
  LODWORD(v62) = v19;
  WMCResElement = 0;
  v28 = *(_DWORD *)(v90 + 128);
  v29 = (v28 & 4) != 0;
  v30 = v67;
  if ( (v28 & 4) != 0 )
    goto LABEL_29;
  if ( (v28 & 8) != 0 )
    goto LABEL_93;
  v56 = v68;
  if ( v68 == -1 || (v57 = 0, *(_QWORD *)(v90 + 32)) )
  {
    v57 = 1;
    if ( v68 == -1 )
      goto LABEL_93;
  }
  v58 = (_QWORD *)_o__recalloc(0, 1, 8);
  if ( v58 )
  {
    v15 = 1;
    HIDWORD(v67) = 1;
    v66 = v58;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      v58,
      (const void **)&v72);
    v30 = 1;
    LODWORD(v67) = 1;
  }
  v59 = (int *)_o__recalloc(0, 1, 4);
  if ( v59 )
  {
    HIDWORD(v65) = 1;
    Block = v59;
    *v59 = v56;
    LODWORD(v65) = 1;
  }
  if ( v57 == 1 )
  {
LABEL_93:
    if ( (_DWORD)v89 != -1 )
    {
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Add(
        &v66,
        &v71);
      ATL::CSimpleArray<int,ATL::CSimpleArrayEqualHelper<int>>::Add(&Block, &v89);
      v15 = HIDWORD(v67);
      v30 = v67;
      goto LABEL_29;
    }
LABEL_62:
    if ( v30 == v15 )
    {
      if ( v15 )
      {
        v49 = 2 * v30;
        if ( (v30 & 0x40000000) == 0 )
          goto LABEL_65;
      }
      else
      {
        v49 = 1;
LABEL_65:
        if ( v49 <= 0xFFFFFFFuLL )
        {
          v50 = _o__recalloc(v66, v49, 8);
          if ( v50 )
          {
            HIDWORD(v67) = v49;
            v66 = (_QWORD *)v50;
            goto LABEL_68;
          }
        }
      }
    }
    else
    {
LABEL_68:
      v51 = &v66[v30];
      if ( v51 )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
          v51,
          (const void **)&v69);
      LODWORD(v67) = ++v30;
    }
    v52 = (int)v65;
    if ( (_DWORD)v65 == HIDWORD(v65) )
    {
      if ( HIDWORD(v65) )
      {
        v53 = 2 * v65;
        if ( (v65 & 0x40000000) == 0 )
          goto LABEL_74;
      }
      else
      {
        v53 = 1;
LABEL_74:
        if ( v53 <= 0x1FFFFFFFuLL )
        {
          v54 = (void *)_o__recalloc(Block, v53, 4);
          if ( v54 )
          {
            HIDWORD(v65) = v53;
            Block = v54;
            goto LABEL_77;
          }
        }
      }
    }
    else
    {
LABEL_77:
      v55 = (char *)Block + 4 * v52;
      if ( v55 )
        *v55 = v63;
      LODWORD(v65) = v52 + 1;
    }
  }
  else
  {
LABEL_29:
    if ( v29 )
      goto LABEL_62;
  }
  v31 = 0;
  if ( v30 <= 0 )
  {
LABEL_51:
    v46 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      goto LABEL_114;
    v47 = a9;
  }
  else
  {
    v32 = v75[0];
    while ( 1 )
    {
      v63 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      if ( v31 < 0 )
        break;
      v33 = v66[v31];
      v34 = (_QWORD *)(v33 - 24);
      v35 = (int *)(v87 - 24);
      if ( v33 - 24 != v87 - 24 )
      {
        if ( v35[4] >= 0 && *v34 == *(_QWORD *)v35 )
        {
          v36 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v34);
          ATL::CStringData::Release((ATL::CStringData *)v35);
          v87 = v36 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v87, v33, *(unsigned int *)(v33 - 16));
        }
      }
      v37 = v90;
      CDlnaContentFeaturesWriter::ToString(
        (size_t)&v87,
        &v63,
        0,
        (*(_DWORD *)(v90 + 128) & 4) != 0,
        (*(_DWORD *)(v90 + 128) & 8) != 0);
      v89 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      LOBYTE(v38) = 1;
      CDlnaContentFeaturesWriter::ToString(
        (size_t)&v87,
        (__int64 *)&v89,
        v38,
        (*(_DWORD *)(v37 + 128) & 4) != 0,
        (*(_DWORD *)(v37 + 128) & 8) != 0);
      lpString2 = v89;
      v39 = CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>::Hash(v89);
      v41 = v39;
      if ( v32 )
      {
        for ( i = *(_QWORD *)(v32 + 8LL * (v39 % v76)); ; i = *(_QWORD *)(i + 16) )
        {
          if ( !i )
          {
            v37 = v90;
            goto LABEL_45;
          }
          if ( *(_DWORD *)(i + 24) == v41 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, lpString2, -1) == 2 )
            break;
        }
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v89);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v63);
      }
      else
      {
LABEL_45:
        LOBYTE(v40) = 1;
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::SetAt(
          v75,
          v89,
          v40);
        ATL::CStringData::Release((ATL::CStringData *)(v89 - 12));
        if ( *(char *)(v37 + 128) >= 0 || memcmp_0(&MFAudioFormat_WMAudio_Lossless, (const void *)(v37 + 96), 0x10u) )
        {
          if ( v31 >= (int)v65 )
            break;
          WMCResElement = CMDEContentServer::GenerateWMCResElement(
                            v37,
                            v91,
                            a5,
                            a6,
                            0,
                            a7,
                            v63,
                            Src,
                            1,
                            *((_DWORD *)Block + v31),
                            a9);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_dSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              84,
              (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
              v62,
              v63,
              WMCResElement);
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)(v63 - 24));
        v32 = v75[0];
      }
      if ( ++v31 >= v30 )
        goto LABEL_51;
    }
    RaiseException(0xC000008C, 1u, 0, 0);
LABEL_114:
    v47 = a9;
    if ( *((unsigned __int8 *)v46 + 25) >= (((int)WMCResElement >> 31) & 0xFFFFFFFD) + 5 )
      WPP_SF_dq(v46[2], 85, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, WMCResElement, *(_QWORD *)(a9 + 16));
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x80u) != 0 )
  {
    if ( v47 )
      v61 = *(unsigned int *)(v47 + 16);
    else
      v61 = 0xFFFFFFFFLL;
    McTemplateU0qq_EventWriteTransfer(v46, MDE_Generate_Nontrans_Res_Element_Stop, v61, WMCResElement);
  }
  ATL::CStringData::Release((ATL::CStringData *)((char *)v74[0] - 24));
  if ( Block )
    free(Block);
  ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v66);
  ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v71 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v72 - 24));
  CDlnaContentFeaturesWriter::~CDlnaContentFeaturesWriter((CDlnaContentFeaturesWriter *)&v87);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::RemoveAll(v75);
  return WMCResElement;
}

```

## disassembly

```asm
0x140005b38  mov     rax, rsp
0x140005b3b  mov     [rax+18h], rbx
0x140005b3f  mov     [rax+20h], r9
0x140005b43  mov     [rax+10h], rdx
0x140005b47  mov     [rax+8], rcx
0x140005b4b  push    rbp
0x140005b4c  push    rsi
0x140005b4d  push    rdi
0x140005b4e  push    r12
0x140005b50  push    r13
0x140005b52  push    r14
0x140005b54  push    r15
0x140005b56  lea     rbp, [rsp-70h]
0x140005b5b  sub     rsp, 170h
0x140005b62  mov     rbx, r8
0x140005b65  mov     r14, rdx
0x140005b68  mov     esi, 0FFFFFFFFh
0x140005b6d  xor     r15d, r15d
0x140005b70  mov     rdi, [rbp+0A0h+arg_40]
0x140005b77  cmp     byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, r15b
0x140005b7e  jl      loc_140006427
0x140005b84  lea     rax, WPP_GLOBAL_Control
0x140005b8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b92  cmp     rcx, rax
0x140005b95  jnz     loc_140006450
0x140005b9b  mov     [rbp+0A0h+var_D0], r15
0x140005b9f  mov     [rbp+0A0h+var_C8], r15
0x140005ba3  mov     [rbp+0A0h+var_C0], 11h
0x140005baa  mov     [rbp+0A0h+var_B0], rsi
0x140005bae  mov     [rbp+0A0h+var_A8], r15
0x140005bb2  mov     [rbp+0A0h+var_A0], r15d
0x140005bb6  mov     [rbp+0A0h+var_9C], 0Ah
0x140005bbd  mov     [rbp+0A0h+var_98], r15
0x140005bc1  mov     [rbp+0A0h+var_90], r15
0x140005bc5  mov     [rbp+0A0h+var_BC], 3F400000h
0x140005bcc  mov     [rbp+0A0h+var_B8], 3E800000h
0x140005bd3  mov     [rbp+0A0h+var_B4], 40100000h
0x140005bda  lea     rcx, [rbp+0A0h+var_D0]
0x140005bde  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(void)
0x140005be3  nop
0x140005be4  mov     rcx, [r14+30h]
0x140005be8  test    rcx, rcx
0x140005beb  jnz     loc_1400064B4
0x140005bf1  mov     r8b, 1; bool
0x140005bf4  mov     rdx, rbx; struct MDEProfile *
0x140005bf7  lea     rcx, [rbp+0A0h+var_70]; this
0x140005bfb  call    ??0CDlnaContentFeaturesWriter@@QEAA@PEBUMDEProfile@@_N1@Z; CDlnaContentFeaturesWriter::CDlnaContentFeaturesWriter(MDEProfile const *,bool,bool)
0x140005c00  nop
0x140005c01  mov     rdx, [r14]
0x140005c04  lea     rcx, [rbp+0A0h+var_68]
0x140005c08  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x140005c0d  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005c14  lea     rdi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005c1b  mov     rcx, rdi
0x140005c1e  mov     rax, [rax+18h]
0x140005c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c27  add     rax, 18h
0x140005c2b  mov     [rbp+0A0h+var_F0], rax
0x140005c2f  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005c36  mov     rcx, rdi
0x140005c39  mov     rax, [rax+18h]
0x140005c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c42  add     rax, 18h
0x140005c46  mov     [rbp+0A0h+var_F8], rax
0x140005c4a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005c51  mov     rcx, rdi
0x140005c54  mov     rax, [rax+18h]
0x140005c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c5d  lea     rsi, [rax+18h]
0x140005c61  mov     [rbp+0A0h+var_108], rsi
0x140005c65  or      ebx, 0FFFFFFFFh
0x140005c68  mov     [rbp+0A0h+var_110], ebx
0x140005c6b  mov     dword ptr [rbp+0A0h+arg_0], ebx
0x140005c71  mov     dword ptr [rsp+1A0h+var_138], ebx
0x140005c75  mov     [rbp+0A0h+var_120], r15
0x140005c79  mov     [rbp+0A0h+var_118], r15
0x140005c7d  mov     r13d, r15d
0x140005c80  mov     [rsp+1A0h+Block], r15
0x140005c85  mov     [rsp+1A0h+var_128], r15
0x140005c8a  mov     r8b, 1
0x140005c8d  lea     edx, [rbx+3]
0x140005c90  lea     rcx, [rbp+0A0h+var_D0]
0x140005c94  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>>::InitHashTable(uint,bool)
0x140005c99  mov     rdx, [r14+8]
0x140005c9d  lea     rcx, [rbp+0A0h+var_E0]
0x140005ca1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140005ca6  nop
0x140005ca7  xor     r14d, r14d
0x140005caa  mov     r15d, r14d
0x140005cad  mov     r12d, ebx
0x140005cb0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005cb7  mov     rcx, rdi
0x140005cba  mov     rax, [rax+18h]
0x140005cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cc3  add     rax, 18h
0x140005cc7  mov     [rsp+1A0h+var_140], rax
0x140005ccc  inc     r12d
0x140005ccf  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005cd6  mov     rcx, rdi
0x140005cd9  mov     rax, [rax+18h]
0x140005cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ce2  lea     rdi, [rax+18h]
0x140005ce6  mov     [rbp+0A0h+var_100], rdi
0x140005cea  lea     r8, [rsp+1A0h+var_140]
0x140005cef  mov     edx, r15d
0x140005cf2  lea     rcx, [rbp+0A0h+var_E0]
0x140005cf6  call    ?GetValueFromStringList@@YAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@HAEAV12@G@Z; GetValueFromStringList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ushort)
0x140005cfb  mov     r15d, eax
0x140005cfe  mov     rbx, [rsp+1A0h+var_140]
0x140005d03  mov     r8d, [rbx-10h]
0x140005d07  test    r8d, r8d
0x140005d0a  jle     short loc_140005D3A
0x140005d0c  mov     rax, rbx
0x140005d0f  test    rbx, rbx
0x140005d12  jz      short loc_140005D3A
0x140005d14  cmp     [rax], r14w
0x140005d18  jz      short loc_140005D3A
0x140005d1a  cmp     word ptr [rax], 3Dh ; '='
0x140005d1e  jz      short loc_140005D26
0x140005d20  add     rax, 2
0x140005d24  jmp     short loc_140005D14
0x140005d26  test    rax, rax
0x140005d29  jz      short loc_140005D3A
0x140005d2b  sub     rax, rbx
0x140005d2e  sar     rax, 1
0x140005d31  cmp     eax, 0FFFFFFFFh
0x140005d34  jnz     loc_140005FCA
0x140005d3a  lea     rcx, [rbx-18h]
0x140005d3e  lea     r14, [rsi-18h]
0x140005d42  cmp     rcx, r14
0x140005d45  jz      short loc_140005D8E
0x140005d47  cmp     dword ptr [r14+10h], 0
0x140005d4c  jl      loc_1400064C6
0x140005d52  mov     rax, [r14]
0x140005d55  cmp     [rcx], rax
0x140005d58  jnz     loc_1400064C6
0x140005d5e  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140005d63  mov     rsi, rax
0x140005d66  or      ecx, 0FFFFFFFFh
0x140005d69  lock xadd [r14+10h], ecx
0x140005d6f  sub     ecx, 1
0x140005d72  jg      short loc_140005D86
0x140005d74  mov     rcx, [r14]
0x140005d77  mov     r8, [rcx]
0x140005d7a  mov     rdx, r14
0x140005d7d  mov     rax, [r8+8]
0x140005d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d86  add     rsi, 18h
0x140005d8a  mov     [rbp+0A0h+var_108], rsi
0x140005d8e  mov     dword ptr [rsp+1A0h+var_138], r12d
0x140005d93  mov     r14b, 1
0x140005d96  or      ecx, 0FFFFFFFFh
0x140005d99  mov     [rsp+1A0h+cchCount2], ecx; cchCount2
0x140005d9d  lea     rax, aV15; "v1.5"
0x140005da4  mov     [rsp+1A0h+lpString2], rax; lpString2
0x140005da9  mov     r9d, ecx; cchCount1
0x140005dac  mov     r8, rdi; lpString1
0x140005daf  lea     edx, [rcx+2]; dwCmpFlags
0x140005db2  lea     ecx, [rdx+7Eh]; Locale
0x140005db5  call    cs:__imp_CompareStringW
0x140005dbb  cmp     eax, 2
0x140005dbe  jz      loc_140006225
0x140005dc4  or      ecx, 0FFFFFFFFh
0x140005dc7  mov     [rsp+1A0h+cchCount2], ecx; cchCount2
0x140005dcb  lea     rax, aV10; "v1.0"
0x140005dd2  mov     [rsp+1A0h+lpString2], rax; lpString2
0x140005dd7  mov     r9d, ecx; cchCount1
0x140005dda  mov     r8, rdi; lpString1
0x140005ddd  lea     edx, [rcx+2]; dwCmpFlags
0x140005de0  lea     ecx, [rdx+7Eh]; Locale
0x140005de3  call    cs:__imp_CompareStringW
0x140005de9  cmp     eax, 2
0x140005dec  jz      loc_14000623C
0x140005df2  test    r14b, r14b
0x140005df5  jz      loc_1400064DB
0x140005dfb  lea     rdx, [rdi-18h]
0x140005dff  or      eax, 0FFFFFFFFh
0x140005e02  lock xadd [rdx+10h], eax
0x140005e07  xor     r14d, r14d
0x140005e0a  sub     eax, 1
0x140005e0d  jg      short loc_140005E1E
0x140005e0f  mov     rcx, [rdx]
0x140005e12  mov     rax, [rcx]
0x140005e15  mov     rax, [rax+8]
0x140005e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e1e  lea     rdx, [rbx-18h]
0x140005e22  or      eax, 0FFFFFFFFh
0x140005e25  lock xadd [rdx+10h], eax
0x140005e2a  sub     eax, 1
0x140005e2d  jg      short loc_140005E3E
0x140005e2f  mov     rcx, [rdx]
0x140005e32  mov     rax, [rcx]
0x140005e35  mov     rax, [rax+8]
0x140005e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e3e  cmp     r15d, 0FFFFFFFFh
0x140005e42  lea     rdi, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005e49  jnz     loc_140005CB0
0x140005e4f  mov     dword ptr [rsp+1A0h+var_140], r12d
0x140005e54  mov     r15d, r14d
0x140005e57  mov     rdx, [rbp+0A0h+arg_8]
0x140005e5e  mov     ecx, [rdx+80h]
0x140005e64  bt      ecx, 2
0x140005e68  setb    bl
0x140005e6b  bt      ecx, 2
0x140005e6f  mov     r12d, dword ptr [rbp+0A0h+var_118]
0x140005e73  jnb     loc_1400064F6
0x140005e79  cmp     bl, 1
0x140005e7c  jz      loc_140006256
0x140005e82  mov     edi, r14d
0x140005e85  test    r12d, r12d
0x140005e88  jle     loc_140006127
0x140005e8e  mov     r13, [rbp+0A0h+var_D0]
0x140005e92  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005e99  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005ea0  mov     rax, [rax+18h]
0x140005ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ea9  add     rax, 18h
0x140005ead  mov     [rsp+1A0h+var_138], rax
0x140005eb2  test    edi, edi
0x140005eb4  js      loc_14000654E
0x140005eba  movsxd  rax, edi
0x140005ebd  mov     rcx, [rbp+0A0h+var_120]
0x140005ec1  mov     rdx, [rcx+rax*8]
0x140005ec5  lea     rcx, [rdx-18h]
0x140005ec9  mov     r14, [rbp+0A0h+var_70]
0x140005ecd  add     r14, 0FFFFFFFFFFFFFFE8h
0x140005ed1  cmp     rcx, r14
0x140005ed4  jz      short loc_140005F05
0x140005ed6  cmp     dword ptr [r14+10h], 0
0x140005edb  jl      loc_140006504
0x140005ee1  mov     rax, [r14]
0x140005ee4  cmp     [rcx], rax
0x140005ee7  jnz     loc_140006504
0x140005eed  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140005ef2  mov     rbx, rax
0x140005ef5  mov     rcx, r14; this
0x140005ef8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140005efd  lea     rax, [rbx+18h]
0x140005f01  mov     [rbp+0A0h+var_70], rax
0x140005f05  mov     rbx, [rbp+0A0h+arg_8]
0x140005f0c  mov     r9d, [rbx+80h]
0x140005f13  mov     eax, r9d
0x140005f16  shr     eax, 3
0x140005f19  and     al, 1
0x140005f1b  shr     r9d, 2
0x140005f1f  and     r9b, 1
0x140005f23  mov     byte ptr [rsp+1A0h+lpString2], al
0x140005f27  xor     r8d, r8d
0x140005f2a  lea     rdx, [rsp+1A0h+var_138]
0x140005f2f  lea     rcx, [rbp+0A0h+var_70]
0x140005f33  call    ?ToString@CDlnaContentFeaturesWriter@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_N11@Z; CDlnaContentFeaturesWriter::ToString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,bool,bool,bool)
0x140005f38  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005f3f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140005f46  mov     rax, [rax+18h]
0x140005f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f4f  add     rax, 18h
0x140005f53  mov     [rbp+0A0h+arg_0], rax
0x140005f5a  mov     r9d, [rbx+80h]
0x140005f61  mov     eax, r9d
0x140005f64  shr     eax, 3
0x140005f67  and     al, 1
0x140005f69  shr     r9d, 2
0x140005f6d  and     r9b, 1
0x140005f71  mov     byte ptr [rsp+1A0h+lpString2], al
0x140005f75  mov     r8b, 1
0x140005f78  lea     rdx, [rbp+0A0h+arg_0]
0x140005f7f  lea     rcx, [rbp+0A0h+var_70]
0x140005f83  call    ?ToString@CDlnaContentFeaturesWriter@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_N11@Z; CDlnaContentFeaturesWriter::ToString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,bool,bool,bool)
0x140005f88  mov     rax, [rbp+0A0h+arg_0]
0x140005f8f  mov     [rbp+0A0h+var_E8], rax
0x140005f93  mov     rcx, rax
0x140005f96  call    ?Hash@?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@SAKPEBG@Z; CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>::Hash(ushort const *)
0x140005f9b  mov     r14d, eax
0x140005f9e  test    r13, r13
0x140005fa1  jz      loc_140006045
0x140005fa7  xor     edx, edx
0x140005fa9  div     [rbp+0A0h+var_C0]
0x140005fac  mov     rbx, [r13+rdx*8+0]
0x140005fb1  test    rbx, rbx
0x140005fb4  jz      loc_14000603E
0x140005fba  cmp     [rbx+18h], r14d
0x140005fbe  jz      loc_1400061DB
0x140005fc4  mov     rbx, [rbx+10h]
0x140005fc8  jmp     short loc_140005FB1
0x140005fca  lea     r8, asc_1400A28A4; "="
0x140005fd1  lea     rdx, [rbp+0A0h+var_80]
0x140005fd5  lea     rcx, [rsp+1A0h+var_140]
0x140005fda  call    ?SpanExcluding@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::SpanExcluding(ushort const *)
0x140005fdf  mov     rdx, rax
0x140005fe2  lea     rcx, [rbp+0A0h+var_100]
0x140005fe6  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140005feb  mov     rcx, [rbp+0A0h+var_80]
0x140005fef  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x140005ff3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140005ff8  mov     rdi, [rbp+0A0h+var_100]
0x140005ffc  mov     r8d, [rdi-10h]
0x140006000  test    r8d, r8d
0x140006003  jz      loc_140005D96
0x140006009  inc     r8d
0x14000600c  lea     rdx, [rbp+0A0h+var_E8]
  ... truncated ...
```
