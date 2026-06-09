# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180027890`
- end: `0x1800278fe`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d8c0`
- `0x18000da60`
- `0x18000e280`
- `0x18000e6a0`
- `0x18000f234`
- `0x180027864`
- `0x1800329f0`
- `0x180033250`

## callees

- `0x180027890`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027899`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027899`

## string_xrefs

- `0x1800278b5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::StopWatching(
        wil::details::ThreadFailureCallbackHolder *this)
{
  wil::details::ThreadFailureCallbackHolder **v2; // rcx
  wil::details::ThreadFailureCallbackHolder *v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) != GetCurrentThreadId() )
  {
    if ( wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
  }
  v2 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  *((_DWORD *)this + 6) = 0;
  v3 = *v2;
  if ( *v2 )
  {
    while ( v3 != this )
    {
      v2 = (wil::details::ThreadFailureCallbackHolder **)((char *)v3 + 16);
      *(_QWORD *)this = (char *)v3 + 16;
      v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v3 + 2);
      if ( !v3 )
      {
        *(_QWORD *)this = 0;
        return;
      }
    }
    *v2 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
  }
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180027890  push    rbx
0x180027892  sub     rsp, 20h
0x180027896  mov     rbx, rcx
0x180027899  call    cs:__imp_GetCurrentThreadId
0x18002789f  cmp     [rbx+18h], eax
0x1800278a2  jz      short loc_1800278C1
0x1800278a4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA; __annotation("Debug", "TelemetryAssert", "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread")
0x1800278ab  test    rax, rax
0x1800278ae  jz      short loc_1800278C1
0x1800278b0  mov     rdx, [rsp+28h]
0x1800278b5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800278bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278c1  mov     rcx, [rbx]
0x1800278c4  xor     edx, edx
0x1800278c6  mov     [rbx+18h], edx
0x1800278c9  mov     rax, [rcx]
0x1800278cc  test    rax, rax
0x1800278cf  jz      short loc_1800278F5
0x1800278d1  cmp     rax, rbx
0x1800278d4  jz      short loc_1800278EE
0x1800278d6  lea     rcx, [rax+10h]
0x1800278da  mov     [rbx], rcx
0x1800278dd  mov     rax, [rcx]
0x1800278e0  test    rax, rax
0x1800278e3  jnz     short loc_1800278D1
0x1800278e5  mov     [rbx], rdx
0x1800278e8  add     rsp, 20h
0x1800278ec  pop     rbx
0x1800278ed  retn
0x1800278ee  mov     rax, [rbx+10h]
0x1800278f2  mov     [rcx], rax
0x1800278f5  mov     [rbx], rdx
0x1800278f8  add     rsp, 20h
0x1800278fc  pop     rbx
0x1800278fd  retn
```
