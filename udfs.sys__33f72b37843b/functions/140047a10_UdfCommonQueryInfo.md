# UdfCommonQueryInfo

- ea: `0x140047a10`
- end: `0x140047df0`
- name: `UdfCommonQueryInfo`
- size: `992`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x1400128f4`
- `0x140032404`
- `0x140032634`
- `0x14003269c`
- `0x140045f10`
- `0x140047a10`
- `0x140047df8`
- `0x140048100`
- `0x140048284`
- `0x140048334`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140047bcb`
- `ntoskrnl!ExRaiseStatus` at `0x140047bcb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140047ab5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140047ab5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047db9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a152`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047db9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a152`

## pseudocode

```c
__int64 __fastcall UdfCommonQueryInfo(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // esi
  __int64 v5; // r14
  char v6; // r12
  __int64 v7; // r15
  __int64 v8; // rbx
  int v9; // eax
  __int64 v10; // r15
  unsigned __int64 v11; // rbx
  BOOLEAN v12; // dl
  int v13; // r8d
  unsigned int AlternateNameInfo; // eax
  __int64 v15; // r10
  __int64 v16; // r10
  unsigned int v18; // [rsp+88h] [rbp+10h] BYREF
  int v19; // [rsp+90h] [rbp+18h]
  unsigned int *v20; // [rsp+98h] [rbp+20h]

  v4 = 0;
  v5 = a2[23];
  v18 = 0;
  v6 = 0;
  v18 = *(_DWORD *)(v5 + 8);
  v19 = *(_DWORD *)(v5 + 16);
  v20 = (unsigned int *)a2[3];
  v7 = *(_QWORD *)(v5 + 48);
  v8 = *(_QWORD *)(v7 + 32);
  v9 = v8 & 7;
  *(_QWORD *)(v7 + 32) = v8;
  if ( (v8 & 7) != 0 )
  {
    v10 = *(_QWORD *)(v7 + 24);
    v11 = v8 & 0xFFFFFFFFFFFFFFF8uLL;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  if ( (unsigned int)(v9 - 3) > 1 )
    goto LABEL_13;
  v12 = 0;
  if ( !a1 || (*(_DWORD *)(a1 + 28) & 4) != 0 )
    v12 = 1;
  if ( !ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v10 + 136) + 80LL) + 8LL), v12) )
  {
    *(_DWORD *)(a1 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  v6 = 1;
  UdfVerifyScbOperation(a1, v10, v11);
  if ( v19 == 9 )
  {
    if ( (*(_DWORD *)(v11 + 4) & 1) == 0 )
    {
      AlternateNameInfo = UdfQueryNameInfo(a1, *(_QWORD *)(v5 + 48), v10, v11, v20, &v18);
LABEL_11:
      v4 = AlternateNameInfo;
      goto LABEL_31;
    }
LABEL_13:
    v4 = -1073741811;
    goto LABEL_31;
  }
  if ( v19 != 5 )
  {
    switch ( v19 )
    {
      case 4:
        UdfFillBasicInfo(v20, v10, v11);
        v18 -= 40;
        goto LABEL_31;
      case 6:
        *(_QWORD *)v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 136) + 16LL) + 184LL);
        v18 -= 8;
        goto LABEL_31;
      case 7:
        *v20 = 0;
        v18 -= 4;
        goto LABEL_31;
      case 14:
        *(_QWORD *)v20 = *(_QWORD *)(*(_QWORD *)(v5 + 48) + 104LL);
        v18 -= 8;
        goto LABEL_31;
      case 18:
        if ( (*(_DWORD *)(v11 + 4) & 1) != 0 )
          goto LABEL_13;
        v18 -= 12;
        UdfFillBasicInfo(v20, v10, v11);
        v18 -= 40;
        UdfFillStandardInfo(v15 + 40);
        v18 -= 24;
        *(_QWORD *)(v16 + 64) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 136) + 16LL) + 184LL);
        v18 -= 8;
        *(_DWORD *)(v16 + 72) = 0;
        v18 -= 4;
        *(_QWORD *)(v16 + 80) = *(_QWORD *)(*(_QWORD *)(v5 + 48) + 104LL);
        v18 -= 8;
        v4 = UdfQueryNameInfo(a1, *(_QWORD *)(v5 + 48), v10, v11, (unsigned int *)(v16 + 96), &v18);
        goto LABEL_31;
      case 21:
        if ( (*(_DWORD *)(v11 + 4) & 1) != 0 )
          goto LABEL_13;
        AlternateNameInfo = UdfQueryAlternateNameInfo(a1, v10, v11, (_DWORD)v20, (__int64)&v18);
        goto LABEL_11;
      case 22:
        v4 = UdfQueryStreamsInfo(a1, v10, (__int64)v20, &v18);
        goto LABEL_31;
      case 28:
        AlternateNameInfo = UdfQueryCompressionInfo(a1, v10, v20, &v18);
        goto LABEL_11;
      case 34:
        UdfFillNetworkOpenInfo(v20, v10, v11);
        v18 -= 56;
        goto LABEL_31;
      case 46:
        if ( (*(_DWORD *)(v11 + 4) & 1) != 0 )
          goto LABEL_13;
        AlternateNameInfo = UdfQueryLinksInfo(a1, v10, v13, (_DWORD)v20, (__int64)&v18);
        goto LABEL_11;
      default:
        goto LABEL_13;
    }
  }
  UdfFillStandardInfo(v20);
  v18 -= 24;
LABEL_31:
  a2[7] = *(_DWORD *)(v5 + 8) - v18;
  if ( v6 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v10 + 136) + 80LL) + 8LL));
  UdfCompleteRequest(a1, a2, v4);
  return v4;
}

```

## disassembly

```asm
0x140047a10  mov     r11, rsp
0x140047a13  push    rbx
0x140047a14  push    rsi
0x140047a15  push    rdi
0x140047a16  push    r12
0x140047a18  push    r13
0x140047a1a  push    r14
0x140047a1c  push    r15
0x140047a1e  sub     rsp, 40h
0x140047a22  mov     rdi, rdx
0x140047a25  mov     r13, rcx
0x140047a28  xor     esi, esi
0x140047a2a  mov     r14, [rdx+0B8h]
0x140047a31  mov     [r11+10h], esi
0x140047a35  xor     r12b, r12b
0x140047a38  mov     [r11-48h], r12b
0x140047a3c  mov     eax, [r14+8]
0x140047a40  mov     [r11+10h], eax
0x140047a44  mov     eax, [r14+10h]
0x140047a48  mov     [rsp+78h+arg_10], eax
0x140047a4f  mov     rax, [rdx+18h]
0x140047a53  mov     [rsp+78h+arg_18], rax
0x140047a5b  mov     r15, [r14+30h]
0x140047a5f  mov     rbx, [r15+20h]
0x140047a63  mov     eax, ebx
0x140047a65  and     eax, 7
0x140047a68  mov     [r15+20h], rbx
0x140047a6c  jz      loc_140047DE6
0x140047a72  mov     r15, [r15+18h]
0x140047a76  and     rbx, 0FFFFFFFFFFFFFFF8h
0x140047a7a  mov     [rsp+78h+var_40], r15
0x140047a7f  sub     eax, 3
0x140047a82  jz      short loc_140047A8D
0x140047a84  cmp     eax, 1
0x140047a87  jnz     def_140047B78; jumptable 0000000140047B78 default case, cases 5,8-13,15-17,19,20,23-27,29-33,35-45
0x140047a8d  mov     rax, [r15+88h]
0x140047a94  mov     rcx, [rax+50h]
0x140047a98  add     rcx, 8; Resource
0x140047a9c  xor     dl, dl
0x140047a9e  mov     [rsp+78h+var_47], dl
0x140047aa2  test    r13, r13
0x140047aa5  jz      short loc_140047AAF
0x140047aa7  mov     eax, [r13+1Ch]
0x140047aab  test    al, 4
0x140047aad  jz      short loc_140047AB5
0x140047aaf  mov     dl, 1; Wait
0x140047ab1  mov     [rsp+78h+var_47], dl
0x140047ab5  call    cs:__imp_ExAcquireResourceSharedLite
0x140047abc  nop     dword ptr [rax+rax+00h]
0x140047ac1  test    al, al
0x140047ac3  jz      loc_140047BBE
0x140047ac9  mov     r12b, 1
0x140047acc  mov     [rsp+78h+var_48], r12b
0x140047ad1  mov     r8, rbx
0x140047ad4  mov     rdx, r15
0x140047ad7  mov     rcx, r13
0x140047ada  call    UdfVerifyScbOperation
0x140047adf  mov     eax, [rsp+78h+arg_10]
0x140047ae6  cmp     eax, 9
0x140047ae9  jnz     short loc_140047B38
0x140047aeb  mov     eax, [rbx+4]
0x140047aee  test    r12b, al
0x140047af1  jnz     short def_140047B78; jumptable 0000000140047B78 default case, cases 5,8-13,15-17,19,20,23-27,29-33,35-45
0x140047af3  lea     rax, [rsp+78h+arg_8]
0x140047afb  mov     [rsp+78h+var_50], rax
0x140047b00  mov     r10, [rsp+78h+arg_18]
0x140047b08  mov     [rsp+78h+var_58], r10
0x140047b0d  mov     r9, rbx
0x140047b10  mov     r8, r15
0x140047b13  mov     rdx, [r14+30h]
0x140047b17  mov     rcx, r13
0x140047b1a  call    UdfQueryNameInfo
0x140047b1f  mov     esi, eax
0x140047b21  jmp     loc_140047D96
0x140047b26  add     eax, 0FFFFFFFCh; switch 43 cases
0x140047b29  cmp     eax, 2Ah
0x140047b2c  jbe     short loc_140047B5D
0x140047b2e  mov     esi, 0C000000Dh; jumptable 0000000140047B78 default case, cases 5,8-13,15-17,19,20,23-27,29-33,35-45
0x140047b33  jmp     loc_140047D96
0x140047b38  cmp     eax, 5
0x140047b3b  jnz     short loc_140047B26
0x140047b3d  mov     r8, rbx
0x140047b40  mov     rdx, r15
0x140047b43  mov     rcx, [rsp+78h+arg_18]
0x140047b4b  call    UdfFillStandardInfo
0x140047b50  add     [rsp+78h+arg_8], 0FFFFFFE8h
0x140047b58  jmp     loc_140047D96
0x140047b5d  cdqe
0x140047b5f  lea     rdx, cs:140000000h
0x140047b66  movzx   eax, ds:(byte_140020D2C - 140000000h)[rdx+rax]
0x140047b6e  mov     ecx, ds:(jpt_140047B78 - 140000000h)[rdx+rax*4]
0x140047b75  add     rcx, rdx
0x140047b78  jmp     rcx; switch jump
0x140047b7e  mov     r8, rbx; jumptable 0000000140047B78 case 34
0x140047b81  mov     rdx, r15
0x140047b84  mov     rcx, [rsp+78h+arg_18]
0x140047b8c  call    UdfFillNetworkOpenInfo
0x140047b91  add     [rsp+78h+arg_8], 0FFFFFFC8h
0x140047b99  jmp     loc_140047D96
0x140047b9e  mov     r8, rbx; jumptable 0000000140047B78 case 4
0x140047ba1  mov     rdx, r15
0x140047ba4  mov     rcx, [rsp+78h+arg_18]
0x140047bac  call    UdfFillBasicInfo
0x140047bb1  add     [rsp+78h+arg_8], 0FFFFFFD8h
0x140047bb9  jmp     loc_140047D96
0x140047bbe  mov     dword ptr [r13+18h], 0C00000D8h
0x140047bc6  mov     ecx, 0C00000D8h; Status
0x140047bcb  call    cs:__imp_ExRaiseStatus
0x140047bd8  mov     eax, [rbx+4]; jumptable 0000000140047B78 case 18
0x140047bdb  test    r12b, al
0x140047bde  jnz     def_140047B78; jumptable 0000000140047B78 default case, cases 5,8-13,15-17,19,20,23-27,29-33,35-45
0x140047be4  add     [rsp+78h+arg_8], 0FFFFFFF4h
0x140047bec  mov     r8, rbx
0x140047bef  mov     rdx, r15
0x140047bf2  mov     r10, [rsp+78h+arg_18]
0x140047bfa  mov     rcx, r10
0x140047bfd  call    UdfFillBasicInfo
0x140047c02  add     [rsp+78h+arg_8], 0FFFFFFD8h
0x140047c0a  lea     rcx, [r10+28h]
0x140047c0e  call    UdfFillStandardInfo
0x140047c13  add     [rsp+78h+arg_8], 0FFFFFFE8h
0x140047c1b  mov     rax, [r15+88h]
0x140047c22  mov     rcx, [rax+10h]
0x140047c26  mov     rax, [rcx+0B8h]
0x140047c2d  mov     [r10+40h], rax
0x140047c31  add     [rsp+78h+arg_8], 0FFFFFFF8h
0x140047c39  mov     dword ptr [r10+48h], 0
0x140047c41  add     [rsp+78h+arg_8], 0FFFFFFFCh
0x140047c49  mov     rax, [r14+30h]
0x140047c4d  mov     rcx, [rax+68h]
0x140047c51  mov     [r10+50h], rcx
0x140047c55  add     [rsp+78h+arg_8], 0FFFFFFF8h
0x140047c5d  lea     rax, [r10+60h]
0x140047c61  lea     rcx, [rsp+78h+arg_8]
0x140047c69  mov     [rsp+78h+var_50], rcx
0x140047c6e  mov     [rsp+78h+var_58], rax
0x140047c73  mov     r9, rbx
0x140047c76  mov     r8, r15
0x140047c79  mov     rdx, [r14+30h]
0x140047c7d  mov     rcx, r13
0x140047c80  call    UdfQueryNameInfo
0x140047c85  mov     esi, eax
0x140047c87  jmp     loc_140047D96
0x140047c8c  mov     rax, [r15+88h]; jumptable 0000000140047B78 case 6
0x140047c93  mov     rcx, [rax+10h]
0x140047c97  mov     rax, [rcx+0B8h]
0x140047c9e  mov     r10, [rsp+78h+arg_18]
0x140047ca6  mov     [r10], rax
0x140047ca9  add     [rsp+78h+arg_8], 0FFFFFFF8h
0x140047cb1  jmp     loc_140047D96
0x140047cb6  mov     r10, [rsp+78h+arg_18]; jumptable 0000000140047B78 case 7
0x140047cbe  mov     dword ptr [r10], 0
0x140047cc5  add     [rsp+78h+arg_8], 0FFFFFFFCh
0x140047ccd  jmp     loc_140047D96
0x140047cd2  mov     rax, [r14+30h]; jumptable 0000000140047B78 case 14
0x140047cd6  mov     rcx, [rax+68h]
0x140047cda  mov     r10, [rsp+78h+arg_18]
0x140047ce2  mov     [r10], rcx
0x140047ce5  add     [rsp+78h+arg_8], 0FFFFFFF8h
0x140047ced  jmp     loc_140047D96
0x140047cf2  mov     eax, [rbx+4]; jumptable 0000000140047B78 case 21
0x140047cf5  test    r12b, al
0x140047cf8  jnz     def_140047B78; jumptable 0000000140047B78 default case, cases 5,8-13,15-17,19,20,23-27,29-33,35-45
0x140047cfe  lea     rax, [rsp+78h+arg_8]
0x140047d06  mov     [rsp+78h+var_58], rax
0x140047d0b  mov     r9, [rsp+78h+arg_18]
0x140047d13  mov     r8, rbx
0x140047d16  mov     rdx, r15
0x140047d19  mov     rcx, r13
0x140047d1c  call    UdfQueryAlternateNameInfo
0x140047d21  jmp     loc_140047B1F
0x140047d26  lea     r9, [rsp+78h+arg_8]; jumptable 0000000140047B78 case 22
0x140047d2e  mov     r8, [rsp+78h+arg_18]
0x140047d36  mov     rdx, r15
0x140047d39  mov     rcx, r13
0x140047d3c  call    UdfQueryStreamsInfo
0x140047d41  mov     esi, eax
0x140047d43  jmp     short loc_140047D96
0x140047d45  mov     eax, [rbx+4]; jumptable 0000000140047B78 case 46
0x140047d48  test    r12b, al
0x140047d4b  jnz     def_140047B78; jumptable 0000000140047B78 default case, cases 5,8-13,15-17,19,20,23-27,29-33,35-45
0x140047d51  lea     rax, [rsp+78h+arg_8]
0x140047d59  mov     [rsp+78h+var_58], rax
0x140047d5e  mov     r9, [rsp+78h+arg_18]
0x140047d66  mov     rdx, r15
0x140047d69  mov     rcx, r13
0x140047d6c  call    UdfQueryLinksInfo
0x140047d71  jmp     loc_140047B1F
0x140047d76  lea     r9, [rsp+78h+arg_8]; jumptable 0000000140047B78 case 28
0x140047d7e  mov     r8, [rsp+78h+arg_18]
0x140047d86  mov     rdx, r15
0x140047d89  mov     rcx, r13
0x140047d8c  call    UdfQueryCompressionInfo
0x140047d91  jmp     loc_140047B1F
0x140047d96  mov     eax, [r14+8]
0x140047d9a  sub     eax, [rsp+78h+arg_8]
0x140047da1  mov     [rdi+38h], rax
0x140047da5  test    r12b, r12b
0x140047da8  jz      short loc_140047DC5
0x140047daa  mov     rax, [r15+88h]
0x140047db1  mov     rcx, [rax+50h]
0x140047db5  add     rcx, 8; Resource
0x140047db9  call    cs:__imp_ExReleaseResourceLite
0x140047dc0  nop     dword ptr [rax+rax+00h]
0x140047dc5  mov     r8d, esi
0x140047dc8  mov     rdx, rdi
0x140047dcb  mov     rcx, r13
0x140047dce  call    UdfCompleteRequest
0x140047dd3  mov     eax, esi
0x140047dd5  add     rsp, 40h
0x140047dd9  pop     r15
0x140047ddb  pop     r14
0x140047ddd  pop     r13
0x140047ddf  pop     r12
0x140047de1  pop     rdi
0x140047de2  pop     rsi
0x140047de3  pop     rbx
0x140047de4  retn
0x140047de6  xor     r15d, r15d
0x140047de9  xor     ebx, ebx
0x140047deb  jmp     loc_140047A7A
0x14005a130  push    rbp
0x14005a132  sub     rsp, 30h
0x14005a136  mov     rbp, rdx
0x14005a139  cmp     byte ptr [rbp+30h], 0
0x14005a13d  jz      short loc_14005A15F
0x14005a13f  mov     rax, [rbp+38h]
0x14005a143  mov     rcx, [rax+88h]
0x14005a14a  mov     rcx, [rcx+50h]
0x14005a14e  add     rcx, 8; Resource
0x14005a152  call    cs:__imp_ExReleaseResourceLite
0x14005a159  nop     dword ptr [rax+rax+00h]
0x14005a15e  nop
0x14005a15f  add     rsp, 30h
0x14005a163  pop     rbp
0x14005a164  retn
```
