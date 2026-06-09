# CContentFolder::_CreateContentItem(int,IPortableDeviceValues *,ushort const *,IPortableDevice *,IPortableDeviceKeyCollection *,IPortableDeviceValues *,CONTENTITEM * *)

- ea: `0x18000ff40`
- end: `0x1800116a8`
- name: `?_CreateContentItem@CContentFolder@@AEAAJHPEAUIPortableDeviceValues@@PEBGPEAUIPortableDevice@@PEAUIPortableDeviceKeyCollection@@0PEAPEFAUCONTENTITEM@@@Z`
- size: `5992`
- prototype: `__int64 __usercall@<rax>(CContentFolder *__hidden this@<rcx>, int@<edx>, struct IPortableDeviceValues *@<r8>, const unsigned __int16 *@<r9>, struct IPortableDevice *, struct IPortableDeviceKeyCollection *, struct IPortableDeviceValues *, struct CONTENTITEM **)`
- caller_count: `3`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ef50`
- `0x180046d3c`
- `0x180046fc0`

## callees

- `0x180004110`
- `0x18000ff40`
- `0x1800116b0`
- `0x180014778`
- `0x180014b60`
- `0x18001a5b0`
- `0x1800202b0`
- `0x1800285c8`
- `0x180028978`
- `0x18002ab58`
- `0x18002e738`
- `0x18002e9f0`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180039d74`
- `0x180041ab0`
- `0x18006d490`
- `0x18006ef64`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x180010404`
- `KERNEL32!SystemTimeToFileTime` at `0x180010404`
- `KERNEL32!TzSpecificLocalTimeToSystemTime` at `0x1800103f2`
- `KERNEL32!TzSpecificLocalTimeToSystemTime` at `0x1800103f2`
- `KERNEL32!QueryPerformanceCounter` at `0x1800101ea`
- `KERNEL32!QueryPerformanceCounter` at `0x180010f17`
- `KERNEL32!QueryPerformanceCounter` at `0x1800110af`
- `KERNEL32!QueryPerformanceCounter` at `0x1800110dc`
- `KERNEL32!QueryPerformanceCounter` at `0x1800101ea`
- `KERNEL32!QueryPerformanceCounter` at `0x180010f17`
- `KERNEL32!QueryPerformanceCounter` at `0x1800110af`
- `KERNEL32!QueryPerformanceCounter` at `0x1800110dc`
- `KERNEL32!QueryPerformanceFrequency` at `0x180010f2a`
- `KERNEL32!QueryPerformanceFrequency` at `0x180010f2a`
- `KERNEL32!GetCurrentThreadId` at `0x180011039`
- `KERNEL32!GetCurrentThreadId` at `0x180011039`
- `SHLWAPI!PathRemoveExtensionW` at `0x180010ec9`
- `SHLWAPI!PathRemoveExtensionW` at `0x180010ec9`
- `USER32!LoadStringW` at `0x180010a7a`
- `USER32!LoadStringW` at `0x180010a7a`
- `ole32!CoTaskMemFree` at `0x1800115c9`
- `ole32!CoTaskMemFree` at `0x1800115d7`
- `ole32!CoTaskMemFree` at `0x1800115e9`
- `ole32!CoTaskMemFree` at `0x1800115f7`
- `ole32!CoTaskMemFree` at `0x1800115c9`
- `ole32!CoTaskMemFree` at `0x1800115d7`
- `ole32!CoTaskMemFree` at `0x1800115e9`
- `ole32!CoTaskMemFree` at `0x1800115f7`
- `ole32!PropVariantClear` at `0x180010327`
- `ole32!PropVariantClear` at `0x18001038e`
- `ole32!PropVariantClear` at `0x180010416`
- `ole32!PropVariantClear` at `0x1800115b7`
- `ole32!PropVariantClear` at `0x180010327`
- `ole32!PropVariantClear` at `0x18001038e`
- `ole32!PropVariantClear` at `0x180010416`
- `ole32!PropVariantClear` at `0x1800115b7`
- `ole32!CoCreateInstance` at `0x18001111a`
- `ole32!CoCreateInstance` at `0x18001111a`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800103db`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800103db`
- `SHELL32!__imp_ILFree` at `0x180011402`
- `SHELL32!__imp_ILFree` at `0x180011402`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CContentFolder::_CreateContentItem(
        CContentFolder *this,
        int a2,
        struct IPortableDeviceValues *a3,
        unsigned __int16 *a4,
        struct IPortableDevice *a5,
        struct IPortableDeviceKeyCollection *a6,
        struct IPortableDeviceValues *a7,
        struct CONTENTITEM **a8)
{
  CBaseFolder *v9; // r13
  unsigned int v10; // r15d
  unsigned __int16 *v11; // r14
  GUID v12; // xmm7
  struct _FILETIME v13; // rsi
  struct _FILETIME v14; // rdi
  int v15; // r13d
  unsigned int v16; // ebx
  unsigned __int64 v17; // rax
  const struct _tagpropertykey *v18; // r8
  int v19; // r15d
  bool v20; // sf
  void *v21; // rax
  __int64 v22; // rbx
  int v23; // r14d
  PVOID *v24; // rax
  __int64 v25; // rdx
  int v26; // eax
  unsigned __int16 *v27; // rcx
  HRESULT v28; // eax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  void *v32; // rcx
  unsigned __int16 v33; // bx
  int v34; // eax
  unsigned int i; // r14d
  const unsigned __int16 *v36; // rax
  PVOID *v37; // rax
  signed int LowPart; // ecx
  signed int v39; // r14d
  double v40; // xmm1_8
  char v41; // bl
  char v42; // r14
  unsigned __int16 *v43; // rcx
  const unsigned __int16 *CommandName; // rax
  __int64 v45; // rcx
  char v46; // r8
  char v47; // r10
  __int16 v48; // r8
  __int16 v49; // dx
  int v50; // eax
  unsigned __int16 v51; // dx
  char *v52; // rax
  __int16 v53; // si
  __int64 v54; // rdx
  unsigned __int64 v55; // r15
  unsigned __int64 v56; // r13
  unsigned __int16 *v57; // r10
  LPVOID v58; // rdi
  unsigned __int16 *v59; // r10
  unsigned __int16 *v60; // rbx
  unsigned __int16 *v61; // r10
  unsigned __int16 *v62; // r15
  int v63; // eax
  __int64 v64; // rsi
  PVOID *v65; // rcx
  unsigned __int64 *ppv; // [rsp+28h] [rbp-E0h]
  __int64 v68; // [rsp+30h] [rbp-D8h]
  int v69; // [rsp+50h] [rbp-B8h]
  int v70; // [rsp+60h] [rbp-A8h]
  int v71; // [rsp+78h] [rbp-90h]
  unsigned int v72; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v73; // [rsp+80h] [rbp-88h]
  unsigned __int16 *v74; // [rsp+88h] [rbp-80h]
  int v75; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int16 *v76; // [rsp+98h] [rbp-70h] BYREF
  int v77; // [rsp+A0h] [rbp-68h]
  int v78; // [rsp+A4h] [rbp-64h]
  __int64 v79; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-58h] BYREF
  int v81; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v82; // [rsp+BCh] [rbp-4Ch] BYREF
  void *v83; // [rsp+C0h] [rbp-48h] BYREF
  unsigned int v84; // [rsp+C8h] [rbp-40h] BYREF
  int v85; // [rsp+CCh] [rbp-3Ch] BYREF
  unsigned int v86; // [rsp+D0h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-30h]
  struct _FILETIME FileTime; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int16 *v89; // [rsp+E8h] [rbp-20h]
  LPVOID v90; // [rsp+F0h] [rbp-18h]
  LPVOID v91; // [rsp+F8h] [rbp-10h] BYREF
  PROPVARIANT pvar; // [rsp+100h] [rbp-8h] BYREF
  char v93[8]; // [rsp+118h] [rbp+10h] BYREF
  char v94[8]; // [rsp+120h] [rbp+18h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+128h] [rbp+20h] BYREF
  __int128 v96; // [rsp+138h] [rbp+30h]
  LARGE_INTEGER Frequency; // [rsp+148h] [rbp+40h] BYREF
  char v98; // [rsp+150h] [rbp+48h]
  struct IPortableDevice *v99; // [rsp+158h] [rbp+50h]
  __int64 v100; // [rsp+160h] [rbp+58h] BYREF
  struct CONTENTITEM **v101; // [rsp+168h] [rbp+60h]
  struct _SYSTEMTIME Buf2; // [rsp+170h] [rbp+68h] BYREF
  int v103; // [rsp+180h] [rbp+78h]
  GUID Buf1; // [rsp+188h] [rbp+80h] BYREF
  int v105; // [rsp+198h] [rbp+90h]
  struct _SYSTEMTIME SystemTime; // [rsp+1A8h] [rbp+A0h] BYREF
  struct _GUID v107; // [rsp+1B8h] [rbp+B0h] BYREF
  struct _GUID v108; // [rsp+1C8h] [rbp+C0h] BYREF
  WCHAR Buffer[264]; // [rsp+1D8h] [rbp+D0h] BYREF
  unsigned __int16 v110[264]; // [rsp+3E8h] [rbp+2E0h] BYREF

  v89 = a4;
  v77 = a2;
  v9 = this;
  *(_QWORD *)&SystemTime.wYear = this;
  v99 = a5;
  v101 = a8;
  v10 = 0;
  *(_QWORD *)v93 = 0;
  *(_QWORD *)v94 = 0;
  v98 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v96 = 0;
  Frequency.QuadPart = 0;
  pv = 0;
  v11 = 0;
  v90 = 0;
  v74 = 0;
  v12 = WPD_CONTENT_TYPE_UNSPECIFIED;
  Buf1 = WPD_CONTENT_TYPE_UNSPECIFIED;
  v107 = WPD_OBJECT_FORMAT_UNSPECIFIED;
  v71 = 0;
  v13 = 0;
  v14 = 0;
  v83 = 0;
  v100 = 0;
  v81 = 0;
  v86 = 0;
  v85 = 0;
  v108 = 0;
  v75 = 0;
  memset(&pvar, 0, sizeof(pvar));
  FileTime = 0;
  v91 = 0;
  if ( !a7
    || ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a7->lpVtbl->GetBoolValue)(
         a7,
         &WPD_RESOURCE_ATTRIBUTE_CAN_READ,
         &v75) >= 0
    && v75 )
  {
    v10 = 8;
  }
  v84 = 0;
  if ( a6 )
  {
    if ( ((int (__fastcall *)(struct IPortableDeviceKeyCollection *, unsigned int *))a6->lpVtbl->GetCount)(a6, &v84) >= 0 )
    {
      v11 = 0;
      if ( v84 )
      {
        v15 = 0;
        do
        {
          Buf2 = 0;
          v103 = 0;
          if ( ((int (__fastcall *)(struct IPortableDeviceKeyCollection *, _QWORD, struct _SYSTEMTIME *))a6->lpVtbl->GetAt)(
                 a6,
                 (unsigned int)v11,
                 &Buf2) >= 0
            && !v103 )
          {
            if ( !memcmp_0(&WPD_RESOURCE_DEFAULT, &Buf2, 0x10u) )
            {
              v15 |= 0x200000u;
              v10 |= 0x20u;
            }
            else if ( !memcmp_0(&WPD_RESOURCE_CONTACT_PHOTO, &Buf2, 0x10u) )
            {
              v15 |= 0x10000u;
            }
            else if ( !memcmp_0(&WPD_RESOURCE_THUMBNAIL, &Buf2, 0x10u) )
            {
              v15 |= 0x20000u;
            }
            else if ( !memcmp_0(&WPD_RESOURCE_ICON, &Buf2, 0x10u) )
            {
              v15 |= 0x40000u;
            }
            else if ( !memcmp_0(&WPD_RESOURCE_AUDIO_CLIP, &Buf2, 0x10u) )
            {
              v15 |= 0x80000u;
            }
            else if ( !memcmp_0(&WPD_RESOURCE_ALBUM_ART, &Buf2, 0x10u) )
            {
              v15 |= 0x100000u;
            }
          }
          LODWORD(v11) = (_DWORD)v11 + 1;
        }
        while ( (unsigned int)v11 < v84 );
        v71 = v15;
        v9 = *(CBaseFolder **)&SystemTime.wYear;
        v11 = 0;
      }
    }
  }
  if ( !v98 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    *(_QWORD *)v93 = 19;
    *(_QWORD *)v94 = 0;
    v96 = 0;
    v98 = 1;
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, struct _GUID *))a3->lpVtbl->GetGuidValue)(
         a3,
         &WPD_OBJECT_CONTENT_TYPE,
         &v108) >= 0
    && ((v12 = v108, Buf1 = v108, !memcmp_0(&Buf1, &WPD_CONTENT_TYPE_FOLDER, 0x10u))
     || !memcmp_0(&Buf1, &WPD_CONTENT_TYPE_FUNCTIONAL_OBJECT, 0x10u)) )
  {
    v10 |= 0x22u;
    if ( !memcmp_0(&Buf1, &WPD_CONTENT_TYPE_FUNCTIONAL_OBJECT, 0x10u) )
      v71 |= 1u;
    v16 = v77;
    if ( !v77 )
    {
      v80 = 0;
      if ( ((unsigned int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64 *))a3->lpVtbl->GetIPortableDevicePropVariantCollectionValue)(
             a3,
             &WPD_FOLDER_CONTENT_TYPES_ALLOWED,
             &v80) )
      {
        v10 |= 1u;
      }
      else
      {
        do
        {
          if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v80 + 32LL))(v80, v16, &pvar) )
            break;
          if ( pvar.vt == 72 )
          {
            v17 = *(_QWORD *)&WPD_CONTENT_TYPE_FOLDER.Data1 - (unsigned __int64)*pvar.pbstrVal;
            if ( *(BSTR *)&WPD_CONTENT_TYPE_FOLDER.Data1 == *pvar.pbstrVal )
              v17 = *(_QWORD *)WPD_CONTENT_TYPE_FOLDER.Data4 - *(_QWORD *)(pvar.hVal.QuadPart + 8);
            if ( !v17 )
              v10 |= 1u;
            PropVariantClear(&pvar);
          }
          ++v16;
        }
        while ( (v10 & 1) == 0 );
        v16 = v77;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
    }
  }
  else
  {
    v16 = v77;
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, PROPVARIANT *))a3->lpVtbl->GetValue)(
         a3,
         &WPD_OBJECT_DATE_CREATED,
         &pvar) >= 0 )
  {
    if ( pvar.vt == 7 && ConvertVariantLocalTimeToUTCFileTime(&pvar.dblVal, &FileTime) >= 0 )
      v13 = FileTime;
    PropVariantClear(&pvar);
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, PROPVARIANT *))a3->lpVtbl->GetValue)(
         a3,
         &WPD_OBJECT_DATE_MODIFIED,
         &pvar) >= 0 )
  {
    if ( pvar.vt == 7 )
    {
      Buf2 = 0;
      SystemTime = 0;
      if ( VariantTimeToSystemTime(pvar.dblVal, &SystemTime) )
      {
        if ( TzSpecificLocalTimeToSystemTime(0, &SystemTime, &Buf2) && SystemTimeToFileTime(&Buf2, &FileTime) )
          v14 = FileTime;
      }
    }
    PropVariantClear(&pvar);
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, struct _GUID *))a3->lpVtbl->GetGuidValue)(
         a3,
         &WPD_OBJECT_FORMAT,
         &v108) >= 0 )
  {
    v107 = v108;
    if ( !memcmp_0(&WPD_OBJECT_FORMAT_PROPERTIES_ONLY, &v107, 0x10u) )
    {
      if ( !memcmp_0(&WPD_CONTENT_TYPE_PLAYLIST, &Buf1, 0x10u) )
      {
        v71 |= 0x100u;
      }
      else if ( !memcmp_0(&WPD_CONTENT_TYPE_MIXED_CONTENT_ALBUM, &Buf1, 0x10u)
             || !memcmp_0(&WPD_CONTENT_TYPE_AUDIO_ALBUM, &Buf1, 0x10u)
             || !memcmp_0(&WPD_CONTENT_TYPE_IMAGE_ALBUM, &Buf1, 0x10u)
             || !memcmp_0(&WPD_CONTENT_TYPE_VIDEO_ALBUM, &Buf1, 0x10u) )
      {
        v71 |= 0x200u;
      }
    }
    else if ( !(unsigned int)IsPropertySupportedByFormat(v99, &v107, v18) )
    {
      v71 |= 8u;
    }
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a3->lpVtbl->GetBoolValue)(
         a3,
         &WPD_OBJECT_GENERATE_THUMBNAIL_FROM_RESOURCE,
         &v75) >= 0
    && v75 )
  {
    v71 |= 0x1000u;
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a3->lpVtbl->GetBoolValue)(
         a3,
         &WPD_OBJECT_IS_DRM_PROTECTED,
         &v75) >= 0
    && v75 )
  {
    v71 |= 4u;
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a3->lpVtbl->GetBoolValue)(
         a3,
         &WPD_OBJECT_ISHIDDEN,
         &v75) >= 0
    && v75 )
  {
    v10 |= 0x100u;
  }
  if ( !(*(unsigned int (__fastcall **)(CBaseFolder *, _QWORD, const PROPERTYKEY *))(*(_QWORD *)v9 + 72LL))(
          v9,
          *((_QWORD *)v9 + 8),
          &WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS) )
    goto LABEL_83;
  v19 = (2 * (v10 & 0x20 | 8)) | v10;
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a3->lpVtbl->GetBoolValue)(
         a3,
         &WPD_OBJECT_CAN_DELETE,
         &v75) >= 0
    && !v75 )
  {
    v10 = v19 & 0xFFFFFFBF;
LABEL_83:
    v19 = v10 | 0x200;
  }
  v78 = v19;
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a3->lpVtbl->GetBoolValue)(
         a3,
         &WPD_OBJECT_ISSYSTEM,
         &v75) >= 0
    && v75 )
  {
    v19 |= 0x400u;
    v78 = v19;
  }
  v20 = ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, void **))a3->lpVtbl->GetStringValue)(
          a3,
          &WPD_OBJECT_NAME,
          &v83) < 0;
  v21 = pv;
  if ( !v20 )
    v21 = v83;
  pv = v21;
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, void **))a3->lpVtbl->GetStringValue)(
         a3,
         &WPD_OBJECT_ORIGINAL_FILE_NAME,
         &v83) >= 0 )
    v11 = (unsigned __int16 *)v83;
  v73 = v11;
  if ( !*((_DWORD *)v9 + 36) && !v16 )
  {
    v22 = 0;
    *(_QWORD *)&Buf2.wYear = 0;
    v76 = 0;
    v80 = 0;
    v79 = 0;
    if ( !v99 )
    {
      v23 = -2147024809;
LABEL_106:
      v24 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_107;
    }
    v22 = 0;
    *(_QWORD *)&Buf2.wYear = 0;
    v23 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v99->lpVtbl->Content)(v99, &v79);
    if ( v23 >= 0 )
    {
      if ( !v79 )
      {
        v23 = -2147418113;
        goto LABEL_106;
      }
      v23 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 32LL))(v79, &v80);
      if ( v23 >= 0 )
      {
        v22 = v80;
        *(_QWORD *)&Buf2.wYear = v80;
        goto LABEL_111;
      }
      v24 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_112;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_107:
        if ( v24 == &WPP_GLOBAL_Control || (*((_BYTE *)v24 + 28) & 2) == 0 )
        {
LABEL_112:
          if ( v79 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
            v24 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v23 < 0 )
          {
            if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 2) != 0 )
              WPP_SF_d(v24[2], 204, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v23);
            if ( v76 )
              (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v76 + 16LL))(v76);
            if ( v22 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            goto LABEL_291;
          }
          if ( v73 )
          {
            if ( (*(int (__fastcall **)(__int64, unsigned __int16 *, const PROPERTYKEY *, unsigned __int16 **))(*(_QWORD *)v22 + 32LL))(
                   v22,
                   v89,
                   &WPD_OBJECT_ORIGINAL_FILE_NAME,
                   &v76) < 0
              || (*(int (__fastcall **)(unsigned __int16 *, const PROPERTYKEY *, int *))(*(_QWORD *)v76 + 192LL))(
                   v76,
                   &WPD_PROPERTY_ATTRIBUTE_CAN_WRITE,
                   &v75) < 0
              || !v75 )
            {
              goto LABEL_133;
            }
          }
          else if ( !pv
                 || (*(int (__fastcall **)(__int64, unsigned __int16 *, const PROPERTYKEY *, unsigned __int16 **))(*(_QWORD *)v22 + 32LL))(
                      v22,
                      v89,
                      &WPD_OBJECT_NAME,
                      &v76) < 0
                 || (*(int (__fastcall **)(unsigned __int16 *, const PROPERTYKEY *, int *))(*(_QWORD *)v76 + 192LL))(
                      v76,
                      &WPD_PROPERTY_ATTRIBUTE_CAN_WRITE,
                      &v75) < 0
                 || !v75 )
          {
            goto LABEL_133;
          }
          v19 |= 0x80u;
          v78 = v19;
LABEL_133:
          if ( v76 )
            (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v76 + 16LL))(v76);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          goto LABEL_137;
        }
        WPP_SF_d(v24[2], 17, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)v23);
LABEL_111:
        v24 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_112;
      }
      v25 = 16;
    }
    else
    {
      v24 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_112;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_107;
      v25 = 15;
    }
    WPP_SF_d(v24[2], v25, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)v23);
    goto LABEL_106;
  }
LABEL_137:
  *(_QWORD *)&SystemTime.wYear = 0;
  v26 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, void **))a3->lpVtbl->GetStringValue)(
          a3,
          &WPD_OBJECT_PERSISTENT_UNIQUE_ID,
          &v83);
  v27 = 0;
  if ( v26 >= 0 )
    v27 = (unsigned __int16 *)v83;
  v74 = v27;
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64 *))a3->lpVtbl->GetUnsignedLargeIntegerValue)(
         a3,
         &WPD_OBJECT_SIZE,
         &v100) >= 0 )
  {
    if ( (v19 & 2) != 0 )
    {
      v28 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *))a3->lpVtbl->RemoveValue)(
              a3,
              &WPD_OBJECT_SIZE);
      v23 = v28;
      if ( v28 < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_291;
        v30 = 205;
        goto LABEL_145;
      }
    }
    else
    {
      *(_QWORD *)&SystemTime.wYear = v100;
    }
  }
  v31 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, void **))a3->lpVtbl->GetStringValue)(
          a3,
          &WPD_MEDIA_TITLE,
          &v83);
  v32 = v90;
  if ( v31 >= 0 )
    v32 = v83;
  v90 = v32;
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, unsigned int *))a3->lpVtbl->GetUnsignedIntegerValue)(
         a3,
         &WPD_MEDIA_WIDTH,
         &v86) >= 0
    && ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a3->lpVtbl->GetUnsignedIntegerValue)(
         a3,
         &WPD_MEDIA_HEIGHT,
         &v85) >= 0
    && v86
    && v85 )
  {
    LoadStringW(g_hInst, 0x10Du, Buffer, 260);
    v28 = StringCchPrintfW(v110, 0x104u, Buffer, v86, v85);
    v23 = v28;
    if ( v28 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_291;
      v30 = 206;
      goto LABEL_145;
    }
    v28 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, unsigned __int16 *))a3->lpVtbl->SetStringValue)(
            a3,
            &PKEY_Image_Dimensions,
            v110);
    v23 = v28;
    if ( v28 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_291;
      v30 = 207;
      goto LABEL_145;
    }
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, __int64 *, int *))a3->lpVtbl->GetUnsignedIntegerValue)(
         a3,
         WPD_OBJECT_MTP_PROTECTIONSTATUS,
         &v81) >= 0
    && v81 == 32771 )
  {
    v19 &= ~8u;
    v78 = v19;
  }
  if ( ((int (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, int *))a3->lpVtbl->GetUnsignedIntegerValue)(
         a3,
         &WPD_MUSIC_TRACK,
         &v81) >= 0
    && !v81 )
  {
    v28 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *))a3->lpVtbl->RemoveValue)(
            a3,
            &WPD_MUSIC_TRACK);
    v23 = v28;
    if ( v28 < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_291;
      v30 = 208;
      goto LABEL_145;
    }
  }
  if ( (v19 & 0x400) != 0 && (v19 & 2) != 0 )
  {
    v19 &= ~0x80u;
    v78 = v19;
  }
  if ( memcmp_0(&WPD_CONTENT_TYPE_UNSPECIFIED, &Buf1, 0x10u)
    && memcmp_0(&WPD_CONTENT_TYPE_GENERIC_FILE, &Buf1, 0x10u)
    && memcmp_0(&WPD_OBJECT_FORMAT_UNSPECIFIED, &v107, 0x10u) )
  {
    v71 |= 2u;
  }
  v33 = 1;
  if ( (v71 & 0x300) != 0 && (v19 & 0x100) == 0 )
  {
    v80 = 0;
    v76 = 0;
    v34 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))v99->lpVtbl->Capabilities)(v99, &v80);
    v23 = v34;
    if ( v34 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          209,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)v34);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v76);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
      goto LABEL_291;
    }
    if ( (*(int (__fastcall **)(__int64, struct _GUID *, unsigned __int16 **))(*(_QWORD *)v80 + 72LL))(v80, &v107, &v76) >= 0 )
    {
      LODWORD(v79) = 0;
      if ( (*(int (__fastcall **)(unsigned __int16 *, __int64 *))(*(_QWORD *)v76 + 24LL))(v76, &v79) >= 0 )
      {
        for ( i = 0; i < (unsigned int)v79; ++i )
        {
          Buf1 = 0;
          v105 = 0;
          if ( (*(int (__fastcall **)(unsigned __int16 *, _QWORD, GUID *))(*(_QWORD *)v76 + 32LL))(v76, i, &Buf1) >= 0
            && v105 == 9
            && !memcmp_0(&WPD_OBJECT_ISHIDDEN, &Buf1, 0x10u) )
          {
            goto LABEL_193;
          }
        }
      }
    }
    ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, __int64))a3->lpVtbl->SetBoolValue)(
      a3,
      &WPD_OBJECT_ISHIDDEN,
      1);
    v19 |= 0x100u;
    v78 = v19;
LABEL_193:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v76);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v80);
  }
  v28 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *))a3->lpVtbl->RemoveValue)(
          a3,
          &WPD_OBJECT_PARENT_ID);
  v23 = v28;
  if ( v28 < 0 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_291;
    v30 = 210;
    goto LABEL_145;
  }
  v28 = ((__int64 (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *))a3->lpVtbl->RemoveValue)(
          a3,
          &WPD_OBJECT_REFERENCES);
  v23 = v28;
  if ( v28 < 0 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_291;
    v30 = 211;
    goto LABEL_145;
  }
  ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *))a3->lpVtbl->RemoveValue)(
    a3,
    &WPD_OBJECT_KEYWORDS);
  if ( !*((_DWORD *)v9 + 36) && !v77 && (v19 & 2) == 0 && !v90 )
  {
    memset_0(Buffer, 0, 0x208u);
    v36 = (const unsigned __int16 *)pv;
    if ( pv || (v36 = v73) != 0 )
      StringCchCopyW(Buffer, 0x104u, v36);
    if ( Buffer[0] )
    {
      PathRemoveExtensionW(Buffer);
      ((void (__fastcall *)(struct IPortableDeviceValues *, const PROPERTYKEY *, WCHAR *))a3->lpVtbl->SetStringValue)(
        a3,
        &WPD_MEDIA_TITLE,
        Buffer);
    }
  }
  *(_QWORD *)&Buf2.wYear = 0;
  if ( *(_DWORD *)v93 != 19 )
    goto LABEL_228;
  v37 = (PVOID *)WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
    goto LABEL_229;
  QueryPerformanceCounter((LARGE_INTEGER *)&Buf2);
  LowPart = Frequency.LowPart;
  if ( !Frequency.QuadPart )
  {
    if ( !QueryPerformanceFrequency(&Frequency) || (LowPart = Frequency.LowPart, !Frequency.QuadPart) )
    {
LABEL_228:
      v37 = (PVOID *)WPP_GLOBAL_Control;
LABEL_229:
      if ( v98 )
        goto LABEL_232;
      goto LABEL_230;
    }
  }
  v39 = *(_DWORD *)&Buf2.wYear - PerformanceCount[0].LowPart;
  switch ( *(_DWORD *)v93 )
  {
    case 1:
      v37 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids);
        LowPart = Frequency.LowPart;
        goto LABEL_220;
      }
      break;
    case 2:
    case 4:
    case 5:
    case 6:
    case 7:
    case 8:
    case 9:
    case 0xA:
    case 0xB:
LABEL_220:
      v37 = (PVOID *)WPP_GLOBAL_Control;
      break;
    default:
      v37 = (PVOID *)WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        goto LABEL_229;
      break;
  }
  if ( v37 != &WPP_GLOBAL_Control && (*((_DWORD *)v37 + 7) & 0x800) != 0 )
  {
    v40 = (double)v39 / (double)LowPart * 1000.0;
    v41 = v93[4];
    v42 = v94[0];
    GetCurrentThreadId();
    v43 = v89;
    if ( !v89 )
      v43 = L"N/A";
    CommandName = CPerfTraceHelper::GetCommandName((CPerfTraceHelper *)v43, *(unsigned int *)v93);
    WPP_SF_dDSdiddddDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v46,
      (__int64)CommandName,
      v47,
      v42,
      (int)v40,
      v69,
      v41,
      v70,
      0,
      v45);
    v19 = v78;
    v33 = 1;
  }
  QueryPerformanceCounter(&PerformanceCount[1]);
  v98 = 0;
  v37 = (PVOID *)WPP_GLOBAL_Control;
LABEL_230:
  if ( (*((_DWORD *)v37 + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    *(_QWORD *)v93 = 20;
    *(_QWORD *)v94 = 0;
    v96 = 0;
    v98 = 1;
  }
LABEL_232:
  v28 = CoCreateInstance(&CLSID_WpdSerializer, 0, 1u, &GUID_b32f4002_bb27_45ff_af4f_06631c1e8dad, &v91);
  v23 = v28;
  if ( v28 < 0 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_291;
    v30 = 212;
    goto LABEL_145;
  }
  v82 = 0;
  v28 = (*(__int64 (__fastcall **)(LPVOID, struct IPortableDeviceValues *, unsigned int *))(*(_QWORD *)v91 + 48LL))(
          v91,
          a3,
          &v82);
  v23 = v28;
  if ( v28 < 0 )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_291;
    v30 = 213;
LABEL_145:
    WPP_SF_d(v29[2], v30, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v28);
LABEL_291:
    v60 = v73;
    v62 = v74;
    goto LABEL_292;
  }
  v48 = 1;
  LOWORD(v79) = 1;
  v49 = 1;
  LOWORD(v77) = 1;
  v76 = 0;
  if ( pv )
  {
    if ( (int)StringCchLengthW((const unsigned __int16 *)pv, 0x104u, (unsigned __int64 *)&v76) < 0 )
    {
      v48 = 1;
      v49 = 1;
    }
    else
    {
      v33 = (_WORD)v76 + 1;
      v48 = v79;
      v49 = v79;
    }
  }
  if ( v73 )
  {
    if ( (int)StringCchLengthW(v73, 0x104u, (unsigned __int64 *)&v76) < 0 )
    {
      v48 = v79;
      v49 = v79;
    }
    else
    {
      v48 = (_WORD)v76 + 1;
      LOWORD(v79) = (_WORD)v76 + 1;
      v49 = v77;
    }
  }
  if ( v74 )
  {
    v50 = StringCchLengthW(v74, 0x104u, (unsigned __int64 *)&v76);
    v48 = v79;
    if ( v50 < 0 )
    {
      v49 = v77;
    }
    else
    {
      v49 = (_WORD)v76 + 1;
      LOWORD(v77) = (_WORD)v76 + 1;
    }
  }
  LODWORD(v76) = v82;
  if ( v82 > 0xFFFF )
  {
    v23 = -2147024362;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v82);
    goto LABEL_291;
  }
  v51 = 2 * (v33 + v48 + v49 + 35);
  LOWORD(v78) = v82 + v51;
  if ( (unsigned __int16)(v82 + v51) < v51 )
  {
    v23 = -2147024362;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LODWORD(v68) = -2147024362;
      LODWORD(ppv) = (unsigned __int16)v82;
      WPP_SF_ddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        215,
        WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
        v51,
        ppv,
        v68);
    }
    goto LABEL_291;
  }
  v52 = (char *)CBaseFolder::_Alloc(v9, (unsigned __int16)v82 + v51);
  *(_QWORD *)&Buf2.wYear = v52;
  if ( !v52 )
  {
    v23 = -2147024882;
    goto LABEL_291;
  }
  v23 = 0;
  *(_DWORD *)(v52 + 6) = 119087110;
  *(_DWORD *)(v52 + 10) = v19;
  *(_DWORD *)(v52 + 14) = v71;
  *(_QWORD *)(v52 + 18) = *(_QWORD *)&SystemTime.wYear;
  *(struct _FILETIME *)(v52 + 26) = v13;
  *(struct _FILETIME *)(v52 + 34) = v14;
  *(GUID *)(v52 + 42) = v12;
  v53 = (__int16)v76;
  v54 = (unsigned __int16)v76;
  v72 = (unsigned __int16)v76;
  *(_DWORD *)(v52 + 58) = (unsigned __int16)v76;
  *(_DWORD *)(v52 + 62) = v33;
  v55 = (unsigned __int16)v79;
  *(_DWORD *)(v52 + 66) = (unsigned __int16)v79;
  v56 = (unsigned __int16)v77;
  *(_DWORD *)(v52 + 70) = (unsigned __int16)v77;
  v57 = (unsigned __int16 *)(v52 + 74);
  v76 = (unsigned __int16 *)(v52 + 74);
  v58 = pv;
  if ( pv )
  {
    StringCchCopyExW((unsigned __int16 *)v52 + 37, v33, (const unsigned __int16 *)pv, &v76, ppv, v68);
    v57 = v76;
    v54 = v72;
  }
  v59 = v57 + 1;
  v76 = v59;
  v60 = v73;
  if ( v73 )
  {
    StringCchCopyExW(v59, v55, v73, &v76, ppv, v68);
    v59 = v76;
    v54 = v72;
  }
  v61 = v59 + 1;
  v76 = v61;
  v62 = v74;
  if ( v74 )
  {
    StringCchCopyExW(v61, v56, v74, &v76, ppv, v68);
    v61 = v76;
    v54 = v72;
  }
  if ( v53 )
  {
    v63 = (*(__int64 (__fastcall **)(LPVOID, __int64, struct IPortableDeviceValues *, unsigned __int16 *, unsigned int *))(*(_QWORD *)v91 + 32LL))(
            v91,
            v54,
            a3,
            v61 + 1,
            &v82);
    v23 = v63;
    if ( v63 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          216,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)v63);
      goto LABEL_269;
    }
    if ( v72 != v82 )
    {
      v23 = -2147418113;
LABEL_269:
      ILFree(*(LPITEMIDLIST *)&Buf2.wYear);
      goto LABEL_292;
    }
  }
  CPerfTraceHelper::ProcessPerformanceData((CPerfTraceHelper *)v93, 0x14u, 0, v89);
  v64 = *(_QWORD *)&Buf2.wYear;
  *v101 = *(struct CONTENTITEM **)&Buf2.wYear;
  v65 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v58);
      v65 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v65 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v65 + 28) & 0x40) != 0 )
      {
        WPP_SF_d(v65[2], 218, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, *(unsigned int *)(v64 + 10));
        v65 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v65 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v65 + 28) & 0x40) != 0 )
        {
          WPP_SF_d(v65[2], 219, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, *(unsigned int *)(v64 + 14));
          v65 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v65 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v65 + 28) & 0x40) != 0 )
          {
            WPP_SF_S(v65[2], 220, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, v74);
            v65 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v65 != &WPP_GLOBAL_Control && (*((_BYTE *)v65 + 28) & 0x40) != 0 )
            WPP_SF_d(v65[2], 221, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned __int16)v78);
        }
      }
    }
  }
LABEL_292:
  PropVariantClear(&pvar);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v60 )
    CoTaskMemFree(v60);
  if ( v90 )
    CoTaskMemFree(v90);
  if ( v62 )
    CoTaskMemFree(v62);
  if ( v23 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      222,
      WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      (unsigned int)v23);
  if ( v91 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v91 + 16LL))(v91);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18000ff40  mov     rax, rsp
0x18000ff43  mov     [rax+10h], rbx
0x18000ff47  push    rbp
0x18000ff48  push    rsi
0x18000ff49  push    rdi
0x18000ff4a  push    r12
0x18000ff4c  push    r13
0x18000ff4e  push    r14
0x18000ff50  push    r15
0x18000ff52  lea     rbp, [rax-558h]
0x18000ff59  sub     rsp, 620h
0x18000ff60  movaps  xmmword ptr [rax-48h], xmm6
0x18000ff64  movaps  xmmword ptr [rax-58h], xmm7
0x18000ff68  mov     rax, cs:__security_cookie
0x18000ff6f  xor     rax, rsp
0x18000ff72  mov     [rbp+550h+var_60], rax
0x18000ff79  mov     [rbp+550h+var_570], r9
0x18000ff7d  mov     r12, r8
0x18000ff80  mov     [rbp+550h+var_5B8], edx
0x18000ff83  mov     r13, rcx
0x18000ff86  mov     qword ptr [rbp+550h+SystemTime.wYear], rcx
0x18000ff8d  mov     rax, [rbp+550h+arg_20]
0x18000ff94  mov     [rbp+550h+var_500], rax
0x18000ff98  mov     rbx, [rbp+550h+arg_28]
0x18000ff9f  mov     rcx, [rbp+550h+arg_30]
0x18000ffa6  mov     rax, [rbp+550h+arg_38]
0x18000ffad  mov     [rbp+550h+var_4F0], rax
0x18000ffb1  xor     r15d, r15d
0x18000ffb4  mov     qword ptr [rbp+550h+var_540], r15
0x18000ffb8  mov     qword ptr [rbp+550h+var_538], r15
0x18000ffbc  mov     [rbp+550h+var_508], r15b
0x18000ffc0  xorps   xmm0, xmm0
0x18000ffc3  movdqa  xmmword ptr [rbp+550h+PerformanceCount], xmm0
0x18000ffc8  xorps   xmm1, xmm1
0x18000ffcb  movdqa  [rbp+550h+var_520], xmm1
0x18000ffd0  mov     qword ptr [rbp+550h+Frequency], r15
0x18000ffd4  mov     [rbp+550h+pv], r15
0x18000ffd8  mov     r14d, r15d
0x18000ffdb  mov     [rsp+650h+var_5D8], r15
0x18000ffe0  mov     [rbp+550h+var_568], r15
0x18000ffe4  mov     [rbp+550h+var_5D0], r15
0x18000ffe8  movups  xmm7, xmmword ptr cs:WPD_CONTENT_TYPE_UNSPECIFIED.Data1
0x18000ffef  movaps  [rbp+550h+Buf1], xmm7
0x18000fff6  movups  xmm0, xmmword ptr cs:WPD_OBJECT_FORMAT_UNSPECIFIED.Data1
0x18000fffd  movaps  xmmword ptr [rbp+550h+var_4A0.Data1], xmm0
0x180010004  mov     dword ptr [rsp+650h+var_5E0], r15d
0x180010009  mov     esi, r15d
0x18001000c  mov     edi, r15d
0x18001000f  mov     [rbp+550h+var_598], r15
0x180010013  mov     [rbp+550h+var_4F8], r15
0x180010017  mov     [rbp+550h+var_5A0], r15d
0x18001001b  mov     [rbp+550h+var_588], r15d
0x18001001f  mov     [rbp+550h+var_58C], r15d
0x180010023  xorps   xmm0, xmm0
0x180010026  movups  [rbp+550h+var_490], xmm0
0x18001002d  mov     [rbp+550h+var_5C8], r15d
0x180010031  xor     eax, eax
0x180010033  movups  xmmword ptr [rbp+550h+pvar], xmm1
0x180010037  mov     qword ptr [rbp+550h+pvar+10h], rax
0x18001003b  mov     qword ptr [rbp+550h+FileTime.dwLowDateTime], r15
0x18001003f  mov     [rbp+550h+var_560], r15
0x180010043  test    rcx, rcx
0x180010046  jz      short loc_18001006C
0x180010048  mov     rax, [rcx]
0x18001004b  lea     r8, [rbp+550h+var_5C8]
0x18001004f  lea     rdx, WPD_RESOURCE_ATTRIBUTE_CAN_READ
0x180010056  mov     rax, [rax+0C0h]
0x18001005d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010062  test    eax, eax
0x180010064  js      short loc_180010072
0x180010066  cmp     [rbp+550h+var_5C8], r15d
0x18001006a  jz      short loc_180010072
0x18001006c  mov     r15d, 8
0x180010072  mov     [rbp+550h+var_590], 0
0x180010079  test    rbx, rbx
0x18001007c  jz      loc_1800101D0
0x180010082  mov     rax, [rbx]
0x180010085  lea     rdx, [rbp+550h+var_590]
0x180010089  mov     rcx, rbx
0x18001008c  mov     rax, [rax+18h]
0x180010090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010095  test    eax, eax
0x180010097  js      loc_1800101D0
0x18001009d  xor     r14d, r14d
0x1800100a0  cmp     [rbp+550h+var_590], r14d
0x1800100a4  jbe     loc_1800101D0
0x1800100aa  mov     r13d, r14d
0x1800100ad  nop     dword ptr [rax]
0x1800100b0  xorps   xmm0, xmm0
0x1800100b3  xor     eax, eax
0x1800100b5  movups  [rbp+550h+Buf2], xmm0
0x1800100b9  mov     [rbp+550h+var_4D8], eax
0x1800100bc  mov     rax, [rbx]
0x1800100bf  lea     r8, [rbp+550h+Buf2]
0x1800100c3  mov     edx, r14d
0x1800100c6  mov     rcx, rbx
0x1800100c9  mov     rax, [rax+20h]
0x1800100cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d2  test    eax, eax
0x1800100d4  js      loc_1800101B2
0x1800100da  cmp     [rbp+550h+var_4D8], 0
0x1800100de  jnz     loc_1800101B2
0x1800100e4  mov     r8d, 10h; Size
0x1800100ea  lea     rdx, [rbp+550h+Buf2]; Buf2
0x1800100ee  lea     rcx, WPD_RESOURCE_DEFAULT; Buf1
0x1800100f5  call    memcmp_0
0x1800100fa  test    eax, eax
0x1800100fc  jnz     short loc_18001010C
0x1800100fe  bts     r13d, 15h
0x180010103  or      r15d, 20h
0x180010107  jmp     loc_1800101B2
0x18001010c  mov     r8d, 10h; Size
0x180010112  lea     rdx, [rbp+550h+Buf2]; Buf2
0x180010116  lea     rcx, WPD_RESOURCE_CONTACT_PHOTO; Buf1
0x18001011d  call    memcmp_0
0x180010122  test    eax, eax
0x180010124  jnz     short loc_180010130
0x180010126  bts     r13d, 10h
0x18001012b  jmp     loc_1800101B2
0x180010130  mov     r8d, 10h; Size
0x180010136  lea     rdx, [rbp+550h+Buf2]; Buf2
0x18001013a  lea     rcx, WPD_RESOURCE_THUMBNAIL; Buf1
0x180010141  call    memcmp_0
0x180010146  test    eax, eax
0x180010148  jnz     short loc_180010151
0x18001014a  bts     r13d, 11h
0x18001014f  jmp     short loc_1800101B2
0x180010151  mov     r8d, 10h; Size
0x180010157  lea     rdx, [rbp+550h+Buf2]; Buf2
0x18001015b  lea     rcx, WPD_RESOURCE_ICON; Buf1
0x180010162  call    memcmp_0
0x180010167  test    eax, eax
0x180010169  jnz     short loc_180010172
0x18001016b  bts     r13d, 12h
0x180010170  jmp     short loc_1800101B2
0x180010172  mov     r8d, 10h; Size
0x180010178  lea     rdx, [rbp+550h+Buf2]; Buf2
0x18001017c  lea     rcx, WPD_RESOURCE_AUDIO_CLIP; Buf1
0x180010183  call    memcmp_0
0x180010188  test    eax, eax
0x18001018a  jnz     short loc_180010193
0x18001018c  bts     r13d, 13h
0x180010191  jmp     short loc_1800101B2
0x180010193  mov     r8d, 10h; Size
0x180010199  lea     rdx, [rbp+550h+Buf2]; Buf2
0x18001019d  lea     rcx, WPD_RESOURCE_ALBUM_ART; Buf1
0x1800101a4  call    memcmp_0
0x1800101a9  test    eax, eax
0x1800101ab  jnz     short loc_1800101B2
0x1800101ad  bts     r13d, 14h
0x1800101b2  inc     r14d
0x1800101b5  cmp     r14d, [rbp+550h+var_590]
0x1800101b9  jb      loc_1800100B0
0x1800101bf  mov     dword ptr [rsp+650h+var_5E0], r13d
0x1800101c4  mov     r13, qword ptr [rbp+550h+SystemTime.wYear]
0x1800101cb  mov     r14, [rsp+650h+var_5D8]
0x1800101d0  cmp     [rbp+550h+var_508], 0
0x1800101d4  jnz     short loc_18001020A
0x1800101d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800101dd  test    dword ptr [rax+1Ch], 800h
0x1800101e4  jz      short loc_18001020A
0x1800101e6  lea     rcx, [rbp+550h+PerformanceCount]; lpPerformanceCount
0x1800101ea  call    cs:__imp_QueryPerformanceCounter
0x1800101f0  mov     qword ptr [rbp+550h+var_540], 13h
0x1800101f8  xor     eax, eax
0x1800101fa  mov     qword ptr [rbp+550h+var_538], rax
0x1800101fe  xorps   xmm0, xmm0
0x180010201  movdqa  [rbp+550h+var_520], xmm0
0x180010206  mov     [rbp+550h+var_508], 1
0x18001020a  mov     rax, [r12]
0x18001020e  lea     r8, [rbp+550h+var_490]
0x180010215  lea     rdx, WPD_OBJECT_CONTENT_TYPE
0x18001021c  mov     rcx, r12
0x18001021f  mov     rax, [rax+0E0h]
0x180010226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001022b  test    eax, eax
0x18001022d  js      loc_180010349
0x180010233  movaps  xmm7, [rbp+550h+var_490]
0x18001023a  movaps  [rbp+550h+Buf1], xmm7
0x180010241  mov     r8d, 10h; Size
0x180010247  lea     rdx, WPD_CONTENT_TYPE_FOLDER; Buf2
0x18001024e  lea     rcx, [rbp+550h+Buf1]; Buf1
0x180010255  call    memcmp_0
0x18001025a  test    eax, eax
0x18001025c  jz      short loc_18001027F
0x18001025e  mov     r8d, 10h; Size
0x180010264  lea     rdx, WPD_CONTENT_TYPE_FUNCTIONAL_OBJECT; Buf2
0x18001026b  lea     rcx, [rbp+550h+Buf1]; Buf1
0x180010272  call    memcmp_0
0x180010277  test    eax, eax
0x180010279  jnz     loc_180010349
0x18001027f  or      r15d, 22h
0x180010283  mov     r8d, 10h; Size
0x180010289  lea     rdx, WPD_CONTENT_TYPE_FUNCTIONAL_OBJECT; Buf2
0x180010290  lea     rcx, [rbp+550h+Buf1]; Buf1
0x180010297  call    memcmp_0
0x18001029c  test    eax, eax
0x18001029e  jnz     short loc_1800102A5
0x1800102a0  or      dword ptr [rsp+650h+var_5E0], 1
0x1800102a5  mov     ebx, [rbp+550h+var_5B8]
0x1800102a8  test    ebx, ebx
0x1800102aa  jnz     loc_18001034C
0x1800102b0  mov     [rbp+550h+var_5A8], 0
0x1800102b8  mov     rax, [r12]
0x1800102bc  lea     r8, [rbp+550h+var_5A8]
0x1800102c0  lea     rdx, WPD_FOLDER_CONTENT_TYPES_ALLOWED
0x1800102c7  mov     rcx, r12
0x1800102ca  mov     rax, [rax+110h]
0x1800102d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102d6  test    eax, eax
0x1800102d8  jnz     short loc_180010343
0x1800102da  mov     rcx, [rbp+550h+var_5A8]
0x1800102de  mov     rax, [rcx]
0x1800102e1  lea     r8, [rbp+550h+pvar]
0x1800102e5  mov     edx, ebx
0x1800102e7  mov     rax, [rax+20h]
0x1800102eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102f0  test    eax, eax
0x1800102f2  jnz     short loc_180010335
0x1800102f4  mov     eax, 48h ; 'H'
0x1800102f9  cmp     ax, word ptr [rbp+550h+pvar]
0x1800102fd  jnz     short loc_18001032D
0x1800102ff  mov     rcx, qword ptr [rbp+550h+pvar+8]
0x180010303  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_FOLDER.Data1
0x18001030a  sub     rax, [rcx]
0x18001030d  jnz     short loc_18001031A
0x18001030f  mov     rax, qword ptr cs:WPD_CONTENT_TYPE_FOLDER.Data4
0x180010316  sub     rax, [rcx+8]
0x18001031a  test    rax, rax
0x18001031d  jnz     short loc_180010323
0x18001031f  or      r15d, 1
0x180010323  lea     rcx, [rbp+550h+pvar]; pvar
0x180010327  call    cs:__imp_PropVariantClear
0x18001032d  inc     ebx
0x18001032f  test    r15b, 1
0x180010333  jz      short loc_1800102DA
0x180010335  mov     ebx, [rbp+550h+var_5B8]
0x180010338  lea     rcx, [rbp+550h+var_5A8]
0x18001033c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180010341  jmp     short loc_18001034C
0x180010343  or      r15d, 1
0x180010347  jmp     short loc_180010338
0x180010349  mov     ebx, [rbp+550h+var_5B8]
0x18001034c  mov     rax, [r12]
0x180010350  lea     r8, [rbp+550h+pvar]
0x180010354  lea     rdx, WPD_OBJECT_DATE_CREATED
0x18001035b  mov     rcx, r12
0x18001035e  mov     rax, [rax+30h]
0x180010362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010367  mov     ecx, 7
0x18001036c  test    eax, eax
0x18001036e  js      short loc_180010394
0x180010370  cmp     cx, word ptr [rbp+550h+pvar]
0x180010374  jnz     short loc_18001038A
0x180010376  lea     rdx, [rbp+550h+FileTime]; struct _FILETIME *
0x18001037a  lea     rcx, [rbp+550h+pvar+8]; double *
0x18001037e  call    ?ConvertVariantLocalTimeToUTCFileTime@@YAJAEBNPEAU_FILETIME@@@Z; ConvertVariantLocalTimeToUTCFileTime(double const &,_FILETIME *)
0x180010383  test    eax, eax
0x180010385  cmovns  rsi, qword ptr [rbp+550h+FileTime.dwLowDateTime]
0x18001038a  lea     rcx, [rbp+550h+pvar]; pvar
0x18001038e  call    cs:__imp_PropVariantClear
0x180010394  mov     rax, [r12]
0x180010398  lea     r8, [rbp+550h+pvar]
0x18001039c  lea     rdx, WPD_OBJECT_DATE_MODIFIED
0x1800103a3  mov     rcx, r12
0x1800103a6  mov     rax, [rax+30h]
0x1800103aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103af  test    eax, eax
0x1800103b1  js      short loc_18001041C
0x1800103b3  mov     eax, 7
0x1800103b8  cmp     ax, word ptr [rbp+550h+pvar]
0x1800103bc  jnz     short loc_180010412
0x1800103be  xorps   xmm0, xmm0
0x1800103c1  movups  [rbp+550h+Buf2], xmm0
0x1800103c5  xorps   xmm1, xmm1
0x1800103c8  movups  xmmword ptr [rbp+550h+SystemTime.wYear], xmm1
0x1800103cf  lea     rdx, [rbp+550h+SystemTime]; lpSystemTime
0x1800103d6  movsd   xmm0, qword ptr [rbp+550h+pvar+8]; vtime
0x1800103db  call    cs:__imp_VariantTimeToSystemTime
0x1800103e1  test    eax, eax
0x1800103e3  jz      short loc_180010412
0x1800103e5  lea     r8, [rbp+550h+Buf2]; lpUniversalTime
0x1800103e9  lea     rdx, [rbp+550h+SystemTime]; lpLocalTime
0x1800103f0  xor     ecx, ecx; lpTimeZoneInformation
0x1800103f2  call    cs:__imp_TzSpecificLocalTimeToSystemTime
0x1800103f8  test    eax, eax
0x1800103fa  jz      short loc_180010412
0x1800103fc  lea     rdx, [rbp+550h+FileTime]; lpFileTime
0x180010400  lea     rcx, [rbp+550h+Buf2]; lpSystemTime
0x180010404  call    cs:__imp_SystemTimeToFileTime
0x18001040a  test    eax, eax
0x18001040c  jz      short loc_180010412
0x18001040e  mov     rdi, qword ptr [rbp+550h+FileTime.dwLowDateTime]
0x180010412  lea     rcx, [rbp+550h+pvar]; pvar
0x180010416  call    cs:__imp_PropVariantClear
0x18001041c  mov     rax, [r12]
0x180010420  lea     r8, [rbp+550h+var_490]
0x180010427  lea     rdx, WPD_OBJECT_FORMAT
0x18001042e  mov     rcx, r12
0x180010431  mov     rax, [rax+0E0h]
  ... truncated ...
```
