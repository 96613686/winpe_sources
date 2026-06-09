# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x1800088cc`
- end: `0x180008933`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005384`
- `0x1800067f4`

## callees

- `0x1800088cc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800088d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800088d5`

## string_xrefs

- `0x1800088f1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800088cc  push    rbx
0x1800088ce  sub     rsp, 20h
0x1800088d2  mov     rbx, rcx
0x1800088d5  call    cs:__imp_GetCurrentThreadId
0x1800088db  cmp     [rbx+18h], eax
0x1800088de  jz      short loc_1800088FD
0x1800088e0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800088e7  test    rax, rax
0x1800088ea  jz      short loc_1800088FD
0x1800088ec  mov     rdx, [rsp+28h]
0x1800088f1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800088f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088fd  mov     rcx, [rbx]
0x180008900  mov     dword ptr [rbx+18h], 0
0x180008907  jmp     short loc_180008915
0x180008909  cmp     rax, rbx
0x18000890c  jz      short loc_18000891F
0x18000890e  lea     rcx, [rax+10h]
0x180008912  mov     [rbx], rcx
0x180008915  mov     rax, [rcx]
0x180008918  test    rax, rax
0x18000891b  jnz     short loc_180008909
0x18000891d  jmp     short loc_180008926
0x18000891f  mov     rax, [rbx+10h]
0x180008923  mov     [rcx], rax
0x180008926  mov     qword ptr [rbx], 0
0x18000892d  add     rsp, 20h
0x180008931  pop     rbx
0x180008932  retn
```
