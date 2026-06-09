# _dynamic_atexit_destructor_for__g_mutxCache__

- ea: `0x180076e60`
- end: `0x180076e7f`
- name: `_dynamic_atexit_destructor_for__g_mutxCache__`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180076e60`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180076e74`
- `KERNEL32!DeleteCriticalSection` at `0x180076e74`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_mutxCache__()
{
  if ( byte_180090791 )
    DeleteCriticalSection(&g_mutxCache);
}

```

## disassembly

```asm
0x180076e60  sub     rsp, 28h
0x180076e64  cmp     cs:byte_180090791, 0
0x180076e6b  jz      short loc_180076E7A
0x180076e6d  lea     rcx, ?g_mutxCache@@3VMUTX@@A; lpCriticalSection
0x180076e74  call    cs:__imp_DeleteCriticalSection
0x180076e7a  add     rsp, 28h
0x180076e7e  retn
```
