# _dynamic_atexit_destructor_for__g_lockObject__

- ea: `0x18001e560`
- end: `0x18001e56e`
- name: `_dynamic_atexit_destructor_for__g_lockObject__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x18001e567`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_lockObject__()
{
  RtlDeleteResource(&g_lockObject);
}

```

## disassembly

```asm
0x18001e560  lea     rcx, ?g_lockObject@@3VLibraryInitLock@@A; LibraryInitLock g_lockObject
0x18001e567  jmp     cs:__imp_RtlDeleteResource
```
