# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180006718`
- end: `0x180006786`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ff4`
- `0x180013d08`

## callees

- `0x180006718`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006721`

## string_xrefs

- `0x180006743`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180006718  push    rbx
0x18000671a  sub     rsp, 20h
0x18000671e  mov     rbx, rcx
0x180006721  call    cs:__imp_GetCurrentThreadId
0x180006728  nop     dword ptr [rax+rax+00h]
0x18000672d  cmp     [rbx+18h], eax
0x180006730  jz      short loc_18000674F
0x180006732  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180006739  test    rax, rax
0x18000673c  jz      short loc_18000674F
0x18000673e  mov     rdx, [rsp+28h]
0x180006743  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000674a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000674f  mov     rcx, [rbx]
0x180006752  mov     dword ptr [rbx+18h], 0
0x180006759  jmp     short loc_180006767
0x18000675b  cmp     rax, rbx
0x18000675e  jz      short loc_180006771
0x180006760  lea     rcx, [rax+10h]
0x180006764  mov     [rbx], rcx
0x180006767  mov     rax, [rcx]
0x18000676a  test    rax, rax
0x18000676d  jnz     short loc_18000675B
0x18000676f  jmp     short loc_180006778
0x180006771  mov     rax, [rbx+10h]
0x180006775  mov     [rcx], rax
0x180006778  mov     qword ptr [rbx], 0
0x18000677f  add     rsp, 20h
0x180006783  pop     rbx
0x180006784  retn
```
