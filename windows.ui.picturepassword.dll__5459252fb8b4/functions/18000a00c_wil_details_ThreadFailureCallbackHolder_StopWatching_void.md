# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000a00c`
- end: `0x18000a073`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e0c`
- `0x180007d94`

## callees

- `0x18000a00c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a015`

## string_xrefs

- `0x18000a031`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000a00c  push    rbx
0x18000a00e  sub     rsp, 20h
0x18000a012  mov     rbx, rcx
0x18000a015  call    cs:__imp_GetCurrentThreadId
0x18000a01b  cmp     [rbx+18h], eax
0x18000a01e  jz      short loc_18000A03D
0x18000a020  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000a027  test    rax, rax
0x18000a02a  jz      short loc_18000A03D
0x18000a02c  mov     rdx, [rsp+28h]
0x18000a031  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000a038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a03d  mov     rcx, [rbx]
0x18000a040  mov     dword ptr [rbx+18h], 0
0x18000a047  jmp     short loc_18000A055
0x18000a049  cmp     rax, rbx
0x18000a04c  jz      short loc_18000A05F
0x18000a04e  lea     rcx, [rax+10h]
0x18000a052  mov     [rbx], rcx
0x18000a055  mov     rax, [rcx]
0x18000a058  test    rax, rax
0x18000a05b  jnz     short loc_18000A049
0x18000a05d  jmp     short loc_18000A066
0x18000a05f  mov     rax, [rbx+10h]
0x18000a063  mov     [rcx], rax
0x18000a066  mov     qword ptr [rbx], 0
0x18000a06d  add     rsp, 20h
0x18000a071  pop     rbx
0x18000a072  retn
```
