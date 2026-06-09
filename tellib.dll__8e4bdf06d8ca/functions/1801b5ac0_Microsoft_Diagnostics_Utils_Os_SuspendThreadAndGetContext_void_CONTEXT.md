# Microsoft::Diagnostics::Utils::Os::SuspendThreadAndGetContext(void *,_CONTEXT &)

- ea: `0x1801b5ac0`
- end: `0x1801b5b6b`
- name: `?SuspendThreadAndGetContext@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXAEAU_CONTEXT@@@Z`
- size: `171`
- prototype: `bool __fastcall(HANDLE hThread, LPCONTEXT lpContext)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801b1d8c`
- `0x1801b589c`

## callees

- `0x1800a0d08`
- `0x1801b5ac0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b5ade`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b5ade`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1801b5b2f`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1801b5b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1801b5aed`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1801b5afe`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1801b5aed`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1801b5afe`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x1801b5b48`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x1801b5b48`

## pseudocode

```c
char __fastcall Microsoft::Diagnostics::Utils::Os::SuspendThreadAndGetContext(HANDLE hThread, LPCONTEXT lpContext)
{
  HANDLE CurrentThread; // rax
  DWORD ThreadId; // ebx
  const char *v7; // r9
  char v8; // bl
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !hThread )
    return 0;
  CurrentThread = GetCurrentThread();
  ThreadId = GetThreadId(CurrentThread);
  if ( GetThreadId(hThread) == ThreadId )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC11,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
      v7);
  lpContext->ContextFlags = 1048607;
  if ( SuspendThread(hThread) == -1 )
    return 0;
  v8 = 1;
  GetThreadContext(hThread, lpContext);
  return v8;
}

```

## disassembly

```asm
0x1801b5ac0  mov     [rsp+arg_0], rbx
0x1801b5ac5  mov     [rsp+arg_8], rsi
0x1801b5aca  push    rdi
0x1801b5acb  sub     rsp, 20h
0x1801b5acf  mov     rsi, rdx
0x1801b5ad2  mov     rdi, rcx
0x1801b5ad5  test    rcx, rcx
0x1801b5ad8  jnz     short loc_1801B5ADE
0x1801b5ada  xor     al, al
0x1801b5adc  jmp     short loc_1801B5B5A
0x1801b5ade  call    cs:__imp_GetCurrentThread
0x1801b5ae5  nop     dword ptr [rax+rax+00h]
0x1801b5aea  mov     rcx, rax; Thread
0x1801b5aed  call    cs:__imp_GetThreadId
0x1801b5af4  nop     dword ptr [rax+rax+00h]
0x1801b5af9  mov     rcx, rdi; Thread
0x1801b5afc  mov     ebx, eax
0x1801b5afe  call    cs:__imp_GetThreadId
0x1801b5b05  nop     dword ptr [rax+rax+00h]
0x1801b5b0a  cmp     eax, ebx
0x1801b5b0c  jnz     short loc_1801B5B25
0x1801b5b0e  mov     rcx, [rsp+28h]; this
0x1801b5b13  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1801b5b1a  mov     edx, 0C11h; void *
0x1801b5b1f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1801b5b25  mov     rcx, rdi; hThread
0x1801b5b28  mov     dword ptr [rsi+30h], 10001Fh
0x1801b5b2f  call    cs:__imp_SuspendThread
0x1801b5b36  nop     dword ptr [rax+rax+00h]
0x1801b5b3b  cmp     eax, 0FFFFFFFFh
0x1801b5b3e  jz      short loc_1801B5B56
0x1801b5b40  mov     rdx, rsi; lpContext
0x1801b5b43  mov     rcx, rdi; hThread
0x1801b5b46  mov     bl, 1
0x1801b5b48  call    cs:__imp_GetThreadContext
0x1801b5b4f  nop     dword ptr [rax+rax+00h]
0x1801b5b54  jmp     short loc_1801B5B58
0x1801b5b56  xor     bl, bl
0x1801b5b58  mov     al, bl
0x1801b5b5a  mov     rbx, [rsp+28h+arg_0]
0x1801b5b5f  mov     rsi, [rsp+28h+arg_8]
0x1801b5b64  add     rsp, 20h
0x1801b5b68  pop     rdi
0x1801b5b69  retn
```
