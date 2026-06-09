# InitializeService(void *)

- ea: `0x180033814`
- end: `0x180033ad1`
- name: `?InitializeService@@YAJPEAX@Z`
- size: `701`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800349a8`

## callees

- `0x180008e64`
- `0x18000c6ec`
- `0x18002dedc`
- `0x18002e168`
- `0x180033238`
- `0x180033814`
- `0x180035258`
- `0x18006ea28`
- `0x1800de0fc`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003387b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003387b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003396e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033a25`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033a9a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033aac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003396e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033a25`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033a9a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033aac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033839`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033839`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800339fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033a67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800339fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033a67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033985`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033985`

## string_xrefs

- `0x18003385d`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x18003388b`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x1800338b6`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180033954`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180033a0b`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180033a80`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180033832`: `combase.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall InitializeService(void *a1)
{
  HMODULE Library; // rax
  const char *v3; // r9
  HMODULE v4; // rbx
  bool v5; // si
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  int v8; // eax
  __int64 *System; // rax
  const char *v10; // r9
  volatile signed __int32 *v11; // rdi
  int Orchestrator; // eax
  unsigned int v13; // edi
  const char *v14; // r9
  __int64 result; // rax
  _DWORD *v16; // rdi
  __int64 v17; // r14
  int v18; // eax
  unsigned int v19; // edi
  int v20; // [rsp+20h] [rbp-48h]
  int v21; // [rsp+20h] [rbp-48h]
  HMODULE v22; // [rsp+28h] [rbp-40h]
  _DWORD *v23; // [rsp+30h] [rbp-38h] BYREF
  volatile signed __int32 *v24; // [rsp+38h] [rbp-30h]
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  Library = LoadLibraryExW(L"combase.dll", 0, 0x800u);
  v4 = Library;
  v22 = Library;
  v5 = Library != 0;
  LOBYTE(v20) = Library != 0;
  if ( !Library )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x264,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
      v3);
  try
  {
    if ( v5 )
    {
      ProcAddress = GetProcAddress(v4, (LPCSTR)0x42);
      if ( ProcAddress )
      {
        v8 = ((__int64 (__fastcall *)(int *))ProcAddress)(&dword_180150110);
        if ( v8 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x26D,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
            (const char *)(unsigned int)v8,
            v20);
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x269,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
          v7);
      }
    }
    try
    {
      System = SystemInterface::Service::GetSystem((__int64 *)&v23);
      (*(void (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)*System + 240LL))(*System, a1, 60000);
      v11 = v24;
      if ( v24 )
      {
        if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x276,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
        v10);
      v4 = v22;
      v5 = v20;
    }
    Orchestrator = UpdateSessionOrchestrator::CreateOrchestrator();
    v13 = Orchestrator;
    if ( Orchestrator < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x278,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
        (const char *)(unsigned int)Orchestrator,
        v20);
      if ( v5 )
        FreeLibrary(v4);
      return v13;
    }
    EnterCriticalSection(&s_pUsoSvcLock);
    v25 = &s_pUsoSvcLock;
    if ( !s_pUsoSvc )
    {
      v16 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v23 = v16;
      if ( v16 )
      {
        *(_QWORD *)v16 = &UsoSvc::`vftable';
        v16[2] = 0;
        SvcAddRef();
      }
      else
      {
        v16 = 0;
      }
      if ( !v16 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UsoSvc.cpp",
          (const char *)0x8007000ELL,
          v20);
        LeaveCriticalSection(&s_pUsoSvcLock);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x279,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
          (const char *)0x8007000ELL,
          v21);
        if ( v5 )
          FreeLibrary(v4);
        return 2147942414LL;
      }
      v17 = s_pUsoSvc;
      s_pUsoSvc = (__int64)v16;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 8LL))(v16);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    LeaveCriticalSection(&s_pUsoSvcLock);
    v18 = CreateAndRegisterClassFactories();
    v19 = v18;
    if ( v18 >= 0 )
    {
      if ( v5 )
        FreeLibrary(v4);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
        (const char *)(unsigned int)v18,
        v20);
      if ( v5 )
        FreeLibrary(v4);
      result = v19;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x27D,
                           (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x180033814  mov     [rsp+arg_8], rbx
0x180033819  mov     [rsp+arg_10], rsi
0x18003381e  push    rdi
0x18003381f  push    r14
0x180033821  push    r15
0x180033823  sub     rsp, 50h
0x180033827  mov     rdi, rcx
0x18003382a  xor     edx, edx; hFile
0x18003382c  mov     r8d, 800h; dwFlags
0x180033832  lea     rcx, aCombaseDll; "combase.dll"
0x180033839  call    cs:__imp_LoadLibraryExW
0x18003383f  mov     rbx, rax
0x180033842  mov     [rsp+68h+var_40], rax
0x180033847  mov     rcx, [rsp+68h]; this
0x18003384c  test    rax, rax
0x18003384f  setnz   sil
0x180033853  mov     byte ptr [rsp+68h+var_48], sil; int
0x180033858  test    rax, rax
0x18003385b  jnz     short loc_18003386E
0x18003385d  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180033864  mov     edx, 264h; void *
0x180033869  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003386e  test    sil, sil
0x180033871  jz      short loc_1800338C8
0x180033873  mov     edx, 42h ; 'B'; lpProcName
0x180033878  mov     rcx, rbx; hModule
0x18003387b  call    cs:__imp_GetProcAddress
0x180033881  mov     rcx, [rsp+68h]; this
0x180033886  test    rax, rax
0x180033889  jnz     short loc_18003389E
0x18003388b  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180033892  mov     edx, 269h; void *
0x180033897  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003389c  jmp     short loc_1800338C8
0x18003389e  lea     rcx, dword_180150110
0x1800338a5  call    _guard_dispatch_icall
0x1800338aa  mov     rcx, [rsp+68h]; this
0x1800338af  test    eax, eax
0x1800338b1  jns     short loc_1800338C8
0x1800338b3  mov     r9d, eax; char *
0x1800338b6  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800338bd  mov     edx, 26Dh; void *
0x1800338c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800338c7  nop
0x1800338c8  lea     rcx, [rsp+68h+var_38]
0x1800338cd  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800338d2  nop
0x1800338d3  mov     rcx, [rax]
0x1800338d6  mov     rax, [rcx]
0x1800338d9  mov     r8d, 0EA60h
0x1800338df  mov     rdx, rdi
0x1800338e2  mov     rax, [rax+0F0h]
0x1800338e9  call    _guard_dispatch_icall
0x1800338ee  nop
0x1800338ef  mov     rdi, [rsp+68h+var_30]
0x1800338f4  test    rdi, rdi
0x1800338f7  jz      short loc_180033935
0x1800338f9  or      r14d, 0FFFFFFFFh
0x1800338fd  mov     eax, r14d
0x180033900  lock xadd [rdi+8], eax
0x180033905  add     eax, r14d
0x180033908  jnz     short loc_180033935
0x18003390a  mov     rax, [rdi]
0x18003390d  mov     rcx, rdi
0x180033910  mov     rax, [rax]
0x180033913  call    _guard_dispatch_icall
0x180033918  mov     eax, r14d
0x18003391b  lock xadd [rdi+0Ch], eax
0x180033920  add     eax, r14d
0x180033923  jnz     short loc_180033935
0x180033925  mov     rax, [rdi]
0x180033928  mov     rcx, rdi
0x18003392b  mov     rax, [rax+8]
0x18003392f  call    _guard_dispatch_icall
0x180033934  nop
0x180033935  jmp     short loc_180033941
0x180033937  mov     rbx, [rsp+68h+var_40]
0x18003393c  mov     sil, byte ptr [rsp+68h+var_48]
0x180033941  call    ?CreateOrchestrator@UpdateSessionOrchestrator@@SAJXZ; UpdateSessionOrchestrator::CreateOrchestrator(void)
0x180033946  mov     edi, eax
0x180033948  test    eax, eax
0x18003394a  jns     short loc_18003397B
0x18003394c  mov     rcx, [rsp+68h]; this
0x180033951  mov     r9d, eax; char *
0x180033954  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18003395b  mov     edx, 278h; void *
0x180033960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033965  nop
0x180033966  test    sil, sil
0x180033969  jz      short loc_180033974
0x18003396b  mov     rcx, rbx; hLibModule
0x18003396e  call    cs:__imp_FreeLibrary
0x180033974  mov     eax, edi
0x180033976  jmp     loc_180033ABA
0x18003397b  lea     r15, ?s_pUsoSvcLock@@3Vcritical_section@wil@@A; wil::critical_section s_pUsoSvcLock
0x180033982  mov     rcx, r15; lpCriticalSection
0x180033985  call    cs:__imp_EnterCriticalSection
0x18003398b  mov     [rsp+68h+var_28], r15
0x180033990  cmp     cs:?s_pUsoSvc@@3V?$com_ptr_t@VUsoSvc@@Uerr_returncode_policy@wil@@@wil@@A, 0; wil::com_ptr_t<UsoSvc,wil::err_returncode_policy> s_pUsoSvc
0x180033998  jnz     loc_180033A64
0x18003399e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800339a5  mov     ecx, 10h; unsigned __int64
0x1800339aa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800339af  mov     rdi, rax
0x1800339b2  mov     [rsp+68h+var_38], rax
0x1800339b7  test    rax, rax
0x1800339ba  jz      short loc_1800339D4
0x1800339bc  lea     rax, ??_7UsoSvc@@6B@; const UsoSvc::`vftable'
0x1800339c3  mov     [rdi], rax
0x1800339c6  mov     dword ptr [rdi+8], 0
0x1800339cd  call    ?SvcAddRef@@YAXXZ; SvcAddRef(void)
0x1800339d2  jmp     short loc_1800339D6
0x1800339d4  xor     edi, edi
0x1800339d6  test    rdi, rdi
0x1800339d9  jnz     short loc_180033A32
0x1800339db  mov     rcx, [rsp+68h]; this
0x1800339e0  mov     edi, 8007000Eh
0x1800339e5  mov     r9d, edi; char *
0x1800339e8  lea     r8, aCW1SSrcOrchest_21; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800339ef  mov     edx, 40h ; '@'; void *
0x1800339f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339f9  nop
0x1800339fa  mov     rcx, r15; lpCriticalSection
0x1800339fd  call    cs:__imp_LeaveCriticalSection
0x180033a03  mov     rcx, [rsp+68h]; this
0x180033a08  mov     r9d, edi; char *
0x180033a0b  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180033a12  mov     edx, 279h; void *
0x180033a17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a1c  nop
0x180033a1d  test    sil, sil
0x180033a20  jz      short loc_180033A2B
0x180033a22  mov     rcx, rbx; hLibModule
0x180033a25  call    cs:__imp_FreeLibrary
0x180033a2b  mov     eax, edi
0x180033a2d  jmp     loc_180033ABA
0x180033a32  mov     r14, cs:?s_pUsoSvc@@3V?$com_ptr_t@VUsoSvc@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<UsoSvc,wil::err_returncode_policy> s_pUsoSvc
0x180033a39  mov     cs:?s_pUsoSvc@@3V?$com_ptr_t@VUsoSvc@@Uerr_returncode_policy@wil@@@wil@@A, rdi; wil::com_ptr_t<UsoSvc,wil::err_returncode_policy> s_pUsoSvc
0x180033a40  mov     rax, [rdi]
0x180033a43  mov     rcx, rdi
0x180033a46  mov     rax, [rax+8]
0x180033a4a  call    _guard_dispatch_icall
0x180033a4f  test    r14, r14
0x180033a52  jz      short loc_180033A64
0x180033a54  mov     rax, [r14]
0x180033a57  mov     rcx, r14
0x180033a5a  mov     rax, [rax+10h]
0x180033a5e  call    _guard_dispatch_icall
0x180033a63  nop
0x180033a64  mov     rcx, r15; lpCriticalSection
0x180033a67  call    cs:__imp_LeaveCriticalSection
0x180033a6d  call    ?CreateAndRegisterClassFactories@@YAJXZ; CreateAndRegisterClassFactories(void)
0x180033a72  mov     edi, eax
0x180033a74  test    eax, eax
0x180033a76  jns     short loc_180033AA4
0x180033a78  mov     rcx, [rsp+68h]; this
0x180033a7d  mov     r9d, eax; char *
0x180033a80  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180033a87  mov     edx, 27Ah; void *
0x180033a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a91  nop
0x180033a92  test    sil, sil
0x180033a95  jz      short loc_180033AA0
0x180033a97  mov     rcx, rbx; hLibModule
0x180033a9a  call    cs:__imp_FreeLibrary
0x180033aa0  mov     eax, edi
0x180033aa2  jmp     short loc_180033ABA
0x180033aa4  test    sil, sil
0x180033aa7  jz      short loc_180033AB2
0x180033aa9  mov     rcx, rbx; hLibModule
0x180033aac  call    cs:__imp_FreeLibrary
0x180033ab2  xor     eax, eax
0x180033ab4  jmp     short loc_180033ABA
0x180033ab6  mov     eax, dword ptr [rsp+68h+var_40]
0x180033aba  lea     r11, [rsp+68h+var_18]
0x180033abf  mov     rbx, [r11+28h]
0x180033ac3  mov     rsi, [r11+30h]
0x180033ac7  mov     rsp, r11
0x180033aca  pop     r15
0x180033acc  pop     r14
0x180033ace  pop     rdi
0x180033acf  retn
```
