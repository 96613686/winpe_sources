# MinAsn1ExtractValues

- ea: `0x18004de78`
- end: `0x18004e120`
- name: `MinAsn1ExtractValues`
- size: `680`
- prototype: ``
- caller_count: `21`
- callee_count: `3`
- tags: ``

## callers

- `0x180044b10`
- `0x18004c6f4`
- `0x18004c8d4`
- `0x18004c91c`
- `0x18004ca40`
- `0x18004cb24`
- `0x18004cb6c`
- `0x18004cbb4`
- `0x18004cbf8`
- `0x18004cc70`
- `0x18004cd54`
- `0x18004cd9c`
- `0x18004ce44`
- `0x18004cf24`
- `0x18004cf6c`
- `0x18004cfb4`
- `0x18004cffc`
- `0x18004d134`
- `0x18004d198`
- `0x18004d310`
- `0x18004e1f4`

## callees

- `0x180033980`
- `0x18004dd2c`
- `0x18004de78`

## pseudocode

```c
__int64 __fastcall MinAsn1ExtractValues(
        _BYTE *a1,
        unsigned int a2,
        unsigned int *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // r10
  unsigned int *v7; // rax
  __int64 v8; // r11
  unsigned int v9; // r12d
  int v10; // esi
  _BYTE *v11; // rdi
  unsigned int v12; // r13d
  unsigned int v13; // eax
  char v14; // r9
  unsigned int v15; // r15d
  unsigned int v16; // edx
  int v17; // r14d
  bool v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  _BYTE *v21; // rax
  int v22; // eax
  unsigned int v23; // r8d
  _BYTE *v24; // r9
  unsigned int v25; // edx
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // r14d
  int v29; // r14d
  __int64 v30; // rcx
  _BYTE *v31; // rax
  unsigned int v32; // esi
  char v34; // [rsp+20h] [rbp-B9h]
  bool v35; // [rsp+21h] [rbp-B8h]
  unsigned int v36; // [rsp+24h] [rbp-B5h]
  unsigned int v37; // [rsp+28h] [rbp-B1h] BYREF
  __int64 v38; // [rsp+30h] [rbp-A9h]
  int v39; // [rsp+38h] [rbp-A1h]
  unsigned int v40; // [rsp+3Ch] [rbp-9Dh]
  unsigned int *v41; // [rsp+40h] [rbp-99h]
  _BYTE *v42; // [rsp+48h] [rbp-91h] BYREF
  __int64 v43; // [rsp+50h] [rbp-89h]
  _QWORD v44[16]; // [rsp+60h] [rbp-79h]

  v6 = a6;
  v7 = a3;
  v41 = a3;
  v8 = a4;
  v38 = a6;
  v9 = a2;
  v43 = a4;
  v10 = (int)a1;
  v11 = a1;
  if ( a2 < 0x7FFFFFFF )
  {
    v13 = *a3;
    v14 = 0;
    v15 = 0;
    v34 = 0;
    v12 = 0;
    v40 = *a3;
    while ( 1 )
    {
      if ( v12 >= v13 )
      {
        v7 = v41;
        v32 = (_DWORD)v11 - v10;
        goto LABEL_48;
      }
      v16 = *(_DWORD *)(v8 + 16LL * v12 + 4);
      v39 = *(_DWORD *)(v8 + 16LL * v12);
      v17 = (unsigned __int8)v39;
      v36 = v16;
      v18 = (v39 & 0xC0000000) != 0 && v6 && v16 < a5;
      v35 = v18;
      v37 = 0;
      v42 = 0;
      if ( (unsigned __int8)v39 == 5 )
      {
        if ( !v15 )
          goto LABEL_45;
        v11 = (_BYTE *)v44[2 * --v15];
        v9 = v44[2 * v15 + 1];
        v14 = BYTE4(v44[2 * v15 + 1]);
LABEL_21:
        v34 = v14;
        goto LABEL_22;
      }
      if ( !v14 )
      {
        if ( v9 )
        {
          v21 = *(_BYTE **)(v8 + 16LL * v12 + 8);
          if ( !v21 )
          {
LABEL_30:
            v22 = MinAsn1ExtractContent(v11, v9, &v37, &v42);
            if ( v22 <= 0 )
              goto LABEL_45;
            v23 = v37;
            v24 = v42;
            v6 = v38;
            v25 = v37 + v22;
            if ( v35 )
            {
              if ( (v39 & 0x40000000) != 0 )
              {
                v26 = 2LL * v36;
                *(_QWORD *)(v38 + 8 * v26 + 8) = v42;
                *(_DWORD *)(v6 + 8 * v26) = v23;
                if ( *v11 == 3 && v23 )
                {
                  *(_QWORD *)(v6 + 16LL * v36 + 8) = v24 + 1;
                  *(_DWORD *)(v6 + 16LL * v36) = v23 - 1;
                }
              }
              else if ( v39 < 0 )
              {
                v27 = 2LL * v36;
                *(_QWORD *)(v38 + 8 * v27 + 8) = v11;
                *(_DWORD *)(v6 + 8 * v27) = v25;
              }
            }
            v28 = v17 - 1;
            if ( v28 && (v29 = v28 - 1) != 0 )
            {
              if ( (unsigned int)(v29 - 1) > 1 || v15 >= 8 )
                goto LABEL_45;
              v30 = 2LL * v15;
              v31 = &v11[v25];
              v11 = v24;
              ++v15;
              LODWORD(v44[v30 + 1]) = v9 - v25;
              v9 = v23;
              v44[v30] = v31;
              BYTE4(v44[v30 + 1]) = 0;
            }
            else
            {
              v11 += v25;
              v9 -= v25;
            }
            v14 = v34;
            v8 = v43;
            goto LABEL_22;
          }
          while ( *v21 )
          {
            if ( *v21 == *v11 )
              goto LABEL_30;
            ++v21;
          }
          if ( (((unsigned __int8)v39 - 2) & 0xFFFFFFFD) != 0 )
          {
LABEL_45:
            v7 = v41;
            goto LABEL_46;
          }
        }
        else if ( (((unsigned __int8)v39 - 2) & 0xFFFFFFFD) != 0 )
        {
          goto LABEL_45;
        }
      }
      if ( v18 )
      {
        v19 = 2LL * v16;
        *(_QWORD *)(v6 + 8 * v19 + 8) = 0;
        *(_DWORD *)(v6 + 8 * v19) = 0;
      }
      if ( (unsigned int)(v17 - 3) <= 1 )
      {
        if ( v15 >= 8 )
          goto LABEL_45;
        v20 = 2LL * v15++;
        BYTE4(v44[v20 + 1]) = v14;
        v14 = 1;
        v44[v20] = v11;
        LODWORD(v44[v20 + 1]) = v9;
        goto LABEL_21;
      }
LABEL_22:
      v13 = v40;
      ++v12;
    }
  }
  v12 = 0;
LABEL_46:
  v32 = v10 - (_DWORD)v11 - 1;
LABEL_48:
  *v7 = v12;
  return v32;
}

```

## disassembly

```asm
0x18004de78  push    rbp
0x18004de7a  push    rsi
0x18004de7b  push    rdi
0x18004de7c  push    r12
0x18004de7e  push    r13
0x18004de80  push    r14
0x18004de82  push    r15
0x18004de84  lea     rbp, [rsp-17h]
0x18004de89  sub     rsp, 0F0h
0x18004de90  mov     rax, cs:__security_cookie
0x18004de97  xor     rax, rsp
0x18004de9a  mov     [rbp+47h+var_40], rax
0x18004de9e  mov     r10, [rbp+47h+arg_28]
0x18004dea2  mov     rax, r8
0x18004dea5  mov     [rsp+120h+var_E0], rax
0x18004deaa  mov     r11, r9
0x18004dead  mov     [rsp+120h+var_F0], r10
0x18004deb2  mov     r12d, edx
0x18004deb5  mov     [rsp+120h+var_D0], r9
0x18004deba  mov     rsi, rcx
0x18004debd  mov     rdi, rcx
0x18004dec0  cmp     edx, 7FFFFFFFh
0x18004dec6  jb      short loc_18004DED0
0x18004dec8  xor     r13d, r13d
0x18004decb  jmp     loc_18004E0EC
0x18004ded0  mov     eax, [r8]
0x18004ded3  xor     r9b, r9b
0x18004ded6  xor     r15d, r15d
0x18004ded9  mov     [rsp+120h+var_100], r9b
0x18004dede  xor     r13d, r13d
0x18004dee1  mov     [rsp+120h+var_E4], eax
0x18004dee5  cmp     r13d, eax
0x18004dee8  jnb     loc_18004E0F2
0x18004deee  mov     eax, r13d
0x18004def1  add     rax, rax
0x18004def4  mov     ecx, [r11+rax*8]
0x18004def8  mov     edx, [r11+rax*8+4]
0x18004defd  mov     [rsp+120h+var_E8], ecx
0x18004df01  movzx   r14d, cl
0x18004df05  mov     [rsp+120h+var_FC], edx
0x18004df09  test    ecx, 0C0000000h
0x18004df0f  jz      short loc_18004DF20
0x18004df11  test    r10, r10
0x18004df14  jz      short loc_18004DF20
0x18004df16  cmp     edx, [rbp+47h+arg_20]
0x18004df19  jnb     short loc_18004DF20
0x18004df1b  mov     r8b, 1
0x18004df1e  jmp     short loc_18004DF23
0x18004df20  xor     r8b, r8b
0x18004df23  mov     [rsp+120h+var_FF], r8b
0x18004df28  mov     [rsp+120h+var_F8], 0
0x18004df30  mov     [rsp+120h+var_D8], 0
0x18004df39  cmp     r14d, 5
0x18004df3d  jnz     short loc_18004DF62
0x18004df3f  test    r15d, r15d
0x18004df42  jz      loc_18004E0E7
0x18004df48  dec     r15d
0x18004df4b  mov     eax, r15d
0x18004df4e  add     rax, rax
0x18004df51  mov     rdi, [rbp+rax*8+47h+var_C0]
0x18004df56  mov     r12d, [rbp+rax*8+47h+var_B8]
0x18004df5b  mov     r9b, [rbp+rax*8+47h+var_B4]
0x18004df60  jmp     short loc_18004DFC4
0x18004df62  test    r9b, r9b
0x18004df65  jnz     short loc_18004DF7B
0x18004df67  test    r12d, r12d
0x18004df6a  jnz     short loc_18004DFD5
0x18004df6c  lea     eax, [r14-2]
0x18004df70  test    eax, 0FFFFFFFDh
0x18004df75  jnz     loc_18004E0E7
0x18004df7b  test    r8b, r8b
0x18004df7e  jz      short loc_18004DF96
0x18004df80  mov     eax, edx
0x18004df82  add     rax, rax
0x18004df85  mov     qword ptr [r10+rax*8+8], 0
0x18004df8e  mov     dword ptr [r10+rax*8], 0
0x18004df96  lea     eax, [r14-3]
0x18004df9a  cmp     eax, 1
0x18004df9d  ja      short loc_18004DFC9
0x18004df9f  cmp     r15d, 8
0x18004dfa3  jnb     loc_18004E0E7
0x18004dfa9  mov     eax, r15d
0x18004dfac  add     rax, rax
0x18004dfaf  inc     r15d
0x18004dfb2  mov     [rbp+rax*8+47h+var_B4], r9b
0x18004dfb7  mov     r9b, 1
0x18004dfba  mov     [rbp+rax*8+47h+var_C0], rdi
0x18004dfbf  mov     [rbp+rax*8+47h+var_B8], r12d
0x18004dfc4  mov     [rsp+120h+var_100], r9b
0x18004dfc9  mov     eax, [rsp+120h+var_E4]
0x18004dfcd  inc     r13d
0x18004dfd0  jmp     loc_18004DEE5
0x18004dfd5  mov     rax, [r11+rax*8+8]
0x18004dfda  test    rax, rax
0x18004dfdd  jz      short loc_18004E008
0x18004dfdf  mov     dl, [rdi]
0x18004dfe1  jmp     short loc_18004DFEA
0x18004dfe3  cmp     cl, dl
0x18004dfe5  jz      short loc_18004E008
0x18004dfe7  inc     rax
0x18004dfea  mov     cl, [rax]
0x18004dfec  test    cl, cl
0x18004dfee  jnz     short loc_18004DFE3
0x18004dff0  lea     eax, [r14-2]
0x18004dff4  test    eax, 0FFFFFFFDh
0x18004dff9  jnz     loc_18004E0E7
0x18004dfff  mov     edx, [rsp+120h+var_FC]
0x18004e003  jmp     loc_18004DF7B
0x18004e008  lea     r9, [rsp+120h+var_D8]
0x18004e00d  mov     edx, r12d
0x18004e010  lea     r8, [rsp+120h+var_F8]
0x18004e015  mov     rcx, rdi
0x18004e018  call    MinAsn1ExtractContent
0x18004e01d  test    eax, eax
0x18004e01f  jle     loc_18004E0E7
0x18004e025  cmp     [rsp+120h+var_FF], 0
0x18004e02a  mov     r8d, [rsp+120h+var_F8]
0x18004e02f  mov     r9, [rsp+120h+var_D8]
0x18004e034  mov     r10, [rsp+120h+var_F0]
0x18004e039  lea     edx, [r8+rax]
0x18004e03d  jz      short loc_18004E08A
0x18004e03f  mov     eax, [rsp+120h+var_E8]
0x18004e043  bt      eax, 1Eh
0x18004e047  jnb     short loc_18004E076
0x18004e049  mov     ecx, [rsp+120h+var_FC]
0x18004e04d  add     rcx, rcx
0x18004e050  mov     [r10+rcx*8+8], r9
0x18004e055  mov     [r10+rcx*8], r8d
0x18004e059  cmp     byte ptr [rdi], 3
0x18004e05c  jnz     short loc_18004E08A
0x18004e05e  test    r8d, r8d
0x18004e061  jz      short loc_18004E08A
0x18004e063  lea     rax, [r9+1]
0x18004e067  mov     [r10+rcx*8+8], rax
0x18004e06c  lea     eax, [r8-1]
0x18004e070  mov     [r10+rcx*8], eax
0x18004e074  jmp     short loc_18004E08A
0x18004e076  test    eax, eax
0x18004e078  jns     short loc_18004E08A
0x18004e07a  mov     eax, [rsp+120h+var_FC]
0x18004e07e  add     rax, rax
0x18004e081  mov     [r10+rax*8+8], rdi
0x18004e086  mov     [r10+rax*8], edx
0x18004e08a  sub     r14d, 1
0x18004e08e  jz      short loc_18004E0DD
0x18004e090  sub     r14d, 1
0x18004e094  jz      short loc_18004E0DD
0x18004e096  sub     r14d, 1
0x18004e09a  jz      short loc_18004E0A2
0x18004e09c  cmp     r14d, 1
0x18004e0a0  jnz     short loc_18004E0E7
0x18004e0a2  cmp     r15d, 8
0x18004e0a6  jnb     short loc_18004E0E7
0x18004e0a8  sub     r12d, edx
0x18004e0ab  mov     ecx, r15d
0x18004e0ae  add     rcx, rcx
0x18004e0b1  mov     eax, edx
0x18004e0b3  add     rax, rdi
0x18004e0b6  mov     rdi, r9
0x18004e0b9  inc     r15d
0x18004e0bc  mov     [rbp+rcx*8+47h+var_B8], r12d
0x18004e0c1  mov     r12d, r8d
0x18004e0c4  mov     [rbp+rcx*8+47h+var_C0], rax
0x18004e0c9  mov     [rbp+rcx*8+47h+var_B4], 0
0x18004e0ce  mov     r9b, [rsp+120h+var_100]
0x18004e0d3  mov     r11, [rsp+120h+var_D0]
0x18004e0d8  jmp     loc_18004DFC9
0x18004e0dd  mov     eax, edx
0x18004e0df  add     rdi, rax
0x18004e0e2  sub     r12d, edx
0x18004e0e5  jmp     short loc_18004E0CE
0x18004e0e7  mov     rax, [rsp+120h+var_E0]
0x18004e0ec  sub     esi, edi
0x18004e0ee  dec     esi
0x18004e0f0  jmp     short loc_18004E0FB
0x18004e0f2  mov     rax, [rsp+120h+var_E0]
0x18004e0f7  sub     edi, esi
0x18004e0f9  mov     esi, edi
0x18004e0fb  mov     [rax], r13d
0x18004e0fe  mov     eax, esi
0x18004e100  mov     rcx, [rbp+47h+var_40]
0x18004e104  xor     rcx, rsp; StackCookie
0x18004e107  call    __security_check_cookie
0x18004e10c  add     rsp, 0F0h
0x18004e113  pop     r15
0x18004e115  pop     r14
0x18004e117  pop     r13
0x18004e119  pop     r12
0x18004e11b  pop     rdi
0x18004e11c  pop     rsi
0x18004e11d  pop     rbp
0x18004e11e  retn
```
