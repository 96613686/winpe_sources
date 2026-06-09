# _dynamic_atexit_destructor_for__g_localAddr__

- ea: `0x18000f310`
- end: `0x18000f33b`
- name: `_dynamic_atexit_destructor_for__g_localAddr__`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f310`
- `0x18000f344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f330`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f330`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_localAddr__()
{
  CLocalHostAddress::Cleanup((CLocalHostAddress *)&g_localAddr);
  if ( *(&g_localAddr + 1) )
    DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18000f310  sub     rsp, 28h
0x18000f314  lea     rcx, ?g_localAddr@@3VCLocalHostAddress@@A; this
0x18000f31b  call    ?Cleanup@CLocalHostAddress@@AEAAXXZ; CLocalHostAddress::Cleanup(void)
0x18000f320  cmp     dword ptr cs:?g_localAddr@@3VCLocalHostAddress@@A+4, 0; CLocalHostAddress g_localAddr
0x18000f327  jz      short loc_18000F336
0x18000f329  lea     rcx, CriticalSection; lpCriticalSection
0x18000f330  call    cs:__imp_DeleteCriticalSection
0x18000f336  add     rsp, 28h
0x18000f33a  retn
```
