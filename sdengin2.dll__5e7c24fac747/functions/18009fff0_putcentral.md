# putcentral

- ea: `0x18009fff0`
- end: `0x1800a03bf`
- name: `putcentral`
- size: `975`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18009f200`
- `0x1800a3378`

## callees

- `0x18009b2f0`
- `0x18009d5e4`
- `0x18009fff0`
- `0x1800c97c2`
- `0x1800c9830`

## import_xrefs

- `msvcrt!free` at `0x1800a0377`
- `msvcrt!free` at `0x1800a038b`
- `msvcrt!free` at `0x1800a0377`
- `msvcrt!free` at `0x1800a038b`
- `msvcrt!malloc` at `0x1800a0104`
- `msvcrt!malloc` at `0x1800a025d`
- `msvcrt!malloc` at `0x1800a0104`
- `msvcrt!malloc` at `0x1800a025d`
- `KERNEL32!WriteFile` at `0x1800a020e`
- `KERNEL32!WriteFile` at `0x1800a0364`
- `KERNEL32!WriteFile` at `0x1800a020e`
- `KERNEL32!WriteFile` at `0x1800a0364`
- `USER32!CharToOemBuffA` at `0x1800a0065`
- `USER32!CharToOemBuffA` at `0x1800a0065`

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
0x18009fff0  push    rbx
0x18009fff2  push    rbp
0x18009fff3  push    rsi
0x18009fff4  push    rdi
0x18009fff5  push    r12
0x18009fff7  push    r14
0x18009fff9  push    r15
0x18009fffb  sub     rsp, 160h
0x1800a0002  mov     rax, cs:__security_cookie
0x1800a0009  xor     rax, rsp
0x1800a000c  mov     [rsp+198h+var_48], rax
0x1800a0014  xor     r12d, r12d
0x1800a0017  mov     rdi, r8
0x1800a001a  mov     rsi, rdx
0x1800a001d  mov     rbx, rcx
0x1800a0020  mov     [rsp+198h+NumberOfBytesWritten], r12d
0x1800a0025  cmp     [r8+26Ch], r12d
0x1800a002c  jnz     short loc_1800A006D
0x1800a002e  mov     rcx, [rcx+78h]; lpszSrc
0x1800a0032  lea     r8d, [r12+1]; cchDstLength
0x1800a0037  test    rcx, rcx
0x1800a003a  jz      short loc_1800A0060
0x1800a003c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a0040  inc     rax
0x1800a0043  cmp     [rcx+rax], r12b
0x1800a0047  jnz     short loc_1800A0040
0x1800a0049  lea     r8d, [rax+1]
0x1800a004d  cmp     r8d, 104h
0x1800a0054  jbe     short loc_1800A0060
0x1800a0056  mov     eax, 0Eh
0x1800a005b  jmp     loc_1800A039D
0x1800a0060  lea     rdx, [rsp+198h+szDst]; lpszDst
0x1800a0065  call    cs:__imp_CharToOemBuffA
0x1800a006b  jmp     short loc_1800A0080
0x1800a006d  mov     r8, [rcx+78h]; pszSrc
0x1800a0071  mov     edx, 104h; cchDest
0x1800a0076  lea     rcx, [rsp+198h+szDst]; pszDest
0x1800a007b  call    StringCchCopyA
0x1800a0080  cmp     [rdi+270h], r12d
0x1800a0087  jnz     loc_1800A0398
0x1800a008d  cmp     [rdi+0E9Ch], r12w
0x1800a0095  jge     short loc_1800A00CC
0x1800a0097  cmp     dword ptr [rdi+0EA4h], 0FFFFh
0x1800a00a1  mov     eax, [rdi+0EA0h]
0x1800a00a7  jnz     short loc_1800A00B1
0x1800a00a9  mov     [rdi+0EA4h], eax
0x1800a00af  jmp     short loc_1800A00B9
0x1800a00b1  cmp     eax, [rdi+0EA8h]
0x1800a00b7  jz      short loc_1800A00C6
0x1800a00b9  mov     [rdi+0EB0h], r12d
0x1800a00c0  mov     [rdi+0EA8h], eax
0x1800a00c6  inc     dword ptr [rdi+0EB0h]
0x1800a00cc  mov     r14, [rbx+20h]
0x1800a00d0  mov     r15, [rbx+30h]
0x1800a00d4  mov     rbp, [rbx+38h]
0x1800a00d8  add     rbp, 2Eh ; '.'
0x1800a00dc  lea     rcx, [r15+r14]
0x1800a00e0  add     rbp, rcx
0x1800a00e3  cmp     qword ptr [rdi+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a00eb  jz      loc_1800A022E
0x1800a00f1  cmp     [rdi+0ED0h], r12d
0x1800a00f8  jnz     loc_1800A022E
0x1800a00fe  lea     eax, [rbp+1]
0x1800a0101  movsxd  rcx, eax; Size
0x1800a0104  call    cs:__imp_malloc
0x1800a010a  mov     rsi, rax
0x1800a010d  test    rax, rax
0x1800a0110  jz      loc_1800A0391
0x1800a0116  movzx   ecx, word ptr [rbx+6]
0x1800a011a  mov     r8, r14; Size
0x1800a011d  mov     dword ptr [rax], 2014B50h
0x1800a0123  sub     cx, 9
0x1800a0127  movzx   eax, word ptr [rbx]
0x1800a012a  neg     cx
0x1800a012d  lea     rcx, [rsi+2Eh]; void *
0x1800a0131  sbb     dx, dx
0x1800a0134  add     dx, 15h
0x1800a0138  cmp     ax, 2Dh ; '-'
0x1800a013c  cmovnb  ax, dx
0x1800a0140  mov     [rsi+4], ax
0x1800a0144  movzx   eax, word ptr [rbx+2]
0x1800a0148  cmp     ax, 2Dh ; '-'
0x1800a014c  cmovnb  ax, dx
0x1800a0150  lea     rdx, [rsp+198h+szDst]; Src
0x1800a0155  mov     [rsi+6], ax
0x1800a0159  movzx   eax, word ptr [rbx+4]
0x1800a015d  mov     [rsi+8], ax
0x1800a0161  movzx   eax, word ptr [rbx+6]
0x1800a0165  mov     [rsi+0Ah], ax
0x1800a0169  mov     eax, [rbx+8]
0x1800a016c  mov     [rsi+0Ch], eax
0x1800a016f  mov     eax, [rbx+0Ch]
0x1800a0172  mov     [rsi+10h], eax
0x1800a0175  mov     eax, [rbx+18h]
0x1800a0178  mov     [rsi+18h], eax
0x1800a017b  mov     eax, [rbx+10h]
0x1800a017e  mov     [rsi+14h], eax
0x1800a0181  mov     eax, [rbx+50h]
0x1800a0184  mov     [rsi+2Ah], eax
0x1800a0187  movzx   eax, word ptr [rbx+20h]
0x1800a018b  mov     [rsi+1Ch], ax
0x1800a018f  movzx   eax, word ptr [rbx+30h]
0x1800a0193  mov     [rsi+1Eh], ax
0x1800a0197  movzx   eax, word ptr [rbx+38h]
0x1800a019b  mov     [rsi+20h], ax
0x1800a019f  movzx   eax, word ptr [rbx+40h]
0x1800a01a3  mov     [rsi+22h], ax
0x1800a01a7  movzx   eax, word ptr [rbx+44h]
0x1800a01ab  mov     [rsi+24h], ax
0x1800a01af  mov     eax, [rbx+48h]
0x1800a01b2  mov     [rsi+26h], eax
0x1800a01b5  call    memcpy_0
0x1800a01ba  cmp     [rbx+30h], r12
0x1800a01be  jbe     short loc_1800A01D3
0x1800a01c0  mov     rdx, [rbx+68h]; Src
0x1800a01c4  lea     rcx, [r14+2Eh]
0x1800a01c8  add     rcx, rsi; void *
0x1800a01cb  mov     r8, r15; Size
0x1800a01ce  call    memcpy_0
0x1800a01d3  mov     r8, [rbx+38h]; Size
0x1800a01d7  test    r8, r8
0x1800a01da  jz      short loc_1800A01F7
0x1800a01dc  mov     rcx, [rbx+20h]
0x1800a01e0  mov     rax, [rbx+30h]
0x1800a01e4  add     rcx, rsi
0x1800a01e7  mov     rdx, [rbx+70h]; Src
0x1800a01eb  add     rax, 2Eh ; '.'
0x1800a01ef  add     rcx, rax; void *
0x1800a01f2  call    memcpy_0
0x1800a01f7  mov     rcx, [rdi+0D8h]; hFile
0x1800a01fe  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a0203  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800a0206  mov     [rsp+198h+lpOverlapped], r12; lpOverlapped
0x1800a020b  mov     rdx, rsi; lpBuffer
0x1800a020e  call    cs:__imp_WriteFile
0x1800a0214  test    eax, eax
0x1800a0216  jz      short loc_1800A0226
0x1800a0218  cmp     [rsp+198h+NumberOfBytesWritten], ebp
0x1800a021c  jnz     short loc_1800A0226
0x1800a021e  mov     rcx, rsi
0x1800a0221  jmp     loc_1800A0377
0x1800a0226  mov     rcx, rsi
0x1800a0229  jmp     loc_1800A038B
0x1800a022e  mov     r9, rdi
0x1800a0231  mov     r8, rbp
0x1800a0234  mov     rdx, rsi
0x1800a0237  xor     ecx, ecx
0x1800a0239  call    PromptForNewDisk
0x1800a023e  test    eax, eax
0x1800a0240  jz      short loc_1800A0257
0x1800a0242  mov     eax, [rdi+0D0h]
0x1800a0248  neg     eax
0x1800a024a  sbb     eax, eax
0x1800a024c  and     eax, 0FFFFFFF6h
0x1800a024f  add     eax, 13h
0x1800a0252  jmp     loc_1800A039D
0x1800a0257  lea     eax, [rbp+1]
0x1800a025a  movsxd  rcx, eax; Size
0x1800a025d  call    cs:__imp_malloc
0x1800a0263  mov     rdi, rax
0x1800a0266  test    rax, rax
0x1800a0269  jz      loc_1800A0391
0x1800a026f  movzx   ecx, word ptr [rbx+6]
0x1800a0273  mov     dword ptr [rax], 2014B50h
0x1800a0279  sub     cx, 9
0x1800a027d  movzx   eax, word ptr [rbx]
0x1800a0280  neg     cx
0x1800a0283  lea     rcx, [rdi+2Eh]; void *
0x1800a0287  sbb     dx, dx
0x1800a028a  add     dx, 15h
0x1800a028e  cmp     ax, 2Dh ; '-'
0x1800a0292  cmovnb  ax, dx
0x1800a0296  mov     [rdi+4], ax
0x1800a029a  movzx   eax, word ptr [rbx+2]
0x1800a029e  cmp     ax, 2Dh ; '-'
0x1800a02a2  cmovnb  ax, dx
0x1800a02a6  lea     rdx, [rsp+198h+szDst]; Src
0x1800a02ab  mov     [rdi+6], ax
0x1800a02af  movzx   eax, word ptr [rbx+4]
0x1800a02b3  mov     r14, [rbx+20h]
0x1800a02b7  mov     [rdi+8], ax
0x1800a02bb  mov     r8, r14; Size
0x1800a02be  movzx   eax, word ptr [rbx+6]
0x1800a02c2  mov     [rdi+0Ah], ax
0x1800a02c6  mov     eax, [rbx+8]
0x1800a02c9  mov     [rdi+0Ch], eax
0x1800a02cc  mov     eax, [rbx+0Ch]
0x1800a02cf  mov     [rdi+10h], eax
0x1800a02d2  mov     eax, [rbx+18h]
0x1800a02d5  mov     [rdi+18h], eax
0x1800a02d8  mov     eax, [rbx+10h]
0x1800a02db  mov     [rdi+14h], eax
0x1800a02de  mov     eax, [rbx+50h]
0x1800a02e1  mov     [rdi+2Ah], eax
0x1800a02e4  movzx   eax, word ptr [rbx+20h]
0x1800a02e8  mov     [rdi+1Ch], ax
0x1800a02ec  movzx   eax, word ptr [rbx+30h]
0x1800a02f0  mov     [rdi+1Eh], ax
0x1800a02f4  movzx   eax, word ptr [rbx+38h]
0x1800a02f8  mov     [rdi+20h], ax
0x1800a02fc  movzx   eax, word ptr [rbx+40h]
0x1800a0300  mov     [rdi+22h], ax
0x1800a0304  movzx   eax, word ptr [rbx+44h]
0x1800a0308  mov     [rdi+24h], ax
0x1800a030c  mov     eax, [rbx+48h]
0x1800a030f  mov     [rdi+26h], eax
0x1800a0312  call    memcpy_0
0x1800a0317  mov     r8, [rbx+30h]; Size
0x1800a031b  test    r8, r8
0x1800a031e  jz      short loc_1800A0330
0x1800a0320  mov     rdx, [rbx+68h]; Src
0x1800a0324  lea     rcx, [r14+2Eh]
0x1800a0328  add     rcx, rdi; void *
0x1800a032b  call    memcpy_0
0x1800a0330  mov     r8, [rbx+38h]; Size
0x1800a0334  test    r8, r8
0x1800a0337  jz      short loc_1800A0351
0x1800a0339  mov     rcx, [rbx+20h]
0x1800a033d  mov     rdx, [rbx+70h]; Src
0x1800a0341  add     rcx, 2Eh ; '.'
0x1800a0345  add     rcx, [rbx+30h]
0x1800a0349  add     rcx, rdi; void *
0x1800a034c  call    memcpy_0
0x1800a0351  mov     rcx, [rsi]; hFile
0x1800a0354  lea     r9, [rsp+198h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a0359  mov     r8d, ebp; nNumberOfBytesToWrite
0x1800a035c  mov     [rsp+198h+lpOverlapped], r12; lpOverlapped
0x1800a0361  mov     rdx, rdi; lpBuffer
0x1800a0364  call    cs:__imp_WriteFile
0x1800a036a  test    eax, eax
0x1800a036c  jz      short loc_1800A0388
0x1800a036e  cmp     [rsp+198h+NumberOfBytesWritten], ebp
0x1800a0372  jnz     short loc_1800A0388
0x1800a0374  mov     rcx, rdi; Block
0x1800a0377  call    cs:__imp_free
0x1800a037d  xor     eax, eax
0x1800a037f  mov     [rbx+90h], r12
0x1800a0386  jmp     short loc_1800A039D
0x1800a0388  mov     rcx, rdi; Block
0x1800a038b  call    cs:__imp_free
0x1800a0391  mov     eax, 0Ah
0x1800a0396  jmp     short loc_1800A039D
0x1800a0398  mov     eax, 9
0x1800a039d  mov     rcx, [rsp+198h+var_48]
0x1800a03a5  xor     rcx, rsp; StackCookie
0x1800a03a8  call    __security_check_cookie
0x1800a03ad  add     rsp, 160h
0x1800a03b4  pop     r15
0x1800a03b6  pop     r14
0x1800a03b8  pop     r12
0x1800a03ba  pop     rdi
0x1800a03bb  pop     rsi
0x1800a03bc  pop     rbp
0x1800a03bd  pop     rbx
0x1800a03be  retn
```
