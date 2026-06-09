# CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)

- ea: `0x18000ef50`
- end: `0x18000fbd0`
- name: `?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z`
- size: `3200`
- prototype: `__int64 __usercall@<rax>(CContentFolder *__hidden this@<rcx>, struct IPortableDevice *@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, struct _ITEMIDLIST **, int *)`
- caller_count: `15`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004200`
- `0x18000e840`
- `0x180019e44`
- `0x1800311d8`
- `0x18003a710`
- `0x18003ab88`
- `0x18003bc08`
- `0x18003c878`
- `0x18003ee9c`
- `0x180042af0`
- `0x180044b20`
- `0x18004673c`
- `0x180049d20`
- `0x18004dfa4`
- `0x1800644cc`

## callees

- `0x18000ef50`
- `0x18000ff40`
- `0x180014b60`
- `0x180016200`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180039e80`
- `0x180041ab0`
- `0x18006d490`
- `0x18006ef64`
- `0x180078010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000f155`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f1fa`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f391`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f3bb`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f453`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f5ec`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f78d`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f155`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f1fa`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f391`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f3bb`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f453`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f5ec`
- `KERNEL32!QueryPerformanceCounter` at `0x18000f78d`
- `KERNEL32!QueryPerformanceFrequency` at `0x18000f20d`
- `KERNEL32!QueryPerformanceFrequency` at `0x18000f466`
- `KERNEL32!QueryPerformanceFrequency` at `0x18000f20d`
- `KERNEL32!QueryPerformanceFrequency` at `0x18000f466`
- `KERNEL32!GetCurrentThreadId` at `0x18000f31b`
- `KERNEL32!GetCurrentThreadId` at `0x18000f576`
- `KERNEL32!GetCurrentThreadId` at `0x18000f31b`
- `KERNEL32!GetCurrentThreadId` at `0x18000f576`
- `ole32!CoTaskMemFree` at `0x18000fb48`
- `ole32!CoTaskMemFree` at `0x18000fb48`
- `ole32!CoCreateInstance` at `0x18000f839`
- `ole32!CoCreateInstance` at `0x18000f839`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CContentFolder::_CreateIDList(
        CContentFolder *this,
        struct IPortableDevice *a2,
        unsigned __int16 *a3,
        int a4,
        struct _ITEMIDLIST **a5,
        int *ppv)
{
  unsigned __int16 *v6; // r15
  struct _ITEMIDLIST **v9; // rbx
  struct _ITEMIDLIST **v10; // rdi
  int *v11; // r14
  __int64 v12; // rdi
  int Instance; // esi
  PVOID *v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  char v17; // cl
  signed int LowPart; // ecx
  signed int v19; // esi
  double v20; // xmm1_8
  CPerfTraceHelper *v21; // rcx
  const unsigned __int16 *CommandName; // rax
  __int64 v23; // rcx
  char v24; // r8
  char v25; // r10
  int v26; // eax
  char v27; // cl
  PVOID *v28; // rax
  signed int v29; // ecx
  signed int v30; // esi
  double v31; // xmm1_8
  CPerfTraceHelper *v32; // rcx
  const unsigned __int16 *v33; // rax
  __int64 v34; // rcx
  char v35; // r8
  char v36; // r10
  __int64 v37; // rdx
  __int64 v38; // rdx
  struct _ITEMIDLIST *v39; // rcx
  int v41; // [rsp+50h] [rbp-B8h]
  int v42; // [rsp+60h] [rbp-A8h]
  char v43[8]; // [rsp+78h] [rbp-90h] BYREF
  char v44[8]; // [rsp+80h] [rbp-88h]
  LARGE_INTEGER PerformanceCount[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v46; // [rsp+98h] [rbp-70h]
  LARGE_INTEGER Frequency; // [rsp+A8h] [rbp-60h] BYREF
  char v48; // [rsp+B0h] [rbp-58h]
  struct IPortableDeviceValues *v49; // [rsp+B8h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-40h] BYREF
  struct IPortableDeviceKeyCollection *v52; // [rsp+D0h] [rbp-38h] BYREF
  struct IPortableDeviceValues *v53; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v54; // [rsp+E0h] [rbp-28h] BYREF
  struct _ITEMIDLIST **v55; // [rsp+E8h] [rbp-20h]
  LARGE_INTEGER v56; // [rsp+158h] [rbp+50h] BYREF
  const unsigned __int16 *v57; // [rsp+168h] [rbp+60h]
  int v58; // [rsp+170h] [rbp+68h]

  v58 = a4;
  v57 = a3;
  v6 = a3;
  *(_QWORD *)v43 = 0;
  *(_QWORD *)v44 = 0;
  v48 = 0;
  *(_OWORD *)&PerformanceCount[0].LowPart = 0;
  v46 = 0;
  Frequency.QuadPart = 0;
  pv = 0;
  v9 = 0;
  v55 = 0;
  v49 = 0;
  v53 = 0;
  v52 = 0;
  v10 = a5;
  *a5 = 0;
  v11 = ppv;
  *ppv = 0;
  if ( *((_DWORD *)this + 36) )
  {
    v28 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_85;
  }
  v12 = 0;
  v51 = 0;
  v54 = 0;
  v56.QuadPart = 0;
  if ( !a2 )
  {
    Instance = -2147024809;
LABEL_15:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v12 = 0;
  v51 = 0;
  Instance = ((__int64 (__fastcall *)(struct IPortableDevice *, LARGE_INTEGER *))a2->lpVtbl->Content)(a2, &v56);
  if ( Instance >= 0 )
  {
    if ( !v56.QuadPart )
    {
      Instance = -2147418113;
      goto LABEL_15;
    }
    Instance = (*(__int64 (__fastcall **)(LARGE_INTEGER, __int64 *))(*(_QWORD *)v56.QuadPart + 40LL))(v56, &v54);
    if ( Instance >= 0 )
    {
      v12 = v54;
      v51 = v54;
      goto LABEL_20;
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_21;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 19;
      goto LABEL_14;
    }
  }
  else
  {
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_21;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v15 = 18;
LABEL_14:
      WPP_SF_d(v14[2], v15, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)Instance);
      goto LABEL_15;
    }
  }
LABEL_16:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
  {
    WPP_SF_d(v14[2], 20, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)Instance);
LABEL_20:
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( v56.QuadPart )
  {
    (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v56.QuadPart + 16LL))(v56);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Instance < 0 )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 )
      WPP_SF_d(v14[2], 189, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)Instance);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
    goto LABEL_139;
  }
  if ( v58 )
  {
LABEL_55:
    if ( v48 )
      goto LABEL_58;
    goto LABEL_56;
  }
  if ( !v48 && (*((_DWORD *)v14 + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    *(_QWORD *)v43 = 17;
    *(_QWORD *)v44 = 0;
    v46 = 0;
    v48 = 1;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, const PROPERTYKEY *, struct IPortableDeviceValues **))(*(_QWORD *)v12 + 32LL))(
          v12,
          v6,
          &WPD_RESOURCE_DEFAULT,
          &v53);
  v17 = v16;
  if ( v16 >= 0 )
    goto LABEL_36;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      190,
      (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      (_DWORD)v6,
      v17);
LABEL_36:
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  v56.QuadPart = 0;
  if ( *(_DWORD *)v43 != 17 || (*((_DWORD *)v14 + 7) & 0x800) == 0 )
    goto LABEL_55;
  QueryPerformanceCounter(&v56);
  LowPart = Frequency.LowPart;
  if ( !Frequency.QuadPart )
  {
    if ( !QueryPerformanceFrequency(&Frequency) || (LowPart = Frequency.LowPart, !Frequency.QuadPart) )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_55;
    }
  }
  v19 = v56.LowPart - PerformanceCount[0].LowPart;
  switch ( *(_DWORD *)v43 )
  {
    case 1:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids);
        LowPart = Frequency.LowPart;
        goto LABEL_47;
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
LABEL_47:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      break;
    default:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        goto LABEL_55;
      break;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x800) != 0 )
  {
    v20 = (double)v19 / (double)LowPart * 1000.0;
    GetCurrentThreadId();
    v21 = (CPerfTraceHelper *)v57;
    if ( !v57 )
      v21 = (CPerfTraceHelper *)L"N/A";
    CommandName = CPerfTraceHelper::GetCommandName(v21, *(unsigned int *)v43);
    WPP_SF_dDSdiddddDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v24,
      (__int64)CommandName,
      v25,
      v44[0],
      (int)v20,
      v41,
      v43[4],
      v42,
      0,
      v23);
    v11 = ppv;
    v6 = (unsigned __int16 *)v57;
  }
  QueryPerformanceCounter(&PerformanceCount[1]);
  v48 = 0;
  v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_56:
  if ( (*((_DWORD *)v14 + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(PerformanceCount);
    *(_QWORD *)v43 = 16;
    *(_QWORD *)v44 = 0;
    v46 = 0;
    v48 = 1;
  }
LABEL_58:
  v26 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, struct IPortableDeviceKeyCollection **))(*(_QWORD *)v12 + 24LL))(
          v12,
          v6,
          &v52);
  v27 = v26;
  if ( v26 < 0 )
  {
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_63;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      191,
      (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      (_DWORD)v6,
      v27);
  }
  v28 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
  v56.QuadPart = 0;
  if ( *(_DWORD *)v43 == 16 && (*((_DWORD *)v28 + 7) & 0x800) != 0 )
  {
    QueryPerformanceCounter(&v56);
    v29 = Frequency.LowPart;
    if ( Frequency.QuadPart || QueryPerformanceFrequency(&Frequency) && (v29 = Frequency.LowPart, Frequency.QuadPart) )
    {
      v30 = v56.LowPart - PerformanceCount[0].LowPart;
      switch ( *(_DWORD *)v43 )
      {
        case 1:
          v28 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
            goto LABEL_75;
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids);
          v29 = Frequency.LowPart;
          goto LABEL_73;
        case 2:
        case 4:
        case 5:
        case 6:
        case 7:
        case 8:
        case 9:
        case 0xA:
        case 0xB:
LABEL_73:
          v28 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_75;
        default:
          v28 = (PVOID *)WPP_GLOBAL_Control;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
LABEL_75:
            if ( v28 != &WPP_GLOBAL_Control && (*((_DWORD *)v28 + 7) & 0x800) != 0 )
            {
              v31 = (double)v30 / (double)v29 * 1000.0;
              GetCurrentThreadId();
              v32 = (CPerfTraceHelper *)v57;
              if ( !v57 )
                v32 = (CPerfTraceHelper *)L"N/A";
              v33 = CPerfTraceHelper::GetCommandName(v32, *(unsigned int *)v43);
              WPP_SF_dDSdiddddDS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v35,
                (__int64)v33,
                v36,
                v44[0],
                (int)v31,
                v41,
                v43[4],
                v42,
                0,
                v34);
              v11 = ppv;
              v6 = (unsigned __int16 *)v57;
            }
            QueryPerformanceCounter(&PerformanceCount[1]);
            v48 = 0;
            v28 = (PVOID *)WPP_GLOBAL_Control;
          }
          break;
      }
    }
    else
    {
      v28 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = a5;
LABEL_85:
  a5 = 0;
  ppv = 0;
  if ( !a2 )
  {
    Instance = -2147024809;
    goto LABEL_99;
  }
  v9 = 0;
  v55 = 0;
  Instance = ((__int64 (__fastcall *)(struct IPortableDevice *, int **))a2->lpVtbl->Content)(a2, &ppv);
  if ( Instance >= 0 )
  {
    if ( !ppv )
    {
      Instance = -2147418113;
LABEL_98:
      v28 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_99;
    }
    Instance = (*(__int64 (__fastcall **)(int *, struct _ITEMIDLIST ***))(*(_QWORD *)ppv + 32LL))(ppv, &a5);
    if ( Instance >= 0 )
    {
      v9 = a5;
      v55 = a5;
      goto LABEL_103;
    }
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_104;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v37 = 16;
      goto LABEL_97;
    }
  }
  else
  {
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_104;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v37 = 15;
LABEL_97:
      WPP_SF_d(v28[2], v37, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)Instance);
      goto LABEL_98;
    }
  }
LABEL_99:
  if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 2) != 0 )
  {
    WPP_SF_d(v28[2], 17, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)Instance);
LABEL_103:
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_104:
  if ( ppv )
  {
    (*(void (__fastcall **)(int *))(*(_QWORD *)ppv + 16LL))(ppv);
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Instance < 0 )
  {
    if ( v28 == &WPP_GLOBAL_Control )
      goto LABEL_144;
    if ( (*((_BYTE *)v28 + 28) & 2) == 0 )
      goto LABEL_140;
    v38 = 192;
    goto LABEL_138;
  }
  if ( *((_DWORD *)this + 36) || v58 )
  {
    ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_PortableDeviceKeyCollection,
                 0,
                 1u,
                 &GUID_dada2357_e0ad_492e_98db_dd61c53ba353,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
    {
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          193,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)Instance);
        v28 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( ppv )
      {
        (*(void (__fastcall **)(int *))(*(_QWORD *)ppv + 16LL))(ppv);
        v28 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_140;
    }
    (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_NAME);
    (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_PERSISTENT_UNIQUE_ID);
    (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_CONTENT_TYPE);
    if ( v58 )
    {
      (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_CAN_DELETE);
      (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_DATE_CREATED);
      (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_DATE_MODIFIED);
      (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_FORMAT);
      (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_ISHIDDEN);
      (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_ISSYSTEM);
      (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_ORIGINAL_FILE_NAME);
      (*(void (__fastcall **)(int *, const PROPERTYKEY *))(*(_QWORD *)ppv + 40LL))(ppv, &WPD_OBJECT_SIZE);
    }
    CPerfTraceHelper::BeginOperation((CPerfTraceHelper *)v43, 0x12u);
    Instance = (*(__int64 (__fastcall **)(struct _ITEMIDLIST **, unsigned __int16 *, int *, struct IPortableDeviceValues **))((char *)&(*v9)[13].mkid.cb + 1))(
                 v9,
                 v6,
                 ppv,
                 &v49);
    CPerfTraceHelper::ProcessPerformanceData((CPerfTraceHelper *)v43, 0x12u, Instance, v6);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          194,
          WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
          (unsigned int)Instance);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
      goto LABEL_139;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  }
  else
  {
    if ( !v48 && (*((_DWORD *)v28 + 7) & 0x800) != 0 )
    {
      QueryPerformanceCounter(PerformanceCount);
      *(_QWORD *)v43 = 18;
      *(_QWORD *)v44 = 0;
      v46 = 0;
      v48 = 1;
    }
    Instance = (*(__int64 (__fastcall **)(struct _ITEMIDLIST **, unsigned __int16 *, _QWORD, struct IPortableDeviceValues **))((char *)&(*v9)[13].mkid.cb + 1))(
                 v9,
                 v6,
                 0,
                 &v49);
    CPerfTraceHelper::ProcessPerformanceData((CPerfTraceHelper *)v43, 0x12u, Instance, v6);
    if ( Instance < 0 )
    {
      v28 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_144;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_140;
      v38 = 195;
      goto LABEL_138;
    }
  }
  Instance = CContentFolder::_CreateContentItem(this, v58, v49, v6, a2, v52, v53, (struct CONTENTITEM **)&pv);
  if ( Instance >= 0 )
  {
    v39 = (struct _ITEMIDLIST *)pv;
    *v11 = 8 * (*(_DWORD *)((_BYTE *)pv + 10) & 2);
    pv = 0;
    *v10 = v39;
    goto LABEL_144;
  }
  v28 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_144;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v38 = 196;
LABEL_138:
    WPP_SF_d(v28[2], v38, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)Instance);
LABEL_139:
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_140:
  if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 2) != 0 )
    WPP_SF_d(v28[2], 197, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)Instance);
LABEL_144:
  if ( v52 )
    ((void (__fastcall *)(struct IPortableDeviceKeyCollection *))v52->lpVtbl->Release)(v52);
  if ( v53 )
    ((void (__fastcall *)(struct IPortableDeviceValues *))v53->lpVtbl->Release)(v53);
  if ( v49 )
    ((void (__fastcall *)(struct IPortableDeviceValues *))v49->lpVtbl->Release)(v49);
  if ( v9 )
    (*(void (__fastcall **)(struct _ITEMIDLIST **))((char *)&(*v9)[5].mkid.cb + 1))(v9);
  CoTaskMemFree(pv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000ef50  mov     rax, rsp
0x18000ef53  mov     [rax+10h], rbx
0x18000ef57  mov     [rax+20h], r9d
0x18000ef5b  mov     [rax+18h], r8
0x18000ef5f  push    rbp
0x18000ef60  push    rsi
0x18000ef61  push    rdi
0x18000ef62  push    r12
0x18000ef64  push    r13
0x18000ef66  push    r14
0x18000ef68  push    r15
0x18000ef6a  lea     rbp, [rax-48h]
0x18000ef6e  sub     rsp, 110h
0x18000ef75  movaps  xmmword ptr [rax-48h], xmm6
0x18000ef79  movaps  xmmword ptr [rax-58h], xmm7
0x18000ef7d  mov     r15, r8
0x18000ef80  mov     r12, rdx
0x18000ef83  mov     r13, rcx
0x18000ef86  xor     esi, esi
0x18000ef88  mov     qword ptr [rsp+140h+var_D0], rsi
0x18000ef8d  mov     qword ptr [rsp+140h+var_C8], rsi
0x18000ef92  mov     [rbp+40h+var_98], sil
0x18000ef96  xorps   xmm0, xmm0
0x18000ef99  movdqa  xmmword ptr [rbp+40h+PerformanceCount], xmm0
0x18000ef9e  xorps   xmm1, xmm1
0x18000efa1  movdqa  [rbp+40h+var_B0], xmm1
0x18000efa6  mov     qword ptr [rbp+40h+Frequency], rsi
0x18000efaa  mov     [rbp+40h+pv], rsi
0x18000efae  mov     ebx, esi
0x18000efb0  mov     [rbp+40h+var_60], rbx
0x18000efb4  mov     [rbp+40h+var_90], rsi
0x18000efb8  mov     [rbp+40h+var_70], rsi
0x18000efbc  mov     [rbp+40h+var_78], rsi
0x18000efc0  mov     rdi, [rbp+40h+arg_20]
0x18000efc4  mov     [rdi], rsi
0x18000efc7  mov     r14, [rbp+40h+arg_28]
0x18000efcb  mov     [r14], esi
0x18000efce  cmp     [rcx+90h], esi
0x18000efd4  jnz     loc_18000F620
0x18000efda  mov     edi, esi
0x18000efdc  mov     [rbp+40h+var_80], rsi
0x18000efe0  mov     [rbp+40h+var_68], rsi
0x18000efe4  mov     qword ptr [rbp+40h+arg_0], rsi
0x18000efe8  test    rdx, rdx
0x18000efeb  jnz     short loc_18000EFF7
0x18000efed  mov     esi, 80070057h
0x18000eff2  jmp     loc_18000F093
0x18000eff7  mov     rdi, rsi
0x18000effa  mov     [rbp+40h+var_80], rsi
0x18000effe  mov     rax, [rdx]
0x18000f001  lea     rdx, [rbp+40h+arg_0]
0x18000f005  mov     rcx, r12
0x18000f008  mov     rax, [rax+28h]
0x18000f00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f011  mov     esi, eax
0x18000f013  test    eax, eax
0x18000f015  jns     short loc_18000F03B
0x18000f017  mov     rax, cs:WPP_GLOBAL_Control
0x18000f01e  lea     rcx, WPP_GLOBAL_Control
0x18000f025  cmp     rax, rcx
0x18000f028  jz      loc_18000F0D5
0x18000f02e  test    byte ptr [rax+1Ch], 2
0x18000f032  jz      short loc_18000F0A1
0x18000f034  mov     edx, 12h
0x18000f039  jmp     short loc_18000F080
0x18000f03b  cmp     qword ptr [rbp+40h+arg_0], rdi
0x18000f03f  jnz     short loc_18000F048
0x18000f041  mov     esi, 8000FFFFh
0x18000f046  jmp     short loc_18000F093
0x18000f048  mov     rcx, qword ptr [rbp+40h+arg_0]
0x18000f04c  mov     rax, [rcx]
0x18000f04f  lea     rdx, [rbp+40h+var_68]
0x18000f053  mov     rax, [rax+28h]
0x18000f057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f05c  mov     esi, eax
0x18000f05e  test    eax, eax
0x18000f060  jns     short loc_18000F0C6
0x18000f062  mov     rax, cs:WPP_GLOBAL_Control
0x18000f069  lea     rcx, WPP_GLOBAL_Control
0x18000f070  cmp     rax, rcx
0x18000f073  jz      short loc_18000F0D5
0x18000f075  test    byte ptr [rax+1Ch], 2
0x18000f079  jz      short loc_18000F0A1
0x18000f07b  mov     edx, 13h
0x18000f080  mov     r9d, esi
0x18000f083  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18000f08a  mov     rcx, [rax+10h]
0x18000f08e  call    WPP_SF_d
0x18000f093  lea     rcx, WPP_GLOBAL_Control
0x18000f09a  mov     rax, cs:WPP_GLOBAL_Control
0x18000f0a1  cmp     rax, rcx
0x18000f0a4  jz      short loc_18000F0D5
0x18000f0a6  test    byte ptr [rax+1Ch], 2
0x18000f0aa  jz      short loc_18000F0D5
0x18000f0ac  mov     edx, 14h
0x18000f0b1  mov     r9d, esi
0x18000f0b4  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18000f0bb  mov     rcx, [rax+10h]
0x18000f0bf  call    WPP_SF_d
0x18000f0c4  jmp     short loc_18000F0CE
0x18000f0c6  mov     rdi, [rbp+40h+var_68]
0x18000f0ca  mov     [rbp+40h+var_80], rdi
0x18000f0ce  mov     rax, cs:WPP_GLOBAL_Control
0x18000f0d5  mov     rcx, qword ptr [rbp+40h+arg_0]
0x18000f0d9  test    rcx, rcx
0x18000f0dc  jz      short loc_18000F0F1
0x18000f0de  mov     rax, [rcx]
0x18000f0e1  mov     rax, [rax+10h]
0x18000f0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ea  mov     rax, cs:WPP_GLOBAL_Control
0x18000f0f1  test    esi, esi
0x18000f0f3  jns     short loc_18000F135
0x18000f0f5  lea     rcx, WPP_GLOBAL_Control
0x18000f0fc  cmp     rax, rcx
0x18000f0ff  jz      short loc_18000F120
0x18000f101  test    byte ptr [rax+1Ch], 2
0x18000f105  jz      short loc_18000F120
0x18000f107  mov     edx, 0BDh
0x18000f10c  mov     r9d, esi
0x18000f10f  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000f116  mov     rcx, [rax+10h]
0x18000f11a  call    WPP_SF_d
0x18000f11f  nop
0x18000f120  lea     rcx, [rbp+40h+var_80]
0x18000f124  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000f129  lea     rdi, WPP_GLOBAL_Control
0x18000f130  jmp     loc_18000FAA6
0x18000f135  xorps   xmm6, xmm6
0x18000f138  cmp     [rbp+40h+arg_18], 0
0x18000f13c  jnz     loc_18000F3A6
0x18000f142  cmp     [rbp+40h+var_98], 0
0x18000f146  jnz     short loc_18000F179
0x18000f148  test    dword ptr [rax+1Ch], 800h
0x18000f14f  jz      short loc_18000F179
0x18000f151  lea     rcx, [rbp+40h+PerformanceCount]; lpPerformanceCount
0x18000f155  call    cs:__imp_QueryPerformanceCounter
0x18000f15b  mov     qword ptr [rsp+140h+var_D0], 11h
0x18000f164  xor     esi, esi
0x18000f166  mov     qword ptr [rsp+140h+var_C8], rsi
0x18000f16b  xorps   xmm0, xmm0
0x18000f16e  movdqa  [rbp+40h+var_B0], xmm0
0x18000f173  mov     [rbp+40h+var_98], 1
0x18000f177  jmp     short loc_18000F17B
0x18000f179  xor     esi, esi
0x18000f17b  mov     rax, [rdi]
0x18000f17e  lea     r9, [rbp+40h+var_70]
0x18000f182  lea     r8, WPD_RESOURCE_DEFAULT
0x18000f189  mov     rdx, r15
0x18000f18c  mov     rcx, rdi
0x18000f18f  mov     rax, [rax+20h]
0x18000f193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f198  mov     ecx, eax
0x18000f19a  test    eax, eax
0x18000f19c  jns     short loc_18000F1D3
0x18000f19e  mov     rax, cs:WPP_GLOBAL_Control
0x18000f1a5  lea     rdx, WPP_GLOBAL_Control
0x18000f1ac  cmp     rax, rdx
0x18000f1af  jz      short loc_18000F1DA
0x18000f1b1  test    byte ptr [rax+1Ch], 4
0x18000f1b5  jz      short loc_18000F1DA
0x18000f1b7  mov     edx, 0BEh
0x18000f1bc  mov     dword ptr [rsp+140h+ppv], ecx
0x18000f1c0  mov     r9, r15
0x18000f1c3  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000f1ca  mov     rcx, [rax+10h]
0x18000f1ce  call    WPP_SF_Sd
0x18000f1d3  mov     rax, cs:WPP_GLOBAL_Control
0x18000f1da  mov     qword ptr [rbp+40h+arg_0], rsi
0x18000f1de  cmp     dword ptr [rsp+140h+var_D0], 11h
0x18000f1e3  jnz     loc_18000F3A8
0x18000f1e9  test    dword ptr [rax+1Ch], 800h
0x18000f1f0  jz      loc_18000F3A8
0x18000f1f6  lea     rcx, [rbp+40h+arg_0]; lpPerformanceCount
0x18000f1fa  call    cs:__imp_QueryPerformanceCounter
0x18000f200  mov     rcx, qword ptr [rbp+40h+Frequency]
0x18000f204  test    rcx, rcx
0x18000f207  jnz     short loc_18000F22C
0x18000f209  lea     rcx, [rbp+40h+Frequency]; lpFrequency
0x18000f20d  call    cs:__imp_QueryPerformanceFrequency
0x18000f213  test    eax, eax
0x18000f215  jz      short loc_18000F220
0x18000f217  mov     rcx, qword ptr [rbp+40h+Frequency]
0x18000f21b  test    rcx, rcx
0x18000f21e  jnz     short loc_18000F22C
0x18000f220  mov     rax, cs:WPP_GLOBAL_Control
0x18000f227  jmp     loc_18000F3A8
0x18000f22c  mov     rsi, qword ptr [rbp+40h+arg_0]
0x18000f230  mov     rdx, qword ptr [rbp+40h+PerformanceCount]
0x18000f234  sub     rsi, rdx
0x18000f237  mov     eax, dword ptr [rsp+140h+var_D0]
0x18000f23b  dec     eax; switch 11 cases
0x18000f23d  cmp     eax, 0Ah
0x18000f240  ja      short def_18000F254; jumptable 000000018000F254 default case, case 3
0x18000f242  lea     r8, __ImageBase
0x18000f249  mov     eax, ds:(jpt_18000F254 - 180000000h)[r8+rax*4]
0x18000f251  add     rax, r8
0x18000f254  jmp     rax; switch jump
0x18000f256  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018000F254 case 1
0x18000f25d  lea     r9, WPP_GLOBAL_Control
0x18000f264  cmp     rax, r9
0x18000f267  jz      short loc_18000F2B3
0x18000f269  test    dword ptr [rax+1Ch], 800h
0x18000f270  jz      short loc_18000F2B3
0x18000f272  mov     edx, 7Dh ; '}'
0x18000f277  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18000f27e  mov     rcx, [rax+10h]
0x18000f282  call    WPP_SF_
0x18000f287  mov     rcx, qword ptr [rbp+40h+Frequency]
0x18000f28b  mov     rdx, qword ptr [rbp+40h+PerformanceCount]
0x18000f28f  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018000F254 cases 2,4-11
0x18000f296  jmp     short loc_18000F2AC
0x18000f298  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018000F254 default case, case 3
0x18000f29f  test    dword ptr [rax+1Ch], 1000h
0x18000f2a6  jz      loc_18000F3A6
0x18000f2ac  lea     r9, WPP_GLOBAL_Control
0x18000f2b3  mov     r8, qword ptr [rbp+40h+PerformanceCount+8]
0x18000f2b7  xorps   xmm7, xmm7
0x18000f2ba  test    r8, r8
0x18000f2bd  jz      short loc_18000F2DB
0x18000f2bf  sub     rdx, r8
0x18000f2c2  cvtsi2sd xmm7, rdx
0x18000f2c7  xorps   xmm0, xmm0
0x18000f2ca  cvtsi2sd xmm0, rcx
0x18000f2cf  divsd   xmm7, xmm0
0x18000f2d3  mulsd   xmm7, cs:__real@408f400000000000
0x18000f2db  cmp     rax, r9
0x18000f2de  jz      loc_18000F38D
0x18000f2e4  test    dword ptr [rax+1Ch], 800h
0x18000f2eb  jz      loc_18000F38D
0x18000f2f1  xorps   xmm1, xmm1
0x18000f2f4  cvtsi2sd xmm1, rsi
0x18000f2f9  xorps   xmm0, xmm0
0x18000f2fc  cvtsi2sd xmm0, rcx
0x18000f301  divsd   xmm1, xmm0
0x18000f305  mulsd   xmm1, cs:__real@408f400000000000
0x18000f30d  cvttsd2si r15, xmm1
0x18000f312  mov     esi, dword ptr [rsp+140h+var_D0+4]
0x18000f316  mov     r14, qword ptr [rsp+140h+var_C8]
0x18000f31b  call    cs:__imp_GetCurrentThreadId
0x18000f321  mov     r10d, eax
0x18000f324  mov     rax, [rbp+40h+arg_10]
0x18000f328  mov     rcx, rax
0x18000f32b  test    rax, rax
0x18000f32e  lea     rax, aNA; "N/A"
0x18000f335  cmovz   rcx, rax; this
0x18000f339  mov     r8d, dword ptr [rsp+140h+var_D0]
0x18000f33e  mov     edx, r8d; unsigned int
0x18000f341  call    ?GetCommandName@CPerfTraceHelper@@QEAAPEBGK@Z; CPerfTraceHelper::GetCommandName(ulong)
0x18000f346  cvttsd2si r9, xmm7
0x18000f34b  mov     [rsp+140h+var_D8], rcx; __int64
0x18000f350  mov     dword ptr [rsp+140h+var_E0], 0; char
0x18000f358  mov     dword ptr [rsp+140h+var_F0], esi; char
0x18000f35c  mov     dword ptr [rsp+140h+var_100], r15d; char
0x18000f361  mov     [rsp+140h+var_108], r14; char
0x18000f366  mov     dword ptr [rsp+140h+var_110], r10d; char
0x18000f36b  mov     [rsp+140h+var_118], rax; __int64
0x18000f370  mov     dword ptr [rsp+140h+ppv], r8d; char
0x18000f375  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f37c  mov     rcx, [rcx+10h]; LoggerHandle
0x18000f380  call    WPP_SF_dDSdiddddDS
0x18000f385  mov     r14, [rbp+40h+arg_28]
0x18000f389  mov     r15, [rbp+40h+arg_10]
0x18000f38d  lea     rcx, [rbp+40h+PerformanceCount+8]; lpPerformanceCount
0x18000f391  call    cs:__imp_QueryPerformanceCounter
0x18000f397  mov     [rbp+40h+var_98], 0
0x18000f39b  mov     rax, cs:WPP_GLOBAL_Control
0x18000f3a2  xor     esi, esi
0x18000f3a4  jmp     short loc_18000F3AE
0x18000f3a6  xor     esi, esi
0x18000f3a8  cmp     [rbp+40h+var_98], 0
0x18000f3ac  jnz     short loc_18000F3DB
0x18000f3ae  test    dword ptr [rax+1Ch], 800h
0x18000f3b5  jz      short loc_18000F3DB
0x18000f3b7  lea     rcx, [rbp+40h+PerformanceCount]; lpPerformanceCount
0x18000f3bb  call    cs:__imp_QueryPerformanceCounter
0x18000f3c1  mov     qword ptr [rsp+140h+var_D0], 10h
0x18000f3ca  mov     qword ptr [rsp+140h+var_C8], rsi
0x18000f3cf  xorps   xmm0, xmm0
0x18000f3d2  movdqa  [rbp+40h+var_B0], xmm0
0x18000f3d7  mov     [rbp+40h+var_98], 1
0x18000f3db  mov     rax, [rdi]
0x18000f3de  lea     r8, [rbp+40h+var_78]
0x18000f3e2  mov     rdx, r15
0x18000f3e5  mov     rcx, rdi
0x18000f3e8  mov     rax, [rax+18h]
0x18000f3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3f1  mov     ecx, eax
0x18000f3f3  test    eax, eax
0x18000f3f5  jns     short loc_18000F42C
0x18000f3f7  mov     rax, cs:WPP_GLOBAL_Control
0x18000f3fe  lea     rdx, WPP_GLOBAL_Control
0x18000f405  cmp     rax, rdx
0x18000f408  jz      short loc_18000F433
0x18000f40a  test    byte ptr [rax+1Ch], 4
0x18000f40e  jz      short loc_18000F433
0x18000f410  mov     edx, 0BFh
0x18000f415  mov     dword ptr [rsp+140h+ppv], ecx
0x18000f419  mov     r9, r15
0x18000f41c  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x18000f423  mov     rcx, [rax+10h]
  ... truncated ...
```
