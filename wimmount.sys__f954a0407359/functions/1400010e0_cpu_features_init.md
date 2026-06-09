# __cpu_features_init

- ea: `0x1400010e0`
- end: `0x140001179`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031c0`

## callees

- `0x1400010e0`

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
0x1400010e0  push    rbx
0x1400010e2  sub     rsp, 10h
0x1400010e6  xor     eax, eax
0x1400010e8  xor     ecx, ecx
0x1400010ea  cpuid
0x1400010ec  mov     r9d, eax
0x1400010ef  xor     ecx, ecx
0x1400010f1  mov     eax, 1
0x1400010f6  cpuid
0x1400010f8  mov     edx, ecx
0x1400010fa  and     edx, 100000h
0x140001100  mov     eax, edx
0x140001102  neg     eax
0x140001104  sbb     r8b, r8b
0x140001107  and     r8b, 8
0x14000110b  test    edx, edx
0x14000110d  jz      short loc_140001133
0x14000110f  bt      ecx, 1Bh
0x140001113  jnb     short loc_140001133
0x140001115  bt      ecx, 1Ch
0x140001119  jnb     short loc_140001133
0x14000111b  xor     ecx, ecx
0x14000111d  xgetbv
0x140001120  shl     rdx, 20h
0x140001124  or      rdx, rax
0x140001127  and     dl, 6
0x14000112a  cmp     dl, 6
0x14000112d  jnz     short loc_140001133
0x14000112f  or      r8b, 4
0x140001133  mov     eax, 7
0x140001138  cmp     r9d, eax
0x14000113b  jl      short loc_140001165
0x14000113d  xor     ecx, ecx
0x14000113f  cpuid
0x140001141  mov     al, r8b
0x140001144  or      al, 2
0x140001146  movzx   ecx, al
0x140001149  bt      ebx, 9
0x14000114d  movzx   eax, r8b
0x140001151  cmovnb  ecx, eax
0x140001154  mov     r8b, cl
0x140001157  test    bl, 20h
0x14000115a  jz      short loc_140001165
0x14000115c  test    cl, 4
0x14000115f  jz      short loc_140001165
0x140001161  or      r8b, 10h
0x140001165  or      r8b, 1
0x140001169  mov     cs:__isa_info, r8b
0x140001170  xor     eax, eax
0x140001172  add     rsp, 10h
0x140001176  pop     rbx
0x140001177  retn
```
