# CWmpEncoderFrame::ErrEncodeContent(void)

- ea: `0x18002c864`
- end: `0x18002cba8`
- name: `?ErrEncodeContent@CWmpEncoderFrame@@IEAAJXZ`
- size: `836`
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
- `0x18002c864`
- `0x18002ded0`
- `0x180030e10`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c9c8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ca84`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ca84`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c996`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c9b1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c996`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002c9b1`

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
0x18002c864  mov     [rsp-38h+arg_18], rbx
0x18002c869  push    rbp
0x18002c86a  push    rsi
0x18002c86b  push    rdi
0x18002c86c  push    r12
0x18002c86e  push    r13
0x18002c870  push    r14
0x18002c872  push    r15
0x18002c874  mov     rbp, rsp
0x18002c877  sub     rsp, 50h
0x18002c87b  cmp     dword ptr [rcx+103CCh], 0
0x18002c882  lea     r13, [rcx+98h]
0x18002c889  mov     rbx, rcx
0x18002c88c  jz      short loc_18002C8A6
0x18002c88e  mov     rax, [r13+58h]
0x18002c892  xor     edx, edx
0x18002c894  mov     rcx, r13
0x18002c897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c89c  mov     edi, eax
0x18002c89e  test    eax, eax
0x18002c8a0  js      loc_18002CB0A
0x18002c8a6  lea     r15, [rbx+80h]
0x18002c8ad  mov     rcx, r13; struct WMPStream *
0x18002c8b0  mov     rdx, r15; unsigned int *
0x18002c8b3  call    ?ErrMarkOffset@@YAJPEAUWMPStream@@PEAI@Z; ErrMarkOffset(WMPStream *,uint *)
0x18002c8b8  mov     edi, eax
0x18002c8ba  test    eax, eax
0x18002c8bc  js      loc_18002CB0A
0x18002c8c2  mov     eax, [rbx+64h]
0x18002c8c5  lea     r9, [rbx+100h]
0x18002c8cc  mov     rcx, [rbx+38h]
0x18002c8d0  lea     rdx, [rbx+180h]
0x18002c8d7  mov     [r9], rax
0x18002c8da  mov     eax, [rbx+68h]
0x18002c8dd  mov     [rbx+108h], rax
0x18002c8e4  mov     eax, [rbx+48h]
0x18002c8e7  mov     [rbx+114h], eax
0x18002c8ed  mov     rax, [rbx+50h]
0x18002c8f1  mov     [rbx+118h], rax
0x18002c8f8  mov     eax, [rbx+58h]
0x18002c8fb  shr     eax, 6
0x18002c8fe  not     eax
0x18002c900  and     eax, 1
0x18002c903  cmp     byte ptr [rbx+60h], 0
0x18002c907  mov     [rbx+128h], eax
0x18002c90d  jz      short loc_18002C91A
0x18002c90f  mov     eax, [rbx+44h]
0x18002c912  mov     [rbx+110h], eax
0x18002c918  jmp     short loc_18002C929
0x18002c91a  cmp     byte ptr [rdx+30h], 3
0x18002c91e  mov     eax, [rbx+40h]
0x18002c921  mov     [rbx+110h], eax
0x18002c927  jnz     short loc_18002C92C
0x18002c929  dec     rcx
0x18002c92c  mov     [rdx+28h], rcx
0x18002c930  mov     eax, [rbx+110h]
0x18002c936  cmp     eax, 7
0x18002c939  jnz     short loc_18002C941
0x18002c93b  mov     eax, [rbx+188h]
0x18002c941  mov     [rbx+188h], eax
0x18002c947  cmp     eax, 8
0x18002c94a  jnz     short loc_18002C956
0x18002c94c  mov     dword ptr [rbx+188h], 3
0x18002c956  lea     r14, [rbx+81F8h]
0x18002c95d  mov     rcx, r9
0x18002c960  mov     r8, r14
0x18002c963  call    ImageStrEncInit
0x18002c968  mov     edi, eax
0x18002c96a  test    eax, eax
0x18002c96c  js      loc_18002CB0A
0x18002c972  mov     rcx, [rbx+10408h]; hFile
0x18002c979  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002c97d  mov     [rbp+arg_8], 0
0x18002c984  cmp     rcx, rsi
0x18002c987  jz      loc_18002CB2E
0x18002c98d  lea     r9d, [rsi+2]; dwMoveMethod
0x18002c991  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002c994  xor     edx, edx; lDistanceToMove
0x18002c996  call    cs:__imp_SetFilePointer
0x18002c99d  nop     dword ptr [rax+rax+00h]
0x18002c9a2  mov     rcx, [rbx+10408h]; hFile
0x18002c9a9  xor     r9d, r9d; dwMoveMethod
0x18002c9ac  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002c9af  xor     edx, edx; lDistanceToMove
0x18002c9b1  call    cs:__imp_SetFilePointer
0x18002c9b8  nop     dword ptr [rax+rax+00h]
0x18002c9bd  mov     r9d, 0FFFFFFFFh
0x18002c9c3  cmp     eax, r9d
0x18002c9c6  jnz     short loc_18002CA00
0x18002c9c8  call    cs:__imp_GetLastError
0x18002c9cf  nop     dword ptr [rax+rax+00h]
0x18002c9d4  test    eax, eax
0x18002c9d6  jz      short loc_18002C9FA
0x18002c9d8  mov     [rbp+arg_8], esi
0x18002c9db  mov     rcx, [r14]; Block
0x18002c9de  call    ImageStrEncTerm
0x18002c9e3  cmp     [rbp+arg_8], 0
0x18002c9e7  jnz     loc_18002CB0C
0x18002c9ed  test    eax, eax
0x18002c9ef  jz      loc_18002CB0A
0x18002c9f5  jmp     loc_18002CB0C
0x18002c9fa  mov     r9d, 0FFFFFFFFh
0x18002ca00  mov     eax, [rbx+68h]
0x18002ca03  test    eax, eax
0x18002ca05  jz      loc_18002CAD3
0x18002ca0b  xor     r12d, r12d
0x18002ca0e  lea     r15d, [r12+10h]
0x18002ca13  mov     rcx, [rbx+10308h]; ullMultiplicand
0x18002ca1a  lea     r8, [rbp+pullResult]; pullResult
0x18002ca1e  sub     eax, r12d
0x18002ca21  mov     [rbp+pullResult], 0
0x18002ca29  cmp     eax, r15d
0x18002ca2c  mov     [rbp+var_10], rcx
0x18002ca30  mov     dword ptr [rbp+NumberOfBytesRead], 0
0x18002ca37  cmova   eax, r15d
0x18002ca3b  mov     edx, eax; ullMultiplier
0x18002ca3d  mov     rax, [rbx+10300h]
0x18002ca44  mov     [rbp+var_20], rax
0x18002ca48  mov     [rbp+var_18], rdx
0x18002ca4c  call    ULongLongMult
0x18002ca51  test    eax, eax
0x18002ca53  jnz     loc_18002CB27
0x18002ca59  mov     rdi, [rbp+pullResult]
0x18002ca5d  cmp     rdi, r9
0x18002ca60  ja      loc_18002CB27
0x18002ca66  mov     rdx, [rbx+10300h]; lpBuffer
0x18002ca6d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002ca71  mov     rcx, [rbx+10408h]; hFile
0x18002ca78  mov     r8d, edi; nNumberOfBytesToRead
0x18002ca7b  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x18002ca84  call    cs:__imp_ReadFile
0x18002ca8b  nop     dword ptr [rax+rax+00h]
0x18002ca90  test    eax, eax
0x18002ca92  jz      loc_18002CB27
0x18002ca98  cmp     dword ptr [rbp+NumberOfBytesRead], edi
0x18002ca9b  jnz     loc_18002CB27
0x18002caa1  mov     rcx, [r14]
0x18002caa4  lea     rdx, [rbp+var_20]
0x18002caa8  call    ImageStrEncEncode
0x18002caad  mov     edi, eax
0x18002caaf  test    eax, eax
0x18002cab1  js      loc_18002C9DB
0x18002cab7  mov     eax, [rbx+68h]
0x18002caba  add     r12d, r15d
0x18002cabd  mov     r9d, 0FFFFFFFFh
0x18002cac3  cmp     r12d, eax
0x18002cac6  jb      loc_18002CA13
0x18002cacc  lea     r15, [rbx+80h]
0x18002cad3  mov     rcx, [r14]; Block
0x18002cad6  call    ImageStrEncTerm
0x18002cadb  mov     edi, eax
0x18002cadd  test    eax, eax
0x18002cadf  js      short loc_18002CB0A
0x18002cae1  mov     edx, [r15]; unsigned int
0x18002cae4  lea     r8, [rbx+84h]; unsigned int *
0x18002caeb  mov     rcx, r13; struct WMPStream *
0x18002caee  call    ?ErrMarkLength@@YAJPEAUWMPStream@@IPEAI@Z; ErrMarkLength(WMPStream *,uint,uint *)
0x18002caf3  mov     edi, eax
0x18002caf5  test    eax, eax
0x18002caf7  js      short loc_18002CB0A
0x18002caf9  mov     r8d, [rbx+84h]; unsigned __int64
0x18002cb00  mov     edx, [r15]; unsigned __int64
0x18002cb03  call    ?CheckSize@CWmpEncoderFrame@@AEAAJ_K0@Z; CWmpEncoderFrame::CheckSize(unsigned __int64,unsigned __int64)
0x18002cb08  mov     edi, eax
0x18002cb0a  mov     esi, edi
0x18002cb0c  mov     eax, esi
0x18002cb0e  mov     rbx, [rsp+50h+arg_18]
0x18002cb16  add     rsp, 50h
0x18002cb1a  pop     r15
0x18002cb1c  pop     r14
0x18002cb1e  pop     r13
0x18002cb20  pop     r12
0x18002cb22  pop     rdi
0x18002cb23  pop     rsi
0x18002cb24  pop     rbp
0x18002cb25  retn
0x18002cb27  mov     eax, 88982F72h
0x18002cb2c  jmp     short loc_18002CB0E
0x18002cb2e  mov     eax, [rbx+68h]
0x18002cb31  test    eax, eax
0x18002cb33  jz      short loc_18002CAD3
0x18002cb35  mov     rdx, [rbx+10300h]
0x18002cb3c  xor     r12d, r12d
0x18002cb3f  mov     [rbp+NumberOfBytesRead], rdx
0x18002cb43  lea     r15d, [r12+10h]
0x18002cb48  sub     eax, r12d
0x18002cb4b  mov     [rbp+var_20], rdx
0x18002cb4f  cmp     eax, r15d
0x18002cb52  lea     rdx, [rbp+var_20]
0x18002cb56  cmova   eax, r15d
0x18002cb5a  mov     ecx, eax
0x18002cb5c  mov     rax, [rbx+10308h]
0x18002cb63  mov     [rbp+pullResult], rcx
0x18002cb67  mov     [rbp+var_18], rcx
0x18002cb6b  mov     rcx, [r14]
0x18002cb6e  mov     [rbp+var_10], rax
0x18002cb72  call    ImageStrEncEncode
0x18002cb77  mov     edi, eax
0x18002cb79  test    eax, eax
0x18002cb7b  js      loc_18002C9DB
0x18002cb81  mov     rdx, [rbp+NumberOfBytesRead]
0x18002cb85  add     r12d, r15d
0x18002cb88  mov     rax, [rbp+pullResult]
0x18002cb8c  imul    rax, [rbx+10308h]
0x18002cb94  add     rdx, rax
0x18002cb97  mov     eax, [rbx+68h]
0x18002cb9a  mov     [rbp+NumberOfBytesRead], rdx
0x18002cb9e  cmp     r12d, eax
0x18002cba1  jb      short loc_18002CB48
0x18002cba3  jmp     loc_18002CACC
```
