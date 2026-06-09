# __cpu_features_init

- ea: `0x140003040`
- end: `0x1400030d9`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400036c0`

## callees

- `0x140003040`

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
0x140003040  push    rbx
0x140003042  sub     rsp, 10h
0x140003046  xor     eax, eax
0x140003048  xor     ecx, ecx
0x14000304a  cpuid
0x14000304c  mov     r9d, eax
0x14000304f  xor     ecx, ecx
0x140003051  mov     eax, 1
0x140003056  cpuid
0x140003058  mov     edx, ecx
0x14000305a  and     edx, 100000h
0x140003060  mov     eax, edx
0x140003062  neg     eax
0x140003064  sbb     r8b, r8b
0x140003067  and     r8b, 8
0x14000306b  test    edx, edx
0x14000306d  jz      short loc_140003093
0x14000306f  bt      ecx, 1Bh
0x140003073  jnb     short loc_140003093
0x140003075  bt      ecx, 1Ch
0x140003079  jnb     short loc_140003093
0x14000307b  xor     ecx, ecx
0x14000307d  xgetbv
0x140003080  shl     rdx, 20h
0x140003084  or      rdx, rax
0x140003087  and     dl, 6
0x14000308a  cmp     dl, 6
0x14000308d  jnz     short loc_140003093
0x14000308f  or      r8b, 4
0x140003093  mov     eax, 7
0x140003098  cmp     r9d, eax
0x14000309b  jl      short loc_1400030C5
0x14000309d  xor     ecx, ecx
0x14000309f  cpuid
0x1400030a1  mov     al, r8b
0x1400030a4  or      al, 2
0x1400030a6  movzx   ecx, al
0x1400030a9  bt      ebx, 9
0x1400030ad  movzx   eax, r8b
0x1400030b1  cmovnb  ecx, eax
0x1400030b4  mov     r8b, cl
0x1400030b7  test    bl, 20h
0x1400030ba  jz      short loc_1400030C5
0x1400030bc  test    cl, 4
0x1400030bf  jz      short loc_1400030C5
0x1400030c1  or      r8b, 10h
0x1400030c5  or      r8b, 1
0x1400030c9  mov     cs:__isa_info, r8b
0x1400030d0  xor     eax, eax
0x1400030d2  add     rsp, 10h
0x1400030d6  pop     rbx
0x1400030d7  retn
```
