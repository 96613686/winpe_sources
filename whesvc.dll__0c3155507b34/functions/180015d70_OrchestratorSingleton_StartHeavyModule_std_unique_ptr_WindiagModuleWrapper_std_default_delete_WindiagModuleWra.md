# OrchestratorSingleton::StartHeavyModule(std::unique_ptr<WindiagModuleWrapper,std::default_delete<WindiagModuleWrapper>>,char const *,std::unique_ptr<OrchestratorSingleton::ModuleThreadData,std::default_delete<OrchestratorSingleton::ModuleThreadData>> &)

- ea: `0x180015d70`
- end: `0x180016201`
- name: `?StartHeavyModule@OrchestratorSingleton@@AEAAJV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBDAEAV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@3@@Z`
- size: `1169`
- prototype: `__int64 __fastcall(__int64, __int64 *, char *, __int64 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180014a14`

## callees

- `0x180003304`
- `0x180003be4`
- `0x180009024`
- `0x180009044`
- `0x180011578`
- `0x180011bf8`
- `0x1800125ec`
- `0x180015d70`
- `0x18001b290`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180016056`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180016056`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180015fc1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180016126`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180015fc1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180016126`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015fab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015fab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015dad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015dad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001614d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001616c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015f1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001614d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001616c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OrchestratorSingleton::StartHeavyModule(__int64 a1, __int64 *a2, char *a3, __int64 **a4)
{
  HANDLE EventW; // rbx
  const char *v7; // r9
  unsigned int LastError; // esi
  __int64 v9; // rbx
  void *v10; // rcx
  int v12; // r13d
  __int64 *v13; // rsi
  void *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  ModuleHandler *v17; // rbx
  int v18; // eax
  unsigned int v19; // r13d
  char *v20; // rcx
  bool v21; // cc
  ModuleHandler *v22; // rbx
  __int64 v23; // rbx
  void *v24; // rcx
  void *v25; // rbx
  char *v26; // rcx
  void *v27; // rbx
  __int64 v28; // rbx
  void *v29; // rcx
  const char *v30; // r9
  __int64 *v31; // rbx
  char *v32; // rcx
  ModuleHandler *v33; // rsi
  __int64 v34; // rbx
  void *v35; // rcx
  ModuleHandler **v36; // rbx
  char *v37; // rcx
  ModuleHandler *v38; // rsi
  __int64 v39; // rbx
  void *v40; // rcx
  __int64 v41; // [rsp+30h] [rbp-68h] BYREF
  int v42[2]; // [rsp+38h] [rbp-60h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-58h]
  void *v44; // [rsp+48h] [rbp-50h]
  int v45[2]; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v44 = 0;
  EventW = CreateEventW(0, 1, 1, 0);
  hObject = EventW;
  if ( !EventW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1E3,
                  (int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
                  v7);
    v9 = *a2;
    if ( *a2 )
    {
      std::string::~string((char **)(v9 + 56));
      std::string::~string((char **)(v9 + 24));
      v10 = *(void **)(v9 + 8);
      if ( v10 )
        operator delete(v10);
      if ( *(_QWORD *)v9 )
        operator delete(*(void **)v9);
      operator delete((void *)v9);
    }
    return LastError;
  }
  v12 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 80));
  try
  {
    v13 = (__int64 *)operator new(0x10u);
    *v13 = 0;
    v13[1] = 0;
    v44 = v13;
    *(_QWORD *)v45 = *(_QWORD *)(a1 + 88);
    v14 = operator new(0x178u);
    v41 = (__int64)EventW;
    hObject = 0;
    v15 = *a2;
    *a2 = 0;
    *(_QWORD *)v42 = v15;
    v16 = ModuleHandler::ModuleHandler((__int64)v14, (const char ****)v42, *(__int64 *)v45, v12, a3, (HANDLE *)&v41);
    v17 = (ModuleHandler *)*v13;
    *v13 = v16;
    if ( v17 )
    {
      ModuleHandler::~ModuleHandler(v17);
      operator delete(v17);
    }
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EE,
      (int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)0x8007000ELL);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    v36 = (ModuleHandler **)v44;
    if ( v44 )
    {
      v37 = (char *)*((_QWORD *)v44 + 1);
      if ( (unsigned __int64)(v37 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v37);
      v38 = *v36;
      if ( *v36 )
      {
        ModuleHandler::~ModuleHandler(*v36);
        operator delete(v38);
      }
      operator delete(v36);
    }
    v39 = *a2;
    if ( *a2 )
    {
      std::string::~string((char **)(v39 + 56));
      std::string::~string((char **)(v39 + 24));
      v40 = *(void **)(v39 + 8);
      if ( v40 )
        operator delete(v40);
      if ( *(_QWORD *)v39 )
        operator delete(*(void **)v39);
      operator delete((void *)v39);
    }
    return 2147942414LL;
  }
  v13 = (__int64 *)operator new(0x10u);
  *v13 = 0;
  v13[1] = 0;
  v44 = v13;
  *(_QWORD *)v45 = *(_QWORD *)(a1 + 88);
}

```

## disassembly

```asm
0x180015d70  mov     rax, rsp
0x180015d73  mov     [rax+20h], r9
0x180015d77  mov     [rax+18h], r8
0x180015d7b  mov     [rax+10h], rdx
0x180015d7f  mov     [rax+8], rcx
0x180015d83  push    rbx
0x180015d84  push    rsi
0x180015d85  push    r12
0x180015d87  push    r13
0x180015d89  push    r14
0x180015d8b  push    r15
0x180015d8d  sub     rsp, 68h
0x180015d91  mov     r12, rdx
0x180015d94  mov     r14, rcx
0x180015d97  mov     qword ptr [rax-50h], 0
0x180015d9f  xor     r9d, r9d; lpName
0x180015da2  lea     esi, [r9+1]
0x180015da6  mov     r8d, esi; bInitialState
0x180015da9  mov     edx, esi; bManualReset
0x180015dab  xor     ecx, ecx; lpEventAttributes
0x180015dad  call    cs:__imp_CreateEventW
0x180015db3  mov     rbx, rax
0x180015db6  mov     [rsp+98h+hObject], rax
0x180015dbb  test    rax, rax
0x180015dbe  jnz     short loc_180015E2B
0x180015dc0  mov     rcx, [rsp+98h]; this
0x180015dc8  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180015dcf  mov     edx, 1E3h; void *
0x180015dd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015dd9  mov     esi, eax
0x180015ddb  mov     rbx, [r12]
0x180015ddf  test    rbx, rbx
0x180015de2  jz      short loc_180015E24
0x180015de4  lea     rcx, [rbx+38h]
0x180015de8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015ded  lea     rcx, [rbx+18h]
0x180015df1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015df6  mov     rcx, [rbx+8]; void *
0x180015dfa  test    rcx, rcx
0x180015dfd  jz      short loc_180015E04
0x180015dff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015e04  cmp     qword ptr [rbx], 0
0x180015e08  jz      short loc_180015E17
0x180015e0a  mov     edx, 18h; unsigned __int64
0x180015e0f  mov     rcx, [rbx]; void *
0x180015e12  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015e17  mov     edx, 58h ; 'X'; unsigned __int64
0x180015e1c  mov     rcx, rbx; void *
0x180015e1f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015e24  mov     eax, esi
0x180015e26  jmp     loc_1800161F2
0x180015e2b  mov     r13d, esi
0x180015e2e  lock xadd [r14+50h], r13d
0x180015e34  add     r13d, esi
0x180015e37  mov     r15d, 10h
0x180015e3d  mov     ecx, r15d; Size
0x180015e40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015e45  mov     rsi, rax
0x180015e48  mov     qword ptr [rax], 0
0x180015e4f  mov     qword ptr [rax+8], 0
0x180015e57  mov     [rsp+98h+var_50], rax
0x180015e5c  mov     rax, [r14+58h]
0x180015e60  mov     qword ptr [rsp+98h+var_48], rax
0x180015e65  mov     r14d, 178h
0x180015e6b  mov     ecx, r14d; Size
0x180015e6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015e73  mov     [rsp+98h+var_68], rbx
0x180015e78  mov     [rsp+98h+hObject], 0
0x180015e81  mov     rcx, [r12]
0x180015e85  mov     qword ptr [r12], 0
0x180015e8d  mov     qword ptr [rsp+98h+var_60], rcx
0x180015e92  lea     rcx, [rsp+98h+var_68]
0x180015e97  mov     [rsp+98h+var_70], rcx; __int64
0x180015e9c  mov     rcx, [rsp+98h+arg_10]
0x180015ea4  mov     [rsp+98h+var_78], rcx; int
0x180015ea9  mov     r9d, r13d; int
0x180015eac  mov     r8, qword ptr [rsp+98h+var_48]; int
0x180015eb1  lea     rdx, [rsp+98h+var_60]; int
0x180015eb6  mov     rcx, rax; int
0x180015eb9  call    ??0ModuleHandler@@QEAA@V?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEAXIPEBDV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; ModuleHandler::ModuleHandler(std::unique_ptr<WindiagModuleWrapper>,void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x180015ebe  mov     rbx, [rsi]
0x180015ec1  mov     [rsi], rax
0x180015ec4  test    rbx, rbx
0x180015ec7  jz      short loc_180015EDD
0x180015ec9  mov     rcx, rbx; this
0x180015ecc  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180015ed1  mov     edx, r14d; unsigned __int64
0x180015ed4  mov     rcx, rbx; void *
0x180015ed7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015edc  nop
0x180015edd  mov     rcx, rsi; this
0x180015ee0  call    ?CreateAndSetThreadHandle@ModuleThreadData@OrchestratorSingleton@@QEAAJXZ; OrchestratorSingleton::ModuleThreadData::CreateAndSetThreadHandle(void)
0x180015ee5  mov     r13d, eax
0x180015ee8  test    eax, eax
0x180015eea  jns     loc_180015F99
0x180015ef0  mov     rcx, [rsp+98h]; this
0x180015ef8  mov     r9d, eax; char *
0x180015efb  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180015f02  mov     edx, 1F2h; void *
0x180015f07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f0c  nop
0x180015f0d  mov     rcx, [rsi+8]; hObject
0x180015f11  lea     r8, [rcx-1]
0x180015f15  cmp     r8, 0FFFFFFFFFFFFFFFDh
0x180015f19  ja      short loc_180015F21
0x180015f1b  call    cs:__imp_CloseHandle
0x180015f21  mov     rbx, [rsi]
0x180015f24  test    rbx, rbx
0x180015f27  jz      short loc_180015F3C
0x180015f29  mov     rcx, rbx; this
0x180015f2c  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180015f31  mov     rdx, r14; unsigned __int64
0x180015f34  mov     rcx, rbx; void *
0x180015f37  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f3c  mov     rdx, r15; unsigned __int64
0x180015f3f  mov     rcx, rsi; void *
0x180015f42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f47  nop
0x180015f48  mov     rbx, [r12]
0x180015f4c  test    rbx, rbx
0x180015f4f  jz      short loc_180015F91
0x180015f51  lea     rcx, [rbx+38h]
0x180015f55  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015f5a  lea     rcx, [rbx+18h]
0x180015f5e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180015f63  mov     rcx, [rbx+8]; void *
0x180015f67  test    rcx, rcx
0x180015f6a  jz      short loc_180015F71
0x180015f6c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f71  cmp     qword ptr [rbx], 0
0x180015f75  jz      short loc_180015F84
0x180015f77  mov     edx, 18h; unsigned __int64
0x180015f7c  mov     rcx, [rbx]; void *
0x180015f7f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f84  mov     edx, 58h ; 'X'; unsigned __int64
0x180015f89  mov     rcx, rbx; void *
0x180015f8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f91  mov     eax, r13d
0x180015f94  jmp     loc_1800161F2
0x180015f99  mov     rbx, [rsi+8]
0x180015f9d  xor     edx, edx; dwMilliseconds
0x180015f9f  mov     rcx, [rsp+98h+arg_0]
0x180015fa7  mov     rcx, [rcx+58h]; hHandle
0x180015fab  call    cs:__imp_WaitForSingleObject
0x180015fb1  mov     rcx, rbx; hThread
0x180015fb4  test    eax, eax
0x180015fb6  jnz     loc_180016056
0x180015fbc  mov     edx, 3E3h; dwExitCode
0x180015fc1  call    cs:__imp_TerminateThread
0x180015fc7  nop
0x180015fc8  mov     rcx, [rsi+8]; hObject
0x180015fcc  lea     rax, [rcx-1]
0x180015fd0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015fd4  ja      short loc_180015FDC
0x180015fd6  call    cs:__imp_CloseHandle
0x180015fdc  mov     rbx, [rsi]
0x180015fdf  test    rbx, rbx
0x180015fe2  jz      short loc_180015FF7
0x180015fe4  mov     rcx, rbx; this
0x180015fe7  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180015fec  mov     rdx, r14; unsigned __int64
0x180015fef  mov     rcx, rbx; void *
0x180015ff2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015ff7  mov     rdx, r15; unsigned __int64
0x180015ffa  mov     rcx, rsi; void *
0x180015ffd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016002  nop
0x180016003  mov     rbx, [r12]
0x180016007  test    rbx, rbx
0x18001600a  jz      short loc_18001604C
0x18001600c  lea     rcx, [rbx+38h]
0x180016010  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016015  lea     rcx, [rbx+18h]
0x180016019  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001601e  mov     rcx, [rbx+8]; void *
0x180016022  test    rcx, rcx
0x180016025  jz      short loc_18001602C
0x180016027  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001602c  cmp     qword ptr [rbx], 0
0x180016030  jz      short loc_18001603F
0x180016032  mov     edx, 18h; unsigned __int64
0x180016037  mov     rcx, [rbx]; void *
0x18001603a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001603f  mov     edx, 58h ; 'X'; unsigned __int64
0x180016044  mov     rcx, rbx; void *
0x180016047  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001604c  mov     eax, 80004004h
0x180016051  jmp     loc_1800161F2
0x180016056  call    cs:__imp_ResumeThread
0x18001605c  test    eax, eax
0x18001605e  js      loc_180016102
0x180016064  mov     rax, [rsp+98h+arg_18]
0x18001606c  mov     rbx, [rax]
0x18001606f  mov     [rax], rsi
0x180016072  test    rbx, rbx
0x180016075  jz      short loc_1800160B2
0x180016077  mov     rcx, [rbx+8]; hObject
0x18001607b  lea     rax, [rcx-1]
0x18001607f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016083  ja      short loc_18001608B
0x180016085  call    cs:__imp_CloseHandle
0x18001608b  mov     rsi, [rbx]
0x18001608e  test    rsi, rsi
0x180016091  jz      short loc_1800160A6
0x180016093  mov     rcx, rsi; this
0x180016096  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x18001609b  mov     rdx, r14; unsigned __int64
0x18001609e  mov     rcx, rsi; void *
0x1800160a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800160a6  mov     rdx, r15; unsigned __int64
0x1800160a9  mov     rcx, rbx; void *
0x1800160ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800160b1  nop
0x1800160b2  mov     rbx, [r12]
0x1800160b6  test    rbx, rbx
0x1800160b9  jz      short loc_1800160FB
0x1800160bb  lea     rcx, [rbx+38h]
0x1800160bf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800160c4  lea     rcx, [rbx+18h]
0x1800160c8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800160cd  mov     rcx, [rbx+8]; void *
0x1800160d1  test    rcx, rcx
0x1800160d4  jz      short loc_1800160DB
0x1800160d6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800160db  cmp     qword ptr [rbx], 0
0x1800160df  jz      short loc_1800160EE
0x1800160e1  mov     edx, 18h; unsigned __int64
0x1800160e6  mov     rcx, [rbx]; void *
0x1800160e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800160ee  mov     edx, 58h ; 'X'; unsigned __int64
0x1800160f3  mov     rcx, rbx; void *
0x1800160f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800160fb  xor     eax, eax
0x1800160fd  jmp     loc_1800161F2
0x180016102  mov     rcx, [rsp+98h]; this
0x18001610a  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180016111  mov     edx, 211h; void *
0x180016116  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001611b  mov     r13d, eax
0x18001611e  mov     edx, 3E3h; dwExitCode
0x180016123  mov     rcx, rbx; hThread
0x180016126  call    cs:__imp_TerminateThread
0x18001612c  nop
0x18001612d  mov     rcx, [rsi+8]
0x180016131  lea     rdx, [rcx-1]
0x180016135  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180016139  jmp     loc_180015F19
0x18001613e  mov     rcx, [rsp+98h+hObject]; hObject
0x180016143  lea     rax, [rcx-1]
0x180016147  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001614b  ja      short loc_180016154
0x18001614d  call    cs:__imp_CloseHandle
0x180016153  nop
0x180016154  mov     rbx, [rsp+98h+var_50]
0x180016159  test    rbx, rbx
0x18001615c  jz      short loc_18001619D
0x18001615e  mov     rcx, [rbx+8]; hObject
0x180016162  lea     rax, [rcx-1]
0x180016166  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001616a  ja      short loc_180016172
0x18001616c  call    cs:__imp_CloseHandle
0x180016172  mov     rsi, [rbx]
0x180016175  test    rsi, rsi
0x180016178  jz      short loc_18001618F
0x18001617a  mov     rcx, rsi; this
0x18001617d  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180016182  mov     edx, 178h; unsigned __int64
0x180016187  mov     rcx, rsi; void *
0x18001618a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001618f  mov     edx, 10h; unsigned __int64
0x180016194  mov     rcx, rbx; void *
0x180016197  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001619c  nop
0x18001619d  mov     rax, [rsp+98h+arg_8]
0x1800161a5  mov     rbx, [rax]
0x1800161a8  test    rbx, rbx
0x1800161ab  jz      short loc_1800161ED
0x1800161ad  lea     rcx, [rbx+38h]
0x1800161b1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800161b6  lea     rcx, [rbx+18h]
0x1800161ba  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800161bf  mov     rcx, [rbx+8]; void *
0x1800161c3  test    rcx, rcx
0x1800161c6  jz      short loc_1800161CD
0x1800161c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800161cd  cmp     qword ptr [rbx], 0
0x1800161d1  jz      short loc_1800161E0
0x1800161d3  mov     edx, 18h; unsigned __int64
0x1800161d8  mov     rcx, [rbx]; void *
0x1800161db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800161e0  mov     edx, 58h ; 'X'; unsigned __int64
0x1800161e5  mov     rcx, rbx; void *
0x1800161e8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800161ed  mov     eax, 8007000Eh
0x1800161f2  add     rsp, 68h
0x1800161f6  pop     r15
0x1800161f8  pop     r14
0x1800161fa  pop     r13
0x1800161fc  pop     r12
0x1800161fe  pop     rsi
  ... truncated ...
```
