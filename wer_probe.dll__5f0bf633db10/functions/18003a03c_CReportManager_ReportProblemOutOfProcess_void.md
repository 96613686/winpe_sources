# CReportManager::ReportProblemOutOfProcess(void)

- ea: `0x18003a03c`
- end: `0x18003aa02`
- name: `?ReportProblemOutOfProcess@CReportManager@@AEAAJXZ`
- size: `2502`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003285c`

## callees

- `0x180004bb4`
- `0x180006c34`
- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x180009ad4`
- `0x18000cc74`
- `0x18001dc24`
- `0x18001fe24`
- `0x180026498`
- `0x18003a03c`
- `0x18003aa08`
- `0x18003bf14`
- `0x18003c1e4`
- `0x180046674`
- `0x1800499e4`
- `0x180050db0`
- `0x1800517cc`
- `0x1800528b4`
- `0x180052984`
- `0x18005b8d1`
- `0x1800742f4`
- `0x18007b9d8`
- `0x18007bad4`
- `0x18007bbdc`
- `0x1800960b0`
- `0x1800a4d94`
- `0x1800aa000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003a501`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a709`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a858`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a709`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003a858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a987`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003a238`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003a238`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003a26f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003a26f`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a71a`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a864`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a71a`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003a864`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CReportManager::ReportProblemOutOfProcess(CReportManager *this)
{
  CReportManager *v1; // r14
  unsigned int i; // r9d
  CReport *v3; // rcx
  int v4; // r9d
  int v5; // edi
  int v6; // r8d
  unsigned int v7; // r9d
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  HANDLE v10; // rax
  HANDLE v11; // rbx
  struct OO_PROC_REPORT_DATA *v12; // rax
  struct OO_PROC_REPORT_DATA *v13; // rsi
  CReportManager *v14; // rcx
  const wchar_t *v15; // rcx
  __int64 v16; // rcx
  int v17; // ebx
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  int v20; // r9d
  DWORD CurrentProcessId; // eax
  int v22; // r13d
  int v23; // r12d
  int v24; // r15d
  int v25; // r14d
  int v26; // esi
  int v27; // edi
  int v28; // eax
  unsigned int j; // r8d
  UINT v30; // r14d
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  DWORD LastError; // eax
  unsigned int dwMaximumSizeLow; // [rsp+20h] [rbp-E0h]
  struct OO_PROC_REPORT_DATA *v46; // [rsp+40h] [rbp-C0h] BYREF
  DWORD OldMode; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v48[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct CReportFile *v49; // [rsp+58h] [rbp-A8h] BYREF
  void *v50; // [rsp+60h] [rbp-A0h] BYREF
  int v51; // [rsp+68h] [rbp-98h]
  int v52; // [rsp+6Ch] [rbp-94h]
  int v53; // [rsp+70h] [rbp-90h]
  int v54; // [rsp+74h] [rbp-8Ch]
  HANDLE hFileMappingObject; // [rsp+78h] [rbp-88h] BYREF
  void **v56; // [rsp+80h] [rbp-80h] BYREF
  __int128 v57; // [rsp+88h] [rbp-78h]
  unsigned int v58[2]; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+A0h] [rbp-60h]
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE Src[1408]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v62; // [rsp+640h] [rbp+540h] BYREF
  char v63[38]; // [rsp+642h] [rbp+542h] BYREF
  int v64; // [rsp+668h] [rbp+568h]
  unsigned int v65; // [rsp+66Ch] [rbp+56Ch]
  __int64 v66; // [rsp+6C8h] [rbp+5C8h]
  _DWORD v67[12]; // [rsp+BC0h] [rbp+AC0h] BYREF
  HANDLE v68; // [rsp+BF0h] [rbp+AF0h]
  __int64 v69; // [rsp+BF8h] [rbp+AF8h]
  __int64 v70; // [rsp+C00h] [rbp+B00h]
  __int64 v71; // [rsp+C08h] [rbp+B08h]
  __int64 v72; // [rsp+C10h] [rbp+B10h]
  __int64 v73; // [rsp+C18h] [rbp+B18h]
  __int64 v74; // [rsp+C20h] [rbp+B20h]
  __int64 v75; // [rsp+C28h] [rbp+B28h]
  __int64 v76; // [rsp+C30h] [rbp+B30h]
  __int64 v77; // [rsp+C38h] [rbp+B38h]
  __int64 v78; // [rsp+C40h] [rbp+B40h]
  HANDLE Value; // [rsp+1140h] [rbp+1040h] BYREF
  __int64 v80[11]; // [rsp+1148h] [rbp+1048h] BYREF
  int v81[2]; // [rsp+11A0h] [rbp+10A0h] BYREF
  const wchar_t *v82; // [rsp+11A8h] [rbp+10A8h]
  _QWORD v83[4]; // [rsp+1210h] [rbp+1110h] BYREF
  char v84[32]; // [rsp+1230h] [rbp+1130h] BYREF
  char v85[32]; // [rsp+1250h] [rbp+1150h] BYREF
  char v86[32]; // [rsp+1270h] [rbp+1170h] BYREF
  char v87[32]; // [rsp+1290h] [rbp+1190h] BYREF
  char v88[32]; // [rsp+12B0h] [rbp+11B0h] BYREF
  char v89[32]; // [rsp+12D0h] [rbp+11D0h] BYREF
  char v90[32]; // [rsp+12F0h] [rbp+11F0h] BYREF
  char v91[32]; // [rsp+1310h] [rbp+1210h] BYREF
  char v92[32]; // [rsp+1330h] [rbp+1230h] BYREF
  char v93[32]; // [rsp+1350h] [rbp+1250h] BYREF
  char v94[32]; // [rsp+1370h] [rbp+1270h] BYREF

  v1 = this;
  v50 = this;
  v49 = 0;
  hFileMappingObject = 0;
  v46 = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  *(_QWORD *)v48 = 0;
  OldMode = 0;
  `eh vector constructor iterator'(
    v83,
    0x20u,
    0xCu,
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
  memset_0(v81, 0, 0x70u);
  v56 = &CMemoryByteStream::`vftable';
  v57 = 0;
  *(_QWORD *)v58 = 0;
  v59 = 0;
  for ( i = 0; ; i = v4 + 1 )
  {
    v3 = (CReport *)*((_QWORD *)v1 + 1);
    if ( i >= (unsigned int)((__int64)(*((_QWORD *)v3 + 728) - *((_QWORD *)v3 + 727)) >> 3) )
      break;
    if ( (int)CReport::GetFileByIndex(v3, i, &v49) >= 0 && *((_QWORD *)v49 + 7) )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
      v5 = -2147024846;
      goto LABEL_106;
    }
  }
  CMemoryByteStream::OpenForReadWrite((CMemoryByteStream *)&v56);
  v5 = CReport::WriteReportToStream(*((CReport **)v1 + 1), (struct CByteStream *)&v56, v6, v7);
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_106;
    v9 = 38;
    goto LABEL_14;
  }
  v5 = CMemoryByteStream::SetFilePointer((CMemoryByteStream *)&v56, 0, 0, 0);
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_106;
    v9 = 39;
    goto LABEL_14;
  }
  FileMappingAttributes.nLength = 24;
  FileMappingAttributes.lpSecurityDescriptor = 0;
  FileMappingAttributes.bInheritHandle = 1;
  v10 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, v58[0] + 2624, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFileMappingObject, v10);
  v11 = hFileMappingObject;
  if ( (unsigned __int64)hFileMappingObject + 1 <= 1
    || (v12 = (struct OO_PROC_REPORT_DATA *)MapViewOfFile(hFileMappingObject, 6u, 0, 0, 0), v13 = v12, (v46 = v12) == 0) )
  {
    LastError = GetLastError();
    v5 = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_106;
  }
  v5 = CReportManager::PopulateSharedMemSectionForOutofProcReporting(v1, v12, (struct IWerByteStream *)&v56, v58[0]);
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_106;
    v9 = 40;
    goto LABEL_14;
  }
  v5 = CReport::ReleaseReportLock(*((CReport **)v1 + 1));
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_106;
    v9 = 41;
    goto LABEL_14;
  }
  v14 = (CReportManager *)(*((_QWORD *)v1 + 12) + 2288LL);
  if ( !*(_BYTE *)v14 || !CRegSetting::GetDwordData(v14) )
  {
    v5 = CReportManager::OutofProcDupHandles(v14, v13);
    if ( v5 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_106;
      v9 = 44;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, (unsigned int)v5);
      goto LABEL_106;
    }
    CurrentProcessId = GetCurrentProcessId();
    LODWORD(v49) = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                     v83,
                     L"%u",
                     CurrentProcessId);
    v54 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v84, L"%Id", v11);
    v53 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v85,
            L"%Id",
            *((_QWORD *)v13 + 1));
    v52 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v86,
            L"%Id",
            *((_QWORD *)v13 + 2));
    v51 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v87,
            L"%Id",
            *((_QWORD *)v13 + 84));
    v22 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v88,
            L"%Id",
            *((_QWORD *)v13 + 85));
    v23 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v89,
            L"%Id",
            *((_QWORD *)v13 + 4));
    v24 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v90,
            L"%Id",
            *((_QWORD *)v13 + 5));
    v25 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v91,
            L"%Id",
            *((_QWORD *)v13 + 164));
    v26 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v92,
            L"%Id",
            *((_QWORD *)v13 + 165));
    v27 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v93,
            L"%Id",
            *((_QWORD *)v46 + 244));
    v28 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v94,
            L"%Id",
            *((_QWORD *)v46 + 245));
    if ( (~v54 & ~v53 & ~v52 & ~v51 & ~v22 & ~v23 & ~v24 & ~v25 & ~v26 & ~v27 & ~v28 & ~(_DWORD)v49) >= 0 )
    {
      v19 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
      v5 = -2147467259;
      goto LABEL_104;
    }
    *(_QWORD *)v81 = L"-outproc";
    v82 = L"0";
    for ( j = 0; j < 0xC; ++j )
      *(_QWORD *)&v81[2 * j + 4] = v83[4 * j];
    v30 = SetErrorMode(1u);
    SetThreadErrorMode(1u, &OldMode);
    memset_0(v80, 0, 0x50u);
    Value = v11;
    v13 = v46;
    v31 = *((_QWORD *)v46 + 1);
    if ( v31 )
      v80[0] = *((_QWORD *)v46 + 1);
    v32 = (unsigned int)(v31 != 0) + 1;
    v33 = *((_QWORD *)v46 + 2);
    if ( v33 )
    {
      v80[v32 - 1] = v33;
      v32 = (unsigned int)(v32 + 1);
    }
    v34 = *((_QWORD *)v13 + 84);
    if ( v34 )
    {
      v80[v32 - 1] = v34;
      v32 = (unsigned int)(v32 + 1);
    }
    v35 = *((_QWORD *)v13 + 85);
    if ( v35 )
    {
      v80[v32 - 1] = v35;
      v32 = (unsigned int)(v32 + 1);
    }
    v36 = *((_QWORD *)v13 + 4);
    if ( v36 )
    {
      v80[v32 - 1] = v36;
      v32 = (unsigned int)(v32 + 1);
    }
    v37 = *((_QWORD *)v13 + 5);
    if ( v37 )
    {
      v80[v32 - 1] = v37;
      v32 = (unsigned int)(v32 + 1);
    }
    v38 = *((_QWORD *)v13 + 164);
    if ( v38 )
    {
      v80[v32 - 1] = v38;
      v32 = (unsigned int)(v32 + 1);
    }
    v39 = *((_QWORD *)v13 + 165);
    if ( v39 )
    {
      v80[v32 - 1] = v39;
      v32 = (unsigned int)(v32 + 1);
    }
    v40 = *((_QWORD *)v13 + 244);
    if ( v40 )
    {
      v80[v32 - 1] = v40;
      v32 = (unsigned int)(v32 + 1);
    }
    v41 = *((_QWORD *)v13 + 245);
    if ( v41 )
    {
      v80[v32 - 1] = v41;
      LODWORD(v32) = v32 + 1;
    }
    v5 = UtilLaunchWerManager((__int64)v81, 14, 2, 0, (__int64)v48, 0, v32, &Value);
    SetErrorMode(v30);
    SetThreadErrorMode(OldMode, 0);
    if ( v5 < 0 )
    {
      v19 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          &WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
          (unsigned int)v5);
      goto LABEL_104;
    }
    v17 = 1;
    if ( (unsigned __int64)(*(_QWORD *)v48 + 1LL) <= 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v19, v42);
    v1 = (CReportManager *)v50;
    goto LABEL_80;
  }
  v62 = 0;
  memset_0(v63, 0, 0x576u);
  memset_0(Src, 0, 0x578u);
  memcpy_0(v67, Src, 0x578u);
  v67[0] = 91751760;
  v67[10] = -536870910;
  v68 = v11;
  v69 = *((_QWORD *)v13 + 1);
  v70 = *((_QWORD *)v13 + 2);
  v71 = *((_QWORD *)v13 + 84);
  v72 = *((_QWORD *)v13 + 85);
  v73 = *((_QWORD *)v13 + 4);
  v74 = *((_QWORD *)v13 + 5);
  v75 = *((_QWORD *)v13 + 164);
  v76 = *((_QWORD *)v13 + 165);
  v77 = *((_QWORD *)v13 + 244);
  v78 = *((_QWORD *)v13 + 245);
  v5 = UtilSendMessageToWersvc(v15, (struct _WERSVC_MSG *)v67, (struct _WERSVC_MSG *)&v62, 0);
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_106;
    v9 = 42;
    goto LABEL_14;
  }
  if ( v64 == -536870912 )
  {
    v17 = 0;
    v18 = v66;
    if ( !v66 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v16, 0);
      v18 = v66;
    }
    tlx::unique_any<tlx::file_handle_traits>::reset(v48, v18);
LABEL_80:
    if ( (*(_DWORD *)(*((_QWORD *)v1 + 1) + 6616LL) & 0x400) != 0 )
      goto LABEL_102;
    v50 = *(void **)v48;
    UtilMsgWaitForMultipleObjects((const wchar_t *)v19, 1u, &v50, v20, dwMaximumSizeLow);
    v19 = *((unsigned int *)v13 + 654);
    if ( (int)v19 <= 7 )
    {
      if ( (_DWORD)v19 == 7 )
      {
        v5 = 1769477;
        goto LABEL_103;
      }
      v19 = (unsigned int)(v19 - 1);
      if ( !(_DWORD)v19 )
      {
        v5 = 1769474;
        goto LABEL_103;
      }
      v19 = (unsigned int)(v19 - 1);
      if ( !(_DWORD)v19 )
      {
        v5 = 1769473;
        goto LABEL_103;
      }
      v19 = (unsigned int)(v19 - 1);
      if ( !(_DWORD)v19 )
      {
        v5 = 1769472;
        goto LABEL_103;
      }
      v19 = (unsigned int)(v19 - 2);
      if ( !(_DWORD)v19 )
      {
        v5 = 1769475;
        goto LABEL_103;
      }
      if ( (_DWORD)v19 == 1 )
      {
        v5 = -2145681407;
        goto LABEL_103;
      }
      goto LABEL_98;
    }
    v19 = (unsigned int)(v19 - 8);
    if ( !(_DWORD)v19 )
    {
LABEL_102:
      v5 = 1769479;
    }
    else
    {
      v19 = (unsigned int)(v19 - 2);
      if ( (_DWORD)v19 )
      {
        v19 = (unsigned int)(v19 - 1);
        if ( (_DWORD)v19 )
        {
          if ( (_DWORD)v19 != 1 )
          {
LABEL_98:
            v5 = *((_DWORD *)v13 + 653);
            goto LABEL_103;
          }
          v5 = -2147024881;
        }
        else
        {
          v5 = 1769484;
        }
      }
      else
      {
        v5 = 1769483;
      }
    }
LABEL_103:
    if ( !v17 )
      goto LABEL_106;
LABEL_104:
    CReportManager::OutofProcCloseDupHandles((CReportManager *)v19, v46);
    goto LABEL_106;
  }
  v5 = v65 | 0x10000000;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v65);
LABEL_106:
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v56);
  `eh vector destructor iterator'(
    v83,
    0x20u,
    0xCu,
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(v48);
  __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6AHPEBX_Z1_UnmapViewOfFile__YAH0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&v46);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFileMappingObject);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003a03c  push    rbp
0x18003a03e  push    rbx
0x18003a03f  push    rsi
0x18003a040  push    rdi
0x18003a041  push    r12
0x18003a043  push    r13
0x18003a045  push    r14
0x18003a047  push    r15
0x18003a049  lea     rbp, [rsp-12A8h]
0x18003a051  mov     eax, 13A8h
0x18003a056  call    _alloca_probe
0x18003a05b  sub     rsp, rax
0x18003a05e  mov     rax, cs:__security_cookie
0x18003a065  xor     rax, rsp
0x18003a068  mov     [rbp+12E0h+var_50], rax
0x18003a06f  mov     r14, rcx
0x18003a072  mov     [rsp+13E0h+var_1380], rcx
0x18003a077  xor     r15d, r15d
0x18003a07a  mov     [rsp+13E0h+var_1388], r15
0x18003a07f  mov     [rsp+13E0h+hFileMappingObject], r15
0x18003a084  mov     [rsp+13E0h+var_13A0], r15
0x18003a089  xorps   xmm0, xmm0
0x18003a08c  xor     eax, eax
0x18003a08e  movups  xmmword ptr [rbp+12E0h+FileMappingAttributes.nLength], xmm0
0x18003a092  mov     qword ptr [rbp+12E0h+FileMappingAttributes.bInheritHandle], rax
0x18003a096  mov     qword ptr [rsp+13E0h+var_1390], r15
0x18003a09b  mov     [rsp+13E0h+OldMode], r15d
0x18003a0a0  lea     rax, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003a0a7  mov     qword ptr [rsp+13E0h+dwMaximumSizeLow], rax; void (*)(void *)
0x18003a0ac  lea     r9, ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; void (*)(void *)
0x18003a0b3  lea     edx, [r15+20h]; unsigned __int64
0x18003a0b7  lea     r8d, [r15+0Ch]; unsigned __int64
0x18003a0bb  lea     rcx, [rbp+12E0h+var_1D0]; void *
0x18003a0c2  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003a0c7  nop
0x18003a0c8  xor     edx, edx; Val
0x18003a0ca  lea     r8d, [r15+70h]; Size
0x18003a0ce  lea     rcx, [rbp+12E0h+var_240]; void *
0x18003a0d5  call    memset_0
0x18003a0da  lea     rax, ??_7CMemoryByteStream@@6B@; const CMemoryByteStream::`vftable'
0x18003a0e1  mov     [rbp+12E0h+var_1360], rax
0x18003a0e5  xorps   xmm0, xmm0
0x18003a0e8  movdqu  [rbp+12E0h+var_1358], xmm0
0x18003a0ed  mov     qword ptr [rbp+12E0h+var_1348], r15
0x18003a0f1  mov     [rbp+12E0h+var_1340], r15d
0x18003a0f5  mov     r9d, r15d
0x18003a0f8  lea     r12d, [r15+1]
0x18003a0fc  mov     rcx, [r14+8]; this
0x18003a100  mov     rax, [rcx+16C0h]
0x18003a107  sub     rax, [rcx+16B8h]
0x18003a10e  sar     rax, 3
0x18003a112  cmp     r9d, eax
0x18003a115  jnb     short loc_18003A170
0x18003a117  lea     r8, [rsp+13E0h+var_1388]; struct CReportFile **
0x18003a11c  mov     edx, r9d; unsigned int
0x18003a11f  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x18003a124  test    eax, eax
0x18003a126  js      short loc_18003A133
0x18003a128  mov     rax, [rsp+13E0h+var_1388]
0x18003a12d  cmp     [rax+38h], r15
0x18003a131  jnz     short loc_18003A138
0x18003a133  add     r9d, r12d
0x18003a136  jmp     short loc_18003A0FC
0x18003a138  lea     rax, WPP_GLOBAL_Control
0x18003a13f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a146  cmp     rcx, rax
0x18003a149  jz      short loc_18003A166
0x18003a14b  test    byte ptr [rcx+1Ch], 2
0x18003a14f  jz      short loc_18003A166
0x18003a151  mov     edx, 25h ; '%'
0x18003a156  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18003a15d  mov     rcx, [rcx+10h]
0x18003a161  call    WPP_SF_
0x18003a166  mov     edi, 80070032h
0x18003a16b  jmp     loc_18003A996
0x18003a170  lea     rcx, [rbp+12E0h+var_1360]; this
0x18003a174  call    ?OpenForReadWrite@CMemoryByteStream@@QEAAXXZ; CMemoryByteStream::OpenForReadWrite(void)
0x18003a179  lea     rdx, [rbp+12E0h+var_1360]; struct CByteStream *
0x18003a17d  mov     rcx, [r14+8]; this
0x18003a181  call    ?WriteReportToStream@CReport@@QEAAJPEAVCByteStream@@HK@Z; CReport::WriteReportToStream(CByteStream *,int,ulong)
0x18003a186  mov     edi, eax
0x18003a188  test    eax, eax
0x18003a18a  jns     short loc_18003A1CA
0x18003a18c  lea     rax, WPP_GLOBAL_Control
0x18003a193  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a19a  cmp     rcx, rax
0x18003a19d  jz      loc_18003A996
0x18003a1a3  test    [rcx+1Ch], r12b
0x18003a1a7  jz      loc_18003A996
0x18003a1ad  mov     edx, 26h ; '&'
0x18003a1b2  mov     r9d, edi
0x18003a1b5  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18003a1bc  mov     rcx, [rcx+10h]
0x18003a1c0  call    WPP_SF_d
0x18003a1c5  jmp     loc_18003A996
0x18003a1ca  xor     r9d, r9d; unsigned __int64 *
0x18003a1cd  xor     r8d, r8d; unsigned int
0x18003a1d0  xor     edx, edx; __int64
0x18003a1d2  lea     rcx, [rbp+12E0h+var_1360]; this
0x18003a1d6  call    ?SetFilePointer@CMemoryByteStream@@UEAAJ_JKPEA_K@Z; CMemoryByteStream::SetFilePointer(__int64,ulong,unsigned __int64 *)
0x18003a1db  mov     edi, eax
0x18003a1dd  test    eax, eax
0x18003a1df  jns     short loc_18003A209
0x18003a1e1  lea     rax, WPP_GLOBAL_Control
0x18003a1e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1ef  cmp     rcx, rax
0x18003a1f2  jz      loc_18003A996
0x18003a1f8  test    [rcx+1Ch], r12b
0x18003a1fc  jz      loc_18003A996
0x18003a202  mov     edx, 27h ; '''
0x18003a207  jmp     short loc_18003A1B2
0x18003a209  mov     [rbp+12E0h+FileMappingAttributes.nLength], 18h
0x18003a210  mov     [rbp+12E0h+FileMappingAttributes.lpSecurityDescriptor], r15
0x18003a214  mov     [rbp+12E0h+FileMappingAttributes.bInheritHandle], r12d
0x18003a218  mov     eax, [rbp+12E0h+var_1348]
0x18003a21b  add     eax, 0A40h
0x18003a220  mov     [rsp+13E0h+lpName], r15; lpName
0x18003a225  mov     [rsp+13E0h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18003a229  xor     r9d, r9d; dwMaximumSizeHigh
0x18003a22c  lea     r8d, [r9+4]; flProtect
0x18003a230  lea     rdx, [rbp+12E0h+FileMappingAttributes]; lpFileMappingAttributes
0x18003a234  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18003a238  call    cs:__imp_CreateFileMappingW
0x18003a23e  mov     rdx, rax
0x18003a241  lea     rcx, [rsp+13E0h+hFileMappingObject]
0x18003a246  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003a24b  mov     rbx, [rsp+13E0h+hFileMappingObject]
0x18003a250  lea     rax, [rbx+1]
0x18003a254  cmp     rax, r12
0x18003a257  jbe     loc_18003A987
0x18003a25d  mov     qword ptr [rsp+13E0h+dwMaximumSizeLow], r15; dwNumberOfBytesToMap
0x18003a262  xor     r9d, r9d; dwFileOffsetLow
0x18003a265  xor     r8d, r8d; dwFileOffsetHigh
0x18003a268  lea     edx, [r9+6]; dwDesiredAccess
0x18003a26c  mov     rcx, rbx; hFileMappingObject
0x18003a26f  call    cs:__imp_MapViewOfFile
0x18003a275  mov     rsi, rax
0x18003a278  mov     [rsp+13E0h+var_13A0], rax
0x18003a27d  test    rax, rax
0x18003a280  jz      loc_18003A987
0x18003a286  mov     r9d, [rbp+12E0h+var_1348]; unsigned int
0x18003a28a  lea     r8, [rbp+12E0h+var_1360]; struct IWerByteStream *
0x18003a28e  mov     rdx, rax; struct OO_PROC_REPORT_DATA *
0x18003a291  mov     rcx, r14; this
0x18003a294  call    ?PopulateSharedMemSectionForOutofProcReporting@CReportManager@@AEAAJPEAUOO_PROC_REPORT_DATA@@PEAUIWerByteStream@@K@Z; CReportManager::PopulateSharedMemSectionForOutofProcReporting(OO_PROC_REPORT_DATA *,IWerByteStream *,ulong)
0x18003a299  mov     edi, eax
0x18003a29b  test    eax, eax
0x18003a29d  jns     short loc_18003A2CA
0x18003a29f  lea     rax, WPP_GLOBAL_Control
0x18003a2a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a2ad  cmp     rcx, rax
0x18003a2b0  jz      loc_18003A996
0x18003a2b6  test    [rcx+1Ch], r12b
0x18003a2ba  jz      loc_18003A996
0x18003a2c0  mov     edx, 28h ; '('
0x18003a2c5  jmp     loc_18003A1B2
0x18003a2ca  mov     rcx, [r14+8]; this
0x18003a2ce  call    ?ReleaseReportLock@CReport@@QEAAJXZ; CReport::ReleaseReportLock(void)
0x18003a2d3  mov     edi, eax
0x18003a2d5  test    eax, eax
0x18003a2d7  jns     short loc_18003A304
0x18003a2d9  lea     rax, WPP_GLOBAL_Control
0x18003a2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a2e7  cmp     rcx, rax
0x18003a2ea  jz      loc_18003A996
0x18003a2f0  test    [rcx+1Ch], r12b
0x18003a2f4  jz      loc_18003A996
0x18003a2fa  mov     edx, 29h ; ')'
0x18003a2ff  jmp     loc_18003A1B2
0x18003a304  mov     rcx, [r14+60h]
0x18003a308  add     rcx, 8F0h; this
0x18003a30f  cmp     [rcx], r15b
0x18003a312  jz      loc_18003A4C8
0x18003a318  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18003a31d  test    eax, eax
0x18003a31f  jz      loc_18003A4C8
0x18003a325  mov     [rbp+12E0h+var_DA0], r15w
0x18003a32d  xor     edx, edx; Val
0x18003a32f  mov     r8d, 576h; Size
0x18003a335  lea     rcx, [rbp+12E0h+var_D9E]; void *
0x18003a33c  call    memset_0
0x18003a341  mov     edi, 578h
0x18003a346  mov     r8d, edi; Size
0x18003a349  xor     edx, edx; Val
0x18003a34b  lea     rcx, [rbp+12E0h+Src]; void *
0x18003a34f  call    memset_0
0x18003a354  lea     rcx, [rbp+12E0h+var_820]; void *
0x18003a35b  lea     rdx, [rbp+12E0h+Src]; Src
0x18003a35f  mov     r8d, edi; Size
0x18003a362  call    memcpy_0
0x18003a367  mov     [rbp+12E0h+var_820], 5780550h
0x18003a371  mov     [rbp+12E0h+var_7F8], 0E0000002h
0x18003a37b  mov     [rbp+12E0h+var_7F0], rbx
0x18003a382  mov     rax, [rsi+8]
0x18003a386  mov     [rbp+12E0h+var_7E8], rax
0x18003a38d  mov     rax, [rsi+10h]
0x18003a391  mov     [rbp+12E0h+var_7E0], rax
0x18003a398  mov     rax, [rsi+2A0h]
0x18003a39f  mov     [rbp+12E0h+var_7D8], rax
0x18003a3a6  mov     rax, [rsi+2A8h]
0x18003a3ad  mov     [rbp+12E0h+var_7D0], rax
0x18003a3b4  mov     rax, [rsi+20h]
0x18003a3b8  mov     [rbp+12E0h+var_7C8], rax
0x18003a3bf  mov     rax, [rsi+28h]
0x18003a3c3  mov     [rbp+12E0h+var_7C0], rax
0x18003a3ca  mov     rax, [rsi+520h]
0x18003a3d1  mov     [rbp+12E0h+var_7B8], rax
0x18003a3d8  mov     rax, [rsi+528h]
0x18003a3df  mov     [rbp+12E0h+var_7B0], rax
0x18003a3e6  mov     rax, [rsi+7A0h]
0x18003a3ed  mov     [rbp+12E0h+var_7A8], rax
0x18003a3f4  mov     rax, [rsi+7A8h]
0x18003a3fb  mov     [rbp+12E0h+var_7A0], rax
0x18003a402  xor     r9d, r9d; unsigned int
0x18003a405  lea     r8, [rbp+12E0h+var_DA0]; struct _WERSVC_MSG *
0x18003a40c  lea     rdx, [rbp+12E0h+var_820]; struct _WERSVC_MSG *
0x18003a413  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18003a418  mov     edi, eax
0x18003a41a  test    eax, eax
0x18003a41c  jns     short loc_18003A449
0x18003a41e  lea     rax, WPP_GLOBAL_Control
0x18003a425  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a42c  cmp     rcx, rax
0x18003a42f  jz      loc_18003A996
0x18003a435  test    [rcx+1Ch], r12b
0x18003a439  jz      loc_18003A996
0x18003a43f  mov     edx, 2Ah ; '*'
0x18003a444  jmp     loc_18003A1B2
0x18003a449  cmp     [rbp+12E0h+var_D78], 0E0000000h
0x18003a453  jz      short loc_18003A49E
0x18003a455  mov     r9d, [rbp+12E0h+var_D74]
0x18003a45c  mov     edi, r9d
0x18003a45f  bts     edi, 1Ch
0x18003a463  lea     rax, WPP_GLOBAL_Control
0x18003a46a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a471  cmp     rcx, rax
0x18003a474  jz      loc_18003A996
0x18003a47a  test    [rcx+1Ch], r12b
0x18003a47e  jz      loc_18003A996
0x18003a484  mov     edx, 2Bh ; '+'
0x18003a489  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x18003a490  mov     rcx, [rcx+10h]
0x18003a494  call    WPP_SF_d
0x18003a499  jmp     loc_18003A996
0x18003a49e  mov     ebx, r15d
0x18003a4a1  mov     rdx, [rbp+12E0h+var_D18]
0x18003a4a8  test    rdx, rdx
0x18003a4ab  jnz     short loc_18003A4B9
0x18003a4ad  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003a4b2  mov     rdx, [rbp+12E0h+var_D18]
0x18003a4b9  lea     rcx, [rsp+13E0h+var_1390]
0x18003a4be  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003a4c3  jmp     loc_18003A8C6
0x18003a4c8  mov     rdx, rsi; struct OO_PROC_REPORT_DATA *
0x18003a4cb  call    ?OutofProcDupHandles@CReportManager@@AEAAJPEAUOO_PROC_REPORT_DATA@@@Z; CReportManager::OutofProcDupHandles(OO_PROC_REPORT_DATA *)
0x18003a4d0  mov     edi, eax
0x18003a4d2  test    eax, eax
0x18003a4d4  jns     short loc_18003A501
0x18003a4d6  lea     rax, WPP_GLOBAL_Control
0x18003a4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4e4  cmp     rcx, rax
0x18003a4e7  jz      loc_18003A996
0x18003a4ed  test    [rcx+1Ch], r12b
0x18003a4f1  jz      loc_18003A996
0x18003a4f7  mov     edx, 2Ch ; ','
0x18003a4fc  jmp     loc_18003A1B2
0x18003a501  call    cs:__imp_GetCurrentProcessId
0x18003a507  mov     r8d, eax
0x18003a50a  lea     rdx, aU_0; "%u"
0x18003a511  lea     rcx, [rbp+12E0h+var_1D0]
0x18003a518  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003a51d  mov     dword ptr [rsp+13E0h+var_1388], eax
0x18003a521  mov     r8, rbx
0x18003a524  lea     rdi, aId_1; "%Id"
0x18003a52b  mov     rdx, rdi
0x18003a52e  lea     rcx, [rbp+12E0h+var_1B0]
0x18003a535  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003a53a  mov     [rsp+13E0h+var_136C], eax
0x18003a53e  mov     r8, [rsi+8]
0x18003a542  mov     rdx, rdi
0x18003a545  lea     rcx, [rbp+12E0h+var_190]
0x18003a54c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003a551  mov     [rsp+13E0h+var_1370], eax
0x18003a555  mov     r8, [rsi+10h]
0x18003a559  mov     rdx, rdi
0x18003a55c  lea     rcx, [rbp+12E0h+var_170]
0x18003a563  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003a568  mov     [rsp+13E0h+var_1374], eax
0x18003a56c  mov     r8, [rsi+2A0h]
0x18003a573  mov     rdx, rdi
0x18003a576  lea     rcx, [rbp+12E0h+var_150]
0x18003a57d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003a582  mov     [rsp+13E0h+var_1378], eax
0x18003a586  mov     r8, [rsi+2A8h]
0x18003a58d  mov     rdx, rdi
0x18003a590  lea     rcx, [rbp+12E0h+var_130]
0x18003a597  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003a59c  mov     r13d, eax
0x18003a59f  mov     r8, [rsi+20h]
0x18003a5a3  mov     rdx, rdi
  ... truncated ...
```
