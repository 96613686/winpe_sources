# _dynamic_atexit_destructor_for__s_RemediationLock__

- ea: `0x180040fe0`
- end: `0x180040fff`
- name: `_dynamic_atexit_destructor_for__s_RemediationLock__`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180040fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180040ff4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180040ff4`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_RemediationLock__()
{
  if ( dword_1800540C0 )
    DeleteCriticalSection(&s_RemediationLock);
}

```

## disassembly

```asm
0x180040fe0  sub     rsp, 28h
0x180040fe4  cmp     cs:dword_1800540C0, 0
0x180040feb  jz      short loc_180040FFA
0x180040fed  lea     rcx, ?s_RemediationLock@@3VCCriticalSection@@A; lpCriticalSection
0x180040ff4  call    cs:__imp_DeleteCriticalSection
0x180040ffa  add     rsp, 28h
0x180040ffe  retn
```
