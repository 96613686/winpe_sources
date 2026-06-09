# CContentContextMenuCB::s_DoDeleteThreadProc(void *)

- ea: `0x180016780`
- end: `0x18001771d`
- name: `?s_DoDeleteThreadProc@CContentContextMenuCB@@SAKPEAX@Z`
- size: `3997`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `39`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004110`
- `0x1800050d0`
- `0x180005460`
- `0x1800082e0`
- `0x18000c180`
- `0x18000d610`
- `0x180014b60`
- `0x180015484`
- `0x18001561c`
- `0x180015730`
- `0x180016260`
- `0x180016780`
- `0x180017724`
- `0x180028ea8`
- `0x180028f54`
- `0x180029730`
- `0x180029bac`
- `0x18002d41c`
- `0x18002d474`
- `0x18002d56c`
- `0x18002d648`
- `0x18002d708`
- `0x18002ff5c`
- `0x180030054`
- `0x180032298`
- `0x18003291c`
- `0x180035590`
- `0x180039654`
- `0x180047160`
- `0x18004864c`
- `0x180048f50`
- `0x18004921c`
- `0x1800535f8`
- `0x180053794`
- `0x180053fd8`
- `0x180054524`
- `0x1800545c8`
- `0x18006b954`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180016b27`
- `KERNEL32!Sleep` at `0x180016d18`
- `KERNEL32!Sleep` at `0x180016ed3`
- `KERNEL32!Sleep` at `0x18001700c`
- `KERNEL32!Sleep` at `0x1800170c4`
- `KERNEL32!Sleep` at `0x180016b27`
- `KERNEL32!Sleep` at `0x180016d18`
- `KERNEL32!Sleep` at `0x180016ed3`
- `KERNEL32!Sleep` at `0x18001700c`
- `KERNEL32!Sleep` at `0x1800170c4`
- `KERNEL32!QueryPerformanceCounter` at `0x18001685c`
- `KERNEL32!QueryPerformanceCounter` at `0x18001685c`
- `KERNEL32!GetCurrentThreadId` at `0x180016a83`
- `KERNEL32!GetCurrentThreadId` at `0x180016ad4`
- `KERNEL32!GetCurrentThreadId` at `0x180016a83`
- `KERNEL32!GetCurrentThreadId` at `0x180016ad4`
- `SHLWAPI!StrCmpIW` at `0x1800172c1`
- `SHLWAPI!StrCmpIW` at `0x1800172c1`
- `ole32!CoUninitialize` at `0x180017619`
- `ole32!CoUninitialize` at `0x180017619`
- `ole32!PropVariantClear` at `0x1800172f4`
- `ole32!PropVariantClear` at `0x18001751c`
- `ole32!PropVariantClear` at `0x1800172f4`
- `ole32!PropVariantClear` at `0x18001751c`
- `ole32!CoCreateInstance` at `0x180016c60`
- `ole32!CoCreateInstance` at `0x180016def`
- `ole32!CoCreateInstance` at `0x180016c60`
- `ole32!CoCreateInstance` at `0x180016def`

## string_xrefs

- `0x1800167b0`: `DeleteItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CContentContextMenuCB::s_DoDeleteThreadProc(LPVOID lpThreadParameter)
{
  int v2; // r14d
  CProgressUI *v3; // rsi
  int v4; // edi
  _DWORD *v5; // rax
  int PortableDeviceProperties; // ebx
  int v7; // eax
  const struct std::nothrow_t *v8; // rdx
  unsigned int v9; // r9d
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rcx
  bool v13; // zf
  int v14; // r15d
  CProgressUI *v15; // rax
  CProgressUI *v16; // rax
  CProgressUI *v17; // r13
  CProgressUI *v18; // rsi
  _QWORD *v19; // rax
  __int64 v20; // rdx
  CProgressUI *v21; // r14
  int v22; // ebx
  DWORD v23; // eax
  int v24; // r15d
  int v25; // r14d
  int IsDelegateFolder; // ebx
  DWORD CurrentThreadId; // eax
  _QWORD *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rax
  __int64 v31; // rdx
  int v32; // r15d
  int v33; // r14d
  unsigned int v34; // r13d
  int v35; // r15d
  int v36; // r14d
  unsigned int i; // r13d
  int v38; // r15d
  int v39; // r14d
  int v40; // r15d
  int v41; // r14d
  int v42; // r15d
  struct IPortableDeviceProperties *v43; // r14
  CContentFolder *v44; // rcx
  int v45; // eax
  struct CProgressUI *v46; // rax
  int v47; // eax
  __int64 v48; // r15
  CContentFolder *v49; // rcx
  const struct CONTENTITEM *v50; // rax
  const struct CONTENTITEM *v51; // r14
  _QWORD *v52; // rax
  __int64 v53; // rdx
  unsigned int v54; // edx
  int ppv; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+30h] [rbp-D0h]
  CProgressUI *v58; // [rsp+38h] [rbp-C8h]
  struct IPortableDevice *v59; // [rsp+40h] [rbp-C0h] BYREF
  CProgressUI *v60; // [rsp+48h] [rbp-B8h]
  int v61; // [rsp+50h] [rbp-B0h] BYREF
  int v62; // [rsp+54h] [rbp-ACh]
  struct IPortableDevicePropVariantCollection *v63; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v64; // [rsp+60h] [rbp-A0h] BYREF
  int v65; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v66; // [rsp+70h] [rbp-90h] BYREF
  __int64 v67; // [rsp+78h] [rbp-88h] BYREF
  int v68; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v69; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v70; // [rsp+88h] [rbp-78h]
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  struct IPortableDeviceProperties *v72; // [rsp+98h] [rbp-68h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h] BYREF
  PROPVARIANT psz1; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v75; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v76; // [rsp+C8h] [rbp-38h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v78; // [rsp+E0h] [rbp-20h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  char v80; // [rsp+F8h] [rbp-8h]
  void **v81; // [rsp+100h] [rbp+0h] BYREF
  char v82[272]; // [rsp+108h] [rbp+8h] BYREF
  char v83[8]; // [rsp+218h] [rbp+118h] BYREF
  char v84[48]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v85[264]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v86[264]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v87[264]; // [rsp+670h] [rbp+570h] BYREF
  unsigned __int16 v88[264]; // [rsp+880h] [rbp+780h] BYREF
  WCHAR psz2[264]; // [rsp+A90h] [rbp+990h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CF8h] [rbp+BF8h]

  wil::ActivityBase<WpdTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WpdTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v81,
    "DeleteItem");
  v81 = &WpdTelemetry::DeleteItem::`vftable';
  WpdTelemetry::DeleteItem::StartActivity((WpdTelemetry::DeleteItem *)&v81);
  v2 = -2147467259;
  v75 = 0;
  v76 = 0;
  v80 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v78 = 0;
  v79 = 0;
  v3 = 0;
  v61 = 0;
  v65 = 1;
  v4 = 1;
  v69 = 0;
  v59 = 0;
  v67 = 0;
  v72 = 0;
  v66 = 0;
  v64 = 0;
  v73 = 0;
  v71 = 0;
  v63 = 0;
  memset(&psz1, 0, sizeof(psz1));
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    v75 = 11;
    v76 = 0;
    v78 = 0;
    v80 = 1;
  }
  v5 = (_DWORD *)*((_QWORD *)lpThreadParameter + 5);
  if ( !v5 || !*v5 )
  {
    PortableDeviceProperties = -2147418113;
    goto LABEL_184;
  }
  v7 = SHCoInitialize();
  v2 = v7;
  v57 = v7;
  if ( v7 < 0 )
  {
    PortableDeviceProperties = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_216;
    v10 = 405;
    v11 = (unsigned int)v7;
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    goto LABEL_10;
  }
  v13 = (*((_DWORD *)lpThreadParameter + 4) & 0x400) == 0;
  v14 = *((_DWORD *)lpThreadParameter + 4) & 0x400;
  v62 = v14;
  v4 = v13;
  PortableDeviceProperties = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, __int64))(**((_QWORD **)lpThreadParameter
                                                                                               + 3)
                                                                                            + 96LL))(
                               *((_QWORD *)lpThreadParameter + 3),
                               v87,
                               260);
  if ( PortableDeviceProperties < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_216;
    v10 = 406;
    v11 = (unsigned int)PortableDeviceProperties;
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_10:
    WPP_SF_d(v12, v10, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v11);
    goto LABEL_216;
  }
  v15 = (CProgressUI *)operator new(0xB08u, v8);
  v60 = v15;
  if ( !v15 )
  {
    v3 = 0;
LABEL_213:
    PortableDeviceProperties = -2147024882;
    goto LABEL_216;
  }
  v16 = CProgressUI::CProgressUI(v15);
  v17 = v16;
  v60 = v16;
  if ( !v16 )
  {
    v3 = 0;
    goto LABEL_213;
  }
  *((_QWORD *)lpThreadParameter + 4) = v16;
  v18 = v16;
  if ( !v14 )
  {
    PortableDeviceProperties = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**((_QWORD **)lpThreadParameter + 3) + 144LL))(
                                 *((_QWORD *)lpThreadParameter + 3),
                                 *(_QWORD *)(*((_QWORD *)lpThreadParameter + 3) + 64LL),
                                 v88,
                                 260);
    if ( PortableDeviceProperties >= 0 )
    {
      PortableDeviceProperties = CProgressUI::_Initialize(v17, v88);
      if ( PortableDeviceProperties >= 0 )
      {
        PortableDeviceProperties = CProgressUI::_BeginProgressUI(v17, SPACTION_RECYCLING, 0x6Fu);
        if ( PortableDeviceProperties >= 0 )
          goto LABEL_33;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_24:
          v21 = v17;
          goto LABEL_207;
        }
        v20 = 409;
      }
      else
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_24;
        v20 = 408;
      }
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_24;
      v20 = 407;
    }
    WPP_SF_d(v19[2], v20, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)PortableDeviceProperties);
    goto LABEL_24;
  }
  v18 = 0;
LABEL_33:
  if ( v18 )
  {
    v24 = 0;
    v25 = 0;
    v58 = v17;
    while ( !*((_DWORD *)v18 + 26) )
    {
      IsDelegateFolder = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)lpThreadParameter + 3));
      CurrentThreadId = GetCurrentThreadId();
      PortableDeviceProperties = CDeviceCache::s_BindToPortableDevice(
                                   v87,
                                   CurrentThreadId,
                                   0,
                                   0,
                                   IsDelegateFolder,
                                   &v59);
      if ( PortableDeviceProperties != -2147024726 )
        goto LABEL_43;
      if ( !v24 )
      {
        v24 = 1;
        v25 = 1;
        CProgressUI::_StartMarquee(v18);
      }
      if ( *((_DWORD *)v18 + 26) )
        break;
      Sleep(0x5DCu);
    }
    PortableDeviceProperties = -2147023673;
LABEL_43:
    if ( v25 )
      CProgressUI::_StopMarquee(v18);
    if ( *((_DWORD *)v18 + 26) )
    {
      PortableDeviceProperties = -2147023673;
      goto LABEL_49;
    }
    v14 = v62;
  }
  else
  {
    v22 = CBaseFolder::_IsDelegateFolder(*((CBaseFolder **)lpThreadParameter + 3));
    v23 = GetCurrentThreadId();
    PortableDeviceProperties = CDeviceCache::s_BindToPortableDevice(v87, v23, 0, 0, v22, &v59);
    v58 = v17;
  }
  v21 = v17;
  if ( PortableDeviceProperties < 0 )
  {
LABEL_49:
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_53;
    v29 = 410;
LABEL_52:
    WPP_SF_d(v28[2], v29, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)PortableDeviceProperties);
LABEL_53:
    v21 = v58;
    goto LABEL_207;
  }
  if ( !v14 )
  {
    PortableDeviceProperties = CProgressUI::_AssociateDevice(v17, v59);
    if ( PortableDeviceProperties < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          411,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)PortableDeviceProperties);
      v3 = v17;
LABEL_183:
      v2 = v57;
      goto LABEL_184;
    }
  }
  PortableDeviceProperties = GetPortableDeviceProperties(v59, &v72);
  if ( PortableDeviceProperties < 0 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_207;
    v31 = 412;
    goto LABEL_64;
  }
  PortableDeviceProperties = CoCreateInstance(
                               &CLSID_PortableDeviceKeyCollection,
                               0,
                               1u,
                               &GUID_dada2357_e0ad_492e_98db_dd61c53ba353,
                               &v66);
  if ( PortableDeviceProperties < 0 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_207;
    v31 = 413;
LABEL_64:
    WPP_SF_d(v30[2], v31, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)PortableDeviceProperties);
    goto LABEL_207;
  }
  (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)v66 + 40LL))(v66, &WPD_OBJECT_CAN_DELETE);
  if ( v18 )
  {
    v32 = 0;
    v33 = 0;
    while ( !*((_DWORD *)v18 + 26) )
    {
      PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v59->lpVtbl->Capabilities)(
                                   v59,
                                   &v67);
      if ( PortableDeviceProperties != -2147024726 )
        goto LABEL_79;
      if ( !v32 )
      {
        v32 = 1;
        v33 = 1;
        CProgressUI::_StartMarquee(v18);
      }
      if ( *((_DWORD *)v18 + 26) )
        break;
      Sleep(0x5DCu);
    }
    PortableDeviceProperties = -2147023673;
LABEL_79:
    if ( v33 )
      CProgressUI::_StopMarquee(v18);
    if ( *((_DWORD *)v18 + 26) )
    {
      PortableDeviceProperties = -2147023673;
      goto LABEL_84;
    }
  }
  else
  {
    PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v59->lpVtbl->Capabilities)(
                                 v59,
                                 &v67);
  }
  if ( PortableDeviceProperties < 0 )
  {
LABEL_84:
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_53;
    v29 = 414;
    goto LABEL_52;
  }
  v34 = 0;
  v70 = 0;
  if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int64 *))(*(_QWORD *)v67 + 32LL))(
         v67,
         &WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS,
         &v71) >= 0 )
  {
    v68 = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v71 + 192LL))(
           v71,
           &WPD_OPTION_OBJECT_MANAGEMENT_RECURSIVE_DELETE_SUPPORTED,
           &v68) >= 0 )
    {
      v34 = v68 != 0;
      v70 = v34;
    }
  }
  PortableDeviceProperties = CoCreateInstance(
                               &CLSID_PortableDevicePropVariantCollection,
                               0,
                               1u,
                               &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
                               (LPVOID *)&v63);
  if ( PortableDeviceProperties < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_53;
    v29 = 415;
    goto LABEL_52;
  }
  if ( v18 )
  {
    v35 = 0;
    v36 = 0;
    while ( !*((_DWORD *)v18 + 26) )
    {
      PortableDeviceProperties = CollectPersistentUniqueIDs(*((struct _IDA **)lpThreadParameter + 5), v63, v34 ^ 1);
      if ( PortableDeviceProperties != -2147024726 )
        goto LABEL_108;
      ((void (__fastcall *)(struct IPortableDevicePropVariantCollection *))v63->lpVtbl->Clear)(v63);
      if ( !v35 )
      {
        v35 = 1;
        v36 = 1;
        CProgressUI::_StartMarquee(v18);
      }
      if ( *((_DWORD *)v18 + 26) )
        break;
      Sleep(0x5DCu);
    }
    PortableDeviceProperties = -2147023673;
LABEL_108:
    if ( v36 )
      CProgressUI::_StopMarquee(v18);
    if ( *((_DWORD *)v18 + 26) )
    {
      PortableDeviceProperties = -2147023673;
LABEL_97:
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_53;
      v29 = 416;
      goto LABEL_52;
    }
  }
  else
  {
    PortableDeviceProperties = CollectPersistentUniqueIDs(*((struct _IDA **)lpThreadParameter + 5), v63, v34 ^ 1);
  }
  if ( PortableDeviceProperties < 0 )
    goto LABEL_97;
  PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDevicePropVariantCollection *, unsigned int *))v63->lpVtbl->GetCount)(
                               v63,
                               &v69);
  if ( PortableDeviceProperties < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_53;
    v29 = 417;
    goto LABEL_52;
  }
  v21 = v58;
  if ( !v62 )
  {
    *((_QWORD *)v58 + 18) = v69;
    PortableDeviceProperties = 0;
  }
  for ( i = 0; ; ++i )
  {
    if ( ((unsigned int (__fastcall *)(struct IPortableDevicePropVariantCollection *, _QWORD, PROPVARIANT *))v63->lpVtbl->GetAt)(
           v63,
           i,
           &psz1) )
    {
      goto LABEL_182;
    }
    if ( psz1.vt != 31 )
    {
      PortableDeviceProperties = -2147418113;
      goto LABEL_207;
    }
    if ( v18 )
    {
      v38 = 0;
      v39 = 0;
      while ( !*((_DWORD *)v18 + 26) )
      {
        PortableDeviceProperties = CBaseFolder::_GetObjectID(
                                     *((CBaseFolder **)lpThreadParameter + 3),
                                     psz1.bstrVal,
                                     v85,
                                     0x104u);
        if ( PortableDeviceProperties != -2147024726 )
          goto LABEL_131;
        if ( !v38 )
        {
          v38 = 1;
          v39 = 1;
          CProgressUI::_StartMarquee(v18);
        }
        if ( *((_DWORD *)v18 + 26) )
          break;
        Sleep(0x5DCu);
      }
      PortableDeviceProperties = -2147023673;
LABEL_131:
      if ( v39 )
        CProgressUI::_StopMarquee(v18);
      if ( *((_DWORD *)v18 + 26) )
      {
        PortableDeviceProperties = -2147023673;
LABEL_203:
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_53;
        v29 = 419;
        goto LABEL_52;
      }
    }
    else
    {
      PortableDeviceProperties = CBaseFolder::_GetObjectID(
                                   *((CBaseFolder **)lpThreadParameter + 3),
                                   psz1.bstrVal,
                                   v85,
                                   0x104u);
    }
    if ( PortableDeviceProperties < 0 )
      goto LABEL_203;
    if ( v18 )
    {
      v40 = 0;
      v41 = 0;
      while ( !*((_DWORD *)v18 + 26) )
      {
        PortableDeviceProperties = CContentFolder::_GetDisplayName(
                                     *((CContentFolder **)lpThreadParameter + 3),
                                     v85,
                                     v86,
                                     v9,
                                     &v61);
        if ( PortableDeviceProperties != -2147024726 )
          goto LABEL_145;
        if ( !v40 )
        {
          v40 = 1;
          v41 = 1;
          CProgressUI::_StartMarquee(v18);
        }
        if ( *((_DWORD *)v18 + 26) )
          break;
        Sleep(0x5DCu);
      }
      PortableDeviceProperties = -2147023673;
LABEL_145:
      if ( v41 )
        CProgressUI::_StopMarquee(v18);
      if ( *((_DWORD *)v18 + 26) )
      {
        PortableDeviceProperties = -2147023673;
LABEL_199:
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_53;
        v29 = 420;
        goto LABEL_52;
      }
    }
    else
    {
      PortableDeviceProperties = CContentFolder::_GetDisplayName(
                                   *((CContentFolder **)lpThreadParameter + 3),
                                   v85,
                                   v86,
                                   v9,
                                   &v61);
    }
    if ( PortableDeviceProperties < 0 )
      goto LABEL_199;
    v42 = v62;
    if ( !v62 )
    {
      v21 = v58;
      PortableDeviceProperties = CProgressUI::_ShowFileName(v58, v86, 0);
      if ( PortableDeviceProperties < 0 )
        break;
    }
    v65 = 1;
    if ( v64 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      v64 = 0;
    }
    v43 = v72;
    if ( ((int (__fastcall *)(struct IPortableDeviceProperties *, unsigned __int16 *, LPVOID, __int64 *))v72->lpVtbl->GetValues)(
           v72,
           v85,
           v66,
           &v64) >= 0 )
      (*(void (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v64 + 192LL))(
        v64,
        &WPD_OBJECT_CAN_DELETE,
        &v65);
    if ( !v65 )
    {
      v45 = CContentContextMenuCB::s_DeleteReadOnlyPrompt(
              (int)v44,
              v86,
              (struct CDeleteThreadData *)lpThreadParameter,
              v61);
      PortableDeviceProperties = v45;
      if ( v45 < 0 )
      {
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v53 = 422;
          goto LABEL_181;
        }
        goto LABEL_182;
      }
      if ( v45 )
        goto LABEL_170;
      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int64))(*(_QWORD *)v64 + 184LL))(
             v64,
             &WPD_OBJECT_CAN_DELETE,
             1) >= 0 )
        ((void (__fastcall *)(struct IPortableDeviceProperties *, unsigned __int16 *, __int64, __int64 *))v43->lpVtbl->SetValues)(
          v43,
          v85,
          v64,
          &v73);
    }
    v46 = 0;
    v21 = v58;
    if ( !v42 )
      v46 = v58;
    v47 = CContentFolder::_DeleteObject(v44, v59, v85, v70, v46);
    PortableDeviceProperties = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x175B,
        (unsigned int)"multimedia\\wpd\\ui\\shellext\\contentfolder.cpp",
        (const char *)(unsigned int)v47,
        ppv);
      PortableDeviceProperties = CContentContextMenuCB::s_DeleteOpErrorMessageWithSkip(
                                   PortableDeviceProperties,
                                   v86,
                                   (struct CDeleteThreadData *)lpThreadParameter,
                                   v61);
      if ( PortableDeviceProperties < 0 )
      {
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v53 = 423;
          goto LABEL_181;
        }
LABEL_182:
        v3 = v60;
        goto LABEL_183;
      }
    }
    if ( !PortableDeviceProperties )
    {
      LODWORD(v48) = 0;
      while ( 1 )
      {
        v49 = (CContentFolder *)*((_QWORD *)lpThreadParameter + 5);
        if ( (unsigned int)v48 >= *(_DWORD *)v49 )
          break;
        v48 = (unsigned int)(v48 + 1);
        v50 = CContentFolder::_IsValid(
                v49,
                (const struct _ITEMIDLIST *)((char *)v49 + *((unsigned int *)v49 + v48 + 1)));
        v51 = v50;
        if ( v50 )
        {
          StringCchCopyW(
            psz2,
            0x104u,
            (const unsigned __int16 *)v50
          + *(unsigned int *)((char *)v50 + 62)
          + *(unsigned int *)((char *)v50 + 66)
          + 37);
          if ( !StrCmpIW(psz1.bstrVal, psz2) )
          {
            CBaseFolder::_ChangeNotifyItem(
              *((CBaseFolder **)lpThreadParameter + 3),
              (*((_BYTE *)v51 + 10) & 2) != 0 ? 16 : 4,
              (const struct _ITEMIDLIST *)v51,
              0);
            break;
          }
        }
      }
LABEL_170:
      v21 = v58;
    }
    PropVariantClear(&psz1);
    if ( !v62 )
    {
      CProgressUI::_IncrementProgress(v21, 1u);
      if ( *((_DWORD *)v21 + 26) )
      {
        PortableDeviceProperties = -2147023673;
LABEL_195:
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v53 = 424;
LABEL_181:
          WPP_SF_d(v52[2], v53, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)PortableDeviceProperties);
        }
        goto LABEL_182;
      }
      if ( PortableDeviceProperties < 0 )
        goto LABEL_195;
    }
  }
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v31 = 421;
    goto LABEL_64;
  }
LABEL_207:
  if ( v4 )
  {
    if ( *((_DWORD *)v21 + 26) )
      PortableDeviceProperties = -2147023673;
    CProgressUI::_EndProgressUI(v21);
    v3 = 0;
  }
  else
  {
    v3 = v60;
  }
  v2 = v57;
LABEL_216:
  CContentContextMenuCB::s_DeleteOpErrorMessage(
    PortableDeviceProperties,
    (const unsigned __int16 *)v8,
    (struct CDeleteThreadData *)lpThreadParameter,
    v9);
LABEL_184:
  CPerfTraceHelper::ProcessPerformanceData((CPerfTraceHelper *)&v75, 0xBu, PortableDeviceProperties, 0);
  if ( v3 && v4 )
  {
    if ( *((_DWORD *)v3 + 26) )
      ChangeNotify(4096, 0, *(LPCVOID *)(*((_QWORD *)lpThreadParameter + 3) + 64LL), 0);
    CProgressUI::_EndProgressUI(v3);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)lpThreadParameter + 3) + 160LL))(
    *((_QWORD *)lpThreadParameter + 3),
    *(_QWORD *)(*((_QWORD *)lpThreadParameter + 3) + 64LL));
  if ( (*((_DWORD *)lpThreadParameter + 4) & 0x100) != 0 )
    *(_DWORD *)lpThreadParameter = PortableDeviceProperties;
  else
    CDeleteThreadData::`scalar deleting destructor'((CDeleteThreadData *)lpThreadParameter, v54);
  PropVariantClear(&psz1);
  if ( v59 )
  {
    ((void (__fastcall *)(struct IPortableDevice *))v59->lpVtbl->Release)(v59);
    v59 = 0;
  }
  if ( v67 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    v67 = 0;
  }
  if ( v72 )
  {
    ((void (__fastcall *)(struct IPortableDeviceProperties *))v72->lpVtbl->Release)(v72);
    v72 = 0;
  }
  if ( v66 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
    v66 = 0;
  }
  if ( v64 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  if ( v73 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    v73 = 0;
  }
  if ( v71 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
  if ( v63 )
  {
    ((void (__fastcall *)(struct IPortableDevicePropVariantCollection *))v63->lpVtbl->Release)(v63);
    v63 = 0;
  }
  if ( v2 >= 0 )
    CoUninitialize();
  wil::ActivityBase<WpdTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v81,
    (unsigned int)PortableDeviceProperties);
  if ( v63 )
    ((void (__fastcall *)(struct IPortableDevicePropVariantCollection *))v63->lpVtbl->Release)(v63);
  if ( v71 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
  if ( v73 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  if ( v64 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v66 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v66 + 16LL))(v66);
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  if ( v59 )
    ((void (__fastcall *)(struct IPortableDevice *))v59->lpVtbl->Release)(v59);
  v81 = &WpdTelemetry::DeleteItem::`vftable';
  wil::ActivityBase<WpdTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v81);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v84);
  wil::details::shared_object<wil::ActivityBase<WpdTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WpdTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v83);
  wil::ActivityBase<WpdTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WpdTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WpdTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v82);
  return 0;
}

```

## disassembly

```asm
0x180016780  push    rbp
0x180016782  push    rbx
0x180016783  push    rsi
0x180016784  push    rdi
0x180016785  push    r12
0x180016787  push    r13
0x180016789  push    r14
0x18001678b  push    r15
0x18001678d  lea     rbp, [rsp-0BB8h]
0x180016795  sub     rsp, 0CB8h
0x18001679c  mov     rax, cs:__security_cookie
0x1800167a3  xor     rax, rsp
0x1800167a6  mov     [rbp+0BF0h+var_50], rax
0x1800167ad  mov     r12, rcx
0x1800167b0  lea     rdx, aDeleteitem; "DeleteItem"
0x1800167b7  lea     rcx, [rbp+0BF0h+var_BF0]
0x1800167bb  call    ??0?$ActivityBase@VWpdTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WpdTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WpdTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800167c0  lea     r13, ??_7DeleteItem@WpdTelemetry@@6B@; const WpdTelemetry::DeleteItem::`vftable'
0x1800167c7  mov     [rbp+0BF0h+var_BF0], r13
0x1800167cb  lea     rcx, [rbp+0BF0h+var_BF0]; this
0x1800167cf  call    ?StartActivity@DeleteItem@WpdTelemetry@@QEAAXXZ; WpdTelemetry::DeleteItem::StartActivity(void)
0x1800167d4  nop
0x1800167d5  mov     r14d, 80004005h
0x1800167db  mov     [rbp+0BF0h+var_C30], 0
0x1800167e3  mov     [rbp+0BF0h+var_C28], 0
0x1800167eb  mov     [rbp+0BF0h+var_BF8], 0
0x1800167ef  xorps   xmm0, xmm0
0x1800167f2  movdqa  xmmword ptr [rbp+0BF0h+PerformanceCount], xmm0
0x1800167f7  xorps   xmm1, xmm1
0x1800167fa  movdqa  [rbp+0BF0h+var_C10], xmm1
0x1800167ff  mov     [rbp+0BF0h+var_C00], 0
0x180016807  xor     esi, esi
0x180016809  mov     [rsp+0CF0h+var_CA0], esi
0x18001680d  lea     ebx, [rsi+1]
0x180016810  mov     [rsp+0CF0h+var_C88], ebx
0x180016814  mov     edi, ebx
0x180016816  mov     [rbp+0BF0h+var_C6C], esi
0x180016819  mov     [rsp+0CF0h+var_CB0], rsi
0x18001681e  mov     [rsp+0CF0h+var_C78], rsi
0x180016823  mov     [rbp+0BF0h+var_C58], rsi
0x180016827  mov     [rsp+0CF0h+var_C80], rsi
0x18001682c  mov     [rsp+0CF0h+var_C90], rsi
0x180016831  mov     [rbp+0BF0h+var_C50], rsi
0x180016835  mov     [rbp+0BF0h+var_C60], rsi
0x180016839  mov     [rsp+0CF0h+var_C98], rsi
0x18001683e  xor     eax, eax
0x180016840  movups  xmmword ptr [rbp+0BF0h+psz1], xmm0
0x180016844  mov     [rbp+0BF0h+var_C38], rax
0x180016848  mov     rax, cs:WPP_GLOBAL_Control
0x18001684f  test    dword ptr [rax+1Ch], 800h
0x180016856  jz      short loc_180016879
0x180016858  lea     rcx, [rbp+0BF0h+PerformanceCount]; lpPerformanceCount
0x18001685c  call    cs:__imp_QueryPerformanceCounter
0x180016862  mov     [rbp+0BF0h+var_C30], 0Bh
0x18001686a  mov     [rbp+0BF0h+var_C28], rsi
0x18001686e  xorps   xmm0, xmm0
0x180016871  movdqa  [rbp+0BF0h+var_C10], xmm0
0x180016876  mov     [rbp+0BF0h+var_BF8], bl
0x180016879  mov     rax, [r12+28h]
0x18001687e  test    rax, rax
0x180016881  jnz     short loc_18001688D
0x180016883  mov     ebx, 8000FFFFh
0x180016888  jmp     loc_18001739A
0x18001688d  cmp     dword ptr [rax], 0
0x180016890  jz      short loc_180016883
0x180016892  call    SHCoInitialize
0x180016897  mov     r14d, eax
0x18001689a  mov     [rsp+0CF0h+var_CC0], eax
0x18001689e  test    eax, eax
0x1800168a0  jns     short loc_1800168E3
0x1800168a2  xor     ebx, ebx
0x1800168a4  lea     rcx, WPP_GLOBAL_Control
0x1800168ab  mov     r10, cs:WPP_GLOBAL_Control
0x1800168b2  cmp     r10, rcx
0x1800168b5  jz      loc_180017501
0x1800168bb  test    byte ptr [r10+1Ch], 2
0x1800168c0  jz      loc_180017501
0x1800168c6  mov     edx, 195h
0x1800168cb  mov     r9d, eax
0x1800168ce  mov     rcx, [r10+10h]
0x1800168d2  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800168d9  call    WPP_SF_d
0x1800168de  jmp     loc_180017501
0x1800168e3  mov     r15d, [r12+10h]
0x1800168e8  and     r15d, 400h
0x1800168ef  mov     [rsp+0CF0h+var_C9C], r15d
0x1800168f4  mov     edi, 0
0x1800168f9  setz    dil
0x1800168fd  mov     rcx, [r12+18h]
0x180016902  mov     rax, [rcx]
0x180016905  mov     r8d, 104h
0x18001690b  lea     rdx, [rbp+0BF0h+var_680]
0x180016912  mov     rax, [rax+60h]
0x180016916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001691b  mov     ebx, eax
0x18001691d  test    eax, eax
0x18001691f  jns     short loc_180016950
0x180016921  lea     rcx, WPP_GLOBAL_Control
0x180016928  mov     rax, cs:WPP_GLOBAL_Control
0x18001692f  cmp     rax, rcx
0x180016932  jz      loc_180017501
0x180016938  test    byte ptr [rax+1Ch], 2
0x18001693c  jz      loc_180017501
0x180016942  mov     edx, 196h
0x180016947  mov     r9d, ebx
0x18001694a  mov     rcx, [rax+10h]
0x18001694e  jmp     short loc_1800168D2
0x180016950  mov     ecx, 0B08h; unsigned __int64
0x180016955  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001695a  mov     [rsp+0CF0h+var_CA8], rax
0x18001695f  test    rax, rax
0x180016962  jz      loc_1800174E9
0x180016968  mov     rcx, rax; this
0x18001696b  call    ??0CProgressUI@@QEAA@XZ; CProgressUI::CProgressUI(void)
0x180016970  mov     r13, rax
0x180016973  mov     [rsp+0CF0h+var_CA8], rax
0x180016978  test    rax, rax
0x18001697b  jz      loc_1800174ED
0x180016981  mov     [r12+20h], rax
0x180016986  mov     rsi, rax
0x180016989  xor     eax, eax
0x18001698b  test    r15d, r15d
0x18001698e  cmovnz  rsi, rax
0x180016992  jnz     loc_180016A72
0x180016998  mov     rcx, [r12+18h]
0x18001699d  mov     rax, [rcx]
0x1800169a0  mov     r9d, 104h
0x1800169a6  lea     r8, [rbp+0BF0h+var_470]
0x1800169ad  mov     rdx, [rcx+40h]
0x1800169b1  mov     rax, [rax+90h]
0x1800169b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169bd  mov     ebx, eax
0x1800169bf  test    eax, eax
0x1800169c1  jns     short loc_1800169FC
0x1800169c3  lea     rcx, WPP_GLOBAL_Control
0x1800169ca  mov     rax, cs:WPP_GLOBAL_Control
0x1800169d1  cmp     rax, rcx
0x1800169d4  jz      short loc_1800169F4
0x1800169d6  test    byte ptr [rax+1Ch], 2
0x1800169da  jz      short loc_1800169F4
0x1800169dc  mov     edx, 197h
0x1800169e1  mov     r9d, ebx
0x1800169e4  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800169eb  mov     rcx, [rax+10h]
0x1800169ef  call    WPP_SF_d
0x1800169f4  mov     r14, r13
0x1800169f7  jmp     loc_1800174CC
0x1800169fc  xor     r9d, r9d; int
0x1800169ff  lea     r8d, [r9+1]; int
0x180016a03  lea     rdx, [rbp+0BF0h+var_470]; unsigned __int16 *
0x180016a0a  mov     rcx, r13; this
0x180016a0d  call    ?_Initialize@CProgressUI@@QEAAJPEBGHH@Z; CProgressUI::_Initialize(ushort const *,int,int)
0x180016a12  mov     ebx, eax
0x180016a14  test    eax, eax
0x180016a16  jns     short loc_180016A38
0x180016a18  lea     rcx, WPP_GLOBAL_Control
0x180016a1f  mov     rax, cs:WPP_GLOBAL_Control
0x180016a26  cmp     rax, rcx
0x180016a29  jz      short loc_1800169F4
0x180016a2b  test    byte ptr [rax+1Ch], 2
0x180016a2f  jz      short loc_1800169F4
0x180016a31  mov     edx, 198h
0x180016a36  jmp     short loc_1800169E1
0x180016a38  mov     edx, 3; enum _SPACTION
0x180016a3d  lea     r8d, [rdx+6Ch]; unsigned int
0x180016a41  mov     rcx, r13; this
0x180016a44  call    ?_BeginProgressUI@CProgressUI@@QEAAJW4_SPACTION@@I@Z; CProgressUI::_BeginProgressUI(_SPACTION,uint)
0x180016a49  mov     ebx, eax
0x180016a4b  test    eax, eax
0x180016a4d  jns     short loc_180016A72
0x180016a4f  lea     rcx, WPP_GLOBAL_Control
0x180016a56  mov     rax, cs:WPP_GLOBAL_Control
0x180016a5d  cmp     rax, rcx
0x180016a60  jz      short loc_1800169F4
0x180016a62  test    byte ptr [rax+1Ch], 2
0x180016a66  jz      short loc_1800169F4
0x180016a68  mov     edx, 199h
0x180016a6d  jmp     loc_1800169E1
0x180016a72  test    rsi, rsi
0x180016a75  jnz     short loc_180016AB7
0x180016a77  mov     rcx, [r12+18h]; this
0x180016a7c  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x180016a81  mov     ebx, eax
0x180016a83  call    cs:__imp_GetCurrentThreadId
0x180016a89  lea     rcx, [rsp+0CF0h+var_CB0]
0x180016a8e  mov     [rsp+0CF0h+var_CC8], rcx; struct IPortableDevice **
0x180016a93  mov     dword ptr [rsp+0CF0h+ppv], ebx; int
0x180016a97  xor     r9d, r9d; struct _ITEMIDLIST *
0x180016a9a  xor     r8d, r8d; struct _ITEMIDLIST *
0x180016a9d  mov     edx, eax; unsigned int
0x180016a9f  lea     rcx, [rbp+0BF0h+var_680]; unsigned __int16 *
0x180016aa6  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x180016aab  mov     ebx, eax
0x180016aad  mov     [rsp+0CF0h+var_CB8], r13
0x180016ab2  jmp     loc_180016B58
0x180016ab7  xor     r15d, r15d
0x180016aba  xor     r14d, r14d
0x180016abd  mov     [rsp+0CF0h+var_CB8], r13
0x180016ac2  cmp     dword ptr [rsi+68h], 0
0x180016ac6  jnz     short loc_180016B34
0x180016ac8  mov     rcx, [r12+18h]; this
0x180016acd  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x180016ad2  mov     ebx, eax
0x180016ad4  call    cs:__imp_GetCurrentThreadId
0x180016ada  lea     rcx, [rsp+0CF0h+var_CB0]
0x180016adf  mov     [rsp+0CF0h+var_CC8], rcx; struct IPortableDevice **
0x180016ae4  mov     dword ptr [rsp+0CF0h+ppv], ebx; int
0x180016ae8  xor     r9d, r9d; struct _ITEMIDLIST *
0x180016aeb  xor     r8d, r8d; struct _ITEMIDLIST *
0x180016aee  mov     edx, eax; unsigned int
0x180016af0  lea     rcx, [rbp+0BF0h+var_680]; unsigned __int16 *
0x180016af7  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x180016afc  mov     ebx, eax
0x180016afe  cmp     eax, 800700AAh
0x180016b03  jnz     short loc_180016B39
0x180016b05  test    r15d, r15d
0x180016b08  jnz     short loc_180016B1C
0x180016b0a  lea     eax, [r15+1]
0x180016b0e  mov     r15d, eax
0x180016b11  mov     r14d, eax
0x180016b14  mov     rcx, rsi; this
0x180016b17  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180016b1c  cmp     dword ptr [rsi+68h], 0
0x180016b20  jnz     short loc_180016B34
0x180016b22  mov     ecx, 5DCh; dwMilliseconds
0x180016b27  call    cs:__imp_Sleep
0x180016b2d  test    r15d, r15d
0x180016b30  jz      short loc_180016B39
0x180016b32  jmp     short loc_180016AC2
0x180016b34  mov     ebx, 800704C7h
0x180016b39  test    r14d, r14d
0x180016b3c  jz      short loc_180016B46
0x180016b3e  mov     rcx, rsi; this
0x180016b41  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180016b46  cmp     dword ptr [rsi+68h], 0
0x180016b4a  jz      short loc_180016B53
0x180016b4c  mov     ebx, 800704C7h
0x180016b51  jmp     short loc_180016B5F
0x180016b53  mov     r15d, [rsp+0CF0h+var_C9C]
0x180016b58  mov     r14, r13
0x180016b5b  test    ebx, ebx
0x180016b5d  jns     short loc_180016B9A
0x180016b5f  lea     rcx, WPP_GLOBAL_Control
0x180016b66  mov     rax, cs:WPP_GLOBAL_Control
0x180016b6d  cmp     rax, rcx
0x180016b70  jz      short loc_180016B90
0x180016b72  test    byte ptr [rax+1Ch], 2
0x180016b76  jz      short loc_180016B90
0x180016b78  mov     edx, 19Ah
0x180016b7d  mov     r9d, ebx
0x180016b80  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180016b87  mov     rcx, [rax+10h]
0x180016b8b  call    WPP_SF_d
0x180016b90  mov     r14, [rsp+0CF0h+var_CB8]
0x180016b95  jmp     loc_1800174CC
0x180016b9a  test    r15d, r15d
0x180016b9d  jnz     short loc_180016BEB
0x180016b9f  mov     rdx, [rsp+0CF0h+var_CB0]; struct IPortableDevice *
0x180016ba4  mov     rcx, r14; this
0x180016ba7  call    ?_AssociateDevice@CProgressUI@@QEAAJPEAUIPortableDevice@@@Z; CProgressUI::_AssociateDevice(IPortableDevice *)
0x180016bac  mov     ebx, eax
0x180016bae  test    eax, eax
0x180016bb0  jns     short loc_180016BEB
0x180016bb2  lea     rcx, WPP_GLOBAL_Control
0x180016bb9  mov     rax, cs:WPP_GLOBAL_Control
0x180016bc0  cmp     rax, rcx
0x180016bc3  jz      short loc_180016BE3
0x180016bc5  test    byte ptr [rax+1Ch], 2
0x180016bc9  jz      short loc_180016BE3
0x180016bcb  mov     edx, 19Bh
0x180016bd0  mov     r9d, ebx
0x180016bd3  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180016bda  mov     rcx, [rax+10h]
0x180016bde  call    WPP_SF_d
0x180016be3  mov     rsi, r13
0x180016be6  jmp     loc_18001738E
0x180016beb  lea     rdx, [rbp+0BF0h+var_C58]; struct IPortableDeviceProperties **
0x180016bef  mov     rcx, [rsp+0CF0h+var_CB0]; struct IPortableDevice *
0x180016bf4  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180016bf9  mov     ebx, eax
0x180016bfb  test    eax, eax
0x180016bfd  jns     short loc_180016C3D
0x180016bff  lea     rcx, WPP_GLOBAL_Control
0x180016c06  mov     rax, cs:WPP_GLOBAL_Control
0x180016c0d  cmp     rax, rcx
0x180016c10  jz      loc_1800174CC
0x180016c16  test    byte ptr [rax+1Ch], 2
0x180016c1a  jz      loc_1800174CC
0x180016c20  mov     edx, 19Ch
0x180016c25  mov     r9d, ebx
0x180016c28  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x180016c2f  mov     rcx, [rax+10h]
0x180016c33  call    WPP_SF_d
0x180016c38  jmp     loc_1800174CC
0x180016c3d  lea     rax, [rsp+0CF0h+var_C80]
0x180016c42  mov     [rsp+0CF0h+ppv], rax; ppv
0x180016c47  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180016c4e  mov     r15d, 1
0x180016c54  mov     r8d, r15d; dwClsContext
0x180016c57  xor     edx, edx; pUnkOuter
  ... truncated ...
```
