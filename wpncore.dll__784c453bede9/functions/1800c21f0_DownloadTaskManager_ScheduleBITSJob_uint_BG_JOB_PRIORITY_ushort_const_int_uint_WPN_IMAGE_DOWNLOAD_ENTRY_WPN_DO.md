# DownloadTaskManager::ScheduleBITSJob(uint,BG_JOB_PRIORITY,ushort const *,int,uint,WPN_IMAGE_DOWNLOAD_ENTRY *,WPN_DOWNLOAD_TASK *,uint)

- ea: `0x1800c21f0`
- end: `0x1800c2d56`
- name: `?ScheduleBITSJob@DownloadTaskManager@@AEAAJIW4BG_JOB_PRIORITY@@PEBGHIPEAUWPN_IMAGE_DOWNLOAD_ENTRY@@PEAUWPN_DOWNLOAD_TASK@@I@Z`
- size: `2918`
- prototype: `int(DownloadTaskManager *__hidden this, unsigned int, enum BG_JOB_PRIORITY, const unsigned __int16 *, int, unsigned int, struct WPN_IMAGE_DOWNLOAD_ENTRY *, struct WPN_DOWNLOAD_TASK *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0c30`

## callees

- `0x180004e38`
- `0x18002ee38`
- `0x18002ee68`
- `0x180067d58`
- `0x180067de0`
- `0x1800a0b2c`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800c059c`
- `0x1800c21f0`
- `0x1800c2d88`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2cbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2bf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c2cbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2bff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2ccd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2bff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c2ccd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c2358`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c2358`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c2c18`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c2c18`

## string_xrefs

- `0x1800c22c1`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2397`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c23f3`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c246d`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c24f9`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2577`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c25f3`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2669`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c26de`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2755`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c27ce`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2838`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c289a`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c28fd`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2964`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c29d4`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2a52`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2abf`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2b21`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`
- `0x1800c2b7a`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\downloadtaskmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DownloadTaskManager::ScheduleBITSJob(
        DownloadTaskManager *this,
        int a2,
        enum BG_JOB_PRIORITY a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned int a6,
        struct WPN_IMAGE_DOWNLOAD_ENTRY *a7,
        struct WPN_DOWNLOAD_TASK *a8,
        unsigned int a9)
{
  unsigned int v10; // r14d
  int v11; // eax
  unsigned int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rsi
  int v17; // eax
  BSTR v18; // rax
  __int64 v19; // rdi
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, const unsigned __int16 * near *, _QWORD, char *); // rbx
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rdi
  int v28; // eax
  int v29; // eax
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v31)(_QWORD, GUID *, __int64 *); // rdi
  int v32; // eax
  int v33; // eax
  __int128 v34; // xmm6
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  DownloadTaskManager *v40; // rdi
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  unsigned int v47; // r14d
  __int64 v48; // rdi
  void *v49; // r15
  HANDLE ProcessHeap; // rax
  OLECHAR *v51; // rcx
  int v52; // r13d
  int v53; // edx
  int v54; // ecx
  unsigned __int16 *v55; // rdi
  __int64 v56; // rsi
  char v57; // di
  int v58; // ebx
  HANDLE v59; // rax
  int v61; // [rsp+28h] [rbp-E0h]
  __int64 v62; // [rsp+48h] [rbp-C0h] BYREF
  int v63[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v64; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v65; // [rsp+60h] [rbp-A8h]
  unsigned __int16 *v66; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v67[24]; // [rsp+70h] [rbp-98h] BYREF
  enum BG_JOB_PRIORITY v68; // [rsp+88h] [rbp-80h]
  int v69; // [rsp+8Ch] [rbp-7Ch]
  __int64 v70; // [rsp+90h] [rbp-78h] BYREF
  __int128 v71; // [rsp+98h] [rbp-70h] BYREF
  DownloadTaskManager *v72; // [rsp+A8h] [rbp-60h]
  __int128 v73; // [rsp+B8h] [rbp-50h]
  _OWORD v74[2]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v75[18]; // [rsp+E8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E0h] [rbp+D8h]

  v68 = a3;
  v69 = a2;
  v72 = this;
  LODWORD(v65) = 0;
  v73 = 0;
  memset(v74, 0, 24);
  v66 = 0;
  *(_QWORD *)v63 = 0;
  v70 = 0;
  v64 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)a8 + 33) + 8LL))((char *)a8 + 264) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v10 = a6;
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v11 = WpnStrCpy(a4, &v66);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x696,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v11,
      v61);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v14 = 32;
LABEL_11:
      v15 = v12;
LABEL_20:
      WPP_SF_d(v13[2], v14, WPP_553fcece65bb3d6b1fb29c99f4a5b044_Traceguids, v15);
    }
    goto LABEL_95;
  }
  v16 = 0;
  while ( (unsigned int)v16 < v10 )
  {
    *((_DWORD *)a8 + 6 * v16 + 12) = *((_DWORD *)a7 + 6 * v16);
    *((_QWORD *)a8 + 3 * v16 + 7) = 0;
    v17 = WpnStrCpy(*((const unsigned __int16 **)a7 + 3 * v16 + 1), (unsigned __int16 **)a8 + 3 * v16 + 7);
    v12 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6A2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
        (const char *)(unsigned int)v17,
        v61);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v14 = 33;
        goto LABEL_11;
      }
LABEL_95:
      v47 = 0;
      if ( a6 )
      {
        v48 = 0;
        do
        {
          v49 = (void *)*((_QWORD *)a8 + 3 * v48 + 7);
          if ( v49 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v49);
            *((_QWORD *)a8 + 3 * v48 + 7) = 0;
          }
          v51 = (OLECHAR *)*((_QWORD *)a8 + 3 * v48 + 8);
          if ( v51 )
          {
            SysFreeString(v51);
            *((_QWORD *)a8 + 3 * v48 + 8) = 0;
          }
          ++v47;
          ++v48;
        }
        while ( v47 < a6 );
      }
      v52 = v65;
LABEL_109:
      v55 = v66;
      goto LABEL_110;
    }
    *((_QWORD *)a8 + 3 * v16 + 8) = 0;
    v18 = SysAllocString(*((const OLECHAR **)a7 + 3 * v16 + 2));
    *((_QWORD *)a8 + 3 * v16 + 8) = v18;
    if ( !v18 )
    {
      v12 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6AB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
        (const char *)0x8007000ELL,
        v61);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v14 = 34;
        v15 = 2147942414LL;
        goto LABEL_20;
      }
      goto LABEL_95;
    }
    v19 = 2LL * (unsigned int)v16;
    v75[v19 + 1] = v18;
    v75[v19] = *((_QWORD *)a8 + 3 * v16 + 7);
    v16 = (unsigned int)(v16 + 1);
    v10 = a6;
  }
  *((_DWORD *)a8 + 11) = v10;
  CRPCTimeout::CRPCTimeout((CRPCTimeout *)v67, 0xBB8u);
  v62 = 0;
  v20 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IBackgroundCopyManager>(
          (char *)a8 + 264,
          &v62);
  v12 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6BD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v20,
      v61);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 35;
LABEL_93:
    WPP_SF_d(v21[2], v22, WPP_553fcece65bb3d6b1fb29c99f4a5b044_Traceguids, v12);
LABEL_94:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v67);
    goto LABEL_95;
  }
  v23 = v62;
  v24 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 * near *, _QWORD, char *))(*(_QWORD *)v62 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v63);
  v25 = v24(v23, (&g_BITSJobDisplayNames)[v69], 0, (char *)a8 + 8);
  v12 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6C4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v25,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 36;
    goto LABEL_93;
  }
  LODWORD(v65) = 1;
  v26 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v63;
  v27 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v63;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
  v28 = v27(v26, &GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af, &v70);
  v12 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6CD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v28,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 37;
    goto LABEL_93;
  }
  v74[0] = 0x400000002uLL;
  v29 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v70 + 328LL))(v70, v74);
  v12 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6D7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v29,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 38;
    goto LABEL_93;
  }
  v30 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v63;
  v31 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v63;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  v32 = v31(v30, &GUID_e847030c_bbba_4657_af6d_484aa42bf1fe, &v64);
  v12 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6DA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v32,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 39;
    goto LABEL_93;
  }
  LODWORD(v73) = 2;
  v71 = v73;
  v33 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v64 + 424LL))(v64, 7, &v71);
  v12 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6E2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v33,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 40;
    goto LABEL_93;
  }
  LODWORD(v73) = 1;
  v34 = v73;
  v71 = v73;
  v35 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v64 + 424LL))(v64, 4, &v71);
  v12 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6EA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v35,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 41;
    goto LABEL_93;
  }
  if ( !a5 )
  {
    v71 = v34;
    v36 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v64 + 424LL))(v64, 6, &v71);
    v12 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x6F3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
        (const char *)(unsigned int)v36,
        (int)v63);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_94;
      v22 = (unsigned int)(a5 + 42);
      goto LABEL_93;
    }
  }
  v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)v63 + 24LL))(*(_QWORD *)v63, a6, v75);
  v12 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6FB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v37,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 43;
    goto LABEL_93;
  }
  v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v63 + 232LL))(*(_QWORD *)v63, 0);
  v12 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x702,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v38,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 44;
    goto LABEL_93;
  }
  v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v63 + 168LL))(*(_QWORD *)v63, (unsigned int)v68);
  v12 = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x709,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v39,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 45;
    goto LABEL_93;
  }
  v40 = v72;
  v41 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v64 + 408LL))(v64, *((unsigned int *)v72 + 19));
  v12 = v41;
  if ( v41 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x710,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v41,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 46;
    goto LABEL_93;
  }
  v71 = v34;
  v42 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v64 + 424LL))(v64, 3, &v71);
  v12 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x717,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v42,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 47;
    goto LABEL_93;
  }
  *(_QWORD *)&v73 = a9 * a6;
  v71 = v73;
  v43 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v64 + 424LL))(v64, 5, &v71);
  v12 = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x722,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v43,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 48;
    goto LABEL_93;
  }
  v44 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)v63 + 200LL))(
          *(_QWORD *)v63,
          ((unsigned __int64)v40 + 32) & -(__int64)(v40 != 0));
  v12 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x729,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v44,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 49;
    goto LABEL_93;
  }
  v45 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v63 + 184LL))(*(_QWORD *)v63, 3);
  v12 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x730,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v45,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 50;
    goto LABEL_93;
  }
  v46 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v63 + 56LL))(*(_QWORD *)v63);
  v12 = v46;
  LODWORD(v72) = v46;
  if ( v46 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x733,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\downloadtaskmanager.cpp",
      (const char *)(unsigned int)v46,
      (int)v63);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_94;
    v22 = 51;
    goto LABEL_93;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v67);
  *((_QWORD *)a8 + 4) = v66;
  *((_DWORD *)a8 + 6) ^= (*((_DWORD *)a8 + 6) ^ (16 * a5)) & 0x10;
  v55 = 0;
  v66 = 0;
  v52 = 0;
  v56 = 0;
  if ( a6 )
  {
    v57 = v68;
    v58 = v69;
    do
    {
      if ( (byte_18015DE48 & 8) != 0 )
        McTemplateU0qqqtz_EventWriteTransfer(
          v54,
          v53,
          v58,
          *((_DWORD *)a7 + 6 * v56),
          v57,
          a5,
          *((_QWORD *)a7 + 3 * v56 + 1));
      v56 = (unsigned int)(v56 + 1);
    }
    while ( (unsigned int)v56 < a6 );
    v12 = (unsigned int)v72;
    goto LABEL_109;
  }
LABEL_110:
  if ( v55 )
  {
    v59 = GetProcessHeap();
    HeapFree(v59, 0, v55);
  }
  if ( *(_QWORD *)v63 && v52 )
  {
    CRPCTimeout::CRPCTimeout((CRPCTimeout *)v67, 0x1F4u);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v63 + 64LL))(*(_QWORD *)v63);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v67);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v63);
  return v12;
}

```

## disassembly

```asm
0x1800c21f0  mov     rax, rsp
0x1800c21f3  push    rbp
0x1800c21f4  push    rbx
0x1800c21f5  push    rsi
0x1800c21f6  push    rdi
0x1800c21f7  push    r12
0x1800c21f9  push    r13
0x1800c21fb  push    r14
0x1800c21fd  push    r15
0x1800c21ff  lea     rbp, [rax-0D8h]
0x1800c2206  sub     rsp, 198h
0x1800c220d  movaps  xmmword ptr [rax-58h], xmm6
0x1800c2211  mov     rax, cs:__security_cookie
0x1800c2218  xor     rax, rsp
0x1800c221b  mov     [rbp+0D0h+var_60], rax
0x1800c221f  mov     rbx, r9
0x1800c2222  mov     [rbp+0D0h+var_150], r8d
0x1800c2226  mov     [rbp+0D0h+var_14C], edx
0x1800c2229  mov     [rbp+0D0h+var_130], rcx
0x1800c222d  mov     r12, [rbp+0D0h+arg_30]
0x1800c2234  mov     r13, [rbp+0D0h+arg_38]
0x1800c223b  mov     dword ptr [rsp+1D0h+var_178], 0
0x1800c2243  xorps   xmm0, xmm0
0x1800c2246  movups  [rbp+0D0h+var_120], xmm0
0x1800c224a  xorps   xmm1, xmm1
0x1800c224d  xor     eax, eax
0x1800c224f  movups  [rbp+0D0h+var_110], xmm1
0x1800c2253  mov     [rbp+0D0h+var_100], rax
0x1800c2257  mov     [rsp+1D0h+var_170], rax
0x1800c225c  mov     qword ptr [rsp+1D0h+var_188], rax
0x1800c2261  mov     [rbp+0D0h+var_148], rax
0x1800c2265  mov     [rsp+1D0h+var_180], rax
0x1800c226a  lea     rdi, [r13+108h]
0x1800c2271  mov     rax, [rdi]
0x1800c2274  mov     rcx, rdi
0x1800c2277  mov     rax, [rax+8]
0x1800c227b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2280  test    al, al
0x1800c2282  jnz     short loc_1800C2289
0x1800c2284  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Task->Bits.IsInitialized()")
0x1800c2289  mov     r14d, [rbp+0D0h+arg_28]
0x1800c2290  test    r14d, r14d
0x1800c2293  jnz     short loc_1800C229A
0x1800c2295  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Count > 0")
0x1800c229a  test    r12, r12
0x1800c229d  jnz     short loc_1800C22A4
0x1800c229f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "DownloadEntry != NULL")
0x1800c22a4  lea     rdx, [rsp+1D0h+var_170]; unsigned __int16 **
0x1800c22a9  mov     rcx, rbx; unsigned __int16 *
0x1800c22ac  call    ?WpnStrCpy@@YAJPEBGPEAPEAG@Z; WpnStrCpy(ushort const *,ushort * *)
0x1800c22b1  mov     ebx, eax
0x1800c22b3  test    eax, eax
0x1800c22b5  jns     short loc_1800C2300
0x1800c22b7  mov     rcx, [rbp+0D8h]; this
0x1800c22be  mov     r9d, eax; char *
0x1800c22c1  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c22c8  mov     edx, 696h; void *
0x1800c22cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c22d2  lea     rax, WPP_GLOBAL_Control
0x1800c22d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c22e0  cmp     rcx, rax
0x1800c22e3  jz      loc_1800C2BD2
0x1800c22e9  test    byte ptr [rcx+1Ch], 80h
0x1800c22ed  jz      loc_1800C2BD2
0x1800c22f3  mov     edx, 20h ; ' '
0x1800c22f8  mov     r9d, ebx
0x1800c22fb  jmp     loc_1800C23D4
0x1800c2300  xor     esi, esi
0x1800c2302  cmp     esi, r14d
0x1800c2305  jnb     loc_1800C242F
0x1800c230b  mov     edi, esi
0x1800c230d  lea     r14, [rsi+rsi*2]
0x1800c2311  lea     rcx, [rsi+rsi*2]
0x1800c2315  mov     eax, [r12+r14*8]
0x1800c2319  mov     [r13+rcx*8+30h], eax
0x1800c231e  lea     r15, ds:0[r14*8]
0x1800c2326  mov     qword ptr [r15+r13+38h], 0
0x1800c232f  lea     rdx, [r13+38h]
0x1800c2333  add     rdx, r15; unsigned __int16 **
0x1800c2336  mov     rcx, [r12+r14*8+8]; unsigned __int16 *
0x1800c233b  call    ?WpnStrCpy@@YAJPEBGPEAPEAG@Z; WpnStrCpy(ushort const *,ushort * *)
0x1800c2340  mov     ebx, eax
0x1800c2342  test    eax, eax
0x1800c2344  js      loc_1800C23E9
0x1800c234a  mov     qword ptr [r13+r14*8+40h], 0
0x1800c2353  mov     rcx, [r12+r14*8+10h]; psz
0x1800c2358  call    cs:__imp_SysAllocString
0x1800c235e  mov     [r13+r14*8+40h], rax
0x1800c2363  test    rax, rax
0x1800c2366  jz      short loc_1800C2388
0x1800c2368  add     rdi, rdi
0x1800c236b  mov     [rbp+rdi*8+0D0h+var_E8], rax
0x1800c2370  mov     rax, [r15+r13+38h]
0x1800c2375  mov     [rbp+rdi*8+0D0h+var_F0], rax
0x1800c237a  inc     esi
0x1800c237c  mov     r14d, [rbp+0D0h+arg_28]
0x1800c2383  jmp     loc_1800C2302
0x1800c2388  mov     ebx, 8007000Eh
0x1800c238d  mov     rcx, [rbp+0D8h]; this
0x1800c2394  mov     r9d, ebx; char *
0x1800c2397  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c239e  mov     edx, 6ABh; void *
0x1800c23a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c23a8  lea     rax, WPP_GLOBAL_Control
0x1800c23af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c23b6  cmp     rcx, rax
0x1800c23b9  jz      loc_1800C2BD2
0x1800c23bf  test    byte ptr [rcx+1Ch], 80h
0x1800c23c3  jz      loc_1800C2BD2
0x1800c23c9  mov     edx, 22h ; '"'
0x1800c23ce  mov     r9d, 8007000Eh
0x1800c23d4  lea     r8, WPP_553fcece65bb3d6b1fb29c99f4a5b044_Traceguids
0x1800c23db  mov     rcx, [rcx+10h]
0x1800c23df  call    WPP_SF_d
0x1800c23e4  jmp     loc_1800C2BD2
0x1800c23e9  mov     rcx, [rbp+0D8h]; this
0x1800c23f0  mov     r9d, ebx; char *
0x1800c23f3  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c23fa  mov     edx, 6A2h; void *
0x1800c23ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c2404  lea     rax, WPP_GLOBAL_Control
0x1800c240b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2412  cmp     rcx, rax
0x1800c2415  jz      loc_1800C2BD2
0x1800c241b  test    byte ptr [rcx+1Ch], 80h
0x1800c241f  jz      loc_1800C2BD2
0x1800c2425  mov     edx, 21h ; '!'
0x1800c242a  jmp     loc_1800C22F8
0x1800c242f  mov     [r13+2Ch], r14d
0x1800c2433  mov     edx, 0BB8h; DueTime
0x1800c2438  lea     rcx, [rsp+1D0h+var_168]; this
0x1800c243d  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x1800c2442  nop
0x1800c2443  mov     [rsp+1D0h+var_190], 0
0x1800c244c  lea     rdx, [rsp+1D0h+var_190]
0x1800c2451  lea     rcx, [r13+108h]
0x1800c2458  call    ??$CopyLocal@UIBackgroundCopyManager@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UIBackgroundCopyManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::CopyLocal<IBackgroundCopyManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IBackgroundCopyManager>>)
0x1800c245d  mov     ebx, eax
0x1800c245f  test    eax, eax
0x1800c2461  jns     short loc_1800C24A9
0x1800c2463  mov     rcx, [rbp+0D8h]; this
0x1800c246a  mov     r9d, eax; char *
0x1800c246d  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c2474  mov     edx, 6BDh; void *
0x1800c2479  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c247e  lea     rax, WPP_GLOBAL_Control
0x1800c2485  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c248c  cmp     rcx, rax
0x1800c248f  jz      loc_1800C2BBD
0x1800c2495  test    byte ptr [rcx+1Ch], 80h
0x1800c2499  jz      loc_1800C2BBD
0x1800c249f  mov     edx, 23h ; '#'
0x1800c24a4  jmp     loc_1800C2BA9
0x1800c24a9  mov     rdi, [rsp+1D0h+var_190]
0x1800c24ae  mov     rax, [rdi]
0x1800c24b1  mov     rbx, [rax+18h]
0x1800c24b5  lea     rcx, [rsp+1D0h+var_188]
0x1800c24ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c24bf  lea     r9, [r13+8]
0x1800c24c3  mov     edx, [rbp+0D0h+var_14C]
0x1800c24c6  lea     rcx, ?g_BITSJobDisplayNames@@3PAPEBGA; ushort const * near * g_BITSJobDisplayNames
0x1800c24cd  lea     rax, [rsp+1D0h+var_188]
0x1800c24d2  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x1800c24d7  xor     r8d, r8d
0x1800c24da  mov     rdx, [rcx+rdx*8]
0x1800c24de  mov     rcx, rdi
0x1800c24e1  mov     rax, rbx
0x1800c24e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c24e9  mov     ebx, eax
0x1800c24eb  test    eax, eax
0x1800c24ed  jns     short loc_1800C2535
0x1800c24ef  mov     rcx, [rbp+0D8h]; this
0x1800c24f6  mov     r9d, eax; char *
0x1800c24f9  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c2500  mov     edx, 6C4h; void *
0x1800c2505  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c250a  lea     rax, WPP_GLOBAL_Control
0x1800c2511  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2518  cmp     rcx, rax
0x1800c251b  jz      loc_1800C2BBD
0x1800c2521  test    byte ptr [rcx+1Ch], 80h
0x1800c2525  jz      loc_1800C2BBD
0x1800c252b  mov     edx, 24h ; '$'
0x1800c2530  jmp     loc_1800C2BA9
0x1800c2535  mov     dword ptr [rsp+1D0h+var_178], 1
0x1800c253d  mov     rbx, qword ptr [rsp+1D0h+var_188]
0x1800c2542  mov     rax, [rbx]
0x1800c2545  mov     rdi, [rax]
0x1800c2548  lea     rcx, [rbp+0D0h+var_148]
0x1800c254c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2551  lea     r8, [rbp+0D0h+var_148]
0x1800c2555  lea     rdx, _GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af
0x1800c255c  mov     rcx, rbx
0x1800c255f  mov     rax, rdi
0x1800c2562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2567  mov     ebx, eax
0x1800c2569  test    eax, eax
0x1800c256b  jns     short loc_1800C25B3
0x1800c256d  mov     rcx, [rbp+0D8h]; this
0x1800c2574  mov     r9d, eax; char *
0x1800c2577  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c257e  mov     edx, 6CDh; void *
0x1800c2583  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c2588  lea     rax, WPP_GLOBAL_Control
0x1800c258f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2596  cmp     rcx, rax
0x1800c2599  jz      loc_1800C2BBD
0x1800c259f  test    byte ptr [rcx+1Ch], 80h
0x1800c25a3  jz      loc_1800C2BBD
0x1800c25a9  mov     edx, 25h ; '%'
0x1800c25ae  jmp     loc_1800C2BA9
0x1800c25b3  mov     r14d, 4
0x1800c25b9  mov     dword ptr [rbp+0D0h+var_110+4], r14d
0x1800c25bd  xorps   xmm0, xmm0
0x1800c25c0  movdqu  [rbp+0D0h+var_110+8], xmm0
0x1800c25c5  lea     esi, [r14-2]
0x1800c25c9  mov     dword ptr [rbp+0D0h+var_110], esi
0x1800c25cc  mov     rcx, [rbp+0D0h+var_148]
0x1800c25d0  mov     rax, [rcx]
0x1800c25d3  lea     rdx, [rbp+0D0h+var_110]
0x1800c25d7  mov     rax, [rax+148h]
0x1800c25de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c25e3  mov     ebx, eax
0x1800c25e5  test    eax, eax
0x1800c25e7  jns     short loc_1800C262D
0x1800c25e9  mov     rcx, [rbp+0D8h]; this
0x1800c25f0  mov     r9d, eax; char *
0x1800c25f3  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c25fa  mov     edx, 6D7h; void *
0x1800c25ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c2604  lea     rax, WPP_GLOBAL_Control
0x1800c260b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2612  cmp     rcx, rax
0x1800c2615  jz      loc_1800C2BBD
0x1800c261b  test    byte ptr [rcx+1Ch], 80h
0x1800c261f  jz      loc_1800C2BBD
0x1800c2625  lea     edx, [rsi+24h]
0x1800c2628  jmp     loc_1800C2BA9
0x1800c262d  mov     rbx, qword ptr [rsp+1D0h+var_188]
0x1800c2632  mov     rax, [rbx]
0x1800c2635  mov     rdi, [rax]
0x1800c2638  lea     rcx, [rsp+1D0h+var_180]
0x1800c263d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2642  lea     r8, [rsp+1D0h+var_180]
0x1800c2647  lea     rdx, _GUID_e847030c_bbba_4657_af6d_484aa42bf1fe
0x1800c264e  mov     rcx, rbx
0x1800c2651  mov     rax, rdi
0x1800c2654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2659  mov     ebx, eax
0x1800c265b  test    eax, eax
0x1800c265d  jns     short loc_1800C26A5
0x1800c265f  mov     rcx, [rbp+0D8h]; this
0x1800c2666  mov     r9d, eax; char *
0x1800c2669  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c2670  mov     edx, 6DAh; void *
0x1800c2675  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c267a  lea     rax, WPP_GLOBAL_Control
0x1800c2681  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c2688  cmp     rcx, rax
0x1800c268b  jz      loc_1800C2BBD
0x1800c2691  test    byte ptr [rcx+1Ch], 80h
0x1800c2695  jz      loc_1800C2BBD
0x1800c269b  mov     edx, 27h ; '''
0x1800c26a0  jmp     loc_1800C2BA9
0x1800c26a5  mov     dword ptr [rbp+0D0h+var_120], esi
0x1800c26a8  mov     rcx, [rsp+1D0h+var_180]
0x1800c26ad  movaps  xmm0, [rbp+0D0h+var_120]
0x1800c26b1  movdqa  [rbp+0D0h+var_140], xmm0
0x1800c26b6  mov     rax, [rcx]
0x1800c26b9  lea     r8, [rbp+0D0h+var_140]
0x1800c26bd  mov     edx, 7
0x1800c26c2  mov     rax, [rax+1A8h]
0x1800c26c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c26ce  mov     ebx, eax
0x1800c26d0  test    eax, eax
0x1800c26d2  jns     short loc_1800C271A
0x1800c26d4  mov     rcx, [rbp+0D8h]; this
0x1800c26db  mov     r9d, eax; char *
0x1800c26de  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800c26e5  mov     edx, 6E2h; void *
0x1800c26ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c26ef  lea     rax, WPP_GLOBAL_Control
0x1800c26f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c26fd  cmp     rcx, rax
0x1800c2700  jz      loc_1800C2BBD
0x1800c2706  test    byte ptr [rcx+1Ch], 80h
0x1800c270a  jz      loc_1800C2BBD
0x1800c2710  mov     edx, 28h ; '('
0x1800c2715  jmp     loc_1800C2BA9
0x1800c271a  mov     dword ptr [rbp+0D0h+var_120], 1
0x1800c2721  mov     rcx, [rsp+1D0h+var_180]
0x1800c2726  movaps  xmm6, [rbp+0D0h+var_120]
0x1800c272a  movdqa  [rbp+0D0h+var_140], xmm6
0x1800c272f  mov     rax, [rcx]
0x1800c2732  lea     r8, [rbp+0D0h+var_140]
0x1800c2736  mov     edx, r14d
0x1800c2739  mov     rax, [rax+1A8h]
0x1800c2740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2745  mov     ebx, eax
0x1800c2747  test    eax, eax
  ... truncated ...
```
