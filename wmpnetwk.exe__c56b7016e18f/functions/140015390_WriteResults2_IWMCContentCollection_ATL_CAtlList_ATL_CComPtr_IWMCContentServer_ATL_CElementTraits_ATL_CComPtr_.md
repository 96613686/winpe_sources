# WriteResults2(IWMCContentCollection *,ATL::CAtlList<ATL::CComPtr<IWMCContentServer>,ATL::CElementTraits<ATL::CComPtr<IWMCContentServer>>> const &,IUnknown *,ulong,bool,CdsFilter *,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &,ulong *)

- ea: `0x140015390`
- end: `0x140016169`
- name: `?WriteResults2@@YAJPEAUIWMCContentCollection@@AEBV?$CAtlList@V?$CComPtr@UIWMCContentServer@@@ATL@@V?$CElementTraits@V?$CComPtr@UIWMCContentServer@@@ATL@@@2@@ATL@@PEAUIUnknown@@K_NPEAVCdsFilter@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@3@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@3@PEAK@Z`
- size: `3545`
- prototype: `__int64 __fastcall(int, int, int, int, char, struct CdsFilter *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `33`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140037954`
- `0x14005c690`

## callees

- `0x140003750`
- `0x1400065e0`
- `0x14000a1f8`
- `0x14000c920`
- `0x1400105a0`
- `0x140015100`
- `0x140015230`
- `0x140015390`
- `0x140024688`
- `0x140026200`
- `0x140032304`
- `0x1400329d4`
- `0x1400349bc`
- `0x1400396dc`
- `0x14003b260`
- `0x14003e064`
- `0x14003f17c`
- `0x140046358`
- `0x140046c32`
- `0x140046d00`
- `0x140047798`
- `0x14004a834`
- `0x1400547b0`
- `0x14005a394`
- `0x14005e01c`
- `0x14005e88c`
- `0x14005e9a0`
- `0x14005f04c`
- `0x140064218`
- `0x140066098`
- `0x1400679e0`
- `0x140067b20`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140015625`
- `ADVAPI32!RegCloseKey` at `0x140015625`
- `ADVAPI32!RegOpenKeyExW` at `0x140015474`
- `ADVAPI32!RegOpenKeyExW` at `0x140015474`
- `KERNEL32!GetTickCount` at `0x140015411`
- `KERNEL32!GetTickCount` at `0x14001559a`
- `KERNEL32!GetTickCount` at `0x140015901`
- `KERNEL32!GetTickCount` at `0x140015b5d`
- `KERNEL32!GetTickCount` at `0x140015411`
- `KERNEL32!GetTickCount` at `0x14001559a`
- `KERNEL32!GetTickCount` at `0x140015901`
- `KERNEL32!GetTickCount` at `0x140015b5d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400158b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140015e7e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140015eca`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400158b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140015e7e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140015eca`

## string_xrefs

- `0x14001567e`: `<DIDL-Lite xmlns:dc="http://purl.org/dc/elements/1.1/"\nxmlns:upnp="urn:schemas-upnp-org:metadata-1-0/upnp/"\nxmlns="urn:schemas-upnp-org:metadata-1-0/DIDL-Lite/"\n`
- `0x140015e94`: `xmlns:microsoft="urn:schemas-microsoft-com:WMPNSS-1-0/"\n`
- `0x140015ea8`: `xmlns:dlna="urn:schemas-dlna-org:metadata-1-0/"\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WriteResults2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 a5,
        struct CdsFilter *a6,
        __int64 a7,
        __int64 *a8,
        int *a9)
{
  unsigned int v9; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  int v13; // r13d
  __int64 *v14; // rdi
  const struct CdsFilter *v15; // r15
  HKEY v16; // r14
  unsigned int v17; // ebx
  __int64 v18; // r12
  PVOID *v19; // r10
  PVOID *v20; // rcx
  char v21; // bl
  int v22; // ebx
  __int64 v23; // rsi
  int *v24; // r12
  signed int v25; // esi
  __int64 v26; // rax
  __int64 v27; // rcx
  char v28; // di
  int *v30; // rax
  ATL::CStringData *v31; // rcx
  __int64 v32; // rdx
  int v33; // ecx
  __int64 v34; // r8
  const wchar_t *v35; // rbx
  unsigned __int64 v36; // r14
  unsigned __int64 v37; // r13
  int v38; // esi
  __int64 v39; // rcx
  _OWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  const wchar_t *v43; // r14
  unsigned __int64 v44; // rsi
  unsigned __int64 v45; // r13
  int v46; // ebx
  __int64 v47; // rcx
  wchar_t *v48; // rcx
  int v49; // esi
  __int64 v50; // rdx
  unsigned int v51; // r13d
  const wchar_t *v52; // r14
  unsigned __int64 v53; // rsi
  unsigned __int64 v54; // r15
  int v55; // ebx
  __int64 v56; // rcx
  __int64 v57; // rax
  unsigned int v58; // r14d
  int XmlEscapedUTF8Length; // r13d
  unsigned int i; // r12d
  signed int v61; // ebx
  _DWORD *v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rdx
  __int64 v65; // r8
  struct IWMCUPnPObject *v66; // rbx
  int v67; // r14d
  _QWORD *v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rbx
  unsigned int v71; // edx
  int v72; // ebx
  unsigned int v73; // eax
  int LocalStringIPAddressesList; // eax
  __int64 v75; // rdx
  signed int v76; // ebx
  int v77; // ebx
  __int64 *v78; // rax
  int v79; // r8d
  int v80; // r9d
  int phkResult; // [rsp+20h] [rbp-E0h]
  int v82; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v83; // [rsp+64h] [rbp-9Ch] BYREF
  int v84; // [rsp+68h] [rbp-98h]
  HKEY v85; // [rsp+70h] [rbp-90h] BYREF
  int v86; // [rsp+78h] [rbp-88h]
  _DWORD *v87; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v88; // [rsp+88h] [rbp-78h]
  DWORD TickCount; // [rsp+8Ch] [rbp-74h]
  _QWORD v90[3]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v91; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v92; // [rsp+B8h] [rbp-48h]
  __int128 v93; // [rsp+C0h] [rbp-40h]
  int v94; // [rsp+D0h] [rbp-30h]
  _QWORD *v95[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v96; // [rsp+F0h] [rbp-10h]
  unsigned __int8 v97; // [rsp+F4h] [rbp-Ch]
  __int128 *v99; // [rsp+100h] [rbp+0h]
  unsigned int v100; // [rsp+108h] [rbp+8h]
  struct IWMCUPnPObject *v101; // [rsp+110h] [rbp+10h]
  __int64 v102; // [rsp+118h] [rbp+18h]
  CdsFilter *v103; // [rsp+120h] [rbp+20h]
  _QWORD *v104; // [rsp+128h] [rbp+28h]
  unsigned int v107; // [rsp+188h] [rbp+88h]

  v107 = a4;
  v9 = a4;
  v11 = a2;
  v12 = a1;
  v86 = 0;
  v13 = a5;
  v84 = a5;
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
  {
    McTemplateU0ttq_EventWriteTransfer(a1, (unsigned int)CDS_Objwriter_Write_Result_Start, a5, 0, 0);
    v9 = v107;
    v12 = a1;
    v11 = a2;
  }
  else
  {
    v84 = a5;
  }
  v14 = a8;
  v15 = a6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqIqDdqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v11,
      v12,
      v11,
      *(_QWORD *)(v11 + 16),
      a3,
      v9,
      a5,
      a6,
      a8,
      a9);
  }
  LODWORD(a6) = GetTickCount();
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 10;
  v88 = 204800;
  v16 = 0;
  memset(v90, 0, sizeof(v90));
  v85 = 0;
  v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0", 0, 0x20119u, &v85);
  if ( !v17 )
  {
    v17 = 0;
    v16 = v85;
    v90[0] = v85;
  }
  v18 = 2;
  v19 = (PVOID *)WPP_GLOBAL_Control;
  v20 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v71 = 5;
    if ( v17 )
      v71 = 2;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v71 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids, v17);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( !v17 )
  {
    v83 = 0;
    v72 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v90, L"BrowseSearchSizeOverride", &v83);
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      phkResult = v72;
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids, v83);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v72 )
    {
      v73 = v83;
      if ( !v83 )
        v73 = -1;
      v88 = v73;
    }
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 )
  {
    WPP_SF_(v19[2], 37, WPP_29adc390e0ea3116cfd5ae79a3787614_Traceguids);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  v21 = *((_BYTE *)v15 + 176);
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 5u )
  {
    WPP_SF_d(v19[2], 38, WPP_29adc390e0ea3116cfd5ae79a3787614_Traceguids, *((unsigned __int8 *)v15 + 176));
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v21 == 1 )
  {
    LocalStringIPAddressesList = GetLocalStringIPAddressesList(a7, &v91);
    v22 = LocalStringIPAddressesList;
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LODWORD(v20) = ((LocalStringIPAddressesList >> 31) & 0xFFFFFFFD) + 5;
      if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)v20 )
      {
        phkResult = v92;
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
          (unsigned int)LocalStringIPAddressesList);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    if ( !a7 )
      ATL::AtlThrowImpl(-2147467259);
    v22 = 0;
    v23 = *(_QWORD *)(a7 + 8);
    if ( v23 )
    {
      do
      {
        v75 = *(_QWORD *)(v23 + 16);
        v23 = *(_QWORD *)(v23 + 8);
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::AddHead(
          &v91,
          v75);
      }
      while ( v23 );
      v82 = 0;
      goto LABEL_133;
    }
  }
  v82 = 0;
  if ( v22 < 0 )
  {
LABEL_14:
    v24 = a9;
LABEL_15:
    v25 = -2147220635;
    goto LABEL_28;
  }
LABEL_133:
  v76 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 64LL))(a1, &v82);
  v83 = v76;
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LODWORD(v20) = ((v76 >> 31) & 0xFFFFFFFD) + 5;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)v20 )
    {
      phkResult = v82;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
        (unsigned int)v76);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v76 < 0 )
    goto LABEL_14;
  if ( v82 < 0 )
    v82 = 0;
  v30 = (int *)*v14;
  v31 = (ATL::CStringData *)(*v14 - 24);
  if ( *((_DWORD *)v31 + 2) )
  {
    if ( *((int *)v31 + 4) >= 0 )
    {
      v70 = *(_QWORD *)v31;
      ATL::CStringData::Release(v31);
      *v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70) + 24;
    }
    else
    {
      if ( *(v30 - 3) < 0 )
        goto LABEL_161;
      *(v30 - 4) = 0;
      *(_WORD *)*v14 = 0;
    }
  }
  v32 = (unsigned int)(6000 * v82 + 177);
  v33 = *(_DWORD *)(*v14 - 12) - v32;
  v34 = v33 | (unsigned int)(1 - *(_DWORD *)(*v14 - 8));
  if ( (v33 | (1 - *(_DWORD *)(*v14 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v14, v32);
  v35 = L"<DIDL-Lite xmlns:dc=\"http://purl.org/dc/elements/1.1/\"\r\n"
         "xmlns:upnp=\"urn:schemas-upnp-org:metadata-1-0/upnp/\"\r\n"
         "xmlns=\"urn:schemas-upnp-org:metadata-1-0/DIDL-Lite/\"\r\n";
  v36 = ((__int64)L"<DIDL-Lite xmlns:dc=\"http://purl.org/dc/elements/1.1/\"\r\n"
                   "xmlns:upnp=\"urn:schemas-upnp-org:metadata-1-0/upnp/\"\r\n"
                   "xmlns=\"urn:schemas-upnp-org:metadata-1-0/DIDL-Lite/\"\r\n"
       - *v14) >> 1;
  v37 = *(unsigned int *)(*v14 - 16);
  v38 = v37 + 164;
  if ( (((*(_DWORD *)(*v14 - 12) - (v37 + 164)) | (1 - *(_DWORD *)(*v14 - 8))) & 0x80000000) != 0LL )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v14, (unsigned int)v38);
  v39 = *v14;
  if ( v36 <= v37 )
    v35 = (const wchar_t *)(v39 + 2 * v36);
  v40 = (_OWORD *)(v39 + 2 * v37);
  if ( !v40 )
    goto LABEL_138;
  if ( !v35 )
  {
    memset_0(v40, 0, 0x148u);
LABEL_138:
    *(_DWORD *)_o__errno(v40, v32, v34) = 22;
    invalid_parameter_noinfo();
    goto LABEL_50;
  }
  do
  {
    *v40 = *(_OWORD *)v35;
    v40[1] = *((_OWORD *)v35 + 1);
    v40[2] = *((_OWORD *)v35 + 2);
    v40[3] = *((_OWORD *)v35 + 3);
    v40[4] = *((_OWORD *)v35 + 4);
    v40[5] = *((_OWORD *)v35 + 5);
    v40[6] = *((_OWORD *)v35 + 6);
    v40[7] = *((_OWORD *)v35 + 7);
    v40 += 8;
    v35 += 64;
    --v18;
  }
  while ( v18 );
  *v40 = *(_OWORD *)v35;
  v40[1] = *((_OWORD *)v35 + 1);
  v40[2] = *((_OWORD *)v35 + 2);
  v40[3] = *((_OWORD *)v35 + 3);
  *((_QWORD *)v40 + 8) = *((_QWORD *)v35 + 8);
LABEL_50:
  if ( v38 < 0 || v38 > *(_DWORD *)(*v14 - 12) )
    goto LABEL_161;
  *(_DWORD *)(*v14 - 16) = v38;
  *(_WORD *)(*v14 + 2LL * v38) = 0;
  if ( (*(unsigned __int8 (__fastcall **)(const struct CdsFilter *, __int64, __int64))(*(_QWORD *)v15 + 8LL))(
         v15,
         16,
         v34) )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(v14, L"xmlns:microsoft=\"urn:schemas-microsoft-com:WMPNSS-1-0/\"\r\n");
  }
  if ( (*(unsigned __int8 (__fastcall **)(const struct CdsFilter *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 74)
    || (*(unsigned __int8 (__fastcall **)(const struct CdsFilter *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 72) )
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(v14, L"xmlns:dlna=\"urn:schemas-dlna-org:metadata-1-0/\"\r\n");
  }
  v43 = L">";
  v44 = ((__int64)L">" - *v14) >> 1;
  v45 = *(unsigned int *)(*v14 - 16);
  v46 = v45 + 1;
  if ( (((*(_DWORD *)(*v14 - 12) - (v45 + 1)) | (1 - *(_DWORD *)(*v14 - 8))) & 0x80000000) != 0LL )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v14, (unsigned int)v46);
  v47 = *v14;
  if ( v44 <= v45 )
    v43 = (const wchar_t *)(v47 + 2 * v44);
  v48 = (wchar_t *)(v47 + 2 * v45);
  if ( !v48 )
    goto LABEL_141;
  if ( !v43 )
  {
    *v48 = 0;
LABEL_141:
    *(_DWORD *)_o__errno(v48, v41, v42) = 22;
    invalid_parameter_noinfo();
    goto LABEL_63;
  }
  *v48 = *v43;
LABEL_63:
  if ( v46 < 0 || v46 > *(_DWORD *)(*v14 - 12) )
    goto LABEL_161;
  v49 = 0;
  *(_DWORD *)(*v14 - 16) = v46;
  v50 = v46;
  *(_WORD *)(*v14 + 2LL * v46) = 0;
  if ( v82 > 0 )
  {
    v58 = v107;
    if ( v82 == 1 )
    {
      v58 = v107 & 0xFFFFEFFF;
      v107 &= ~0x1000u;
    }
    TickCount = GetTickCount();
    XmlEscapedUTF8Length = GetXmlEscapedUTF8Length(v14);
    for ( i = 0; i < v82; ++i )
    {
      v85 = 0;
      v61 = (*(__int64 (__fastcall **)(__int64, _QWORD, HKEY *))(*(_QWORD *)a1 + 56LL))(a1, i, &v85);
      v83 = v61;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v61 >> 31) & 0xFFFFFFFD) + 5) )
      {
        WPP_SF_ddq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
          (unsigned int)v61,
          i,
          v85);
      }
      if ( v61 < 0 )
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v85);
        break;
      }
      v62 = (_DWORD *)((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
      v87 = v62 + 6;
      v63 = (v62[3] - 6000) | (unsigned int)(1 - v62[4]);
      if ( (int)v63 < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v87, 6000);
      if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
        McTemplateU0q_EventWriteTransfer(v63, CDS_Objwriter_Write_Object_Start, i);
      CdsObjectWriter::CdsObjectWriter((CdsObjectWriter *)v95);
      v66 = (struct IWMCUPnPObject *)v85;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_IDDdqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v64, v65, v92, phkResult, v58, v84, v85, v15);
      }
      v103 = (CdsFilter *)operator new(0xB8u);
      if ( CdsFilter::CdsFilter(v103, v15) )
      {
        v67 = 0;
        v68 = operator new(0x10u);
        v104 = v68;
        *v68 = &CdsItemInfo::`vftable';
        v68[1] = 0;
        v95[1] = v68;
        CdsItemInfo::Initialize((CdsItemInfo *)v68, v66);
        v99 = &v91;
        v96 = 0;
        v100 = v107;
        v97 = a5;
        v101 = v66;
        (*(void (__fastcall **)(struct IWMCUPnPObject *))(*(_QWORD *)v66 + 8LL))(v66);
        v102 = a2;
      }
      else
      {
        v67 = -2147024882;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v67 >> 31) & 0xFFFFFFFD) + 5) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_dbb15cfc8a373ec782525eb0398c9c07_Traceguids,
          (unsigned int)v67);
      }
      CDidlLiteObjectWriter::WriteObject(v95, (__int64 *)&v87);
      if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
        McTemplateU0q_EventWriteTransfer(v69, CDS_Objwriter_Write_Object_Stop, i);
      v58 = v107;
      if ( *(v87 - 4) )
      {
        if ( (v107 & 0x408) == 0 )
        {
          XmlEscapedUTF8Length += GetXmlEscapedUTF8Length(&v87) + 2;
          if ( XmlEscapedUTF8Length + 12 > v88 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_dddd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                77,
                &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
                i,
                v82,
                XmlEscapedUTF8Length + 12,
                v88);
            }
            CdsObjectWriter::~CdsObjectWriter((CdsObjectWriter *)v95);
            ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v87);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v85);
            break;
          }
        }
        ++v49;
        ATL::CSimpleStringT<unsigned short,0>::Append(v14, (const void **)&v87);
        ATL::CSimpleStringT<unsigned short,0>::Append(v14, L"\r\n");
      }
      CdsObjectWriter::~CdsObjectWriter((CdsObjectWriter *)v95);
      ATL::CStringData::Release((ATL::CStringData *)(v87 - 6));
      if ( v85 )
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v85 + 16LL))(v85);
    }
    GetTickCount();
    v51 = (unsigned int)a6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids,
        TickCount - (unsigned int)a6);
    }
  }
  else
  {
    v51 = (unsigned int)a6;
  }
  v24 = a9;
  *a9 = v49;
  v52 = L"</DIDL-Lite>";
  v53 = ((__int64)L"</DIDL-Lite>" - *v14) >> 1;
  v54 = *(unsigned int *)(*v14 - 16);
  v55 = v54 + 12;
  if ( (((*(_DWORD *)(*v14 - 12) - (v54 + 12)) | (1 - *(_DWORD *)(*v14 - 8))) & 0x80000000) != 0LL )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v14, (unsigned int)v55);
  v56 = *v14;
  if ( v53 <= v54 )
    v52 = (const wchar_t *)(v56 + 2 * v53);
  v57 = v56 + 2 * v54;
  if ( v57 )
  {
    if ( v52 )
    {
      *(_OWORD *)v57 = *(_OWORD *)v52;
      *(_QWORD *)(v57 + 16) = *((_QWORD *)v52 + 2);
      goto LABEL_19;
    }
    v56 = 0;
    *(_OWORD *)v57 = 0;
    *(_QWORD *)(v57 + 16) = 0;
  }
  *(_DWORD *)_o__errno(v56, v50, v42) = 22;
  invalid_parameter_noinfo();
LABEL_19:
  if ( v55 < 0 )
    goto LABEL_161;
  if ( v55 > *(_DWORD *)(*v14 - 12) )
    goto LABEL_161;
  *(_DWORD *)(*v14 - 16) = v55;
  LODWORD(v26) = 0;
  *(_WORD *)(*v14 + 2LL * v55) = 0;
  v27 = *v14;
  if ( *v14 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(v27 + 2 * v26) );
    if ( (int)v26 < 0 )
      goto LABEL_161;
  }
  if ( (int)v26 > *(_DWORD *)(v27 - 12) )
LABEL_161:
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(v27 - 16) = v26;
  *(_WORD *)(*v14 + 2LL * (unsigned int)v26) = 0;
  GetTickCount();
  v19 = (PVOID *)WPP_GLOBAL_Control;
  v20 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_824a16f0d22d333a8f4c6073dd71f265_Traceguids, v51);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  v25 = v83;
  v16 = (HKEY)v90[0];
  v13 = v84;
  if ( (v83 & 0x80000000) != 0 )
    goto LABEL_15;
LABEL_28:
  if ( v19 == &WPP_GLOBAL_Control
    || (*((_BYTE *)v19 + 28) & 1) == 0
    || *((unsigned __int8 *)v19 + 25) < (int)(((v25 >> 31) & 0xFFFFFFFD) + 5) )
  {
    v28 = v86;
  }
  else
  {
    v77 = *v24;
    v78 = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Left(
                       v14,
                       &a6,
                       3900);
    v28 = 1;
    WPP_SF_dSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, v79, v25, *v78, v77);
  }
  if ( (v28 & 1) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&a6);
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
  {
    if ( v24 )
      v80 = *v24;
    else
      v80 = -1;
    McTemplateU0ttq_EventWriteTransfer((_DWORD)v20, (unsigned int)CDS_Objwriter_Write_Result_Stop, v13, v80, v25);
  }
  if ( v16 )
    RegCloseKey(v16);
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v91);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x140015390  mov     [rsp-8+arg_10], rbx
0x140015395  mov     [rsp-8+arg_18], r9d
0x14001539a  mov     [rsp-8+arg_8], rdx
0x14001539f  mov     [rsp-8+arg_0], rcx
0x1400153a4  push    rbp
0x1400153a5  push    rsi
0x1400153a6  push    rdi
0x1400153a7  push    r12
0x1400153a9  push    r13
0x1400153ab  push    r14
0x1400153ad  push    r15
0x1400153af  lea     rbp, [rsp-30h]
0x1400153b4  sub     rsp, 130h
0x1400153bb  mov     eax, r9d
0x1400153be  mov     rbx, r8
0x1400153c1  mov     r8, rdx
0x1400153c4  mov     rdx, rcx
0x1400153c7  xor     esi, esi
0x1400153c9  mov     [rsp+160h+var_E8], esi
0x1400153cd  movzx   r13d, [rbp+60h+arg_20]
0x1400153d5  mov     [rsp+160h+var_F8], r13d
0x1400153da  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x1400153e1  jnz     loc_140015BB6
0x1400153e7  mov     [rsp+160h+var_F8], r13d
0x1400153ec  lea     r9, WPP_GLOBAL_Control
0x1400153f3  mov     rdi, [rbp+60h+arg_38]
0x1400153fa  mov     r15, [rbp+60h+arg_28]
0x140015401  mov     rcx, cs:WPP_GLOBAL_Control
0x140015408  cmp     rcx, r9
0x14001540b  jnz     loc_140015BDF
0x140015411  call    cs:__imp_GetTickCount
0x140015417  mov     dword ptr [rbp+60h+arg_28], eax
0x14001541d  xorps   xmm0, xmm0
0x140015420  movdqu  [rbp+60h+var_B8], xmm0
0x140015425  mov     [rbp+60h+var_A8], rsi
0x140015429  xorps   xmm1, xmm1
0x14001542c  movdqu  [rbp+60h+var_A0], xmm1
0x140015431  mov     [rbp+60h+var_90], 0Ah
0x140015438  mov     [rbp+60h+var_D8], 32000h
0x14001543f  mov     r14, rsi
0x140015442  mov     [rbp+60h+var_D0], rsi
0x140015446  mov     [rbp+60h+var_C8], rsi
0x14001544a  mov     [rbp+60h+var_C0], rsi
0x14001544e  mov     [rsp+160h+var_F0], rsi
0x140015453  lea     rax, [rsp+160h+var_F0]
0x140015458  mov     [rsp+160h+phkResult], rax; phkResult
0x14001545d  mov     r9d, 20119h; samDesired
0x140015463  xor     r8d, r8d; ulOptions
0x140015466  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Media Play"...
0x14001546d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140015474  call    cs:__imp_RegOpenKeyExW
0x14001547a  mov     ebx, eax
0x14001547c  test    eax, eax
0x14001547e  jnz     short loc_14001548B
0x140015480  mov     ebx, esi
0x140015482  mov     r14, [rsp+160h+var_F0]
0x140015487  mov     [rbp+60h+var_D0], r14
0x14001548b  mov     r12d, 2
0x140015491  mov     r10, cs:WPP_GLOBAL_Control
0x140015498  lea     rcx, WPP_GLOBAL_Control
0x14001549f  cmp     r10, rcx
0x1400154a2  jnz     loc_140015C36
0x1400154a8  mov     esi, 0FFFFFFFFh
0x1400154ad  test    ebx, ebx
0x1400154af  jz      loc_140015C7C
0x1400154b5  lea     rsi, WPP_GLOBAL_Control
0x1400154bc  cmp     r10, rsi
0x1400154bf  jnz     loc_140015CF9
0x1400154c5  movzx   ebx, byte ptr [r15+0B0h]
0x1400154cd  cmp     r10, rsi
0x1400154d0  jnz     loc_140015D25
0x1400154d6  cmp     bl, 1
0x1400154d9  jz      loc_140015D5F
0x1400154df  mov     rax, [rbp+60h+arg_30]
0x1400154e6  test    rax, rax
0x1400154e9  jz      short loc_140015519
0x1400154eb  xor     ebx, ebx
0x1400154ed  mov     rsi, [rax+8]
0x1400154f1  test    rsi, rsi
0x1400154f4  jnz     loc_140015DCE
0x1400154fa  xor     esi, esi
0x1400154fc  mov     [rsp+160h+var_100], esi
0x140015500  test    ebx, ebx
0x140015502  jns     loc_140015DE8
0x140015508  mov     r12, [rbp+60h+arg_40]
0x14001550f  mov     esi, 80040365h
0x140015514  jmp     loc_1400155CC
0x140015519  mov     ecx, 80004005h; int
0x14001551e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140015524  test    r14, r14
0x140015527  jz      loc_140016067
0x14001552d  movups  xmm0, xmmword ptr [r14]
0x140015531  movups  xmmword ptr [rax], xmm0
0x140015534  movsd   xmm1, qword ptr [r14+10h]
0x14001553a  movsd   qword ptr [rax+10h], xmm1
0x14001553f  test    ebx, ebx
0x140015541  js      loc_1400160B9
0x140015547  mov     rax, [rdi]
0x14001554a  cmp     ebx, [rax-0Ch]
0x14001554d  jg      loc_1400160B9
0x140015553  mov     [rax-10h], ebx
0x140015556  movsxd  rdx, ebx
0x140015559  mov     rcx, [rdi]
0x14001555c  xor     eax, eax
0x14001555e  mov     [rcx+rdx*2], ax
0x140015562  mov     rcx, [rdi]
0x140015565  test    rcx, rcx
0x140015568  jz      short loc_140015583
0x14001556a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140015571  inc     rax
0x140015574  cmp     word ptr [rcx+rax*2], 0
0x140015579  jnz     short loc_140015571
0x14001557b  test    eax, eax
0x14001557d  js      loc_1400160B9
0x140015583  cmp     eax, [rcx-0Ch]
0x140015586  jg      loc_1400160B9
0x14001558c  mov     [rcx-10h], eax
0x14001558f  mov     edx, eax
0x140015591  mov     rcx, [rdi]
0x140015594  xor     eax, eax
0x140015596  mov     [rcx+rdx*2], ax
0x14001559a  call    cs:__imp_GetTickCount
0x1400155a0  mov     r10, cs:WPP_GLOBAL_Control
0x1400155a7  lea     rcx, WPP_GLOBAL_Control
0x1400155ae  cmp     r10, rcx
0x1400155b1  jnz     loc_140016078
0x1400155b7  mov     esi, [rsp+160h+var_FC]
0x1400155bb  mov     r14, [rbp+60h+var_D0]
0x1400155bf  mov     r13d, [rsp+160h+var_F8]
0x1400155c4  test    esi, esi
0x1400155c6  js      loc_14001550F
0x1400155cc  lea     rax, WPP_GLOBAL_Control
0x1400155d3  cmp     r10, rax
0x1400155d6  jnz     loc_1400160C4
0x1400155dc  mov     edi, [rsp+160h+var_E8]
0x1400155e0  test    dil, 1
0x1400155e4  jnz     loc_14001612E
0x1400155ea  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 20h
0x1400155f1  jnz     loc_14001613F
0x1400155f7  test    r14, r14
0x1400155fa  jnz     short loc_140015622
0x1400155fc  lea     rcx, [rbp+60h+var_B8]
0x140015600  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RemoveAll(void)
0x140015605  mov     eax, esi
0x140015607  mov     rbx, [rsp+160h+arg_10]
0x14001560f  add     rsp, 130h
0x140015616  pop     r15
0x140015618  pop     r14
0x14001561a  pop     r13
0x14001561c  pop     r12
0x14001561e  pop     rdi
0x14001561f  pop     rsi
0x140015620  pop     rbp
0x140015621  retn
0x140015622  mov     rcx, r14; hKey
0x140015625  call    cs:__imp_RegCloseKey
0x14001562b  jmp     short loc_1400155FC
0x14001562d  test    ebx, ebx
0x14001562f  js      loc_140015508
0x140015635  cmp     [rsp+160h+var_100], 0
0x14001563a  jge     short loc_140015640
0x14001563c  mov     [rsp+160h+var_100], esi
0x140015640  mov     rax, [rdi]
0x140015643  lea     rcx, [rax-18h]; this
0x140015647  cmp     dword ptr [rcx+8], 0
0x14001564b  jnz     loc_1400158CF
0x140015651  imul    edx, [rsp+160h+var_100], 1770h
0x140015659  add     edx, 0B1h
0x14001565f  mov     rax, [rdi]
0x140015662  mov     r8d, 1
0x140015668  sub     r8d, [rax-8]
0x14001566c  mov     ecx, [rax-0Ch]
0x14001566f  sub     ecx, edx
0x140015671  or      r8d, ecx
0x140015674  jge     short loc_14001567E
0x140015676  mov     rcx, rdi
0x140015679  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14001567e  lea     rbx, aDidlLiteXmlnsD; "<DIDL-Lite xmlns:dc=\"http://purl.org/d"...
0x140015685  mov     rax, [rdi]
0x140015688  mov     r14, rbx
0x14001568b  sub     r14, rax
0x14001568e  sar     r14, 1
0x140015691  mov     r13d, [rax-10h]
0x140015695  lea     esi, [r13+0A4h]
0x14001569c  mov     ecx, 1
0x1400156a1  sub     ecx, [rax-8]
0x1400156a4  mov     eax, [rax-0Ch]
0x1400156a7  sub     eax, esi
0x1400156a9  or      ecx, eax
0x1400156ab  jge     short loc_1400156B7
0x1400156ad  mov     edx, esi
0x1400156af  mov     rcx, rdi
0x1400156b2  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400156b7  mov     rcx, [rdi]
0x1400156ba  cmp     r14, r13
0x1400156bd  jbe     loc_140015E68
0x1400156c3  lea     rcx, [rcx+r13*2]; void *
0x1400156c7  test    rcx, rcx
0x1400156ca  jz      loc_140015E7E
0x1400156d0  test    rbx, rbx
0x1400156d3  jz      loc_140015E71
0x1400156d9  movups  xmm0, xmmword ptr [rbx]
0x1400156dc  movups  xmmword ptr [rcx], xmm0
0x1400156df  movups  xmm1, xmmword ptr [rbx+10h]
0x1400156e3  movups  xmmword ptr [rcx+10h], xmm1
0x1400156e7  movups  xmm0, xmmword ptr [rbx+20h]
0x1400156eb  movups  xmmword ptr [rcx+20h], xmm0
0x1400156ef  movups  xmm1, xmmword ptr [rbx+30h]
0x1400156f3  movups  xmmword ptr [rcx+30h], xmm1
0x1400156f7  movups  xmm0, xmmword ptr [rbx+40h]
0x1400156fb  movups  xmmword ptr [rcx+40h], xmm0
0x1400156ff  movups  xmm1, xmmword ptr [rbx+50h]
0x140015703  movups  xmmword ptr [rcx+50h], xmm1
0x140015707  movups  xmm0, xmmword ptr [rbx+60h]
0x14001570b  movups  xmmword ptr [rcx+60h], xmm0
0x14001570f  movups  xmm1, xmmword ptr [rbx+70h]
0x140015713  movups  xmmword ptr [rcx+70h], xmm1
0x140015717  lea     rcx, [rcx+80h]
0x14001571e  lea     rbx, [rbx+80h]
0x140015725  sub     r12, 1
0x140015729  jnz     short loc_1400156D9
0x14001572b  movups  xmm0, xmmword ptr [rbx]
0x14001572e  movups  xmmword ptr [rcx], xmm0
0x140015731  movups  xmm1, xmmword ptr [rbx+10h]
0x140015735  movups  xmmword ptr [rcx+10h], xmm1
0x140015739  movups  xmm0, xmmword ptr [rbx+20h]
0x14001573d  movups  xmmword ptr [rcx+20h], xmm0
0x140015741  movups  xmm1, xmmword ptr [rbx+30h]
0x140015745  movups  xmmword ptr [rcx+30h], xmm1
0x140015749  mov     rax, [rbx+40h]
0x14001574d  mov     [rcx+40h], rax
0x140015751  test    esi, esi
0x140015753  js      loc_1400160B9
0x140015759  mov     rax, [rdi]
0x14001575c  cmp     esi, [rax-0Ch]
0x14001575f  jg      loc_1400160B9
0x140015765  mov     [rax-10h], esi
0x140015768  movsxd  rdx, esi
0x14001576b  mov     rcx, [rdi]
0x14001576e  xor     eax, eax
0x140015770  mov     [rcx+rdx*2], ax
0x140015774  mov     rax, [r15]
0x140015777  mov     edx, 10h
0x14001577c  mov     rcx, r15
0x14001577f  mov     rax, [rax+8]
0x140015783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015788  test    al, al
0x14001578a  jnz     loc_140015E94
0x140015790  mov     rax, [r15]
0x140015793  mov     edx, 4Ah ; 'J'
0x140015798  mov     rcx, r15
0x14001579b  mov     rax, [rax+8]
0x14001579f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400157a4  test    al, al
0x1400157a6  jnz     loc_140015EA8
0x1400157ac  mov     rax, [r15]
0x1400157af  mov     edx, 48h ; 'H'
0x1400157b4  mov     rcx, r15
0x1400157b7  mov     rax, [rax+8]
0x1400157bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400157c0  test    al, al
0x1400157c2  jnz     loc_140015EA8
0x1400157c8  lea     r14, asc_1400A3CBC; ">"
0x1400157cf  mov     rax, [rdi]
0x1400157d2  mov     rsi, r14
0x1400157d5  sub     rsi, rax
0x1400157d8  sar     rsi, 1
0x1400157db  mov     r13d, [rax-10h]
0x1400157df  lea     ebx, [r13+1]
0x1400157e3  mov     ecx, 1
0x1400157e8  sub     ecx, [rax-8]
0x1400157eb  mov     eax, [rax-0Ch]
0x1400157ee  sub     eax, ebx
0x1400157f0  or      ecx, eax
0x1400157f2  jge     short loc_1400157FE
0x1400157f4  mov     edx, ebx
0x1400157f6  mov     rcx, rdi
0x1400157f9  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400157fe  mov     rcx, [rdi]
0x140015801  cmp     rsi, r13
0x140015804  jbe     loc_140015EBC
0x14001580a  lea     rcx, [rcx+r13*2]
0x14001580e  test    rcx, rcx
0x140015811  jz      loc_140015ECA
0x140015817  test    r14, r14
0x14001581a  jz      loc_140015EC5
0x140015820  movzx   eax, word ptr [r14]
0x140015824  mov     [rcx], ax
0x140015827  test    ebx, ebx
0x140015829  js      loc_1400160B9
0x14001582f  mov     rax, [rdi]
0x140015832  cmp     ebx, [rax-0Ch]
0x140015835  jg      loc_1400160B9
0x14001583b  xor     esi, esi
0x14001583d  mov     [rax-10h], ebx
0x140015840  movsxd  rdx, ebx
0x140015843  mov     rcx, [rdi]
0x140015846  xor     eax, eax
0x140015848  mov     [rcx+rdx*2], ax
0x14001584c  mov     eax, [rsp+160h+var_100]
  ... truncated ...
```
