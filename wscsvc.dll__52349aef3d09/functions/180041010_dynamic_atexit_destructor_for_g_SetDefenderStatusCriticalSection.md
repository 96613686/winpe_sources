# _dynamic_atexit_destructor_for__g_SetDefenderStatusCriticalSection__

- ea: `0x180041010`
- end: `0x18004102f`
- name: `_dynamic_atexit_destructor_for__g_SetDefenderStatusCriticalSection__`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041024`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041024`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_SetDefenderStatusCriticalSection__()
{
  if ( dword_180054058 )
    DeleteCriticalSection(&g_SetDefenderStatusCriticalSection);
}

```

## disassembly

```asm
0x180041010  sub     rsp, 28h
0x180041014  cmp     cs:dword_180054058, 0
0x18004101b  jz      short loc_18004102A
0x18004101d  lea     rcx, ?g_SetDefenderStatusCriticalSection@@3VCCriticalSection@@A; lpCriticalSection
0x180041024  call    cs:__imp_DeleteCriticalSection
0x18004102a  add     rsp, 28h
0x18004102e  retn
```
