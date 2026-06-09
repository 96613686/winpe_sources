# CReportManager::ReportProblemOutOfProcess(void)

- ea: `0x18003bf5c`
- end: `0x18003c942`
- name: `?ReportProblemOutOfProcess@CReportManager@@AEAAJXZ`
- size: `2534`
- prototype: `__int64 __fastcall(CReportManager *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180034288`

## callees

- `0x180004c64`
- `0x18000753c`
- `0x180007fd8`
- `0x180008004`
- `0x18000ad98`
- `0x18000e31c`
- `0x18001c368`
- `0x18001e288`
- `0x180020680`
- `0x180025848`
- `0x18003bf5c`
- `0x18003c948`
- `0x18003de9c`
- `0x18003e17c`
- `0x1800490c0`
- `0x180053300`
- `0x180053d3c`
- `0x180054e24`
- `0x180054ef4`
- `0x18005dd11`
- `0x18007774c`
- `0x18007f14c`
- `0x18007f284`
- `0x18007f38c`
- `0x180080b94`
- `0x18009a350`
- `0x1800a9b8c`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c430`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c430`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003c642`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003c793`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003c642`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18003c793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c8c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c8c0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003c15b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003c15b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003c198`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003c198`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003c658`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003c7a5`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003c658`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x18003c7a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CReportManager::ReportProblemOutOfProcess(CReportManager *this)
{
  CReportManager *v1; // r15
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
  struct OO_PROC_REPORT_DATA *v13; // r14
  CReportManager *v14; // rcx
  const wchar_t *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // esi
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  __int64 v21; // r8
  DWORD CurrentProcessId; // eax
  int v23; // r13d
  int v24; // r12d
  int v25; // r15d
  int v26; // r14d
  int v27; // esi
  int v28; // edi
  int v29; // eax
  unsigned int v30; // r8d
  UINT v31; // r15d
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rdx
  DWORD LastError; // eax
  struct OO_PROC_REPORT_DATA *v46; // [rsp+40h] [rbp-C0h] BYREF
  DWORD OldMode; // [rsp+48h] [rbp-B8h] BYREF
  void *v48; // [rsp+50h] [rbp-B0h] BYREF
  struct CReportFile *v49; // [rsp+58h] [rbp-A8h] BYREF
  int v50; // [rsp+60h] [rbp-A0h]
  int v51; // [rsp+64h] [rbp-9Ch]
  int v52; // [rsp+68h] [rbp-98h]
  int v53; // [rsp+6Ch] [rbp-94h]
  HANDLE hFileMappingObject; // [rsp+70h] [rbp-90h] BYREF
  CReportManager *v55; // [rsp+78h] [rbp-88h]
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
  v55 = this;
  v49 = 0;
  hFileMappingObject = 0;
  v46 = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  v48 = 0;
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
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
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, (unsigned int)v5);
      goto LABEL_106;
    }
    CurrentProcessId = GetCurrentProcessId();
    LODWORD(v49) = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                     v83,
                     L"%u",
                     CurrentProcessId);
    v53 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v84, L"%Id", v11);
    v52 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v85,
            L"%Id",
            *((_QWORD *)v13 + 1));
    v51 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v86,
            L"%Id",
            *((_QWORD *)v13 + 2));
    v50 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v87,
            L"%Id",
            *((_QWORD *)v13 + 84));
    v23 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v88,
            L"%Id",
            *((_QWORD *)v13 + 85));
    v24 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v89,
            L"%Id",
            *((_QWORD *)v13 + 4));
    v25 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v90,
            L"%Id",
            *((_QWORD *)v13 + 5));
    v26 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v91,
            L"%Id",
            *((_QWORD *)v13 + 164));
    v27 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v92,
            L"%Id",
            *((_QWORD *)v46 + 165));
    v28 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v93,
            L"%Id",
            *((_QWORD *)v46 + 244));
    v29 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v94,
            L"%Id",
            *((_QWORD *)v46 + 245));
    if ( (~v53 & ~v52 & ~v51 & ~v50 & ~v23 & ~v24 & ~v25 & ~v26 & ~v27 & ~v28 & ~v29 & ~(_DWORD)v49) >= 0 )
    {
      v20 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
      v5 = -2147467259;
      goto LABEL_104;
    }
    *(_QWORD *)v81 = L"-outproc";
    v82 = L"0";
    v30 = 0;
    v18 = 1;
    do
    {
      *(_QWORD *)&v81[2 * v30 + 4] = v83[4 * v30];
      ++v30;
    }
    while ( v30 < 0xC );
    v31 = SetErrorMode(1u);
    SetThreadErrorMode(1u, &OldMode);
    memset_0(v80, 0, 0x50u);
    Value = v11;
    v13 = v46;
    v32 = *((_QWORD *)v46 + 1);
    if ( v32 )
      v80[0] = *((_QWORD *)v46 + 1);
    v33 = (unsigned int)(v32 != 0) + 1;
    v34 = *((_QWORD *)v46 + 2);
    if ( v34 )
    {
      v80[v33 - 1] = v34;
      v33 = (unsigned int)(v33 + 1);
    }
    v35 = *((_QWORD *)v13 + 84);
    if ( v35 )
    {
      v80[v33 - 1] = v35;
      v33 = (unsigned int)(v33 + 1);
    }
    v36 = *((_QWORD *)v13 + 85);
    if ( v36 )
    {
      v80[v33 - 1] = v36;
      v33 = (unsigned int)(v33 + 1);
    }
    v37 = *((_QWORD *)v13 + 4);
    if ( v37 )
    {
      v80[v33 - 1] = v37;
      v33 = (unsigned int)(v33 + 1);
    }
    v38 = *((_QWORD *)v13 + 5);
    if ( v38 )
    {
      v80[v33 - 1] = v38;
      v33 = (unsigned int)(v33 + 1);
    }
    v39 = *((_QWORD *)v13 + 164);
    if ( v39 )
    {
      v80[v33 - 1] = v39;
      v33 = (unsigned int)(v33 + 1);
    }
    v40 = *((_QWORD *)v13 + 165);
    if ( v40 )
    {
      v80[v33 - 1] = v40;
      v33 = (unsigned int)(v33 + 1);
    }
    v41 = *((_QWORD *)v13 + 244);
    if ( v41 )
    {
      v80[v33 - 1] = v41;
      v33 = (unsigned int)(v33 + 1);
    }
    v42 = *((_QWORD *)v13 + 245);
    if ( v42 )
    {
      v80[v33 - 1] = v42;
      LODWORD(v33) = v33 + 1;
    }
    v5 = UtilLaunchWerManager((__int64)v81, 14, 2, 0, (__int64)&v48, 0, v33, &Value);
    SetErrorMode(v31);
    SetThreadErrorMode(OldMode, 0);
    if ( v5 < 0 )
    {
      v20 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
          (unsigned int)v5);
      goto LABEL_104;
    }
    if ( (unsigned __int64)v48 + 1 <= 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v20, v43, v21);
    v1 = v55;
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
    v18 = 0;
    v19 = v66;
    if ( !v66 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v16, 0, v17);
      v19 = v66;
    }
    tlx::unique_any<tlx::file_handle_traits>::reset(&v48, v19);
LABEL_80:
    if ( (*(_DWORD *)(*((_QWORD *)v1 + 1) + 6616LL) & 0x400) != 0 )
      goto LABEL_102;
    UtilMsgWaitForSingleObject((const wchar_t *)v20, v48, v21);
    v20 = *((unsigned int *)v13 + 654);
    if ( (int)v20 <= 7 )
    {
      if ( (_DWORD)v20 == 7 )
      {
        v5 = 1769477;
        goto LABEL_103;
      }
      v20 = (unsigned int)(v20 - 1);
      if ( !(_DWORD)v20 )
      {
        v5 = 1769474;
        goto LABEL_103;
      }
      v20 = (unsigned int)(v20 - 1);
      if ( !(_DWORD)v20 )
      {
        v5 = 1769473;
        goto LABEL_103;
      }
      v20 = (unsigned int)(v20 - 1);
      if ( !(_DWORD)v20 )
      {
        v5 = 1769472;
        goto LABEL_103;
      }
      v20 = (unsigned int)(v20 - 2);
      if ( !(_DWORD)v20 )
      {
        v5 = 1769475;
        goto LABEL_103;
      }
      if ( (_DWORD)v20 == 1 )
      {
        v5 = -2145681407;
        goto LABEL_103;
      }
      goto LABEL_98;
    }
    v20 = (unsigned int)(v20 - 8);
    if ( !(_DWORD)v20 )
    {
LABEL_102:
      v5 = 1769479;
    }
    else
    {
      v20 = (unsigned int)(v20 - 2);
      if ( (_DWORD)v20 )
      {
        v20 = (unsigned int)(v20 - 1);
        if ( (_DWORD)v20 )
        {
          if ( (_DWORD)v20 != 1 )
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
    if ( !v18 )
      goto LABEL_106;
LABEL_104:
    CReportManager::OutofProcCloseDupHandles((CReportManager *)v20, v46);
    goto LABEL_106;
  }
  v5 = v65 | 0x10000000;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v65);
LABEL_106:
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v56);
  `eh vector destructor iterator'(
    v83,
    0x20u,
    0xCu,
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v48);
  __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6AHPEBX_Z1_UnmapViewOfFile__YAH0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&v46);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFileMappingObject);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003bf5c  push    rbp
0x18003bf5e  push    rbx
0x18003bf5f  push    rsi
0x18003bf60  push    rdi
0x18003bf61  push    r12
0x18003bf63  push    r13
0x18003bf65  push    r14
0x18003bf67  push    r15
0x18003bf69  lea     rbp, [rsp-12A8h]
0x18003bf71  mov     eax, 13A8h
0x18003bf76  call    _alloca_probe
0x18003bf7b  sub     rsp, rax
0x18003bf7e  mov     rax, cs:__security_cookie
0x18003bf85  xor     rax, rsp
0x18003bf88  mov     [rbp+12E0h+var_50], rax
0x18003bf8f  mov     r15, rcx
0x18003bf92  mov     [rsp+13E0h+var_1368], rcx
0x18003bf97  xor     r12d, r12d
0x18003bf9a  mov     [rsp+13E0h+var_1388], r12
0x18003bf9f  mov     [rsp+13E0h+hFileMappingObject], r12
0x18003bfa4  mov     [rsp+13E0h+var_13A0], r12
0x18003bfa9  xorps   xmm0, xmm0
0x18003bfac  xor     eax, eax
0x18003bfae  movups  xmmword ptr [rbp+12E0h+FileMappingAttributes.nLength], xmm0
0x18003bfb2  mov     qword ptr [rbp+12E0h+FileMappingAttributes.bInheritHandle], rax
0x18003bfb6  mov     [rsp+13E0h+var_1390], r12
0x18003bfbb  mov     [rsp+13E0h+OldMode], r12d
0x18003bfc0  lea     rax, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003bfc7  mov     qword ptr [rsp+13E0h+dwMaximumSizeLow], rax; void (*)(void *)
0x18003bfcc  lea     r9, ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; void (*)(void *)
0x18003bfd3  lea     edx, [r12+20h]; unsigned __int64
0x18003bfd8  lea     r8d, [r12+0Ch]; unsigned __int64
0x18003bfdd  lea     rcx, [rbp+12E0h+var_1D0]; void *
0x18003bfe4  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003bfe9  nop
0x18003bfea  xor     edx, edx; Val
0x18003bfec  lea     r8d, [r12+70h]; Size
0x18003bff1  lea     rcx, [rbp+12E0h+var_240]; void *
0x18003bff8  call    memset_0
0x18003bffd  lea     rax, ??_7CMemoryByteStream@@6B@; const CMemoryByteStream::`vftable'
0x18003c004  mov     [rbp+12E0h+var_1360], rax
0x18003c008  xorps   xmm0, xmm0
0x18003c00b  movdqu  [rbp+12E0h+var_1358], xmm0
0x18003c010  mov     qword ptr [rbp+12E0h+var_1348], r12
0x18003c014  mov     [rbp+12E0h+var_1340], r12d
0x18003c018  mov     r9d, r12d
0x18003c01b  lea     esi, [r12+1]
0x18003c020  mov     rcx, [r15+8]; this
0x18003c024  mov     rax, [rcx+16C0h]
0x18003c02b  sub     rax, [rcx+16B8h]
0x18003c032  sar     rax, 3
0x18003c036  cmp     r9d, eax
0x18003c039  jnb     short loc_18003C094
0x18003c03b  lea     r8, [rsp+13E0h+var_1388]; struct CReportFile **
0x18003c040  mov     edx, r9d; unsigned int
0x18003c043  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x18003c048  test    eax, eax
0x18003c04a  js      short loc_18003C057
0x18003c04c  mov     rax, [rsp+13E0h+var_1388]
0x18003c051  cmp     [rax+38h], r12
0x18003c055  jnz     short loc_18003C05C
0x18003c057  add     r9d, esi
0x18003c05a  jmp     short loc_18003C020
0x18003c05c  lea     rax, WPP_GLOBAL_Control
0x18003c063  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c06a  cmp     rcx, rax
0x18003c06d  jz      short loc_18003C08A
0x18003c06f  test    byte ptr [rcx+1Ch], 2
0x18003c073  jz      short loc_18003C08A
0x18003c075  mov     edx, 25h ; '%'
0x18003c07a  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18003c081  mov     rcx, [rcx+10h]
0x18003c085  call    WPP_SF_
0x18003c08a  mov     edi, 80070032h
0x18003c08f  jmp     loc_18003C8D5
0x18003c094  lea     rcx, [rbp+12E0h+var_1360]; this
0x18003c098  call    ?OpenForReadWrite@CMemoryByteStream@@QEAAXXZ; CMemoryByteStream::OpenForReadWrite(void)
0x18003c09d  lea     rdx, [rbp+12E0h+var_1360]; struct CByteStream *
0x18003c0a1  mov     rcx, [r15+8]; this
0x18003c0a5  call    ?WriteReportToStream@CReport@@QEAAJPEAVCByteStream@@HK@Z; CReport::WriteReportToStream(CByteStream *,int,ulong)
0x18003c0aa  mov     edi, eax
0x18003c0ac  test    eax, eax
0x18003c0ae  jns     short loc_18003C0EE
0x18003c0b0  lea     rax, WPP_GLOBAL_Control
0x18003c0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0be  cmp     rcx, rax
0x18003c0c1  jz      loc_18003C8D5
0x18003c0c7  test    [rcx+1Ch], sil
0x18003c0cb  jz      loc_18003C8D5
0x18003c0d1  mov     edx, 26h ; '&'
0x18003c0d6  mov     r9d, edi
0x18003c0d9  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18003c0e0  mov     rcx, [rcx+10h]
0x18003c0e4  call    WPP_SF_d
0x18003c0e9  jmp     loc_18003C8D5
0x18003c0ee  xor     r9d, r9d; unsigned __int64 *
0x18003c0f1  xor     r8d, r8d; unsigned int
0x18003c0f4  xor     edx, edx; __int64
0x18003c0f6  lea     rcx, [rbp+12E0h+var_1360]; this
0x18003c0fa  call    ?SetFilePointer@CMemoryByteStream@@UEAAJ_JKPEA_K@Z; CMemoryByteStream::SetFilePointer(__int64,ulong,unsigned __int64 *)
0x18003c0ff  mov     edi, eax
0x18003c101  test    eax, eax
0x18003c103  jns     short loc_18003C12D
0x18003c105  lea     rax, WPP_GLOBAL_Control
0x18003c10c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c113  cmp     rcx, rax
0x18003c116  jz      loc_18003C8D5
0x18003c11c  test    [rcx+1Ch], sil
0x18003c120  jz      loc_18003C8D5
0x18003c126  mov     edx, 27h ; '''
0x18003c12b  jmp     short loc_18003C0D6
0x18003c12d  mov     [rbp+12E0h+FileMappingAttributes.nLength], 18h
0x18003c134  mov     [rbp+12E0h+FileMappingAttributes.lpSecurityDescriptor], r12
0x18003c138  mov     [rbp+12E0h+FileMappingAttributes.bInheritHandle], esi
0x18003c13b  mov     eax, [rbp+12E0h+var_1348]
0x18003c13e  add     eax, 0A40h
0x18003c143  mov     [rsp+13E0h+lpName], r12; lpName
0x18003c148  mov     [rsp+13E0h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18003c14c  xor     r9d, r9d; dwMaximumSizeHigh
0x18003c14f  lea     r8d, [r9+4]; flProtect
0x18003c153  lea     rdx, [rbp+12E0h+FileMappingAttributes]; lpFileMappingAttributes
0x18003c157  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18003c15b  call    cs:__imp_CreateFileMappingW
0x18003c162  nop     dword ptr [rax+rax+00h]
0x18003c167  mov     rdx, rax
0x18003c16a  lea     rcx, [rsp+13E0h+hFileMappingObject]
0x18003c16f  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003c174  mov     rbx, [rsp+13E0h+hFileMappingObject]
0x18003c179  lea     rax, [rbx+1]
0x18003c17d  cmp     rax, rsi
0x18003c180  jbe     loc_18003C8C0
0x18003c186  mov     qword ptr [rsp+13E0h+dwMaximumSizeLow], r12; dwNumberOfBytesToMap
0x18003c18b  xor     r9d, r9d; dwFileOffsetLow
0x18003c18e  xor     r8d, r8d; dwFileOffsetHigh
0x18003c191  lea     edx, [r9+6]; dwDesiredAccess
0x18003c195  mov     rcx, rbx; hFileMappingObject
0x18003c198  call    cs:__imp_MapViewOfFile
0x18003c19f  nop     dword ptr [rax+rax+00h]
0x18003c1a4  mov     r14, rax
0x18003c1a7  mov     [rsp+13E0h+var_13A0], rax
0x18003c1ac  test    rax, rax
0x18003c1af  jz      loc_18003C8C0
0x18003c1b5  mov     r9d, [rbp+12E0h+var_1348]; unsigned int
0x18003c1b9  lea     r8, [rbp+12E0h+var_1360]; struct IWerByteStream *
0x18003c1bd  mov     rdx, rax; struct OO_PROC_REPORT_DATA *
0x18003c1c0  mov     rcx, r15; this
0x18003c1c3  call    ?PopulateSharedMemSectionForOutofProcReporting@CReportManager@@AEAAJPEAUOO_PROC_REPORT_DATA@@PEAUIWerByteStream@@K@Z; CReportManager::PopulateSharedMemSectionForOutofProcReporting(OO_PROC_REPORT_DATA *,IWerByteStream *,ulong)
0x18003c1c8  mov     edi, eax
0x18003c1ca  test    eax, eax
0x18003c1cc  jns     short loc_18003C1F9
0x18003c1ce  lea     rax, WPP_GLOBAL_Control
0x18003c1d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c1dc  cmp     rcx, rax
0x18003c1df  jz      loc_18003C8D5
0x18003c1e5  test    [rcx+1Ch], sil
0x18003c1e9  jz      loc_18003C8D5
0x18003c1ef  mov     edx, 28h ; '('
0x18003c1f4  jmp     loc_18003C0D6
0x18003c1f9  mov     rcx, [r15+8]; this
0x18003c1fd  call    ?ReleaseReportLock@CReport@@QEAAJXZ; CReport::ReleaseReportLock(void)
0x18003c202  mov     edi, eax
0x18003c204  test    eax, eax
0x18003c206  jns     short loc_18003C233
0x18003c208  lea     rax, WPP_GLOBAL_Control
0x18003c20f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c216  cmp     rcx, rax
0x18003c219  jz      loc_18003C8D5
0x18003c21f  test    [rcx+1Ch], sil
0x18003c223  jz      loc_18003C8D5
0x18003c229  mov     edx, 29h ; ')'
0x18003c22e  jmp     loc_18003C0D6
0x18003c233  mov     rcx, [r15+60h]
0x18003c237  add     rcx, 8F0h; this
0x18003c23e  cmp     [rcx], r12b
0x18003c241  jz      loc_18003C3F7
0x18003c247  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18003c24c  test    eax, eax
0x18003c24e  jz      loc_18003C3F7
0x18003c254  mov     [rbp+12E0h+var_DA0], r12w
0x18003c25c  xor     edx, edx; Val
0x18003c25e  mov     r8d, 576h; Size
0x18003c264  lea     rcx, [rbp+12E0h+var_D9E]; void *
0x18003c26b  call    memset_0
0x18003c270  mov     edi, 578h
0x18003c275  mov     r8d, edi; Size
0x18003c278  xor     edx, edx; Val
0x18003c27a  lea     rcx, [rbp+12E0h+Src]; void *
0x18003c27e  call    memset_0
0x18003c283  lea     rcx, [rbp+12E0h+var_820]; void *
0x18003c28a  lea     rdx, [rbp+12E0h+Src]; Src
0x18003c28e  mov     r8d, edi; Size
0x18003c291  call    memcpy_0
0x18003c296  mov     [rbp+12E0h+var_820], 5780550h
0x18003c2a0  mov     [rbp+12E0h+var_7F8], 0E0000002h
0x18003c2aa  mov     [rbp+12E0h+var_7F0], rbx
0x18003c2b1  mov     rax, [r14+8]
0x18003c2b5  mov     [rbp+12E0h+var_7E8], rax
0x18003c2bc  mov     rax, [r14+10h]
0x18003c2c0  mov     [rbp+12E0h+var_7E0], rax
0x18003c2c7  mov     rax, [r14+2A0h]
0x18003c2ce  mov     [rbp+12E0h+var_7D8], rax
0x18003c2d5  mov     rax, [r14+2A8h]
0x18003c2dc  mov     [rbp+12E0h+var_7D0], rax
0x18003c2e3  mov     rax, [r14+20h]
0x18003c2e7  mov     [rbp+12E0h+var_7C8], rax
0x18003c2ee  mov     rax, [r14+28h]
0x18003c2f2  mov     [rbp+12E0h+var_7C0], rax
0x18003c2f9  mov     rax, [r14+520h]
0x18003c300  mov     [rbp+12E0h+var_7B8], rax
0x18003c307  mov     rax, [r14+528h]
0x18003c30e  mov     [rbp+12E0h+var_7B0], rax
0x18003c315  mov     rax, [r14+7A0h]
0x18003c31c  mov     [rbp+12E0h+var_7A8], rax
0x18003c323  mov     rax, [r14+7A8h]
0x18003c32a  mov     [rbp+12E0h+var_7A0], rax
0x18003c331  xor     r9d, r9d; unsigned int
0x18003c334  lea     r8, [rbp+12E0h+var_DA0]; struct _WERSVC_MSG *
0x18003c33b  lea     rdx, [rbp+12E0h+var_820]; struct _WERSVC_MSG *
0x18003c342  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18003c347  mov     edi, eax
0x18003c349  test    eax, eax
0x18003c34b  jns     short loc_18003C378
0x18003c34d  lea     rax, WPP_GLOBAL_Control
0x18003c354  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c35b  cmp     rcx, rax
0x18003c35e  jz      loc_18003C8D5
0x18003c364  test    [rcx+1Ch], sil
0x18003c368  jz      loc_18003C8D5
0x18003c36e  mov     edx, 2Ah ; '*'
0x18003c373  jmp     loc_18003C0D6
0x18003c378  cmp     [rbp+12E0h+var_D78], 0E0000000h
0x18003c382  jz      short loc_18003C3CD
0x18003c384  mov     r9d, [rbp+12E0h+var_D74]
0x18003c38b  mov     edi, r9d
0x18003c38e  bts     edi, 1Ch
0x18003c392  lea     rax, WPP_GLOBAL_Control
0x18003c399  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c3a0  cmp     rcx, rax
0x18003c3a3  jz      loc_18003C8D5
0x18003c3a9  test    [rcx+1Ch], sil
0x18003c3ad  jz      loc_18003C8D5
0x18003c3b3  mov     edx, 2Bh ; '+'
0x18003c3b8  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18003c3bf  mov     rcx, [rcx+10h]
0x18003c3c3  call    WPP_SF_d
0x18003c3c8  jmp     loc_18003C8D5
0x18003c3cd  mov     esi, r12d
0x18003c3d0  mov     rdx, [rbp+12E0h+var_D18]
0x18003c3d7  test    rdx, rdx
0x18003c3da  jnz     short loc_18003C3E8
0x18003c3dc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003c3e1  mov     rdx, [rbp+12E0h+var_D18]
0x18003c3e8  lea     rcx, [rsp+13E0h+var_1390]
0x18003c3ed  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003c3f2  jmp     loc_18003C80A
0x18003c3f7  mov     rdx, r14; struct OO_PROC_REPORT_DATA *
0x18003c3fa  call    ?OutofProcDupHandles@CReportManager@@AEAAJPEAUOO_PROC_REPORT_DATA@@@Z; CReportManager::OutofProcDupHandles(OO_PROC_REPORT_DATA *)
0x18003c3ff  mov     edi, eax
0x18003c401  test    eax, eax
0x18003c403  jns     short loc_18003C430
0x18003c405  lea     rax, WPP_GLOBAL_Control
0x18003c40c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c413  cmp     rcx, rax
0x18003c416  jz      loc_18003C8D5
0x18003c41c  test    [rcx+1Ch], sil
0x18003c420  jz      loc_18003C8D5
0x18003c426  mov     edx, 2Ch ; ','
0x18003c42b  jmp     loc_18003C0D6
0x18003c430  call    cs:__imp_GetCurrentProcessId
0x18003c437  nop     dword ptr [rax+rax+00h]
0x18003c43c  mov     r8d, eax
0x18003c43f  lea     rdx, aU_0; "%u"
0x18003c446  lea     rcx, [rbp+12E0h+var_1D0]
0x18003c44d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003c452  mov     dword ptr [rsp+13E0h+var_1388], eax
0x18003c456  mov     r8, rbx
0x18003c459  lea     rsi, aId_1; "%Id"
0x18003c460  mov     rdx, rsi
0x18003c463  lea     rcx, [rbp+12E0h+var_1B0]
0x18003c46a  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003c46f  mov     [rsp+13E0h+var_1374], eax
0x18003c473  mov     r8, [r14+8]
0x18003c477  mov     rdx, rsi
0x18003c47a  lea     rcx, [rbp+12E0h+var_190]
0x18003c481  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003c486  mov     [rsp+13E0h+var_1378], eax
0x18003c48a  mov     r8, [r14+10h]
0x18003c48e  mov     rdx, rsi
0x18003c491  lea     rcx, [rbp+12E0h+var_170]
0x18003c498  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003c49d  mov     [rsp+13E0h+var_137C], eax
0x18003c4a1  mov     r8, [r14+2A0h]
0x18003c4a8  mov     rdx, rsi
0x18003c4ab  lea     rcx, [rbp+12E0h+var_150]
0x18003c4b2  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003c4b7  mov     [rsp+13E0h+var_1380], eax
0x18003c4bb  mov     r8, [r14+2A8h]
0x18003c4c2  mov     rdx, rsi
0x18003c4c5  lea     rcx, [rbp+12E0h+var_130]
0x18003c4cc  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
  ... truncated ...
```
