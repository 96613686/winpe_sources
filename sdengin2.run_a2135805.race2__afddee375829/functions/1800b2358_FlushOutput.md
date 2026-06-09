# FlushOutput

- ea: `0x1800b2358`
- end: `0x1800b2a02`
- name: `FlushOutput`
- size: `1706`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800b205c`
- `0x1800b31d4`

## callees

- `0x1800af958`
- `0x1800b2358`
- `0x1800d1010`

## import_xrefs

- `msvcrt!free` at `0x1800b2838`
- `msvcrt!free` at `0x1800b2899`
- `msvcrt!free` at `0x1800b2972`
- `msvcrt!free` at `0x1800b2838`
- `msvcrt!free` at `0x1800b2899`
- `msvcrt!free` at `0x1800b2972`
- `msvcrt!malloc` at `0x1800b2695`
- `msvcrt!malloc` at `0x1800b2695`
- `KERNEL32!WriteFile` at `0x1800b24d5`
- `KERNEL32!WriteFile` at `0x1800b2537`
- `KERNEL32!WriteFile` at `0x1800b24d5`
- `KERNEL32!WriteFile` at `0x1800b2537`

## pseudocode

```c
__int64 __fastcall FlushOutput(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rax
  _BYTE *v5; // r9
  __int64 v6; // r15
  __int64 v7; // rcx
  _QWORD *v8; // r8
  unsigned __int8 *v9; // r11
  int i; // r10d
  __int64 v11; // rax
  unsigned int v12; // r14d
  unsigned int *v13; // r14
  __int64 v14; // r12
  int v15; // esi
  void *v16; // rcx
  unsigned int *v17; // rdx
  DWORD v18; // r8d
  unsigned int v19; // r12d
  DWORD v20; // esi
  DWORD v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r10
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  unsigned int v31; // r12d
  char *v32; // rax
  char *v33; // rsi
  __int64 v34; // r8
  char *v35; // rcx
  unsigned int v36; // edx
  char v37; // al
  char *v38; // r10
  __int64 v39; // rcx
  __int64 v40; // rdx
  signed __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r9
  void (__fastcall *v45)(__int64, char *, unsigned int *, __int64, int, int, int, __int64, int *); // rax
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // r9
  void (__fastcall *v50)(__int64, char *, unsigned int *, __int64, int, int, int, __int64, int *); // rax
  __int64 v51; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-48h]
  int lpOverlappeda; // [rsp+20h] [rbp-48h]
  int v54; // [rsp+28h] [rbp-40h]
  int v55; // [rsp+28h] [rbp-40h]
  int v56; // [rsp+30h] [rbp-38h]
  int v57; // [rsp+30h] [rbp-38h]
  __int64 v58; // [rsp+38h] [rbp-30h]
  __int64 v59; // [rsp+38h] [rbp-30h]
  char *v60; // [rsp+50h] [rbp-18h]
  signed __int64 v61; // [rsp+58h] [rbp-10h]
  unsigned int v62; // [rsp+B0h] [rbp+48h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v64; // [rsp+C0h] [rbp+58h] BYREF
  int v65; // [rsp+C8h] [rbp+60h] BYREF

  NumberOfBytesWritten = 0;
  v65 = 0;
  v64 = 0;
  if ( *(_DWORD *)(a1 + 72186) )
  {
    *(_DWORD *)(a1 + 72170) += *(_DWORD *)(a1 + 72174);
    *(_QWORD *)(a1 + 71894) = *(_QWORD *)(a1 + 71886);
    *(_DWORD *)(a1 + 72174) = 0;
    return 50;
  }
  v4 = *(unsigned int *)(a1 + 72174);
  if ( !(_DWORD)v4 )
    return 0;
  v5 = (_BYTE *)*(unsigned int *)(a1 + 40);
  v6 = (unsigned int)v4;
  if ( !(_DWORD)v5 && !*(_DWORD *)(a1 + 48) )
  {
    a2 = *(_QWORD *)(a1 + 4616);
    v7 = *(_QWORD *)(a1 + 4896);
    if ( a2 + v4 > v7 )
      v6 = v7 - a2;
  }
  if ( v6 <= 0 )
  {
    *(_DWORD *)a1 = 1;
    if ( (_DWORD)v5 && !*(_DWORD *)(a1 + 48) )
      *(_DWORD *)(a1 + 72186) = 2;
    else
      *(_DWORD *)(a1 + 24) = 1;
LABEL_117:
    v8 = (_QWORD *)(a1 + 71886);
    goto LABEL_118;
  }
  a2 = *(unsigned int *)(a1 + 71228);
  v8 = (_QWORD *)(a1 + 71886);
  v9 = *(unsigned __int8 **)(a1 + 71886);
  for ( i = v6; i; --i )
  {
    v11 = *v9++;
    a2 = *((_DWORD *)crc_32_tab + (v11 ^ (unsigned __int8)a2)) ^ ((unsigned int)a2 >> 8);
  }
  *(_DWORD *)(a1 + 71228) = a2;
  if ( *(_DWORD *)(a1 + 4604) )
  {
    if ( !(_DWORD)v5 )
      goto LABEL_61;
    goto LABEL_41;
  }
  if ( (_DWORD)v5 )
  {
LABEL_41:
    if ( !*(_DWORD *)(a1 + 44) )
    {
      v23 = *(_QWORD *)(a1 + 108);
      v24 = *(_QWORD *)(a1 + 4896);
      v5 = (_BYTE *)(*(_QWORD *)(a1 + 100) + *(_QWORD *)(a1 + 92));
      v25 = *(_QWORD *)(a1 + 71902);
      if ( v23 + v24 >= *(_QWORD *)(a1 + 76) )
        a2 = *(_QWORD *)(a1 + 76);
      else
        a2 = v24 + v23 - *(_QWORD *)(a1 + 84);
      while ( v6 > 0 )
      {
        v26 = *(_QWORD *)(a1 + 116);
        if ( v26 < *(_QWORD *)(a1 + 84) )
        {
          v29 = *(unsigned int *)(a1 + 5066);
          v30 = v26 + 1;
          *(_QWORD *)(a1 + 116) = v30;
          if ( v30 >= v29 )
            goto LABEL_59;
          v28 = v25;
          --v6;
          v25 = 1;
        }
        else
        {
          v27 = *(_QWORD *)(a1 + 100);
          if ( v27 >= *(_QWORD *)(a1 + 76) )
          {
LABEL_39:
            result = 50;
            goto LABEL_72;
          }
          if ( v27 >= a2 )
          {
LABEL_59:
            *(_DWORD *)(a1 + 72186) = 3;
            return 2;
          }
          if ( *(_DWORD *)(a1 + 5040) == 0x4000 && *(_BYTE *)v25 == 10 )
          {
            *v5 = 13;
            if ( a2 < *(_QWORD *)(a1 + 76) )
            {
              ++*(_QWORD *)(a1 + 108);
              ++a2;
            }
            if ( ++*(_QWORD *)(a1 + 100) >= a2 )
              goto LABEL_59;
            ++v5;
          }
          *v5++ = *(_BYTE *)v25;
          ++*(_QWORD *)(a1 + 100);
          v28 = 1;
          --v6;
        }
        v25 += v28;
      }
      goto LABEL_118;
    }
LABEL_61:
    if ( *(_DWORD *)(a1 + 48) || *(_DWORD *)(a1 + 44) )
      goto LABEL_63;
LABEL_118:
    *(_DWORD *)(a1 + 72170) += *(_DWORD *)(a1 + 72174);
    *(_QWORD *)(a1 + 71894) = *v8;
    *(_DWORD *)(a1 + 72174) = 0;
    if ( *(_DWORD *)(a1 + 40) )
    {
      v51 = *(_QWORD *)(a1 + 100);
LABEL_120:
      *(_QWORD *)(a1 + 4616) = v51;
LABEL_127:
      SendPercent(v51, a2, v8, v5);
      return 0;
    }
    if ( *(_DWORD *)(a1 + 48) )
    {
      if ( *(_DWORD *)(a1 + 44) )
      {
        v51 = *(_QWORD *)(a1 + 100);
        *(_QWORD *)(a1 + 68) = v51;
        goto LABEL_120;
      }
      *(_QWORD *)(a1 + 4616) += v6;
      *(_QWORD *)(a1 + 68) += v6;
    }
    else
    {
      *(_QWORD *)(a1 + 4616) += v6;
    }
    v51 = *(_QWORD *)(a1 + 4616);
    goto LABEL_127;
  }
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v12 = 0x4000;
    if ( *(_DWORD *)(a1 + 5040) == 0x4000 )
    {
      v13 = *(unsigned int **)(a1 + 71902);
      v14 = v6;
      v15 = 0;
      LOWORD(v62) = 2573;
      do
      {
        if ( v15 )
          break;
        v16 = *(void **)(a1 + 72178);
        v15 = 0;
        if ( *(_BYTE *)v13 == 10 )
        {
          ++*(_QWORD *)(a1 + 108);
          v17 = &v62;
          v18 = 2;
        }
        else
        {
          v18 = 1;
          v17 = v13;
        }
        if ( !WriteFile(v16, v17, v18, &NumberOfBytesWritten, 0) || !NumberOfBytesWritten )
          v15 = 1;
        v13 = (unsigned int *)((char *)v13 + 1);
        --v14;
      }
      while ( v14 > 0 );
    }
    else
    {
      v19 = 0;
      v20 = v6;
      while ( v20 )
      {
        v21 = v20;
        if ( v12 <= v20 )
          v21 = v12;
        v12 = v21;
        if ( !WriteFile(
                *(HANDLE *)(a1 + 72178),
                (LPCVOID)(*(_QWORD *)(a1 + 71902) + v19),
                v21,
                &NumberOfBytesWritten,
                0)
          || (v22 = 1, NumberOfBytesWritten != v12) )
        {
          v22 = 0;
        }
        v20 -= v12;
        v19 += v12;
        if ( !v22 )
        {
          if ( *(_DWORD *)(a1 + 4592) )
            goto LABEL_117;
          goto LABEL_39;
        }
      }
    }
    goto LABEL_117;
  }
LABEL_63:
  v31 = v6;
  v65 = 3;
  if ( *(_DWORD *)(a1 + 5040) != 0x4000 )
  {
    v38 = *(char **)(a1 + 71902);
    v33 = 0;
    v60 = v38;
LABEL_74:
    if ( *(_DWORD *)(a1 + 44) )
    {
      v39 = *(_QWORD *)(a1 + 108);
      v40 = *(_QWORD *)(a1 + 4896);
      if ( v39 + v40 >= *(_QWORD *)(a1 + 76) )
        v41 = *(_QWORD *)(a1 + 76);
      else
        v41 = v40 + v39 - *(_QWORD *)(a1 + 84);
      a2 = 0;
      v61 = v41;
      v62 = 0;
      while ( !(_DWORD)a2 && v31 )
      {
        v42 = *(_QWORD *)(a1 + 116);
        if ( v42 < *(_QWORD *)(a1 + 84) )
        {
          v47 = v42 + 1;
          v48 = *(unsigned int *)(a1 + 5066);
          *(_QWORD *)(a1 + 116) = v47;
          if ( v47 >= v48 )
            goto LABEL_92;
          --v31;
          v60 = ++v38;
        }
        else
        {
          v43 = *(_QWORD *)(a1 + 100);
          if ( v43 >= *(_QWORD *)(a1 + 76) )
          {
            *(_DWORD *)(a1 + 72186) = 2;
            if ( *(_DWORD *)(a1 + 5040) == 0x4000 && v33 )
              free(v33);
            return 50;
          }
          if ( v43 + v31 > v41 )
          {
            v65 = 0;
            v31 = v41 - v43;
          }
          v44 = *(unsigned int *)(a1 + 60);
          v45 = *(void (__fastcall **)(__int64, char *, unsigned int *, __int64, int, int, int, __int64, int *))(a1 + 4960);
          v58 = *(_QWORD *)(a1 + 4968);
          v56 = HIDWORD(*(_QWORD *)(a1 + 68));
          v54 = *(_DWORD *)(a1 + 68);
          lpOverlapped = HIDWORD(*(_QWORD *)(a1 + 60));
          v64 = v31;
          v45(1, v38, &v64, v44, lpOverlapped, v54, v56, v58, &v65);
          v46 = v64;
          v38 = v60;
          *(_QWORD *)(a1 + 100) += (int)v64;
          if ( (unsigned int)v46 >= v31 )
          {
            a2 = 1;
            v62 = 1;
          }
          else
          {
            a2 = v62;
            v38 = &v60[v46];
            v60 += v46;
            v31 -= v46;
          }
          if ( v65 )
          {
            if ( v65 == 1 )
              goto LABEL_92;
            if ( v65 != 3 )
              goto LABEL_91;
          }
          else
          {
            a2 = 1;
            v62 = 1;
          }
        }
        v41 = v61;
      }
    }
    else
    {
      a2 = 0;
LABEL_103:
      v62 = a2;
      while ( !(_DWORD)a2 && v31 )
      {
        v49 = *(unsigned int *)(a1 + 60);
        v50 = *(void (__fastcall **)(__int64, char *, unsigned int *, __int64, int, int, int, __int64, int *))(a1 + 4960);
        v59 = *(_QWORD *)(a1 + 4968);
        v57 = HIDWORD(*(_QWORD *)(a1 + 68));
        v55 = *(_DWORD *)(a1 + 68);
        lpOverlappeda = HIDWORD(*(_QWORD *)(a1 + 60));
        v64 = v31;
        v50(1, v38, &v64, v49, lpOverlappeda, v55, v57, v59, &v65);
        v38 = v60;
        if ( v64 >= v31 )
        {
          a2 = 1;
          v62 = 1;
        }
        else
        {
          a2 = v62;
          v38 = &v60[v64];
          v60 = v38;
          v31 -= v64;
        }
        if ( !v65 )
        {
          a2 = 1;
          goto LABEL_103;
        }
        if ( v65 == 1 )
          goto LABEL_92;
        if ( v65 != 3 )
        {
LABEL_91:
          *(_DWORD *)a1 = 1;
LABEL_92:
          *(_DWORD *)(a1 + 72186) = 3;
          if ( *(_DWORD *)(a1 + 5040) == 0x4000 && v33 )
            free(v33);
          return 2;
        }
      }
    }
    if ( *(_DWORD *)(a1 + 5040) == 0x4000 && v33 )
      free(v33);
    goto LABEL_117;
  }
  v32 = (char *)malloc(2 * (int)v6);
  v33 = v32;
  if ( v32 )
  {
    if ( (int)v6 > 0 )
    {
      v34 = *(_QWORD *)(a1 + 71902);
      v35 = v32;
      v36 = 0;
      do
      {
        if ( *(_BYTE *)(v36 + v34) == 10 )
        {
          ++*(_QWORD *)(a1 + 108);
          *v35++ = 13;
          ++v31;
        }
        v37 = *(_BYTE *)(v36++ + v34);
        *v35++ = v37;
      }
      while ( (int)v36 < (int)v6 );
    }
    v38 = v33;
    v60 = v33;
    goto LABEL_74;
  }
  result = 4;
LABEL_72:
  *(_DWORD *)(a1 + 72186) = 2;
  return result;
}

```

## disassembly

```asm
0x1800b2358  push    rbp
0x1800b235a  push    rbx
0x1800b235b  push    rsi
0x1800b235c  push    rdi
0x1800b235d  push    r12
0x1800b235f  push    r13
0x1800b2361  push    r14
0x1800b2363  push    r15
0x1800b2365  mov     rbp, rsp
0x1800b2368  sub     rsp, 68h
0x1800b236c  xor     r11d, r11d
0x1800b236f  mov     rbx, rcx
0x1800b2372  mov     [rbp+NumberOfBytesWritten], r11d
0x1800b2376  mov     [rbp+arg_18], r11d
0x1800b237a  mov     [rbp+arg_10], r11d
0x1800b237e  cmp     [rcx+119FAh], r11d
0x1800b2385  jz      short loc_1800B23B2
0x1800b2387  mov     eax, [rcx+119EEh]
0x1800b238d  add     [rcx+119EAh], eax
0x1800b2393  mov     rax, [rcx+118CEh]
0x1800b239a  mov     [rcx+118D6h], rax
0x1800b23a1  mov     [rcx+119EEh], r11d
0x1800b23a8  mov     eax, 32h ; '2'
0x1800b23ad  jmp     loc_1800B29F0
0x1800b23b2  mov     eax, [rcx+119EEh]
0x1800b23b8  test    eax, eax
0x1800b23ba  jz      loc_1800B29EE
0x1800b23c0  mov     r9d, [rcx+28h]
0x1800b23c4  mov     r15d, eax
0x1800b23c7  test    r9d, r9d
0x1800b23ca  jnz     short loc_1800B23EE
0x1800b23cc  cmp     [rcx+30h], r11d
0x1800b23d0  jnz     short loc_1800B23EE
0x1800b23d2  mov     rdx, [rbx+1208h]
0x1800b23d9  mov     rcx, [rcx+1320h]
0x1800b23e0  add     rax, rdx
0x1800b23e3  cmp     rax, rcx
0x1800b23e6  jle     short loc_1800B23EE
0x1800b23e8  mov     r15, rcx
0x1800b23eb  sub     r15, rdx
0x1800b23ee  mov     edi, 1
0x1800b23f3  test    r15, r15
0x1800b23f6  jg      short loc_1800B241C
0x1800b23f8  mov     [rbx], edi
0x1800b23fa  test    r9d, r9d
0x1800b23fd  jz      short loc_1800B2405
0x1800b23ff  cmp     [rbx+30h], r11d
0x1800b2403  jz      short loc_1800B240D
0x1800b2405  mov     [rbx+18h], edi
0x1800b2408  jmp     loc_1800B2981
0x1800b240d  mov     dword ptr [rbx+119FAh], 2
0x1800b2417  jmp     loc_1800B2981
0x1800b241c  mov     edx, [rbx+1163Ch]
0x1800b2422  lea     r8, [rbx+118CEh]
0x1800b2429  mov     r11, [r8]
0x1800b242c  mov     r10d, r15d
0x1800b242f  test    r15d, r15d
0x1800b2432  jz      short loc_1800B2453
0x1800b2434  movzx   eax, byte ptr [r11]
0x1800b2438  add     r11, rdi
0x1800b243b  movzx   ecx, dl
0x1800b243e  xor     rcx, rax
0x1800b2441  shr     edx, 8
0x1800b2444  lea     rax, crc_32_tab
0x1800b244b  xor     edx, [rax+rcx*4]
0x1800b244e  sub     r10d, edi
0x1800b2451  jnz     short loc_1800B2434
0x1800b2453  xor     r11d, r11d
0x1800b2456  mov     [rbx+1163Ch], edx
0x1800b245c  cmp     [rbx+11FCh], r11d
0x1800b2463  jnz     loc_1800B2576
0x1800b2469  test    r9d, r9d
0x1800b246c  jnz     loc_1800B257F
0x1800b2472  cmp     [rbx+30h], r11d
0x1800b2476  jnz     loc_1800B2672
0x1800b247c  mov     r14d, 4000h
0x1800b2482  cmp     [rbx+13B0h], r14d
0x1800b2489  jnz     short loc_1800B2500
0x1800b248b  mov     r14, [rbx+118DEh]
0x1800b2492  mov     r12, r15
0x1800b2495  mov     esi, r11d
0x1800b2498  mov     word ptr [rbp+arg_0], 0A0Dh
0x1800b249e  test    esi, esi
0x1800b24a0  jnz     loc_1800B2981
0x1800b24a6  cmp     byte ptr [r14], 0Ah
0x1800b24aa  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800b24ae  mov     rcx, [rbx+119F2h]; hFile
0x1800b24b5  mov     esi, r11d
0x1800b24b8  mov     [rsp+68h+lpOverlapped], r11; lpOverlapped
0x1800b24bd  jnz     short loc_1800B24CF
0x1800b24bf  add     [rbx+6Ch], rdi
0x1800b24c3  lea     rdx, [rbp+arg_0]
0x1800b24c7  mov     r8d, 2
0x1800b24cd  jmp     short loc_1800B24D5
0x1800b24cf  mov     r8d, edi; nNumberOfBytesToWrite
0x1800b24d2  mov     rdx, r14; lpBuffer
0x1800b24d5  call    cs:__imp_WriteFile
0x1800b24dc  nop     dword ptr [rax+rax+00h]
0x1800b24e1  xor     r11d, r11d
0x1800b24e4  test    eax, eax
0x1800b24e6  jz      short loc_1800B24EE
0x1800b24e8  cmp     [rbp+NumberOfBytesWritten], r11d
0x1800b24ec  ja      short loc_1800B24F0
0x1800b24ee  mov     esi, edi
0x1800b24f0  add     r14, rdi
0x1800b24f3  sub     r12, rdi
0x1800b24f6  test    r12, r12
0x1800b24f9  jg      short loc_1800B249E
0x1800b24fb  jmp     loc_1800B2981
0x1800b2500  mov     r12d, r11d
0x1800b2503  mov     esi, r15d
0x1800b2506  test    esi, esi
0x1800b2508  jz      loc_1800B2981
0x1800b250e  mov     rcx, [rbx+119F2h]; hFile
0x1800b2515  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800b2519  cmp     r14d, esi
0x1800b251c  mov     edx, r12d
0x1800b251f  mov     eax, esi
0x1800b2521  mov     [rsp+68h+lpOverlapped], r11; lpOverlapped
0x1800b2526  cmovbe  eax, r14d
0x1800b252a  add     rdx, [rbx+118DEh]; lpBuffer
0x1800b2531  mov     r8d, eax; nNumberOfBytesToWrite
0x1800b2534  mov     r14d, eax
0x1800b2537  call    cs:__imp_WriteFile
0x1800b253e  nop     dword ptr [rax+rax+00h]
0x1800b2543  xor     r11d, r11d
0x1800b2546  test    eax, eax
0x1800b2548  jz      short loc_1800B2552
0x1800b254a  mov     eax, edi
0x1800b254c  cmp     [rbp+NumberOfBytesWritten], r14d
0x1800b2550  jz      short loc_1800B2555
0x1800b2552  mov     eax, r11d
0x1800b2555  sub     esi, r14d
0x1800b2558  add     r12d, r14d
0x1800b255b  test    eax, eax
0x1800b255d  jnz     short loc_1800B2506
0x1800b255f  cmp     [rbx+11F0h], r11d
0x1800b2566  jnz     loc_1800B2981
0x1800b256c  mov     eax, 32h ; '2'
0x1800b2571  jmp     loc_1800B26F2
0x1800b2576  test    r9d, r9d
0x1800b2579  jz      loc_1800B2662
0x1800b257f  cmp     [rbx+2Ch], r11d
0x1800b2583  jnz     loc_1800B2662
0x1800b2589  mov     rdx, [rbx+6Ch]
0x1800b258d  mov     rcx, [rbx+1320h]
0x1800b2594  mov     r9, [rbx+5Ch]
0x1800b2598  add     r9, [rbx+64h]
0x1800b259c  mov     r10, [rbx+118DEh]
0x1800b25a3  lea     rax, [rdx+rcx]
0x1800b25a7  cmp     rax, [rbx+4Ch]
0x1800b25ab  jge     short loc_1800B25B6
0x1800b25ad  sub     rdx, [rbx+54h]
0x1800b25b1  add     rdx, rcx
0x1800b25b4  jmp     short loc_1800B25BA
0x1800b25b6  mov     rdx, [rbx+4Ch]
0x1800b25ba  mov     r14d, 4000h
0x1800b25c0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b25c4  test    r15, r15
0x1800b25c7  jle     loc_1800B2988
0x1800b25cd  mov     rcx, [rbx+74h]
0x1800b25d1  cmp     rcx, [rbx+54h]
0x1800b25d5  jl      short loc_1800B262B
0x1800b25d7  mov     rax, [rbx+64h]
0x1800b25db  cmp     rax, [rbx+4Ch]
0x1800b25df  jge     short loc_1800B256C
0x1800b25e1  cmp     rax, rdx
0x1800b25e4  jge     short loc_1800B264E
0x1800b25e6  cmp     [rbx+13B0h], r14d
0x1800b25ed  jnz     short loc_1800B2613
0x1800b25ef  cmp     byte ptr [r10], 0Ah
0x1800b25f3  jnz     short loc_1800B2613
0x1800b25f5  mov     byte ptr [r9], 0Dh
0x1800b25f9  cmp     rdx, [rbx+4Ch]
0x1800b25fd  jge     short loc_1800B2606
0x1800b25ff  add     [rbx+6Ch], rdi
0x1800b2603  add     rdx, rdi
0x1800b2606  add     [rbx+64h], rdi
0x1800b260a  cmp     [rbx+64h], rdx
0x1800b260e  jge     short loc_1800B264E
0x1800b2610  add     r9, rdi
0x1800b2613  mov     al, [r10]
0x1800b2616  mov     rcx, rsi
0x1800b2619  mov     [r9], al
0x1800b261c  add     r9, rdi
0x1800b261f  add     [rbx+64h], rdi
0x1800b2623  mov     rax, rdi
0x1800b2626  add     r15, rcx
0x1800b2629  jmp     short loc_1800B2646
0x1800b262b  mov     eax, [rbx+13CAh]
0x1800b2631  inc     rcx
0x1800b2634  mov     [rbx+74h], rcx
0x1800b2638  cmp     rcx, rax
0x1800b263b  jge     short loc_1800B264E
0x1800b263d  mov     rax, r10
0x1800b2640  sub     r15, rdi
0x1800b2643  mov     r10, rdi
0x1800b2646  add     r10, rax
0x1800b2649  jmp     loc_1800B25C4
0x1800b264e  mov     dword ptr [rbx+119FAh], 3
0x1800b2658  mov     eax, 2
0x1800b265d  jmp     loc_1800B29F0
0x1800b2662  cmp     [rbx+30h], r11d
0x1800b2666  jnz     short loc_1800B2672
0x1800b2668  cmp     [rbx+2Ch], r11d
0x1800b266c  jz      loc_1800B2988
0x1800b2672  mov     r14d, 4000h
0x1800b2678  mov     r13d, 3
0x1800b267e  mov     r12d, r15d
0x1800b2681  mov     [rbp+arg_18], r13d
0x1800b2685  cmp     [rbx+13B0h], r14d
0x1800b268c  jnz     short loc_1800B2701
0x1800b268e  lea     rax, [r15+r15]
0x1800b2692  movsxd  rcx, eax; Size
0x1800b2695  call    cs:__imp_malloc
0x1800b269c  nop     dword ptr [rax+rax+00h]
0x1800b26a1  xor     r11d, r11d
0x1800b26a4  mov     rsi, rax
0x1800b26a7  test    rax, rax
0x1800b26aa  jz      short loc_1800B26ED
0x1800b26ac  test    r15d, r15d
0x1800b26af  jle     short loc_1800B26E4
0x1800b26b1  mov     r8, [rbx+118DEh]
0x1800b26b8  mov     rcx, rax
0x1800b26bb  mov     edx, r11d
0x1800b26be  mov     eax, edx
0x1800b26c0  cmp     byte ptr [rax+r8], 0Ah
0x1800b26c5  jnz     short loc_1800B26D4
0x1800b26c7  add     [rbx+6Ch], rdi
0x1800b26cb  mov     byte ptr [rcx], 0Dh
0x1800b26ce  add     rcx, rdi
0x1800b26d1  add     r12d, edi
0x1800b26d4  mov     al, [rax+r8]
0x1800b26d8  add     edx, edi
0x1800b26da  mov     [rcx], al
0x1800b26dc  add     rcx, rdi
0x1800b26df  cmp     edx, r15d
0x1800b26e2  jl      short loc_1800B26BE
0x1800b26e4  mov     r10, rsi
0x1800b26e7  mov     [rbp+var_18], rsi
0x1800b26eb  jmp     short loc_1800B270F
0x1800b26ed  mov     eax, 4
0x1800b26f2  mov     dword ptr [rbx+119FAh], 2
0x1800b26fc  jmp     loc_1800B29F0
0x1800b2701  mov     r10, [rbx+118DEh]
0x1800b2708  mov     rsi, r11
0x1800b270b  mov     [rbp+var_18], r10
0x1800b270f  cmp     [rbx+2Ch], r11d
0x1800b2713  jz      loc_1800B28AA
0x1800b2719  mov     rcx, [rbx+6Ch]
0x1800b271d  mov     rdx, [rbx+1320h]
0x1800b2724  lea     rax, [rcx+rdx]
0x1800b2728  cmp     rax, [rbx+4Ch]
0x1800b272c  jge     short loc_1800B2737
0x1800b272e  sub     rcx, [rbx+54h]
0x1800b2732  add     rcx, rdx
0x1800b2735  jmp     short loc_1800B273B
0x1800b2737  mov     rcx, [rbx+4Ch]
0x1800b273b  mov     edx, r11d
0x1800b273e  mov     [rbp+var_10], rcx
0x1800b2742  mov     [rbp+arg_0], edx
0x1800b2745  test    edx, edx
0x1800b2747  jnz     loc_1800B2961
0x1800b274d  test    r12d, r12d
0x1800b2750  jz      loc_1800B2961
0x1800b2756  mov     rax, [rbx+74h]
0x1800b275a  cmp     rax, [rbx+54h]
0x1800b275e  jl      loc_1800B2850
0x1800b2764  mov     rdx, [rbx+64h]
0x1800b2768  cmp     rdx, [rbx+4Ch]
0x1800b276c  jge     loc_1800B2876
0x1800b2772  mov     eax, r12d
0x1800b2775  add     rax, rdx
0x1800b2778  cmp     rax, rcx
0x1800b277b  jle     short loc_1800B2787
0x1800b277d  mov     r12d, ecx
0x1800b2780  mov     [rbp+arg_18], r11d
0x1800b2784  sub     r12d, edx
0x1800b2787  mov     rcx, [rbx+1368h]
0x1800b278e  lea     rax, [rbp+arg_18]
0x1800b2792  mov     rdx, [rbx+44h]
0x1800b2796  mov     r8, [rbx+3Ch]
0x1800b279a  mov     r9d, [rbx+3Ch]
0x1800b279e  mov     [rsp+68h+var_28], rax
0x1800b27a3  mov     rax, [rbx+1360h]
0x1800b27aa  mov     [rsp+68h+var_30], rcx
0x1800b27af  mov     ecx, [rbx+44h]
0x1800b27b2  sar     rdx, 20h
0x1800b27b6  mov     [rsp+68h+var_38], edx
0x1800b27ba  mov     rdx, r10
0x1800b27bd  sar     r8, 20h
0x1800b27c1  mov     [rsp+68h+var_40], ecx
0x1800b27c5  mov     ecx, edi
0x1800b27c7  mov     dword ptr [rsp+68h+lpOverlapped], r8d
0x1800b27cc  lea     r8, [rbp+arg_10]
0x1800b27d0  mov     [rbp+arg_10], r12d
0x1800b27d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b27d9  mov     ecx, [rbp+arg_10]
0x1800b27dc  mov     r10, [rbp+var_18]
0x1800b27e0  movsxd  rax, ecx
  ... truncated ...
```
