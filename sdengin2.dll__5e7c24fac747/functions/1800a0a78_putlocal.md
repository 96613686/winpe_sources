# putlocal

- ea: `0x1800a0a78`
- end: `0x1800a0f40`
- name: `putlocal`
- size: `1224`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18009c2f8`
- `0x18009c3e4`

## callees

- `0x18009b2f0`
- `0x18009d5e4`
- `0x1800a0a78`
- `0x1800c97c2`
- `0x1800c9830`

## import_xrefs

- `msvcrt!free` at `0x1800a0bfb`
- `msvcrt!free` at `0x1800a0d60`
- `msvcrt!free` at `0x1800a0ec0`
- `msvcrt!free` at `0x1800a0ece`
- `msvcrt!free` at `0x1800a0eec`
- `msvcrt!free` at `0x1800a0ef5`
- `msvcrt!free` at `0x1800a0f0a`
- `msvcrt!free` at `0x1800a0bfb`
- `msvcrt!free` at `0x1800a0d60`
- `msvcrt!free` at `0x1800a0ec0`
- `msvcrt!free` at `0x1800a0ece`
- `msvcrt!free` at `0x1800a0eec`
- `msvcrt!free` at `0x1800a0ef5`
- `msvcrt!free` at `0x1800a0f0a`
- `msvcrt!malloc` at `0x1800a0b46`
- `msvcrt!malloc` at `0x1800a0c3a`
- `msvcrt!malloc` at `0x1800a0d89`
- `msvcrt!malloc` at `0x1800a0b46`
- `msvcrt!malloc` at `0x1800a0c3a`
- `msvcrt!malloc` at `0x1800a0d89`
- `KERNEL32!WriteFile` at `0x1800a0d34`
- `KERNEL32!WriteFile` at `0x1800a0e98`
- `KERNEL32!WriteFile` at `0x1800a0d34`
- `KERNEL32!WriteFile` at `0x1800a0e98`
- `USER32!CharToOemBuffA` at `0x1800a0af1`
- `USER32!CharToOemBuffA` at `0x1800a0af1`

## pseudocode

```c
__int64 __fastcall putlocal(__int64 a1, HANDLE *a2, __int64 a3)
{
  const CHAR *v6; // rcx
  DWORD v7; // r8d
  __int64 v8; // rax
  void *v10; // rdi
  unsigned __int16 v11; // r15
  __int64 v12; // r14
  size_t v13; // rsi
  char *v14; // rax
  __int64 v15; // r14
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  size_t v21; // rcx
  _DWORD *v22; // rax
  _DWORD *v23; // rsi
  unsigned __int16 v24; // ax
  size_t v25; // rbp
  size_t v26; // r8
  const void *v27; // rdx
  void *v28; // rcx
  _DWORD *v29; // rax
  unsigned __int16 v30; // ax
  int v31; // r13d
  int v32; // r12d
  __int16 v33; // r15
  size_t v34; // r15
  size_t v35; // r8
  const void *v36; // rdx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-168h] BYREF
  CHAR szDst[272]; // [rsp+40h] [rbp-158h] BYREF

  NumberOfBytesWritten = 0;
  if ( *(_DWORD *)(a3 + 620) )
  {
    StringCchCopyA(szDst, 0x104u, *(STRSAFE_LPCSTR *)(a1 + 120));
  }
  else
  {
    v6 = *(const CHAR **)(a1 + 120);
    v7 = 1;
    if ( v6 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      v7 = v8 + 1;
      if ( (unsigned int)(v8 + 1) > 0x104 )
        return 14;
    }
    CharToOemBuffA(v6, szDst, v7);
  }
  v10 = 0;
  v11 = 0;
  if ( *(_DWORD *)(a3 + 624) )
  {
    v12 = *(_QWORD *)(a1 + 16);
    if ( v12 > 0xFFFFFFFFLL || *(__int64 *)(a1 + 24) > 3500000000LL || *(__int16 *)(a3 + 3740) < 0 )
    {
      v13 = *(_QWORD *)(a1 + 40);
      v14 = (char *)malloc(v13 + 20);
      v10 = v14;
      if ( !v14 )
        return 4;
      *(_DWORD *)v14 = 1048577;
      v11 = 20;
      *(_QWORD *)(v14 + 4) = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(v14 + 12) = v12;
      if ( v13 )
        memcpy_0(v14 + 20, *(const void **)(a1 + 96), v13);
    }
  }
  v15 = v11;
  if ( *(_QWORD *)(a3 + 216) == -1 )
  {
    v16 = *(_QWORD *)(a3 + 3576) != 0 ? 42LL : 30LL;
    v17 = v11 + v16;
    if ( v17 < v16 )
      goto LABEL_73;
    v18 = v17 + *(_QWORD *)(a1 + 32);
    if ( v18 < v17 )
      goto LABEL_73;
    v19 = v18 + *(_QWORD *)(a1 + 40);
    if ( v19 < v18 || v19 < 0 )
      goto LABEL_73;
    if ( (unsigned int)PromptForNewDisk(a1, a2, v19, a3) )
    {
      if ( v10 )
        free(v10);
      return *(_DWORD *)(a3 + 208) != 0 ? 9 : 19;
    }
    v20 = v11 + 31LL + *(_QWORD *)(a1 + 32);
    if ( v20 < (unsigned __int64)v11 + 31 )
      goto LABEL_73;
    v21 = v20 + *(_QWORD *)(a1 + 40);
    if ( v21 < v20 )
      goto LABEL_73;
    v22 = malloc(v21);
    v23 = v22;
    if ( v22 )
    {
      *v22 = 67324752;
      v24 = *(_WORD *)(a1 + 2);
      if ( !v11 && v24 >= 0x2Du )
        v24 = 21 - (*(_WORD *)(a1 + 6) != 9);
      *((_WORD *)v23 + 2) = v24;
      *((_WORD *)v23 + 3) = *(_WORD *)(a1 + 70);
      *((_WORD *)v23 + 4) = *(_WORD *)(a1 + 6);
      *(_DWORD *)((char *)v23 + 10) = *(_DWORD *)(a1 + 8);
      *(_DWORD *)((char *)v23 + 14) = *(_DWORD *)(a1 + 12);
      if ( v11 && (*(__int64 *)(a1 + 16) > 0xFFFFFFFFLL || *(__int64 *)(a1 + 24) > 0xFFFFFFFFLL) )
      {
        *(_QWORD *)((char *)v23 + 18) = -1;
      }
      else
      {
        *(_DWORD *)((char *)v23 + 18) = *(_DWORD *)(a1 + 16);
        *(_DWORD *)((char *)v23 + 22) = *(_DWORD *)(a1 + 24);
      }
      v25 = *(_QWORD *)(a1 + 32);
      *((_WORD *)v23 + 13) = *(_WORD *)(a1 + 32);
      *((_WORD *)v23 + 14) = *(_WORD *)(a1 + 40) + v11;
      memcpy_0((char *)v23 + 30, szDst, v25);
      v26 = *(_QWORD *)(a1 + 40);
      if ( v11 )
      {
        v26 += v11;
        v27 = v10;
      }
      else
      {
        if ( !v26 )
        {
LABEL_41:
          if ( !WriteFile(*a2, v23, *(_DWORD *)(a1 + 32) + v11 + *(_DWORD *)(a1 + 40) + 30, &NumberOfBytesWritten, 0)
            || NumberOfBytesWritten != *(_QWORD *)(a1 + 40) + 30LL + v11 + *(_QWORD *)(a1 + 32) )
          {
            free(v23);
            if ( !v10 )
              return 10;
            v28 = v10;
LABEL_70:
            free(v28);
            return 10;
          }
          goto LABEL_63;
        }
        v27 = *(const void **)(a1 + 96);
      }
      memcpy_0((char *)v23 + v25 + 30, v27, v26);
      goto LABEL_41;
    }
LABEL_72:
    if ( v10 )
LABEL_73:
      free(v10);
    return 4;
  }
  v29 = malloc(*(_QWORD *)(a1 + 40) + 31LL + v11 + *(_QWORD *)(a1 + 32));
  v23 = v29;
  if ( !v29 )
    goto LABEL_72;
  *v29 = 67324752;
  v30 = *(_WORD *)(a1 + 2);
  v31 = v11;
  if ( !v11 && v30 >= 0x2Du )
    v30 = 21 - (*(_WORD *)(a1 + 6) != 9);
  *((_WORD *)v23 + 2) = v30;
  v32 = *(_DWORD *)(a3 + 624);
  *((_WORD *)v23 + 3) = *(_WORD *)(a1 + 70);
  *((_WORD *)v23 + 4) = *(_WORD *)(a1 + 6);
  *(_DWORD *)((char *)v23 + 10) = *(_DWORD *)(a1 + 8);
  *(_DWORD *)((char *)v23 + 14) = *(_DWORD *)(a1 + 12);
  if ( v32 && (*(__int64 *)(a1 + 16) > 0xFFFFFFFFLL || *(__int64 *)(a1 + 24) > 0xFFFFFFFFLL) )
  {
    *(_QWORD *)((char *)v23 + 18) = -1;
  }
  else
  {
    *(_DWORD *)((char *)v23 + 18) = *(_DWORD *)(a1 + 16);
    *(_DWORD *)((char *)v23 + 22) = *(_DWORD *)(a1 + 24);
  }
  v33 = *(_WORD *)(a1 + 40) + v11;
  *((_WORD *)v23 + 13) = *(_WORD *)(a1 + 32);
  if ( !v32 )
    v33 = *(_WORD *)(a1 + 40);
  *((_WORD *)v23 + 14) = v33;
  v34 = *(_QWORD *)(a1 + 32);
  memcpy_0((char *)v23 + 30, szDst, v34);
  v35 = *(_QWORD *)(a1 + 40);
  if ( v32 )
  {
    v35 += v15;
    v36 = v10;
LABEL_60:
    memcpy_0((char *)v23 + v34 + 30, v36, v35);
    goto LABEL_61;
  }
  if ( v35 )
  {
    v36 = *(const void **)(a1 + 96);
    goto LABEL_60;
  }
LABEL_61:
  if ( !WriteFile(
          *(HANDLE *)(a3 + 216),
          v23,
          v31 + *(_DWORD *)(a1 + 32) + *(_DWORD *)(a1 + 40) + 30,
          &NumberOfBytesWritten,
          0)
    || NumberOfBytesWritten != *(_QWORD *)(a1 + 40) + 30LL + v15 + *(_QWORD *)(a1 + 32) )
  {
    if ( v10 )
      free(v10);
    v28 = v23;
    goto LABEL_70;
  }
LABEL_63:
  free(v23);
  if ( v10 )
    free(v10);
  else
    v15 = 0;
  *(_QWORD *)(a1 + 136) = v15;
  return 0;
}

```

## disassembly

```asm
0x1800a0a78  mov     [rsp+arg_18], rbx
0x1800a0a7d  push    rbp
0x1800a0a7e  push    rsi
0x1800a0a7f  push    rdi
0x1800a0a80  push    r12
0x1800a0a82  push    r13
0x1800a0a84  push    r14
0x1800a0a86  push    r15
0x1800a0a88  sub     rsp, 160h
0x1800a0a8f  mov     rax, cs:__security_cookie
0x1800a0a96  xor     rax, rsp
0x1800a0a99  mov     [rsp+198h+var_48], rax
0x1800a0aa1  xor     r13d, r13d
0x1800a0aa4  mov     rbp, r8
0x1800a0aa7  mov     r12, rdx
0x1800a0aaa  mov     rbx, rcx
0x1800a0aad  mov     [rsp+198h+NumberOfBytesWritten], r13d
0x1800a0ab2  cmp     [r8+26Ch], r13d
0x1800a0ab9  jnz     short loc_1800A0AF9
0x1800a0abb  mov     rcx, [rcx+78h]; lpszSrc
0x1800a0abf  lea     r8d, [r13+1]; cchDstLength
0x1800a0ac3  test    rcx, rcx
0x1800a0ac6  jz      short loc_1800A0AEC
0x1800a0ac8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a0acc  inc     rax
0x1800a0acf  cmp     [rcx+rax], r13b
0x1800a0ad3  jnz     short loc_1800A0ACC
0x1800a0ad5  lea     r8d, [rax+1]
0x1800a0ad9  cmp     r8d, 104h
0x1800a0ae0  jbe     short loc_1800A0AEC
0x1800a0ae2  mov     eax, 0Eh
0x1800a0ae7  jmp     loc_1800A0F15
0x1800a0aec  lea     rdx, [rsp+198h+szDst]; lpszDst
0x1800a0af1  call    cs:__imp_CharToOemBuffA
0x1800a0af7  jmp     short loc_1800A0B0C
0x1800a0af9  mov     r8, [rcx+78h]; pszSrc
0x1800a0afd  mov     edx, 104h; cchDest
0x1800a0b02  lea     rcx, [rsp+198h+szDst]; pszDest
0x1800a0b07  call    StringCchCopyA
0x1800a0b0c  mov     rdi, r13
0x1800a0b0f  mov     r15d, r13d
0x1800a0b12  mov     eax, 0FFFFFFFFh
0x1800a0b17  cmp     [rbp+270h], r13d
0x1800a0b1e  jz      short loc_1800A0B85
0x1800a0b20  mov     r14, [rbx+10h]
0x1800a0b24  cmp     r14, rax
0x1800a0b27  jg      short loc_1800A0B3E
0x1800a0b29  mov     eax, 0D09DC300h
0x1800a0b2e  cmp     [rbx+18h], rax
0x1800a0b32  jg      short loc_1800A0B3E
0x1800a0b34  cmp     [rbp+0E9Ch], r13w
0x1800a0b3c  jge     short loc_1800A0B85
0x1800a0b3e  mov     rsi, [rbx+28h]
0x1800a0b42  lea     rcx, [rsi+14h]; Size
0x1800a0b46  call    cs:__imp_malloc
0x1800a0b4c  mov     rdi, rax
0x1800a0b4f  test    rax, rax
0x1800a0b52  jz      loc_1800A0F10
0x1800a0b58  mov     dword ptr [rax], 100001h
0x1800a0b5e  mov     r15d, 14h
0x1800a0b64  mov     rax, [rbx+18h]
0x1800a0b68  mov     [rdi+4], rax
0x1800a0b6c  mov     [rdi+0Ch], r14
0x1800a0b70  test    rsi, rsi
0x1800a0b73  jz      short loc_1800A0B85
0x1800a0b75  mov     rdx, [rbx+60h]; Src
0x1800a0b79  lea     rcx, [rdi+14h]; void *
0x1800a0b7d  mov     r8, rsi; Size
0x1800a0b80  call    memcpy_0
0x1800a0b85  cmp     qword ptr [rbp+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a0b8d  movzx   r14d, r15w
0x1800a0b91  jnz     loc_1800A0D77
0x1800a0b97  mov     rax, [rbp+0DF8h]
0x1800a0b9e  neg     rax
0x1800a0ba1  sbb     rcx, rcx
0x1800a0ba4  and     ecx, 0Ch
0x1800a0ba7  add     rcx, 1Eh
0x1800a0bab  lea     rdx, [r14+rcx]
0x1800a0baf  cmp     rdx, rcx
0x1800a0bb2  jb      loc_1800A0F07
0x1800a0bb8  mov     rcx, [rbx+20h]
0x1800a0bbc  add     rcx, rdx
0x1800a0bbf  cmp     rcx, rdx
0x1800a0bc2  jb      loc_1800A0F07
0x1800a0bc8  mov     r8, [rbx+28h]
0x1800a0bcc  add     r8, rcx
0x1800a0bcf  cmp     r8, rcx
0x1800a0bd2  jb      loc_1800A0F07
0x1800a0bd8  test    r8, r8
0x1800a0bdb  js      loc_1800A0F07
0x1800a0be1  mov     r9, rbp
0x1800a0be4  mov     rdx, r12
0x1800a0be7  mov     rcx, rbx
0x1800a0bea  call    PromptForNewDisk
0x1800a0bef  test    eax, eax
0x1800a0bf1  jz      short loc_1800A0C16
0x1800a0bf3  test    rdi, rdi
0x1800a0bf6  jz      short loc_1800A0C01
0x1800a0bf8  mov     rcx, rdi; Block
0x1800a0bfb  call    cs:__imp_free
0x1800a0c01  mov     eax, [rbp+0D0h]
0x1800a0c07  neg     eax
0x1800a0c09  sbb     eax, eax
0x1800a0c0b  and     eax, 0FFFFFFF6h
0x1800a0c0e  add     eax, 13h
0x1800a0c11  jmp     loc_1800A0F15
0x1800a0c16  mov     rdx, [rbx+20h]
0x1800a0c1a  lea     rcx, [r14+1Fh]
0x1800a0c1e  add     rdx, rcx
0x1800a0c21  cmp     rdx, rcx
0x1800a0c24  jb      loc_1800A0F07
0x1800a0c2a  mov     rcx, [rbx+28h]
0x1800a0c2e  add     rcx, rdx; Size
0x1800a0c31  cmp     rcx, rdx
0x1800a0c34  jb      loc_1800A0F07
0x1800a0c3a  call    cs:__imp_malloc
0x1800a0c40  mov     rsi, rax
0x1800a0c43  test    rax, rax
0x1800a0c46  jz      loc_1800A0F02
0x1800a0c4c  mov     dword ptr [rax], 4034B50h
0x1800a0c52  movzx   eax, word ptr [rbx+2]
0x1800a0c56  test    r15w, r15w
0x1800a0c5a  jnz     short loc_1800A0C74
0x1800a0c5c  cmp     ax, 2Dh ; '-'
0x1800a0c60  jb      short loc_1800A0C74
0x1800a0c62  movzx   eax, word ptr [rbx+6]
0x1800a0c66  sub     ax, 9
0x1800a0c6a  neg     ax
0x1800a0c6d  sbb     ax, ax
0x1800a0c70  add     ax, 15h
0x1800a0c74  mov     [rsi+4], ax
0x1800a0c78  movzx   eax, word ptr [rbx+46h]
0x1800a0c7c  mov     [rsi+6], ax
0x1800a0c80  movzx   eax, word ptr [rbx+6]
0x1800a0c84  mov     [rsi+8], ax
0x1800a0c88  mov     eax, [rbx+8]
0x1800a0c8b  mov     [rsi+0Ah], eax
0x1800a0c8e  mov     eax, [rbx+0Ch]
0x1800a0c91  mov     [rsi+0Eh], eax
0x1800a0c94  test    r15w, r15w
0x1800a0c98  jz      short loc_1800A0CB5
0x1800a0c9a  mov     eax, 0FFFFFFFFh
0x1800a0c9f  cmp     [rbx+10h], rax
0x1800a0ca3  jg      short loc_1800A0CAB
0x1800a0ca5  cmp     [rbx+18h], rax
0x1800a0ca9  jle     short loc_1800A0CB5
0x1800a0cab  mov     qword ptr [rsi+12h], 0FFFFFFFFFFFFFFFFh
0x1800a0cb3  jmp     short loc_1800A0CC1
0x1800a0cb5  mov     eax, [rbx+10h]
0x1800a0cb8  mov     [rsi+12h], eax
0x1800a0cbb  mov     eax, [rbx+18h]
0x1800a0cbe  mov     [rsi+16h], eax
0x1800a0cc1  movzx   eax, word ptr [rbx+20h]
0x1800a0cc5  lea     rcx, [rsi+1Eh]; void *
0x1800a0cc9  mov     rbp, [rbx+20h]
0x1800a0ccd  lea     rdx, [rsp+198h+szDst]; Src
0x1800a0cd2  mov     [rsi+1Ah], ax
0x1800a0cd6  mov     r8, rbp; Size
0x1800a0cd9  movzx   eax, r15w
0x1800a0cdd  add     ax, [rbx+28h]
0x1800a0ce1  mov     [rsi+1Ch], ax
0x1800a0ce5  call    memcpy_0
0x1800a0cea  mov     r8, [rbx+28h]; Size
0x1800a0cee  test    r15w, r15w
0x1800a0cf2  jz      short loc_1800A0CFC
0x1800a0cf4  add     r8, r14
0x1800a0cf7  mov     rdx, rdi
0x1800a0cfa  jmp     short loc_1800A0D05
0x1800a0cfc  test    r8, r8
0x1800a0cff  jz      short loc_1800A0D11
0x1800a0d01  mov     rdx, [rbx+60h]; Src
0x1800a0d05  lea     rcx, [rbp+1Eh]
0x1800a0d09  add     rcx, rsi; void *
0x1800a0d0c  call    memcpy_0
0x1800a0d11  mov     r8d, [rbx+28h]
0x1800a0d15  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a0d1a  mov     rcx, [r12]; hFile
0x1800a0d1e  add     r8d, 1Eh
0x1800a0d22  movzx   edx, r15w
0x1800a0d26  add     edx, [rbx+20h]
0x1800a0d29  add     r8d, edx; nNumberOfBytesToWrite
0x1800a0d2c  mov     [rsp+198h+lpOverlapped], r13; lpOverlapped
0x1800a0d31  mov     rdx, rsi; lpBuffer
0x1800a0d34  call    cs:__imp_WriteFile
0x1800a0d3a  test    eax, eax
0x1800a0d3c  jz      short loc_1800A0D5D
0x1800a0d3e  mov     rcx, [rbx+20h]
0x1800a0d42  mov     rax, [rbx+28h]
0x1800a0d46  add     rcx, r14
0x1800a0d49  add     rax, 1Eh
0x1800a0d4d  add     rcx, rax
0x1800a0d50  mov     eax, [rsp+198h+NumberOfBytesWritten]
0x1800a0d54  cmp     rax, rcx
0x1800a0d57  jz      loc_1800A0EBD
0x1800a0d5d  mov     rcx, rsi; Block
0x1800a0d60  call    cs:__imp_free
0x1800a0d66  test    rdi, rdi
0x1800a0d69  jz      loc_1800A0EFB
0x1800a0d6f  mov     rcx, rdi
0x1800a0d72  jmp     loc_1800A0EF5
0x1800a0d77  mov     rcx, [rbx+20h]
0x1800a0d7b  mov     rax, [rbx+28h]
0x1800a0d7f  add     rcx, r14
0x1800a0d82  add     rax, 1Fh
0x1800a0d86  add     rcx, rax; Size
0x1800a0d89  call    cs:__imp_malloc
0x1800a0d8f  mov     rsi, rax
0x1800a0d92  test    rax, rax
0x1800a0d95  jz      loc_1800A0F02
0x1800a0d9b  mov     dword ptr [rax], 4034B50h
0x1800a0da1  movzx   eax, word ptr [rbx+2]
0x1800a0da5  movzx   r13d, r15w
0x1800a0da9  test    r15w, r15w
0x1800a0dad  jnz     short loc_1800A0DC7
0x1800a0daf  cmp     ax, 2Dh ; '-'
0x1800a0db3  jb      short loc_1800A0DC7
0x1800a0db5  movzx   eax, word ptr [rbx+6]
0x1800a0db9  sub     ax, 9
0x1800a0dbd  neg     ax
0x1800a0dc0  sbb     ax, ax
0x1800a0dc3  add     ax, 15h
0x1800a0dc7  mov     [rsi+4], ax
0x1800a0dcb  movzx   eax, word ptr [rbx+46h]
0x1800a0dcf  mov     r12d, [rbp+270h]
0x1800a0dd6  mov     [rsi+6], ax
0x1800a0dda  movzx   eax, word ptr [rbx+6]
0x1800a0dde  mov     [rsi+8], ax
0x1800a0de2  mov     eax, [rbx+8]
0x1800a0de5  mov     [rsi+0Ah], eax
0x1800a0de8  mov     eax, [rbx+0Ch]
0x1800a0deb  mov     [rsi+0Eh], eax
0x1800a0dee  test    r12d, r12d
0x1800a0df1  jz      short loc_1800A0E0E
0x1800a0df3  mov     eax, 0FFFFFFFFh
0x1800a0df8  cmp     [rbx+10h], rax
0x1800a0dfc  jg      short loc_1800A0E04
0x1800a0dfe  cmp     [rbx+18h], rax
0x1800a0e02  jle     short loc_1800A0E0E
0x1800a0e04  mov     qword ptr [rsi+12h], 0FFFFFFFFFFFFFFFFh
0x1800a0e0c  jmp     short loc_1800A0E1A
0x1800a0e0e  mov     eax, [rbx+10h]
0x1800a0e11  mov     [rsi+12h], eax
0x1800a0e14  mov     eax, [rbx+18h]
0x1800a0e17  mov     [rsi+16h], eax
0x1800a0e1a  add     r15w, [rbx+28h]
0x1800a0e1f  lea     rcx, [rsi+1Eh]; void *
0x1800a0e23  movzx   eax, word ptr [rbx+20h]
0x1800a0e27  lea     rdx, [rsp+198h+szDst]; Src
0x1800a0e2c  mov     [rsi+1Ah], ax
0x1800a0e30  test    r12d, r12d
0x1800a0e33  cmovz   r15w, [rbx+28h]
0x1800a0e39  mov     [rsi+1Ch], r15w
0x1800a0e3e  mov     r15, [rbx+20h]
0x1800a0e42  mov     r8, r15; Size
0x1800a0e45  call    memcpy_0
0x1800a0e4a  mov     r8, [rbx+28h]; Size
0x1800a0e4e  test    r12d, r12d
0x1800a0e51  jz      short loc_1800A0E5B
0x1800a0e53  add     r8, r14
0x1800a0e56  mov     rdx, rdi
0x1800a0e59  jmp     short loc_1800A0E64
0x1800a0e5b  test    r8, r8
0x1800a0e5e  jz      short loc_1800A0E70
0x1800a0e60  mov     rdx, [rbx+60h]; Src
0x1800a0e64  lea     rcx, [r15+1Eh]
0x1800a0e68  add     rcx, rsi; void *
0x1800a0e6b  call    memcpy_0
0x1800a0e70  mov     ecx, [rbx+20h]
0x1800a0e73  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a0e78  mov     r8d, [rbx+28h]
0x1800a0e7c  add     ecx, r13d
0x1800a0e7f  add     r8d, 1Eh
0x1800a0e83  xor     r13d, r13d
0x1800a0e86  add     r8d, ecx; nNumberOfBytesToWrite
0x1800a0e89  mov     [rsp+198h+lpOverlapped], r13; lpOverlapped
0x1800a0e8e  mov     rcx, [rbp+0D8h]; hFile
0x1800a0e95  mov     rdx, rsi; lpBuffer
0x1800a0e98  call    cs:__imp_WriteFile
0x1800a0e9e  test    eax, eax
0x1800a0ea0  jz      short loc_1800A0EE4
0x1800a0ea2  mov     rcx, [rbx+20h]
0x1800a0ea6  mov     rax, [rbx+28h]
0x1800a0eaa  add     rcx, r14
0x1800a0ead  add     rax, 1Eh
0x1800a0eb1  add     rcx, rax
0x1800a0eb4  mov     eax, [rsp+198h+NumberOfBytesWritten]
0x1800a0eb8  cmp     rax, rcx
0x1800a0ebb  jnz     short loc_1800A0EE4
0x1800a0ebd  mov     rcx, rsi; Block
0x1800a0ec0  call    cs:__imp_free
0x1800a0ec6  test    rdi, rdi
0x1800a0ec9  jz      short loc_1800A0ED6
0x1800a0ecb  mov     rcx, rdi; Block
0x1800a0ece  call    cs:__imp_free
0x1800a0ed4  jmp     short loc_1800A0ED9
0x1800a0ed6  mov     r14, r13
0x1800a0ed9  mov     [rbx+88h], r14
0x1800a0ee0  xor     eax, eax
0x1800a0ee2  jmp     short loc_1800A0F15
0x1800a0ee4  test    rdi, rdi
  ... truncated ...
```
