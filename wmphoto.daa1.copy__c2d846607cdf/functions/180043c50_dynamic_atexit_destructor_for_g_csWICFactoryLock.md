# _dynamic_atexit_destructor_for__g_csWICFactoryLock__

- ea: `0x180043c50`
- end: `0x180043c76`
- name: `_dynamic_atexit_destructor_for__g_csWICFactoryLock__`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180043c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180043c64`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180043c64`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csWICFactoryLock__()
{
  if ( byte_1800505E8 )
  {
    DeleteCriticalSection(&g_csWICFactoryLock);
    byte_1800505E8 = 0;
  }
}

```

## disassembly

```asm
0x180043c50  sub     rsp, 28h
0x180043c54  cmp     cs:byte_1800505E8, 0
0x180043c5b  jz      short loc_180043C71
0x180043c5d  lea     rcx, ?g_csWICFactoryLock@@3VCCriticalSection@@A; lpCriticalSection
0x180043c64  call    cs:__imp_DeleteCriticalSection
0x180043c6a  mov     cs:byte_1800505E8, 0
0x180043c71  add     rsp, 28h
0x180043c75  retn
```
