# _dynamic_atexit_destructor_for__g_cabDecompressorListInit__

- ea: `0x140022140`
- end: `0x14002214b`
- name: `_dynamic_atexit_destructor_for__g_cabDecompressorListInit__`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_cabDecompressorListInit__()
{
  CCabDecompressorList::m_fInited = 0;
}

```

## disassembly

```asm
0x140022140  mov     cs:?m_fInited@CCabDecompressorList@@0HA, 0; int CCabDecompressorList::m_fInited
0x14002214a  retn
```
