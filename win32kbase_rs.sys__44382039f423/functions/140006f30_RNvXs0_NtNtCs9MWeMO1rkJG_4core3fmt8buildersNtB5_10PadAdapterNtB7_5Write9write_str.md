# _RNvXs0_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_10PadAdapterNtB7_5Write9write_str

- ea: `0x140006f30`
- end: `0x1400071e5`
- name: `_RNvXs0_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_10PadAdapterNtB7_5Write9write_str`
- size: `693`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005670`
- `0x140007c60`

## callees

- `0x140006f30`
- `0x140017a50`

## pseudocode

```c
char __fastcall RNvXs0_NtNtCs9MWeMO1rkJG_4core3fmt8buildersNtB5_10PadAdapterNtB7_5Write9write_str(
        __int64 *a1,
        __int64 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // r12
  __int64 v4; // rbp
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  char v7; // r13
  bool v8; // al
  char v9; // al
  unsigned __int64 v10; // r15
  __int64 v11; // r9
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // r10
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // r8
  __int64 v17; // r14
  unsigned __int64 v18; // rbp
  unsigned __int64 v19; // r12
  char v20; // al
  unsigned __int64 v23; // [rsp+30h] [rbp-68h]
  __int64 v24; // [rsp+38h] [rbp-60h]
  __int64 v25; // [rsp+40h] [rbp-58h]
  bool *v26; // [rsp+48h] [rbp-50h]
  __int64 v27; // [rsp+50h] [rbp-48h]

  v3 = 0x8080808080808080uLL;
  v4 = 0xA0A0A0A0A0A0A0ALL;
  v26 = (bool *)a1[2];
  v25 = *a1;
  v24 = a1[1];
  v27 = a2 + 8;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v23 = a3;
  do
  {
    if ( (v7 & 1) != 0 )
      return 0;
    if ( a3 < v5 )
    {
      v10 = v5;
      v11 = a2;
      goto LABEL_32;
    }
    v11 = a2;
    while ( 1 )
    {
      v12 = a3 - v5;
      v13 = v11 + v5;
      if ( a3 - v5 > 0xF )
        break;
      if ( a3 == v5 )
        goto LABEL_31;
      v14 = 0;
      while ( *(_BYTE *)(v13 + v14) != 10 )
      {
        if ( v12 == ++v14 )
          goto LABEL_31;
      }
LABEL_28:
      v10 = v5 + v14 + 1;
      if ( v14 + v5 < a3 && *(_BYTE *)(v14 + v13) == 10 )
      {
        v17 = v4;
        v18 = v3;
        v7 = 0;
        v5 += v14 + 1;
        v19 = v10;
        goto LABEL_33;
      }
      v5 += v14 + 1;
      if ( a3 < v10 )
        goto LABEL_32;
    }
    v15 = ((v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL) - v13;
    if ( v15 )
    {
      v14 = 0;
      while ( *(_BYTE *)(v13 + v14) != 10 )
      {
        if ( v15 == ++v14 )
        {
          v16 = v12 - 16;
          if ( v15 <= v12 - 16 )
            goto LABEL_17;
          goto LABEL_24;
        }
      }
      goto LABEL_28;
    }
    v16 = v12 - 16;
    v15 = 0;
    do
    {
LABEL_17:
      if ( ((v4 ^ *(_QWORD *)(v5 + v27 + v15) | (0x101010101010100LL - (v4 ^ *(_QWORD *)(v5 + v27 + v15))))
          & v3
          & (*(_QWORD *)(v5 + v27 + v15 - 8) | (0x101010101010100LL - (v4 ^ *(_QWORD *)(v5 + v27 + v15 - 8))))) != v3 )
        break;
      v15 += 16LL;
    }
    while ( v15 <= v16 );
LABEL_24:
    v14 = v15;
    v11 = a2;
    a3 = v23;
    if ( v12 != v15 )
    {
      while ( *(_BYTE *)(v13 + v14) != 10 )
      {
        if ( v12 == ++v14 )
          goto LABEL_31;
      }
      goto LABEL_28;
    }
LABEL_31:
    v10 = a3;
LABEL_32:
    v17 = v4;
    v18 = v3;
    v7 = 1;
    v5 = v10;
    v10 = v6;
    v19 = a3;
    if ( a3 == v6 )
      return 0;
LABEL_33:
    if ( *v26 )
    {
      v20 = (*(__int64 (__fastcall **)(__int64, char *, __int64))(v24 + 24))(v25, byte_14001CC33, 4);
      v11 = a2;
      if ( v20 )
        break;
    }
    v8 = v19 != v6 && *(_BYTE *)(v11 + v19 - 1) == 10;
    *v26 = v8;
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int64))(v24 + 24))(v25, v11 + v6, v19 - v6);
    v6 = v10;
    v3 = v18;
    v4 = v17;
    a3 = v23;
  }
  while ( !v9 );
  return 1;
}

```

## disassembly

```asm
0x140006f30  push    r15
0x140006f32  push    r14
0x140006f34  push    r13
0x140006f36  push    r12
0x140006f38  push    rsi
0x140006f39  push    rdi
0x140006f3a  push    rbp
0x140006f3b  push    rbx
0x140006f3c  sub     rsp, 58h
0x140006f40  mov     r12, 8080808080808080h
0x140006f4a  mov     rbp, 0A0A0A0A0A0A0A0Ah
0x140006f54  mov     rsi, 101010101010100h
0x140006f5e  mov     rax, [rcx+10h]
0x140006f62  mov     [rsp+98h+var_50], rax
0x140006f67  mov     rax, [rcx]
0x140006f6a  mov     [rsp+98h+var_58], rax
0x140006f6f  mov     rax, [rcx+8]
0x140006f73  mov     [rsp+98h+var_60], rax
0x140006f78  mov     [rsp+98h+var_70], rdx
0x140006f7d  lea     rax, [rdx+8]
0x140006f81  mov     [rsp+98h+var_48], rax
0x140006f86  xor     ebx, ebx
0x140006f88  xor     edi, edi
0x140006f8a  xor     r13d, r13d
0x140006f8d  mov     [rsp+98h+var_68], r8
0x140006f92  jmp     short loc_140006FE6
0x140006fa0  cmp     byte ptr [r9+r12-1], 0Ah
0x140006fa6  setz    al
0x140006fa9  sub     r12, rdi
0x140006fac  add     rdi, r9
0x140006faf  mov     rcx, [rsp+98h+var_50]
0x140006fb4  mov     [rcx], al
0x140006fb6  mov     rax, [rsp+98h+var_60]
0x140006fbb  mov     rax, [rax+18h]
0x140006fbf  mov     rcx, [rsp+98h+var_58]
0x140006fc4  mov     rdx, rdi
0x140006fc7  mov     r8, r12
0x140006fca  call    cs:__guard_dispatch_icall_fptr
0x140006fd0  mov     rdi, r15
0x140006fd3  test    al, al
0x140006fd5  mov     r12, rbp
0x140006fd8  mov     rbp, r14
0x140006fdb  mov     r8, [rsp+98h+var_68]
0x140006fe0  jnz     loc_1400071D2
0x140006fe6  test    r13b, 1
0x140006fea  jnz     loc_1400071CE
0x140006ff0  cmp     r8, rbx
0x140006ff3  jnb     short loc_140007010
0x140006ff5  mov     r15, rbx
0x140006ff8  mov     r9, [rsp+98h+var_70]
0x140006ffd  jmp     loc_140007173
0x140007010  mov     r9, [rsp+98h+var_70]
0x140007015  jmp     short loc_14000702C
0x140007020  mov     rbx, r15
0x140007023  cmp     r8, r15
0x140007026  jb      loc_140007173
0x14000702c  mov     rcx, r8
0x14000702f  sub     rcx, rbx
0x140007032  lea     rax, [r9+rbx]
0x140007036  cmp     rcx, 0Fh
0x14000703a  ja      short loc_140007070
0x14000703c  cmp     r8, rbx
0x14000703f  jz      loc_140007170
0x140007045  xor     r10d, r10d
0x140007048  nop     dword ptr [rax+rax+00000000h]
0x140007050  cmp     byte ptr [rax+r10], 0Ah
0x140007055  jz      loc_140007140
0x14000705b  inc     r10
0x14000705e  cmp     rcx, r10
0x140007061  jnz     short loc_140007050
0x140007063  jmp     loc_140007170
0x140007070  lea     rdx, [rax+7]
0x140007074  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140007078  sub     rdx, rax
0x14000707b  jnz     short loc_1400070D0
0x14000707d  lea     r8, [rcx-10h]
0x140007081  xor     edx, edx
0x140007083  mov     r9, [rsp+98h+var_48]
0x140007088  add     r9, rbx
0x14000708b  nop     dword ptr [rax+rax+00h]
0x140007090  mov     r10, [r9+rdx-8]
0x140007095  mov     r11, r10
0x140007098  xor     r11, rbp
0x14000709b  mov     r15, rsi
0x14000709e  sub     r15, r11
0x1400070a1  or      r15, r10
0x1400070a4  mov     r10, [r9+rdx]
0x1400070a8  xor     r10, rbp
0x1400070ab  mov     r11, rsi
0x1400070ae  sub     r11, r10
0x1400070b1  or      r11, r10
0x1400070b4  and     r15, r12
0x1400070b7  and     r15, r11
0x1400070ba  cmp     r15, r12
0x1400070bd  jnz     short loc_140007100
0x1400070bf  add     rdx, 10h
0x1400070c3  cmp     rdx, r8
0x1400070c6  jbe     short loc_140007090
0x1400070c8  jmp     short loc_140007100
0x1400070d0  xor     r10d, r10d
0x1400070d3  nop     word ptr [rax+rax+00000000h]
0x1400070e0  cmp     byte ptr [rax+r10], 0Ah
0x1400070e5  jz      short loc_140007140
0x1400070e7  inc     r10
0x1400070ea  cmp     rdx, r10
0x1400070ed  jnz     short loc_1400070E0
0x1400070ef  lea     r8, [rcx-10h]
0x1400070f3  cmp     rdx, r8
0x1400070f6  jbe     short loc_140007083
0x1400070f8  nop     dword ptr [rax+rax+00000000h]
0x140007100  mov     r10, rdx
0x140007103  cmp     rcx, rdx
0x140007106  mov     r9, [rsp+98h+var_70]
0x14000710b  mov     r8, [rsp+98h+var_68]
0x140007110  jz      short loc_140007170
0x140007112  nop     word ptr [rax+rax+00000000h]
0x140007120  cmp     byte ptr [rax+r10], 0Ah
0x140007125  jz      short loc_140007140
0x140007127  inc     r10
0x14000712a  cmp     rcx, r10
0x14000712d  jnz     short loc_140007120
0x14000712f  jmp     short loc_140007170
0x140007140  lea     r15, [rbx+r10]
0x140007144  inc     r15
0x140007147  add     rbx, r10
0x14000714a  cmp     rbx, r8
0x14000714d  jnb     loc_140007020
0x140007153  cmp     byte ptr [r10+rax], 0Ah
0x140007158  jnz     loc_140007020
0x14000715e  mov     r14, rbp
0x140007161  mov     rbp, r12
0x140007164  xor     r13d, r13d
0x140007167  mov     rbx, r15
0x14000716a  mov     r12, r15
0x14000716d  jmp     short loc_14000718A
0x140007170  mov     r15, r8
0x140007173  mov     r14, rbp
0x140007176  mov     rbp, r12
0x140007179  mov     r13b, 1
0x14000717c  mov     rbx, r15
0x14000717f  mov     r15, rdi
0x140007182  mov     r12, r8
0x140007185  cmp     r8, rdi
0x140007188  jz      short loc_1400071CE
0x14000718a  mov     rax, [rsp+98h+var_50]
0x14000718f  cmp     byte ptr [rax], 0
0x140007192  jz      short loc_1400071BE
0x140007194  mov     rax, [rsp+98h+var_60]
0x140007199  mov     rax, [rax+18h]
0x14000719d  mov     r8d, 4
0x1400071a3  mov     rcx, [rsp+98h+var_58]
0x1400071a8  lea     rdx, byte_14001CC33
0x1400071af  call    cs:__guard_dispatch_icall_fptr
0x1400071b5  mov     r9, [rsp+98h+var_70]
0x1400071ba  test    al, al
0x1400071bc  jnz     short loc_1400071D2
0x1400071be  cmp     r12, rdi
0x1400071c1  jnz     loc_140006FA0
0x1400071c7  xor     eax, eax
0x1400071c9  jmp     loc_140006FA9
0x1400071ce  xor     eax, eax
0x1400071d0  jmp     short loc_1400071D4
0x1400071d2  mov     al, 1
0x1400071d4  add     rsp, 58h
0x1400071d8  pop     rbx
0x1400071d9  pop     rbp
0x1400071da  pop     rdi
0x1400071db  pop     rsi
0x1400071dc  pop     r12
0x1400071de  pop     r13
0x1400071e0  pop     r14
0x1400071e2  pop     r15
0x1400071e4  retn
```
