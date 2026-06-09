# _dynamic_atexit_destructor_for__CCabDecompressorList::m_CabDecompressorList__

- ea: `0x1400220f0`
- end: `0x1400220fc`
- name: `_dynamic_atexit_destructor_for__CCabDecompressorList::m_CabDecompressorList__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001a5dc`

## pseudocode

```c
void **dynamic_atexit_destructor_for__CCabDecompressorList::m_CabDecompressorList__()
{
  return CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::~CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>((__int64)&CCabDecompressorList::m_CabDecompressorList);
}

```

## disassembly

```asm
0x1400220f0  lea     rcx, ?m_CabDecompressorList@CCabDecompressorList@@0V?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@A; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>> CCabDecompressorList::m_CabDecompressorList
0x1400220f7  jmp     ??1?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@UEAA@XZ; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::~CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>(void)
```
