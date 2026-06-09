# SlbNatUpdateInstanceInterfaces

- ea: `0x140033c98`
- end: `0x140033cbf`
- name: `SlbNatUpdateInstanceInterfaces`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14002e380`
- `0x14002e560`

## callees

- `0x14002e0c0`
- `0x140033c98`
- `0x140033cc8`

## pseudocode

```c
__int64 __fastcall SlbNatUpdateInstanceInterfaces(
        __int64 a1,
        __int64 a2,
        const NET_LUID *a3,
        const NET_LUID *a4,
        unsigned int a5)
{
  if ( *(_BYTE *)(a1 + 230) )
    return SlbNatUpdateInternalPrefixInstanceInterfaces(a1, a2, a3, a4, a5);
  else
    return SlbNatUpdateExternalPrefixInstanceInterfaces(a1, a2, (__int64)a3, (__int64)a4, a5);
}

```

## disassembly

```asm
0x140033c98  sub     rsp, 38h
0x140033c9c  cmp     byte ptr [rcx+0E6h], 0
0x140033ca3  mov     eax, [rsp+38h+arg_20]
0x140033ca7  mov     [rsp+38h+var_18], eax
0x140033cab  jbe     short loc_140033CB4
0x140033cad  call    SlbNatUpdateInternalPrefixInstanceInterfaces
0x140033cb2  jmp     short loc_140033CB9
0x140033cb4  call    SlbNatUpdateExternalPrefixInstanceInterfaces
0x140033cb9  add     rsp, 38h
0x140033cbd  retn
```
