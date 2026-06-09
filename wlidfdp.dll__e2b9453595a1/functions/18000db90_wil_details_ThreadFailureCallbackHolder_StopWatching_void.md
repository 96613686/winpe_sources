# wil::details::ThreadFailureCallbackHolder::StopWatching(void)

- ea: `0x18000db90`
- end: `0x18000dbf7`
- name: `?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ`
- size: `103`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c8f4`
- `0x18000ca18`

## callees

- `0x18000db90`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db99`

## string_xrefs

- `0x18000dbb5`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

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
0x18000db90  push    rbx
0x18000db92  sub     rsp, 20h
0x18000db96  mov     rbx, rcx
0x18000db99  call    cs:__imp_GetCurrentThreadId
0x18000db9f  cmp     [rbx+18h], eax
0x18000dba2  jz      short loc_18000DBC1
0x18000dba4  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000dbab  test    rax, rax
0x18000dbae  jz      short loc_18000DBC1
0x18000dbb0  mov     rdx, [rsp+28h]
0x18000dbb5  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000dbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc1  mov     rcx, [rbx]
0x18000dbc4  mov     dword ptr [rbx+18h], 0
0x18000dbcb  jmp     short loc_18000DBD9
0x18000dbcd  cmp     rax, rbx
0x18000dbd0  jz      short loc_18000DBE3
0x18000dbd2  lea     rcx, [rax+10h]
0x18000dbd6  mov     [rbx], rcx
0x18000dbd9  mov     rax, [rcx]
0x18000dbdc  test    rax, rax
0x18000dbdf  jnz     short loc_18000DBCD
0x18000dbe1  jmp     short loc_18000DBEA
0x18000dbe3  mov     rax, [rbx+10h]
0x18000dbe7  mov     [rcx], rax
0x18000dbea  mov     qword ptr [rbx], 0
0x18000dbf1  add     rsp, 20h
0x18000dbf5  pop     rbx
0x18000dbf6  retn
```
