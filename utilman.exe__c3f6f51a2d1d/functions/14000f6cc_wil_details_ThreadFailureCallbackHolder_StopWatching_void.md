# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x14000f6cc`
- end: `0x14000f73a`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d1cc`

## callees

- `0x14000f6cc`
- `0x140029010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000f6d5`
- `KERNEL32!GetCurrentThreadId` at `0x14000f6d5`

## string_xrefs

- `0x14000f6f7`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x14000f6cc  push    rbx
0x14000f6ce  sub     rsp, 20h
0x14000f6d2  mov     rbx, rcx
0x14000f6d5  call    cs:__imp_GetCurrentThreadId
0x14000f6dc  nop     dword ptr [rax+rax+00h]
0x14000f6e1  cmp     [rbx+18h], eax
0x14000f6e4  jz      short loc_14000F703
0x14000f6e6  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x14000f6ed  test    rax, rax
0x14000f6f0  jz      short loc_14000F703
0x14000f6f2  mov     rdx, [rsp+28h]
0x14000f6f7  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x14000f6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f703  mov     rcx, [rbx]
0x14000f706  mov     dword ptr [rbx+18h], 0
0x14000f70d  jmp     short loc_14000F71B
0x14000f70f  cmp     rax, rbx
0x14000f712  jz      short loc_14000F725
0x14000f714  lea     rcx, [rax+10h]
0x14000f718  mov     [rbx], rcx
0x14000f71b  mov     rax, [rcx]
0x14000f71e  test    rax, rax
0x14000f721  jnz     short loc_14000F70F
0x14000f723  jmp     short loc_14000F72C
0x14000f725  mov     rax, [rbx+10h]
0x14000f729  mov     [rcx], rax
0x14000f72c  mov     qword ptr [rbx], 0
0x14000f733  add     rsp, 20h
0x14000f737  pop     rbx
0x14000f738  retn
```
