# wil::details::ThreadFailureCallbackHolder::suspend(void)

- ea: `0x180048878`
- end: `0x180048905`
- name: `?suspend@ThreadFailureCallbackHolder@details@wil@@QEAA_NXZ`
- size: `141`
- prototype: `bool __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18003f0c0`
- `0x18003f128`
- `0x180048b40`
- `0x18004d0e4`
- `0x180050c3c`
- `0x180050d70`
- `0x180050ea4`
- `0x180068b1c`

## callees

- `0x180048878`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048896`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048896`

## string_xrefs

- `0x1800488b1`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
char __fastcall wil::details::ThreadFailureCallbackHolder::suspend(wil::details::ThreadFailureCallbackHolder *this)
{
  char v2; // si
  int v3; // ebx
  wil::details::ThreadFailureCallbackHolder **v4; // rcx
  wil::details::ThreadFailureCallbackHolder *v5; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*((_DWORD *)this + 6) )
    return 0;
  v2 = 1;
  v3 = *((_DWORD *)this + 6);
  if ( v3 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
    wil::details::g_pfnReportFatalUsageError(
      "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
      retaddr);
  *((_DWORD *)this + 6) = 0;
  v4 = *(wil::details::ThreadFailureCallbackHolder ***)this;
  while ( 1 )
  {
    v5 = *v4;
    if ( !*v4 )
      break;
    if ( v5 == this )
    {
      *v4 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
      break;
    }
    v4 = (wil::details::ThreadFailureCallbackHolder **)((char *)v5 + 16);
    *(_QWORD *)this = (char *)v5 + 16;
  }
  *(_QWORD *)this = 0;
  return v2;
}

```

## disassembly

```asm
0x180048878  mov     [rsp+arg_0], rbx
0x18004887d  mov     [rsp+arg_8], rsi
0x180048882  push    rdi
0x180048883  sub     rsp, 20h
0x180048887  mov     rdi, rcx
0x18004888a  cmp     dword ptr [rcx+18h], 0
0x18004888e  jz      short loc_1800488EF
0x180048890  mov     sil, 1
0x180048893  mov     ebx, [rcx+18h]
0x180048896  call    cs:__imp_GetCurrentThreadId
0x18004889c  cmp     ebx, eax
0x18004889e  jz      short loc_1800488BD
0x1800488a0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800488a7  test    rax, rax
0x1800488aa  jz      short loc_1800488BD
0x1800488ac  mov     rdx, [rsp+28h]
0x1800488b1  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800488b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488bd  mov     dword ptr [rdi+18h], 0
0x1800488c4  mov     rcx, [rdi]
0x1800488c7  jmp     short loc_1800488D5
0x1800488c9  cmp     rax, rdi
0x1800488cc  jz      short loc_1800488DF
0x1800488ce  lea     rcx, [rax+10h]
0x1800488d2  mov     [rdi], rcx
0x1800488d5  mov     rax, [rcx]
0x1800488d8  test    rax, rax
0x1800488db  jnz     short loc_1800488C9
0x1800488dd  jmp     short loc_1800488E6
0x1800488df  mov     rax, [rdi+10h]
0x1800488e3  mov     [rcx], rax
0x1800488e6  mov     qword ptr [rdi], 0
0x1800488ed  jmp     short loc_1800488F2
0x1800488ef  xor     sil, sil
0x1800488f2  mov     al, sil
0x1800488f5  mov     rbx, [rsp+28h+arg_0]
0x1800488fa  mov     rsi, [rsp+28h+arg_8]
0x1800488ff  add     rsp, 20h
0x180048903  pop     rdi
0x180048904  retn
```
