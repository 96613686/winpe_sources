# _dynamic_atexit_destructor_for__g_ProviderLock__

- ea: `0x180033cf0`
- end: `0x180033d20`
- name: `_dynamic_atexit_destructor_for__g_ProviderLock__`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180033cf0`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180033d04`
- `ntdll!RtlDeleteResource` at `0x180033d04`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_ProviderLock__()
{
  if ( dword_18005A5B0 )
    RtlDeleteResource(&g_ProviderLock);
  dword_18005A5B0 = 0;
}

```

## disassembly

```asm
0x180033cf0  sub     rsp, 28h
0x180033cf4  cmp     cs:dword_18005A5B0, 0
0x180033cfb  jz      short loc_180033D10
0x180033cfd  lea     rcx, ?g_ProviderLock@@3VCResource@@A; Resource
0x180033d04  call    cs:__imp_RtlDeleteResource
0x180033d0b  nop     dword ptr [rax+rax+00h]
0x180033d10  mov     cs:dword_18005A5B0, 0
0x180033d1a  add     rsp, 28h
0x180033d1e  retn
```
