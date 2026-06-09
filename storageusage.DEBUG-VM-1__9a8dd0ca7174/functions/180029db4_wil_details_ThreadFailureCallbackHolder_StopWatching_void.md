# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180029db4`
- end: `0x180029e1b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800271c8`
- `0x180027a34`

## callees

- `0x180029db4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029dbd`

## string_xrefs

- `0x180029dd9`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180029db4  push    rbx
0x180029db6  sub     rsp, 20h
0x180029dba  mov     rbx, rcx
0x180029dbd  call    cs:__imp_GetCurrentThreadId
0x180029dc3  cmp     [rbx+18h], eax
0x180029dc6  jz      short loc_180029DE5
0x180029dc8  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180029dcf  test    rax, rax
0x180029dd2  jz      short loc_180029DE5
0x180029dd4  mov     rdx, [rsp+28h]
0x180029dd9  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180029de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029de5  mov     rcx, [rbx]
0x180029de8  mov     dword ptr [rbx+18h], 0
0x180029def  jmp     short loc_180029DFD
0x180029df1  cmp     rax, rbx
0x180029df4  jz      short loc_180029E07
0x180029df6  lea     rcx, [rax+10h]
0x180029dfa  mov     [rbx], rcx
0x180029dfd  mov     rax, [rcx]
0x180029e00  test    rax, rax
0x180029e03  jnz     short loc_180029DF1
0x180029e05  jmp     short loc_180029E0E
0x180029e07  mov     rax, [rbx+10h]
0x180029e0b  mov     [rcx], rax
0x180029e0e  mov     qword ptr [rbx], 0
0x180029e15  add     rsp, 20h
0x180029e19  pop     rbx
0x180029e1a  retn
```
