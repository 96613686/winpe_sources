# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180025c38`
- end: `0x180025c9f`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800251d8`
- `0x18006cadc`

## callees

- `0x180025c38`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025c41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025c41`

## string_xrefs

- `0x180025c5d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180025c38  push    rbx
0x180025c3a  sub     rsp, 20h
0x180025c3e  mov     rbx, rcx
0x180025c41  call    cs:__imp_GetCurrentThreadId
0x180025c47  cmp     [rbx+18h], eax
0x180025c4a  jz      short loc_180025C69
0x180025c4c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x180025c53  test    rax, rax
0x180025c56  jz      short loc_180025C69
0x180025c58  mov     rdx, [rsp+28h]
0x180025c5d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180025c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c69  mov     rcx, [rbx]
0x180025c6c  mov     dword ptr [rbx+18h], 0
0x180025c73  jmp     short loc_180025C81
0x180025c75  cmp     rax, rbx
0x180025c78  jz      short loc_180025C8B
0x180025c7a  lea     rcx, [rax+10h]
0x180025c7e  mov     [rbx], rcx
0x180025c81  mov     rax, [rcx]
0x180025c84  test    rax, rax
0x180025c87  jnz     short loc_180025C75
0x180025c89  jmp     short loc_180025C92
0x180025c8b  mov     rax, [rbx+10h]
0x180025c8f  mov     [rcx], rax
0x180025c92  mov     qword ptr [rbx], 0
0x180025c99  add     rsp, 20h
0x180025c9d  pop     rbx
0x180025c9e  retn
```
