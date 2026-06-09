# _dynamic_atexit_destructor_for__g_LibraryCache__

- ea: `0x140033940`
- end: `0x14003394e`
- name: `_dynamic_atexit_destructor_for__g_LibraryCache__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140033947`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_LibraryCache__()
{
  DeleteCriticalSection(&g_LibraryCache);
}

```

## disassembly

```asm
0x140033940  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; LibraryCache g_LibraryCache
0x140033947  jmp     cs:__imp_DeleteCriticalSection
```
