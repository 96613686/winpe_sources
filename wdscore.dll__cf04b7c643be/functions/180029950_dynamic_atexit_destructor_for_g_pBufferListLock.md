# _dynamic_atexit_destructor_for__g_pBufferListLock__

- ea: `0x180029950`
- end: `0x180029977`
- name: `_dynamic_atexit_destructor_for__g_pBufferListLock__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029964`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029964`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void dynamic_atexit_destructor_for__g_pBufferListLock__()
{
  DeleteCriticalSection(&g_pBufferListLock);
}

```

## disassembly

```asm
0x180029950  sub     rsp, 38h
0x180029954  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002995d  lea     rcx, ?g_pBufferListLock@@3VCWdsCritSection@@A; lpCriticalSection
0x180029964  call    cs:__imp_DeleteCriticalSection
0x18002996b  nop     dword ptr [rax+rax+00h]
0x180029970  nop
0x180029971  add     rsp, 38h
0x180029975  retn
```
