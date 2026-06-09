# wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18000a920`
- end: `0x18000a994`
- name: `?IgnoreCurrentThread@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5c4`
- `0x18000b750`
- `0x180016840`

## callees

- `0x18000a920`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a936`

## string_xrefs

- `0x18000a952`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
    *(_DWORD *)(v1 + 24) = 0;
    v2 = *(__int64 **)v1;
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
0x18000a920  push    rbx
0x18000a922  sub     rsp, 20h
0x18000a926  cmp     dword ptr [rcx+138h], 0
0x18000a92d  jz      short loc_18000A98E
0x18000a92f  lea     rbx, [rcx+120h]
0x18000a936  call    cs:__imp_GetCurrentThreadId
0x18000a93c  cmp     [rbx+18h], eax
0x18000a93f  jz      short loc_18000A95E
0x18000a941  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18000a948  test    rax, rax
0x18000a94b  jz      short loc_18000A95E
0x18000a94d  mov     rdx, [rsp+28h]
0x18000a952  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18000a959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a95e  mov     dword ptr [rbx+18h], 0
0x18000a965  mov     rcx, [rbx]
0x18000a968  jmp     short loc_18000A976
0x18000a96a  cmp     rax, rbx
0x18000a96d  jz      short loc_18000A980
0x18000a96f  lea     rcx, [rax+10h]
0x18000a973  mov     [rbx], rcx
0x18000a976  mov     rax, [rcx]
0x18000a979  test    rax, rax
0x18000a97c  jnz     short loc_18000A96A
0x18000a97e  jmp     short loc_18000A987
0x18000a980  mov     rax, [rbx+10h]
0x18000a984  mov     [rcx], rax
0x18000a987  mov     qword ptr [rbx], 0
0x18000a98e  add     rsp, 20h
0x18000a992  pop     rbx
0x18000a993  retn
```
