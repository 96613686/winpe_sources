# _dynamic_initializer_for__CCabDecompressorList::m_CabDecompressorList__

- ea: `0x140001aa0`
- end: `0x140001aac`
- name: `_dynamic_initializer_for__CCabDecompressorList::m_CabDecompressorList__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001acd4`

## pseudocode

```c
int dynamic_initializer_for__CCabDecompressorList::m_CabDecompressorList__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CCabDecompressorList::m_CabDecompressorList__);
}

```

## disassembly

```asm
0x140001aa0  lea     rcx, _dynamic_atexit_destructor_for__CCabDecompressorList__m_CabDecompressorList__
0x140001aa7  jmp     atexit
```
