# VsmmMemXferpFillBatchedWrite

- ea: `0x140017c20`
- end: `0x140018384`
- name: `VsmmMemXferpFillBatchedWrite`
- size: `1892`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400269dc`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x1400116c8`
- `0x140017acc`
- `0x140017c20`
- `0x140021650`
- `0x1400fb920`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017c96`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017ffd`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017c96`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140017ffd`
- `ntoskrnl!ExAllocatePool2` at `0x140017e68`
- `ntoskrnl!ExAllocatePool2` at `0x140017e68`

## string_xrefs

- `0x140017d2e`: `VsmmMemXferpFillBatchedWrite`
- `0x140017eb1`: `VsmmMemXferpFillBatchedWrite`
- `0x1400180a6`: `VsmmMemXferpFillBatchedWrite`
- `0x140018166`: `VsmmMemXferpFillBatchedWrite`
- `0x14001823b`: `VsmmMemXferpFillBatchedWrite`

## pseudocode

```c
__int64 __fastcall VsmmMemXferpFillBatchedWrite(_QWORD *a1, __int64 a2, unsigned __int64 a3)
{
  unsigned int v6; // edi
  unsigned __int64 i; // rsi
  unsigned __int64 v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  __int64 Pool2; // rax
  int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rax
  char *v15; // rdx
  __int64 v16; // r8
  unsigned __int64 j; // rsi
  unsigned __int64 v18; // rdi
  __int64 v19; // r14
  int v21; // [rsp+30h] [rbp-208h] BYREF
  int v22; // [rsp+34h] [rbp-204h] BYREF
  __int64 v23; // [rsp+38h] [rbp-200h] BYREF
  __int64 v24; // [rsp+40h] [rbp-1F8h]
  char v25[24]; // [rsp+50h] [rbp-1E8h] BYREF
  _BYTE v26[16]; // [rsp+70h] [rbp-1C8h] BYREF
  _BYTE v27[16]; // [rsp+80h] [rbp-1B8h] BYREF
  int *v28; // [rsp+90h] [rbp-1A8h]
  __int64 v29; // [rsp+98h] [rbp-1A0h]
  int *v30; // [rsp+A0h] [rbp-198h]
  __int64 v31; // [rsp+A8h] [rbp-190h]
  __int64 v32; // [rsp+B0h] [rbp-188h]
  __int64 v33; // [rsp+B8h] [rbp-180h]
  int *v34; // [rsp+C0h] [rbp-178h]
  __int64 v35; // [rsp+C8h] [rbp-170h]
  __int64 v36; // [rsp+D0h] [rbp-168h]
  int v37; // [rsp+D8h] [rbp-160h] BYREF
  int v38; // [rsp+DCh] [rbp-15Ch]
  __int64 *v39; // [rsp+E0h] [rbp-158h]
  __int64 v40; // [rsp+E8h] [rbp-150h]
  _QWORD v41[32]; // [rsp+F0h] [rbp-148h] BYREF

  v24 = *(_QWORD *)(a1[2] + 8LL);
  v23 = v24;
  v6 = 0;
  for ( i = 0; i < a3; i += v8 )
  {
    v8 = 16;
    if ( a3 - i < 0x10 )
      v8 = a3 - i;
    if ( 16 * v8 )
    {
      if ( (a2 & 7) != 0 )
        ExRaiseDatatypeMisalignment();
    }
    RtlCopyFromUser(v41, (void *)(a2 + 16 * i), 16 * v8);
    v9 = 0;
    if ( v8 )
    {
      while ( v41[2 * v9 + 1] < 0xFFFFFu )
      {
        v10 = 8 * LODWORD(v41[2 * v9 + 1]) + 48;
        if ( v10 + v6 < v6 )
        {
          v6 = 8 * LODWORD(v41[2 * v9 + 1]) + 48;
          break;
        }
        v6 += v10;
        if ( ++v9 >= v8 )
          break;
      }
    }
  }
  if ( v6 )
  {
    Pool2 = ExAllocatePool2(64, v6, 1833788502);
    a1[9] = Pool2;
    if ( !Pool2 )
    {
      v12 = -1073741670;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v26, "VsmmMemXferpFillBatchedWrite");
        tlgCreate1Sz_char(v27, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v22 = 2808;
        v28 = &v22;
        v30 = &v21;
        v32 = v24 + 656;
        v34 = &v37;
        v36 = *(_QWORD *)(v24 + 128);
        v37 = *(unsigned __int16 *)(v24 + 120);
        v14 = *(_QWORD *)(v24 + 648);
        v15 = byte_14004CB2B;
LABEL_20:
        v16 = 0;
        v38 = v13;
LABEL_21:
        v23 = v14;
        v39 = &v23;
        v29 = 4;
        v21 = v12;
        v31 = 4;
        v33 = 16;
        v35 = 2;
        v40 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v15, v16, v13, 10, v25);
      }
      return (unsigned int)v12;
    }
    a1[11] = 0;
    a1[10] = v6;
  }
  for ( j = 0; ; j += v18 )
  {
    if ( j >= a3 )
      return 0;
    v18 = 16;
    if ( a3 - j < 0x10 )
      v18 = a3 - j;
    if ( 16 * v18 && (a2 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(v41, (void *)(a2 + 16 * j), 16 * v18);
    v19 = 0;
    if ( v18 )
      break;
LABEL_33:
    v12 = VsmmMemXferpBatchedWriteAddRanges((__int64)a1, (int)v41, v18);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v26, "VsmmMemXferpFillBatchedWrite");
        tlgCreate1Sz_char(v27, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
        v22 = 2869;
        v28 = &v22;
        v30 = &v21;
        v32 = v24 + 656;
        v34 = &v37;
        v36 = *(_QWORD *)(v24 + 128);
        v37 = *(unsigned __int16 *)(v24 + 120);
        v14 = *(_QWORD *)(v24 + 648);
        v15 = &byte_14004CA4F;
        goto LABEL_20;
      }
      return (unsigned int)v12;
    }
  }
  while ( 1 )
  {
    v12 = VsmmGpaRangeValidatePageRange(v24, v41[2 * v19], v41[2 * v19 + 1]);
    if ( v12 < 0 )
      break;
    if ( ++v19 >= v18 )
      goto LABEL_33;
  }
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v26, "VsmmMemXferpFillBatchedWrite");
    tlgCreate1Sz_char(v27, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfer.c");
    v22 = 2854;
    v28 = &v22;
    v30 = &v21;
    v32 = v24 + 656;
    v34 = &v37;
    v36 = *(_QWORD *)(v24 + 128);
    v37 = *(unsigned __int16 *)(v24 + 120);
    v38 = v16;
    v14 = *(_QWORD *)(v24 + 648);
    v13 = 0;
    v15 = byte_14004C973;
    goto LABEL_21;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140017c20  push    rbx
0x140017c22  push    rsi
0x140017c23  push    rdi
0x140017c24  push    r12
0x140017c26  push    r13
0x140017c28  push    r14
0x140017c2a  push    r15
0x140017c2c  sub     rsp, 200h
0x140017c33  mov     rax, cs:__security_cookie
0x140017c3a  xor     rax, rsp
0x140017c3d  mov     [rsp+238h+var_48], rax
0x140017c45  mov     r12, r8
0x140017c48  mov     r13, rdx
0x140017c4b  mov     r15, rcx
0x140017c4e  mov     rax, [rcx+10h]
0x140017c52  mov     rax, [rax+8]
0x140017c56  mov     [rsp+238h+var_1F8], rax
0x140017c5b  mov     [rsp+238h+var_200], rax
0x140017c60  xor     r9d, r9d
0x140017c63  mov     edi, r9d
0x140017c66  mov     esi, r9d
0x140017c69  cmp     rsi, r12
0x140017c6c  jnb     loc_140017E51
0x140017c72  mov     rax, r12
0x140017c75  sub     rax, rsi
0x140017c78  mov     ebx, 10h
0x140017c7d  cmp     rax, rbx
0x140017c80  cmovb   rbx, rax
0x140017c84  mov     r8, rbx
0x140017c87  shl     r8, 4
0x140017c8b  test    r8, r8
0x140017c8e  jz      short loc_140017CA2
0x140017c90  test    r13b, 7
0x140017c94  jz      short loc_140017CA2
0x140017c96  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140017c9d  nop     dword ptr [rax+rax+00h]
0x140017ca2  mov     rdx, rsi
0x140017ca5  shl     rdx, 4
0x140017ca9  add     rdx, r13; Src
0x140017cac  lea     rcx, [rsp+238h+var_148]; void *
0x140017cb4  call    RtlCopyFromUser
0x140017cb9  nop
0x140017cba  xor     r9d, r9d
0x140017cbd  mov     ecx, r9d
0x140017cc0  test    rbx, rbx
0x140017cc3  jz      short loc_140017CFC
0x140017cc5  mov     rax, rcx
0x140017cc8  add     rax, rax
0x140017ccb  cmp     [rsp+rax*8+238h+var_140], 0FFFFFh
0x140017cd7  jnb     short loc_140017CFC
0x140017cd9  mov     eax, dword ptr [rsp+rax*8+238h+var_140]
0x140017ce0  lea     eax, ds:30h[rax*8]
0x140017ce7  lea     edx, [rax+rdi]
0x140017cea  cmp     edx, edi
0x140017cec  jb      short loc_140017CFA
0x140017cee  mov     edi, edx
0x140017cf0  inc     rcx
0x140017cf3  cmp     rcx, rbx
0x140017cf6  jb      short loc_140017CC5
0x140017cf8  jmp     short loc_140017CFC
0x140017cfa  mov     edi, eax
0x140017cfc  add     rsi, rbx
0x140017cff  jmp     loc_140017C69
0x140017d04  mov     ebx, eax
0x140017d06  mov     eax, cs:dword_140064110
0x140017d0c  cmp     eax, 2
0x140017d0f  jbe     loc_140017E4C
0x140017d15  mov     edx, 100h
0x140017d1a  lea     rcx, dword_140064110
0x140017d21  call    _tlgKeywordOn
0x140017d26  test    al, al
0x140017d28  jz      loc_140017E4C
0x140017d2e  lea     rdx, aVsmmmemxferpfi; "VsmmMemXferpFillBatchedWrite"
0x140017d35  lea     rcx, [rsp+238h+var_1C8]
0x140017d3a  call    _tlgCreate1Sz_char
0x140017d3f  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140017d46  lea     rcx, [rsp+238h+var_1B8]
0x140017d4e  call    _tlgCreate1Sz_char
0x140017d53  mov     [rsp+238h+var_208], 0AD2h
0x140017d5b  lea     rax, [rsp+238h+var_208]
0x140017d60  mov     [rsp+238h+var_1A8], rax
0x140017d68  mov     [rsp+238h+var_1A0], 4
0x140017d74  mov     [rsp+238h+var_204], ebx
0x140017d78  lea     rax, [rsp+238h+var_204]
0x140017d7d  mov     [rsp+238h+var_198], rax
0x140017d85  mov     [rsp+238h+var_190], 4
0x140017d91  mov     rcx, [rsp+238h+var_200]
0x140017d96  lea     rax, [rcx+290h]
0x140017d9d  mov     [rsp+238h+var_188], rax
0x140017da5  mov     [rsp+238h+var_180], 10h
0x140017db1  mov     edx, 7
0x140017db6  mov     eax, edx
0x140017db8  shl     rax, 4
0x140017dbc  lea     r8, [rsp+238h+var_1D0]
0x140017dc1  add     rax, r8
0x140017dc4  mov     [rsp+238h+var_178], rax
0x140017dcc  mov     [rsp+238h+var_170], 2
0x140017dd8  mov     rax, [rcx+80h]
0x140017ddf  mov     [rsp+238h+var_168], rax
0x140017de7  movzx   eax, word ptr [rcx+78h]
0x140017deb  mov     [rsp+238h+var_160], eax
0x140017df2  mov     [rsp+238h+var_15C], 0
0x140017dfd  mov     rax, [rcx+288h]
0x140017e04  mov     [rsp+238h+var_200], rax
0x140017e09  lea     rax, [rsp+238h+var_200]
0x140017e0e  mov     [rsp+238h+var_158], rax
0x140017e16  mov     [rsp+238h+var_150], 8
0x140017e22  lea     eax, [rdx+3]
0x140017e25  lea     rcx, [rsp+238h+var_1E8]
0x140017e2a  mov     [rsp+238h+var_210], rcx
0x140017e2f  mov     [rsp+238h+var_218], eax
0x140017e33  xor     r9d, r9d
0x140017e36  xor     r8d, r8d
0x140017e39  lea     rdx, byte_14004CB99
0x140017e40  lea     rcx, dword_140064110
0x140017e47  call    _tlgWriteTransfer_EtwWriteTransfer
0x140017e4c  jmp     loc_14001835E
0x140017e51  test    edi, edi
0x140017e53  jz      loc_140017FCD
0x140017e59  mov     ebx, edi
0x140017e5b  mov     r8d, 6D4D6456h
0x140017e61  mov     edx, edi
0x140017e63  mov     ecx, 40h ; '@'
0x140017e68  call    cs:__imp_ExAllocatePool2
0x140017e6f  nop     dword ptr [rax+rax+00h]
0x140017e74  mov     [r15+48h], rax
0x140017e78  xor     r9d, r9d
0x140017e7b  test    rax, rax
0x140017e7e  jnz     loc_140017FC5
0x140017e84  mov     ebx, 0C000009Ah
0x140017e89  mov     eax, cs:dword_140064110
0x140017e8f  cmp     eax, 2
0x140017e92  jbe     loc_14001835E
0x140017e98  mov     edx, 100h
0x140017e9d  lea     rcx, dword_140064110
0x140017ea4  call    _tlgKeywordOn
0x140017ea9  test    al, al
0x140017eab  jz      loc_14001835E
0x140017eb1  lea     rdx, aVsmmmemxferpfi; "VsmmMemXferpFillBatchedWrite"
0x140017eb8  lea     rcx, [rsp+238h+var_1C8]
0x140017ebd  call    _tlgCreate1Sz_char
0x140017ec2  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x140017ec9  lea     rcx, [rsp+238h+var_1B8]
0x140017ed1  call    _tlgCreate1Sz_char
0x140017ed6  mov     [rsp+238h+var_204], 0AF8h
0x140017ede  lea     rax, [rsp+238h+var_204]
0x140017ee3  mov     [rsp+238h+var_1A8], rax
0x140017eeb  lea     rcx, [rsp+238h+var_208]
0x140017ef0  mov     [rsp+238h+var_198], rcx
0x140017ef8  mov     r14, [rsp+238h+var_1F8]
0x140017efd  lea     rax, [r14+290h]
0x140017f04  mov     [rsp+238h+var_188], rax
0x140017f0c  lea     rax, [rsp+238h+var_160]
0x140017f14  mov     [rsp+238h+var_178], rax
0x140017f1c  mov     rax, [r14+80h]
0x140017f23  mov     [rsp+238h+var_168], rax
0x140017f2b  movzx   eax, word ptr [r14+78h]
0x140017f30  mov     [rsp+238h+var_160], eax
0x140017f37  mov     rax, [r14+288h]
0x140017f3e  lea     rdx, byte_14004CB2B
0x140017f45  xor     r8d, r8d
0x140017f48  mov     [rsp+238h+var_15C], r9d
0x140017f50  mov     [rsp+238h+var_200], rax
0x140017f55  lea     rax, [rsp+238h+var_200]
0x140017f5a  mov     [rsp+238h+var_158], rax
0x140017f62  lea     rax, [rsp+238h+var_1E8]
0x140017f67  mov     [rsp+238h+var_210], rax
0x140017f6c  mov     [rsp+238h+var_1A0], 4
0x140017f78  mov     [rsp+238h+var_208], ebx
0x140017f7c  mov     [rsp+238h+var_190], 4
0x140017f88  mov     [rsp+238h+var_180], 10h
0x140017f94  mov     [rsp+238h+var_170], 2
0x140017fa0  mov     [rsp+238h+var_150], 8
0x140017fac  mov     [rsp+238h+var_218], 0Ah
0x140017fb4  lea     rcx, dword_140064110
0x140017fbb  call    _tlgWriteTransfer_EtwWriteTransfer
0x140017fc0  jmp     loc_14001835E
0x140017fc5  mov     [r15+58h], r9
0x140017fc9  mov     [r15+50h], rbx
0x140017fcd  mov     rsi, r9
0x140017fd0  cmp     rsi, r12
0x140017fd3  jnb     loc_14001835B
0x140017fd9  mov     rax, r12
0x140017fdc  sub     rax, rsi
0x140017fdf  mov     edi, 10h
0x140017fe4  cmp     rax, rdi
0x140017fe7  cmovb   rdi, rax
0x140017feb  mov     r8, rdi
0x140017fee  shl     r8, 4
0x140017ff2  test    r8, r8
0x140017ff5  jz      short loc_140018009
0x140017ff7  test    r13b, 7
0x140017ffb  jz      short loc_140018009
0x140017ffd  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140018004  nop     dword ptr [rax+rax+00h]
0x140018009  mov     rdx, rsi
0x14001800c  shl     rdx, 4
0x140018010  add     rdx, r13; Src
0x140018013  lea     rcx, [rsp+238h+var_148]; void *
0x14001801b  call    RtlCopyFromUser
0x140018020  nop
0x140018021  xor     r14d, r14d
0x140018024  test    rdi, rdi
0x140018027  jz      short loc_14001805E
0x140018029  mov     rdx, r14
0x14001802c  add     rdx, rdx
0x14001802f  mov     r8, [rsp+rdx*8+238h+var_140]
0x140018037  mov     rdx, [rsp+rdx*8+238h+var_148]
0x14001803f  mov     rcx, [rsp+238h+var_1F8]
0x140018044  call    VsmmGpaRangeValidatePageRange
0x140018049  mov     ebx, eax
0x14001804b  xor     r8d, r8d
0x14001804e  test    eax, eax
0x140018050  js      loc_14001813E
0x140018056  inc     r14
0x140018059  cmp     r14, rdi
0x14001805c  jb      short loc_140018029
0x14001805e  mov     r8, rdi
0x140018061  lea     rdx, [rsp+238h+var_148]
0x140018069  mov     rcx, r15
0x14001806c  call    VsmmMemXferpBatchedWriteAddRanges
0x140018071  mov     ebx, eax
0x140018073  xor     r9d, r9d
0x140018076  test    eax, eax
0x140018078  jns     loc_140018209
0x14001807e  mov     eax, cs:dword_140064110
0x140018084  cmp     eax, 2
0x140018087  jbe     loc_14001835E
0x14001808d  mov     edx, 100h
0x140018092  lea     rcx, dword_140064110
0x140018099  call    _tlgKeywordOn
0x14001809e  test    al, al
0x1400180a0  jz      loc_14001835E
0x1400180a6  lea     rdx, aVsmmmemxferpfi; "VsmmMemXferpFillBatchedWrite"
0x1400180ad  lea     rcx, [rsp+238h+var_1C8]
0x1400180b2  call    _tlgCreate1Sz_char
0x1400180b7  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x1400180be  lea     rcx, [rsp+238h+var_1B8]
0x1400180c6  call    _tlgCreate1Sz_char
0x1400180cb  mov     [rsp+238h+var_204], 0B35h
0x1400180d3  lea     rax, [rsp+238h+var_204]
0x1400180d8  mov     [rsp+238h+var_1A8], rax
0x1400180e0  lea     rcx, [rsp+238h+var_208]
0x1400180e5  mov     [rsp+238h+var_198], rcx
0x1400180ed  mov     rcx, [rsp+238h+var_1F8]
0x1400180f2  lea     rax, [rcx+290h]
0x1400180f9  mov     [rsp+238h+var_188], rax
0x140018101  lea     rax, [rsp+238h+var_160]
0x140018109  mov     [rsp+238h+var_178], rax
0x140018111  mov     rax, [rcx+80h]
0x140018118  mov     [rsp+238h+var_168], rax
0x140018120  movzx   eax, word ptr [rcx+78h]
0x140018124  mov     [rsp+238h+var_160], eax
0x14001812b  mov     rax, [rcx+288h]
0x140018132  lea     rdx, byte_14004CA4F
0x140018139  jmp     loc_140017F45
0x14001813e  mov     eax, cs:dword_140064110
0x140018144  cmp     eax, 2
0x140018147  jbe     loc_14001835E
0x14001814d  mov     edx, 100h
0x140018152  lea     rcx, dword_140064110
0x140018159  call    _tlgKeywordOn
0x14001815e  test    al, al
0x140018160  jz      loc_14001835E
0x140018166  lea     rdx, aVsmmmemxferpfi; "VsmmMemXferpFillBatchedWrite"
0x14001816d  lea     rcx, [rsp+238h+var_1C8]
0x140018172  call    _tlgCreate1Sz_char
0x140018177  lea     rdx, aOnecoreVmVidSy_56; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemxfe"...
0x14001817e  lea     rcx, [rsp+238h+var_1B8]
0x140018186  call    _tlgCreate1Sz_char
0x14001818b  mov     [rsp+238h+var_204], 0B26h
0x140018193  lea     rax, [rsp+238h+var_204]
0x140018198  mov     [rsp+238h+var_1A8], rax
0x1400181a0  lea     rcx, [rsp+238h+var_208]
0x1400181a5  mov     [rsp+238h+var_198], rcx
0x1400181ad  mov     rcx, [rsp+238h+var_1F8]
0x1400181b2  lea     rax, [rcx+290h]
0x1400181b9  mov     [rsp+238h+var_188], rax
0x1400181c1  lea     rax, [rsp+238h+var_160]
0x1400181c9  mov     [rsp+238h+var_178], rax
0x1400181d1  mov     rax, [rcx+80h]
0x1400181d8  mov     [rsp+238h+var_168], rax
0x1400181e0  movzx   eax, word ptr [rcx+78h]
0x1400181e4  mov     [rsp+238h+var_160], eax
0x1400181eb  mov     [rsp+238h+var_15C], r8d
0x1400181f3  mov     rax, [rcx+288h]
0x1400181fa  xor     r9d, r9d
0x1400181fd  lea     rdx, byte_14004C973
0x140018204  jmp     loc_140017F50
0x140018209  add     rsi, rdi
0x14001820c  jmp     loc_140017FD0
0x140018211  mov     ebx, eax
0x140018213  mov     eax, cs:dword_140064110
0x140018219  cmp     eax, 2
0x14001821c  jbe     loc_140018359
0x140018222  mov     edx, 100h
0x140018227  lea     rcx, dword_140064110
0x14001822e  call    _tlgKeywordOn
0x140018233  test    al, al
0x140018235  jz      loc_140018359
  ... truncated ...
```
