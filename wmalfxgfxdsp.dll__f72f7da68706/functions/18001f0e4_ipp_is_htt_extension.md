# ipp_is_htt_extension

- ea: `0x18001f0e4`
- end: `0x18001f109`
- name: `ipp_is_htt_extension`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f0e4`

## pseudocode

```c
bool ipp_is_htt_extension()
{
  _RAX = 1;
  __asm { cpuid }
  if ( (_RDX & 0x10000000) == 0 )
    BYTE2(_RBX) = 0;
  return BYTE2(_RBX) > 1u;
}

```

## disassembly

```asm
0x18001f0e4  push    rbx
0x18001f0e5  mov     rax, 1
0x18001f0ec  cpuid
0x18001f0ee  xor     rax, rax
0x18001f0f1  test    rdx, 10000000h
0x18001f0f8  jnz     short loc_18001F0FD
0x18001f0fa  mov     rbx, rax
0x18001f0fd  shr     rbx, 10h
0x18001f101  cmp     bl, 1
0x18001f104  setnbe  al
0x18001f107  pop     rbx
0x18001f108  retn
```
