# wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000946c`
- end: `0x1800094e0`
- name: `?IgnoreCurrentThread@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000745c`
- `0x180007788`
- `0x18000b820`
- `0x18000c1ec`
- `0x18000c5b4`
- `0x18000c8d8`
- `0x18000cbfc`

## callees

- `0x18000946c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009482`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009482`

## string_xrefs

- `0x18000949e`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rcx
  __int64 v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = a1 + 288;
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    v2 = *(__int64 **)v1;
    *(_DWORD *)(v1 + 24) = 0;
    while ( 1 )
    {
      v3 = *v2;
      if ( !*v2 )
        break;
      if ( v3 == v1 )
      {
        *v2 = *(_QWORD *)(v1 + 16);
        break;
      }
      v2 = (__int64 *)(v3 + 16);
      *(_QWORD *)v1 = v3 + 16;
    }
    *(_QWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x18000946c  push    rbx
0x18000946e  sub     rsp, 20h
0x180009472  cmp     dword ptr [rcx+138h], 0
0x180009479  jz      short loc_1800094DA
0x18000947b  lea     rbx, [rcx+120h]
0x180009482  call    cs:__imp_GetCurrentThreadId
0x180009488  cmp     [rbx+18h], eax
0x18000948b  jz      short loc_1800094AA
0x18000948d  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180009494  test    rax, rax
0x180009497  jz      short loc_1800094AA
0x180009499  mov     rdx, [rsp+28h]
0x18000949e  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800094a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094aa  mov     rcx, [rbx]
0x1800094ad  mov     dword ptr [rbx+18h], 0
0x1800094b4  jmp     short loc_1800094C2
0x1800094b6  cmp     rax, rbx
0x1800094b9  jz      short loc_1800094CC
0x1800094bb  lea     rcx, [rax+10h]
0x1800094bf  mov     [rbx], rcx
0x1800094c2  mov     rax, [rcx]
0x1800094c5  test    rax, rax
0x1800094c8  jnz     short loc_1800094B6
0x1800094ca  jmp     short loc_1800094D3
0x1800094cc  mov     rax, [rbx+10h]
0x1800094d0  mov     [rcx], rax
0x1800094d3  mov     qword ptr [rbx], 0
0x1800094da  add     rsp, 20h
0x1800094de  pop     rbx
0x1800094df  retn
```
