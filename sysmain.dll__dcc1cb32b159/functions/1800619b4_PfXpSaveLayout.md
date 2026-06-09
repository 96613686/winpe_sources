# PfXpSaveLayout

- ea: `0x1800619b4`
- end: `0x180061c27`
- name: `PfXpSaveLayout`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180018ec0`

## callees

- `0x1800231b0`
- `0x1800619b4`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!towupper` at `0x180061a7e`
- `msvcrt!towupper` at `0x180061a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061a5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061bfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061bfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180061a54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180061a54`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180061bbc`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180061bbc`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180061bd7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180061bd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061a2c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061a2c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061aac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061b56`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061b82`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061aac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061b56`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061b82`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180061ba1`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180061ba1`

## pseudocode

```c
__int64 __fastcall PfXpSaveLayout(const WCHAR *a1, __int64 a2, struct _FILETIME *a3, _DWORD *a4)
{
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  UINT SystemDirectoryW; // eax
  wint_t v8; // ax
  WCHAR v9; // r12
  wint_t v10; // r13
  __int64 v11; // rcx
  unsigned __int64 v12; // r14
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  BOOL v18; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-A8h] BYREF
  LPFILETIME lpLastWriteTime; // [rsp+60h] [rbp-A0h]
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  lpLastWriteTime = a3;
  v21 = a2;
  NumberOfBytesWritten = 0;
  v22 = 0;
  FileSize.QuadPart = 0;
  FileW = CreateFileW(a1, 0xC0000000, 0, 0, 2u, 0, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( SystemDirectoryW )
    {
      if ( SystemDirectoryW >= 0x104 )
      {
        LastError = 122;
        goto LABEL_28;
      }
      v8 = towupper(Buffer[0]);
      v9 = Buffer[1];
      v10 = v8;
      if ( WriteFile(FileW, L"[OptimalLayoutFile]\r\nVersion=1\r\n", 0x40u, &NumberOfBytesWritten, 0) )
      {
        v11 = v21;
        v12 = 0;
        v13 = 0;
        v14 = v21 + 16;
        while ( 1 )
        {
          v15 = v11;
          if ( v13 )
            v15 = v13;
          v13 = 0;
          v16 = *(_QWORD *)(v15 + 16);
          if ( v16 != v14 )
            v13 = v16 - 16;
          if ( !v13 )
            break;
          v11 = v21;
          if ( *(_WORD *)(v13 + 44) == v10 && *(_WORD *)(v13 + 46) == v9 )
          {
            v17 = PfsGetFileSize(v13 + 44, &v22);
            v11 = v21;
            v14 = v21 + 16;
            if ( !v17 )
            {
              v14 = v21 + 16;
              if ( v22 <= 0x4000000 )
              {
                v12 += v22;
                if ( v12 > 0x100000000LL )
                  break;
                if ( !WriteFile(FileW, (LPCVOID)(v13 + 44), 2 * *(_DWORD *)(v13 + 40), &NumberOfBytesWritten, 0) )
                  goto LABEL_4;
                v18 = WriteFile(FileW, L"\r\n", 4u, &NumberOfBytesWritten, 0);
                v11 = v21;
                v14 = v21 + 16;
                if ( !v18 )
                  goto LABEL_4;
              }
            }
          }
        }
        if ( FlushFileBuffers(FileW) && GetFileTime(FileW, 0, 0, lpLastWriteTime) )
        {
          if ( !a4 )
          {
LABEL_27:
            LastError = 0;
            goto LABEL_28;
          }
          if ( GetFileSizeEx(FileW, &FileSize) )
          {
            *a4 = FileSize.QuadPart / 1024;
            goto LABEL_27;
          }
        }
      }
    }
LABEL_4:
    LastError = GetLastError();
LABEL_28:
    CloseHandle(FileW);
    return LastError;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x1800619b4  push    rbp
0x1800619b6  push    rbx
0x1800619b7  push    rsi
0x1800619b8  push    rdi
0x1800619b9  push    r12
0x1800619bb  push    r13
0x1800619bd  push    r14
0x1800619bf  push    r15
0x1800619c1  lea     rbp, [rsp-198h]
0x1800619c9  sub     rsp, 298h
0x1800619d0  mov     rax, cs:__security_cookie
0x1800619d7  xor     rax, rsp
0x1800619da  mov     [rbp+1D0h+var_50], rax
0x1800619e1  mov     r15, r9
0x1800619e4  mov     [rsp+2D0h+lpLastWriteTime], r8
0x1800619e9  mov     [rsp+2D0h+var_288], rdx
0x1800619ee  xor     r9d, r9d; lpSecurityAttributes
0x1800619f1  mov     [rsp+2D0h+hTemplateFile], 0; hTemplateFile
0x1800619fa  xor     r8d, r8d; dwShareMode
0x1800619fd  mov     [rsp+2D0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180061a05  mov     edx, 0C0000000h; dwDesiredAccess
0x180061a0a  mov     [rsp+2D0h+dwCreationDisposition], 2; dwCreationDisposition
0x180061a12  mov     [rsp+2D0h+NumberOfBytesWritten], 0
0x180061a1a  mov     [rsp+2D0h+var_280], 0
0x180061a23  mov     qword ptr [rsp+2D0h+FileSize], 0
0x180061a2c  call    cs:__imp_CreateFileW
0x180061a32  mov     rdi, rax
0x180061a35  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180061a39  jnz     short loc_180061A48
0x180061a3b  call    cs:__imp_GetLastError
0x180061a41  mov     ebx, eax
0x180061a43  jmp     loc_180061C02
0x180061a48  mov     ebx, 104h
0x180061a4d  lea     rcx, [rsp+2D0h+Buffer]; lpBuffer
0x180061a52  mov     edx, ebx; uSize
0x180061a54  call    cs:__imp_GetSystemDirectoryW
0x180061a5a  test    eax, eax
0x180061a5c  jnz     short loc_180061A6B
0x180061a5e  call    cs:__imp_GetLastError
0x180061a64  mov     ebx, eax
0x180061a66  jmp     loc_180061BF9
0x180061a6b  cmp     eax, ebx
0x180061a6d  jb      short loc_180061A79
0x180061a6f  mov     ebx, 7Ah ; 'z'
0x180061a74  jmp     loc_180061BF9
0x180061a79  movzx   ecx, [rsp+2D0h+Buffer]; C
0x180061a7e  call    cs:__imp_towupper
0x180061a84  movzx   r12d, [rsp+2D0h+var_25E]
0x180061a8a  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180061a8f  mov     r8d, 40h ; '@'; nNumberOfBytesToWrite
0x180061a95  mov     qword ptr [rsp+2D0h+dwCreationDisposition], 0; lpOverlapped
0x180061a9e  lea     rdx, aOptimallayoutf_0; "[OptimalLayoutFile]\r\nVersion=1\r\n"
0x180061aa5  mov     rcx, rdi; hFile
0x180061aa8  movzx   r13d, ax
0x180061aac  call    cs:__imp_WriteFile
0x180061ab2  test    eax, eax
0x180061ab4  jz      short loc_180061A5E
0x180061ab6  mov     rcx, [rsp+2D0h+var_288]
0x180061abb  xor     r14d, r14d
0x180061abe  xor     ebx, ebx
0x180061ac0  lea     rdx, [rcx+10h]
0x180061ac4  test    rbx, rbx
0x180061ac7  mov     rax, rcx
0x180061aca  cmovnz  rax, rbx
0x180061ace  xor     ebx, ebx
0x180061ad0  mov     rcx, [rax+10h]
0x180061ad4  cmp     rcx, rdx
0x180061ad7  lea     rax, [rcx-10h]
0x180061adb  cmovnz  rbx, rax
0x180061adf  test    rbx, rbx
0x180061ae2  jz      loc_180061B9E
0x180061ae8  mov     rcx, [rsp+2D0h+var_288]
0x180061aed  lea     rsi, [rbx+2Ch]
0x180061af1  cmp     [rsi], r13w
0x180061af5  jnz     short loc_180061AC4
0x180061af7  cmp     [rbx+2Eh], r12w
0x180061afc  jnz     short loc_180061AC4
0x180061afe  lea     rdx, [rsp+2D0h+var_280]
0x180061b03  mov     rcx, rsi
0x180061b06  call    PfsGetFileSize
0x180061b0b  mov     rcx, [rsp+2D0h+var_288]
0x180061b10  lea     rdx, [rcx+10h]
0x180061b14  test    eax, eax
0x180061b16  jnz     short loc_180061AC4
0x180061b18  mov     rax, [rsp+2D0h+var_280]
0x180061b1d  lea     rdx, [rcx+10h]
0x180061b21  cmp     rax, 4000000h
0x180061b27  ja      short loc_180061AC4
0x180061b29  add     r14, rax
0x180061b2c  mov     rax, 100000000h
0x180061b36  cmp     r14, rax
0x180061b39  ja      short loc_180061B9E
0x180061b3b  mov     r8d, [rbx+28h]
0x180061b3f  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180061b44  add     r8d, r8d; nNumberOfBytesToWrite
0x180061b47  mov     qword ptr [rsp+2D0h+dwCreationDisposition], 0; lpOverlapped
0x180061b50  mov     rdx, rsi; lpBuffer
0x180061b53  mov     rcx, rdi; hFile
0x180061b56  call    cs:__imp_WriteFile
0x180061b5c  test    eax, eax
0x180061b5e  jz      loc_180061A5E
0x180061b64  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180061b69  mov     qword ptr [rsp+2D0h+dwCreationDisposition], 0; lpOverlapped
0x180061b72  mov     r8d, 4; nNumberOfBytesToWrite
0x180061b78  lea     rdx, asc_1800C29D0; "\r\n"
0x180061b7f  mov     rcx, rdi; hFile
0x180061b82  call    cs:__imp_WriteFile
0x180061b88  mov     rcx, [rsp+2D0h+var_288]
0x180061b8d  lea     rdx, [rcx+10h]
0x180061b91  test    eax, eax
0x180061b93  jnz     loc_180061AC4
0x180061b99  jmp     loc_180061A5E
0x180061b9e  mov     rcx, rdi; hFile
0x180061ba1  call    cs:__imp_FlushFileBuffers
0x180061ba7  test    eax, eax
0x180061ba9  jz      loc_180061A5E
0x180061baf  mov     r9, [rsp+2D0h+lpLastWriteTime]; lpLastWriteTime
0x180061bb4  xor     r8d, r8d; lpLastAccessTime
0x180061bb7  xor     edx, edx; lpCreationTime
0x180061bb9  mov     rcx, rdi; hFile
0x180061bbc  call    cs:__imp_GetFileTime
0x180061bc2  test    eax, eax
0x180061bc4  jz      loc_180061A5E
0x180061bca  test    r15, r15
0x180061bcd  jz      short loc_180061BF7
0x180061bcf  lea     rdx, [rsp+2D0h+FileSize]; lpFileSize
0x180061bd4  mov     rcx, rdi; hFile
0x180061bd7  call    cs:__imp_GetFileSizeEx
0x180061bdd  test    eax, eax
0x180061bdf  jz      loc_180061A5E
0x180061be5  mov     rax, qword ptr [rsp+2D0h+FileSize]
0x180061bea  mov     ecx, 400h
0x180061bef  cqo
0x180061bf1  idiv    rcx
0x180061bf4  mov     [r15], eax
0x180061bf7  xor     ebx, ebx
0x180061bf9  mov     rcx, rdi; hObject
0x180061bfc  call    cs:__imp_CloseHandle
0x180061c02  mov     eax, ebx
0x180061c04  mov     rcx, [rbp+1D0h+var_50]
0x180061c0b  xor     rcx, rsp; StackCookie
0x180061c0e  call    __security_check_cookie
0x180061c13  add     rsp, 298h
0x180061c1a  pop     r15
0x180061c1c  pop     r14
0x180061c1e  pop     r13
0x180061c20  pop     r12
0x180061c22  pop     rdi
0x180061c23  pop     rsi
0x180061c24  pop     rbx
0x180061c25  pop     rbp
0x180061c26  retn
```
