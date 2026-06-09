# _dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__

- ea: `0x180079b50`
- end: `0x180079b76`
- name: `_dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180079b50`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180079b64`
- `KERNEL32!DeleteCriticalSection` at `0x180079b64`

## pseudocode

```c
void dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__()
{
  if ( byte_1800937C1 )
    DeleteCriticalSection(&ThreadGlobals::g_mutx);
}

```

## disassembly

```asm
0x180079b50  sub     rsp, 28h
0x180079b54  cmp     cs:byte_1800937C1, 0
0x180079b5b  jz      short loc_180079B70
0x180079b5d  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; lpCriticalSection
0x180079b64  call    cs:__imp_DeleteCriticalSection
0x180079b6b  nop     dword ptr [rax+rax+00h]
0x180079b70  add     rsp, 28h
0x180079b74  retn
```
