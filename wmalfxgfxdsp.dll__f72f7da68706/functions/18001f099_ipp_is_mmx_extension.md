# ipp_is_mmx_extension

- ea: `0x18001f099`
- end: `0x18001f0b2`
- name: `ipp_is_mmx_extension`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
_BOOL8 ipp_is_mmx_extension()
{
  _RAX = 1;
  __asm { cpuid }
  return (_RDX & 0x800000) != 0;
}

```

## disassembly

```asm
0x18001f099  push    rbx
0x18001f09a  mov     rax, 1
0x18001f0a1  cpuid
0x18001f0a3  xor     rax, rax
0x18001f0a6  test    rdx, 800000h
0x18001f0ad  setnz   al
0x18001f0b0  pop     rbx
0x18001f0b1  retn
```
