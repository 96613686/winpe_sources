# GetFileProperties(IPortableDevice *,IPortableDeviceValues *,_ITEMIDLIST const *,CBaseFolder *,_ITEMIDLIST const *,ushort const *,ushort const *,ushort const *,CProgressUI *,ushort const *)

- ea: `0x180025048`
- end: `0x180025a9d`
- name: `?GetFileProperties@@YAJPEAUIPortableDevice@@PEAUIPortableDeviceValues@@PEFBU_ITEMIDLIST@@PEAVCBaseFolder@@2PEBG44PEAVCProgressUI@@4@Z`
- size: `2645`
- prototype: `int(struct IPortableDevice *, struct IPortableDeviceValues *, const struct _ITEMIDLIST *, struct CBaseFolder *, const struct _ITEMIDLIST *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct CProgressUI *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800118d4`
- `0x180063ed8`

## callees

- `0x180025048`
- `0x180025aa4`
- `0x1800285c8`
- `0x18002a1d8`
- `0x18002ab58`
- `0x18002ff5c`
- `0x180030cfc`
- `0x180035590`
- `0x1800361ba`
- `0x180052c80`
- `0x180054524`
- `0x1800545c8`
- `0x180062518`
- `0x18006cea0`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800254a3`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800254a3`
- `KERNEL32!Sleep` at `0x1800251ea`
- `KERNEL32!Sleep` at `0x1800253a2`
- `KERNEL32!Sleep` at `0x1800251ea`
- `KERNEL32!Sleep` at `0x1800253a2`
- `KERNEL32!GetFileAttributesW` at `0x1800256da`
- `KERNEL32!GetFileAttributesW` at `0x1800256da`
- `KERNEL32!GetSystemTime` at `0x1800258ef`
- `KERNEL32!GetSystemTime` at `0x1800258ef`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x1800258ff`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x1800258ff`
- `ole32!PropVariantClear` at `0x180025875`
- `ole32!PropVariantClear` at `0x18002595d`
- `ole32!PropVariantClear` at `0x180025a15`
- `ole32!PropVariantClear` at `0x180025875`
- `ole32!PropVariantClear` at `0x18002595d`
- `ole32!PropVariantClear` at `0x180025a15`
- `OLEAUT32!__imp_VariantInit` at `0x1800256f8`
- `OLEAUT32!__imp_VariantInit` at `0x1800256f8`
- `OLEAUT32!__imp_VariantClear` at `0x180025791`
- `OLEAUT32!__imp_VariantClear` at `0x180025791`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180025911`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180025911`
- `SHELL32!SHBindToParent` at `0x180025631`
- `SHELL32!SHBindToParent` at `0x180025631`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetFileProperties(
        struct IPortableDevice *a1,
        struct IPortableDeviceValues *a2,
        const struct _ITEMIDLIST *a3,
        struct CBaseFolder *a4,
        const struct _ITEMIDLIST *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        wchar_t *a8,
        struct CProgressUI *a9)
{
  wchar_t *v13; // r12
  int v14; // edi
  int v15; // ebx
  int v16; // r12d
  int v17; // edi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  int FormatFromFileName; // eax
  int v22; // r13d
  int v23; // edi
  int v24; // r12d
  int v25; // ebx
  unsigned int i; // ebx
  HRESULT (__stdcall *SetStringValue)(IPortableDeviceValues *, const PROPERTYKEY *const, LPCWSTR); // rax
  HRESULT LongProperty; // eax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  unsigned int v31; // edi
  __int64 v32; // r8
  __int64 v33; // r8
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *FullPath; // [rsp+60h] [rbp-A0h] BYREF
  struct IPortableDeviceCapabilities *v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h] BYREF
  PROPVARIANT pvar; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME v43; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 *v45; // [rsp+D0h] [rbp-30h]
  GUID Buf2; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID v47; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v48; // [rsp+F8h] [rbp-8h] BYREF
  int v49; // [rsp+108h] [rbp+8h]
  struct _SYSTEMTIME SystemTime; // [rsp+110h] [rbp+10h] BYREF
  struct _SYSTEMTIME LocalTime; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v52[264]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t Filename[264]; // [rsp+340h] [rbp+240h] BYREF
  wchar_t Ext[264]; // [rsp+550h] [rbp+450h] BYREF

  v13 = a8;
  FullPath = a8;
  lpFileName = a7;
  v45 = a6;
  v39 = 0;
  v48 = 0;
  v49 = 0;
  Buf2 = 0;
  v47 = 0;
  v43 = 0;
  SystemTime = 0;
  LocalTime = 0;
  memset_0(v52, 0, 0x208u);
  memset_0(Filename, 0, 0x208u);
  memset_0(Ext, 0, 0x208u);
  v38 = 0;
  v40 = 0;
  memset(&pvar, 0, sizeof(pvar));
  LODWORD(ppv) = (*(__int64 (__fastcall **)(struct CBaseFolder *, const struct _ITEMIDLIST *, const GUID *))(*(_QWORD *)a4 + 56LL))(
                   a4,
                   a5,
                   &WPD_CONTENT_TYPE_GENERIC_FILE);
  *(GUID *)&pvarg.vt = WPD_CONTENT_TYPE_GENERIC_FILE;
  v14 = (*(__int64 (__fastcall **)(struct CBaseFolder *, const struct _ITEMIDLIST *, VARIANTARG *, _QWORD))(*(_QWORD *)a4 + 64LL))(
          a4,
          a5,
          &pvarg,
          0);
  v36 = v14;
  if ( !a9 )
  {
    v15 = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceCapabilities **))a1->lpVtbl->Capabilities)(
            a1,
            &v38);
    goto LABEL_16;
  }
  v16 = 0;
  v17 = 0;
  while ( !*((_DWORD *)a9 + 26) )
  {
    v15 = ((__int64 (__fastcall *)(struct IPortableDevice *, struct IPortableDeviceCapabilities **))a1->lpVtbl->Capabilities)(
            a1,
            &v38);
    if ( v15 != -2147024726 )
      goto LABEL_11;
    if ( !v16 )
    {
      v16 = 1;
      v17 = 1;
      CProgressUI::_StartMarquee(a9);
    }
    if ( *((_DWORD *)a9 + 26) )
      break;
    Sleep(0x5DCu);
  }
  v15 = -2147023673;
LABEL_11:
  if ( v17 )
    CProgressUI::_StopMarquee(a9);
  if ( !*((_DWORD *)a9 + 26) )
  {
    v13 = FullPath;
    v14 = v36;
LABEL_16:
    if ( v15 < 0 )
      goto LABEL_17;
    if ( !v13 )
      v13 = (wchar_t *)lpFileName;
    FullPath = v13;
    FormatFromFileName = GetFormatFromFileName(v38, v13, &Buf2, &v47);
    v15 = FormatFromFileName;
    if ( FormatFromFileName < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_130;
      v19 = 59;
      goto LABEL_27;
    }
    if ( !memcmp_0(&WPD_CONTENT_TYPE_UNSPECIFIED, &Buf2, 0x10u) && (_DWORD)ppv && v14 )
      Buf2 = WPD_CONTENT_TYPE_GENERIC_FILE;
    FormatFromFileName = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, const unsigned __int16 *))a2->lpVtbl->SetStringValue)(
                           a2,
                           &WPD_OBJECT_PARENT_ID,
                           v45);
    v15 = FormatFromFileName;
    if ( FormatFromFileName < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_130;
      v19 = 60;
      goto LABEL_27;
    }
    v22 = 0;
    if ( a9 )
    {
      v24 = 0;
      v25 = 0;
      while ( !*((_DWORD *)a9 + 26) )
      {
        v23 = ((__int64 (__fastcall *)(struct IPortableDeviceCapabilities *, struct _GUID *, __int64 *))v38->lpVtbl->GetSupportedFormatProperties)(
                v38,
                &v47,
                &v40);
        if ( v23 != -2147024726 )
          goto LABEL_46;
        if ( !v24 )
        {
          v24 = 1;
          v25 = 1;
          CProgressUI::_StartMarquee(a9);
        }
        if ( *((_DWORD *)a9 + 26) )
          break;
        Sleep(0x5DCu);
      }
      v23 = -2147023673;
LABEL_46:
      if ( v25 )
        CProgressUI::_StopMarquee(a9);
      if ( *((_DWORD *)a9 + 26) )
        goto LABEL_61;
    }
    else
    {
      v23 = ((__int64 (__fastcall *)(struct IPortableDeviceCapabilities *, struct _GUID *, __int64 *))v38->lpVtbl->GetSupportedFormatProperties)(
              v38,
              &v47,
              &v40);
    }
    if ( v23 >= 0 )
    {
      FormatFromFileName = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 24LL))(v40, &v39);
      v15 = FormatFromFileName;
      if ( FormatFromFileName < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_130;
        v19 = 61;
        goto LABEL_27;
      }
      for ( i = 0; i < v39; ++i )
      {
        if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v40 + 32LL))(v40, i, &v48) >= 0
          && v49 == 12
          && !memcmp_0(&WPD_OBJECT_ORIGINAL_FILE_NAME, &v48, 0x10u) )
        {
          v22 = 1;
          break;
        }
      }
    }
LABEL_61:
    _wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x104u, Ext, 0x104u);
    StringCchPrintfW(v52, 0x104u, L"%ws%ws", Filename, Ext);
    SetStringValue = a2->lpVtbl->SetStringValue;
    if ( v22 )
    {
      FormatFromFileName = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, unsigned __int16 *))SetStringValue)(
                             a2,
                             &WPD_OBJECT_ORIGINAL_FILE_NAME,
                             v52);
      v15 = FormatFromFileName;
      if ( FormatFromFileName < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_130;
        v19 = 62;
        goto LABEL_27;
      }
      FormatFromFileName = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, wchar_t *))a2->lpVtbl->SetStringValue)(
                             a2,
                             &WPD_OBJECT_NAME,
                             Filename);
      v15 = FormatFromFileName;
      if ( FormatFromFileName < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_130;
        v19 = 63;
        goto LABEL_27;
      }
    }
    else
    {
      FormatFromFileName = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, unsigned __int16 *))SetStringValue)(
                             a2,
                             &WPD_OBJECT_NAME,
                             v52);
      v15 = FormatFromFileName;
      if ( FormatFromFileName < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_130;
        v19 = 64;
        goto LABEL_27;
      }
      FormatFromFileName = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, unsigned __int16 *))a2->lpVtbl->SetStringValue)(
                             a2,
                             &WPD_OBJECT_ORIGINAL_FILE_NAME,
                             v52);
      v15 = FormatFromFileName;
      if ( FormatFromFileName < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_130;
        v19 = 65;
        goto LABEL_27;
      }
    }
    if ( a3 )
    {
      FullPath = 0;
      ppv = 0;
      LongProperty = SHBindToParent(a3, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &ppv, (LPCITEMIDLIST *)&FullPath);
      v15 = LongProperty;
      if ( LongProperty < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v30 = 66;
LABEL_83:
        WPP_SF_d(v29[2], v30, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)LongProperty);
LABEL_84:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        goto LABEL_130;
      }
      v36 = 0x40000000;
      LongProperty = (*(__int64 (__fastcall **)(void *, __int64, wchar_t **, int *))(*(_QWORD *)ppv + 72LL))(
                       ppv,
                       1,
                       &FullPath,
                       &v36);
      v15 = LongProperty;
      if ( LongProperty < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v30 = 67;
        goto LABEL_83;
      }
      if ( (v36 & 0x40000000) != 0 )
      {
        LOBYTE(v31) = GetFileAttributesW(lpFileName);
      }
      else
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        LongProperty = (*(__int64 (__fastcall **)(void *, wchar_t *, __int64 *, VARIANTARG *))(*(_QWORD *)ppv + 136LL))(
                         ppv,
                         FullPath,
                         &PKEY_WPDNSE_Attributes,
                         &pvarg);
        v15 = LongProperty;
        if ( LongProperty < 0 )
        {
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_84;
          v30 = 68;
          goto LABEL_83;
        }
        LOBYTE(v31) = 0;
        if ( pvarg.vt == 19 )
          v31 = ((pvarg.bVal & 2) != 0 ? 16 : 128)
              | ((pvarg.iVal & 0x100 | ((pvarg.iVal & 0x400 | ((unsigned int)pvarg.lVal >> 1) & 0x100) >> 1)) >> 7);
        VariantClear(&pvarg);
      }
      lpFileName = 0;
      LongProperty = GetLongProperty(ppv, FullPath, v32, &lpFileName);
      v15 = LongProperty;
      if ( LongProperty < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v30 = 69;
        goto LABEL_83;
      }
      LongProperty = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, LPCWSTR))a2->lpVtbl->SetUnsignedLargeIntegerValue)(
                       a2,
                       &WPD_OBJECT_SIZE,
                       lpFileName);
      v15 = LongProperty;
      if ( LongProperty < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v30 = 70;
        goto LABEL_83;
      }
      if ( (int)GetDateProperty(ppv, FullPath, v33, &v43) >= 0 )
      {
        pvar.vt = 7;
        ConvertUTCFileTimeToVariantLocalTime(&v43, &pvar.dblVal);
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, PROPVARIANT *))a2->lpVtbl->SetValue)(
          a2,
          &WPD_OBJECT_DATE_MODIFIED,
          &pvar);
        PropVariantClear(&pvar);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      if ( (v31 & 2) != 0 )
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))a2->lpVtbl->SetBoolValue)(
          a2,
          &WPD_OBJECT_ISHIDDEN,
          1);
      if ( (v31 & 1) != 0 )
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, _QWORD))a2->lpVtbl->SetBoolValue)(
          a2,
          &WPD_OBJECT_CAN_DELETE,
          0);
      if ( (v31 & 4) != 0 )
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))a2->lpVtbl->SetBoolValue)(
          a2,
          &WPD_OBJECT_ISSYSTEM,
          1);
    }
    GetSystemTime(&SystemTime);
    if ( SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
    {
      if ( SystemTimeToVariantTime(&LocalTime, &pvar.dblVal) )
      {
        pvar.vt = 7;
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, PROPVARIANT *))a2->lpVtbl->SetValue)(
          a2,
          &WPD_OBJECT_DATE_CREATED,
          &pvar);
      }
      if ( !a3 )
        ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, PROPVARIANT *))a2->lpVtbl->SetValue)(
          a2,
          &WPD_OBJECT_DATE_MODIFIED,
          &pvar);
      PropVariantClear(&pvar);
    }
    FormatFromFileName = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, GUID *))a2->lpVtbl->SetGuidValue)(
                           a2,
                           &WPD_OBJECT_CONTENT_TYPE,
                           &Buf2);
    v15 = FormatFromFileName;
    if ( FormatFromFileName >= 0 )
    {
      FormatFromFileName = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, struct _GUID *))a2->lpVtbl->SetGuidValue)(
                             a2,
                             &WPD_OBJECT_FORMAT,
                             &v47);
      v15 = FormatFromFileName;
      if ( FormatFromFileName >= 0 )
      {
        if ( a3 )
        {
          FixFormatBasedOnProperties(a3, a2);
          SearchForMetaData(a3, a2);
        }
        goto LABEL_130;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_130;
      v19 = 72;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_130;
      v19 = 71;
    }
LABEL_27:
    v20 = (unsigned int)FormatFromFileName;
    goto LABEL_20;
  }
  v15 = -2147023673;
LABEL_17:
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v19 = 58;
    v20 = (unsigned int)v15;
LABEL_20:
    WPP_SF_d(v18[2], v19, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, v20);
  }
LABEL_130:
  PropVariantClear(&pvar);
  if ( v15 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids,
      (unsigned int)v15);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v38 )
    ((void (__fastcall *)(struct IPortableDeviceCapabilities *))v38->lpVtbl->Release)(v38);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180025048  push    rbp
0x18002504a  push    rbx
0x18002504b  push    rsi
0x18002504c  push    rdi
0x18002504d  push    r12
0x18002504f  push    r13
0x180025051  push    r14
0x180025053  push    r15
0x180025055  lea     rbp, [rsp-678h]
0x18002505d  sub     rsp, 778h
0x180025064  mov     rax, cs:__security_cookie
0x18002506b  xor     rax, rsp
0x18002506e  mov     [rbp+6B0h+var_50], rax
0x180025075  mov     rdi, r9
0x180025078  mov     r15, r8
0x18002507b  mov     rsi, rdx
0x18002507e  mov     r13, rcx
0x180025081  mov     r12, [rbp+6B0h+arg_38]
0x180025088  mov     [rsp+7B0h+FullPath], r12
0x18002508d  mov     rax, [rbp+6B0h+arg_30]
0x180025094  mov     [rbp+6B0h+lpFileName], rax
0x180025098  mov     rbx, [rbp+6B0h+arg_20]
0x18002509f  mov     rax, [rbp+6B0h+arg_28]
0x1800250a6  mov     [rbp+6B0h+var_6E0], rax
0x1800250aa  mov     r14, [rbp+6B0h+arg_40]
0x1800250b1  mov     [rsp+7B0h+var_740], 0
0x1800250b9  xorps   xmm0, xmm0
0x1800250bc  xor     eax, eax
0x1800250be  movups  [rbp+6B0h+var_6B8], xmm0
0x1800250c2  mov     [rbp+6B0h+var_6A8], eax
0x1800250c5  movups  [rbp+6B0h+Buf2], xmm0
0x1800250c9  xorps   xmm1, xmm1
0x1800250cc  movups  xmmword ptr [rbp+6B0h+var_6C8.Data1], xmm1
0x1800250d0  mov     qword ptr [rbp+6B0h+var_710.dwLowDateTime], rax
0x1800250d4  movups  xmmword ptr [rbp+6B0h+SystemTime.wYear], xmm0
0x1800250d8  movups  xmmword ptr [rbp+6B0h+LocalTime.wYear], xmm1
0x1800250dc  xor     edx, edx; Val
0x1800250de  mov     r8d, 208h; Size
0x1800250e4  lea     rcx, [rbp+6B0h+var_680]; void *
0x1800250e8  call    memset_0
0x1800250ed  xor     edx, edx; Val
0x1800250ef  mov     r8d, 208h; Size
0x1800250f5  lea     rcx, [rbp+6B0h+var_470]; void *
0x1800250fc  call    memset_0
0x180025101  xor     edx, edx; Val
0x180025103  mov     r8d, 208h; Size
0x180025109  lea     rcx, [rbp+6B0h+var_260]; void *
0x180025110  call    memset_0
0x180025115  mov     [rsp+7B0h+var_748], 0
0x18002511e  mov     [rsp+7B0h+var_738], 0
0x180025127  xorps   xmm0, xmm0
0x18002512a  xor     eax, eax
0x18002512c  movups  xmmword ptr [rbp+6B0h+pvar], xmm0
0x180025130  mov     qword ptr [rbp+6B0h+pvar+10h], rax
0x180025134  mov     rax, [rdi]
0x180025137  lea     r8, WPD_CONTENT_TYPE_GENERIC_FILE
0x18002513e  mov     rdx, rbx
0x180025141  mov     rcx, rdi
0x180025144  mov     rax, [rax+38h]
0x180025148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002514d  mov     dword ptr [rsp+7B0h+ppv], eax
0x180025151  movups  xmm0, xmmword ptr cs:WPD_CONTENT_TYPE_GENERIC_FILE.Data1
0x180025158  movdqu  xmmword ptr [rbp+6B0h+pvarg], xmm0
0x18002515d  mov     rcx, [rdi]
0x180025160  mov     rax, [rcx+40h]
0x180025164  xor     r9d, r9d
0x180025167  lea     r8, [rbp+6B0h+pvarg]
0x18002516b  mov     rdx, rbx
0x18002516e  mov     rcx, rdi
0x180025171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025176  mov     edi, eax
0x180025178  mov     [rsp+7B0h+var_758], eax
0x18002517c  test    r14, r14
0x18002517f  jnz     short loc_18002519D
0x180025181  mov     rdx, [r13+0]
0x180025185  mov     rax, [rdx+30h]
0x180025189  lea     rdx, [rsp+7B0h+var_748]
0x18002518e  mov     rcx, r13
0x180025191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025196  mov     ebx, eax
0x180025198  jmp     loc_18002521F
0x18002519d  xor     r12d, r12d
0x1800251a0  xor     edi, edi
0x1800251a2  cmp     dword ptr [r14+68h], 0
0x1800251a7  jnz     short loc_1800251F7
0x1800251a9  mov     rax, [r13+0]
0x1800251ad  lea     rdx, [rsp+7B0h+var_748]
0x1800251b2  mov     rcx, r13
0x1800251b5  mov     rax, [rax+30h]
0x1800251b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251be  mov     ebx, eax
0x1800251c0  cmp     eax, 800700AAh
0x1800251c5  jnz     short loc_1800251FC
0x1800251c7  test    r12d, r12d
0x1800251ca  jnz     short loc_1800251DE
0x1800251cc  lea     eax, [r12+1]
0x1800251d1  mov     r12d, eax
0x1800251d4  mov     edi, eax
0x1800251d6  mov     rcx, r14; this
0x1800251d9  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x1800251de  cmp     dword ptr [r14+68h], 0
0x1800251e3  jnz     short loc_1800251F7
0x1800251e5  mov     ecx, 5DCh; dwMilliseconds
0x1800251ea  call    cs:__imp_Sleep
0x1800251f0  test    r12d, r12d
0x1800251f3  jz      short loc_1800251FC
0x1800251f5  jmp     short loc_1800251A2
0x1800251f7  mov     ebx, 800704C7h
0x1800251fc  test    edi, edi
0x1800251fe  jz      short loc_180025208
0x180025200  mov     rcx, r14; this
0x180025203  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180025208  cmp     dword ptr [r14+68h], 0
0x18002520d  jz      short loc_180025216
0x18002520f  mov     ebx, 800704C7h
0x180025214  jmp     short loc_180025223
0x180025216  mov     r12, [rsp+7B0h+FullPath]
0x18002521b  mov     edi, [rsp+7B0h+var_758]
0x18002521f  test    ebx, ebx
0x180025221  jns     short loc_180025261
0x180025223  mov     rcx, cs:WPP_GLOBAL_Control
0x18002522a  lea     rdi, WPP_GLOBAL_Control
0x180025231  cmp     rcx, rdi
0x180025234  jz      loc_180025A11
0x18002523a  test    byte ptr [rcx+1Ch], 2
0x18002523e  jz      loc_180025A11
0x180025244  mov     edx, 3Ah ; ':'
0x180025249  mov     r9d, ebx
0x18002524c  lea     r8, WPP_97501a7b54843d9fecff243f22a7f928_Traceguids
0x180025253  mov     rcx, [rcx+10h]
0x180025257  call    WPP_SF_d
0x18002525c  jmp     loc_180025A11
0x180025261  test    r12, r12
0x180025264  cmovz   r12, [rbp+6B0h+lpFileName]
0x180025269  mov     [rsp+7B0h+FullPath], r12
0x18002526e  lea     r9, [rbp+6B0h+var_6C8]; struct _GUID *
0x180025272  lea     r8, [rbp+6B0h+Buf2]; struct _GUID *
0x180025276  mov     rdx, r12; unsigned __int16 *
0x180025279  mov     rcx, [rsp+7B0h+var_748]; struct IPortableDeviceCapabilities *
0x18002527e  call    ?GetFormatFromFileName@@YAJPEAUIPortableDeviceCapabilities@@PEBGPEAU_GUID@@2@Z; GetFormatFromFileName(IPortableDeviceCapabilities *,ushort const *,_GUID *,_GUID *)
0x180025283  mov     ebx, eax
0x180025285  test    eax, eax
0x180025287  jns     short loc_1800252B4
0x180025289  mov     rcx, cs:WPP_GLOBAL_Control
0x180025290  lea     rdi, WPP_GLOBAL_Control
0x180025297  cmp     rcx, rdi
0x18002529a  jz      loc_180025A11
0x1800252a0  test    byte ptr [rcx+1Ch], 2
0x1800252a4  jz      loc_180025A11
0x1800252aa  mov     edx, 3Bh ; ';'
0x1800252af  mov     r9d, eax
0x1800252b2  jmp     short loc_18002524C
0x1800252b4  mov     r8d, 10h; Size
0x1800252ba  lea     rdx, [rbp+6B0h+Buf2]; Buf2
0x1800252be  lea     rcx, WPD_CONTENT_TYPE_UNSPECIFIED; Buf1
0x1800252c5  call    memcmp_0
0x1800252ca  test    eax, eax
0x1800252cc  jnz     short loc_1800252E4
0x1800252ce  cmp     dword ptr [rsp+7B0h+ppv], eax
0x1800252d2  jz      short loc_1800252E4
0x1800252d4  test    edi, edi
0x1800252d6  jz      short loc_1800252E4
0x1800252d8  movups  xmm0, xmmword ptr cs:WPD_CONTENT_TYPE_GENERIC_FILE.Data1
0x1800252df  movdqu  [rbp+6B0h+Buf2], xmm0
0x1800252e4  mov     rax, [rsi]
0x1800252e7  mov     r8, [rbp+6B0h+var_6E0]
0x1800252eb  lea     rdx, WPD_OBJECT_PARENT_ID
0x1800252f2  mov     rcx, rsi
0x1800252f5  mov     rax, [rax+38h]
0x1800252f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252fe  mov     ebx, eax
0x180025300  test    eax, eax
0x180025302  jns     short loc_18002532C
0x180025304  mov     rcx, cs:WPP_GLOBAL_Control
0x18002530b  lea     rdi, WPP_GLOBAL_Control
0x180025312  cmp     rcx, rdi
0x180025315  jz      loc_180025A11
0x18002531b  test    byte ptr [rcx+1Ch], 2
0x18002531f  jz      loc_180025A11
0x180025325  mov     edx, 3Ch ; '<'
0x18002532a  jmp     short loc_1800252AF
0x18002532c  xor     r13d, r13d
0x18002532f  test    r14, r14
0x180025332  jnz     short loc_180025352
0x180025334  mov     rcx, [rsp+7B0h+var_748]
0x180025339  mov     rax, [rcx]
0x18002533c  lea     r8, [rsp+7B0h+var_738]
0x180025341  lea     rdx, [rbp+6B0h+var_6C8]
0x180025345  mov     rax, [rax+48h]
0x180025349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002534e  mov     edi, eax
0x180025350  jmp     short loc_1800253CA
0x180025352  xor     r12d, r12d
0x180025355  xor     ebx, ebx
0x180025357  cmp     [r14+68h], r13d
0x18002535b  jnz     short loc_1800253AF
0x18002535d  mov     rcx, [rsp+7B0h+var_748]
0x180025362  mov     rax, [rcx]
0x180025365  lea     r8, [rsp+7B0h+var_738]
0x18002536a  lea     rdx, [rbp+6B0h+var_6C8]
0x18002536e  mov     rax, [rax+48h]
0x180025372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025377  mov     edi, eax
0x180025379  cmp     eax, 800700AAh
0x18002537e  jnz     short loc_1800253B4
0x180025380  test    r12d, r12d
0x180025383  jnz     short loc_180025397
0x180025385  lea     eax, [r12+1]
0x18002538a  mov     r12d, eax
0x18002538d  mov     ebx, eax
0x18002538f  mov     rcx, r14; this
0x180025392  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180025397  cmp     [r14+68h], r13d
0x18002539b  jnz     short loc_1800253AF
0x18002539d  mov     ecx, 5DCh; dwMilliseconds
0x1800253a2  call    cs:__imp_Sleep
0x1800253a8  test    r12d, r12d
0x1800253ab  jz      short loc_1800253B4
0x1800253ad  jmp     short loc_180025357
0x1800253af  mov     edi, 800704C7h
0x1800253b4  test    ebx, ebx
0x1800253b6  jz      short loc_1800253C0
0x1800253b8  mov     rcx, r14; this
0x1800253bb  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x1800253c0  cmp     [r14+68h], r13d
0x1800253c4  jnz     loc_180025466
0x1800253ca  test    edi, edi
0x1800253cc  js      loc_180025466
0x1800253d2  mov     rcx, [rsp+7B0h+var_738]
0x1800253d7  mov     rax, [rcx]
0x1800253da  lea     rdx, [rsp+7B0h+var_740]
0x1800253df  mov     rax, [rax+18h]
0x1800253e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253e8  mov     ebx, eax
0x1800253ea  test    eax, eax
0x1800253ec  jns     short loc_180025419
0x1800253ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253f5  lea     rdi, WPP_GLOBAL_Control
0x1800253fc  cmp     rcx, rdi
0x1800253ff  jz      loc_180025A11
0x180025405  test    byte ptr [rcx+1Ch], 2
0x180025409  jz      loc_180025A11
0x18002540f  mov     edx, 3Dh ; '='
0x180025414  jmp     loc_1800252AF
0x180025419  xor     ebx, ebx
0x18002541b  cmp     ebx, [rsp+7B0h+var_740]
0x18002541f  jnb     short loc_180025466
0x180025421  mov     rcx, [rsp+7B0h+var_738]
0x180025426  mov     rax, [rcx]
0x180025429  lea     r8, [rbp+6B0h+var_6B8]
0x18002542d  mov     edx, ebx
0x18002542f  mov     rax, [rax+20h]
0x180025433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025438  test    eax, eax
0x18002543a  js      short loc_18002545C
0x18002543c  cmp     [rbp+6B0h+var_6A8], 0Ch
0x180025440  jnz     short loc_18002545C
0x180025442  mov     r8d, 10h; Size
0x180025448  lea     rdx, [rbp+6B0h+var_6B8]; Buf2
0x18002544c  lea     rcx, WPD_OBJECT_ORIGINAL_FILE_NAME; Buf1
0x180025453  call    memcmp_0
0x180025458  test    eax, eax
0x18002545a  jz      short loc_180025460
0x18002545c  inc     ebx
0x18002545e  jmp     short loc_18002541B
0x180025460  mov     r13d, 1
0x180025466  mov     ebx, 104h
0x18002546b  mov     [rsp+7B0h+ExtCount], rbx; ExtCount
0x180025470  lea     rax, [rbp+6B0h+var_260]
0x180025477  mov     [rsp+7B0h+Ext], rax; Ext
0x18002547c  mov     [rsp+7B0h+FilenameCount], rbx; FilenameCount
0x180025481  lea     rax, [rbp+6B0h+var_470]
0x180025488  mov     [rsp+7B0h+Filename], rax; Filename
0x18002548d  mov     [rsp+7B0h+DirCount], 0; DirCount
0x180025496  xor     r9d, r9d; Dir
0x180025499  xor     r8d, r8d; DriveCount
0x18002549c  xor     edx, edx; Drive
0x18002549e  mov     rcx, [rsp+7B0h+FullPath]; FullPath
0x1800254a3  call    cs:__imp__wsplitpath_s
0x1800254a9  lea     rax, [rbp+6B0h+var_260]
0x1800254b0  mov     [rsp+7B0h+DirCount], rax
0x1800254b5  lea     r9, [rbp+6B0h+var_470]
0x1800254bc  lea     r8, aWsWs; "%ws%ws"
0x1800254c3  mov     edx, ebx; unsigned __int64
0x1800254c5  lea     rcx, [rbp+6B0h+var_680]; unsigned __int16 *
0x1800254c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800254ce  mov     rax, [rsi]
0x1800254d1  mov     rax, [rax+38h]
0x1800254d5  lea     r8, [rbp+6B0h+var_680]
0x1800254d9  mov     rcx, rsi
0x1800254dc  test    r13d, r13d
0x1800254df  jz      loc_180025574
0x1800254e5  lea     rdx, WPD_OBJECT_ORIGINAL_FILE_NAME
0x1800254ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254f1  mov     ebx, eax
0x1800254f3  test    eax, eax
0x1800254f5  jns     short loc_180025522
0x1800254f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254fe  lea     rdi, WPP_GLOBAL_Control
0x180025505  cmp     rcx, rdi
  ... truncated ...
```
