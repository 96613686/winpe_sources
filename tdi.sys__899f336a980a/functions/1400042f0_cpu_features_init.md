# __cpu_features_init

- ea: `0x1400042f0`
- end: `0x140004389`
- name: `__cpu_features_init`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005ac0`

## callees

- `0x1400042f0`

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
0x1400042f0  push    rbx
0x1400042f2  sub     rsp, 10h
0x1400042f6  xor     eax, eax
0x1400042f8  xor     ecx, ecx
0x1400042fa  cpuid
0x1400042fc  mov     r9d, eax
0x1400042ff  xor     ecx, ecx
0x140004301  mov     eax, 1
0x140004306  cpuid
0x140004308  mov     edx, ecx
0x14000430a  and     edx, 100000h
0x140004310  mov     eax, edx
0x140004312  neg     eax
0x140004314  sbb     r8b, r8b
0x140004317  and     r8b, 8
0x14000431b  test    edx, edx
0x14000431d  jz      short loc_140004343
0x14000431f  bt      ecx, 1Bh
0x140004323  jnb     short loc_140004343
0x140004325  bt      ecx, 1Ch
0x140004329  jnb     short loc_140004343
0x14000432b  xor     ecx, ecx
0x14000432d  xgetbv
0x140004330  shl     rdx, 20h
0x140004334  or      rdx, rax
0x140004337  and     dl, 6
0x14000433a  cmp     dl, 6
0x14000433d  jnz     short loc_140004343
0x14000433f  or      r8b, 4
0x140004343  mov     eax, 7
0x140004348  cmp     r9d, eax
0x14000434b  jl      short loc_140004375
0x14000434d  xor     ecx, ecx
0x14000434f  cpuid
0x140004351  mov     al, r8b
0x140004354  or      al, 2
0x140004356  movzx   ecx, al
0x140004359  bt      ebx, 9
0x14000435d  movzx   eax, r8b
0x140004361  cmovnb  ecx, eax
0x140004364  mov     r8b, cl
0x140004367  test    bl, 20h
0x14000436a  jz      short loc_140004375
0x14000436c  test    cl, 4
0x14000436f  jz      short loc_140004375
0x140004371  or      r8b, 10h
0x140004375  or      r8b, 1
0x140004379  mov     cs:__isa_info, r8b
0x140004380  xor     eax, eax
0x140004382  add     rsp, 10h
0x140004386  pop     rbx
0x140004387  retn
```
