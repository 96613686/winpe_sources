# BaseClearSrvActivationContextCache

- ea: `0x180006270`
- end: `0x18000637d`
- name: `BaseClearSrvActivationContextCache`
- size: `269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001110`

## callees

- `0x180005050`
- `0x180006270`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006321`
- `ntdll!RtlFreeHeap` at `0x180006321`
- `ntdll!RtlEnterCriticalSection` at `0x1800062fd`
- `ntdll!RtlEnterCriticalSection` at `0x1800062fd`
- `ntdll!RtlLeaveCriticalSection` at `0x18000635b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000635b`
- `ntdll!RtlLeaveCriticalSection` at `0x180007085`
- `ntdll!RtlAllocateHeap` at `0x180006294`
- `ntdll!RtlAllocateHeap` at `0x180006294`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800062df`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800062df`

## pseudocode

```c
__int64 BaseClearSrvActivationContextCache()
{
  struct _RTL_AVL_TABLE *Heap; // rax
  struct _RTL_AVL_TABLE *v1; // rbx
  NTSTATUS v3; // edi
  struct _PEB *v4; // rcx
  struct _RTL_AVL_TABLE *v5; // r8
  struct _RTL_AVL_TABLE *v6; // rsi

  Heap = (struct _RTL_AVL_TABLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x78u);
  v1 = Heap;
  if ( !Heap )
    return 3221225495LL;
  RtlInitializeGenericTableAvl(
    Heap,
    (PRTL_AVL_COMPARE_ROUTINE)BaseSrvActivationContextCacheCompareEntries,
    BaseSrvActivationContextCacheAVLTableAllocate,
    BaseSrvActivationContextCacheAVLTableFree,
    0);
  v1[1].BalancedRoot.LeftChild = &v1[1].BalancedRoot;
  v1[1].BalancedRoot.Parent = &v1[1].BalancedRoot;
  v3 = RtlEnterCriticalSection(&SxsActCtxCacheCS);
  if ( v3 >= 0 )
  {
    v6 = g_SxsActCtxCache;
    g_SxsActCtxCache = v1;
    ++g_dwCacheFlush;
    RtlLeaveCriticalSection(&SxsActCtxCacheCS);
    BaseClearSrvActivationContextCacheNoLock(v6);
    v4 = NtCurrentPeb();
    v5 = v6;
  }
  else
  {
    v4 = NtCurrentPeb();
    v5 = v1;
  }
  RtlFreeHeap(v4->ProcessHeap, 0, v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006270  mov     [rsp+arg_0], rbx
0x180006275  mov     [rsp+arg_8], rsi
0x18000627a  push    rdi
0x18000627b  sub     rsp, 30h
0x18000627f  mov     rcx, gs:60h
0x180006288  xor     edx, edx; Flags
0x18000628a  mov     r8d, 78h ; 'x'; Size
0x180006290  mov     rcx, [rcx+30h]; HeapHandle
0x180006294  call    cs:__imp_RtlAllocateHeap
0x18000629b  nop     dword ptr [rax+rax+00h]
0x1800062a0  mov     rbx, rax
0x1800062a3  test    rax, rax
0x1800062a6  jnz     short loc_1800062BE
0x1800062a8  mov     eax, 0C0000017h
0x1800062ad  mov     rbx, [rsp+38h+arg_0]
0x1800062b2  mov     rsi, [rsp+38h+arg_8]
0x1800062b7  add     rsp, 30h
0x1800062bb  pop     rdi
0x1800062bc  retn
0x1800062be  mov     [rsp+38h+TableContext], 0; TableContext
0x1800062c7  lea     r9, BaseSrvActivationContextCacheAVLTableFree; FreeRoutine
0x1800062ce  lea     r8, BaseSrvActivationContextCacheAVLTableAllocate; AllocateRoutine
0x1800062d5  lea     rdx, BaseSrvActivationContextCacheCompareEntries; CompareRoutine
0x1800062dc  mov     rcx, rbx; Table
0x1800062df  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800062e6  nop     dword ptr [rax+rax+00h]
0x1800062eb  lea     rax, [rbx+68h]
0x1800062ef  mov     [rax+8], rax
0x1800062f3  mov     [rax], rax
0x1800062f6  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x1800062fd  call    cs:__imp_RtlEnterCriticalSection
0x180006304  nop     dword ptr [rax+rax+00h]
0x180006309  mov     edi, eax
0x18000630b  test    eax, eax
0x18000630d  jns     short loc_180006340
0x18000630f  mov     rcx, gs:60h
0x180006318  mov     r8, rbx; P
0x18000631b  xor     edx, edx; Flags
0x18000631d  mov     rcx, [rcx+30h]; HeapHandle
0x180006321  call    cs:__imp_RtlFreeHeap
0x180006328  nop     dword ptr [rax+rax+00h]
0x18000632d  mov     eax, edi
0x18000632f  mov     rbx, [rsp+38h+arg_0]
0x180006334  mov     rsi, [rsp+38h+arg_8]
0x180006339  add     rsp, 30h
0x18000633d  pop     rdi
0x18000633e  retn
0x180006340  mov     rsi, cs:g_SxsActCtxCache
0x180006347  mov     cs:g_SxsActCtxCache, rbx
0x18000634e  inc     cs:g_dwCacheFlush
0x180006354  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x18000635b  call    cs:__imp_RtlLeaveCriticalSection
0x180006362  nop     dword ptr [rax+rax+00h]
0x180006367  mov     rcx, rsi; Table
0x18000636a  call    BaseClearSrvActivationContextCacheNoLock
0x18000636f  mov     rcx, gs:60h
0x180006378  mov     r8, rsi
0x18000637b  jmp     short loc_18000631B
0x180007070  push    rbp
0x180007072  sub     rsp, 30h
0x180007076  mov     rbp, rdx
0x180007079  lea     rcx, SxsActCtxCacheCS
0x180007080  add     rsp, 30h
0x180007084  pop     rbp
0x180007085  jmp     cs:__imp_RtlLeaveCriticalSection
```
