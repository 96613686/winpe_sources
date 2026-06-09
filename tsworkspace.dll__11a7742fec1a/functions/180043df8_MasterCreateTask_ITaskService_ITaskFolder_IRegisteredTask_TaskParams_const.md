# MasterCreateTask(ITaskService *,ITaskFolder *,IRegisteredTask * *,TaskParams const &)

- ea: `0x180043df8`
- end: `0x1800451a4`
- name: `?MasterCreateTask@@YAJPEAUITaskService@@PEAUITaskFolder@@PEAPEAUIRegisteredTask@@AEBUTaskParams@@@Z`
- size: `5036`
- prototype: `__int64 __fastcall(struct ITaskService *, struct ITaskFolder *, struct IRegisteredTask **, const struct TaskParams *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f090`
- `0x18003da0c`
- `0x18003dcf0`
- `0x18003e03c`

## callees

- `0x180003108`
- `0x1800054c4`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000ef54`
- `0x18000efc4`
- `0x18000eff0`
- `0x18000ff00`
- `0x180043df8`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800450f1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800450f1`
- `ADVAPI32!GetUserNameW` at `0x180044881`
- `ADVAPI32!GetUserNameW` at `0x180044881`
- `OLEAUT32!__imp_VariantInit` at `0x180044ff2`
- `OLEAUT32!__imp_VariantInit` at `0x180045008`
- `OLEAUT32!__imp_VariantInit` at `0x18004501d`
- `OLEAUT32!__imp_VariantInit` at `0x180044ff2`
- `OLEAUT32!__imp_VariantInit` at `0x180045008`
- `OLEAUT32!__imp_VariantInit` at `0x18004501d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180043f71`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180044043`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180043f71`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180044043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004407d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800447f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004492d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004407d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800447f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004492d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044966`
- `SspiCli!GetUserNameExW` at `0x1800447e3`
- `SspiCli!GetUserNameExW` at `0x1800448fc`
- `SspiCli!GetUserNameExW` at `0x1800447e3`
- `SspiCli!GetUserNameExW` at `0x1800448fc`

## string_xrefs

- `0x180043ecf`: `NewTask failed`
- `0x18004470e`: `ITriggerCollection::Create failed`
- `0x180044ec1`: `IActionCollection::Create failed`
- `0x180044f7d`: `put_Path failed`
- `0x180044e05`: `QueryInterface failed when creating the com handler action`
- `0x180044e64`: `put_ClassId failed`
- `0x1800450da`: `RegisterTaskDefinition failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall MasterCreateTask(
        struct ITaskService *a1,
        struct ITaskFolder *a2,
        struct IRegisteredTask **a3,
        const struct TaskParams *a4)
{
  signed int v7; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  signed int LastError; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rdx
  signed int v15; // eax
  __int64 v16; // rbx
  void (__fastcall *v17)(__int64, __int64); // rdi
  _bstr_t *v18; // rax
  __int64 v19; // rdx
  signed int v20; // eax
  __int64 v21; // rbx
  void (__fastcall *v22)(__int64, __int64); // rdi
  _bstr_t *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD); // rbx
  unsigned __int16 v27; // ax
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, _QWORD); // rbx
  unsigned __int16 v30; // ax
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, _QWORD); // rbx
  unsigned __int16 v33; // ax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, _QWORD); // rbx
  unsigned __int16 v36; // ax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD); // rbx
  unsigned __int16 v39; // ax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, _QWORD); // rbx
  unsigned __int16 v42; // ax
  unsigned __int16 *v43; // r14
  int v44; // ecx
  int v45; // ecx
  unsigned int v46; // eax
  signed int v47; // eax
  WCHAR *v48; // rax
  unsigned int v49; // eax
  __int64 v50; // rdx
  int UserNameW; // eax
  unsigned __int64 v52; // rax
  WCHAR *v53; // rax
  signed int v54; // eax
  unsigned int v55; // ebx
  unsigned int v56; // eax
  signed int v57; // eax
  __int64 v58; // rbx
  __int64 (__fastcall *v59)(__int64, __int64); // rdi
  _bstr_t *v60; // rax
  __int64 v61; // rdx
  unsigned int v62; // eax
  int v63; // edx
  const char *v64; // rcx
  unsigned int v65; // eax
  __int64 v66; // rdx
  int v67; // ecx
  unsigned int v68; // eax
  HRESULT (__stdcall *RegisterTaskDefinition)(ITaskFolder *, BSTR, ITaskDefinition *, LONG, VARIANT, VARIANT, TASK_LOGON_TYPE, VARIANT, IRegisteredTask **); // rbx
  __int128 v70; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v72; // xmm6
  IRecordInfo *v73; // xmm7_8
  __int64 v75; // [rsp+30h] [rbp-D8h]
  __int64 v76; // [rsp+58h] [rbp-B0h] BYREF
  DWORD nSize; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG nSize_8; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v79; // [rsp+80h] [rbp-88h] BYREF
  __int64 (__fastcall ***v80)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-80h] BYREF
  __int64 v81; // [rsp+90h] [rbp-78h] BYREF
  __int64 (__fastcall ***v82)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-70h] BYREF
  _BYTE v83[8]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v84; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v85; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v86; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v87; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v88; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v89; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v90; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v92; // [rsp+108h] [rbp+0h]
  __int128 v93; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v94; // [rsp+128h] [rbp+20h]
  __int128 v95; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v96; // [rsp+148h] [rbp+40h]
  VARIANTARG v97; // [rsp+158h] [rbp+50h] BYREF
  WCHAR Buffer[1024]; // [rsp+178h] [rbp+70h] BYREF

  v92 = -2;
  v79 = 0;
  v88 = 0;
  v76 = 0;
  v87 = 0;
  v82 = 0;
  v86 = 0;
  v81 = 0;
  v85 = 0;
  v80 = 0;
  v84 = 0;
  v89 = 0;
  nSize = 0;
  v7 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, __int64 *))a1->lpVtbl->NewTask)(a1, 0, &v79);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 37;
      v10 = "NewTask failed";
LABEL_6:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)WPP_060bbe8053683a966e9955f0decff737_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v10,
        v7);
      goto LABEL_252;
    }
    goto LABEL_252;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 56LL))(v79, &v88);
  if ( v7 >= 0 )
  {
    if ( LoadStringW(g_hinst, *((_DWORD *)a4 + 2), Buffer, 1024) <= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 39;
LABEL_19:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v13, v12);
        goto LABEL_20;
      }
      goto LABEL_20;
    }
    v16 = v88;
    v17 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v88 + 64LL);
    v18 = _bstr_t::_bstr_t((_bstr_t *)v83, Buffer);
    if ( *(_QWORD *)v18 )
      v19 = **(_QWORD **)v18;
    else
      v19 = 0;
    v17(v16, v19);
    _bstr_t::_Free((_bstr_t *)v83);
    if ( LoadStringW(g_hinst, 0x3CF2u, Buffer, 1024) <= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = GetLastError();
        v12 = v20;
        if ( v20 > 0 )
          v12 = (unsigned __int16)v20 | 0x80070000;
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 41;
        goto LABEL_19;
      }
LABEL_20:
      v15 = GetLastError();
      v7 = v15;
      if ( v15 > 0 )
        v7 = (unsigned __int16)v15 | 0x80070000;
      goto LABEL_252;
    }
    v21 = v88;
    v22 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v88 + 80LL);
    v23 = _bstr_t::_bstr_t((_bstr_t *)v83, Buffer);
    if ( *(_QWORD *)v23 )
      v24 = **(_QWORD **)v23;
    else
      v24 = 0;
    v22(v21, v24);
    _bstr_t::_Free((_bstr_t *)v83);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 88LL))(v79, &v76);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 43;
        v10 = "get_Settings failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    v25 = v76;
    v26 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 64LL);
    nSize_8.vt = 11;
    nSize_8.iVal = -1;
    v27 = _variant_t::operator short(&nSize_8);
    v7 = v26(v25, v27);
    _variant_t::~_variant_t((_variant_t *)&nSize_8);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 44;
        v10 = "put_AllowDemandStart failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    v28 = v76;
    v29 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 160LL);
    nSize_8.vt = 11;
    nSize_8.iVal = -1;
    v30 = _variant_t::operator short(&nSize_8);
    v7 = v29(v28, v30);
    _variant_t::~_variant_t((_variant_t *)&nSize_8);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 45;
        v10 = "put_AllowHardTerminate failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 112LL))(v76, *((unsigned int *)a4 + 10));
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 46;
        v10 = "put_MultipleInstances failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    v31 = v76;
    v32 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 144LL);
    nSize_8.vt = 11;
    nSize_8.iVal = 0;
    v33 = _variant_t::operator short(&nSize_8);
    v7 = v32(v31, v33);
    _variant_t::~_variant_t((_variant_t *)&nSize_8);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 47;
        v10 = "put_DisallowStartIfOnBatteries failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    v34 = v76;
    v35 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 128LL);
    nSize_8.vt = 11;
    nSize_8.iVal = 0;
    v36 = _variant_t::operator short(&nSize_8);
    v7 = v35(v34, v36);
    _variant_t::~_variant_t((_variant_t *)&nSize_8);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 48;
        v10 = "put_StopIfGoingOnBatteries  failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 224LL))(v76, *((_QWORD *)a4 + 2));
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 49;
        v10 = "put_ExecutionTimeLimit failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    if ( *((int *)a4 + 7) > 0 && *((_QWORD *)a4 + 4) )
    {
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v76 + 96LL))(v76);
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 50;
          v10 = "put_RestartCount failed";
          goto LABEL_6;
        }
        goto LABEL_252;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 80LL))(v76, *((_QWORD *)a4 + 4));
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 51;
          v10 = "put_RestartInterval failed";
          goto LABEL_6;
        }
        goto LABEL_252;
      }
    }
    if ( *((_DWORD *)a4 + 6) )
    {
      v37 = v76;
      v38 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 176LL);
      nSize_8.vt = 11;
      nSize_8.iVal = -1;
      v39 = _variant_t::operator short(&nSize_8);
      v7 = v38(v37, v39);
      _variant_t::~_variant_t((_variant_t *)&nSize_8);
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 52;
          v10 = "put_StartWhenAvailable failed";
          goto LABEL_6;
        }
        goto LABEL_252;
      }
    }
    if ( *((_DWORD *)a4 + 3) )
    {
      v40 = v76;
      v41 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 208LL);
      nSize_8.vt = 11;
      nSize_8.iVal = -1;
      v42 = _variant_t::operator short(&nSize_8);
      v7 = v41(v40, v42);
      _variant_t::~_variant_t((_variant_t *)&nSize_8);
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 53;
          v10 = "put_RunOnlyIfNetworkAvailable failed";
          goto LABEL_6;
        }
        goto LABEL_252;
      }
    }
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 72LL))(v79, &v87);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 54;
        v10 = "get_Triggers failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    v43 = 0;
    v44 = *((_DWORD *)a4 + 11);
    if ( !v44 )
      goto LABEL_196;
    v45 = v44 - 1;
    if ( !v45 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v87 + 80LL))(v87, 2, &v82);
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_252;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 55;
LABEL_112:
        v10 = "ITriggerCollection::Create failed";
        goto LABEL_6;
      }
      v7 = (**v82)(v82, &IID_IDailyTrigger, &v81);
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 56;
          v10 = "QueryInterface failed when creating the daily trigger";
          goto LABEL_6;
        }
        goto LABEL_252;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v81 + 168LL))(v81, *((unsigned __int16 *)a4 + 24));
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 57;
          v10 = "put_DaysInterval failed";
          goto LABEL_6;
        }
        goto LABEL_252;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v81 + 120LL))(v81, *((_QWORD *)a4 + 7));
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 58;
          v10 = "put_StartBoundary failed";
          goto LABEL_6;
        }
        goto LABEL_252;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v81 + 184LL))(v81, *((_QWORD *)a4 + 8));
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 59;
          v10 = "put_RandomDelay failed";
          goto LABEL_6;
        }
        goto LABEL_252;
      }
      goto LABEL_196;
    }
    if ( v45 != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v46);
      }
      v7 = -2147418113;
      goto LABEL_252;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v87 + 80LL))(v87, 9, &v82);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_252;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 60;
      goto LABEL_112;
    }
    v7 = (**v82)(v82, &IID_ILogonTrigger, &v86);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 61;
        v10 = "QueryInterface failed when creating the logon trigger";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v86 + 168LL))(v86, *((_QWORD *)a4 + 6));
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 62;
        v10 = "put_Delay failed";
        goto LABEL_6;
      }
      goto LABEL_252;
    }
    if ( GetUserNameExW(NameUserPrincipal, 0, &nSize) )
    {
      v7 = -2147418113;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_252;
      }
      v65 = RdpWppGetCurrentThreadActivityIdPrefix();
      v66 = 66;
    }
    else
    {
      v47 = GetLastError();
      v7 = v47;
      if ( v47 == 1332 )
      {
        nSize = 257;
        v48 = (WCHAR *)operator new[](0x202u, (const struct std::nothrow_t *)&std::nothrow);
        v43 = v48;
        if ( !v48 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_131;
          }
          v49 = RdpWppGetCurrentThreadActivityIdPrefix();
          v50 = 63;
LABEL_130:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v50,
            WPP_060bbe8053683a966e9955f0decff737_Traceguids,
            v49,
            -2147024882);
LABEL_131:
          v7 = -2147024882;
          goto LABEL_252;
        }
        UserNameW = GetUserNameW(v48, &nSize);
        goto LABEL_142;
      }
      if ( v47 == 234 )
      {
        v52 = 2LL * nSize;
        if ( !is_mul_ok(nSize, 2u) )
          v52 = -1;
        v53 = (WCHAR *)operator new[](v52, (const struct std::nothrow_t *)&std::nothrow);
        v43 = v53;
        if ( !v53 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_131;
          }
          v49 = RdpWppGetCurrentThreadActivityIdPrefix();
          v50 = 64;
          goto LABEL_130;
        }
        UserNameW = GetUserNameExW(NameUserPrincipal, v53, &nSize);
LABEL_142:
        if ( !UserNameW )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v54 = GetLastError();
            v55 = v54;
            if ( v54 > 0 )
              v55 = (unsigned __int16)v54 | 0x80070000;
            v56 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              WPP_060bbe8053683a966e9955f0decff737_Traceguids,
              v56,
              v55);
          }
          v57 = GetLastError();
          v7 = v57;
          if ( v57 > 0 )
            v7 = (unsigned __int16)v57 | 0x80070000;
          goto LABEL_250;
        }
        v58 = v86;
        v59 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 184LL);
        v60 = _bstr_t::_bstr_t((_bstr_t *)v83, v43);
        if ( *(_QWORD *)v60 )
          v61 = **(_QWORD **)v60;
        else
          v61 = 0;
        v7 = v59(v58, v61);
        _bstr_t::_Free((_bstr_t *)v83);
        if ( v7 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v62 = RdpWppGetCurrentThreadActivityIdPrefix();
            v63 = 68;
            v64 = "put_UserId failed";
LABEL_159:
            LODWORD(v75) = v7;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v63,
              (unsigned int)WPP_060bbe8053683a966e9955f0decff737_Traceguids,
              v62,
              (__int64)v64,
              v75);
            goto LABEL_250;
          }
          goto LABEL_250;
        }
LABEL_196:
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 136LL))(v79, &v85);
        if ( v7 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v62 = RdpWppGetCurrentThreadActivityIdPrefix();
            v63 = 70;
            v64 = "get_Actions failed";
            goto LABEL_159;
          }
LABEL_250:
          if ( v43 )
            operator delete[](v43);
          goto LABEL_252;
        }
        v67 = *((_DWORD *)a4 + 18);
        if ( v67 )
        {
          if ( v67 != 1 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v68 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v68);
            }
            v7 = -2147418113;
            goto LABEL_250;
          }
          v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v85 + 96LL))(v85, 5, &v80);
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_250;
            }
            v62 = RdpWppGetCurrentThreadActivityIdPrefix();
            v63 = 75;
            goto LABEL_228;
          }
          v7 = (**v80)(v80, &IID_IComHandlerAction, &v89);
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v62 = RdpWppGetCurrentThreadActivityIdPrefix();
              v63 = 76;
              v64 = "QueryInterface failed when creating the com handler action";
              goto LABEL_159;
            }
            goto LABEL_250;
          }
          v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v89 + 88LL))(v89, *((_QWORD *)a4 + 10));
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v62 = RdpWppGetCurrentThreadActivityIdPrefix();
              v63 = 77;
              v64 = "put_ClassId failed";
              goto LABEL_159;
            }
            goto LABEL_250;
          }
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v85 + 96LL))(v85, 0, &v80);
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_250;
            }
            v62 = RdpWppGetCurrentThreadActivityIdPrefix();
            v63 = 71;
LABEL_228:
            v64 = "IActionCollection::Create failed";
            goto LABEL_159;
          }
          v7 = (**v80)(v80, &IID_IExecAction, &v84);
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v62 = RdpWppGetCurrentThreadActivityIdPrefix();
              v63 = 72;
              v64 = "QueryInterface failed when creating the exec action";
              goto LABEL_159;
            }
            goto LABEL_250;
          }
          v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v84 + 88LL))(v84, *((_QWORD *)a4 + 10));
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v62 = RdpWppGetCurrentThreadActivityIdPrefix();
              v63 = 73;
              v64 = "put_Path failed";
              goto LABEL_159;
            }
            goto LABEL_250;
          }
          v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v84 + 104LL))(v84, *((_QWORD *)a4 + 11));
          if ( v7 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v62 = RdpWppGetCurrentThreadActivityIdPrefix();
              v63 = 74;
              v64 = "put_Arguments failed";
              goto LABEL_159;
            }
            goto LABEL_250;
          }
        }
        RegisterTaskDefinition = a2->lpVtbl->RegisterTaskDefinition;
        VariantInit(&pvarg);
        v70 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        VariantInit(&v90);
        v72 = *(_OWORD *)&v90.vt;
        v73 = v90.pRecInfo;
        VariantInit(&nSize_8);
        v93 = v70;
        v94 = pRecInfo;
        v95 = v72;
        v96 = v73;
        v97 = nSize_8;
        v7 = ((__int64 (__fastcall *)(struct ITaskFolder *, _QWORD, __int64, __int64, VARIANTARG *, __int128 *, int, __int128 *, struct IRegisteredTask **))RegisterTaskDefinition)(
               a2,
               *(_QWORD *)a4,
               v79,
               2,
               &v97,
               &v95,
               3,
               &v93,
               a3);
        _variant_t::~_variant_t((_variant_t *)&nSize_8);
        _variant_t::~_variant_t((_variant_t *)&v90);
        _variant_t::~_variant_t((_variant_t *)&pvarg);
        if ( v7 >= 0 )
        {
          v7 = 0;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v62 = RdpWppGetCurrentThreadActivityIdPrefix();
          v63 = 79;
          v64 = "RegisterTaskDefinition failed";
          goto LABEL_159;
        }
        goto LABEL_250;
      }
      if ( v47 > 0 )
        v7 = (unsigned __int16)v47 | 0x80070000;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_252;
      }
      v65 = RdpWppGetCurrentThreadActivityIdPrefix();
      v66 = 65;
    }
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v66, WPP_060bbe8053683a966e9955f0decff737_Traceguids, v65);
    goto LABEL_252;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 38;
    v10 = "get_RegistrationInfo failed";
    goto LABEL_6;
  }
LABEL_252:
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v89);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v84);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v80);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v85);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v81);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v86);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v82);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v87);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v76);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v88);
  ComPlainSmartPtr<IXMLDOMNamedNodeMap>::~ComPlainSmartPtr<IXMLDOMNamedNodeMap>(&v79);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180043df8  mov     rax, rsp
0x180043dfb  push    rbp
0x180043dfc  push    rbx
0x180043dfd  push    rsi
0x180043dfe  push    rdi
0x180043dff  push    r12
0x180043e01  push    r13
0x180043e03  push    r14
0x180043e05  push    r15
0x180043e07  lea     rbp, [rax-908h]
0x180043e0e  sub     rsp, 9C8h
0x180043e15  mov     [rbp+900h+var_900], 0FFFFFFFFFFFFFFFEh
0x180043e1d  movaps  xmmword ptr [rax-58h], xmm6
0x180043e21  movaps  xmmword ptr [rax-68h], xmm7
0x180043e25  movaps  xmmword ptr [rax-78h], xmm8
0x180043e2a  movaps  xmmword ptr [rax-88h], xmm9
0x180043e32  mov     rax, cs:__security_cookie
0x180043e39  xor     rax, rsp
0x180043e3c  mov     [rbp+900h+var_90], rax
0x180043e43  mov     rsi, r9
0x180043e46  mov     r12, r8
0x180043e49  mov     r15, rdx
0x180043e4c  xor     r13d, r13d
0x180043e4f  mov     [rsp+0A00h+var_988], r13
0x180043e54  mov     [rbp+900h+var_940], r13
0x180043e58  mov     [rsp+0A00h+var_9B0], r13
0x180043e5d  mov     [rbp+900h+var_948], r13
0x180043e61  mov     [rbp+900h+var_970], r13
0x180043e65  mov     [rbp+900h+var_950], r13
0x180043e69  mov     [rbp+900h+var_978], r13
0x180043e6d  mov     [rbp+900h+var_958], r13
0x180043e71  mov     [rbp+900h+var_980], r13
0x180043e75  mov     [rbp+900h+var_960], r13
0x180043e79  mov     [rbp+900h+var_938], r13
0x180043e7d  mov     [rsp+0A00h+nSize], r13d
0x180043e82  mov     rax, [rcx]
0x180043e85  lea     r8, [rsp+0A00h+var_988]
0x180043e8a  xor     edx, edx
0x180043e8c  mov     rax, [rax+48h]
0x180043e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e95  mov     ebx, eax
0x180043e97  test    eax, eax
0x180043e99  jns     short loc_180043EFE
0x180043e9b  lea     rax, WPP_GLOBAL_Control
0x180043ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180043ea9  cmp     rcx, rax
0x180043eac  jz      loc_1800450F8
0x180043eb2  test    byte ptr [rcx+1Ch], 8
0x180043eb6  jz      loc_1800450F8
0x180043ebc  cmp     byte ptr [rcx+19h], 2
0x180043ec0  jb      loc_1800450F8
0x180043ec6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043ecb  lea     edx, [r13+25h]
0x180043ecf  lea     rcx, aNewtaskFailed; "NewTask failed"
0x180043ed6  mov     dword ptr [rsp+0A00h+var_9D8], ebx
0x180043eda  mov     [rsp+0A00h+var_9E0], rcx
0x180043edf  mov     r9d, eax
0x180043ee2  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180043ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180043ef0  mov     rcx, [rcx+10h]
0x180043ef4  call    WPP_SF_DsD
0x180043ef9  jmp     loc_1800450F8
0x180043efe  mov     rcx, [rsp+0A00h+var_988]
0x180043f03  mov     rax, [rcx]
0x180043f06  lea     rdx, [rbp+900h+var_940]
0x180043f0a  mov     rax, [rax+38h]
0x180043f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f13  mov     ebx, eax
0x180043f15  test    eax, eax
0x180043f17  jns     short loc_180043F5A
0x180043f19  lea     rax, WPP_GLOBAL_Control
0x180043f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f27  cmp     rcx, rax
0x180043f2a  jz      loc_1800450F8
0x180043f30  test    byte ptr [rcx+1Ch], 8
0x180043f34  jz      loc_1800450F8
0x180043f3a  cmp     byte ptr [rcx+19h], 2
0x180043f3e  jb      loc_1800450F8
0x180043f44  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043f49  mov     edx, 26h ; '&'
0x180043f4e  lea     rcx, aGetRegistratio; "get_RegistrationInfo failed"
0x180043f55  jmp     loc_180043ED6
0x180043f5a  mov     r14d, 400h
0x180043f60  mov     r9d, r14d; cchBufferMax
0x180043f63  lea     r8, [rbp+900h+Buffer]; lpBuffer
0x180043f67  mov     edx, [rsi+8]; uID
0x180043f6a  mov     rcx, cs:g_hinst; hInstance
0x180043f71  call    cs:__imp_LoadStringW
0x180043f77  test    eax, eax
0x180043f79  jg      short loc_180043FF2
0x180043f7b  lea     rax, WPP_GLOBAL_Control
0x180043f82  mov     edi, 80070000h
0x180043f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f8e  cmp     rcx, rax
0x180043f91  jz      short loc_180043FD8
0x180043f93  test    byte ptr [rcx+1Ch], 8
0x180043f97  jz      short loc_180043FD8
0x180043f99  cmp     byte ptr [rcx+19h], 2
0x180043f9d  jb      short loc_180043FD8
0x180043f9f  call    cs:__imp_GetLastError
0x180043fa5  mov     ebx, eax
0x180043fa7  test    eax, eax
0x180043fa9  jle     short loc_180043FB0
0x180043fab  movzx   ebx, ax
0x180043fae  or      ebx, edi
0x180043fb0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180043fb5  mov     edx, 27h ; '''
0x180043fba  mov     dword ptr [rsp+0A00h+var_9E0], ebx
0x180043fbe  mov     r9d, eax
0x180043fc1  lea     r8, WPP_060bbe8053683a966e9955f0decff737_Traceguids
0x180043fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180043fcf  mov     rcx, [rcx+10h]
0x180043fd3  call    WPP_SF_Dd
0x180043fd8  call    cs:__imp_GetLastError
0x180043fde  mov     ebx, eax
0x180043fe0  test    eax, eax
0x180043fe2  jle     loc_1800450F8
0x180043fe8  movzx   ebx, ax
0x180043feb  or      ebx, edi
0x180043fed  jmp     loc_1800450F8
0x180043ff2  mov     rbx, [rbp+900h+var_940]
0x180043ff6  mov     rax, [rbx]
0x180043ff9  mov     rdi, [rax+40h]
0x180043ffd  lea     rdx, [rbp+900h+Buffer]; unsigned __int16 *
0x180044001  lea     rcx, [rbp+900h+var_968]; this
0x180044005  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18004400a  nop
0x18004400b  mov     rcx, [rax]
0x18004400e  test    rcx, rcx
0x180044011  jz      short loc_180044018
0x180044013  mov     rdx, [rcx]
0x180044016  jmp     short loc_18004401B
0x180044018  mov     rdx, r13
0x18004401b  mov     rcx, rbx
0x18004401e  mov     rax, rdi
0x180044021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044026  nop
0x180044027  lea     rcx, [rbp+900h+var_968]; this
0x18004402b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180044030  mov     r9d, r14d; cchBufferMax
0x180044033  lea     r8, [rbp+900h+Buffer]; lpBuffer
0x180044037  mov     edx, 3CF2h; uID
0x18004403c  mov     rcx, cs:g_hinst; hInstance
0x180044043  call    cs:__imp_LoadStringW
0x180044049  test    eax, eax
0x18004404b  jg      short loc_18004409D
0x18004404d  lea     rax, WPP_GLOBAL_Control
0x180044054  mov     edi, 80070000h
0x180044059  mov     rcx, cs:WPP_GLOBAL_Control
0x180044060  cmp     rcx, rax
0x180044063  jz      loc_180043FD8
0x180044069  test    byte ptr [rcx+1Ch], 8
0x18004406d  jz      loc_180043FD8
0x180044073  cmp     byte ptr [rcx+19h], 2
0x180044077  jb      loc_180043FD8
0x18004407d  call    cs:__imp_GetLastError
0x180044083  mov     ebx, eax
0x180044085  test    eax, eax
0x180044087  jle     short loc_18004408E
0x180044089  movzx   ebx, ax
0x18004408c  or      ebx, edi
0x18004408e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180044093  mov     edx, 29h ; ')'
0x180044098  jmp     loc_180043FBA
0x18004409d  mov     rbx, [rbp+900h+var_940]
0x1800440a1  mov     rax, [rbx]
0x1800440a4  mov     rdi, [rax+50h]
0x1800440a8  lea     rdx, [rbp+900h+Buffer]; unsigned __int16 *
0x1800440ac  lea     rcx, [rbp+900h+var_968]; this
0x1800440b0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800440b5  nop
0x1800440b6  mov     rcx, [rax]
0x1800440b9  test    rcx, rcx
0x1800440bc  jz      short loc_1800440C3
0x1800440be  mov     rdx, [rcx]
0x1800440c1  jmp     short loc_1800440C6
0x1800440c3  mov     rdx, r13
0x1800440c6  mov     rcx, rbx
0x1800440c9  mov     rax, rdi
0x1800440cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440d1  nop
0x1800440d2  lea     rcx, [rbp+900h+var_968]; this
0x1800440d6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800440db  mov     rcx, [rsp+0A00h+var_988]
0x1800440e0  mov     rax, [rcx]
0x1800440e3  lea     rdx, [rsp+0A00h+var_9B0]
0x1800440e8  mov     rax, [rax+58h]
0x1800440ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440f1  mov     ebx, eax
0x1800440f3  test    eax, eax
0x1800440f5  jns     short loc_180044138
0x1800440f7  lea     rax, WPP_GLOBAL_Control
0x1800440fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180044105  cmp     rcx, rax
0x180044108  jz      loc_1800450F8
0x18004410e  test    byte ptr [rcx+1Ch], 8
0x180044112  jz      loc_1800450F8
0x180044118  cmp     byte ptr [rcx+19h], 2
0x18004411c  jb      loc_1800450F8
0x180044122  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180044127  mov     edx, 2Bh ; '+'
0x18004412c  lea     rcx, aGetSettingsFai; "get_Settings failed"
0x180044133  jmp     loc_180043ED6
0x180044138  mov     rdi, [rsp+0A00h+var_9B0]
0x18004413d  mov     rax, [rdi]
0x180044140  mov     rbx, [rax+40h]
0x180044144  mov     r14d, 0Bh
0x18004414a  mov     word ptr [rsp+0A00h+nSize+8], r14w
0x180044150  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044154  mov     word ptr [rsp+0A00h+var_998], ax
0x180044159  lea     rcx, [rsp+0A00h+nSize+8]; pvarSrc
0x18004415e  call    ??B_variant_t@@QEBAFXZ; _variant_t::operator short(void)
0x180044163  movzx   edx, ax
0x180044166  mov     rcx, rdi
0x180044169  mov     rax, rbx
0x18004416c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044171  mov     ebx, eax
0x180044173  lea     rcx, [rsp+0A00h+nSize+8]; this
0x180044178  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004417d  test    ebx, ebx
0x18004417f  jns     short loc_1800441C1
0x180044181  lea     rax, WPP_GLOBAL_Control
0x180044188  mov     rcx, cs:WPP_GLOBAL_Control
0x18004418f  cmp     rcx, rax
0x180044192  jz      loc_1800450F8
0x180044198  test    byte ptr [rcx+1Ch], 8
0x18004419c  jz      loc_1800450F8
0x1800441a2  cmp     byte ptr [rcx+19h], 2
0x1800441a6  jb      loc_1800450F8
0x1800441ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800441b1  lea     edx, [r14+21h]
0x1800441b5  lea     rcx, aPutAllowdemand; "put_AllowDemandStart failed"
0x1800441bc  jmp     loc_180043ED6
0x1800441c1  mov     rdi, [rsp+0A00h+var_9B0]
0x1800441c6  mov     rax, [rdi]
0x1800441c9  mov     rbx, [rax+0A0h]
0x1800441d0  mov     word ptr [rsp+0A00h+nSize+8], r14w
0x1800441d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800441da  mov     word ptr [rsp+0A00h+var_998], ax
0x1800441df  lea     rcx, [rsp+0A00h+nSize+8]; pvarSrc
0x1800441e4  call    ??B_variant_t@@QEBAFXZ; _variant_t::operator short(void)
0x1800441e9  movzx   edx, ax
0x1800441ec  mov     rcx, rdi
0x1800441ef  mov     rax, rbx
0x1800441f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441f7  mov     ebx, eax
0x1800441f9  lea     rcx, [rsp+0A00h+nSize+8]; this
0x1800441fe  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180044203  test    ebx, ebx
0x180044205  jns     short loc_180044248
0x180044207  lea     rax, WPP_GLOBAL_Control
0x18004420e  mov     rcx, cs:WPP_GLOBAL_Control
0x180044215  cmp     rcx, rax
0x180044218  jz      loc_1800450F8
0x18004421e  test    byte ptr [rcx+1Ch], 8
0x180044222  jz      loc_1800450F8
0x180044228  cmp     byte ptr [rcx+19h], 2
0x18004422c  jb      loc_1800450F8
0x180044232  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180044237  mov     edx, 2Dh ; '-'
0x18004423c  lea     rcx, aPutAllowhardte; "put_AllowHardTerminate failed"
0x180044243  jmp     loc_180043ED6
0x180044248  mov     rcx, [rsp+0A00h+var_9B0]
0x18004424d  mov     rax, [rcx]
0x180044250  mov     edx, [rsi+28h]
0x180044253  mov     rax, [rax+70h]
0x180044257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004425c  mov     ebx, eax
0x18004425e  test    eax, eax
0x180044260  jns     short loc_1800442A3
0x180044262  lea     rax, WPP_GLOBAL_Control
0x180044269  mov     rcx, cs:WPP_GLOBAL_Control
0x180044270  cmp     rcx, rax
0x180044273  jz      loc_1800450F8
0x180044279  test    byte ptr [rcx+1Ch], 8
0x18004427d  jz      loc_1800450F8
0x180044283  cmp     byte ptr [rcx+19h], 2
0x180044287  jb      loc_1800450F8
0x18004428d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180044292  mov     edx, 2Eh ; '.'
0x180044297  lea     rcx, aPutMultipleins; "put_MultipleInstances failed"
0x18004429e  jmp     loc_180043ED6
0x1800442a3  mov     rdi, [rsp+0A00h+var_9B0]
0x1800442a8  mov     rax, [rdi]
0x1800442ab  mov     rbx, [rax+90h]
0x1800442b2  mov     word ptr [rsp+0A00h+nSize+8], r14w
0x1800442b8  mov     word ptr [rsp+0A00h+var_998], r13w
0x1800442be  lea     rcx, [rsp+0A00h+nSize+8]; pvarSrc
0x1800442c3  call    ??B_variant_t@@QEBAFXZ; _variant_t::operator short(void)
0x1800442c8  movzx   edx, ax
0x1800442cb  mov     rcx, rdi
0x1800442ce  mov     rax, rbx
0x1800442d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442d6  mov     ebx, eax
0x1800442d8  lea     rcx, [rsp+0A00h+nSize+8]; this
0x1800442dd  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800442e2  test    ebx, ebx
0x1800442e4  jns     short loc_180044327
0x1800442e6  lea     rax, WPP_GLOBAL_Control
0x1800442ed  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
