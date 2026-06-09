# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)

- ea: `0x180005c80`
- end: `0x180005c94`
- name: `??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z`
- size: `20`
- prototype: `void(void *)`
- caller_count: `34`
- callee_count: `0`
- tags: ``

## callers

- `0x180005fec`
- `0x180006440`
- `0x18000765c`
- `0x180007e50`
- `0x1800080d8`
- `0x1800083c0`
- `0x1800084b8`
- `0x180008528`
- `0x180008668`
- `0x18000899c`
- `0x180008cd0`
- `0x180008ec8`
- `0x180009944`
- `0x180009a30`
- `0x180009d14`
- `0x18000b5dc`
- `0x18000cbc8`
- `0x18000e18c`
- `0x18000e440`
- `0x18000e6a4`
- `0x18000ea8c`
- `0x18000ec8c`
- `0x18000f504`
- `0x18000f834`
- `0x18000fb24`
- `0x18000fc94`
- `0x1800105c8`
- `0x180010df0`
- `0x1800117fc`
- `0x180012b0c`
- `0x18001326c`
- `0x180013580`
- `0x180013ce8`
- `0x1800148a8`

## pseudocode

```c
void __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
        _QWORD *a1)
{
  *a1 = a1 + 2;
  a1[1] = a1 + 2;
  *((_WORD *)a1 + 8) = 0;
}

```

## disassembly

```asm
0x180005c80  lea     rax, [rcx+10h]
0x180005c84  xor     edx, edx
0x180005c86  mov     [rcx], rax
0x180005c89  mov     [rcx+8], rax
0x180005c8d  mov     [rax], dx
0x180005c90  mov     rax, rcx
0x180005c93  retn
```
