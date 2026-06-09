# CJob::LoadP(ushort const *,ulong,int,int)

- ea: `0x180025974`
- end: `0x180025e09`
- name: `?LoadP@CJob@@QEAAJPEBGKHH@Z`
- size: `1173`
- prototype: `__int64 __usercall@<rax>(CJob *__hidden this@<rcx>, LPCWSTR lpFileName@<rdx>, unsigned int@<r8d>, int@<r9d>, int)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180012178`
- `0x180016040`
- `0x180016bf0`
- `0x180025950`
- `0x180029360`
- `0x180029920`
- `0x18002b4a4`

## callees

- `0x1800040c0`
- `0x180007948`
- `0x180007988`
- `0x18002568c`
- `0x180025974`
- `0x180025e10`
- `0x180025e5c`
- `0x1800271e8`
- `0x18002b5a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025b14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025a57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025b4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025de2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025a57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025b4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025de2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180025b04`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180025b04`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180025a43`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180025a43`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180025a84`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180025a84`

## pseudocode

```c
__int64 __fastcall CJob::LoadP(CJob *this, LPCWSTR lpFileName, DWORD a3, int a4, int a5)
{
  __int64 v8; // rcx
  _WORD *v9; // rsi
  __int64 result; // rax
  void *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r14
  DWORD FileSize; // eax
  size_t v15; // r15
  signed int LastError; // eax
  unsigned int TriggersFromBuffer; // ebx
  _WORD *v18; // rax
  _WORD *v19; // rsi
  signed int v20; // eax
  __int16 v21; // ax
  _WORD *v22; // rsi
  char *v23; // rcx
  __int64 v24; // rax
  _WORD *v25; // rsi
  unsigned __int64 v26; // rax
  unsigned __int64 *v27; // rdx
  char *v28; // rcx
  unsigned __int64 v29; // rax
  HANDLE v30; // rax
  HANDLE hFile; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v32; // [rsp+38h] [rbp-8h]
  DWORD FileSizeHigh; // [rsp+90h] [rbp+50h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+58h] BYREF

  FileSizeHigh = a3;
  if ( a4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( lpFileName[v8] );
    v9 = operator new(saturated_mul(v8 + 1, 2u));
    if ( !v9 )
      return 2147942414LL;
    v11 = (void *)*((_QWORD *)this + 19);
    if ( v11 )
      operator delete(v11);
    *((_QWORD *)this + 19) = v9;
    v12 = -1;
    *v9 = 0;
    do
      ++v12;
    while ( lpFileName[v12] );
    StringCchCopyW(*((unsigned __int16 **)this + 19), v12 + 1, lpFileName);
  }
  hFile = 0;
  result = OpenFileWithRetry(lpFileName, 0x80000000, 1u, &hFile);
  if ( (int)result >= 0 )
  {
    v13 = (__int64)hFile;
    if ( GetFileType(hFile) != 1 )
    {
      CloseHandle((HANDLE)v13);
      return 2147942405LL;
    }
    if ( a4 )
      *((_DWORD *)this + 40) = 1;
    FileSizeHigh = 0;
    FileSize = GetFileSize((HANDLE)v13, &FileSizeHigh);
    v15 = FileSize;
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
      TriggersFromBuffer = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          TriggersFromBuffer = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_57;
      }
    }
    if ( FileSizeHigh || (unsigned int)v15 < 0x44 )
    {
      TriggersFromBuffer = -2147024883;
      goto LABEL_57;
    }
    v18 = operator new(v15);
    v19 = v18;
    if ( !v18 )
    {
      TriggersFromBuffer = -2147024882;
      goto LABEL_57;
    }
    NumberOfBytesRead = 0;
    if ( !ReadFile((HANDLE)v13, v18, v15, &NumberOfBytesRead, 0) )
    {
      v20 = GetLastError();
      TriggersFromBuffer = v20;
      if ( v20 > 0 )
        TriggersFromBuffer = (unsigned __int16)v20 | 0x80070000;
      goto LABEL_28;
    }
    if ( NumberOfBytesRead != (_DWORD)v15 )
    {
      TriggersFromBuffer = -2147024883;
LABEL_28:
      operator delete(v19);
      goto LABEL_57;
    }
    CloseHandle((HANDLE)v13);
    v13 = -1;
    CJob::FreeProperties(this);
    operator delete(*((void **)this + 28));
    *((_QWORD *)this + 28) = v19;
    *((_QWORD *)this + 29) = (char *)v19 + v15;
    hFile = v19 + 34;
    v21 = v19[1];
    v32 = (unsigned __int64)v19 + v15;
    if ( *((_WORD *)this + 21) != v21 )
      return (unsigned int)-2147216621;
    *((_WORD *)this + 20) = *v19;
    *((_WORD *)this + 21) = v19[1];
    TriggersFromBuffer = -2147024883;
    *(_OWORD *)((char *)this + 44) = *(_OWORD *)(v19 + 2);
    *((_WORD *)this + 30) = v19[11];
    *((_WORD *)this + 31) = v19[12];
    *((_WORD *)this + 32) = v19[13];
    *((_WORD *)this + 34) = v19[15];
    *((_WORD *)this + 35) = v19[14];
    *((_DWORD *)this + 18) = *((_DWORD *)v19 + 8);
    *((_DWORD *)this + 19) = *((_DWORD *)v19 + 9);
    *((_DWORD *)this + 20) = *((_DWORD *)v19 + 10);
    *((_DWORD *)this + 21) = *((_DWORD *)v19 + 11);
    *((_DWORD *)this + 22) = *((_DWORD *)v19 + 12);
    *((_OWORD *)this + 6) = *(_OWORD *)(v19 + 26);
    if ( !CInputBuffer::Read((CInputBuffer *)&hFile, (char *)this + 66, 2u)
      || !(unsigned int)ReadString((struct CInputBuffer *)&hFile, (unsigned __int16 **)this + 14) )
    {
      return TriggersFromBuffer;
    }
    if ( a5 )
    {
      if ( !(unsigned int)ReadString((struct CInputBuffer *)&hFile, (unsigned __int16 **)this + 15) )
        return TriggersFromBuffer;
      if ( !(unsigned int)ReadString((struct CInputBuffer *)&hFile, (unsigned __int16 **)this + 16) )
        return TriggersFromBuffer;
      if ( !(unsigned int)ReadString((struct CInputBuffer *)&hFile, (unsigned __int16 **)this + 17) )
        return TriggersFromBuffer;
      if ( !(unsigned int)ReadString((struct CInputBuffer *)&hFile, (unsigned __int16 **)this + 18) )
        return TriggersFromBuffer;
      v22 = (_WORD *)((char *)this + 176);
      *((_QWORD *)this + 21) = 0;
      *((_WORD *)this + 88) = 0;
      if ( !CInputBuffer::Read((CInputBuffer *)&hFile, (char *)this + 176, 2u) )
        return TriggersFromBuffer;
      if ( *v22 )
      {
        v23 = (char *)hFile;
        v24 = (unsigned __int16)*v22;
        *((_QWORD *)this + 21) = hFile;
        hFile = &v23[v24];
        if ( (unsigned __int64)&v23[v24] > v32 )
          return TriggersFromBuffer;
      }
      else
      {
        *((_QWORD *)this + 21) = 0;
      }
      v25 = (_WORD *)((char *)this + 178);
      *((_QWORD *)this + 23) = 0;
      *((_WORD *)this + 89) = 0;
      if ( !CInputBuffer::Read((CInputBuffer *)&hFile, (char *)this + 178, 2u) )
        return TriggersFromBuffer;
      if ( *v25 )
      {
        if ( *v25 < 8u )
        {
          *v25 = 0;
          return TriggersFromBuffer;
        }
        v27 = (unsigned __int64 *)hFile;
        v28 = (char *)hFile + (unsigned __int16)*v25;
        *((_QWORD *)this + 23) = hFile;
        hFile = v28;
        if ( (unsigned __int64)v28 > v32 )
          return TriggersFromBuffer;
        v29 = *v27;
        *((_DWORD *)this + 48) = *v27;
        v26 = HIDWORD(v29);
      }
      else
      {
        *((_DWORD *)this + 48) = 267011;
        LODWORD(v26) = 0;
      }
      *((_DWORD *)this + 23) = v26;
      TriggersFromBuffer = CJob::_LoadTriggersFromBuffer(this, (struct CInputBuffer *)&hFile);
      if ( (TriggersFromBuffer & 0x80000000) != 0 )
        return TriggersFromBuffer;
      FileSizeHigh = 0;
      if ( CInputBuffer::Read((CInputBuffer *)&hFile, &FileSizeHigh, 4u) )
      {
        if ( HIWORD(FileSizeHigh) <= 1u )
        {
          v30 = hFile;
          *((_QWORD *)this + 26) = hFile;
          if ( (unsigned __int64)v30 + 64 > v32 )
            *((_QWORD *)this + 26) = 0;
        }
      }
    }
    TriggersFromBuffer = 0;
LABEL_57:
    if ( v13 != -1 )
      CloseHandle((HANDLE)v13);
    return TriggersFromBuffer;
  }
  return result;
}

```

## disassembly

```asm
0x180025974  mov     [rsp-38h+arg_0], rbx
0x180025979  mov     [rsp-38h+FileSizeHigh], r8d
0x18002597e  push    rbp
0x18002597f  push    rsi
0x180025980  push    rdi
0x180025981  push    r12
0x180025983  push    r13
0x180025985  push    r14
0x180025987  push    r15
0x180025989  mov     rbp, rsp
0x18002598c  sub     rsp, 40h
0x180025990  or      r14, 0FFFFFFFFFFFFFFFFh
0x180025994  xor     r12d, r12d
0x180025997  mov     r15d, r9d
0x18002599a  mov     rbx, rdx
0x18002599d  mov     rdi, rcx
0x1800259a0  test    r9d, r9d
0x1800259a3  jz      short loc_180025A16
0x1800259a5  mov     rcx, r14
0x1800259a8  inc     rcx
0x1800259ab  cmp     [rdx+rcx*2], r12w
0x1800259b0  jnz     short loc_1800259A8
0x1800259b2  inc     rcx
0x1800259b5  mov     eax, 2
0x1800259ba  mul     rcx
0x1800259bd  cmovb   rax, r14
0x1800259c1  mov     rcx, rax; Size
0x1800259c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800259c9  mov     rsi, rax
0x1800259cc  test    rax, rax
0x1800259cf  jnz     short loc_1800259DB
0x1800259d1  mov     eax, 8007000Eh
0x1800259d6  jmp     loc_180025DF0
0x1800259db  mov     rcx, [rdi+98h]; Block
0x1800259e2  test    rcx, rcx
0x1800259e5  jz      short loc_1800259EC
0x1800259e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800259ec  mov     [rdi+98h], rsi
0x1800259f3  mov     rdx, r14
0x1800259f6  mov     [rsi], r12w
0x1800259fa  inc     rdx
0x1800259fd  cmp     [rbx+rdx*2], r12w
0x180025a02  jnz     short loc_1800259FA
0x180025a04  mov     rcx, [rdi+98h]; unsigned __int16 *
0x180025a0b  inc     rdx; unsigned __int64
0x180025a0e  mov     r8, rbx; unsigned __int16 *
0x180025a11  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025a16  mov     r13d, 1
0x180025a1c  mov     [rbp+hFile], r12
0x180025a20  mov     r8d, r13d; dwShareMode
0x180025a23  lea     r9, [rbp+hFile]; void **
0x180025a27  mov     edx, 80000000h; dwDesiredAccess
0x180025a2c  mov     rcx, rbx; lpFileName
0x180025a2f  call    ?OpenFileWithRetry@@YAJPEBGKKPEAPEAX@Z; OpenFileWithRetry(ushort const *,ulong,ulong,void * *)
0x180025a34  test    eax, eax
0x180025a36  js      loc_180025DF0
0x180025a3c  mov     r14, [rbp+hFile]
0x180025a40  mov     rcx, r14; hFile
0x180025a43  call    cs:__imp_GetFileType
0x180025a4a  nop     dword ptr [rax+rax+00h]
0x180025a4f  cmp     eax, r13d
0x180025a52  jz      short loc_180025A6D
0x180025a54  mov     rcx, r14; hObject
0x180025a57  call    cs:__imp_CloseHandle
0x180025a5e  nop     dword ptr [rax+rax+00h]
0x180025a63  mov     eax, 80070005h
0x180025a68  jmp     loc_180025DF0
0x180025a6d  test    r15d, r15d
0x180025a70  jz      short loc_180025A79
0x180025a72  mov     [rdi+0A0h], r13d
0x180025a79  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x180025a7d  mov     [rbp+FileSizeHigh], r12d
0x180025a81  mov     rcx, r14; hFile
0x180025a84  call    cs:__imp_GetFileSize
0x180025a8b  nop     dword ptr [rax+rax+00h]
0x180025a90  mov     r15d, eax
0x180025a93  cmp     eax, 0FFFFFFFFh
0x180025a96  jnz     short loc_180025ABE
0x180025a98  call    cs:__imp_GetLastError
0x180025a9f  nop     dword ptr [rax+rax+00h]
0x180025aa4  mov     ebx, eax
0x180025aa6  test    eax, eax
0x180025aa8  jz      short loc_180025ABE
0x180025aaa  jle     loc_180025DD9
0x180025ab0  movzx   ebx, ax
0x180025ab3  or      ebx, 80070000h
0x180025ab9  jmp     loc_180025DD9
0x180025abe  cmp     [rbp+FileSizeHigh], r12d
0x180025ac2  jbe     short loc_180025ACE
0x180025ac4  mov     ebx, 8007000Dh
0x180025ac9  jmp     loc_180025DD9
0x180025ace  cmp     r15d, 44h ; 'D'
0x180025ad2  jb      short loc_180025AC4
0x180025ad4  mov     rcx, r15; Size
0x180025ad7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025adc  mov     rsi, rax
0x180025adf  test    rax, rax
0x180025ae2  jnz     short loc_180025AEE
0x180025ae4  mov     ebx, 8007000Eh
0x180025ae9  jmp     loc_180025DD9
0x180025aee  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180025af2  mov     [rbp+NumberOfBytesRead], r12d
0x180025af6  mov     r8d, r15d; nNumberOfBytesToRead
0x180025af9  mov     [rsp+40h+lpOverlapped], r12; lpOverlapped
0x180025afe  mov     rdx, rsi; lpBuffer
0x180025b01  mov     rcx, r14; hFile
0x180025b04  call    cs:__imp_ReadFile
0x180025b0b  nop     dword ptr [rax+rax+00h]
0x180025b10  test    eax, eax
0x180025b12  jnz     short loc_180025B3C
0x180025b14  call    cs:__imp_GetLastError
0x180025b1b  nop     dword ptr [rax+rax+00h]
0x180025b20  mov     ebx, eax
0x180025b22  test    eax, eax
0x180025b24  jle     short loc_180025B2F
0x180025b26  movzx   ebx, ax
0x180025b29  or      ebx, 80070000h
0x180025b2f  mov     rcx, rsi; Block
0x180025b32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025b37  jmp     loc_180025DD9
0x180025b3c  cmp     [rbp+NumberOfBytesRead], r15d
0x180025b40  jz      short loc_180025B49
0x180025b42  mov     ebx, 8007000Dh
0x180025b47  jmp     short loc_180025B2F
0x180025b49  mov     rcx, r14; hObject
0x180025b4c  call    cs:__imp_CloseHandle
0x180025b53  nop     dword ptr [rax+rax+00h]
0x180025b58  mov     rcx, rdi; this
0x180025b5b  or      r14, 0FFFFFFFFFFFFFFFFh
0x180025b5f  call    ?FreeProperties@CJob@@AEAAXXZ; CJob::FreeProperties(void)
0x180025b64  mov     rcx, [rdi+0E0h]; Block
0x180025b6b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025b70  lea     rcx, [r15+rsi]
0x180025b74  mov     [rdi+0E0h], rsi
0x180025b7b  lea     rax, [rsi+44h]
0x180025b7f  mov     [rdi+0E8h], rcx
0x180025b86  mov     [rbp+hFile], rax
0x180025b8a  movzx   eax, word ptr [rsi+2]
0x180025b8e  mov     [rbp+var_8], rcx
0x180025b92  cmp     [rdi+2Ah], ax
0x180025b96  jz      short loc_180025BA2
0x180025b98  mov     ebx, 80041313h
0x180025b9d  jmp     loc_180025DEE
0x180025ba2  movzx   eax, word ptr [rsi]
0x180025ba5  lea     rdx, [rdi+42h]; void *
0x180025ba9  mov     [rdi+28h], ax
0x180025bad  lea     rcx, [rbp+hFile]; this
0x180025bb1  movzx   eax, word ptr [rsi+2]
0x180025bb5  mov     r8d, 2; unsigned int
0x180025bbb  mov     [rdi+2Ah], ax
0x180025bbf  mov     ebx, 8007000Dh
0x180025bc4  movups  xmm0, xmmword ptr [rsi+4]
0x180025bc8  movdqu  xmmword ptr [rdi+2Ch], xmm0
0x180025bcd  movzx   eax, word ptr [rsi+16h]
0x180025bd1  mov     [rdi+3Ch], ax
0x180025bd5  movzx   eax, word ptr [rsi+18h]
0x180025bd9  mov     [rdi+3Eh], ax
0x180025bdd  movzx   eax, word ptr [rsi+1Ah]
0x180025be1  mov     [rdi+40h], ax
0x180025be5  movzx   eax, word ptr [rsi+1Eh]
0x180025be9  mov     [rdi+44h], ax
0x180025bed  movzx   eax, word ptr [rsi+1Ch]
0x180025bf1  mov     [rdi+46h], ax
0x180025bf5  mov     eax, [rsi+20h]
0x180025bf8  mov     [rdi+48h], eax
0x180025bfb  mov     eax, [rsi+24h]
0x180025bfe  mov     [rdi+4Ch], eax
0x180025c01  mov     eax, [rsi+28h]
0x180025c04  mov     [rdi+50h], eax
0x180025c07  mov     eax, [rsi+2Ch]
0x180025c0a  mov     [rdi+54h], eax
0x180025c0d  mov     eax, [rsi+30h]
0x180025c10  mov     [rdi+58h], eax
0x180025c13  movups  xmm0, xmmword ptr [rsi+34h]
0x180025c17  movdqu  xmmword ptr [rdi+60h], xmm0
0x180025c1c  call    ?Read@CInputBuffer@@QEAAHPEAXK@Z; CInputBuffer::Read(void *,ulong)
0x180025c21  test    eax, eax
0x180025c23  jz      loc_180025DEE
0x180025c29  lea     rdx, [rdi+70h]; unsigned __int16 **
0x180025c2d  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x180025c31  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x180025c36  test    eax, eax
0x180025c38  jz      loc_180025DEE
0x180025c3e  cmp     [rbp+arg_20], r12d
0x180025c42  jz      loc_180025DD6
0x180025c48  lea     rdx, [rdi+78h]; unsigned __int16 **
0x180025c4c  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x180025c50  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x180025c55  test    eax, eax
0x180025c57  jz      loc_180025DEE
0x180025c5d  lea     rdx, [rdi+80h]; unsigned __int16 **
0x180025c64  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x180025c68  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x180025c6d  test    eax, eax
0x180025c6f  jz      loc_180025DEE
0x180025c75  lea     rdx, [rdi+88h]; unsigned __int16 **
0x180025c7c  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x180025c80  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x180025c85  test    eax, eax
0x180025c87  jz      loc_180025DEE
0x180025c8d  lea     rdx, [rdi+90h]; unsigned __int16 **
0x180025c94  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x180025c98  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x180025c9d  test    eax, eax
0x180025c9f  jz      loc_180025DEE
0x180025ca5  lea     rsi, [rdi+0B0h]
0x180025cac  mov     [rdi+0A8h], r12
0x180025cb3  mov     rdx, rsi; void *
0x180025cb6  mov     [rsi], r12w
0x180025cba  mov     r8d, 2; unsigned int
0x180025cc0  lea     rcx, [rbp+hFile]; this
0x180025cc4  call    ?Read@CInputBuffer@@QEAAHPEAXK@Z; CInputBuffer::Read(void *,ulong)
0x180025cc9  test    eax, eax
0x180025ccb  jz      loc_180025DEE
0x180025cd1  cmp     [rsi], r12w
0x180025cd5  jnz     short loc_180025CE0
0x180025cd7  mov     [rdi+0A8h], r12
0x180025cde  jmp     short loc_180025CFF
0x180025ce0  mov     rcx, [rbp+hFile]
0x180025ce4  movzx   eax, word ptr [rsi]
0x180025ce7  mov     [rdi+0A8h], rcx
0x180025cee  add     rcx, rax
0x180025cf1  mov     [rbp+hFile], rcx
0x180025cf5  cmp     rcx, [rbp+var_8]
0x180025cf9  ja      loc_180025DEE
0x180025cff  lea     rsi, [rdi+0B2h]
0x180025d06  mov     [rdi+0B8h], r12
0x180025d0d  mov     rdx, rsi; void *
0x180025d10  mov     [rsi], r12w
0x180025d14  mov     r8d, 2; unsigned int
0x180025d1a  lea     rcx, [rbp+hFile]; this
0x180025d1e  call    ?Read@CInputBuffer@@QEAAHPEAXK@Z; CInputBuffer::Read(void *,ulong)
0x180025d23  test    eax, eax
0x180025d25  jz      loc_180025DEE
0x180025d2b  cmp     [rsi], r12w
0x180025d2f  jnz     short loc_180025D40
0x180025d31  mov     dword ptr [rdi+0C0h], 41303h
0x180025d3b  mov     eax, r12d
0x180025d3e  jmp     short loc_180025D7B
0x180025d40  cmp     word ptr [rsi], 8
0x180025d44  jnb     short loc_180025D4F
0x180025d46  mov     [rsi], r12w
0x180025d4a  jmp     loc_180025DEE
0x180025d4f  mov     rdx, [rbp+hFile]
0x180025d53  movzx   ecx, word ptr [rsi]
0x180025d56  add     rcx, rdx
0x180025d59  mov     [rdi+0B8h], rdx
0x180025d60  mov     [rbp+hFile], rcx
0x180025d64  cmp     rcx, [rbp+var_8]
0x180025d68  ja      loc_180025DEE
0x180025d6e  mov     rax, [rdx]
0x180025d71  mov     [rdi+0C0h], eax
0x180025d77  shr     rax, 20h
0x180025d7b  mov     ecx, 5Ch ; '\'
0x180025d80  mov     rdx, rdi
0x180025d83  mov     [rcx+rdx], eax
0x180025d86  lea     rdx, [rbp+hFile]; struct CInputBuffer *
0x180025d8a  mov     rcx, rdi; this
0x180025d8d  call    ?_LoadTriggersFromBuffer@CJob@@AEAAJPEAVCInputBuffer@@@Z; CJob::_LoadTriggersFromBuffer(CInputBuffer *)
0x180025d92  mov     ebx, eax
0x180025d94  test    eax, eax
0x180025d96  js      short loc_180025DEE
0x180025d98  mov     r8d, 4; unsigned int
0x180025d9e  mov     [rbp+FileSizeHigh], r12d
0x180025da2  lea     rdx, [rbp+FileSizeHigh]; void *
0x180025da6  lea     rcx, [rbp+hFile]; this
0x180025daa  call    ?Read@CInputBuffer@@QEAAHPEAXK@Z; CInputBuffer::Read(void *,ulong)
0x180025daf  test    eax, eax
0x180025db1  jz      short loc_180025DD6
0x180025db3  cmp     word ptr [rbp+FileSizeHigh+2], r13w
0x180025db8  ja      short loc_180025DD6
0x180025dba  mov     rax, [rbp+hFile]
0x180025dbe  mov     [rdi+0D0h], rax
0x180025dc5  add     rax, 40h ; '@'
0x180025dc9  cmp     rax, [rbp+var_8]
0x180025dcd  jbe     short loc_180025DD6
0x180025dcf  mov     [rdi+0D0h], r12
0x180025dd6  mov     ebx, r12d
0x180025dd9  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180025ddd  jz      short loc_180025DEE
0x180025ddf  mov     rcx, r14; hObject
0x180025de2  call    cs:__imp_CloseHandle
0x180025de9  nop     dword ptr [rax+rax+00h]
0x180025dee  mov     eax, ebx
0x180025df0  mov     rbx, [rsp+40h+arg_0]
0x180025df8  add     rsp, 40h
0x180025dfc  pop     r15
0x180025dfe  pop     r14
0x180025e00  pop     r13
0x180025e02  pop     r12
0x180025e04  pop     rdi
0x180025e05  pop     rsi
0x180025e06  pop     rbp
0x180025e07  retn
```
