# CReportManager::AddSecondLevelData(CDataRequest const *)

- ea: `0x1800429c0`
- end: `0x18004334b`
- name: `?AddSecondLevelData@CReportManager@@AEAAJPEBVCDataRequest@@@Z`
- size: `2443`
- prototype: `__int64 __fastcall(CReportManager *__hidden this, const struct CDataRequest *)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800147b8`
- `0x18007969c`

## callees

- `0x180004bb4`
- `0x18000bc10`
- `0x18000c390`
- `0x18000dad0`
- `0x18001b280`
- `0x18001fe24`
- `0x180026ac8`
- `0x1800278bc`
- `0x1800293ac`
- `0x18002b748`
- `0x180035ce0`
- `0x1800429c0`
- `0x180043354`
- `0x1800433d0`
- `0x18004a12c`
- `0x18004ee3c`
- `0x18004f344`
- `0x180072268`
- `0x18007a980`
- `0x18007b07c`
- `0x18007b104`
- `0x18007bee8`
- `0x18007c06c`
- `0x18007c528`
- `0x18007c81c`
- `0x18007cefc`
- `0x18008a9d0`
- `0x18008aa24`
- `0x18008aa74`
- `0x18008aac4`
- `0x18008bf00`
- `0x18008caa4`
- `0x18008cbfc`
- `0x18008eb7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042ae7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043127`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043145`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180042ae7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043127`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043145`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180042b82`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180042b82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800429f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042a08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800432fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800429f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042a08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800432fe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180042a14`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004330a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180042a14`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004330a`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800429ff`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800429ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042b2e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042c1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042b2e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042c1c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042d35`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042d35`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180042d03`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180042d03`

## pseudocode

```c
__int64 __fastcall CReportManager::AddSecondLevelData(CReportManager *this, const struct CDataRequest *a2)
{
  const struct CDataRequest *v2; // r14
  __int64 v4; // r13
  __int64 v5; // rbx
  unsigned int v6; // edi
  HANDLE CurrentThread; // rax
  HANDLE v8; // rax
  int v9; // esi
  CDataRequest *v10; // rbx
  unsigned __int64 v11; // r13
  __int64 v12; // rax
  wchar_t *v13; // r14
  int DataRequestType; // ebx
  wchar_t *v15; // rsi
  __int64 v16; // rbx
  unsigned int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // edx
  CDataRequest *v20; // rdi
  wchar_t *v21; // r13
  const wchar_t *v22; // rbx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  unsigned int Files; // eax
  unsigned int v29; // ebx
  wchar_t *v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // edi
  int WMIDataInternal; // ebx
  wchar_t *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rdx
  unsigned int v37; // edi
  int v38; // edx
  int v39; // edx
  unsigned int v40; // eax
  unsigned int RegistryData; // eax
  unsigned int FilesVersion; // eax
  int v43; // ecx
  int v44; // ecx
  int v45; // ecx
  int v46; // ecx
  int v47; // ecx
  unsigned int v48; // eax
  int v49; // edx
  unsigned int v50; // eax
  int v51; // edx
  __int64 v52; // rax
  struct HPSS__ *v53; // r8
  void *v54; // rdx
  int v55; // eax
  unsigned int v56; // edi
  unsigned int DWORD; // eax
  __int64 v58; // rcx
  int v59; // edx
  HANDLE v60; // rax
  bool v62; // [rsp+28h] [rbp-81h]
  wchar_t *v63[4]; // [rsp+30h] [rbp-79h] BYREF
  wchar_t *v64; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int64 v65; // [rsp+58h] [rbp-51h]
  CReport *v66[3]; // [rsp+60h] [rbp-49h] BYREF
  char v67[40]; // [rsp+78h] [rbp-31h] BYREF
  wchar_t *v68[12]; // [rsp+A0h] [rbp-9h] BYREF
  wchar_t *v69; // [rsp+110h] [rbp+67h] BYREF
  CDataRequest *v70; // [rsp+118h] [rbp+6Fh]
  wchar_t *v71; // [rsp+120h] [rbp+77h] BYREF
  int nPriority; // [rsp+128h] [rbp+7Fh]

  v70 = a2;
  v2 = a2;
  v4 = *((_QWORD *)a2 + 1);
  v5 = *(_QWORD *)a2;
  CDataCollection::CDataCollection((CDataCollection *)v66);
  v6 = 0;
  CurrentThread = GetCurrentThread();
  nPriority = GetThreadPriority(CurrentThread);
  v8 = GetCurrentThread();
  SetThreadPriority(v8, -1);
  v9 = CDataCollection::Initialize(
         (CDataCollection *)v66,
         *((struct CReport **)this + 1),
         *(struct CReportHandleInstance **)this,
         *((void **)this + 33));
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
    v10 = v70;
    goto LABEL_147;
  }
  v11 = 0xEEEEEEEEEEEEEEEFuLL * ((v4 - v5) >> 3);
  v65 = v11;
  if ( (_DWORD)v11 )
  {
    CReportManager::ExternalCallbackDataRequestBegin(this);
    *(_DWORD *)(*((_QWORD *)this + 1) + 6624LL) = 3;
    v69 = 0;
    if ( *((_DWORD *)this + 50) && !*(_DWORD *)(*((_QWORD *)this + 1) + 46680LL) )
    {
      if ( (int)CDataRequest::GetRequestByType(v2, L"DesktopHeap", (const wchar_t **)&v69) >= 0
        && !(unsigned int)_o__wcsicmp(v69, L"1")
        || (v12 = *((_QWORD *)this + 1), *(_DWORD *)(v12 + 5872) == 3)
        || (*(_DWORD *)(v12 + 6616) & 0x80000) != 0 )
      {
        CReportManager::AddDesktopHeapDataForReport(this);
      }
    }
    LODWORD(v69) = 1;
    while ( v6 < (unsigned int)v11 )
    {
      if ( !WaitForSingleObject(*((HANDLE *)this + 33), 0) )
      {
        v9 = -2145681407;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
        v10 = v70;
        v6 = 1;
        goto LABEL_147;
      }
      v64 = 0;
      v71 = 0;
      if ( (int)CDataRequest::GetRequestByIndex(v2, v6, (const wchar_t **)&v71, (const wchar_t **)&v64) >= 0 )
      {
        v13 = v71;
        DataRequestType = RequestToken::GetDataRequestType(v71);
        v15 = v64;
        CReportManager::ProcessConditionalFileAdds(this, v13, v64);
        if ( DataRequestType == 19 )
        {
          v16 = *((_QWORD *)this + 1);
          v17 = _o__wtoi(v15);
          if ( v17 <= 3 )
            *(_DWORD *)(v16 + 5956) = v17;
        }
        CReportManager::ExternalCallbackDataRequest(this, v13, v15, (unsigned int *)this + 54);
        v2 = v70;
      }
      ++v6;
    }
    v18 = 0;
    LODWORD(v71) = 0;
    v9 = -2145681407;
    v10 = v70;
    while ( 1 )
    {
      if ( v18 >= (unsigned int)v11 )
      {
        v6 = (unsigned int)v69;
        goto LABEL_152;
      }
      if ( !WaitForSingleObject(*((HANDLE *)this + 33), 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
        v6 = (unsigned int)v69;
        goto LABEL_147;
      }
      v64 = 0;
      v19 = v18;
      v20 = v70;
      if ( (int)CDataRequest::GetRequest(v70, v19, (struct RequestToken **)&v64) >= 0 )
        break;
      v10 = v70;
LABEL_142:
      v18 = (_DWORD)v71 + 1;
      LODWORD(v71) = (_DWORD)v71 + 1;
    }
    v21 = v64;
    v22 = (const wchar_t *)*((_QWORD *)v64 + 4);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v63);
    v23 = *((_DWORD *)v21 + 28);
    if ( v23 > 6 )
    {
      v43 = v23 - 7;
      if ( !v43 )
      {
        v59 = *v22 - 49;
        if ( *v22 == 49 )
          v59 = v22[1];
        if ( v59 )
          goto LABEL_139;
        v29 = CReportManager::ProcessHeapDumpRequest(this, v20, v63);
        if ( (int)(v29 + 0x80000000) < 0 )
          goto LABEL_137;
        if ( v29 == -2145681407 )
          goto LABEL_137;
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v63,
          L"ProcessHeapDumpRequest failed: 0x%x\r\n",
          v29);
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_137;
        v31 = 216;
        goto LABEL_136;
      }
      v44 = v43 - 4;
      if ( !v44 )
      {
        if ( *(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) != 4 )
          goto LABEL_139;
        if ( (unsigned int)_o__wcsicmp(v22, L"AskFull") )
        {
          v56 = 0;
          if ( !(unsigned int)_o__wcsicmp(v22, L"AskKernel") )
            v56 = 2;
        }
        else
        {
          v56 = 1;
        }
        DWORD = UtilRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Control\\CrashControl",
                  L"CrashDumpEnabled",
                  0xFFFFFFFF,
                  0,
                  v62);
        if ( v56 - 1 > 1 )
          goto LABEL_139;
        v58 = DWORD - 1;
        if ( (v58 & 0xFFFFFFFB) == 0 )
        {
          if ( v56 == 2 )
            goto LABEL_139;
          if ( DWORD == 1 )
            goto LABEL_124;
        }
        if ( DWORD == 5 )
        {
LABEL_124:
          if ( v56 == 1 )
            goto LABEL_139;
        }
        if ( ((DWORD - 2) & 0xFFFFFFFB) != 0 || v56 != 2 )
          CReportManager::EnableFullKernelDump(v58, v56);
        goto LABEL_139;
      }
      v45 = v44 - 1;
      if ( v45 )
      {
        v46 = v45 - 4;
        if ( v46 )
        {
          v47 = v46 - 4;
          if ( v47 )
          {
            if ( v47 == 1 && *(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) == 4 )
              EnableKernelIptTracing(v22);
            goto LABEL_139;
          }
          v48 = CDataCollection::AddReportMetadata((CDataCollection *)v66);
          v29 = v48;
          if ( (int)(v48 + 0x80000000) < 0 )
            goto LABEL_137;
          if ( v48 == -2145681407 )
            goto LABEL_137;
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v63,
            L"AddMetadata failed: 0x%x\r\n",
            v48);
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_137;
          v31 = 225;
        }
        else
        {
          v49 = *v22 - 49;
          if ( *v22 == 49 )
            v49 = v22[1];
          if ( v49 )
            goto LABEL_139;
          v50 = CReportManager::ProcessMiniDumpRequest(this, v20, v63);
          v29 = v50;
          if ( (int)(v50 + 0x80000000) < 0 )
            goto LABEL_137;
          if ( v50 == -2145681407 )
            goto LABEL_137;
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v63,
            L"ProcessMiniDumpRequest failed: 0x%x\r\n",
            v50);
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_137;
          v31 = 217;
        }
        goto LABEL_136;
      }
      v32 = 0;
      v51 = *v22 - 49;
      if ( *v22 == 49 )
        v51 = v22[1];
      if ( !v51 )
      {
        v52 = *((_QWORD *)this + 1);
        v53 = *(struct HPSS__ **)(v52 + 9112);
        v54 = *(void **)(v52 + 6640);
        if ( v54 || v53 )
        {
          v55 = CDataCollection::AddLoadedModuleInformation((CDataCollection *)v66, v54, v53);
          v32 = v55;
          if ( v55 < 0 )
          {
            tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              v63,
              L"GetLoadedModuleInformation failed: 0x%x\r\n",
              (unsigned int)v55);
            v34 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v35 = 224;
              goto LABEL_53;
            }
          }
        }
      }
    }
    else
    {
      if ( v23 == 6 )
      {
        FilesVersion = CDataCollection::GetFilesVersion(v66, v22);
        v29 = FilesVersion;
        if ( (int)(FilesVersion + 0x80000000) < 0 )
          goto LABEL_137;
        if ( FilesVersion == -2145681407 )
          goto LABEL_137;
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v63,
          L"GetFileVersion failed: 0x%x\r\n",
          FilesVersion);
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_137;
        v31 = 222;
        goto LABEL_136;
      }
      if ( !v23 )
      {
        RegistryData = CDataCollection::GetRegistryData((CDataCollection *)v66, v22, 0);
        v29 = RegistryData;
        if ( (int)(RegistryData + 0x80000000) < 0 )
          goto LABEL_137;
        if ( RegistryData == -2145681407 )
          goto LABEL_137;
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v63,
          L"GetRegKey failed: 0x%x\r\n",
          RegistryData);
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_137;
        v31 = 219;
        goto LABEL_136;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        v40 = CDataCollection::GetRegistryData((CDataCollection *)v66, v22, 1u);
        v29 = v40;
        if ( (int)(v40 + 0x80000000) < 0 )
          goto LABEL_137;
        if ( v40 == -2145681407 )
          goto LABEL_137;
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v63,
          L"GetRegTree failed: 0x%x\r\n",
          v40);
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_137;
        v31 = 220;
        goto LABEL_136;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v39 = *v22 - 49;
        if ( *v22 == 49 )
          v39 = v22[1];
        if ( !v39 )
          CReport::MarkFilesForUploadByType(*((CReport **)this + 1), WerFileTypeUserDocument);
        v36 = 0;
        goto LABEL_138;
      }
      v26 = v25 - 1;
      if ( !v26 )
      {
        v37 = 0;
        v38 = *v22 - 49;
        if ( *v22 == 49 )
          v38 = v22[1];
        v10 = v70;
        if ( !v38 )
        {
          v37 = CReportManager::ProcessDefaultDataCollection(this, v70);
          if ( (int)(v37 + 0x80000000) >= 0 && v37 != -2145681407 )
          {
            tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              v63,
              L"DefaultDataCollection failed: 0x%x\r\n",
              v37);
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v37);
          }
        }
        RequestToken::SetResult(v21, v37, v63);
        goto LABEL_140;
      }
      v27 = v26 - 1;
      if ( v27 )
      {
        if ( v27 == 1 )
        {
          Files = CDataCollection::GetFiles((CDataCollection *)v66, v22);
          v29 = Files;
          if ( (int)(Files + 0x80000000) < 0 )
            goto LABEL_137;
          if ( Files == -2145681407 )
            goto LABEL_137;
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v63,
            L"GetFile failed: 0x%x\r\n",
            Files);
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_137;
          v31 = 221;
LABEL_136:
          WPP_SF_d(*((_QWORD *)v30 + 2), v31, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v29);
LABEL_137:
          v36 = v29;
          goto LABEL_138;
        }
LABEL_139:
        v10 = v70;
LABEL_140:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v63);
        LODWORD(v11) = v65;
        goto LABEL_142;
      }
      v32 = CoInitializeEx(0, 0);
      LODWORD(v64) = v32;
      if ( (int)(v32 + 0x80000000) >= 0 && v32 != -2147417850 )
        goto LABEL_51;
      WMIDataInternal = CDataCollection::GetWMIDataInternal((CDataCollection *)v66, v22);
      if ( (v32 & 0x80000000) == 0 )
        CoUninitialize();
      v32 = WMIDataInternal;
      if ( WMIDataInternal < 0 )
      {
LABEL_51:
        if ( v32 != -2145681407 )
        {
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v63,
            L"GetWMIData failed: 0x%x\r\n",
            v32);
          v34 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v35 = 218;
LABEL_53:
            WPP_SF_d(*((_QWORD *)v34 + 2), v35, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v32);
          }
        }
      }
    }
    v36 = v32;
LABEL_138:
    RequestToken::SetResult(v21, v36, v63);
    goto LABEL_139;
  }
  v10 = v70;
LABEL_152:
  v9 = 0;
LABEL_147:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v63);
  CDataRequest::PrintRequests(v10);
  CDataCollection::AddDataCollectionFailure((CDataCollection *)v66, v63[0]);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v63);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v68);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
    v68,
    L"External Collection Data\n\n");
  if ( v6 )
    CReportManager::ExternalCallbackDataRequestEnd(this, v68);
  CDataCollection::AddDataCollectionFailure((CDataCollection *)v66, v68[0]);
  v60 = GetCurrentThread();
  SetThreadPriority(v60, nPriority);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v68);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v67);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800429c0  mov     [rsp-8+arg_8], rdx
0x1800429c5  push    rbp
0x1800429c6  push    rbx
0x1800429c7  push    rsi
0x1800429c8  push    rdi
0x1800429c9  push    r12
0x1800429cb  push    r13
0x1800429cd  push    r14
0x1800429cf  push    r15
0x1800429d1  lea     rbp, [rsp-1Fh]
0x1800429d6  sub     rsp, 0C8h
0x1800429dd  mov     r14, rdx
0x1800429e0  mov     r15, rcx
0x1800429e3  mov     r13, [rdx+8]
0x1800429e7  mov     rbx, [rdx]
0x1800429ea  lea     rcx, [rbp+57h+var_A0]; this
0x1800429ee  call    ??0CDataCollection@@QEAA@XZ; CDataCollection::CDataCollection(void)
0x1800429f3  nop
0x1800429f4  xor     edi, edi
0x1800429f6  call    cs:__imp_GetCurrentThread
0x1800429fc  mov     rcx, rax; hThread
0x1800429ff  call    cs:__imp_GetThreadPriority
0x180042a05  mov     [rbp+57h+nPriority], eax
0x180042a08  call    cs:__imp_GetCurrentThread
0x180042a0e  mov     rcx, rax; hThread
0x180042a11  or      edx, 0FFFFFFFFh; nPriority
0x180042a14  call    cs:__imp_SetThreadPriority
0x180042a1a  mov     r9, [r15+108h]; void *
0x180042a21  mov     r8, [r15]; struct CReportHandleInstance *
0x180042a24  mov     rdx, [r15+8]; struct CReport *
0x180042a28  lea     rcx, [rbp+57h+var_A0]; this
0x180042a2c  call    ?Initialize@CDataCollection@@QEAAJPEAVCReport@@PEAVCReportHandleInstance@@PEAX@Z; CDataCollection::Initialize(CReport *,CReportHandleInstance *,void *)
0x180042a31  mov     esi, eax
0x180042a33  test    eax, eax
0x180042a35  jns     short loc_180042A72
0x180042a37  lea     r14, WPP_GLOBAL_Control
0x180042a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a45  cmp     rcx, r14
0x180042a48  jz      short loc_180042A69
0x180042a4a  lea     r12d, [rdi+1]
0x180042a4e  test    [rcx+1Ch], r12b
0x180042a52  jz      short loc_180042A69
0x180042a54  mov     edx, 0D5h
0x180042a59  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180042a60  mov     rcx, [rcx+10h]
0x180042a64  call    WPP_SF_
0x180042a69  mov     rbx, [rbp+57h+arg_8]
0x180042a6d  jmp     loc_18004329A
0x180042a72  sub     r13, rbx
0x180042a75  sar     r13, 3
0x180042a79  mov     rax, 0EEEEEEEEEEEEEEEFh
0x180042a83  imul    r13, rax
0x180042a87  mov     [rbp+57h+var_A8], r13
0x180042a8b  xor     ebx, ebx
0x180042a8d  test    r13d, r13d
0x180042a90  jz      loc_18004333A
0x180042a96  mov     rcx, r15; this
0x180042a99  call    ?ExternalCallbackDataRequestBegin@CReportManager@@AEAAHXZ; CReportManager::ExternalCallbackDataRequestBegin(void)
0x180042a9e  mov     rax, [r15+8]
0x180042aa2  mov     dword ptr [rax+19E0h], 3
0x180042aac  mov     [rbp+57h+arg_0], rbx
0x180042ab0  cmp     [r15+0C8h], ebx
0x180042ab7  jz      short loc_180042B12
0x180042ab9  mov     rax, [r15+8]
0x180042abd  cmp     [rax+0B658h], ebx
0x180042ac3  jnz     short loc_180042B12
0x180042ac5  lea     r8, [rbp+57h+arg_0]; wchar_t **
0x180042ac9  lea     rdx, aDesktopheap; "DesktopHeap"
0x180042ad0  mov     rcx, r14; this
0x180042ad3  call    ?GetRequestByType@CDataRequest@@QEBAJPEB_WPEAPEB_W@Z; CDataRequest::GetRequestByType(wchar_t const *,wchar_t const * *)
0x180042ad8  test    eax, eax
0x180042ada  js      short loc_180042AF1
0x180042adc  lea     rdx, a1; "1"
0x180042ae3  mov     rcx, [rbp+57h+arg_0]
0x180042ae7  call    cs:__imp__o__wcsicmp
0x180042aed  test    eax, eax
0x180042aef  jz      short loc_180042B0A
0x180042af1  mov     rax, [r15+8]
0x180042af5  cmp     dword ptr [rax+16F0h], 3
0x180042afc  jz      short loc_180042B0A
0x180042afe  test    dword ptr [rax+19D8h], 80000h
0x180042b08  jz      short loc_180042B12
0x180042b0a  mov     rcx, r15; this
0x180042b0d  call    ?AddDesktopHeapDataForReport@CReportManager@@AEAAJXZ; CReportManager::AddDesktopHeapDataForReport(void)
0x180042b12  mov     r12d, 1
0x180042b18  mov     dword ptr [rbp+57h+arg_0], r12d
0x180042b1c  cmp     edi, r13d
0x180042b1f  jnb     loc_180042BF5
0x180042b25  xor     edx, edx; dwMilliseconds
0x180042b27  mov     rcx, [r15+108h]; hHandle
0x180042b2e  call    cs:__imp_WaitForSingleObject
0x180042b34  test    eax, eax
0x180042b36  jz      short loc_180042BB6
0x180042b38  mov     [rbp+57h+var_B0], rbx
0x180042b3c  mov     [rbp+57h+arg_10], rbx
0x180042b40  lea     r9, [rbp+57h+var_B0]; wchar_t **
0x180042b44  lea     r8, [rbp+57h+arg_10]; wchar_t **
0x180042b48  mov     edx, edi; unsigned int
0x180042b4a  mov     rcx, r14; this
0x180042b4d  call    ?GetRequestByIndex@CDataRequest@@QEBAJKPEAPEB_W0@Z; CDataRequest::GetRequestByIndex(ulong,wchar_t const * *,wchar_t const * *)
0x180042b52  test    eax, eax
0x180042b54  js      short loc_180042BAE
0x180042b56  mov     r14, [rbp+57h+arg_10]
0x180042b5a  mov     rcx, r14
0x180042b5d  call    ?GetDataRequestType@RequestToken@@SA?AW4DATA_REQUEST_TYPE@1@PEB_W@Z; RequestToken::GetDataRequestType(wchar_t const *)
0x180042b62  mov     ebx, eax
0x180042b64  mov     rsi, [rbp+57h+var_B0]
0x180042b68  mov     r8, rsi
0x180042b6b  mov     rdx, r14
0x180042b6e  mov     rcx, r15
0x180042b71  call    ?ProcessConditionalFileAdds@CReportManager@@AEAAHPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ProcessConditionalFileAdds(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180042b76  cmp     ebx, 13h
0x180042b79  jnz     short loc_180042B93
0x180042b7b  mov     rbx, [r15+8]
0x180042b7f  mov     rcx, rsi
0x180042b82  call    cs:__imp__o__wtoi
0x180042b88  cmp     eax, 3
0x180042b8b  ja      short loc_180042B93
0x180042b8d  mov     [rbx+1744h], eax
0x180042b93  lea     r9, [r15+0D8h]; unsigned int *
0x180042b9a  mov     r8, rsi; wchar_t *
0x180042b9d  mov     rdx, r14; wchar_t *
0x180042ba0  mov     rcx, r15; this
0x180042ba3  call    ?ExternalCallbackDataRequest@CReportManager@@AEAAHPEB_W0PEAK@Z; CReportManager::ExternalCallbackDataRequest(wchar_t const *,wchar_t const *,ulong *)
0x180042ba8  mov     r14, [rbp+57h+arg_8]
0x180042bac  xor     ebx, ebx
0x180042bae  add     edi, r12d
0x180042bb1  jmp     loc_180042B1C
0x180042bb6  mov     esi, 801B8001h
0x180042bbb  lea     r14, WPP_GLOBAL_Control
0x180042bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180042bc9  cmp     rcx, r14
0x180042bcc  jz      short loc_180042BE9
0x180042bce  test    byte ptr [rcx+1Ch], 4
0x180042bd2  jz      short loc_180042BE9
0x180042bd4  mov     edx, 0D6h
0x180042bd9  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180042be0  mov     rcx, [rcx+10h]
0x180042be4  call    WPP_SF_
0x180042be9  mov     rbx, [rbp+57h+arg_8]
0x180042bed  mov     edi, r12d
0x180042bf0  jmp     loc_18004329A
0x180042bf5  mov     edi, ebx
0x180042bf7  mov     dword ptr [rbp+57h+arg_10], ebx
0x180042bfa  lea     r14, WPP_GLOBAL_Control
0x180042c01  mov     esi, 801B8001h
0x180042c06  mov     rbx, [rbp+57h+arg_8]
0x180042c0a  cmp     edi, r13d
0x180042c0d  jnb     loc_180043340
0x180042c13  xor     edx, edx; dwMilliseconds
0x180042c15  mov     rcx, [r15+108h]; hHandle
0x180042c1c  call    cs:__imp_WaitForSingleObject
0x180042c22  test    eax, eax
0x180042c24  jz      loc_180043270
0x180042c2a  mov     [rbp+57h+var_B0], 0
0x180042c32  lea     r8, [rbp+57h+var_B0]; struct RequestToken **
0x180042c36  mov     edx, edi; unsigned int
0x180042c38  mov     rdi, [rbp+57h+arg_8]
0x180042c3c  mov     rcx, rdi; this
0x180042c3f  call    ?GetRequest@CDataRequest@@QEBAJKPEAPEAVRequestToken@@@Z; CDataRequest::GetRequest(ulong,RequestToken * *)
0x180042c44  test    eax, eax
0x180042c46  js      loc_18004325E
0x180042c4c  mov     r13, [rbp+57h+var_B0]
0x180042c50  mov     rbx, [r13+20h]
0x180042c54  lea     rcx, [rbp+57h+var_D0]; void *
0x180042c58  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180042c5d  nop
0x180042c5e  mov     ecx, [r13+70h]
0x180042c62  cmp     ecx, 6
0x180042c65  jg      loc_180042F60
0x180042c6b  jz      loc_180042F03
0x180042c71  test    ecx, ecx
0x180042c73  jz      loc_180042EA3
0x180042c79  sub     ecx, 1
0x180042c7c  jz      loc_180042E43
0x180042c82  sub     ecx, 1
0x180042c85  jz      loc_180042E17
0x180042c8b  sub     ecx, 1
0x180042c8e  jz      loc_180042D89
0x180042c94  sub     ecx, 1
0x180042c97  jz      short loc_180042CFF
0x180042c99  cmp     ecx, 1
0x180042c9c  jnz     loc_18004324B
0x180042ca2  mov     rdx, rbx; wchar_t *
0x180042ca5  lea     rcx, [rbp+57h+var_A0]; this
0x180042ca9  call    ?GetFiles@CDataCollection@@QEAAJPEB_W@Z; CDataCollection::GetFiles(wchar_t const *)
0x180042cae  mov     ebx, eax
0x180042cb0  mov     edi, 80000000h
0x180042cb5  lea     ecx, [rax+rdi]
0x180042cb8  test    edi, ecx
0x180042cba  jnz     loc_18004323D
0x180042cc0  cmp     eax, esi
0x180042cc2  jz      loc_18004323D
0x180042cc8  mov     r8d, eax
0x180042ccb  lea     rdx, aGetfileFailed0; "GetFile failed: 0x%x\r\n"
0x180042cd2  lea     rcx, [rbp+57h+var_D0]
0x180042cd6  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180042cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180042ce2  cmp     rcx, r14
0x180042ce5  jz      loc_18004323D
0x180042ceb  test    [rcx+1Ch], r12b
0x180042cef  jz      loc_18004323D
0x180042cf5  mov     edx, 0DDh
0x180042cfa  jmp     loc_18004322A
0x180042cff  xor     edx, edx; dwCoInit
0x180042d01  xor     ecx, ecx; pvReserved
0x180042d03  call    cs:__imp_CoInitializeEx
0x180042d09  mov     edi, eax
0x180042d0b  mov     dword ptr [rbp+57h+var_B0], eax
0x180042d0e  mov     ecx, 80000000h
0x180042d13  add     eax, ecx
0x180042d15  test    ecx, eax
0x180042d17  jnz     short loc_180042D23
0x180042d19  cmp     edi, 80010106h
0x180042d1f  jz      short loc_180042D23
0x180042d21  jmp     short loc_180042D41
0x180042d23  mov     rdx, rbx; wchar_t *
0x180042d26  lea     rcx, [rbp+57h+var_A0]; this
0x180042d2a  call    ?GetWMIDataInternal@CDataCollection@@AEAAJPEB_W@Z; CDataCollection::GetWMIDataInternal(wchar_t const *)
0x180042d2f  mov     ebx, eax
0x180042d31  test    edi, edi
0x180042d33  js      short loc_180042D3B
0x180042d35  call    cs:__imp_CoUninitialize
0x180042d3b  mov     edi, ebx
0x180042d3d  test    ebx, ebx
0x180042d3f  jns     short loc_180042D82
0x180042d41  cmp     edi, esi
0x180042d43  jz      short loc_180042D82
0x180042d45  mov     r8d, edi
0x180042d48  lea     rdx, aGetwmidataFail; "GetWMIData failed: 0x%x\r\n"
0x180042d4f  lea     rcx, [rbp+57h+var_D0]
0x180042d53  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180042d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d5f  cmp     rcx, r14
0x180042d62  jz      short loc_180042D82
0x180042d64  test    [rcx+1Ch], r12b
0x180042d68  jz      short loc_180042D82
0x180042d6a  mov     edx, 0DAh
0x180042d6f  mov     r9d, edi
0x180042d72  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180042d79  mov     rcx, [rcx+10h]
0x180042d7d  call    WPP_SF_d
0x180042d82  mov     edx, edi
0x180042d84  jmp     loc_18004323F
0x180042d89  xor     edi, edi
0x180042d8b  movzx   edx, word ptr [rbx]
0x180042d8e  sub     edx, 31h ; '1'
0x180042d91  jnz     short loc_180042D9E
0x180042d93  movzx   edx, word ptr [rbx+2]
0x180042d97  xor     eax, eax
0x180042d99  movzx   ecx, ax
0x180042d9c  sub     edx, ecx
0x180042d9e  mov     rbx, [rbp+57h+arg_8]
0x180042da2  test    edx, edx
0x180042da4  jnz     short loc_180042E04
0x180042da6  lea     r8, [rbp+57h+var_D0]
0x180042daa  mov     rdx, rbx; struct CDataRequest *
0x180042dad  mov     rcx, r15; this
0x180042db0  call    ?ProcessDefaultDataCollection@CReportManager@@AEAAJPEBVCDataRequest@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ProcessDefaultDataCollection(CDataRequest const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180042db5  mov     edi, eax
0x180042db7  mov     eax, 80000000h
0x180042dbc  lea     ecx, [rdi+rax]
0x180042dbf  test    eax, ecx
0x180042dc1  jnz     short loc_180042E04
0x180042dc3  cmp     edi, esi
0x180042dc5  jz      short loc_180042E04
0x180042dc7  mov     r8d, edi
0x180042dca  lea     rdx, aDefaultdatacol; "DefaultDataCollection failed: 0x%x\r\n"
0x180042dd1  lea     rcx, [rbp+57h+var_D0]
0x180042dd5  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180042dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180042de1  cmp     rcx, r14
0x180042de4  jz      short loc_180042E04
0x180042de6  test    [rcx+1Ch], r12b
0x180042dea  jz      short loc_180042E04
0x180042dec  mov     edx, 0DFh
0x180042df1  mov     r9d, edi
0x180042df4  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180042dfb  mov     rcx, [rcx+10h]
0x180042dff  call    WPP_SF_d
0x180042e04  lea     r8, [rbp+57h+var_D0]
0x180042e08  mov     edx, edi
0x180042e0a  mov     rcx, r13
0x180042e0d  call    ?SetResult@RequestToken@@QEAAXJ$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RequestToken::SetResult(long,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180042e12  jmp     loc_18004324F
0x180042e17  movzx   edx, word ptr [rbx]
0x180042e1a  sub     edx, 31h ; '1'
0x180042e1d  jnz     short loc_180042E2A
0x180042e1f  movzx   edx, word ptr [rbx+2]
0x180042e23  xor     eax, eax
0x180042e25  movzx   ecx, ax
0x180042e28  sub     edx, ecx
0x180042e2a  test    edx, edx
0x180042e2c  jnz     short loc_180042E3C
0x180042e2e  mov     edx, 4; enum _WER_FILE_TYPE
0x180042e33  mov     rcx, [r15+8]; this
0x180042e37  call    ?MarkFilesForUploadByType@CReport@@QEAAJW4_WER_FILE_TYPE@@@Z; CReport::MarkFilesForUploadByType(_WER_FILE_TYPE)
0x180042e3c  xor     edx, edx
0x180042e3e  jmp     loc_18004323F
0x180042e43  mov     r8d, r12d; int
  ... truncated ...
```
