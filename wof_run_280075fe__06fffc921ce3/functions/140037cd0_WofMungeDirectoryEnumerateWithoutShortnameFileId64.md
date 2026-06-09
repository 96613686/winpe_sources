# WofMungeDirectoryEnumerateWithoutShortnameFileId64

- ea: `0x140037cd0`
- end: `0x14003825a`
- name: `WofMungeDirectoryEnumerateWithoutShortnameFileId64`
- size: `1418`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140036e20`

## callees

- `0x140011590`
- `0x1400115b0`
- `0x140022fcc`
- `0x1400230a8`
- `0x140023150`
- `0x140023198`
- `0x140035e80`
- `0x140037cd0`

## pseudocode

```c
__int64 __fastcall WofMungeDirectoryEnumerateWithoutShortnameFileId64(
        int a1,
        _DWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        unsigned int *a7)
{
  _DWORD *v7; // rdi
  unsigned __int64 v8; // r15
  unsigned int v9; // ebx
  unsigned int v10; // r13d
  _DWORD *v11; // rsi
  unsigned int v12; // edx
  unsigned int v13; // r14d
  unsigned int v14; // esi
  unsigned int v15; // r8d
  size_t v16; // r8
  void *v17; // rcx
  unsigned int *v18; // r15
  __int64 v19; // r8
  unsigned int v20; // eax
  unsigned int *v21; // rcx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int *v24; // rcx
  void *v25; // rcx
  void *v26; // rdx
  unsigned int v27; // eax
  _DWORD *v28; // rcx
  void *v29; // rcx
  __int64 v30; // r8
  unsigned int v31; // eax
  unsigned int *v32; // rcx
  unsigned int v33; // eax
  _QWORD *v34; // rcx
  unsigned int v35; // eax
  unsigned int *v36; // rcx
  unsigned int v37; // eax
  unsigned int *v38; // rcx
  unsigned int v39; // eax
  unsigned int *v40; // rcx
  __int64 v41; // r8
  unsigned int v42; // eax
  unsigned int *v43; // rcx
  unsigned int v44; // eax
  unsigned int v45; // ecx
  unsigned int v46; // eax
  unsigned int v47; // ecx
  int v49; // [rsp+80h] [rbp+8h]
  unsigned __int64 v50; // [rsp+88h] [rbp+10h]
  __int64 v51; // [rsp+98h] [rbp+20h]

  v51 = a4;
  v49 = a1;
  v7 = a2;
  v8 = (unsigned __int64)a2 + a3;
  v50 = v8;
  v9 = 0;
  v10 = 0;
  v11 = a2;
  v12 = a5;
  while ( 1 )
  {
    v13 = v11[15];
    if ( v13 >= a3 - 80 )
      v13 = a3 - 80;
    switch ( a1 )
    {
      case 1:
        v18 = (unsigned int *)(a4 + v9);
        v10 = v13 + 64;
        if ( a6 )
          RtlCopyToUser(v18, v7, 0x38u);
        else
          RtlCopyVolatileMemory(v18, v7, 0x38u);
        v37 = v11[14];
        if ( v11[17] == FileTag )
        {
          if ( byte_140018454 )
            v37 &= ~0x400u;
          if ( byte_140018455 )
            v37 &= ~0x200u;
          if ( !v37 )
            v37 = 128;
        }
        v38 = v18 + 14;
        if ( a6 )
          RtlWriteULongToUser(v38, v37);
        else
          *v38 = v37;
        v39 = v11[15];
        v40 = v18 + 15;
        if ( a6 )
          RtlWriteULongToUser(v40, v39);
        else
          *v40 = v39;
        v25 = v18 + 16;
        goto LABEL_28;
      case 2:
        v18 = (unsigned int *)(a4 + v9);
        v10 = v13 + 68;
        if ( a6 )
          RtlCopyToUser(v18, v7, 0x38u);
        else
          RtlCopyVolatileMemory(v18, v7, 0x38u);
        if ( v11[17] != FileTag )
        {
          v20 = v11[14];
          if ( a6 )
            RtlWriteULongToUser(v18 + 14, v20);
          else
            v18[14] = v20;
          v21 = v18 + 16;
          if ( (v11[14] & 0x400) != 0 )
            v22 = v11[17];
          else
            v22 = v11[16];
          if ( a6 )
            RtlWriteULongToUser(v21, v22);
          else
            *v21 = v22;
          goto LABEL_25;
        }
        v46 = WofSanitizeAttributes((unsigned int)v11[14], 0, v19);
        if ( a6 )
          RtlWriteULongToUser(v18 + 14, v46);
        else
          v18[14] = v46;
        if ( byte_140018454 )
        {
          v47 = v11[16];
          if ( !a6 )
          {
LABEL_112:
            v18[16] = v47;
LABEL_25:
            v23 = v11[15];
            v24 = v18 + 15;
            if ( a6 )
              RtlWriteULongToUser(v24, v23);
            else
              *v24 = v23;
            v25 = v18 + 17;
LABEL_28:
            v26 = v7 + 20;
            goto LABEL_29;
          }
        }
        else
        {
          v47 = v11[17];
          if ( !a6 )
            goto LABEL_112;
        }
        RtlWriteULongToUser(v18 + 16, v47);
        goto LABEL_25;
      case 38:
        v18 = (unsigned int *)(a4 + v9);
        v10 = v13 + 80;
        if ( a6 )
          RtlCopyToUser(v18, v7, 0x38u);
        else
          RtlCopyVolatileMemory(v18, v7, 0x38u);
        v29 = v18 + 17;
        if ( a6 )
          RtlSetUserMemory(v29);
        else
          RtlSetVolatileMemory(v29, 0, 4u);
        if ( v11[17] != FileTag )
        {
          v31 = v11[14];
          if ( a6 )
            RtlWriteULongToUser(v18 + 14, v31);
          else
            v18[14] = v31;
          v32 = v18 + 16;
          if ( (v11[14] & 0x400) != 0 )
            v33 = v11[17];
          else
            v33 = v11[16];
          if ( a6 )
            RtlWriteULongToUser(v32, v33);
          else
            *v32 = v33;
          goto LABEL_48;
        }
        v44 = WofSanitizeAttributes((unsigned int)v11[14], 0, v30);
        if ( a6 )
          RtlWriteULongToUser(v18 + 14, v44);
        else
          v18[14] = v44;
        if ( byte_140018454 )
        {
          v45 = v11[16];
          if ( !a6 )
          {
LABEL_103:
            v18[16] = v45;
LABEL_48:
            v34 = v18 + 18;
            if ( a6 )
              RtlWriteULong64ToUser(v34, *((_QWORD *)v11 + 9));
            else
              *v34 = *((_QWORD *)v11 + 9);
            v35 = v11[15];
            v36 = v18 + 15;
            if ( a6 )
              RtlWriteULongToUser(v36, v35);
            else
              *v36 = v35;
            v26 = v11 + 20;
            v25 = v18 + 20;
            goto LABEL_29;
          }
        }
        else
        {
          v45 = v11[17];
          if ( !a6 )
            goto LABEL_103;
        }
        RtlWriteULongToUser(v18 + 16, v45);
        goto LABEL_48;
    }
    if ( a1 != 78 )
      goto LABEL_8;
    v18 = (unsigned int *)(a4 + v9);
    v10 = v13 + 80;
    if ( a6 )
      RtlCopyToUser(v18, v7, 0x50u);
    else
      RtlCopyVolatileMemory(v18, v7, 0x50u);
    if ( v11[17] == FileTag )
    {
      v42 = WofSanitizeAttributes((unsigned int)v11[14], 0, v41);
      v43 = v18 + 14;
      if ( a6 )
        RtlWriteULongToUser(v43, v42);
      else
        *v43 = v42;
      if ( byte_140018454 )
      {
        if ( a6 )
          RtlWriteULongToUser(v18 + 17, 0);
        else
          v18[17] = 0;
      }
    }
    v26 = v11 + 20;
    v25 = v18 + 20;
LABEL_29:
    if ( a6 )
      RtlCopyToUser(v25, v26, v13);
    else
      RtlCopyVolatileMemory(v25, v26, v13);
    v27 = (v10 + 7) & 0xFFFFFFF8;
    if ( a6 )
      RtlWriteULongToUser(v18, v27);
    else
      *v18 = v27;
    v12 = a5;
    a4 = v51;
    v8 = v50;
LABEL_8:
    if ( !*v7 )
      break;
    v14 = (v10 + 7) & 0xFFFFFFF8;
    v15 = v14;
    if ( v14 >= v12 - v9 )
      v15 = v12 - v9;
    v16 = v15 - v10;
    v17 = (void *)(a4 + v9 + v10);
    if ( a6 )
      RtlSetUserMemory(v17);
    else
      RtlSetVolatileMemory(v17, 0, v16);
    v9 += v14;
    v7 = (_DWORD *)((char *)v7 + (unsigned int)*v7);
    v11 = v7;
    if ( (unsigned __int64)v7 >= v8 )
      goto LABEL_117;
    v12 = a5;
    if ( v9 >= a5 )
      goto LABEL_117;
    a3 = v8 - (_DWORD)v7;
    a1 = v49;
    a4 = v51;
  }
  v28 = (_DWORD *)(a4 + v9);
  if ( a6 )
    RtlWriteULongToUser(v28, 0);
  else
    *v28 = 0;
  v9 += v10;
LABEL_117:
  *a7 = v9;
  return 0;
}

```

## disassembly

```asm
0x140037cd0  mov     [rsp+arg_18], r9
0x140037cd5  mov     [rsp+arg_0], ecx
0x140037cd9  push    rbx
0x140037cda  push    rsi
0x140037cdb  push    rdi
0x140037cdc  push    r12
0x140037cde  push    r13
0x140037ce0  push    r14
0x140037ce2  push    r15
0x140037ce4  sub     rsp, 40h
0x140037ce8  mov     rdi, rdx
0x140037ceb  mov     [rsp+78h+var_58], 0
0x140037cf0  mov     [rsp+78h+arg_10], 0
0x140037cfb  mov     r15d, r8d
0x140037cfe  add     r15, rdx
0x140037d01  mov     [rsp+78h+arg_8], r15
0x140037d09  xor     ebx, ebx
0x140037d0b  xor     r13d, r13d
0x140037d0e  mov     rsi, rdx
0x140037d11  movzx   r12d, [rsp+78h+arg_28]
0x140037d1a  mov     edx, [rsp+78h+arg_20]
0x140037d21  mov     r14d, [rsi+3Ch]
0x140037d25  lea     eax, [r8-50h]
0x140037d29  cmp     r14d, eax
0x140037d2c  cmovnb  r14d, eax
0x140037d30  mov     eax, ecx
0x140037d32  sub     eax, 1
0x140037d35  jz      loc_14003800D
0x140037d3b  sub     eax, 1
0x140037d3e  jz      loc_140037DDC
0x140037d44  sub     eax, 24h ; '$'
0x140037d47  jz      loc_140037EE5
0x140037d4d  cmp     eax, 28h ; '('
0x140037d50  jz      loc_1400380E3
0x140037d56  mov     [rsp+78h+var_58], 1
0x140037d5b  cmp     dword ptr [rdi], 0
0x140037d5e  jz      loc_140037EBF
0x140037d64  mov     ecx, edx
0x140037d66  sub     ecx, ebx
0x140037d68  lea     esi, [r13+7]
0x140037d6c  and     esi, 0FFFFFFF8h
0x140037d6f  mov     r8d, esi
0x140037d72  cmp     esi, ecx
0x140037d74  cmovnb  r8d, ecx
0x140037d78  sub     r8d, r13d; Size
0x140037d7b  lea     ecx, [rbx+r13]
0x140037d7f  add     rcx, r9; void *
0x140037d82  xor     edx, edx; Val
0x140037d84  test    r12b, r12b
0x140037d87  jz      loc_140037FB9
0x140037d8d  call    RtlSetUserMemory
0x140037d92  mov     [rsp+78h+var_58], 0
0x140037d97  add     ebx, esi
0x140037d99  mov     [rsp+78h+var_48], ebx
0x140037d9d  mov     eax, [rdi]
0x140037d9f  add     rdi, rax
0x140037da2  mov     [rsp+78h+var_40], rdi
0x140037da7  mov     rsi, rdi
0x140037daa  cmp     rdi, r15
0x140037dad  jnb     loc_140038231
0x140037db3  mov     edx, [rsp+78h+arg_20]
0x140037dba  cmp     ebx, edx
0x140037dbc  jnb     loc_140038231
0x140037dc2  mov     r8d, r15d
0x140037dc5  sub     r8d, edi
0x140037dc8  mov     ecx, [rsp+78h+arg_0]
0x140037dcf  mov     r9, [rsp+78h+arg_18]
0x140037dd7  jmp     loc_140037D21
0x140037ddc  mov     r15d, ebx
0x140037ddf  add     r15, r9
0x140037de2  lea     r13d, [r14+44h]
0x140037de6  mov     [rsp+78h+var_54], r13d
0x140037deb  mov     [rsp+78h+var_58], 1
0x140037df0  mov     r8d, 38h ; '8'; Size
0x140037df6  mov     rdx, rdi; Src
0x140037df9  mov     rcx, r15; void *
0x140037dfc  test    r12b, r12b
0x140037dff  jz      loc_140037FEF
0x140037e05  call    RtlCopyToUser
0x140037e0a  mov     eax, cs:FileTag
0x140037e10  cmp     [rsi+44h], eax
0x140037e13  jz      loc_1400381CF
0x140037e19  mov     eax, [rsi+38h]
0x140037e1c  test    r12b, r12b
0x140037e1f  jz      loc_140037FCD
0x140037e25  mov     edx, eax
0x140037e27  lea     rcx, [r15+38h]
0x140037e2b  call    RtlWriteULongToUser
0x140037e30  lea     rcx, [r15+40h]
0x140037e34  test    dword ptr [rsi+38h], 400h
0x140037e3b  jnz     loc_14003807F
0x140037e41  mov     eax, [rsi+40h]
0x140037e44  test    r12b, r12b
0x140037e47  jz      loc_140037FD6
0x140037e4d  mov     edx, eax
0x140037e4f  call    RtlWriteULongToUser
0x140037e54  mov     eax, [rsi+3Ch]
0x140037e57  lea     rcx, [r15+3Ch]
0x140037e5b  test    r12b, r12b
0x140037e5e  jz      loc_140037FDD
0x140037e64  mov     edx, eax
0x140037e66  call    RtlWriteULongToUser
0x140037e6b  lea     rcx, [r15+44h]; void *
0x140037e6f  lea     rdx, [rdi+50h]; Src
0x140037e73  mov     r8d, r14d; Size
0x140037e76  test    r12b, r12b
0x140037e79  jz      loc_140037FC3
0x140037e7f  call    RtlCopyToUser
0x140037e84  lea     eax, [r13+7]
0x140037e88  and     eax, 0FFFFFFF8h
0x140037e8b  test    r12b, r12b
0x140037e8e  jz      loc_140037FAC
0x140037e94  mov     edx, eax
0x140037e96  mov     rcx, r15
0x140037e99  call    RtlWriteULongToUser
0x140037e9e  mov     [rsp+78h+var_58], 0
0x140037ea3  mov     edx, [rsp+78h+arg_20]
0x140037eaa  mov     r9, [rsp+78h+arg_18]
0x140037eb2  mov     r15, [rsp+78h+arg_8]
0x140037eba  jmp     loc_140037D56
0x140037ebf  mov     ecx, ebx
0x140037ec1  add     rcx, r9
0x140037ec4  test    r12b, r12b
0x140037ec7  jz      loc_140037FE4
0x140037ecd  xor     edx, edx
0x140037ecf  call    RtlWriteULongToUser
0x140037ed4  mov     [rsp+78h+var_58], 0
0x140037ed9  add     ebx, r13d
0x140037edc  mov     [rsp+78h+var_48], ebx
0x140037ee0  jmp     loc_140038231
0x140037ee5  mov     r15d, ebx
0x140037ee8  add     r15, r9
0x140037eeb  lea     r13d, [r14+50h]
0x140037eef  mov     [rsp+78h+var_54], r13d
0x140037ef4  mov     [rsp+78h+var_58], 1
0x140037ef9  mov     r8d, 38h ; '8'; Size
0x140037eff  mov     rdx, rdi; Src
0x140037f02  mov     rcx, r15; void *
0x140037f05  test    r12b, r12b
0x140037f08  jz      loc_140038075
0x140037f0e  call    RtlCopyToUser
0x140037f13  lea     rcx, [r15+44h]; void *
0x140037f17  xor     edx, edx; Val
0x140037f19  mov     r8d, 4; Size
0x140037f1f  test    r12b, r12b
0x140037f22  jz      loc_140038087
0x140037f28  call    RtlSetUserMemory
0x140037f2d  mov     eax, cs:FileTag
0x140037f33  cmp     [rsi+44h], eax
0x140037f36  jz      loc_14003816D
0x140037f3c  mov     eax, [rsi+38h]
0x140037f3f  test    r12b, r12b
0x140037f42  jz      loc_140037FF9
0x140037f48  mov     edx, eax
0x140037f4a  lea     rcx, [r15+38h]
0x140037f4e  call    RtlWriteULongToUser
0x140037f53  lea     rcx, [r15+40h]
0x140037f57  test    dword ptr [rsi+38h], 400h
0x140037f5e  jz      loc_140038091
0x140037f64  mov     eax, [rsi+44h]
0x140037f67  test    r12b, r12b
0x140037f6a  jz      loc_140038002
0x140037f70  mov     edx, eax
0x140037f72  call    RtlWriteULongToUser
0x140037f77  mov     rax, [rsi+48h]
0x140037f7b  lea     rcx, [r15+48h]
0x140037f7f  test    r12b, r12b
0x140037f82  jz      short loc_140037FB4
0x140037f84  mov     rdx, rax
0x140037f87  call    RtlWriteULong64ToUser
0x140037f8c  mov     eax, [rsi+3Ch]
0x140037f8f  lea     rcx, [r15+3Ch]
0x140037f93  test    r12b, r12b
0x140037f96  jz      short loc_140038009
0x140037f98  mov     edx, eax
0x140037f9a  call    RtlWriteULongToUser
0x140037f9f  lea     rdx, [rsi+50h]
0x140037fa3  lea     rcx, [r15+50h]
0x140037fa7  jmp     loc_140037E73
0x140037fac  mov     [r15], eax
0x140037faf  jmp     loc_140037E9E
0x140037fb4  mov     [rcx], rax
0x140037fb7  jmp     short loc_140037F8C
0x140037fb9  call    RtlSetVolatileMemory
0x140037fbe  jmp     loc_140037D92
0x140037fc3  call    RtlCopyVolatileMemory
0x140037fc8  jmp     loc_140037E84
0x140037fcd  mov     [r15+38h], eax
0x140037fd1  jmp     loc_140037E30
0x140037fd6  mov     [rcx], eax
0x140037fd8  jmp     loc_140037E54
0x140037fdd  mov     [rcx], eax
0x140037fdf  jmp     loc_140037E6B
0x140037fe4  mov     dword ptr [rcx], 0
0x140037fea  jmp     loc_140037ED4
0x140037fef  call    RtlCopyVolatileMemory
0x140037ff4  jmp     loc_140037E0A
0x140037ff9  mov     [r15+38h], eax
0x140037ffd  jmp     loc_140037F53
0x140038002  mov     [rcx], eax
0x140038004  jmp     loc_140037F77
0x140038009  mov     [rcx], eax
0x14003800b  jmp     short loc_140037F9F
0x14003800d  mov     r15d, ebx
0x140038010  add     r15, r9
0x140038013  lea     r13d, [r14+40h]
0x140038017  mov     [rsp+78h+var_54], r13d
0x14003801c  mov     [rsp+78h+var_58], 1
0x140038021  mov     r8d, 38h ; '8'; Size
0x140038027  mov     rdx, rdi; Src
0x14003802a  mov     rcx, r15; void *
0x14003802d  test    r12b, r12b
0x140038030  jz      loc_1400380D9
0x140038036  call    RtlCopyToUser
0x14003803b  mov     eax, cs:FileTag
0x140038041  cmp     [rsi+44h], eax
0x140038044  mov     eax, [rsi+38h]
0x140038047  jz      short loc_140038099
0x140038049  test    r12b, r12b
0x14003804c  lea     rcx, [r15+38h]
0x140038050  jz      short loc_1400380D1
0x140038052  mov     edx, eax
0x140038054  call    RtlWriteULongToUser
0x140038059  mov     eax, [rsi+3Ch]
0x14003805c  lea     rcx, [r15+3Ch]
0x140038060  test    r12b, r12b
0x140038063  jz      short loc_1400380D5
0x140038065  mov     edx, eax
0x140038067  call    RtlWriteULongToUser
0x14003806c  lea     rcx, [r15+40h]
0x140038070  jmp     loc_140037E6F
0x140038075  call    RtlCopyVolatileMemory
0x14003807a  jmp     loc_140037F13
0x14003807f  mov     eax, [rsi+44h]
0x140038082  jmp     loc_140037E44
0x140038087  call    RtlSetVolatileMemory
0x14003808c  jmp     loc_140037F2D
0x140038091  mov     eax, [rsi+40h]
0x140038094  jmp     loc_140037F67
0x140038099  mov     [rsp+78h+var_50], eax
0x14003809d  cmp     cs:byte_140018454, 0
0x1400380a4  jz      short loc_1400380AE
0x1400380a6  btr     eax, 0Ah
0x1400380aa  mov     [rsp+78h+var_50], eax
0x1400380ae  cmp     cs:byte_140018455, 0
0x1400380b5  jnz     short loc_1400380C7
0x1400380b7  test    eax, eax
0x1400380b9  mov     ecx, 80h
0x1400380be  cmovz   eax, ecx
0x1400380c1  mov     [rsp+78h+var_50], eax
0x1400380c5  jmp     short loc_140038049
0x1400380c7  btr     eax, 9
0x1400380cb  mov     [rsp+78h+var_50], eax
0x1400380cf  jmp     short loc_1400380B7
0x1400380d1  mov     [rcx], eax
0x1400380d3  jmp     short loc_140038059
0x1400380d5  mov     [rcx], eax
0x1400380d7  jmp     short loc_14003806C
0x1400380d9  call    RtlCopyVolatileMemory
0x1400380de  jmp     loc_14003803B
0x1400380e3  mov     r15d, ebx
0x1400380e6  add     r15, r9
0x1400380e9  lea     r13d, [r14+50h]
0x1400380ed  mov     [rsp+78h+var_54], r13d
0x1400380f2  mov     [rsp+78h+var_58], 1
0x1400380f7  mov     r8d, 50h ; 'P'; Size
0x1400380fd  mov     rdx, rdi; Src
0x140038100  mov     rcx, r15; void *
0x140038103  test    r12b, r12b
0x140038106  jz      short loc_140038158
0x140038108  call    RtlCopyToUser
0x14003810d  mov     eax, cs:FileTag
0x140038113  cmp     [rsi+44h], eax
0x140038116  jnz     short loc_14003814B
0x140038118  xor     edx, edx
0x14003811a  mov     ecx, [rsi+38h]
0x14003811d  call    WofSanitizeAttributes
0x140038122  lea     rcx, [r15+38h]
0x140038126  test    r12b, r12b
0x140038129  jz      short loc_14003815F
0x14003812b  mov     edx, eax
0x14003812d  call    RtlWriteULongToUser
0x140038132  cmp     cs:byte_140018454, 0
0x140038139  jz      short loc_14003814B
0x14003813b  test    r12b, r12b
0x14003813e  jz      short loc_140038163
0x140038140  xor     edx, edx
0x140038142  lea     rcx, [r15+44h]
0x140038146  call    RtlWriteULongToUser
0x14003814b  lea     rdx, [rsi+50h]
0x14003814f  lea     rcx, [r15+50h]
0x140038153  jmp     loc_140037E73
0x140038158  call    RtlCopyVolatileMemory
0x14003815d  jmp     short loc_14003810D
0x14003815f  mov     [rcx], eax
0x140038161  jmp     short loc_140038132
0x140038163  mov     dword ptr [r15+44h], 0
0x14003816b  jmp     short loc_14003814B
0x14003816d  xor     edx, edx
0x14003816f  mov     ecx, [rsi+38h]
  ... truncated ...
```
