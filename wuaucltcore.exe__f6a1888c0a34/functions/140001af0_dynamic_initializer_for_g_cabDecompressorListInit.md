# _dynamic_initializer_for__g_cabDecompressorListInit__

- ea: `0x140001af0`
- end: `0x140001b06`
- name: `_dynamic_initializer_for__g_cabDecompressorListInit__`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001acd4`

## pseudocode

```c
int dynamic_initializer_for__g_cabDecompressorListInit__()
{
  CCabDecompressorList::m_fInited = 1;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_cabDecompressorListInit__);
}

```

## disassembly

```asm
0x140001af0  lea     rcx, _dynamic_atexit_destructor_for__g_cabDecompressorListInit__
0x140001af7  mov     cs:?m_fInited@CCabDecompressorList@@0HA, 1; int CCabDecompressorList::m_fInited
0x140001b01  jmp     atexit
```
