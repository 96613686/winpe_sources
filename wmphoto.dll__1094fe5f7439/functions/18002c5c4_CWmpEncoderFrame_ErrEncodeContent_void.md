# CWmpEncoderFrame::ErrEncodeContent(void)

- ea: `0x18002c5c4`
- end: `0x18002c8ef`
- name: `?ErrEncodeContent@CWmpEncoderFrame@@IEAAJXZ`
- size: `811`
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
- `0x18002c5c4`
- `0x18002dbd0`
- `0x1800309d0`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c71c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c71c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c7d2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c7d2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c6f6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c70b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c6f6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c70b`

## pseudocode

```c
__int64 __fastcall CWmpEncoderFrame::ErrEncodeContent(CWmpEncoderFrame *this)
{
  struct WMPStream *v1; // r13
  int v3; // edi
  unsigned int *v4; // r15
  __int64 v5; // rcx
  bool v6; // zf
  int v7; // eax
  void **v8; // r14
  void *v9; // rcx
  unsigned int v10; // esi
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // r12d
  ULONGLONG v14; // rcx
  unsigned int v15; // eax
  ULONGLONG v16; // r9
  int v17; // edi
  CWmpEncoderFrame *v18; // rcx
  unsigned int v20; // eax
  ULONGLONG v21; // rdx
  unsigned int v22; // r12d
  unsigned int v23; // eax
  ULONGLONG v24; // rcx
  ULONGLONG v25; // rax
  void *v26; // rcx
  ULONGLONG v27; // [rsp+30h] [rbp-20h] BYREF
  ULONGLONG v28; // [rsp+38h] [rbp-18h]
  ULONGLONG v29; // [rsp+40h] [rbp-10h]
  ULONGLONG NumberOfBytesRead; // [rsp+90h] [rbp+40h] BYREF
  int v31; // [rsp+98h] [rbp+48h]
  ULONGLONG pullResult; // [rsp+A0h] [rbp+50h] BYREF

  v1 = (CWmpEncoderFrame *)((char *)this + 152);
  if ( *((_DWORD *)this + 16627) )
  {
    v3 = (*((__int64 (__fastcall **)(char *, _QWORD))this + 30))((char *)this + 152, 0);
    if ( v3 < 0 )
      return (unsigned int)v3;
  }
  v4 = (unsigned int *)((char *)this + 128);
  v3 = ErrMarkOffset(v1, (unsigned int *)this + 32);
  if ( v3 < 0 )
    return (unsigned int)v3;
  v5 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 32) = *((unsigned int *)this + 25);
  *((_QWORD *)this + 33) = *((unsigned int *)this + 26);
  *((_DWORD *)this + 69) = *((_DWORD *)this + 18);
  *((_QWORD *)this + 35) = *((_QWORD *)this + 10);
  v6 = *((_BYTE *)this + 96) == 0;
  *((_DWORD *)this + 74) = (*((_DWORD *)this + 22) & 0x40) == 0;
  if ( v6 )
  {
    v6 = *((_BYTE *)this + 432) == 3;
    *((_DWORD *)this + 68) = *((_DWORD *)this + 16);
    if ( !v6 )
      goto LABEL_8;
  }
  else
  {
    *((_DWORD *)this + 68) = *((_DWORD *)this + 17);
  }
  --v5;
LABEL_8:
  *((_QWORD *)this + 53) = v5;
  v7 = *((_DWORD *)this + 68);
  if ( v7 == 7 )
    v7 = *((_DWORD *)this + 98);
  *((_DWORD *)this + 98) = v7;
  if ( v7 == 8 )
    *((_DWORD *)this + 98) = 3;
  v8 = (void **)((char *)this + 33272);
  v3 = ImageStrEncInit((char *)this + 256, (char *)this + 384, (char *)this + 33272);
  if ( v3 < 0 )
    return (unsigned int)v3;
  v9 = (void *)*((_QWORD *)this + 8321);
  v10 = -1;
  v31 = 0;
  if ( v9 == (void *)-1LL )
  {
    v20 = *((_DWORD *)this + 26);
    if ( v20 )
    {
      v21 = *((_QWORD *)this + 8288);
      v22 = 0;
      NumberOfBytesRead = v21;
      while ( 1 )
      {
        v23 = v20 - v22;
        v27 = v21;
        if ( v23 > 0x10 )
          v23 = 16;
        v24 = v23;
        v25 = *((_QWORD *)this + 8289);
        pullResult = v24;
        v28 = v24;
        v26 = *v8;
        v29 = v25;
        v3 = ImageStrEncEncode(v26, &v27);
        if ( v3 < 0 )
          break;
        v22 += 16;
        v21 = *((_QWORD *)this + 8289) * pullResult + NumberOfBytesRead;
        v20 = *((_DWORD *)this + 26);
        NumberOfBytesRead = v21;
        if ( v22 >= v20 )
        {
LABEL_30:
          v4 = (unsigned int *)((char *)this + 128);
          goto LABEL_31;
        }
      }
LABEL_17:
      v11 = ImageStrEncTerm(*v8);
      if ( v31 || v11 )
        return v10;
      return (unsigned int)v3;
    }
    goto LABEL_31;
  }
  SetFilePointer(v9, 0, 0, 1u);
  if ( SetFilePointer(*((HANDLE *)this + 8321), 0, 0, 0) == -1 && GetLastError() )
  {
    v31 = -1;
    goto LABEL_17;
  }
  v12 = *((_DWORD *)this + 26);
  if ( !v12 )
  {
LABEL_31:
    v3 = ImageStrEncTerm(*v8);
    if ( v3 >= 0 )
    {
      v3 = ErrMarkLength(v1, *v4, (unsigned int *)this + 33);
      if ( v3 >= 0 )
        return (unsigned int)CWmpEncoderFrame::CheckSize(v18, *v4, *((unsigned int *)this + 33));
    }
    return (unsigned int)v3;
  }
  v13 = 0;
  while ( 1 )
  {
    v14 = *((_QWORD *)this + 8289);
    v15 = v12 - v13;
    pullResult = 0;
    v29 = v14;
    LODWORD(NumberOfBytesRead) = 0;
    if ( v15 > 0x10 )
      v15 = 16;
    v27 = *((_QWORD *)this + 8288);
    v28 = v15;
    if ( ULongLongMult(v14, v15, &pullResult) )
      return 2291674994LL;
    v17 = pullResult;
    if ( pullResult > v16
      || !ReadFile(*((HANDLE *)this + 8321), *((LPVOID *)this + 8288), pullResult, (LPDWORD)&NumberOfBytesRead, 0)
      || (_DWORD)NumberOfBytesRead != v17 )
    {
      return 2291674994LL;
    }
    v3 = ImageStrEncEncode(*v8, &v27);
    if ( v3 < 0 )
      goto LABEL_17;
    v12 = *((_DWORD *)this + 26);
    v13 += 16;
    if ( v13 >= v12 )
      goto LABEL_30;
  }
}

```

## disassembly

```asm
0x18002c5c4  mov     [rsp-38h+arg_18], rbx
0x18002c5c9  push    rbp
0x18002c5ca  push    rsi
0x18002c5cb  push    rdi
0x18002c5cc  push    r12
0x18002c5ce  push    r13
0x18002c5d0  push    r14
0x18002c5d2  push    r15
0x18002c5d4  mov     rbp, rsp
0x18002c5d7  sub     rsp, 50h
0x18002c5db  cmp     dword ptr [rcx+103CCh], 0
0x18002c5e2  lea     r13, [rcx+98h]
0x18002c5e9  mov     rbx, rcx
0x18002c5ec  jz      short loc_18002C606
0x18002c5ee  mov     rax, [r13+58h]
0x18002c5f2  xor     edx, edx
0x18002c5f4  mov     rcx, r13
0x18002c5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5fc  mov     edi, eax
0x18002c5fe  test    eax, eax
0x18002c600  js      loc_18002C852
0x18002c606  lea     r15, [rbx+80h]
0x18002c60d  mov     rcx, r13; struct WMPStream *
0x18002c610  mov     rdx, r15; unsigned int *
0x18002c613  call    ?ErrMarkOffset@@YAJPEAUWMPStream@@PEAI@Z; ErrMarkOffset(WMPStream *,uint *)
0x18002c618  mov     edi, eax
0x18002c61a  test    eax, eax
0x18002c61c  js      loc_18002C852
0x18002c622  mov     eax, [rbx+64h]
0x18002c625  lea     r9, [rbx+100h]
0x18002c62c  mov     rcx, [rbx+38h]
0x18002c630  lea     rdx, [rbx+180h]
0x18002c637  mov     [r9], rax
0x18002c63a  mov     eax, [rbx+68h]
0x18002c63d  mov     [rbx+108h], rax
0x18002c644  mov     eax, [rbx+48h]
0x18002c647  mov     [rbx+114h], eax
0x18002c64d  mov     rax, [rbx+50h]
0x18002c651  mov     [rbx+118h], rax
0x18002c658  mov     eax, [rbx+58h]
0x18002c65b  shr     eax, 6
0x18002c65e  not     eax
0x18002c660  and     eax, 1
0x18002c663  cmp     byte ptr [rbx+60h], 0
0x18002c667  mov     [rbx+128h], eax
0x18002c66d  jz      short loc_18002C67A
0x18002c66f  mov     eax, [rbx+44h]
0x18002c672  mov     [rbx+110h], eax
0x18002c678  jmp     short loc_18002C689
0x18002c67a  cmp     byte ptr [rdx+30h], 3
0x18002c67e  mov     eax, [rbx+40h]
0x18002c681  mov     [rbx+110h], eax
0x18002c687  jnz     short loc_18002C68C
0x18002c689  dec     rcx
0x18002c68c  mov     [rdx+28h], rcx
0x18002c690  mov     eax, [rbx+110h]
0x18002c696  cmp     eax, 7
0x18002c699  jnz     short loc_18002C6A1
0x18002c69b  mov     eax, [rbx+188h]
0x18002c6a1  mov     [rbx+188h], eax
0x18002c6a7  cmp     eax, 8
0x18002c6aa  jnz     short loc_18002C6B6
0x18002c6ac  mov     dword ptr [rbx+188h], 3
0x18002c6b6  lea     r14, [rbx+81F8h]
0x18002c6bd  mov     rcx, r9
0x18002c6c0  mov     r8, r14
0x18002c6c3  call    ImageStrEncInit
0x18002c6c8  mov     edi, eax
0x18002c6ca  test    eax, eax
0x18002c6cc  js      loc_18002C852
0x18002c6d2  mov     rcx, [rbx+10408h]; hFile
0x18002c6d9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002c6dd  mov     [rbp+arg_8], 0
0x18002c6e4  cmp     rcx, rsi
0x18002c6e7  jz      loc_18002C875
0x18002c6ed  lea     r9d, [rsi+2]; dwMoveMethod
0x18002c6f1  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002c6f4  xor     edx, edx; lDistanceToMove
0x18002c6f6  call    cs:__imp_SetFilePointer
0x18002c6fc  mov     rcx, [rbx+10408h]; hFile
0x18002c703  xor     r9d, r9d; dwMoveMethod
0x18002c706  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002c709  xor     edx, edx; lDistanceToMove
0x18002c70b  call    cs:__imp_SetFilePointer
0x18002c711  mov     r9d, 0FFFFFFFFh
0x18002c717  cmp     eax, r9d
0x18002c71a  jnz     short loc_18002C74E
0x18002c71c  call    cs:__imp_GetLastError
0x18002c722  test    eax, eax
0x18002c724  jz      short loc_18002C748
0x18002c726  mov     [rbp+arg_8], esi
0x18002c729  mov     rcx, [r14]; Block
0x18002c72c  call    ImageStrEncTerm
0x18002c731  cmp     [rbp+arg_8], 0
0x18002c735  jnz     loc_18002C854
0x18002c73b  test    eax, eax
0x18002c73d  jz      loc_18002C852
0x18002c743  jmp     loc_18002C854
0x18002c748  mov     r9d, 0FFFFFFFFh
0x18002c74e  mov     eax, [rbx+68h]
0x18002c751  test    eax, eax
0x18002c753  jz      loc_18002C81B
0x18002c759  xor     r12d, r12d
0x18002c75c  lea     r15d, [r12+10h]
0x18002c761  mov     rcx, [rbx+10308h]; ullMultiplicand
0x18002c768  lea     r8, [rbp+pullResult]; pullResult
0x18002c76c  sub     eax, r12d
0x18002c76f  mov     [rbp+pullResult], 0
0x18002c777  cmp     eax, r15d
0x18002c77a  mov     [rbp+var_10], rcx
0x18002c77e  mov     dword ptr [rbp+NumberOfBytesRead], 0
0x18002c785  cmova   eax, r15d
0x18002c789  mov     edx, eax; ullMultiplier
0x18002c78b  mov     rax, [rbx+10300h]
0x18002c792  mov     [rbp+var_20], rax
0x18002c796  mov     [rbp+var_18], rdx
0x18002c79a  call    ULongLongMult
0x18002c79f  test    eax, eax
0x18002c7a1  jnz     loc_18002C86E
0x18002c7a7  mov     rdi, [rbp+pullResult]
0x18002c7ab  cmp     rdi, r9
0x18002c7ae  ja      loc_18002C86E
0x18002c7b4  mov     rdx, [rbx+10300h]; lpBuffer
0x18002c7bb  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002c7bf  mov     rcx, [rbx+10408h]; hFile
0x18002c7c6  mov     r8d, edi; nNumberOfBytesToRead
0x18002c7c9  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x18002c7d2  call    cs:__imp_ReadFile
0x18002c7d8  test    eax, eax
0x18002c7da  jz      loc_18002C86E
0x18002c7e0  cmp     dword ptr [rbp+NumberOfBytesRead], edi
0x18002c7e3  jnz     loc_18002C86E
0x18002c7e9  mov     rcx, [r14]
0x18002c7ec  lea     rdx, [rbp+var_20]
0x18002c7f0  call    ImageStrEncEncode
0x18002c7f5  mov     edi, eax
0x18002c7f7  test    eax, eax
0x18002c7f9  js      loc_18002C729
0x18002c7ff  mov     eax, [rbx+68h]
0x18002c802  add     r12d, r15d
0x18002c805  mov     r9d, 0FFFFFFFFh
0x18002c80b  cmp     r12d, eax
0x18002c80e  jb      loc_18002C761
0x18002c814  lea     r15, [rbx+80h]
0x18002c81b  mov     rcx, [r14]; Block
0x18002c81e  call    ImageStrEncTerm
0x18002c823  mov     edi, eax
0x18002c825  test    eax, eax
0x18002c827  js      short loc_18002C852
0x18002c829  mov     edx, [r15]; unsigned int
0x18002c82c  lea     r8, [rbx+84h]; unsigned int *
0x18002c833  mov     rcx, r13; struct WMPStream *
0x18002c836  call    ?ErrMarkLength@@YAJPEAUWMPStream@@IPEAI@Z; ErrMarkLength(WMPStream *,uint,uint *)
0x18002c83b  mov     edi, eax
0x18002c83d  test    eax, eax
0x18002c83f  js      short loc_18002C852
0x18002c841  mov     r8d, [rbx+84h]; unsigned __int64
0x18002c848  mov     edx, [r15]; unsigned __int64
0x18002c84b  call    ?CheckSize@CWmpEncoderFrame@@AEAAJ_K0@Z; CWmpEncoderFrame::CheckSize(unsigned __int64,unsigned __int64)
0x18002c850  mov     edi, eax
0x18002c852  mov     esi, edi
0x18002c854  mov     eax, esi
0x18002c856  mov     rbx, [rsp+50h+arg_18]
0x18002c85e  add     rsp, 50h
0x18002c862  pop     r15
0x18002c864  pop     r14
0x18002c866  pop     r13
0x18002c868  pop     r12
0x18002c86a  pop     rdi
0x18002c86b  pop     rsi
0x18002c86c  pop     rbp
0x18002c86d  retn
0x18002c86e  mov     eax, 88982F72h
0x18002c873  jmp     short loc_18002C856
0x18002c875  mov     eax, [rbx+68h]
0x18002c878  test    eax, eax
0x18002c87a  jz      short loc_18002C81B
0x18002c87c  mov     rdx, [rbx+10300h]
0x18002c883  xor     r12d, r12d
0x18002c886  mov     [rbp+NumberOfBytesRead], rdx
0x18002c88a  lea     r15d, [r12+10h]
0x18002c88f  sub     eax, r12d
0x18002c892  mov     [rbp+var_20], rdx
0x18002c896  cmp     eax, r15d
0x18002c899  lea     rdx, [rbp+var_20]
0x18002c89d  cmova   eax, r15d
0x18002c8a1  mov     ecx, eax
0x18002c8a3  mov     rax, [rbx+10308h]
0x18002c8aa  mov     [rbp+pullResult], rcx
0x18002c8ae  mov     [rbp+var_18], rcx
0x18002c8b2  mov     rcx, [r14]
0x18002c8b5  mov     [rbp+var_10], rax
0x18002c8b9  call    ImageStrEncEncode
0x18002c8be  mov     edi, eax
0x18002c8c0  test    eax, eax
0x18002c8c2  js      loc_18002C729
0x18002c8c8  mov     rdx, [rbp+NumberOfBytesRead]
0x18002c8cc  add     r12d, r15d
0x18002c8cf  mov     rax, [rbp+pullResult]
0x18002c8d3  imul    rax, [rbx+10308h]
0x18002c8db  add     rdx, rax
0x18002c8de  mov     eax, [rbx+68h]
0x18002c8e1  mov     [rbp+NumberOfBytesRead], rdx
0x18002c8e5  cmp     r12d, eax
0x18002c8e8  jb      short loc_18002C88F
0x18002c8ea  jmp     loc_18002C814
```
