# OrchestratorSingleton::StartModule(std::unique_ptr<WindiagModuleWrapper,std::default_delete<WindiagModuleWrapper>>,char const *)

- ea: `0x180016208`
- end: `0x18001674b`
- name: `?StartModule@OrchestratorSingleton@@QEAAJV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBD@Z`
- size: `1347`
- prototype: `__int64 __fastcall(_Mtx_t)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180016754`

## callees

- `0x180003304`
- `0x180003be4`
- `0x180009044`
- `0x180009068`
- `0x1800101f4`
- `0x180011578`
- `0x180011bf8`
- `0x1800125ec`
- `0x180016208`
- `0x180017918`
- `0x18001b290`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800164bf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800164bf`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180016407`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001652b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800165d8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001668b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180016407`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001652b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x1800165d8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001668b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800163e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800163e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001641c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001654a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800165f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001641c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001654a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800165f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800166b6`
- `msvcp_win!_Mtx_unlock` at `0x1800163f8`
- `msvcp_win!_Mtx_unlock` at `0x1800164cc`
- `msvcp_win!_Mtx_unlock` at `0x18001651c`
- `msvcp_win!_Mtx_unlock` at `0x1800165c9`
- `msvcp_win!_Mtx_unlock` at `0x18001667a`
- `msvcp_win!_Mtx_unlock` at `0x1800163f8`
- `msvcp_win!_Mtx_unlock` at `0x1800164cc`
- `msvcp_win!_Mtx_unlock` at `0x18001651c`
- `msvcp_win!_Mtx_unlock` at `0x1800165c9`
- `msvcp_win!_Mtx_unlock` at `0x18001667a`
- `msvcp_win!_Mtx_lock` at `0x1800163b0`
- `msvcp_win!_Mtx_lock` at `0x1800163b0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800163bf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800163da`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800163bf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800163da`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OrchestratorSingleton::StartModule(_Mtx_t a1, __int64 *a2, char *a3)
{
  int v6; // r12d
  __int64 *v7; // rdi
  void *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  ModuleHandler *v11; // r12
  int v12; // eax
  unsigned int v13; // r12d
  char *v14; // rcx
  ModuleHandler *v15; // rbx
  __int64 v16; // rbx
  void *v17; // rcx
  __int64 result; // rax
  void *v19; // r12
  char *v21; // rcx
  void *v22; // rbx
  __int64 v23; // rbx
  void *v24; // rcx
  DWORD LastError; // r13d
  unsigned int v26; // r13d
  ModuleHandler **v27; // rbx
  char *v28; // rcx
  ModuleHandler *v29; // rdi
  __int64 v30; // rbx
  void *v31; // rcx
  ModuleHandler **v32; // rbx
  char *v33; // rcx
  ModuleHandler *v34; // rdi
  __int64 v35; // rbx
  void *v36; // rcx
  ModuleHandler **v37; // rbx
  ModuleHandler *v38; // rcx
  ModuleHandler *v39; // rdi
  __int64 v40; // rbx
  void *v41; // rcx
  unsigned int v42; // [rsp+20h] [rbp-88h]
  void *v43; // [rsp+30h] [rbp-78h] BYREF
  __int64 v44; // [rsp+38h] [rbp-70h] BYREF
  char v45; // [rsp+40h] [rbp-68h]
  int v46[2]; // [rsp+48h] [rbp-60h] BYREF
  HANDLE hThread; // [rsp+50h] [rbp-58h]
  char v48[80]; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  int v52; // [rsp+C8h] [rbp+20h] BYREF

  try
  {
    v6 = _InterlockedIncrement((volatile signed __int32 *)a1 + 20);
    v52 = v6;
    v7 = (__int64 *)operator new(0x10u);
    *v7 = 0;
    v7[1] = 0;
    v43 = v7;
    hThread = (HANDLE)*((_QWORD *)a1 + 11);
    v8 = operator new(0x178u);
    v44 = 0;
    v9 = *a2;
    *a2 = 0;
    *(_QWORD *)v46 = v9;
    v10 = ModuleHandler::ModuleHandler((__int64)v8, (const char ****)v46, (__int64)hThread, v6, a3, (HANDLE *)&v44);
    v11 = (ModuleHandler *)*v7;
    *v7 = v10;
    if ( v11 )
    {
      ModuleHandler::~ModuleHandler(v11);
      operator delete(v11);
    }
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)0x8007000ELL);
    v37 = (ModuleHandler **)v43;
    if ( !v43 )
      goto LABEL_69;
LABEL_63:
    if ( v37 )
    {
      v38 = v37[1];
      if ( (unsigned __int64)v38 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v38);
      v39 = *v37;
      if ( *v37 )
      {
        ModuleHandler::~ModuleHandler(*v37);
        operator delete(v39);
      }
      operator delete(v37);
    }
LABEL_69:
    v40 = *a2;
    if ( *a2 )
    {
      std::string::~string((char **)(v40 + 56));
      std::string::~string((char **)(v40 + 24));
      v41 = *(void **)(v40 + 8);
      if ( v41 )
        operator delete(v41);
      if ( *(_QWORD *)v40 )
        operator delete(*(void **)v40);
      operator delete((void *)v40);
    }
    return 2147942414LL;
  }
  v12 = OrchestratorSingleton::ModuleThreadData::CreateAndSetThreadHandle((LPVOID *)v7);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)(unsigned int)v12);
    v14 = (char *)v7[1];
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v14);
    v15 = (ModuleHandler *)*v7;
    if ( *v7 )
    {
      ModuleHandler::~ModuleHandler((ModuleHandler *)*v7);
      operator delete(v15);
    }
    operator delete(v7);
    v16 = *a2;
    if ( *a2 )
    {
      std::string::~string((char **)(v16 + 56));
      std::string::~string((char **)(v16 + 24));
      v17 = *(void **)(v16 + 8);
      if ( v17 )
        operator delete(v17);
      if ( *(_QWORD *)v16 )
        operator delete(*(void **)v16);
      operator delete((void *)v16);
    }
    return v13;
  }
  v19 = (void *)v7[1];
  hThread = v19;
  v44 = (__int64)v19;
  v45 = 1;
  *(_QWORD *)v46 = a1;
  if ( _Mtx_lock(a1) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)a1 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)a1 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !WaitForSingleObject(*((HANDLE *)a1 + 11), 0) )
  {
    _Mtx_unlock(a1);
    TerminateThread(v19, 0x3E3u);
    v21 = (char *)v7[1];
    if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v21);
    v22 = (void *)*v7;
    if ( *v7 )
    {
      ModuleHandler::~ModuleHandler((ModuleHandler *)*v7);
      operator delete(v22);
    }
    operator delete(v7);
    v23 = *a2;
    if ( *a2 )
    {
      std::string::~string((char **)(v23 + 56));
      std::string::~string((char **)(v23 + 24));
      v24 = *(void **)(v23 + 8);
      if ( v24 )
        operator delete(v24);
      if ( *(_QWORD *)v23 )
        operator delete(*(void **)v23);
      operator delete((void *)v23);
    }
    return 2147500036LL;
  }
  try
  {
    std::_Hash<std::_Umap_traits<unsigned int,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>,0>>::emplace<unsigned int const &,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>(
      (__int64)a1 + 288,
      (__int64)v48,
      &v52,
      (__int64 *)&v43);
    if ( (ResumeThread(v19) & 0x80000000) == 0 )
    {
      _Mtx_unlock(a1);
LABEL_49:
      v32 = (ModuleHandler **)v43;
      if ( v43 )
      {
        v33 = (char *)*((_QWORD *)v43 + 1);
        if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v33);
        v34 = *v32;
        if ( *v32 )
        {
          ModuleHandler::~ModuleHandler(*v32);
          operator delete(v34);
        }
        operator delete(v32);
      }
      v35 = *a2;
      if ( *a2 )
      {
        std::string::~string((char **)(v35 + 56));
        std::string::~string((char **)(v35 + 24));
        v36 = *(void **)(v35 + 8);
        if ( v36 )
          operator delete(v36);
        if ( *(_QWORD *)v35 )
          operator delete(*(void **)v35);
        operator delete((void *)v35);
      }
      return 0;
    }
    LastError = GetLastError();
    std::_Hash<std::_Umap_traits<unsigned int,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>,0>>::erase(
      (_QWORD *)a1 + 36,
      &v52);
    if ( !LastError )
    {
      _Mtx_unlock(a1);
      TerminateThread(v19, 0x3E3u);
      goto LABEL_49;
    }
    v26 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xD5,
            (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
            (const char *)LastError,
            v42);
    _Mtx_unlock(a1);
    TerminateThread(v19, 0x3E3u);
    v27 = (ModuleHandler **)v43;
    if ( v43 )
    {
      v28 = (char *)*((_QWORD *)v43 + 1);
      if ( (unsigned __int64)(v28 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v28);
      v29 = *v27;
      if ( *v27 )
      {
        ModuleHandler::~ModuleHandler(*v27);
        operator delete(v29);
      }
      operator delete(v27);
    }
    v30 = *a2;
    if ( *a2 )
    {
      std::string::~string((char **)(v30 + 56));
      std::string::~string((char **)(v30 + 24));
      v31 = *(void **)(v30 + 8);
      if ( v31 )
        operator delete(v31);
      if ( *(_QWORD *)v30 )
        operator delete(*(void **)v30);
      operator delete((void *)v30);
    }
    result = v26;
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)0x8007000ELL);
    _Mtx_unlock(a1);
    TerminateThread(hThread, 0x3E3u);
    v37 = (ModuleHandler **)v43;
    goto LABEL_63;
  }
  return result;
}

```

## disassembly

```asm
0x180016208  mov     rax, rsp
0x18001620b  mov     [rax+10h], rdx
0x18001620f  mov     [rax+8], rcx
0x180016213  push    rbx
0x180016214  push    rsi
0x180016215  push    rdi
0x180016216  push    r12
0x180016218  push    r13
0x18001621a  push    r14
0x18001621c  push    r15
0x18001621e  sub     rsp, 70h
0x180016222  mov     r13, r8
0x180016225  mov     r15, rdx
0x180016228  mov     rbx, rcx
0x18001622b  mov     qword ptr [rax-78h], 0
0x180016233  mov     r12d, 1
0x180016239  lock xadd [rcx+50h], r12d
0x18001623f  inc     r12d
0x180016242  mov     [rax+20h], r12d
0x180016246  mov     esi, 10h
0x18001624b  mov     ecx, esi; Size
0x18001624d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016252  mov     rdi, rax
0x180016255  mov     qword ptr [rax], 0
0x18001625c  mov     qword ptr [rax+8], 0
0x180016264  mov     [rsp+0A8h+var_78], rax
0x180016269  mov     rax, [rbx+58h]
0x18001626d  mov     [rsp+0A8h+hThread], rax
0x180016272  mov     r14d, 178h
0x180016278  mov     ecx, r14d; Size
0x18001627b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016280  mov     [rsp+0A8h+var_70], 0
0x180016289  mov     rcx, [r15]
0x18001628c  mov     qword ptr [r15], 0
0x180016293  mov     qword ptr [rsp+0A8h+var_60], rcx
0x180016298  lea     rcx, [rsp+0A8h+var_70]
0x18001629d  mov     [rsp+0A8h+var_80], rcx; __int64
0x1800162a2  mov     [rsp+0A8h+var_88], r13; unsigned int
0x1800162a7  mov     r9d, r12d; int
0x1800162aa  mov     r8, [rsp+0A8h+hThread]; int
0x1800162af  lea     rdx, [rsp+0A8h+var_60]; int
0x1800162b4  mov     rcx, rax; int
0x1800162b7  call    ??0ModuleHandler@@QEAA@V?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEAXIPEBDV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; ModuleHandler::ModuleHandler(std::unique_ptr<WindiagModuleWrapper>,void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>)
0x1800162bc  mov     r12, [rdi]
0x1800162bf  mov     [rdi], rax
0x1800162c2  test    r12, r12
0x1800162c5  jz      short loc_1800162DB
0x1800162c7  mov     rcx, r12; this
0x1800162ca  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x1800162cf  mov     edx, r14d; unsigned __int64
0x1800162d2  mov     rcx, r12; void *
0x1800162d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800162da  nop
0x1800162db  mov     rcx, rdi; this
0x1800162de  call    ?CreateAndSetThreadHandle@ModuleThreadData@OrchestratorSingleton@@QEAAJXZ; OrchestratorSingleton::ModuleThreadData::CreateAndSetThreadHandle(void)
0x1800162e3  mov     r12d, eax
0x1800162e6  test    eax, eax
0x1800162e8  jns     loc_180016395
0x1800162ee  mov     rcx, [rsp+0A8h]; this
0x1800162f6  mov     r9d, eax; char *
0x1800162f9  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180016300  mov     edx, 0ACh; void *
0x180016305  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001630a  nop
0x18001630b  mov     rcx, [rdi+8]; hObject
0x18001630f  lea     r8, [rcx-1]
0x180016313  cmp     r8, 0FFFFFFFFFFFFFFFDh
0x180016317  ja      short loc_18001631F
0x180016319  call    cs:__imp_CloseHandle
0x18001631f  mov     rbx, [rdi]
0x180016322  test    rbx, rbx
0x180016325  jz      short loc_18001633A
0x180016327  mov     rcx, rbx; this
0x18001632a  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x18001632f  mov     rdx, r14; unsigned __int64
0x180016332  mov     rcx, rbx; void *
0x180016335  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001633a  mov     rdx, rsi; unsigned __int64
0x18001633d  mov     rcx, rdi; void *
0x180016340  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016345  nop
0x180016346  mov     rbx, [r15]
0x180016349  test    rbx, rbx
0x18001634c  jz      short loc_18001638D
0x18001634e  lea     rcx, [rbx+38h]
0x180016352  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016357  lea     rcx, [rbx+18h]
0x18001635b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016360  mov     rcx, [rbx+8]; void *
0x180016364  test    rcx, rcx
0x180016367  jz      short loc_18001636E
0x180016369  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001636e  mov     rcx, [rbx]; void *
0x180016371  test    rcx, rcx
0x180016374  jz      short loc_180016380
0x180016376  mov     edx, 18h; unsigned __int64
0x18001637b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016380  mov     edx, 58h ; 'X'; unsigned __int64
0x180016385  mov     rcx, rbx; void *
0x180016388  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001638d  mov     eax, r12d
0x180016390  jmp     loc_18001673B
0x180016395  mov     r12, [rdi+8]
0x180016399  mov     [rsp+0A8h+hThread], r12
0x18001639e  mov     [rsp+0A8h+var_70], r12
0x1800163a3  mov     [rsp+0A8h+var_68], 1
0x1800163a8  mov     qword ptr [rsp+0A8h+var_60], rbx
0x1800163ad  mov     rcx, rbx; _Mtx_t
0x1800163b0  call    cs:__imp__Mtx_lock
0x1800163b6  test    eax, eax
0x1800163b8  jz      short loc_1800163C6
0x1800163ba  mov     ecx, 5
0x1800163bf  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800163c5  int     3; Trap to Debugger
0x1800163c6  mov     eax, [rbx+4Ch]
0x1800163c9  cmp     eax, 7FFFFFFFh
0x1800163ce  jnz     short loc_1800163E1
0x1800163d0  dec     eax
0x1800163d2  mov     [rbx+4Ch], eax
0x1800163d5  mov     ecx, 6
0x1800163da  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800163e0  nop
0x1800163e1  xor     edx, edx; dwMilliseconds
0x1800163e3  mov     rcx, [rbx+58h]; hHandle
0x1800163e7  call    cs:__imp_WaitForSingleObject
0x1800163ed  test    eax, eax
0x1800163ef  jnz     loc_18001649A
0x1800163f5  mov     rcx, rbx; _Mtx_t
0x1800163f8  call    cs:__imp__Mtx_unlock
0x1800163fe  nop
0x1800163ff  mov     edx, 3E3h; dwExitCode
0x180016404  mov     rcx, r12; hThread
0x180016407  call    cs:__imp_TerminateThread
0x18001640d  nop
0x18001640e  mov     rcx, [rdi+8]; hObject
0x180016412  lea     rax, [rcx-1]
0x180016416  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001641a  ja      short loc_180016422
0x18001641c  call    cs:__imp_CloseHandle
0x180016422  mov     rbx, [rdi]
0x180016425  test    rbx, rbx
0x180016428  jz      short loc_18001643D
0x18001642a  mov     rcx, rbx; this
0x18001642d  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180016432  mov     rdx, r14; unsigned __int64
0x180016435  mov     rcx, rbx; void *
0x180016438  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001643d  mov     rdx, rsi; unsigned __int64
0x180016440  mov     rcx, rdi; void *
0x180016443  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016448  nop
0x180016449  mov     rbx, [r15]
0x18001644c  test    rbx, rbx
0x18001644f  jz      short loc_180016490
0x180016451  lea     rcx, [rbx+38h]
0x180016455  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001645a  lea     rcx, [rbx+18h]
0x18001645e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016463  mov     rcx, [rbx+8]; void *
0x180016467  test    rcx, rcx
0x18001646a  jz      short loc_180016471
0x18001646c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016471  mov     rcx, [rbx]; void *
0x180016474  test    rcx, rcx
0x180016477  jz      short loc_180016483
0x180016479  mov     edx, 18h; unsigned __int64
0x18001647e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016483  mov     edx, 58h ; 'X'; unsigned __int64
0x180016488  mov     rcx, rbx; void *
0x18001648b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016490  mov     eax, 80004004h
0x180016495  jmp     loc_18001673B
0x18001649a  lea     rdi, [rbx+120h]
0x1800164a1  lea     r9, [rsp+0A8h+var_78]
0x1800164a6  lea     r8, [rsp+0A8h+arg_18]
0x1800164ae  lea     rdx, [rsp+0A8h+var_50]
0x1800164b3  mov     rcx, rdi
0x1800164b6  call    ??$emplace@AEBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@?$_Hash@V?$_Umap_traits@IV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@AEBI$$QEAV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@1@@Z; std::_Hash<std::_Umap_traits<uint,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>,0>>::emplace<uint const &,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>(uint const &,std::unique_ptr<OrchestratorSingleton::ModuleThreadData> &&)
0x1800164bb  nop
0x1800164bc  mov     rcx, r12; hThread
0x1800164bf  call    cs:__imp_ResumeThread
0x1800164c5  test    eax, eax
0x1800164c7  js      short loc_1800164D8
0x1800164c9  mov     rcx, rbx; _Mtx_t
0x1800164cc  call    cs:__imp__Mtx_unlock
0x1800164d2  nop
0x1800164d3  jmp     loc_1800165DF
0x1800164d8  call    cs:__imp_GetLastError
0x1800164de  mov     r13d, eax
0x1800164e1  lea     rdx, [rsp+0A8h+arg_18]
0x1800164e9  mov     rcx, rdi
0x1800164ec  call    ?erase@?$_Hash@V?$_Umap_traits@IV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBI@Z; std::_Hash<std::_Umap_traits<uint,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::unique_ptr<OrchestratorSingleton::ModuleThreadData>>>,0>>::erase(uint const &)
0x1800164f1  test    r13d, r13d
0x1800164f4  jz      loc_1800165C6
0x1800164fa  mov     rcx, [rsp+0A8h]; this
0x180016502  mov     r9d, r13d; char *
0x180016505  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x18001650c  mov     edx, 0D5h; void *
0x180016511  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016516  mov     r13d, eax
0x180016519  mov     rcx, rbx; _Mtx_t
0x18001651c  call    cs:__imp__Mtx_unlock
0x180016522  nop
0x180016523  mov     edx, 3E3h; dwExitCode
0x180016528  mov     rcx, r12; hThread
0x18001652b  call    cs:__imp_TerminateThread
0x180016531  nop
0x180016532  mov     rbx, [rsp+0A8h+var_78]
0x180016537  test    rbx, rbx
0x18001653a  jz      short loc_180016577
0x18001653c  mov     rcx, [rbx+8]; hObject
0x180016540  lea     rax, [rcx-1]
0x180016544  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016548  ja      short loc_180016550
0x18001654a  call    cs:__imp_CloseHandle
0x180016550  mov     rdi, [rbx]
0x180016553  test    rdi, rdi
0x180016556  jz      short loc_18001656B
0x180016558  mov     rcx, rdi; this
0x18001655b  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180016560  mov     rdx, r14; unsigned __int64
0x180016563  mov     rcx, rdi; void *
0x180016566  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001656b  mov     rdx, rsi; unsigned __int64
0x18001656e  mov     rcx, rbx; void *
0x180016571  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016576  nop
0x180016577  mov     rbx, [r15]
0x18001657a  test    rbx, rbx
0x18001657d  jz      short loc_1800165BE
0x18001657f  lea     rcx, [rbx+38h]
0x180016583  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016588  lea     rcx, [rbx+18h]
0x18001658c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016591  mov     rcx, [rbx+8]; void *
0x180016595  test    rcx, rcx
0x180016598  jz      short loc_18001659F
0x18001659a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001659f  mov     rcx, [rbx]; void *
0x1800165a2  test    rcx, rcx
0x1800165a5  jz      short loc_1800165B1
0x1800165a7  mov     edx, 18h; unsigned __int64
0x1800165ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800165b1  mov     edx, 58h ; 'X'; unsigned __int64
0x1800165b6  mov     rcx, rbx; void *
0x1800165b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800165be  mov     eax, r13d
0x1800165c1  jmp     loc_18001673B
0x1800165c6  mov     rcx, rbx; _Mtx_t
0x1800165c9  call    cs:__imp__Mtx_unlock
0x1800165cf  nop
0x1800165d0  mov     edx, 3E3h; dwExitCode
0x1800165d5  mov     rcx, r12; hThread
0x1800165d8  call    cs:__imp_TerminateThread
0x1800165de  nop
0x1800165df  mov     rbx, [rsp+0A8h+var_78]
0x1800165e4  test    rbx, rbx
0x1800165e7  jz      short loc_180016624
0x1800165e9  mov     rcx, [rbx+8]; hObject
0x1800165ed  lea     rax, [rcx-1]
0x1800165f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800165f5  ja      short loc_1800165FD
0x1800165f7  call    cs:__imp_CloseHandle
0x1800165fd  mov     rdi, [rbx]
0x180016600  test    rdi, rdi
0x180016603  jz      short loc_180016618
0x180016605  mov     rcx, rdi; this
0x180016608  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x18001660d  mov     rdx, r14; unsigned __int64
0x180016610  mov     rcx, rdi; void *
0x180016613  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016618  mov     rdx, rsi; unsigned __int64
0x18001661b  mov     rcx, rbx; void *
0x18001661e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016623  nop
0x180016624  mov     rbx, [r15]
0x180016627  test    rbx, rbx
0x18001662a  jz      short loc_18001666B
0x18001662c  lea     rcx, [rbx+38h]
0x180016630  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180016635  lea     rcx, [rbx+18h]
0x180016639  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001663e  mov     rcx, [rbx+8]; void *
0x180016642  test    rcx, rcx
0x180016645  jz      short loc_18001664C
0x180016647  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001664c  mov     rcx, [rbx]; void *
0x18001664f  test    rcx, rcx
0x180016652  jz      short loc_18001665E
0x180016654  mov     edx, 18h; unsigned __int64
0x180016659  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001665e  mov     edx, 58h ; 'X'; unsigned __int64
0x180016663  mov     rcx, rbx; void *
0x180016666  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001666b  xor     eax, eax
0x18001666d  jmp     loc_18001673B
0x180016672  mov     rcx, [rsp+0A8h+arg_0]; _Mtx_t
0x18001667a  call    cs:__imp__Mtx_unlock
0x180016680  nop
0x180016681  mov     edx, 3E3h; dwExitCode
  ... truncated ...
```
