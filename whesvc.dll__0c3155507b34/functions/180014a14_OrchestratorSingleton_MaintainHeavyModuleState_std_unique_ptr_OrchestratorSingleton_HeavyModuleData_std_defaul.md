# OrchestratorSingleton::MaintainHeavyModuleState(std::unique_ptr<OrchestratorSingleton::HeavyModuleData,std::default_delete<OrchestratorSingleton::HeavyModuleData>>)

- ea: `0x180014a14`
- end: `0x180014beb`
- name: `?MaintainHeavyModuleState@OrchestratorSingleton@@AEAAXV?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@@Z`
- size: `471`
- prototype: `void __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180014398`

## callees

- `0x180003304`
- `0x180009024`
- `0x180011904`
- `0x180011bf8`
- `0x180014964`
- `0x180014a14`
- `0x180015d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014b30`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180014b30`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014a36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014b5a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014b86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014a36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014b5a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014b86`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014a69`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014a69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ba4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ba4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180014aef`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180014aef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall OrchestratorSingleton::MaintainHeavyModuleState(__int64 a1, void **a2)
{
  HANDLE *v2; // rbx
  char *v5; // rcx
  const char *v6; // r9
  __int64 *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // rax
  int started; // eax
  DWORD v11; // eax
  unsigned int v12; // r8d
  const char *v13; // r9
  char *v14; // rcx
  const char *v15; // r9
  unsigned int v16; // r8d
  const char *v17; // r9
  char *v18; // rcx
  HANDLE v19; // rdi
  HANDLE Handles[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE *v22; // [rsp+40h] [rbp+8h] BYREF
  __int64 v23; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v22 = 0;
  while ( WaitForSingleObject(*(HANDLE *)(a1 + 88), 0) )
  {
    if ( *(_BYTE *)(a1 + 280) )
    {
      if ( v2 )
      {
        v5 = (char *)*((_QWORD *)*v2 + 1);
        if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !SetEvent(v5) )
          wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x1A7,
            (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
            v6);
      }
      else
      {
        v7 = (__int64 *)*a2;
        v8 = (char *)*a2 + 8;
        if ( *((_QWORD *)*a2 + 4) > 0xFu )
          v8 = (_QWORD *)*v8;
        v9 = *v7;
        *v7 = 0;
        v23 = v9;
        started = OrchestratorSingleton::StartHeavyModule(a1, &v23, v8, &v22);
        v2 = v22;
        if ( started < 0 )
          goto LABEL_22;
      }
      Handles[0] = *(HANDLE *)(a1 + 272);
      Handles[1] = v2[1];
      v11 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( v11 )
      {
        if ( v11 == 1 )
          goto LABEL_23;
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x1C5, v12, v13);
      }
    }
    else
    {
      if ( v2 )
      {
        v14 = (char *)*((_QWORD *)*v2 + 1);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !ResetEvent(v14) )
          wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x198,
            (unsigned int)"pcshell\\base\\whesvc\\lib\\modulehandler.cpp",
            v15);
      }
      if ( WaitForSingleObject(*(HANDLE *)(a1 + 272), 0xFFFFFFFF) == -1 )
      {
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x1D4, v16, v17);
        goto LABEL_22;
      }
    }
  }
  if ( !v2 )
    goto LABEL_29;
  WaitForSingleObject(v2[1], 0xFFFFFFFF);
LABEL_22:
  if ( !v2 )
    goto LABEL_29;
LABEL_23:
  if ( v2 )
  {
    v18 = (char *)v2[1];
    if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v18);
    v19 = *v2;
    if ( *v2 )
    {
      ModuleHandler::~ModuleHandler((ModuleHandler *)*v2);
      operator delete(v19);
    }
    operator delete(v2);
  }
LABEL_29:
  std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(a2);
}

```

## disassembly

```asm
0x180014a14  mov     [rsp+arg_8], rbx
0x180014a19  mov     [rsp+arg_18], rsi
0x180014a1e  push    rdi
0x180014a1f  sub     rsp, 30h
0x180014a23  xor     ebx, ebx
0x180014a25  mov     rsi, rdx
0x180014a28  mov     [rsp+38h+arg_0], rbx
0x180014a2d  mov     rdi, rcx
0x180014a30  mov     rcx, [rdi+58h]; hHandle
0x180014a34  xor     edx, edx; dwMilliseconds
0x180014a36  call    cs:__imp_WaitForSingleObject
0x180014a3c  test    eax, eax
0x180014a3e  jz      loc_180014B7A
0x180014a44  mov     al, [rdi+118h]
0x180014a4a  nop
0x180014a4b  test    al, al
0x180014a4d  jz      loc_180014B1A
0x180014a53  test    rbx, rbx
0x180014a56  jz      short loc_180014A8B
0x180014a58  mov     rax, [rbx]
0x180014a5b  mov     rcx, [rax+8]; hEvent
0x180014a5f  lea     rax, [rcx-1]
0x180014a63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014a67  ja      short loc_180014ACA
0x180014a69  call    cs:__imp_SetEvent
0x180014a6f  test    eax, eax
0x180014a71  jnz     short loc_180014ACA
0x180014a73  mov     rcx, [rsp+38h]; this
0x180014a78  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180014a7f  mov     edx, 1A7h; void *
0x180014a84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014a89  jmp     short loc_180014ACA
0x180014a8b  mov     rcx, [rsi]
0x180014a8e  cmp     qword ptr [rcx+20h], 0Fh
0x180014a93  lea     r8, [rcx+8]
0x180014a97  jbe     short loc_180014A9C
0x180014a99  mov     r8, [r8]
0x180014a9c  mov     rax, [rcx]
0x180014a9f  lea     r9, [rsp+38h+arg_0]
0x180014aa4  mov     qword ptr [rcx], 0
0x180014aab  lea     rdx, [rsp+38h+arg_10]
0x180014ab0  mov     rcx, rdi
0x180014ab3  mov     [rsp+38h+arg_10], rax
0x180014ab8  call    ?StartHeavyModule@OrchestratorSingleton@@AEAAJV?$unique_ptr@VWindiagModuleWrapper@@U?$default_delete@VWindiagModuleWrapper@@@std@@@std@@PEBDAEAV?$unique_ptr@UModuleThreadData@OrchestratorSingleton@@U?$default_delete@UModuleThreadData@OrchestratorSingleton@@@std@@@3@@Z; OrchestratorSingleton::StartHeavyModule(std::unique_ptr<WindiagModuleWrapper>,char const *,std::unique_ptr<OrchestratorSingleton::ModuleThreadData> &)
0x180014abd  mov     rbx, [rsp+38h+arg_0]
0x180014ac2  test    eax, eax
0x180014ac4  js      loc_180014B8C
0x180014aca  mov     rax, [rdi+110h]
0x180014ad1  lea     rdx, [rsp+38h+Handles]; lpHandles
0x180014ad6  xor     r8d, r8d; bWaitAll
0x180014ad9  mov     [rsp+38h+Handles], rax
0x180014ade  mov     rax, [rbx+8]
0x180014ae2  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180014ae6  mov     [rsp+38h+var_10], rax
0x180014aeb  lea     ecx, [r8+2]; nCount
0x180014aef  call    cs:__imp_WaitForMultipleObjects
0x180014af5  test    eax, eax
0x180014af7  jz      loc_180014A30
0x180014afd  cmp     eax, 1
0x180014b00  jz      loc_180014B91
0x180014b06  mov     rcx, [rsp+38h]; this
0x180014b0b  mov     edx, 1C5h; void *
0x180014b10  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180014b15  jmp     loc_180014A30
0x180014b1a  test    rbx, rbx
0x180014b1d  jz      short loc_180014B50
0x180014b1f  mov     rax, [rbx]
0x180014b22  mov     rcx, [rax+8]; hEvent
0x180014b26  lea     rax, [rcx-1]
0x180014b2a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014b2e  ja      short loc_180014B50
0x180014b30  call    cs:__imp_ResetEvent
0x180014b36  test    eax, eax
0x180014b38  jnz     short loc_180014B50
0x180014b3a  mov     rcx, [rsp+38h]; this
0x180014b3f  lea     r8, aPcshellBaseWhe_2; "pcshell\\base\\whesvc\\lib\\modulehandl"...
0x180014b46  mov     edx, 198h; void *
0x180014b4b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014b50  mov     rcx, [rdi+110h]; hHandle
0x180014b57  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014b5a  call    cs:__imp_WaitForSingleObject
0x180014b60  cmp     eax, 0FFFFFFFFh
0x180014b63  jnz     loc_180014A30
0x180014b69  mov     rcx, [rsp+38h]; this
0x180014b6e  mov     edx, 1D4h; void *
0x180014b73  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180014b78  jmp     short loc_180014B8C
0x180014b7a  test    rbx, rbx
0x180014b7d  jz      short loc_180014BD4
0x180014b7f  mov     rcx, [rbx+8]; hHandle
0x180014b83  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014b86  call    cs:__imp_WaitForSingleObject
0x180014b8c  test    rbx, rbx
0x180014b8f  jz      short loc_180014BD4
0x180014b91  test    rbx, rbx
0x180014b94  jz      short loc_180014BD4
0x180014b96  mov     rcx, [rbx+8]; hObject
0x180014b9a  lea     rax, [rcx-1]
0x180014b9e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014ba2  ja      short loc_180014BAA
0x180014ba4  call    cs:__imp_CloseHandle
0x180014baa  mov     rdi, [rbx]
0x180014bad  test    rdi, rdi
0x180014bb0  jz      short loc_180014BC7
0x180014bb2  mov     rcx, rdi; this
0x180014bb5  call    ??1ModuleHandler@@QEAA@XZ; ModuleHandler::~ModuleHandler(void)
0x180014bba  mov     edx, 178h; unsigned __int64
0x180014bbf  mov     rcx, rdi; void *
0x180014bc2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014bc7  mov     edx, 10h; unsigned __int64
0x180014bcc  mov     rcx, rbx; void *
0x180014bcf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014bd4  mov     rcx, rsi
0x180014bd7  mov     rbx, [rsp+38h+arg_8]
0x180014bdc  mov     rsi, [rsp+38h+arg_18]
0x180014be1  add     rsp, 30h
0x180014be5  pop     rdi
0x180014be6  jmp     ??1?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ; std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(void)
```
