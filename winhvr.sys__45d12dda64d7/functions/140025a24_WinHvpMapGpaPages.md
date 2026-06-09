# WinHvpMapGpaPages

- ea: `0x140025a24`
- end: `0x140025ce1`
- name: `WinHvpMapGpaPages`
- size: `701`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x14001b440`
- `0x14001b4b0`
- `0x14001b520`
- `0x140021ec0`
- `0x140021f80`
- `0x140025990`
- `0x1400259e0`

## callees

- `0x140004398`
- `0x140009c90`
- `0x14000a040`
- `0x1400257c0`
- `0x140025a24`
- `0x140025ce8`

## pseudocode

```c
__int64 __fastcall WinHvpMapGpaPages(
        int a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        _QWORD *a8)
{
  char v10; // r10
  int v11; // r12d
  char v12; // al
  _QWORD *v13; // r13
  unsigned int v15; // r13d
  unsigned __int64 v16; // rbx
  unsigned __int64 i; // rdi
  int v18; // r8d
  __int64 v19; // rax
  unsigned int v21; // r11d
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // r13
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // [rsp+58h] [rbp-49h] BYREF
  __int64 v31; // [rsp+60h] [rbp-41h] BYREF
  _QWORD v32[14]; // [rsp+68h] [rbp-39h] BYREF

  memset(v32, 0, 0x40u);
  v10 = a7;
  v11 = 0;
  v12 = v32[3];
  v13 = a8;
  if ( (a7 & 2) != 0 )
    v12 = 1;
  LOBYTE(v32[3]) = v12;
  v30 = 0;
  v31 = 0;
  *a8 = 0;
  a7 = 0;
  if ( (v10 & 1) != 0 )
  {
    v15 = a4;
    v16 = ((a2 + 511) & 0xFFFFFFFFFFFFFE00uLL) - a2;
    if ( v16 >= a3 )
      v16 = a3;
    for ( i = a3 - v16; i; i -= v24 )
    {
      while ( v16 >= 0x1FD )
      {
        v27 = WinHvpMapGpaPagesHypercall(a1, a2, 509, v15, a5, a6, (__int64)v32, (__int64)&a7, (__int64)&v30);
        v28 = v30;
        v11 = v27;
        v29 = v30;
        *a8 += v30;
        if ( v27 < 0 )
          goto LABEL_13;
        a2 += v28;
        a5 += a6 * (unsigned int)v28;
        v16 -= v29;
      }
      if ( i < 0x200 )
        goto LABEL_23;
      if ( (unsigned __int8)WinHvpCheckLargeSpaPage(a4, a5 + v16 * a6, a6) )
      {
        while ( v16 )
        {
          v11 = WinHvpMapGpaPagesHypercall(a1, a2, v16, v21, a5, a6, (__int64)v32, (__int64)&a7, (__int64)&v30);
          v22 = v30;
          v23 = v30;
          *a8 += v30;
          if ( v11 < 0 )
            goto LABEL_13;
          v21 = a4;
          a2 += v22;
          a5 += a6 * (unsigned int)v22;
          v16 -= v23;
        }
        WinHvpMapLargeGpaPages(a1, a2, i, v21, a5, a6, (__int64)v32, (__int64)&a7, (__int64)&v31);
        v25 = v31;
        a2 += v31;
        v26 = v31 * a6;
        *a8 += v31;
        a5 += v26;
        i -= v25;
      }
      v15 = a4;
      v24 = 512;
      if ( i <= 0x200 )
LABEL_23:
        v24 = (unsigned int)i;
      v16 += v24;
    }
    v13 = a8;
  }
  else
  {
    v16 = a3;
  }
  do
  {
    if ( !v16 )
      break;
    v18 = v16;
    if ( v16 >= 0x1FD )
      v18 = 509;
    v11 = WinHvpMapGpaPagesHypercall(a1, a2, v18, a4, a5, a6, (__int64)v32, (__int64)&a7, (__int64)&v30);
    v19 = v30;
    *v13 += v30;
    a2 += v19;
    v16 -= (unsigned int)v19;
    a5 += a6 * (unsigned int)v19;
  }
  while ( v11 >= 0 );
LABEL_13:
  if ( v32[0] )
    ((void (*)(void))v32[7])();
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140025a24  mov     rax, rsp
0x140025a27  mov     [rax+10h], rbx
0x140025a2b  mov     [rax+20h], r9d
0x140025a2f  mov     [rax+8], rcx
0x140025a33  push    rbp
0x140025a34  push    rsi
0x140025a35  push    rdi
0x140025a36  push    r12
0x140025a38  push    r13
0x140025a3a  push    r14
0x140025a3c  push    r15
0x140025a3e  lea     rbp, [rax-3Fh]
0x140025a42  sub     rsp, 0A0h
0x140025a49  mov     r14, rdx
0x140025a4c  lea     rcx, [rbp+37h+var_70]; void *
0x140025a50  xor     edx, edx; Val
0x140025a52  mov     rdi, r8
0x140025a55  lea     r8d, [rdx+40h]; Size
0x140025a59  call    memset
0x140025a5e  mov     r10b, byte ptr [rbp+37h+arg_30]
0x140025a62  xor     r12d, r12d
0x140025a65  movzx   eax, [rbp+37h+var_58]
0x140025a69  test    r10b, 2
0x140025a6d  mov     r13, [rbp+37h+arg_38]
0x140025a71  mov     ecx, 1
0x140025a76  mov     r15d, [rbp+37h+arg_28]
0x140025a7a  cmovnz  eax, ecx
0x140025a7d  mov     rsi, [rbp+37h+arg_20]
0x140025a81  mov     [rbp+37h+var_58], al
0x140025a84  mov     [rbp+37h+var_80], 0
0x140025a8b  mov     [rbp+37h+var_78], 0
0x140025a93  mov     [r13+0], r12
0x140025a97  mov     [rbp+37h+arg_30], r12d
0x140025a9b  test    cl, r10b
0x140025a9e  jz      loc_140025C10
0x140025aa4  mov     r13d, [rbp+37h+arg_18]
0x140025aa8  lea     rbx, [r14+1FFh]
0x140025aaf  and     rbx, 0FFFFFFFFFFFFFE00h
0x140025ab6  sub     rbx, r14
0x140025ab9  cmp     rbx, rdi
0x140025abc  cmovnb  rbx, rdi
0x140025ac0  sub     rdi, rbx
0x140025ac3  test    rdi, rdi
0x140025ac6  jnz     loc_140025B6B
0x140025acc  mov     r13, [rbp+37h+arg_38]
0x140025ad0  test    rbx, rbx
0x140025ad3  jz      short loc_140025B3A
0x140025ad5  mov     r8d, ebx
0x140025ad8  cmp     rbx, 1FDh
0x140025adf  jb      short loc_140025AE7
0x140025ae1  mov     r8d, 1FDh
0x140025ae7  mov     r9d, [rbp+37h+arg_18]
0x140025aeb  lea     rax, [rbp+37h+var_80]
0x140025aef  mov     rcx, [rbp+37h+arg_0]
0x140025af3  mov     rdx, r14
0x140025af6  mov     [rsp+40h], rax
0x140025afb  lea     rax, [rbp+37h+arg_30]
0x140025aff  mov     [rsp+0D0h+var_98], rax
0x140025b04  lea     rax, [rbp+37h+var_70]
0x140025b08  mov     [rsp+0D0h+var_A0], rax
0x140025b0d  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x140025b12  mov     qword ptr [rsp+0D0h+var_B0], rsi
0x140025b17  call    WinHvpMapGpaPagesHypercall
0x140025b1c  mov     r12d, eax
0x140025b1f  mov     eax, [rbp+37h+var_80]
0x140025b22  add     [r13+0], rax
0x140025b26  mov     ecx, eax
0x140025b28  add     r14, rax
0x140025b2b  sub     rbx, rcx
0x140025b2e  imul    eax, r15d
0x140025b32  add     rsi, rax
0x140025b35  test    r12d, r12d
0x140025b38  jns     short loc_140025AD0
0x140025b3a  mov     rcx, [rbp+37h+var_70]
0x140025b3e  test    rcx, rcx
0x140025b41  jz      short loc_140025B4C
0x140025b43  mov     rax, [rbp+37h+var_38]
0x140025b47  call    _guard_dispatch_icall
0x140025b4c  mov     rbx, [rsp+0D0h+arg_8]
0x140025b54  mov     eax, r12d
0x140025b57  add     rsp, 0A0h
0x140025b5e  pop     r15
0x140025b60  pop     r14
0x140025b62  pop     r13
0x140025b64  pop     r12
0x140025b66  pop     rdi
0x140025b67  pop     rsi
0x140025b68  pop     rbp
0x140025b69  retn
0x140025b6b  cmp     rbx, 1FDh
0x140025b72  jnb     loc_140025C7E
0x140025b78  cmp     rdi, 200h
0x140025b7f  jb      loc_140025C18
0x140025b85  mov     r11d, [rbp+37h+arg_18]
0x140025b89  mov     rdx, r15
0x140025b8c  imul    rdx, rbx
0x140025b90  mov     r8d, r15d
0x140025b93  mov     ecx, r11d
0x140025b96  add     rdx, rsi
0x140025b99  mov     r13, r15
0x140025b9c  call    WinHvpCheckLargeSpaPage
0x140025ba1  test    al, al
0x140025ba3  jz      loc_140025C61
0x140025ba9  mov     rcx, [rbp+37h+arg_0]
0x140025bad  mov     r9d, r11d
0x140025bb0  mov     rdx, r14
0x140025bb3  test    rbx, rbx
0x140025bb6  jz      short loc_140025C1C
0x140025bb8  lea     rax, [rbp+37h+var_80]
0x140025bbc  mov     r8d, ebx
0x140025bbf  mov     [rsp+40h], rax
0x140025bc4  lea     rax, [rbp+37h+arg_30]
0x140025bc8  mov     [rsp+0D0h+var_98], rax
0x140025bcd  lea     rax, [rbp+37h+var_70]
0x140025bd1  mov     [rsp+0D0h+var_A0], rax
0x140025bd6  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x140025bdb  mov     qword ptr [rsp+0D0h+var_B0], rsi
0x140025be0  call    WinHvpMapGpaPagesHypercall
0x140025be5  mov     rdx, [rbp+37h+arg_38]
0x140025be9  mov     r12d, eax
0x140025bec  mov     eax, [rbp+37h+var_80]
0x140025bef  mov     ecx, eax
0x140025bf1  add     [rdx], rax
0x140025bf4  test    r12d, r12d
0x140025bf7  js      loc_140025B3A
0x140025bfd  mov     r11d, [rbp+37h+arg_18]
0x140025c01  add     r14, rax
0x140025c04  imul    eax, r15d
0x140025c08  add     rsi, rax
0x140025c0b  sub     rbx, rcx
0x140025c0e  jmp     short loc_140025BA9
0x140025c10  mov     rbx, rdi
0x140025c13  jmp     loc_140025AD0
0x140025c18  mov     eax, edi
0x140025c1a  jmp     short loc_140025C73
0x140025c1c  lea     rax, [rbp+37h+var_78]
0x140025c20  mov     r8, rdi
0x140025c23  mov     [rsp+40h], rax
0x140025c28  lea     rax, [rbp+37h+arg_30]
0x140025c2c  mov     [rsp+0D0h+var_98], rax
0x140025c31  lea     rax, [rbp+37h+var_70]
0x140025c35  mov     [rsp+0D0h+var_A0], rax
0x140025c3a  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x140025c3f  mov     qword ptr [rsp+0D0h+var_B0], rsi
0x140025c44  call    WinHvpMapLargeGpaPages
0x140025c49  mov     rax, [rbp+37h+var_78]
0x140025c4d  mov     rdx, [rbp+37h+arg_38]
0x140025c51  add     r14, rax
0x140025c54  imul    r13, rax
0x140025c58  add     [rdx], rax
0x140025c5b  add     rsi, r13
0x140025c5e  sub     rdi, rax
0x140025c61  mov     r13d, [rbp+37h+arg_18]
0x140025c65  mov     eax, 200h
0x140025c6a  cmp     rdi, 200h
0x140025c71  jbe     short loc_140025C18
0x140025c73  add     rbx, rax
0x140025c76  sub     rdi, rax
0x140025c79  jmp     loc_140025AC3
0x140025c7e  mov     rcx, [rbp+37h+arg_0]
0x140025c82  lea     rax, [rbp+37h+var_80]
0x140025c86  mov     [rsp+40h], rax
0x140025c8b  mov     r9d, r13d
0x140025c8e  lea     rax, [rbp+37h+arg_30]
0x140025c92  mov     r8d, 1FDh
0x140025c98  mov     [rsp+0D0h+var_98], rax
0x140025c9d  mov     rdx, r14
0x140025ca0  lea     rax, [rbp+37h+var_70]
0x140025ca4  mov     [rsp+0D0h+var_A0], rax
0x140025ca9  mov     dword ptr [rsp+0D0h+var_A8], r15d
0x140025cae  mov     qword ptr [rsp+0D0h+var_B0], rsi
0x140025cb3  call    WinHvpMapGpaPagesHypercall
0x140025cb8  mov     ecx, [rbp+37h+var_80]
0x140025cbb  mov     r12d, eax
0x140025cbe  mov     r11, [rbp+37h+arg_38]
0x140025cc2  mov     edx, ecx
0x140025cc4  add     [r11], rcx
0x140025cc7  test    eax, eax
0x140025cc9  js      loc_140025B3A
0x140025ccf  add     r14, rcx
0x140025cd2  imul    ecx, r15d
0x140025cd6  add     rsi, rcx
0x140025cd9  sub     rbx, rdx
0x140025cdc  jmp     loc_140025B6B
```
