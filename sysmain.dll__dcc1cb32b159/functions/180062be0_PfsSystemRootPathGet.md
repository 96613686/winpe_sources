# PfsSystemRootPathGet

- ea: `0x180062be0`
- end: `0x180062d4d`
- name: `PfsSystemRootPathGet`
- size: `365`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180056b04`

## callees

- `0x18003bafc`
- `0x180062be0`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180062cb0`
- `ntdll!NtCreateFile` at `0x180062cb0`
- `ntdll!RtlInitUnicodeString` at `0x180062c37`
- `ntdll!RtlInitUnicodeString` at `0x180062c37`
- `ntdll!RtlNtStatusToDosError` at `0x180062cbc`
- `ntdll!RtlNtStatusToDosError` at `0x180062cbc`
- `ntdll!NtClose` at `0x180062d25`
- `ntdll!NtClose` at `0x180062d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d13`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180062cd6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180062cd6`

## pseudocode

```c
__int64 __fastcall PfsSystemRootPathGet(STRSAFE_LPWSTR pszDest)
{
  int v2; // eax
  ULONG LastError; // eax
  DWORD FinalPathNameByHandleW; // eax
  unsigned int v5; // ebx
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR szFilePath; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszSrc[260]; // [rsp+C8h] [rbp-38h] BYREF

  FileHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  IoStatusBlock = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  RtlInitUnicodeString(&DestinationString, L"\\SystemRoot");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  v2 = NtCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0x204021u, 0, 0);
  if ( v2 < 0 )
  {
    LastError = RtlNtStatusToDosError(v2);
LABEL_8:
    v5 = LastError;
    goto LABEL_9;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileHandle, &szFilePath, 0x104u, 0);
  if ( FinalPathNameByHandleW - 1 > 0x103 )
  {
    LastError = GetLastError();
    goto LABEL_8;
  }
  if ( 2 * (unsigned __int64)(FinalPathNameByHandleW - 4) + 2 <= 0x208 )
  {
    StringCbCopyW(pszDest, 0x208u, pszSrc);
    v5 = 0;
  }
  else
  {
    v5 = 122;
  }
LABEL_9:
  if ( FileHandle )
    NtClose(FileHandle);
  return v5;
}

```

## disassembly

```asm
0x180062be0  mov     [rsp-8+arg_8], rbx
0x180062be5  push    rbp
0x180062be6  lea     rbp, [rsp-1E0h]
0x180062bee  sub     rsp, 2E0h
0x180062bf5  mov     rax, cs:__security_cookie
0x180062bfc  xor     rax, rsp
0x180062bff  mov     [rbp+1E0h+var_10], rax
0x180062c06  xorps   xmm0, xmm0
0x180062c09  lea     rdx, aSystemroot; "\\SystemRoot"
0x180062c10  mov     rbx, rcx
0x180062c13  xorps   xmm1, xmm1
0x180062c16  xor     eax, eax
0x180062c18  lea     rcx, [rbp+1E0h+DestinationString]; DestinationString
0x180062c1c  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x180062c21  mov     [rsp+2E0h+FileHandle], rax
0x180062c26  movups  xmmword ptr [rbp+1E0h+ObjectAttributes+1Ch], xmm0
0x180062c2a  movups  xmmword ptr [rbp+1E0h+IoStatusBlock], xmm0
0x180062c2e  movups  xmmword ptr [rbp+1E0h+DestinationString.Length], xmm1
0x180062c32  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x180062c37  call    cs:__imp_RtlInitUnicodeString
0x180062c3d  mov     [rsp+2E0h+EaLength], 0; EaLength
0x180062c45  lea     rax, [rbp+1E0h+DestinationString]
0x180062c49  mov     [rsp+2E0h+EaBuffer], 0; EaBuffer
0x180062c52  lea     r9, [rbp+1E0h+IoStatusBlock]; IoStatusBlock
0x180062c56  mov     [rsp+2E0h+CreateOptions], 204021h; CreateOptions
0x180062c5e  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180062c63  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180062c68  lea     rcx, [rsp+2E0h+FileHandle]; FileHandle
0x180062c6d  mov     eax, 3
0x180062c72  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180062c7a  mov     [rsp+2E0h+CreateDisposition], eax; CreateDisposition
0x180062c7e  xorps   xmm0, xmm0
0x180062c81  mov     [rsp+2E0h+ShareAccess], eax; ShareAccess
0x180062c85  mov     edx, 100001h; DesiredAccess
0x180062c8a  mov     [rsp+2E0h+FileAttributes], 80h; FileAttributes
0x180062c92  mov     [rsp+2E0h+AllocationSize], 0; AllocationSize
0x180062c9b  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], 0
0x180062ca4  mov     [rbp+1E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180062cab  movdqu  xmmword ptr [rbp+1E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180062cb0  call    cs:__imp_NtCreateFile
0x180062cb6  test    eax, eax
0x180062cb8  jns     short loc_180062CC4
0x180062cba  mov     ecx, eax; Status
0x180062cbc  call    cs:__imp_RtlNtStatusToDosError
0x180062cc2  jmp     short loc_180062D19
0x180062cc4  mov     rcx, [rsp+2E0h+FileHandle]; hFile
0x180062cc9  lea     rdx, [rbp+1E0h+szFilePath]; lpszFilePath
0x180062ccd  xor     r9d, r9d; dwFlags
0x180062cd0  mov     r8d, 104h; cchFilePath
0x180062cd6  call    cs:__imp_GetFinalPathNameByHandleW
0x180062cdc  lea     ecx, [rax-1]
0x180062cdf  cmp     ecx, 103h
0x180062ce5  ja      short loc_180062D13
0x180062ce7  add     eax, 0FFFFFFFCh
0x180062cea  mov     edx, 208h; cbDest
0x180062cef  lea     rcx, ds:2[rax*2]
0x180062cf7  cmp     rcx, rdx
0x180062cfa  jbe     short loc_180062D03
0x180062cfc  mov     ebx, 7Ah ; 'z'
0x180062d01  jmp     short loc_180062D1B
0x180062d03  lea     r8, [rbp+1E0h+pszSrc]; pszSrc
0x180062d07  mov     rcx, rbx; pszDest
0x180062d0a  call    StringCbCopyW
0x180062d0f  xor     ebx, ebx
0x180062d11  jmp     short loc_180062D1B
0x180062d13  call    cs:__imp_GetLastError
0x180062d19  mov     ebx, eax
0x180062d1b  mov     rcx, [rsp+2E0h+FileHandle]; Handle
0x180062d20  test    rcx, rcx
0x180062d23  jz      short loc_180062D2B
0x180062d25  call    cs:__imp_NtClose
0x180062d2b  mov     eax, ebx
0x180062d2d  mov     rcx, [rbp+1E0h+var_10]
0x180062d34  xor     rcx, rsp; StackCookie
0x180062d37  call    __security_check_cookie
0x180062d3c  mov     rbx, [rsp+2E0h+arg_8]
0x180062d44  add     rsp, 2E0h
0x180062d4b  pop     rbp
0x180062d4c  retn
```
