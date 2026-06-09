# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x18000a6c4`
- end: `0x18000a73c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a4f0`
- `0x18001ba1c`
- `0x1800221ec`

## callees

- `0x18000a6c4`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6da`

## string_xrefs

- `0x18000a6f5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
    *((_DWORD *)this + 6) = 0;
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
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
0x18000a6c4  mov     [rsp+arg_0], rbx
0x18000a6c9  push    rdi
0x18000a6ca  sub     rsp, 20h
0x18000a6ce  mov     rdi, rcx
0x18000a6d1  cmp     dword ptr [rcx+18h], 0
0x18000a6d5  jz      short loc_18000A731
0x18000a6d7  mov     ebx, [rcx+18h]
0x18000a6da  call    cs:__imp_GetCurrentThreadId
0x18000a6e0  cmp     ebx, eax
0x18000a6e2  jz      short loc_18000A701
0x18000a6e4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000a6eb  test    rax, rax
0x18000a6ee  jz      short loc_18000A701
0x18000a6f0  mov     rdx, [rsp+28h]
0x18000a6f5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000a6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a701  mov     dword ptr [rdi+18h], 0
0x18000a708  mov     rcx, [rdi]
0x18000a70b  jmp     short loc_18000A719
0x18000a70d  cmp     rax, rdi
0x18000a710  jz      short loc_18000A723
0x18000a712  lea     rcx, [rax+10h]
0x18000a716  mov     [rdi], rcx
0x18000a719  mov     rax, [rcx]
0x18000a71c  test    rax, rax
0x18000a71f  jnz     short loc_18000A70D
0x18000a721  jmp     short loc_18000A72A
0x18000a723  mov     rax, [rdi+10h]
0x18000a727  mov     [rcx], rax
0x18000a72a  mov     qword ptr [rdi], 0
0x18000a731  mov     rbx, [rsp+28h+arg_0]
0x18000a736  add     rsp, 20h
0x18000a73a  pop     rdi
0x18000a73b  retn
```
