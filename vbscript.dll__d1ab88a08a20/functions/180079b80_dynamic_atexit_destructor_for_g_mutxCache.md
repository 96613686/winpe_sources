# _dynamic_atexit_destructor_for__g_mutxCache__

- ea: `0x180079b80`
- end: `0x180079ba6`
- name: `_dynamic_atexit_destructor_for__g_mutxCache__`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180079b80`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180079b94`
- `KERNEL32!DeleteCriticalSection` at `0x180079b94`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_mutxCache__()
{
  if ( byte_180093791 )
    DeleteCriticalSection(&g_mutxCache);
}

```

## disassembly

```asm
0x180079b80  sub     rsp, 28h
0x180079b84  cmp     cs:byte_180093791, 0
0x180079b8b  jz      short loc_180079BA0
0x180079b8d  lea     rcx, ?g_mutxCache@@3VMUTX@@A; lpCriticalSection
0x180079b94  call    cs:__imp_DeleteCriticalSection
0x180079b9b  nop     dword ptr [rax+rax+00h]
0x180079ba0  add     rsp, 28h
0x180079ba4  retn
```
