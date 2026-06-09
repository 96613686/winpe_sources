# _dynamic_initializer_for__CCabDecompressorList::m_Lock__

- ea: `0x140001ac0`
- end: `0x140001ae1`
- name: `_dynamic_initializer_for__CCabDecompressorList::m_Lock__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001acd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140001acb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140001acb`

## pseudocode

```c
int dynamic_initializer_for__CCabDecompressorList::m_Lock__()
{
  InitializeCriticalSection(&CriticalSection);
  return atexit(dynamic_atexit_destructor_for__CCabDecompressorList::m_Lock__);
}

```

## disassembly

```asm
0x140001ac0  sub     rsp, 28h
0x140001ac4  lea     rcx, CriticalSection; lpCriticalSection
0x140001acb  call    cs:__imp_InitializeCriticalSection
0x140001ad1  lea     rcx, _dynamic_atexit_destructor_for__CCabDecompressorList__m_Lock__
0x140001ad8  add     rsp, 28h
0x140001adc  jmp     atexit
```
