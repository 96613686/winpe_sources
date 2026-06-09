# _dynamic_atexit_destructor_for__g_cs__

- ea: `0x1800467b0`
- end: `0x1800467cf`
- name: `_dynamic_atexit_destructor_for__g_cs__`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800467b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800467c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800467c4`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_cs__()
{
  if ( byte_1800701C8 )
    DeleteCriticalSection(&g_cs);
}

```

## disassembly

```asm
0x1800467b0  sub     rsp, 28h
0x1800467b4  cmp     cs:byte_1800701C8, 0
0x1800467bb  jz      short loc_1800467CA
0x1800467bd  lea     rcx, ?g_cs@@3VCStaticCritSec@@A; lpCriticalSection
0x1800467c4  call    cs:__imp_DeleteCriticalSection
0x1800467ca  add     rsp, 28h
0x1800467ce  retn
```
