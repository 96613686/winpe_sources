# BeginMiniDump(_EXCEPTION_POINTERS *,ushort const *,void * *,_ULARGE_INTEGER *,void * *)

- ea: `0x180019eb8`
- end: `0x18001a0c2`
- name: `?BeginMiniDump@@YAPEAXPEAU_EXCEPTION_POINTERS@@PEBGPEAPEAXPEAT_ULARGE_INTEGER@@2@Z`
- size: `522`
- prototype: `void *(struct _EXCEPTION_POINTERS *, const unsigned __int16 *, void **, union _ULARGE_INTEGER *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001c830`

## callees

- `0x180019eb8`
- `0x180022bcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019f66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019f66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019f74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180019f74`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180019fc8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180019fc8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019f2a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019f2a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a06d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002903c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a06d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002903c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180019ff8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180019ff8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001a027`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001a027`
- `dbghelp!MiniDumpWriteDump` at `0x180019fb0`
- `dbghelp!MiniDumpWriteDump` at `0x180019fb0`

## pseudocode

```c
LPVOID __fastcall BeginMiniDump(
        struct _EXCEPTION_POINTERS *a1,
        const unsigned __int16 *a2,
        void **a3,
        union _ULARGE_INTEGER *a4,
        void **a5)
{
  union _ULARGE_INTEGER *v5; // rbx
  LPVOID v9; // r14
  __int64 v10; // rsi
  HANDLE FileW; // rdi
  DWORD CurrentProcessId; // ebx
  HANDLE CurrentProcess; // rax
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax
  DWORD FileSizeHigh[2]; // [rsp+40h] [rbp-58h] BYREF
  LPVOID v18; // [rsp+48h] [rbp-50h]
  __int64 v19; // [rsp+50h] [rbp-48h]
  HANDLE v20; // [rsp+58h] [rbp-40h]
  __int128 v21; // [rsp+60h] [rbp-38h] BYREF

  v5 = a4;
  v9 = 0;
  v18 = 0;
  v10 = -1;
  v19 = -1;
  *(_QWORD *)FileSizeHigh = 0;
  v21 = 0;
  FileW = CreateFileW(a2, 0xC0000000, 0, 0, 2u, 0x100u, 0);
  v20 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( a1 )
    {
      LODWORD(v21) = GetCurrentThreadId();
      *(_QWORD *)((char *)&v21 + 4) = a1;
      HIDWORD(v21) = 0;
    }
    CurrentProcessId = GetCurrentProcessId();
    CurrentProcess = GetCurrentProcess();
    if ( MiniDumpWriteDump(
           CurrentProcess,
           CurrentProcessId,
           FileW,
           MiniDumpNormal,
           (PMINIDUMP_EXCEPTION_INFORMATION)((unsigned __int64)&v21 & -(__int64)(a1 != 0)),
           0,
           0) )
    {
      FileSize = GetFileSize(FileW, &FileSizeHigh[1]);
      FileSizeHigh[0] = FileSize;
      if ( FileSize != -1 )
      {
        FileMappingW = CreateFileMappingW(FileW, 0, 2u, FileSizeHigh[1], FileSize, 0);
        v10 = (__int64)FileMappingW;
        v19 = (__int64)FileMappingW;
        if ( FileMappingW )
        {
          v9 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
          v18 = v9;
        }
      }
    }
    v5 = a4;
  }
  if ( v9 )
  {
    if ( v5 )
      *v5 = *(union _ULARGE_INTEGER *)FileSizeHigh;
    if ( a5 )
      *a5 = (void *)v10;
    if ( a3 )
      *a3 = FileW;
  }
  else
  {
    if ( v10 != -1 )
      CloseHandleWrapper(v10);
    if ( FileW != (HANDLE)-1LL )
    {
      CloseHandleWrapper(FileW);
      DeleteFileW(a2);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180019eb8  mov     r11, rsp
0x180019ebb  mov     [r11+8], rbx
0x180019ebf  mov     [r11+18h], rsi
0x180019ec3  mov     [r11+20h], r9
0x180019ec7  mov     [r11+10h], rdx
0x180019ecb  push    rdi
0x180019ecc  push    r12
0x180019ece  push    r13
0x180019ed0  push    r14
0x180019ed2  push    r15
0x180019ed4  sub     rsp, 70h
0x180019ed8  mov     rbx, r9
0x180019edb  mov     r13, r8
0x180019ede  mov     r12, rdx
0x180019ee1  mov     r15, rcx
0x180019ee4  xor     r14d, r14d
0x180019ee7  mov     [r11-50h], r14
0x180019eeb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019eef  mov     [r11-40h], rax
0x180019ef3  mov     rsi, rax
0x180019ef6  mov     [r11-48h], rax
0x180019efa  mov     [r11-58h], r14
0x180019efe  xor     eax, eax
0x180019f00  xorps   xmm0, xmm0
0x180019f03  movups  [rsp+98h+var_38], xmm0
0x180019f08  mov     [r11-68h], rax
0x180019f0c  mov     [rsp+98h+dwFlagsAndAttributes], 100h; dwFlagsAndAttributes
0x180019f14  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x180019f1c  xor     r9d, r9d; lpSecurityAttributes
0x180019f1f  xor     r8d, r8d; dwShareMode
0x180019f22  mov     edx, 0C0000000h; dwDesiredAccess
0x180019f27  mov     rcx, r12; lpFileName
0x180019f2a  call    cs:__imp_CreateFileW
0x180019f31  nop     dword ptr [rax+rax+00h]
0x180019f36  mov     rdi, rax
0x180019f39  mov     [rsp+98h+var_40], rax
0x180019f3e  cmp     rax, rsi
0x180019f41  jz      loc_18001A043
0x180019f47  test    r15, r15
0x180019f4a  jz      short loc_180019F66
0x180019f4c  call    cs:__imp_GetCurrentThreadId
0x180019f53  nop     dword ptr [rax+rax+00h]
0x180019f58  mov     dword ptr [rsp+98h+var_38], eax
0x180019f5c  mov     qword ptr [rsp+98h+var_38+4], r15
0x180019f61  mov     dword ptr [rsp+98h+var_38+0Ch], r14d
0x180019f66  call    cs:__imp_GetCurrentProcessId
0x180019f6d  nop     dword ptr [rax+rax+00h]
0x180019f72  mov     ebx, eax
0x180019f74  call    cs:__imp_GetCurrentProcess
0x180019f7b  nop     dword ptr [rax+rax+00h]
0x180019f80  mov     rcx, rax; hProcess
0x180019f83  neg     r15
0x180019f86  sbb     rax, rax
0x180019f89  lea     rdx, [rsp+98h+var_38]
0x180019f8e  and     rax, rdx
0x180019f91  mov     [rsp+98h+CallbackParam], 0; CallbackParam
0x180019f9a  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], 0; UserStreamParam
0x180019fa3  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; ExceptionParam
0x180019fa8  xor     r9d, r9d; DumpType
0x180019fab  mov     r8, rdi; hFile
0x180019fae  mov     edx, ebx; ProcessId
0x180019fb0  call    cs:__imp_MiniDumpWriteDump
0x180019fb7  nop     dword ptr [rax+rax+00h]
0x180019fbc  test    eax, eax
0x180019fbe  jz      short loc_18001A03B
0x180019fc0  lea     rdx, [rsp+98h+FileSizeHigh+4]; lpFileSizeHigh
0x180019fc5  mov     rcx, rdi; hFile
0x180019fc8  call    cs:__imp_GetFileSize
0x180019fcf  nop     dword ptr [rax+rax+00h]
0x180019fd4  mov     [rsp+98h+FileSizeHigh], eax
0x180019fd8  cmp     eax, 0FFFFFFFFh
0x180019fdb  jz      short loc_18001A03B
0x180019fdd  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], 0; lpName
0x180019fe6  mov     [rsp+98h+dwCreationDisposition], eax; dwMaximumSizeLow
0x180019fea  mov     r9d, [rsp+98h+FileSizeHigh+4]; dwMaximumSizeHigh
0x180019fef  xor     edx, edx; lpFileMappingAttributes
0x180019ff1  lea     r8d, [rdx+2]; flProtect
0x180019ff5  mov     rcx, rdi; hFile
0x180019ff8  call    cs:__imp_CreateFileMappingW
0x180019fff  nop     dword ptr [rax+rax+00h]
0x18001a004  mov     rsi, rax
0x18001a007  mov     [rsp+98h+var_48], rax
0x18001a00c  test    rax, rax
0x18001a00f  jz      short loc_18001A03B
0x18001a011  mov     qword ptr [rsp+98h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18001a01a  xor     r9d, r9d; dwFileOffsetLow
0x18001a01d  xor     r8d, r8d; dwFileOffsetHigh
0x18001a020  lea     edx, [r9+4]; dwDesiredAccess
0x18001a024  mov     rcx, rax; hFileMappingObject
0x18001a027  call    cs:__imp_MapViewOfFile
0x18001a02e  nop     dword ptr [rax+rax+00h]
0x18001a033  mov     r14, rax
0x18001a036  mov     [rsp+98h+var_50], rax
0x18001a03b  mov     rbx, [rsp+98h+arg_18]
0x18001a043  test    r14, r14
0x18001a046  jnz     short loc_18001A07E
0x18001a048  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001a04c  jz      short loc_18001A056
0x18001a04e  mov     rcx, rsi
0x18001a051  call    CloseHandleWrapper
0x18001a056  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001a05a  jz      short loc_18001A079
0x18001a05c  mov     rcx, rdi
0x18001a05f  call    CloseHandleWrapper
0x18001a064  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001a068  jz      short loc_18001A079
0x18001a06a  mov     rcx, r12; lpFileName
0x18001a06d  call    cs:__imp_DeleteFileW
0x18001a074  nop     dword ptr [rax+rax+00h]
0x18001a079  test    r14, r14
0x18001a07c  jz      short loc_18001A0A4
0x18001a07e  test    rbx, rbx
0x18001a081  jz      short loc_18001A08B
0x18001a083  mov     rax, qword ptr [rsp+98h+FileSizeHigh]
0x18001a088  mov     [rbx], rax
0x18001a08b  mov     rax, [rsp+98h+arg_20]
0x18001a093  test    rax, rax
0x18001a096  jz      short loc_18001A09B
0x18001a098  mov     [rax], rsi
0x18001a09b  test    r13, r13
0x18001a09e  jz      short loc_18001A0A4
0x18001a0a0  mov     [r13+0], rdi
0x18001a0a4  mov     rax, r14
0x18001a0a7  lea     r11, [rsp+98h+var_28]
0x18001a0ac  mov     rbx, [r11+30h]
0x18001a0b0  mov     rsi, [r11+40h]
0x18001a0b4  mov     rsp, r11
0x18001a0b7  pop     r15
0x18001a0b9  pop     r14
0x18001a0bb  pop     r13
0x18001a0bd  pop     r12
0x18001a0bf  pop     rdi
0x18001a0c0  retn
0x180028ffb  push    rbx
0x180028ffd  push    rbp
0x180028ffe  sub     rsp, 48h
0x180029002  mov     rbp, rdx
0x180029005  cmp     qword ptr [rbp+48h], 0
0x18002900a  jnz     short loc_180029049
0x18002900c  mov     rcx, [rbp+50h]
0x180029010  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029014  jz      short loc_18002901C
0x180029016  call    CloseHandleWrapper
0x18002901b  nop
0x18002901c  mov     rbx, [rbp+58h]
0x180029020  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180029024  jz      short loc_180029049
0x180029026  mov     rcx, rbx
0x180029029  call    CloseHandleWrapper
0x18002902e  nop
0x18002902f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180029033  jz      short loc_180029049
0x180029035  mov     rcx, [rbp+0A8h]; lpFileName
0x18002903c  call    cs:__imp_DeleteFileW
0x180029043  nop     dword ptr [rax+rax+00h]
0x180029048  nop
0x180029049  add     rsp, 48h
0x18002904d  pop     rbp
0x18002904e  pop     rbx
0x18002904f  retn
```
