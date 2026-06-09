# CContentDropTarget::_CreateObject(_ITEMIDLIST const *,_ITEMIDLIST const *,IPortableDevice *,IPortableDeviceContent *,IPortableDeviceValues *,ushort const *,int,COPY_THREAD_DATA *,ushort *,uint)

- ea: `0x18003ab88`
- end: `0x18003b8de`
- name: `?_CreateObject@CContentDropTarget@@AEAAJPEFBU_ITEMIDLIST@@0PEAUIPortableDevice@@PEAUIPortableDeviceContent@@PEAUIPortableDeviceValues@@PEBGHPEAVCOPY_THREAD_DATA@@PEAGI@Z`
- size: `3414`
- prototype: `int(CContentDropTarget *__hidden this, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, struct IPortableDevice *, struct IPortableDeviceContent *, struct IPortableDeviceValues *, const unsigned __int16 *, int, struct COPY_THREAD_DATA *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800118d4`

## callees

- `0x180004110`
- `0x1800082e0`
- `0x18000ef50`
- `0x180014b60`
- `0x180014dd0`
- `0x180015108`
- `0x180016200`
- `0x1800177dc`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x180035590`
- `0x18003ab88`
- `0x18003b8e4`
- `0x180041ab0`
- `0x180052bcc`
- `0x180054524`
- `0x1800545c8`
- `0x18006b954`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18003af13`
- `KERNEL32!Sleep` at `0x18003b004`
- `KERNEL32!Sleep` at `0x18003b30a`
- `KERNEL32!Sleep` at `0x18003b4e4`
- `KERNEL32!Sleep` at `0x18003b670`
- `KERNEL32!Sleep` at `0x18003b7b6`
- `KERNEL32!Sleep` at `0x18003af13`
- `KERNEL32!Sleep` at `0x18003b004`
- `KERNEL32!Sleep` at `0x18003b30a`
- `KERNEL32!Sleep` at `0x18003b4e4`
- `KERNEL32!Sleep` at `0x18003b670`
- `KERNEL32!Sleep` at `0x18003b7b6`
- `ole32!CoTaskMemFree` at `0x18003b645`
- `ole32!CoTaskMemFree` at `0x18003b6d6`
- `ole32!CoTaskMemFree` at `0x18003b78d`
- `ole32!CoTaskMemFree` at `0x18003b813`
- `ole32!CoTaskMemFree` at `0x18003b645`
- `ole32!CoTaskMemFree` at `0x18003b6d6`
- `ole32!CoTaskMemFree` at `0x18003b78d`
- `ole32!CoTaskMemFree` at `0x18003b813`
- `ole32!PropVariantClear` at `0x18003b0f5`
- `ole32!PropVariantClear` at `0x18003b0f5`
- `SHELL32!SHBindToParent` at `0x18003adeb`
- `SHELL32!SHBindToParent` at `0x18003adeb`
- `SHELL32!__imp_ILFree` at `0x18003b855`
- `SHELL32!__imp_ILFree` at `0x18003b867`
- `SHELL32!__imp_ILFree` at `0x18003b855`
- `SHELL32!__imp_ILFree` at `0x18003b867`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CContentDropTarget::_CreateObject(
        CContentDropTarget *this,
        const struct _ITEMIDLIST *a2,
        const struct _ITEMIDLIST *a3,
        struct IPortableDevice *a4,
        struct IPortableDeviceContent *a5,
        struct IPortableDeviceValues *a6,
        unsigned __int16 *a7,
        int a8,
        CProgressUI **a9,
        unsigned __int16 *a10)
{
  struct IPortableDeviceValues *v11; // r14
  unsigned __int16 *v12; // r12
  CProgressUI *v13; // rdi
  int v14; // ebx
  int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // r14d
  HRESULT v21; // eax
  CContentFolder *v22; // rcx
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  int v26; // r12d
  int v27; // r12d
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  LARGE_INTEGER *v31; // rbx
  int v32; // ecx
  PVOID *v33; // rcx
  int v34; // eax
  struct IPortableDevice *v35; // r14
  int v36; // r12d
  CContentDropTarget *v37; // rcx
  int v38; // r14d
  int v39; // r12d
  int v40; // ebx
  int v41; // r12d
  int v42; // r14d
  int v43; // r14d
  int v44; // r12d
  int v45; // ebx
  __int64 v47; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  struct IUnknown *v49; // [rsp+40h] [rbp-C0h] BYREF
  int v50; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v51; // [rsp+4Ch] [rbp-B4h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+50h] [rbp-B0h] BYREF
  struct COPY_THREAD_DATA *v53; // [rsp+58h] [rbp-A8h]
  struct IUnknown *v54; // [rsp+60h] [rbp-A0h] BYREF
  void *ppv; // [rsp+68h] [rbp-98h] BYREF
  struct IStream *v56; // [rsp+70h] [rbp-90h] BYREF
  PROPVARIANT pvar; // [rsp+78h] [rbp-88h] BYREF
  CContentDropTarget *v58; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v59; // [rsp+98h] [rbp-68h]
  LPITEMIDLIST v60; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v61; // [rsp+A8h] [rbp-58h] BYREF
  struct IPortableDevice *v62; // [rsp+B0h] [rbp-50h]
  struct IPortableDeviceContent *v63; // [rsp+B8h] [rbp-48h]
  struct IPortableDeviceValues *v64; // [rsp+C0h] [rbp-40h]
  LPITEMIDLIST pidl; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v66; // [rsp+D0h] [rbp-30h]
  const struct _ITEMIDLIST *v67; // [rsp+D8h] [rbp-28h]
  GUID Buf2; // [rsp+E0h] [rbp-20h] BYREF
  GUID v69; // [rsp+F0h] [rbp-10h] BYREF

  v62 = a4;
  v67 = a3;
  v58 = this;
  v63 = a5;
  v11 = a6;
  v64 = a6;
  v12 = a7;
  v59 = a7;
  v53 = (struct COPY_THREAD_DATA *)a9;
  v66 = a10;
  v13 = a9[557];
  v69 = WPD_OBJECT_FORMAT_UNSPECIFIED;
  Buf2 = WPD_CONTENT_TYPE_UNSPECIFIED;
  v51 = 0;
  pv = 0;
  v50 = 0;
  v60 = 0;
  pidl = 0;
  v56 = 0;
  v49 = 0;
  v54 = 0;
  CPerfTraceHelper::BeginOperation((CPerfTraceHelper *)(a9 + 560), 8u);
  v14 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, GUID *))v11->lpVtbl->GetGuidValue)(
          v11,
          &WPD_OBJECT_CONTENT_TYPE,
          &Buf2);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        139,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v14);
    goto LABEL_206;
  }
  if ( memcmp_0(&WPD_CONTENT_TYPE_FOLDER, &Buf2, 0x10u) )
  {
    v15 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, GUID *))a6->lpVtbl->GetGuidValue)(
            a6,
            &WPD_OBJECT_FORMAT,
            &v69);
    v14 = v15;
    if ( v15 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_206;
      v17 = 140;
      v18 = (unsigned int)v15;
      goto LABEL_10;
    }
    RemoveUnsupportedProperties(&Buf2, a6);
  }
  if ( memcmp_0(&WPD_CONTENT_TYPE_FOLDER, &Buf2, 0x10u) && memcmp_0(&WPD_OBJECT_FORMAT_PROPERTIES_ONLY, &v69, 0x10u) )
  {
    memset(&pvar, 0, sizeof(pvar));
    v20 = 0;
    v61 = 0;
    v47 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        *((unsigned int *)a9[4] + 3));
    if ( *((_DWORD *)a9[4] + 3) )
    {
      ppidlLast = 0;
      ppv = 0;
      v21 = SHBindToParent(a2, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &ppv, &ppidlLast);
      v14 = v21;
      if ( v21 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_23;
        v24 = 143;
        v25 = (unsigned int)v21;
        goto LABEL_22;
      }
      if ( !CContentFolder::_IsValid(v22, ppidlLast) )
      {
        v14 = -2147418113;
        goto LABEL_23;
      }
      if ( v13 )
      {
        v26 = 0;
        while ( !*((_DWORD *)v13 + 26) )
        {
          v14 = (*(__int64 (__fastcall **)(__int64, LPCITEMIDLIST, _QWORD, GUID *, struct IUnknown **))(*(_QWORD *)(*((_QWORD *)v58 + 10) + 16LL) + 40LL))(
                  *((_QWORD *)v58 + 10) + 16LL,
                  ppidlLast,
                  0,
                  &GUID_0000000c_0000_0000_c000_000000000046,
                  &v49);
          if ( v14 != -2147024726 )
            goto LABEL_39;
          if ( v49 )
            ATL::AtlComPtrAssign(&v49, 0);
          if ( !v26 )
          {
            v26 = 1;
            v20 = 1;
            CProgressUI::_StartMarquee(v13);
          }
          if ( *((_DWORD *)v13 + 26) )
            break;
          Sleep(0x5DCu);
        }
        v14 = -2147023673;
LABEL_39:
        if ( v20 )
          CProgressUI::_StopMarquee(v13);
        v20 = 0;
        if ( *((_DWORD *)v13 + 26) )
        {
          v14 = -2147023673;
          goto LABEL_45;
        }
        v12 = v59;
      }
      else
      {
        v14 = (*(__int64 (__fastcall **)(__int64, LPCITEMIDLIST, _QWORD, GUID *, struct IUnknown **))(*(_QWORD *)(*((_QWORD *)v58 + 10) + 16LL) + 40LL))(
                *((_QWORD *)v58 + 10) + 16LL,
                ppidlLast,
                0,
                &GUID_0000000c_0000_0000_c000_000000000046,
                &v49);
      }
      if ( v14 < 0 )
      {
LABEL_45:
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_23;
        v24 = 144;
        v25 = (unsigned int)v14;
LABEL_22:
        WPP_SF_d(v23[2], v24, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v25);
LABEL_23:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
        goto LABEL_177;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
LABEL_72:
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v49->lpVtbl->QueryInterface)(
             v49,
             &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
             &v47) < 0 )
      {
        v33 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids);
          v33 = (PVOID *)WPP_GLOBAL_Control;
        }
        v31 = (LARGE_INTEGER *)v53;
      }
      else
      {
        memset(&pvar, 0, sizeof(pvar));
        v31 = (LARGE_INTEGER *)v53;
        v32 = *(_DWORD *)(*((_QWORD *)v53 + 4) + 12LL);
        pvar.vt = 11;
        if ( v32 )
          pvar.iVal = -1;
        else
          pvar.iVal = 0;
        (*(void (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v47 + 48LL))(
          v47,
          &PKEY_WPDNSE_IsSameDevice,
          &pvar);
        PropVariantClear(&pvar);
        pvar.vt = 16401;
        pvar.hVal = v31[557];
        (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v47 + 48LL))(
          v47,
          &PKEY_WPDNSE_pProgressUI,
          &pvar);
        pvar.vt = 0;
        pvar.hVal.QuadPart = 0;
        if ( (*(int (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v47 + 40LL))(
               v47,
               &PKEY_WPDNSE_CanCopyObject,
               &pvar) >= 0
          && pvar.vt == 11
          && !pvar.iVal )
        {
          v14 = -2147483171;
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_177;
          v29 = 146;
          goto LABEL_70;
        }
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *(_DWORD *)(v31[4].QuadPart + 12) )
      {
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 0x40) != 0 )
          WPP_SF_(v33[2], 148, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids);
        ppidlLast = 0;
        v34 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, _QWORD))v49->lpVtbl[1].Release)(v49, 0, 0, 0);
        v14 = v34;
        if ( v34 < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_177;
          v29 = 149;
          goto LABEL_95;
        }
      }
      if ( v12 )
      {
        if ( v13 )
        {
          v36 = 0;
          while ( !*((_DWORD *)v13 + 26) )
          {
            v14 = CContentFolder::_CreateIDList(*((CContentFolder **)v58 + 10), v62, v59, 0, &v60, &v50);
            if ( v14 != -2147024726 )
              goto LABEL_107;
            if ( !v36 )
            {
              v36 = 1;
              v20 = 1;
              CProgressUI::_StartMarquee(v13);
            }
            if ( *((_DWORD *)v13 + 26) )
              break;
            Sleep(0x5DCu);
          }
          v14 = -2147023673;
LABEL_107:
          if ( v20 )
            CProgressUI::_StopMarquee(v13);
          if ( *((_DWORD *)v13 + 26) )
          {
            v14 = -2147023673;
            goto LABEL_113;
          }
          v12 = v59;
          v35 = v62;
        }
        else
        {
          v35 = v62;
          v14 = CContentFolder::_CreateIDList(*((CContentFolder **)v58 + 10), v62, v12, 0, &v60, &v50);
        }
        if ( v14 < 0 )
        {
LABEL_113:
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_177;
          v29 = 150;
          goto LABEL_70;
        }
        v34 = SHILCombine(v67, v60, &pidl);
        v14 = v34;
        if ( v34 < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_177;
          v29 = 151;
          goto LABEL_95;
        }
        v34 = CContentDropTarget::_DeleteExistingObject(v37, v35, v12, a8, v13);
        v14 = v34;
        if ( v34 < 0 )
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_177;
          v29 = 152;
          goto LABEL_95;
        }
        ChangeNotify(v50 != 0 ? 16 : 4, 0, pidl, 0);
      }
      if ( v13 )
      {
        v39 = 0;
        v40 = 0;
        while ( !*((_DWORD *)v13 + 26) )
        {
          v38 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, struct IPortableDeviceValues *, struct IUnknown **, unsigned int *, _QWORD))v63->lpVtbl->CreateObjectWithPropertiesAndData)(
                  v63,
                  v64,
                  &v54,
                  &v51,
                  0);
          if ( v38 != -2147024726 )
            goto LABEL_143;
          if ( v54 )
            ATL::AtlComPtrAssign(&v54, 0);
          if ( !v39 )
          {
            v39 = 1;
            v40 = 1;
            CProgressUI::_StartMarquee(v13);
          }
          if ( *((_DWORD *)v13 + 26) )
            break;
          Sleep(0x5DCu);
        }
        v38 = -2147023673;
LABEL_143:
        if ( v40 )
          CProgressUI::_StopMarquee(v13);
        if ( *((_DWORD *)v13 + 26) )
        {
          v14 = -2147023673;
LABEL_130:
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_177;
          v29 = 153;
          goto LABEL_70;
        }
      }
      else
      {
        v38 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, struct IPortableDeviceValues *, struct IUnknown **, unsigned int *, _QWORD))v63->lpVtbl->CreateObjectWithPropertiesAndData)(
                v63,
                v64,
                &v54,
                &v51,
                0);
      }
      v14 = 0;
      if ( v38 != -2147023893 )
        v14 = v38;
      if ( v14 < 0 )
        goto LABEL_130;
      v34 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IStream **))v54->lpVtbl->QueryInterface)(
              v54,
              &GUID_88e04db3_1012_4d64_9996_f703a950d3f4,
              &v56);
      v14 = v34;
      if ( v34 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_177;
        v29 = 154;
        goto LABEL_95;
      }
      v34 = StreamCopy(v56, (struct IStream *)v49, *((struct CProgressUI **)v53 + 557), v51, &v61, 1);
      v14 = v34;
      if ( v34 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_177;
        v29 = 155;
LABEL_95:
        v30 = (unsigned int)v34;
        goto LABEL_71;
      }
      if ( v13 )
      {
        v41 = 0;
        v42 = 0;
        while ( !*((_DWORD *)v13 + 26) )
        {
          v14 = ((__int64 (__fastcall *)(struct IStream *, LPVOID *))v56->lpVtbl[1].QueryInterface)(v56, &pv);
          if ( v14 != -2147024726 )
            goto LABEL_171;
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( !v41 )
          {
            v41 = 1;
            v42 = 1;
            CProgressUI::_StartMarquee(v13);
          }
          if ( *((_DWORD *)v13 + 26) )
            break;
          Sleep(0x5DCu);
        }
        v14 = -2147023673;
LABEL_171:
        if ( v42 )
          CProgressUI::_StopMarquee(v13);
        if ( *((_DWORD *)v13 + 26) )
        {
          v14 = -2147023673;
LABEL_158:
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_177;
          v29 = 156;
          goto LABEL_70;
        }
      }
      else
      {
        v14 = ((__int64 (__fastcall *)(struct IStream *, LPVOID *))v56->lpVtbl[1].QueryInterface)(v56, &pv);
      }
      if ( v14 >= 0 )
      {
        if ( pv )
        {
          StringCchCopyW(v66, 0x104u, (const unsigned __int16 *)pv);
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
        }
        else
        {
          v14 = -2147418113;
        }
        goto LABEL_177;
      }
      goto LABEL_158;
    }
    if ( v13 )
    {
      v27 = 0;
      while ( !*((_DWORD *)v13 + 26) )
      {
        v14 = SHBindToIDList(a2, v19, &GUID_0000000c_0000_0000_c000_000000000046, &v49);
        if ( v14 != -2147024726 )
          goto LABEL_61;
        if ( v49 )
          ATL::AtlComPtrAssign(&v49, 0);
        if ( !v27 )
        {
          v27 = 1;
          v20 = 1;
          CProgressUI::_StartMarquee(v13);
        }
        if ( *((_DWORD *)v13 + 26) )
          break;
        Sleep(0x5DCu);
      }
      v14 = -2147023673;
LABEL_61:
      if ( v20 )
        CProgressUI::_StopMarquee(v13);
      v20 = 0;
      if ( *((_DWORD *)v13 + 26) )
      {
        v14 = -2147023673;
        goto LABEL_67;
      }
      v12 = v59;
    }
    else
    {
      v14 = SHBindToIDList(a2, v19, &GUID_0000000c_0000_0000_c000_000000000046, &v49);
    }
    if ( v14 >= 0 )
      goto LABEL_72;
LABEL_67:
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_177;
    v29 = 145;
LABEL_70:
    v30 = (unsigned int)v14;
LABEL_71:
    WPP_SF_d(v28[2], v29, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v30);
LABEL_177:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
    goto LABEL_206;
  }
  if ( v13 )
  {
    v44 = 0;
    v45 = 0;
    while ( !*((_DWORD *)v13 + 26) )
    {
      v43 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, struct IPortableDeviceValues *, LPVOID *))v63->lpVtbl->CreateObjectWithPropertiesOnly)(
              v63,
              v11,
              &pv);
      if ( v43 != -2147024726 )
        goto LABEL_198;
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( !v44 )
      {
        v44 = 1;
        v45 = 1;
        CProgressUI::_StartMarquee(v13);
      }
      if ( *((_DWORD *)v13 + 26) )
        break;
      Sleep(0x5DCu);
      v11 = v64;
    }
    v43 = -2147023673;
LABEL_198:
    if ( v45 )
      CProgressUI::_StopMarquee(v13);
    if ( *((_DWORD *)v13 + 26) )
    {
      v14 = -2147023673;
LABEL_185:
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_206;
      v17 = 141;
      v18 = (unsigned int)v14;
LABEL_10:
      WPP_SF_d(v16[2], v17, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v18);
      goto LABEL_206;
    }
  }
  else
  {
    v43 = ((__int64 (__fastcall *)(struct IPortableDeviceContent *, struct IPortableDeviceValues *, LPVOID *))a5->lpVtbl->CreateObjectWithPropertiesOnly)(
            a5,
            a6,
            &pv);
  }
  v14 = 0;
  if ( v43 != -2147023893 )
    v14 = v43;
  if ( v14 < 0 )
    goto LABEL_185;
  if ( pv )
  {
    StringCchCopyW(v66, 0x104u, (const unsigned __int16 *)pv);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
  }
  else
  {
    v14 = -2147418113;
  }
LABEL_206:
  CPerfTraceHelper::ProcessPerformanceData(
    (struct COPY_THREAD_DATA *)((char *)v53 + 4480),
    8u,
    v14,
    (const unsigned __int16 *)v53 + 1444);
  if ( pidl )
    ILFree(pidl);
  if ( v60 )
    ILFree(v60);
  if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      157,
      WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
      (unsigned int)v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v56);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003ab88  push    rbp
0x18003ab8a  push    rbx
0x18003ab8b  push    rsi
0x18003ab8c  push    rdi
0x18003ab8d  push    r12
0x18003ab8f  push    r13
0x18003ab91  push    r14
0x18003ab93  push    r15
0x18003ab95  lea     rbp, [rsp-18h]
0x18003ab9a  sub     rsp, 118h
0x18003aba1  mov     rax, cs:__security_cookie
0x18003aba8  xor     rax, rsp
0x18003abab  mov     [rbp+50h+var_50], rax
0x18003abaf  mov     [rbp+50h+var_A0], r9
0x18003abb3  mov     [rbp+50h+var_78], r8
0x18003abb7  mov     r13, rdx
0x18003abba  mov     [rbp+50h+var_C0], rcx
0x18003abbe  mov     rsi, [rbp+50h+arg_20]
0x18003abc5  mov     [rbp+50h+var_98], rsi
0x18003abc9  mov     r14, [rbp+50h+arg_28]
0x18003abd0  mov     [rbp+50h+var_90], r14
0x18003abd4  mov     r12, [rbp+50h+arg_30]
0x18003abdb  mov     [rbp+50h+var_B8], r12
0x18003abdf  mov     r15, [rbp+50h+arg_40]
0x18003abe6  mov     [rsp+150h+var_F8], r15
0x18003abeb  mov     rax, [rbp+50h+arg_48]
0x18003abf2  mov     [rbp+50h+var_80], rax
0x18003abf6  mov     rdi, [r15+1168h]
0x18003abfd  movups  xmm0, xmmword ptr cs:WPD_OBJECT_FORMAT_UNSPECIFIED.Data1
0x18003ac04  movdqu  [rbp+50h+var_60], xmm0
0x18003ac09  movups  xmm1, xmmword ptr cs:WPD_CONTENT_TYPE_UNSPECIFIED.Data1
0x18003ac10  movdqu  [rbp+50h+Buf2], xmm1
0x18003ac15  xor     eax, eax
0x18003ac17  mov     [rsp+150h+var_104], eax
0x18003ac1b  mov     [rsp+150h+pv], rax
0x18003ac20  mov     [rsp+150h+var_108], eax
0x18003ac24  mov     [rbp+50h+var_B0], rax
0x18003ac28  mov     [rbp+50h+pidl], rax
0x18003ac2c  mov     [rsp+150h+var_E0], rax
0x18003ac31  mov     [rsp+150h+var_110], rax
0x18003ac36  mov     [rsp+150h+var_F0], rax
0x18003ac3b  lea     rcx, [r15+1180h]; this
0x18003ac42  lea     edx, [rax+8]; unsigned int
0x18003ac45  call    ?BeginOperation@CPerfTraceHelper@@QEAAXK@Z; CPerfTraceHelper::BeginOperation(ulong)
0x18003ac4a  mov     rax, [r14]
0x18003ac4d  lea     r8, [rbp+50h+Buf2]
0x18003ac51  lea     rdx, WPD_OBJECT_CONTENT_TYPE
0x18003ac58  mov     rcx, r14
0x18003ac5b  mov     rax, [rax+0E0h]
0x18003ac62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac67  mov     ebx, eax
0x18003ac69  lea     rax, WPP_GLOBAL_Control
0x18003ac70  test    ebx, ebx
0x18003ac72  jns     short loc_18003ACAB
0x18003ac74  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac7b  cmp     rcx, rax
0x18003ac7e  jz      loc_18003B822
0x18003ac84  test    byte ptr [rcx+1Ch], 2
0x18003ac88  jz      loc_18003B822
0x18003ac8e  mov     edx, 8Bh
0x18003ac93  mov     r9d, ebx
0x18003ac96  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003ac9d  mov     rcx, [rcx+10h]
0x18003aca1  call    WPP_SF_d
0x18003aca6  jmp     loc_18003B822
0x18003acab  mov     ebx, 10h
0x18003acb0  mov     r8d, ebx; Size
0x18003acb3  lea     rdx, [rbp+50h+Buf2]; Buf2
0x18003acb7  lea     rcx, WPD_CONTENT_TYPE_FOLDER; Buf1
0x18003acbe  call    memcmp_0
0x18003acc3  test    eax, eax
0x18003acc5  jz      short loc_18003AD39
0x18003acc7  mov     rax, [r14]
0x18003acca  lea     r8, [rbp+50h+var_60]
0x18003acce  lea     rdx, WPD_OBJECT_FORMAT
0x18003acd5  mov     rcx, r14
0x18003acd8  mov     rax, [rax+0E0h]
0x18003acdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ace4  mov     ebx, eax
0x18003ace6  test    eax, eax
0x18003ace8  jns     short loc_18003AD28
0x18003acea  mov     rcx, cs:WPP_GLOBAL_Control
0x18003acf1  lea     rsi, WPP_GLOBAL_Control
0x18003acf8  cmp     rcx, rsi
0x18003acfb  jz      loc_18003B829
0x18003ad01  test    byte ptr [rcx+1Ch], 2
0x18003ad05  jz      loc_18003B829
0x18003ad0b  mov     edx, 8Ch
0x18003ad10  mov     r9d, eax
0x18003ad13  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003ad1a  mov     rcx, [rcx+10h]
0x18003ad1e  call    WPP_SF_d
0x18003ad23  jmp     loc_18003B829
0x18003ad28  mov     rdx, r14; struct IPortableDeviceValues *
0x18003ad2b  lea     rcx, [rbp+50h+Buf2]; struct _GUID *
0x18003ad2f  call    ?RemoveUnsupportedProperties@@YAXAEBU_GUID@@PEAUIPortableDeviceValues@@@Z; RemoveUnsupportedProperties(_GUID const &,IPortableDeviceValues *)
0x18003ad34  mov     ebx, 10h
0x18003ad39  mov     r8, rbx; Size
0x18003ad3c  lea     rdx, [rbp+50h+Buf2]; Buf2
0x18003ad40  lea     rcx, WPD_CONTENT_TYPE_FOLDER; Buf1
0x18003ad47  call    memcmp_0
0x18003ad4c  test    eax, eax
0x18003ad4e  jz      loc_18003B6E7
0x18003ad54  mov     r8, rbx; Size
0x18003ad57  lea     rdx, [rbp+50h+var_60]; Buf2
0x18003ad5b  lea     rcx, WPD_OBJECT_FORMAT_PROPERTIES_ONLY; Buf1
0x18003ad62  call    memcmp_0
0x18003ad67  test    eax, eax
0x18003ad69  jz      loc_18003B6E7
0x18003ad6f  xorps   xmm0, xmm0
0x18003ad72  xor     eax, eax
0x18003ad74  movups  xmmword ptr [rsp+150h+pvar], xmm0
0x18003ad79  mov     qword ptr [rbp+50h+pvar+10h], rax
0x18003ad7d  xor     r14d, r14d
0x18003ad80  mov     [rbp+50h+var_A8], r14d
0x18003ad84  mov     [rsp+150h+var_120], r14
0x18003ad89  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ad90  lea     rsi, WPP_GLOBAL_Control
0x18003ad97  cmp     rcx, rsi
0x18003ad9a  jz      short loc_18003ADBF
0x18003ad9c  test    byte ptr [rcx+1Ch], 40h
0x18003ada0  jz      short loc_18003ADBF
0x18003ada2  mov     r9, [r15+20h]
0x18003ada6  mov     edx, 8Eh
0x18003adab  mov     r9d, [r9+0Ch]
0x18003adaf  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003adb6  mov     rcx, [rcx+10h]
0x18003adba  call    WPP_SF_d
0x18003adbf  mov     rax, [r15+20h]
0x18003adc3  cmp     [rax+0Ch], r14d
0x18003adc7  jz      loc_18003AF81
0x18003adcd  mov     [rsp+150h+ppidlLast], r14
0x18003add2  mov     [rsp+150h+ppv], r14
0x18003add7  lea     r9, [rsp+150h+ppidlLast]; ppidlLast
0x18003addc  lea     r8, [rsp+150h+ppv]; ppv
0x18003ade1  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x18003ade8  mov     rcx, r13; pidl
0x18003adeb  call    cs:__imp_SHBindToParent
0x18003adf1  mov     ebx, eax
0x18003adf3  test    eax, eax
0x18003adf5  jns     short loc_18003AE3C
0x18003adf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003adfe  cmp     rcx, rsi
0x18003ae01  jz      short loc_18003AE22
0x18003ae03  test    byte ptr [rcx+1Ch], 2
0x18003ae07  jz      short loc_18003AE22
0x18003ae09  mov     edx, 8Fh
0x18003ae0e  mov     r9d, eax
0x18003ae11  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x18003ae18  mov     rcx, [rcx+10h]
0x18003ae1c  call    WPP_SF_d
0x18003ae21  nop
0x18003ae22  lea     rcx, [rsp+150h+ppv]
0x18003ae27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ae2c  nop
0x18003ae2d  lea     rcx, [rsp+150h+var_120]
0x18003ae32  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ae37  jmp     loc_18003B829
0x18003ae3c  mov     rdx, [rsp+150h+ppidlLast]; struct _ITEMIDLIST *
0x18003ae41  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x18003ae46  test    rax, rax
0x18003ae49  jnz     short loc_18003AE52
0x18003ae4b  mov     ebx, 8000FFFFh
0x18003ae50  jmp     short loc_18003AE22
0x18003ae52  mov     esi, 800704C7h
0x18003ae57  mov     r15d, 1
0x18003ae5d  mov     r13d, 5DCh
0x18003ae63  test    rdi, rdi
0x18003ae66  jnz     short loc_18003AEA0
0x18003ae68  mov     rax, [rbp+50h+var_C0]
0x18003ae6c  mov     rcx, [rax+50h]
0x18003ae70  add     rcx, 10h
0x18003ae74  mov     rax, [rcx]
0x18003ae77  lea     rdx, [rsp+150h+var_110]
0x18003ae7c  mov     [rsp+150h+var_130], rdx
0x18003ae81  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x18003ae88  xor     r8d, r8d
0x18003ae8b  mov     rdx, [rsp+150h+ppidlLast]
0x18003ae90  mov     rax, [rax+28h]
0x18003ae94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae99  mov     ebx, eax
0x18003ae9b  jmp     loc_18003AF40
0x18003aea0  mov     r12d, r14d
0x18003aea3  cmp     dword ptr [rdi+68h], 0
0x18003aea7  jnz     short loc_18003AF20
0x18003aea9  mov     rax, [rbp+50h+var_C0]
0x18003aead  mov     rcx, [rax+50h]
0x18003aeb1  add     rcx, 10h
0x18003aeb5  mov     rax, [rcx]
0x18003aeb8  lea     rdx, [rsp+150h+var_110]
0x18003aebd  mov     [rsp+150h+var_130], rdx
0x18003aec2  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x18003aec9  xor     r8d, r8d
0x18003aecc  mov     rdx, [rsp+150h+ppidlLast]
0x18003aed1  mov     rax, [rax+28h]
0x18003aed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aeda  mov     ebx, eax
0x18003aedc  cmp     eax, 800700AAh
0x18003aee1  jnz     short loc_18003AF22
0x18003aee3  cmp     [rsp+150h+var_110], 0
0x18003aee9  jz      short loc_18003AEF7
0x18003aeeb  xor     edx, edx; struct IUnknown *
0x18003aeed  lea     rcx, [rsp+150h+var_110]; struct IUnknown **
0x18003aef2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003aef7  test    r12d, r12d
0x18003aefa  jnz     short loc_18003AF0A
0x18003aefc  mov     r12d, r15d
0x18003aeff  mov     r14d, r15d
0x18003af02  mov     rcx, rdi; this
0x18003af05  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003af0a  cmp     dword ptr [rdi+68h], 0
0x18003af0e  jnz     short loc_18003AF20
0x18003af10  mov     ecx, r13d; dwMilliseconds
0x18003af13  call    cs:__imp_Sleep
0x18003af19  test    r12d, r12d
0x18003af1c  jz      short loc_18003AF22
0x18003af1e  jmp     short loc_18003AEA3
0x18003af20  mov     ebx, esi
0x18003af22  test    r14d, r14d
0x18003af25  jz      short loc_18003AF2F
0x18003af27  mov     rcx, rdi; this
0x18003af2a  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003af2f  xor     r14d, r14d
0x18003af32  cmp     [rdi+68h], r14d
0x18003af36  jz      short loc_18003AF3C
0x18003af38  mov     ebx, esi
0x18003af3a  jmp     short loc_18003AF44
0x18003af3c  mov     r12, [rbp+50h+var_B8]
0x18003af40  test    ebx, ebx
0x18003af42  jns     short loc_18003AF72
0x18003af44  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af4b  lea     rsi, WPP_GLOBAL_Control
0x18003af52  cmp     rcx, rsi
0x18003af55  jz      loc_18003AE22
0x18003af5b  test    byte ptr [rcx+1Ch], 2
0x18003af5f  jz      loc_18003AE22
0x18003af65  mov     edx, 90h
0x18003af6a  mov     r9d, ebx
0x18003af6d  jmp     loc_18003AE11
0x18003af72  lea     rcx, [rsp+150h+ppv]
0x18003af77  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003af7c  jmp     loc_18003B079
0x18003af81  mov     esi, 800704C7h
0x18003af86  mov     r15d, 1
0x18003af8c  test    rdi, rdi
0x18003af8f  jnz     short loc_18003AFAC
0x18003af91  lea     r9, [rsp+150h+var_110]
0x18003af96  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x18003af9d  mov     rcx, r13
0x18003afa0  call    SHBindToIDList
0x18003afa5  mov     ebx, eax
0x18003afa7  jmp     loc_18003B031
0x18003afac  mov     r12d, r14d
0x18003afaf  cmp     dword ptr [rdi+68h], 0
0x18003afb3  jnz     short loc_18003B011
0x18003afb5  lea     r9, [rsp+150h+var_110]
0x18003afba  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x18003afc1  mov     rcx, r13
0x18003afc4  call    SHBindToIDList
0x18003afc9  mov     ebx, eax
0x18003afcb  cmp     eax, 800700AAh
0x18003afd0  jnz     short loc_18003B013
0x18003afd2  cmp     [rsp+150h+var_110], 0
0x18003afd8  jz      short loc_18003AFE6
0x18003afda  xor     edx, edx; struct IUnknown *
0x18003afdc  lea     rcx, [rsp+150h+var_110]; struct IUnknown **
0x18003afe1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18003afe6  test    r12d, r12d
0x18003afe9  jnz     short loc_18003AFF9
0x18003afeb  mov     r12d, r15d
0x18003afee  mov     r14d, r15d
0x18003aff1  mov     rcx, rdi; this
0x18003aff4  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x18003aff9  cmp     dword ptr [rdi+68h], 0
0x18003affd  jnz     short loc_18003B011
0x18003afff  mov     ecx, 5DCh; dwMilliseconds
0x18003b004  call    cs:__imp_Sleep
0x18003b00a  test    r12d, r12d
0x18003b00d  jz      short loc_18003B013
0x18003b00f  jmp     short loc_18003AFAF
0x18003b011  mov     ebx, esi
0x18003b013  test    r14d, r14d
0x18003b016  jz      short loc_18003B020
0x18003b018  mov     rcx, rdi; this
0x18003b01b  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x18003b020  xor     r14d, r14d
0x18003b023  cmp     [rdi+68h], r14d
0x18003b027  jz      short loc_18003B02D
0x18003b029  mov     ebx, esi
0x18003b02b  jmp     short loc_18003B035
0x18003b02d  mov     r12, [rbp+50h+var_B8]
0x18003b031  test    ebx, ebx
0x18003b033  jns     short loc_18003B073
0x18003b035  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b03c  lea     rsi, WPP_GLOBAL_Control
0x18003b043  cmp     rcx, rsi
0x18003b046  jz      loc_18003AE2D
0x18003b04c  test    byte ptr [rcx+1Ch], 2
0x18003b050  jz      loc_18003AE2D
0x18003b056  mov     edx, 91h
  ... truncated ...
```
