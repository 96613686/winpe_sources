# BfspMapFileForRead

- ea: `0x1800318b0`
- end: `0x180031aba`
- name: `BfspMapFileForRead`
- size: `522`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800340fc`
- `0x180037c40`
- `0x18003814c`

## callees

- `0x1800318b0`
- `0x180031b50`
- `0x1800366b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180031962`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180031962`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800318ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800318ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031a8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031a8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003196c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800318fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003196c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800319f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031a85`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800319e7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800319e7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180031a37`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180031a37`

## string_xrefs

- `0x180031925`: `Failed to open file %s for read! Error code = %#x`
- `0x180031941`: `Unable to open file %s for read because the file or path does not exist`
- `0x180031a12`: `CreateFileMapping(%s) failed! Error code = %#x`

## pseudocode

```c
LPVOID __fastcall BfspMapFileForRead(LPCWSTR lpFileName, DWORD *a2, _QWORD *a3)
{
  LPVOID v3; // r14
  HANDLE FileW; // rax
  void *v8; // rsi
  DWORD LastError; // ebx
  DWORD v10; // eax
  HANDLE FileMappingW; // rbp
  DWORD v12; // eax
  DWORD v13; // eax
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  FileSize.QuadPart = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError - 2 <= 1 )
    {
      BfspLogMessage(2, L"Unable to open file %s for read because the file or path does not exist", lpFileName);
    }
    else
    {
      if ( LastError == 5 || LastError - 32 <= 1 )
        BfspPrintFileOwnerProcess(lpFileName);
      BfspLogMessage(4, L"Failed to open file %s for read! Error code = %#x", lpFileName, LastError);
    }
  }
  else
  {
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      if ( FileSize.HighPart )
      {
        LastError = 87;
        BfspLogMessage(4, L"File %s is too large!", lpFileName);
      }
      else
      {
        FileMappingW = CreateFileMappingW(v8, 0, 2u, 0, FileSize.LowPart, 0);
        if ( FileMappingW )
        {
          v3 = MapViewOfFile(FileMappingW, 4u, 0, 0, FileSize.LowPart);
          if ( v3 )
          {
            *a2 = FileSize.LowPart;
            *a3 = v8;
            a3[1] = FileMappingW;
            a3[2] = v3;
            return v3;
          }
          v13 = GetLastError();
          LastError = v13;
          if ( v13 == 5 || v13 - 32 <= 1 )
            BfspPrintFileOwnerProcess(lpFileName);
          BfspLogMessage(4, L"MapViewOfFile(%s) failed! Error code = %#x", lpFileName, LastError);
          CloseHandle(FileMappingW);
        }
        else
        {
          v12 = GetLastError();
          LastError = v12;
          if ( v12 == 5 || v12 - 32 <= 1 )
            BfspPrintFileOwnerProcess(lpFileName);
          BfspLogMessage(4, L"CreateFileMapping(%s) failed! Error code = %#x", lpFileName, LastError);
        }
      }
    }
    else
    {
      v10 = GetLastError();
      LastError = v10;
      if ( v10 == 5 || v10 - 32 <= 1 )
        BfspPrintFileOwnerProcess(lpFileName);
      BfspLogMessage(4, L"Failed to get file size for %s! Error code = %#x", lpFileName, LastError);
    }
    CloseHandle(v8);
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x1800318b0  mov     rax, rsp
0x1800318b3  push    rbx
0x1800318b4  push    rbp
0x1800318b5  push    rsi
0x1800318b6  push    rdi
0x1800318b7  push    r14
0x1800318b9  push    r15
0x1800318bb  sub     rsp, 48h
0x1800318bf  xor     r14d, r14d
0x1800318c2  mov     qword ptr [rax+20h], 0
0x1800318ca  mov     [rax-48h], r14
0x1800318ce  mov     rbx, r8
0x1800318d1  mov     r15, rdx
0x1800318d4  mov     [rax-50h], r14d
0x1800318d8  xor     r9d, r9d; lpSecurityAttributes
0x1800318db  mov     dword ptr [rax-58h], 3
0x1800318e2  lea     r8d, [r14+1]; dwShareMode
0x1800318e6  mov     edx, 80000000h; dwDesiredAccess
0x1800318eb  mov     rdi, rcx
0x1800318ee  call    cs:__imp_CreateFileW
0x1800318f4  mov     rsi, rax
0x1800318f7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800318fb  jnz     short loc_180031957
0x1800318fd  call    cs:__imp_GetLastError
0x180031903  mov     ebx, eax
0x180031905  add     eax, 0FFFFFFFEh
0x180031908  cmp     eax, 1
0x18003190b  jbe     short loc_18003193E
0x18003190d  cmp     ebx, 5
0x180031910  jz      short loc_18003191A
0x180031912  lea     eax, [rbx-20h]
0x180031915  cmp     eax, 1
0x180031918  ja      short loc_180031922
0x18003191a  mov     rcx, rdi; lpFileName
0x18003191d  call    BfspPrintFileOwnerProcess
0x180031922  mov     r9d, ebx
0x180031925  lea     rdx, aFailedToOpenFi; "Failed to open file %s for read! Error "...
0x18003192c  mov     r8, rdi
0x18003192f  mov     ecx, 4
0x180031934  call    BfspLogMessage
0x180031939  jmp     loc_180031A8B
0x18003193e  mov     r8, rdi
0x180031941  lea     rdx, aUnableToOpenFi; "Unable to open file %s for read because"...
0x180031948  mov     ecx, 2
0x18003194d  call    BfspLogMessage
0x180031952  jmp     loc_180031A8B
0x180031957  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x18003195f  mov     rcx, rsi; hFile
0x180031962  call    cs:__imp_GetFileSizeEx
0x180031968  test    eax, eax
0x18003196a  jnz     short loc_1800319A5
0x18003196c  call    cs:__imp_GetLastError
0x180031972  mov     ebx, eax
0x180031974  cmp     eax, 5
0x180031977  jz      short loc_180031981
0x180031979  add     eax, 0FFFFFFE0h
0x18003197c  cmp     eax, 1
0x18003197f  ja      short loc_180031989
0x180031981  mov     rcx, rdi; lpFileName
0x180031984  call    BfspPrintFileOwnerProcess
0x180031989  lea     rdx, aFailedToGetFil; "Failed to get file size for %s! Error c"...
0x180031990  mov     r8, rdi
0x180031993  mov     r9d, ebx
0x180031996  mov     ecx, 4
0x18003199b  call    BfspLogMessage
0x1800319a0  jmp     loc_180031A82
0x1800319a5  cmp     dword ptr [rsp+78h+FileSize+4], r14d
0x1800319ad  jz      short loc_1800319CB
0x1800319af  mov     ebx, 57h ; 'W'
0x1800319b4  lea     rdx, aFileSIsTooLarg; "File %s is too large!"
0x1800319bb  mov     r8, rdi
0x1800319be  lea     ecx, [rbx-53h]
0x1800319c1  call    BfspLogMessage
0x1800319c6  jmp     loc_180031A82
0x1800319cb  mov     eax, dword ptr [rsp+78h+FileSize]
0x1800319d2  xor     r9d, r9d; dwMaximumSizeHigh
0x1800319d5  mov     [rsp+78h+lpName], r14; lpName
0x1800319da  xor     edx, edx; lpFileMappingAttributes
0x1800319dc  mov     rcx, rsi; hFile
0x1800319df  mov     [rsp+78h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x1800319e3  lea     r8d, [r9+2]; flProtect
0x1800319e7  call    cs:__imp_CreateFileMappingW
0x1800319ed  mov     rbp, rax
0x1800319f0  test    rax, rax
0x1800319f3  jnz     short loc_180031A1E
0x1800319f5  call    cs:__imp_GetLastError
0x1800319fb  mov     ebx, eax
0x1800319fd  cmp     eax, 5
0x180031a00  jz      short loc_180031A0A
0x180031a02  add     eax, 0FFFFFFE0h
0x180031a05  cmp     eax, 1
0x180031a08  ja      short loc_180031A12
0x180031a0a  mov     rcx, rdi; lpFileName
0x180031a0d  call    BfspPrintFileOwnerProcess
0x180031a12  lea     rdx, aCreatefilemapp; "CreateFileMapping(%s) failed! Error cod"...
0x180031a19  jmp     loc_180031990
0x180031a1e  mov     eax, dword ptr [rsp+78h+FileSize]
0x180031a25  xor     r9d, r9d; dwFileOffsetLow
0x180031a28  xor     r8d, r8d; dwFileOffsetHigh
0x180031a2b  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x180031a30  mov     rcx, rbp; hFileMappingObject
0x180031a33  lea     edx, [r9+4]; dwDesiredAccess
0x180031a37  call    cs:__imp_MapViewOfFile
0x180031a3d  mov     r14, rax
0x180031a40  test    rax, rax
0x180031a43  jnz     short loc_180031A95
0x180031a45  call    cs:__imp_GetLastError
0x180031a4b  mov     ebx, eax
0x180031a4d  cmp     eax, 5
0x180031a50  jz      short loc_180031A5A
0x180031a52  lea     ecx, [rax-20h]
0x180031a55  cmp     ecx, 1
0x180031a58  ja      short loc_180031A62
0x180031a5a  mov     rcx, rdi; lpFileName
0x180031a5d  call    BfspPrintFileOwnerProcess
0x180031a62  mov     r9d, ebx
0x180031a65  lea     rdx, aMapviewoffileS; "MapViewOfFile(%s) failed! Error code = "...
0x180031a6c  mov     r8, rdi
0x180031a6f  mov     ecx, 4
0x180031a74  call    BfspLogMessage
0x180031a79  mov     rcx, rbp; hObject
0x180031a7c  call    cs:__imp_CloseHandle
0x180031a82  mov     rcx, rsi; hObject
0x180031a85  call    cs:__imp_CloseHandle
0x180031a8b  mov     ecx, ebx; dwErrCode
0x180031a8d  call    cs:__imp_SetLastError
0x180031a93  jmp     short loc_180031AAA
0x180031a95  mov     eax, dword ptr [rsp+78h+FileSize]
0x180031a9c  mov     [r15], eax
0x180031a9f  mov     [rbx], rsi
0x180031aa2  mov     [rbx+8], rbp
0x180031aa6  mov     [rbx+10h], r14
0x180031aaa  mov     rax, r14
0x180031aad  add     rsp, 48h
0x180031ab1  pop     r15
0x180031ab3  pop     r14
0x180031ab5  pop     rdi
0x180031ab6  pop     rsi
0x180031ab7  pop     rbp
0x180031ab8  pop     rbx
0x180031ab9  retn
```
