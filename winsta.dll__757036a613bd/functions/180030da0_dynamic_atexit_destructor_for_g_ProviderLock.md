# _dynamic_atexit_destructor_for__g_ProviderLock__

- ea: `0x180030da0`
- end: `0x180030dc9`
- name: `_dynamic_atexit_destructor_for__g_ProviderLock__`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180030da0`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180030db4`
- `ntdll!RtlDeleteResource` at `0x180030db4`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_ProviderLock__()
{
  if ( dword_1800575B0 )
    RtlDeleteResource(&g_ProviderLock);
  dword_1800575B0 = 0;
}

```

## disassembly

```asm
0x180030da0  sub     rsp, 28h
0x180030da4  cmp     cs:dword_1800575B0, 0
0x180030dab  jz      short loc_180030DBA
0x180030dad  lea     rcx, ?g_ProviderLock@@3VCResource@@A; Resource
0x180030db4  call    cs:__imp_RtlDeleteResource
0x180030dba  mov     cs:dword_1800575B0, 0
0x180030dc4  add     rsp, 28h
0x180030dc8  retn
```
