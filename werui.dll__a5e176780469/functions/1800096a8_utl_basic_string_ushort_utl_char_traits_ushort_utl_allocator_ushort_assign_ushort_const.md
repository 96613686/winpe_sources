# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)

- ea: `0x1800096a8`
- end: `0x1800096c7`
- name: `?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180006440`
- `0x1800080d8`
- `0x180008668`
- `0x180009c80`
- `0x18000a14c`
- `0x18000a238`
- `0x18000b5dc`
- `0x18000d4c0`
- `0x18000d6b8`
- `0x18000e6a4`
- `0x180010df0`
- `0x180012b0c`
- `0x180012d68`

## callees

- `0x1800096a8`
- `0x1800096d0`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
        _QWORD *a1,
        _WORD *a2)
{
  __int64 v2; // r8

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a2[v2] );
  }
  else
  {
    v2 = 0;
  }
  return utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
           a1,
           a2,
           v2);
}

```

## disassembly

```asm
0x1800096a8  xor     eax, eax
0x1800096aa  test    rdx, rdx
0x1800096ad  jz      short loc_1800096BF
0x1800096af  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800096b3  inc     r8
0x1800096b6  cmp     [rdx+r8*2], ax
0x1800096bb  jnz     short loc_1800096B3
0x1800096bd  jmp     short loc_1800096C2
0x1800096bf  mov     r8, rax
0x1800096c2  jmp     ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
```
