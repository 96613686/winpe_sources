# CWiaLog::ProcessTruncation(void)

- ea: `0x180074758`
- end: `0x180074903`
- name: `?ProcessTruncation@CWiaLog@@AEAAXXZ`
- size: `427`
- prototype: `void __fastcall(CWiaLog *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180074360`
- `0x180074440`

## callees

- `0x180010d78`
- `0x180033cc0`
- `0x180039b40`
- `0x180074758`
- `0x180074db0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180074863`
- `KERNEL32!WriteFile` at `0x180074863`
- `KERNEL32!LocalFree` at `0x1800748e2`
- `KERNEL32!LocalFree` at `0x1800748e2`
- `KERNEL32!LocalAlloc` at `0x1800747d9`
- `KERNEL32!LocalAlloc` at `0x1800747d9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800747fb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180074830`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800747fb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180074830`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800747a1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800747a1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007483a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18007483a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007481c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007481c`

## pseudocode

```c
void __fastcall CWiaLog::ProcessTruncation(CWiaLog *this)
{
  void *v2; // rcx
  DWORD nFileSizeLow; // ebx
  HLOCAL v4; // rsi
  BOOL v5; // ebx
  int v6; // r8d
  int v7; // r8d
  unsigned int v8; // r11d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+34h] [rbp-CCh] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v15[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = (void *)*((_QWORD *)this + 5);
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandle(v2, &FileInformation) )
  {
    nFileSizeLow = FileInformation.nFileSizeLow;
    if ( FileInformation.nFileSizeLow > 0x55730 )
    {
      NumberOfBytesRead = 0;
      NumberOfBytesWritten = 0;
      v4 = LocalAlloc(0x40u, 0x55730u);
      if ( v4 )
      {
        SetFilePointer(*((HANDLE *)this + 5), nFileSizeLow - 350000, 0, 0);
        v5 = ReadFile(*((HANDLE *)this + 5), v4, 0x55730u, &NumberOfBytesRead, 0);
        SetFilePointer(*((HANDLE *)this + 5), 0, 0, 0);
        SetEndOfFile(*((HANDLE *)this + 5));
        if ( v5 )
        {
          WriteFile(*((HANDLE *)this + 5), v4, 0x55730u, &NumberOfBytesWritten, 0);
          CWiaLog::WriteStringToLog(this, L" ", v6);
          CWiaLog::WriteStringToLog(
            this,
            L"=============================================================================",
            v7);
          StringCchCopyW(v15, 0x104u, (const unsigned __int16 *)this + 28);
          StringCchCatW(v15, v8, L" REQUESTED A FILE TRUNCATION");
          CWiaLog::WriteStringToLog(this, L"          (Data above this marker is saved from a previous session)", v9);
          CWiaLog::WriteStringToLog(
            this,
            L"=============================================================================",
            v10);
          CWiaLog::WriteStringToLog(this, L" ", v11);
        }
        LocalFree(v4);
      }
    }
  }
}

```

## disassembly

```asm
0x180074758  push    rbp
0x18007475a  push    rbx
0x18007475b  push    rsi
0x18007475c  push    rdi
0x18007475d  lea     rbp, [rsp-198h]
0x180074765  sub     rsp, 298h
0x18007476c  mov     rax, cs:__security_cookie
0x180074773  xor     rax, rsp
0x180074776  mov     [rbp+1B0h+var_30], rax
0x18007477d  xorps   xmm0, xmm0
0x180074780  lea     rdx, [rsp+2B0h+FileInformation]; lpFileInformation
0x180074785  mov     rdi, rcx
0x180074788  xor     eax, eax
0x18007478a  mov     rcx, [rcx+28h]; hFile
0x18007478e  movups  xmmword ptr [rsp+2B0h+FileInformation.dwFileAttributes], xmm0
0x180074793  mov     [rsp+2B0h+FileInformation.nFileIndexLow], eax
0x180074797  movups  xmmword ptr [rsp+2B0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18007479c  movups  xmmword ptr [rsp+2B0h+FileInformation.nFileSizeHigh], xmm0
0x1800747a1  call    cs:__imp_GetFileInformationByHandle
0x1800747a7  test    eax, eax
0x1800747a9  jz      loc_1800748E8
0x1800747af  mov     ebx, [rsp+2B0h+FileInformation.nFileSizeLow]
0x1800747b3  cmp     ebx, 55730h
0x1800747b9  jbe     loc_1800748E8
0x1800747bf  mov     edx, 55730h; uBytes
0x1800747c4  mov     [rsp+2B0h+NumberOfBytesRead], 0
0x1800747cc  mov     ecx, 40h ; '@'; uFlags
0x1800747d1  mov     [rsp+2B0h+NumberOfBytesWritten], 0
0x1800747d9  call    cs:__imp_LocalAlloc
0x1800747df  mov     rsi, rax
0x1800747e2  test    rax, rax
0x1800747e5  jz      loc_1800748E8
0x1800747eb  mov     rcx, [rdi+28h]; hFile
0x1800747ef  lea     edx, [rbx-55730h]; lDistanceToMove
0x1800747f5  xor     r9d, r9d; dwMoveMethod
0x1800747f8  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800747fb  call    cs:__imp_SetFilePointer
0x180074801  mov     rcx, [rdi+28h]; hFile
0x180074805  lea     r9, [rsp+2B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18007480a  mov     r8d, 55730h; nNumberOfBytesToRead
0x180074810  mov     [rsp+2B0h+lpOverlapped], 0; lpOverlapped
0x180074819  mov     rdx, rsi; lpBuffer
0x18007481c  call    cs:__imp_ReadFile
0x180074822  mov     rcx, [rdi+28h]; hFile
0x180074826  xor     r9d, r9d; dwMoveMethod
0x180074829  xor     r8d, r8d; lpDistanceToMoveHigh
0x18007482c  xor     edx, edx; lDistanceToMove
0x18007482e  mov     ebx, eax
0x180074830  call    cs:__imp_SetFilePointer
0x180074836  mov     rcx, [rdi+28h]; hFile
0x18007483a  call    cs:__imp_SetEndOfFile
0x180074840  test    ebx, ebx
0x180074842  jz      loc_1800748DF
0x180074848  mov     rcx, [rdi+28h]; hFile
0x18007484c  lea     r9, [rsp+2B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180074851  mov     r8d, 55730h; nNumberOfBytesToWrite
0x180074857  mov     [rsp+2B0h+lpOverlapped], 0; lpOverlapped
0x180074860  mov     rdx, rsi; lpBuffer
0x180074863  call    cs:__imp_WriteFile
0x180074869  lea     rdx, asc_1800A15CC; " "
0x180074870  mov     rcx, rdi; this
0x180074873  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x180074878  lea     rdx, asc_1800A1530; "======================================="...
0x18007487f  mov     rcx, rdi; this
0x180074882  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x180074887  mov     r11d, 104h
0x18007488d  lea     r8, [rdi+38h]; unsigned __int16 *
0x180074891  mov     edx, r11d; unsigned __int64
0x180074894  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x180074899  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007489e  lea     r8, aRequestedAFile; " REQUESTED A FILE TRUNCATION"
0x1800748a5  mov     edx, r11d; unsigned __int64
0x1800748a8  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x1800748ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800748b2  lea     rdx, aDataAboveThisM; "          (Data above this marker is sa"...
0x1800748b9  mov     rcx, rdi; this
0x1800748bc  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x1800748c1  lea     rdx, asc_1800A1530; "======================================="...
0x1800748c8  mov     rcx, rdi; this
0x1800748cb  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x1800748d0  lea     rdx, asc_1800A15CC; " "
0x1800748d7  mov     rcx, rdi; this
0x1800748da  call    ?WriteStringToLog@CWiaLog@@AEAAXPEAGH@Z; CWiaLog::WriteStringToLog(ushort *,int)
0x1800748df  mov     rcx, rsi; hMem
0x1800748e2  call    cs:__imp_LocalFree
0x1800748e8  mov     rcx, [rbp+1B0h+var_30]
0x1800748ef  xor     rcx, rsp; StackCookie
0x1800748f2  call    __security_check_cookie
0x1800748f7  add     rsp, 298h
0x1800748fe  pop     rdi
0x1800748ff  pop     rsi
0x180074900  pop     rbx
0x180074901  pop     rbp
0x180074902  retn
```
