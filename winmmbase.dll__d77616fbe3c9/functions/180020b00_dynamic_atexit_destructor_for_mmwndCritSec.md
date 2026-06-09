# _dynamic_atexit_destructor_for__mmwndCritSec__

- ea: `0x180020b00`
- end: `0x180020b0e`
- name: `_dynamic_atexit_destructor_for__mmwndCritSec__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020b07`

## pseudocode

```c
void dynamic_atexit_destructor_for__mmwndCritSec__()
{
  DeleteCriticalSection(&mmwndCritSec);
}

```

## disassembly

```asm
0x180020b00  lea     rcx, ?mmwndCritSec@@3VCCriticalSection@ATL@@A; ATL::CCriticalSection mmwndCritSec
0x180020b07  jmp     cs:__imp_DeleteCriticalSection
```
