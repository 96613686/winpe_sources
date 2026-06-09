# CUxpDllWrapper::Initialize(void)

- ea: `0x18003b964`
- end: `0x18003bc1a`
- name: `?Initialize@CUxpDllWrapper@@QEAAJXZ`
- size: `694`
- prototype: `__int64 __fastcall(CUxpDllWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039050`

## callees

- `0x180002da0`
- `0x18000a804`
- `0x18000c354`
- `0x18000cc9c`
- `0x18000e870`
- `0x180034730`
- `0x18003aec8`
- `0x18003af90`
- `0x18003b7f8`
- `0x18003b964`
- `0x18003bc20`
- `0x1800530e4`
- `0x180053890`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003bbb6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003bbb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bb0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bb25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bb3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bb0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bb25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003bb3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bae7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003bad9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003bad9`

## string_xrefs

- `0x18003ba3d`: `CUxpDllWrapper::Initialize`
- `0x18003ba5c`: `CUxpDllWrapper::Initialize`
- `0x18003baac`: `hr = GetWlidUxModulePath(wstrPath)`
- `0x18003bb34`: `WlidUxCreateObject`
- `0x18003bb5e`: `hr = CUxpDllWrapper::WlidUxInitProcess()`
- `0x18003bb77`: `CUxpDllWrapper::Initialize succeeded.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUxpDllWrapper::Initialize(CUxpDllWrapper *this)
{
  CUxpDllWrapper *v2; // rcx
  int v3; // eax
  int WlidUxModulePath; // eax
  const char *v5; // rcx
  unsigned int v6; // r8d
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  unsigned int v12; // ebx
  char *v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v16[4]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[24]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v18[3]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpLibFileName; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v20; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+98h] [rbp-68h]
  int v22; // [rsp+9Ch] [rbp-64h]
  int v23; // [rsp+A0h] [rbp-60h]
  __int16 v24; // [rsp+A8h] [rbp-58h]

  v15 = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v17,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
  v18[0] = &ATL::CFixedStringMgr::`vftable';
  v18[1] = &ATL::g_strmgr;
  v18[2] = &v20;
  v23 = -1;
  v21 = 0;
  v22 = 260;
  v20 = v18;
  v24 = 0;
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&lpLibFileName, v18);
  v18[0] = &ATL::CFixedStringT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,260>::`vftable';
  if ( *((int *)this + 2) > 0 )
    goto LABEL_27;
  if ( !g_fInitialized )
  {
    v3 = CUxpDllWrapper::InitializeIDCRL(v2);
    v15 = v3;
    if ( v3 < 0 )
    {
      Telemetry::IfFailExit(
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
        "CUxpDllWrapper::Initialize",
        0x22u,
        v3,
        "hr = InitializeIDCRL()");
      goto LABEL_21;
    }
    *((_DWORD *)this + 3) = 1;
  }
  v16[0] = "CUxpDllWrapper::Initialize";
  v16[1] = &v15;
  v16[2] = 0;
  v16[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
    "CUxpDllWrapper::Initialize",
    (const char *)0x27,
    0,
    (const unsigned __int16 *)v14);
  WlidUxModulePath = CUxpDllWrapper::GetWlidUxModulePath(&lpLibFileName);
  v15 = WlidUxModulePath;
  if ( WlidUxModulePath >= 0 )
  {
    LibraryW = LoadLibraryW(lpLibFileName);
    *(_QWORD *)this = LibraryW;
    if ( !LibraryW )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v15 = LastError;
      goto LABEL_20;
    }
    ProcAddress = GetProcAddress(LibraryW, "WlidUxInitProcess");
    *((_QWORD *)this + 7) = ProcAddress;
    if ( !ProcAddress
      || (v10 = GetProcAddress(*(HMODULE *)this, "WlidUxUninitProcess"), (*((_QWORD *)this + 8) = v10) == 0)
      || (v11 = GetProcAddress(*(HMODULE *)this, "WlidUxCreateObject"), (*((_QWORD *)this + 9) = v11) == 0) )
    {
      v15 = -2147187933;
      goto LABEL_20;
    }
    WlidUxModulePath = (*((__int64 (**)(void))this + 7))();
    v15 = WlidUxModulePath;
    if ( WlidUxModulePath >= 0 )
    {
      *((_DWORD *)this + 2) = 1;
      TracePrintW(
        5u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
        0x48u,
        L"CUxpDllWrapper::Initialize succeeded.");
      goto LABEL_20;
    }
    v5 = "hr = CUxpDllWrapper::WlidUxInitProcess()";
    v6 = 69;
  }
  else
  {
    v5 = "hr = GetWlidUxModulePath(wstrPath)";
    v6 = 41;
  }
  Telemetry::IfFailExit(
    "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
    "CUxpDllWrapper::Initialize",
    v6,
    WlidUxModulePath,
    v5);
LABEL_20:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v16);
LABEL_21:
  if ( !*((_DWORD *)this + 2) )
  {
    if ( *(_QWORD *)this )
    {
      FreeLibrary(*(HMODULE *)this);
      *(_QWORD *)this = 0;
    }
    if ( !*((_DWORD *)this + 2) && *((_DWORD *)this + 3) )
    {
      Uninitialize();
      *((_DWORD *)this + 3) = 0;
    }
  }
LABEL_27:
  v12 = v15;
  ATL::CFixedStringT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,260>::~CFixedStringT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,260>(v18);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v17);
  return v12;
}

```

## disassembly

```asm
0x18003b964  mov     [rsp-8+arg_8], rbx
0x18003b969  mov     [rsp-8+arg_10], rsi
0x18003b96e  push    rbp
0x18003b96f  lea     rbp, [rsp-1D0h]
0x18003b977  sub     rsp, 2D0h
0x18003b97e  mov     rax, cs:__security_cookie
0x18003b985  xor     rax, rsp
0x18003b988  mov     [rbp+1D0h+var_10], rax
0x18003b98f  mov     rbx, rcx
0x18003b992  mov     [rsp+2D0h+var_2A0], 0
0x18003b99a  lea     rdx, [rcx+10h]
0x18003b99e  lea     rcx, [rsp+2D0h+var_278]
0x18003b9a3  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18003b9a8  nop
0x18003b9a9  lea     rax, ??_7CFixedStringMgr@ATL@@6B@; const ATL::CFixedStringMgr::`vftable'
0x18003b9b0  mov     [rsp+2D0h+var_260], rax
0x18003b9b5  lea     rax, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18003b9bc  mov     [rsp+2D0h+var_258], rax
0x18003b9c1  lea     rax, [rbp+1D0h+var_240]
0x18003b9c5  mov     [rbp+1D0h+var_250], rax
0x18003b9c9  mov     [rbp+1D0h+var_230], 0FFFFFFFFh
0x18003b9d0  mov     [rbp+1D0h+var_238], 0
0x18003b9d7  mov     [rbp+1D0h+var_234], 104h
0x18003b9de  lea     rax, [rsp+2D0h+var_260]
0x18003b9e3  mov     [rbp+1D0h+var_240], rax
0x18003b9e7  xor     eax, eax
0x18003b9e9  mov     [rbp+1D0h+var_228], ax
0x18003b9ed  lea     rdx, [rsp+2D0h+var_260]
0x18003b9f2  lea     rcx, [rbp+1D0h+lpLibFileName]
0x18003b9f6  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18003b9fb  nop
0x18003b9fc  lea     rax, ??_7?$CFixedStringT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$0BAE@@ATL@@6B@; const ATL::CFixedStringT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,260>::`vftable'
0x18003ba03  mov     [rsp+2D0h+var_260], rax
0x18003ba08  cmp     dword ptr [rbx+8], 0
0x18003ba0c  jg      loc_18003BBDB
0x18003ba12  cmp     cs:?g_fInitialized@@3_NA, 0; bool g_fInitialized
0x18003ba19  jnz     short loc_18003BA5C
0x18003ba1b  call    ?InitializeIDCRL@CUxpDllWrapper@@IEAAJXZ; CUxpDllWrapper::InitializeIDCRL(void)
0x18003ba20  mov     [rsp+2D0h+var_2A0], eax
0x18003ba24  test    eax, eax
0x18003ba26  jns     short loc_18003BA55
0x18003ba28  lea     rcx, aHrInitializeid; "hr = InitializeIDCRL()"
0x18003ba2f  mov     [rsp+2D0h+var_2B0], rcx; char *
0x18003ba34  mov     r9d, eax; int
0x18003ba37  mov     r8d, 22h ; '"'; unsigned int
0x18003ba3d  lea     rdx, aCuxpdllwrapper_2; "CUxpDllWrapper::Initialize"
0x18003ba44  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003ba4b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003ba50  jmp     loc_18003BBA8
0x18003ba55  mov     dword ptr [rbx+0Ch], 1
0x18003ba5c  lea     rsi, aCuxpdllwrapper_2; "CUxpDllWrapper::Initialize"
0x18003ba63  mov     [rsp+2D0h+var_298], rsi
0x18003ba68  lea     rax, [rsp+2D0h+var_2A0]
0x18003ba6d  mov     [rsp+2D0h+var_290], rax
0x18003ba72  mov     [rsp+2D0h+var_288], 0
0x18003ba7b  mov     [rsp+2D0h+var_280], 0
0x18003ba84  xor     r9d, r9d; unsigned int
0x18003ba87  lea     r8d, [r9+27h]; char *
0x18003ba8b  mov     rdx, rsi; char *
0x18003ba8e  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003ba95  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003ba9a  nop
0x18003ba9b  lea     rcx, [rbp+1D0h+lpLibFileName]
0x18003ba9f  call    ?GetWlidUxModulePath@CUxpDllWrapper@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CUxpDllWrapper::GetWlidUxModulePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003baa4  mov     [rsp+2D0h+var_2A0], eax
0x18003baa8  test    eax, eax
0x18003baaa  jns     short loc_18003BAD5
0x18003baac  lea     rcx, aHrGetwliduxmod; "hr = GetWlidUxModulePath(wstrPath)"
0x18003bab3  mov     r8d, 29h ; ')'; unsigned int
0x18003bab9  mov     r9d, eax; int
0x18003babc  mov     [rsp+2D0h+var_2B0], rcx; char *
0x18003bac1  mov     rdx, rsi; char *
0x18003bac4  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003bacb  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003bad0  jmp     loc_18003BB9E
0x18003bad5  mov     rcx, [rbp+1D0h+lpLibFileName]; lpLibFileName
0x18003bad9  call    cs:__imp_LoadLibraryW
0x18003badf  mov     [rbx], rax
0x18003bae2  test    rax, rax
0x18003bae5  jnz     short loc_18003BB02
0x18003bae7  call    cs:__imp_GetLastError
0x18003baed  test    eax, eax
0x18003baef  jle     short loc_18003BAF9
0x18003baf1  movzx   eax, ax
0x18003baf4  or      eax, 80070000h
0x18003baf9  mov     [rsp+2D0h+var_2A0], eax
0x18003bafd  jmp     loc_18003BB9E
0x18003bb02  lea     rdx, aWliduxinitproc; "WlidUxInitProcess"
0x18003bb09  mov     rcx, rax; hModule
0x18003bb0c  call    cs:__imp_GetProcAddress
0x18003bb12  mov     [rbx+38h], rax
0x18003bb16  test    rax, rax
0x18003bb19  jz      short loc_18003BB96
0x18003bb1b  lea     rdx, aWliduxuninitpr; "WlidUxUninitProcess"
0x18003bb22  mov     rcx, [rbx]; hModule
0x18003bb25  call    cs:__imp_GetProcAddress
0x18003bb2b  mov     [rbx+40h], rax
0x18003bb2f  test    rax, rax
0x18003bb32  jz      short loc_18003BB96
0x18003bb34  lea     rdx, aWliduxcreateob; "WlidUxCreateObject"
0x18003bb3b  mov     rcx, [rbx]; hModule
0x18003bb3e  call    cs:__imp_GetProcAddress
0x18003bb44  mov     [rbx+48h], rax
0x18003bb48  test    rax, rax
0x18003bb4b  jz      short loc_18003BB96
0x18003bb4d  mov     rax, [rbx+38h]
0x18003bb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb56  mov     [rsp+2D0h+var_2A0], eax
0x18003bb5a  test    eax, eax
0x18003bb5c  jns     short loc_18003BB70
0x18003bb5e  lea     rcx, aHrCuxpdllwrapp; "hr = CUxpDllWrapper::WlidUxInitProcess("...
0x18003bb65  mov     r8d, 45h ; 'E'
0x18003bb6b  jmp     loc_18003BAB9
0x18003bb70  mov     dword ptr [rbx+8], 1
0x18003bb77  lea     r9, aCuxpdllwrapper; "CUxpDllWrapper::Initialize succeeded."
0x18003bb7e  mov     r8d, 48h ; 'H'; unsigned int
0x18003bb84  lea     rdx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003bb8b  lea     ecx, [r8-43h]; unsigned __int8
0x18003bb8f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003bb94  jmp     short loc_18003BB9E
0x18003bb96  mov     [rsp+2D0h+var_2A0], 80048323h
0x18003bb9e  lea     rcx, [rsp+2D0h+var_298]
0x18003bba3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003bba8  cmp     dword ptr [rbx+8], 0
0x18003bbac  jnz     short loc_18003BBDB
0x18003bbae  mov     rcx, [rbx]; hLibModule
0x18003bbb1  test    rcx, rcx
0x18003bbb4  jz      short loc_18003BBC3
0x18003bbb6  call    cs:__imp_FreeLibrary
0x18003bbbc  mov     qword ptr [rbx], 0
0x18003bbc3  cmp     dword ptr [rbx+8], 0
0x18003bbc7  jnz     short loc_18003BBDB
0x18003bbc9  cmp     dword ptr [rbx+0Ch], 0
0x18003bbcd  jz      short loc_18003BBDB
0x18003bbcf  call    Uninitialize
0x18003bbd4  mov     dword ptr [rbx+0Ch], 0
0x18003bbdb  mov     ebx, [rsp+2D0h+var_2A0]
0x18003bbdf  lea     rcx, [rsp+2D0h+var_260]
0x18003bbe4  call    ??1?$CFixedStringT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$0BAE@@ATL@@UEAA@XZ; ATL::CFixedStringT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,260>::~CFixedStringT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,260>(void)
0x18003bbe9  nop
0x18003bbea  lea     rcx, [rsp+2D0h+var_278]
0x18003bbef  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18003bbf4  mov     eax, ebx
0x18003bbf6  mov     rcx, [rbp+1D0h+var_10]
0x18003bbfd  xor     rcx, rsp; StackCookie
0x18003bc00  call    __security_check_cookie
0x18003bc05  lea     r11, [rsp+2D0h+var_s0]
0x18003bc0d  mov     rbx, [r11+18h]
0x18003bc11  mov     rsi, [r11+20h]
0x18003bc15  mov     rsp, r11
0x18003bc18  pop     rbp
0x18003bc19  retn
```
