# wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x18004453c`
- end: `0x1800445b0`
- name: `?IgnoreCurrentThread@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `116`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180047128`
- `0x180047260`
- `0x180047510`
- `0x1800477c0`
- `0x18004c010`
- `0x18004c2c0`
- `0x18004fc30`
- `0x180054ec0`
- `0x18005e000`
- `0x180067090`

## callees

- `0x18004453c`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044552`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044552`

## string_xrefs

- `0x18004456e`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
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
0x18004453c  push    rbx
0x18004453e  sub     rsp, 20h
0x180044542  cmp     dword ptr [rcx+138h], 0
0x180044549  jz      short loc_1800445AA
0x18004454b  lea     rbx, [rcx+120h]
0x180044552  call    cs:__imp_GetCurrentThreadId
0x180044558  cmp     [rbx+18h], eax
0x18004455b  jz      short loc_18004457A
0x18004455d  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180044564  test    rax, rax
0x180044567  jz      short loc_18004457A
0x180044569  mov     rdx, [rsp+28h]
0x18004456e  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180044575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004457a  mov     dword ptr [rbx+18h], 0
0x180044581  mov     rcx, [rbx]
0x180044584  jmp     short loc_180044592
0x180044586  cmp     rax, rbx
0x180044589  jz      short loc_18004459C
0x18004458b  lea     rcx, [rax+10h]
0x18004458f  mov     [rbx], rcx
0x180044592  mov     rax, [rcx]
0x180044595  test    rax, rax
0x180044598  jnz     short loc_180044586
0x18004459a  jmp     short loc_1800445A3
0x18004459c  mov     rax, [rbx+10h]
0x1800445a0  mov     [rcx], rax
0x1800445a3  mov     qword ptr [rbx], 0
0x1800445aa  add     rsp, 20h
0x1800445ae  pop     rbx
0x1800445af  retn
```
