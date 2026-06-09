# RegionCore_bInside_rcl

- ea: `0x140004a70`
- end: `0x140004a83`
- name: `RegionCore_bInside_rcl`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000a990`

## pseudocode

```c
__int64 RegionCore_bInside_rcl()
{
  return (unsigned int)(unsigned __int8)RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore10intersects() + 1;
}

```

## disassembly

```asm
0x140004a70  sub     rsp, 28h
0x140004a74  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore10intersects
0x140004a79  movzx   eax, al
0x140004a7c  inc     eax
0x140004a7e  add     rsp, 28h
0x140004a82  retn
```
