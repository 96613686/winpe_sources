# _dynamic_atexit_destructor_for__CWLIDTimerQueue::s_CriticalSection__

- ea: `0x180011400`
- end: `0x18001140e`
- name: `_dynamic_atexit_destructor_for__CWLIDTimerQueue::s_CriticalSection__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011407`

## pseudocode

```c
void dynamic_atexit_destructor_for__CWLIDTimerQueue::s_CriticalSection__()
{
  DeleteCriticalSection(&CWLIDTimerQueue::s_CriticalSection);
}

```

## disassembly

```asm
0x180011400  lea     rcx, ?s_CriticalSection@CWLIDTimerQueue@@0VCCritSecLite@@A; CCritSecLite CWLIDTimerQueue::s_CriticalSection
0x180011407  jmp     cs:__imp_DeleteCriticalSection
```
