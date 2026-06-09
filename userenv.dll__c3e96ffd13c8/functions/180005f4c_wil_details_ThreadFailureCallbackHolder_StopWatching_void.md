# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180005f4c`
- end: `0x180005fb3`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000584c`
- `0x180012c48`

## callees

- `0x180005f4c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f55`

## string_xrefs

- `0x180005f71`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005f4c  push    rbx
0x180005f4e  sub     rsp, 20h
0x180005f52  mov     rbx, rcx
0x180005f55  call    cs:__imp_GetCurrentThreadId
0x180005f5b  cmp     [rbx+18h], eax
0x180005f5e  jz      short loc_180005F7D
0x180005f60  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180005f67  test    rax, rax
0x180005f6a  jz      short loc_180005F7D
0x180005f6c  mov     rdx, [rsp+28h]
0x180005f71  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180005f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f7d  mov     rcx, [rbx]
0x180005f80  mov     dword ptr [rbx+18h], 0
0x180005f87  jmp     short loc_180005F95
0x180005f89  cmp     rax, rbx
0x180005f8c  jz      short loc_180005F9F
0x180005f8e  lea     rcx, [rax+10h]
0x180005f92  mov     [rbx], rcx
0x180005f95  mov     rax, [rcx]
0x180005f98  test    rax, rax
0x180005f9b  jnz     short loc_180005F89
0x180005f9d  jmp     short loc_180005FA6
0x180005f9f  mov     rax, [rbx+10h]
0x180005fa3  mov     [rcx], rax
0x180005fa6  mov     qword ptr [rbx], 0
0x180005fad  add     rsp, 20h
0x180005fb1  pop     rbx
0x180005fb2  retn
```
