# RegionCore_bInside_point

- ea: `0x140004a50`
- end: `0x140004a63`
- name: `RegionCore_bInside_point`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000b0e0`

## pseudocode

```c
__int64 RegionCore_bInside_point()
{
  return (unsigned int)(unsigned __int8)RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore14contains_point() + 1;
}

```

## disassembly

```asm
0x140004a50  sub     rsp, 28h
0x140004a54  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore14contains_point
0x140004a59  movzx   eax, al
0x140004a5c  inc     eax
0x140004a5e  add     rsp, 28h
0x140004a62  retn
```
