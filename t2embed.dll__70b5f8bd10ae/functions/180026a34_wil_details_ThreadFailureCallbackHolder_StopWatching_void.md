# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x180026a34`
- end: `0x180026a9b`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c400`
- `0x18001d4e8`

## callees

- `0x180026a34`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180026a3d`
- `KERNEL32!GetCurrentThreadId` at `0x180026a3d`

## string_xrefs

- `0x180026a59`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x180026a34  push    rbx
0x180026a36  sub     rsp, 20h
0x180026a3a  mov     rbx, rcx
0x180026a3d  call    cs:__imp_GetCurrentThreadId
0x180026a43  cmp     [rbx+18h], eax
0x180026a46  jz      short loc_180026A65
0x180026a48  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180026a4f  test    rax, rax
0x180026a52  jz      short loc_180026A65
0x180026a54  mov     rdx, [rsp+28h]
0x180026a59  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180026a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a65  mov     rcx, [rbx]
0x180026a68  mov     dword ptr [rbx+18h], 0
0x180026a6f  jmp     short loc_180026A7D
0x180026a71  cmp     rax, rbx
0x180026a74  jz      short loc_180026A87
0x180026a76  lea     rcx, [rax+10h]
0x180026a7a  mov     [rbx], rcx
0x180026a7d  mov     rax, [rcx]
0x180026a80  test    rax, rax
0x180026a83  jnz     short loc_180026A71
0x180026a85  jmp     short loc_180026A8E
0x180026a87  mov     rax, [rbx+10h]
0x180026a8b  mov     [rcx], rax
0x180026a8e  mov     qword ptr [rbx], 0
0x180026a95  add     rsp, 20h
0x180026a99  pop     rbx
0x180026a9a  retn
```
