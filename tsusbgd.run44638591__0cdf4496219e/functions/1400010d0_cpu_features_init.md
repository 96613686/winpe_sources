# __cpu_features_init

- ea: `0x1400010d0`
- end: `0x140001169`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140006600`

## callees

- `0x1400010d0`

## pseudocode

```c
__int64 _cpu_features_init()
{
  int v5; // r9d
  char v11; // r8
  char v17; // cl

  _RAX = 0;
  __asm { cpuid }
  v5 = _RAX;
  _RAX = 1;
  __asm { cpuid }
  v11 = (_RCX & 0x100000) != 0 ? 8 : 0;
  if ( (_RCX & 0x100000) != 0 && (_RCX & 0x8000000) != 0 && (_RCX & 0x10000000) != 0 )
    __asm { xgetbv }
  _RAX = 7;
  if ( v5 >= 7 )
  {
    __asm { cpuid }
    v17 = v11 | 2;
    if ( (_RBX & 0x200) == 0 )
      v17 = v11;
    v11 = v17;
    if ( (_RBX & 0x20) != 0 && (v17 & 4) != 0 )
      v11 = v17 | 0x10;
  }
  _isa_info = v11 | 1;
  return 0;
}

```

## disassembly

```asm
0x1400010d0  push    rbx
0x1400010d2  sub     rsp, 10h
0x1400010d6  xor     eax, eax
0x1400010d8  xor     ecx, ecx
0x1400010da  cpuid
0x1400010dc  mov     r9d, eax
0x1400010df  xor     ecx, ecx
0x1400010e1  mov     eax, 1
0x1400010e6  cpuid
0x1400010e8  mov     edx, ecx
0x1400010ea  and     edx, 100000h
0x1400010f0  mov     eax, edx
0x1400010f2  neg     eax
0x1400010f4  sbb     r8b, r8b
0x1400010f7  and     r8b, 8
0x1400010fb  test    edx, edx
0x1400010fd  jz      short loc_140001123
0x1400010ff  bt      ecx, 1Bh
0x140001103  jnb     short loc_140001123
0x140001105  bt      ecx, 1Ch
0x140001109  jnb     short loc_140001123
0x14000110b  xor     ecx, ecx
0x14000110d  xgetbv
0x140001110  shl     rdx, 20h
0x140001114  or      rdx, rax
0x140001117  and     dl, 6
0x14000111a  cmp     dl, 6
0x14000111d  jnz     short loc_140001123
0x14000111f  or      r8b, 4
0x140001123  mov     eax, 7
0x140001128  cmp     r9d, eax
0x14000112b  jl      short loc_140001155
0x14000112d  xor     ecx, ecx
0x14000112f  cpuid
0x140001131  mov     al, r8b
0x140001134  or      al, 2
0x140001136  movzx   ecx, al
0x140001139  bt      ebx, 9
0x14000113d  movzx   eax, r8b
0x140001141  cmovnb  ecx, eax
0x140001144  mov     r8b, cl
0x140001147  test    bl, 20h
0x14000114a  jz      short loc_140001155
0x14000114c  test    cl, 4
0x14000114f  jz      short loc_140001155
0x140001151  or      r8b, 10h
0x140001155  or      r8b, 1
0x140001159  mov     cs:__isa_info, r8b
0x140001160  xor     eax, eax
0x140001162  add     rsp, 10h
0x140001166  pop     rbx
0x140001167  retn
```
