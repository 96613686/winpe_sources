# RegionCore_bCopy

- ea: `0x1400049d0`
- end: `0x1400049e7`
- name: `RegionCore_bCopy`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000bc20`

## pseudocode

```c
_BOOL8 RegionCore_bCopy()
{
  return (unsigned int)RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore17set_to_scans_from() == 0;
}

```

## disassembly

```asm
0x1400049d0  sub     rsp, 28h
0x1400049d4  call    _RNvMs_CsdcpJtfrLhSH_7rgncoreNtB4_10RegionCore17set_to_scans_from
0x1400049d9  xor     ecx, ecx
0x1400049db  test    eax, eax
0x1400049dd  setz    cl
0x1400049e0  mov     eax, ecx
0x1400049e2  add     rsp, 28h
0x1400049e6  retn
```
