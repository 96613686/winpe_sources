# putcentral

- ea: `0x1800a4c0c`
- end: `0x1800a5006`
- name: `putcentral`
- size: `1018`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800a3d14`
- `0x1800a8284`

## callees

- `0x18009fa48`
- `0x1800a1f1c`
- `0x1800a4c0c`
- `0x1800cf552`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!free` at `0x1800a4fb1`
- `msvcrt!free` at `0x1800a4fcb`
- `msvcrt!free` at `0x1800a4fb1`
- `msvcrt!free` at `0x1800a4fcb`
- `msvcrt!malloc` at `0x1800a4d26`
- `msvcrt!malloc` at `0x1800a4e8b`
- `msvcrt!malloc` at `0x1800a4d26`
- `msvcrt!malloc` at `0x1800a4e8b`
- `KERNEL32!WriteFile` at `0x1800a4e36`
- `KERNEL32!WriteFile` at `0x1800a4f98`
- `KERNEL32!WriteFile` at `0x1800a4e36`
- `KERNEL32!WriteFile` at `0x1800a4f98`
- `USER32!CharToOemBuffA` at `0x1800a4c81`
- `USER32!CharToOemBuffA` at `0x1800a4c81`

## pseudocode

```c
__int64 __fastcall putcentral(__int16 *a1, HANDLE *a2, __int64 a3)
{
  const CHAR *v6; // rcx
  DWORD v7; // r8d
  __int64 v8; // rax
  __int64 result; // rax
  int v10; // eax
  size_t v11; // r14
  size_t v12; // r15
  __int64 v13; // rbp
  _DWORD *v14; // rax
  _DWORD *v15; // rsi
  __int16 v16; // cx
  __int16 v17; // ax
  unsigned __int16 v18; // ax
  size_t v19; // r8
  void *v20; // rcx
  void *v21; // rcx
  _DWORD *v22; // rax
  _DWORD *v23; // rdi
  __int16 v24; // cx
  __int16 v25; // ax
  unsigned __int16 v26; // ax
  size_t v27; // r14
  size_t v28; // r8
  size_t v29; // r8
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-168h] BYREF
  CHAR szDst[272]; // [rsp+40h] [rbp-158h] BYREF

  NumberOfBytesWritten = 0;
  if ( *(_DWORD *)(a3 + 620) )
  {
    StringCchCopyA(szDst, 0x104u, *((STRSAFE_LPCSTR *)a1 + 15));
  }
  else
  {
    v6 = (const CHAR *)*((_QWORD *)a1 + 15);
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
  if ( !*(_DWORD *)(a3 + 624) )
  {
    if ( *(__int16 *)(a3 + 3740) >= 0 )
    {
LABEL_16:
      v11 = *((_QWORD *)a1 + 4);
      v12 = *((_QWORD *)a1 + 6);
      v13 = v12 + v11 + *((_QWORD *)a1 + 7) + 46LL;
      if ( *(_QWORD *)(a3 + 216) == -1 || *(_DWORD *)(a3 + 3792) )
      {
        if ( (unsigned int)PromptForNewDisk(0, a2, v12 + v11 + *((_QWORD *)a1 + 7) + 46LL, a3) )
          return *(_DWORD *)(a3 + 208) != 0 ? 9 : 19;
        v22 = malloc((int)v13 + 1);
        v23 = v22;
        if ( !v22 )
          return 10;
        v24 = a1[3];
        *v22 = 33639248;
        v25 = *a1;
        if ( (unsigned __int16)*a1 >= 0x2Du )
          v25 = 21 - (v24 != 9);
        *((_WORD *)v23 + 2) = v25;
        v26 = a1[1];
        if ( v26 >= 0x2Du )
          v26 = 21 - (v24 != 9);
        *((_WORD *)v23 + 3) = v26;
        v27 = *((_QWORD *)a1 + 4);
        *((_WORD *)v23 + 4) = a1[2];
        *((_WORD *)v23 + 5) = a1[3];
        v23[3] = *((_DWORD *)a1 + 2);
        v23[4] = *((_DWORD *)a1 + 3);
        v23[6] = *((_DWORD *)a1 + 6);
        v23[5] = *((_DWORD *)a1 + 4);
        *(_DWORD *)((char *)v23 + 42) = *((_DWORD *)a1 + 20);
        *((_WORD *)v23 + 14) = a1[16];
        *((_WORD *)v23 + 15) = a1[24];
        *((_WORD *)v23 + 16) = a1[28];
        *((_WORD *)v23 + 17) = a1[32];
        *((_WORD *)v23 + 18) = a1[34];
        *(_DWORD *)((char *)v23 + 38) = *((_DWORD *)a1 + 18);
        memcpy_0((char *)v23 + 46, szDst, v27);
        v28 = *((_QWORD *)a1 + 6);
        if ( v28 )
          memcpy_0((char *)v23 + v27 + 46, *((const void **)a1 + 13), v28);
        v29 = *((_QWORD *)a1 + 7);
        if ( v29 )
          memcpy_0((char *)v23 + *((_QWORD *)a1 + 6) + *((_QWORD *)a1 + 4) + 46, *((const void **)a1 + 14), v29);
        if ( WriteFile(*a2, v23, v13, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == (_DWORD)v13 )
        {
          v20 = v23;
          goto LABEL_45;
        }
        v21 = v23;
      }
      else
      {
        v14 = malloc((int)v13 + 1);
        v15 = v14;
        if ( !v14 )
          return 10;
        v16 = a1[3];
        *v14 = 33639248;
        v17 = *a1;
        if ( (unsigned __int16)*a1 >= 0x2Du )
          v17 = 21 - (v16 != 9);
        *((_WORD *)v15 + 2) = v17;
        v18 = a1[1];
        if ( v18 >= 0x2Du )
          v18 = 21 - (v16 != 9);
        *((_WORD *)v15 + 3) = v18;
        *((_WORD *)v15 + 4) = a1[2];
        *((_WORD *)v15 + 5) = a1[3];
        v15[3] = *((_DWORD *)a1 + 2);
        v15[4] = *((_DWORD *)a1 + 3);
        v15[6] = *((_DWORD *)a1 + 6);
        v15[5] = *((_DWORD *)a1 + 4);
        *(_DWORD *)((char *)v15 + 42) = *((_DWORD *)a1 + 20);
        *((_WORD *)v15 + 14) = a1[16];
        *((_WORD *)v15 + 15) = a1[24];
        *((_WORD *)v15 + 16) = a1[28];
        *((_WORD *)v15 + 17) = a1[32];
        *((_WORD *)v15 + 18) = a1[34];
        *(_DWORD *)((char *)v15 + 38) = *((_DWORD *)a1 + 18);
        memcpy_0((char *)v15 + 46, szDst, v11);
        if ( *((_QWORD *)a1 + 6) )
          memcpy_0((char *)v15 + v11 + 46, *((const void **)a1 + 13), v12);
        v19 = *((_QWORD *)a1 + 7);
        if ( v19 )
          memcpy_0((char *)v15 + *((_QWORD *)a1 + 4) + *((_QWORD *)a1 + 6) + 46, *((const void **)a1 + 14), v19);
        if ( WriteFile(*(HANDLE *)(a3 + 216), v15, v13, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == (_DWORD)v13 )
        {
          v20 = v15;
LABEL_45:
          free(v20);
          result = 0;
          *((_QWORD *)a1 + 18) = 0;
          return result;
        }
        v21 = v15;
      }
      free(v21);
      return 10;
    }
    v10 = *(_DWORD *)(a3 + 3744);
    if ( *(_DWORD *)(a3 + 3748) == 0xFFFF )
    {
      *(_DWORD *)(a3 + 3748) = v10;
    }
    else if ( v10 == *(_DWORD *)(a3 + 3752) )
    {
LABEL_15:
      ++*(_DWORD *)(a3 + 3760);
      goto LABEL_16;
    }
    *(_DWORD *)(a3 + 3760) = 0;
    *(_DWORD *)(a3 + 3752) = v10;
    goto LABEL_15;
  }
  return 9;
}

```

## disassembly

```asm
0x1800a4c0c  push    rbx
0x1800a4c0e  push    rbp
0x1800a4c0f  push    rsi
0x1800a4c10  push    rdi
0x1800a4c11  push    r12
0x1800a4c13  push    r14
0x1800a4c15  push    r15
0x1800a4c17  sub     rsp, 160h
0x1800a4c1e  mov     rax, cs:__security_cookie
0x1800a4c25  xor     rax, rsp
0x1800a4c28  mov     [rsp+198h+var_48], rax
0x1800a4c30  xor     r12d, r12d
0x1800a4c33  mov     rdi, r8
0x1800a4c36  mov     rsi, rdx
0x1800a4c39  mov     rbx, rcx
0x1800a4c3c  mov     [rsp+198h+NumberOfBytesWritten], r12d
0x1800a4c41  cmp     [r8+26Ch], r12d
0x1800a4c48  jnz     short loc_1800A4C8F
0x1800a4c4a  mov     rcx, [rcx+78h]; lpszSrc
0x1800a4c4e  lea     r8d, [r12+1]; cchDstLength
0x1800a4c53  test    rcx, rcx
0x1800a4c56  jz      short loc_1800A4C7C
0x1800a4c58  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a4c5c  inc     rax
0x1800a4c5f  cmp     [rcx+rax], r12b
0x1800a4c63  jnz     short loc_1800A4C5C
0x1800a4c65  lea     r8d, [rax+1]
0x1800a4c69  cmp     r8d, 104h
0x1800a4c70  jbe     short loc_1800A4C7C
0x1800a4c72  mov     eax, 0Eh
0x1800a4c77  jmp     loc_1800A4FE3
0x1800a4c7c  lea     rdx, [rsp+198h+szDst]; lpszDst
0x1800a4c81  call    cs:__imp_CharToOemBuffA
0x1800a4c88  nop     dword ptr [rax+rax+00h]
0x1800a4c8d  jmp     short loc_1800A4CA2
0x1800a4c8f  mov     r8, [rcx+78h]; pszSrc
0x1800a4c93  mov     edx, 104h; cchDest
0x1800a4c98  lea     rcx, [rsp+198h+szDst]; pszDest
0x1800a4c9d  call    StringCchCopyA
0x1800a4ca2  cmp     [rdi+270h], r12d
0x1800a4ca9  jnz     loc_1800A4FDE
0x1800a4caf  cmp     [rdi+0E9Ch], r12w
0x1800a4cb7  jge     short loc_1800A4CEE
0x1800a4cb9  cmp     dword ptr [rdi+0EA4h], 0FFFFh
0x1800a4cc3  mov     eax, [rdi+0EA0h]
0x1800a4cc9  jnz     short loc_1800A4CD3
0x1800a4ccb  mov     [rdi+0EA4h], eax
0x1800a4cd1  jmp     short loc_1800A4CDB
0x1800a4cd3  cmp     eax, [rdi+0EA8h]
0x1800a4cd9  jz      short loc_1800A4CE8
0x1800a4cdb  mov     [rdi+0EB0h], r12d
0x1800a4ce2  mov     [rdi+0EA8h], eax
0x1800a4ce8  inc     dword ptr [rdi+0EB0h]
0x1800a4cee  mov     r14, [rbx+20h]
0x1800a4cf2  mov     r15, [rbx+30h]
0x1800a4cf6  mov     rbp, [rbx+38h]
0x1800a4cfa  add     rbp, 2Eh ; '.'
0x1800a4cfe  lea     rcx, [r15+r14]
0x1800a4d02  add     rbp, rcx
0x1800a4d05  cmp     qword ptr [rdi+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a4d0d  jz      loc_1800A4E5C
0x1800a4d13  cmp     [rdi+0ED0h], r12d
0x1800a4d1a  jnz     loc_1800A4E5C
0x1800a4d20  lea     eax, [rbp+1]
0x1800a4d23  movsxd  rcx, eax; Size
0x1800a4d26  call    cs:__imp_malloc
0x1800a4d2d  nop     dword ptr [rax+rax+00h]
0x1800a4d32  mov     rsi, rax
0x1800a4d35  test    rax, rax
0x1800a4d38  jz      loc_1800A4FD7
0x1800a4d3e  movzx   ecx, word ptr [rbx+6]
0x1800a4d42  mov     r8, r14; Size
0x1800a4d45  mov     dword ptr [rax], 2014B50h
0x1800a4d4b  sub     cx, 9
0x1800a4d4f  movzx   eax, word ptr [rbx]
0x1800a4d52  neg     cx
0x1800a4d55  lea     rcx, [rsi+2Eh]; void *
0x1800a4d59  sbb     dx, dx
0x1800a4d5c  add     dx, 15h
0x1800a4d60  cmp     ax, 2Dh ; '-'
0x1800a4d64  cmovnb  ax, dx
0x1800a4d68  mov     [rsi+4], ax
0x1800a4d6c  movzx   eax, word ptr [rbx+2]
0x1800a4d70  cmp     ax, 2Dh ; '-'
0x1800a4d74  cmovnb  ax, dx
0x1800a4d78  lea     rdx, [rsp+198h+szDst]; Src
0x1800a4d7d  mov     [rsi+6], ax
0x1800a4d81  movzx   eax, word ptr [rbx+4]
0x1800a4d85  mov     [rsi+8], ax
0x1800a4d89  movzx   eax, word ptr [rbx+6]
0x1800a4d8d  mov     [rsi+0Ah], ax
0x1800a4d91  mov     eax, [rbx+8]
0x1800a4d94  mov     [rsi+0Ch], eax
0x1800a4d97  mov     eax, [rbx+0Ch]
0x1800a4d9a  mov     [rsi+10h], eax
0x1800a4d9d  mov     eax, [rbx+18h]
0x1800a4da0  mov     [rsi+18h], eax
0x1800a4da3  mov     eax, [rbx+10h]
0x1800a4da6  mov     [rsi+14h], eax
0x1800a4da9  mov     eax, [rbx+50h]
0x1800a4dac  mov     [rsi+2Ah], eax
0x1800a4daf  movzx   eax, word ptr [rbx+20h]
0x1800a4db3  mov     [rsi+1Ch], ax
0x1800a4db7  movzx   eax, word ptr [rbx+30h]
0x1800a4dbb  mov     [rsi+1Eh], ax
0x1800a4dbf  movzx   eax, word ptr [rbx+38h]
0x1800a4dc3  mov     [rsi+20h], ax
0x1800a4dc7  movzx   eax, word ptr [rbx+40h]
0x1800a4dcb  mov     [rsi+22h], ax
0x1800a4dcf  movzx   eax, word ptr [rbx+44h]
0x1800a4dd3  mov     [rsi+24h], ax
0x1800a4dd7  mov     eax, [rbx+48h]
0x1800a4dda  mov     [rsi+26h], eax
0x1800a4ddd  call    memcpy_0
0x1800a4de2  cmp     [rbx+30h], r12
0x1800a4de6  jbe     short loc_1800A4DFB
0x1800a4de8  mov     rdx, [rbx+68h]; Src
0x1800a4dec  lea     rcx, [r14+2Eh]
0x1800a4df0  add     rcx, rsi; void *
0x1800a4df3  mov     r8, r15; Size
0x1800a4df6  call    memcpy_0
0x1800a4dfb  mov     r8, [rbx+38h]; Size
0x1800a4dff  test    r8, r8
0x1800a4e02  jz      short loc_1800A4E1F
0x1800a4e04  mov     rcx, [rbx+20h]
0x1800a4e08  mov     rax, [rbx+30h]
0x1800a4e0c  add     rcx, rsi
0x1800a4e0f  mov     rdx, [rbx+70h]; Src
0x1800a4e13  add     rax, 2Eh ; '.'
0x1800a4e17  add     rcx, rax; void *
0x1800a4e1a  call    memcpy_0
0x1800a4e1f  mov     rcx, [rdi+0D8h]; hFile
0x1800a4e26  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a4e2b  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800a4e2e  mov     [rsp+198h+lpOverlapped], r12; lpOverlapped
0x1800a4e33  mov     rdx, rsi; lpBuffer
0x1800a4e36  call    cs:__imp_WriteFile
0x1800a4e3d  nop     dword ptr [rax+rax+00h]
0x1800a4e42  test    eax, eax
0x1800a4e44  jz      short loc_1800A4E54
0x1800a4e46  cmp     [rsp+198h+NumberOfBytesWritten], ebp
0x1800a4e4a  jnz     short loc_1800A4E54
0x1800a4e4c  mov     rcx, rsi
0x1800a4e4f  jmp     loc_1800A4FB1
0x1800a4e54  mov     rcx, rsi
0x1800a4e57  jmp     loc_1800A4FCB
0x1800a4e5c  mov     r9, rdi
0x1800a4e5f  mov     r8, rbp
0x1800a4e62  mov     rdx, rsi
0x1800a4e65  xor     ecx, ecx
0x1800a4e67  call    PromptForNewDisk
0x1800a4e6c  test    eax, eax
0x1800a4e6e  jz      short loc_1800A4E85
0x1800a4e70  mov     eax, [rdi+0D0h]
0x1800a4e76  neg     eax
0x1800a4e78  sbb     eax, eax
0x1800a4e7a  and     eax, 0FFFFFFF6h
0x1800a4e7d  add     eax, 13h
0x1800a4e80  jmp     loc_1800A4FE3
0x1800a4e85  lea     eax, [rbp+1]
0x1800a4e88  movsxd  rcx, eax; Size
0x1800a4e8b  call    cs:__imp_malloc
0x1800a4e92  nop     dword ptr [rax+rax+00h]
0x1800a4e97  mov     rdi, rax
0x1800a4e9a  test    rax, rax
0x1800a4e9d  jz      loc_1800A4FD7
0x1800a4ea3  movzx   ecx, word ptr [rbx+6]
0x1800a4ea7  mov     dword ptr [rax], 2014B50h
0x1800a4ead  sub     cx, 9
0x1800a4eb1  movzx   eax, word ptr [rbx]
0x1800a4eb4  neg     cx
0x1800a4eb7  lea     rcx, [rdi+2Eh]; void *
0x1800a4ebb  sbb     dx, dx
0x1800a4ebe  add     dx, 15h
0x1800a4ec2  cmp     ax, 2Dh ; '-'
0x1800a4ec6  cmovnb  ax, dx
0x1800a4eca  mov     [rdi+4], ax
0x1800a4ece  movzx   eax, word ptr [rbx+2]
0x1800a4ed2  cmp     ax, 2Dh ; '-'
0x1800a4ed6  cmovnb  ax, dx
0x1800a4eda  lea     rdx, [rsp+198h+szDst]; Src
0x1800a4edf  mov     [rdi+6], ax
0x1800a4ee3  movzx   eax, word ptr [rbx+4]
0x1800a4ee7  mov     r14, [rbx+20h]
0x1800a4eeb  mov     [rdi+8], ax
0x1800a4eef  mov     r8, r14; Size
0x1800a4ef2  movzx   eax, word ptr [rbx+6]
0x1800a4ef6  mov     [rdi+0Ah], ax
0x1800a4efa  mov     eax, [rbx+8]
0x1800a4efd  mov     [rdi+0Ch], eax
0x1800a4f00  mov     eax, [rbx+0Ch]
0x1800a4f03  mov     [rdi+10h], eax
0x1800a4f06  mov     eax, [rbx+18h]
0x1800a4f09  mov     [rdi+18h], eax
0x1800a4f0c  mov     eax, [rbx+10h]
0x1800a4f0f  mov     [rdi+14h], eax
0x1800a4f12  mov     eax, [rbx+50h]
0x1800a4f15  mov     [rdi+2Ah], eax
0x1800a4f18  movzx   eax, word ptr [rbx+20h]
0x1800a4f1c  mov     [rdi+1Ch], ax
0x1800a4f20  movzx   eax, word ptr [rbx+30h]
0x1800a4f24  mov     [rdi+1Eh], ax
0x1800a4f28  movzx   eax, word ptr [rbx+38h]
0x1800a4f2c  mov     [rdi+20h], ax
0x1800a4f30  movzx   eax, word ptr [rbx+40h]
0x1800a4f34  mov     [rdi+22h], ax
0x1800a4f38  movzx   eax, word ptr [rbx+44h]
0x1800a4f3c  mov     [rdi+24h], ax
0x1800a4f40  mov     eax, [rbx+48h]
0x1800a4f43  mov     [rdi+26h], eax
0x1800a4f46  call    memcpy_0
0x1800a4f4b  mov     r8, [rbx+30h]; Size
0x1800a4f4f  test    r8, r8
0x1800a4f52  jz      short loc_1800A4F64
0x1800a4f54  mov     rdx, [rbx+68h]; Src
0x1800a4f58  lea     rcx, [r14+2Eh]
0x1800a4f5c  add     rcx, rdi; void *
0x1800a4f5f  call    memcpy_0
0x1800a4f64  mov     r8, [rbx+38h]; Size
0x1800a4f68  test    r8, r8
0x1800a4f6b  jz      short loc_1800A4F85
0x1800a4f6d  mov     rcx, [rbx+20h]
0x1800a4f71  mov     rdx, [rbx+70h]; Src
0x1800a4f75  add     rcx, 2Eh ; '.'
0x1800a4f79  add     rcx, [rbx+30h]
0x1800a4f7d  add     rcx, rdi; void *
0x1800a4f80  call    memcpy_0
0x1800a4f85  mov     rcx, [rsi]; hFile
0x1800a4f88  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a4f8d  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800a4f90  mov     [rsp+198h+lpOverlapped], r12; lpOverlapped
0x1800a4f95  mov     rdx, rdi; lpBuffer
0x1800a4f98  call    cs:__imp_WriteFile
0x1800a4f9f  nop     dword ptr [rax+rax+00h]
0x1800a4fa4  test    eax, eax
0x1800a4fa6  jz      short loc_1800A4FC8
0x1800a4fa8  cmp     [rsp+198h+NumberOfBytesWritten], ebp
0x1800a4fac  jnz     short loc_1800A4FC8
0x1800a4fae  mov     rcx, rdi; Block
0x1800a4fb1  call    cs:__imp_free
0x1800a4fb8  nop     dword ptr [rax+rax+00h]
0x1800a4fbd  xor     eax, eax
0x1800a4fbf  mov     [rbx+90h], r12
0x1800a4fc6  jmp     short loc_1800A4FE3
0x1800a4fc8  mov     rcx, rdi; Block
0x1800a4fcb  call    cs:__imp_free
0x1800a4fd2  nop     dword ptr [rax+rax+00h]
0x1800a4fd7  mov     eax, 0Ah
0x1800a4fdc  jmp     short loc_1800A4FE3
0x1800a4fde  mov     eax, 9
0x1800a4fe3  mov     rcx, [rsp+198h+var_48]
0x1800a4feb  xor     rcx, rsp; StackCookie
0x1800a4fee  call    __security_check_cookie
0x1800a4ff3  add     rsp, 160h
0x1800a4ffa  pop     r15
0x1800a4ffc  pop     r14
0x1800a4ffe  pop     r12
0x1800a5000  pop     rdi
0x1800a5001  pop     rsi
0x1800a5002  pop     rbp
0x1800a5003  pop     rbx
0x1800a5004  retn
```
