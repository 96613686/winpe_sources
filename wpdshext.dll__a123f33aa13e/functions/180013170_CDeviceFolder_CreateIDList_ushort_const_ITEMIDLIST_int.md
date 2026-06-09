# CDeviceFolder::_CreateIDList(ushort const *,_ITEMIDLIST * *,int *)

- ea: `0x180013170`
- end: `0x18001412e`
- name: `?_CreateIDList@CDeviceFolder@@AEAAJPEBGPEAPEFAU_ITEMIDLIST@@PEAH@Z`
- size: `4030`
- prototype: `int(CDeviceFolder *__hidden this, const unsigned __int16 *, struct _ITEMIDLIST **, int *)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000ba84`
- `0x180057c90`

## callees

- `0x180004110`
- `0x18000c180`
- `0x180012b90`
- `0x180013170`
- `0x180014748`
- `0x180014778`
- `0x180016260`
- `0x18001a5b0`
- `0x18001f600`
- `0x1800285c8`
- `0x180028978`
- `0x180028ea8`
- `0x18002c270`
- `0x18002e738`
- `0x18002e9f0`
- `0x18002ff5c`
- `0x180035590`
- `0x180036166`
- `0x1800361ba`
- `0x180039d74`
- `0x18003a2b0`
- `0x18003a530`
- `0x1800755a8`
- `0x1800755b4`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013414`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013414`
- `KERNEL32!GetCurrentThreadId` at `0x18001363e`
- `KERNEL32!GetCurrentThreadId` at `0x18001363e`
- `ole32!CoTaskMemFree` at `0x180013918`
- `ole32!CoTaskMemFree` at `0x180014085`
- `ole32!CoTaskMemFree` at `0x180013918`
- `ole32!CoTaskMemFree` at `0x180014085`
- `ole32!CoCreateInstance` at `0x180013254`
- `ole32!CoCreateInstance` at `0x1800132c6`
- `ole32!CoCreateInstance` at `0x18001357b`
- `ole32!CoCreateInstance` at `0x1800137cf`
- `ole32!CoCreateInstance` at `0x180013254`
- `ole32!CoCreateInstance` at `0x1800132c6`
- `ole32!CoCreateInstance` at `0x18001357b`
- `ole32!CoCreateInstance` at `0x1800137cf`
- `SHELL32!__imp_ILFree` at `0x180013e19`
- `SHELL32!__imp_ILFree` at `0x180013e19`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CDeviceFolder::_CreateIDList(
        struct IPortableDeviceProperties *this,
        unsigned __int16 *a2,
        struct _ITEMIDLIST **a3,
        int *a4)
{
  const unsigned __int16 *v6; // r12
  __int16 v7; // r15
  HRESULT v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // r10
  __int64 v11; // rdx
  unsigned __int16 *v12; // r14
  int v13; // edi
  __int64 v14; // rbx
  unsigned __int64 v15; // r12
  signed __int64 v16; // r14
  int v17; // ecx
  char *v18; // rdx
  __int64 v19; // r15
  unsigned __int64 v20; // r14
  char *v21; // rcx
  CBaseFolder *v22; // rbx
  int IsDelegateFolder; // ebx
  DWORD CurrentThreadId; // eax
  int v25; // eax
  HRESULT PortableDeviceProperties; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  int v29; // eax
  unsigned __int16 *v30; // rdi
  int v31; // r13d
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r9
  struct IPortableDeviceProperties *v35; // rax
  __int16 v36; // cx
  bool v37; // sf
  __int64 v38; // rcx
  unsigned __int16 *v39; // rax
  unsigned __int16 v40; // r14
  unsigned __int16 v41; // dx
  unsigned __int16 v42; // r12
  char *v43; // rax
  char *v44; // r15
  unsigned __int16 v45; // cx
  unsigned __int16 v46; // dx
  unsigned __int16 v47; // r9
  unsigned __int16 *v48; // rdi
  unsigned __int16 *v49; // r8
  wchar_t *v50; // rdi
  STRSAFE_PCNZWCH v51; // rcx
  wchar_t *v52; // rax
  HRESULT v53; // r8d
  bool v54; // zf
  unsigned __int16 *v55; // rdi
  unsigned __int16 *v56; // r11
  int v57; // eax
  const WCHAR *v58; // rsi
  const WCHAR *v59; // r9
  unsigned __int64 *ppv; // [rsp+20h] [rbp-528h]
  unsigned int *v62; // [rsp+28h] [rbp-520h]
  int v63; // [rsp+40h] [rbp-508h]
  unsigned __int16 v64; // [rsp+40h] [rbp-508h]
  void *v65; // [rsp+48h] [rbp-500h] BYREF
  struct IPortableDeviceProperties *v66; // [rsp+50h] [rbp-4F8h] BYREF
  size_t cchToCopy; // [rsp+58h] [rbp-4F0h] BYREF
  unsigned __int16 *v68; // [rsp+60h] [rbp-4E8h] BYREF
  STRSAFE_PCNZWCH pszSrc; // [rsp+68h] [rbp-4E0h]
  unsigned int v70; // [rsp+70h] [rbp-4D8h] BYREF
  unsigned __int16 *v71; // [rsp+78h] [rbp-4D0h]
  struct IPortableDevice *v72; // [rsp+80h] [rbp-4C8h] BYREF
  unsigned __int16 *v73; // [rsp+88h] [rbp-4C0h]
  int v74; // [rsp+90h] [rbp-4B8h] BYREF
  unsigned int v75; // [rsp+94h] [rbp-4B4h] BYREF
  LPVOID v76; // [rsp+98h] [rbp-4B0h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-4A8h] BYREF
  int v78; // [rsp+A8h] [rbp-4A0h]
  size_t pcchNewDestLength; // [rsp+B0h] [rbp-498h] BYREF
  LPVOID v80; // [rsp+B8h] [rbp-490h] BYREF
  struct _ITEMIDLIST **v81; // [rsp+C0h] [rbp-488h]
  LPVOID v82; // [rsp+C8h] [rbp-480h] BYREF
  int *v83; // [rsp+D0h] [rbp-478h]
  struct _ITEMIDLIST **v84; // [rsp+D8h] [rbp-470h]
  int *v85; // [rsp+E0h] [rbp-468h]
  unsigned __int16 Src[520]; // [rsp+F0h] [rbp-458h] BYREF
  __int64 v87; // [rsp+500h] [rbp-48h] BYREF

  v83 = a4;
  v84 = a3;
  v6 = a2;
  v73 = a2;
  pcchNewDestLength = (size_t)this;
  v66 = this;
  v72 = (struct IPortableDevice *)a2;
  v81 = a3;
  v85 = a4;
  LODWORD(cchToCopy) = 0;
  v70 = 0;
  v74 = 0;
  v75 = 0;
  memset_0(Src, 0, sizeof(Src));
  v82 = 0;
  v80 = 0;
  v76 = 0;
  *a3 = 0;
  *a4 = 0;
  v7 = 1;
  v78 = 1;
  v8 = CoCreateInstance(&CLSID_WpdSerializer, 0, 1u, &GUID_b32f4002_bb27_45ff_af4f_06631c1e8dad, &v82);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_185;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_182;
    v11 = 91;
    goto LABEL_5;
  }
  v8 = CoCreateInstance(&CLSID_PortableDeviceManager, 0, 1u, &GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40, &v80);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_185;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_182;
    v11 = 92;
    goto LABEL_5;
  }
  v71 = 0;
  v12 = 0;
  pszSrc = 0;
  pv = 0;
  v13 = 1;
  v63 = 1;
  LODWORD(cchToCopy) = 520;
  if ( (*(int (__fastcall **)(LPVOID, const unsigned __int16 *, unsigned __int16 *, size_t *))(*(_QWORD *)v80 + 40LL))(
         v80,
         v6,
         Src,
         &cchToCopy) >= 0 )
  {
    v65 = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v14 = -1;
    do
      ++v14;
    while ( Src[v14] );
    try
    {
      if ( !(_DWORD)v14 )
      {
        ATL::CSimpleStringT<unsigned short,0>::Empty(&v65);
LABEL_30:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(&v65);
        v21 = (char *)v65;
        if ( *((int *)v65 - 4) > 0 )
        {
          v12 = Src;
          pszSrc = Src;
          pv = Src;
          v13 = 0;
          v63 = 0;
        }
        goto LABEL_194;
      }
      v15 = *((unsigned int *)v65 - 4);
      v16 = (char *)Src - (_BYTE *)v65;
      v17 = *((_DWORD *)v65 - 3) - v14;
      v18 = (char *)(v17 | (unsigned int)(1 - *((_DWORD *)v65 - 2)));
      if ( (v17 | (1 - *((_DWORD *)v65 - 2))) < 0 )
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v65, (unsigned int)v14);
      v19 = 2LL * (int)v14;
      if ( v19 )
      {
        v20 = v16 >> 1;
        if ( v20 > v15 )
        {
          if ( v65 )
          {
            memcpy_0(v65, Src, 2LL * (int)v14);
            goto LABEL_27;
          }
        }
        else if ( v65 )
        {
          v18 = (char *)v65 + 2 * v20;
          if ( v18 )
          {
            memmove_0(v65, v18, 2LL * (int)v14);
            goto LABEL_27;
          }
        }
        *(_DWORD *)_o__errno(v65, v18) = 22;
        invalid_parameter_noinfo();
      }
LABEL_27:
      if ( (int)v14 < 0 || (int)v14 > *((_DWORD *)v65 - 3) )
        ATL::AtlThrowImpl(-2147024809);
      *((_DWORD *)v65 - 4) = v14;
      *(_WORD *)((char *)v65 + v19) = 0;
      v12 = 0;
      v7 = 1;
      v6 = v73;
      goto LABEL_30;
    }
    catch ( ATL::CAtlException v87 )
    {
      v7 = 1;
      v78 = 1;
      v71 = 0;
      v12 = (unsigned __int16 *)pv;
      pszSrc = (STRSAFE_PCNZWCH)pv;
      v13 = v63;
      v21 = (char *)v65;
      v22 = (CBaseFolder *)v66;
      pcchNewDestLength = (size_t)v66;
      v6 = (const unsigned __int16 *)v72;
      v73 = (unsigned __int16 *)v72;
      v84 = v81;
      v83 = v85;
      goto LABEL_34;
    }
LABEL_194:
    v22 = (CBaseFolder *)pcchNewDestLength;
LABEL_34:
    ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
    if ( !v13 )
      goto LABEL_38;
  }
  LODWORD(cchToCopy) = 520;
  if ( (*(int (__fastcall **)(LPVOID, const unsigned __int16 *, unsigned __int16 *, size_t *))(*(_QWORD *)v80 + 48LL))(
         v80,
         v6,
         Src,
         &cchToCopy) >= 0 )
  {
    v12 = Src;
    pszSrc = Src;
    goto LABEL_39;
  }
  v22 = (CBaseFolder *)pcchNewDestLength;
LABEL_38:
  if ( !v12 )
  {
    v72 = 0;
    v66 = 0;
    v65 = 0;
    if ( !v6 )
    {
      v9 = -2147024809;
      goto LABEL_53;
    }
    v72 = 0;
    IsDelegateFolder = CBaseFolder::_IsDelegateFolder(v22);
    CurrentThreadId = GetCurrentThreadId();
    v25 = CDeviceCache::s_BindToPortableDevice(v6, CurrentThreadId, 0, 0, IsDelegateFolder, &v72);
    v9 = v25;
    if ( v25 < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_60:
        if ( v65 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v65 + 16LL))(v65);
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v72 )
        {
          ((void (__fastcall *)(struct IPortableDevice *))v72->lpVtbl->Release)(v72);
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
LABEL_181:
        if ( (v9 & 0x80000000) == 0 )
          goto LABEL_185;
        goto LABEL_182;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_54:
        if ( v10 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v10 + 28) & 2) != 0 )
          {
            WPP_SF_d(v10[2], 30, WPP_f4dfe53786183352449e3e96734e584d_Traceguids, v9);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
          {
            WPP_SF_d(v10[2], 95, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v9);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        goto LABEL_60;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_f4dfe53786183352449e3e96734e584d_Traceguids,
        (unsigned int)v25);
LABEL_53:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_54;
    }
    PortableDeviceProperties = GetPortableDeviceProperties(v72, &v66);
    v9 = PortableDeviceProperties;
    if ( PortableDeviceProperties >= 0 )
    {
      PortableDeviceProperties = CoCreateInstance(
                                   &CLSID_PortableDeviceKeyCollection,
                                   0,
                                   1u,
                                   &GUID_dada2357_e0ad_492e_98db_dd61c53ba353,
                                   &v65);
      v9 = PortableDeviceProperties;
      if ( PortableDeviceProperties >= 0 )
      {
        (*(void (__fastcall **)(void *, const PROPERTYKEY *))(*(_QWORD *)v65 + 40LL))(v65, &WPD_OBJECT_NAME);
        (*(void (__fastcall **)(void *, const PROPERTYKEY *))(*(_QWORD *)v65 + 40LL))(v65, &WPD_DEVICE_FRIENDLY_NAME);
        PortableDeviceProperties = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const WCHAR *, void *, LPVOID *))v66->lpVtbl->GetValues)(
                                     v66,
                                     L"DEVICE",
                                     v65,
                                     &v76);
        v9 = PortableDeviceProperties;
        if ( PortableDeviceProperties >= 0 )
        {
          pv = 0;
          v29 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)v76 + 64LL))(
                  v76,
                  &WPD_OBJECT_NAME,
                  &pv);
          v30 = v71;
          if ( v29 >= 0 )
            v30 = (unsigned __int16 *)pv;
          v71 = v30;
          if ( (*(int (__fastcall **)(LPVOID, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)v76 + 64LL))(
                 v76,
                 &WPD_DEVICE_FRIENDLY_NAME,
                 &pv) >= 0 )
          {
            v9 = StringCchCopyW(Src, 0x208u, (const unsigned __int16 *)pv);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( (v9 & 0x80000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v9);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
              goto LABEL_178;
            }
            v12 = Src;
            pszSrc = Src;
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
LABEL_91:
          LODWORD(v81) = 0;
          LODWORD(cchToCopy) = 4;
          v70 = 0;
          if ( (*(int (__fastcall **)(LPVOID, const unsigned __int16 *, const wchar_t *, int *, size_t *, unsigned int *))(*(_QWORD *)v80 + 64LL))(
                 v80,
                 v6,
                 L"PortableDeviceIsMassStorage",
                 &v74,
                 &cchToCopy,
                 &v70) >= 0
            && v70 == 4 )
          {
            LODWORD(v81) = v74 != 0;
          }
          v31 = 0;
          LODWORD(cchToCopy) = 4;
          v70 = 0;
          v62 = &v70;
          ppv = &cchToCopy;
          if ( (*(int (__fastcall **)(LPVOID, const unsigned __int16 *, const wchar_t *, int *))(*(_QWORD *)v80 + 64LL))(
                 v80,
                 v6,
                 L"PortableDeviceType",
                 &v74) >= 0
            && v70 == 4 )
          {
            v31 = v74;
          }
          (*(void (__fastcall **)(LPVOID, const PROPERTYKEY *, const GUID *))(*(_QWORD *)v76 + 216LL))(
            v76,
            &WPD_FUNCTIONAL_OBJECT_CATEGORY,
            &WPD_FUNCTIONAL_CATEGORY_DEVICE);
          v32 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, unsigned int *))(*(_QWORD *)v82 + 48LL))(v82, v76, &v75);
          v9 = v32;
          if ( v32 < 0 )
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v33 = 100;
              v34 = (unsigned int)v32;
LABEL_101:
              WPP_SF_d(v10[2], v33, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v34);
LABEL_178:
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
LABEL_179:
            if ( v71 )
            {
              CoTaskMemFree(v71);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            goto LABEL_181;
          }
          LOWORD(v35) = 1;
          v66 = (struct IPortableDeviceProperties *)1;
          v36 = 1;
          v64 = 1;
          v68 = 0;
          if ( v30 )
          {
            v37 = (int)StringCchLengthW(v30, 0x104u, (unsigned __int64 *)&v68) < 0;
            LOWORD(v35) = (_WORD)v66;
            if ( !v37 )
            {
              v7 = (_WORD)v68 + 1;
              v78 = (unsigned __int16)((_WORD)v68 + 1);
            }
            v36 = 1;
          }
          if ( v12 )
          {
            v38 = 260;
            v39 = v12;
            while ( *v39 )
            {
              ++v39;
              if ( !--v38 )
              {
                v68 = 0;
                LOWORD(v35) = (_WORD)v66;
                goto LABEL_112;
              }
            }
            v35 = (struct IPortableDeviceProperties *)(260 - v38);
            v68 = (unsigned __int16 *)(260 - v38);
            LOWORD(v35) = 260 - v38 + 1;
            v66 = v35;
LABEL_112:
            v36 = 1;
          }
          if ( v6 )
          {
            v37 = (int)StringCchLengthW(v6, 0x104u, (unsigned __int64 *)&v68) < 0;
            LOWORD(v35) = (_WORD)v66;
            if ( v37 )
            {
              v36 = 1;
            }
            else
            {
              v36 = (_WORD)v68 + 1;
              v64 = (_WORD)v68 + 1;
            }
          }
          v40 = v75;
          if ( v75 > 0xFFFF )
          {
            v9 = -2147024362;
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v75);
              goto LABEL_178;
            }
            goto LABEL_179;
          }
          v41 = 2 * (v7 + (_WORD)v35 + v36 + 17);
          v42 = v41 + v75;
          if ( (unsigned __int16)(v41 + v75) < v41 )
          {
            v9 = -2147024362;
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              LODWORD(v62) = -2147024362;
              LODWORD(ppv) = (unsigned __int16)v75;
              WPP_SF_ddd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                102,
                WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
                v41,
                ppv,
                v62);
              goto LABEL_178;
            }
            goto LABEL_179;
          }
          v43 = (char *)CBaseFolder::_Alloc((CBaseFolder *)pcchNewDestLength, v41 + (unsigned __int16)v75);
          v44 = v43;
          if ( !v43 )
          {
            v9 = -2147024882;
            goto LABEL_178;
          }
          v9 = 0;
          *(_DWORD *)(v43 + 6) = 137437190;
          *(_DWORD *)(v43 + 10) = 3;
          *(_DWORD *)(v43 + 14) = (_DWORD)v81;
          *(_DWORD *)(v43 + 18) = v31;
          *(_DWORD *)(v43 + 22) = v40;
          v45 = v78;
          *(_DWORD *)(v43 + 26) = (unsigned __int16)v78;
          v46 = (unsigned __int16)v66;
          *(_DWORD *)(v43 + 30) = (unsigned __int16)v66;
          v47 = v64;
          *(_DWORD *)(v43 + 34) = v64;
          v48 = (unsigned __int16 *)(v43 + 38);
          v68 = (unsigned __int16 *)(v43 + 38);
          v49 = v71;
          if ( v71 )
          {
            StringCchCopyExW((unsigned __int16 *)v43 + 19, v45, v71, &v68, &cchToCopy, (unsigned int)&v70);
            v48 = v68;
            v49 = v71;
            v46 = (unsigned __int16)v66;
            v47 = v64;
          }
          v50 = v48 + 1;
          v51 = pszSrc;
          if ( pszSrc )
          {
            if ( v50 )
            {
              if ( v46 )
              {
                pcchNewDestLength = 0;
                v53 = StringCopyWorkerW_0(v50, v46, &pcchNewDestLength, pszSrc, (size_t)ppv);
                v52 = &v50[pcchNewDestLength];
                v47 = v64;
                v51 = pszSrc;
                if ( (int)(v53 + 0x80000000) < 0 )
                {
                  v49 = v71;
                }
                else
                {
                  v54 = v53 == -2147024774;
                  v49 = v71;
                  if ( !v54 )
                    goto LABEL_136;
                }
LABEL_135:
                v50 = v52;
                goto LABEL_136;
              }
            }
            else if ( v46 )
            {
              MEMORY[0] = 0;
              goto LABEL_136;
            }
            v52 = v50;
            if ( !*pszSrc || v50 )
              goto LABEL_135;
          }
LABEL_136:
          v55 = v50 + 1;
          v68 = v55;
          v56 = v73;
          if ( v73 )
          {
            StringCchCopyExW(v55, v47, v73, &v68, ppv, (unsigned int)v62);
            v55 = v68;
            v51 = pszSrc;
            v49 = v71;
            v56 = v73;
          }
          if ( v40 )
          {
            v57 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID, unsigned __int16 *, unsigned int *))(*(_QWORD *)v82 + 32LL))(
                    v82,
                    v40,
                    v76,
                    v55 + 1,
                    &v75);
            v9 = v57;
            if ( v57 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  103,
                  WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids,
                  (unsigned int)v57);
              goto LABEL_145;
            }
            if ( v40 != v75 )
            {
              v9 = -2147418113;
LABEL_145:
              ILFree((LPITEMIDLIST)v44);
              goto LABEL_178;
            }
            v51 = pszSrc;
            v49 = v71;
            v56 = v73;
          }
          *v83 = 8 * (*(_DWORD *)(v44 + 10) & 2);
          *v84 = (struct _ITEMIDLIST *)v44;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_179;
          v58 = &String;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            v59 = &String;
            if ( v49 )
              v59 = v49;
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v59);
            v10 = (PVOID *)WPP_GLOBAL_Control;
            v51 = pszSrc;
            v56 = v73;
          }
          if ( v10 == &WPP_GLOBAL_Control )
            goto LABEL_179;
          if ( (*((_BYTE *)v10 + 28) & 0x40) != 0 )
          {
            WPP_SF_d(v10[2], 105, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, *(unsigned int *)(v44 + 10));
            v10 = (PVOID *)WPP_GLOBAL_Control;
            v51 = pszSrc;
            v56 = v73;
          }
          if ( v10 == &WPP_GLOBAL_Control )
            goto LABEL_179;
          if ( (*((_BYTE *)v10 + 28) & 0x40) != 0 )
          {
            WPP_SF_d(v10[2], 106, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, *(unsigned int *)(v44 + 14));
            v10 = (PVOID *)WPP_GLOBAL_Control;
            v51 = pszSrc;
            v56 = v73;
          }
          if ( v10 == &WPP_GLOBAL_Control )
            goto LABEL_179;
          if ( (*((_BYTE *)v10 + 28) & 0x40) != 0 )
          {
            WPP_SF_d(v10[2], 107, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, *(unsigned int *)(v44 + 18));
            v10 = (PVOID *)WPP_GLOBAL_Control;
            v51 = pszSrc;
            v56 = v73;
          }
          if ( v10 == &WPP_GLOBAL_Control )
            goto LABEL_179;
          if ( (*((_BYTE *)v10 + 28) & 0x40) != 0 )
          {
            if ( v51 )
              v58 = v51;
            WPP_SF_S(v10[2], 108, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v58);
            v10 = (PVOID *)WPP_GLOBAL_Control;
            v56 = v73;
          }
          if ( v10 == &WPP_GLOBAL_Control )
            goto LABEL_179;
          if ( (*((_BYTE *)v10 + 28) & 0x40) != 0 )
          {
            WPP_SF_S(v10[2], 109, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v56);
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 0x40) == 0 )
            goto LABEL_179;
          v34 = v42;
          v33 = 110;
          goto LABEL_101;
        }
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_69:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v66);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v72);
          goto LABEL_6;
        }
        v28 = 98;
      }
      else
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_69;
        v28 = 97;
      }
    }
    else
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_69;
      v28 = 96;
    }
    WPP_SF_d(v27[2], v28, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)PortableDeviceProperties);
    goto LABEL_69;
  }
LABEL_39:
  v8 = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143, &v76);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_185;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_182;
    v11 = 93;
    goto LABEL_5;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, unsigned __int16 *))(*(_QWORD *)v76 + 56LL))(
         v76,
         &WPD_DEVICE_FRIENDLY_NAME,
         v12);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v30 = v71;
    goto LABEL_91;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_185;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_182;
  v11 = 94;
LABEL_5:
  WPP_SF_d(v10[2], v11, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, (unsigned int)v8);
LABEL_6:
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_182:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
    WPP_SF_d(v10[2], 111, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids, v9);
LABEL_185:
  if ( v76 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v76 + 16LL))(v76);
  if ( v80 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v80 + 16LL))(v80);
  if ( v82 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v82 + 16LL))(v82);
  return v9;
}

```

## disassembly

```asm
0x180013170  push    rbx
0x180013172  push    rsi
0x180013173  push    rdi
0x180013174  push    r12
0x180013176  push    r13
0x180013178  push    r14
0x18001317a  push    r15
0x18001317c  sub     rsp, 510h
0x180013183  mov     rax, cs:__security_cookie
0x18001318a  xor     rax, rsp
0x18001318d  mov     [rsp+548h+var_40], rax
0x180013195  mov     rbx, r9
0x180013198  mov     [rsp+548h+var_478], rbx
0x1800131a0  mov     r13, r8
0x1800131a3  mov     [rsp+548h+var_470], r8
0x1800131ab  mov     r12, rdx
0x1800131ae  mov     [rsp+548h+var_4C0], rdx
0x1800131b6  mov     [rsp+548h+pcchNewDestLength], rcx
0x1800131be  mov     [rsp+548h+var_4F8], rcx
0x1800131c3  mov     [rsp+548h+var_4C8], rdx
0x1800131cb  mov     [rsp+548h+var_488], r8
0x1800131d3  mov     [rsp+548h+var_468], rbx
0x1800131db  xor     esi, esi
0x1800131dd  mov     dword ptr [rsp+548h+cchToCopy], esi
0x1800131e1  mov     [rsp+548h+var_4D8], esi
0x1800131e5  mov     [rsp+548h+var_4B8], esi
0x1800131ec  mov     [rsp+548h+var_4B4], esi
0x1800131f3  xor     edx, edx; Val
0x1800131f5  mov     r8d, 410h; Size
0x1800131fb  lea     rcx, [rsp+548h+Src]; void *
0x180013203  call    memset_0
0x180013208  mov     [rsp+548h+var_480], rsi
0x180013210  mov     [rsp+548h+var_490], rsi
0x180013218  mov     [rsp+548h+var_4B0], rsi
0x180013220  mov     [r13+0], rsi
0x180013224  mov     [rbx], esi
0x180013226  lea     rax, [rsp+548h+var_480]
0x18001322e  mov     [rsp+548h+ppv], rax; ppv
0x180013233  lea     r9, _GUID_b32f4002_bb27_45ff_af4f_06631c1e8dad; riid
0x18001323a  mov     r15d, 1
0x180013240  mov     [rsp+548h+var_4A0], r15d
0x180013248  mov     r8d, r15d; dwClsContext
0x18001324b  xor     edx, edx; pUnkOuter
0x18001324d  lea     rcx, CLSID_WpdSerializer; rclsid
0x180013254  call    cs:__imp_CoCreateInstance
0x18001325a  mov     ebx, eax
0x18001325c  test    eax, eax
0x18001325e  jns     short loc_1800132A6
0x180013260  lea     rdi, WPP_GLOBAL_Control
0x180013267  mov     r10, cs:WPP_GLOBAL_Control
0x18001326e  cmp     r10, rdi
0x180013271  jz      loc_1800140BB
0x180013277  test    byte ptr [r10+1Ch], 2
0x18001327c  jz      loc_180014096
0x180013282  mov     edx, 5Bh ; '['
0x180013287  mov     r9d, eax
0x18001328a  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x180013291  mov     rcx, [r10+10h]
0x180013295  call    WPP_SF_d
0x18001329a  mov     r10, cs:WPP_GLOBAL_Control
0x1800132a1  jmp     loc_180014096
0x1800132a6  lea     rax, [rsp+548h+var_490]
0x1800132ae  mov     [rsp+548h+ppv], rax; ppv
0x1800132b3  lea     r9, _GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40; riid
0x1800132ba  mov     r8d, r15d; dwClsContext
0x1800132bd  xor     edx, edx; pUnkOuter
0x1800132bf  lea     rcx, CLSID_PortableDeviceManager; rclsid
0x1800132c6  call    cs:__imp_CoCreateInstance
0x1800132cc  mov     ebx, eax
0x1800132ce  test    eax, eax
0x1800132d0  jns     short loc_1800132FB
0x1800132d2  lea     rdi, WPP_GLOBAL_Control
0x1800132d9  mov     r10, cs:WPP_GLOBAL_Control
0x1800132e0  cmp     r10, rdi
0x1800132e3  jz      loc_1800140BB
0x1800132e9  test    byte ptr [r10+1Ch], 2
0x1800132ee  jz      loc_180014096
0x1800132f4  mov     edx, 5Ch ; '\'
0x1800132f9  jmp     short loc_180013287
0x1800132fb  mov     [rsp+548h+var_4D0], rsi
0x180013300  mov     r14, rsi
0x180013303  mov     [rsp+548h+pszSrc], rsi
0x180013308  mov     [rsp+548h+pv], rsi
0x180013310  mov     edi, r15d
0x180013313  mov     [rsp+548h+var_508], r15d
0x180013318  mov     dword ptr [rsp+548h+cchToCopy], 208h
0x180013320  mov     rcx, [rsp+548h+var_490]
0x180013328  mov     rax, [rcx]
0x18001332b  lea     r9, [rsp+548h+cchToCopy]
0x180013330  lea     r8, [rsp+548h+Src]
0x180013338  mov     rdx, r12
0x18001333b  mov     rax, [rax+28h]
0x18001333f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013344  test    eax, eax
0x180013346  js      loc_18001350B
0x18001334c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013353  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001335a  mov     rax, [rax+18h]
0x18001335e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013363  add     rax, 18h
0x180013367  mov     [rsp+548h+var_500], rax
0x18001336c  lea     rax, [rsp+548h+Src]
0x180013374  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001337b  nop     dword ptr [rax+rax+00h]
0x180013380  inc     rbx
0x180013383  cmp     word ptr [rax+rbx*2], 0
0x180013388  jnz     short loc_180013380
0x18001338a  test    ebx, ebx
0x18001338c  jnz     short loc_18001339D
0x18001338e  lea     rcx, [rsp+548h+var_500]
0x180013393  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180013398  jmp     loc_180013451
0x18001339d  mov     rax, [rsp+548h+var_500]
0x1800133a2  mov     r12d, [rax-10h]
0x1800133a6  lea     r14, [rsp+548h+Src]
0x1800133ae  sub     r14, rax
0x1800133b1  mov     edx, r15d
0x1800133b4  sub     edx, [rax-8]
0x1800133b7  mov     ecx, [rax-0Ch]
0x1800133ba  sub     ecx, ebx
0x1800133bc  or      edx, ecx
0x1800133be  jge     short loc_1800133CC
0x1800133c0  mov     edx, ebx
0x1800133c2  lea     rcx, [rsp+548h+var_500]
0x1800133c7  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800133cc  movsxd  rax, ebx
0x1800133cf  lea     r15, [rax+rax]
0x1800133d3  test    r15, r15
0x1800133d6  jz      short loc_180013425
0x1800133d8  sar     r14, 1
0x1800133db  mov     rcx, [rsp+548h+var_500]; void *
0x1800133e0  cmp     r14, r12
0x1800133e3  ja      short loc_1800133FD
0x1800133e5  test    rcx, rcx
0x1800133e8  jz      short loc_180013414
0x1800133ea  lea     rdx, [rcx+r14*2]; Src
0x1800133ee  test    rdx, rdx
0x1800133f1  jz      short loc_180013414
0x1800133f3  mov     r8, r15; Size
0x1800133f6  call    memmove_0
0x1800133fb  jmp     short loc_180013425
0x1800133fd  test    rcx, rcx
0x180013400  jz      short loc_180013414
0x180013402  mov     r8, r15; Size
0x180013405  lea     rdx, [rsp+548h+Src]; Src
0x18001340d  call    memcpy_0
0x180013412  jmp     short loc_180013425
0x180013414  call    cs:__imp__o__errno
0x18001341a  mov     dword ptr [rax], 16h
0x180013420  call    _invalid_parameter_noinfo
0x180013425  test    ebx, ebx
0x180013427  js      short loc_18001348B
0x180013429  mov     rax, [rsp+548h+var_500]
0x18001342e  cmp     ebx, [rax-0Ch]
0x180013431  jg      short loc_18001348B
0x180013433  mov     [rax-10h], ebx
0x180013436  mov     rax, [rsp+548h+var_500]
0x18001343b  mov     [r15+rax], si
0x180013440  mov     r14, rsi
0x180013443  mov     r15d, 1
0x180013449  mov     r12, [rsp+548h+var_4C0]
0x180013451  lea     rcx, [rsp+548h+var_500]
0x180013456  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x18001345b  mov     rcx, [rsp+548h+var_500]
0x180013460  cmp     dword ptr [rcx-10h], 0
0x180013464  jle     short loc_180013481
0x180013466  lea     r14, [rsp+548h+Src]
0x18001346e  mov     [rsp+548h+pszSrc], r14
0x180013473  mov     [rsp+548h+pv], r14
0x18001347b  mov     edi, esi
0x18001347d  mov     [rsp+548h+var_508], esi
0x180013481  mov     rbx, [rsp+548h+pcchNewDestLength]
0x180013489  jmp     short loc_1800134FE
0x18001348b  mov     ecx, 80070057h; int
0x180013490  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013496  xor     esi, esi
0x180013498  mov     r15d, 1
0x18001349e  mov     [rsp+548h+var_4A0], r15d
0x1800134a6  mov     [rsp+548h+var_4D0], rsi
0x1800134ab  mov     r14, [rsp+548h+pv]
0x1800134b3  mov     [rsp+548h+pszSrc], r14
0x1800134b8  mov     edi, [rsp+548h+var_508]
0x1800134bc  mov     rcx, [rsp+548h+var_500]
0x1800134c1  mov     rbx, [rsp+548h+var_4F8]
0x1800134c6  mov     [rsp+548h+pcchNewDestLength], rbx
0x1800134ce  mov     r12, [rsp+548h+var_4C8]
0x1800134d6  mov     [rsp+548h+var_4C0], r12
0x1800134de  mov     rax, [rsp+548h+var_488]
0x1800134e6  mov     [rsp+548h+var_470], rax
0x1800134ee  mov     rax, [rsp+548h+var_468]
0x1800134f6  mov     [rsp+548h+var_478], rax
0x1800134fe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180013502  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180013507  test    edi, edi
0x180013509  jz      short loc_180013552
0x18001350b  mov     dword ptr [rsp+548h+cchToCopy], 208h
0x180013513  mov     rcx, [rsp+548h+var_490]
0x18001351b  mov     rax, [rcx]
0x18001351e  lea     r9, [rsp+548h+cchToCopy]
0x180013523  lea     r8, [rsp+548h+Src]
0x18001352b  mov     rdx, r12
0x18001352e  mov     rax, [rax+30h]
0x180013532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013537  test    eax, eax
0x180013539  js      short loc_18001354A
0x18001353b  lea     r14, [rsp+548h+Src]
0x180013543  mov     [rsp+548h+pszSrc], r14
0x180013548  jmp     short loc_18001355B
0x18001354a  mov     rbx, [rsp+548h+pcchNewDestLength]
0x180013552  test    r14, r14
0x180013555  jz      loc_180013607
0x18001355b  lea     rax, [rsp+548h+var_4B0]
0x180013563  mov     [rsp+548h+ppv], rax; ppv
0x180013568  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x18001356f  mov     r8d, r15d; dwClsContext
0x180013572  xor     edx, edx; pUnkOuter
0x180013574  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x18001357b  call    cs:__imp_CoCreateInstance
0x180013581  mov     ebx, eax
0x180013583  test    eax, eax
0x180013585  jns     short loc_1800135B3
0x180013587  lea     rdi, WPP_GLOBAL_Control
0x18001358e  mov     r10, cs:WPP_GLOBAL_Control
0x180013595  cmp     r10, rdi
0x180013598  jz      loc_1800140BB
0x18001359e  test    byte ptr [r10+1Ch], 2
0x1800135a3  jz      loc_180014096
0x1800135a9  mov     edx, 5Dh ; ']'
0x1800135ae  jmp     loc_180013287
0x1800135b3  mov     rcx, [rsp+548h+var_4B0]
0x1800135bb  mov     rax, [rcx]
0x1800135be  mov     r8, r14
0x1800135c1  lea     rdx, WPD_DEVICE_FRIENDLY_NAME
0x1800135c8  mov     rax, [rax+38h]
0x1800135cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135d1  mov     ebx, eax
0x1800135d3  test    eax, eax
0x1800135d5  jns     loc_1800139B6
0x1800135db  lea     rdi, WPP_GLOBAL_Control
0x1800135e2  mov     r10, cs:WPP_GLOBAL_Control
0x1800135e9  cmp     r10, rdi
0x1800135ec  jz      loc_1800140BB
0x1800135f2  test    byte ptr [r10+1Ch], 2
0x1800135f7  jz      loc_180014096
0x1800135fd  mov     edx, 5Eh ; '^'
0x180013602  jmp     loc_180013287
0x180013607  mov     [rsp+548h+var_4C8], rsi
0x18001360f  mov     [rsp+548h+var_4F8], rsi
0x180013614  mov     [rsp+548h+var_500], rsi
0x180013619  test    r12, r12
0x18001361c  jnz     short loc_18001362C
0x18001361e  mov     ebx, 80070057h
0x180013623  lea     rdi, WPP_GLOBAL_Control
0x18001362a  jmp     short loc_1800136A1
0x18001362c  mov     [rsp+548h+var_4C8], rsi
0x180013634  mov     rcx, rbx; this
0x180013637  call    ?_IsDelegateFolder@CBaseFolder@@QEAAHXZ; CBaseFolder::_IsDelegateFolder(void)
0x18001363c  mov     ebx, eax
0x18001363e  call    cs:__imp_GetCurrentThreadId
0x180013644  lea     rcx, [rsp+548h+var_4C8]
0x18001364c  mov     [rsp+548h+var_520], rcx; struct IPortableDevice **
0x180013651  mov     dword ptr [rsp+548h+ppv], ebx; int
0x180013655  xor     r9d, r9d; struct _ITEMIDLIST *
0x180013658  xor     r8d, r8d; struct _ITEMIDLIST *
0x18001365b  mov     edx, eax; unsigned int
0x18001365d  mov     rcx, r12; unsigned __int16 *
0x180013660  call    ?s_BindToPortableDevice@CDeviceCache@@SAJPEBGKPEFAU_ITEMIDLIST@@1HPEAPEAUIPortableDevice@@@Z; CDeviceCache::s_BindToPortableDevice(ushort const *,ulong,_ITEMIDLIST *,_ITEMIDLIST *,int,IPortableDevice * *)
0x180013665  mov     ebx, eax
0x180013667  test    eax, eax
0x180013669  jns     loc_180013740
0x18001366f  lea     rdi, WPP_GLOBAL_Control
0x180013676  mov     r10, cs:WPP_GLOBAL_Control
0x18001367d  cmp     r10, rdi
0x180013680  jz      short loc_1800136FE
0x180013682  test    byte ptr [r10+1Ch], 2
0x180013687  jz      short loc_1800136A8
0x180013689  mov     edx, 1Dh
0x18001368e  mov     r9d, eax
0x180013691  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x180013698  mov     rcx, [r10+10h]
0x18001369c  call    WPP_SF_d
0x1800136a1  mov     r10, cs:WPP_GLOBAL_Control
0x1800136a8  cmp     r10, rdi
0x1800136ab  jz      short loc_1800136FE
0x1800136ad  test    byte ptr [r10+1Ch], 2
0x1800136b2  jz      short loc_1800136D3
0x1800136b4  mov     edx, 1Eh
0x1800136b9  mov     r9d, ebx
0x1800136bc  lea     r8, WPP_f4dfe53786183352449e3e96734e584d_Traceguids
0x1800136c3  mov     rcx, [r10+10h]
0x1800136c7  call    WPP_SF_d
0x1800136cc  mov     r10, cs:WPP_GLOBAL_Control
0x1800136d3  cmp     r10, rdi
0x1800136d6  jz      short loc_1800136FE
0x1800136d8  test    byte ptr [r10+1Ch], 2
0x1800136dd  jz      short loc_1800136FE
0x1800136df  mov     edx, 5Fh ; '_'
0x1800136e4  mov     r9d, ebx
0x1800136e7  lea     r8, WPP_4da16da3d21a3bea60eae2174f41afdd_Traceguids
0x1800136ee  mov     rcx, [r10+10h]
  ... truncated ...
```
