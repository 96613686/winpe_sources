# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)

- ea: `0x1800095a8`
- end: `0x1800095c7`
- name: `?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ec8`
- `0x18000e18c`
- `0x18000e440`
- `0x18000e6a4`
- `0x180010df0`

## callees

- `0x1800095a8`
- `0x1800095d0`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
        __int64 a1,
        _WORD *a2)
{
  unsigned __int64 v2; // r8

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
  return utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
           a1,
           a2,
           v2);
}

```

## disassembly

```asm
0x1800095a8  xor     eax, eax
0x1800095aa  test    rdx, rdx
0x1800095ad  jz      short loc_1800095BF
0x1800095af  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800095b3  inc     r8
0x1800095b6  cmp     [rdx+r8*2], ax
0x1800095bb  jnz     short loc_1800095B3
0x1800095bd  jmp     short loc_1800095C2
0x1800095bf  mov     r8, rax
0x1800095c2  jmp     ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
```
