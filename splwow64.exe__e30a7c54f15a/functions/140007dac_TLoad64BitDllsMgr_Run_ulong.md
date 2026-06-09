# TLoad64BitDllsMgr::Run(ulong)

- ea: `0x140007dac`
- end: `0x140008055`
- name: `?Run@TLoad64BitDllsMgr@@QEAAKK@Z`
- size: `681`
- prototype: `unsigned int __fastcall(TLoad64BitDllsMgr *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000cca0`

## callees

- `0x140007dac`
- `0x14000805c`
- `0x1400083f4`
- `0x1400085d8`
- `0x1400086e0`
- `0x1400112c8`
- `0x140016010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140007ffc`
- `KERNEL32!WaitForSingleObject` at `0x140007ffc`
- `KERNEL32!GetLastError` at `0x140008034`
- `KERNEL32!GetLastError` at `0x140008034`
- `KERNEL32!CloseHandle` at `0x140008010`
- `KERNEL32!CloseHandle` at `0x140008010`
- `KERNEL32!GetProcAddress` at `0x140007e2b`
- `KERNEL32!GetProcAddress` at `0x140007e52`
- `KERNEL32!GetProcAddress` at `0x140007e2b`
- `KERNEL32!GetProcAddress` at `0x140007e52`
- `KERNEL32!CreateEventW` at `0x140007dd7`
- `KERNEL32!CreateEventW` at `0x140007dd7`
- `KERNEL32!FreeLibrary` at `0x140007e77`
- `KERNEL32!FreeLibrary` at `0x140007e77`
- `KERNEL32!LoadLibraryExW` at `0x140007e0c`
- `KERNEL32!LoadLibraryExW` at `0x140007e0c`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140007f36`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140007f36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007f92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007f92`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000802c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000802c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007eb0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007eb0`

## string_xrefs

- `0x140007e88`: `TLoad64BitDllsMgr::Run`
- `0x140007ea0`: `TLoad64BitDllsMgr::Run`
- `0x140007fd5`: `TLoad64BitDllsMgr::Run`
- `0x140007e81`: `Failed to load PrintIsolationProxy.dll`
- `0x140007dff`: `PrintIsolationProxy.dll`
- `0x140007e48`: `DllCanUnloadNow`

## pseudocode

```c
__int64 __fastcall TLoad64BitDllsMgr::Run(TLoad64BitDllsMgr *this, unsigned int a2)
{
  HANDLE EventW; // rax
  char v5; // r14
  NCoreLibrary *v6; // rcx
  HMODULE Library; // rbx
  NCoreLibrary *v8; // rcx
  NCoreLibrary *v9; // rcx
  HRESULT v10; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v11; // rdi
  __int64 *v12; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v13; // rsi
  bool v14; // zf
  unsigned int started; // ebx
  TLoad64BitDllsMgr *v16; // rcx
  LPUNKNOWN pUnk; // [rsp+60h] [rbp+8h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 16) = EventW;
  if ( !EventW )
    return GetLastError();
  v5 = 0;
  if ( a2 <= 0x2000 )
  {
    Library = LoadLibraryExW(L"PrintIsolationProxy.dll", 0, 0x800u);
    if ( Library || (int)NCoreLibrary::GetLastErrorAsFailHR(v6) >= 0 )
    {
      sandbox::g_pfnCreate = (unsigned int (*)(int, struct IPrintSandbox **))GetProcAddress(Library, (LPCSTR)0x190);
      if ( sandbox::g_pfnCreate || (int)NCoreLibrary::GetLastErrorAsFailHR(v8) >= 0 )
      {
        sandbox::g_pfnDllCanUnloadNow = (int (*)(void))GetProcAddress(Library, "DllCanUnloadNow");
        if ( sandbox::g_pfnDllCanUnloadNow || (int)NCoreLibrary::GetLastErrorAsFailHR(v9) >= 0 )
        {
          SplWow64Telemetry::WriteDbgTraceInfo("TLoad64BitDllsMgr::Run", L"Registering isolation host");
          v10 = CoInitializeEx(0, 0);
          if ( v10 < 0 )
            goto LABEL_30;
          v11 = off_140021270;
          v5 = 1;
          v12 = off_140021278;
          v10 = 1;
          while ( v11 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v12 )
          {
            if ( v10 < 0 )
              goto LABEL_30;
            v13 = *v11;
            if ( *v11 )
            {
              v14 = *((_QWORD *)v13 + 2) == 0;
              pUnk = 0;
              if ( v14 )
              {
                v10 = 0;
              }
              else
              {
                v10 = (*((__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))v13 + 2))(
                        *((_QWORD *)v13 + 3),
                        &GUID_00000000_0000_0000_c000_000000000046,
                        &pUnk);
                if ( v10 >= 0 )
                  v10 = CoRegisterClassObject(*(const IID *const *)v13, pUnk, 4u, 1u, (LPDWORD)v13 + 10);
                if ( pUnk )
                  ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
                v12 = off_140021278;
              }
            }
            ++v11;
          }
          if ( v10 < 0 )
          {
LABEL_30:
            SplWow64Telemetry::WriteDbgTraceError(
              "TLoad64BitDllsMgr::Run",
              L"RegisterClassObjects failed: hr: 0x%x",
              (unsigned int)v10);
          }
          else
          {
            pUnk = 0;
            if ( CoCreateInstance(
                   &CLSID_GlobalOptions,
                   0,
                   1u,
                   &GUID_0000015b_0000_0000_c000_000000000046,
                   (LPVOID *)&pUnk) >= 0 )
              ((void (__fastcall *)(LPUNKNOWN, __int64, __int64))pUnk->lpVtbl[1].QueryInterface)(pUnk, 1, 1);
            if ( pUnk )
              ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
          }
          goto LABEL_31;
        }
      }
      if ( Library )
        FreeLibrary(Library);
    }
    SplWow64Telemetry::WriteDbgTraceError("TLoad64BitDllsMgr::Run", L"Failed to load PrintIsolationProxy.dll");
  }
LABEL_31:
  started = TLoad64BitDllsMgr::StartLdrRPCServer(this, a2);
  if ( !started )
  {
    WaitForSingleObject(*((HANDLE *)this + 16), 0xFFFFFFFF);
    started = TLoad64BitDllsMgr::StopLdrRPCServer(v16);
  }
  CloseHandle(*((HANDLE *)this + 16));
  if ( v5 )
  {
    if ( ATL::_pPerfUnRegFunc )
      ATL::_pPerfUnRegFunc();
    CoUninitialize();
  }
  return started;
}

```

## disassembly

```asm
0x140007dac  mov     [rsp+arg_8], rbx
0x140007db1  mov     [rsp+arg_10], rbp
0x140007db6  push    rsi
0x140007db7  push    rdi
0x140007db8  push    r13
0x140007dba  push    r14
0x140007dbc  push    r15
0x140007dbe  sub     rsp, 30h
0x140007dc2  xor     r9d, r9d; lpName
0x140007dc5  mov     r15d, edx
0x140007dc8  mov     rbp, rcx
0x140007dcb  xor     r8d, r8d; bInitialState
0x140007dce  xor     ecx, ecx; lpEventAttributes
0x140007dd0  lea     r13d, [r9+1]
0x140007dd4  mov     edx, r13d; bManualReset
0x140007dd7  call    cs:__imp_CreateEventW
0x140007ddd  mov     [rbp+80h], rax
0x140007de4  test    rax, rax
0x140007de7  jz      loc_140008034
0x140007ded  xor     r14b, r14b
0x140007df0  cmp     r15d, 2000h
0x140007df7  ja      loc_140007FE1
0x140007dfd  xor     edx, edx; hFile
0x140007dff  lea     rcx, aPrintisolation; "PrintIsolationProxy.dll"
0x140007e06  mov     r8d, 800h; dwFlags
0x140007e0c  call    cs:__imp_LoadLibraryExW
0x140007e12  mov     rbx, rax
0x140007e15  test    rax, rax
0x140007e18  jnz     short loc_140007E23
0x140007e1a  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x140007e1f  test    eax, eax
0x140007e21  js      short loc_140007E81
0x140007e23  mov     edx, 190h; lpProcName
0x140007e28  mov     rcx, rbx; hModule
0x140007e2b  call    cs:__imp_GetProcAddress
0x140007e31  mov     cs:?g_pfnCreate@sandbox@@3P6AKHPEAPEAUIPrintSandbox@@@ZEA, rax; ulong (*sandbox::g_pfnCreate)(int,IPrintSandbox * *)
0x140007e38  test    rax, rax
0x140007e3b  jnz     short loc_140007E48
0x140007e3d  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x140007e42  mov     edi, eax
0x140007e44  test    eax, eax
0x140007e46  js      short loc_140007E6F
0x140007e48  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x140007e4f  mov     rcx, rbx; hModule
0x140007e52  call    cs:__imp_GetProcAddress
0x140007e58  mov     cs:?g_pfnDllCanUnloadNow@sandbox@@3P6AJXZEA, rax; long (*sandbox::g_pfnDllCanUnloadNow)(void)
0x140007e5f  test    rax, rax
0x140007e62  jnz     short loc_140007E99
0x140007e64  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x140007e69  mov     edi, eax
0x140007e6b  test    eax, eax
0x140007e6d  jns     short loc_140007E99
0x140007e6f  test    rbx, rbx
0x140007e72  jz      short loc_140007E81
0x140007e74  mov     rcx, rbx; hLibModule
0x140007e77  call    cs:__imp_FreeLibrary
0x140007e7d  test    edi, edi
0x140007e7f  jns     short loc_140007E99
0x140007e81  lea     rdx, aFailedToLoadPr; "Failed to load PrintIsolationProxy.dll"
0x140007e88  lea     rcx, aTload64bitdlls_10; "TLoad64BitDllsMgr::Run"
0x140007e8f  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140007e94  jmp     loc_140007FE1
0x140007e99  lea     rdx, aRegisteringIso; "Registering isolation host"
0x140007ea0  lea     rcx, aTload64bitdlls_10; "TLoad64BitDllsMgr::Run"
0x140007ea7  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140007eac  xor     edx, edx; dwCoInit
0x140007eae  xor     ecx, ecx; pvReserved
0x140007eb0  call    cs:__imp_CoInitializeEx
0x140007eb6  mov     ebx, eax
0x140007eb8  test    eax, eax
0x140007eba  js      loc_140007FCB
0x140007ec0  mov     rdi, cs:off_140021270
0x140007ec7  mov     r14b, r13b
0x140007eca  mov     rax, cs:off_140021278
0x140007ed1  mov     ebx, r13d
0x140007ed4  jmp     loc_140007F5F
0x140007ed9  test    ebx, ebx
0x140007edb  js      loc_140007FCB
0x140007ee1  mov     rsi, [rdi]
0x140007ee4  test    rsi, rsi
0x140007ee7  jz      short loc_140007F5B
0x140007ee9  cmp     qword ptr [rsi+10h], 0
0x140007eee  mov     [rsp+58h+pUnk], 0
0x140007ef7  jnz     short loc_140007EFD
0x140007ef9  xor     ebx, ebx
0x140007efb  jmp     short loc_140007F5B
0x140007efd  mov     rcx, [rsi+18h]
0x140007f01  lea     r8, [rsp+58h+pUnk]
0x140007f06  mov     rax, [rsi+10h]
0x140007f0a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140007f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f16  mov     ebx, eax
0x140007f18  test    eax, eax
0x140007f1a  js      short loc_140007F3E
0x140007f1c  mov     rdx, [rsp+58h+pUnk]; pUnk
0x140007f21  lea     rax, [rsi+28h]
0x140007f25  mov     rcx, [rsi]; rclsid
0x140007f28  mov     r9d, r13d; flags
0x140007f2b  mov     r8d, 4; dwClsContext
0x140007f31  mov     [rsp+58h+lpdwRegister], rax; lpdwRegister
0x140007f36  call    cs:__imp_CoRegisterClassObject
0x140007f3c  mov     ebx, eax
0x140007f3e  mov     rcx, [rsp+58h+pUnk]
0x140007f43  test    rcx, rcx
0x140007f46  jz      short loc_140007F54
0x140007f48  mov     rax, [rcx]
0x140007f4b  mov     rax, [rax+10h]
0x140007f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f54  mov     rax, cs:off_140021278
0x140007f5b  add     rdi, 8
0x140007f5f  cmp     rdi, rax
0x140007f62  jb      loc_140007ED9
0x140007f68  test    ebx, ebx
0x140007f6a  js      short loc_140007FCB
0x140007f6c  lea     rax, [rsp+58h+pUnk]
0x140007f71  mov     [rsp+58h+pUnk], 0
0x140007f7a  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x140007f81  mov     [rsp+58h+lpdwRegister], rax; ppv
0x140007f86  mov     r8d, r13d; dwClsContext
0x140007f89  lea     rcx, CLSID_GlobalOptions; rclsid
0x140007f90  xor     edx, edx; pUnkOuter
0x140007f92  call    cs:__imp_CoCreateInstance
0x140007f98  test    eax, eax
0x140007f9a  js      short loc_140007FB3
0x140007f9c  mov     rcx, [rsp+58h+pUnk]
0x140007fa1  mov     r8, r13
0x140007fa4  mov     edx, r13d
0x140007fa7  mov     rax, [rcx]
0x140007faa  mov     rax, [rax+18h]
0x140007fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fb3  mov     rcx, [rsp+58h+pUnk]
0x140007fb8  test    rcx, rcx
0x140007fbb  jz      short loc_140007FE1
0x140007fbd  mov     rax, [rcx]
0x140007fc0  mov     rax, [rax+10h]
0x140007fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fc9  jmp     short loc_140007FE1
0x140007fcb  mov     r8d, ebx
0x140007fce  lea     rdx, aRegisterclasso; "RegisterClassObjects failed: hr: 0x%x"
0x140007fd5  lea     rcx, aTload64bitdlls_10; "TLoad64BitDllsMgr::Run"
0x140007fdc  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140007fe1  mov     edx, r15d; unsigned int
0x140007fe4  mov     rcx, rbp; this
0x140007fe7  call    ?StartLdrRPCServer@TLoad64BitDllsMgr@@IEAAKK@Z; TLoad64BitDllsMgr::StartLdrRPCServer(ulong)
0x140007fec  mov     ebx, eax
0x140007fee  test    eax, eax
0x140007ff0  jnz     short loc_140008009
0x140007ff2  mov     rcx, [rbp+80h]; hHandle
0x140007ff9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140007ffc  call    cs:__imp_WaitForSingleObject
0x140008002  call    ?StopLdrRPCServer@TLoad64BitDllsMgr@@QEAAKXZ; TLoad64BitDllsMgr::StopLdrRPCServer(void)
0x140008007  mov     ebx, eax
0x140008009  mov     rcx, [rbp+80h]; hObject
0x140008010  call    cs:__imp_CloseHandle
0x140008016  test    r14b, r14b
0x140008019  jz      short loc_14000803C
0x14000801b  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x140008022  test    rax, rax
0x140008025  jz      short loc_14000802C
0x140008027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000802c  call    cs:__imp_CoUninitialize
0x140008032  jmp     short loc_14000803C
0x140008034  call    cs:__imp_GetLastError
0x14000803a  mov     ebx, eax
0x14000803c  mov     rbp, [rsp+58h+arg_10]
0x140008041  mov     eax, ebx
0x140008043  mov     rbx, [rsp+58h+arg_8]
0x140008048  add     rsp, 30h
0x14000804c  pop     r15
0x14000804e  pop     r14
0x140008050  pop     r13
0x140008052  pop     rdi
0x140008053  pop     rsi
0x140008054  retn
```
