# PfSvReadFile

- ea: `0x180054a5c`
- end: `0x180054cd4`
- name: `PfSvReadFile`
- size: `632`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *, _DWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180031818`
- `0x180054330`
- `0x180054874`
- `0x180054960`
- `0x18008bdf4`

## callees

- `0x180025f6c`
- `0x180054a5c`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x180054c13`
- `ntdll!NtQueryVolumeInformationFile` at `0x180054c13`
- `ntdll!RtlNtStatusToDosError` at `0x180054c1f`
- `ntdll!RtlNtStatusToDosError` at `0x180054c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054c96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054c96`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180054cac`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180054cac`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180054c4c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180054c4c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180054bab`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180054bab`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180054b9e`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180054b9e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054b58`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054b58`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180054c75`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180054c75`

## string_xrefs

- `0x180054abd`: `// Reading file %wsbuffered: %ws...\n`

## pseudocode

```c
__int64 __fastcall PfSvReadFile(__int64 a1, char a2, _QWORD *a3, _DWORD *a4)
{
  bool v4; // zf
  int v5; // r12d
  const wchar_t *v7; // rdx
  unsigned int v9; // r10d
  const WCHAR *v10; // r11
  int v11; // r8d
  int v12; // ebx
  int v13; // edx
  DWORD dwFlagsAndAttributes; // r9d
  DWORD v15; // r8d
  HANDLE FileW; // rax
  void *v17; // r14
  unsigned int v18; // ebx
  void *v19; // rdi
  DWORD FileSize; // eax
  SIZE_T v21; // rsi
  ULONG LastError; // eax
  int v23; // eax
  int v24; // eax
  SIZE_T v25; // rdx
  void *v26; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-49h] BYREF
  DWORD FileSizeHigh; // [rsp+44h] [rbp-45h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-41h] BYREF
  __m128i FileInformation; // [rsp+58h] [rbp-31h] BYREF
  __m128i v32; // [rsp+68h] [rbp-21h]
  __int64 v33; // [rsp+78h] [rbp-11h]
  __int128 FsInformation; // [rsp+80h] [rbp-9h] BYREF
  __int64 v35; // [rsp+90h] [rbp+7h]

  v33 = 0;
  v35 = 0;
  FileSizeHigh = 0;
  v4 = (a2 & 1) == 0;
  v5 = a2 & 1;
  NumberOfBytesRead = 0;
  v7 = L"un";
  if ( v4 )
    v7 = &Src;
  FileInformation = 0;
  v32 = 0;
  FsInformation = 0;
  IoStatusBlock = 0;
  PFSV_PRINTF("// Reading file %wsbuffered: %ws...\n", v7, a1);
  v11 = (unsigned __int16)(v9 >> 7) | 0x20000000;
  if ( !v5 )
    v11 = (unsigned __int16)(v9 >> 7);
  v12 = v9 & 2;
  v13 = (v9 >> 2) & 1 | 2;
  if ( (v9 & 8) == 0 )
    v13 = (v9 >> 2) & 1;
  dwFlagsAndAttributes = v11 | 0x200000;
  if ( (v9 & 0x20) == 0 )
    dwFlagsAndAttributes = v11;
  v15 = v13 | 4;
  if ( (v9 & 0x10) == 0 )
    v15 = v13;
  FileW = CreateFileW(v10, v12 != 0 ? 0x80000000 : -2147483392, v15, 0, 3u, dwFlagsAndAttributes, 0);
  v17 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  v19 = 0;
  if ( !v12 )
  {
    v33 = 0;
    FileInformation = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v32 = FileInformation;
    SetFileInformationByHandle(FileW, FileBasicInfo, &FileInformation, 0x28u);
  }
  FileSize = GetFileSize(v17, &FileSizeHigh);
  v21 = FileSize;
  if ( FileSize == -1 && GetLastError() )
    goto LABEL_17;
  if ( FileSizeHigh )
  {
    v18 = 24;
  }
  else if ( *a4 && (unsigned int)v21 > *a4 )
  {
    v18 = 223;
  }
  else
  {
    NumberOfBytesRead = v21;
    if ( v5 )
    {
      v23 = NtQueryVolumeInformationFile(v17, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
      if ( v23 < 0 )
      {
        LastError = RtlNtStatusToDosError(v23);
        goto LABEL_18;
      }
      v24 = ~(HIDWORD(v35) - 1);
      v25 = v24 & (HIDWORD(v35) + NumberOfBytesRead - 1);
      NumberOfBytesRead = v24 & (HIDWORD(v35) + NumberOfBytesRead - 1);
    }
    else
    {
      v25 = v21;
    }
    v26 = VirtualAlloc(0, v25, 0x1000u, 4u);
    v19 = v26;
    if ( !v26 || !ReadFile(v17, v26, NumberOfBytesRead, &NumberOfBytesRead, 0) && NumberOfBytesRead < (unsigned int)v21 )
    {
LABEL_17:
      LastError = GetLastError();
LABEL_18:
      v18 = LastError;
      goto LABEL_33;
    }
    *a3 = v19;
    v19 = 0;
    v18 = 0;
    *a4 = v21;
  }
LABEL_33:
  CloseHandle(v17);
  if ( v19 )
    VirtualFree(v19, 0, 0x8000u);
  return v18;
}

```

## disassembly

```asm
0x180054a5c  push    rbp
0x180054a5e  push    rbx
0x180054a5f  push    rsi
0x180054a60  push    rdi
0x180054a61  push    r12
0x180054a63  push    r13
0x180054a65  push    r14
0x180054a67  push    r15
0x180054a69  lea     rbp, [rsp-1Fh]
0x180054a6e  sub     rsp, 0A8h
0x180054a75  mov     rax, cs:__security_cookie
0x180054a7c  xor     rax, rsp
0x180054a7f  mov     [rbp+57h+var_48], rax
0x180054a83  xor     eax, eax
0x180054a85  xorps   xmm0, xmm0
0x180054a88  xor     esi, esi
0x180054a8a  mov     [rbp+57h+var_68], rax
0x180054a8e  mov     r12d, edx
0x180054a91  mov     [rbp+57h+var_50], rax
0x180054a95  mov     r10d, edx
0x180054a98  mov     [rbp+57h+FileSizeHigh], esi
0x180054a9b  and     r12d, 1
0x180054a9f  mov     [rbp+57h+NumberOfBytesRead], esi
0x180054aa2  lea     rax, Src
0x180054aa9  mov     r13, r8
0x180054aac  mov     r8, rcx
0x180054aaf  lea     rdx, aUn; "un"
0x180054ab6  mov     r11, rcx
0x180054ab9  cmovz   rdx, rax
0x180054abd  lea     rcx, aReadingFileWsb; "// Reading file %wsbuffered: %ws...\n"
0x180054ac4  mov     r15, r9
0x180054ac7  movups  [rbp+57h+FileInformation], xmm0
0x180054acb  movups  [rbp+57h+var_78], xmm0
0x180054acf  movups  [rbp+57h+FsInformation], xmm0
0x180054ad3  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180054ad7  call    PFSV_PRINTF
0x180054adc  mov     eax, r10d
0x180054adf  mov     [rsp+0E0h+hTemplateFile], rsi; hTemplateFile
0x180054ae4  shr     eax, 7
0x180054ae7  mov     ebx, r10d
0x180054aea  movzx   ecx, ax
0x180054aed  mov     r8d, ecx
0x180054af0  bts     r8d, 1Dh
0x180054af5  test    r12d, r12d
0x180054af8  cmovz   r8d, ecx
0x180054afc  and     ebx, 2
0x180054aff  mov     r9d, r8d
0x180054b02  mov     ecx, r10d
0x180054b05  shr     ecx, 2
0x180054b08  mov     eax, ebx
0x180054b0a  and     ecx, 1
0x180054b0d  mov     edx, ecx
0x180054b0f  or      edx, 2
0x180054b12  test    r10b, 8
0x180054b16  cmovz   edx, ecx
0x180054b19  bts     r9d, 15h
0x180054b1e  test    r10b, 20h
0x180054b22  mov     rcx, r11; lpFileName
0x180054b25  cmovz   r9d, r8d
0x180054b29  mov     r8d, edx
0x180054b2c  or      r8d, 4
0x180054b30  mov     [rsp+0E0h+dwFlagsAndAttributes], r9d; dwFlagsAndAttributes
0x180054b35  test    r10b, 10h
0x180054b39  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180054b41  cmovz   r8d, edx; dwShareMode
0x180054b45  neg     eax
0x180054b47  sbb     edx, edx
0x180054b49  xor     r9d, r9d; lpSecurityAttributes
0x180054b4c  and     edx, 0FFFFFF00h
0x180054b52  add     edx, 80000100h; dwDesiredAccess
0x180054b58  call    cs:__imp_CreateFileW
0x180054b5e  mov     r14, rax
0x180054b61  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054b65  jnz     short loc_180054B74
0x180054b67  call    cs:__imp_GetLastError
0x180054b6d  mov     ebx, eax
0x180054b6f  jmp     loc_180054CB2
0x180054b74  mov     rdi, rsi
0x180054b77  test    ebx, ebx
0x180054b79  jnz     short loc_180054BA4
0x180054b7b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180054b83  lea     r9d, [rbx+28h]; dwBufferSize
0x180054b87  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180054b8b  mov     [rbp+57h+var_68], rsi
0x180054b8f  xor     edx, edx; FileInformationClass
0x180054b91  mov     rcx, r14; hFile
0x180054b94  movdqu  [rbp+57h+FileInformation], xmm0
0x180054b99  movdqu  [rbp+57h+var_78], xmm0
0x180054b9e  call    cs:__imp_SetFileInformationByHandle
0x180054ba4  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x180054ba8  mov     rcx, r14; hFile
0x180054bab  call    cs:__imp_GetFileSize
0x180054bb1  mov     esi, eax
0x180054bb3  cmp     eax, 0FFFFFFFFh
0x180054bb6  jnz     short loc_180054BCF
0x180054bb8  call    cs:__imp_GetLastError
0x180054bbe  test    eax, eax
0x180054bc0  jz      short loc_180054BCF
0x180054bc2  call    cs:__imp_GetLastError
0x180054bc8  mov     ebx, eax
0x180054bca  jmp     loc_180054C93
0x180054bcf  cmp     [rbp+57h+FileSizeHigh], edi
0x180054bd2  jz      short loc_180054BDE
0x180054bd4  mov     ebx, 18h
0x180054bd9  jmp     loc_180054C93
0x180054bde  cmp     [r15], edi
0x180054be1  jz      short loc_180054BF2
0x180054be3  cmp     esi, [r15]
0x180054be6  jbe     short loc_180054BF2
0x180054be8  mov     ebx, 0DFh
0x180054bed  jmp     loc_180054C93
0x180054bf2  mov     [rbp+57h+NumberOfBytesRead], esi
0x180054bf5  test    r12d, r12d
0x180054bf8  jz      short loc_180054C3D
0x180054bfa  mov     r9d, 18h; Length
0x180054c00  mov     [rsp+0E0h+dwCreationDisposition], 3; FsInformationClass
0x180054c08  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x180054c0c  mov     rcx, r14; FileHandle
0x180054c0f  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180054c13  call    cs:__imp_NtQueryVolumeInformationFile
0x180054c19  test    eax, eax
0x180054c1b  jns     short loc_180054C27
0x180054c1d  mov     ecx, eax; Status
0x180054c1f  call    cs:__imp_RtlNtStatusToDosError
0x180054c25  jmp     short loc_180054BC8
0x180054c27  mov     ecx, dword ptr [rbp+57h+var_50+4]
0x180054c2a  mov     edx, [rbp+57h+NumberOfBytesRead]
0x180054c2d  dec     edx
0x180054c2f  add     edx, ecx
0x180054c31  lea     eax, [rcx-1]
0x180054c34  not     eax
0x180054c36  and     edx, eax
0x180054c38  mov     [rbp+57h+NumberOfBytesRead], edx
0x180054c3b  jmp     short loc_180054C40
0x180054c3d  mov     rdx, rsi; dwSize
0x180054c40  xor     ecx, ecx; lpAddress
0x180054c42  mov     r8d, 1000h; flAllocationType
0x180054c48  lea     r9d, [rcx+4]; flProtect
0x180054c4c  call    cs:__imp_VirtualAlloc
0x180054c52  mov     rdi, rax
0x180054c55  test    rax, rax
0x180054c58  jz      loc_180054BC2
0x180054c5e  mov     r8d, [rbp+57h+NumberOfBytesRead]; nNumberOfBytesToRead
0x180054c62  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180054c66  mov     rdx, rax; lpBuffer
0x180054c69  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x180054c72  mov     rcx, r14; hFile
0x180054c75  call    cs:__imp_ReadFile
0x180054c7b  test    eax, eax
0x180054c7d  jnz     short loc_180054C88
0x180054c7f  cmp     [rbp+57h+NumberOfBytesRead], esi
0x180054c82  jb      loc_180054BC2
0x180054c88  mov     [r13+0], rdi
0x180054c8c  xor     edi, edi
0x180054c8e  xor     ebx, ebx
0x180054c90  mov     [r15], esi
0x180054c93  mov     rcx, r14; hObject
0x180054c96  call    cs:__imp_CloseHandle
0x180054c9c  test    rdi, rdi
0x180054c9f  jz      short loc_180054CB2
0x180054ca1  xor     edx, edx; dwSize
0x180054ca3  mov     r8d, 8000h; dwFreeType
0x180054ca9  mov     rcx, rdi; lpAddress
0x180054cac  call    cs:__imp_VirtualFree
0x180054cb2  mov     eax, ebx
0x180054cb4  mov     rcx, [rbp+57h+var_48]
0x180054cb8  xor     rcx, rsp; StackCookie
0x180054cbb  call    __security_check_cookie
0x180054cc0  add     rsp, 0A8h
0x180054cc7  pop     r15
0x180054cc9  pop     r14
0x180054ccb  pop     r13
0x180054ccd  pop     r12
0x180054ccf  pop     rdi
0x180054cd0  pop     rsi
0x180054cd1  pop     rbx
0x180054cd2  pop     rbp
0x180054cd3  retn
```
