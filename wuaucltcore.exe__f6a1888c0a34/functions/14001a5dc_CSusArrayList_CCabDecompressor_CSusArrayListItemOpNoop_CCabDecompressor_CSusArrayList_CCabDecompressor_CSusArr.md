# CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::~CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>(void)

- ea: `0x14001a5dc`
- end: `0x14001a617`
- name: `??1?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@UEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001a6e0`
- `0x1400220f0`

## callees

- `0x14000d4cc`
- `0x14001a5dc`

## pseudocode

```c
void **__fastcall CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::~CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>(
        __int64 a1)
{
  void *v2; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::`vftable';
  if ( *(_DWORD *)(a1 + 20) )
    *(_DWORD *)(a1 + 20) = 0;
  v2 = *(void **)(a1 + 8);
  if ( v2 )
    SusFree(v2);
  result = &CSusBaseAllocTag<7169389>::`vftable';
  *(_QWORD *)a1 = &CSusBaseAllocTag<7169389>::`vftable';
  return result;
}

```

## disassembly

```asm
0x14001a5dc  push    rbx
0x14001a5de  sub     rsp, 20h
0x14001a5e2  lea     rax, ??_7?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@6B@; const CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::`vftable'
0x14001a5e9  mov     rbx, rcx
0x14001a5ec  mov     [rcx], rax
0x14001a5ef  mov     eax, [rcx+14h]
0x14001a5f2  test    eax, eax
0x14001a5f4  jz      short loc_14001A5F9
0x14001a5f6  sub     [rcx+14h], eax
0x14001a5f9  mov     rcx, [rcx+8]; lpMem
0x14001a5fd  test    rcx, rcx
0x14001a600  jz      short loc_14001A607
0x14001a602  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001a607  lea     rax, ??_7?$CSusBaseAllocTag@$0GNGFGN@@@6B@; const CSusBaseAllocTag<7169389>::`vftable'
0x14001a60e  mov     [rbx], rax
0x14001a611  add     rsp, 20h
0x14001a615  pop     rbx
0x14001a616  retn
```
