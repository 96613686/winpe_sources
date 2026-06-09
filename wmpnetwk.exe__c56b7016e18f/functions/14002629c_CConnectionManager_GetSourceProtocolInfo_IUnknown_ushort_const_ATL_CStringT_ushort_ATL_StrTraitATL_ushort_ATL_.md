# CConnectionManager::GetSourceProtocolInfo(IUnknown *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x14002629c`
- end: `0x140026f6d`
- name: `?GetSourceProtocolInfo@CConnectionManager@@AEAAJPEAUIUnknown@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z`
- size: `3281`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140032a60`
- `0x140059320`

## callees

- `0x140002fd8`
- `0x140003750`
- `0x1400065e0`
- `0x140006d70`
- `0x140009a40`
- `0x14000b3f0`
- `0x14000c920`
- `0x14000c9cc`
- `0x14000cbd0`
- `0x14000dc4c`
- `0x1400105a0`
- `0x140015100`
- `0x14002629c`
- `0x140026f80`
- `0x1400271a4`
- `0x14002c4a0`
- `0x14002c50c`
- `0x14002f87c`
- `0x140034e14`
- `0x14003b610`
- `0x14003c860`
- `0x14003d4b0`
- `0x14003e064`
- `0x14003e5f4`
- `0x14004a79c`
- `0x140054490`
- `0x1400549e0`
- `0x140055eb4`
- `0x14005788c`
- `0x140057af4`
- `0x1400582f8`
- `0x140058900`
- `0x14009e010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14002631f`
- `KERNEL32!EnterCriticalSection` at `0x14002631f`
- `KERNEL32!LeaveCriticalSection` at `0x1400265bf`
- `KERNEL32!LeaveCriticalSection` at `0x1400265bf`
- `KERNEL32!GetTickCount64` at `0x14002668d`
- `KERNEL32!GetTickCount64` at `0x140026f4a`
- `KERNEL32!GetTickCount64` at `0x14002668d`
- `KERNEL32!GetTickCount64` at `0x140026f4a`
- `KERNEL32!CompareStringW` at `0x140026a28`
- `KERNEL32!CompareStringW` at `0x140026a78`
- `KERNEL32!CompareStringW` at `0x140026d7b`
- `KERNEL32!CompareStringW` at `0x140026a28`
- `KERNEL32!CompareStringW` at `0x140026a78`
- `KERNEL32!CompareStringW` at `0x140026d7b`
- `OLEAUT32!__imp_SysFreeString` at `0x140026783`
- `OLEAUT32!__imp_SysFreeString` at `0x140026795`
- `OLEAUT32!__imp_SysFreeString` at `0x140026def`
- `OLEAUT32!__imp_SysFreeString` at `0x140026e8d`
- `OLEAUT32!__imp_SysFreeString` at `0x140026783`
- `OLEAUT32!__imp_SysFreeString` at `0x140026795`
- `OLEAUT32!__imp_SysFreeString` at `0x140026def`
- `OLEAUT32!__imp_SysFreeString` at `0x140026e8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CConnectionManager::GetSourceProtocolInfo(
        __int64 a1,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        __int64 *a4)
{
  __int64 *v4; // r14
  __int64 v7; // r13
  int WMCContentProvider; // r12d
  __int64 v9; // r15
  int v10; // r10d
  __int64 v11; // r9
  int v12; // r10d
  __int64 v13; // r9
  int v14; // r10d
  __int64 v15; // r9
  struct IWMCContentProvider *v16; // rsi
  int v18; // ebx
  int v19; // eax
  int v20; // ecx
  _BYTE *v21; // rdi
  __int64 v22; // rbx
  int v23; // r14d
  unsigned int i; // ebx
  int v25; // eax
  int v26; // edi
  BSTR v27; // r8
  _QWORD *v28; // rbx
  _QWORD *v29; // r12
  __int64 v30; // r14
  int v31; // eax
  int v32; // ebx
  BSTR v33; // r8
  char v34; // r12
  char v35; // di
  PCNZWCH v36; // rbx
  PVOID *v37; // r10
  __int64 v38; // rax
  const WCHAR *v39; // rdi
  __int64 v40; // rdi
  _QWORD *v41; // rax
  PCNZWCH v42; // r14
  unsigned int v43; // eax
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  _WORD *v46; // rax
  __int64 v47; // rax
  const WCHAR *v48; // r8
  __int64 v49; // r8
  __int64 v50; // rdi
  bool v51; // bl
  unsigned int v52; // r14d
  const void **v53; // rax
  _QWORD *v54; // rax
  __int64 v55; // rax
  _QWORD *v56; // rax
  PCNZWCH v57; // rbx
  _QWORD *v58; // rcx
  __int64 v59; // rdx
  _QWORD *v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // [rsp+48h] [rbp-C0h] BYREF
  PCNZWCH v66; // [rsp+50h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-B0h] BYREF
  char *v68; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v69; // [rsp+68h] [rbp-A0h] BYREF
  int v70; // [rsp+6Ch] [rbp-9Ch] BYREF
  unsigned int v71; // [rsp+70h] [rbp-98h]
  int v72; // [rsp+74h] [rbp-94h]
  PCNZWCH lpString1; // [rsp+78h] [rbp-90h] BYREF
  __int64 v74; // [rsp+80h] [rbp-88h] BYREF
  BSTR v75; // [rsp+88h] [rbp-80h] BYREF
  struct IWMCContentProvider *v76; // [rsp+90h] [rbp-78h] BYREF
  void *v77; // [rsp+98h] [rbp-70h] BYREF
  BSTR v78; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v81; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v82; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v83; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v84; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v85; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v86; // [rsp+E0h] [rbp-28h]
  _QWORD *v87; // [rsp+E8h] [rbp-20h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+F0h] [rbp-18h]
  _QWORD v89[2]; // [rsp+F8h] [rbp-10h] BYREF
  int v90; // [rsp+108h] [rbp+0h]
  int v91; // [rsp+10Ch] [rbp+4h]
  int v92; // [rsp+110h] [rbp+8h]
  int v93; // [rsp+114h] [rbp+Ch]
  __int64 v94; // [rsp+118h] [rbp+10h]
  __int64 v95; // [rsp+120h] [rbp+18h]
  int v96; // [rsp+128h] [rbp+20h]
  int v97; // [rsp+12Ch] [rbp+24h]
  __int64 v98; // [rsp+130h] [rbp+28h]
  __int64 v99; // [rsp+138h] [rbp+30h]
  _QWORD v100[2]; // [rsp+148h] [rbp+40h] BYREF
  int v101; // [rsp+158h] [rbp+50h]
  int v102; // [rsp+15Ch] [rbp+54h]
  int v103; // [rsp+160h] [rbp+58h]
  int v104; // [rsp+164h] [rbp+5Ch]
  __int64 v105; // [rsp+168h] [rbp+60h]
  __int64 v106; // [rsp+170h] [rbp+68h]
  int v107; // [rsp+178h] [rbp+70h]
  int v108; // [rsp+17Ch] [rbp+74h]
  __int64 v109; // [rsp+180h] [rbp+78h]
  __int64 v110; // [rsp+188h] [rbp+80h]
  _QWORD v111[2]; // [rsp+198h] [rbp+90h] BYREF
  int v112; // [rsp+1A8h] [rbp+A0h]
  int v113; // [rsp+1ACh] [rbp+A4h]
  int v114; // [rsp+1B0h] [rbp+A8h]
  int v115; // [rsp+1B4h] [rbp+ACh]
  __int64 v116; // [rsp+1B8h] [rbp+B0h]
  __int64 v117; // [rsp+1C0h] [rbp+B8h]
  int v118; // [rsp+1C8h] [rbp+C0h]
  int v119; // [rsp+1CCh] [rbp+C4h]
  __int64 v120; // [rsp+1D0h] [rbp+C8h]
  __int64 v121; // [rsp+1D8h] [rbp+D0h]
  _QWORD v122[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  int v123; // [rsp+1F8h] [rbp+F0h]
  int v124; // [rsp+1FCh] [rbp+F4h]
  int v125; // [rsp+200h] [rbp+F8h]
  int v126; // [rsp+204h] [rbp+FCh]
  __int64 v127; // [rsp+208h] [rbp+100h]
  __int64 v128; // [rsp+210h] [rbp+108h]
  int v129; // [rsp+218h] [rbp+110h]
  int v130; // [rsp+21Ch] [rbp+114h]
  __int64 v131; // [rsp+220h] [rbp+118h]
  __int64 v132; // [rsp+228h] [rbp+120h]
  __int128 v133; // [rsp+238h] [rbp+130h] BYREF
  __int64 v134; // [rsp+248h] [rbp+140h]
  __int128 v135; // [rsp+250h] [rbp+148h]
  int v136; // [rsp+260h] [rbp+158h]
  __int64 v137; // [rsp+268h] [rbp+160h]
  __int128 v138; // [rsp+270h] [rbp+168h] BYREF
  __int64 v139; // [rsp+280h] [rbp+178h]
  __int128 v140; // [rsp+288h] [rbp+180h]
  int v141; // [rsp+298h] [rbp+190h]
  __int64 v142; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int64 *v143; // [rsp+300h] [rbp+1F8h]

  v143 = a4;
  v142 = a1;
  v4 = a4;
  v7 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      (unsigned int)&WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids,
      (_DWORD)a2,
      (__int64)a3);
  }
  WMCContentProvider = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)(v7 + 240);
  EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 240));
  if ( *(_QWORD *)(v7 + 280) )
  {
    v76 = 0;
    v133 = 0;
    v134 = 0;
    v135 = 0;
    v136 = 10;
    v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v74 = v9;
    v122[0] = 0;
    v122[1] = 0;
    v123 = 17;
    v127 = 0xFFFFFFFFLL;
    v128 = 0;
    v129 = 0;
    v130 = 10;
    v131 = 0;
    v132 = 0;
    v124 = 1061158912;
    v125 = 1048576000;
    v126 = 1074790400;
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(v122);
    v111[0] = 0;
    v111[1] = 0;
    v112 = v10;
    v116 = v11;
    v117 = 0;
    v118 = 0;
    v119 = 10;
    v120 = 0;
    v121 = 0;
    v113 = 1061158912;
    v114 = 1048576000;
    v115 = 1074790400;
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(v111);
    v100[0] = 0;
    v100[1] = 0;
    v101 = v12;
    v105 = v13;
    v106 = 0;
    v107 = 0;
    v108 = 10;
    v109 = 0;
    v110 = 0;
    v102 = 1061158912;
    v103 = 1048576000;
    v104 = 1074790400;
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(v100);
    v89[0] = 0;
    v89[1] = 0;
    v90 = v14;
    v94 = v15;
    v95 = 0;
    v96 = 0;
    v97 = 10;
    v98 = 0;
    v99 = 0;
    v91 = 1061158912;
    v92 = 1048576000;
    v93 = 1074790400;
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(v89);
    v69 = 0;
    WMCContentProvider = CMediaServer::GetWMCContentProvider(*(CMediaServer **)(v7 + 280), &v76);
    v16 = v76;
    if ( WMCContentProvider < 0 )
      goto LABEL_11;
    WMCContentProvider = CMediaServer::GetWMCContentServers(*(_QWORD *)(v7 + 280), &v133);
    v72 = WMCContentProvider;
    if ( WMCContentProvider < 0 )
      goto LABEL_11;
    if ( a2 )
    {
      if ( a3 )
      {
        WMCContentProvider = CDeviceShim::GetCompatFlags(a2, a3, &v69);
        v72 = WMCContentProvider;
        if ( WMCContentProvider < 0 )
          goto LABEL_11;
      }
    }
    LODWORD(v65) = 0;
    v18 = 0;
    v19 = (*(__int64 (__fastcall **)(struct IWMCContentProvider *, __int64 *))(*(_QWORD *)v16 + 72LL))(v16, &v65);
    v20 = v65;
    if ( v19 >= 0 )
      LOBYTE(v18) = *(_DWORD *)(v7 + 292) != (_DWORD)v65;
    v21 = (_BYTE *)(v7 + 288);
    if ( *(_DWORD *)(*(_QWORD *)(v7 + 304) - 16LL) && (*v21 || (_BYTE)v69 == 0xFF) )
    {
      if ( !v18 || (v22 = *(_QWORD *)(v7 + 296), GetTickCount64() - v22 <= 0x1D4C0) )
      {
LABEL_11:
        ATL::CSimpleStringT<unsigned short,0>::operator=(v4, (_QWORD *)(v7 + 304));
        goto LABEL_12;
      }
      v20 = v65;
    }
    *v21 = 1;
    *(_DWORD *)(v7 + 292) = v20;
    v23 = 0;
    for ( i = 0; i != 0x7FFFFFFF; ++i )
    {
      bstrString = 0;
      v25 = (*(__int64 (__fastcall **)(struct IWMCContentProvider *, _QWORD, BSTR *, _QWORD))(*(_QWORD *)v16 + 112LL))(
              v16,
              i,
              &bstrString,
              0);
      v26 = v25;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v25 >> 31) & 0xFFFFFFFD) + 5 )
      {
        v27 = L"NULL";
        if ( bstrString )
          v27 = bstrString;
        WPP_SF_dqdS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          (unsigned int)&WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids,
          v25,
          (char)v16,
          i,
          (__int64)v27);
      }
      if ( v26 < 0 )
      {
        SysFreeString(bstrString);
        break;
      }
      if ( v23 )
        ATL::CSimpleStringT<unsigned short,0>::Append(&v74, L",");
      else
        v23 = 1;
      ATL::CSimpleStringT<unsigned short,0>::Append(&v74, bstrString);
      SysFreeString(bstrString);
    }
    v9 = v74;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids, v74);
    }
    if ( !*(_DWORD *)(v9 - 16) || (v28 = (_QWORD *)v133) == 0 )
    {
LABEL_132:
      v142 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
      CConnectionManager::serializeProtocolInfoMap(v61, v122, &v142);
      CConnectionManager::serializeProtocolInfoMap(v62, v100, &v142);
      CConnectionManager::serializeProtocolInfoMap(v63, v111, &v142);
      CConnectionManager::serializeProtocolInfoMap(v64, v89, &v142);
      v4 = v143;
      ATL::CSimpleStringT<unsigned short,0>::operator=(v143, &v142);
      ATL::CSimpleStringT<unsigned short,0>::operator=((_QWORD *)(v7 + 304), &v142);
      *(_QWORD *)(v7 + 296) = GetTickCount64();
      ATL::CStringData::Release((ATL::CStringData *)(v142 - 24));
LABEL_12:
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::RemoveAll(v89);
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::RemoveAll(v100);
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::RemoveAll(v111);
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::RemoveAll(v122);
      ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
      ATL::CAtlList<ATL::CComPtr<IWMCContentServer>,ATL::CElementTraits<ATL::CComPtr<IWMCContentServer>>>::RemoveAll(&v133);
      if ( v16 )
        (*(void (__fastcall **)(struct IWMCContentProvider *))(*(_QWORD *)v16 + 16LL))(v16);
      goto LABEL_14;
    }
    while ( 1 )
    {
      v29 = (_QWORD *)*v28;
      v87 = (_QWORD *)*v28;
      v30 = v28[2];
      v86 = v30;
      v137 = v30;
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
      v75 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, BSTR *))(*(_QWORD *)v30 + 88LL))(v30, v9, v69, &v75);
      v32 = v31;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v31 >> 31) & 0xFFFFFFFD) + 5 )
      {
        v33 = L"NULL";
        if ( v75 )
          v33 = v75;
        WPP_SF_dqSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)v16, v9, (__int64)v33);
      }
      if ( v32 >= 0 )
        break;
LABEL_130:
      v28 = v29;
      SysFreeString(v75);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      if ( !v29 )
      {
        v7 = v142;
        WMCContentProvider = v72;
        goto LABEL_132;
      }
    }
    v34 = 0;
    LODWORD(v65) = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      (void **)&v68,
      (char *)v75);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Tokenize(
      &v68,
      &v66,
      L",",
      &v65);
    v35 = v65;
    v36 = v66;
    v37 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        (unsigned int)&WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids,
        (_DWORD)v66,
        v65);
      v37 = (PVOID *)WPP_GLOBAL_Control;
    }
    while ( 1 )
    {
      if ( !*v36 )
      {
        ATL::CStringData::Release((ATL::CStringData *)(v36 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v68 - 24));
        v9 = v74;
        v30 = v86;
        v29 = v87;
        goto LABEL_130;
      }
      if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 2) != 0 && *((_BYTE *)v37 + 25) >= 5u )
        WPP_SF_Sd(
          (unsigned int)v37[2],
          80,
          (unsigned int)&WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids,
          (_DWORD)v36,
          v35);
      if ( v36 )
      {
        v38 = -1;
        do
          ++v38;
        while ( v36[v38] );
      }
      else
      {
        LODWORD(v38) = 0;
      }
      v39 = &v36[(int)v38];
      if ( 2LL * (int)v38 )
      {
        while ( *v39 != 58 )
        {
          if ( --v39 == v36 )
            goto LABEL_72;
        }
      }
      else
      {
LABEL_72:
        if ( *v39 != 58 )
          goto LABEL_128;
      }
      if ( v39 )
      {
        v40 = v39 - v36;
        if ( (_DWORD)v40 != -1 )
          break;
      }
LABEL_128:
      v60 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Tokenize(
                        &v68,
                        &v85,
                        L",",
                        &v65);
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v66, v60);
      ATL::CStringData::Release((ATL::CStringData *)(v85 - 24));
      v35 = v65;
      v36 = v66;
      v37 = (PVOID *)WPP_GLOBAL_Control;
    }
    v71 = v40 + 1;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
      &v66,
      &lpString1,
      (unsigned int)(v40 + 1));
    v41 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                      &lpString1,
                      &v79,
                      11);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&lpString1, v41);
    ATL::CStringData::Release((ATL::CStringData *)(v79 - 24));
    v42 = lpString1;
    if ( CompareStringW(0x7Fu, 0, lpString1, -1, L"DLNA.ORG_PN", -1) == 2 )
    {
      v43 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Find(
              &v66,
              59,
              (unsigned int)v40);
      if ( v43 != -1 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Truncate(&v66, v43);
        v36 = v66;
      }
      if ( CompareStringW(0x7Fu, 0, v36, 9, L"http-get:", -1) == 2 )
      {
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::SetAt(
          v122,
          v36);
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_127;
        }
        v45 = 81;
      }
      else
      {
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::SetAt(
          v111,
          v36);
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_127;
        }
        v45 = 82;
      }
      WPP_SF_S(v44[2], v45, &WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids, v36);
LABEL_127:
      ATL::CStringData::Release((ATL::CStringData *)(v42 - 12));
      goto LABEL_128;
    }
    if ( *((int *)v36 - 4) > 0 )
    {
      v46 = v36;
      if ( v36 )
      {
        while ( *v46 )
        {
          if ( *v46 == 58 )
          {
            if ( !v46 )
              break;
            v47 = v46 - v36;
            goto LABEL_96;
          }
          ++v46;
        }
      }
      LODWORD(v47) = -1;
LABEL_96:
      if ( (int)v47 + 1 >= 0 && (int)v47 + 1 < *((_DWORD *)v36 - 4) )
      {
        v48 = &v36[(int)v47 + 1];
        if ( v48 )
        {
          while ( *v48 )
          {
            if ( *v48 == 58 )
            {
              if ( !v48 )
                break;
              v49 = v48 - v36;
              goto LABEL_105;
            }
            ++v48;
          }
        }
      }
    }
    LODWORD(v49) = -1;
LABEL_105:
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
      &v66,
      &v80,
      (unsigned int)(v49 + 1),
      (unsigned int)(v40 - (v49 + 1)));
    v138 = 0;
    v139 = 0;
    v140 = 0;
    v141 = 10;
    v78 = 0;
    v50 = v80;
    if ( (*(int (__fastcall **)(struct IWMCContentProvider *, __int64, BSTR *))(*(_QWORD *)v16 + 224LL))(v16, v80, &v78) < 0 )
      goto LABEL_116;
    v51 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v77,
      (char *)v78);
    v70 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Tokenize(
      &v77,
      &bstrString,
      L",",
      &v70);
    if ( (unsigned __int8)ATL::operator!=(&bstrString) )
    {
      v52 = v71;
      do
      {
        if ( (unsigned __int8)ATL::operator!=(&v68) )
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(&v68, 44);
        if ( (unsigned __int8)ATL::operator==(&bstrString, L"*") )
        {
          v34 = 1;
        }
        else
        {
          v53 = (const void **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Mid(
                                 &v66,
                                 &v81,
                                 0,
                                 v52);
          ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&v68, v53);
          ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v81);
          ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&v68, L"DLNA.ORG_PN=");
          ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&v68, (const void **)&bstrString);
        }
        v51 = v34 == 0;
        v54 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Tokenize(
                          &v77,
                          &v82,
                          L",",
                          &v70);
        ATL::CSimpleStringT<unsigned short,0>::operator=(&bstrString, v54);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v82);
      }
      while ( (unsigned __int8)ATL::operator!=(&bstrString) );
      v16 = v76;
      v42 = lpString1;
    }
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&bstrString);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v77);
    v34 = 0;
    if ( !v51 )
    {
LABEL_116:
      v55 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
              &v66,
              &v84,
              v71);
      v56 = (_QWORD *)ATL::operator+(&v83, v55, L"*");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v66, v56);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v83);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v84);
      v57 = v66;
      if ( CompareStringW(0x7Fu, 0, v66, 9, L"http-get:", -1) == 2 )
      {
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::SetAt(
          v100,
          v57);
        v58 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_126;
        }
        v59 = 83;
      }
      else
      {
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::SetAt(
          v89,
          v57);
        v58 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_126;
        }
        v59 = 84;
      }
      WPP_SF_S(v58[2], v59, &WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids, v57);
    }
LABEL_126:
    SysFreeString(v78);
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v138);
    ATL::CStringData::Release((ATL::CStringData *)(v50 - 24));
    goto LABEL_127;
  }
LABEL_14:
  LeaveCriticalSection(lpCriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((WMCContentProvider >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      (unsigned int)&WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids,
      WMCContentProvider,
      *v4);
  }
  return (unsigned int)WMCContentProvider;
}

```

## disassembly

```asm
0x14002629c  mov     rax, rsp
0x14002629f  mov     [rax+10h], rbx
0x1400262a3  mov     [rax+20h], r9
0x1400262a7  mov     [rax+8], rcx
0x1400262ab  push    rbp
0x1400262ac  push    rsi
0x1400262ad  push    rdi
0x1400262ae  push    r12
0x1400262b0  push    r13
0x1400262b2  push    r14
0x1400262b4  push    r15
0x1400262b6  lea     rbp, [rax-1D8h]
0x1400262bd  sub     rsp, 2A0h
0x1400262c4  mov     r14, r9
0x1400262c7  mov     rbx, r8
0x1400262ca  mov     rdi, rdx
0x1400262cd  mov     r13, rcx
0x1400262d0  lea     rax, WPP_GLOBAL_Control
0x1400262d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400262de  cmp     rcx, rax
0x1400262e1  jz      short loc_14002630C
0x1400262e3  test    byte ptr [rcx+1Ch], 1
0x1400262e7  jz      short loc_14002630C
0x1400262e9  cmp     byte ptr [rcx+19h], 5
0x1400262ed  jb      short loc_14002630C
0x1400262ef  mov     edx, 4Bh ; 'K'
0x1400262f4  mov     [rsp+2D0h+lpString2], rbx
0x1400262f9  mov     r9, rdi
0x1400262fc  lea     r8, WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids
0x140026303  mov     rcx, [rcx+10h]
0x140026307  call    WPP_SF_qS
0x14002630c  xor     esi, esi
0x14002630e  mov     r12d, esi
0x140026311  lea     rax, [r13+0F0h]
0x140026318  mov     [rbp+1D0h+lpCriticalSection], rax
0x14002631c  mov     rcx, rax; lpCriticalSection
0x14002631f  call    cs:__imp_EnterCriticalSection
0x140026325  cmp     [r13+118h], rsi
0x14002632c  jz      loc_1400265BB
0x140026332  mov     [rbp+1D0h+var_248], rsi
0x140026336  xorps   xmm0, xmm0
0x140026339  movdqu  [rbp+1D0h+var_A0], xmm0
0x140026341  mov     [rbp+1D0h+var_90], rsi
0x140026348  xorps   xmm1, xmm1
0x14002634b  movdqu  [rbp+1D0h+var_88], xmm1
0x140026353  lea     r12d, [rsi+0Ah]
0x140026357  mov     [rbp+1D0h+var_78], r12d
0x14002635e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140026365  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002636c  mov     rax, [rax+18h]
0x140026370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026375  lea     r15, [rax+18h]
0x140026379  mov     [rsp+2D0h+var_258], r15
0x14002637e  mov     [rbp+1D0h+var_F0], rsi
0x140026385  mov     [rbp+1D0h+var_E8], rsi
0x14002638c  lea     r10d, [rsi+11h]
0x140026390  mov     [rbp+1D0h+var_E0], r10d
0x140026397  mov     r9d, 0FFFFFFFFh
0x14002639d  mov     [rbp+1D0h+var_D0], r9
0x1400263a4  mov     [rbp+1D0h+var_C8], rsi
0x1400263ab  mov     [rbp+1D0h+var_C0], esi
0x1400263b1  mov     [rbp+1D0h+var_BC], r12d
0x1400263b8  mov     [rbp+1D0h+var_B8], rsi
0x1400263bf  mov     [rbp+1D0h+var_B0], rsi
0x1400263c6  mov     [rbp+1D0h+var_DC], 3F400000h
0x1400263d0  mov     [rbp+1D0h+var_D8], 3E800000h
0x1400263da  mov     [rbp+1D0h+var_D4], 40100000h
0x1400263e4  lea     rcx, [rbp+1D0h+var_F0]
0x1400263eb  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(void)
0x1400263f0  nop
0x1400263f1  mov     [rbp+1D0h+var_140], rsi
0x1400263f8  mov     [rbp+1D0h+var_138], rsi
0x1400263ff  mov     [rbp+1D0h+var_130], r10d
0x140026406  mov     [rbp+1D0h+var_120], r9
0x14002640d  mov     [rbp+1D0h+var_118], rsi
0x140026414  mov     [rbp+1D0h+var_110], esi
0x14002641a  mov     [rbp+1D0h+var_10C], r12d
0x140026421  mov     [rbp+1D0h+var_108], rsi
0x140026428  mov     [rbp+1D0h+var_100], rsi
0x14002642f  mov     [rbp+1D0h+var_12C], 3F400000h
0x140026439  mov     [rbp+1D0h+var_128], 3E800000h
0x140026443  mov     [rbp+1D0h+var_124], 40100000h
0x14002644d  lea     rcx, [rbp+1D0h+var_140]
0x140026454  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(void)
0x140026459  nop
0x14002645a  mov     [rbp+1D0h+var_190], rsi
0x14002645e  mov     [rbp+1D0h+var_188], rsi
0x140026462  mov     [rbp+1D0h+var_180], r10d
0x140026466  mov     [rbp+1D0h+var_170], r9
0x14002646a  mov     [rbp+1D0h+var_168], rsi
0x14002646e  mov     [rbp+1D0h+var_160], esi
0x140026471  mov     [rbp+1D0h+var_15C], r12d
0x140026475  mov     [rbp+1D0h+var_158], rsi
0x140026479  mov     [rbp+1D0h+var_150], rsi
0x140026480  mov     [rbp+1D0h+var_17C], 3F400000h
0x140026487  mov     [rbp+1D0h+var_178], 3E800000h
0x14002648e  mov     [rbp+1D0h+var_174], 40100000h
0x140026495  lea     rcx, [rbp+1D0h+var_190]
0x140026499  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(void)
0x14002649e  nop
0x14002649f  mov     [rbp+1D0h+var_1E0], rsi
0x1400264a3  mov     [rbp+1D0h+var_1D8], rsi
0x1400264a7  mov     [rbp+1D0h+var_1D0], r10d
0x1400264ab  mov     [rbp+1D0h+var_1C0], r9
0x1400264af  mov     [rbp+1D0h+var_1B8], rsi
0x1400264b3  mov     [rbp+1D0h+var_1B0], esi
0x1400264b6  mov     [rbp+1D0h+var_1AC], r12d
0x1400264ba  mov     [rbp+1D0h+var_1A8], rsi
0x1400264be  mov     [rbp+1D0h+var_1A0], rsi
0x1400264c2  mov     [rbp+1D0h+var_1CC], 3F400000h
0x1400264c9  mov     [rbp+1D0h+var_1C8], 3E800000h
0x1400264d0  mov     [rbp+1D0h+var_1C4], 40100000h
0x1400264d7  lea     rcx, [rbp+1D0h+var_1E0]
0x1400264db  call    ?UpdateRehashThresholds@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CComPtr@UIWMCContentProvider@@@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CComPtr@UIWMCContentProvider@@@ATL@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CComPtr<IWMCContentProvider>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>,ATL::CElementTraits<ATL::CComPtr<IWMCContentProvider>>>::UpdateRehashThresholds(void)
0x1400264e0  nop
0x1400264e1  mov     [rsp+2D0h+var_270], esi
0x1400264e5  lea     rdx, [rbp+1D0h+var_248]; struct IWMCContentProvider **
0x1400264e9  mov     rcx, [r13+118h]; this
0x1400264f0  call    ?GetWMCContentProvider@CMediaServer@@QEAAJPEAPEAUIWMCContentProvider@@@Z; CMediaServer::GetWMCContentProvider(IWMCContentProvider * *)
0x1400264f5  mov     r12d, eax
0x1400264f8  mov     rsi, [rbp+1D0h+var_248]
0x1400264fc  test    eax, eax
0x1400264fe  js      short loc_140026551
0x140026500  lea     rdx, [rbp+1D0h+var_A0]
0x140026507  mov     rcx, [r13+118h]
0x14002650e  call    ?GetWMCContentServers@CMediaServer@@QEAAJAEAV?$CAtlList@V?$CComPtr@UIWMCContentServer@@@ATL@@V?$CElementTraits@V?$CComPtr@UIWMCContentServer@@@ATL@@@2@@ATL@@@Z; CMediaServer::GetWMCContentServers(ATL::CAtlList<ATL::CComPtr<IWMCContentServer>,ATL::CElementTraits<ATL::CComPtr<IWMCContentServer>>> &)
0x140026513  mov     r12d, eax
0x140026516  mov     dword ptr [rsp+2D0h+var_268+4], eax
0x14002651a  test    eax, eax
0x14002651c  js      short loc_140026551
0x14002651e  test    rdi, rdi
0x140026521  jz      loc_140026630
0x140026527  test    rbx, rbx
0x14002652a  jz      loc_140026630
0x140026530  lea     r8, [rsp+2D0h+var_270]; unsigned int *
0x140026535  mov     rdx, rbx; unsigned __int16 *
0x140026538  mov     rcx, rdi; struct IUnknown *
0x14002653b  call    ?GetCompatFlags@CDeviceShim@@SAJPEAUIUnknown@@PEBGPEAK@Z; CDeviceShim::GetCompatFlags(IUnknown *,ushort const *,ulong *)
0x140026540  mov     r12d, eax
0x140026543  mov     dword ptr [rsp+2D0h+var_268+4], eax
0x140026547  xor     edi, edi
0x140026549  test    eax, eax
0x14002654b  jns     loc_140026632
0x140026551  lea     rdx, [r13+130h]
0x140026558  mov     rcx, r14
0x14002655b  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140026560  nop
0x140026561  lea     rcx, [rbp+1D0h+var_1E0]
0x140026565  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@EV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@E@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,uchar,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<uchar>>::RemoveAll(void)
0x14002656a  nop
0x14002656b  lea     rcx, [rbp+1D0h+var_190]
0x14002656f  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@EV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@E@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,uchar,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<uchar>>::RemoveAll(void)
0x140026574  nop
0x140026575  lea     rcx, [rbp+1D0h+var_140]
0x14002657c  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@EV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@E@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,uchar,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<uchar>>::RemoveAll(void)
0x140026581  nop
0x140026582  lea     rcx, [rbp+1D0h+var_F0]
0x140026589  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@EV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@E@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,uchar,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<uchar>>::RemoveAll(void)
0x14002658e  nop
0x14002658f  lea     rcx, [r15-18h]; this
0x140026593  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x140026598  nop
0x140026599  lea     rcx, [rbp+1D0h+var_A0]
0x1400265a0  call    ?RemoveAll@?$CAtlList@V?$CComPtr@UIWMCContentServer@@@ATL@@V?$CElementTraits@V?$CComPtr@UIWMCContentServer@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CComPtr<IWMCContentServer>,ATL::CElementTraits<ATL::CComPtr<IWMCContentServer>>>::RemoveAll(void)
0x1400265a5  nop
0x1400265a6  test    rsi, rsi
0x1400265a9  jz      short loc_1400265BB
0x1400265ab  mov     rax, [rsi]
0x1400265ae  mov     rcx, rsi
0x1400265b1  mov     rax, [rax+10h]
0x1400265b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400265ba  nop
0x1400265bb  mov     rcx, [rbp+1D0h+lpCriticalSection]; lpCriticalSection
0x1400265bf  call    cs:__imp_LeaveCriticalSection
0x1400265c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400265cc  lea     rax, WPP_GLOBAL_Control
0x1400265d3  cmp     rcx, rax
0x1400265d6  jz      short loc_140026612
0x1400265d8  test    byte ptr [rcx+1Ch], 1
0x1400265dc  jz      short loc_140026612
0x1400265de  mov     edx, r12d
0x1400265e1  sar     edx, 1Fh
0x1400265e4  and     edx, 0FFFFFFFDh
0x1400265e7  add     edx, 5
0x1400265ea  movzx   eax, byte ptr [rcx+19h]
0x1400265ee  cmp     eax, edx
0x1400265f0  jb      short loc_140026612
0x1400265f2  mov     edx, 55h ; 'U'
0x1400265f7  mov     rax, [r14]
0x1400265fa  mov     [rsp+2D0h+lpString2], rax
0x1400265ff  mov     r9d, r12d
0x140026602  lea     r8, WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids
0x140026609  mov     rcx, [rcx+10h]
0x14002660d  call    WPP_SF_dS
0x140026612  mov     eax, r12d
0x140026615  mov     rbx, [rsp+2D0h+arg_8]
0x14002661d  add     rsp, 2A0h
0x140026624  pop     r15
0x140026626  pop     r14
0x140026628  pop     r13
0x14002662a  pop     r12
0x14002662c  pop     rdi
0x14002662d  pop     rsi
0x14002662e  pop     rbp
0x14002662f  retn
0x140026630  xor     edi, edi
0x140026632  mov     dword ptr [rsp+2D0h+var_290], edi
0x140026636  mov     ebx, edi
0x140026638  mov     rax, [rsi]
0x14002663b  lea     rdx, [rsp+2D0h+var_290]
0x140026640  mov     rcx, rsi
0x140026643  mov     rax, [rax+48h]
0x140026647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002664c  mov     ecx, dword ptr [rsp+2D0h+var_290]
0x140026650  test    eax, eax
0x140026652  js      short loc_14002665E
0x140026654  cmp     [r13+124h], ecx
0x14002665b  setnz   bl
0x14002665e  lea     rdi, [r13+120h]
0x140026665  mov     rax, [r13+130h]
0x14002666c  xor     edx, edx
0x14002666e  cmp     [rax-10h], edx
0x140026671  jz      short loc_1400266A6
0x140026673  cmp     [rdi], dl
0x140026675  jnz     short loc_14002667E
0x140026677  cmp     byte ptr [rsp+2D0h+var_270], 0FFh
0x14002667c  jnz     short loc_1400266A6
0x14002667e  test    ebx, ebx
0x140026680  jz      loc_140026551
0x140026686  mov     rbx, [r13+128h]
0x14002668d  call    cs:__imp_GetTickCount64
0x140026693  sub     rax, rbx
0x140026696  cmp     rax, 1D4C0h
0x14002669c  jbe     loc_140026551
0x1400266a2  mov     ecx, dword ptr [rsp+2D0h+var_290]
0x1400266a6  mov     byte ptr [rdi], 1
0x1400266a9  mov     [r13+124h], ecx
0x1400266b0  xor     edi, edi
0x1400266b2  mov     r14d, edi
0x1400266b5  mov     ebx, edi
0x1400266b7  lea     r15, WPP_GLOBAL_Control
0x1400266be  cmp     ebx, 7FFFFFFFh
0x1400266c4  jge     loc_14002679D
0x1400266ca  mov     [rsp+2D0h+bstrString], rdi
0x1400266cf  mov     rax, [rsi]
0x1400266d2  xor     r9d, r9d
0x1400266d5  lea     r8, [rsp+2D0h+bstrString]
0x1400266da  mov     edx, ebx
0x1400266dc  mov     rcx, rsi
0x1400266df  mov     rax, [rax+70h]
0x1400266e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400266e8  mov     edi, eax
0x1400266ea  mov     r10, cs:WPP_GLOBAL_Control
0x1400266f1  cmp     r10, r15
0x1400266f4  jz      short loc_14002674A
0x1400266f6  test    byte ptr [r10+1Ch], 2
0x1400266fb  jz      short loc_14002674A
0x1400266fd  mov     ecx, eax
0x1400266ff  sar     ecx, 1Fh
0x140026702  and     ecx, 0FFFFFFFDh
0x140026705  add     ecx, 5
0x140026708  movzx   eax, byte ptr [r10+19h]
0x14002670d  cmp     eax, ecx
0x14002670f  jb      short loc_14002674A
0x140026711  lea     r8, aNull_0; "NULL"
0x140026718  mov     rax, [rsp+2D0h+bstrString]
0x14002671d  test    rax, rax
0x140026720  cmovnz  r8, rax
0x140026724  mov     edx, 4Ch ; 'L'
0x140026729  mov     [rsp+30h], r8
0x14002672e  mov     [rsp+2D0h+cchCount2], ebx
0x140026732  mov     [rsp+2D0h+lpString2], rsi
0x140026737  mov     r9d, edi
0x14002673a  lea     r8, WPP_3ea60de7e99b317d3a0375edce31d359_Traceguids
0x140026741  mov     rcx, [r10+10h]
0x140026745  call    WPP_SF_dqdS
0x14002674a  test    edi, edi
0x14002674c  js      short loc_140026790
0x14002674e  xor     edi, edi
0x140026750  test    r14d, r14d
0x140026753  jz      short loc_140026768
0x140026755  lea     rdx, asc_1400A3E98; ","
0x14002675c  lea     rcx, [rsp+2D0h+var_258]
0x140026761  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x140026766  jmp     short loc_14002676E
0x140026768  mov     r14d, 1
0x14002676e  mov     rdx, [rsp+2D0h+bstrString]
0x140026773  lea     rcx, [rsp+2D0h+var_258]
0x140026778  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14002677d  nop
0x14002677e  mov     rcx, [rsp+2D0h+bstrString]; bstrString
0x140026783  call    cs:__imp_SysFreeString
0x140026789  inc     ebx
0x14002678b  jmp     loc_1400266BE
0x140026790  mov     rcx, [rsp+2D0h+bstrString]; bstrString
0x140026795  call    cs:__imp_SysFreeString
0x14002679b  xor     edi, edi
0x14002679d  mov     r15, [rsp+2D0h+var_258]
0x1400267a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400267a9  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
