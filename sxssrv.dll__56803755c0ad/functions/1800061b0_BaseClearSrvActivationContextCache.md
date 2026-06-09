# BaseClearSrvActivationContextCache

- ea: `0x1800061b0`
- end: `0x1800062b9`
- name: `BaseClearSrvActivationContextCache`
- size: `265`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001110`

## callees

- `0x180004e90`
- `0x1800061b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000629a`
- `ntdll!RtlFreeHeap` at `0x18000629a`
- `ntdll!RtlEnterCriticalSection` at `0x180006240`
- `ntdll!RtlEnterCriticalSection` at `0x180006240`
- `ntdll!RtlLeaveCriticalSection` at `0x180006272`
- `ntdll!RtlLeaveCriticalSection` at `0x180006272`
- `ntdll!RtlLeaveCriticalSection` at `0x180006fc5`
- `ntdll!RtlAllocateHeap` at `0x1800061d2`
- `ntdll!RtlAllocateHeap` at `0x1800061d2`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180006222`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180006222`

## pseudocode

```c
__int64 BaseClearSrvActivationContextCache()
{
  struct _RTL_AVL_TABLE *Heap; // rax
  struct _RTL_AVL_TABLE *v1; // rbx
  NTSTATUS v3; // esi
  struct _RTL_AVL_TABLE *v4; // rdi
  PRTL_AVL_TABLE P; // [rsp+40h] [rbp+8h]

  Heap = (struct _RTL_AVL_TABLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x78u);
  v1 = Heap;
  P = Heap;
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
    v4 = g_SxsActCtxCache;
    P = g_SxsActCtxCache;
    g_SxsActCtxCache = v1;
    ++g_dwCacheFlush;
    RtlLeaveCriticalSection(&SxsActCtxCacheCS);
    BaseClearSrvActivationContextCacheNoLock(v4);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800061b0  mov     [rsp+arg_8], rbx
0x1800061b5  mov     [rsp+arg_10], rsi
0x1800061ba  push    rdi
0x1800061bb  sub     rsp, 30h
0x1800061bf  mov     rcx, gs:60h
0x1800061c8  xor     edx, edx; Flags
0x1800061ca  lea     r8d, [rdx+78h]; Size
0x1800061ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800061d2  call    cs:__imp_RtlAllocateHeap
0x1800061d9  nop     dword ptr [rax+rax+00h]
0x1800061de  mov     rbx, rax
0x1800061e1  mov     [rsp+38h+P], rax
0x1800061e6  test    rax, rax
0x1800061e9  jnz     short loc_180006201
0x1800061eb  mov     eax, 0C0000017h
0x1800061f0  mov     rbx, [rsp+38h+arg_8]
0x1800061f5  mov     rsi, [rsp+38h+arg_10]
0x1800061fa  add     rsp, 30h
0x1800061fe  pop     rdi
0x1800061ff  retn
0x180006201  mov     [rsp+38h+TableContext], 0; TableContext
0x18000620a  lea     r9, BaseSrvActivationContextCacheAVLTableFree; FreeRoutine
0x180006211  lea     r8, BaseSrvActivationContextCacheAVLTableAllocate; AllocateRoutine
0x180006218  lea     rdx, BaseSrvActivationContextCacheCompareEntries; CompareRoutine
0x18000621f  mov     rcx, rbx; Table
0x180006222  call    cs:__imp_RtlInitializeGenericTableAvl
0x180006229  nop     dword ptr [rax+rax+00h]
0x18000622e  lea     rax, [rbx+68h]
0x180006232  mov     [rax+8], rax
0x180006236  mov     [rax], rax
0x180006239  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180006240  call    cs:__imp_RtlEnterCriticalSection
0x180006247  nop     dword ptr [rax+rax+00h]
0x18000624c  mov     esi, eax
0x18000624e  test    eax, eax
0x180006250  js      short loc_180006286
0x180006252  mov     rdi, cs:g_SxsActCtxCache
0x180006259  mov     [rsp+38h+P], rdi
0x18000625e  mov     cs:g_SxsActCtxCache, rbx
0x180006265  inc     cs:g_dwCacheFlush
0x18000626b  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180006272  call    cs:__imp_RtlLeaveCriticalSection
0x180006279  nop     dword ptr [rax+rax+00h]
0x18000627e  mov     rcx, rdi; Table
0x180006281  call    BaseClearSrvActivationContextCacheNoLock
0x180006286  mov     rcx, gs:60h
0x18000628f  mov     r8, [rsp+38h+P]; P
0x180006294  xor     edx, edx; Flags
0x180006296  mov     rcx, [rcx+30h]; HeapHandle
0x18000629a  call    cs:__imp_RtlFreeHeap
0x1800062a1  nop     dword ptr [rax+rax+00h]
0x1800062a6  mov     eax, esi
0x1800062a8  mov     rbx, [rsp+38h+arg_8]
0x1800062ad  mov     rsi, [rsp+38h+arg_10]
0x1800062b2  add     rsp, 30h
0x1800062b6  pop     rdi
0x1800062b7  retn
0x180006fb0  push    rbp
0x180006fb2  sub     rsp, 30h
0x180006fb6  mov     rbp, rdx
0x180006fb9  lea     rcx, SxsActCtxCacheCS
0x180006fc0  add     rsp, 30h
0x180006fc4  pop     rbp
0x180006fc5  jmp     cs:__imp_RtlLeaveCriticalSection
```
