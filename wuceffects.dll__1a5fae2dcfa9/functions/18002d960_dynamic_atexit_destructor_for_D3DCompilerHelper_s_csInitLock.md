# _dynamic_atexit_destructor_for__D3DCompilerHelper::s_csInitLock__

- ea: `0x18002d960`
- end: `0x18002d96e`
- name: `_dynamic_atexit_destructor_for__D3DCompilerHelper::s_csInitLock__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002d967`

## pseudocode

```c
void dynamic_atexit_destructor_for__D3DCompilerHelper::s_csInitLock__()
{
  DeleteCriticalSection(&D3DCompilerHelper::s_csInitLock);
}

```

## disassembly

```asm
0x18002d960  lea     rcx, ?s_csInitLock@D3DCompilerHelper@@0VCCriticalSection@@A; CCriticalSection D3DCompilerHelper::s_csInitLock
0x18002d967  jmp     cs:__imp_DeleteCriticalSection
```
