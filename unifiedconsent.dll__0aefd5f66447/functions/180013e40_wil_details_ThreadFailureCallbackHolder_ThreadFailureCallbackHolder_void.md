# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x180013e40`
- end: `0x180013eb8`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180013bd0`
- `0x180018380`
- `0x180022f20`
- `0x180022f70`
- `0x180022fc0`
- `0x1800254a8`
- `0x18002be40`
- `0x180040520`
- `0x180040794`
- `0x180041410`
- `0x18005878c`
- `0x1800587dc`
- `0x18005882c`
- `0x180059840`
- `0x18005ba20`
- `0x18005d2e8`
- `0x180060f60`
- `0x180061d10`
- `0x1800695ec`
- `0x18006a080`

## callees

- `0x180013e40`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013e56`

## string_xrefs

- `0x180013e71`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  int v2; // ebx
  wil::details::ThreadFailureCallbackHolder **v3; // rcx
  wil::details::ThreadFailureCallbackHolder *v4; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    v2 = *((_DWORD *)this + 6);
    if ( v2 != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)this + 6) = 0;
    v3 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    while ( 1 )
    {
      v4 = *v3;
      if ( !*v3 )
        break;
      if ( v4 == this )
      {
        *v3 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v3 = (wil::details::ThreadFailureCallbackHolder **)((char *)v4 + 16);
      *(_QWORD *)this = (char *)v4 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180013e40  mov     [rsp+arg_0], rbx
0x180013e45  push    rdi
0x180013e46  sub     rsp, 20h
0x180013e4a  mov     rdi, rcx
0x180013e4d  cmp     dword ptr [rcx+18h], 0
0x180013e51  jz      short loc_180013EAD
0x180013e53  mov     ebx, [rcx+18h]
0x180013e56  call    cs:__imp_GetCurrentThreadId
0x180013e5c  cmp     ebx, eax
0x180013e5e  jz      short loc_180013E7D
0x180013e60  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180013e67  test    rax, rax
0x180013e6a  jz      short loc_180013E7D
0x180013e6c  mov     rdx, [rsp+28h]
0x180013e71  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180013e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e7d  mov     dword ptr [rdi+18h], 0
0x180013e84  mov     rcx, [rdi]
0x180013e87  jmp     short loc_180013E95
0x180013e89  cmp     rax, rdi
0x180013e8c  jz      short loc_180013E9F
0x180013e8e  lea     rcx, [rax+10h]
0x180013e92  mov     [rdi], rcx
0x180013e95  mov     rax, [rcx]
0x180013e98  test    rax, rax
0x180013e9b  jnz     short loc_180013E89
0x180013e9d  jmp     short loc_180013EA6
0x180013e9f  mov     rax, [rdi+10h]
0x180013ea3  mov     [rcx], rax
0x180013ea6  mov     qword ptr [rdi], 0
0x180013ead  mov     rbx, [rsp+28h+arg_0]
0x180013eb2  add     rsp, 20h
0x180013eb6  pop     rdi
0x180013eb7  retn
```
