# mlib::_dynamic_atexit_destructor_for__g_SpritnfStrsCritSec__

- ea: `0x180030b00`
- end: `0x180030b0e`
- name: `mlib::_dynamic_atexit_destructor_for__g_SpritnfStrsCritSec__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030b07`

## pseudocode

```c
void mlib::_dynamic_atexit_destructor_for__g_SpritnfStrsCritSec__()
{
  DeleteCriticalSection(&stru_180049DD8);
}

```

## disassembly

```asm
0x180030b00  lea     rcx, stru_180049DD8
0x180030b07  jmp     cs:__imp_DeleteCriticalSection
```
