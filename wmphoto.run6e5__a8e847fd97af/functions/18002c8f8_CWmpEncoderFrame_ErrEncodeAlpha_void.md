# CWmpEncoderFrame::ErrEncodeAlpha(void)

- ea: `0x18002c8f8`
- end: `0x18002cc2d`
- name: `?ErrEncodeAlpha@CWmpEncoderFrame@@IEAAJXZ`
- size: `821`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18002bfd0`

## callees

- `0x1800211c4`
- `0x1800219b0`
- `0x180029d10`
- `0x180029d48`
- `0x180029d8c`
- `0x18002c8f8`
- `0x18002dbd0`
- `0x1800309d0`
- `0x180043630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca46`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002caff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002caff`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ca35`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002ca35`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::ErrEncodeAlpha(CWmpEncoderFrame *this)
{
  int v1; // ebx
  unsigned int *v3; // r13
  struct WMPStream *v4; // r14
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  void **v12; // r12
  __int64 v13; // rax
  void *v14; // rcx
  unsigned int v15; // edi
  int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // r15d
  ULONGLONG v19; // rcx
  unsigned int v20; // eax
  ULONGLONG v21; // r9
  int v22; // ebx
  CWmpEncoderFrame *v23; // rcx
  unsigned int v25; // eax
  __int64 v26; // rcx
  unsigned int v27; // r15d
  ULONGLONG v28; // rdx
  unsigned int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // r12
  __int64 v32; // [rsp+30h] [rbp-20h] BYREF
  __int64 v33; // [rsp+38h] [rbp-18h]
  ULONGLONG v34; // [rsp+40h] [rbp-10h]
  __int64 NumberOfBytesRead; // [rsp+90h] [rbp+40h] BYREF
  int v36; // [rsp+98h] [rbp+48h]
  ULONGLONG pullResult; // [rsp+A0h] [rbp+50h] BYREF

  v1 = 0;
  if ( !*((_BYTE *)this + 96) )
    return (unsigned int)v1;
  v3 = (unsigned int *)((char *)this + 136);
  v4 = (CWmpEncoderFrame *)((char *)this + 152);
  v1 = ErrMarkOffset((CWmpEncoderFrame *)((char *)this + 152), (unsigned int *)this + 34);
  if ( v1 < 0 )
    return (unsigned int)v1;
  v5 = *((_OWORD *)this + 17);
  *((_OWORD *)this + 2080) = *((_OWORD *)this + 16);
  v6 = *((_OWORD *)this + 18);
  *((_OWORD *)this + 2081) = v5;
  v7 = *((_OWORD *)this + 19);
  *((_OWORD *)this + 2082) = v6;
  v8 = *((_OWORD *)this + 20);
  *((_OWORD *)this + 2083) = v7;
  v9 = *((_OWORD *)this + 21);
  *((_OWORD *)this + 2084) = v8;
  v10 = *((_OWORD *)this + 22);
  *((_OWORD *)this + 2085) = v9;
  v11 = *((_OWORD *)this + 23);
  *((_OWORD *)this + 2086) = v10;
  *((_OWORD *)this + 2087) = v11;
  memcpy_0((char *)this + 33408, (char *)this + 384, 0x8078u);
  v12 = (void **)((char *)this + 66296);
  v13 = *((_QWORD *)this + 7) - 1LL;
  *((_DWORD *)this + 8324) = 0;
  *((_QWORD *)this + 4164) = v13;
  *((_BYTE *)this + 33412) = *((_BYTE *)this + 66488);
  *((_DWORD *)this + 8354) = 0;
  *((_QWORD *)this + 4181) = 1;
  v1 = ImageStrEncInit((char *)this + 33280, (char *)this + 33408, (char *)this + 66296);
  if ( v1 < 0 )
    return (unsigned int)v1;
  v14 = (void *)*((_QWORD *)this + 8321);
  v15 = -1;
  v36 = 0;
  if ( v14 == (void *)-1LL )
  {
    v25 = *((_DWORD *)this + 26);
    if ( v25 )
    {
      v26 = *((_QWORD *)this + 8288);
      v27 = 0;
      v28 = *((_QWORD *)this + 8289);
      NumberOfBytesRead = v26;
      while ( 1 )
      {
        v29 = v25 - v27;
        v32 = v26;
        v30 = *((_QWORD *)this + 8287);
        v34 = v28;
        if ( v29 > 0x10 )
          v29 = 16;
        v31 = v29;
        v33 = v29;
        v1 = ImageStrEncEncode(v30, &v32);
        if ( v1 < 0 )
          break;
        v27 += 16;
        v28 = *((_QWORD *)this + 8289);
        v25 = *((_DWORD *)this + 26);
        v26 = v28 * v31 + NumberOfBytesRead;
        NumberOfBytesRead = v26;
        if ( v27 >= v25 )
        {
          v4 = (CWmpEncoderFrame *)((char *)this + 152);
          v12 = (void **)((char *)this + 66296);
          goto LABEL_22;
        }
      }
LABEL_8:
      v16 = ImageStrEncTerm(*((void **)this + 4159));
      if ( v36 || v16 )
        return v15;
      return (unsigned int)v1;
    }
    goto LABEL_22;
  }
  if ( SetFilePointer(v14, 0, 0, 0) == -1 && GetLastError() )
  {
    v36 = -1;
    goto LABEL_8;
  }
  v17 = *((_DWORD *)this + 26);
  if ( !v17 )
  {
LABEL_22:
    v1 = ImageStrEncTerm(*v12);
    if ( v1 >= 0 )
    {
      v1 = ErrMarkLength(v4, *v3, (unsigned int *)this + 35);
      if ( v1 >= 0 )
        return (unsigned int)CWmpEncoderFrame::CheckSize(v23, *v3, *((unsigned int *)this + 35));
    }
    return (unsigned int)v1;
  }
  v18 = 0;
  while ( 1 )
  {
    v19 = *((_QWORD *)this + 8289);
    v20 = v17 - v18;
    pullResult = 0;
    v34 = v19;
    LODWORD(NumberOfBytesRead) = 0;
    if ( v20 > 0x10 )
      v20 = 16;
    v32 = *((_QWORD *)this + 8288);
    v33 = v20;
    if ( ULongLongMult(v19, v20, &pullResult) )
      return 2291674994LL;
    v22 = pullResult;
    if ( pullResult > v21
      || !ReadFile(*((HANDLE *)this + 8321), *((LPVOID *)this + 8288), pullResult, (LPDWORD)&NumberOfBytesRead, 0)
      || (_DWORD)NumberOfBytesRead != v22 )
    {
      return 2291674994LL;
    }
    v1 = ImageStrEncEncode(*v12, &v32);
    if ( v1 < 0 )
      goto LABEL_8;
    v17 = *((_DWORD *)this + 26);
    v18 += 16;
    if ( v18 >= v17 )
    {
      v4 = (CWmpEncoderFrame *)((char *)this + 152);
      goto LABEL_22;
    }
  }
}

```

## disassembly

```asm
0x18002c8f8  mov     [rsp-38h+arg_18], rbx
0x18002c8fd  push    rbp
0x18002c8fe  push    rsi
0x18002c8ff  push    rdi
0x18002c900  push    r12
0x18002c902  push    r13
0x18002c904  push    r14
0x18002c906  push    r15
0x18002c908  mov     rbp, rsp
0x18002c90b  sub     rsp, 50h
0x18002c90f  xor     ebx, ebx
0x18002c911  mov     rsi, rcx
0x18002c914  cmp     [rcx+60h], bl
0x18002c917  jz      loc_18002CB83
0x18002c91d  lea     r13, [rcx+88h]
0x18002c924  lea     r14, [rcx+98h]
0x18002c92b  mov     rdx, r13; unsigned int *
0x18002c92e  mov     rcx, r14; struct WMPStream *
0x18002c931  call    ?ErrMarkOffset@@YAJPEAUWMPStream@@PEAI@Z; ErrMarkOffset(WMPStream *,uint *)
0x18002c936  mov     ebx, eax
0x18002c938  test    eax, eax
0x18002c93a  js      loc_18002CB83
0x18002c940  movups  xmm0, xmmword ptr [rsi+100h]
0x18002c947  lea     rdi, [rsi+8200h]
0x18002c94e  mov     r8d, 8078h; Size
0x18002c954  movups  xmm1, xmmword ptr [rsi+110h]
0x18002c95b  lea     rbx, [rsi+8280h]
0x18002c962  movups  xmmword ptr [rdi], xmm0
0x18002c965  lea     rdx, [rsi+180h]; Src
0x18002c96c  mov     rcx, rbx; void *
0x18002c96f  movups  xmm0, xmmword ptr [rsi+120h]
0x18002c976  movups  xmmword ptr [rdi+10h], xmm1
0x18002c97a  movups  xmm1, xmmword ptr [rsi+130h]
0x18002c981  movups  xmmword ptr [rdi+20h], xmm0
0x18002c985  movups  xmm0, xmmword ptr [rsi+140h]
0x18002c98c  movups  xmmword ptr [rdi+30h], xmm1
0x18002c990  movups  xmm1, xmmword ptr [rsi+150h]
0x18002c997  movups  xmmword ptr [rdi+40h], xmm0
0x18002c99b  movups  xmm0, xmmword ptr [rsi+160h]
0x18002c9a2  movups  xmmword ptr [rdi+50h], xmm1
0x18002c9a6  movups  xmm1, xmmword ptr [rsi+170h]
0x18002c9ad  movups  xmmword ptr [rdi+60h], xmm0
0x18002c9b1  movups  xmmword ptr [rdi+70h], xmm1
0x18002c9b5  call    memcpy_0
0x18002c9ba  mov     rax, [rsi+38h]
0x18002c9be  lea     r12, [rsi+102F8h]
0x18002c9c5  dec     rax
0x18002c9c8  mov     dword ptr [rsi+8210h], 0
0x18002c9d2  mov     [rsi+8220h], rax
0x18002c9d9  mov     r8, r12
0x18002c9dc  mov     al, [rsi+103B8h]
0x18002c9e2  mov     rdx, rbx
0x18002c9e5  mov     rcx, rdi
0x18002c9e8  mov     [rsi+8284h], al
0x18002c9ee  mov     dword ptr [rsi+8288h], 0
0x18002c9f8  mov     qword ptr [rsi+82A8h], 1
0x18002ca03  call    ImageStrEncInit
0x18002ca08  mov     ebx, eax
0x18002ca0a  test    eax, eax
0x18002ca0c  js      loc_18002CB83
0x18002ca12  mov     rcx, [rsi+10408h]; hFile
0x18002ca19  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002ca1d  mov     [rbp+arg_8], 0
0x18002ca24  cmp     rcx, rdi
0x18002ca27  jz      loc_18002CBA6
0x18002ca2d  xor     r9d, r9d; dwMoveMethod
0x18002ca30  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002ca33  xor     edx, edx; lDistanceToMove
0x18002ca35  call    cs:__imp_SetFilePointer
0x18002ca3b  mov     r9d, 0FFFFFFFFh
0x18002ca41  cmp     eax, r9d
0x18002ca44  jnz     short loc_18002CA7C
0x18002ca46  call    cs:__imp_GetLastError
0x18002ca4c  test    eax, eax
0x18002ca4e  jz      short loc_18002CA76
0x18002ca50  mov     [rbp+arg_8], edi
0x18002ca53  mov     rcx, [rsi+81F8h]; Block
0x18002ca5a  call    ImageStrEncTerm
0x18002ca5f  cmp     [rbp+arg_8], 0
0x18002ca63  jnz     loc_18002CB85
0x18002ca69  test    eax, eax
0x18002ca6b  jz      loc_18002CB83
0x18002ca71  jmp     loc_18002CB85
0x18002ca76  mov     r9d, 0FFFFFFFFh
0x18002ca7c  mov     eax, [rsi+68h]
0x18002ca7f  test    eax, eax
0x18002ca81  jz      loc_18002CB49
0x18002ca87  xor     r15d, r15d
0x18002ca8a  lea     r14d, [r15+10h]
0x18002ca8e  mov     rcx, [rsi+10308h]; ullMultiplicand
0x18002ca95  lea     r8, [rbp+pullResult]; pullResult
0x18002ca99  sub     eax, r15d
0x18002ca9c  mov     [rbp+pullResult], 0
0x18002caa4  cmp     eax, r14d
0x18002caa7  mov     [rbp+var_10], rcx
0x18002caab  mov     dword ptr [rbp+NumberOfBytesRead], 0
0x18002cab2  cmova   eax, r14d
0x18002cab6  mov     edx, eax; ullMultiplier
0x18002cab8  mov     rax, [rsi+10300h]
0x18002cabf  mov     [rbp+var_20], rax
0x18002cac3  mov     [rbp+var_18], rdx
0x18002cac7  call    ULongLongMult
0x18002cacc  test    eax, eax
0x18002cace  jnz     loc_18002CB9F
0x18002cad4  mov     rbx, [rbp+pullResult]
0x18002cad8  cmp     rbx, r9
0x18002cadb  ja      loc_18002CB9F
0x18002cae1  mov     rdx, [rsi+10300h]; lpBuffer
0x18002cae8  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002caec  mov     rcx, [rsi+10408h]; hFile
0x18002caf3  mov     r8d, ebx; nNumberOfBytesToRead
0x18002caf6  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x18002caff  call    cs:__imp_ReadFile
0x18002cb05  test    eax, eax
0x18002cb07  jz      loc_18002CB9F
0x18002cb0d  cmp     dword ptr [rbp+NumberOfBytesRead], ebx
0x18002cb10  jnz     loc_18002CB9F
0x18002cb16  mov     rcx, [r12]
0x18002cb1a  lea     rdx, [rbp+var_20]
0x18002cb1e  call    ImageStrEncEncode
0x18002cb23  mov     ebx, eax
0x18002cb25  test    eax, eax
0x18002cb27  js      loc_18002CA53
0x18002cb2d  mov     eax, [rsi+68h]
0x18002cb30  add     r15d, r14d
0x18002cb33  mov     r9d, 0FFFFFFFFh
0x18002cb39  cmp     r15d, eax
0x18002cb3c  jb      loc_18002CA8E
0x18002cb42  lea     r14, [rsi+98h]
0x18002cb49  mov     rcx, [r12]; Block
0x18002cb4d  call    ImageStrEncTerm
0x18002cb52  mov     ebx, eax
0x18002cb54  test    eax, eax
0x18002cb56  js      short loc_18002CB83
0x18002cb58  mov     edx, [r13+0]; unsigned int
0x18002cb5c  lea     r8, [rsi+8Ch]; unsigned int *
0x18002cb63  mov     rcx, r14; struct WMPStream *
0x18002cb66  call    ?ErrMarkLength@@YAJPEAUWMPStream@@IPEAI@Z; ErrMarkLength(WMPStream *,uint,uint *)
0x18002cb6b  mov     ebx, eax
0x18002cb6d  test    eax, eax
0x18002cb6f  js      short loc_18002CB83
0x18002cb71  mov     r8d, [rsi+8Ch]; unsigned __int64
0x18002cb78  mov     edx, [r13+0]; unsigned __int64
0x18002cb7c  call    ?CheckSize@CWmpEncoderFrame@@AEAAJ_K0@Z; CWmpEncoderFrame::CheckSize(unsigned __int64,unsigned __int64)
0x18002cb81  mov     ebx, eax
0x18002cb83  mov     edi, ebx
0x18002cb85  mov     eax, edi
0x18002cb87  mov     rbx, [rsp+50h+arg_18]
0x18002cb8f  add     rsp, 50h
0x18002cb93  pop     r15
0x18002cb95  pop     r14
0x18002cb97  pop     r13
0x18002cb99  pop     r12
0x18002cb9b  pop     rdi
0x18002cb9c  pop     rsi
0x18002cb9d  pop     rbp
0x18002cb9e  retn
0x18002cb9f  mov     eax, 88982F72h
0x18002cba4  jmp     short loc_18002CB87
0x18002cba6  mov     eax, [rsi+68h]
0x18002cba9  test    eax, eax
0x18002cbab  jz      short loc_18002CB49
0x18002cbad  mov     rcx, [rsi+10300h]
0x18002cbb4  xor     r15d, r15d
0x18002cbb7  mov     rdx, [rsi+10308h]
0x18002cbbe  mov     [rbp+NumberOfBytesRead], rcx
0x18002cbc2  lea     r14d, [r15+10h]
0x18002cbc6  sub     eax, r15d
0x18002cbc9  mov     [rbp+var_20], rcx
0x18002cbcd  mov     rcx, [rsi+102F8h]
0x18002cbd4  cmp     eax, r14d
0x18002cbd7  mov     [rbp+var_10], rdx
0x18002cbdb  lea     rdx, [rbp+var_20]
0x18002cbdf  cmova   eax, r14d
0x18002cbe3  mov     r12d, eax
0x18002cbe6  mov     [rbp+var_18], r12
0x18002cbea  call    ImageStrEncEncode
0x18002cbef  mov     ebx, eax
0x18002cbf1  test    eax, eax
0x18002cbf3  js      loc_18002CA53
0x18002cbf9  mov     rcx, [rbp+NumberOfBytesRead]
0x18002cbfd  add     r15d, r14d
0x18002cc00  mov     rdx, [rsi+10308h]
0x18002cc07  mov     eax, [rsi+68h]
0x18002cc0a  imul    r12, rdx
0x18002cc0e  add     rcx, r12
0x18002cc11  mov     [rbp+NumberOfBytesRead], rcx
0x18002cc15  cmp     r15d, eax
0x18002cc18  jb      short loc_18002CBC6
0x18002cc1a  lea     r14, [rsi+98h]
0x18002cc21  lea     r12, [rsi+102F8h]
0x18002cc28  jmp     loc_18002CB49
```
