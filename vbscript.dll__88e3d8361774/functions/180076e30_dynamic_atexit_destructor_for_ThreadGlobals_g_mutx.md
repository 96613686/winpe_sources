# _dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__

- ea: `0x180076e30`
- end: `0x180076e4f`
- name: `_dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180076e30`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180076e44`
- `KERNEL32!DeleteCriticalSection` at `0x180076e44`

## pseudocode

```c
void dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__()
{
  if ( byte_1800907C1 )
    DeleteCriticalSection(&ThreadGlobals::g_mutx);
}

```

## disassembly

```asm
0x180076e30  sub     rsp, 28h
0x180076e34  cmp     cs:byte_1800907C1, 0
0x180076e3b  jz      short loc_180076E4A
0x180076e3d  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; lpCriticalSection
0x180076e44  call    cs:__imp_DeleteCriticalSection
0x180076e4a  add     rsp, 28h
0x180076e4e  retn
```
