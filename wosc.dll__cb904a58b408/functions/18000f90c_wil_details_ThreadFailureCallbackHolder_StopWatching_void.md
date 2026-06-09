# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000f90c`
- end: `0x18000f973`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a71c`
- `0x18000c5a8`

## callees

- `0x18000f90c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f915`

## string_xrefs

- `0x18000f931`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000f90c  push    rbx
0x18000f90e  sub     rsp, 20h
0x18000f912  mov     rbx, rcx
0x18000f915  call    cs:__imp_GetCurrentThreadId
0x18000f91b  cmp     [rbx+18h], eax
0x18000f91e  jz      short loc_18000F93D
0x18000f920  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000f927  test    rax, rax
0x18000f92a  jz      short loc_18000F93D
0x18000f92c  mov     rdx, [rsp+28h]
0x18000f931  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000f938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f93d  mov     rcx, [rbx]
0x18000f940  mov     dword ptr [rbx+18h], 0
0x18000f947  jmp     short loc_18000F955
0x18000f949  cmp     rax, rbx
0x18000f94c  jz      short loc_18000F95F
0x18000f94e  lea     rcx, [rax+10h]
0x18000f952  mov     [rbx], rcx
0x18000f955  mov     rax, [rcx]
0x18000f958  test    rax, rax
0x18000f95b  jnz     short loc_18000F949
0x18000f95d  jmp     short loc_18000F966
0x18000f95f  mov     rax, [rbx+10h]
0x18000f963  mov     [rcx], rax
0x18000f966  mov     qword ptr [rbx], 0
0x18000f96d  add     rsp, 20h
0x18000f971  pop     rbx
0x18000f972  retn
```
