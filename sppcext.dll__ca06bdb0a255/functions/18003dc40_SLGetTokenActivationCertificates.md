# SLGetTokenActivationCertificates

- ea: `0x18003dc40`
- end: `0x18003ded5`
- name: `SLGetTokenActivationCertificates`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: ``

## callees

- `0x180004590`
- `0x180004ca0`
- `0x180006c10`
- `0x180034964`
- `0x180034c28`
- `0x180035284`
- `0x1800367d8`
- `0x1800369e0`
- `0x180037150`
- `0x1800376f4`
- `0x180037884`
- `0x18003b1d0`
- `0x18003b228`
- `0x18003b8e4`
- `0x18003c660`
- `0x18003dc40`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043364`
- `0x18004362c`
- `0x180043900`
- `0x180043bd8`
- `0x180043eac`

## pseudocode

```c
__int64 __fastcall SLGetTokenActivationCertificates(_DWORD *a1, char a2, _QWORD *a3)
{
  __int64 v5; // r14
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // r8
  int v14; // edi
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // r8
  unsigned int v18; // edx
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v23; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v24[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v25; // [rsp+38h] [rbp-18h] BYREF
  __int64 v26; // [rsp+40h] [rbp-10h]
  __int64 v27; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+58h] BYREF

  v23 = 0;
  v5 = 0;
  sub_180042514(qword_180081398, qword_18008DCB8);
  v27 = 0;
  v24[0] = 0;
  v24[1] = 0;
  sub_180043BD8(&dword_180083D94, &dword_18008DAC4);
  v25 = 0;
  v26 = 0;
  sub_1800427F4(qword_180083AE0, &dword_18008E0CC);
  v28 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
LABEL_3:
    v8 = v7;
LABEL_4:
    sub_180004CA0(v8);
    goto LABEL_32;
  }
  sub_180042ACC(byte_180080978, &dword_18008D46C);
  if ( a1 )
  {
    v11 = sub_1800369E0(v10, v9, &v23);
    v7 = v11;
    if ( v11 < 0 )
      goto LABEL_7;
    v12 = 0;
    v5 = v23;
    if ( *a1 )
    {
      do
      {
        sub_18003B228(&v27);
        v11 = sub_180034964(&v27);
        v7 = v11;
        if ( v11 < 0 )
          goto LABEL_7;
        v11 = sub_18003B8E4(v27, *(_QWORD *)&a1[2 * v12 + 2]);
        v7 = v11;
        if ( v11 < 0 )
          goto LABEL_7;
        v11 = sub_180035284(v5, v12, v13, v27);
        v7 = v11;
        if ( v11 < 0 )
          goto LABEL_7;
      }
      while ( ++v12 < *a1 );
    }
  }
  v7 = 0;
  sub_180043EAC(qword_180080948, qword_18008D458);
  v14 = 0;
  if ( (a2 & 1) != 0 )
    v7 = sub_180037884(v24);
  if ( (a2 & 2) != 0 )
    v14 = sub_1800376F4((__int64)v24);
  if ( !HIDWORD(v24[0]) )
  {
    if ( (v7 & 0x80000000) != 0 )
      goto LABEL_3;
    if ( v14 < 0 )
    {
      sub_18004362C(byte_180084320, byte_18008CF40);
      v7 = v14;
      sub_180043900(byte_1800856D8, qword_18008CB30);
      v8 = (unsigned int)v14;
      goto LABEL_4;
    }
  }
  if ( a1 )
  {
    v15 = sub_180037150(v5, v24, &v25);
    v7 = v15;
    if ( v15 < 0 )
    {
      sub_180004CA0((unsigned int)v15);
      sub_180043088(byte_180081D30, &dword_18008E21C);
      goto LABEL_32;
    }
  }
  else
  {
    sub_18003C660(&v25, v24);
  }
  v16 = HIDWORD(v25);
  if ( !HIDWORD(v25) )
  {
    v7 = -1073417467;
    goto LABEL_3;
  }
  v11 = sub_1800367D8(HIDWORD(v25), &v28);
  v7 = v11;
  if ( v11 < 0 )
  {
LABEL_7:
    v8 = (unsigned int)v11;
    goto LABEL_4;
  }
  v17 = v28;
  v18 = 0;
  if ( v16 )
  {
    v19 = v26;
    do
    {
      v20 = *(_QWORD *)(v19 + 8LL * (int)v18);
      *(_QWORD *)(v19 + 8LL * (int)v18) = 0;
      v21 = v18++;
      *(_QWORD *)(v17 + 8 * v21 + 8) = v20;
    }
    while ( v18 < v16 );
  }
  v28 = 0;
  *a3 = v17;
  sub_180042DB0(qword_180083E48, &dword_18008E1B4);
LABEL_32:
  sub_180006C10(v7);
  sub_18003B1D0(&v28);
  sub_180034C28(&v25);
  sub_180034C28(v24);
  sub_180043364(byte_180082198, qword_18008CD68);
  sub_18003B228(&v27);
  sub_180004590(&v23);
  return v7;
}

```

## disassembly

```asm
0x18003dc40  mov     [rsp-38h+arg_0], rbx
0x18003dc45  push    rbp
0x18003dc46  push    rsi
0x18003dc47  push    rdi
0x18003dc48  push    r12
0x18003dc4a  push    r13
0x18003dc4c  push    r14
0x18003dc4e  push    r15
0x18003dc50  mov     rbp, rsp
0x18003dc53  sub     rsp, 50h
0x18003dc57  mov     r15d, edx
0x18003dc5a  mov     rsi, rcx
0x18003dc5d  xor     r13d, r13d
0x18003dc60  lea     rdx, qword_18008DCB8
0x18003dc67  lea     rcx, qword_180081398
0x18003dc6e  mov     [rbp+var_30], r13
0x18003dc72  mov     r14d, r13d
0x18003dc75  mov     r12, r8
0x18003dc78  call    sub_180042514
0x18003dc7d  lea     rdx, dword_18008DAC4
0x18003dc84  mov     [rbp+arg_10], r13
0x18003dc88  lea     rcx, dword_180083D94
0x18003dc8f  mov     [rbp+var_28], r13
0x18003dc93  mov     [rbp+var_20], r13
0x18003dc97  call    sub_180043BD8
0x18003dc9c  lea     rdx, dword_18008E0CC
0x18003dca3  mov     [rbp+var_18], r13
0x18003dca7  lea     rcx, qword_180083AE0
0x18003dcae  mov     [rbp+var_10], r13
0x18003dcb2  call    sub_1800427F4
0x18003dcb7  mov     [rbp+arg_18], r13
0x18003dcbb  test    r12, r12
0x18003dcbe  jnz     short loc_18003DCD1
0x18003dcc0  mov     ebx, 80070057h
0x18003dcc5  mov     ecx, ebx
0x18003dcc7  call    sub_180004CA0
0x18003dccc  jmp     loc_18003DE74
0x18003dcd1  lea     rdx, dword_18008D46C
0x18003dcd8  lea     rcx, byte_180080978
0x18003dcdf  call    sub_180042ACC
0x18003dce4  test    rsi, rsi
0x18003dce7  jz      short loc_18003DD50
0x18003dce9  lea     r8, [rbp+var_30]
0x18003dced  call    sub_1800369E0
0x18003dcf2  mov     ebx, eax
0x18003dcf4  test    eax, eax
0x18003dcf6  jns     short loc_18003DCFC
0x18003dcf8  mov     ecx, eax
0x18003dcfa  jmp     short loc_18003DCC7
0x18003dcfc  mov     edi, r13d
0x18003dcff  mov     r14, [rbp+var_30]
0x18003dd03  cmp     [rsi], r13d
0x18003dd06  jbe     short loc_18003DD50
0x18003dd08  lea     rcx, [rbp+arg_10]
0x18003dd0c  call    sub_18003B228
0x18003dd11  lea     rcx, [rbp+arg_10]
0x18003dd15  call    sub_180034964
0x18003dd1a  mov     ebx, eax
0x18003dd1c  test    eax, eax
0x18003dd1e  js      short loc_18003DCF8
0x18003dd20  mov     rcx, [rbp+arg_10]
0x18003dd24  mov     edx, edi
0x18003dd26  mov     rdx, [rsi+rdx*8+8]
0x18003dd2b  call    sub_18003B8E4
0x18003dd30  mov     ebx, eax
0x18003dd32  test    eax, eax
0x18003dd34  js      short loc_18003DCF8
0x18003dd36  mov     r9, [rbp+arg_10]
0x18003dd3a  mov     edx, edi
0x18003dd3c  mov     rcx, r14
0x18003dd3f  call    sub_180035284
0x18003dd44  mov     ebx, eax
0x18003dd46  test    eax, eax
0x18003dd48  js      short loc_18003DCF8
0x18003dd4a  inc     edi
0x18003dd4c  cmp     edi, [rsi]
0x18003dd4e  jb      short loc_18003DD08
0x18003dd50  lea     rdx, qword_18008D458
0x18003dd57  mov     ebx, r13d
0x18003dd5a  lea     rcx, qword_180080948
0x18003dd61  call    sub_180043EAC
0x18003dd66  mov     edi, r13d
0x18003dd69  test    r15b, 1
0x18003dd6d  jz      short loc_18003DD7A
0x18003dd6f  lea     rcx, [rbp+var_28]
0x18003dd73  call    sub_180037884
0x18003dd78  mov     ebx, eax
0x18003dd7a  test    r15b, 2
0x18003dd7e  jz      short loc_18003DD8B
0x18003dd80  lea     rcx, [rbp+var_28]
0x18003dd84  call    sub_1800376F4
0x18003dd89  mov     edi, eax
0x18003dd8b  cmp     dword ptr [rbp+var_28+4], r13d
0x18003dd8f  jnz     short loc_18003DDCC
0x18003dd91  test    ebx, ebx
0x18003dd93  js      loc_18003DCC5
0x18003dd99  test    edi, edi
0x18003dd9b  jns     short loc_18003DDCC
0x18003dd9d  lea     rdx, byte_18008CF40
0x18003dda4  lea     rcx, byte_180084320
0x18003ddab  call    sub_18004362C
0x18003ddb0  lea     rdx, qword_18008CB30
0x18003ddb7  mov     ebx, edi
0x18003ddb9  lea     rcx, byte_1800856D8
0x18003ddc0  call    sub_180043900
0x18003ddc5  mov     ecx, edi
0x18003ddc7  jmp     loc_18003DCC7
0x18003ddcc  lea     rdx, [rbp+var_28]
0x18003ddd0  test    rsi, rsi
0x18003ddd3  jz      short loc_18003DE03
0x18003ddd5  lea     r8, [rbp+var_18]
0x18003ddd9  mov     rcx, r14
0x18003dddc  call    sub_180037150
0x18003dde1  mov     ebx, eax
0x18003dde3  test    eax, eax
0x18003dde5  jns     short loc_18003DE0C
0x18003dde7  mov     ecx, eax
0x18003dde9  call    sub_180004CA0
0x18003ddee  lea     rdx, dword_18008E21C
0x18003ddf5  lea     rcx, byte_180081D30
0x18003ddfc  call    sub_180043088
0x18003de01  jmp     short loc_18003DE74
0x18003de03  lea     rcx, [rbp+var_18]
0x18003de07  call    sub_18003C660
0x18003de0c  mov     edi, dword ptr [rbp+var_18+4]
0x18003de0f  test    edi, edi
0x18003de11  jnz     short loc_18003DE1D
0x18003de13  mov     ebx, 0C004F305h
0x18003de18  jmp     loc_18003DCC5
0x18003de1d  lea     rdx, [rbp+arg_18]
0x18003de21  mov     ecx, edi
0x18003de23  call    sub_1800367D8
0x18003de28  mov     ebx, eax
0x18003de2a  test    eax, eax
0x18003de2c  js      loc_18003DCF8
0x18003de32  mov     r8, [rbp+arg_18]
0x18003de36  mov     edx, r13d
0x18003de39  test    edi, edi
0x18003de3b  jz      short loc_18003DE59
0x18003de3d  mov     r9, [rbp+var_10]
0x18003de41  movsxd  rax, edx
0x18003de44  mov     rcx, [r9+rax*8]
0x18003de48  mov     [r9+rax*8], r13
0x18003de4c  mov     eax, edx
0x18003de4e  inc     edx
0x18003de50  mov     [r8+rax*8+8], rcx
0x18003de55  cmp     edx, edi
0x18003de57  jb      short loc_18003DE41
0x18003de59  lea     rdx, dword_18008E1B4
0x18003de60  mov     [rbp+arg_18], r13
0x18003de64  lea     rcx, qword_180083E48
0x18003de6b  mov     [r12], r8
0x18003de6f  call    sub_180042DB0
0x18003de74  mov     ecx, ebx
0x18003de76  call    sub_180006C10
0x18003de7b  lea     rcx, [rbp+arg_18]
0x18003de7f  call    sub_18003B1D0
0x18003de84  lea     rcx, [rbp+var_18]
0x18003de88  call    sub_180034C28
0x18003de8d  lea     rcx, [rbp+var_28]
0x18003de91  call    sub_180034C28
0x18003de96  lea     rdx, qword_18008CD68
0x18003de9d  lea     rcx, byte_180082198
0x18003dea4  call    sub_180043364
0x18003dea9  lea     rcx, [rbp+arg_10]
0x18003dead  call    sub_18003B228
0x18003deb2  lea     rcx, [rbp+var_30]
0x18003deb6  call    sub_180004590
0x18003debb  mov     eax, ebx
0x18003debd  mov     rbx, [rsp+50h+arg_0]
0x18003dec5  add     rsp, 50h
0x18003dec9  pop     r15
0x18003decb  pop     r14
0x18003decd  pop     r13
0x18003decf  pop     r12
0x18003ded1  pop     rdi
0x18003ded2  pop     rsi
0x18003ded3  pop     rbp
0x18003ded4  retn
```
