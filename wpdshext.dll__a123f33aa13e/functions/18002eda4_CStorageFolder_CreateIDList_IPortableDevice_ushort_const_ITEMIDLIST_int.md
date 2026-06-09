# CStorageFolder::_CreateIDList(IPortableDevice *,ushort const *,_ITEMIDLIST * *,int *)

- ea: `0x18002eda4`
- end: `0x18002feae`
- name: `?_CreateIDList@CStorageFolder@@AEAAJPEAUIPortableDevice@@PEBGPEAPEFAU_ITEMIDLIST@@PEAH@Z`
- size: `4362`
- prototype: `__int64 __fastcall(CStorageFolder *__hidden this, struct IPortableDevice *, const unsigned __int16 *, struct _ITEMIDLIST **, int *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180064fa0`
- `0x1800660d0`

## callees

- `0x180014748`
- `0x180014778`
- `0x180016260`
- `0x18001a5b0`
- `0x18001ee70`
- `0x180023584`
- `0x1800285c8`
- `0x180028978`
- `0x18002950c`
- `0x18002e738`
- `0x18002e9f0`
- `0x18002eda4`
- `0x18002feb4`
- `0x18002ff5c`
- `0x180035590`
- `0x180039d74`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f0ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f0ec`
- `ole32!CoTaskMemFree` at `0x18002fdbe`
- `ole32!CoTaskMemFree` at `0x18002fdcc`
- `ole32!CoTaskMemFree` at `0x18002fdda`
- `ole32!CoTaskMemFree` at `0x18002fdbe`
- `ole32!CoTaskMemFree` at `0x18002fdcc`
- `ole32!CoTaskMemFree` at `0x18002fdda`
- `ole32!PropVariantClear` at `0x18002f185`
- `ole32!PropVariantClear` at `0x18002fb67`
- `ole32!PropVariantClear` at `0x18002fdab`
- `ole32!PropVariantClear` at `0x18002f185`
- `ole32!PropVariantClear` at `0x18002fb67`
- `ole32!PropVariantClear` at `0x18002fdab`
- `ole32!CoCreateInstance` at `0x18002eec3`
- `ole32!CoCreateInstance` at `0x18002eec3`
- `ole32!StringFromGUID2` at `0x18002fb2d`
- `ole32!StringFromGUID2` at `0x18002fb2d`
- `SHELL32!__imp_ILFree` at `0x18002fc00`
- `SHELL32!__imp_ILFree` at `0x18002fc00`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CStorageFolder::_CreateIDList(
        CStorageFolder *this,
        struct IPortableDevice *a2,
        const unsigned __int16 *a3,
        struct _ITEMIDLIST **a4,
        int *a5)
{
  unsigned __int16 *v6; // r13
  HRESULT v7; // eax
  int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned __int16 *v11; // r12
  unsigned __int16 *v12; // r13
  int v13; // esi
  unsigned int i; // ebx
  unsigned int v15; // r12d
  __int64 v16; // r8
  __int64 v17; // rbx
  int v18; // ebx
  int PortableDeviceResources; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  struct IPortableDevice *v22; // r12
  unsigned int j; // ebx
  int v24; // r12d
  int v25; // eax
  void *v26; // rcx
  int v27; // eax
  unsigned __int16 *v28; // r14
  int v29; // eax
  struct _ITEMIDLIST **v30; // rcx
  int v31; // eax
  const unsigned __int16 *v32; // rcx
  int v33; // eax
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  unsigned __int16 v36; // r13
  __int16 v37; // r14
  unsigned __int64 v38; // r10
  __int16 v39; // r11
  unsigned __int16 v40; // dx
  char *v41; // rax
  char *v42; // r14
  unsigned __int64 v43; // r12
  unsigned __int16 *v44; // rsi
  unsigned __int16 *v45; // rsi
  unsigned __int16 *v46; // rsi
  OLECHAR *v47; // rsi
  unsigned int k; // r12d
  unsigned __int64 v49; // rax
  OLECHAR *v50; // r9
  int v51; // esi
  int v52; // eax
  PVOID *v53; // rcx
  const WCHAR *v54; // r9
  unsigned __int64 *ppv; // [rsp+20h] [rbp-1B8h]
  unsigned int v57; // [rsp+28h] [rbp-1B0h]
  int v58; // [rsp+30h] [rbp-1A8h]
  unsigned __int16 v59; // [rsp+30h] [rbp-1A8h]
  unsigned __int16 v60[2]; // [rsp+34h] [rbp-1A4h] BYREF
  unsigned int v61; // [rsp+38h] [rbp-1A0h] BYREF
  unsigned __int16 *v62; // [rsp+40h] [rbp-198h]
  unsigned __int16 *v63; // [rsp+48h] [rbp-190h] BYREF
  unsigned __int16 *v64; // [rsp+50h] [rbp-188h]
  __int64 v65; // [rsp+58h] [rbp-180h] BYREF
  int v66; // [rsp+60h] [rbp-178h]
  unsigned int v67; // [rsp+64h] [rbp-174h] BYREF
  int v68; // [rsp+68h] [rbp-170h] BYREF
  unsigned int v69; // [rsp+6Ch] [rbp-16Ch] BYREF
  LPVOID pv; // [rsp+70h] [rbp-168h]
  __int64 v71; // [rsp+78h] [rbp-160h] BYREF
  void *v72; // [rsp+80h] [rbp-158h] BYREF
  __int64 v73; // [rsp+88h] [rbp-150h] BYREF
  int v74; // [rsp+90h] [rbp-148h] BYREF
  int v75; // [rsp+94h] [rbp-144h] BYREF
  const unsigned __int16 *v76; // [rsp+98h] [rbp-140h]
  struct _ITEMIDLIST **v77; // [rsp+A0h] [rbp-138h] BYREF
  __int64 v78; // [rsp+A8h] [rbp-130h] BYREF
  __int64 v79; // [rsp+B0h] [rbp-128h] BYREF
  LPVOID v80; // [rsp+B8h] [rbp-120h] BYREF
  __int64 v81; // [rsp+C0h] [rbp-118h] BYREF
  __int64 v82; // [rsp+C8h] [rbp-110h] BYREF
  struct IPortableDeviceProperties *v83; // [rsp+D0h] [rbp-108h] BYREF
  struct IPortableDeviceResources *v84; // [rsp+D8h] [rbp-100h] BYREF
  const unsigned __int16 *v85; // [rsp+E0h] [rbp-F8h]
  struct _ITEMIDLIST **v86; // [rsp+E8h] [rbp-F0h]
  CBaseFolder *v87; // [rsp+F0h] [rbp-E8h]
  int *v88; // [rsp+F8h] [rbp-E0h]
  struct _ITEMIDLIST **v89; // [rsp+100h] [rbp-D8h]
  __int64 v90; // [rsp+108h] [rbp-D0h] BYREF
  struct IPortableDevice *v91; // [rsp+110h] [rbp-C8h]
  PROPVARIANT rguid; // [rsp+118h] [rbp-C0h] BYREF
  CBaseFolder *v93; // [rsp+140h] [rbp-98h]
  struct IPortableDevice *v94; // [rsp+148h] [rbp-90h]
  __int64 v95; // [rsp+158h] [rbp-80h] BYREF
  PROPVARIANT pvar; // [rsp+160h] [rbp-78h] BYREF
  __int128 Buf2; // [rsp+178h] [rbp-60h] BYREF
  int v98; // [rsp+188h] [rbp-50h]
  __int64 v99; // [rsp+190h] [rbp-48h] BYREF

  v89 = a4;
  v76 = a3;
  v91 = a2;
  v87 = this;
  v93 = this;
  v94 = a2;
  v85 = a3;
  v86 = a4;
  v88 = a5;
  pv = 0;
  v64 = 0;
  v6 = 0;
  v62 = 0;
  v75 = 0;
  Buf2 = 0;
  v98 = 0;
  v69 = 0;
  v67 = 0;
  v80 = 0;
  v84 = 0;
  v83 = 0;
  v79 = 0;
  v82 = 0;
  v65 = 0;
  v95 = 0;
  v73 = 0;
  v78 = 0;
  *a4 = 0;
  *a5 = 0;
  memset(&rguid, 0, sizeof(rguid));
  v7 = CoCreateInstance(&CLSID_WpdSerializer, 0, 1u, &GUID_b32f4002_bb27_45ff_af4f_06631c1e8dad, &v80);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_6;
    v10 = 96;
    goto LABEL_5;
  }
  v7 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a2->lpVtbl->Capabilities)(a2, &v73);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_6;
    v10 = 97;
    goto LABEL_5;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 24LL))(v73, &v82);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_189;
    v10 = 98;
LABEL_5:
    WPP_SF_d(v9[2], v10, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v7);
LABEL_6:
    v11 = 0;
    v12 = 0;
    goto LABEL_190;
  }
  v13 = 0;
  v58 = 0;
  for ( i = 0; ; ++i )
  {
    v61 = i;
    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v82 + 32LL))(v82, i, &Buf2) )
      break;
    switch ( v98 )
    {
      case 2:
        if ( memcmp_0(&WPD_COMMAND_STORAGE_FORMAT, &Buf2, 0x10u) )
        {
          if ( memcmp_0(&WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_ONLY, &Buf2, 0x10u) )
            continue;
          v13 |= 8u;
          goto LABEL_49;
        }
        v71 = 0;
        v81 = 0;
        if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int64 *))(*(_QWORD *)v73 + 32LL))(
               v73,
               &WPD_COMMAND_STORAGE_FORMAT,
               &v71) < 0
          || (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int64 *))(*(_QWORD *)v71 + 272LL))(
               v71,
               &WPD_OPTION_VALID_OBJECT_IDS,
               &v81) < 0 )
        {
          v13 |= 4u;
          v58 = v13;
        }
        else
        {
          v15 = 0;
          *(_DWORD *)v60 = 0;
          memset(&pvar, 0, sizeof(pvar));
          while ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v81 + 32LL))(
                     v81,
                     v15,
                     &pvar) )
          {
            v66 = 0;
            try
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v90);
              if ( pvar.hVal.QuadPart )
              {
                v16 = -1;
                do
                  ++v16;
                while ( *(_WORD *)(pvar.hVal.QuadPart + 2 * v16) );
              }
              else
              {
                v16 = 0;
              }
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))ATL::CSimpleStringT<unsigned short,0>::SetString)(
                &v90,
                (LARGE_INTEGER)pvar.hVal.QuadPart,
                v16);
              v17 = v90;
              LODWORD(v63) = _o__wcsicmp(v90, v76) == 0;
              v66 = (int)v63;
              ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
              v18 = (int)v63;
            }
            catch ( ATL::CAtlException v99 )
            {
              pv = 0;
              v64 = 0;
              v6 = 0;
              v62 = 0;
              v13 = v58;
              v15 = *(_DWORD *)v60;
              v18 = v66;
              v87 = v93;
              v91 = v94;
              v76 = v85;
              v89 = v86;
            }
            PropVariantClear(&pvar);
            if ( v18 == 1 )
            {
              v13 |= 4u;
              v58 = v13;
              break;
            }
            *(_DWORD *)v60 = ++v15;
          }
          i = v61;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v81);
        goto LABEL_56;
      case 7:
        if ( memcmp_0(&WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS, &Buf2, 0x10u) )
          continue;
        v13 |= 2u;
LABEL_49:
        v58 = v13;
        continue;
      case 3:
        if ( memcmp_0(&WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_AND_DATA, &Buf2, 0x10u) )
          continue;
        v13 |= 0x10u;
        goto LABEL_49;
      case 8:
        if ( memcmp_0(&WPD_COMMAND_OBJECT_MANAGEMENT_MOVE_OBJECTS, &Buf2, 0x10u) )
          continue;
        v13 |= 0x20u;
        goto LABEL_49;
      case 9:
        if ( memcmp_0(&WPD_COMMAND_OBJECT_MANAGEMENT_COPY_OBJECTS, &Buf2, 0x10u) )
          continue;
        v13 |= 0x80u;
        goto LABEL_49;
    }
    if ( v98 == 11 && !memcmp_0(&WPD_COMMAND_OBJECT_RESOURCES_SEEK, &Buf2, 0x10u) )
    {
      v71 = 0;
      if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, __int64 *))(*(_QWORD *)v73 + 32LL))(
             v73,
             &WPD_COMMAND_OBJECT_RESOURCES_SEEK,
             &v71) >= 0 )
      {
        v61 = 0;
        if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, unsigned int *))(*(_QWORD *)v71 + 192LL))(
               v71,
               &WPD_OPTION_OBJECT_RESOURCES_SEEK_ON_READ_SUPPORTED,
               &v61) >= 0 )
        {
          if ( v61 )
          {
            v13 |= 0x40u;
            v58 = v13;
          }
        }
      }
LABEL_56:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v71);
      continue;
    }
  }
  PortableDeviceResources = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64 *))(*(_QWORD *)v73 + 56LL))(
                              v73,
                              &WPD_FUNCTIONAL_CATEGORY_STORAGE,
                              &v78);
  v8 = PortableDeviceResources;
  if ( PortableDeviceResources >= 0 )
  {
    PortableDeviceResources = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v78 + 24LL))(v78, &v75);
    v8 = PortableDeviceResources;
    if ( PortableDeviceResources < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_189;
      v21 = 100;
      goto LABEL_62;
    }
    v22 = v91;
    PortableDeviceResources = GetPortableDeviceResources(v91, &v84);
    v8 = PortableDeviceResources;
    if ( PortableDeviceResources < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_189;
      v21 = 101;
      goto LABEL_62;
    }
    if ( ((int (__fastcall *)(struct IPortableDeviceResources *, const unsigned __int16 *, __int64 *))v84->lpVtbl->GetSupportedResources)(
           v84,
           v76,
           &v79) >= 0
      && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v79 + 24LL))(v79, &v69) >= 0 )
    {
      for ( j = 0; j < v69; ++j )
      {
        if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v79 + 32LL))(v79, j, &Buf2) >= 0 && !v98 )
        {
          if ( !memcmp_0(&WPD_RESOURCE_CONTACT_PHOTO, &Buf2, 0x10u) )
          {
            v13 |= 0x10000u;
          }
          else if ( !memcmp_0(&WPD_RESOURCE_THUMBNAIL, &Buf2, 0x10u) )
          {
            v13 |= 0x20000u;
          }
          else if ( !memcmp_0(&WPD_RESOURCE_ICON, &Buf2, 0x10u) )
          {
            v13 |= 0x40000u;
          }
          else if ( !memcmp_0(&WPD_RESOURCE_AUDIO_CLIP, &Buf2, 0x10u) )
          {
            v13 |= 0x80000u;
          }
          else if ( !memcmp_0(&WPD_RESOURCE_ALBUM_ART, &Buf2, 0x10u) )
          {
            v13 |= 0x100000u;
          }
        }
      }
    }
    PortableDeviceResources = GetPortableDeviceProperties(v22, &v83);
    v8 = PortableDeviceResources;
    if ( PortableDeviceResources < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_189;
      v21 = 102;
      goto LABEL_62;
    }
    PortableDeviceResources = ((__int64 (__fastcall *)(struct IPortableDeviceProperties *, const unsigned __int16 *, _QWORD, __int64 *))v83->lpVtbl->GetValues)(
                                v83,
                                v76,
                                0,
                                &v65);
    v8 = PortableDeviceResources;
    if ( PortableDeviceResources < 0 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_189;
      v21 = 103;
LABEL_62:
      WPP_SF_d(v20[2], v21, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)PortableDeviceResources);
      goto LABEL_189;
    }
    v24 = 0;
    v72 = 0;
    v77 = 0;
    v74 = 0;
    v68 = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v65 + 192LL))(
           v65,
           &WPD_OBJECT_ISHIDDEN,
           &v68) >= 0
      && v68 )
    {
      v24 = 256;
    }
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v65 + 192LL))(
           v65,
           &WPD_OBJECT_ISSYSTEM,
           &v68) >= 0
      && v68 )
    {
      v24 |= 0x400u;
    }
    v25 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, void **))(*(_QWORD *)v65 + 64LL))(
            v65,
            &WPD_OBJECT_NAME,
            &v72);
    v26 = pv;
    if ( v25 >= 0 )
      v26 = v72;
    pv = v26;
    v27 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, void **))(*(_QWORD *)v65 + 64LL))(
            v65,
            &WPD_OBJECT_PERSISTENT_UNIQUE_ID,
            &v72);
    v28 = v64;
    if ( v27 >= 0 )
      v28 = (unsigned __int16 *)v72;
    v64 = v28;
    v29 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct _ITEMIDLIST ***))(*(_QWORD *)v65 + 112LL))(
            v65,
            &WPD_STORAGE_CAPACITY,
            &v77);
    v30 = 0;
    if ( v29 >= 0 )
      v30 = v77;
    v86 = v30;
    v31 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct _ITEMIDLIST ***))(*(_QWORD *)v65 + 112LL))(
            v65,
            &WPD_STORAGE_MAX_OBJECT_SIZE,
            &v77);
    v32 = 0;
    if ( v31 >= 0 )
      v32 = (const unsigned __int16 *)v77;
    v85 = v32;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, void **))(*(_QWORD *)v65 + 64LL))(
           v65,
           &WPD_STORAGE_FILE_SYSTEM_TYPE,
           &v72) >= 0 )
      v6 = (unsigned __int16 *)v72;
    v62 = v6;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, int *))(*(_QWORD *)v65 + 80LL))(
           v65,
           &WPD_STORAGE_TYPE,
           &v74) >= 0
      && (v74 & 6) != 0 )
    {
      v13 |= 0x200000u;
    }
    v33 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *))(*(_QWORD *)v65 + 312LL))(v65, &WPD_OBJECT_ID);
    v8 = v33;
    if ( v33 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_189;
      v35 = 104;
LABEL_118:
      WPP_SF_d(v34[2], v35, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v33);
      v11 = v6;
      v12 = v28;
      goto LABEL_190;
    }
    v33 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *))(*(_QWORD *)v65 + 312LL))(v65, &WPD_OBJECT_PARENT_ID);
    v8 = v33;
    if ( v33 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_189;
      v35 = 105;
      goto LABEL_118;
    }
    v33 = (*(__int64 (__fastcall **)(LPVOID, __int64, unsigned int *))(*(_QWORD *)v80 + 48LL))(v80, v65, &v67);
    v8 = v33;
    if ( v33 < 0 )
    {
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_189;
      v35 = 106;
      goto LABEL_118;
    }
    v36 = 1;
    LOWORD(v61) = 1;
    v37 = 1;
    LOWORD(v66) = 1;
    v63 = 0;
    v38 = 260;
    if ( pv && (int)StringCchLengthW((const unsigned __int16 *)pv, 0x104u, (unsigned __int64 *)&v63) >= 0 )
      v36 = (_WORD)v63 + 1;
    if ( v64 && (int)StringCchLengthW(v64, v38, (unsigned __int64 *)&v63) >= 0 )
      LOWORD(v61) = (_WORD)v63 + 1;
    if ( v62 && (int)StringCchLengthW(v62, v38, (unsigned __int64 *)&v63) >= 0 )
    {
      v37 = (_WORD)v63 + 1;
      LOWORD(v66) = (_WORD)v63 + 1;
    }
    v60[0] = 0;
    v8 = UIntToUShort(v67, v60);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v67);
      goto LABEL_189;
    }
    v40 = 2 * (v36 + v39 + v37 + 39 * v75 + 25);
    v59 = v60[0] + v40;
    if ( (unsigned __int16)(v60[0] + v40) < v40 )
    {
      v8 = -2147024362;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LODWORD(ppv) = v60[0];
        WPP_SF_ddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          108,
          WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
          v40,
          ppv,
          -2147024362);
      }
      goto LABEL_189;
    }
    v41 = (char *)CBaseFolder::_Alloc(v87, v60[0] + v40);
    v42 = v41;
    if ( !v41 )
    {
      v8 = -2147024882;
      goto LABEL_189;
    }
    v8 = 0;
    *(_DWORD *)(v41 + 6) = 271654917;
    *(_DWORD *)(v41 + 10) = v24 | 2;
    *(_DWORD *)(v41 + 14) = v13;
    *(_QWORD *)(v41 + 18) = v86;
    *(_QWORD *)(v41 + 26) = v85;
    *(_DWORD *)(v41 + 34) = v60[0];
    *(_DWORD *)(v41 + 38) = v36;
    v43 = (unsigned __int16)v61;
    *(_DWORD *)(v41 + 42) = (unsigned __int16)v61;
    *(_DWORD *)(v41 + 46) = (unsigned __int16)v66;
    v44 = (unsigned __int16 *)(v41 + 54);
    v63 = (unsigned __int16 *)(v41 + 54);
    if ( pv )
    {
      StringCchCopyExW((unsigned __int16 *)v41 + 27, v36, (const unsigned __int16 *)pv, &v63, ppv, v57);
      v44 = v63;
    }
    v45 = v44 + 1;
    v63 = v45;
    v12 = v64;
    if ( v64 )
    {
      StringCchCopyExW(v45, v43, v64, &v63, ppv, v57);
      v45 = v63;
    }
    v46 = v45 + 1;
    v63 = v46;
    if ( v62 )
    {
      StringCchCopyExW(v46, (unsigned __int16)v66, v62, &v63, ppv, v57);
      v46 = v63;
    }
    v47 = v46 + 1;
    for ( k = 0;
          !(*(unsigned int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v78 + 32LL))(v78, k, &rguid);
          ++k )
    {
      if ( rguid.vt == 72 )
      {
        ++*(_DWORD *)(v42 + 50);
        StringFromGUID2(rguid.puuid, v47, 39);
        v47 += 39;
        v49 = *(_QWORD *)&WPD_CONTENT_TYPE_FOLDER.Data1 - (unsigned __int64)*rguid.pbstrVal;
        if ( *(BSTR *)&WPD_CONTENT_TYPE_FOLDER.Data1 == *rguid.pbstrVal )
          v49 = *(_QWORD *)WPD_CONTENT_TYPE_FOLDER.Data4 - *(_QWORD *)(rguid.hVal.QuadPart + 8);
        if ( !v49 )
          *(_DWORD *)(v42 + 10) |= 1u;
        PropVariantClear(&rguid);
      }
    }
    v11 = v62;
    if ( v60[0] )
    {
      v50 = v47;
      v51 = v60[0];
      v52 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, OLECHAR *, unsigned int *))(*(_QWORD *)v80 + 32LL))(
              v80,
              v60[0],
              v65,
              v50,
              &v67);
      v8 = v52;
      if ( v52 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            109,
            WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
            (unsigned int)v52);
        goto LABEL_165;
      }
      if ( v51 != v67 )
      {
        v8 = -2147418113;
LABEL_165:
        ILFree((LPITEMIDLIST)v42);
        goto LABEL_190;
      }
    }
    *v88 = 8 * (*(_DWORD *)(v42 + 10) & 2);
    *v89 = (struct _ITEMIDLIST *)v42;
    v53 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, pv);
        v53 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v53 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v53 + 28) & 0x40) != 0 )
        {
          WPP_SF_d(v53[2], 111, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, *(unsigned int *)(v42 + 10));
          v53 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v53 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v53 + 28) & 0x40) != 0 )
          {
            WPP_SF_d(v53[2], 112, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, *(unsigned int *)(v42 + 14));
            v53 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v53 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v53 + 28) & 0x40) != 0 )
            {
              WPP_SF_S(v53[2], 113, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v12);
              v53 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v53 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v53 + 28) & 0x40) != 0 )
              {
                v54 = &String;
                if ( v11 )
                  v54 = v11;
                WPP_SF_S(v53[2], 114, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v54);
                v53 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v53 != &WPP_GLOBAL_Control && (*((_BYTE *)v53 + 28) & 0x40) != 0 )
                WPP_SF_d(v53[2], 115, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v59);
            }
          }
        }
      }
    }
    goto LABEL_190;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v21 = 99;
    goto LABEL_62;
  }
LABEL_189:
  v11 = v62;
  v12 = v64;
LABEL_190:
  PropVariantClear(&rguid);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v8 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      WPP_9caa288f52d13f713777aed0becde05d_Traceguids,
      (unsigned int)v8);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v78);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v95);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v65);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v82);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v79);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v83);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v84);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002eda4  mov     r11, rsp
0x18002eda7  push    rbx
0x18002eda8  push    rsi
0x18002eda9  push    rdi
0x18002edaa  push    r12
0x18002edac  push    r13
0x18002edae  push    r14
0x18002edb0  push    r15
0x18002edb2  sub     rsp, 1A0h
0x18002edb9  mov     rax, cs:__security_cookie
0x18002edc0  xor     rax, rsp
0x18002edc3  mov     [rsp+1D8h+var_40], rax
0x18002edcb  mov     [rsp+1D8h+var_D8], r9
0x18002edd3  mov     rax, r8
0x18002edd6  mov     [rsp+1D8h+var_140], rax
0x18002edde  mov     r12, rdx
0x18002ede1  mov     [rsp+1D8h+var_C8], rdx
0x18002ede9  mov     [rsp+1D8h+var_E8], rcx
0x18002edf1  mov     [rsp+1D8h+var_98], rcx
0x18002edf9  mov     [rsp+1D8h+var_90], rdx
0x18002ee01  mov     [rsp+1D8h+var_F8], rax
0x18002ee09  mov     [rsp+1D8h+var_F0], r9
0x18002ee11  mov     rdx, [rsp+1D8h+arg_20]
0x18002ee19  mov     [rsp+1D8h+var_E0], rdx
0x18002ee21  xor     edi, edi
0x18002ee23  mov     eax, edi
0x18002ee25  mov     [rsp+1D8h+pv], rax
0x18002ee2a  mov     [rsp+1D8h+var_188], rdi
0x18002ee2f  mov     r13d, edi
0x18002ee32  mov     [rsp+1D8h+var_198], rdi
0x18002ee37  mov     [rsp+1D8h+var_144], edi
0x18002ee3e  xorps   xmm0, xmm0
0x18002ee41  movups  xmmword ptr [r11-60h], xmm0
0x18002ee46  mov     [r11-50h], eax
0x18002ee4a  mov     [rsp+1D8h+var_16C], edi
0x18002ee4e  mov     [rsp+1D8h+var_174], edi
0x18002ee52  mov     [r11-120h], rdi
0x18002ee59  mov     [r11-100h], rdi
0x18002ee60  mov     [r11-108h], rdi
0x18002ee67  mov     [r11-128h], rdi
0x18002ee6e  mov     [r11-110h], rdi
0x18002ee75  mov     [rsp+1D8h+var_180], rdi
0x18002ee7a  mov     [r11-80h], rdi
0x18002ee7e  mov     [r11-150h], rdi
0x18002ee85  mov     [r11-130h], rdi
0x18002ee8c  mov     [r9], rdi
0x18002ee8f  mov     [rdx], edi
0x18002ee91  movups  xmmword ptr [rsp+1D8h+rguid], xmm0
0x18002ee99  mov     [r11-0B0h], rax
0x18002eea0  lea     rax, [r11-120h]
0x18002eea7  mov     [rsp+1D8h+ppv], rax; unsigned __int64 *
0x18002eeac  lea     r9, _GUID_b32f4002_bb27_45ff_af4f_06631c1e8dad; riid
0x18002eeb3  lea     r15d, [rdi+1]
0x18002eeb7  mov     r8d, r15d; dwClsContext
0x18002eeba  xor     edx, edx; pUnkOuter
0x18002eebc  lea     rcx, CLSID_WpdSerializer; rclsid
0x18002eec3  call    cs:__imp_CoCreateInstance
0x18002eec9  mov     ebx, eax
0x18002eecb  test    eax, eax
0x18002eecd  jns     short loc_18002EF09
0x18002eecf  lea     rsi, WPP_GLOBAL_Control
0x18002eed6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eedd  cmp     rcx, rsi
0x18002eee0  jz      short loc_18002EEFE
0x18002eee2  test    byte ptr [rcx+1Ch], 2
0x18002eee6  jz      short loc_18002EEFE
0x18002eee8  lea     edx, [rdi+60h]
0x18002eeeb  mov     r9d, eax
0x18002eeee  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x18002eef5  mov     rcx, [rcx+10h]
0x18002eef9  call    WPP_SF_d
0x18002eefe  mov     r12, rdi
0x18002ef01  mov     r13, rdi
0x18002ef04  jmp     loc_18002FDA3
0x18002ef09  mov     rax, [r12]
0x18002ef0d  lea     rdx, [rsp+1D8h+var_150]
0x18002ef15  mov     rcx, r12
0x18002ef18  mov     rax, [rax+30h]
0x18002ef1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef21  mov     ebx, eax
0x18002ef23  test    eax, eax
0x18002ef25  jns     short loc_18002EF47
0x18002ef27  lea     rsi, WPP_GLOBAL_Control
0x18002ef2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef35  cmp     rcx, rsi
0x18002ef38  jz      short loc_18002EEFE
0x18002ef3a  test    byte ptr [rcx+1Ch], 2
0x18002ef3e  jz      short loc_18002EEFE
0x18002ef40  mov     edx, 61h ; 'a'
0x18002ef45  jmp     short loc_18002EEEB
0x18002ef47  mov     rcx, [rsp+1D8h+var_150]
0x18002ef4f  mov     rax, [rcx]
0x18002ef52  lea     rdx, [rsp+1D8h+var_110]
0x18002ef5a  mov     rax, [rax+18h]
0x18002ef5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef63  mov     ebx, eax
0x18002ef65  test    eax, eax
0x18002ef67  jns     short loc_18002EF90
0x18002ef69  lea     rsi, WPP_GLOBAL_Control
0x18002ef70  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef77  cmp     rcx, rsi
0x18002ef7a  jz      short loc_18002EEFE
0x18002ef7c  test    byte ptr [rcx+1Ch], 2
0x18002ef80  jz      loc_18002FD99
0x18002ef86  mov     edx, 62h ; 'b'
0x18002ef8b  jmp     loc_18002EEEB
0x18002ef90  mov     esi, edi
0x18002ef92  mov     [rsp+1D8h+var_1A8], edi
0x18002ef96  mov     ebx, edi
0x18002ef98  mov     r14d, 10h
0x18002ef9e  mov     [rsp+1D8h+var_1A0], ebx
0x18002efa2  mov     rcx, [rsp+1D8h+var_110]
0x18002efaa  mov     rax, [rcx]
0x18002efad  lea     r8, [rsp+1D8h+Buf2]
0x18002efb5  mov     edx, ebx
0x18002efb7  mov     rax, [rax+20h]
0x18002efbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efc0  test    eax, eax
0x18002efc2  jnz     loc_18002F330
0x18002efc8  mov     eax, [rsp+1D8h+var_50]
0x18002efcf  cmp     eax, 2
0x18002efd2  jnz     loc_18002F1C4
0x18002efd8  mov     r8, r14; Size
0x18002efdb  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18002efe3  lea     rcx, WPD_COMMAND_STORAGE_FORMAT; Buf1
0x18002efea  call    memcmp_0
0x18002efef  test    eax, eax
0x18002eff1  jnz     loc_18002F1F5
0x18002eff7  mov     [rsp+1D8h+var_160], rdi
0x18002effc  mov     [rsp+1D8h+var_118], rdi
0x18002f004  mov     rcx, [rsp+1D8h+var_150]
0x18002f00c  mov     rax, [rcx]
0x18002f00f  lea     r8, [rsp+1D8h+var_160]
0x18002f014  lea     rdx, WPD_COMMAND_STORAGE_FORMAT
0x18002f01b  mov     rax, [rax+20h]
0x18002f01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f024  test    eax, eax
0x18002f026  js      loc_18002F1BB
0x18002f02c  mov     rcx, [rsp+1D8h+var_160]
0x18002f031  mov     rax, [rcx]
0x18002f034  lea     r8, [rsp+1D8h+var_118]
0x18002f03c  lea     rdx, WPD_OPTION_VALID_OBJECT_IDS
0x18002f043  mov     rax, [rax+110h]
0x18002f04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f04f  test    eax, eax
0x18002f051  js      loc_18002F1BB
0x18002f057  mov     r12d, edi
0x18002f05a  mov     dword ptr [rsp+1D8h+var_1A4], edi
0x18002f05e  xorps   xmm0, xmm0
0x18002f061  xor     eax, eax
0x18002f063  movups  xmmword ptr [rsp+1D8h+pvar], xmm0
0x18002f06b  mov     qword ptr [rsp+1D8h+pvar+10h], rax
0x18002f073  mov     rcx, [rsp+1D8h+var_118]
0x18002f07b  mov     rax, [rcx]
0x18002f07e  lea     r8, [rsp+1D8h+pvar]
0x18002f086  mov     edx, r12d
0x18002f089  mov     rax, [rax+20h]
0x18002f08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f092  test    eax, eax
0x18002f094  jnz     loc_18002F197
0x18002f09a  mov     [rsp+1D8h+var_178], edi
0x18002f09e  lea     rcx, [rsp+1D8h+var_D0]
0x18002f0a6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002f0ab  nop
0x18002f0ac  mov     rdx, qword ptr [rsp+1D8h+pvar+8]
0x18002f0b4  test    rdx, rdx
0x18002f0b7  jnz     short loc_18002F0BE
0x18002f0b9  mov     r8d, edi
0x18002f0bc  jmp     short loc_18002F0CC
0x18002f0be  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f0c2  inc     r8
0x18002f0c5  cmp     [rdx+r8*2], di
0x18002f0ca  jnz     short loc_18002F0C2
0x18002f0cc  lea     rcx, [rsp+1D8h+var_D0]
0x18002f0d4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002f0d9  mov     rdx, [rsp+1D8h+var_140]
0x18002f0e1  mov     rbx, [rsp+1D8h+var_D0]
0x18002f0e9  mov     rcx, rbx
0x18002f0ec  call    cs:__imp__o__wcsicmp
0x18002f0f2  mov     ecx, edi
0x18002f0f4  test    eax, eax
0x18002f0f6  cmovz   ecx, r15d
0x18002f0fa  mov     dword ptr [rsp+1D8h+var_190], ecx
0x18002f0fe  mov     [rsp+1D8h+var_178], ecx
0x18002f102  lea     rcx, [rbx-18h]; this
0x18002f106  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002f10b  nop
0x18002f10c  mov     ebx, dword ptr [rsp+1D8h+var_190]
0x18002f110  jmp     short loc_18002F17D
0x18002f112  xor     edi, edi
0x18002f114  lea     r15d, [rdi+1]
0x18002f118  lea     r14d, [rdi+10h]
0x18002f11c  mov     [rsp+1D8h+pv], rdi
0x18002f121  mov     ecx, edi
0x18002f123  mov     [rsp+1D8h+var_188], rcx
0x18002f128  mov     r13d, edi
0x18002f12b  mov     [rsp+1D8h+var_198], rcx
0x18002f130  mov     esi, [rsp+1D8h+var_1A8]
0x18002f134  mov     r12d, dword ptr [rsp+1D8h+var_1A4]
0x18002f139  mov     ebx, [rsp+1D8h+var_178]
0x18002f13d  mov     rax, [rsp+1D8h+var_98]
0x18002f145  mov     [rsp+1D8h+var_E8], rax
0x18002f14d  mov     rax, [rsp+1D8h+var_90]
0x18002f155  mov     [rsp+1D8h+var_C8], rax
0x18002f15d  mov     rax, [rsp+1D8h+var_F8]
0x18002f165  mov     [rsp+1D8h+var_140], rax
0x18002f16d  mov     rax, [rsp+1D8h+var_F0]
0x18002f175  mov     [rsp+1D8h+var_D8], rax
0x18002f17d  lea     rcx, [rsp+1D8h+pvar]; pvar
0x18002f185  call    cs:__imp_PropVariantClear
0x18002f18b  cmp     ebx, r15d
0x18002f18e  jnz     short loc_18002F1AE
0x18002f190  or      esi, 4
0x18002f193  mov     [rsp+1D8h+var_1A8], esi
0x18002f197  mov     ebx, [rsp+1D8h+var_1A0]
0x18002f19b  lea     rcx, [rsp+1D8h+var_118]
0x18002f1a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002f1a8  nop
0x18002f1a9  jmp     loc_18002F31E
0x18002f1ae  add     r12d, r15d
0x18002f1b1  mov     dword ptr [rsp+1D8h+var_1A4], r12d
0x18002f1b6  jmp     loc_18002F073
0x18002f1bb  or      esi, 4
0x18002f1be  mov     [rsp+1D8h+var_1A8], esi
0x18002f1c2  jmp     short loc_18002F19B
0x18002f1c4  cmp     eax, 7
0x18002f1c7  jnz     short loc_18002F1F0
0x18002f1c9  mov     r8, r14; Size
0x18002f1cc  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18002f1d4  lea     rcx, WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS; Buf1
0x18002f1db  call    memcmp_0
0x18002f1e0  test    eax, eax
0x18002f1e2  jnz     loc_18002F328
0x18002f1e8  or      esi, 2
0x18002f1eb  jmp     loc_18002F293
0x18002f1f0  cmp     eax, 2
0x18002f1f3  jnz     short loc_18002F219
0x18002f1f5  mov     r8, r14; Size
0x18002f1f8  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18002f200  lea     rcx, WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_ONLY; Buf1
0x18002f207  call    memcmp_0
0x18002f20c  test    eax, eax
0x18002f20e  jnz     loc_18002F328
0x18002f214  or      esi, 8
0x18002f217  jmp     short loc_18002F293
0x18002f219  cmp     eax, 3
0x18002f21c  jnz     short loc_18002F242
0x18002f21e  mov     r8, r14; Size
0x18002f221  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18002f229  lea     rcx, WPD_COMMAND_OBJECT_MANAGEMENT_CREATE_OBJECT_WITH_PROPERTIES_AND_DATA; Buf1
0x18002f230  call    memcmp_0
0x18002f235  test    eax, eax
0x18002f237  jnz     loc_18002F328
0x18002f23d  or      esi, r14d
0x18002f240  jmp     short loc_18002F293
0x18002f242  cmp     eax, 8
0x18002f245  jnz     short loc_18002F26B
0x18002f247  mov     r8, r14; Size
0x18002f24a  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18002f252  lea     rcx, WPD_COMMAND_OBJECT_MANAGEMENT_MOVE_OBJECTS; Buf1
0x18002f259  call    memcmp_0
0x18002f25e  test    eax, eax
0x18002f260  jnz     loc_18002F328
0x18002f266  or      esi, 20h
0x18002f269  jmp     short loc_18002F293
0x18002f26b  cmp     eax, 9
0x18002f26e  jnz     short loc_18002F29C
0x18002f270  mov     r8, r14; Size
0x18002f273  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18002f27b  lea     rcx, WPD_COMMAND_OBJECT_MANAGEMENT_COPY_OBJECTS; Buf1
0x18002f282  call    memcmp_0
0x18002f287  test    eax, eax
0x18002f289  jnz     loc_18002F328
0x18002f28f  bts     esi, 7
0x18002f293  mov     [rsp+1D8h+var_1A8], esi
0x18002f297  jmp     loc_18002F328
0x18002f29c  cmp     eax, 0Bh
0x18002f29f  jnz     loc_18002F328
0x18002f2a5  mov     r8, r14; Size
0x18002f2a8  lea     rdx, [rsp+1D8h+Buf2]; Buf2
0x18002f2b0  lea     rcx, WPD_COMMAND_OBJECT_RESOURCES_SEEK; Buf1
0x18002f2b7  call    memcmp_0
0x18002f2bc  test    eax, eax
0x18002f2be  jnz     short loc_18002F328
0x18002f2c0  mov     [rsp+1D8h+var_160], rdi
0x18002f2c5  mov     rcx, [rsp+1D8h+var_150]
0x18002f2cd  mov     rax, [rcx]
0x18002f2d0  lea     r8, [rsp+1D8h+var_160]
0x18002f2d5  lea     rdx, WPD_COMMAND_OBJECT_RESOURCES_SEEK
0x18002f2dc  mov     rax, [rax+20h]
0x18002f2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2e5  test    eax, eax
0x18002f2e7  js      short loc_18002F31E
0x18002f2e9  mov     [rsp+1D8h+var_1A0], edi
0x18002f2ed  mov     rcx, [rsp+1D8h+var_160]
0x18002f2f2  mov     rax, [rcx]
0x18002f2f5  lea     r8, [rsp+1D8h+var_1A0]
0x18002f2fa  lea     rdx, WPD_OPTION_OBJECT_RESOURCES_SEEK_ON_READ_SUPPORTED
0x18002f301  mov     rax, [rax+0C0h]
0x18002f308  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
