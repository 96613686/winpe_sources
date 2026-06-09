# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18005ffb0`
- end: `0x18006001e`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005e9a0`

## callees

- `0x18005ffb0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ffb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ffb9`

## string_xrefs

- `0x18005ffdb`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **v2; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  v2 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v3 = *v2;
    if ( !*v2 )
      break;
    if ( v3 == this )
    {
      *v2 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
      break;
    }
    v2 = (wil::details::ThreadFailureCallbackHolder **)((char *)v3 + 16);
    *(_QWORD *)this = (char *)v3 + 16;
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18005ffb0  push    rbx
0x18005ffb2  sub     rsp, 20h
0x18005ffb6  mov     rbx, rcx
0x18005ffb9  call    cs:__imp_GetCurrentThreadId
0x18005ffc0  nop     dword ptr [rax+rax+00h]
0x18005ffc5  cmp     [rbx+18h], eax
0x18005ffc8  jz      short loc_18005FFE7
0x18005ffca  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18005ffd1  test    rax, rax
0x18005ffd4  jz      short loc_18005FFE7
0x18005ffd6  mov     rdx, [rsp+28h]
0x18005ffdb  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18005ffe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ffe7  mov     rcx, [rbx]
0x18005ffea  mov     dword ptr [rbx+18h], 0
0x18005fff1  jmp     short loc_18005FFFF
0x18005fff3  cmp     rax, rbx
0x18005fff6  jz      short loc_180060009
0x18005fff8  lea     rcx, [rax+10h]
0x18005fffc  mov     [rbx], rcx
0x18005ffff  mov     rax, [rcx]
0x180060002  test    rax, rax
0x180060005  jnz     short loc_18005FFF3
0x180060007  jmp     short loc_180060010
0x180060009  mov     rax, [rbx+10h]
0x18006000d  mov     [rcx], rax
0x180060010  mov     qword ptr [rbx], 0
0x180060017  add     rsp, 20h
0x18006001b  pop     rbx
0x18006001c  retn
```
