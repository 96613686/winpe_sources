# CWUApiModule::CWUApiModule(void)

- ea: `0x18007e21c`
- end: `0x18007e9b4`
- name: `??0CWUApiModule@@QEAA@XZ`
- size: `1944`
- prototype: `CWUApiModule *__fastcall(CWUApiModule *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001aa0`

## callees

- `0x18000588c`
- `0x1800072f8`
- `0x180007638`
- `0x18002ded8`
- `0x18003a110`
- `0x18003e860`
- `0x180075a30`
- `0x18007e21c`
- `0x180081a38`
- `0x180081adc`
- `0x18008d284`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007e2ae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007e3e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007e4d8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007e593`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007e2ae`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007e3e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007e4d8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18007e593`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18007e445`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18007e5f5`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18007e445`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18007e5f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e7fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007e7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e59d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e59d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007e77a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007e77a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18007e7c3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18007e7c3`

## string_xrefs

- `0x18007e6ed`: `C:\__w\1\s\src\Client\comapi\wuapimodule.cpp`
- `0x18007e754`: `C:\__w\1\s\src\Client\comapi\wuapimodule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
CWUApiModule *__fastcall CWUApiModule::CWUApiModule(CWUApiModule *this)
{
  __int64 v1; // rcx
  signed int LastError; // eax
  GUID ***v3; // rbx
  __int64 *v4; // rax
  signed int v5; // ebx
  __int64 v6; // rdx
  void *v7; // r8
  signed int v8; // eax
  int FreeThreadedMarshaler; // eax
  IUnknown *v10; // rax
  signed int v11; // ebx
  signed int v12; // eax
  signed int v13; // ebx
  __int64 v14; // rdx
  void *v15; // r8
  signed int v16; // eax
  int v17; // eax
  IUnknown *v18; // rax
  _WORD *v19; // rax
  _WORD *v20; // rdx
  unsigned __int64 v21; // r9
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  char *v25; // rcx
  __int16 v26; // ax
  _WORD *v27; // rax
  int v28; // eax
  const wchar_t *FileNameW; // rax
  int v30; // eax
  HANDLE CurrentProcess; // rdi
  int PackageFullNameFromProcess; // eax
  wchar_t *v33; // rbx
  int v34; // eax
  int v35; // eax
  int AppIdDescription; // eax
  wchar_t *v37; // rsi
  wchar_t *v38; // rdi
  int v39; // eax
  int v40; // eax
  int v41; // eax
  wchar_t *v43; // [rsp+28h] [rbp-E0h] BYREF
  wchar_t *v44; // [rsp+30h] [rbp-D8h] BYREF
  wchar_t *v45[4]; // [rsp+38h] [rbp-D0h] BYREF
  WCHAR Filename[512]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+490h] [rbp+388h]

  v45[2] = (wchar_t *)&_AtlModule;
  *(_OWORD *)&stru_1800EEEE8.DebugInfo = 0;
  *(_OWORD *)&stru_1800EEEE8.OwningThread = 0;
  stru_1800EEEE8.SpinCount = 0;
  qword_1800EEED8 = 0;
  qword_1800EEEE0 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  qword_1800EEF10 = 0;
  if ( InitializeCriticalSectionEx(&stru_1800EEEE8, 0, 0) )
    goto LABEL_6;
  LastError = GetLastError();
  v1 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v1 = (unsigned int)LastError;
  if ( (int)v1 >= 0 )
LABEL_6:
    LODWORD(qword_1800EEED8) = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  ATL::CAtlModule::m_libid = LIBID_WUApiLib;
  v3 = off_1800EE300;
  v4 = off_1800EE308;
  while ( v3 < (GUID ***)v4 )
  {
    if ( *v3 )
    {
      LOBYTE(v1) = 1;
      ((void (__fastcall *)(__int64))(*v3)[7])(v1);
      v4 = off_1800EE308;
    }
    ++v3;
  }
  qword_1800EEF20 = 0;
  _AtlModule = &CWUApiModule::`vftable'{for `ATL::CAtlDllModuleT<CWUApiModule>'};
  qword_1800EEF18 = &CWUApiModule::`vftable'{for `CModuleResHelper'};
  dword_1800EEF48 = 0;
  *(_OWORD *)&stru_1800EEF50.DebugInfo = 0;
  *(_OWORD *)&stru_1800EEF50.OwningThread = 0;
  stru_1800EEF50.SpinCount = 0;
  byte_1800EEF78 = 0;
  word_1800EEF38 = 0;
  ppunkMarshal = 0;
  qword_1800EEF90 = 0;
  qword_1800EEF98 = 0;
  qword_1800EEF88 = (__int64)&CSusArray<wchar_t *,CStringCollection::CSusArrayListItemOpsBstr>::`vftable';
  qword_1800EEF28 = (__int64)&ATL::CComObjectGlobal<CStringCollection>::`vftable'{for `CSusBaseAllocTag<1668505955>'};
  qword_1800EEF30 = (__int64)&CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'};
  qword_1800EEF40 = (__int64)&ATL::CComObjectGlobal<CStringCollection>::`vftable'{for `ATL::IDispatchImpl<IStringCollection,&_GUID const IID_IStringCollection,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
  dword_1800EEFA0 = 0;
  _InterlockedIncrement(&dword_1800EEF48);
  v5 = 0;
  if ( InitializeCriticalSectionEx(&stru_1800EEF50, 0, 0) )
    goto LABEL_17;
  v8 = GetLastError();
  v5 = (unsigned __int16)v8 | 0x80070000;
  if ( v8 <= 0 )
    v5 = v8;
  if ( v5 >= 0 )
  {
LABEL_17:
    byte_1800EEF78 = 1;
    dword_1800EEFA0 = v5;
    FreeThreadedMarshaler = SecurityCheck(-2147483647, v6, v7);
    if ( FreeThreadedMarshaler >= 0 )
    {
      v10 = (IUnknown *)(*(__int64 (__fastcall **)(__int64 *))(qword_1800EEF28 + 8))(&qword_1800EEF28);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v10, &ppunkMarshal);
    }
    dword_1800EEFA0 = FreeThreadedMarshaler;
  }
  else
  {
    dword_1800EEFA0 = v5;
  }
  _InterlockedAdd(&dword_1800EEF48, 0xFFFFFFFF);
  CWebProxy::CWebProxy((CWebProxy *)&qword_1800EEFA8);
  qword_1800EEFA8 = &ATL::CComObjectGlobal<CWebProxy>::`vftable'{for `CSusBaseAllocTag<1886871907>'};
  qword_1800EEFB0 = (__int64)&CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'};
  qword_1800EEFC0 = (__int64)&ATL::CComObjectGlobal<CWebProxy>::`vftable'{for `CUpdateLockdown'};
  qword_1800EEFD0 = (__int64)&ATL::CComObjectGlobal<CWebProxy>::`vftable'{for `IWebProxyInternal'};
  qword_1800EEFD8 = (__int64)&ATL::CComObject<CWebProxy>::`vftable'{for `ISaveWebProxy'};
  qword_1800EEFE0 = (__int64)&ATL::CComObjectGlobal<CWebProxy>::`vftable'{for `ATL::IDispatchImpl<IWebProxy,&_GUID const IID_IWebProxy,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
  dword_1800EF058 = 0;
  _InterlockedIncrement(&dword_1800EEFE8);
  v11 = 0;
  if ( InitializeCriticalSectionEx(&stru_1800EEFF0, 0, 0) )
    goto LABEL_25;
  v12 = GetLastError();
  v11 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 <= 0 )
    v11 = v12;
  if ( v11 >= 0 )
  {
LABEL_25:
    byte_1800EF018 = 1;
    dword_1800EF058 = v11;
    dword_1800EF058 = CWebProxy::FinalConstruct((CWebProxy *)&qword_1800EEFA8);
  }
  else
  {
    dword_1800EF058 = v11;
  }
  _InterlockedAdd(&dword_1800EEFE8, 0xFFFFFFFF);
  CUpdateSession::CUpdateSession((CUpdateSession *)&qword_1800EF060);
  qword_1800EF060 = (__int64)&ATL::CComObjectGlobal<CUpdateSession>::`vftable'{for `CSusBaseAllocTag<7561571>'};
  qword_1800EF068 = (__int64)&CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'};
  qword_1800EF078 = (__int64)&ATL::CComObjectGlobal<CUpdateSession>::`vftable'{for `CUpdateLockdown'};
  qword_1800EF088 = (__int64)&ATL::CComObjectGlobal<CUpdateSession>::`vftable'{for `IUpdateInternalConfiguration'};
  qword_1800EF090 = (__int64)&ATL::CComObjectGlobal<CUpdateSession>::`vftable'{for `ATL::IDispatchImpl<IUpdateSession3,&_GUID const IID_IUpdateSession3,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'};
  dword_1800EF1C0 = 0;
  _InterlockedIncrement(&dword_1800EF098);
  v13 = 0;
  if ( InitializeCriticalSectionEx(&stru_1800EF0A0, 0, 0) )
    goto LABEL_31;
  v16 = GetLastError();
  v13 = (unsigned __int16)v16 | 0x80070000;
  if ( v16 <= 0 )
    v13 = v16;
  if ( v13 >= 0 )
  {
LABEL_31:
    byte_1800EF0C8 = 1;
    dword_1800EF1C0 = v13;
    v17 = SecurityCheck(-2147483646, v14, v15);
    if ( v17 >= 0 )
    {
      v18 = (IUnknown *)(*(__int64 (__fastcall **)(__int64 *))(qword_1800EF060 + 8))(&qword_1800EF060);
      v17 = CoCreateFreeThreadedMarshaler(v18, &qword_1800EF0D0);
    }
    dword_1800EF1C0 = v17;
  }
  else
  {
    dword_1800EF1C0 = v13;
  }
  _InterlockedAdd(&dword_1800EF098, 0xFFFFFFFF);
  Uuid = GUID_NULL;
  qword_1800EF1E8 = 0;
  xmmword_1800EF1F0 = 0;
  pOptionalEntropy = 0;
  pOptionalEntropy.pbData = (BYTE *)&Uuid;
  pOptionalEntropy.cbData = 16;
  word_1800EEF38 = -1;
  (*(void (__fastcall **)(__int64 *, __int64 *))(qword_1800EEFE0 + 80))(&qword_1800EEFE0, &qword_1800EEF40);
  word_1800EEFB8 = -1;
  (*(void (__fastcall **)(__int64 *, __int64 *))(qword_1800EF090 + 88))(&qword_1800EF090, &qword_1800EEFE0);
  word_1800EF070 = -1;
  if ( *((_QWORD *)&xmmword_1800EF1F0 + 1) )
  {
    SusFree(*((void **)&xmmword_1800EF1F0 + 1));
    *((_QWORD *)&xmmword_1800EF1F0 + 1) = 0;
  }
  v19 = SafeSusAllocArray(0x20Cu, 2u);
  v20 = v19;
  *((_QWORD *)&xmmword_1800EF1F0 + 1) = v19;
  v21 = v19 == 0 ? 0x8007000E : 0;
  v22 = retaddr;
  if ( !v19 )
  {
    v23 = 34;
LABEL_49:
    wil::details::in1diag3::_Log_Hr(
      v22,
      (void *)v23,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\wuapimodule.cpp",
      (const char *)v21,
      (int)v43);
    return (CWUApiModule *)&_AtlModule;
  }
  v24 = 524;
  v25 = (char *)((char *)L"<<PROCESS>>: " - (char *)v19);
  do
  {
    if ( v24 == -2147483122 )
      break;
    v26 = *(_WORD *)((char *)v20 + (_QWORD)v25);
    if ( !v26 )
      break;
    *v20++ = v26;
    --v24;
  }
  while ( v24 );
  v27 = v20 - 1;
  if ( v24 )
    v27 = v20;
  *v27 = 0;
  if ( !v24 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\wuapimodule.cpp",
      (const char *)0x8007007ALL,
      (int)v43);
  if ( GetModuleFileNameW(0, Filename, 0x1FFu) )
  {
    FileNameW = PathFindFileNameW(Filename);
    v30 = StringCchCatW(*((wchar_t **)&xmmword_1800EF1F0 + 1), 0x20Cu, FileNameW);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\wuapimodule.cpp",
        (const char *)(unsigned int)v30,
        (int)v43);
    v43 = 0;
    CurrentProcess = GetCurrentProcess();
    PackageFullNameFromProcess = GetPackageFullNameFromProcess(CurrentProcess, &v43);
    v33 = v43;
    if ( PackageFullNameFromProcess >= 0 )
    {
      if ( !v43 )
        goto LABEL_61;
      if ( *v43 )
      {
        v34 = StringCchCatW(*((wchar_t **)&xmmword_1800EF1F0 + 1), 0x20Cu, L": ");
        if ( v34 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x42,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\wuapimodule.cpp",
            (const char *)(unsigned int)v34,
            (int)v43);
        v35 = StringCchCatW(*((wchar_t **)&xmmword_1800EF1F0 + 1), 0x20Cu, v33);
        if ( v35 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x43,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\wuapimodule.cpp",
            (const char *)(unsigned int)v35,
            (int)v43);
      }
    }
    if ( v33 && *v33 )
    {
LABEL_74:
      if ( v33 )
        SusFree(v33);
      return (CWUApiModule *)&_AtlModule;
    }
LABEL_61:
    v44 = 0;
    v45[0] = 0;
    AppIdDescription = GetAppIdDescription(CurrentProcess, &v44, v45);
    v37 = v44;
    v38 = v45[0];
    if ( AppIdDescription >= 0 )
    {
      v39 = StringCchCatW(*((wchar_t **)&xmmword_1800EF1F0 + 1), 0x20Cu, L":");
      if ( v39 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\wuapimodule.cpp",
          (const char *)(unsigned int)v39,
          (int)v43);
      if ( !v38 || !*v38 )
      {
        v40 = StringCchCatW(*((wchar_t **)&xmmword_1800EF1F0 + 1), 0x20Cu, v37);
        if ( v40 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x53,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\wuapimodule.cpp",
            (const char *)(unsigned int)v40,
            (int)v43);
      }
      v41 = StringCchCatW(*((wchar_t **)&xmmword_1800EF1F0 + 1), 0x20Cu, v38);
      if ( v41 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\wuapimodule.cpp",
          (const char *)(unsigned int)v41,
          (int)v43);
    }
    if ( v38 )
      SusFree(v38);
    if ( v37 )
      SusFree(v37);
    goto LABEL_74;
  }
  v28 = StringCchCatW(*((wchar_t **)&xmmword_1800EF1F0 + 1), 0x20Cu, L"<unknown process name>");
  v22 = retaddr;
  if ( v28 < 0 )
  {
    v21 = (unsigned int)v28;
    v23 = 48;
    goto LABEL_49;
  }
  return (CWUApiModule *)&_AtlModule;
}

```

## disassembly

```asm
0x18007e21c  mov     rax, rsp
0x18007e21f  mov     [rax+8], rbx
0x18007e223  mov     [rax+10h], rsi
0x18007e227  mov     [rax+18h], rdi
0x18007e22b  push    rbp
0x18007e22c  push    r12
0x18007e22e  push    r13
0x18007e230  push    r14
0x18007e232  push    r15
0x18007e234  lea     rbp, [rax-388h]
0x18007e23b  sub     rsp, 460h
0x18007e242  mov     rax, cs:__security_cookie
0x18007e249  xor     rax, rsp
0x18007e24c  mov     [rbp+380h+var_30], rax
0x18007e253  mov     rax, [rsp+480h+var_440]
0x18007e258  mov     [rsp+480h+var_440], rax
0x18007e25d  lea     r13, ?_AtlModule@@3VCWUApiModule@@A; CWUApiModule _AtlModule
0x18007e264  mov     [rsp+480h+var_440], r13
0x18007e269  xorps   xmm0, xmm0
0x18007e26c  xor     eax, eax
0x18007e26e  movups  xmmword ptr cs:stru_1800EEEE8.DebugInfo, xmm0
0x18007e275  movups  xmmword ptr cs:stru_1800EEEE8.OwningThread, xmm0
0x18007e27c  mov     cs:stru_1800EEEE8.SpinCount, rax
0x18007e283  xor     r15d, r15d
0x18007e286  mov     cs:qword_1800EEED8, r15
0x18007e28d  mov     cs:qword_1800EEEE0, r15
0x18007e294  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, r13; ATL::CAtlModule * ATL::_pAtlModule
0x18007e29b  mov     cs:qword_1800EEF10, r15
0x18007e2a2  xor     r8d, r8d; Flags
0x18007e2a5  xor     edx, edx; dwSpinCount
0x18007e2a7  lea     rcx, stru_1800EEEE8; lpCriticalSection
0x18007e2ae  call    cs:__imp_InitializeCriticalSectionEx
0x18007e2b4  mov     edi, 80070000h
0x18007e2b9  test    eax, eax
0x18007e2bb  jnz     short loc_18007E2DA
0x18007e2bd  call    cs:__imp_GetLastError
0x18007e2c3  movzx   ecx, ax
0x18007e2c6  or      ecx, edi
0x18007e2c8  test    eax, eax
0x18007e2ca  cmovle  ecx, eax
0x18007e2cd  test    ecx, ecx
0x18007e2cf  jns     short loc_18007E2DA
0x18007e2d1  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x18007e2d8  jmp     short loc_18007E2E4
0x18007e2da  mov     dword ptr cs:qword_1800EEED8, 38h ; '8'
0x18007e2e4  movups  xmm0, xmmword ptr cs:LIBID_WUApiLib.Data1
0x18007e2eb  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x18007e2f3  mov     rbx, cs:off_1800EE300
0x18007e2fa  mov     rax, cs:off_1800EE308
0x18007e301  jmp     short loc_18007E321
0x18007e303  mov     rdx, [rbx]
0x18007e306  test    rdx, rdx
0x18007e309  jz      short loc_18007E31D
0x18007e30b  mov     cl, 1
0x18007e30d  mov     rax, [rdx+38h]
0x18007e311  call    _guard_dispatch_icall
0x18007e316  mov     rax, cs:off_1800EE308
0x18007e31d  add     rbx, 8
0x18007e321  cmp     rbx, rax
0x18007e324  jb      short loc_18007E303
0x18007e326  mov     cs:qword_1800EEF20, r15
0x18007e32d  lea     rax, ??_7CWUApiModule@@6B?$CAtlDllModuleT@VCWUApiModule@@@ATL@@@; const CWUApiModule::`vftable'{for `ATL::CAtlDllModuleT<CWUApiModule>'}
0x18007e334  mov     cs:?_AtlModule@@3VCWUApiModule@@A, rax; CWUApiModule _AtlModule
0x18007e33b  lea     rax, ??_7CWUApiModule@@6BCModuleResHelper@@@; const CWUApiModule::`vftable'{for `CModuleResHelper'}
0x18007e342  mov     cs:qword_1800EEF18, rax
0x18007e349  mov     cs:dword_1800EEF48, r15d
0x18007e350  xorps   xmm0, xmm0
0x18007e353  xor     eax, eax
0x18007e355  movups  xmmword ptr cs:stru_1800EEF50.DebugInfo, xmm0
0x18007e35c  movups  xmmword ptr cs:stru_1800EEF50.OwningThread, xmm0
0x18007e363  mov     cs:stru_1800EEF50.SpinCount, rax
0x18007e36a  mov     cs:byte_1800EEF78, r15b
0x18007e371  mov     cs:word_1800EEF38, r15w
0x18007e379  mov     cs:ppunkMarshal, r15
0x18007e380  mov     cs:qword_1800EEF90, r15
0x18007e387  mov     cs:qword_1800EEF98, r15
0x18007e38e  lea     rax, ??_7?$CSusArray@PEA_WVCSusArrayListItemOpsBstr@CStringCollection@@@@6B@; const CSusArray<wchar_t *,CStringCollection::CSusArrayListItemOpsBstr>::`vftable'
0x18007e395  mov     cs:qword_1800EEF88, rax
0x18007e39c  lea     rax, ??_7?$CComObjectGlobal@VCStringCollection@@@ATL@@6B?$CSusBaseAllocTag@$0GDHDGBGD@@@@; const ATL::CComObjectGlobal<CStringCollection>::`vftable'{for `CSusBaseAllocTag<1668505955>'}
0x18007e3a3  mov     cs:qword_1800EEF28, rax
0x18007e3aa  lea     rax, ??_7?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@6BCSupportReadOnly@@@; const CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'}
0x18007e3b1  mov     cs:qword_1800EEF30, rax
0x18007e3b8  lea     rax, ??_7?$CComObjectGlobal@VCStringCollection@@@ATL@@6B?$IDispatchImpl@UIStringCollection@@$1?IID_IStringCollection@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObjectGlobal<CStringCollection>::`vftable'{for `ATL::IDispatchImpl<IStringCollection,&_GUID const IID_IStringCollection,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x18007e3bf  mov     cs:qword_1800EEF40, rax
0x18007e3c6  mov     cs:dword_1800EEFA0, r15d
0x18007e3cd  lock inc cs:dword_1800EEF48
0x18007e3d4  mov     ebx, r15d
0x18007e3d7  xor     r8d, r8d; Flags
0x18007e3da  xor     edx, edx; dwSpinCount
0x18007e3dc  lea     rcx, stru_1800EEF50; lpCriticalSection
0x18007e3e3  call    cs:__imp_InitializeCriticalSectionEx
0x18007e3e9  test    eax, eax
0x18007e3eb  jnz     short loc_18007E409
0x18007e3ed  call    cs:__imp_GetLastError
0x18007e3f3  movzx   ebx, ax
0x18007e3f6  or      ebx, edi
0x18007e3f8  test    eax, eax
0x18007e3fa  cmovle  ebx, eax
0x18007e3fd  test    ebx, ebx
0x18007e3ff  jns     short loc_18007E409
0x18007e401  mov     cs:dword_1800EEFA0, ebx
0x18007e407  jmp     short loc_18007E451
0x18007e409  mov     cs:byte_1800EEF78, 1
0x18007e410  mov     cs:dword_1800EEFA0, ebx
0x18007e416  mov     ecx, 80000001h; unsigned int
0x18007e41b  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18007e420  test    eax, eax
0x18007e422  js      short loc_18007E44B
0x18007e424  mov     rax, cs:qword_1800EEF28
0x18007e42b  lea     rcx, qword_1800EEF28
0x18007e432  mov     rax, [rax+8]
0x18007e436  call    _guard_dispatch_icall
0x18007e43b  mov     rcx, rax; punkOuter
0x18007e43e  lea     rdx, ppunkMarshal; ppunkMarshal
0x18007e445  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18007e44b  mov     cs:dword_1800EEFA0, eax
0x18007e451  or      esi, 0FFFFFFFFh
0x18007e454  lock add cs:dword_1800EEF48, esi
0x18007e45b  lea     rcx, qword_1800EEFA8; this
0x18007e462  call    ??0CWebProxy@@QEAA@XZ; CWebProxy::CWebProxy(void)
0x18007e467  lea     rax, ??_7?$CComObjectGlobal@VCWebProxy@@@ATL@@6B?$CSusBaseAllocTag@$0HAHHGBGD@@@@; const ATL::CComObjectGlobal<CWebProxy>::`vftable'{for `CSusBaseAllocTag<1886871907>'}
0x18007e46e  mov     cs:qword_1800EEFA8, rax
0x18007e475  lea     rax, ??_7?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@6BCSupportReadOnly@@@; const CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'}
0x18007e47c  mov     cs:qword_1800EEFB0, rax
0x18007e483  lea     rax, ??_7?$CComObjectGlobal@VCWebProxy@@@ATL@@6BCUpdateLockdown@@@; const ATL::CComObjectGlobal<CWebProxy>::`vftable'{for `CUpdateLockdown'}
0x18007e48a  mov     cs:qword_1800EEFC0, rax
0x18007e491  lea     rax, ??_7?$CComObjectGlobal@VCWebProxy@@@ATL@@6BIWebProxyInternal@@@; const ATL::CComObjectGlobal<CWebProxy>::`vftable'{for `IWebProxyInternal'}
0x18007e498  mov     cs:qword_1800EEFD0, rax
0x18007e49f  lea     rax, ??_7?$CComObject@VCWebProxy@@@ATL@@6BISaveWebProxy@@@; const ATL::CComObject<CWebProxy>::`vftable'{for `ISaveWebProxy'}
0x18007e4a6  mov     cs:qword_1800EEFD8, rax
0x18007e4ad  lea     rax, ??_7?$CComObjectGlobal@VCWebProxy@@@ATL@@6B?$IDispatchImpl@UIWebProxy@@$1?IID_IWebProxy@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObjectGlobal<CWebProxy>::`vftable'{for `ATL::IDispatchImpl<IWebProxy,&_GUID const IID_IWebProxy,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x18007e4b4  mov     cs:qword_1800EEFE0, rax
0x18007e4bb  mov     cs:dword_1800EF058, r15d
0x18007e4c2  lock inc cs:dword_1800EEFE8
0x18007e4c9  mov     ebx, r15d
0x18007e4cc  xor     r8d, r8d; Flags
0x18007e4cf  xor     edx, edx; dwSpinCount
0x18007e4d1  lea     rcx, stru_1800EEFF0; lpCriticalSection
0x18007e4d8  call    cs:__imp_InitializeCriticalSectionEx
0x18007e4de  test    eax, eax
0x18007e4e0  jnz     short loc_18007E4FE
0x18007e4e2  call    cs:__imp_GetLastError
0x18007e4e8  movzx   ebx, ax
0x18007e4eb  or      ebx, edi
0x18007e4ed  test    eax, eax
0x18007e4ef  cmovle  ebx, eax
0x18007e4f2  test    ebx, ebx
0x18007e4f4  jns     short loc_18007E4FE
0x18007e4f6  mov     cs:dword_1800EF058, ebx
0x18007e4fc  jmp     short loc_18007E51D
0x18007e4fe  mov     cs:byte_1800EF018, 1
0x18007e505  mov     cs:dword_1800EF058, ebx
0x18007e50b  lea     rcx, qword_1800EEFA8; this
0x18007e512  call    ?FinalConstruct@CWebProxy@@QEAAJXZ; CWebProxy::FinalConstruct(void)
0x18007e517  mov     cs:dword_1800EF058, eax
0x18007e51d  lock add cs:dword_1800EEFE8, esi
0x18007e524  lea     rcx, qword_1800EF060; this
0x18007e52b  call    ??0CUpdateSession@@QEAA@XZ; CUpdateSession::CUpdateSession(void)
0x18007e530  lea     rax, ??_7?$CComObjectGlobal@VCUpdateSession@@@ATL@@6B?$CSusBaseAllocTag@$0HDGBGD@@@@; const ATL::CComObjectGlobal<CUpdateSession>::`vftable'{for `CSusBaseAllocTag<7561571>'}
0x18007e537  mov     cs:qword_1800EF060, rax
0x18007e53e  lea     rax, ??_7?$CComObjectSessionCached@VCSearchResult@@VCUpdateCollection@@@@6BCSupportReadOnly@@@; const CComObjectSessionCached<CSearchResult,CUpdateCollection>::`vftable'{for `CSupportReadOnly'}
0x18007e545  mov     cs:qword_1800EF068, rax
0x18007e54c  lea     rax, ??_7?$CComObjectGlobal@VCUpdateSession@@@ATL@@6BCUpdateLockdown@@@; const ATL::CComObjectGlobal<CUpdateSession>::`vftable'{for `CUpdateLockdown'}
0x18007e553  mov     cs:qword_1800EF078, rax
0x18007e55a  lea     rax, ??_7?$CComObjectGlobal@VCUpdateSession@@@ATL@@6BIUpdateInternalConfiguration@@@; const ATL::CComObjectGlobal<CUpdateSession>::`vftable'{for `IUpdateInternalConfiguration'}
0x18007e561  mov     cs:qword_1800EF088, rax
0x18007e568  lea     rax, ??_7?$CComObjectGlobal@VCUpdateSession@@@ATL@@6B?$IDispatchImpl@UIUpdateSession3@@$1?IID_IUpdateSession3@@3U_GUID@@B$1?LIBID_WUApiLib@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObjectGlobal<CUpdateSession>::`vftable'{for `ATL::IDispatchImpl<IUpdateSession3,&_GUID const IID_IUpdateSession3,&_GUID const LIBID_WUApiLib,2,0,ATL::CComTypeInfoHolder>'}
0x18007e56f  mov     cs:qword_1800EF090, rax
0x18007e576  mov     cs:dword_1800EF1C0, r15d
0x18007e57d  lock inc cs:dword_1800EF098
0x18007e584  mov     ebx, r15d
0x18007e587  xor     r8d, r8d; Flags
0x18007e58a  xor     edx, edx; dwSpinCount
0x18007e58c  lea     rcx, stru_1800EF0A0; lpCriticalSection
0x18007e593  call    cs:__imp_InitializeCriticalSectionEx
0x18007e599  test    eax, eax
0x18007e59b  jnz     short loc_18007E5B9
0x18007e59d  call    cs:__imp_GetLastError
0x18007e5a3  movzx   ebx, ax
0x18007e5a6  or      ebx, edi
0x18007e5a8  test    eax, eax
0x18007e5aa  cmovle  ebx, eax
0x18007e5ad  test    ebx, ebx
0x18007e5af  jns     short loc_18007E5B9
0x18007e5b1  mov     cs:dword_1800EF1C0, ebx
0x18007e5b7  jmp     short loc_18007E601
0x18007e5b9  mov     cs:byte_1800EF0C8, 1
0x18007e5c0  mov     cs:dword_1800EF1C0, ebx
0x18007e5c6  mov     ecx, 80000002h; unsigned int
0x18007e5cb  call    ?SecurityCheck@@YAJK@Z; SecurityCheck(ulong)
0x18007e5d0  test    eax, eax
0x18007e5d2  js      short loc_18007E5FB
0x18007e5d4  mov     rax, cs:qword_1800EF060
0x18007e5db  lea     rcx, qword_1800EF060
0x18007e5e2  mov     rax, [rax+8]
0x18007e5e6  call    _guard_dispatch_icall
0x18007e5eb  mov     rcx, rax; punkOuter
0x18007e5ee  lea     rdx, qword_1800EF0D0; ppunkMarshal
0x18007e5f5  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18007e5fb  mov     cs:dword_1800EF1C0, eax
0x18007e601  lock add cs:dword_1800EF098, esi
0x18007e608  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007e60f  movdqu  xmmword ptr cs:Uuid.Data1, xmm0
0x18007e617  mov     cs:qword_1800EF1E8, r15
0x18007e61e  xorps   xmm0, xmm0
0x18007e621  movdqa  cs:xmmword_1800EF1F0, xmm0
0x18007e629  movups  xmmword ptr cs:pOptionalEntropy.cbData, xmm0
0x18007e630  lea     rax, Uuid
0x18007e637  mov     cs:pOptionalEntropy.pbData, rax
0x18007e63e  mov     cs:pOptionalEntropy.cbData, 10h
0x18007e648  mov     cs:word_1800EEF38, si
0x18007e64f  mov     rax, cs:qword_1800EEFE0
0x18007e656  lea     rdx, qword_1800EEF40
0x18007e65d  lea     rcx, qword_1800EEFE0
0x18007e664  mov     rax, [rax+50h]
0x18007e668  call    _guard_dispatch_icall
0x18007e66d  mov     cs:word_1800EEFB8, si
0x18007e674  mov     rax, cs:qword_1800EF090
0x18007e67b  lea     rdx, qword_1800EEFE0
0x18007e682  lea     rcx, qword_1800EF090
0x18007e689  mov     rax, [rax+58h]
0x18007e68d  call    _guard_dispatch_icall
0x18007e692  mov     cs:word_1800EF070, si
0x18007e699  mov     rcx, qword ptr cs:xmmword_1800EF1F0+8; lpMem
0x18007e6a0  test    rcx, rcx
0x18007e6a3  jz      short loc_18007E6B1
0x18007e6a5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18007e6aa  mov     qword ptr cs:xmmword_1800EF1F0+8, r15
0x18007e6b1  mov     edx, 2; unsigned __int64
0x18007e6b6  mov     r12d, 20Ch
0x18007e6bc  mov     ecx, r12d; unsigned __int64
0x18007e6bf  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18007e6c4  mov     rdx, rax
0x18007e6c7  mov     qword ptr cs:xmmword_1800EF1F0+8, rax
0x18007e6ce  mov     rcx, rax
0x18007e6d1  neg     rcx
0x18007e6d4  sbb     r9d, r9d
0x18007e6d7  not     r9d
0x18007e6da  and     r9d, 8007000Eh
0x18007e6e1  mov     rcx, [rbp+388h]
0x18007e6e8  test    rax, rax
0x18007e6eb  jnz     short loc_18007E6FC
0x18007e6ed  lea     r8, aCW1SSrcClientC_23; "C:\\__w\\1\\s\\src\\Client\\comapi\\wua"...
0x18007e6f4  lea     edx, [rax+22h]
0x18007e6f7  jmp     loc_18007E7B4
0x18007e6fc  mov     r8, r12
0x18007e6ff  lea     rcx, aProcess; "<<PROCESS>>: "
0x18007e706  sub     rcx, rax
0x18007e709  lea     rax, [r8+7FFFFDF2h]
0x18007e710  test    rax, rax
0x18007e713  jz      short loc_18007E72B
0x18007e715  movzx   eax, word ptr [rcx+rdx]
0x18007e719  test    ax, ax
0x18007e71c  jz      short loc_18007E72B
0x18007e71e  mov     [rdx], ax
0x18007e721  add     rdx, 2
0x18007e725  sub     r8, 1
0x18007e729  jnz     short loc_18007E709
0x18007e72b  lea     rax, [rdx-2]
0x18007e72f  test    r8, r8
0x18007e732  cmovnz  rax, rdx
0x18007e736  mov     [rax], r15w
0x18007e73a  mov     rax, r8
0x18007e73d  neg     rax
0x18007e740  sbb     r9d, r9d
0x18007e743  not     r9d
0x18007e746  and     r9d, 8007007Ah; char *
0x18007e74d  mov     rcx, [rbp+388h]; this
0x18007e754  lea     r14, aCW1SSrcClientC_23; "C:\\__w\\1\\s\\src\\Client\\comapi\\wua"...
0x18007e75b  test    r8, r8
0x18007e75e  jnz     short loc_18007E76D
0x18007e760  mov     r8, r14; unsigned int
0x18007e763  mov     edx, 26h ; '&'; void *
0x18007e768  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007e76d  mov     r8d, 1FFh; nSize
0x18007e773  lea     rdx, [rsp+480h+Filename]; lpFilename
0x18007e778  xor     ecx, ecx; hModule
0x18007e77a  call    cs:__imp_GetModuleFileNameW
0x18007e780  test    eax, eax
0x18007e782  jnz     short loc_18007E7BE
0x18007e784  lea     r8, aUnknownProcess; "<unknown process name>"
0x18007e78b  mov     rdx, r12; unsigned __int64
0x18007e78e  mov     rcx, qword ptr cs:xmmword_1800EF1F0+8; wchar_t *
0x18007e795  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18007e79a  mov     rcx, [rbp+388h]; this
0x18007e7a1  test    eax, eax
0x18007e7a3  jns     loc_18007E981
0x18007e7a9  mov     r9d, eax; char *
0x18007e7ac  mov     r8, r14; unsigned int
0x18007e7af  mov     edx, 30h ; '0'; void *
0x18007e7b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007e7b9  jmp     loc_18007E981
0x18007e7be  lea     rcx, [rsp+480h+Filename]; pszPath
0x18007e7c3  call    cs:__imp_PathFindFileNameW
0x18007e7c9  mov     r8, rax; wchar_t *
0x18007e7cc  mov     rdx, r12; unsigned __int64
0x18007e7cf  mov     rcx, qword ptr cs:xmmword_1800EF1F0+8; wchar_t *
0x18007e7d6  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18007e7db  mov     rcx, [rbp+388h]; this
0x18007e7e2  test    eax, eax
  ... truncated ...
```
