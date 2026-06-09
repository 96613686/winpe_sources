# CMDEContentServer::AddDLNAProtocolInfoForGetProtocolInfo(ushort const *,CDlnaContentFeaturesWriter *,ulong,ushort const *,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,uchar,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<uchar>> &)

- ea: `0x140007388`
- end: `0x140007ab2`
- name: `?AddDLNAProtocolInfoForGetProtocolInfo@CMDEContentServer@@CAXPEBGPEAVCDlnaContentFeaturesWriter@@K0AEAV?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@EV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@E@2@@ATL@@@Z`
- size: `1834`
- prototype: `void __fastcall(PCNZWCH lpString1, _QWORD *, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004160`

## callees

- `0x140002fd8`
- `0x1400065e0`
- `0x140006d70`
- `0x140007388`
- `0x140007ab8`
- `0x14000900c`
- `0x14000b3f0`
- `0x14000c920`
- `0x140013a20`
- `0x140018df0`
- `0x1400396dc`
- `0x14003e5f4`
- `0x140047798`
- `0x1400906a0`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14000746a`
- `KERNEL32!CompareStringW` at `0x14000753f`
- `KERNEL32!CompareStringW` at `0x1400075d9`
- `KERNEL32!CompareStringW` at `0x1400077ee`
- `KERNEL32!CompareStringW` at `0x1400078d6`
- `KERNEL32!CompareStringW` at `0x140007949`
- `KERNEL32!CompareStringW` at `0x14000746a`
- `KERNEL32!CompareStringW` at `0x14000753f`
- `KERNEL32!CompareStringW` at `0x1400075d9`
- `KERNEL32!CompareStringW` at `0x1400077ee`
- `KERNEL32!CompareStringW` at `0x1400078d6`
- `KERNEL32!CompareStringW` at `0x140007949`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140007a7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140007a7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMDEContentServer::AddDLNAProtocolInfoForGetProtocolInfo(
        PCNZWCH lpString1,
        _QWORD *a2,
        char a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v7; // rbx
  void **v8; // rsi
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // r15
  wchar_t *v15; // rdx
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // r15
  unsigned __int64 v20; // r14
  unsigned __int64 v21; // rdi
  unsigned __int64 v22; // r15
  unsigned __int64 v23; // rdi
  unsigned __int64 v24; // r15
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // r15
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // r15
  unsigned __int64 v29; // rdi
  unsigned __int64 v30; // r15
  unsigned __int64 v31; // rdi
  unsigned __int64 v32; // r15
  unsigned __int64 v33; // r14
  const wchar_t *v34; // rdx
  unsigned __int64 v35; // r15
  char v36; // r14
  bool v37; // r13
  int v38; // r9d
  int v39; // r8d
  PVOID *v40; // rcx
  unsigned __int64 i; // r14
  __int64 v42; // [rsp+40h] [rbp-30h] BYREF
  __int64 v43; // [rsp+48h] [rbp-28h] BYREF
  void *Block; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v45; // [rsp+58h] [rbp-18h]
  unsigned __int64 v46; // [rsp+60h] [rbp-10h]
  int v47; // [rsp+68h] [rbp-8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SqDSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)a2, a3, a4, a5);
  }
  v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v43 = v7;
  v42 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v8 = 0;
  Block = 0;
  v9 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"audio/x-ms-wma", -1) == 2 )
  {
    if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                             &Block,
                             1) )
      goto LABEL_55;
    v8 = (void **)Block;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      (void **)Block,
      (char *)L"WMABASE");
    v10 = v45 + 1;
    v45 = v10;
    v11 = v10;
    v12 = v46;
    if ( v10 >= v46 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v10 + 1) )
        goto LABEL_55;
      v12 = v46;
      v10 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v11],
      (char *)L"WMAFULL");
    v13 = v10 + 1;
    v45 = v13;
    v14 = v13;
    if ( v13 < v12 )
    {
LABEL_13:
      v15 = L"WMAPRO";
LABEL_53:
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v8[v14],
        (char *)v15);
      v9 = v13 + 1;
      goto LABEL_54;
    }
    if ( (unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                            &Block,
                            v13 + 1) )
    {
      v13 = v45;
      v8 = (void **)Block;
      goto LABEL_13;
    }
LABEL_55:
    ATL::AtlThrowImpl(-2147024882);
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"audio/mpeg", -1) == 2 )
  {
    if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                             &Block,
                             1) )
      goto LABEL_55;
    v8 = (void **)Block;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      (void **)Block,
      (char *)L"MP3X");
    v16 = v45 + 1;
    v45 = v16;
    v17 = v16;
    if ( v16 >= v46 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v16 + 1) )
        goto LABEL_55;
      v16 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v17],
      (char *)L"MP3");
    v9 = v16 + 1;
LABEL_54:
    v45 = v9;
    goto LABEL_61;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"video/x-ms-wmv", -1) == 2 )
  {
    if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                             &Block,
                             1) )
      goto LABEL_55;
    v8 = (void **)Block;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      (void **)Block,
      (char *)L"WMVSPLL_BASE");
    v18 = v45 + 1;
    v45 = v18;
    v19 = v18;
    v20 = v46;
    if ( v18 >= v46 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v18 + 1) )
        goto LABEL_55;
      v20 = v46;
      v18 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v19],
      (char *)L"WMVSPML_BASE");
    v21 = v18 + 1;
    v45 = v21;
    v22 = v21;
    if ( v21 >= v20 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v21 + 1) )
        goto LABEL_55;
      v20 = v46;
      v21 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v22],
      (char *)L"WMVSPML_MP3");
    v23 = v21 + 1;
    v45 = v23;
    v24 = v23;
    if ( v23 >= v20 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v23 + 1) )
        goto LABEL_55;
      v20 = v46;
      v23 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v24],
      (char *)L"WMVMED_BASE");
    v25 = v23 + 1;
    v45 = v25;
    v26 = v25;
    if ( v25 >= v20 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v25 + 1) )
        goto LABEL_55;
      v20 = v46;
      v25 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v26],
      (char *)L"WMVMED_FULL");
    v27 = v25 + 1;
    v45 = v27;
    v28 = v27;
    if ( v27 >= v20 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v27 + 1) )
        goto LABEL_55;
      v20 = v46;
      v27 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v28],
      (char *)L"WMVMED_PRO");
    v29 = v27 + 1;
    v45 = v29;
    v30 = v29;
    if ( v29 >= v20 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v29 + 1) )
        goto LABEL_55;
      v20 = v46;
      v29 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v30],
      (char *)L"WMVHIGH_FULL");
    v13 = v29 + 1;
    v45 = v13;
    v14 = v13;
    if ( v13 >= v20 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v13 + 1) )
        goto LABEL_55;
      v13 = v45;
      v8 = (void **)Block;
    }
    v15 = L"WMVHIGH_PRO";
    goto LABEL_53;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"video/x-ms-asf", -1) == 2 )
  {
    if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                             &Block,
                             1) )
      goto LABEL_55;
    v8 = (void **)Block;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      (void **)Block,
      (char *)L"MPEG4_P2_ASF_SP_G726");
    v31 = v45 + 1;
    v45 = v31;
    v32 = v31;
    v33 = v46;
    if ( v31 >= v46 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v31 + 1) )
        goto LABEL_55;
      v33 = v46;
      v31 = v45;
      v8 = (void **)Block;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &v8[v32],
      (char *)L"MPEG4_P2_ASF_ASP_L4_SO_G726");
    v13 = v31 + 1;
    v45 = v13;
    v14 = v13;
    if ( v13 >= v33 )
    {
      if ( !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(
                               &Block,
                               v13 + 1) )
        goto LABEL_55;
      v13 = v45;
      v8 = (void **)Block;
    }
    v15 = L"MPEG4_P2_ASF_ASP_L5_SO_G726";
    goto LABEL_53;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"video/mpeg", -1) == 2 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Add(
      &Block,
      L"MPEG_PS_NTSC_XAC3");
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Add(
      &Block,
      L"MPEG_PS_NTSC");
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Add(
      &Block,
      L"MPEG_PS_PAL_XAC3");
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Add(
      &Block,
      L"MPEG_PS_PAL");
    v34 = L"MPEG1";
  }
  else
  {
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"image/png", -1) != 2 )
      goto LABEL_61;
    v34 = L"PNG_LRG";
  }
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Add(
    &Block,
    v34);
  v8 = (void **)Block;
  v9 = v45;
LABEL_61:
  v35 = 0;
  if ( v9 )
  {
    v36 = (a3 & 8) != 0;
    v37 = (a3 & 4) != 0;
    do
    {
      ATL::CSimpleStringT<unsigned short,0>::operator=(a2, &v8[v35]);
      LOBYTE(v38) = v37;
      LOBYTE(v39) = 1;
      CDlnaContentFeaturesWriter::ToString((_DWORD)a2, (unsigned int)&v42, v39, v38, v36);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
        &v43,
        L"%ls:*:%ls:%ls",
        a4,
        lpString1,
        v42);
      v7 = v43;
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::SetAt(
        a5,
        v43);
      v40 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, v7);
        v40 = (PVOID *)WPP_GLOBAL_Control;
      }
      ++v35;
    }
    while ( v35 < v9 );
  }
  else
  {
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 1) != 0 )
    WPP_SF_(v40[2], 108, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids);
  if ( v8 )
  {
    for ( i = 0; i < v9; ++i )
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v8[i]);
    free(v8);
  }
  ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
}

```

## disassembly

```asm
0x140007388  mov     r11, rsp
0x14000738b  mov     [r11+8], rbx
0x14000738f  mov     [r11+20h], r9
0x140007393  mov     [r11+10h], rdx
0x140007397  push    rbp
0x140007398  push    rsi
0x140007399  push    rdi
0x14000739a  push    r12
0x14000739c  push    r13
0x14000739e  push    r14
0x1400073a0  push    r15
0x1400073a2  mov     rbp, rsp
0x1400073a5  sub     rsp, 70h
0x1400073a9  mov     r13d, r8d
0x1400073ac  mov     rax, rdx
0x1400073af  mov     r12, rcx
0x1400073b2  lea     rdx, WPP_GLOBAL_Control
0x1400073b9  mov     r15d, 1
0x1400073bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073c6  cmp     rcx, rdx
0x1400073c9  jz      short loc_1400073F8
0x1400073cb  test    [rcx+1Ch], r15b
0x1400073cf  jz      short loc_1400073F8
0x1400073d1  cmp     byte ptr [rcx+19h], 5
0x1400073d5  jb      short loc_1400073F8
0x1400073d7  mov     rdx, [rbp+arg_20]
0x1400073db  mov     [r11-70h], rdx
0x1400073df  mov     [r11-78h], r9
0x1400073e3  mov     [r11-80h], r8d
0x1400073e7  mov     [rsp+70h+lpString2], rax; char
0x1400073ec  mov     r9, r12
0x1400073ef  mov     rcx, [rcx+10h]; LoggerHandle
0x1400073f3  call    WPP_SF_SqDSq
0x1400073f8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400073ff  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007406  mov     rax, [rax+18h]
0x14000740a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000740f  lea     rbx, [rax+18h]
0x140007413  mov     [rbp+var_28], rbx
0x140007417  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000741e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140007425  mov     rax, [rax+18h]
0x140007429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000742e  add     rax, 18h
0x140007432  mov     [rbp+var_30], rax
0x140007436  xor     esi, esi
0x140007438  mov     [rbp+Block], rsi
0x14000743c  xor     edi, edi
0x14000743e  mov     [rbp+var_18], rdi
0x140007442  mov     [rbp+var_10], rsi
0x140007446  mov     [rbp+var_8], esi
0x140007449  or      r14d, 0FFFFFFFFh
0x14000744d  mov     [rsp+70h+cchCount2], r14d; cchCount2
0x140007452  lea     rax, aAudioXMsWma; "audio/x-ms-wma"
0x140007459  mov     [rsp+70h+lpString2], rax; lpString2
0x14000745e  mov     r9d, r14d; cchCount1
0x140007461  mov     r8, r12; lpString1
0x140007464  mov     edx, r15d; dwCmpFlags
0x140007467  lea     ecx, [rsi+7Fh]; Locale
0x14000746a  call    cs:__imp_CompareStringW
0x140007470  cmp     eax, 2
0x140007473  jnz     loc_140007520
0x140007479  mov     rdx, r15
0x14000747c  lea     rcx, [rbp+Block]
0x140007480  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007485  test    al, al
0x140007487  jz      loc_1400078AC
0x14000748d  lea     rdx, aWmabase; "WMABASE"
0x140007494  mov     rsi, [rbp+Block]
0x140007498  mov     rcx, rsi
0x14000749b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400074a0  mov     rdi, [rbp+var_18]
0x1400074a4  add     rdi, r15
0x1400074a7  mov     [rbp+var_18], rdi
0x1400074ab  mov     r15, rdi
0x1400074ae  mov     r14, [rbp+var_10]
0x1400074b2  cmp     rdi, r14
0x1400074b5  jb      short loc_1400074D8
0x1400074b7  lea     rdx, [rdi+1]
0x1400074bb  lea     rcx, [rbp+Block]
0x1400074bf  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x1400074c4  test    al, al
0x1400074c6  jz      loc_1400078AC
0x1400074cc  mov     r14, [rbp+var_10]
0x1400074d0  mov     rdi, [rbp+var_18]
0x1400074d4  mov     rsi, [rbp+Block]
0x1400074d8  lea     rcx, [rsi+r15*8]
0x1400074dc  lea     rdx, aWmafull; "WMAFULL"
0x1400074e3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400074e8  inc     rdi
0x1400074eb  mov     [rbp+var_18], rdi
0x1400074ef  mov     r15, rdi
0x1400074f2  cmp     rdi, r14
0x1400074f5  jb      short loc_140007514
0x1400074f7  lea     rdx, [rdi+1]
0x1400074fb  lea     rcx, [rbp+Block]
0x1400074ff  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007504  test    al, al
0x140007506  jz      loc_1400078AC
0x14000750c  mov     rdi, [rbp+var_18]
0x140007510  mov     rsi, [rbp+Block]
0x140007514  lea     rdx, aWmapro; "WMAPRO"
0x14000751b  jmp     loc_140007897
0x140007520  mov     [rsp+70h+cchCount2], r14d; cchCount2
0x140007525  lea     rax, aAudioMpeg; "audio/mpeg"
0x14000752c  mov     [rsp+70h+lpString2], rax; lpString2
0x140007531  mov     r9d, r14d; cchCount1
0x140007534  mov     r8, r12; lpString1
0x140007537  mov     edx, r15d; dwCmpFlags
0x14000753a  mov     ecx, 7Fh; Locale
0x14000753f  call    cs:__imp_CompareStringW
0x140007545  cmp     eax, 2
0x140007548  jnz     short loc_1400075BA
0x14000754a  mov     rdx, r15
0x14000754d  lea     rcx, [rbp+Block]
0x140007551  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007556  test    al, al
0x140007558  jz      loc_1400078AC
0x14000755e  lea     rdx, aMp3x; "MP3X"
0x140007565  mov     rsi, [rbp+Block]
0x140007569  mov     rcx, rsi
0x14000756c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140007571  mov     rdi, [rbp+var_18]
0x140007575  add     rdi, r15
0x140007578  mov     [rbp+var_18], rdi
0x14000757c  mov     r14, rdi
0x14000757f  cmp     rdi, [rbp+var_10]
0x140007583  jb      short loc_1400075A2
0x140007585  lea     rdx, [rdi+1]
0x140007589  lea     rcx, [rbp+Block]
0x14000758d  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007592  test    al, al
0x140007594  jz      loc_1400078AC
0x14000759a  mov     rdi, [rbp+var_18]
0x14000759e  mov     rsi, [rbp+Block]
0x1400075a2  lea     rcx, [rsi+r14*8]
0x1400075a6  lea     rdx, aMp3; "MP3"
0x1400075ad  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400075b2  add     rdi, r15
0x1400075b5  jmp     loc_1400078A3
0x1400075ba  mov     [rsp+70h+cchCount2], r14d; cchCount2
0x1400075bf  lea     rax, aVideoXMsWmv; "video/x-ms-wmv"
0x1400075c6  mov     [rsp+70h+lpString2], rax; lpString2
0x1400075cb  mov     r9d, r14d; cchCount1
0x1400075ce  mov     r8, r12; lpString1
0x1400075d1  mov     edx, r15d; dwCmpFlags
0x1400075d4  mov     ecx, 7Fh; Locale
0x1400075d9  call    cs:__imp_CompareStringW
0x1400075df  cmp     eax, 2
0x1400075e2  jnz     loc_1400077CF
0x1400075e8  mov     rdx, r15
0x1400075eb  lea     rcx, [rbp+Block]
0x1400075ef  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x1400075f4  test    al, al
0x1400075f6  jz      loc_1400078AC
0x1400075fc  lea     rdx, aWmvspllBase; "WMVSPLL_BASE"
0x140007603  mov     rsi, [rbp+Block]
0x140007607  mov     rcx, rsi
0x14000760a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14000760f  mov     rdi, [rbp+var_18]
0x140007613  add     rdi, r15
0x140007616  mov     [rbp+var_18], rdi
0x14000761a  mov     r15, rdi
0x14000761d  mov     r14, [rbp+var_10]
0x140007621  cmp     rdi, r14
0x140007624  jb      short loc_140007647
0x140007626  lea     rdx, [rdi+1]
0x14000762a  lea     rcx, [rbp+Block]
0x14000762e  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007633  test    al, al
0x140007635  jz      loc_1400078AC
0x14000763b  mov     r14, [rbp+var_10]
0x14000763f  mov     rdi, [rbp+var_18]
0x140007643  mov     rsi, [rbp+Block]
0x140007647  lea     rcx, [rsi+r15*8]
0x14000764b  lea     rdx, aWmvspmlBase; "WMVSPML_BASE"
0x140007652  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140007657  inc     rdi
0x14000765a  mov     [rbp+var_18], rdi
0x14000765e  mov     r15, rdi
0x140007661  cmp     rdi, r14
0x140007664  jb      short loc_140007687
0x140007666  lea     rdx, [rdi+1]
0x14000766a  lea     rcx, [rbp+Block]
0x14000766e  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007673  test    al, al
0x140007675  jz      loc_1400078AC
0x14000767b  mov     r14, [rbp+var_10]
0x14000767f  mov     rdi, [rbp+var_18]
0x140007683  mov     rsi, [rbp+Block]
0x140007687  lea     rcx, [rsi+r15*8]
0x14000768b  lea     rdx, aWmvspmlMp3; "WMVSPML_MP3"
0x140007692  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140007697  inc     rdi
0x14000769a  mov     [rbp+var_18], rdi
0x14000769e  mov     r15, rdi
0x1400076a1  cmp     rdi, r14
0x1400076a4  jb      short loc_1400076C7
0x1400076a6  lea     rdx, [rdi+1]
0x1400076aa  lea     rcx, [rbp+Block]
0x1400076ae  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x1400076b3  test    al, al
0x1400076b5  jz      loc_1400078AC
0x1400076bb  mov     r14, [rbp+var_10]
0x1400076bf  mov     rdi, [rbp+var_18]
0x1400076c3  mov     rsi, [rbp+Block]
0x1400076c7  lea     rcx, [rsi+r15*8]
0x1400076cb  lea     rdx, aWmvmedBase; "WMVMED_BASE"
0x1400076d2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400076d7  inc     rdi
0x1400076da  mov     [rbp+var_18], rdi
0x1400076de  mov     r15, rdi
0x1400076e1  cmp     rdi, r14
0x1400076e4  jb      short loc_140007707
0x1400076e6  lea     rdx, [rdi+1]
0x1400076ea  lea     rcx, [rbp+Block]
0x1400076ee  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x1400076f3  test    al, al
0x1400076f5  jz      loc_1400078AC
0x1400076fb  mov     r14, [rbp+var_10]
0x1400076ff  mov     rdi, [rbp+var_18]
0x140007703  mov     rsi, [rbp+Block]
0x140007707  lea     rcx, [rsi+r15*8]
0x14000770b  lea     rdx, aWmvmedFull; "WMVMED_FULL"
0x140007712  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140007717  inc     rdi
0x14000771a  mov     [rbp+var_18], rdi
0x14000771e  mov     r15, rdi
0x140007721  cmp     rdi, r14
0x140007724  jb      short loc_140007747
0x140007726  lea     rdx, [rdi+1]
0x14000772a  lea     rcx, [rbp+Block]
0x14000772e  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007733  test    al, al
0x140007735  jz      loc_1400078AC
0x14000773b  mov     r14, [rbp+var_10]
0x14000773f  mov     rdi, [rbp+var_18]
0x140007743  mov     rsi, [rbp+Block]
0x140007747  lea     rcx, [rsi+r15*8]
0x14000774b  lea     rdx, aWmvmedPro; "WMVMED_PRO"
0x140007752  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140007757  inc     rdi
0x14000775a  mov     [rbp+var_18], rdi
0x14000775e  mov     r15, rdi
0x140007761  cmp     rdi, r14
0x140007764  jb      short loc_140007787
0x140007766  lea     rdx, [rdi+1]
0x14000776a  lea     rcx, [rbp+Block]
0x14000776e  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007773  test    al, al
0x140007775  jz      loc_1400078AC
0x14000777b  mov     r14, [rbp+var_10]
0x14000777f  mov     rdi, [rbp+var_18]
0x140007783  mov     rsi, [rbp+Block]
0x140007787  lea     rcx, [rsi+r15*8]
0x14000778b  lea     rdx, aWmvhighFull; "WMVHIGH_FULL"
0x140007792  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140007797  inc     rdi
0x14000779a  mov     [rbp+var_18], rdi
0x14000779e  mov     r15, rdi
0x1400077a1  cmp     rdi, r14
0x1400077a4  jb      short loc_1400077C3
0x1400077a6  lea     rdx, [rdi+1]
0x1400077aa  lea     rcx, [rbp+Block]
0x1400077ae  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x1400077b3  test    al, al
0x1400077b5  jz      loc_1400078AC
0x1400077bb  mov     rdi, [rbp+var_18]
0x1400077bf  mov     rsi, [rbp+Block]
0x1400077c3  lea     rdx, aWmvhighPro; "WMVHIGH_PRO"
0x1400077ca  jmp     loc_140007897
0x1400077cf  mov     [rsp+70h+cchCount2], r14d; cchCount2
0x1400077d4  lea     rax, aVideoXMsAsf; "video/x-ms-asf"
0x1400077db  mov     [rsp+70h+lpString2], rax; lpString2
0x1400077e0  mov     r9d, r14d; cchCount1
0x1400077e3  mov     r8, r12; lpString1
0x1400077e6  mov     edx, r15d; dwCmpFlags
0x1400077e9  mov     ecx, 7Fh; Locale
0x1400077ee  call    cs:__imp_CompareStringW
0x1400077f4  cmp     eax, 2
0x1400077f7  jnz     loc_1400078B7
0x1400077fd  mov     rdx, r15
0x140007800  lea     rcx, [rbp+Block]
0x140007804  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
0x140007809  test    al, al
0x14000780b  jz      loc_1400078AC
0x140007811  lea     rdx, aMpeg4P2AsfSpG7; "MPEG4_P2_ASF_SP_G726"
0x140007818  mov     rsi, [rbp+Block]
0x14000781c  mov     rcx, rsi
0x14000781f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140007824  mov     rdi, [rbp+var_18]
0x140007828  add     rdi, r15
0x14000782b  mov     [rbp+var_18], rdi
0x14000782f  mov     r15, rdi
0x140007832  mov     r14, [rbp+var_10]
0x140007836  cmp     rdi, r14
0x140007839  jb      short loc_140007858
0x14000783b  lea     rdx, [rdi+1]
0x14000783f  lea     rcx, [rbp+Block]
0x140007843  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIHMELibraryMonitorEventHandler@@$1?_GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>,ATL::CComQIPtrElementTraits<IHMELibraryMonitorEventHandler,&__s_GUID const _GUID_b21579aa_2fbe_4816_8426_b87a28feb5dc>>::GrowBuffer(unsigned __int64)
  ... truncated ...
```
