# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180046c70`
- end: `0x180046cd7`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180045a10`
- `0x180045b38`

## callees

- `0x180046c70`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046c79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046c79`

## string_xrefs

- `0x180046c95`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180046c70  push    rbx
0x180046c72  sub     rsp, 20h
0x180046c76  mov     rbx, rcx
0x180046c79  call    cs:__imp_GetCurrentThreadId
0x180046c7f  cmp     [rbx+18h], eax
0x180046c82  jz      short loc_180046CA1
0x180046c84  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180046c8b  test    rax, rax
0x180046c8e  jz      short loc_180046CA1
0x180046c90  mov     rdx, [rsp+28h]
0x180046c95  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180046c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ca1  mov     rcx, [rbx]
0x180046ca4  mov     dword ptr [rbx+18h], 0
0x180046cab  jmp     short loc_180046CB9
0x180046cad  cmp     rax, rbx
0x180046cb0  jz      short loc_180046CC3
0x180046cb2  lea     rcx, [rax+10h]
0x180046cb6  mov     [rbx], rcx
0x180046cb9  mov     rax, [rcx]
0x180046cbc  test    rax, rax
0x180046cbf  jnz     short loc_180046CAD
0x180046cc1  jmp     short loc_180046CCA
0x180046cc3  mov     rax, [rbx+10h]
0x180046cc7  mov     [rcx], rax
0x180046cca  mov     qword ptr [rbx], 0
0x180046cd1  add     rsp, 20h
0x180046cd5  pop     rbx
0x180046cd6  retn
```
