# create_output_file

- ea: `0x180005738`
- end: `0x18000587a`
- name: `create_output_file`
- size: `322`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800054dc`

## callees

- `0x180005738`
- `0x180029b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000582c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005854`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005753`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005753`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000579b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000579b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005768`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005768`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800057e3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800057e3`
- `ntdll!RtlGetLastNtStatus` at `0x1800057c9`
- `ntdll!RtlGetLastNtStatus` at `0x1800057fd`
- `ntdll!RtlGetLastNtStatus` at `0x1800057c9`
- `ntdll!RtlGetLastNtStatus` at `0x1800057fd`

## pseudocode

```c
__int64 __fastcall create_output_file(LPCWSTR lpFileName, signed int *a2)
{
  _QWORD *Value; // rbp
  DWORD FileAttributesW; // ebx
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  signed int v9; // eax
  signed int v10; // eax
  DWORD LastError; // eax

  *a2 = 0;
  Value = TlsGetValue(dwUnZIPTlsIndex);
  if ( !Value )
    return 4;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1
    || (unsigned int)DeleteFileWithoutPending(lpFileName)
    || RtlGetLastNtStatus() == -1073741535
    && (FileAttributesW & 1) != 0
    && SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE)
    && (unsigned int)DeleteFileWithoutPending(lpFileName) )
  {
    v6 = 0;
    FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 2u, 0x8000020u, 0);
    Value[9023] = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError == 5 )
      {
        return 53;
      }
      else if ( LastError == 206 )
      {
        return 51;
      }
      else
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        *a2 = v10;
        return 54;
      }
    }
    return v6;
  }
  else
  {
    if ( RtlGetLastNtStatus() == -1073741535 )
    {
      v9 = -2147024864;
    }
    else
    {
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
    }
    *a2 = v9;
    return 54;
  }
}

```

## disassembly

```asm
0x180005738  push    rbx
0x18000573a  push    rbp
0x18000573b  push    rsi
0x18000573c  push    rdi
0x18000573d  sub     rsp, 48h
0x180005741  mov     rdi, rcx
0x180005744  mov     dword ptr [rdx], 0
0x18000574a  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180005750  mov     rsi, rdx
0x180005753  call    cs:__imp_TlsGetValue
0x180005759  mov     rbp, rax
0x18000575c  test    rax, rax
0x18000575f  jz      loc_18000584A
0x180005765  mov     rcx, rdi; lpFileName
0x180005768  call    cs:__imp_GetFileAttributesW
0x18000576e  mov     ebx, eax
0x180005770  cmp     eax, 0FFFFFFFFh
0x180005773  jnz     short loc_1800057BD
0x180005775  xor     ebx, ebx
0x180005777  xor     r9d, r9d; lpSecurityAttributes
0x18000577a  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x18000577f  mov     edx, 0C0000000h; dwDesiredAccess
0x180005784  mov     [rsp+68h+dwFlagsAndAttributes], 8000020h; dwFlagsAndAttributes
0x18000578c  mov     rcx, rdi; lpFileName
0x18000578f  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x180005797  lea     r8d, [rbx+3]; dwShareMode
0x18000579b  call    cs:__imp_CreateFileW
0x1800057a1  mov     [rbp+119F8h], rax
0x1800057a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800057ac  jz      loc_180005854
0x1800057b2  mov     eax, ebx
0x1800057b4  add     rsp, 48h
0x1800057b8  pop     rdi
0x1800057b9  pop     rsi
0x1800057ba  pop     rbp
0x1800057bb  pop     rbx
0x1800057bc  retn
0x1800057bd  mov     rcx, rdi
0x1800057c0  call    DeleteFileWithoutPending
0x1800057c5  test    eax, eax
0x1800057c7  jnz     short loc_180005775
0x1800057c9  call    cs:__imp_RtlGetLastNtStatus
0x1800057cf  cmp     eax, 0C0000121h
0x1800057d4  jnz     short loc_1800057FD
0x1800057d6  test    bl, 1
0x1800057d9  jz      short loc_1800057FD
0x1800057db  and     ebx, 0FFFFFFFEh
0x1800057de  mov     rcx, rdi; lpFileName
0x1800057e1  mov     edx, ebx; dwFileAttributes
0x1800057e3  call    cs:__imp_SetFileAttributesW
0x1800057e9  test    eax, eax
0x1800057eb  jz      short loc_1800057FD
0x1800057ed  mov     rcx, rdi
0x1800057f0  call    DeleteFileWithoutPending
0x1800057f5  test    eax, eax
0x1800057f7  jnz     loc_180005775
0x1800057fd  call    cs:__imp_RtlGetLastNtStatus
0x180005803  cmp     eax, 0C0000121h
0x180005808  jnz     short loc_180005811
0x18000580a  mov     eax, 80070020h
0x18000580f  jmp     short loc_180005823
0x180005811  call    cs:__imp_GetLastError
0x180005817  test    eax, eax
0x180005819  jle     short loc_180005823
0x18000581b  movzx   eax, ax
0x18000581e  or      eax, 80070000h
0x180005823  mov     [rsi], eax
0x180005825  mov     eax, 36h ; '6'
0x18000582a  jmp     short loc_1800057B4
0x18000582c  call    cs:__imp_GetLastError
0x180005832  test    eax, eax
0x180005834  jle     short loc_18000583E
0x180005836  movzx   eax, ax
0x180005839  or      eax, 80070000h
0x18000583e  mov     [rsi], eax
0x180005840  mov     ebx, 36h ; '6'
0x180005845  jmp     loc_1800057B2
0x18000584a  mov     eax, 4
0x18000584f  jmp     loc_1800057B4
0x180005854  call    cs:__imp_GetLastError
0x18000585a  cmp     eax, 5
0x18000585d  jz      short loc_180005870
0x18000585f  cmp     eax, 0CEh
0x180005864  jnz     short loc_18000582C
0x180005866  mov     ebx, 33h ; '3'
0x18000586b  jmp     loc_1800057B2
0x180005870  mov     ebx, 35h ; '5'
0x180005875  jmp     loc_1800057B2
```
