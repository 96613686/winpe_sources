# OrchestratorSingleton::ModuleThreadData::CreateAndSetThreadHandle(void)

- ea: `0x1800125ec`
- end: `0x180012673`
- name: `?CreateAndSetThreadHandle@ModuleThreadData@OrchestratorSingleton@@QEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180015d70`
- `0x180016208`

## callees

- `0x180009024`
- `0x1800125ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012617`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001262e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001262e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012641`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012639`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012639`

## pseudocode

```c
__int64 __fastcall OrchestratorSingleton::ModuleThreadData::CreateAndSetThreadHandle(LPVOID *this)
{
  HANDLE Thread; // rax
  const char *v3; // r9
  char *v4; // rbp
  HANDLE v5; // rdi
  DWORD LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Thread = CreateThread(0, 0, OrchestratorSingleton::ModuleThreadProc, *this, 4u, 0);
  v4 = (char *)this[1];
  v5 = Thread;
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v4);
    SetLastError(LastError);
  }
  this[1] = v5;
  if ( v5 )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x80,
             (unsigned int)"pcshell\\base\\whesvc\\lib\\OrchestratorSingletonDefinition.h",
             v3);
}

```

## disassembly

```asm
0x1800125ec  push    rbx
0x1800125ee  push    rbp
0x1800125ef  push    rsi
0x1800125f0  push    rdi
0x1800125f1  sub     rsp, 38h
0x1800125f5  mov     r9, [rcx]; lpParameter
0x1800125f8  lea     r8, ?ModuleThreadProc@OrchestratorSingleton@@CAKPEAX@Z; lpStartAddress
0x1800125ff  mov     rsi, rcx
0x180012602  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18001260b  xor     ecx, ecx; lpThreadAttributes
0x18001260d  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x180012615  xor     edx, edx; dwStackSize
0x180012617  call    cs:__imp_CreateThread
0x18001261d  mov     rbp, [rsi+8]
0x180012621  mov     rdi, rax
0x180012624  lea     rdx, [rbp-1]
0x180012628  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001262c  ja      short loc_180012647
0x18001262e  call    cs:__imp_GetLastError
0x180012634  mov     rcx, rbp; hObject
0x180012637  mov     ebx, eax
0x180012639  call    cs:__imp_CloseHandle
0x18001263f  mov     ecx, ebx; dwErrCode
0x180012641  call    cs:__imp_SetLastError
0x180012647  mov     [rsi+8], rdi
0x18001264b  test    rdi, rdi
0x18001264e  jnz     short loc_180012668
0x180012650  mov     rcx, [rsp+58h]; this
0x180012655  lea     r8, aPcshellBaseWhe_1; "pcshell\\base\\whesvc\\lib\\Orchestrato"...
0x18001265c  mov     edx, 80h; void *
0x180012661  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012666  jmp     short loc_18001266A
0x180012668  xor     eax, eax
0x18001266a  add     rsp, 38h
0x18001266e  pop     rdi
0x18001266f  pop     rsi
0x180012670  pop     rbp
0x180012671  pop     rbx
0x180012672  retn
```
