# CReportManager::AddSecondLevelData(CDataRequest const *)

- ea: `0x180044080`
- end: `0x180044a10`
- name: `?AddSecondLevelData@CReportManager@@AEAAJPEBVCDataRequest@@@Z`
- size: `2448`
- prototype: `__int64 __fastcall(CReportManager *__hidden this, const struct CDataRequest *)`
- caller_count: `2`
- callee_count: `33`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800180d8`
- `0x18007cc74`

## callees

- `0x180004c64`
- `0x180009074`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x180020680`
- `0x1800287a0`
- `0x18002a0f4`
- `0x18002d124`
- `0x180037cb8`
- `0x180044080`
- `0x180044a18`
- `0x18004c428`
- `0x180051270`
- `0x1800517ac`
- `0x180075608`
- `0x18007e000`
- `0x18007e738`
- `0x18007e7b8`
- `0x18007e840`
- `0x18007f6a4`
- `0x18007f734`
- `0x18007f8dc`
- `0x18007fd9c`
- `0x18008009c`
- `0x1800807b8`
- `0x18008e878`
- `0x18008e8d4`
- `0x18008e928`
- `0x18008fe08`
- `0x1800909f4`
- `0x180090b54`
- `0x180092c2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800447d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800447fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800447d6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800447fa`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180044215`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180044215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800440b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800440d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800449b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800440b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800440d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800449b6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800440e6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800449c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800440e6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800449c8`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800440c5`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800440c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800441ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800442b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800441ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800442b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800443da`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800443da`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800443a2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800443a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  wchar_t *v12; // r14
  int DataRequestType; // ebx
  wchar_t *v14; // rsi
  __int64 v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // edi
  wchar_t *v18; // r13
  const wchar_t *v19; // rbx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  unsigned int Files; // eax
  unsigned int v26; // ebx
  wchar_t *v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // edi
  int WMIDataInternal; // ebx
  wchar_t *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  unsigned int v34; // edi
  int v35; // edx
  int v36; // edx
  unsigned int v37; // eax
  unsigned int RegistryData; // eax
  unsigned int FilesVersion; // eax
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  unsigned int v45; // eax
  int v46; // edx
  unsigned int v47; // eax
  int v48; // edx
  __int64 v49; // rax
  struct HPSS__ *v50; // r8
  void *v51; // rdx
  int v52; // eax
  unsigned int v53; // edi
  unsigned int DWORD; // eax
  __int64 v55; // rcx
  int v56; // edx
  HANDLE v57; // rax
  bool v59; // [rsp+28h] [rbp-81h]
  wchar_t *v60[4]; // [rsp+30h] [rbp-79h] BYREF
  wchar_t *v61; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int64 v62; // [rsp+58h] [rbp-51h]
  _BYTE v63[24]; // [rsp+60h] [rbp-49h] BYREF
  char v64[40]; // [rsp+78h] [rbp-31h] BYREF
  wchar_t *v65[12]; // [rsp+A0h] [rbp-9h] BYREF
  wchar_t *v67; // [rsp+120h] [rbp+77h] BYREF
  int nPriority; // [rsp+128h] [rbp+7Fh]

  v2 = a2;
  v4 = *((_QWORD *)a2 + 1);
  v5 = *(_QWORD *)a2;
  CDataCollection::CDataCollection((CDataCollection *)v63);
  v6 = 0;
  CurrentThread = GetCurrentThread();
  nPriority = GetThreadPriority(CurrentThread);
  v8 = GetCurrentThread();
  SetThreadPriority(v8, -1);
  v9 = CDataCollection::Initialize(
         (CDataCollection *)v63,
         *((struct CReport **)this + 1),
         *(struct CReportHandleInstance **)this,
         *((void **)this + 33));
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
    v10 = a2;
    goto LABEL_140;
  }
  v11 = 0xEEEEEEEEEEEEEEEFuLL * ((v4 - v5) >> 3);
  v62 = v11;
  if ( (_DWORD)v11 )
  {
    CReportManager::ExternalCallbackDataRequestBegin(this);
    *(_DWORD *)(*((_QWORD *)this + 1) + 6624LL) = 3;
    CReportManager::PreCollectionActions(this, v2);
    while ( v6 < (unsigned int)v11 )
    {
      if ( !WaitForSingleObject(*((HANDLE *)this + 33), 0) )
      {
        v9 = -2145681407;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
        v10 = a2;
        v6 = 1;
        goto LABEL_140;
      }
      v61 = 0;
      v67 = 0;
      if ( (int)CDataRequest::GetRequestByIndex(v2, v6, (const wchar_t **)&v67, (const wchar_t **)&v61) >= 0 )
      {
        v12 = v67;
        DataRequestType = RequestToken::GetDataRequestType(v67);
        v14 = v61;
        CReportManager::ProcessConditionalFileAdds(this, v12, v61);
        if ( DataRequestType == 19 )
        {
          v15 = *((_QWORD *)this + 1);
          v16 = _o__wtoi(v14);
          if ( v16 <= 3 )
            *(_DWORD *)(v15 + 5956) = v16;
        }
        CReportManager::ExternalCallbackDataRequest(this, v12, v14, (unsigned int *)this + 54);
        v2 = a2;
      }
      ++v6;
    }
    v17 = 0;
    v9 = -2145681407;
    v10 = a2;
    while ( 1 )
    {
      LODWORD(v67) = v17;
      if ( v17 >= (unsigned int)v11 )
      {
        v6 = 1;
        goto LABEL_145;
      }
      if ( !WaitForSingleObject(*((HANDLE *)this + 33), 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
        v6 = 1;
        goto LABEL_140;
      }
      v61 = 0;
      if ( (int)CDataRequest::GetRequest(a2, v17, (struct RequestToken **)&v61) >= 0 )
        break;
      v10 = a2;
LABEL_135:
      v17 = (_DWORD)v67 + 1;
    }
    v18 = v61;
    v19 = (const wchar_t *)*((_QWORD *)v61 + 4);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v60);
    v20 = *((_DWORD *)v18 + 28);
    if ( v20 > 6 )
    {
      v40 = v20 - 7;
      if ( !v40 )
      {
        v56 = *v19 - 49;
        if ( *v19 == 49 )
          v56 = v19[1];
        if ( v56 )
          goto LABEL_132;
        v26 = CReportManager::ProcessHeapDumpRequest(this, a2, v60);
        if ( (int)(v26 + 0x80000000) < 0 )
          goto LABEL_130;
        if ( v26 == -2145681407 )
          goto LABEL_130;
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v60,
          L"ProcessHeapDumpRequest failed: 0x%x\r\n",
          v26);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_130;
        v28 = 216;
        goto LABEL_129;
      }
      v41 = v40 - 4;
      if ( !v41 )
      {
        if ( *(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) != 4 )
          goto LABEL_132;
        if ( (unsigned int)_o__wcsicmp(v19, L"AskFull") )
        {
          v53 = 0;
          if ( !(unsigned int)_o__wcsicmp(v19, L"AskKernel") )
            v53 = 2;
        }
        else
        {
          v53 = 1;
        }
        DWORD = UtilRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Control\\CrashControl",
                  L"CrashDumpEnabled",
                  0xFFFFFFFF,
                  0,
                  v59);
        if ( v53 - 1 > 1 )
          goto LABEL_132;
        v55 = DWORD - 1;
        if ( (v55 & 0xFFFFFFFB) == 0 )
        {
          if ( v53 == 2 )
            goto LABEL_132;
          if ( DWORD == 1 )
            goto LABEL_117;
        }
        if ( DWORD == 5 )
        {
LABEL_117:
          if ( v53 == 1 )
            goto LABEL_132;
        }
        if ( ((DWORD - 2) & 0xFFFFFFFB) != 0 || v53 != 2 )
          CReportManager::EnableFullKernelDump(v55, v53);
        goto LABEL_132;
      }
      v42 = v41 - 1;
      if ( v42 )
      {
        v43 = v42 - 4;
        if ( v43 )
        {
          v44 = v43 - 4;
          if ( v44 )
          {
            if ( v44 == 1 && *(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) == 4 )
              EnableKernelIptTracing(v19);
            goto LABEL_132;
          }
          v45 = CDataCollection::AddReportMetadata((CDataCollection *)v63);
          v26 = v45;
          if ( (int)(v45 + 0x80000000) < 0 )
            goto LABEL_130;
          if ( v45 == -2145681407 )
            goto LABEL_130;
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v60,
            L"AddMetadata failed: 0x%x\r\n",
            v45);
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_130;
          v28 = 225;
        }
        else
        {
          v46 = *v19 - 49;
          if ( *v19 == 49 )
            v46 = v19[1];
          if ( v46 )
            goto LABEL_132;
          v47 = CReportManager::ProcessMiniDumpRequest(this, a2, v60);
          v26 = v47;
          if ( (int)(v47 + 0x80000000) < 0 )
            goto LABEL_130;
          if ( v47 == -2145681407 )
            goto LABEL_130;
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v60,
            L"ProcessMiniDumpRequest failed: 0x%x\r\n",
            v47);
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_130;
          v28 = 217;
        }
        goto LABEL_129;
      }
      v29 = 0;
      v48 = *v19 - 49;
      if ( *v19 == 49 )
        v48 = v19[1];
      if ( !v48 )
      {
        v49 = *((_QWORD *)this + 1);
        v50 = *(struct HPSS__ **)(v49 + 9112);
        v51 = *(void **)(v49 + 6640);
        if ( v51 || v50 )
        {
          v52 = CDataCollection::AddLoadedModuleInformation((CDataCollection *)v63, v51, v50);
          v29 = v52;
          if ( v52 < 0 )
          {
            tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              v60,
              L"GetLoadedModuleInformation failed: 0x%x\r\n",
              (unsigned int)v52);
            v31 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v32 = 224;
              goto LABEL_46;
            }
          }
        }
      }
    }
    else
    {
      if ( v20 == 6 )
      {
        FilesVersion = CDataCollection::GetFilesVersion((CDataCollection *)v63, v19);
        v26 = FilesVersion;
        if ( (int)(FilesVersion + 0x80000000) < 0 )
          goto LABEL_130;
        if ( FilesVersion == -2145681407 )
          goto LABEL_130;
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v60,
          L"GetFileVersion failed: 0x%x\r\n",
          FilesVersion);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_130;
        v28 = 222;
        goto LABEL_129;
      }
      if ( !v20 )
      {
        RegistryData = CDataCollection::GetRegistryData((CDataCollection *)v63, v19, 0);
        v26 = RegistryData;
        if ( (int)(RegistryData + 0x80000000) < 0 )
          goto LABEL_130;
        if ( RegistryData == -2145681407 )
          goto LABEL_130;
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v60,
          L"GetRegKey failed: 0x%x\r\n",
          RegistryData);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_130;
        v28 = 219;
        goto LABEL_129;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v37 = CDataCollection::GetRegistryData((CDataCollection *)v63, v19, 1);
        v26 = v37;
        if ( (int)(v37 + 0x80000000) < 0 )
          goto LABEL_130;
        if ( v37 == -2145681407 )
          goto LABEL_130;
        tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v60,
          L"GetRegTree failed: 0x%x\r\n",
          v37);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_130;
        v28 = 220;
        goto LABEL_129;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v36 = *v19 - 49;
        if ( *v19 == 49 )
          v36 = v19[1];
        if ( !v36 )
          CReport::MarkFilesForUploadByType(*((CReport **)this + 1), WerFileTypeUserDocument);
        v33 = 0;
        goto LABEL_131;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v34 = 0;
        v35 = *v19 - 49;
        if ( *v19 == 49 )
          v35 = v19[1];
        v10 = a2;
        if ( !v35 )
        {
          v34 = CReportManager::ProcessDefaultDataCollection(this, a2);
          if ( (int)(v34 + 0x80000000) >= 0 && v34 != -2145681407 )
          {
            tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              v60,
              L"DefaultDataCollection failed: 0x%x\r\n",
              v34);
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v34);
          }
        }
        RequestToken::SetResult(v18, v34, v60);
        goto LABEL_133;
      }
      v24 = v23 - 1;
      if ( v24 )
      {
        if ( v24 == 1 )
        {
          Files = CDataCollection::GetFiles((CDataCollection *)v63, v19);
          v26 = Files;
          if ( (int)(Files + 0x80000000) < 0 )
            goto LABEL_130;
          if ( Files == -2145681407 )
            goto LABEL_130;
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v60,
            L"GetFile failed: 0x%x\r\n",
            Files);
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_130;
          v28 = 221;
LABEL_129:
          WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v26);
LABEL_130:
          v33 = v26;
          goto LABEL_131;
        }
LABEL_132:
        v10 = a2;
LABEL_133:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v60);
        LODWORD(v11) = v62;
        goto LABEL_135;
      }
      v29 = CoInitializeEx(0, 0);
      LODWORD(v61) = v29;
      if ( (int)(v29 + 0x80000000) >= 0 && v29 != -2147417850 )
        goto LABEL_44;
      WMIDataInternal = CDataCollection::GetWMIDataInternal((CDataCollection *)v63, v19);
      if ( (v29 & 0x80000000) == 0 )
        CoUninitialize();
      v29 = WMIDataInternal;
      if ( WMIDataInternal < 0 )
      {
LABEL_44:
        if ( v29 != -2145681407 )
        {
          tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            v60,
            L"GetWMIData failed: 0x%x\r\n",
            v29);
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v32 = 218;
LABEL_46:
            WPP_SF_d(*((_QWORD *)v31 + 2), v32, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v29);
          }
        }
      }
    }
    v33 = v29;
LABEL_131:
    RequestToken::SetResult(v18, v33, v60);
    goto LABEL_132;
  }
  v10 = a2;
LABEL_145:
  v9 = 0;
LABEL_140:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v60);
  CDataRequest::PrintRequests(v10);
  CDataCollection::AddDataCollectionFailure((CDataCollection *)v63, v60[0]);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v60);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v65);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
    v65,
    L"External Collection Data\n\n");
  if ( v6 )
    CReportManager::ExternalCallbackDataRequestEnd(this, v65);
  CDataCollection::AddDataCollectionFailure((CDataCollection *)v63, v65[0]);
  v57 = GetCurrentThread();
  SetThreadPriority(v57, nPriority);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v65);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v64);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180044080  mov     [rsp-8+arg_8], rdx
0x180044085  push    rbp
0x180044086  push    rbx
0x180044087  push    rsi
0x180044088  push    rdi
0x180044089  push    r12
0x18004408b  push    r13
0x18004408d  push    r14
0x18004408f  push    r15
0x180044091  lea     rbp, [rsp-1Fh]
0x180044096  sub     rsp, 0C8h
0x18004409d  mov     r14, rdx
0x1800440a0  mov     r12, rcx
0x1800440a3  mov     r13, [rdx+8]
0x1800440a7  mov     rbx, [rdx]
0x1800440aa  lea     rcx, [rbp+57h+var_A0]; this
0x1800440ae  call    ??0CDataCollection@@QEAA@XZ; CDataCollection::CDataCollection(void)
0x1800440b3  nop
0x1800440b4  xor     edi, edi
0x1800440b6  call    cs:__imp_GetCurrentThread
0x1800440bd  nop     dword ptr [rax+rax+00h]
0x1800440c2  mov     rcx, rax; hThread
0x1800440c5  call    cs:__imp_GetThreadPriority
0x1800440cc  nop     dword ptr [rax+rax+00h]
0x1800440d1  mov     [rbp+57h+nPriority], eax
0x1800440d4  call    cs:__imp_GetCurrentThread
0x1800440db  nop     dword ptr [rax+rax+00h]
0x1800440e0  mov     rcx, rax; hThread
0x1800440e3  or      edx, 0FFFFFFFFh; nPriority
0x1800440e6  call    cs:__imp_SetThreadPriority
0x1800440ed  nop     dword ptr [rax+rax+00h]
0x1800440f2  mov     r9, [r12+108h]; void *
0x1800440fa  mov     r8, [r12]; struct CReportHandleInstance *
0x1800440fe  mov     rdx, [r12+8]; struct CReport *
0x180044103  lea     rcx, [rbp+57h+var_A0]; this
0x180044107  call    ?Initialize@CDataCollection@@QEAAJPEAVCReport@@PEAVCReportHandleInstance@@PEAX@Z; CDataCollection::Initialize(CReport *,CReportHandleInstance *,void *)
0x18004410c  mov     esi, eax
0x18004410e  test    eax, eax
0x180044110  jns     short loc_18004414D
0x180044112  lea     r14, WPP_GLOBAL_Control
0x180044119  mov     rcx, cs:WPP_GLOBAL_Control
0x180044120  cmp     rcx, r14
0x180044123  jz      short loc_180044144
0x180044125  lea     r15d, [rdi+1]
0x180044129  test    [rcx+1Ch], r15b
0x18004412d  jz      short loc_180044144
0x18004412f  mov     edx, 0D5h
0x180044134  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x18004413b  mov     rcx, [rcx+10h]
0x18004413f  call    WPP_SF_
0x180044144  mov     rbx, [rbp+57h+arg_8]
0x180044148  jmp     loc_180044952
0x18004414d  sub     r13, rbx
0x180044150  sar     r13, 3
0x180044154  mov     rax, 0EEEEEEEEEEEEEEEFh
0x18004415e  imul    r13, rax
0x180044162  mov     [rbp+57h+var_A8], r13
0x180044166  test    r13d, r13d
0x180044169  jz      loc_1800449FF
0x18004416f  mov     rcx, r12; this
0x180044172  call    ?ExternalCallbackDataRequestBegin@CReportManager@@AEAAHXZ; CReportManager::ExternalCallbackDataRequestBegin(void)
0x180044177  mov     rax, [r12+8]
0x18004417c  mov     dword ptr [rax+19E0h], 3
0x180044186  mov     rdx, r14; struct CDataRequest *
0x180044189  mov     rcx, r12; this
0x18004418c  call    ?PreCollectionActions@CReportManager@@AEAAJPEBVCDataRequest@@@Z; CReportManager::PreCollectionActions(CDataRequest const *)
0x180044191  mov     r15d, 1
0x180044197  mov     [rbp+57h+arg_0], r15d
0x18004419b  cmp     edi, r13d
0x18004419e  jnb     loc_18004428D
0x1800441a4  xor     edx, edx; dwMilliseconds
0x1800441a6  mov     rcx, [r12+108h]; hHandle
0x1800441ae  call    cs:__imp_WaitForSingleObject
0x1800441b5  nop     dword ptr [rax+rax+00h]
0x1800441ba  test    eax, eax
0x1800441bc  jz      loc_18004424E
0x1800441c2  mov     [rbp+57h+var_B0], 0
0x1800441ca  mov     [rbp+57h+arg_10], 0
0x1800441d2  lea     r9, [rbp+57h+var_B0]; wchar_t **
0x1800441d6  lea     r8, [rbp+57h+arg_10]; wchar_t **
0x1800441da  mov     edx, edi; unsigned int
0x1800441dc  mov     rcx, r14; this
0x1800441df  call    ?GetRequestByIndex@CDataRequest@@QEBAJKPEAPEB_W0@Z; CDataRequest::GetRequestByIndex(ulong,wchar_t const * *,wchar_t const * *)
0x1800441e4  test    eax, eax
0x1800441e6  js      short loc_180044246
0x1800441e8  mov     r14, [rbp+57h+arg_10]
0x1800441ec  mov     rcx, r14
0x1800441ef  call    ?GetDataRequestType@RequestToken@@SA?AW4DATA_REQUEST_TYPE@1@PEB_W@Z; RequestToken::GetDataRequestType(wchar_t const *)
0x1800441f4  mov     ebx, eax
0x1800441f6  mov     rsi, [rbp+57h+var_B0]
0x1800441fa  mov     r8, rsi
0x1800441fd  mov     rdx, r14
0x180044200  mov     rcx, r12
0x180044203  call    ?ProcessConditionalFileAdds@CReportManager@@AEAAHPEB_W0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ProcessConditionalFileAdds(wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180044208  cmp     ebx, 13h
0x18004420b  jnz     short loc_18004422C
0x18004420d  mov     rbx, [r12+8]
0x180044212  mov     rcx, rsi
0x180044215  call    cs:__imp__o__wtoi
0x18004421c  nop     dword ptr [rax+rax+00h]
0x180044221  cmp     eax, 3
0x180044224  ja      short loc_18004422C
0x180044226  mov     [rbx+1744h], eax
0x18004422c  lea     r9, [r12+0D8h]; unsigned int *
0x180044234  mov     r8, rsi; wchar_t *
0x180044237  mov     rdx, r14; wchar_t *
0x18004423a  mov     rcx, r12; this
0x18004423d  call    ?ExternalCallbackDataRequest@CReportManager@@AEAAHPEB_W0PEAK@Z; CReportManager::ExternalCallbackDataRequest(wchar_t const *,wchar_t const *,ulong *)
0x180044242  mov     r14, [rbp+57h+arg_8]
0x180044246  add     edi, r15d
0x180044249  jmp     loc_18004419B
0x18004424e  mov     esi, 801B8001h
0x180044253  lea     r14, WPP_GLOBAL_Control
0x18004425a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044261  cmp     rcx, r14
0x180044264  jz      short loc_180044281
0x180044266  test    byte ptr [rcx+1Ch], 4
0x18004426a  jz      short loc_180044281
0x18004426c  mov     edx, 0D6h
0x180044271  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180044278  mov     rcx, [rcx+10h]
0x18004427c  call    WPP_SF_
0x180044281  mov     rbx, [rbp+57h+arg_8]
0x180044285  mov     edi, r15d
0x180044288  jmp     loc_180044952
0x18004428d  xor     edi, edi
0x18004428f  lea     r14, WPP_GLOBAL_Control
0x180044296  mov     esi, 801B8001h
0x18004429b  mov     rbx, [rbp+57h+arg_8]
0x18004429f  mov     dword ptr [rbp+57h+arg_10], edi
0x1800442a2  cmp     edi, r13d
0x1800442a5  jnb     loc_180044A05
0x1800442ab  xor     edx, edx; dwMilliseconds
0x1800442ad  mov     rcx, [r12+108h]; hHandle
0x1800442b5  call    cs:__imp_WaitForSingleObject
0x1800442bc  nop     dword ptr [rax+rax+00h]
0x1800442c1  test    eax, eax
0x1800442c3  jz      loc_180044928
0x1800442c9  mov     [rbp+57h+var_B0], 0
0x1800442d1  lea     r8, [rbp+57h+var_B0]; struct RequestToken **
0x1800442d5  mov     edx, edi; unsigned int
0x1800442d7  mov     rdi, [rbp+57h+arg_8]
0x1800442db  mov     rcx, rdi; this
0x1800442de  call    ?GetRequest@CDataRequest@@QEBAJKPEAPEAVRequestToken@@@Z; CDataRequest::GetRequest(ulong,RequestToken * *)
0x1800442e3  test    eax, eax
0x1800442e5  js      loc_180044919
0x1800442eb  mov     r13, [rbp+57h+var_B0]
0x1800442ef  mov     rbx, [r13+20h]
0x1800442f3  lea     rcx, [rbp+57h+var_D0]; void *
0x1800442f7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800442fc  nop
0x1800442fd  mov     ecx, [r13+70h]
0x180044301  cmp     ecx, 6
0x180044304  jg      loc_18004460C
0x18004430a  jz      loc_1800445AF
0x180044310  test    ecx, ecx
0x180044312  jz      loc_18004454F
0x180044318  sub     ecx, 1
0x18004431b  jz      loc_1800444EF
0x180044321  sub     ecx, 1
0x180044324  jz      loc_1800444C2
0x18004432a  sub     ecx, 1
0x18004432d  jz      loc_180044434
0x180044333  sub     ecx, 1
0x180044336  jz      short loc_18004439E
0x180044338  cmp     ecx, 1
0x18004433b  jnz     loc_180044906
0x180044341  mov     rdx, rbx; wchar_t *
0x180044344  lea     rcx, [rbp+57h+var_A0]; this
0x180044348  call    ?GetFiles@CDataCollection@@QEAAJPEB_W@Z; CDataCollection::GetFiles(wchar_t const *)
0x18004434d  mov     ebx, eax
0x18004434f  mov     edi, 80000000h
0x180044354  lea     ecx, [rax+rdi]
0x180044357  test    edi, ecx
0x180044359  jnz     loc_1800448F8
0x18004435f  cmp     eax, esi
0x180044361  jz      loc_1800448F8
0x180044367  mov     r8d, eax
0x18004436a  lea     rdx, aGetfileFailed0; "GetFile failed: 0x%x\r\n"
0x180044371  lea     rcx, [rbp+57h+var_D0]
0x180044375  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18004437a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044381  cmp     rcx, r14
0x180044384  jz      loc_1800448F8
0x18004438a  test    [rcx+1Ch], r15b
0x18004438e  jz      loc_1800448F8
0x180044394  mov     edx, 0DDh
0x180044399  jmp     loc_1800448E5
0x18004439e  xor     edx, edx; dwCoInit
0x1800443a0  xor     ecx, ecx; pvReserved
0x1800443a2  call    cs:__imp_CoInitializeEx
0x1800443a9  nop     dword ptr [rax+rax+00h]
0x1800443ae  mov     edi, eax
0x1800443b0  mov     dword ptr [rbp+57h+var_B0], eax
0x1800443b3  mov     ecx, 80000000h
0x1800443b8  add     eax, ecx
0x1800443ba  test    ecx, eax
0x1800443bc  jnz     short loc_1800443C8
0x1800443be  cmp     edi, 80010106h
0x1800443c4  jz      short loc_1800443C8
0x1800443c6  jmp     short loc_1800443EC
0x1800443c8  mov     rdx, rbx; wchar_t *
0x1800443cb  lea     rcx, [rbp+57h+var_A0]; this
0x1800443cf  call    ?GetWMIDataInternal@CDataCollection@@AEAAJPEB_W@Z; CDataCollection::GetWMIDataInternal(wchar_t const *)
0x1800443d4  mov     ebx, eax
0x1800443d6  test    edi, edi
0x1800443d8  js      short loc_1800443E6
0x1800443da  call    cs:__imp_CoUninitialize
0x1800443e1  nop     dword ptr [rax+rax+00h]
0x1800443e6  mov     edi, ebx
0x1800443e8  test    ebx, ebx
0x1800443ea  jns     short loc_18004442D
0x1800443ec  cmp     edi, esi
0x1800443ee  jz      short loc_18004442D
0x1800443f0  mov     r8d, edi
0x1800443f3  lea     rdx, aGetwmidataFail; "GetWMIData failed: 0x%x\r\n"
0x1800443fa  lea     rcx, [rbp+57h+var_D0]
0x1800443fe  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180044403  mov     rcx, cs:WPP_GLOBAL_Control
0x18004440a  cmp     rcx, r14
0x18004440d  jz      short loc_18004442D
0x18004440f  test    [rcx+1Ch], r15b
0x180044413  jz      short loc_18004442D
0x180044415  mov     edx, 0DAh
0x18004441a  mov     r9d, edi
0x18004441d  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180044424  mov     rcx, [rcx+10h]
0x180044428  call    WPP_SF_d
0x18004442d  mov     edx, edi
0x18004442f  jmp     loc_1800448FA
0x180044434  xor     edi, edi
0x180044436  movzx   edx, word ptr [rbx]
0x180044439  sub     edx, 31h ; '1'
0x18004443c  jnz     short loc_180044449
0x18004443e  movzx   edx, word ptr [rbx+2]
0x180044442  xor     eax, eax
0x180044444  movzx   ecx, ax
0x180044447  sub     edx, ecx
0x180044449  mov     rbx, [rbp+57h+arg_8]
0x18004444d  test    edx, edx
0x18004444f  jnz     short loc_1800444AF
0x180044451  lea     r8, [rbp+57h+var_D0]
0x180044455  mov     rdx, rbx; struct CDataRequest *
0x180044458  mov     rcx, r12; this
0x18004445b  call    ?ProcessDefaultDataCollection@CReportManager@@AEAAJPEBVCDataRequest@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ProcessDefaultDataCollection(CDataRequest const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180044460  mov     edi, eax
0x180044462  mov     eax, 80000000h
0x180044467  lea     ecx, [rdi+rax]
0x18004446a  test    eax, ecx
0x18004446c  jnz     short loc_1800444AF
0x18004446e  cmp     edi, esi
0x180044470  jz      short loc_1800444AF
0x180044472  mov     r8d, edi
0x180044475  lea     rdx, aDefaultdatacol; "DefaultDataCollection failed: 0x%x\r\n"
0x18004447c  lea     rcx, [rbp+57h+var_D0]
0x180044480  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180044485  mov     rcx, cs:WPP_GLOBAL_Control
0x18004448c  cmp     rcx, r14
0x18004448f  jz      short loc_1800444AF
0x180044491  test    [rcx+1Ch], r15b
0x180044495  jz      short loc_1800444AF
0x180044497  mov     edx, 0DFh
0x18004449c  mov     r9d, edi
0x18004449f  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x1800444a6  mov     rcx, [rcx+10h]
0x1800444aa  call    WPP_SF_d
0x1800444af  lea     r8, [rbp+57h+var_D0]
0x1800444b3  mov     edx, edi
0x1800444b5  mov     rcx, r13
0x1800444b8  call    ?SetResult@RequestToken@@QEAAXJ$$QEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RequestToken::SetResult(long,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1800444bd  jmp     loc_18004490A
0x1800444c2  movzx   edx, word ptr [rbx]
0x1800444c5  sub     edx, 31h ; '1'
0x1800444c8  jnz     short loc_1800444D5
0x1800444ca  movzx   edx, word ptr [rbx+2]
0x1800444ce  xor     eax, eax
0x1800444d0  movzx   ecx, ax
0x1800444d3  sub     edx, ecx
0x1800444d5  test    edx, edx
0x1800444d7  jnz     short loc_1800444E8
0x1800444d9  mov     edx, 4; enum _WER_FILE_TYPE
0x1800444de  mov     rcx, [r12+8]; this
0x1800444e3  call    ?MarkFilesForUploadByType@CReport@@QEAAJW4_WER_FILE_TYPE@@@Z; CReport::MarkFilesForUploadByType(_WER_FILE_TYPE)
0x1800444e8  xor     edx, edx
0x1800444ea  jmp     loc_1800448FA
0x1800444ef  mov     r8d, r15d; int
0x1800444f2  mov     rdx, rbx; wchar_t *
0x1800444f5  lea     rcx, [rbp+57h+var_A0]; this
0x1800444f9  call    ?GetRegistryData@CDataCollection@@QEAAJPEB_WH@Z; CDataCollection::GetRegistryData(wchar_t const *,int)
0x1800444fe  mov     ebx, eax
0x180044500  mov     edi, 80000000h
0x180044505  lea     ecx, [rax+rdi]
0x180044508  test    edi, ecx
0x18004450a  jnz     loc_1800448F8
0x180044510  cmp     eax, esi
0x180044512  jz      loc_1800448F8
0x180044518  mov     r8d, eax
0x18004451b  lea     rdx, aGetregtreeFail; "GetRegTree failed: 0x%x\r\n"
0x180044522  lea     rcx, [rbp+57h+var_D0]
0x180044526  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
  ... truncated ...
```
