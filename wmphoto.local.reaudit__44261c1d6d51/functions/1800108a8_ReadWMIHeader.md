# ReadWMIHeader

- ea: `0x1800108a8`
- end: `0x180010e02`
- name: `ReadWMIHeader`
- size: `1370`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180007400`
- `0x18000f3b4`
- `0x18001022c`
- `0x1800102e0`

## callees

- `0x1800108a8`
- `0x18002d9a0`
- `0x18002dcdc`
- `0x18002f470`
- `0x18002f750`
- `0x180036420`
- `0x180045010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001091c`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001091c`

## pseudocode

```c
__int64 __fastcall ReadWMIHeader(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  int v7; // ebx
  unsigned int Bit32_SB; // ecx
  int v9; // r15d
  int v10; // eax
  int v11; // r13d
  int v12; // r12d
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  int v21; // ecx
  __int64 v22; // r15
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // r15
  unsigned int v27; // ebx
  int v28; // eax
  int v29; // r15d
  unsigned int v30; // ebx
  __int64 v31; // r11
  unsigned __int64 v32; // r9
  __int64 v33; // rbx
  unsigned __int64 v34; // r10
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // r8
  char v37; // al
  __int128 v39; // [rsp+20h] [rbp-40h] BYREF
  __int128 v40; // [rsp+30h] [rbp-30h]
  __int64 v41; // [rsp+40h] [rbp-20h]
  int v42; // [rsp+48h] [rbp-18h]
  char Str[8]; // [rsp+50h] [rbp-10h] BYREF

  v3 = *(_QWORD *)(a2 + 64);
  v41 = 0;
  *(_QWORD *)Str = 0;
  v39 = 0;
  v40 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, char *, __int64))(v3 + 64))(v3, Str, 8);
  if ( v7 >= 0 )
  {
    Str[7] = 0;
    if ( !strstr(Str, "WMPHOTO") )
    {
      v7 = -106;
      return (unsigned int)-(v7 != 0);
    }
    v7 = attach_SB(&v39, v3);
    if ( v7 < 0 )
      return (unsigned int)-(v7 != 0);
    if ( (unsigned int)getBit32_SB(&v39, 4) != 1
      || (*(_QWORD *)a3 = 1, *(_DWORD *)(a2 + 20) = getBit32_SB(&v39, 1), Bit32_SB = getBit32_SB(&v39, 3), Bit32_SB >= 2) )
    {
      v7 = -107;
LABEL_60:
      detach_SB(&v39);
      return (unsigned int)-(v7 != 0);
    }
    *(_DWORD *)(a2 + 24) = Bit32_SB == 1;
    v9 = getBit32_SB(&v39, 1);
    *(_DWORD *)(a2 + 32) = getBit32_SB(&v39, 1);
    *((_DWORD *)a1 + 29) = getBit32_SB(&v39, 3);
    *(_DWORD *)(a3 + 20) = getBit32_SB(&v39, 1);
    v10 = getBit32_SB(&v39, 2);
    if ( v10 == 3 )
    {
LABEL_9:
      v7 = -104;
      goto LABEL_60;
    }
    *(_DWORD *)(a2 + 16) = v10;
    v11 = getBit32_SB(&v39, 1);
    getBit32_SB(&v39, 1);
    *(_DWORD *)(a2 + 12) = 1;
    v42 = getBit32_SB(&v39, 1);
    *(_DWORD *)(a3 + 24) = getBit32_SB(&v39, 1);
    if ( *(_DWORD *)(a2 + 24) )
    {
      getBit32_SB(&v39, 1);
      *((_DWORD *)a1 + 11) = getBit32_SB(&v39, 1);
      v12 = 0;
      v13 = getBit32_SB(&v39, 1);
    }
    else
    {
      v12 = getBit32_SB(&v39, 1);
      getBit32_SB(&v39, 2);
      v13 = 0;
      *((_DWORD *)a1 + 11) = 0;
    }
    *((_DWORD *)a1 + 12) = v13;
    v14 = getBit32_SB(&v39, 1);
    *(_DWORD *)(a3 + 12) = v14;
    if ( !v14 )
      *((_DWORD *)a1 + 12) = 0;
    *(_DWORD *)(a2 + 32872) = *(_DWORD *)(a3 + 12);
    v15 = getBit32_SB(&v39, 4);
    *((_DWORD *)a1 + 4) = v15;
    if ( v15 == 4 || v15 <= 0 || (unsigned int)(v15 - 6) <= 2 )
    {
      v16 = getBit32_SB(&v39, 4);
      *((_DWORD *)a1 + 5) = v16;
      if ( v16 >= 11 )
      {
        if ( v16 != 15 )
          goto LABEL_20;
        *((_DWORD *)a1 + 5) = 0;
        *(_DWORD *)(a2 + 32860) = 1;
      }
      v17 = v11 != 0 ? 0xFFFFFFF0 : 0;
      *a1 = (unsigned int)getBit32_SB(&v39, v17 + 32) + 1;
      a1[1] = (unsigned int)getBit32_SB(&v39, v17 + 32) + 1;
      *(_QWORD *)(a3 + 64) = 0;
      *(_QWORD *)(a3 + 56) = 0;
      *(_QWORD *)(a3 + 48) = 0;
      *(_QWORD *)(a3 + 40) = 0;
      if ( !v42 )
      {
        if ( (*a1 & 0xF) != 0 )
          *(_QWORD *)(a3 + 64) = 16 - (*a1 & 0xF);
        if ( (a1[1] & 0xF) != 0 )
          *(_QWORD *)(a3 + 56) = 16 - (a1[1] & 0xF);
      }
      *(_DWORD *)(a2 + 16468) = 0;
      *(_DWORD *)(a2 + 80) = 0;
      if ( v9 )
      {
        v18 = getBit32_SB(&v39, 12);
        *(_DWORD *)(a2 + 80) = v18;
        v19 = v18;
        v20 = getBit32_SB(&v39, 12);
        *(_DWORD *)(a2 + 16468) = v20;
        v21 = v19;
      }
      else
      {
        v19 = 0;
        v20 = 0;
        v21 = 0;
      }
      if ( *(_DWORD *)(a3 + 20) || *(_DWORD *)(a2 + 32) != 1 && !(v19 + v20) )
      {
        *(_DWORD *)(a2 + 16472) = 0;
        LODWORD(v22) = 0;
        *(_DWORD *)(a2 + 84) = 0;
        if ( v21 )
        {
          while ( DWORD2(v39) < 0x4100 )
          {
            v23 = *(_DWORD *)(a2 + 4LL * (unsigned int)v22 + 84);
            v24 = getBit32_SB(&v39, v11 != 0 ? 8 : 16);
            v22 = (unsigned int)(v22 + 1);
            *(_DWORD *)(a2 + 4 * v22 + 84) = v24 + v23;
            if ( v24 + v23 <= v23 )
              break;
            if ( (unsigned int)v22 >= *(_DWORD *)(a2 + 80) )
              goto LABEL_38;
          }
        }
        else
        {
LABEL_38:
          v25 = *(_DWORD *)(a2 + 16468);
          LODWORD(v26) = 0;
          if ( v25 )
          {
            while ( DWORD2(v39) < 0x4100 )
            {
              v27 = *(_DWORD *)(a2 + 4LL * (unsigned int)v26 + 16472);
              v28 = getBit32_SB(&v39, v11 != 0 ? 8 : 16);
              v26 = (unsigned int)(v26 + 1);
              *(_DWORD *)(a2 + 4 * v26 + 16472) = v28 + v27;
              if ( v28 + v27 <= v27 )
                break;
              v25 = *(_DWORD *)(a2 + 16468);
              if ( (unsigned int)v26 >= v25 )
                goto LABEL_42;
            }
          }
          else
          {
LABEL_42:
            if ( v12 && (v29 = 0, (v30 = (v25 + 1) * (*(_DWORD *)(a2 + 80) + 1)) != 0) )
            {
              while ( DWORD2(v39) < 0x4100 )
              {
                getBit32_SB(&v39, 8);
                if ( ++v29 >= v30 )
                  goto LABEL_46;
              }
            }
            else
            {
LABEL_46:
              if ( v42 )
              {
                *(_QWORD *)(a3 + 40) = (unsigned __int8)getBit32_SB(&v39, 6);
                *(_QWORD *)(a3 + 48) = (unsigned __int8)getBit32_SB(&v39, 6);
                *(_QWORD *)(a3 + 56) = (unsigned __int8)getBit32_SB(&v39, 6);
                *(_QWORD *)(a3 + 64) = (unsigned __int8)getBit32_SB(&v39, 6);
              }
              v31 = *(_QWORD *)(a3 + 48);
              v32 = *(_QWORD *)(a3 + 64);
              v33 = *(_QWORD *)(a3 + 40);
              v34 = *(_QWORD *)(a3 + 56);
              v35 = *a1;
              v36 = a1[1];
              if ( (((unsigned __int8)*a1 + (_BYTE)v32 + (_BYTE)v31) & 0xF)
                 + (unsigned __int64)(((_BYTE)v36 + (_BYTE)v34 + (_BYTE)v33) & 0xF) )
              {
                if ( v31 + v33 + (a1[1] & 0xF) + (*a1 & 0xF) || v35 <= v32 || v36 <= v34 )
                  goto LABEL_9;
                *a1 = v35 - v32;
                a1[1] = v36 - *(_QWORD *)(a3 + 56);
              }
              BYTE12(v39) = 0;
              LODWORD(v40) = 0;
              if ( !(unsigned int)ReadImagePlaneHeader(a1, a2, a3, &v39) )
              {
                v7 = 0;
                *(_QWORD *)(a2 + 72) = (unsigned int)-DWORD2(v39);
                if ( *(_DWORD *)(a3 + 12) )
                  v37 = *(_BYTE *)(a2 + 48);
                else
                  v37 = 0;
                *(_BYTE *)(a2 + 48) = v37;
                *(_QWORD *)(a2 + 40) = *(_QWORD *)(a3 + 32);
                if ( (unsigned int)(*((_DWORD *)a1 + 5) - 8) <= 2 && *(_DWORD *)(a2 + 8) > 3u )
                  v7 = -1;
                goto LABEL_60;
              }
            }
          }
        }
      }
    }
LABEL_20:
    v7 = -106;
    goto LABEL_60;
  }
  return (unsigned int)-(v7 != 0);
}

```

## disassembly

```asm
0x1800108a8  mov     [rsp-38h+arg_18], rbx
0x1800108ad  push    rbp
0x1800108ae  push    rsi
0x1800108af  push    rdi
0x1800108b0  push    r12
0x1800108b2  push    r13
0x1800108b4  push    r14
0x1800108b6  push    r15
0x1800108b8  mov     rbp, rsp
0x1800108bb  sub     rsp, 60h
0x1800108bf  mov     rax, cs:__security_cookie
0x1800108c6  xor     rax, rsp
0x1800108c9  mov     [rbp+var_8], rax
0x1800108cd  mov     r15, [rdx+40h]
0x1800108d1  xor     eax, eax
0x1800108d3  xorps   xmm0, xmm0
0x1800108d6  mov     [rbp+var_20], rax
0x1800108da  mov     rsi, r8
0x1800108dd  mov     qword ptr [rbp+Str], rax
0x1800108e1  mov     rdi, rdx
0x1800108e4  mov     r14, rcx
0x1800108e7  lea     r8d, [rax+8]
0x1800108eb  mov     rcx, r15
0x1800108ee  movups  [rbp+var_40], xmm0
0x1800108f2  lea     rdx, [rbp+Str]
0x1800108f6  movups  [rbp+var_30], xmm0
0x1800108fa  mov     rax, [r15+40h]
0x1800108fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010903  mov     ebx, eax
0x180010905  test    eax, eax
0x180010907  js      loc_180010DD5
0x18001090d  lea     rdx, SubStr; "WMPHOTO"
0x180010914  mov     [rbp+Str+7], 0
0x180010918  lea     rcx, [rbp+Str]; Str
0x18001091c  call    cs:__imp_strstr
0x180010923  nop     dword ptr [rax+rax+00h]
0x180010928  test    rax, rax
0x18001092b  jnz     short loc_180010935
0x18001092d  lea     ebx, [rax-6Ah]
0x180010930  jmp     loc_180010DD5
0x180010935  mov     rdx, r15
0x180010938  lea     rcx, [rbp+var_40]
0x18001093c  call    attach_SB
0x180010941  mov     ebx, eax
0x180010943  test    eax, eax
0x180010945  js      loc_180010DD5
0x18001094b  mov     edx, 4
0x180010950  lea     rcx, [rbp+var_40]
0x180010954  call    getBit32_SB
0x180010959  mov     ebx, 1
0x18001095e  cmp     eax, ebx
0x180010960  jz      short loc_18001096C
0x180010962  mov     ebx, 0FFFFFF95h
0x180010967  jmp     loc_180010DCC
0x18001096c  mov     edx, ebx
0x18001096e  mov     [rsi], rbx
0x180010971  lea     rcx, [rbp+var_40]
0x180010975  call    getBit32_SB
0x18001097a  mov     r12d, 3
0x180010980  mov     [rdi+14h], eax
0x180010983  mov     edx, r12d
0x180010986  lea     rcx, [rbp+var_40]
0x18001098a  call    getBit32_SB
0x18001098f  mov     ecx, eax
0x180010991  cmp     eax, 2
0x180010994  jnb     short loc_180010962
0x180010996  xor     eax, eax
0x180010998  mov     edx, ebx
0x18001099a  cmp     ecx, ebx
0x18001099c  lea     rcx, [rbp+var_40]
0x1800109a0  setz    al
0x1800109a3  mov     [rdi+18h], eax
0x1800109a6  call    getBit32_SB
0x1800109ab  mov     edx, ebx
0x1800109ad  lea     rcx, [rbp+var_40]
0x1800109b1  mov     r15d, eax
0x1800109b4  call    getBit32_SB
0x1800109b9  mov     edx, r12d
0x1800109bc  mov     [rdi+20h], eax
0x1800109bf  lea     rcx, [rbp+var_40]
0x1800109c3  call    getBit32_SB
0x1800109c8  mov     edx, ebx
0x1800109ca  mov     [r14+74h], eax
0x1800109ce  lea     rcx, [rbp+var_40]
0x1800109d2  call    getBit32_SB
0x1800109d7  lea     edx, [r12-1]
0x1800109dc  mov     [rsi+14h], eax
0x1800109df  lea     rcx, [rbp+var_40]
0x1800109e3  call    getBit32_SB
0x1800109e8  cmp     eax, r12d
0x1800109eb  jnz     short loc_1800109F7
0x1800109ed  mov     ebx, 0FFFFFF98h
0x1800109f2  jmp     loc_180010DCC
0x1800109f7  mov     edx, ebx
0x1800109f9  mov     [rdi+10h], eax
0x1800109fc  lea     rcx, [rbp+var_40]
0x180010a00  call    getBit32_SB
0x180010a05  mov     edx, ebx
0x180010a07  lea     rcx, [rbp+var_40]
0x180010a0b  mov     r13d, eax
0x180010a0e  call    getBit32_SB
0x180010a13  mov     edx, ebx
0x180010a15  mov     [rdi+0Ch], ebx
0x180010a18  lea     rcx, [rbp+var_40]
0x180010a1c  call    getBit32_SB
0x180010a21  mov     edx, ebx
0x180010a23  mov     [rbp+var_18], eax
0x180010a26  lea     rcx, [rbp+var_40]
0x180010a2a  call    getBit32_SB
0x180010a2f  mov     [rsi+18h], eax
0x180010a32  lea     rcx, [rbp+var_40]
0x180010a36  cmp     dword ptr [rdi+18h], 0
0x180010a3a  mov     edx, ebx
0x180010a3c  jz      short loc_180010A62
0x180010a3e  call    getBit32_SB
0x180010a43  mov     edx, ebx
0x180010a45  lea     rcx, [rbp+var_40]
0x180010a49  call    getBit32_SB
0x180010a4e  mov     edx, ebx
0x180010a50  mov     [r14+2Ch], eax
0x180010a54  lea     rcx, [rbp+var_40]
0x180010a58  xor     r12d, r12d
0x180010a5b  call    getBit32_SB
0x180010a60  jmp     short loc_180010A82
0x180010a62  call    getBit32_SB
0x180010a67  mov     edx, 2
0x180010a6c  lea     rcx, [rbp+var_40]
0x180010a70  mov     r12d, eax
0x180010a73  call    getBit32_SB
0x180010a78  xor     eax, eax
0x180010a7a  mov     dword ptr [r14+2Ch], 0
0x180010a82  mov     edx, ebx
0x180010a84  mov     [r14+30h], eax
0x180010a88  lea     rcx, [rbp+var_40]
0x180010a8c  call    getBit32_SB
0x180010a91  mov     [rsi+0Ch], eax
0x180010a94  test    eax, eax
0x180010a96  jnz     short loc_180010A9C
0x180010a98  mov     [r14+30h], eax
0x180010a9c  mov     eax, [rsi+0Ch]
0x180010a9f  lea     rcx, [rbp+var_40]
0x180010aa3  mov     edx, 4
0x180010aa8  mov     [rdi+8068h], eax
0x180010aae  call    getBit32_SB
0x180010ab3  mov     [r14+10h], eax
0x180010ab7  cmp     eax, 4
0x180010aba  jz      short loc_180010AC8
0x180010abc  test    eax, eax
0x180010abe  jle     short loc_180010AC8
0x180010ac0  add     eax, 0FFFFFFFAh
0x180010ac3  cmp     eax, 2
0x180010ac6  ja      short loc_180010AE4
0x180010ac8  mov     edx, 4
0x180010acd  lea     rcx, [rbp+var_40]
0x180010ad1  call    getBit32_SB
0x180010ad6  mov     [r14+14h], eax
0x180010ada  cmp     eax, 0Bh
0x180010add  jl      short loc_180010AEE
0x180010adf  cmp     eax, 0Fh
0x180010ae2  jz      short loc_180010AF3
0x180010ae4  mov     ebx, 0FFFFFF96h
0x180010ae9  jmp     loc_180010DCC
0x180010aee  cmp     eax, 0Fh
0x180010af1  jnz     short loc_180010B01
0x180010af3  mov     dword ptr [r14+14h], 0
0x180010afb  mov     [rdi+805Ch], ebx
0x180010b01  mov     eax, r13d
0x180010b04  lea     rcx, [rbp+var_40]
0x180010b08  neg     eax
0x180010b0a  sbb     ebx, ebx
0x180010b0c  and     ebx, 0FFFFFFF0h
0x180010b0f  lea     edx, [rbx+20h]
0x180010b12  call    getBit32_SB
0x180010b17  inc     eax
0x180010b19  lea     edx, [rbx+20h]
0x180010b1c  lea     rcx, [rbp+var_40]
0x180010b20  mov     [r14], rax
0x180010b23  call    getBit32_SB
0x180010b28  xor     edx, edx
0x180010b2a  inc     eax
0x180010b2c  mov     [r14+8], rax
0x180010b30  mov     [rsi+40h], rdx
0x180010b34  mov     [rsi+38h], rdx
0x180010b38  mov     [rsi+30h], rdx
0x180010b3c  mov     [rsi+28h], rdx
0x180010b40  cmp     [rbp+var_18], edx
0x180010b43  jnz     short loc_180010B6C
0x180010b45  mov     rcx, [r14]
0x180010b48  and     ecx, 0Fh
0x180010b4b  jz      short loc_180010B57
0x180010b4d  lea     eax, [rdx+10h]
0x180010b50  sub     rax, rcx
0x180010b53  mov     [rsi+40h], rax
0x180010b57  mov     rcx, [r14+8]
0x180010b5b  and     ecx, 0Fh
0x180010b5e  jz      short loc_180010B6C
0x180010b60  mov     eax, 10h
0x180010b65  sub     rax, rcx
0x180010b68  mov     [rsi+38h], rax
0x180010b6c  mov     [rdi+4054h], edx
0x180010b72  mov     [rdi+50h], edx
0x180010b75  test    r15d, r15d
0x180010b78  jz      short loc_180010BA9
0x180010b7a  mov     r15d, 0Ch
0x180010b80  lea     rcx, [rbp+var_40]
0x180010b84  mov     edx, r15d
0x180010b87  call    getBit32_SB
0x180010b8c  mov     edx, r15d
0x180010b8f  mov     [rdi+50h], eax
0x180010b92  lea     rcx, [rbp+var_40]
0x180010b96  mov     ebx, eax
0x180010b98  call    getBit32_SB
0x180010b9d  mov     [rdi+4054h], eax
0x180010ba3  mov     ecx, ebx
0x180010ba5  xor     edx, edx
0x180010ba7  jmp     short loc_180010BAF
0x180010ba9  mov     ebx, edx
0x180010bab  mov     eax, edx
0x180010bad  mov     ecx, edx
0x180010baf  cmp     [rsi+14h], edx
0x180010bb2  jnz     short loc_180010BC6
0x180010bb4  cmp     dword ptr [rdi+20h], 1
0x180010bb8  jz      loc_180010AE4
0x180010bbe  add     eax, ebx
0x180010bc0  jnz     loc_180010AE4
0x180010bc6  mov     [rdi+4058h], edx
0x180010bcc  mov     r15d, edx
0x180010bcf  mov     [rdi+54h], edx
0x180010bd2  test    ecx, ecx
0x180010bd4  jz      short loc_180010C1B
0x180010bd6  cmp     dword ptr [rbp+var_40+8], 4100h
0x180010bdd  jnb     loc_180010AE4
0x180010be3  mov     eax, r15d
0x180010be6  lea     rcx, [rbp+var_40]
0x180010bea  mov     ebx, [rdi+rax*4+54h]
0x180010bee  mov     eax, r13d
0x180010bf1  neg     eax
0x180010bf3  sbb     edx, edx
0x180010bf5  and     edx, 0FFFFFFF8h
0x180010bf8  add     edx, 10h
0x180010bfb  call    getBit32_SB
0x180010c00  inc     r15d
0x180010c03  lea     ecx, [rax+rbx]
0x180010c06  mov     [rdi+r15*4+54h], ecx
0x180010c0b  cmp     ecx, ebx
0x180010c0d  jbe     loc_180010AE4
0x180010c13  cmp     r15d, [rdi+50h]
0x180010c17  jb      short loc_180010BD6
0x180010c19  xor     edx, edx
0x180010c1b  mov     eax, [rdi+4054h]
0x180010c21  mov     r15d, edx
0x180010c24  test    eax, eax
0x180010c26  jz      short loc_180010C78
0x180010c28  cmp     dword ptr [rbp+var_40+8], 4100h
0x180010c2f  jnb     loc_180010AE4
0x180010c35  mov     eax, r15d
0x180010c38  lea     rcx, [rbp+var_40]
0x180010c3c  mov     ebx, [rdi+rax*4+4058h]
0x180010c43  mov     eax, r13d
0x180010c46  neg     eax
0x180010c48  sbb     edx, edx
0x180010c4a  and     edx, 0FFFFFFF8h
0x180010c4d  add     edx, 10h
0x180010c50  call    getBit32_SB
0x180010c55  inc     r15d
0x180010c58  lea     ecx, [rax+rbx]
0x180010c5b  mov     [rdi+r15*4+4058h], ecx
0x180010c63  cmp     ecx, ebx
0x180010c65  jbe     loc_180010AE4
0x180010c6b  mov     eax, [rdi+4054h]
0x180010c71  cmp     r15d, eax
0x180010c74  jb      short loc_180010C28
0x180010c76  xor     edx, edx
0x180010c78  test    r12d, r12d
0x180010c7b  jz      short loc_180010CB3
0x180010c7d  mov     ebx, [rdi+50h]
0x180010c80  mov     r15d, edx
0x180010c83  inc     ebx
0x180010c85  inc     eax
0x180010c87  imul    ebx, eax
0x180010c8a  test    ebx, ebx
0x180010c8c  jz      short loc_180010CB3
0x180010c8e  cmp     dword ptr [rbp+var_40+8], 4100h
0x180010c95  jnb     loc_180010AE4
0x180010c9b  mov     edx, 8
0x180010ca0  lea     rcx, [rbp+var_40]
0x180010ca4  call    getBit32_SB
0x180010ca9  inc     r15d
0x180010cac  cmp     r15d, ebx
0x180010caf  jb      short loc_180010C8E
0x180010cb1  xor     edx, edx
0x180010cb3  cmp     [rbp+var_18], edx
0x180010cb6  jz      short loc_180010D05
0x180010cb8  mov     ebx, 6
0x180010cbd  lea     rcx, [rbp+var_40]
0x180010cc1  mov     edx, ebx
0x180010cc3  call    getBit32_SB
0x180010cc8  movzx   ecx, al
0x180010ccb  mov     edx, ebx
0x180010ccd  mov     [rsi+28h], rcx
  ... truncated ...
```
