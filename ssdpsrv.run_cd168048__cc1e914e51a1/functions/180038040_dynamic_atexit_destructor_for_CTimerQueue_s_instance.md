# _dynamic_atexit_destructor_for__CTimerQueue::s_instance__

- ea: `0x180038040`
- end: `0x18003804e`
- name: `_dynamic_atexit_destructor_for__CTimerQueue::s_instance__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038047`

## pseudocode

```c
void dynamic_atexit_destructor_for__CTimerQueue::s_instance__()
{
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180038040  lea     rcx, CriticalSection
0x180038047  jmp     cs:__imp_DeleteCriticalSection
```
