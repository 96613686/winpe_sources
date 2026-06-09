# _dynamic_atexit_destructor_for__ErrorRecordStackCriticalSection__

- ea: `0x180030ae0`
- end: `0x180030aee`
- name: `_dynamic_atexit_destructor_for__ErrorRecordStackCriticalSection__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030ae7`

## pseudocode

```c
void dynamic_atexit_destructor_for__ErrorRecordStackCriticalSection__()
{
  DeleteCriticalSection(&stru_180049CC0);
}

```

## disassembly

```asm
0x180030ae0  lea     rcx, stru_180049CC0
0x180030ae7  jmp     cs:__imp_DeleteCriticalSection
```
