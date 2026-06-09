# wil::details_abi::heap_vector<wil::details::EnabledStateManager::CachedFeaturePropertyData>::~heap_vector<wil::details::EnabledStateManager::CachedFeaturePropertyData>(void)

- ea: `0x1800183c8`
- end: `0x180018403`
- name: `??1?$heap_vector@UCachedFeaturePropertyData@EnabledStateManager@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180016aa8`
- `0x18003e310`
- `0x18003e3b0`
- `0x18003eff2`
- `0x18003f041`
- `0x18003f091`
- `0x18003f155`
- `0x18003f16b`
- `0x18003f210`

## callees

- `0x1800183c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800183f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800183f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800183e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800183e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details_abi::heap_vector<wil::details::EnabledStateManager::CachedFeaturePropertyData>::~heap_vector<wil::details::EnabledStateManager::CachedFeaturePropertyData>(
        __int64 a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *(void **)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x1800183c8  mov     [rsp+arg_0], rcx
0x1800183cd  push    rbx
0x1800183ce  sub     rsp, 20h
0x1800183d2  mov     [rsp+28h+arg_8], rcx
0x1800183d7  mov     rbx, [rcx+18h]
0x1800183db  mov     qword ptr [rcx+18h], 0
0x1800183e3  test    rbx, rbx
0x1800183e6  jz      short loc_1800183FD
0x1800183e8  call    cs:__imp_GetProcessHeap
0x1800183ee  mov     rcx, rax; hHeap
0x1800183f1  mov     r8, rbx; lpMem
0x1800183f4  xor     edx, edx; dwFlags
0x1800183f6  call    cs:__imp_HeapFree
0x1800183fc  nop
0x1800183fd  add     rsp, 20h
0x180018401  pop     rbx
0x180018402  retn
```
