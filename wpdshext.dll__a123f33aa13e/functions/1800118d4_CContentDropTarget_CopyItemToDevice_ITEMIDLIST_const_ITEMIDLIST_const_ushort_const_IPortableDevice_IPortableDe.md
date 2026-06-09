# CContentDropTarget::_CopyItemToDevice(_ITEMIDLIST const *,_ITEMIDLIST const *,ushort const *,IPortableDevice *,IPortableDeviceContent *,ulong,ushort const *,int,COPY_THREAD_DATA *,ushort *,uint,ushort const *)

- ea: `0x1800118d4`
- end: `0x1800123ff`
- name: `?_CopyItemToDevice@CContentDropTarget@@AEAAJPEFBU_ITEMIDLIST@@0PEBGPEAUIPortableDevice@@PEAUIPortableDeviceContent@@K1HPEAVCOPY_THREAD_DATA@@PEAGI1@Z`
- size: `2859`
- prototype: `__int64 __usercall@<rax>(CContentDropTarget *__hidden this@<rcx>, const struct _ITEMIDLIST *@<rdx>, const struct _ITEMIDLIST *@<r8>, const unsigned __int16 *@<r9>, struct IPortableDevice *, struct IPortableDeviceContent *, unsigned int, const unsigned __int16 *, int, struct COPY_THREAD_DATA *, unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019e44`
- `0x18003ee9c`

## callees

- `0x180003f20`
- `0x180004110`
- `0x180004190`
- `0x1800082e0`
- `0x1800118d4`
- `0x180012408`
- `0x180012974`
- `0x1800147ec`
- `0x180025048`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039d74`
- `0x180039e80`
- `0x18003ab88`
- `0x18003f890`
- `0x180040e08`
- `0x180040e84`
- `0x180051ee0`
- `0x180054524`
- `0x1800545c8`
- `0x18006260c`
- `0x180072884`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180011e20`
- `KERNEL32!Sleep` at `0x180011e20`
- `SHLWAPI!StrRetToBufW` at `0x180011b04`
- `SHLWAPI!StrRetToBufW` at `0x180011b04`
- `ole32!CoCreateInstance` at `0x180011b77`
- `ole32!CoCreateInstance` at `0x180011b77`
- `SHELL32!SHBindToParent` at `0x180011a36`
- `SHELL32!SHBindToParent` at `0x180011c61`
- `SHELL32!SHBindToParent` at `0x180011a36`
- `SHELL32!SHBindToParent` at `0x180011c61`
- `SHELL32!__imp_ILFindLastID` at `0x180011c2b`
- `SHELL32!__imp_ILFindLastID` at `0x180011d6a`
- `SHELL32!__imp_ILFindLastID` at `0x180011c2b`
- `SHELL32!__imp_ILFindLastID` at `0x180011d6a`
- `SHELL32!__imp_ILRemoveLastID` at `0x180011c41`
- `SHELL32!__imp_ILRemoveLastID` at `0x180011c49`
- `SHELL32!__imp_ILRemoveLastID` at `0x180011c41`
- `SHELL32!__imp_ILRemoveLastID` at `0x180011c49`
- `SHELL32!__imp_ILFree` at `0x180012318`
- `SHELL32!__imp_ILFree` at `0x180012318`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CContentDropTarget::_CopyItemToDevice(
        CContentDropTarget *this,
        const struct _ITEMIDLIST *a2,
        struct _ITEMIDLIST *a3,
        unsigned __int16 *a4,
        struct IPortableDevice *a5,
        struct IPortableDeviceContent *a6,
        unsigned int a7,
        unsigned __int16 *a8,
        int a9,
        CProgressUI **a10,
        unsigned __int16 *a11,
        unsigned int a12,
        unsigned __int16 *a13)
{
  struct COPY_THREAD_DATA *v15; // rsi
  CProgressUI *v16; // r15
  ITEMIDLIST *i; // rdi
  unsigned __int16 v18; // r10
  __int64 v19; // r11
  __int64 v20; // rcx
  const WCHAR *v21; // r8
  __int64 v22; // rdx
  unsigned __int16 *v23; // rax
  WCHAR v24; // r9
  unsigned __int16 *v25; // rcx
  HRESULT Instance; // eax
  int StringProperty; // ebx
  PVOID *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  const struct CONTENTITEM *v31; // rax
  CContentFolder *v32; // rcx
  unsigned int v33; // r9d
  const ITEMIDLIST *v34; // rsi
  void *v35; // rbx
  const struct _ITEMIDLIST *ID; // rax
  CContentFolder *v37; // rcx
  __int64 v38; // rdx
  const struct _ITEMIDLIST *v39; // rax
  CContentFolder *v40; // rcx
  const struct CONTENTITEM *v41; // rax
  int v42; // ebx
  int v43; // esi
  struct IPortableDevice *v44; // r14
  CContentDropTarget *v45; // rcx
  unsigned __int16 *v46; // rdx
  struct IPortableDeviceContent *v47; // rsi
  unsigned int v49; // [rsp+28h] [rbp-D8h]
  CProgressUI **v50; // [rsp+40h] [rbp-C0h]
  unsigned int v51; // [rsp+58h] [rbp-A8h]
  struct IPortableDeviceValues *v52; // [rsp+60h] [rbp-A0h] BYREF
  struct IPortableDevice *v53; // [rsp+68h] [rbp-98h] BYREF
  LPCITEMIDLIST pidl; // [rsp+70h] [rbp-90h] BYREF
  struct COPY_THREAD_DATA *v55; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v56; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v57; // [rsp+88h] [rbp-78h]
  int v58; // [rsp+90h] [rbp-70h]
  LPCITEMIDLIST ppidlLast; // [rsp+98h] [rbp-68h] BYREF
  struct IPortableDevice *v60; // [rsp+A0h] [rbp-60h]
  struct _ITEMIDLIST *v61; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v62; // [rsp+B0h] [rbp-50h]
  void *ppv; // [rsp+B8h] [rbp-48h] BYREF
  void *v64; // [rsp+C0h] [rbp-40h] BYREF
  LPCITEMIDLIST v65; // [rsp+C8h] [rbp-38h] BYREF
  struct IPortableDeviceContent *v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  struct _GUID Buf2; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v69; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR pszBuf[264]; // [rsp+100h] [rbp+0h] BYREF
  STRRET pstr; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v72; // [rsp+520h] [rbp+420h] BYREF
  char v73[526]; // [rsp+522h] [rbp+422h] BYREF
  _BYTE v74[528]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v75[264]; // [rsp+940h] [rbp+840h] BYREF
  unsigned __int16 v76[264]; // [rsp+B50h] [rbp+A50h] BYREF

  v57 = a4;
  v61 = a3;
  v60 = a5;
  v66 = a6;
  v15 = (struct COPY_THREAD_DATA *)a10;
  v55 = (struct COPY_THREAD_DATA *)a10;
  v62 = a11;
  v56 = a13;
  v16 = a10[557];
  v58 = (a7 & 0x20000000) != 0;
  Buf2 = 0;
  v69 = 0;
  ppidlLast = 0;
  v65 = 0;
  i = 0;
  pidl = 0;
  v72 = 0;
  memset_0(v73, 0, 0x206u);
  v18 = 0;
  v53 = 0;
  v64 = 0;
  ppv = 0;
  v52 = 0;
  v67 = 0;
  v19 = 260;
  if ( a8 )
    StringCchCopyW(&v72, 0x104u, a8);
  v20 = 2147483646;
  v21 = &String;
  v22 = v19;
  v23 = v62;
  do
  {
    if ( !v20 )
      break;
    v24 = *v21;
    if ( !*v21 )
      break;
    ++v21;
    *v23++ = v24;
    --v20;
    --v22;
  }
  while ( v22 );
  v25 = v23 - 1;
  if ( v22 )
    v25 = v23;
  *v25 = v18;
  Instance = SHBindToParent(a2, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &ppv, &ppidlLast);
  StringProperty = Instance;
  if ( Instance < 0 )
  {
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_135;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_132;
    v29 = 158;
    goto LABEL_13;
  }
  if ( *(_DWORD *)(*((_QWORD *)v15 + 4) + 24LL) )
  {
    v31 = CContentFolder::_IsValid(0, ppidlLast);
    if ( !v31 )
    {
      StringProperty = -2147418113;
LABEL_131:
      v28 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_132;
    }
    CContentFolder::_Name(v32, v31, pszBuf, v33);
LABEL_25:
    Instance = CoCreateInstance(
                 &CLSID_PortableDeviceValues,
                 0,
                 1u,
                 &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143,
                 (LPVOID *)&v52);
    StringProperty = Instance;
    if ( Instance < 0 )
    {
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_135;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_132;
      v29 = 160;
      goto LABEL_13;
    }
    if ( *(_DWORD *)(*((_QWORD *)v15 + 4) + 24LL) )
    {
      StringProperty = SHILClone(a2, &pidl);
      if ( StringProperty < 0 )
      {
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
          i = (ITEMIDLIST *)pidl;
          goto LABEL_123;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          161,
          WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
          (unsigned int)StringProperty);
        i = (ITEMIDLIST *)pidl;
        goto LABEL_122;
      }
      for ( i = (ITEMIDLIST *)pidl; i && i->mkid.cb; ILRemoveLastID(i) )
      {
        ID = ILFindLastID(i);
        if ( !CContentFolder::_IsValid(v37, ID) )
        {
          ILRemoveLastID(i);
          break;
        }
      }
      StringProperty = SHBindToParent(i, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &v64, &v65);
      if ( StringProperty < 0 )
      {
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v38 = 162;
LABEL_45:
          WPP_SF_d(v28[2], v38, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)StringProperty);
LABEL_122:
          v28 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_123;
        }
        goto LABEL_123;
      }
      StringProperty = GetStringProperty(v64, v65, &PKEY_WPDNSE_PnPDevicePath, v74, 260);
      if ( StringProperty < 0 )
      {
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v38 = 163;
          goto LABEL_45;
        }
        goto LABEL_123;
      }
      StringProperty = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, struct IPortableDevice **))(**((_QWORD **)this + 10)
                                                                                             + 128LL))(
                         *((_QWORD *)this + 10),
                         v74,
                         &v53);
      if ( StringProperty < 0 )
      {
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            164,
            (unsigned int)WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
            (unsigned int)v74,
            StringProperty);
          goto LABEL_122;
        }
        goto LABEL_123;
      }
      v39 = ILFindLastID(a2);
      v41 = CContentFolder::_IsValid(v40, v39);
      if ( !v41 )
      {
        StringProperty = -2147418113;
        goto LABEL_122;
      }
      StringCchCopyW(
        v75,
        0x104u,
        (const unsigned __int16 *)v41 + *(unsigned int *)((char *)v41 + 62) + *(unsigned int *)((char *)v41 + 66) + 37);
      if ( v16 )
      {
        v42 = 0;
        v43 = 0;
        while ( !*((_DWORD *)v16 + 26) && (unsigned int)GetObjectID(v53, v75, v76, 0x104u) == -2147024726 )
        {
          if ( !v42 )
          {
            v42 = 1;
            v43 = 1;
            CProgressUI::_StartMarquee(v16);
          }
          if ( *((_DWORD *)v16 + 26) )
            break;
          Sleep(0x5DCu);
        }
        if ( v43 )
          CProgressUI::_StopMarquee(v16);
        v15 = v55;
      }
      else
      {
        GetObjectID(v53, v75, v76, 0x104u);
      }
      StringProperty = GetWpdProperties(v53, v76, v57, pszBuf, v56, v16, &v52);
      if ( StringProperty < 0 )
      {
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v38 = 165;
          goto LABEL_45;
        }
        goto LABEL_123;
      }
      goto LABEL_81;
    }
    if ( (a7 & 0x20000000) != 0 )
    {
      Instance = GetFolderProperties(v52, a2, v57, pszBuf, v56);
      StringProperty = Instance;
      if ( Instance >= 0 )
      {
LABEL_81:
        v44 = v60;
        goto LABEL_82;
      }
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_135;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_132;
      v29 = 166;
    }
    else
    {
      v44 = v60;
      Instance = GetFileProperties(v60, v52, a2, *((struct CBaseFolder **)this + 10), v61, v57, pszBuf, v56, v16, 0);
      StringProperty = Instance;
      if ( Instance >= 0 )
      {
LABEL_82:
        StringProperty = CContentDropTarget::_CheckForDuplicateFileOnDevice(
                           this,
                           a2,
                           v61,
                           v52,
                           v15,
                           v57,
                           v44,
                           v66,
                           v56,
                           &a9,
                           &v72,
                           v51);
        if ( StringProperty >= 0 )
        {
          if ( StringProperty == 1 )
            goto LABEL_122;
          if ( (unsigned int)CContentDropTarget::_IsEDPEvaluationRequired(v45, a7, v15) )
          {
            StringProperty = EdpCache::EvaluatePolicy(
                               (CContentDropTarget *)((char *)this + 88),
                               *((struct CProgressUI **)v15 + 557),
                               pszBuf,
                               v44,
                               (unsigned __int16 *)&pstr,
                               v49,
                               v58);
            if ( StringProperty < 0 )
            {
              v28 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v38 = 169;
                goto LABEL_45;
              }
              goto LABEL_123;
            }
            if ( LOWORD(pstr.uType) )
            {
              StringProperty = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, __int64 *, STRRET *))v52->lpVtbl->SetStringValue)(
                                 v52,
                                 WPD_OBJECT_MTP_IDENTITYSTRING,
                                 &pstr);
              if ( StringProperty < 0 )
              {
                v28 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v38 = 170;
                  goto LABEL_45;
                }
                goto LABEL_123;
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, pszBuf);
          }
          StringProperty = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, struct _GUID *))v52->lpVtbl->GetGuidValue)(
                             v52,
                             &WPD_OBJECT_CONTENT_TYPE,
                             &Buf2);
          if ( StringProperty >= 0 )
          {
            if ( !memcmp_0(&WPD_CONTENT_TYPE_UNSPECIFIED, &Buf2, 0x10u)
              || !memcmp_0(&WPD_CONTENT_TYPE_GENERIC_FILE, &Buf2, 0x10u) )
            {
              ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))v52->lpVtbl->SetBoolValue)(
                v52,
                &WPD_OBJECT_NON_CONSUMABLE,
                1);
            }
            StringProperty = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, struct _GUID *))v52->lpVtbl->GetGuidValue)(
                               v52,
                               &WPD_OBJECT_FORMAT,
                               &v69);
            if ( StringProperty >= 0 )
            {
              if ( memcmp_0(&WPD_OBJECT_FORMAT_WMA, &v69, 0x10u) && memcmp_0(&WPD_OBJECT_FORMAT_WMV, &v69, 0x10u) )
                ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))v52->lpVtbl->SetBoolValue)(
                  v52,
                  &WPD_API_OPTION_USE_CLEAR_DATA_STREAM,
                  1);
              v46 = &v72;
              if ( !v72 )
                v46 = 0;
              v50 = (CProgressUI **)v15;
              v47 = v66;
              StringProperty = CContentDropTarget::_CreateObject(this, a2, v61, v44, v66, v52, v46, a9, v50, v62);
              if ( StringProperty >= 0 )
              {
                if ( (unsigned int)CContentDropTarget::_IsThumbnailResourceGenerationEnabled(this, v44, &Buf2) )
                  CContentDropTarget::_GenerateThumbnailResource(this, a2, v44, v47, &v69, v62, v16);
                goto LABEL_122;
              }
              v28 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v38 = 174;
                goto LABEL_45;
              }
            }
            else
            {
              v28 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v38 = 173;
                goto LABEL_45;
              }
            }
          }
          else
          {
            v28 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v38 = 172;
              goto LABEL_45;
            }
          }
          goto LABEL_123;
        }
        v28 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v38 = 168;
          goto LABEL_45;
        }
LABEL_123:
        if ( i )
        {
          ILFree(i);
          v28 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( StringProperty < 0 )
          goto LABEL_132;
        goto LABEL_135;
      }
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_135;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_132;
      v29 = 167;
    }
LABEL_13:
    v30 = (unsigned int)Instance;
LABEL_130:
    WPP_SF_d(v28[2], v29, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v30);
    goto LABEL_131;
  }
  v34 = ppidlLast;
  v35 = ppv;
  pszBuf[0] = 0;
  memset_0(&pstr, 0, sizeof(pstr));
  StringProperty = (*(__int64 (__fastcall **)(void *, const ITEMIDLIST *, __int64, STRRET *))(*(_QWORD *)v35 + 88LL))(
                     v35,
                     v34,
                     0x8000,
                     &pstr);
  if ( StringProperty >= 0 )
  {
    StringProperty = StrRetToBufW(&pstr, v34, pszBuf, 0x104u);
    if ( StringProperty >= 0 )
    {
      v15 = v55;
      goto LABEL_25;
    }
  }
  v28 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids,
        (unsigned int)StringProperty);
      v28 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v28 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v28 + 28) & 2) == 0 )
      {
LABEL_132:
        if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 2) != 0 )
          WPP_SF_d(v28[2], 175, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)StringProperty);
        goto LABEL_135;
      }
      v29 = 159;
      v30 = (unsigned int)StringProperty;
      goto LABEL_130;
    }
  }
LABEL_135:
  if ( v52 )
    ((void (__fastcall *)(struct IPortableDeviceValues *))v52->lpVtbl->Release)(v52);
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v64 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v53 )
    ((void (__fastcall *)(struct IPortableDevice *))v53->lpVtbl->Release)(v53);
  return (unsigned int)StringProperty;
}

```

## disassembly

```asm
0x1800118d4  push    rbp
0x1800118d6  push    rbx
0x1800118d7  push    rsi
0x1800118d8  push    rdi
0x1800118d9  push    r12
0x1800118db  push    r13
0x1800118dd  push    r14
0x1800118df  push    r15
0x1800118e1  lea     rbp, [rsp-0C78h]
0x1800118e9  sub     rsp, 0D78h
0x1800118f0  mov     rax, cs:__security_cookie
0x1800118f7  xor     rax, rsp
0x1800118fa  mov     [rbp+0CB0h+var_50], rax
0x180011901  mov     [rbp+0CB0h+var_D28], r9
0x180011905  mov     [rbp+0CB0h+var_D08], r8
0x180011909  mov     r12, rdx
0x18001190c  mov     r13, rcx
0x18001190f  mov     rax, [rbp+0CB0h+arg_20]
0x180011916  mov     [rbp+0CB0h+var_D10], rax
0x18001191a  mov     rax, [rbp+0CB0h+arg_28]
0x180011921  mov     [rbp+0CB0h+var_CE0], rax
0x180011925  mov     rbx, [rbp+0CB0h+arg_38]
0x18001192c  mov     rsi, [rbp+0CB0h+arg_48]
0x180011933  mov     [rsp+0DB0h+var_D38], rsi
0x180011938  mov     rax, [rbp+0CB0h+arg_50]
0x18001193f  mov     [rbp+0CB0h+var_D00], rax
0x180011943  mov     rax, [rbp+0CB0h+arg_60]
0x18001194a  mov     [rbp+0CB0h+var_D30], rax
0x18001194e  mov     r15, [rsi+1168h]
0x180011955  mov     r14d, [rbp+0CB0h+arg_30]
0x18001195c  and     r14d, 20000000h
0x180011963  mov     ecx, 0
0x180011968  mov     eax, ecx
0x18001196a  setnz   al
0x18001196d  mov     [rbp+0CB0h+var_D20], eax
0x180011970  xorps   xmm0, xmm0
0x180011973  movups  [rbp+0CB0h+Buf2], xmm0
0x180011977  xorps   xmm1, xmm1
0x18001197a  movups  xmmword ptr [rbp+0CB0h+var_CC0.Data1], xmm1
0x18001197e  mov     [rbp+0CB0h+ppidlLast], rcx
0x180011982  mov     [rbp+0CB0h+var_CE8], rcx
0x180011986  mov     edi, ecx
0x180011988  mov     [rsp+0DB0h+pidl], rcx
0x18001198d  mov     [rbp+0CB0h+var_890], cx
0x180011994  xor     edx, edx; Val
0x180011996  mov     r8d, 206h; Size
0x18001199c  lea     rcx, [rbp+0CB0h+var_88E]; void *
0x1800119a3  call    memset_0
0x1800119a8  xor     r10d, r10d
0x1800119ab  mov     [rsp+0DB0h+var_D48], r10
0x1800119b0  mov     [rbp+0CB0h+var_CF0], r10
0x1800119b4  mov     [rbp+0CB0h+ppv], r10
0x1800119b8  mov     [rsp+0DB0h+var_D50], r10
0x1800119bd  mov     [rbp+0CB0h+var_CD8], r10
0x1800119c1  mov     r11d, 104h
0x1800119c7  test    rbx, rbx
0x1800119ca  jz      short loc_1800119DE
0x1800119cc  mov     r8, rbx; unsigned __int16 *
0x1800119cf  mov     edx, r11d; unsigned __int64
0x1800119d2  lea     rcx, [rbp+0CB0h+var_890]; unsigned __int16 *
0x1800119d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800119de  mov     ecx, 7FFFFFFEh
0x1800119e3  lea     r8, String
0x1800119ea  mov     rdx, r11
0x1800119ed  mov     rax, [rbp+0CB0h+var_D00]
0x1800119f1  test    rcx, rcx
0x1800119f4  jz      short loc_180011A15
0x1800119f6  movzx   r9d, word ptr [r8]
0x1800119fa  test    r9w, r9w
0x1800119fe  jz      short loc_180011A15
0x180011a00  add     r8, 2
0x180011a04  mov     [rax], r9w
0x180011a08  add     rax, 2
0x180011a0c  dec     rcx
0x180011a0f  sub     rdx, 1
0x180011a13  jnz     short loc_1800119F1
0x180011a15  lea     rcx, [rax-2]
0x180011a19  test    rdx, rdx
0x180011a1c  cmovnz  rcx, rax
0x180011a20  mov     [rcx], r10w
0x180011a24  lea     r9, [rbp+0CB0h+ppidlLast]; ppidlLast
0x180011a28  lea     r8, [rbp+0CB0h+ppv]; ppv
0x180011a2c  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x180011a33  mov     rcx, r12; pidl
0x180011a36  call    cs:__imp_SHBindToParent
0x180011a3c  mov     ebx, eax
0x180011a3e  xor     ecx, ecx; this
0x180011a40  test    eax, eax
0x180011a42  jns     short loc_180011A72
0x180011a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a4b  lea     rsi, WPP_GLOBAL_Control
0x180011a52  cmp     rcx, rsi
0x180011a55  jz      loc_180012380
0x180011a5b  test    byte ptr [rcx+1Ch], 2
0x180011a5f  jz      loc_18001235C
0x180011a65  mov     edx, 9Eh
0x180011a6a  mov     r9d, eax
0x180011a6d  jmp     loc_180012345
0x180011a72  mov     rax, [rsi+20h]
0x180011a76  cmp     [rax+18h], ecx
0x180011a79  jz      short loc_180011AAB
0x180011a7b  mov     rdx, [rbp+0CB0h+ppidlLast]; struct _ITEMIDLIST *
0x180011a7f  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180011a84  test    rax, rax
0x180011a87  jnz     short loc_180011A9A
0x180011a89  mov     ebx, 8000FFFFh
0x180011a8e  lea     rsi, WPP_GLOBAL_Control
0x180011a95  jmp     loc_180012355
0x180011a9a  lea     r8, [rbp+0CB0h+pszBuf]; unsigned __int16 *
0x180011a9e  mov     rdx, rax; struct CONTENTITEM *
0x180011aa1  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x180011aa6  jmp     loc_180011B59
0x180011aab  mov     rsi, [rbp+0CB0h+ppidlLast]
0x180011aaf  mov     rbx, [rbp+0CB0h+ppv]
0x180011ab3  mov     [rbp+0CB0h+pszBuf], cx
0x180011ab7  xor     edx, edx; Val
0x180011ab9  mov     r8d, 110h; Size
0x180011abf  lea     rcx, [rbp+0CB0h+pstr]; void *
0x180011ac6  call    memset_0
0x180011acb  mov     rax, [rbx]
0x180011ace  lea     r9, [rbp+0CB0h+pstr]
0x180011ad5  mov     r8d, 8000h
0x180011adb  mov     rdx, rsi
0x180011ade  mov     rcx, rbx
0x180011ae1  mov     rax, [rax+58h]
0x180011ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011aea  mov     ebx, eax
0x180011aec  test    eax, eax
0x180011aee  js      short loc_180011B10
0x180011af0  mov     r9d, 104h; cchBuf
0x180011af6  lea     r8, [rbp+0CB0h+pszBuf]; pszBuf
0x180011afa  mov     rdx, rsi; pidl
0x180011afd  lea     rcx, [rbp+0CB0h+pstr]; pstr
0x180011b04  call    cs:__imp_StrRetToBufW
0x180011b0a  mov     ebx, eax
0x180011b0c  test    eax, eax
0x180011b0e  jns     short loc_180011B54
0x180011b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b17  lea     rsi, WPP_GLOBAL_Control
0x180011b1e  cmp     rcx, rsi
0x180011b21  jz      loc_180012380
0x180011b27  test    byte ptr [rcx+1Ch], 2
0x180011b2b  jz      short loc_180011B4C
0x180011b2d  mov     edx, 0Ch
0x180011b32  mov     r9d, ebx
0x180011b35  lea     r8, WPP_d7637b305d8b3afba9326780f352c02a_Traceguids
0x180011b3c  mov     rcx, [rcx+10h]
0x180011b40  call    WPP_SF_d
0x180011b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b4c  test    ebx, ebx
0x180011b4e  js      loc_180012332
0x180011b54  mov     rsi, [rsp+0DB0h+var_D38]
0x180011b59  lea     rax, [rsp+0DB0h+var_D50]
0x180011b5e  mov     [rsp+0DB0h+var_D90], rax; ppv
0x180011b63  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180011b6a  xor     edx, edx; pUnkOuter
0x180011b6c  lea     r8d, [rdx+1]; dwClsContext
0x180011b70  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x180011b77  call    cs:__imp_CoCreateInstance
0x180011b7d  mov     ebx, eax
0x180011b7f  xor     ecx, ecx
0x180011b81  test    eax, eax
0x180011b83  jns     short loc_180011BB0
0x180011b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b8c  lea     rsi, WPP_GLOBAL_Control
0x180011b93  cmp     rcx, rsi
0x180011b96  jz      loc_180012380
0x180011b9c  test    byte ptr [rcx+1Ch], 2
0x180011ba0  jz      loc_18001235C
0x180011ba6  mov     edx, 0A0h
0x180011bab  jmp     loc_180011A6A
0x180011bb0  mov     rax, [rsi+20h]
0x180011bb4  cmp     [rax+18h], ecx
0x180011bb7  jz      loc_180011EA1
0x180011bbd  lea     rdx, [rsp+0DB0h+pidl]
0x180011bc2  mov     rcx, r12
0x180011bc5  call    SHILClone
0x180011bca  mov     ebx, eax
0x180011bcc  xor     r14d, r14d
0x180011bcf  test    eax, eax
0x180011bd1  jns     short loc_180011C18
0x180011bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bda  lea     rax, WPP_GLOBAL_Control
0x180011be1  cmp     rcx, rax
0x180011be4  jz      short loc_180011C0E
0x180011be6  test    byte ptr [rcx+1Ch], 2
0x180011bea  jz      short loc_180011C0E
0x180011bec  mov     edx, 0A1h
0x180011bf1  mov     r9d, ebx
0x180011bf4  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180011bfb  mov     rcx, [rcx+10h]
0x180011bff  call    WPP_SF_d
0x180011c04  mov     rdi, [rsp+0DB0h+pidl]
0x180011c09  jmp     loc_180012309
0x180011c0e  mov     rdi, [rsp+0DB0h+pidl]
0x180011c13  jmp     loc_180012310
0x180011c18  mov     rdi, [rsp+0DB0h+pidl]
0x180011c1d  test    rdi, rdi
0x180011c20  jz      short loc_180011C4F
0x180011c22  cmp     [rdi], r14w
0x180011c26  jz      short loc_180011C4F
0x180011c28  mov     rcx, rdi; pidl
0x180011c2b  call    cs:__imp_ILFindLastID
0x180011c31  mov     rdx, rax; struct _ITEMIDLIST *
0x180011c34  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180011c39  mov     rcx, rdi; pidl
0x180011c3c  test    rax, rax
0x180011c3f  jz      short loc_180011C49
0x180011c41  call    cs:__imp_ILRemoveLastID
0x180011c47  jmp     short loc_180011C1D
0x180011c49  call    cs:__imp_ILRemoveLastID
0x180011c4f  lea     r9, [rbp+0CB0h+var_CE8]; ppidlLast
0x180011c53  lea     r8, [rbp+0CB0h+var_CF0]; ppv
0x180011c57  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1; riid
0x180011c5e  mov     rcx, rdi; pidl
0x180011c61  call    cs:__imp_SHBindToParent
0x180011c67  mov     ebx, eax
0x180011c69  test    eax, eax
0x180011c6b  jns     short loc_180011CAB
0x180011c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c74  lea     rax, WPP_GLOBAL_Control
0x180011c7b  cmp     rcx, rax
0x180011c7e  jz      loc_180012310
0x180011c84  test    byte ptr [rcx+1Ch], 2
0x180011c88  jz      loc_180012310
0x180011c8e  mov     edx, 0A2h
0x180011c93  mov     r9d, ebx
0x180011c96  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180011c9d  mov     rcx, [rcx+10h]
0x180011ca1  call    WPP_SF_d
0x180011ca6  jmp     loc_180012309
0x180011cab  mov     dword ptr [rsp+0DB0h+var_D90], 104h
0x180011cb3  lea     r9, [rbp+0CB0h+var_680]
0x180011cba  lea     r8, PKEY_WPDNSE_PnPDevicePath
0x180011cc1  mov     rdx, [rbp+0CB0h+var_CE8]
0x180011cc5  mov     rcx, [rbp+0CB0h+var_CF0]
0x180011cc9  call    GetStringProperty
0x180011cce  mov     ebx, eax
0x180011cd0  test    eax, eax
0x180011cd2  jns     short loc_180011CFC
0x180011cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cdb  lea     rax, WPP_GLOBAL_Control
0x180011ce2  cmp     rcx, rax
0x180011ce5  jz      loc_180012310
0x180011ceb  test    byte ptr [rcx+1Ch], 2
0x180011cef  jz      loc_180012310
0x180011cf5  mov     edx, 0A3h
0x180011cfa  jmp     short loc_180011C93
0x180011cfc  mov     rcx, [r13+50h]
0x180011d00  mov     rax, [rcx]
0x180011d03  lea     r8, [rsp+0DB0h+var_D48]
0x180011d08  lea     rdx, [rbp+0CB0h+var_680]
0x180011d0f  mov     rax, [rax+80h]
0x180011d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d1b  mov     ebx, eax
0x180011d1d  test    eax, eax
0x180011d1f  jns     short loc_180011D67
0x180011d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d28  lea     rax, WPP_GLOBAL_Control
0x180011d2f  cmp     rcx, rax
0x180011d32  jz      loc_180012310
0x180011d38  test    byte ptr [rcx+1Ch], 2
0x180011d3c  jz      loc_180012310
0x180011d42  mov     edx, 0A4h
0x180011d47  mov     dword ptr [rsp+0DB0h+var_D90], ebx
0x180011d4b  lea     r9, [rbp+0CB0h+var_680]
0x180011d52  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180011d59  mov     rcx, [rcx+10h]
0x180011d5d  call    WPP_SF_Sd
0x180011d62  jmp     loc_180012309
0x180011d67  mov     rcx, r12; pidl
0x180011d6a  call    cs:__imp_ILFindLastID
0x180011d70  mov     rdx, rax; struct _ITEMIDLIST *
0x180011d73  call    ?_IsValid@CContentFolder@@QEAAPEFBUCONTENTITEM@@PEFBU_ITEMIDLIST@@@Z; CContentFolder::_IsValid(_ITEMIDLIST const *)
0x180011d78  mov     rdx, rax
0x180011d7b  test    rax, rax
0x180011d7e  jnz     short loc_180011D8A
0x180011d80  mov     ebx, 8000FFFFh
0x180011d85  jmp     loc_180012309
0x180011d8a  mov     ecx, [rax+42h]
0x180011d8d  mov     eax, [rax+3Eh]
0x180011d90  add     rax, 25h ; '%'
0x180011d94  add     rcx, rax
0x180011d97  lea     r8, [rdx+rcx*2]; unsigned __int16 *
0x180011d9b  mov     edx, 104h; unsigned __int64
0x180011da0  lea     rcx, [rbp+0CB0h+var_470]; unsigned __int16 *
0x180011da7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011dac  test    r15, r15
0x180011daf  jnz     short loc_180011DD1
0x180011db1  mov     r9d, 104h; unsigned int
0x180011db7  lea     r8, [rbp+0CB0h+var_260]; unsigned __int16 *
0x180011dbe  lea     rdx, [rbp+0CB0h+var_470]; unsigned __int16 *
0x180011dc5  mov     rcx, [rsp+0DB0h+var_D48]; struct IPortableDevice *
0x180011dca  call    ?GetObjectID@@YAJPEAUIPortableDevice@@PEAG1I@Z; GetObjectID(IPortableDevice *,ushort *,ushort *,uint)
0x180011dcf  jmp     short loc_180011E3B
0x180011dd1  mov     ebx, r14d
0x180011dd4  mov     esi, r14d
0x180011dd7  cmp     [r15+68h], r14d
0x180011ddb  jnz     short loc_180011E2A
0x180011ddd  mov     r9d, 104h; unsigned int
  ... truncated ...
```
