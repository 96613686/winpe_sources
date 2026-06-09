# CWmpEncoderFrame::ErrEncodeAlpha(void)

- ea: `0x18002cbb0`
- end: `0x18002cef8`
- name: `?ErrEncodeAlpha@CWmpEncoderFrame@@IEAAJXZ`
- size: `840`
- prototype: `__int64 __fastcall(CWmpEncoderFrame *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18002c260`

## callees

- `0x1800213f8`
- `0x180021bf0`
- `0x180029e8c`
- `0x180029ec4`
- `0x180029f08`
- `0x18002cbb0`
- `0x18002ded0`
- `0x180030e10`
- `0x180043e40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd04`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cdc3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002cdc3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cced`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002cced`

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
0x18002cbb0  mov     [rsp-38h+arg_18], rbx
0x18002cbb5  push    rbp
0x18002cbb6  push    rsi
0x18002cbb7  push    rdi
0x18002cbb8  push    r12
0x18002cbba  push    r13
0x18002cbbc  push    r14
0x18002cbbe  push    r15
0x18002cbc0  mov     rbp, rsp
0x18002cbc3  sub     rsp, 50h
0x18002cbc7  xor     ebx, ebx
0x18002cbc9  mov     rsi, rcx
0x18002cbcc  cmp     [rcx+60h], bl
0x18002cbcf  jz      loc_18002CE4D
0x18002cbd5  lea     r13, [rcx+88h]
0x18002cbdc  lea     r14, [rcx+98h]
0x18002cbe3  mov     rdx, r13; unsigned int *
0x18002cbe6  mov     rcx, r14; struct WMPStream *
0x18002cbe9  call    ?ErrMarkOffset@@YAJPEAUWMPStream@@PEAI@Z; ErrMarkOffset(WMPStream *,uint *)
0x18002cbee  mov     ebx, eax
0x18002cbf0  test    eax, eax
0x18002cbf2  js      loc_18002CE4D
0x18002cbf8  movups  xmm0, xmmword ptr [rsi+100h]
0x18002cbff  lea     rdi, [rsi+8200h]
0x18002cc06  mov     r8d, 8078h; Size
0x18002cc0c  movups  xmm1, xmmword ptr [rsi+110h]
0x18002cc13  lea     rbx, [rsi+8280h]
0x18002cc1a  movups  xmmword ptr [rdi], xmm0
0x18002cc1d  lea     rdx, [rsi+180h]; Src
0x18002cc24  mov     rcx, rbx; void *
0x18002cc27  movups  xmm0, xmmword ptr [rsi+120h]
0x18002cc2e  movups  xmmword ptr [rdi+10h], xmm1
0x18002cc32  movups  xmm1, xmmword ptr [rsi+130h]
0x18002cc39  movups  xmmword ptr [rdi+20h], xmm0
0x18002cc3d  movups  xmm0, xmmword ptr [rsi+140h]
0x18002cc44  movups  xmmword ptr [rdi+30h], xmm1
0x18002cc48  movups  xmm1, xmmword ptr [rsi+150h]
0x18002cc4f  movups  xmmword ptr [rdi+40h], xmm0
0x18002cc53  movups  xmm0, xmmword ptr [rsi+160h]
0x18002cc5a  movups  xmmword ptr [rdi+50h], xmm1
0x18002cc5e  movups  xmm1, xmmword ptr [rsi+170h]
0x18002cc65  movups  xmmword ptr [rdi+60h], xmm0
0x18002cc69  movups  xmmword ptr [rdi+70h], xmm1
0x18002cc6d  call    memcpy_0
0x18002cc72  mov     rax, [rsi+38h]
0x18002cc76  lea     r12, [rsi+102F8h]
0x18002cc7d  dec     rax
0x18002cc80  mov     dword ptr [rsi+8210h], 0
0x18002cc8a  mov     [rsi+8220h], rax
0x18002cc91  mov     r8, r12
0x18002cc94  mov     al, [rsi+103B8h]
0x18002cc9a  mov     rdx, rbx
0x18002cc9d  mov     rcx, rdi
0x18002cca0  mov     [rsi+8284h], al
0x18002cca6  mov     dword ptr [rsi+8288h], 0
0x18002ccb0  mov     qword ptr [rsi+82A8h], 1
0x18002ccbb  call    ImageStrEncInit
0x18002ccc0  mov     ebx, eax
0x18002ccc2  test    eax, eax
0x18002ccc4  js      loc_18002CE4D
0x18002ccca  mov     rcx, [rsi+10408h]; hFile
0x18002ccd1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002ccd5  mov     [rbp+arg_8], 0
0x18002ccdc  cmp     rcx, rdi
0x18002ccdf  jz      loc_18002CE71
0x18002cce5  xor     r9d, r9d; dwMoveMethod
0x18002cce8  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002cceb  xor     edx, edx; lDistanceToMove
0x18002cced  call    cs:__imp_SetFilePointer
0x18002ccf4  nop     dword ptr [rax+rax+00h]
0x18002ccf9  mov     r9d, 0FFFFFFFFh
0x18002ccff  cmp     eax, r9d
0x18002cd02  jnz     short loc_18002CD40
0x18002cd04  call    cs:__imp_GetLastError
0x18002cd0b  nop     dword ptr [rax+rax+00h]
0x18002cd10  test    eax, eax
0x18002cd12  jz      short loc_18002CD3A
0x18002cd14  mov     [rbp+arg_8], edi
0x18002cd17  mov     rcx, [rsi+81F8h]; Block
0x18002cd1e  call    ImageStrEncTerm
0x18002cd23  cmp     [rbp+arg_8], 0
0x18002cd27  jnz     loc_18002CE4F
0x18002cd2d  test    eax, eax
0x18002cd2f  jz      loc_18002CE4D
0x18002cd35  jmp     loc_18002CE4F
0x18002cd3a  mov     r9d, 0FFFFFFFFh
0x18002cd40  mov     eax, [rsi+68h]
0x18002cd43  test    eax, eax
0x18002cd45  jz      loc_18002CE13
0x18002cd4b  xor     r15d, r15d
0x18002cd4e  lea     r14d, [r15+10h]
0x18002cd52  mov     rcx, [rsi+10308h]; ullMultiplicand
0x18002cd59  lea     r8, [rbp+pullResult]; pullResult
0x18002cd5d  sub     eax, r15d
0x18002cd60  mov     [rbp+pullResult], 0
0x18002cd68  cmp     eax, r14d
0x18002cd6b  mov     [rbp+var_10], rcx
0x18002cd6f  mov     dword ptr [rbp+NumberOfBytesRead], 0
0x18002cd76  cmova   eax, r14d
0x18002cd7a  mov     edx, eax; ullMultiplier
0x18002cd7c  mov     rax, [rsi+10300h]
0x18002cd83  mov     [rbp+var_20], rax
0x18002cd87  mov     [rbp+var_18], rdx
0x18002cd8b  call    ULongLongMult
0x18002cd90  test    eax, eax
0x18002cd92  jnz     loc_18002CE6A
0x18002cd98  mov     rbx, [rbp+pullResult]
0x18002cd9c  cmp     rbx, r9
0x18002cd9f  ja      loc_18002CE6A
0x18002cda5  mov     rdx, [rsi+10300h]; lpBuffer
0x18002cdac  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002cdb0  mov     rcx, [rsi+10408h]; hFile
0x18002cdb7  mov     r8d, ebx; nNumberOfBytesToRead
0x18002cdba  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x18002cdc3  call    cs:__imp_ReadFile
0x18002cdca  nop     dword ptr [rax+rax+00h]
0x18002cdcf  test    eax, eax
0x18002cdd1  jz      loc_18002CE6A
0x18002cdd7  cmp     dword ptr [rbp+NumberOfBytesRead], ebx
0x18002cdda  jnz     loc_18002CE6A
0x18002cde0  mov     rcx, [r12]
0x18002cde4  lea     rdx, [rbp+var_20]
0x18002cde8  call    ImageStrEncEncode
0x18002cded  mov     ebx, eax
0x18002cdef  test    eax, eax
0x18002cdf1  js      loc_18002CD17
0x18002cdf7  mov     eax, [rsi+68h]
0x18002cdfa  add     r15d, r14d
0x18002cdfd  mov     r9d, 0FFFFFFFFh
0x18002ce03  cmp     r15d, eax
0x18002ce06  jb      loc_18002CD52
0x18002ce0c  lea     r14, [rsi+98h]
0x18002ce13  mov     rcx, [r12]; Block
0x18002ce17  call    ImageStrEncTerm
0x18002ce1c  mov     ebx, eax
0x18002ce1e  test    eax, eax
0x18002ce20  js      short loc_18002CE4D
0x18002ce22  mov     edx, [r13+0]; unsigned int
0x18002ce26  lea     r8, [rsi+8Ch]; unsigned int *
0x18002ce2d  mov     rcx, r14; struct WMPStream *
0x18002ce30  call    ?ErrMarkLength@@YAJPEAUWMPStream@@IPEAI@Z; ErrMarkLength(WMPStream *,uint,uint *)
0x18002ce35  mov     ebx, eax
0x18002ce37  test    eax, eax
0x18002ce39  js      short loc_18002CE4D
0x18002ce3b  mov     r8d, [rsi+8Ch]; unsigned __int64
0x18002ce42  mov     edx, [r13+0]; unsigned __int64
0x18002ce46  call    ?CheckSize@CWmpEncoderFrame@@AEAAJ_K0@Z; CWmpEncoderFrame::CheckSize(unsigned __int64,unsigned __int64)
0x18002ce4b  mov     ebx, eax
0x18002ce4d  mov     edi, ebx
0x18002ce4f  mov     eax, edi
0x18002ce51  mov     rbx, [rsp+50h+arg_18]
0x18002ce59  add     rsp, 50h
0x18002ce5d  pop     r15
0x18002ce5f  pop     r14
0x18002ce61  pop     r13
0x18002ce63  pop     r12
0x18002ce65  pop     rdi
0x18002ce66  pop     rsi
0x18002ce67  pop     rbp
0x18002ce68  retn
0x18002ce6a  mov     eax, 88982F72h
0x18002ce6f  jmp     short loc_18002CE51
0x18002ce71  mov     eax, [rsi+68h]
0x18002ce74  test    eax, eax
0x18002ce76  jz      short loc_18002CE13
0x18002ce78  mov     rcx, [rsi+10300h]
0x18002ce7f  xor     r15d, r15d
0x18002ce82  mov     rdx, [rsi+10308h]
0x18002ce89  mov     [rbp+NumberOfBytesRead], rcx
0x18002ce8d  lea     r14d, [r15+10h]
0x18002ce91  sub     eax, r15d
0x18002ce94  mov     [rbp+var_20], rcx
0x18002ce98  mov     rcx, [rsi+102F8h]
0x18002ce9f  cmp     eax, r14d
0x18002cea2  mov     [rbp+var_10], rdx
0x18002cea6  lea     rdx, [rbp+var_20]
0x18002ceaa  cmova   eax, r14d
0x18002ceae  mov     r12d, eax
0x18002ceb1  mov     [rbp+var_18], r12
0x18002ceb5  call    ImageStrEncEncode
0x18002ceba  mov     ebx, eax
0x18002cebc  test    eax, eax
0x18002cebe  js      loc_18002CD17
0x18002cec4  mov     rcx, [rbp+NumberOfBytesRead]
0x18002cec8  add     r15d, r14d
0x18002cecb  mov     rdx, [rsi+10308h]
0x18002ced2  mov     eax, [rsi+68h]
0x18002ced5  imul    r12, rdx
0x18002ced9  add     rcx, r12
0x18002cedc  mov     [rbp+NumberOfBytesRead], rcx
0x18002cee0  cmp     r15d, eax
0x18002cee3  jb      short loc_18002CE91
0x18002cee5  lea     r14, [rsi+98h]
0x18002ceec  lea     r12, [rsi+102F8h]
0x18002cef3  jmp     loc_18002CE13
```
