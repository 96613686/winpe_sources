# _dynamic_atexit_destructor_for__CCabDecompressorList::m_Lock__

- ea: `0x140022110`
- end: `0x14002212c`
- name: `_dynamic_atexit_destructor_for__CCabDecompressorList::m_Lock__`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140022125`

## pseudocode

```c
void dynamic_atexit_destructor_for__CCabDecompressorList::m_Lock__()
{
  CCabDecompressorList::m_Lock = &CSusLock::`vftable';
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x140022110  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x140022117  lea     rcx, CriticalSection
0x14002211e  mov     cs:?m_Lock@CCabDecompressorList@@0VCSusLock@@A, rax; CSusLock CCabDecompressorList::m_Lock
0x140022125  jmp     cs:__imp_DeleteCriticalSection
```
