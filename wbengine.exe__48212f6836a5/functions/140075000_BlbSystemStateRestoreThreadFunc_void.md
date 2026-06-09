# BlbSystemStateRestoreThreadFunc(void *)

- ea: `0x140075000`
- end: `0x140075c64`
- name: `?BlbSystemStateRestoreThreadFunc@@YAKPEAX@Z`
- size: `3172`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `34`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x140006ca8`
- `0x14000aee8`
- `0x14000b0bc`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x140013008`
- `0x140014200`
- `0x140014260`
- `0x14003c69c`
- `0x140075000`
- `0x140075c6c`
- `0x140075d00`
- `0x140076c6c`
- `0x140077044`
- `0x140077844`
- `0x1400778d8`
- `0x140077a78`
- `0x1400787f0`
- `0x140078884`
- `0x140078aa8`
- `0x140078b24`
- `0x140078c18`
- `0x140082700`
- `0x14008271c`
- `0x1400889f0`
- `0x14008fed0`
- `0x1400d7e48`
- `0x1400f07dc`
- `0x14011ae40`
- `0x14011b1a8`
- `0x14011cf98`
- `0x14011d420`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x140075083`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140075741`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140075083`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140075741`
- `KERNEL32!LeaveCriticalSection` at `0x140075a12`
- `KERNEL32!LeaveCriticalSection` at `0x140075a12`
- `KERNEL32!EnterCriticalSection` at `0x1400759e5`
- `KERNEL32!EnterCriticalSection` at `0x1400759e5`
- `ole32!CoTaskMemFree` at `0x1400757f2`
- `ole32!CoTaskMemFree` at `0x140075816`
- `ole32!CoTaskMemFree` at `0x140075860`
- `ole32!CoTaskMemFree` at `0x14007590b`
- `ole32!CoTaskMemFree` at `0x14007592d`
- `ole32!CoTaskMemFree` at `0x14007594e`
- `ole32!CoTaskMemFree` at `0x14007597c`
- `ole32!CoTaskMemFree` at `0x140075992`
- `ole32!CoTaskMemFree` at `0x1400757f2`
- `ole32!CoTaskMemFree` at `0x140075816`
- `ole32!CoTaskMemFree` at `0x140075860`
- `ole32!CoTaskMemFree` at `0x14007590b`
- `ole32!CoTaskMemFree` at `0x14007592d`
- `ole32!CoTaskMemFree` at `0x14007594e`
- `ole32!CoTaskMemFree` at `0x14007597c`
- `ole32!CoTaskMemFree` at `0x140075992`
- `ole32!CoInitializeEx` at `0x140075160`
- `ole32!CoInitializeEx` at `0x140075160`
- `ole32!CoUninitialize` at `0x1400759a1`
- `ole32!CoUninitialize` at `0x1400759a1`
- `OLEAUT32!__imp_SysFreeString` at `0x140075156`
- `OLEAUT32!__imp_SysFreeString` at `0x140075156`

## string_xrefs

- `0x1400752c1`: `base\stor\blb\engine\service\systemstaterestore.cpp`
- `0x140075320`: `base\stor\blb\engine\service\systemstaterestore.cpp`

## pseudocode

```c
__int64 __fastcall BlbSystemStateRestoreThreadFunc(char *Parameter)
{
  char v2; // bl
  struct CBlbEngine *v3; // r12
  struct IBlbsrvSystemStateRestore *v4; // r13
  __int64 v5; // r8
  unsigned __int16 *v6; // rax
  unsigned int v7; // r9d
  struct _FILETIME v8; // rcx
  PVOID *v9; // rax
  ATL::CComBSTR *v10; // rax
  unsigned int v11; // edi
  int IsClientSKU; // r14d
  char v13; // si
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rax
  int StagingDirectory; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  char *v25; // rbx
  CBlbSystemStateRestoreAsync *v26; // rcx
  int v27; // eax
  CBlbSystemStateRestoreAsync *v28; // rcx
  __int64 v29; // rdx
  CBlbSystemStateRestoreAsync *v30; // rcx
  char *v31; // r12
  CBlbImpersonationHelper *v32; // r13
  LPVOID *v33; // rcx
  unsigned int v34; // ebx
  struct _BLBSRV_VOLUME_MAP *v35; // rcx
  struct CBlbEngine *v36; // rsi
  int v37; // eax
  unsigned __int16 *v38; // r9
  __int64 v39; // rcx
  char v40; // r8
  int v41; // eax
  int v42; // ebx
  int v43; // edi
  int v44; // ebx
  unsigned int v45; // edi
  int v46; // r9d
  struct _BLBSRV_VOLUME_MAP **v48; // [rsp+20h] [rbp-49h]
  unsigned __int16 *v49; // [rsp+40h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-21h] BYREF
  struct _FILETIME v51; // [rsp+50h] [rbp-19h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-11h] BYREF
  struct CBlbEngine *v53; // [rsp+60h] [rbp-9h]
  struct _GUID v54; // [rsp+70h] [rbp+7h] BYREF
  BSTR bstrString; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int8 v56; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v57; // [rsp+E0h] [rbp+77h] BYREF
  struct _BLBSRV_VOLUME_MAP *v58; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = 0;
  LODWORD(bstrString) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  v3 = (struct CBlbEngine *)*((_QWORD *)Parameter + 7);
  v4 = (struct IBlbsrvSystemStateRestore *)*((_QWORD *)Parameter + 38);
  v53 = v3;
  v58 = 0;
  v57 = 0;
  v49 = 0;
  pv = 0;
  SystemTimeAsFileTime = 0;
  v51 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v5 = *((_QWORD *)Parameter + 71);
  v6 = (unsigned __int16 *)*((_QWORD *)Parameter + 56);
  v7 = *((_DWORD *)Parameter + 117);
  v8 = *(struct _FILETIME *)(Parameter + 404);
  v54 = (struct _GUID)*((_OWORD *)Parameter + 16);
  if ( (int)PublishSystemStateRestoreStartEvent(v8, &v54, *(struct _FILETIME *)(v5 + 100), v7, v6) >= 0 )
    goto LABEL_10;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
LABEL_10:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
  {
    v10 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, (const struct _GUID *)Parameter + 16);
    v2 = 1;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids, *(_QWORD *)v10);
  }
LABEL_15:
  if ( (v2 & 1) != 0 )
    SysFreeString(bstrString);
  v11 = 0;
  IsClientSKU = CoInitializeEx(0, 0);
  if ( IsClientSKU < 0 )
  {
    v13 = 0;
    LOBYTE(bstrString) = 0;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_106;
    }
    v15 = 46;
    goto LABEL_22;
  }
  v16 = *((_QWORD *)Parameter + 71);
  v13 = 1;
  LOBYTE(bstrString) = 1;
  IsClientSKU = CBlbSystemStateRestoreAsync::MountVolumesInBackupSet(
                  (unsigned __int16 **)Parameter,
                  v3,
                  *(unsigned int *)(v16 + 64),
                  &v57,
                  &v58,
                  (unsigned __int16 ***)&pv);
  if ( IsClientSKU < 0 )
    goto LABEL_106;
  IsClientSKU = BlbDeleteStagingDirectories(*((struct CBlbEngine **)Parameter + 7));
  if ( IsClientSKU < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
    }
    (*(void (__fastcall **)(char *, __int64, _QWORD))(*((_QWORD *)Parameter + 17) + 64LL))(
      Parameter + 136,
      2155348229LL,
      (unsigned int)IsClientSKU);
    goto LABEL_106;
  }
  if ( ((*((_DWORD *)Parameter + 117) - 2) & 0xFFFFFFFD) == 0 )
  {
LABEL_43:
    IsClientSKU = CBlbSystemStateRestoreAsync::InitializeSSRHelper((CBlbSystemStateRestoreAsync *)Parameter);
    if ( IsClientSKU < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v23 = 49;
LABEL_48:
      WPP_SF_d(v22[2], v23, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
LABEL_49:
      *((_DWORD *)Parameter + 3) = IsClientSKU;
      goto LABEL_106;
    }
    IsClientSKU = CBlbSystemStateRestoreAsync::SetComponentsToRestore((CBlbSystemStateRestoreAsync *)Parameter);
    if ( IsClientSKU < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_49;
      }
      v23 = 50;
      goto LABEL_48;
    }
    IsClientSKU = CBlbSystemStateRestoreAsync::SetVolumeMap((CBlbSystemStateRestoreAsync *)Parameter, v58, v57);
    if ( IsClientSKU < 0 )
      goto LABEL_106;
    if ( !*((_QWORD *)Parameter + 56) )
    {
      CBlbSystemStateRestoreAsync::SetState(Parameter, 11);
      IsClientSKU = CBlbSystemStateRestoreAsync::StopServices((CBlbSystemStateRestoreAsync *)Parameter);
      if ( IsClientSKU < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_106;
        }
        v15 = 51;
        goto LABEL_22;
      }
    }
    CBlbSystemStateRestoreAsync::SetState(Parameter, 2);
    v25 = Parameter + 136;
    IsClientSKU = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)Parameter + 17) + 120LL))(Parameter + 136);
    if ( IsClientSKU < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_106;
      }
      v15 = 52;
      goto LABEL_22;
    }
    CBlbSystemStateRestoreAsync::SetState(Parameter, 4);
    IsClientSKU = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v25 + 128LL))(Parameter + 136);
    if ( IsClientSKU < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_106;
      }
      v15 = 53;
      goto LABEL_22;
    }
    if ( !*((_QWORD *)Parameter + 56) )
    {
      CBlbSystemStateRestoreAsync::SetState(Parameter, 7);
      IsClientSKU = CBlbSystemStateRestoreAsync::DeleteFiles((CBlbSystemStateRestoreAsync *)Parameter);
      if ( IsClientSKU < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_106;
        }
        v15 = 54;
        goto LABEL_22;
      }
      CBlbSystemStateRestoreAsync::SetState(Parameter, 3);
      IsClientSKU = CBlbSystemStateRestoreAsync::PrerestoreRegistry((CBlbSystemStateRestoreAsync *)Parameter);
      if ( IsClientSKU < 0 )
        goto LABEL_106;
      v27 = CBlbSystemStateRestoreAsync::DelayedOperations(v26, v4);
      IsClientSKU = v27;
      if ( v27 < 0 )
      {
        (*(void (__fastcall **)(char *, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
          Parameter + 136,
          (unsigned int)v27,
          *((unsigned int *)Parameter + 3));
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_106;
        }
        v15 = 55;
LABEL_22:
        WPP_SF_d(v14[2], v15, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
        goto LABEL_106;
      }
      CBlbSystemStateRestoreAsync::SetState(Parameter, 5);
      IsClientSKU = CBlbSystemStateRestoreAsync::RestoreRegistry(v28, v4);
      if ( IsClientSKU < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
        }
        v29 = 2155348234LL;
LABEL_98:
        (*(void (__fastcall **)(char *, __int64, _QWORD))(*(_QWORD *)v25 + 64LL))(
          Parameter + 136,
          v29,
          (unsigned int)IsClientSKU);
        goto LABEL_106;
      }
      CBlbSystemStateRestoreAsync::SetState(Parameter, 6);
      IsClientSKU = CBlbSystemStateRestoreAsync::PostrestoreRegistry(v30, v4);
      if ( IsClientSKU < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
        }
        v29 = 2155348236LL;
        goto LABEL_98;
      }
    }
    CBlbSystemStateRestoreAsync::SetState(Parameter, 8);
    goto LABEL_106;
  }
  v17 = *((_QWORD *)Parameter + 71);
  v18 = 0;
  if ( !*(_DWORD *)(v17 + 64) )
  {
LABEL_41:
    if ( v18 != v57 )
      BlbAssert("base\\stor\\blb\\engine\\service\\systemstaterestore.cpp", 0x670u, "iVolumeMap == cVolumeMap");
    goto LABEL_43;
  }
  while ( 1 )
  {
    v19 = 120LL * v11;
    v20 = *(_QWORD *)(v17 + 72);
    if ( (*(_BYTE *)(v19 + v20 + 16) & 0x20) == 0 || !*(_BYTE *)(v19 + v20 + 41) && *((_DWORD *)Parameter + 117) != 4 )
      goto LABEL_39;
    if ( v18 >= v57 )
    {
      BlbAssert("base\\stor\\blb\\engine\\service\\systemstaterestore.cpp", 0x653u, "iVolumeMap < cVolumeMap");
      if ( v18 >= v57 )
      {
        IsClientSKU = -2147418113;
        v11 = 0;
        goto LABEL_106;
      }
    }
    StagingDirectory = BlbCreateStagingDirectory(*((unsigned __int16 **)v58 + 3 * v18 + 1), (int *)Parameter + 3);
    IsClientSKU = StagingDirectory;
    if ( StagingDirectory < 0 )
      break;
    ++v18;
LABEL_39:
    v17 = *((_QWORD *)Parameter + 71);
    if ( ++v11 >= *(_DWORD *)(v17 + 64) )
    {
      v11 = 0;
      goto LABEL_41;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      (unsigned int)WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids,
      *((_QWORD *)v58 + 3 * v18 + 1),
      StagingDirectory);
  }
  v11 = 0;
  v24 = (unsigned int)IsClientSKU;
  if ( *((int *)Parameter + 3) < 0 )
    v24 = 2155348230LL;
  (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)Parameter + 17) + 64LL))(Parameter + 136, v24);
LABEL_106:
  v31 = Parameter + 136;
  v32 = (CBlbImpersonationHelper *)(Parameter + 16);
  while ( 2 )
  {
    GetSystemTimeAsFileTime(&v51);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids,
        (*(_QWORD *)&v51 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
    }
    if ( (int)CBlbFileAsync::StopFileLogging((CBlbFileAsync *)(Parameter + 136)) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
    }
    CBlbImpersonationHelper::Revert(v32);
    v33 = (LPVOID *)pv;
    if ( pv )
    {
      v34 = 0;
      if ( v57 )
      {
        do
        {
          if ( v33[v34] )
          {
            CoTaskMemFree(v33[v34]);
            *((_QWORD *)pv + v34) = 0;
            v33 = (LPVOID *)pv;
          }
          ++v34;
        }
        while ( v34 < v57 );
        v11 = 0;
      }
      if ( v33 )
      {
        CoTaskMemFree(v33);
        pv = 0;
      }
    }
    v35 = v58;
    if ( v58 )
    {
      if ( v57 )
      {
        v36 = v53;
        while ( !*((_QWORD *)v35 + 3 * v11 + 2) )
        {
LABEL_140:
          if ( *((_QWORD *)v35 + 3 * v11 + 2) )
          {
            CoTaskMemFree(*((LPVOID *)v35 + 3 * v11 + 2));
            *((_QWORD *)v58 + 3 * v11 + 2) = 0;
            v35 = v58;
          }
          if ( *((_QWORD *)v35 + 3 * v11 + 1) )
          {
            CoTaskMemFree(*((LPVOID *)v35 + 3 * v11 + 1));
            *((_QWORD *)v58 + 3 * v11 + 1) = 0;
            v35 = v58;
          }
          if ( *((_QWORD *)v35 + 3 * v11) )
          {
            CoTaskMemFree(*((LPVOID *)v35 + 3 * v11));
            *((_QWORD *)v58 + 3 * v11) = 0;
            v35 = v58;
          }
          if ( ++v11 >= v57 )
          {
            v13 = (char)bstrString;
            v32 = (CBlbImpersonationHelper *)(Parameter + 16);
            goto LABEL_148;
          }
        }
        if ( v49 )
        {
          CoTaskMemFree(v49);
          v35 = v58;
          v49 = 0;
        }
        v37 = BlbutilDuplicateString(*((const unsigned __int16 **)v35 + 3 * v11 + 2), &v49, 0);
        v38 = v49;
        v39 = -1;
        v40 = v37;
        do
          ++v39;
        while ( v49[v39] );
        v49[v39 - 1] = 0;
        if ( v37 >= 0 )
        {
          v41 = (*(__int64 (__fastcall **)(struct CBlbEngine *, unsigned __int16 *, _QWORD))(*(_QWORD *)v36 + 360LL))(
                  v36,
                  v38,
                  (unsigned int)v37);
          v40 = v41;
          if ( v41 >= 0 )
          {
LABEL_139:
            v35 = v58;
            goto LABEL_140;
          }
          LODWORD(v38) = (_DWORD)v49;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            (unsigned int)WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids,
            (_DWORD)v38,
            v40);
        }
        goto LABEL_139;
      }
LABEL_148:
      if ( v35 )
      {
        CoTaskMemFree(v35);
        v58 = 0;
      }
    }
    if ( v49 )
    {
      CoTaskMemFree(v49);
      v49 = 0;
    }
    if ( v13 )
      CoUninitialize();
    if ( IsClientSKU >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
      }
      CBlbSystemStateRestoreAsync::SetState(Parameter, 8);
    }
    else
    {
      if ( !CBlbAsync::CheckPoint((CBlbAsync *)Parameter) )
      {
        IsClientSKU = -2139618969;
        (*(void (__fastcall **)(char *, __int64, _QWORD))(*(_QWORD *)v31 + 64LL))(Parameter + 136, 2155348327LL, 0);
      }
      v42 = *((_DWORD *)Parameter + 3);
      v43 = *((_DWORD *)Parameter + 2);
      EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 64));
      CBlbSystemStateRestoreAsync::SetState(Parameter, 10);
      if ( v43 >= 0 )
        v43 = IsClientSKU;
      CBlbAsync::SetResult((CBlbAsync *)Parameter, v43, v42, 0);
      LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 64));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
      }
      v13 = (char)bstrString;
    }
    if ( (int)CBlbSystemStateRestoreAsync::PublishSystemStateRestoreStopEvent((CBlbSystemStateRestoreAsync *)Parameter) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
    }
    v44 = *((_DWORD *)Parameter + 2);
    v45 = *((_DWORD *)Parameter + 3);
    v56 = 0;
    IsClientSKU = BlbutilIsClientSKU(&v56);
    if ( IsClientSKU < 0 )
    {
      v11 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
      }
      continue;
    }
    break;
  }
  if ( v44 < 0 && !v56 )
  {
    if ( IsWERRequiredForError(v44) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
        v46 = 0;
      }
      LODWORD(v48) = v46;
      BlbGenerateErrorReport(*((unsigned int *)Parameter + 108), 6, (unsigned int)v44, v45, v48, v46, v46, v46);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
    }
  }
  CBlbFileAsync::Uninitialize((CBlbFileAsync *)(Parameter + 136));
  CBlbAsync::Done((CBlbAsync *)Parameter);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v31 + 16LL))(Parameter + 136);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140075000  push    rbp
0x140075002  push    rbx
0x140075003  push    rsi
0x140075004  push    rdi
0x140075005  push    r12
0x140075007  push    r13
0x140075009  push    r14
0x14007500b  push    r15
0x14007500d  lea     rbp, [rsp-1Fh]
0x140075012  sub     rsp, 88h
0x140075019  xor     esi, esi
0x14007501b  mov     r15, rcx
0x14007501e  mov     ebx, esi
0x140075020  mov     dword ptr [rbp+57h+bstrString], ebx
0x140075023  mov     rcx, cs:WPP_GLOBAL_Control
0x14007502a  lea     rax, WPP_GLOBAL_Control
0x140075031  lea     r14d, [rsi+1]
0x140075035  cmp     rcx, rax
0x140075038  jz      short loc_140075059
0x14007503a  test    [rcx+1Ch], r14b
0x14007503e  jz      short loc_140075059
0x140075040  cmp     byte ptr [rcx+19h], 4
0x140075044  jb      short loc_140075059
0x140075046  mov     rcx, [rcx+10h]
0x14007504a  lea     edx, [rsi+2Bh]
0x14007504d  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x140075054  call    WPP_SF_
0x140075059  mov     r12, [r15+38h]
0x14007505d  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140075061  mov     r13, [r15+130h]
0x140075068  mov     [rbp+57h+var_60], r12
0x14007506c  mov     [rbp+57h+arg_18], rsi
0x140075070  mov     [rbp+57h+arg_10], esi
0x140075073  mov     [rbp+57h+var_80], rsi
0x140075077  mov     [rbp+57h+pv], rsi
0x14007507b  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x14007507f  mov     qword ptr [rbp+57h+var_70.dwLowDateTime], rsi
0x140075083  call    cs:__imp_GetSystemTimeAsFileTime
0x140075089  mov     r8, [r15+238h]
0x140075090  lea     rdi, [r15+100h]
0x140075097  movups  xmm0, xmmword ptr [rdi]
0x14007509a  mov     rax, [r15+1C0h]
0x1400750a1  lea     rdx, [rbp+57h+var_50]; struct _GUID *
0x1400750a5  mov     r9d, [r15+1D4h]; unsigned int
0x1400750ac  mov     rcx, [r15+194h]; struct _FILETIME
0x1400750b3  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x1400750b8  mov     r8, [r8+64h]; struct _FILETIME
0x1400750bc  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 *
0x1400750c1  call    ?PublishSystemStateRestoreStartEvent@@YAJU_FILETIME@@U_GUID@@0IPEAG@Z; PublishSystemStateRestoreStartEvent(_FILETIME,_GUID,_FILETIME,uint,ushort *)
0x1400750c6  test    eax, eax
0x1400750c8  jns     short loc_140075100
0x1400750ca  mov     rax, cs:WPP_GLOBAL_Control
0x1400750d1  lea     rsi, WPP_GLOBAL_Control
0x1400750d8  cmp     rax, rsi
0x1400750db  jz      short loc_14007514D
0x1400750dd  test    [rax+1Ch], r14b
0x1400750e1  jz      short loc_14007510E
0x1400750e3  cmp     byte ptr [rax+19h], 3
0x1400750e7  jb      short loc_14007510E
0x1400750e9  mov     rcx, [rax+10h]
0x1400750ed  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x1400750f4  mov     edx, 2Ch ; ','
0x1400750f9  call    WPP_SF_
0x1400750fe  jmp     short loc_140075107
0x140075100  lea     rsi, WPP_GLOBAL_Control
0x140075107  mov     rax, cs:WPP_GLOBAL_Control
0x14007510e  cmp     rax, rsi
0x140075111  jz      short loc_14007514D
0x140075113  test    [rax+1Ch], r14b
0x140075117  jz      short loc_14007514D
0x140075119  cmp     byte ptr [rax+19h], 4
0x14007511d  jb      short loc_14007514D
0x14007511f  mov     rdx, rdi; struct _GUID *
0x140075122  lea     rcx, [rbp+57h+bstrString]; this
0x140075126  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x14007512b  mov     rcx, cs:WPP_GLOBAL_Control
0x140075132  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x140075139  mov     edx, 2Dh ; '-'
0x14007513e  mov     ebx, r14d
0x140075141  mov     r9, [rax]
0x140075144  mov     rcx, [rcx+10h]
0x140075148  call    WPP_SF_S
0x14007514d  test    r14b, bl
0x140075150  jz      short loc_14007515C
0x140075152  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140075156  call    cs:__imp_SysFreeString
0x14007515c  xor     edx, edx; dwCoInit
0x14007515e  xor     ecx, ecx; pvReserved
0x140075160  call    cs:__imp_CoInitializeEx
0x140075166  xor     edi, edi
0x140075168  mov     r14d, eax
0x14007516b  test    eax, eax
0x14007516d  jns     short loc_1400751BC
0x14007516f  mov     sil, dil
0x140075172  mov     byte ptr [rbp+57h+bstrString], dil
0x140075176  mov     rcx, cs:WPP_GLOBAL_Control
0x14007517d  lea     rbx, WPP_GLOBAL_Control
0x140075184  cmp     rcx, rbx
0x140075187  jz      loc_140075732
0x14007518d  test    byte ptr [rcx+1Ch], 1
0x140075191  jz      loc_140075732
0x140075197  cmp     byte ptr [rcx+19h], 2
0x14007519b  jb      loc_140075732
0x1400751a1  lea     edx, [rdi+2Eh]
0x1400751a4  mov     rcx, [rcx+10h]
0x1400751a8  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x1400751af  mov     r9d, eax
0x1400751b2  call    WPP_SF_d
0x1400751b7  jmp     loc_140075732
0x1400751bc  mov     r8, [r15+238h]
0x1400751c3  lea     rax, [rbp+57h+pv]
0x1400751c7  mov     [rsp+0C0h+var_98], rax; unsigned __int16 ***
0x1400751cc  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x1400751d0  lea     rax, [rbp+57h+arg_18]
0x1400751d4  mov     sil, 1
0x1400751d7  mov     rdx, r12; struct CBlbEngine *
0x1400751da  mov     byte ptr [rbp+57h+bstrString], sil
0x1400751de  mov     r8d, [r8+40h]; unsigned int
0x1400751e2  mov     rcx, r15; this
0x1400751e5  mov     [rsp+0C0h+var_A0], rax; struct _BLBSRV_VOLUME_MAP **
0x1400751ea  call    ?MountVolumesInBackupSet@CBlbSystemStateRestoreAsync@@AEAAJPEAVCBlbEngine@@KPEAKPEAPEAU_BLBSRV_VOLUME_MAP@@PEAPEAPEAG@Z; CBlbSystemStateRestoreAsync::MountVolumesInBackupSet(CBlbEngine *,ulong,ulong *,_BLBSRV_VOLUME_MAP * *,ushort * * *)
0x1400751ef  mov     r14d, eax
0x1400751f2  test    eax, eax
0x1400751f4  js      loc_14007572B
0x1400751fa  mov     rcx, [r15+38h]; struct CBlbEngine *
0x1400751fe  call    ?BlbDeleteStagingDirectories@@YAJPEAVCBlbEngine@@@Z; BlbDeleteStagingDirectories(CBlbEngine *)
0x140075203  mov     r14d, eax
0x140075206  test    eax, eax
0x140075208  jns     short loc_140075261
0x14007520a  mov     rcx, cs:WPP_GLOBAL_Control
0x140075211  lea     rbx, WPP_GLOBAL_Control
0x140075218  cmp     rcx, rbx
0x14007521b  jz      short loc_140075241
0x14007521d  test    [rcx+1Ch], sil
0x140075221  jz      short loc_140075241
0x140075223  cmp     byte ptr [rcx+19h], 2
0x140075227  jb      short loc_140075241
0x140075229  mov     rcx, [rcx+10h]
0x14007522d  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x140075234  mov     edx, 2Fh ; '/'
0x140075239  mov     r9d, eax
0x14007523c  call    WPP_SF_d
0x140075241  lea     rcx, [r15+88h]
0x140075248  mov     r8d, r14d
0x14007524b  mov     rax, [rcx]
0x14007524e  mov     edx, 80780105h
0x140075253  mov     rax, [rax+40h]
0x140075257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007525c  jmp     loc_140075732
0x140075261  mov     eax, [r15+1D4h]
0x140075268  mov     r12d, 2
0x14007526e  sub     eax, r12d
0x140075271  test    eax, 0FFFFFFFDh
0x140075276  jz      loc_14007532C
0x14007527c  mov     rcx, [r15+238h]
0x140075283  mov     ebx, edi
0x140075285  cmp     [rcx+40h], edi
0x140075288  jbe     loc_14007530F
0x14007528e  mov     eax, edi
0x140075290  imul    rdx, rax, 78h ; 'x'
0x140075294  mov     rax, [rcx+48h]
0x140075298  test    byte ptr [rdx+rax+10h], 20h
0x14007529d  jz      short loc_1400752FB
0x14007529f  cmp     byte ptr [rdx+rax+29h], 0
0x1400752a4  jnz     short loc_1400752B0
0x1400752a6  cmp     dword ptr [r15+1D4h], 4
0x1400752ae  jnz     short loc_1400752FB
0x1400752b0  cmp     ebx, [rbp+57h+arg_10]
0x1400752b3  jb      short loc_1400752D6
0x1400752b5  lea     r8, aIvolumemapCvol_0; "iVolumeMap < cVolumeMap"
0x1400752bc  mov     edx, 653h; unsigned int
0x1400752c1  lea     rcx, aBaseStorBlbEng_41; "base\\stor\\blb\\engine\\service\\syste"...
0x1400752c8  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400752cd  cmp     ebx, [rbp+57h+arg_10]
0x1400752d0  jnb     loc_14007537F
0x1400752d6  mov     rcx, [rbp+57h+arg_18]
0x1400752da  lea     rdx, [r15+0Ch]; int *
0x1400752de  mov     eax, ebx
0x1400752e0  lea     r12, [rax+rax*2]
0x1400752e4  mov     rcx, [rcx+r12*8+8]; unsigned __int16 *
0x1400752e9  call    ?BlbCreateStagingDirectory@@YAJPEAGPEAJ@Z; BlbCreateStagingDirectory(ushort *,long *)
0x1400752ee  mov     r14d, eax
0x1400752f1  test    eax, eax
0x1400752f3  js      loc_14007538C
0x1400752f9  inc     ebx
0x1400752fb  mov     rcx, [r15+238h]
0x140075302  inc     edi
0x140075304  cmp     edi, [rcx+40h]
0x140075307  jb      short loc_14007528E
0x140075309  xor     edi, edi
0x14007530b  lea     r12d, [rdi+2]
0x14007530f  cmp     ebx, [rbp+57h+arg_10]
0x140075312  jz      short loc_14007532C
0x140075314  lea     r8, aIvolumemapCvol; "iVolumeMap == cVolumeMap"
0x14007531b  mov     edx, 670h; unsigned int
0x140075320  lea     rcx, aBaseStorBlbEng_41; "base\\stor\\blb\\engine\\service\\syste"...
0x140075327  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007532c  mov     rcx, r15; this
0x14007532f  call    ?InitializeSSRHelper@CBlbSystemStateRestoreAsync@@QEAAJXZ; CBlbSystemStateRestoreAsync::InitializeSSRHelper(void)
0x140075334  mov     r14d, eax
0x140075337  test    eax, eax
0x140075339  jns     loc_1400753F9
0x14007533f  mov     rcx, cs:WPP_GLOBAL_Control
0x140075346  lea     rbx, WPP_GLOBAL_Control
0x14007534d  cmp     rcx, rbx
0x140075350  jz      short loc_140075376
0x140075352  test    byte ptr [rcx+1Ch], 1
0x140075356  jz      short loc_140075376
0x140075358  cmp     [rcx+19h], r12b
0x14007535c  jb      short loc_140075376
0x14007535e  mov     edx, 31h ; '1'
0x140075363  mov     rcx, [rcx+10h]
0x140075367  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x14007536e  mov     r9d, r14d
0x140075371  call    WPP_SF_d
0x140075376  mov     [r15+0Ch], r14d
0x14007537a  jmp     loc_140075732
0x14007537f  mov     r14d, 8000FFFFh
0x140075385  xor     edi, edi
0x140075387  jmp     loc_14007572B
0x14007538c  mov     rcx, cs:WPP_GLOBAL_Control
0x140075393  lea     rbx, WPP_GLOBAL_Control
0x14007539a  cmp     rcx, rbx
0x14007539d  jz      short loc_1400753CE
0x14007539f  test    [rcx+1Ch], sil
0x1400753a3  jz      short loc_1400753CE
0x1400753a5  cmp     byte ptr [rcx+19h], 2
0x1400753a9  jb      short loc_1400753CE
0x1400753ab  mov     r9, [rbp+57h+arg_18]
0x1400753af  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x1400753b6  mov     rcx, [rcx+10h]
0x1400753ba  mov     edx, 30h ; '0'
0x1400753bf  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x1400753c4  mov     r9, [r9+r12*8+8]
0x1400753c9  call    WPP_SF_Sd
0x1400753ce  mov     r8d, [r15+0Ch]
0x1400753d2  lea     rcx, [r15+88h]
0x1400753d9  mov     rax, [rcx]
0x1400753dc  xor     edi, edi
0x1400753de  mov     edx, r14d
0x1400753e1  mov     rax, [rax+40h]
0x1400753e5  test    r8d, r8d
0x1400753e8  jns     short loc_1400753EF
0x1400753ea  mov     edx, 80780106h
0x1400753ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400753f4  jmp     loc_140075732
0x1400753f9  mov     rcx, r15; this
0x1400753fc  call    ?SetComponentsToRestore@CBlbSystemStateRestoreAsync@@QEAAJXZ; CBlbSystemStateRestoreAsync::SetComponentsToRestore(void)
0x140075401  mov     r14d, eax
0x140075404  test    eax, eax
0x140075406  jns     short loc_14007543D
0x140075408  mov     rcx, cs:WPP_GLOBAL_Control
0x14007540f  lea     rbx, WPP_GLOBAL_Control
0x140075416  cmp     rcx, rbx
0x140075419  jz      loc_140075376
0x14007541f  test    byte ptr [rcx+1Ch], 1
0x140075423  jz      loc_140075376
0x140075429  cmp     [rcx+19h], r12b
0x14007542d  jb      loc_140075376
0x140075433  mov     edx, 32h ; '2'
0x140075438  jmp     loc_140075363
0x14007543d  mov     r8d, [rbp+57h+arg_10]; unsigned int
0x140075441  mov     rcx, r15; this
0x140075444  mov     rdx, [rbp+57h+arg_18]; struct _BLBSRV_VOLUME_MAP *
0x140075448  call    ?SetVolumeMap@CBlbSystemStateRestoreAsync@@QEAAJPEAU_BLBSRV_VOLUME_MAP@@K@Z; CBlbSystemStateRestoreAsync::SetVolumeMap(_BLBSRV_VOLUME_MAP *,ulong)
0x14007544d  mov     r14d, eax
0x140075450  test    eax, eax
0x140075452  js      loc_14007572B
0x140075458  cmp     [r15+1C0h], rdi
0x14007545f  jnz     short loc_1400754C5
0x140075461  mov     edx, 0Bh
0x140075466  mov     rcx, r15
0x140075469  call    ?SetState@CBlbSystemStateRestoreAsync@@QEAAXW4_BLB_SYSTEM_STATE_RESTORE_STATE@@E@Z; CBlbSystemStateRestoreAsync::SetState(_BLB_SYSTEM_STATE_RESTORE_STATE,uchar)
0x14007546e  mov     rcx, r15; this
0x140075471  call    ?StopServices@CBlbSystemStateRestoreAsync@@QEAAJXZ; CBlbSystemStateRestoreAsync::StopServices(void)
0x140075476  mov     r14d, eax
0x140075479  test    eax, eax
0x14007547b  jns     short loc_1400754C5
0x14007547d  mov     rcx, cs:WPP_GLOBAL_Control
0x140075484  lea     rbx, WPP_GLOBAL_Control
0x14007548b  cmp     rcx, rbx
0x14007548e  jz      loc_140075732
0x140075494  test    byte ptr [rcx+1Ch], 1
0x140075498  jz      loc_140075732
0x14007549e  cmp     [rcx+19h], r12b
0x1400754a2  jb      loc_140075732
0x1400754a8  mov     edx, 33h ; '3'
0x1400754ad  mov     r9d, eax
0x1400754b0  mov     rcx, [rcx+10h]
0x1400754b4  lea     r8, WPP_8e9bb37e94e73f7c6c939e5e199b5852_Traceguids
0x1400754bb  call    WPP_SF_d
0x1400754c0  jmp     loc_140075732
0x1400754c5  mov     edx, r12d
0x1400754c8  mov     rcx, r15
0x1400754cb  call    ?SetState@CBlbSystemStateRestoreAsync@@QEAAXW4_BLB_SYSTEM_STATE_RESTORE_STATE@@E@Z; CBlbSystemStateRestoreAsync::SetState(_BLB_SYSTEM_STATE_RESTORE_STATE,uchar)
0x1400754d0  lea     rbx, [r15+88h]
0x1400754d7  mov     rax, [rbx]
0x1400754da  mov     rcx, rbx
0x1400754dd  mov     rax, [rax+78h]
0x1400754e1  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
