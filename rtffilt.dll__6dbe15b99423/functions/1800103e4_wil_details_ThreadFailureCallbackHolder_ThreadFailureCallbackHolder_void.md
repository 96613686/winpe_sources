# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800103e4`
- end: `0x18001045c`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `120`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fec4`
- `0x18000ff14`
- `0x180010b80`
- `0x180010f28`
- `0x180011994`

## callees

- `0x1800103e4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103fa`

## string_xrefs

- `0x180010415`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x1800103e4  mov     [rsp+arg_0], rbx
0x1800103e9  push    rdi
0x1800103ea  sub     rsp, 20h
0x1800103ee  mov     rdi, rcx
0x1800103f1  cmp     dword ptr [rcx+18h], 0
0x1800103f5  jz      short loc_180010451
0x1800103f7  mov     ebx, [rcx+18h]
0x1800103fa  call    cs:__imp_GetCurrentThreadId
0x180010400  cmp     ebx, eax
0x180010402  jz      short loc_180010421
0x180010404  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18001040b  test    rax, rax
0x18001040e  jz      short loc_180010421
0x180010410  mov     rdx, [rsp+28h]
0x180010415  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18001041c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010421  mov     dword ptr [rdi+18h], 0
0x180010428  mov     rcx, [rdi]
0x18001042b  jmp     short loc_180010439
0x18001042d  cmp     rax, rdi
0x180010430  jz      short loc_180010443
0x180010432  lea     rcx, [rax+10h]
0x180010436  mov     [rdi], rcx
0x180010439  mov     rax, [rcx]
0x18001043c  test    rax, rax
0x18001043f  jnz     short loc_18001042D
0x180010441  jmp     short loc_18001044A
0x180010443  mov     rax, [rdi+10h]
0x180010447  mov     [rcx], rax
0x18001044a  mov     qword ptr [rdi], 0
0x180010451  mov     rbx, [rsp+28h+arg_0]
0x180010456  add     rsp, 20h
0x18001045a  pop     rdi
0x18001045b  retn
```
