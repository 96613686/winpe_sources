# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18002f15c`
- end: `0x18002f1c3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180028830`
- `0x18002ad6c`

## callees

- `0x18002f15c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f165`

## string_xrefs

- `0x18002f181`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18002f15c  push    rbx
0x18002f15e  sub     rsp, 20h
0x18002f162  mov     rbx, rcx
0x18002f165  call    cs:__imp_GetCurrentThreadId
0x18002f16b  cmp     [rbx+18h], eax
0x18002f16e  jz      short loc_18002F18D
0x18002f170  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002f177  test    rax, rax
0x18002f17a  jz      short loc_18002F18D
0x18002f17c  mov     rdx, [rsp+28h]
0x18002f181  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002f188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f18d  mov     rcx, [rbx]
0x18002f190  mov     dword ptr [rbx+18h], 0
0x18002f197  jmp     short loc_18002F1A5
0x18002f199  cmp     rax, rbx
0x18002f19c  jz      short loc_18002F1AF
0x18002f19e  lea     rcx, [rax+10h]
0x18002f1a2  mov     [rbx], rcx
0x18002f1a5  mov     rax, [rcx]
0x18002f1a8  test    rax, rax
0x18002f1ab  jnz     short loc_18002F199
0x18002f1ad  jmp     short loc_18002F1B6
0x18002f1af  mov     rax, [rbx+10h]
0x18002f1b3  mov     [rcx], rax
0x18002f1b6  mov     qword ptr [rbx], 0
0x18002f1bd  add     rsp, 20h
0x18002f1c1  pop     rbx
0x18002f1c2  retn
```
