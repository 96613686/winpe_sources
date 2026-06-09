# ChpCreateGpaRanges

- ea: `0x14000f070`
- end: `0x14000f152`
- name: `ChpCreateGpaRanges`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f158`

## callees

- `0x1400033e0`
- `0x14000f070`
- `0x140015018`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f0ec`
- `ntoskrnl!ExAllocatePool2` at `0x14000f0ec`

## pseudocode

```c
__int64 __fastcall ChpCreateGpaRanges(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 *a4,
        unsigned int *a5,
        _DWORD *a6)
{
  int v9; // r14d
  unsigned int v11; // eax
  int v12; // r15d
  unsigned int v13; // ebx
  __int64 Pool2; // rax
  int v15; // ecx
  __int64 v16; // rbp
  unsigned int *v17; // rax
  int v18; // [rsp+78h] [rbp+10h] BYREF

  v9 = a1;
  if ( a2 && !a3 )
    return 3221225712LL;
  v18 = 0;
  v11 = PkCalculateGpaRangesSize(a1, &v18, a2, a3);
  v12 = v18;
  v13 = v11;
  if ( !v18 )
    return 3221225715LL;
  if ( v11 > 0xFFFF )
    return 2147483653LL;
  Pool2 = ExAllocatePool2(64, v11, 1937072726);
  v16 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  PkCreateGpaRangesEx(v15, v9, Pool2, v13, a2, a3);
  *a6 = v12;
  v17 = a5;
  *a4 = v16;
  *v17 = v13;
  return 0;
}

```

## disassembly

```asm
0x14000f070  mov     [rsp+arg_0], rbx
0x14000f075  mov     [rsp+arg_10], rbp
0x14000f07a  push    rsi
0x14000f07b  push    rdi
0x14000f07c  push    r12
0x14000f07e  push    r14
0x14000f080  push    r15
0x14000f082  sub     rsp, 40h
0x14000f086  mov     r12, r9
0x14000f089  mov     edi, r8d
0x14000f08c  mov     esi, edx
0x14000f08e  mov     r14, rcx
0x14000f091  test    edx, edx
0x14000f093  jz      short loc_14000F0A4
0x14000f095  test    r8d, r8d
0x14000f098  jnz     short loc_14000F0A4
0x14000f09a  mov     eax, 0C00000F0h
0x14000f09f  jmp     loc_14000F138
0x14000f0a4  mov     r9d, edi
0x14000f0a7  mov     [rsp+68h+arg_8], 0
0x14000f0af  mov     r8d, esi
0x14000f0b2  lea     rdx, [rsp+68h+arg_8]
0x14000f0b7  call    PkCalculateGpaRangesSize
0x14000f0bc  mov     r15d, [rsp+68h+arg_8]
0x14000f0c1  mov     ebx, eax
0x14000f0c3  test    r15d, r15d
0x14000f0c6  jnz     short loc_14000F0CF
0x14000f0c8  mov     eax, 0C00000F3h
0x14000f0cd  jmp     short loc_14000F138
0x14000f0cf  cmp     ebx, 0FFFFh
0x14000f0d5  jbe     short loc_14000F0DE
0x14000f0d7  mov     eax, 80000005h
0x14000f0dc  jmp     short loc_14000F138
0x14000f0de  mov     rdx, rbx
0x14000f0e1  mov     ecx, 40h ; '@'
0x14000f0e6  mov     r8d, 73756256h
0x14000f0ec  call    cs:__imp_ExAllocatePool2
0x14000f0f3  nop     dword ptr [rax+rax+00h]
0x14000f0f8  mov     rbp, rax
0x14000f0fb  test    rax, rax
0x14000f0fe  jnz     short loc_14000F107
0x14000f100  mov     eax, 0C000009Ah
0x14000f105  jmp     short loc_14000F138
0x14000f107  mov     [rsp+68h+var_40], edi
0x14000f10b  mov     r9d, ebx
0x14000f10e  mov     r8, rbp
0x14000f111  mov     [rsp+68h+var_48], esi
0x14000f115  mov     rdx, r14
0x14000f118  call    PkCreateGpaRangesEx
0x14000f11d  mov     rax, [rsp+68h+arg_28]
0x14000f125  mov     [rax], r15d
0x14000f128  mov     rax, [rsp+68h+arg_20]
0x14000f130  mov     [r12], rbp
0x14000f134  mov     [rax], ebx
0x14000f136  xor     eax, eax
0x14000f138  lea     r11, [rsp+68h+var_28]
0x14000f13d  mov     rbx, [r11+30h]
0x14000f141  mov     rbp, [r11+40h]
0x14000f145  mov     rsp, r11
0x14000f148  pop     r15
0x14000f14a  pop     r14
0x14000f14c  pop     r12
0x14000f14e  pop     rdi
0x14000f14f  pop     rsi
0x14000f150  retn
```
