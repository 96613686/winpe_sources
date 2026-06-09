# CUpdate::InitInternal(tagDSUpdateMetadata const &,tagDSDeployment const &)

- ea: `0x18005759c`
- end: `0x1800584b0`
- name: `?InitInternal@CUpdate@@AEAAJAEBUtagDSUpdateMetadata@@AEBUtagDSDeployment@@@Z`
- size: `3860`
- prototype: `__int64 __fastcall(CUpdate *__hidden this, const struct tagDSUpdateMetadata *, const struct tagDSDeployment *)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180057304`

## callees

- `0x18000588c`
- `0x180005bc0`
- `0x180006ac4`
- `0x180007ecc`
- `0x180008c34`
- `0x1800224a0`
- `0x1800404ac`
- `0x1800573e4`
- `0x18005759c`
- `0x180059074`
- `0x18005ce5c`
- `0x18005e70c`
- `0x1800620a0`
- `0x180080ce4`
- `0x180081a38`
- `0x180081adc`
- `0x180082534`
- `0x180090bc8`
- `0x180091568`
- `0x180091c70`
- `0x180092b2c`
- `0x180096bb0`
- `0x18009ae75`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180058186`
- `RPCRT4!RpcStringFreeW` at `0x1800581d2`
- `RPCRT4!RpcStringFreeW` at `0x180058186`
- `RPCRT4!RpcStringFreeW` at `0x1800581d2`
- `RPCRT4!UuidToStringW` at `0x180058123`
- `RPCRT4!UuidToStringW` at `0x180058123`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057e09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180057e09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057e84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180057e84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057e75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180057e75`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800575e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800575e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18005836c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800583ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800583ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18005836c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800583ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800583ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180057aab`
- `OLEAUT32!__imp_SysFreeString` at `0x180057ae6`
- `OLEAUT32!__imp_SysFreeString` at `0x180057c25`
- `OLEAUT32!__imp_SysFreeString` at `0x180057c58`
- `OLEAUT32!__imp_SysFreeString` at `0x180057c8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180057cca`
- `OLEAUT32!__imp_SysFreeString` at `0x180057d11`
- `OLEAUT32!__imp_SysFreeString` at `0x180057d78`
- `OLEAUT32!__imp_SysFreeString` at `0x180057dac`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f92`
- `OLEAUT32!__imp_SysFreeString` at `0x180057fee`
- `OLEAUT32!__imp_SysFreeString` at `0x18005831e`
- `OLEAUT32!__imp_SysFreeString` at `0x180058355`
- `OLEAUT32!__imp_SysFreeString` at `0x180058396`
- `OLEAUT32!__imp_SysFreeString` at `0x1800583d7`
- `OLEAUT32!__imp_SysFreeString` at `0x180057aab`
- `OLEAUT32!__imp_SysFreeString` at `0x180057ae6`
- `OLEAUT32!__imp_SysFreeString` at `0x180057c25`
- `OLEAUT32!__imp_SysFreeString` at `0x180057c58`
- `OLEAUT32!__imp_SysFreeString` at `0x180057c8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180057cca`
- `OLEAUT32!__imp_SysFreeString` at `0x180057d11`
- `OLEAUT32!__imp_SysFreeString` at `0x180057d78`
- `OLEAUT32!__imp_SysFreeString` at `0x180057dac`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f92`
- `OLEAUT32!__imp_SysFreeString` at `0x180057fee`
- `OLEAUT32!__imp_SysFreeString` at `0x18005831e`
- `OLEAUT32!__imp_SysFreeString` at `0x180058355`
- `OLEAUT32!__imp_SysFreeString` at `0x180058396`
- `OLEAUT32!__imp_SysFreeString` at `0x1800583d7`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x1800575f1`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x1800575f1`

## string_xrefs

- `0x180057610`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x1800581e3`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x180057650`: `Update metadata for %ws is missing core or localized properties`
- `0x180057de3`: `http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/SingleStageAppX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUpdate::InitInternal(
        CUpdate *this,
        const struct tagDSUpdateMetadata *a2,
        const struct tagDSDeployment *a3)
{
  INT v6; // eax
  __int64 v7; // r8
  const char *v8; // r9
  int Instance; // r15d
  __int64 v10; // rdx
  __int16 v11; // ax
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // r9d
  __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rcx
  CImageInformation *v21; // rbx
  __int64 v22; // rcx
  CImageInformation *v23; // rbx
  __int64 v24; // rcx
  CImageInformation *v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int v28; // eax
  wchar_t **v29; // rdx
  const WCHAR **v30; // r14
  const wchar_t *v31; // rcx
  const WCHAR *v32; // r8
  bool v33; // al
  int v34; // ecx
  void (__fastcall ***v35)(_QWORD, __int64); // rcx
  HANDLE ProcessHeap; // rax
  _QWORD *v37; // rax
  _QWORD *v38; // rbx
  CImageInformation *v39; // rbx
  unsigned int v40; // r14d
  __int64 v41; // rdx
  HINSTANCE LocResourceInstance; // rax
  int v43; // edx
  int v44; // r8d
  unsigned __int64 v45; // r9
  int v46; // eax
  HINSTANCE v47; // rax
  int StringAllocW; // eax
  unsigned __int64 v49; // r9
  __int64 v50; // rdx
  int refreshed; // eax
  unsigned __int64 v52; // rbx
  void *v53; // rax
  unsigned int v54; // ebx
  unsigned int v55; // ecx
  unsigned int v56; // eax
  int v57; // eax
  __int64 i; // rbx
  unsigned int j; // ebx
  int v60; // eax
  __int16 v61; // ax
  const OLECHAR *v62; // rbx
  BSTR v63; // rax
  const OLECHAR *v64; // rbx
  BSTR v65; // rax
  const OLECHAR *v66; // rbx
  BSTR v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v73; // [rsp+30h] [rbp-D0h]
  CImageInformation *v74[4]; // [rsp+40h] [rbp-C0h] BYREF
  char v75; // [rsp+60h] [rbp-A0h]
  _BYTE v76[112]; // [rsp+70h] [rbp-90h] BYREF
  void *lpMem; // [rsp+E0h] [rbp-20h] BYREF
  struct _FILETIME v78; // [rsp+E8h] [rbp-18h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  lpMem = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v6 = SystemTimeToVariantTime(&SystemTime, (DOUBLE *)this + 50);
  v8 = v6 != 1 ? (const char *)0x80240FFFLL : 0LL;
  if ( v6 != 1 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE39,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      v8,
      (int)lpString2);
  Instance = -2145124323;
  if ( (*((_DWORD *)a2 + 7) & 0xF00) != 0xF00 )
  {
    Trace::UpdateIdToString::UpdateIdToString(
      (Trace::UpdateIdToString *)v76,
      (const struct tagDSUpdateMetadata *)((char *)a2 + 4));
    LODWORD(lpString2) = -2145124323;
    WUTrace(0, 0, 0x10000, 1, lpString2, L"Update metadata for %ws is missing core or localized properties");
    v10 = 3652;
LABEL_186:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)Instance,
      (int)lpString2);
    v40 = Instance;
    goto LABEL_187;
  }
  if ( !*((_DWORD *)a2 + 108) || !*((_QWORD *)a2 + 55) )
  {
    v10 = 3655;
    goto LABEL_186;
  }
  if ( *((_DWORD *)a2 + 120) && !*((_QWORD *)a2 + 61) )
  {
    v10 = 3656;
    goto LABEL_186;
  }
  if ( *((_DWORD *)a3 + 7) )
  {
    Instance = FileTimeToVariantTime((char *)a3 + 8, (char *)this + 592, v7, v8);
    if ( Instance < 0 )
    {
      v10 = 3662;
      goto LABEL_186;
    }
    *((_WORD *)this + 292) = 7;
  }
  Instance = FileTimeToVariantTime((char *)a3 + 16, (char *)this + 392, v7, v8);
  if ( Instance < 0 )
  {
    v10 = 3666;
    goto LABEL_186;
  }
  v11 = -1;
  if ( *((_WORD *)this + 312) != 0xFFFF || (*((_BYTE *)a2 + 144) & 1) == 0 )
    v11 = 0;
  *((_WORD *)this + 313) = v11;
  v12 = *((_DWORD *)a2 + 112);
  *((_DWORD *)this + 105) = v12 != 0;
  if ( v12 )
  {
    *((_OWORD *)this + 41) = *((_OWORD *)a2 + 26);
    *((_DWORD *)this + 107) = *((_DWORD *)a2 + 51);
    *((_DWORD *)this + 106) = *((_DWORD *)a2 + 37) == 1;
  }
  *((_WORD *)this + 304) = -(*((_DWORD *)a2 + 22) != 0);
  *((_WORD *)this + 305) = -((*((_DWORD *)a2 + 46) & 4) != 0);
  *((_WORD *)this + 306) = -((*((_DWORD *)a2 + 46) & 0x20) != 0);
  *((_WORD *)this + 316) = -((*((_DWORD *)a2 + 46) & 0x100) != 0);
  v13 = *((_DWORD *)a2 + 46);
  if ( (v13 & 0x800) != 0 )
  {
    *((_DWORD *)this + 244) = 2;
  }
  else if ( (v13 & 0x1000) != 0 )
  {
    *((_DWORD *)this + 244) = 1;
  }
  else
  {
    v14 = 0;
    v15 = *((_DWORD *)a2 + 124);
    if ( !v15 )
      goto LABEL_32;
    v16 = *((_QWORD *)a2 + 63);
    while ( *(_DWORD *)(v16 + 24LL * v14) != 914996680
         || *(_DWORD *)(v16 + 24LL * v14 + 4) != *(_DWORD *)&GUID_3689bdc8_b205_4af4_8d4a_a63924c5e9d5.Data2
         || *(_DWORD *)(v16 + 24LL * v14 + 8) != *(_DWORD *)GUID_3689bdc8_b205_4af4_8d4a_a63924c5e9d5.Data4
         || *(_DWORD *)(v16 + 24LL * v14 + 12) != *(_DWORD *)&GUID_3689bdc8_b205_4af4_8d4a_a63924c5e9d5.Data4[4] )
    {
      if ( ++v14 >= v15 )
        goto LABEL_32;
    }
    if ( CUpdate::IsUUPUpdate(this, a2) )
      *((_DWORD *)this + 244) = 3;
    else
LABEL_32:
      *((_DWORD *)this + 244) = 0;
  }
  *((_WORD *)this + 319) = -((*((_DWORD *)a2 + 47) & 1) != 0);
  *((_QWORD *)this + 54) = *((_QWORD *)a2 + 20);
  *((_QWORD *)this + 55) = *((_QWORD *)a2 + 19);
  *((_QWORD *)this + 56) = *((_QWORD *)this + 99);
  v17 = *((_DWORD *)a2 + 42);
  if ( v17 > 0x7FFFFFFF )
    v17 = 0x7FFFFFFF;
  *((_DWORD *)this + 102) = v17;
  v18 = *((_DWORD *)a2 + 44);
  if ( v18 > 0x7FFFFFFF )
    v18 = 0x7FFFFFFF;
  *((_DWORD *)this + 103) = v18;
  v19 = *((_DWORD *)a2 + 43);
  if ( v19 > 0x7FFFFFFF )
    v19 = 0x7FFFFFFF;
  *((_DWORD *)this + 104) = v19;
  *((_WORD *)this + 310) = -(*((_DWORD *)a2 + 48) != 0);
  *((_WORD *)this + 311) = -(*((_DWORD *)a2 + 49) != 0);
  *((_WORD *)this + 307) = -(*((_DWORD *)a2 + 50) != 0);
  if ( (*((_BYTE *)a2 + 132) & 1) != 0 )
  {
    v20 = *((_QWORD *)this + 62);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v20 + 8) + 16LL))(v20 + 8);
    *((_QWORD *)this + 62) = 0;
    v74[0] = 0;
    Instance = ATL::CComObject<CInstallationBehavior>::CreateInstance(v74);
    if ( Instance < 0 )
    {
      v10 = 3731;
      goto LABEL_186;
    }
    v21 = v74[0];
    (*(void (__fastcall **)(char *))(*((_QWORD *)v74[0] + 1) + 8LL))((char *)v74[0] + 8);
    *((_QWORD *)this + 62) = v21;
    *((_QWORD *)v21 + 6) = *(_QWORD *)((char *)a2 + 124);
    *((_DWORD *)v21 + 14) = *((_DWORD *)a2 + 33);
  }
  if ( (*((_BYTE *)a2 + 144) & 1) != 0 )
  {
    v22 = *((_QWORD *)this + 63);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v22 + 8) + 16LL))(v22 + 8);
    *((_QWORD *)this + 63) = 0;
    v74[0] = 0;
    Instance = ATL::CComObject<CInstallationBehavior>::CreateInstance(v74);
    if ( Instance < 0 )
    {
      v10 = 3741;
      goto LABEL_186;
    }
    v23 = v74[0];
    (*(void (__fastcall **)(char *))(*((_QWORD *)v74[0] + 1) + 8LL))((char *)v74[0] + 8);
    *((_QWORD *)this + 63) = v23;
    *((_QWORD *)v23 + 6) = *((_QWORD *)a2 + 17);
    *((_DWORD *)v23 + 14) = *((_DWORD *)a2 + 36);
  }
  if ( *(_QWORD *)(*((_QWORD *)a2 + 55) + 48LL) )
  {
    v24 = *((_QWORD *)this + 61);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v24 + 8) + 16LL))(v24 + 8);
    *((_QWORD *)this + 61) = 0;
    v74[0] = 0;
    Instance = ATL::CComObject<CImageInformation>::CreateInstance(v74);
    if ( Instance < 0 )
    {
      v10 = 3751;
      goto LABEL_186;
    }
    v25 = v74[0];
    (*(void (__fastcall **)(char *))(*((_QWORD *)v74[0] + 1) + 8LL))((char *)v74[0] + 8);
    *((_QWORD *)this + 61) = v25;
    Instance = CImageInformation::Initialize(v25, (const struct tagDSLocImage *)(*((_QWORD *)a2 + 55) + 48LL));
    if ( Instance < 0 )
    {
      v10 = 3754;
      goto LABEL_186;
    }
  }
  SysFreeString(*((BSTR *)this + 42));
  *((_QWORD *)this + 42) = 0;
  Instance = SusSysAllocString(*(const wchar_t **)(*((_QWORD *)a2 + 55) + 16LL), (wchar_t **)this + 42);
  if ( Instance < 0 )
  {
    v10 = 3758;
    goto LABEL_186;
  }
  SysFreeString(*((BSTR *)this + 47));
  *((_QWORD *)this + 47) = 0;
  Instance = SusSysAllocString(*(const wchar_t **)(*((_QWORD *)a2 + 55) + 8LL), (wchar_t **)this + 47);
  if ( Instance < 0 )
  {
    v10 = 3760;
    goto LABEL_186;
  }
  v26 = *((_QWORD *)this + 60);
  *(_OWORD *)(v26 + 40) = *(_OWORD *)((char *)a2 + 4);
  *(_DWORD *)(v26 + 56) = *((_DWORD *)a2 + 5);
  Instance = CStringCollection::Initialize(
               *((CStringCollection **)this + 65),
               *((wchar_t ***)a2 + 51),
               *((unsigned int *)a2 + 100));
  if ( Instance < 0 )
  {
    v10 = 3762;
    goto LABEL_186;
  }
  v27 = *((_QWORD *)a2 + 55);
  v28 = *(_DWORD *)(v27 + 72);
  if ( v28 )
  {
    v29 = *(wchar_t ***)(v27 + 80);
  }
  else
  {
    v29 = (wchar_t **)*((_QWORD *)a2 + 29);
    v28 = *((_DWORD *)a2 + 56);
  }
  Instance = CStringCollection::Initialize(*((CStringCollection **)this + 66), v29, v28);
  if ( Instance < 0 )
  {
    v10 = 3767;
    goto LABEL_186;
  }
  Instance = CStringCollection::Initialize(
               *((CStringCollection **)this + 67),
               *((wchar_t ***)a2 + 31),
               *((unsigned int *)a2 + 60));
  if ( Instance < 0 )
  {
    v10 = 3768;
    goto LABEL_186;
  }
  Instance = CStringCollection::Initialize(
               *((CStringCollection **)this + 68),
               *((wchar_t ***)a2 + 35),
               *((unsigned int *)a2 + 68));
  if ( Instance < 0 )
  {
    v10 = 3769;
    goto LABEL_186;
  }
  Instance = CStringCollection::Initialize(
               *((CStringCollection **)this + 69),
               *((wchar_t ***)a2 + 33),
               *((unsigned int *)a2 + 64));
  if ( Instance < 0 )
  {
    v10 = 3770;
    goto LABEL_186;
  }
  v30 = (const WCHAR **)((char *)this + 344);
  SysFreeString(*((BSTR *)this + 43));
  *((_QWORD *)this + 43) = 0;
  Instance = SusSysAllocString(*((const wchar_t **)a2 + 48), (wchar_t **)this + 43);
  if ( Instance < 0 )
  {
    v10 = 3772;
    goto LABEL_186;
  }
  SysFreeString(*((BSTR *)this + 44));
  *((_QWORD *)this + 44) = 0;
  Instance = SusSysAllocString(*((const wchar_t **)a2 + 26), (wchar_t **)this + 44);
  if ( Instance < 0 )
  {
    v10 = 3774;
    goto LABEL_186;
  }
  SysFreeString(*((BSTR *)this + 45));
  *((_QWORD *)this + 45) = 0;
  Instance = SusSysAllocString(*(const wchar_t **)(*((_QWORD *)a2 + 55) + 24LL), (wchar_t **)this + 45);
  if ( Instance < 0 )
  {
    v10 = 3776;
    goto LABEL_186;
  }
  SysFreeString(*((BSTR *)this + 46));
  *((_QWORD *)this + 46) = 0;
  v31 = *(const wchar_t **)(*((_QWORD *)a2 + 55) + 40LL);
  if ( !v31 )
    v31 = (const wchar_t *)*((_QWORD *)a2 + 27);
  Instance = SusSysAllocString(v31, (wchar_t **)this + 46);
  if ( Instance < 0 )
  {
    v10 = 3781;
    goto LABEL_186;
  }
  SysFreeString(*((BSTR *)this + 48));
  *((_QWORD *)this + 48) = 0;
  Instance = SusSysAllocString(*(const wchar_t **)(*((_QWORD *)a2 + 55) + 32LL), (wchar_t **)this + 48);
  if ( Instance < 0 )
  {
    v10 = 3783;
    goto LABEL_186;
  }
  Instance = CStringCollection::Initialize(
               *((CStringCollection **)this + 71),
               *(wchar_t ***)(*((_QWORD *)a2 + 55) + 96LL),
               *(unsigned int *)(*((_QWORD *)a2 + 55) + 88LL));
  if ( Instance < 0 )
  {
    v10 = 3785;
    goto LABEL_186;
  }
  SysFreeString(*((BSTR *)this + 123));
  *((_QWORD *)this + 123) = 0;
  Instance = SusSysAllocString(*((const wchar_t **)a3 + 13), (wchar_t **)this + 123);
  if ( Instance < 0 )
  {
    v10 = 3787;
    goto LABEL_186;
  }
  SysFreeString(*((BSTR *)this + 124));
  *((_QWORD *)this + 124) = 0;
  Instance = SusSysAllocString(*((const wchar_t **)a3 + 15), (wchar_t **)this + 124);
  if ( Instance < 0 )
  {
    v10 = 3789;
    goto LABEL_186;
  }
  v33 = 1;
  if ( !*((_DWORD *)this + 226) )
  {
    v32 = *v30;
    if ( *v30 != L"http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/SingleStageAppX"
      && (!v32
       || CompareStringW(
            0x7Fu,
            1u,
            v32,
            -1,
            L"http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/SingleStageAppX",
            -1) != 2) )
    {
      v33 = 0;
    }
  }
  *((_BYTE *)this + 1000) = v33;
  v34 = *((_DWORD *)a3 + 23);
  *((_WORD *)this + 315) = (v34 != 1) - 1;
  Instance = -2147024882;
  if ( v34 == 1 )
  {
    *((_DWORD *)this + 144) = 2;
    v35 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 81);
    if ( v35 )
      (**v35)(v35, 1);
    *((_QWORD *)this + 81) = 0;
    ProcessHeap = GetProcessHeap();
    v37 = HeapAlloc(ProcessHeap, 0, 0x48u);
    v38 = v37;
    v78 = (struct _FILETIME)v37;
    if ( !v37 )
    {
      *((_QWORD *)this + 81) = 0;
      v10 = 3811;
      goto LABEL_186;
    }
    memset_0(v37, 0, 0x48u);
    *v38 = &CUpdate::CWindowsDriverInfo::`vftable';
    v38[1] = 0;
    v38[2] = 0;
    v38[3] = 0;
    v38[4] = 0;
    v38[5] = 0;
    v38[6] = 0;
    v38[7] = 0;
    v38[8] = 0;
    *((_QWORD *)this + 81) = v38;
    v78 = (struct _FILETIME)*((_QWORD *)a3 + 2);
    LODWORD(v74[0]) = *((_DWORD *)a2 + 46) & 0xC0;
    v39 = (CImageInformation *)SafeSusAllocArray(0x1F4u, 2u);
    v74[1] = v39;
    v40 = v39 == 0 ? 0x8007000E : 0;
    if ( !v39 )
    {
      v41 = 3821;
LABEL_109:
      v45 = v40;
      goto LABEL_112;
    }
    LocResourceInstance = CModuleResHelper::GetLocResourceInstance((CModuleResHelper *)&qword_1800EEF18);
    v40 = ConstructTitleForIDPParent(LocResourceInstance, v43, v44, &v78, (int)v74[0], (wchar_t *)v39, v73);
    if ( (v40 & 0x80000000) != 0 )
    {
      v41 = 3829;
      goto LABEL_109;
    }
    WUTrace(0, 0, 0x10000, 5, 0, L"ConstructTitleForIDPParent succeeded");
    SysFreeString(*((BSTR *)this + 47));
    *((_QWORD *)this + 47) = 0;
    v46 = SusSysAllocString((const wchar_t *)v39, (wchar_t **)this + 47);
    v40 = v46;
    if ( v46 < 0 )
    {
      v45 = (unsigned int)v46;
      v41 = 3834;
LABEL_112:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)v45,
        (int)lpString2);
      if ( v39 )
        SusFree(v39);
      goto LABEL_187;
    }
    SusFree(v39);
    SysFreeString(*((BSTR *)this + 42));
    *((_QWORD *)this + 42) = 0;
    v47 = CModuleResHelper::GetLocResourceInstance((CModuleResHelper *)&qword_1800EEF18);
    StringAllocW = LoadStringAllocW(v47, 63531, AllocBstr, (wchar_t **)this + 42);
    v40 = StringAllocW;
    if ( StringAllocW < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\LoadString.cpp",
        (const char *)(unsigned int)StringAllocW,
        (int)lpString2);
      v49 = v40;
      v50 = 3841;
LABEL_181:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)v49,
        (int)lpString2);
      goto LABEL_187;
    }
  }
  refreshed = CUpdateDownloadContentCollection::Initialize(
                *((CUpdateDownloadContentCollection **)this + 64),
                *((const struct tagDSFile **)a2 + 59),
                *((unsigned int *)a2 + 116),
                *((const struct tagDSEulaFile_V2 **)a2 + 57),
                *((unsigned int *)a2 + 112));
  v40 = refreshed;
  if ( refreshed < 0 )
  {
    v50 = 3845;
LABEL_180:
    v49 = (unsigned int)refreshed;
    goto LABEL_181;
  }
  v52 = *((unsigned int *)a2 + 120);
  if ( (_DWORD)v52 )
  {
    if ( lpMem )
    {
      SusFree(lpMem);
      lpMem = 0;
    }
    v53 = SafeSusAllocArray(v52, 8u);
    lpMem = v53;
    v40 = v53 == 0 ? 0x8007000E : 0;
    v54 = 0;
    if ( !v53 )
    {
      v49 = v40;
      v50 = 3849;
      goto LABEL_181;
    }
    v74[2] = a2;
    v74[3] = (CImageInformation *)&lpMem;
    v75 = 1;
    v55 = *((_DWORD *)a2 + 120);
    if ( v55 )
    {
      while ( 1 )
      {
        v56 = UuidToStringW((const UUID *)(*((_QWORD *)a2 + 61) + 16LL * v54), (RPC_WSTR *)v53 + v54);
        if ( v56 )
          break;
        ++v54;
        v55 = *((_DWORD *)a2 + 120);
        v53 = lpMem;
        if ( v54 >= v55 )
          goto LABEL_127;
      }
      v40 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xF15,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
              (const char *)v56,
              (unsigned int)lpString2);
      goto LABEL_129;
    }
LABEL_127:
    v57 = CStringCollection::Initialize(*((CStringCollection **)this + 70), (wchar_t **)v53, v55);
    v40 = v57;
    if ( v57 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF19,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)(unsigned int)v57,
        (int)lpString2);
LABEL_129:
      for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 120); i = (unsigned int)(i + 1) )
        RpcStringFreeW((RPC_WSTR *)lpMem + i);
      goto LABEL_187;
    }
    for ( j = 0; j < *((_DWORD *)a2 + 120); ++j )
      RpcStringFreeW((RPC_WSTR *)lpMem + j);
  }
  *((_DWORD *)this + 264) = *((_DWORD *)a3 + 6);
  switch ( *(_DWORD *)a3 )
  {
    case 1:
      *((_DWORD *)this + 230) = 4;
      break;
    case 2:
      *((_DWORD *)this + 230) = 1;
      break;
    case 3:
      *((_DWORD *)this + 230) = 2;
      break;
    case 4:
      *((_DWORD *)this + 230) = 3;
      break;
    default:
      *((_DWORD *)this + 230) = 0;
      break;
  }
  if ( *((_DWORD *)a3 + 1) == 1 )
  {
    *((_DWORD *)this + 231) = 1;
  }
  else if ( *((_DWORD *)a3 + 1) == 3 )
  {
    *((_DWORD *)this + 231) = 3;
  }
  else
  {
    *((_DWORD *)this + 231) = 2;
  }
  switch ( *((_DWORD *)a3 + 12) )
  {
    case 1:
      *((_DWORD *)this + 232) = 1;
      break;
    case 2:
      *((_DWORD *)this + 232) = 2;
      break;
    case 3:
      *((_DWORD *)this + 232) = 3;
      break;
    default:
      *((_DWORD *)this + 232) = 0;
      break;
  }
  if ( *((_DWORD *)a3 + 13) == 1 )
  {
    *((_DWORD *)this + 233) = 1;
  }
  else if ( *((_DWORD *)a3 + 13) == 2 )
  {
    *((_DWORD *)this + 233) = 2;
  }
  else
  {
    *((_DWORD *)this + 233) = 0;
  }
  v60 = *((_DWORD *)a2 + 46);
  if ( *((_DWORD *)a3 + 8) || (*((_DWORD *)a2 + 20) != 4 || (v60 & 0x18) != 0) && (v60 & 4) == 0 )
    v61 = 0;
  else
    v61 = -1;
  *((_WORD *)this + 317) = v61;
  *((_QWORD *)this + 127) = *((_QWORD *)a2 + 45);
  SysFreeString(*((BSTR *)this + 126));
  *((_QWORD *)this + 126) = 0;
  refreshed = SusSysAllocString(*((const wchar_t **)a2 + 44), (wchar_t **)this + 126);
  v40 = refreshed;
  if ( refreshed < 0 )
  {
    v50 = 3946;
    goto LABEL_180;
  }
  v62 = (const OLECHAR *)*((_QWORD *)a3 + 19);
  SysFreeString(*((BSTR *)this + 134));
  *((_QWORD *)this + 134) = 0;
  if ( v62 )
  {
    v63 = SysAllocString(v62);
    *((_QWORD *)this + 134) = v63;
    if ( !v63 )
    {
      v10 = 3948;
      goto LABEL_186;
    }
  }
  v64 = (const OLECHAR *)*((_QWORD *)a3 + 18);
  SysFreeString(*((BSTR *)this + 133));
  *((_QWORD *)this + 133) = 0;
  if ( v64 )
  {
    v65 = SysAllocString(v64);
    *((_QWORD *)this + 133) = v65;
    if ( !v65 )
    {
      v10 = 3949;
      goto LABEL_186;
    }
  }
  v66 = (const OLECHAR *)*((_QWORD *)a3 + 20);
  SysFreeString(*((BSTR *)this + 135));
  *((_QWORD *)this + 135) = 0;
  if ( v66 )
  {
    v67 = SysAllocString(v66);
    *((_QWORD *)this + 135) = v67;
    LODWORD(v66) = 0;
    if ( !v67 )
    {
      v10 = 3950;
      goto LABEL_186;
    }
  }
  refreshed = CUpdate::RefreshUpdateStickyState(this);
  v40 = refreshed;
  if ( refreshed < 0 )
  {
    v50 = 3952;
    goto LABEL_180;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_OutOfScopeExemptUpdates>::GetImpl'::`2'::impl,
                          v68,
                          v69,
                          v70) )
    *((_WORD *)this + 320) = !IsUpdateOutOfScopeExempt((CUpdate *)((char *)this + 688)) - 1;
  v40 = (unsigned int)v66;
LABEL_187:
  if ( lpMem )
    SusFree(lpMem);
  return v40;
}

```

## disassembly

```asm
0x18005759c  mov     [rsp-8+arg_18], rbx
0x1800575a1  push    rbp
0x1800575a2  push    rsi
0x1800575a3  push    rdi
0x1800575a4  push    r12
0x1800575a6  push    r13
0x1800575a8  push    r14
0x1800575aa  push    r15
0x1800575ac  lea     rbp, [rsp-10h]
0x1800575b1  sub     rsp, 110h
0x1800575b8  mov     rax, cs:__security_cookie
0x1800575bf  xor     rax, rsp
0x1800575c2  mov     [rbp+40h+var_40], rax
0x1800575c6  mov     r13, r8
0x1800575c9  mov     rsi, rdx
0x1800575cc  mov     rdi, rcx
0x1800575cf  xor     ebx, ebx
0x1800575d1  mov     [rbp+40h+lpMem], rbx
0x1800575d5  xorps   xmm0, xmm0
0x1800575d8  movups  xmmword ptr [rbp+40h+SystemTime.wYear], xmm0
0x1800575dc  lea     rcx, [rbp+40h+SystemTime]; lpSystemTime
0x1800575e0  call    cs:__imp_GetSystemTime
0x1800575e6  lea     rdx, [rdi+190h]; pvtime
0x1800575ed  lea     rcx, [rbp+40h+SystemTime]; lpSystemTime
0x1800575f1  call    cs:__imp_SystemTimeToVariantTime
0x1800575f7  mov     ecx, eax
0x1800575f9  lea     r14d, [rbx+1]
0x1800575fd  sub     ecx, r14d
0x180057600  neg     ecx
0x180057602  sbb     r9d, r9d
0x180057605  and     r9d, 80240FFFh; char *
0x18005760c  mov     rcx, [rbp+48h]; this
0x180057610  lea     r12, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180057617  cmp     eax, r14d
0x18005761a  jz      short loc_180057629
0x18005761c  mov     r8, r12; unsigned int
0x18005761f  mov     edx, 0E39h; void *
0x180057624  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180057629  mov     eax, [rsi+1Ch]
0x18005762c  mov     ecx, 0F00h
0x180057631  and     eax, ecx
0x180057633  mov     r15d, 8024001Dh
0x180057639  cmp     eax, ecx
0x18005763b  jz      short loc_18005767D
0x18005763d  lea     rdx, [rsi+4]; struct tagDSGlobalUpdateId *
0x180057641  lea     rcx, [rsp+140h+var_D0]; this
0x180057646  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18005764b  mov     [rsp+140h+var_110], rax
0x180057650  lea     rax, aUpdateMetadata; "Update metadata for %ws is missing core"...
0x180057657  mov     qword ptr [rsp+140h+cchCount2], rax
0x18005765c  mov     dword ptr [rsp+140h+lpString2], r15d
0x180057661  mov     r9d, r14d
0x180057664  xor     edx, edx
0x180057666  xor     ecx, ecx
0x180057668  mov     r8d, 10000h
0x18005766e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180057673  mov     edx, 0E44h
0x180057678  jmp     loc_180058466
0x18005767d  cmp     [rsi+1B0h], ebx
0x180057683  jbe     loc_180058461
0x180057689  cmp     [rsi+1B8h], rbx
0x180057690  jz      loc_180058461
0x180057696  cmp     [rsi+1E0h], ebx
0x18005769c  jbe     short loc_1800576B1
0x18005769e  cmp     [rsi+1E8h], rbx
0x1800576a5  jnz     short loc_1800576B1
0x1800576a7  mov     edx, 0E48h
0x1800576ac  jmp     loc_180058466
0x1800576b1  cmp     [r13+1Ch], ebx
0x1800576b5  jz      short loc_1800576E1
0x1800576b7  lea     rdx, [rdi+250h]
0x1800576be  lea     rcx, [r13+8]
0x1800576c2  call    FileTimeToVariantTime
0x1800576c7  mov     r15d, eax
0x1800576ca  test    eax, eax
0x1800576cc  jns     short loc_1800576D8
0x1800576ce  mov     edx, 0E4Eh
0x1800576d3  jmp     loc_180058466
0x1800576d8  mov     word ptr [rdi+248h], 7
0x1800576e1  lea     rcx, [r13+10h]
0x1800576e5  lea     rdx, [rdi+188h]
0x1800576ec  call    FileTimeToVariantTime
0x1800576f1  mov     r15d, eax
0x1800576f4  test    eax, eax
0x1800576f6  jns     short loc_180057702
0x1800576f8  mov     edx, 0E52h
0x1800576fd  jmp     loc_180058466
0x180057702  or      eax, 0FFFFFFFFh
0x180057705  cmp     ax, [rdi+270h]
0x18005770c  jnz     short loc_180057717
0x18005770e  test    [rsi+90h], r14b
0x180057715  jnz     short loc_180057719
0x180057717  mov     eax, ebx
0x180057719  mov     [rdi+272h], ax
0x180057720  mov     ecx, [rsi+1C0h]
0x180057726  mov     eax, ebx
0x180057728  test    ecx, ecx
0x18005772a  setnz   al
0x18005772d  mov     [rdi+1A4h], eax
0x180057733  test    ecx, ecx
0x180057735  jz      short loc_180057764
0x180057737  movups  xmm0, xmmword ptr [rsi+1A0h]
0x18005773e  movdqu  xmmword ptr [rdi+290h], xmm0
0x180057746  mov     eax, [rsi+0CCh]
0x18005774c  mov     [rdi+1ACh], eax
0x180057752  mov     eax, ebx
0x180057754  cmp     [rsi+94h], r14d
0x18005775b  setz    al
0x18005775e  mov     [rdi+1A8h], eax
0x180057764  mov     eax, [rsi+58h]
0x180057767  neg     eax
0x180057769  sbb     cx, cx
0x18005776c  mov     [rdi+260h], cx
0x180057773  mov     eax, [rsi+0B8h]
0x180057779  and     al, 4
0x18005777b  neg     al
0x18005777d  sbb     ax, ax
0x180057780  mov     [rdi+262h], ax
0x180057787  mov     eax, [rsi+0B8h]
0x18005778d  and     al, 20h
0x18005778f  neg     al
0x180057791  sbb     ax, ax
0x180057794  mov     [rdi+264h], ax
0x18005779b  mov     eax, [rsi+0B8h]
0x1800577a1  and     eax, 100h
0x1800577a6  neg     eax
0x1800577a8  sbb     ax, ax
0x1800577ab  mov     [rdi+278h], ax
0x1800577b2  mov     eax, [rsi+0B8h]
0x1800577b8  bt      eax, 0Bh
0x1800577bc  jnb     short loc_1800577CA
0x1800577be  mov     dword ptr [rdi+3D0h], 2
0x1800577c8  jmp     short loc_18005783B
0x1800577ca  bt      eax, 0Ch
0x1800577ce  jnb     short loc_1800577D9
0x1800577d0  mov     [rdi+3D0h], r14d
0x1800577d7  jmp     short loc_18005783B
0x1800577d9  mov     r8d, ebx
0x1800577dc  mov     r9d, [rsi+1F0h]
0x1800577e3  test    r9d, r9d
0x1800577e6  jz      short loc_180057835
0x1800577e8  mov     rdx, [rsi+1F8h]
0x1800577ef  mov     r10d, dword ptr cs:_GUID_3689bdc8_b205_4af4_8d4a_a63924c5e9d5.Data4+4
0x1800577f6  mov     r11d, dword ptr cs:_GUID_3689bdc8_b205_4af4_8d4a_a63924c5e9d5.Data4
0x1800577fd  mov     ebx, dword ptr cs:_GUID_3689bdc8_b205_4af4_8d4a_a63924c5e9d5.Data2
0x180057803  mov     eax, r8d
0x180057806  lea     rcx, [rax+rax*2]
0x18005780a  cmp     dword ptr [rdx+rcx*8], 3689BDC8h
0x180057811  jnz     short loc_18005782B
0x180057813  cmp     [rdx+rcx*8+4], ebx
0x180057817  jnz     short loc_18005782B
0x180057819  cmp     [rdx+rcx*8+8], r11d
0x18005781e  jnz     short loc_18005782B
0x180057820  cmp     [rdx+rcx*8+0Ch], r10d
0x180057825  jz      loc_180057938
0x18005782b  add     r8d, r14d
0x18005782e  cmp     r8d, r9d
0x180057831  jb      short loc_180057803
0x180057833  xor     ebx, ebx
0x180057835  mov     [rdi+3D0h], ebx
0x18005783b  mov     eax, [rsi+0BCh]
0x180057841  and     al, r14b
0x180057844  neg     al
0x180057846  sbb     ax, ax
0x180057849  mov     [rdi+27Eh], ax
0x180057850  mov     rax, [rsi+0A0h]
0x180057857  mov     [rdi+1B0h], rax
0x18005785e  mov     rax, [rsi+98h]
0x180057865  mov     [rdi+1B8h], rax
0x18005786c  mov     rax, [rdi+318h]
0x180057873  mov     [rdi+1C0h], rax
0x18005787a  mov     eax, [rsi+0A8h]
0x180057880  mov     ecx, 7FFFFFFFh
0x180057885  cmp     eax, ecx
0x180057887  cmova   eax, ecx
0x18005788a  mov     [rdi+198h], eax
0x180057890  mov     eax, [rsi+0B0h]
0x180057896  cmp     eax, ecx
0x180057898  cmova   eax, ecx
0x18005789b  mov     [rdi+19Ch], eax
0x1800578a1  mov     eax, [rsi+0ACh]
0x1800578a7  cmp     eax, ecx
0x1800578a9  cmova   eax, ecx
0x1800578ac  mov     [rdi+1A0h], eax
0x1800578b2  mov     eax, [rsi+0C0h]
0x1800578b8  neg     eax
0x1800578ba  sbb     cx, cx
0x1800578bd  mov     [rdi+26Ch], cx
0x1800578c4  mov     eax, [rsi+0C4h]
0x1800578ca  neg     eax
0x1800578cc  sbb     cx, cx
0x1800578cf  mov     [rdi+26Eh], cx
0x1800578d6  mov     eax, [rsi+0C8h]
0x1800578dc  neg     eax
0x1800578de  sbb     cx, cx
0x1800578e1  mov     [rdi+266h], cx
0x1800578e8  test    [rsi+84h], r14b
0x1800578ef  jz      loc_18005798D
0x1800578f5  mov     rcx, [rdi+1F0h]
0x1800578fc  test    rcx, rcx
0x1800578ff  jz      short loc_180057911
0x180057901  add     rcx, 8
0x180057905  mov     rax, [rcx]
0x180057908  mov     rax, [rax+10h]
0x18005790c  call    _guard_dispatch_icall
0x180057911  mov     [rdi+1F0h], rbx
0x180057918  mov     [rsp+140h+var_100], rbx
0x18005791d  lea     rcx, [rsp+140h+var_100]
0x180057922  call    ?CreateInstance@?$CComObject@VCInstallationBehavior@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInstallationBehavior>::CreateInstance(ATL::CComObject<CInstallationBehavior> * *)
0x180057927  mov     r15d, eax
0x18005792a  test    eax, eax
0x18005792c  jns     short loc_18005795C
0x18005792e  mov     edx, 0E93h
0x180057933  jmp     loc_180058466
0x180057938  mov     rdx, rsi; struct tagDSUpdateMetadata *
0x18005793b  mov     rcx, rdi; this
0x18005793e  call    ?IsUUPUpdate@CUpdate@@AEAA_NAEBUtagDSUpdateMetadata@@@Z; CUpdate::IsUUPUpdate(tagDSUpdateMetadata const &)
0x180057943  xor     ebx, ebx
0x180057945  test    al, al
0x180057947  jz      loc_180057835
0x18005794d  mov     dword ptr [rdi+3D0h], 3
0x180057957  jmp     loc_18005783B
0x18005795c  mov     rbx, [rsp+140h+var_100]
0x180057961  lea     rcx, [rbx+8]
0x180057965  mov     rax, [rcx]
0x180057968  mov     rax, [rax+8]
0x18005796c  call    _guard_dispatch_icall
0x180057971  mov     [rdi+1F0h], rbx
0x180057978  movsd   xmm0, qword ptr [rsi+7Ch]
0x18005797d  movsd   qword ptr [rbx+30h], xmm0
0x180057982  mov     eax, [rsi+84h]
0x180057988  mov     [rbx+38h], eax
0x18005798b  xor     ebx, ebx
0x18005798d  test    [rsi+90h], r14b
0x180057994  jz      short loc_180057A0D
0x180057996  mov     rcx, [rdi+1F8h]
0x18005799d  test    rcx, rcx
0x1800579a0  jz      short loc_1800579B2
0x1800579a2  add     rcx, 8
0x1800579a6  mov     rax, [rcx]
0x1800579a9  mov     rax, [rax+10h]
0x1800579ad  call    _guard_dispatch_icall
0x1800579b2  mov     [rdi+1F8h], rbx
0x1800579b9  mov     [rsp+140h+var_100], rbx
0x1800579be  lea     rcx, [rsp+140h+var_100]
0x1800579c3  call    ?CreateInstance@?$CComObject@VCInstallationBehavior@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CInstallationBehavior>::CreateInstance(ATL::CComObject<CInstallationBehavior> * *)
0x1800579c8  mov     r15d, eax
0x1800579cb  test    eax, eax
0x1800579cd  jns     short loc_1800579D9
0x1800579cf  mov     edx, 0E9Dh
0x1800579d4  jmp     loc_180058466
0x1800579d9  mov     rbx, [rsp+140h+var_100]
0x1800579de  lea     rcx, [rbx+8]
0x1800579e2  mov     rax, [rcx]
0x1800579e5  mov     rax, [rax+8]
0x1800579e9  call    _guard_dispatch_icall
0x1800579ee  mov     [rdi+1F8h], rbx
0x1800579f5  movsd   xmm0, qword ptr [rsi+88h]
0x1800579fd  movsd   qword ptr [rbx+30h], xmm0
0x180057a02  mov     eax, [rsi+90h]
0x180057a08  mov     [rbx+38h], eax
0x180057a0b  xor     ebx, ebx
0x180057a0d  mov     rax, [rsi+1B8h]
0x180057a14  cmp     [rax+30h], rbx
0x180057a18  jz      loc_180057AA1
0x180057a1e  mov     rcx, [rdi+1E8h]
0x180057a25  test    rcx, rcx
0x180057a28  jz      short loc_180057A3A
0x180057a2a  add     rcx, 8
0x180057a2e  mov     rax, [rcx]
0x180057a31  mov     rax, [rax+10h]
0x180057a35  call    _guard_dispatch_icall
0x180057a3a  mov     [rdi+1E8h], rbx
0x180057a41  mov     [rsp+140h+var_100], rbx
0x180057a46  lea     rcx, [rsp+140h+var_100]
0x180057a4b  call    ?CreateInstance@?$CComObject@VCImageInformation@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CImageInformation>::CreateInstance(ATL::CComObject<CImageInformation> * *)
0x180057a50  mov     r15d, eax
0x180057a53  test    eax, eax
0x180057a55  jns     short loc_180057A61
0x180057a57  mov     edx, 0EA7h
0x180057a5c  jmp     loc_180058466
0x180057a61  mov     rbx, [rsp+140h+var_100]
0x180057a66  lea     rcx, [rbx+8]
0x180057a6a  mov     rax, [rcx]
0x180057a6d  mov     rax, [rax+8]
0x180057a71  call    _guard_dispatch_icall
0x180057a76  mov     [rdi+1E8h], rbx
0x180057a7d  mov     rdx, [rsi+1B8h]
0x180057a84  add     rdx, 30h ; '0'; struct tagDSLocImage *
0x180057a88  mov     rcx, rbx; this
0x180057a8b  call    ?Initialize@CImageInformation@@QEAAJAEBUtagDSLocImage@@@Z; CImageInformation::Initialize(tagDSLocImage const &)
0x180057a90  mov     r15d, eax
0x180057a93  test    eax, eax
0x180057a95  jns     short loc_180057AA1
0x180057a97  mov     edx, 0EAAh
0x180057a9c  jmp     loc_180058466
0x180057aa1  lea     rbx, [rdi+150h]
0x180057aa8  mov     rcx, [rbx]; bstrString
0x180057aab  call    cs:__imp_SysFreeString
0x180057ab1  mov     qword ptr [rbx], 0
  ... truncated ...
```
