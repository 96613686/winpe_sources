# GetExtendedError

- ea: `0x18002df40`
- end: `0x18002f122`
- name: `GetExtendedError`
- size: `4578`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002da0`
- `0x180003298`
- `0x1800039e4`
- `0x18000a914`
- `0x18000af14`
- `0x18000af40`
- `0x18000b0bc`
- `0x18000ba8c`
- `0x18000bdf0`
- `0x18000be18`
- `0x18000c354`
- `0x18000c538`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x18000fa9c`
- `0x180010b9c`
- `0x18001170c`
- `0x180012240`
- `0x18001d378`
- `0x18002126c`
- `0x180022740`
- `0x18002932c`
- `0x180029788`
- `0x18002df40`
- `0x180032180`
- `0x180037da8`
- `0x180042dac`
- `0x18004b1c0`
- `0x1800530e4`
- `0x180054c00`
- `0x180054eec`
- `0x1800558c0`
- `0x18005b890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002efc9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002efe4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002efff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002efc9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002efe4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002efff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ead7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ead7`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002e924`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002e924`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002ea3c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18002ea3c`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18002e8cf`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x18002e8cf`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x18002eaf6`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x18002eaf6`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18002eb2b`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18002eb2b`

## string_xrefs

- `0x18002e948`: `Thread locale is %ls.`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
__int64 __fastcall GetExtendedError(__int64 a1, __int64 a2, unsigned int *a3, _DWORD *a4, unsigned __int16 **a5)
{
  __int64 v8; // r8
  __int64 v9; // rbx
  _QWORD *v10; // r14
  void *v11; // rbx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  DWORD v15; // eax
  LCID ThreadLocale; // eax
  __int64 v17; // rdx
  volatile signed __int32 *v18; // rcx
  volatile signed __int32 *v19; // r13
  int *v20; // rbx
  volatile signed __int32 *v21; // r13
  HANDLE CurrentProcess; // rsi
  DWORD i; // ebx
  __int64 v24; // r12
  __int64 v25; // r15
  __int64 v26; // r14
  __int64 v27; // rsi
  __int64 v28; // rdi
  int v29; // ecx
  unsigned __int16 *v30; // rbx
  unsigned int v31; // ebx
  char **v33; // [rsp+20h] [rbp-2388h]
  char **v34; // [rsp+20h] [rbp-2388h]
  unsigned __int16 *v35; // [rsp+50h] [rbp-2358h] BYREF
  int IdentityFromExternalHandle_Internal; // [rsp+58h] [rbp-2350h] BYREF
  __int64 v37; // [rsp+60h] [rbp-2348h] BYREF
  volatile signed __int32 *v38; // [rsp+68h] [rbp-2340h] BYREF
  __int64 v39; // [rsp+70h] [rbp-2338h] BYREF
  __int64 v40; // [rsp+78h] [rbp-2330h] BYREF
  __int64 v41; // [rsp+80h] [rbp-2328h] BYREF
  __int64 v42; // [rsp+88h] [rbp-2320h] BYREF
  __int64 v43; // [rsp+90h] [rbp-2318h] BYREF
  __int64 v44; // [rsp+98h] [rbp-2310h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-2308h] BYREF
  __time64_t Time; // [rsp+A8h] [rbp-2300h] BYREF
  unsigned int v47; // [rsp+B0h] [rbp-22F8h] BYREF
  DWORD cbNeeded[2]; // [rsp+B8h] [rbp-22F0h] BYREF
  char v49; // [rsp+C0h] [rbp-22E8h]
  int v50; // [rsp+C8h] [rbp-22E0h] BYREF
  unsigned int v51; // [rsp+CCh] [rbp-22DCh] BYREF
  unsigned int v52; // [rsp+D0h] [rbp-22D8h] BYREF
  void *Block; // [rsp+D8h] [rbp-22D0h] BYREF
  char *v54; // [rsp+E0h] [rbp-22C8h] BYREF
  char *v55; // [rsp+E8h] [rbp-22C0h] BYREF
  unsigned __int16 *v56; // [rsp+F0h] [rbp-22B8h] BYREF
  __int64 v57; // [rsp+F8h] [rbp-22B0h] BYREF
  char *v58[5]; // [rsp+100h] [rbp-22A8h] BYREF
  unsigned __int16 **v59; // [rsp+128h] [rbp-2280h]
  HMODULE hModule[1024]; // [rsp+150h] [rbp-2258h] BYREF
  struct _OSVERSIONINFOW TimeZoneInformation; // [rsp+2150h] [rbp-258h] BYREF

  v59 = a5;
  IdentityFromExternalHandle_Internal = 0;
  v57 = 0;
  v56 = 0;
  v55 = 0;
  v54 = 0;
  Block = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v45);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v44);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v35);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v37);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v43);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v41);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v40);
  v52 = 0;
  v51 = 0;
  v50 = 0;
  v47 = 0;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v58,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
    0x102Au,
    (char *)&IdentityFromExternalHandle_Internal,
    "IDCRL::GetExtendedError",
    L"hIdentity=0x%p, pdwCategory=0x%p, pdwError=0x%p, pszErrorBlob=0x%p",
    0,
    a3,
    a4,
    a5);
  if ( a1 && a3 && a4 )
  {
    IdentityFromExternalHandle_Internal = VerifyInitialized();
    if ( IdentityFromExternalHandle_Internal < 0
      || (LOBYTE(v8) = 1,
          IdentityFromExternalHandle_Internal = CClientIdentityStore::GetIdentityFromExternalHandle_Internal(
                                                  g_pPPCRL + 8,
                                                  a1,
                                                  v8,
                                                  &v57),
          IdentityFromExternalHandle_Internal < 0) )
    {
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
      ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 6));
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v44 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
      goto LABEL_43;
    }
    v9 = v57;
    if ( !v57 )
    {
      IdentityFromExternalHandle_Internal = -2147188704;
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
      ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 6));
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v44 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
      goto LABEL_43;
    }
    *(_QWORD *)cbNeeded = v57 + 16;
    v49 = 0;
    IdentityFromExternalHandle_Internal = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::TryLock(cbNeeded);
    if ( IdentityFromExternalHandle_Internal < 0 )
      goto LABEL_19;
    v10 = (_QWORD *)(v9 + 64);
    v11 = *(void **)(v9 + 64);
    if ( !v11 )
    {
      v11 = operator new(0x28u);
      *((_QWORD *)v11 + 1) = 0;
      *((_DWORD *)v11 + 6) = 1;
      *(_QWORD *)v11 = &SmartWLIDHandle::`vftable'{for `SmartObj<void *>'};
      *((_QWORD *)v11 + 2) = &SmartWLIDHandle::`vftable'{for `CRefCounted'};
      *((_QWORD *)v11 + 4) = 0;
      CAutoRefPtr<SmartWLIDHandle>::Deinit(v10);
      *v10 = v11;
    }
    v12 = WLIDCGetExtendedError(*((void *const *)v11 + 1), a3, &v47, &v55, &v54, (char **)&Block, &v56, &v52);
    IdentityFromExternalHandle_Internal = v12;
    if ( v12 < 0 || v12 == 1 )
      goto LABEL_19;
    if ( !*a3 && !v47 )
    {
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x1051u,
        L"No extended error info is set.");
      IdentityFromExternalHandle_Internal = 1;
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)cbNeeded);
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
      ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 6));
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v44 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
      goto LABEL_43;
    }
    *a4 = MapSQMError(v47);
    if ( a5 )
    {
      v13 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &Time,
              v54);
      PPEscapedXML(v13, &v45);
      ATL::CStringData::Release((ATL::CStringData *)(Time - 24));
      v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &Time,
              Block);
      PPEscapedXML(v14, &v44);
      ATL::CStringData::Release((ATL::CStringData *)(Time - 24));
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)cbNeeded);
      memset_0(&TimeZoneInformation, 0, 0xACu);
      v15 = GetTimeZoneInformation((LPTIME_ZONE_INFORMATION)&TimeZoneInformation);
      if ( v15 == 1 || v15 == 2 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v39);
      }
      else
      {
        LODWORD(v33) = ATL::AtlHresultFromLastError();
        TracePrintW(
          2u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          0x106Eu,
          L"GetTimeZoneInformation failed (0x%x)\n",
          v33);
      }
      ThreadLocale = GetThreadLocale();
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v37,
        L"%-d",
        ThreadLocale);
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x1075u,
        L"Thread locale is %ls.",
        v37);
      ATL::CTime::GetTickCount(&Time);
      v17 = *(_QWORD *)ATL::CTime::FormatGmt(&Time);
      v18 = (volatile signed __int32 *)(v17 - 24);
      v19 = v38;
      v20 = (int *)(v38 - 6);
      if ( (volatile signed __int32 *)(v17 - 24) != v38 - 6 )
      {
        if ( v20[4] >= 0 && *(_QWORD *)v18 == *(_QWORD *)v20 )
        {
          v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v18);
          ATL::CStringData::Release((ATL::CStringData *)v20);
          v19 = v21 + 6;
          v38 = v19;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v38, v17, *(unsigned int *)(v17 - 16));
          v19 = v38;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)cbNeeded - 24LL));
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x107Du,
        L"Current time is %ls.",
        v19);
      memset_0(&TimeZoneInformation.dwMajorVersion, 0, 0x110u);
      TimeZoneInformation.dwOSVersionInfoSize = 276;
      if ( GetVersionExW(&TimeZoneInformation) )
      {
        LODWORD(v34) = TimeZoneInformation.dwBuildNumber;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &v43,
          L"%d.%d.%d (%s)",
          TimeZoneInformation.dwMajorVersion,
          TimeZoneInformation.dwMinorVersion,
          v34,
          TimeZoneInformation.szCSDVersion);
      }
      else
      {
        LODWORD(v34) = ATL::AtlHresultFromLastError();
        TracePrintW(
          2u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          0x1090u,
          L"GetVersionEx failed with (0x%x).",
          v34);
      }
      memset_0(hModule, 0, sizeof(hModule));
      cbNeeded[0] = 0;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&Time);
      CurrentProcess = GetCurrentProcess();
      if ( K32EnumProcessModules(CurrentProcess, hModule, 0x2000u, cbNeeded) )
      {
        for ( i = 0; i < cbNeeded[0] >> 3; ++i )
        {
          if ( K32GetModuleFileNameExW(CurrentProcess, hModule[i], (LPWSTR)&TimeZoneInformation, 0x104u) )
          {
            GetDisplayFileVersion((LPCWSTR)&TimeZoneInformation);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
              &v40,
              L"<Module version=\"%s\">%s</Module>",
              Time,
              &TimeZoneInformation);
          }
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(Time - 24));
      CWininetHandler::GetInternetConnectedState(&v50, &v51);
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v35);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v35,
        L"<ErrorCode>%d</ErrorCode>",
        v47);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v35,
        L"<FileAndLine>%S</FileAndLine>",
        v55);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v35,
        L"%d",
        v50 != 0);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v35,
        L"0x%x",
        v51);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v35,
        L"<Host port=\"%d\">%s</Host>",
        v52,
        v56);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      v24 = v43;
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      v25 = v39;
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      v26 = v45;
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      v27 = v44;
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      v28 = v40;
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      ATL::CSimpleStringT<unsigned short,0>::Append(&v35);
      v30 = v35;
      if ( (byte_180094B07 & 0x40) != 0 )
        McTemplateU0sqz_EventWriteTransfer(
          v29,
          (unsigned int)WlidCli_TraceVerbose,
          (unsigned int)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          4310,
          (__int64)v35);
      IdentityFromExternalHandle_Internal = CExternalMemoryManager::AllocateStringForExternal(
                                              (CExternalMemoryManager *)(g_pPPCRL + 58),
                                              v30,
                                              v59);
      if ( IdentityFromExternalHandle_Internal < 0 )
        TracePrintW(
          2u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          0x10DCu,
          L"Could not allocate memory for external string");
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
      ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 6));
      ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v30 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    }
    else
    {
LABEL_19:
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)cbNeeded);
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
      ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 6));
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v44 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
    }
  }
  else
  {
    IdentityFromExternalHandle_Internal = -2147024809;
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v58);
    ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 6));
    ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v44 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
  }
LABEL_43:
  v31 = IdentityFromExternalHandle_Internal;
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  if ( v54 )
  {
    free(v54);
    v54 = 0;
  }
  if ( v55 )
  {
    free(v55);
    v55 = 0;
  }
  CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v56);
  CAutoRefPtr<CAuthContext>::Deinit(&v57);
  return v31;
}

```

## disassembly

```asm
0x18002df40  push    rbx
0x18002df42  push    rsi
0x18002df43  push    rdi
0x18002df44  push    r12
0x18002df46  push    r13
0x18002df48  push    r14
0x18002df4a  push    r15
0x18002df4c  mov     eax, 2370h
0x18002df51  call    _alloca_probe
0x18002df56  sub     rsp, rax
0x18002df59  mov     rax, cs:__security_cookie
0x18002df60  xor     rax, rsp
0x18002df63  mov     [rsp+23A8h+var_48], rax
0x18002df6b  mov     r15, r9
0x18002df6e  mov     rsi, r8
0x18002df71  mov     rbx, rcx
0x18002df74  mov     r12, [rsp+23A8h+arg_20]
0x18002df7c  mov     [rsp+23A8h+var_2280], r12
0x18002df84  xor     edi, edi
0x18002df86  mov     [rsp+23A8h+var_2350], edi
0x18002df8a  mov     [rsp+23A8h+var_22B0], rdi
0x18002df92  mov     [rsp+23A8h+var_22B8], rdi
0x18002df9a  mov     [rsp+23A8h+var_22C0], rdi
0x18002dfa2  mov     [rsp+23A8h+var_22C8], rdi
0x18002dfaa  mov     [rsp+23A8h+Block], rdi
0x18002dfb2  lea     rcx, [rsp+23A8h+var_2308]
0x18002dfba  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002dfbf  nop
0x18002dfc0  lea     rcx, [rsp+23A8h+var_2310]
0x18002dfc8  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002dfcd  nop
0x18002dfce  lea     rcx, [rsp+23A8h+var_2358]
0x18002dfd3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002dfd8  nop
0x18002dfd9  lea     rcx, [rsp+23A8h+var_2338]
0x18002dfde  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002dfe3  nop
0x18002dfe4  lea     rcx, [rsp+23A8h+var_2340]
0x18002dfe9  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002dfee  nop
0x18002dfef  lea     rcx, [rsp+23A8h+var_2348]
0x18002dff4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002dff9  nop
0x18002dffa  lea     rcx, [rsp+23A8h+var_2318]
0x18002e002  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002e007  nop
0x18002e008  lea     rcx, [rsp+23A8h+var_2320]
0x18002e010  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002e015  nop
0x18002e016  lea     rcx, [rsp+23A8h+var_2328]
0x18002e01e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002e023  nop
0x18002e024  lea     rcx, [rsp+23A8h+var_2330]
0x18002e029  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002e02e  nop
0x18002e02f  mov     [rsp+23A8h+var_22D8], edi
0x18002e036  mov     [rsp+23A8h+var_22DC], edi
0x18002e03d  mov     [rsp+23A8h+var_22E0], edi
0x18002e044  mov     [rsp+23A8h+var_22F8], edi
0x18002e04b  mov     [rsp+23A8h+var_2360], r12
0x18002e050  mov     [rsp+23A8h+var_2368], r15
0x18002e055  mov     [rsp+23A8h+var_2370], rsi
0x18002e05a  mov     [rsp+23A8h+var_2378], rdi
0x18002e05f  lea     rax, aHidentity0xPPd; "hIdentity=0x%p, pdwCategory=0x%p, pdwEr"...
0x18002e066  mov     [rsp+23A8h+var_2380], rax
0x18002e06b  lea     rax, aIdcrlGetextend; "IDCRL::GetExtendedError"
0x18002e072  mov     [rsp+23A8h+var_2388], rax
0x18002e077  lea     r9, [rsp+23A8h+var_2350]
0x18002e07c  mov     r8d, 102Ah
0x18002e082  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18002e089  lea     rcx, [rsp+23A8h+var_22A8]
0x18002e091  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x18002e096  nop
0x18002e097  test    rbx, rbx
0x18002e09a  jz      loc_18002F04D
0x18002e0a0  test    rsi, rsi
0x18002e0a3  jz      loc_18002F04D
0x18002e0a9  test    r15, r15
0x18002e0ac  jz      loc_18002F04D
0x18002e0b2  call    ?VerifyInitialized@@YAJXZ; VerifyInitialized(void)
0x18002e0b7  mov     [rsp+23A8h+var_2350], eax
0x18002e0bb  test    eax, eax
0x18002e0bd  jns     loc_18002E17B
0x18002e0c3  lea     rcx, [rsp+23A8h+var_22A8]
0x18002e0cb  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002e0d0  nop
0x18002e0d1  mov     rcx, [rsp+23A8h+var_2330]
0x18002e0d6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e0da  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e0df  nop
0x18002e0e0  mov     rcx, [rsp+23A8h+var_2328]
0x18002e0e8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e0ec  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e0f1  nop
0x18002e0f2  mov     rcx, [rsp+23A8h+var_2320]
0x18002e0fa  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e0fe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e103  nop
0x18002e104  mov     rcx, [rsp+23A8h+var_2318]
0x18002e10c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e110  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e115  nop
0x18002e116  mov     rcx, [rsp+23A8h+var_2348]
0x18002e11b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e11f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e124  nop
0x18002e125  mov     rcx, [rsp+23A8h+var_2340]
0x18002e12a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e12e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e133  nop
0x18002e134  mov     rcx, [rsp+23A8h+var_2338]
0x18002e139  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e13d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e142  nop
0x18002e143  mov     rcx, [rsp+23A8h+var_2358]
0x18002e148  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e14c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e151  nop
0x18002e152  mov     rcx, [rsp+23A8h+var_2310]
0x18002e15a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e15e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e163  nop
0x18002e164  mov     rcx, [rsp+23A8h+var_2308]
0x18002e16c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e170  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e175  nop
0x18002e176  jmp     loc_18002EFB8
0x18002e17b  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x18002e182  add     rcx, 20h ; ' '
0x18002e186  lea     r9, [rsp+23A8h+var_22B0]
0x18002e18e  mov     r13d, 1
0x18002e194  mov     r8b, r13b
0x18002e197  mov     rdx, rbx
0x18002e19a  call    ?GetIdentityFromExternalHandle_Internal@CClientIdentityStore@@QEAAJPEAU_tagPIH@IDCRL@@_NAEAV?$CAutoRefPtr@VCClientSingleIdentity@@@@@Z; CClientIdentityStore::GetIdentityFromExternalHandle_Internal(IDCRL::_tagPIH *,bool,CAutoRefPtr<CClientSingleIdentity> &)
0x18002e19f  mov     [rsp+23A8h+var_2350], eax
0x18002e1a3  test    eax, eax
0x18002e1a5  jns     loc_18002E263
0x18002e1ab  lea     rcx, [rsp+23A8h+var_22A8]
0x18002e1b3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002e1b8  nop
0x18002e1b9  mov     rcx, [rsp+23A8h+var_2330]
0x18002e1be  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e1c2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e1c7  nop
0x18002e1c8  mov     rcx, [rsp+23A8h+var_2328]
0x18002e1d0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e1d4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e1d9  nop
0x18002e1da  mov     rcx, [rsp+23A8h+var_2320]
0x18002e1e2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e1e6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e1eb  nop
0x18002e1ec  mov     rcx, [rsp+23A8h+var_2318]
0x18002e1f4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e1f8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e1fd  nop
0x18002e1fe  mov     rcx, [rsp+23A8h+var_2348]
0x18002e203  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e207  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e20c  nop
0x18002e20d  mov     rcx, [rsp+23A8h+var_2340]
0x18002e212  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e216  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e21b  nop
0x18002e21c  mov     rcx, [rsp+23A8h+var_2338]
0x18002e221  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e225  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e22a  nop
0x18002e22b  mov     rcx, [rsp+23A8h+var_2358]
0x18002e230  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e234  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e239  nop
0x18002e23a  mov     rcx, [rsp+23A8h+var_2310]
0x18002e242  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e246  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e24b  nop
0x18002e24c  mov     rcx, [rsp+23A8h+var_2308]
0x18002e254  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e258  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e25d  nop
0x18002e25e  jmp     loc_18002EFB8
0x18002e263  mov     rbx, [rsp+23A8h+var_22B0]
0x18002e26b  test    rbx, rbx
0x18002e26e  jnz     loc_18002E334
0x18002e274  mov     [rsp+23A8h+var_2350], 80048020h
0x18002e27c  lea     rcx, [rsp+23A8h+var_22A8]
0x18002e284  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002e289  nop
0x18002e28a  mov     rcx, [rsp+23A8h+var_2330]
0x18002e28f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e293  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e298  nop
0x18002e299  mov     rcx, [rsp+23A8h+var_2328]
0x18002e2a1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e2a5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e2aa  nop
0x18002e2ab  mov     rcx, [rsp+23A8h+var_2320]
0x18002e2b3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e2b7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e2bc  nop
0x18002e2bd  mov     rcx, [rsp+23A8h+var_2318]
0x18002e2c5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e2c9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e2ce  nop
0x18002e2cf  mov     rcx, [rsp+23A8h+var_2348]
0x18002e2d4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e2d8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e2dd  nop
0x18002e2de  mov     rcx, [rsp+23A8h+var_2340]
0x18002e2e3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e2e7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e2ec  nop
0x18002e2ed  mov     rcx, [rsp+23A8h+var_2338]
0x18002e2f2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e2f6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e2fb  nop
0x18002e2fc  mov     rcx, [rsp+23A8h+var_2358]
0x18002e301  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e305  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e30a  nop
0x18002e30b  mov     rcx, [rsp+23A8h+var_2310]
0x18002e313  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e317  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e31c  nop
0x18002e31d  mov     rcx, [rsp+23A8h+var_2308]
0x18002e325  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e329  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e32e  nop
0x18002e32f  jmp     loc_18002EFB8
0x18002e334  lea     rax, [rbx+10h]
0x18002e338  mov     qword ptr [rsp+23A8h+cbNeeded], rax
0x18002e340  mov     [rsp+23A8h+var_22E8], dil
0x18002e348  lea     rcx, [rsp+23A8h+cbNeeded]
0x18002e350  call    ?TryLock@?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAAJXZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::TryLock(void)
0x18002e355  mov     [rsp+23A8h+var_2350], eax
0x18002e359  test    eax, eax
0x18002e35b  jns     loc_18002E427
0x18002e361  lea     rcx, [rsp+23A8h+cbNeeded]
0x18002e369  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18002e36e  nop
0x18002e36f  lea     rcx, [rsp+23A8h+var_22A8]
0x18002e377  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002e37c  nop
0x18002e37d  mov     rcx, [rsp+23A8h+var_2330]
0x18002e382  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e386  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e38b  nop
0x18002e38c  mov     rcx, [rsp+23A8h+var_2328]
0x18002e394  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e398  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e39d  nop
0x18002e39e  mov     rcx, [rsp+23A8h+var_2320]
0x18002e3a6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e3aa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e3af  nop
0x18002e3b0  mov     rcx, [rsp+23A8h+var_2318]
0x18002e3b8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e3bc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e3c1  nop
0x18002e3c2  mov     rcx, [rsp+23A8h+var_2348]
0x18002e3c7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e3cb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e3d0  nop
0x18002e3d1  mov     rcx, [rsp+23A8h+var_2340]
0x18002e3d6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e3da  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e3df  nop
0x18002e3e0  mov     rcx, [rsp+23A8h+var_2338]
0x18002e3e5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e3e9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e3ee  nop
0x18002e3ef  mov     rcx, [rsp+23A8h+var_2358]
0x18002e3f4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e3f8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e3fd  nop
0x18002e3fe  mov     rcx, [rsp+23A8h+var_2310]
0x18002e406  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e40a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e40f  nop
0x18002e410  mov     rcx, [rsp+23A8h+var_2308]
0x18002e418  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002e41c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002e421  nop
0x18002e422  jmp     loc_18002EFB8
0x18002e427  lea     r14, [rbx+40h]
0x18002e42b  mov     rbx, [r14]
0x18002e42e  test    rbx, rbx
0x18002e431  jnz     short loc_18002E46C
0x18002e433  lea     ecx, [rbx+28h]; Size
0x18002e436  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e43b  mov     rbx, rax
0x18002e43e  xor     eax, eax
0x18002e440  mov     [rbx+8], rax
0x18002e444  mov     [rbx+18h], r13d
0x18002e448  lea     rax, ??_7SmartWLIDHandle@@6B?$SmartObj@PEAX@@@; const SmartWLIDHandle::`vftable'{for `SmartObj<void *>'}
0x18002e44f  mov     [rbx], rax
0x18002e452  lea     rax, ??_7SmartWLIDHandle@@6BCRefCounted@@@; const SmartWLIDHandle::`vftable'{for `CRefCounted'}
0x18002e459  mov     [rbx+10h], rax
0x18002e45d  mov     [rbx+20h], rdi
0x18002e461  mov     rcx, r14
  ... truncated ...
```
