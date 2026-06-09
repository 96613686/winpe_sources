# FlushOutput

- ea: `0x1800acbe8`
- end: `0x1800ad26d`
- name: `FlushOutput`
- size: `1669`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800ac900`
- `0x1800ad9cc`

## callees

- `0x1800aa370`
- `0x1800acbe8`
- `0x1800cb010`

## import_xrefs

- `msvcrt!free` at `0x1800ad0b6`
- `msvcrt!free` at `0x1800ad111`
- `msvcrt!free` at `0x1800ad1e4`
- `msvcrt!free` at `0x1800ad0b6`
- `msvcrt!free` at `0x1800ad111`
- `msvcrt!free` at `0x1800ad1e4`
- `msvcrt!malloc` at `0x1800acf19`
- `msvcrt!malloc` at `0x1800acf19`
- `KERNEL32!WriteFile` at `0x1800acd65`
- `KERNEL32!WriteFile` at `0x1800acdc1`
- `KERNEL32!WriteFile` at `0x1800acd65`
- `KERNEL32!WriteFile` at `0x1800acdc1`

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
0x1800acbe8  push    rbp
0x1800acbea  push    rbx
0x1800acbeb  push    rsi
0x1800acbec  push    rdi
0x1800acbed  push    r12
0x1800acbef  push    r13
0x1800acbf1  push    r14
0x1800acbf3  push    r15
0x1800acbf5  mov     rbp, rsp
0x1800acbf8  sub     rsp, 68h
0x1800acbfc  xor     r11d, r11d
0x1800acbff  mov     rbx, rcx
0x1800acc02  mov     [rbp+NumberOfBytesWritten], r11d
0x1800acc06  mov     [rbp+arg_18], r11d
0x1800acc0a  mov     [rbp+arg_10], r11d
0x1800acc0e  cmp     [rcx+119FAh], r11d
0x1800acc15  jz      short loc_1800ACC42
0x1800acc17  mov     eax, [rcx+119EEh]
0x1800acc1d  add     [rcx+119EAh], eax
0x1800acc23  mov     rax, [rcx+118CEh]
0x1800acc2a  mov     [rcx+118D6h], rax
0x1800acc31  mov     [rcx+119EEh], r11d
0x1800acc38  mov     eax, 32h ; '2'
0x1800acc3d  jmp     loc_1800AD25C
0x1800acc42  mov     eax, [rcx+119EEh]
0x1800acc48  test    eax, eax
0x1800acc4a  jz      loc_1800AD25A
0x1800acc50  mov     r9d, [rcx+28h]
0x1800acc54  mov     r15d, eax
0x1800acc57  test    r9d, r9d
0x1800acc5a  jnz     short loc_1800ACC7E
0x1800acc5c  cmp     [rcx+30h], r11d
0x1800acc60  jnz     short loc_1800ACC7E
0x1800acc62  mov     rdx, [rbx+1208h]
0x1800acc69  mov     rcx, [rcx+1320h]
0x1800acc70  add     rax, rdx
0x1800acc73  cmp     rax, rcx
0x1800acc76  jle     short loc_1800ACC7E
0x1800acc78  mov     r15, rcx
0x1800acc7b  sub     r15, rdx
0x1800acc7e  mov     edi, 1
0x1800acc83  test    r15, r15
0x1800acc86  jg      short loc_1800ACCAC
0x1800acc88  mov     [rbx], edi
0x1800acc8a  test    r9d, r9d
0x1800acc8d  jz      short loc_1800ACC95
0x1800acc8f  cmp     [rbx+30h], r11d
0x1800acc93  jz      short loc_1800ACC9D
0x1800acc95  mov     [rbx+18h], edi
0x1800acc98  jmp     loc_1800AD1ED
0x1800acc9d  mov     dword ptr [rbx+119FAh], 2
0x1800acca7  jmp     loc_1800AD1ED
0x1800accac  mov     edx, [rbx+1163Ch]
0x1800accb2  lea     r8, [rbx+118CEh]
0x1800accb9  mov     r11, [r8]
0x1800accbc  mov     r10d, r15d
0x1800accbf  test    r15d, r15d
0x1800accc2  jz      short loc_1800ACCE3
0x1800accc4  movzx   eax, byte ptr [r11]
0x1800accc8  add     r11, rdi
0x1800acccb  movzx   ecx, dl
0x1800accce  xor     rcx, rax
0x1800accd1  shr     edx, 8
0x1800accd4  lea     rax, crc_32_tab
0x1800accdb  xor     edx, [rax+rcx*4]
0x1800accde  sub     r10d, edi
0x1800acce1  jnz     short loc_1800ACCC4
0x1800acce3  xor     r11d, r11d
0x1800acce6  mov     [rbx+1163Ch], edx
0x1800accec  cmp     [rbx+11FCh], r11d
0x1800accf3  jnz     loc_1800ACDFA
0x1800accf9  test    r9d, r9d
0x1800accfc  jnz     loc_1800ACE03
0x1800acd02  cmp     [rbx+30h], r11d
0x1800acd06  jnz     loc_1800ACEF6
0x1800acd0c  mov     r14d, 4000h
0x1800acd12  cmp     [rbx+13B0h], r14d
0x1800acd19  jnz     short loc_1800ACD8A
0x1800acd1b  mov     r14, [rbx+118DEh]
0x1800acd22  mov     r12, r15
0x1800acd25  mov     esi, r11d
0x1800acd28  mov     word ptr [rbp+arg_0], 0A0Dh
0x1800acd2e  test    esi, esi
0x1800acd30  jnz     loc_1800AD1ED
0x1800acd36  cmp     byte ptr [r14], 0Ah
0x1800acd3a  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800acd3e  mov     rcx, [rbx+119F2h]; hFile
0x1800acd45  mov     esi, r11d
0x1800acd48  mov     [rsp+68h+lpOverlapped], r11; lpOverlapped
0x1800acd4d  jnz     short loc_1800ACD5F
0x1800acd4f  add     [rbx+6Ch], rdi
0x1800acd53  lea     rdx, [rbp+arg_0]
0x1800acd57  mov     r8d, 2
0x1800acd5d  jmp     short loc_1800ACD65
0x1800acd5f  mov     r8d, edi; nNumberOfBytesToWrite
0x1800acd62  mov     rdx, r14; lpBuffer
0x1800acd65  call    cs:__imp_WriteFile
0x1800acd6b  xor     r11d, r11d
0x1800acd6e  test    eax, eax
0x1800acd70  jz      short loc_1800ACD78
0x1800acd72  cmp     [rbp+NumberOfBytesWritten], r11d
0x1800acd76  ja      short loc_1800ACD7A
0x1800acd78  mov     esi, edi
0x1800acd7a  add     r14, rdi
0x1800acd7d  sub     r12, rdi
0x1800acd80  test    r12, r12
0x1800acd83  jg      short loc_1800ACD2E
0x1800acd85  jmp     loc_1800AD1ED
0x1800acd8a  mov     r12d, r11d
0x1800acd8d  mov     esi, r15d
0x1800acd90  test    esi, esi
0x1800acd92  jz      loc_1800AD1ED
0x1800acd98  mov     rcx, [rbx+119F2h]; hFile
0x1800acd9f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800acda3  cmp     r14d, esi
0x1800acda6  mov     edx, r12d
0x1800acda9  mov     eax, esi
0x1800acdab  mov     [rsp+68h+lpOverlapped], r11; lpOverlapped
0x1800acdb0  cmovbe  eax, r14d
0x1800acdb4  add     rdx, [rbx+118DEh]; lpBuffer
0x1800acdbb  mov     r8d, eax; nNumberOfBytesToWrite
0x1800acdbe  mov     r14d, eax
0x1800acdc1  call    cs:__imp_WriteFile
0x1800acdc7  xor     r11d, r11d
0x1800acdca  test    eax, eax
0x1800acdcc  jz      short loc_1800ACDD6
0x1800acdce  mov     eax, edi
0x1800acdd0  cmp     [rbp+NumberOfBytesWritten], r14d
0x1800acdd4  jz      short loc_1800ACDD9
0x1800acdd6  mov     eax, r11d
0x1800acdd9  sub     esi, r14d
0x1800acddc  add     r12d, r14d
0x1800acddf  test    eax, eax
0x1800acde1  jnz     short loc_1800ACD90
0x1800acde3  cmp     [rbx+11F0h], r11d
0x1800acdea  jnz     loc_1800AD1ED
0x1800acdf0  mov     eax, 32h ; '2'
0x1800acdf5  jmp     loc_1800ACF70
0x1800acdfa  test    r9d, r9d
0x1800acdfd  jz      loc_1800ACEE6
0x1800ace03  cmp     [rbx+2Ch], r11d
0x1800ace07  jnz     loc_1800ACEE6
0x1800ace0d  mov     rdx, [rbx+6Ch]
0x1800ace11  mov     rcx, [rbx+1320h]
0x1800ace18  mov     r9, [rbx+5Ch]
0x1800ace1c  add     r9, [rbx+64h]
0x1800ace20  mov     r10, [rbx+118DEh]
0x1800ace27  lea     rax, [rdx+rcx]
0x1800ace2b  cmp     rax, [rbx+4Ch]
0x1800ace2f  jge     short loc_1800ACE3A
0x1800ace31  sub     rdx, [rbx+54h]
0x1800ace35  add     rdx, rcx
0x1800ace38  jmp     short loc_1800ACE3E
0x1800ace3a  mov     rdx, [rbx+4Ch]
0x1800ace3e  mov     r14d, 4000h
0x1800ace44  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ace48  test    r15, r15
0x1800ace4b  jle     loc_1800AD1F4
0x1800ace51  mov     rcx, [rbx+74h]
0x1800ace55  cmp     rcx, [rbx+54h]
0x1800ace59  jl      short loc_1800ACEAF
0x1800ace5b  mov     rax, [rbx+64h]
0x1800ace5f  cmp     rax, [rbx+4Ch]
0x1800ace63  jge     short loc_1800ACDF0
0x1800ace65  cmp     rax, rdx
0x1800ace68  jge     short loc_1800ACED2
0x1800ace6a  cmp     [rbx+13B0h], r14d
0x1800ace71  jnz     short loc_1800ACE97
0x1800ace73  cmp     byte ptr [r10], 0Ah
0x1800ace77  jnz     short loc_1800ACE97
0x1800ace79  mov     byte ptr [r9], 0Dh
0x1800ace7d  cmp     rdx, [rbx+4Ch]
0x1800ace81  jge     short loc_1800ACE8A
0x1800ace83  add     [rbx+6Ch], rdi
0x1800ace87  add     rdx, rdi
0x1800ace8a  add     [rbx+64h], rdi
0x1800ace8e  cmp     [rbx+64h], rdx
0x1800ace92  jge     short loc_1800ACED2
0x1800ace94  add     r9, rdi
0x1800ace97  mov     al, [r10]
0x1800ace9a  mov     rcx, rsi
0x1800ace9d  mov     [r9], al
0x1800acea0  add     r9, rdi
0x1800acea3  add     [rbx+64h], rdi
0x1800acea7  mov     rax, rdi
0x1800aceaa  add     r15, rcx
0x1800acead  jmp     short loc_1800ACECA
0x1800aceaf  mov     eax, [rbx+13CAh]
0x1800aceb5  inc     rcx
0x1800aceb8  mov     [rbx+74h], rcx
0x1800acebc  cmp     rcx, rax
0x1800acebf  jge     short loc_1800ACED2
0x1800acec1  mov     rax, r10
0x1800acec4  sub     r15, rdi
0x1800acec7  mov     r10, rdi
0x1800aceca  add     r10, rax
0x1800acecd  jmp     loc_1800ACE48
0x1800aced2  mov     dword ptr [rbx+119FAh], 3
0x1800acedc  mov     eax, 2
0x1800acee1  jmp     loc_1800AD25C
0x1800acee6  cmp     [rbx+30h], r11d
0x1800aceea  jnz     short loc_1800ACEF6
0x1800aceec  cmp     [rbx+2Ch], r11d
0x1800acef0  jz      loc_1800AD1F4
0x1800acef6  mov     r14d, 4000h
0x1800acefc  mov     r13d, 3
0x1800acf02  mov     r12d, r15d
0x1800acf05  mov     [rbp+arg_18], r13d
0x1800acf09  cmp     [rbx+13B0h], r14d
0x1800acf10  jnz     short loc_1800ACF7F
0x1800acf12  lea     rax, [r15+r15]
0x1800acf16  movsxd  rcx, eax; Size
0x1800acf19  call    cs:__imp_malloc
0x1800acf1f  xor     r11d, r11d
0x1800acf22  mov     rsi, rax
0x1800acf25  test    rax, rax
0x1800acf28  jz      short loc_1800ACF6B
0x1800acf2a  test    r15d, r15d
0x1800acf2d  jle     short loc_1800ACF62
0x1800acf2f  mov     r8, [rbx+118DEh]
0x1800acf36  mov     rcx, rax
0x1800acf39  mov     edx, r11d
0x1800acf3c  mov     eax, edx
0x1800acf3e  cmp     byte ptr [rax+r8], 0Ah
0x1800acf43  jnz     short loc_1800ACF52
0x1800acf45  add     [rbx+6Ch], rdi
0x1800acf49  mov     byte ptr [rcx], 0Dh
0x1800acf4c  add     rcx, rdi
0x1800acf4f  add     r12d, edi
0x1800acf52  mov     al, [rax+r8]
0x1800acf56  add     edx, edi
0x1800acf58  mov     [rcx], al
0x1800acf5a  add     rcx, rdi
0x1800acf5d  cmp     edx, r15d
0x1800acf60  jl      short loc_1800ACF3C
0x1800acf62  mov     r10, rsi
0x1800acf65  mov     [rbp+var_18], rsi
0x1800acf69  jmp     short loc_1800ACF8D
0x1800acf6b  mov     eax, 4
0x1800acf70  mov     dword ptr [rbx+119FAh], 2
0x1800acf7a  jmp     loc_1800AD25C
0x1800acf7f  mov     r10, [rbx+118DEh]
0x1800acf86  mov     rsi, r11
0x1800acf89  mov     [rbp+var_18], r10
0x1800acf8d  cmp     [rbx+2Ch], r11d
0x1800acf91  jz      loc_1800AD11C
0x1800acf97  mov     rcx, [rbx+6Ch]
0x1800acf9b  mov     rdx, [rbx+1320h]
0x1800acfa2  lea     rax, [rcx+rdx]
0x1800acfa6  cmp     rax, [rbx+4Ch]
0x1800acfaa  jge     short loc_1800ACFB5
0x1800acfac  sub     rcx, [rbx+54h]
0x1800acfb0  add     rcx, rdx
0x1800acfb3  jmp     short loc_1800ACFB9
0x1800acfb5  mov     rcx, [rbx+4Ch]
0x1800acfb9  mov     edx, r11d
0x1800acfbc  mov     [rbp+var_10], rcx
0x1800acfc0  mov     [rbp+arg_0], edx
0x1800acfc3  test    edx, edx
0x1800acfc5  jnz     loc_1800AD1D3
0x1800acfcb  test    r12d, r12d
0x1800acfce  jz      loc_1800AD1D3
0x1800acfd4  mov     rax, [rbx+74h]
0x1800acfd8  cmp     rax, [rbx+54h]
0x1800acfdc  jl      loc_1800AD0C8
0x1800acfe2  mov     rdx, [rbx+64h]
0x1800acfe6  cmp     rdx, [rbx+4Ch]
0x1800acfea  jge     loc_1800AD0EE
0x1800acff0  mov     eax, r12d
0x1800acff3  add     rax, rdx
0x1800acff6  cmp     rax, rcx
0x1800acff9  jle     short loc_1800AD005
0x1800acffb  mov     r12d, ecx
0x1800acffe  mov     [rbp+arg_18], r11d
0x1800ad002  sub     r12d, edx
0x1800ad005  mov     rcx, [rbx+1368h]
0x1800ad00c  lea     rax, [rbp+arg_18]
0x1800ad010  mov     rdx, [rbx+44h]
0x1800ad014  mov     r8, [rbx+3Ch]
0x1800ad018  mov     r9d, [rbx+3Ch]
0x1800ad01c  mov     [rsp+68h+var_28], rax
0x1800ad021  mov     rax, [rbx+1360h]
0x1800ad028  mov     [rsp+68h+var_30], rcx
0x1800ad02d  mov     ecx, [rbx+44h]
0x1800ad030  sar     rdx, 20h
0x1800ad034  mov     [rsp+68h+var_38], edx
0x1800ad038  mov     rdx, r10
0x1800ad03b  sar     r8, 20h
0x1800ad03f  mov     [rsp+68h+var_40], ecx
0x1800ad043  mov     ecx, edi
0x1800ad045  mov     dword ptr [rsp+68h+lpOverlapped], r8d
0x1800ad04a  lea     r8, [rbp+arg_10]
0x1800ad04e  mov     [rbp+arg_10], r12d
0x1800ad052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad057  mov     ecx, [rbp+arg_10]
0x1800ad05a  mov     r10, [rbp+var_18]
0x1800ad05e  movsxd  rax, ecx
0x1800ad061  add     [rbx+64h], rax
0x1800ad065  cmp     ecx, r12d
0x1800ad068  jnb     short loc_1800AD079
  ... truncated ...
```
