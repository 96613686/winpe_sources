# CContentDropTarget::_DoInsert(_ITEMIDLIST const *,_ITEMIDLIST const *,IPortableDevice *,IPortableDeviceContent *,int,ushort const *,int,COPY_THREAD_DATA *)

- ea: `0x180017c88`
- end: `0x180019269`
- name: `?_DoInsert@CContentDropTarget@@AEAAJPEFBU_ITEMIDLIST@@0PEAUIPortableDevice@@PEAUIPortableDeviceContent@@HPEBGHPEAVCOPY_THREAD_DATA@@@Z`
- size: `5601`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, struct IPortableDevice *, struct IPortableDeviceContent *, int, const unsigned __int16 *, int, struct COPY_THREAD_DATA *)`
- caller_count: `3`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003a95c`
- `0x18003d4f4`
- `0x18003e96c`

## callees

- `0x180003f20`
- `0x180004110`
- `0x180004190`
- `0x1800050d0`
- `0x1800082e0`
- `0x180014748`
- `0x180016260`
- `0x1800177dc`
- `0x180017c88`
- `0x180019270`
- `0x1800194d8`
- `0x1800196d0`
- `0x180019788`
- `0x180019d90`
- `0x180019e44`
- `0x18001a550`
- `0x1800285c8`
- `0x18002ab58`
- `0x18002c490`
- `0x18002feb4`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18003ee9c`
- `0x180053f34`
- `0x180054524`
- `0x1800545c8`
- `0x18006d5e0`
- `0x180075530`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180017e79`
- `KERNEL32!Sleep` at `0x180017f9c`
- `KERNEL32!Sleep` at `0x18001814f`
- `KERNEL32!Sleep` at `0x1800182b6`
- `KERNEL32!Sleep` at `0x1800183e3`
- `KERNEL32!Sleep` at `0x1800184f3`
- `KERNEL32!Sleep` at `0x180018f6f`
- `KERNEL32!Sleep` at `0x18001904f`
- `KERNEL32!Sleep` at `0x180017e79`
- `KERNEL32!Sleep` at `0x180017f9c`
- `KERNEL32!Sleep` at `0x18001814f`
- `KERNEL32!Sleep` at `0x1800182b6`
- `KERNEL32!Sleep` at `0x1800183e3`
- `KERNEL32!Sleep` at `0x1800184f3`
- `KERNEL32!Sleep` at `0x180018f6f`
- `KERNEL32!Sleep` at `0x18001904f`
- `KERNEL32!CompareStringOrdinal` at `0x1800185f6`
- `KERNEL32!CompareStringOrdinal` at `0x180018615`
- `KERNEL32!CompareStringOrdinal` at `0x180018634`
- `KERNEL32!CompareStringOrdinal` at `0x180018653`
- `KERNEL32!CompareStringOrdinal` at `0x180018672`
- `KERNEL32!CompareStringOrdinal` at `0x1800185f6`
- `KERNEL32!CompareStringOrdinal` at `0x180018615`
- `KERNEL32!CompareStringOrdinal` at `0x180018634`
- `KERNEL32!CompareStringOrdinal` at `0x180018653`
- `KERNEL32!CompareStringOrdinal` at `0x180018672`
- `KERNEL32!SetEvent` at `0x180018a08`
- `KERNEL32!SetEvent` at `0x180018a08`
- `SHLWAPI!StrCmpIW` at `0x180018d58`
- `SHLWAPI!StrCmpIW` at `0x180018dfb`
- `SHLWAPI!StrCmpIW` at `0x180018d58`
- `SHLWAPI!StrCmpIW` at `0x180018dfb`
- `SHLWAPI!StrStrW` at `0x1800188f8`
- `SHLWAPI!StrStrW` at `0x1800188f8`
- `SHLWAPI!StrCSpnW` at `0x1800181b0`
- `SHLWAPI!StrCSpnW` at `0x1800181b0`
- `USER32!LoadStringW` at `0x180018922`
- `USER32!LoadStringW` at `0x180018922`
- `ole32!CoTaskMemFree` at `0x1800181ce`
- `ole32!CoTaskMemFree` at `0x180018215`
- `ole32!CoTaskMemFree` at `0x1800181ce`
- `ole32!CoTaskMemFree` at `0x180018215`
- `ole32!PropVariantClear` at `0x180018343`
- `ole32!PropVariantClear` at `0x180018365`
- `ole32!PropVariantClear` at `0x18001845d`
- `ole32!PropVariantClear` at `0x180018471`
- `ole32!PropVariantClear` at `0x180018343`
- `ole32!PropVariantClear` at `0x180018365`
- `ole32!PropVariantClear` at `0x18001845d`
- `ole32!PropVariantClear` at `0x180018471`
- `ole32!CoCreateInstance` at `0x180018000`
- `ole32!CoCreateInstance` at `0x180018000`
- `SHELL32!SHBindToParent` at `0x180018701`
- `SHELL32!SHBindToParent` at `0x180018701`
- `SHELL32!__imp_ILFindLastID` at `0x180018cd4`
- `SHELL32!__imp_ILFindLastID` at `0x180018ee3`
- `SHELL32!__imp_ILFindLastID` at `0x180018cd4`
- `SHELL32!__imp_ILFindLastID` at `0x180018ee3`
- `SHELL32!__imp_ILRemoveLastID` at `0x180018e09`
- `SHELL32!__imp_ILRemoveLastID` at `0x180018e09`
- `SHELL32!__imp_ILFree` at `0x1800191f9`
- `SHELL32!__imp_ILFree` at `0x1800191f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CContentDropTarget::_DoInsert(
        CContentDropTarget *this,
        const struct _ITEMIDLIST *a2,
        struct _ITEMIDLIST *a3,
        struct IPortableDevice *a4,
        struct IPortableDeviceContent *a5,
        int a6,
        const unsigned __int16 *a7,
        int a8,
        struct COPY_THREAD_DATA *a9)
{
  struct IPortableDevice *v9; // rbx
  struct _ITEMIDLIST *v10; // r12
  const ITEMIDLIST *v11; // r13
  CContentDropTarget *v12; // rdi
  __int64 v13; // rsi
  unsigned int v14; // r15d
  int v15; // r13d
  _DWORD *v16; // r12
  int PortableDeviceProperties; // edi
  int v18; // ebx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // ebx
  HRESULT v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  struct IPortableDeviceProperties *v26; // rbx
  int v27; // ebx
  unsigned int i; // r15d
  unsigned __int64 v29; // rax
  unsigned int j; // ebx
  unsigned __int64 v31; // rax
  int v32; // ebx
  int v33; // edi
  CContentDropTarget *v34; // r15
  __int64 v35; // rcx
  __int64 v36; // rcx
  HRESULT v37; // eax
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r9
  CContentFolder *v41; // rcx
  const struct CONTENTITEM *v42; // rax
  CContentFolder *v43; // rcx
  unsigned int v44; // r9d
  const struct CONTENTITEM *v45; // rbx
  __int64 v46; // rax
  unsigned __int16 *v47; // rcx
  __int64 v48; // rdx
  unsigned __int16 *v49; // r8
  unsigned __int16 v50; // r9
  unsigned __int16 *v51; // rcx
  int v52; // eax
  PVOID *v53; // rcx
  __int64 v54; // rdx
  __int64 v55; // r9
  PWSTR v56; // rax
  WCHAR *p_pszFirst; // rbx
  int v58; // ebx
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // r9
  __int64 v62; // rdx
  WCHAR *v63; // rax
  HRESULT ObjectID; // edi
  size_t *v65; // r8
  _QWORD *v66; // rcx
  __int64 v67; // rdx
  int v68; // eax
  __int64 v69; // r9
  int v70; // r13d
  int v71; // eax
  const ITEMIDLIST *v72; // rbx
  CContentDropTarget *v73; // rdi
  PCWSTR v74; // rbx
  int v75; // r13d
  int v76; // r12d
  const struct _ITEMIDLIST *v77; // rax
  CContentFolder *v78; // rcx
  const struct CONTENTITEM *v79; // rax
  __int64 v80; // r10
  int v81; // eax
  _QWORD *v82; // rcx
  __int64 v83; // rdx
  ATL::CStringData *v84; // rcx
  int v85; // eax
  int v86; // eax
  const struct _ITEMIDLIST *ID; // rax
  CContentFolder *v88; // rcx
  const struct CONTENTITEM *v89; // rax
  int v90; // r12d
  int v91; // r12d
  int inserted; // eax
  PVOID *v93; // rcx
  __int64 v94; // rdx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v97[2]; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR v98; // [rsp+78h] [rbp-88h] BYREF
  int v99; // [rsp+80h] [rbp-80h]
  CContentDropTarget *v100; // [rsp+88h] [rbp-78h]
  __int64 v101; // [rsp+90h] [rbp-70h] BYREF
  struct IUnknown *v102; // [rsp+98h] [rbp-68h] BYREF
  struct IPortableDeviceProperties *v103; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v104; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v105; // [rsp+B0h] [rbp-50h] BYREF
  LPCITEMIDLIST v106; // [rsp+B8h] [rbp-48h]
  struct IPortableDevice *v107; // [rsp+C0h] [rbp-40h]
  struct _ITEMIDLIST *v108; // [rsp+C8h] [rbp-38h]
  LPCITEMIDLIST pidl; // [rsp+D0h] [rbp-30h] BYREF
  PROPVARIANT pvar; // [rsp+D8h] [rbp-28h] BYREF
  PCWSTR pszStr[2]; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID pv[2]; // [rsp+100h] [rbp+0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v114; // [rsp+118h] [rbp+18h] BYREF
  void *v115; // [rsp+120h] [rbp+20h] BYREF
  struct IPortableDeviceContent *v116; // [rsp+128h] [rbp+28h]
  unsigned __int16 v117; // [rsp+130h] [rbp+30h] BYREF
  char v118[526]; // [rsp+132h] [rbp+32h] BYREF
  WCHAR pszFirst; // [rsp+340h] [rbp+240h] BYREF
  char v120[526]; // [rsp+342h] [rbp+242h] BYREF
  unsigned __int16 v121; // [rsp+550h] [rbp+450h] BYREF
  char v122[526]; // [rsp+552h] [rbp+452h] BYREF
  WCHAR psz1; // [rsp+760h] [rbp+660h] BYREF
  char v124[526]; // [rsp+762h] [rbp+662h] BYREF
  unsigned __int16 v125; // [rsp+970h] [rbp+870h] BYREF
  char v126[526]; // [rsp+972h] [rbp+872h] BYREF
  WCHAR Buffer; // [rsp+B80h] [rbp+A80h] BYREF
  char v128[526]; // [rsp+B82h] [rbp+A82h] BYREF
  WCHAR psz2; // [rsp+D90h] [rbp+C90h] BYREF
  char v130[526]; // [rsp+D92h] [rbp+C92h] BYREF
  WCHAR v131; // [rsp+FA0h] [rbp+EA0h] BYREF
  char v132[526]; // [rsp+FA2h] [rbp+EA2h] BYREF
  unsigned __int16 v133; // [rsp+11B0h] [rbp+10B0h] BYREF
  char v134[526]; // [rsp+11B2h] [rbp+10B2h] BYREF
  unsigned __int16 v135; // [rsp+13C0h] [rbp+12C0h] BYREF
  char v136[1038]; // [rsp+13C2h] [rbp+12C2h] BYREF

  v9 = a4;
  v107 = a4;
  v10 = a3;
  v108 = a3;
  v11 = a2;
  v106 = a2;
  v12 = this;
  v100 = this;
  v116 = a5;
  v13 = *((_QWORD *)a9 + 557);
  v14 = 541589504;
  v97[0] = 541589504;
  ppidlLast = 0;
  pidl = 0;
  v114 = 0;
  v125 = 0;
  memset_0(v126, 0, 0x206u);
  psz2 = 0;
  memset_0(v130, 0, 0x206u);
  v133 = 0;
  memset_0(v134, 0, 0x206u);
  v117 = 0;
  memset_0(v118, 0, 0x206u);
  v121 = 0;
  memset_0(v122, 0, 0x206u);
  pszFirst = 0;
  memset_0(v120, 0, 0x206u);
  Buffer = 0;
  memset_0(v128, 0, 0x206u);
  v135 = 0;
  memset_0(v136, 0, sizeof(v136));
  v115 = 0;
  if ( !*((_DWORD *)a9 + 15) )
  {
    memset(&pvar, 0, sizeof(pvar));
    v15 = 0;
    v103 = 0;
    v101 = 0;
    v98 = 0;
    v105 = 0;
    *((_DWORD *)a9 + 15) = 1;
    v16 = (_DWORD *)(v13 + 104);
    if ( v13 )
    {
      v18 = 0;
      while ( !*v16 )
      {
        PortableDeviceProperties = GetPortableDeviceProperties(v107, &v103);
        if ( PortableDeviceProperties != -2147024726 )
          goto LABEL_12;
        if ( !v15 )
        {
          v18 = 1;
          v15 = 1;
          CProgressUI::_StartMarquee((CProgressUI *)v13);
        }
        if ( *v16 )
          break;
        Sleep(0x5DCu);
      }
      PortableDeviceProperties = -2147023673;
LABEL_12:
      v15 = 0;
      if ( v18 )
        CProgressUI::_StopMarquee((CProgressUI *)v13);
      if ( *v16 )
      {
        PortableDeviceProperties = -2147023673;
        goto LABEL_18;
      }
      v9 = v107;
    }
    else
    {
      PortableDeviceProperties = GetPortableDeviceProperties(v9, &v103);
    }
    if ( PortableDeviceProperties < 0 )
    {
LABEL_18:
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_22;
      v20 = 100;
      goto LABEL_21;
    }
    if ( v13 )
    {
      v21 = 0;
      while ( !*v16 )
      {
        PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v107->lpVtbl->Capabilities)(
                                     v107,
                                     &v101);
        if ( PortableDeviceProperties != -2147024726 )
          goto LABEL_37;
        if ( !v15 )
        {
          v21 = 1;
          v15 = 1;
          CProgressUI::_StartMarquee((CProgressUI *)v13);
        }
        if ( *v16 )
          break;
        Sleep(0x5DCu);
      }
      PortableDeviceProperties = -2147023673;
LABEL_37:
      v15 = 0;
      if ( v21 )
        CProgressUI::_StopMarquee((CProgressUI *)v13);
      if ( *v16 )
      {
        PortableDeviceProperties = -2147023673;
LABEL_26:
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_22;
        v20 = 101;
LABEL_21:
        WPP_SF_d(v19[2], v20, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)PortableDeviceProperties);
LABEL_22:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v105);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v98);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v101);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v103);
LABEL_208:
        CContentDropTarget::_DisplayErrorMessage(
          v100,
          PortableDeviceProperties,
          (const unsigned __int16 *)((unsigned __int64)&v117 & -(__int64)(v117 != 0)),
          a9,
          (v14 >> 29) & 1);
LABEL_209:
        v72 = v106;
LABEL_286:
        if ( PortableDeviceProperties == 1 )
        {
          *(_DWORD *)a9 = 1;
          if ( (int)GetFileSize(v72, &v114) >= 0
            && (int)CProgressUI::_IncrementCatchUp((CProgressUI *)v13, v114) >= 0
            && *(_DWORD *)(*((_QWORD *)a9 + 4) + 12LL) )
          {
            CProgressUI::_IncrementCatchUp((CProgressUI *)v13, v114);
          }
        }
        goto LABEL_291;
      }
    }
    else
    {
      PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v9->lpVtbl->Capabilities)(
                                   v9,
                                   &v101);
    }
    if ( PortableDeviceProperties < 0 )
      goto LABEL_26;
    pszStr[0] = 0;
    pv[0] = 0;
    v104 = 0;
    v102 = 0;
    v22 = CoCreateInstance(&CLSID_PortableDeviceKeyCollection, 0, 1u, &GUID_dada2357_e0ad_492e_98db_dd61c53ba353, &v104);
    PortableDeviceProperties = v22;
    if ( v22 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_46;
      v24 = 102;
      v25 = (unsigned int)v22;
LABEL_45:
      WPP_SF_d(v23[2], v24, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v25);
LABEL_46:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v102);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v104);
      goto LABEL_22;
    }
    (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)v104 + 40LL))(v104, &WPD_DEVICE_PROTOCOL);
    (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *))(*(_QWORD *)v104 + 40LL))(v104, &WPD_DEVICE_MODEL);
    if ( v13 )
    {
      v99 = 0;
      v26 = v103;
      while ( !*v16 )
      {
        PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const WCHAR *, LPVOID, struct IUnknown **))v26->lpVtbl->GetValues)(
                                     v26,
                                     L"DEVICE",
                                     v104,
                                     &v102);
        if ( PortableDeviceProperties != -2147024726 )
          goto LABEL_63;
        if ( v102 )
          ATL::AtlComPtrAssign(&v102, 0);
        if ( !v99 )
        {
          v99 = 1;
          v15 = 1;
          CProgressUI::_StartMarquee((CProgressUI *)v13);
        }
        if ( *v16 )
          break;
        Sleep(0x5DCu);
      }
      PortableDeviceProperties = -2147023673;
LABEL_63:
      if ( v15 )
        CProgressUI::_StopMarquee((CProgressUI *)v13);
      if ( *v16 )
      {
        PortableDeviceProperties = -2147023673;
LABEL_50:
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_46;
        v24 = 103;
        v25 = (unsigned int)PortableDeviceProperties;
        goto LABEL_45;
      }
    }
    else
    {
      PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const WCHAR *, LPVOID, struct IUnknown **))v103->lpVtbl->GetValues)(
                                   v103,
                                   L"DEVICE",
                                   v104,
                                   &v102);
    }
    if ( PortableDeviceProperties < 0 )
      goto LABEL_50;
    if ( ((int (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, PCWSTR *))v102->lpVtbl[2].Release)(
           v102,
           &WPD_DEVICE_PROTOCOL,
           pszStr) >= 0 )
    {
      if ( !StrCSpnW(pszStr[0], L"MTP:") )
        *(_DWORD *)(*((_QWORD *)a9 + 4) + 32LL) = 1;
      if ( pszStr[0] )
      {
        CoTaskMemFree((LPVOID)pszStr[0]);
        pszStr[0] = 0;
      }
    }
    if ( ((int (__fastcall *)(struct IUnknown *, const PROPERTYKEY *, LPVOID *))v102->lpVtbl[2].Release)(
           v102,
           &WPD_DEVICE_MODEL,
           pv) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)a9 + 1964, 0x104u, (const unsigned __int16 *)pv[0]);
      if ( pv[0] )
      {
        CoTaskMemFree(pv[0]);
        pv[0] = 0;
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v102);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v104);
    if ( !v13 || (v27 = 0, !*(_DWORD *)(v13 + 104)) )
      v27 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64 *))(*(_QWORD *)v101 + 64LL))(
              v101,
              &WPD_CONTENT_TYPE_UNSPECIFIED,
              &v105);
    if ( v27 >= 0 )
    {
      memset(&pvar, 0, sizeof(pvar));
      for ( i = 0;
            !(*(unsigned int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v105 + 32LL))(v105, i, &pvar);
            ++i )
      {
        if ( pvar.vt == 72 )
        {
          v29 = *(_QWORD *)&WPD_OBJECT_FORMAT_UNSPECIFIED.Data1 - (unsigned __int64)*pvar.pbstrVal;
          if ( *(BSTR *)&WPD_OBJECT_FORMAT_UNSPECIFIED.Data1 == *pvar.pbstrVal )
            v29 = *(_QWORD *)WPD_OBJECT_FORMAT_UNSPECIFIED.Data4 - *(_QWORD *)(pvar.hVal.QuadPart + 8);
          if ( !v29 )
          {
            *((_DWORD *)a9 + 10) = 1;
            PropVariantClear(&pvar);
            break;
          }
        }
        PropVariantClear(&pvar);
      }
    }
    if ( !v13 || !*(_DWORD *)(v13 + 104) )
      v27 = (*(__int64 (__fastcall **)(__int64, const GUID *, PCWSTR *))(*(_QWORD *)v101 + 64LL))(
              v101,
              &WPD_CONTENT_TYPE_GENERIC_FILE,
              &v98);
    if ( v27 >= 0 )
    {
      memset(&pvar, 0, sizeof(pvar));
      for ( j = 0;
            !(*(unsigned int (__fastcall **)(PCWSTR, _QWORD, PROPVARIANT *))(*(_QWORD *)v98 + 32LL))(v98, j, &pvar);
            ++j )
      {
        if ( pvar.vt == 72 )
        {
          v31 = *(_QWORD *)&WPD_OBJECT_FORMAT_UNSPECIFIED.Data1 - (unsigned __int64)*pvar.pbstrVal;
          if ( *(BSTR *)&WPD_OBJECT_FORMAT_UNSPECIFIED.Data1 == *pvar.pbstrVal )
            v31 = *(_QWORD *)WPD_OBJECT_FORMAT_UNSPECIFIED.Data4 - *(_QWORD *)(pvar.hVal.QuadPart + 8);
          if ( !v31 )
          {
            *((_DWORD *)a9 + 12) = 1;
            PropVariantClear(&pvar);
            break;
          }
        }
        PropVariantClear(&pvar);
      }
    }
    if ( v13 )
    {
      v32 = 0;
      v33 = 0;
      v34 = v100;
      while ( !*(_DWORD *)(v13 + 104)
           && (*(unsigned int (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)v34 + 10) + 176LL))(
                *((_QWORD *)v34 + 10),
                *(_QWORD *)(*((_QWORD *)v34 + 10) + 64LL),
                (char *)a9 + 4448) == -2147024726 )
      {
        if ( !v32 )
        {
          v32 = 1;
          v33 = 1;
          CProgressUI::_StartMarquee((CProgressUI *)v13);
        }
        if ( *(_DWORD *)(v13 + 104) )
          break;
        Sleep(0x5DCu);
      }
      if ( v33 )
        CProgressUI::_StopMarquee((CProgressUI *)v13);
      v12 = v34;
    }
    else
    {
      v12 = v100;
      (*(void (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)v100 + 10) + 176LL))(
        *((_QWORD *)v100 + 10),
        *(_QWORD *)(*((_QWORD *)v100 + 10) + 64LL),
        (char *)a9 + 4448);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v105);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v98);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v101);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v103);
    v10 = v108;
    v11 = v106;
  }
  memset_0((char *)a9 + 840, 0, 0x800u);
  memset_0((char *)a9 + 2888, 0, 0x208u);
  *((_DWORD *)a9 + 14) = 0;
  *((_DWORD *)a9 + 11) = 0;
  if ( *((_DWORD *)a9 + 10) )
  {
    v35 = *((_QWORD *)v12 + 10);
    *(GUID *)pv = WPD_CONTENT_TYPE_UNSPECIFIED;
    *((_DWORD *)a9 + 11) = (*(__int64 (__fastcall **)(__int64, struct _ITEMIDLIST *, LPVOID *, _QWORD))(*(_QWORD *)v35 + 64LL))(
                             v35,
                             v10,
                             pv,
                             0);
  }
  *((_DWORD *)a9 + 13) = 0;
  if ( *((_DWORD *)a9 + 12) )
  {
    v36 = *((_QWORD *)v12 + 10);
    *(GUID *)pv = WPD_CONTENT_TYPE_GENERIC_FILE;
    *((_DWORD *)a9 + 13) = (*(__int64 (__fastcall **)(__int64, struct _ITEMIDLIST *, LPVOID *, _QWORD))(*(_QWORD *)v36 + 64LL))(
                             v36,
                             v10,
                             pv,
                             0);
  }
  if ( CompareStringOrdinal(L"IRIVER Device", -1, (LPCWCH)a9 + 1964, -1, 1) == 2
    || CompareStringOrdinal(L"iriver T10", -1, (LPCWCH)a9 + 1964, -1, 1) == 2
    || CompareStringOrdinal(L"iriver T30", -1, (LPCWCH)a9 + 1964, -1, 1) == 2
    || CompareStringOrdinal(L"iriver U10", -1, (LPCWCH)a9 + 1964, -1, 1) == 2
    || CompareStringOrdinal(L"Gateway MP3 Photo Jukebox", -1, (LPCWCH)a9 + 1964, -1, 1) == 2 )
  {
    *((_DWORD *)a9 + 10) = 1;
    *(_QWORD *)((char *)a9 + 44) = 1;
    *((_DWORD *)a9 + 13) = 0;
  }
  v37 = SHGetNameAndFlagsW(v11, (__int64)v97);
  PortableDeviceProperties = v37;
  if ( v37 < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_129;
    v39 = 104;
    goto LABEL_127;
  }
  v37 = SHBindToParent(v11, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &v115, &ppidlLast);
  PortableDeviceProperties = v37;
  if ( v37 < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_129;
    v39 = 105;
    goto LABEL_127;
  }
  if ( *(_DWORD *)(*((_QWORD *)a9 + 4) + 24LL) )
  {
    v42 = CContentFolder::_IsValid(v41, ppidlLast);
    v45 = v42;
    if ( !v42 )
    {
      PortableDeviceProperties = -2147418113;
      v14 = v97[0];
      goto LABEL_208;
    }
    CContentFolder::_Name(v43, v42, &v121, v44);
    StringCchCopyW(
      &psz2,
      0x104u,
      (const unsigned __int16 *)v45 + *(unsigned int *)((char *)v45 + 62) + *(unsigned int *)((char *)v45 + 66) + 37);
  }
  else
  {
    v37 = DisplayNameOfW(v115, ppidlLast, 32769, &v121, 260);
    PortableDeviceProperties = v37;
    if ( v37 < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_129;
      v39 = 106;
LABEL_127:
      v40 = (unsigned int)v37;
LABEL_128:
      WPP_SF_d(v38[2], v39, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v40);
LABEL_129:
      v14 = v97[0];
      goto LABEL_208;
    }
  }
  v46 = 2147483646;
  v47 = &v121;
  v48 = 260;
  v49 = (unsigned __int16 *)((char *)a9 + 2888);
  do
  {
    if ( !v46 )
      break;
    v50 = *v47;
    if ( !*v47 )
      break;
    ++v47;
    *v49++ = v50;
    --v46;
    --v48;
  }
  while ( v48 );
  PortableDeviceProperties = v48 == 0 ? 0x8007007A : 0;
  v51 = v49 - 1;
  if ( v48 )
    v51 = v49;
  *v51 = 0;
  if ( !v48 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_129;
    v39 = 107;
    v40 = (unsigned int)PortableDeviceProperties;
    goto LABEL_128;
  }
  v14 = v97[0];
  if ( (v97[0] & 0x400000) != 0 )
    v14 = v97[0] & 0xDFFFFFFF;
  v52 = SHGetNameAndFlagsW(v10, 0);
  PortableDeviceProperties = v52;
  if ( v52 < 0 )
  {
    v53 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_208;
    v54 = 108;
    goto LABEL_158;
  }
  v56 = StrStrW(&pszFirst, (PCWSTR)a9 + 1704);
  p_pszFirst = &pszFirst;
  if ( v56 )
    p_pszFirst = v56;
  LoadStringW(g_hInst, 0xE4u, &Buffer, 260);
  v52 = StringCchPrintfW(&v135, 0x208u, &Buffer, p_pszFirst);
  PortableDeviceProperties = v52;
  v58 = 0;
  if ( v52 < 0 )
  {
    v53 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_208;
    v54 = 109;
LABEL_158:
    v55 = (unsigned int)v52;
LABEL_159:
    WPP_SF_d(v53[2], v54, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v55);
    goto LABEL_208;
  }
  v59 = StringCchCopyW((unsigned __int16 *)(v13 + 172), 0x104u, &v117);
  PortableDeviceProperties = v59;
  if ( v59 < 0 )
  {
    v53 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_208;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_180;
    v60 = 146;
LABEL_170:
    v61 = (unsigned int)v59;
    goto LABEL_179;
  }
  v59 = StringCchCopyW((unsigned __int16 *)(v13 + 692), 0x208u, &v135);
  PortableDeviceProperties = v59;
  if ( v59 < 0 )
  {
    v53 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_208;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_180;
    v60 = 147;
    goto LABEL_170;
  }
  if ( !SetEvent(*(HANDLE *)(v13 + 80)) )
  {
    PortableDeviceProperties = -2147467259;
    v53 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_208;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_180;
    v60 = 148;
    v61 = 2147500037LL;
LABEL_179:
    WPP_SF_d(v53[2], v60, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, v61);
    v53 = (PVOID *)WPP_GLOBAL_Control;
LABEL_180:
    if ( v53 == &WPP_GLOBAL_Control )
      goto LABEL_208;
    if ( (*((_BYTE *)v53 + 28) & 2) != 0 )
    {
      WPP_SF_d(v53[2], 149, &WPP_97501a7b54843d9fecff243f22a7f928_Traceguids, (unsigned int)PortableDeviceProperties);
      v53 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v53 == &WPP_GLOBAL_Control || (*((_BYTE *)v53 + 28) & 2) == 0 )
      goto LABEL_208;
    v54 = 110;
    v55 = (unsigned int)PortableDeviceProperties;
    goto LABEL_159;
  }
  v62 = 260;
  v63 = &pszFirst;
  do
  {
    if ( !*v63 )
      break;
    ++v63;
    --v62;
  }
  while ( v62 );
  ObjectID = v62 == 0 ? 0x80070057 : 0;
  if ( v62 )
  {
    v65 = (size_t *)((260 - v62) & -(__int64)(v62 != 0));
    ObjectID = StringCopyWorkerW(
                 (STRSAFE_LPWSTR)&v120[2 * (_QWORD)v65 - 2],
                 260LL - (_QWORD)v65,
                 v65,
                 L"\\",
                 (size_t)ppv);
  }
  if ( ObjectID == -2147024774 )
    goto LABEL_192;
  if ( ObjectID < 0 )
  {
    v66 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_263;
    v67 = 111;
    goto LABEL_261;
  }
  v68 = StringCchCatW(&pszFirst, 0x104u, &v121);
  ObjectID = v68;
  if ( v68 == -2147024774 )
  {
LABEL_192:
    ObjectID = -2147483400;
LABEL_263:
    PortableDeviceProperties = CContentDropTarget::_DisplayErrorMessageWithSkip(
                                 v100,
                                 ObjectID,
                                 &v117,
                                 a9,
                                 (v14 >> 29) & 1);
    goto LABEL_209;
  }
  if ( v68 < 0 )
  {
    v66 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_263;
    v67 = 112;
    v69 = (unsigned int)v68;
    goto LABEL_262;
  }
  v70 = v14 & 0x20000000;
  v99 = v14 & 0x20000000;
  if ( (v14 & 0x20000000) == 0 )
  {
LABEL_244:
    ID = ILFindLastID(v10);
    v89 = CContentFolder::_IsValid(v88, ID);
    if ( v89 )
    {
      StringCchCopyW(
        &v133,
        0x104u,
        (const unsigned __int16 *)v89 + *(unsigned int *)((char *)v89 + 62) + *(unsigned int *)((char *)v89 + 66) + 37);
      v90 = 0;
      while ( !*(_DWORD *)(v13 + 104) )
      {
        ObjectID = CBaseFolder::_GetObjectID(*((CBaseFolder **)v100 + 10), &v133, &v125, 0x104u);
        if ( ObjectID != -2147024726 )
          goto LABEL_253;
        if ( !v90 )
        {
          v58 = 1;
          v90 = 1;
          CProgressUI::_StartMarquee((CProgressUI *)v13);
        }
        if ( *(_DWORD *)(v13 + 104) )
          break;
        Sleep(0x5DCu);
      }
      ObjectID = -2147023673;
LABEL_253:
      if ( v58 )
        CProgressUI::_StopMarquee((CProgressUI *)v13);
      if ( *(_DWORD *)(v13 + 104) )
        ObjectID = -2147023673;
    }
    else
    {
      v91 = 0;
      while ( !*(_DWORD *)(v13 + 104) )
      {
        ObjectID = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**((_QWORD **)v100 + 10)
                                                                                          + 88LL))(
                     *((_QWORD *)v100 + 10),
                     *(_QWORD *)(*((_QWORD *)v100 + 10) + 64LL),
                     &v125,
                     260);
        if ( ObjectID != -2147024726 )
          goto LABEL_272;
        if ( !v91 )
        {
          v58 = 1;
          v91 = 1;
          CProgressUI::_StartMarquee((CProgressUI *)v13);
        }
        if ( *(_DWORD *)(v13 + 104) )
          break;
        Sleep(0x5DCu);
      }
      ObjectID = -2147023673;
LABEL_272:
      if ( v58 )
        CProgressUI::_StopMarquee((CProgressUI *)v13);
      if ( *(_DWORD *)(v13 + 104) )
      {
        ObjectID = -2147023673;
LABEL_258:
        v66 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_263;
        v67 = 118;
LABEL_261:
        v69 = (unsigned int)ObjectID;
LABEL_262:
        WPP_SF_d(v66[2], v67, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v69);
        goto LABEL_263;
      }
    }
    if ( ObjectID >= 0 )
    {
      if ( v70 )
      {
        v72 = v106;
        inserted = CContentDropTarget::_DoInsertFolder(
                     v100,
                     v106,
                     v108,
                     v107,
                     v116,
                     a6,
                     0,
                     0,
                     v14,
                     &v121,
                     &v117,
                     &v125,
                     a9);
        PortableDeviceProperties = inserted;
        if ( inserted >= 0 )
          goto LABEL_286;
        v93 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_292;
        v94 = 119;
      }
      else
      {
        v72 = v106;
        inserted = CContentDropTarget::_DoInsertFile(v100, v106, v108, v107, v116, 0, 0, v14, &v121, &v117, &v125, a9);
        PortableDeviceProperties = inserted;
        if ( inserted >= 0 )
          goto LABEL_286;
        v93 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_292;
        v94 = 120;
      }
      WPP_SF_d(v93[2], v94, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)inserted);
      goto LABEL_291;
    }
    goto LABEL_258;
  }
  psz1 = 0;
  memset_0(v124, 0, 0x206u);
  v131 = 0;
  memset_0(v132, 0, 0x206u);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v98);
  v71 = SHILClone(v10, &pidl);
  PortableDeviceProperties = v71;
  if ( v71 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
        (unsigned int)v71);
    ATL::CStringData::Release((ATL::CStringData *)(v98 - 12));
    goto LABEL_208;
  }
  v73 = v100;
  if ( !*(_DWORD *)(*((_QWORD *)a9 + 4) + 16LL)
    && (!(*(unsigned int (__fastcall **)(_QWORD, struct _ITEMIDLIST *))(**((_QWORD **)v100 + 10) + 80LL))(
           *((_QWORD *)v100 + 10),
           v10)
     || !*(_DWORD *)(*((_QWORD *)a9 + 4) + 28LL)) )
  {
    v74 = v98;
LABEL_243:
    ATL::CStringData::Release((ATL::CStringData *)(v74 - 12));
    v58 = 0;
    goto LABEL_244;
  }
  v75 = 1;
  v76 = 1;
  v74 = v98;
  while ( 1 )
  {
    if ( !v76 )
    {
LABEL_242:
      v10 = v108;
      v70 = v99;
      goto LABEL_243;
    }
    v77 = ILFindLastID(pidl);
    v79 = CContentFolder::_IsValid(v78, v77);
    if ( v79 )
    {
      StringCchCopyW(
        &psz1,
        0x104u,
        (const unsigned __int16 *)v79 + *(unsigned int *)((char *)v79 + 62) + *(unsigned int *)((char *)v79 + 66) + 37);
    }
    else
    {
      v76 = 0;
      v81 = (*(__int64 (__fastcall **)(_QWORD, LPCITEMIDLIST, WCHAR *, __int64))(**((_QWORD **)v73 + 10) + 184LL))(
              *((_QWORD *)v73 + 10),
              pidl,
              &psz1,
              260);
      v80 = 0;
      if ( v81 < 0 )
        goto LABEL_242;
    }
    if ( *(_DWORD *)(*((_QWORD *)a9 + 4) + 16LL) != (_DWORD)v80 )
    {
      if ( !StrCmpIW(&psz1, &psz2) )
      {
        ObjectID = v75 - 2147483297;
        v82 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v83 = 114;
          goto LABEL_224;
        }
        goto LABEL_225;
      }
      goto LABEL_230;
    }
    v85 = SHGetNameAndFlagsW(v106, v80);
    PortableDeviceProperties = v85;
    if ( v85 < 0 )
      break;
    v86 = UnescapeMassStoragePUID(&psz1, &v98);
    ObjectID = v86;
    if ( v86 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          116,
          WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
          (unsigned int)v86);
      v84 = (ATL::CStringData *)(v98 - 12);
      goto LABEL_226;
    }
    v74 = v98;
    if ( !StrCmpIW(v98, &v131) )
    {
      ObjectID = v75 - 2147483297;
      v82 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v83 = 117;
LABEL_224:
        WPP_SF_d(v82[2], v83, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)ObjectID);
      }
LABEL_225:
      v84 = (ATL::CStringData *)(v74 - 12);
LABEL_226:
      ATL::CStringData::Release(v84);
      goto LABEL_263;
    }
LABEL_230:
    ILRemoveLastID((LPITEMIDLIST)pidl);
    v75 = 0;
    v73 = v100;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      115,
      WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids,
      (unsigned int)v85);
  ATL::CStringData::Release((ATL::CStringData *)(v74 - 12));
LABEL_291:
  v93 = (PVOID *)WPP_GLOBAL_Control;
LABEL_292:
  if ( pidl )
  {
    ILFree((LPITEMIDLIST)pidl);
    v93 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( PortableDeviceProperties < 0 && v93 != &WPP_GLOBAL_Control && (*((_BYTE *)v93 + 28) & 2) != 0 )
    WPP_SF_d(v93[2], 121, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, (unsigned int)PortableDeviceProperties);
  if ( v115 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v115 + 16LL))(v115);
  return (unsigned int)PortableDeviceProperties;
}

```

## disassembly

```asm
0x180017c88  push    rbp
0x180017c8a  push    rbx
0x180017c8b  push    rsi
0x180017c8c  push    rdi
0x180017c8d  push    r12
0x180017c8f  push    r13
0x180017c91  push    r14
0x180017c93  push    r15
0x180017c95  lea     rbp, [rsp-16E8h]
0x180017c9d  mov     eax, 17E8h
0x180017ca2  call    _alloca_probe
0x180017ca7  sub     rsp, rax
0x180017caa  mov     rax, cs:__security_cookie
0x180017cb1  xor     rax, rsp
0x180017cb4  mov     [rbp+1720h+var_50], rax
0x180017cbb  mov     rbx, r9
0x180017cbe  mov     [rbp+1720h+var_1760], rbx
0x180017cc2  mov     r12, r8
0x180017cc5  mov     [rbp+1720h+var_1758], r8
0x180017cc9  mov     r13, rdx
0x180017ccc  mov     [rbp+1720h+var_1768], rdx
0x180017cd0  mov     rdi, rcx
0x180017cd3  mov     [rbp+1720h+var_1798], rcx
0x180017cd7  mov     r14, [rbp+1720h+arg_40]
0x180017cde  mov     rax, [rbp+1720h+arg_20]
0x180017ce5  mov     [rbp+1720h+var_16F8], rax
0x180017ce9  mov     rsi, [r14+1168h]
0x180017cf0  mov     r15d, 20480000h
0x180017cf6  mov     [rsp+1820h+var_17B0], r15d
0x180017cfb  xor     eax, eax
0x180017cfd  mov     [rbp+1720h+ppidlLast], rax
0x180017d01  mov     [rbp+1720h+pidl], rax
0x180017d05  mov     [rbp+1720h+var_1708], rax
0x180017d09  mov     [rbp+1720h+var_EB0], ax
0x180017d10  xor     edx, edx; Val
0x180017d12  mov     r8d, 206h; Size
0x180017d18  lea     rcx, [rbp+1720h+var_EAE]; void *
0x180017d1f  call    memset_0
0x180017d24  xor     eax, eax
0x180017d26  mov     [rbp+1720h+psz2], ax
0x180017d2d  xor     edx, edx; Val
0x180017d2f  mov     r8d, 206h; Size
0x180017d35  lea     rcx, [rbp+1720h+var_A8E]; void *
0x180017d3c  call    memset_0
0x180017d41  xor     eax, eax
0x180017d43  mov     [rbp+1720h+var_670], ax
0x180017d4a  xor     edx, edx; Val
0x180017d4c  mov     r8d, 206h; Size
0x180017d52  lea     rcx, [rbp+1720h+var_66E]; void *
0x180017d59  call    memset_0
0x180017d5e  xor     eax, eax
0x180017d60  mov     [rbp+1720h+var_16F0], ax
0x180017d64  xor     edx, edx; Val
0x180017d66  mov     r8d, 206h; Size
0x180017d6c  lea     rcx, [rbp+1720h+var_16EE]; void *
0x180017d70  call    memset_0
0x180017d75  xor     eax, eax
0x180017d77  mov     [rbp+1720h+var_12D0], ax
0x180017d7e  xor     edx, edx; Val
0x180017d80  mov     r8d, 206h; Size
0x180017d86  lea     rcx, [rbp+1720h+var_12CE]; void *
0x180017d8d  call    memset_0
0x180017d92  xor     eax, eax
0x180017d94  mov     [rbp+1720h+pszFirst], ax
0x180017d9b  xor     edx, edx; Val
0x180017d9d  mov     r8d, 206h; Size
0x180017da3  lea     rcx, [rbp+1720h+var_14DE]; void *
0x180017daa  call    memset_0
0x180017daf  xor     eax, eax
0x180017db1  mov     [rbp+1720h+Buffer], ax
0x180017db8  xor     edx, edx; Val
0x180017dba  mov     r8d, 206h; Size
0x180017dc0  lea     rcx, [rbp+1720h+var_C9E]; void *
0x180017dc7  call    memset_0
0x180017dcc  xor     eax, eax
0x180017dce  mov     [rbp+1720h+var_460], ax
0x180017dd5  xor     edx, edx; Val
0x180017dd7  mov     r8d, 40Eh; Size
0x180017ddd  lea     rcx, [rbp+1720h+var_45E]; void *
0x180017de4  call    memset_0
0x180017de9  xor     eax, eax
0x180017deb  mov     [rbp+1720h+var_1700], rax
0x180017def  cmp     [r14+3Ch], eax
0x180017df3  jnz     loc_18001853C
0x180017df9  xorps   xmm0, xmm0
0x180017dfc  movups  xmmword ptr [rbp+1720h+pvar], xmm0
0x180017e00  mov     qword ptr [rbp+1720h+pvar+10h], rax
0x180017e04  xor     r13d, r13d
0x180017e07  mov     [rbp+1720h+var_1780], r13
0x180017e0b  mov     [rbp+1720h+var_1790], r13
0x180017e0f  mov     [rsp+1820h+var_17A8], r13
0x180017e14  mov     [rbp+1720h+var_1770], r13
0x180017e18  mov     dword ptr [r14+3Ch], 1
0x180017e20  lea     r12, [rsi+68h]
0x180017e24  test    rsi, rsi
0x180017e27  jnz     short loc_180017E39
0x180017e29  lea     rdx, [rbp+1720h+var_1780]; struct IPortableDeviceProperties **
0x180017e2d  mov     rcx, rbx; struct IPortableDevice *
0x180017e30  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180017e35  mov     edi, eax
0x180017e37  jmp     short loc_180017EAD
0x180017e39  xor     eax, eax
0x180017e3b  mov     ebx, eax
0x180017e3d  cmp     [r12], eax
0x180017e41  jnz     short loc_180017E88
0x180017e43  lea     rdx, [rbp+1720h+var_1780]; struct IPortableDeviceProperties **
0x180017e47  mov     rcx, [rbp+1720h+var_1760]; struct IPortableDevice *
0x180017e4b  call    ?GetPortableDeviceProperties@@YAJPEAUIPortableDevice@@PEAPEAUIPortableDeviceProperties@@@Z; GetPortableDeviceProperties(IPortableDevice *,IPortableDeviceProperties * *)
0x180017e50  mov     edi, eax
0x180017e52  cmp     eax, 800700AAh
0x180017e57  jnz     short loc_180017E8D
0x180017e59  test    r13d, r13d
0x180017e5c  jnz     short loc_180017E6D
0x180017e5e  lea     ebx, [r13+1]
0x180017e62  mov     r13d, ebx
0x180017e65  mov     rcx, rsi; this
0x180017e68  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180017e6d  cmp     dword ptr [r12], 0
0x180017e72  jnz     short loc_180017E88
0x180017e74  mov     ecx, 5DCh; dwMilliseconds
0x180017e79  call    cs:__imp_Sleep
0x180017e7f  xor     eax, eax
0x180017e81  test    r13d, r13d
0x180017e84  jz      short loc_180017E8D
0x180017e86  jmp     short loc_180017E3D
0x180017e88  mov     edi, 800704C7h
0x180017e8d  xor     r13d, r13d
0x180017e90  test    ebx, ebx
0x180017e92  jz      short loc_180017E9C
0x180017e94  mov     rcx, rsi; this
0x180017e97  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180017e9c  cmp     [r12], r13d
0x180017ea0  jz      short loc_180017EA9
0x180017ea2  mov     edi, 800704C7h
0x180017ea7  jmp     short loc_180017EB1
0x180017ea9  mov     rbx, [rbp+1720h+var_1760]
0x180017ead  test    edi, edi
0x180017eaf  jns     short loc_180017F10
0x180017eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180017eb8  lea     r12, WPP_GLOBAL_Control
0x180017ebf  cmp     rcx, r12
0x180017ec2  jz      short loc_180017EE3
0x180017ec4  test    byte ptr [rcx+1Ch], 2
0x180017ec8  jz      short loc_180017EE3
0x180017eca  mov     edx, 64h ; 'd'
0x180017ecf  mov     r9d, edi
0x180017ed2  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180017ed9  mov     rcx, [rcx+10h]
0x180017edd  call    WPP_SF_d
0x180017ee2  nop
0x180017ee3  lea     rcx, [rbp+1720h+var_1770]
0x180017ee7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017eec  nop
0x180017eed  lea     rcx, [rsp+1820h+var_17A8]
0x180017ef2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017ef7  nop
0x180017ef8  lea     rcx, [rbp+1720h+var_1790]
0x180017efc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017f01  nop
0x180017f02  lea     rcx, [rbp+1720h+var_1780]
0x180017f06  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017f0b  jmp     loc_180018C4A
0x180017f10  test    rsi, rsi
0x180017f13  jnz     short loc_180017F55
0x180017f15  mov     rax, [rbx]
0x180017f18  lea     rdx, [rbp+1720h+var_1790]
0x180017f1c  mov     rcx, rbx
0x180017f1f  mov     rax, [rax+30h]
0x180017f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f28  mov     edi, eax
0x180017f2a  test    edi, edi
0x180017f2c  jns     loc_180017FD3
0x180017f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f39  lea     r12, WPP_GLOBAL_Control
0x180017f40  cmp     rcx, r12
0x180017f43  jz      short loc_180017EE3
0x180017f45  test    byte ptr [rcx+1Ch], 2
0x180017f49  jz      short loc_180017EE3
0x180017f4b  mov     edx, 65h ; 'e'
0x180017f50  jmp     loc_180017ECF
0x180017f55  xor     eax, eax
0x180017f57  mov     ebx, eax
0x180017f59  cmp     [r12], eax
0x180017f5d  jnz     short loc_180017FAB
0x180017f5f  mov     rcx, [rbp+1720h+var_1760]
0x180017f63  mov     rax, [rcx]
0x180017f66  lea     rdx, [rbp+1720h+var_1790]
0x180017f6a  mov     rax, [rax+30h]
0x180017f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f73  mov     edi, eax
0x180017f75  cmp     eax, 800700AAh
0x180017f7a  jnz     short loc_180017FB0
0x180017f7c  test    r13d, r13d
0x180017f7f  jnz     short loc_180017F90
0x180017f81  lea     ebx, [r13+1]
0x180017f85  mov     r13d, ebx
0x180017f88  mov     rcx, rsi; this
0x180017f8b  call    ?_StartMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StartMarquee(void)
0x180017f90  cmp     dword ptr [r12], 0
0x180017f95  jnz     short loc_180017FAB
0x180017f97  mov     ecx, 5DCh; dwMilliseconds
0x180017f9c  call    cs:__imp_Sleep
0x180017fa2  xor     eax, eax
0x180017fa4  test    r13d, r13d
0x180017fa7  jz      short loc_180017FB0
0x180017fa9  jmp     short loc_180017F59
0x180017fab  mov     edi, 800704C7h
0x180017fb0  xor     r13d, r13d
0x180017fb3  test    ebx, ebx
0x180017fb5  jz      short loc_180017FBF
0x180017fb7  mov     rcx, rsi; this
0x180017fba  call    ?_StopMarquee@CProgressUI@@QEAAJXZ; CProgressUI::_StopMarquee(void)
0x180017fbf  cmp     [r12], r13d
0x180017fc3  jz      loc_180017F2A
0x180017fc9  mov     edi, 800704C7h
0x180017fce  jmp     loc_180017F32
0x180017fd3  mov     [rbp+1720h+pszStr], r13
0x180017fd7  mov     [rbp+1720h+pv], r13
0x180017fdb  mov     [rbp+1720h+var_1778], r13
0x180017fdf  mov     [rbp+1720h+var_1788], r13
0x180017fe3  lea     rax, [rbp+1720h+var_1778]
0x180017fe7  mov     [rsp+1820h+ppv], rax; ppv
0x180017fec  lea     r9, _GUID_dada2357_e0ad_492e_98db_dd61c53ba353; riid
0x180017ff3  xor     edx, edx; pUnkOuter
0x180017ff5  lea     r8d, [rdx+1]; dwClsContext
0x180017ff9  lea     rcx, CLSID_PortableDeviceKeyCollection; rclsid
0x180018000  call    cs:__imp_CoCreateInstance
0x180018006  mov     edi, eax
0x180018008  test    eax, eax
0x18001800a  jns     short loc_180018056
0x18001800c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018013  lea     r12, WPP_GLOBAL_Control
0x18001801a  cmp     rcx, r12
0x18001801d  jz      short loc_18001803E
0x18001801f  test    byte ptr [rcx+1Ch], 2
0x180018023  jz      short loc_18001803E
0x180018025  mov     edx, 66h ; 'f'
0x18001802a  mov     r9d, eax
0x18001802d  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180018034  mov     rcx, [rcx+10h]
0x180018038  call    WPP_SF_d
0x18001803d  nop
0x18001803e  lea     rcx, [rbp+1720h+var_1788]
0x180018042  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018047  nop
0x180018048  lea     rcx, [rbp+1720h+var_1778]
0x18001804c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180018051  jmp     loc_180017EE3
0x180018056  mov     rcx, [rbp+1720h+var_1778]
0x18001805a  mov     rax, [rcx]
0x18001805d  lea     rdx, WPD_DEVICE_PROTOCOL
0x180018064  mov     rax, [rax+28h]
0x180018068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001806d  mov     rcx, [rbp+1720h+var_1778]
0x180018071  mov     rax, [rcx]
0x180018074  lea     rdx, WPD_DEVICE_MODEL
0x18001807b  mov     rax, [rax+28h]
0x18001807f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018084  test    rsi, rsi
0x180018087  jnz     short loc_1800180E0
0x180018089  mov     rcx, [rbp+1720h+var_1780]
0x18001808d  mov     rax, [rcx]
0x180018090  lea     r9, [rbp+1720h+var_1788]
0x180018094  mov     r8, [rbp+1720h+var_1778]
0x180018098  lea     rdx, aDevice_0; "DEVICE"
0x18001809f  mov     rax, [rax+28h]
0x1800180a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180a8  mov     edi, eax
0x1800180aa  test    edi, edi
0x1800180ac  jns     loc_180018186
0x1800180b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180b9  lea     r12, WPP_GLOBAL_Control
0x1800180c0  cmp     rcx, r12
0x1800180c3  jz      loc_18001803E
0x1800180c9  test    byte ptr [rcx+1Ch], 2
0x1800180cd  jz      loc_18001803E
0x1800180d3  mov     edx, 67h ; 'g'
0x1800180d8  mov     r9d, edi
0x1800180db  jmp     loc_18001802D
0x1800180e0  mov     [rbp+1720h+var_17A0], r13d
0x1800180e4  mov     rbx, [rbp+1720h+var_1780]
0x1800180e8  cmp     dword ptr [r12], 0
0x1800180ed  jnz     short loc_18001815D
0x1800180ef  mov     rax, [rbx]
0x1800180f2  lea     r9, [rbp+1720h+var_1788]
0x1800180f6  mov     r8, [rbp+1720h+var_1778]
0x1800180fa  lea     rdx, aDevice_0; "DEVICE"
0x180018101  mov     rcx, rbx
0x180018104  mov     rax, [rax+28h]
0x180018108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001810d  mov     edi, eax
0x18001810f  cmp     eax, 800700AAh
0x180018114  jnz     short loc_180018162
0x180018116  cmp     [rbp+1720h+var_1788], 0
0x18001811b  jz      short loc_180018128
0x18001811d  xor     edx, edx; struct IUnknown *
0x18001811f  lea     rcx, [rbp+1720h+var_1788]; struct IUnknown **
0x180018123  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180018128  cmp     [rbp+1720h+var_17A0], 0
0x18001812c  jnz     short loc_180018143
  ... truncated ...
```
