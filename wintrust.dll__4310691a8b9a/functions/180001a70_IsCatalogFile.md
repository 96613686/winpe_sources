# IsCatalogFile

- ea: `0x180001a70`
- end: `0x180001c70`
- name: `IsCatalogFile`
- size: `512`
- prototype: `BOOL __stdcall(HANDLE hFile, WCHAR *pwszFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001510`

## callees

- `0x180001a70`
- `0x18004de76`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180001b2e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180001b2e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001bcf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001bcf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001c47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001b1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001c68`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180001c5d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180001c5d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180001b0d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180001b0d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180001ae5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180001ae5`
- `CRYPT32!CertCreateContext` at `0x180001b6c`
- `CRYPT32!CertCreateContext` at `0x180001b6c`
- `CRYPT32!CertFreeCTLContext` at `0x180001c52`
- `CRYPT32!CertFreeCTLContext` at `0x180001c52`

## pseudocode

```c
BOOL __stdcall IsCatalogFile(HANDLE hFile, WCHAR *pwszFileName)
{
  HANDLE FileW; // rsi
  const CTL_CONTEXT *v3; // r15
  const BYTE *v4; // r14
  int v5; // r12d
  BOOL v6; // edi
  char *FileMappingA; // r13
  DWORD FileSize; // r9d
  const CTL_CONTEXT *Context; // rax
  PCTL_INFO pCtlInfo; // rcx

  FileW = hFile;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = 1;
  }
  else
  {
    if ( !pwszFileName )
    {
LABEL_28:
      SetLastError(0x57u);
LABEL_20:
      v6 = 0;
      goto LABEL_21;
    }
    FileW = CreateFileW(pwszFileName, 0x80000000, 5u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_20;
    v6 = 1;
    v5 = 1;
  }
  FileMappingA = (char *)CreateFileMappingA(FileW, 0, 2u, 0, 0, 0);
  if ( (unsigned __int64)(FileMappingA - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_20;
  v4 = (const BYTE *)MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
  CloseHandle(FileMappingA);
  if ( !v4 )
    goto LABEL_20;
  FileSize = GetFileSize(FileW, 0);
  if ( FileSize - 1 > 0xFFFFFFFD )
    goto LABEL_28;
  if ( *v4 != 48 )
    goto LABEL_20;
  Context = (const CTL_CONTEXT *)CertCreateContext(3u, 0x10001u, v4, FileSize, 0xDu, 0);
  v3 = Context;
  if ( !Context )
    goto LABEL_20;
  pCtlInfo = Context->pCtlInfo;
  if ( !pCtlInfo->SubjectUsage.cUsageIdentifier
    || strcmp_0(*(const char **)pCtlInfo->SubjectUsage.rgpszUsageIdentifier, "1.3.6.1.4.1.311.12.1.1") )
  {
    goto LABEL_20;
  }
LABEL_21:
  if ( v3 )
    CertFreeCTLContext(v3);
  if ( v4 )
    UnmapViewOfFile(v4);
  if ( v5 )
    CloseHandle(FileW);
  return v6;
}

```

## disassembly

```asm
0x180001a70  mov     rax, rsp
0x180001a73  mov     [rax+8], rcx
0x180001a77  push    rsi
0x180001a78  push    rdi
0x180001a79  push    r12
0x180001a7b  push    r13
0x180001a7d  push    r14
0x180001a7f  push    r15
0x180001a81  sub     rsp, 68h
0x180001a85  mov     r10, rdx
0x180001a88  mov     rsi, rcx
0x180001a8b  mov     dword ptr [rax-58h], 0
0x180001a92  mov     qword ptr [rax-50h], 0
0x180001a9a  mov     qword ptr [rax-48h], 0
0x180001aa2  xor     r15d, r15d
0x180001aa5  mov     [rax-48h], r15
0x180001aa9  xor     r14d, r14d
0x180001aac  mov     [rax-50h], r14
0x180001ab0  xor     r12d, r12d
0x180001ab3  mov     [rax-58h], r12d
0x180001ab7  mov     [rax-54h], r12d
0x180001abb  lea     rax, [rcx+1]
0x180001abf  test    rax, 0FFFFFFFFFFFFFFFEh
0x180001ac5  jz      loc_180001BA6
0x180001acb  lea     edi, [r15+1]
0x180001acf  mov     [rsp+98h+lpName], r14; lpName
0x180001ad4  mov     [rsp+98h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x180001ad9  xor     r9d, r9d; dwMaximumSizeHigh
0x180001adc  xor     edx, edx; lpFileMappingAttributes
0x180001ade  lea     r8d, [r9+2]; flProtect
0x180001ae2  mov     rcx, rsi; hFile
0x180001ae5  call    cs:__imp_CreateFileMappingA
0x180001aeb  mov     r13, rax
0x180001aee  dec     rax
0x180001af1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001af5  ja      loc_180001BFF
0x180001afb  mov     qword ptr [rsp+98h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x180001b00  xor     r9d, r9d; dwFileOffsetLow
0x180001b03  xor     r8d, r8d; dwFileOffsetHigh
0x180001b06  lea     edx, [r9+4]; dwDesiredAccess
0x180001b0a  mov     rcx, r13; hFileMappingObject
0x180001b0d  call    cs:__imp_MapViewOfFile
0x180001b13  mov     r14, rax
0x180001b16  mov     [rsp+98h+var_50], rax
0x180001b1b  mov     rcx, r13; hObject
0x180001b1e  call    cs:__imp_CloseHandle
0x180001b24  test    r14, r14
0x180001b27  jz      short loc_180001B4D
0x180001b29  xor     edx, edx; lpFileSizeHigh
0x180001b2b  mov     rcx, rsi; hFile
0x180001b2e  call    cs:__imp_GetFileSize
0x180001b34  mov     r9d, eax; cbEncoded
0x180001b37  dec     eax
0x180001b39  cmp     eax, 0FFFFFFFDh
0x180001b3c  ja      loc_180001BFD
0x180001b42  cmp     byte ptr [r14], 30h ; '0'
0x180001b46  jz      short loc_180001B52
0x180001b48  jmp     loc_180001C20
0x180001b4d  jmp     loc_180001C20
0x180001b52  mov     [rsp+98h+lpName], r15; pCreatePara
0x180001b57  mov     [rsp+98h+dwMaximumSizeLow], 0Dh; dwFlags
0x180001b5f  mov     r8, r14; pbEncoded
0x180001b62  mov     edx, 10001h; dwEncodingType
0x180001b67  mov     ecx, 3; dwContextType
0x180001b6c  call    cs:__imp_CertCreateContext
0x180001b72  mov     r15, rax
0x180001b75  mov     [rsp+98h+var_48], rax
0x180001b7a  test    rax, rax
0x180001b7d  jz      short loc_180001BFB
0x180001b7f  mov     rcx, [rax+18h]
0x180001b83  cmp     dword ptr [rcx+8], 0
0x180001b87  jz      short loc_180001BFB
0x180001b89  mov     rcx, [rcx+10h]
0x180001b8d  lea     rdx, Str2; "1.3.6.1.4.1.311.12.1.1"
0x180001b94  mov     rcx, [rcx]; Str1
0x180001b97  call    strcmp_0
0x180001b9c  test    eax, eax
0x180001b9e  jnz     short loc_180001BFB
0x180001ba0  mov     [rsp+98h+var_54], edi
0x180001ba4  jmp     short loc_180001C22
0x180001ba6  test    r10, r10
0x180001ba9  jz      short loc_180001BF7
0x180001bab  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x180001bb0  mov     dword ptr [rsp+98h+lpName], 80h; dwFlagsAndAttributes
0x180001bb8  mov     [rsp+98h+dwMaximumSizeLow], 3; dwCreationDisposition
0x180001bc0  xor     r9d, r9d; lpSecurityAttributes
0x180001bc3  mov     edx, 80000000h; dwDesiredAccess
0x180001bc8  lea     r8d, [r9+5]; dwShareMode
0x180001bcc  mov     rcx, r10; lpFileName
0x180001bcf  call    cs:__imp_CreateFileW
0x180001bd5  mov     rsi, rax
0x180001bd8  mov     [rsp+98h+arg_0], rax
0x180001be0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001be4  jz      short loc_180001BF9
0x180001be6  mov     edi, 1
0x180001beb  mov     r12d, edi
0x180001bee  mov     [rsp+98h+var_58], edi
0x180001bf2  jmp     loc_180001ACF
0x180001bf7  jmp     short loc_180001C42
0x180001bf9  jmp     short loc_180001C20
0x180001bfb  jmp     short loc_180001C20
0x180001bfd  jmp     short loc_180001C42
0x180001bff  jmp     short loc_180001C20
0x180001c01  mov     ecx, eax; dwErrCode
0x180001c03  call    cs:__imp_SetLastError
0x180001c09  mov     rsi, [rsp+98h+arg_0]
0x180001c11  mov     r12d, [rsp+98h+var_58]
0x180001c16  mov     r14, [rsp+98h+var_50]
0x180001c1b  mov     r15, [rsp+98h+var_48]
0x180001c20  xor     edi, edi
0x180001c22  test    r15, r15
0x180001c25  jnz     short loc_180001C4F
0x180001c27  test    r14, r14
0x180001c2a  jnz     short loc_180001C5A
0x180001c2c  test    r12d, r12d
0x180001c2f  jnz     short loc_180001C65
0x180001c31  mov     eax, edi
0x180001c33  add     rsp, 68h
0x180001c37  pop     r15
0x180001c39  pop     r14
0x180001c3b  pop     r13
0x180001c3d  pop     r12
0x180001c3f  pop     rdi
0x180001c40  pop     rsi
0x180001c41  retn
0x180001c42  mov     ecx, 57h ; 'W'; dwErrCode
0x180001c47  call    cs:__imp_SetLastError
0x180001c4d  jmp     short loc_180001C20
0x180001c4f  mov     rcx, r15; pCtlContext
0x180001c52  call    cs:__imp_CertFreeCTLContext
0x180001c58  jmp     short loc_180001C27
0x180001c5a  mov     rcx, r14; lpBaseAddress
0x180001c5d  call    cs:__imp_UnmapViewOfFile
0x180001c63  jmp     short loc_180001C2C
0x180001c65  mov     rcx, rsi; hObject
0x180001c68  call    cs:__imp_CloseHandle
0x180001c6e  jmp     short loc_180001C31
```
