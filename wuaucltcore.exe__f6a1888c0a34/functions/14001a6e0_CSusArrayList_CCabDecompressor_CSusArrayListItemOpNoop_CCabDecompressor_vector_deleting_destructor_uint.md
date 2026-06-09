# CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::`vector deleting destructor'(uint)

- ea: `0x14001a6e0`
- end: `0x14001a736`
- name: `??_E?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@UEAAPEAXI@Z`
- size: `86`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001b70`
- `0x14001a5dc`
- `0x14001a6e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a713`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a713`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a705`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001a705`

## pseudocode

```c
void *__fastcall CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::~CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>((__int64)a1);
  if ( (a2 & 1) != 0 )
  {
    if ( (a2 & 4) != 0 )
    {
      __global_delete(a1);
    }
    else if ( a1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, a1);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14001a6e0  mov     [rsp+arg_0], rbx
0x14001a6e5  push    rdi
0x14001a6e6  sub     rsp, 20h
0x14001a6ea  mov     edi, edx
0x14001a6ec  mov     rbx, rcx
0x14001a6ef  call    ??1?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@UEAA@XZ; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::~CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>(void)
0x14001a6f4  test    dil, 1
0x14001a6f8  jz      short loc_14001A728
0x14001a6fa  test    dil, 4
0x14001a6fe  jnz     short loc_14001A71B
0x14001a700  test    rbx, rbx
0x14001a703  jz      short loc_14001A728
0x14001a705  call    cs:__imp_GetProcessHeap
0x14001a70b  mov     r8, rbx; lpMem
0x14001a70e  xor     edx, edx; dwFlags
0x14001a710  mov     rcx, rax; hHeap
0x14001a713  call    cs:__imp_HeapFree
0x14001a719  jmp     short loc_14001A728
0x14001a71b  mov     edx, 18h; unsigned __int64
0x14001a720  mov     rcx, rbx; void *
0x14001a723  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x14001a728  mov     rax, rbx
0x14001a72b  mov     rbx, [rsp+28h+arg_0]
0x14001a730  add     rsp, 20h
0x14001a734  pop     rdi
0x14001a735  retn
```
