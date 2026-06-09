# CJob::LoadP(ushort const *,ulong,int,int)

- ea: `0x1800242b4`
- end: `0x180024714`
- name: `?LoadP@CJob@@QEAAJPEBGKHH@Z`
- size: `1120`
- prototype: `__int64 __fastcall(CJob *this, LPCWSTR lpFileName, DWORD, int, int)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180011690`
- `0x180015280`
- `0x180015d80`
- `0x180024290`
- `0x180027b30`
- `0x180028070`
- `0x180029a70`

## callees

- `0x180003ef0`
- `0x180007488`
- `0x1800074c8`
- `0x180023fdc`
- `0x1800242b4`
- `0x18002471c`
- `0x180024764`
- `0x180025a08`
- `0x180029b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800243c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024436`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800246f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024391`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024468`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800246f4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002442c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002442c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180024383`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180024383`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800243b8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800243b8`

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
0x1800242b4  mov     [rsp-38h+arg_0], rbx
0x1800242b9  mov     [rsp-38h+FileSizeHigh], r8d
0x1800242be  push    rbp
0x1800242bf  push    rsi
0x1800242c0  push    rdi
0x1800242c1  push    r12
0x1800242c3  push    r13
0x1800242c5  push    r14
0x1800242c7  push    r15
0x1800242c9  mov     rbp, rsp
0x1800242cc  sub     rsp, 40h
0x1800242d0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800242d4  xor     r12d, r12d
0x1800242d7  mov     r15d, r9d
0x1800242da  mov     rbx, rdx
0x1800242dd  mov     rdi, rcx
0x1800242e0  test    r9d, r9d
0x1800242e3  jz      short loc_180024356
0x1800242e5  mov     rcx, r14
0x1800242e8  inc     rcx
0x1800242eb  cmp     [rdx+rcx*2], r12w
0x1800242f0  jnz     short loc_1800242E8
0x1800242f2  inc     rcx
0x1800242f5  mov     eax, 2
0x1800242fa  mul     rcx
0x1800242fd  cmovb   rax, r14
0x180024301  mov     rcx, rax; Size
0x180024304  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024309  mov     rsi, rax
0x18002430c  test    rax, rax
0x18002430f  jnz     short loc_18002431B
0x180024311  mov     eax, 8007000Eh
0x180024316  jmp     loc_1800246FC
0x18002431b  mov     rcx, [rdi+98h]; Block
0x180024322  test    rcx, rcx
0x180024325  jz      short loc_18002432C
0x180024327  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002432c  mov     [rdi+98h], rsi
0x180024333  mov     rdx, r14
0x180024336  mov     [rsi], r12w
0x18002433a  inc     rdx
0x18002433d  cmp     [rbx+rdx*2], r12w
0x180024342  jnz     short loc_18002433A
0x180024344  mov     rcx, [rdi+98h]; unsigned __int16 *
0x18002434b  inc     rdx; unsigned __int64
0x18002434e  mov     r8, rbx; unsigned __int16 *
0x180024351  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024356  mov     r13d, 1
0x18002435c  mov     [rbp+hFile], r12
0x180024360  mov     r8d, r13d; dwShareMode
0x180024363  lea     r9, [rbp+hFile]; void **
0x180024367  mov     edx, 80000000h; dwDesiredAccess
0x18002436c  mov     rcx, rbx; lpFileName
0x18002436f  call    ?OpenFileWithRetry@@YAJPEBGKKPEAPEAX@Z; OpenFileWithRetry(ushort const *,ulong,ulong,void * *)
0x180024374  test    eax, eax
0x180024376  js      loc_1800246FC
0x18002437c  mov     r14, [rbp+hFile]
0x180024380  mov     rcx, r14; hFile
0x180024383  call    cs:__imp_GetFileType
0x180024389  cmp     eax, r13d
0x18002438c  jz      short loc_1800243A1
0x18002438e  mov     rcx, r14; hObject
0x180024391  call    cs:__imp_CloseHandle
0x180024397  mov     eax, 80070005h
0x18002439c  jmp     loc_1800246FC
0x1800243a1  test    r15d, r15d
0x1800243a4  jz      short loc_1800243AD
0x1800243a6  mov     [rdi+0A0h], r13d
0x1800243ad  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x1800243b1  mov     [rbp+FileSizeHigh], r12d
0x1800243b5  mov     rcx, r14; hFile
0x1800243b8  call    cs:__imp_GetFileSize
0x1800243be  mov     r15d, eax
0x1800243c1  cmp     eax, 0FFFFFFFFh
0x1800243c4  jnz     short loc_1800243E6
0x1800243c6  call    cs:__imp_GetLastError
0x1800243cc  mov     ebx, eax
0x1800243ce  test    eax, eax
0x1800243d0  jz      short loc_1800243E6
0x1800243d2  jle     loc_1800246EB
0x1800243d8  movzx   ebx, ax
0x1800243db  or      ebx, 80070000h
0x1800243e1  jmp     loc_1800246EB
0x1800243e6  cmp     [rbp+FileSizeHigh], r12d
0x1800243ea  jbe     short loc_1800243F6
0x1800243ec  mov     ebx, 8007000Dh
0x1800243f1  jmp     loc_1800246EB
0x1800243f6  cmp     r15d, 44h ; 'D'
0x1800243fa  jb      short loc_1800243EC
0x1800243fc  mov     rcx, r15; Size
0x1800243ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024404  mov     rsi, rax
0x180024407  test    rax, rax
0x18002440a  jnz     short loc_180024416
0x18002440c  mov     ebx, 8007000Eh
0x180024411  jmp     loc_1800246EB
0x180024416  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002441a  mov     [rbp+NumberOfBytesRead], r12d
0x18002441e  mov     r8d, r15d; nNumberOfBytesToRead
0x180024421  mov     [rsp+40h+lpOverlapped], r12; lpOverlapped
0x180024426  mov     rdx, rsi; lpBuffer
0x180024429  mov     rcx, r14; hFile
0x18002442c  call    cs:__imp_ReadFile
0x180024432  test    eax, eax
0x180024434  jnz     short loc_180024458
0x180024436  call    cs:__imp_GetLastError
0x18002443c  mov     ebx, eax
0x18002443e  test    eax, eax
0x180024440  jle     short loc_18002444B
0x180024442  movzx   ebx, ax
0x180024445  or      ebx, 80070000h
0x18002444b  mov     rcx, rsi; Block
0x18002444e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024453  jmp     loc_1800246EB
0x180024458  cmp     [rbp+NumberOfBytesRead], r15d
0x18002445c  jz      short loc_180024465
0x18002445e  mov     ebx, 8007000Dh
0x180024463  jmp     short loc_18002444B
0x180024465  mov     rcx, r14; hObject
0x180024468  call    cs:__imp_CloseHandle
0x18002446e  mov     rcx, rdi; this
0x180024471  or      r14, 0FFFFFFFFFFFFFFFFh
0x180024475  call    ?FreeProperties@CJob@@AEAAXXZ; CJob::FreeProperties(void)
0x18002447a  mov     rcx, [rdi+0E0h]; Block
0x180024481  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024486  lea     rcx, [r15+rsi]
0x18002448a  mov     [rdi+0E0h], rsi
0x180024491  lea     rax, [rsi+44h]
0x180024495  mov     [rdi+0E8h], rcx
0x18002449c  mov     [rbp+hFile], rax
0x1800244a0  movzx   eax, word ptr [rsi+2]
0x1800244a4  mov     [rbp+var_8], rcx
0x1800244a8  cmp     [rdi+2Ah], ax
0x1800244ac  jz      short loc_1800244B8
0x1800244ae  mov     ebx, 80041313h
0x1800244b3  jmp     loc_1800246FA
0x1800244b8  movzx   eax, word ptr [rsi]
0x1800244bb  lea     rdx, [rdi+42h]; void *
0x1800244bf  mov     [rdi+28h], ax
0x1800244c3  lea     rcx, [rbp+hFile]; this
0x1800244c7  movzx   eax, word ptr [rsi+2]
0x1800244cb  mov     r8d, 2; unsigned int
0x1800244d1  mov     [rdi+2Ah], ax
0x1800244d5  mov     ebx, 8007000Dh
0x1800244da  movups  xmm0, xmmword ptr [rsi+4]
0x1800244de  movdqu  xmmword ptr [rdi+2Ch], xmm0
0x1800244e3  movzx   eax, word ptr [rsi+16h]
0x1800244e7  mov     [rdi+3Ch], ax
0x1800244eb  movzx   eax, word ptr [rsi+18h]
0x1800244ef  mov     [rdi+3Eh], ax
0x1800244f3  movzx   eax, word ptr [rsi+1Ah]
0x1800244f7  mov     [rdi+40h], ax
0x1800244fb  movzx   eax, word ptr [rsi+1Eh]
0x1800244ff  mov     [rdi+44h], ax
0x180024503  movzx   eax, word ptr [rsi+1Ch]
0x180024507  mov     [rdi+46h], ax
0x18002450b  mov     eax, [rsi+20h]
0x18002450e  mov     [rdi+48h], eax
0x180024511  mov     eax, [rsi+24h]
0x180024514  mov     [rdi+4Ch], eax
0x180024517  mov     eax, [rsi+28h]
0x18002451a  mov     [rdi+50h], eax
0x18002451d  mov     eax, [rsi+2Ch]
0x180024520  mov     [rdi+54h], eax
0x180024523  mov     eax, [rsi+30h]
0x180024526  mov     [rdi+58h], eax
0x180024529  movups  xmm0, xmmword ptr [rsi+34h]
0x18002452d  movdqu  xmmword ptr [rdi+60h], xmm0
0x180024532  call    ?Read@CInputBuffer@@QEAAHPEAXK@Z; CInputBuffer::Read(void *,ulong)
0x180024537  test    eax, eax
0x180024539  jz      loc_1800246FA
0x18002453f  lea     rdx, [rdi+70h]; unsigned __int16 **
0x180024543  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x180024547  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x18002454c  test    eax, eax
0x18002454e  jz      loc_1800246FA
0x180024554  cmp     [rbp+arg_20], r12d
0x180024558  jz      loc_1800246E8
0x18002455e  lea     rdx, [rdi+78h]; unsigned __int16 **
0x180024562  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x180024566  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x18002456b  test    eax, eax
0x18002456d  jz      loc_1800246FA
0x180024573  lea     rdx, [rdi+80h]; unsigned __int16 **
0x18002457a  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x18002457e  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x180024583  test    eax, eax
0x180024585  jz      loc_1800246FA
0x18002458b  lea     rdx, [rdi+88h]; unsigned __int16 **
0x180024592  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x180024596  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x18002459b  test    eax, eax
0x18002459d  jz      loc_1800246FA
0x1800245a3  lea     rdx, [rdi+90h]; unsigned __int16 **
0x1800245aa  lea     rcx, [rbp+hFile]; struct CInputBuffer *
0x1800245ae  call    ?ReadString@@YAHPEAVCInputBuffer@@PEAPEAG@Z; ReadString(CInputBuffer *,ushort * *)
0x1800245b3  test    eax, eax
0x1800245b5  jz      loc_1800246FA
0x1800245bb  lea     rsi, [rdi+0B0h]
0x1800245c2  mov     [rdi+0A8h], r12
0x1800245c9  mov     rdx, rsi; void *
0x1800245cc  mov     [rsi], r12w
0x1800245d0  mov     r8d, 2; unsigned int
0x1800245d6  lea     rcx, [rbp+hFile]; this
0x1800245da  call    ?Read@CInputBuffer@@QEAAHPEAXK@Z; CInputBuffer::Read(void *,ulong)
0x1800245df  test    eax, eax
0x1800245e1  jz      loc_1800246FA
0x1800245e7  cmp     [rsi], r12w
0x1800245eb  jnz     short loc_1800245F6
0x1800245ed  mov     [rdi+0A8h], r12
0x1800245f4  jmp     short loc_180024615
0x1800245f6  mov     rcx, [rbp+hFile]
0x1800245fa  movzx   eax, word ptr [rsi]
0x1800245fd  mov     [rdi+0A8h], rcx
0x180024604  add     rcx, rax
0x180024607  mov     [rbp+hFile], rcx
0x18002460b  cmp     rcx, [rbp+var_8]
0x18002460f  ja      loc_1800246FA
0x180024615  lea     rsi, [rdi+0B2h]
0x18002461c  mov     [rdi+0B8h], r12
0x180024623  mov     rdx, rsi; void *
0x180024626  mov     [rsi], r12w
0x18002462a  mov     r8d, 2; unsigned int
0x180024630  lea     rcx, [rbp+hFile]; this
0x180024634  call    ?Read@CInputBuffer@@QEAAHPEAXK@Z; CInputBuffer::Read(void *,ulong)
0x180024639  test    eax, eax
0x18002463b  jz      loc_1800246FA
0x180024641  cmp     [rsi], r12w
0x180024645  jnz     short loc_180024656
0x180024647  mov     dword ptr [rdi+0C0h], 41303h
0x180024651  mov     eax, r12d
0x180024654  jmp     short loc_18002468D
0x180024656  cmp     word ptr [rsi], 8
0x18002465a  jnb     short loc_180024665
0x18002465c  mov     [rsi], r12w
0x180024660  jmp     loc_1800246FA
0x180024665  mov     rdx, [rbp+hFile]
0x180024669  movzx   ecx, word ptr [rsi]
0x18002466c  add     rcx, rdx
0x18002466f  mov     [rdi+0B8h], rdx
0x180024676  mov     [rbp+hFile], rcx
0x18002467a  cmp     rcx, [rbp+var_8]
0x18002467e  ja      short loc_1800246FA
0x180024680  mov     rax, [rdx]
0x180024683  mov     [rdi+0C0h], eax
0x180024689  shr     rax, 20h
0x18002468d  mov     ecx, 5Ch ; '\'
0x180024692  mov     rdx, rdi
0x180024695  mov     [rcx+rdx], eax
0x180024698  lea     rdx, [rbp+hFile]; struct CInputBuffer *
0x18002469c  mov     rcx, rdi; this
0x18002469f  call    ?_LoadTriggersFromBuffer@CJob@@AEAAJPEAVCInputBuffer@@@Z; CJob::_LoadTriggersFromBuffer(CInputBuffer *)
0x1800246a4  mov     ebx, eax
0x1800246a6  test    eax, eax
0x1800246a8  js      short loc_1800246FA
0x1800246aa  mov     r8d, 4; unsigned int
0x1800246b0  mov     [rbp+FileSizeHigh], r12d
0x1800246b4  lea     rdx, [rbp+FileSizeHigh]; void *
0x1800246b8  lea     rcx, [rbp+hFile]; this
0x1800246bc  call    ?Read@CInputBuffer@@QEAAHPEAXK@Z; CInputBuffer::Read(void *,ulong)
0x1800246c1  test    eax, eax
0x1800246c3  jz      short loc_1800246E8
0x1800246c5  cmp     word ptr [rbp+FileSizeHigh+2], r13w
0x1800246ca  ja      short loc_1800246E8
0x1800246cc  mov     rax, [rbp+hFile]
0x1800246d0  mov     [rdi+0D0h], rax
0x1800246d7  add     rax, 40h ; '@'
0x1800246db  cmp     rax, [rbp+var_8]
0x1800246df  jbe     short loc_1800246E8
0x1800246e1  mov     [rdi+0D0h], r12
0x1800246e8  mov     ebx, r12d
0x1800246eb  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800246ef  jz      short loc_1800246FA
0x1800246f1  mov     rcx, r14; hObject
0x1800246f4  call    cs:__imp_CloseHandle
0x1800246fa  mov     eax, ebx
0x1800246fc  mov     rbx, [rsp+40h+arg_0]
0x180024704  add     rsp, 40h
0x180024708  pop     r15
0x18002470a  pop     r14
0x18002470c  pop     r13
0x18002470e  pop     r12
0x180024710  pop     rdi
0x180024711  pop     rsi
0x180024712  pop     rbp
0x180024713  retn
```
