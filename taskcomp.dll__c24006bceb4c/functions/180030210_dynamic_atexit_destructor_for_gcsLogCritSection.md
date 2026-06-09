# _dynamic_atexit_destructor_for__gcsLogCritSection__

- ea: `0x180030210`
- end: `0x180030228`
- name: `_dynamic_atexit_destructor_for__gcsLogCritSection__`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180030210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030220`

## pseudocode

```c
void dynamic_atexit_destructor_for__gcsLogCritSection__()
{
  if ( byte_18005E188 )
    DeleteCriticalSection(&gcsLogCritSection);
}

```

## disassembly

```asm
0x180030210  cmp     cs:byte_18005E188, 0
0x180030217  jz      short locret_180030227
0x180030219  lea     rcx, ?gcsLogCritSection@@3VCStaticCritSec@@A; CStaticCritSec gcsLogCritSection
0x180030220  jmp     cs:__imp_DeleteCriticalSection
0x180030227  retn
```
