# CContentDropTarget::_GenerateThumbnailResource(_ITEMIDLIST const *,IPortableDevice *,IPortableDeviceContent *,_GUID const &,ushort const *,CProgressUI *)

- ea: `0x18003f890`
- end: `0x1800405e1`
- name: `?_GenerateThumbnailResource@CContentDropTarget@@AEAAJPEFBU_ITEMIDLIST@@PEAUIPortableDevice@@PEAUIPortableDeviceContent@@AEBU_GUID@@PEBGPEAVCProgressUI@@@Z`
- size: `3409`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, const struct _ITEMIDLIST *, struct IPortableDevice *, struct IPortableDeviceContent *, const struct _GUID *, const unsigned __int16 *, struct CProgressUI *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800118d4`

## callees

- `0x18000d540`
- `0x18000d610`
- `0x18000e760`
- `0x1800177dc`
- `0x18001d6b0`
- `0x1800206f0`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180033054`
- `0x180035590`
- `0x1800361ba`
- `0x18003f890`
- `0x1800409ac`
- `0x18004123c`
- `0x180054524`
- `0x1800545c8`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003fa47`
- `KERNEL32!Sleep` at `0x18003fc23`
- `KERNEL32!Sleep` at `0x18003fdc8`
- `KERNEL32!Sleep` at `0x18003fa47`
- `KERNEL32!Sleep` at `0x18003fc23`
- `KERNEL32!Sleep` at `0x18003fdc8`
- `GDI32!DeleteObject` at `0x18004045d`
- `GDI32!DeleteObject` at `0x18004045d`
- `ole32!PropVariantClear` at `0x180040260`
- `ole32!PropVariantClear` at `0x18004026a`
- `ole32!PropVariantClear` at `0x180040274`
- `ole32!PropVariantClear` at `0x180040521`
- `ole32!PropVariantClear` at `0x18004052b`
- `ole32!PropVariantClear` at `0x180040535`
- `ole32!PropVariantClear` at `0x18004053f`
- `ole32!PropVariantClear` at `0x180040260`
- `ole32!PropVariantClear` at `0x18004026a`
- `ole32!PropVariantClear` at `0x180040274`
- `ole32!PropVariantClear` at `0x180040521`
- `ole32!PropVariantClear` at `0x18004052b`
- `ole32!PropVariantClear` at `0x180040535`
- `ole32!PropVariantClear` at `0x18004053f`
- `SHELL32!SHBindToParent` at `0x180040322`
- `SHELL32!SHBindToParent` at `0x180040322`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CContentDropTarget::_GenerateThumbnailResource(
        CContentDropTarget *this,
        const struct _ITEMIDLIST *a2,
        struct IPortableDevice *a3,
        struct IPortableDeviceContent *a4,
        const struct _GUID *a5,
        unsigned __int16 *a6,
        struct CProgressUI *a7)
{
  unsigned int v9; // edi
  HRESULT ThumbnailFormatFromProfile; // esi
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // ebx
  unsigned int i; // ebx
  __int64 v17; // rax
  int v18; // ebx
  int v19; // ebx
  _DWORD *v20; // rbx
  int v21; // r12d
  unsigned int j; // r15d
  __int64 v23; // rax
  const struct std::nothrow_t *v24; // rdx
  unsigned int *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r9
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  int k; // r15d
  unsigned int *Ptr; // rax
  CContentDropTarget *v32; // rcx
  int v33; // edi
  int v34; // eax
  CContentDropTarget *v35; // rcx
  CContentDropTarget *v36; // rcx
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v44; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v46; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v47; // [rsp+60h] [rbp-A0h] BYREF
  struct IUnknown *v48; // [rsp+68h] [rbp-98h] BYREF
  struct IUnknown *v49; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v50[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v51; // [rsp+80h] [rbp-80h] BYREF
  __int64 v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-60h] BYREF
  HGDIOBJ ho; // [rsp+A8h] [rbp-58h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+B0h] [rbp-50h] BYREF
  PROPVARIANT v58; // [rsp+B8h] [rbp-48h] BYREF
  PROPVARIANT pvar; // [rsp+D0h] [rbp-30h] BYREF
  PROPVARIANT v60; // [rsp+E8h] [rbp-18h] BYREF
  PROPVARIANT v61; // [rsp+100h] [rbp+0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v63; // [rsp+120h] [rbp+20h]
  struct IPortableDeviceContent *v64; // [rsp+128h] [rbp+28h]
  CContentDropTarget *v65; // [rsp+130h] [rbp+30h]
  __int128 Buf1; // [rsp+138h] [rbp+38h] BYREF
  int v67; // [rsp+148h] [rbp+48h]
  __int128 v68; // [rsp+150h] [rbp+50h] BYREF
  struct _GUID v69; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v70[528]; // [rsp+170h] [rbp+70h] BYREF

  v64 = a4;
  pidl = a2;
  v65 = this;
  v63 = a6;
  v9 = 0;
  v49 = 0;
  v55 = 0;
  v54 = 0;
  v53 = 0;
  v47 = 0;
  v52 = 0;
  v48 = 0;
  Buf1 = 0;
  v67 = 0;
  v44 = 0;
  v51 = 0;
  v50[0] = 0;
  v69 = 0;
  v68 = 0;
  memset(&v58, 0, sizeof(v58));
  memset(&pvar, 0, sizeof(pvar));
  memset(&v60, 0, sizeof(v60));
  memset(&v61, 0, sizeof(v61));
  if ( !a2 || !a3 || !a4 || !a6 )
  {
    ThumbnailFormatFromProfile = -2147024809;
    goto LABEL_191;
  }
  v11 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, __int64 *))a4->lpVtbl->Transfer)(a4, &v55);
  ThumbnailFormatFromProfile = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_191;
    v13 = 182;
LABEL_10:
    v14 = (unsigned int)v11;
    goto LABEL_190;
  }
  if ( a7 )
  {
    v15 = 0;
    while ( !*((_DWORD *)a7 + 26) )
    {
      ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 **))(*(_QWORD *)v55 + 24LL))(
                                     v55,
                                     a6,
                                     &v47);
      if ( ThumbnailFormatFromProfile != -2147024726 )
        goto LABEL_25;
      if ( !v9 )
      {
        v9 = 1;
        v15 = 1;
        CProgressUI::_StartMarquee(a7);
      }
      if ( *((_DWORD *)a7 + 26) )
        break;
      Sleep(0x5DCu);
    }
    ThumbnailFormatFromProfile = -2147023673;
LABEL_25:
    v9 = 0;
    if ( v15 )
      CProgressUI::_StopMarquee(a7);
    if ( *((_DWORD *)a7 + 26) )
    {
      ThumbnailFormatFromProfile = -2147023673;
LABEL_14:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_191;
      v13 = 183;
LABEL_17:
      v14 = (unsigned int)ThumbnailFormatFromProfile;
      goto LABEL_190;
    }
  }
  else
  {
    ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64 **))(*(_QWORD *)v55 + 24LL))(
                                   v55,
                                   a6,
                                   &v47);
  }
  if ( ThumbnailFormatFromProfile < 0 )
    goto LABEL_14;
  v11 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v47 + 24))(v47, &v44);
  ThumbnailFormatFromProfile = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_191;
    v13 = 184;
    goto LABEL_10;
  }
  for ( i = 0; ; ++i )
  {
    v17 = *v47;
    if ( i >= v44 )
      break;
    (*(void (__fastcall **)(__int64 *, _QWORD, __int128 *))(v17 + 32))(v47, i, &Buf1);
    if ( !v67 && !memcmp_0(&Buf1, &WPD_RESOURCE_THUMBNAIL, 0x10u) )
    {
      ThumbnailFormatFromProfile = 1;
      goto LABEL_191;
    }
  }
  (*(void (**)(void))(v17 + 48))();
  v11 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a3->lpVtbl->Capabilities)(a3, &v53);
  ThumbnailFormatFromProfile = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_191;
    v13 = 185;
    goto LABEL_10;
  }
  if ( a7 )
  {
    v18 = 0;
    while ( !*((_DWORD *)a7 + 26) )
    {
      ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, const GUID *, struct IUnknown **))(*(_QWORD *)v53 + 48LL))(
                                     v53,
                                     &WPD_FUNCTIONAL_CATEGORY_RENDERING_INFORMATION,
                                     &v48);
      if ( ThumbnailFormatFromProfile != -2147024726 )
        goto LABEL_60;
      if ( v48 )
        ATL::AtlComPtrAssign(&v48, 0);
      if ( !v9 )
      {
        v9 = 1;
        v18 = 1;
        CProgressUI::_StartMarquee(a7);
      }
      if ( *((_DWORD *)a7 + 26) )
        break;
      Sleep(0x5DCu);
    }
    ThumbnailFormatFromProfile = -2147023673;
LABEL_60:
    v9 = 0;
    if ( v18 )
      CProgressUI::_StopMarquee(a7);
    if ( *((_DWORD *)a7 + 26) )
    {
      ThumbnailFormatFromProfile = -2147023673;
LABEL_47:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_191;
      v13 = 186;
      goto LABEL_17;
    }
  }
  else
  {
    ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, const GUID *, struct IUnknown **))(*(_QWORD *)v53 + 48LL))(
                                   v53,
                                   &WPD_FUNCTIONAL_CATEGORY_RENDERING_INFORMATION,
                                   &v48);
  }
  if ( ThumbnailFormatFromProfile < 0 )
    goto LABEL_47;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, PROPVARIANT *))v48->lpVtbl[1].AddRef)(v48, 0, &v58);
  ThumbnailFormatFromProfile = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_191;
    v13 = 187;
    goto LABEL_10;
  }
  if ( v58.vt != 31 )
  {
    ThumbnailFormatFromProfile = -2147418113;
    goto LABEL_191;
  }
  v11 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, __int64 *))a4->lpVtbl->Properties)(a4, &v54);
  ThumbnailFormatFromProfile = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_191;
    v13 = 188;
    goto LABEL_10;
  }
  (*(void (__fastcall **)(__int64 *, const PROPERTYKEY *))(*v47 + 40))(v47, &WPD_RENDERING_INFORMATION_PROFILES);
  if ( a7 )
  {
    v19 = 0;
    while ( !*((_DWORD *)a7 + 26) )
    {
      ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER, __int64 *, struct IUnknown **))(*(_QWORD *)v54 + 40LL))(
                                     v54,
                                     v58.hVal,
                                     v47,
                                     &v49);
      if ( ThumbnailFormatFromProfile != -2147024726 )
        goto LABEL_90;
      if ( v49 )
        ATL::AtlComPtrAssign(&v49, 0);
      if ( !v9 )
      {
        v9 = 1;
        v19 = 1;
        CProgressUI::_StartMarquee(a7);
      }
      if ( *((_DWORD *)a7 + 26) )
        break;
      Sleep(0x5DCu);
    }
    ThumbnailFormatFromProfile = -2147023673;
LABEL_90:
    v9 = 0;
    if ( v19 )
      CProgressUI::_StopMarquee(a7);
    if ( *((_DWORD *)a7 + 26) )
    {
      ThumbnailFormatFromProfile = -2147023673;
LABEL_77:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_191;
      v13 = 189;
      goto LABEL_17;
    }
  }
  else
  {
    ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, LARGE_INTEGER, __int64 *, struct IUnknown **))(*(_QWORD *)v54 + 40LL))(
                                   v54,
                                   v58.hVal,
                                   v47,
                                   &v49);
  }
  if ( ThumbnailFormatFromProfile < 0 )
    goto LABEL_77;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, __int64 *))v49->lpVtbl[12].Release)(
          v49,
          &WPD_RENDERING_INFORMATION_PROFILES,
          &v52);
  ThumbnailFormatFromProfile = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_191;
    v13 = 190;
    goto LABEL_10;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 24LL))(v52, &v44);
  ThumbnailFormatFromProfile = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_191;
    v13 = 191;
    goto LABEL_10;
  }
  v20 = (_DWORD *)IsolationAwareDPA_Create(10);
  if ( !v20 )
  {
    v14 = 2147942414LL;
    ThumbnailFormatFromProfile = -2147024882;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_191;
    v13 = 192;
LABEL_190:
    WPP_SF_d(v12[2], v13, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v14);
    goto LABEL_191;
  }
  ThumbnailFormatFromProfile = 0;
  v21 = 0;
  for ( j = 0; j < v44; ++j )
  {
    v42 = 0;
    ppv = 0;
    v46 = 0;
    v45 = 0;
    ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 32LL))(
                                   v52,
                                   j,
                                   &v42);
    if ( ThumbnailFormatFromProfile < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_128;
      v29 = 193;
LABEL_133:
      v27 = (unsigned int)ThumbnailFormatFromProfile;
      goto LABEL_127;
    }
    ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v42 + 224LL))(
                                   v42,
                                   &WPD_OBJECT_FORMAT,
                                   &v68);
    if ( ThumbnailFormatFromProfile < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_128;
      v29 = 194;
      goto LABEL_133;
    }
    v23 = v68 - *(_QWORD *)&a5->Data1;
    if ( (_QWORD)v68 == *(_QWORD *)&a5->Data1 )
      v23 = *((_QWORD *)&v68 + 1) - *(_QWORD *)a5->Data4;
    if ( !v23 )
    {
      (*(void (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v42 + 80LL))(
        v42,
        &WPD_RENDERING_INFORMATION_PROFILE_ENTRY_TYPE,
        &v45);
      if ( v45 == 1 )
      {
        v25 = (unsigned int *)operator new(4u, v24);
        if ( !v25 )
        {
          ThumbnailFormatFromProfile = -2147024882;
          goto LABEL_128;
        }
        *v25 = j;
        if ( (unsigned int)IsolationAwareDPA_InsertPtr(v20, v26, v25) == -1 )
        {
          v27 = 2147942414LL;
          ThumbnailFormatFromProfile = -2147024882;
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v29 = 195;
LABEL_127:
            WPP_SF_d(v28[2], v29, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v27);
          }
LABEL_128:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_185:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
          goto LABEL_186;
        }
        ThumbnailFormatFromProfile = 0;
      }
      else
      {
        ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, void **))(*(_QWORD *)v42 + 288LL))(
                                       v42,
                                       &WPD_RENDERING_INFORMATION_PROFILE_ENTRY_CREATABLE_RESOURCES,
                                       &ppv);
        if ( ThumbnailFormatFromProfile >= 0 )
        {
          ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(void *, unsigned int *))(*(_QWORD *)ppv + 24LL))(
                                         ppv,
                                         &v46);
          if ( ThumbnailFormatFromProfile < 0 )
          {
            v28 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v29 = 196;
              goto LABEL_133;
            }
            goto LABEL_128;
          }
          while ( v9 < v46 )
          {
            ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(void *, _QWORD, __int128 *))(*(_QWORD *)ppv + 32LL))(
                                           ppv,
                                           v9,
                                           &Buf1);
            if ( ThumbnailFormatFromProfile >= 0 && !v67 && !memcmp_0(&Buf1, &WPD_RESOURCE_THUMBNAIL, 0x10u) )
            {
              v21 = 1;
              break;
            }
            ++v9;
          }
          v9 = 0;
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  }
  if ( v21 != 1 )
    goto LABEL_186;
  for ( k = 0; ; ++k )
  {
    if ( k >= *v20 )
      goto LABEL_186;
    v42 = 0;
    Ptr = (unsigned int *)IsolationAwareDPA_GetPtr(v20, k);
    if ( Ptr )
      break;
LABEL_162:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  }
  ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 32LL))(
                                 v52,
                                 *Ptr,
                                 &v42);
  if ( ThumbnailFormatFromProfile < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        197,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)ThumbnailFormatFromProfile);
    goto LABEL_185;
  }
  ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v42 + 48LL))(
                                 v42,
                                 &WPD_RESOURCE_ATTRIBUTE_FORMAT,
                                 &v61);
  if ( ThumbnailFormatFromProfile < 0
    || v61.vt == 10
    || !v61.vt
    || (ThumbnailFormatFromProfile = CContentDropTarget::_GetThumbnailFormatFromProfile(v32, &v61, &v69),
        ThumbnailFormatFromProfile < 0) )
  {
LABEL_161:
    PropVariantClear(&v61);
    goto LABEL_162;
  }
  v33 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v42 + 48LL))(
          v42,
          &WPD_MEDIA_HEIGHT,
          &pvar);
  v34 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v42 + 48LL))(
          v42,
          &WPD_MEDIA_WIDTH,
          &v60);
  if ( v33 < 0 || pvar.vt == 10 || !pvar.vt || v34 < 0 || v60.vt == 10 || !v60.vt )
  {
    PropVariantClear(&pvar);
    PropVariantClear(&v60);
    goto LABEL_161;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ThumbnailFormatFromProfile = CContentDropTarget::_GetMaximumUnsignedIntegerValueFromProfile(v35, &pvar, &v51);
  if ( ThumbnailFormatFromProfile < 0 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v38 = 198;
LABEL_159:
      WPP_SF_d(v37[2], v38, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)ThumbnailFormatFromProfile);
      goto LABEL_186;
    }
    goto LABEL_186;
  }
  ThumbnailFormatFromProfile = CContentDropTarget::_GetMaximumUnsignedIntegerValueFromProfile(v36, &v60, v50);
  if ( ThumbnailFormatFromProfile >= 0 )
  {
    ppv = 0;
    v42 = 0;
    ppidlLast = 0;
    ho = 0;
    memset_0(v70, 0, 0x208u);
    v45 = 0x10000000;
    v46 = 320;
    v50[1] = v51;
    ThumbnailFormatFromProfile = SHBindToParent(pidl, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
    if ( ThumbnailFormatFromProfile >= 0 )
    {
      ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, LPCITEMIDLIST *, GUID *, _QWORD, __int64 *))(*(_QWORD *)ppv + 80LL))(
                                     ppv,
                                     0,
                                     1,
                                     &ppidlLast,
                                     &GUID_bb2e617c_0920_11d1_9a0b_00c04fc2d6c1,
                                     0,
                                     &v42);
      if ( ThumbnailFormatFromProfile >= 0 )
      {
        (*(void (__fastcall **)(__int64, _BYTE *, __int64, int *, unsigned int *, int, unsigned int *))(*(_QWORD *)v42 + 24LL))(
          v42,
          v70,
          260,
          &v45,
          v50,
          24,
          &v46);
        ThumbnailFormatFromProfile = (*(__int64 (__fastcall **)(__int64, HGDIOBJ *))(*(_QWORD *)v42 + 32LL))(v42, &ho);
        if ( ThumbnailFormatFromProfile < 0 )
          goto LABEL_172;
        ThumbnailFormatFromProfile = CContentDropTarget::_TransferThumbnailResource(
                                       v65,
                                       (HBITMAP)ho,
                                       v64,
                                       &v69,
                                       v63,
                                       a7);
        DeleteObject(ho);
        if ( ThumbnailFormatFromProfile >= 0 )
          goto LABEL_172;
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_172;
        v40 = 202;
      }
      else
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_172;
        v40 = 201;
      }
    }
    else
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_172;
      v40 = 200;
    }
    WPP_SF_d(v39[2], v40, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)ThumbnailFormatFromProfile);
LABEL_172:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    goto LABEL_186;
  }
  v37 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v38 = 199;
    goto LABEL_159;
  }
LABEL_186:
  IsolationAwareDPA_DestroyCallback(v20, DPA_DeleteCB<unsigned long>);
LABEL_191:
  PropVariantClear(&v58);
  PropVariantClear(&pvar);
  PropVariantClear(&v60);
  PropVariantClear(&v61);
  if ( ThumbnailFormatFromProfile < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      203,
      WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
      (unsigned int)ThumbnailFormatFromProfile);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  return (unsigned int)ThumbnailFormatFromProfile;
}

```

## disassembly

```asm
0x18003f890  push    rbp
0x18003f892  push    rbx
0x18003f893  push    rsi
0x18003f894  push    rdi
0x18003f895  push    r12
0x18003f897  push    r13
0x18003f899  push    r14
0x18003f89b  push    r15
0x18003f89d  lea     rbp, [rsp-298h]
0x18003f8a5  sub     rsp, 398h
0x18003f8ac  mov     rax, cs:__security_cookie
0x18003f8b3  xor     rax, rsp
0x18003f8b6  mov     [rbp+2D0h+var_50], rax
0x18003f8bd  mov     r12, r9
0x18003f8c0  mov     [rbp+2D0h+var_2A8], r9
0x18003f8c4  mov     r15, r8
0x18003f8c7  mov     [rbp+2D0h+pidl], rdx
0x18003f8cb  mov     [rbp+2D0h+var_2A0], rcx
0x18003f8cf  mov     r13, [rbp+2D0h+arg_28]
0x18003f8d6  mov     [rbp+2D0h+var_2B0], r13
0x18003f8da  mov     r14, [rbp+2D0h+arg_30]
0x18003f8e1  xor     edi, edi
0x18003f8e3  mov     [rsp+3D0h+var_360], rdi
0x18003f8e8  mov     [rbp+2D0h+var_330], rdi
0x18003f8ec  mov     [rbp+2D0h+var_338], rdi
0x18003f8f0  mov     [rbp+2D0h+var_340], rdi
0x18003f8f4  mov     [rsp+3D0h+var_370], rdi
0x18003f8f9  mov     [rbp+2D0h+var_348], rdi
0x18003f8fd  mov     [rsp+3D0h+var_368], rdi
0x18003f902  xorps   xmm0, xmm0
0x18003f905  xor     ecx, ecx
0x18003f907  movups  [rbp+2D0h+Buf1], xmm0
0x18003f90b  mov     [rbp+2D0h+var_288], ecx
0x18003f90e  mov     [rsp+3D0h+var_380], edi
0x18003f912  mov     [rbp+2D0h+var_350], edi
0x18003f915  mov     [rsp+3D0h+var_358], edi
0x18003f919  movups  xmmword ptr [rbp+2D0h+var_270.Data1], xmm0
0x18003f91d  xorps   xmm1, xmm1
0x18003f920  movups  [rbp+2D0h+var_280], xmm1
0x18003f924  movups  xmmword ptr [rbp+2D0h+var_318], xmm0
0x18003f928  mov     qword ptr [rbp+2D0h+var_318+10h], rcx
0x18003f92c  movups  xmmword ptr [rbp+2D0h+pvar], xmm1
0x18003f930  mov     qword ptr [rbp+2D0h+pvar+10h], rcx
0x18003f934  movups  xmmword ptr [rbp+2D0h+var_2E8], xmm0
0x18003f938  mov     qword ptr [rbp+2D0h+var_2E8+10h], rcx
0x18003f93c  movups  xmmword ptr [rbp+2D0h+var_2D0], xmm1
0x18003f940  mov     qword ptr [rbp+2D0h+var_2D0+10h], rcx
0x18003f944  lea     rbx, WPP_GLOBAL_Control
0x18003f94b  test    rdx, rdx
0x18003f94e  jnz     short loc_18003F95A
0x18003f950  mov     esi, 80070057h
0x18003f955  jmp     loc_18004051D
0x18003f95a  test    r15, r15
0x18003f95d  jz      short loc_18003F950
0x18003f95f  test    r12, r12
0x18003f962  jz      short loc_18003F950
0x18003f964  test    r13, r13
0x18003f967  jz      short loc_18003F950
0x18003f969  mov     rax, [r9]
0x18003f96c  lea     rdx, [rbp+2D0h+var_330]
0x18003f970  mov     rcx, r12
0x18003f973  mov     rax, [rax+28h]
0x18003f977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f97c  mov     esi, eax
0x18003f97e  test    eax, eax
0x18003f980  jns     short loc_18003F9A9
0x18003f982  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f989  cmp     rcx, rbx
0x18003f98c  jz      loc_18004051D
0x18003f992  test    byte ptr [rcx+1Ch], 2
0x18003f996  jz      loc_18004051D
0x18003f99c  mov     edx, 0B6h
0x18003f9a1  mov     r9d, eax
0x18003f9a4  jmp     loc_18004050D
0x18003f9a9  test    r14, r14
0x18003f9ac  jnz     short loc_18003F9FD
0x18003f9ae  mov     rcx, [rbp+2D0h+var_330]
0x18003f9b2  mov     rax, [rcx]
0x18003f9b5  lea     r8, [rsp+3D0h+var_370]
0x18003f9ba  mov     rdx, r13
0x18003f9bd  mov     rax, [rax+18h]
0x18003f9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9c6  mov     esi, eax
0x18003f9c8  mov     r13d, 800704C7h
0x18003f9ce  test    esi, esi
0x18003f9d0  jns     loc_18003FA8B
0x18003f9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f9dd  cmp     rcx, rbx
0x18003f9e0  jz      loc_18004051D
0x18003f9e6  test    byte ptr [rcx+1Ch], 2
0x18003f9ea  jz      loc_18004051D
0x18003f9f0  mov     edx, 0B7h
0x18003f9f5  mov     r9d, esi
0x18003f9f8  jmp     loc_18004050D
0x18003f9fd  xor     eax, eax
0x18003f9ff  mov     ebx, eax
0x18003fa01  cmp     [r14+68h], eax
0x18003fa05  jnz     short loc_18003FA80
0x18003fa07  mov     rcx, [rbp+2D0h+var_330]
0x18003fa0b  mov     rax, [rcx]
0x18003fa0e  lea     r8, [rsp+3D0h+var_370]
0x18003fa13  mov     rdx, r13
0x18003fa16  mov     rax, [rax+18h]
0x18003fa1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa1f  mov     esi, eax
0x18003fa21  cmp     eax, 800700AAh
0x18003fa26  jnz     short loc_18003FA53
0x18003fa28  test    edi, edi
0x18003fa2a  jnz     short loc_18003FA3B
0x18003fa2c  lea     eax, [rdi+1]
0x18003fa2f  mov     edi, eax
0x18003fa31  mov     ebx, eax
0x18003fa33  mov     rcx, r14; this
0x18003fa36  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003fa3b  cmp     dword ptr [r14+68h], 0
0x18003fa40  jnz     short loc_18003FA80
0x18003fa42  mov     ecx, 5DCh; dwMilliseconds
0x18003fa47  call    cs:__imp_Sleep
0x18003fa4d  xor     eax, eax
0x18003fa4f  test    edi, edi
0x18003fa51  jnz     short loc_18003FA01
0x18003fa53  mov     r13d, 800704C7h
0x18003fa59  xor     edi, edi
0x18003fa5b  test    ebx, ebx
0x18003fa5d  jz      short loc_18003FA67
0x18003fa5f  mov     rcx, r14; this
0x18003fa62  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003fa67  lea     rbx, WPP_GLOBAL_Control
0x18003fa6e  cmp     [r14+68h], edi
0x18003fa72  jz      loc_18003F9CE
0x18003fa78  mov     esi, r13d
0x18003fa7b  jmp     loc_18003F9D6
0x18003fa80  mov     r13d, 800704C7h
0x18003fa86  mov     esi, r13d
0x18003fa89  jmp     short loc_18003FA59
0x18003fa8b  mov     rcx, [rsp+3D0h+var_370]
0x18003fa90  mov     rax, [rcx]
0x18003fa93  lea     rdx, [rsp+3D0h+var_380]
0x18003fa98  mov     rax, [rax+18h]
0x18003fa9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003faa1  mov     esi, eax
0x18003faa3  test    eax, eax
0x18003faa5  jns     short loc_18003FACB
0x18003faa7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003faae  cmp     rcx, rbx
0x18003fab1  jz      loc_18004051D
0x18003fab7  test    byte ptr [rcx+1Ch], 2
0x18003fabb  jz      loc_18004051D
0x18003fac1  mov     edx, 0B8h
0x18003fac6  jmp     loc_18003F9A1
0x18003facb  mov     ebx, edi
0x18003facd  mov     rcx, [rsp+3D0h+var_370]
0x18003fad2  mov     rax, [rcx]
0x18003fad5  cmp     ebx, [rsp+3D0h+var_380]
0x18003fad9  jnb     short loc_18003FB1E
0x18003fadb  lea     r8, [rbp+2D0h+Buf1]
0x18003fadf  mov     edx, ebx
0x18003fae1  mov     rax, [rax+20h]
0x18003fae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003faea  cmp     [rbp+2D0h+var_288], edi
0x18003faed  jnz     short loc_18003FB09
0x18003faef  mov     r8d, 10h; Size
0x18003faf5  lea     rdx, WPD_RESOURCE_THUMBNAIL; Buf2
0x18003fafc  lea     rcx, [rbp+2D0h+Buf1]; Buf1
0x18003fb00  call    memcmp_0
0x18003fb05  test    eax, eax
0x18003fb07  jz      short loc_18003FB0D
0x18003fb09  inc     ebx
0x18003fb0b  jmp     short loc_18003FACD
0x18003fb0d  mov     esi, 1
0x18003fb12  lea     rbx, WPP_GLOBAL_Control
0x18003fb19  jmp     loc_18004051D
0x18003fb1e  mov     rax, [rax+30h]
0x18003fb22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb27  mov     rax, [r15]
0x18003fb2a  lea     rdx, [rbp+2D0h+var_340]
0x18003fb2e  mov     rcx, r15
0x18003fb31  mov     rax, [rax+30h]
0x18003fb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb3a  mov     esi, eax
0x18003fb3c  test    eax, eax
0x18003fb3e  jns     short loc_18003FB6B
0x18003fb40  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb47  lea     rbx, WPP_GLOBAL_Control
0x18003fb4e  cmp     rcx, rbx
0x18003fb51  jz      loc_18004051D
0x18003fb57  test    byte ptr [rcx+1Ch], 2
0x18003fb5b  jz      loc_18004051D
0x18003fb61  mov     edx, 0B9h
0x18003fb66  jmp     loc_18003F9A1
0x18003fb6b  test    r14, r14
0x18003fb6e  jnz     short loc_18003FBC1
0x18003fb70  mov     rcx, [rbp+2D0h+var_340]
0x18003fb74  mov     rax, [rcx]
0x18003fb77  lea     r8, [rsp+3D0h+var_368]
0x18003fb7c  lea     rdx, WPD_FUNCTIONAL_CATEGORY_RENDERING_INFORMATION
0x18003fb83  mov     rax, [rax+30h]
0x18003fb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb8c  mov     esi, eax
0x18003fb8e  test    esi, esi
0x18003fb90  jns     loc_18003FC52
0x18003fb96  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb9d  lea     rbx, WPP_GLOBAL_Control
0x18003fba4  cmp     rcx, rbx
0x18003fba7  jz      loc_18004051D
0x18003fbad  test    byte ptr [rcx+1Ch], 2
0x18003fbb1  jz      loc_18004051D
0x18003fbb7  mov     edx, 0BAh
0x18003fbbc  jmp     loc_18003F9F5
0x18003fbc1  xor     r15d, r15d
0x18003fbc4  mov     ebx, r15d
0x18003fbc7  cmp     [r14+68h], r15d
0x18003fbcb  jnz     short loc_18003FC2F
0x18003fbcd  mov     rcx, [rbp+2D0h+var_340]
0x18003fbd1  mov     rax, [rcx]
0x18003fbd4  lea     r8, [rsp+3D0h+var_368]
0x18003fbd9  lea     rdx, WPD_FUNCTIONAL_CATEGORY_RENDERING_INFORMATION
0x18003fbe0  mov     rax, [rax+30h]
0x18003fbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbe9  mov     esi, eax
0x18003fbeb  cmp     eax, 800700AAh
0x18003fbf0  jnz     short loc_18003FC32
0x18003fbf2  cmp     [rsp+3D0h+var_368], r15
0x18003fbf7  jz      short loc_18003FC05
0x18003fbf9  xor     edx, edx; struct IUnknown *
0x18003fbfb  lea     rcx, [rsp+3D0h+var_368]; struct IUnknown **
0x18003fc00  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003fc05  test    edi, edi
0x18003fc07  jnz     short loc_18003FC18
0x18003fc09  lea     eax, [rdi+1]
0x18003fc0c  mov     edi, eax
0x18003fc0e  mov     ebx, eax
0x18003fc10  mov     rcx, r14; this
0x18003fc13  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003fc18  cmp     [r14+68h], r15d
0x18003fc1c  jnz     short loc_18003FC2F
0x18003fc1e  mov     ecx, 5DCh; dwMilliseconds
0x18003fc23  call    cs:__imp_Sleep
0x18003fc29  test    edi, edi
0x18003fc2b  jz      short loc_18003FC32
0x18003fc2d  jmp     short loc_18003FBC7
0x18003fc2f  mov     esi, r13d
0x18003fc32  xor     edi, edi
0x18003fc34  test    ebx, ebx
0x18003fc36  jz      short loc_18003FC40
0x18003fc38  mov     rcx, r14; this
0x18003fc3b  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003fc40  cmp     [r14+68h], edi
0x18003fc44  jz      loc_18003FB8E
0x18003fc4a  mov     esi, r13d
0x18003fc4d  jmp     loc_18003FB96
0x18003fc52  mov     rcx, [rsp+3D0h+var_368]
0x18003fc57  mov     rax, [rcx]
0x18003fc5a  lea     r8, [rbp+2D0h+var_318]
0x18003fc5e  xor     edx, edx
0x18003fc60  mov     rax, [rax+20h]
0x18003fc64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc69  mov     esi, eax
0x18003fc6b  test    eax, eax
0x18003fc6d  jns     short loc_18003FC9A
0x18003fc6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc76  lea     rbx, WPP_GLOBAL_Control
0x18003fc7d  cmp     rcx, rbx
0x18003fc80  jz      loc_18004051D
0x18003fc86  test    byte ptr [rcx+1Ch], 2
0x18003fc8a  jz      loc_18004051D
0x18003fc90  mov     edx, 0BBh
0x18003fc95  jmp     loc_18003F9A1
0x18003fc9a  mov     eax, 1Fh
0x18003fc9f  cmp     ax, word ptr [rbp+2D0h+var_318]
0x18003fca3  jz      short loc_18003FCAF
0x18003fca5  mov     esi, 8000FFFFh
0x18003fcaa  jmp     loc_18003FB12
0x18003fcaf  mov     rax, [r12]
0x18003fcb3  lea     rdx, [rbp+2D0h+var_338]
0x18003fcb7  mov     rcx, r12
0x18003fcba  mov     rax, [rax+20h]
0x18003fcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fcc3  mov     esi, eax
0x18003fcc5  test    eax, eax
0x18003fcc7  jns     short loc_18003FCF4
0x18003fcc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fcd0  lea     rbx, WPP_GLOBAL_Control
0x18003fcd7  cmp     rcx, rbx
0x18003fcda  jz      loc_18004051D
0x18003fce0  test    byte ptr [rcx+1Ch], 2
0x18003fce4  jz      loc_18004051D
0x18003fcea  mov     edx, 0BCh
0x18003fcef  jmp     loc_18003F9A1
0x18003fcf4  mov     rcx, [rsp+3D0h+var_370]
0x18003fcf9  mov     rax, [rcx]
0x18003fcfc  lea     rdx, WPD_RENDERING_INFORMATION_PROFILES
0x18003fd03  mov     rax, [rax+28h]
0x18003fd07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd0c  test    r14, r14
0x18003fd0f  jnz     short loc_18003FD64
0x18003fd11  mov     rcx, [rbp+2D0h+var_338]
0x18003fd15  mov     rax, [rcx]
0x18003fd18  lea     r9, [rsp+3D0h+var_360]
0x18003fd1d  mov     r8, [rsp+3D0h+var_370]
  ... truncated ...
```
