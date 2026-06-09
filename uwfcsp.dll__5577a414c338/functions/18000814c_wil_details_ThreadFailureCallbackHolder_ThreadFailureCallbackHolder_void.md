# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000814c`
- end: `0x1800081c4`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007c58`

## callees

- `0x18000814c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008162`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008162`

## string_xrefs

- `0x18000817d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder **v3; // rcx
  wil::details::ThreadFailureCallbackHolder *v4; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    v2 = *((_DWORD *)this + 6);
    if ( v2 != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    *((_DWORD *)this + 6) = 0;
    while ( 1 )
    {
      v4 = *v3;
      if ( !*v3 )
        break;
      if ( v4 == this )
      {
        *v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v3 = (wil::details::ThreadFailureCallbackHolder **)((char *)v4 + 16);
      *(_QWORD *)this = (char *)v4 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000814c  mov     [rsp+arg_0], rbx
0x180008151  push    rdi
0x180008152  sub     rsp, 20h
0x180008156  cmp     dword ptr [rcx+18h], 0
0x18000815a  mov     rdi, rcx
0x18000815d  jz      short loc_1800081B9
0x18000815f  mov     ebx, [rcx+18h]
0x180008162  call    cs:__imp_GetCurrentThreadId
0x180008168  cmp     ebx, eax
0x18000816a  jz      short loc_180008189
0x18000816c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180008173  test    rax, rax
0x180008176  jz      short loc_180008189
0x180008178  mov     rdx, [rsp+28h]
0x18000817d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180008184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008189  mov     rcx, [rdi]
0x18000818c  mov     dword ptr [rdi+18h], 0
0x180008193  jmp     short loc_1800081A1
0x180008195  cmp     rax, rdi
0x180008198  jz      short loc_1800081AB
0x18000819a  lea     rcx, [rax+10h]
0x18000819e  mov     [rdi], rcx
0x1800081a1  mov     rax, [rcx]
0x1800081a4  test    rax, rax
0x1800081a7  jnz     short loc_180008195
0x1800081a9  jmp     short loc_1800081B2
0x1800081ab  mov     rax, [rdi+10h]
0x1800081af  mov     [rcx], rax
0x1800081b2  mov     qword ptr [rdi], 0
0x1800081b9  mov     rbx, [rsp+28h+arg_0]
0x1800081be  add     rsp, 20h
0x1800081c2  pop     rdi
0x1800081c3  retn
```
