# replaceUTF8

- ea: `0x1800269f0`
- end: `0x180026c7b`
- name: `replaceUTF8`
- size: `651`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001a6cc`

## callees

- `0x180005464`
- `0x18001b4ac`
- `0x1800269f0`
- `0x180034f28`
- `0x180036f50`

## import_xrefs

- `SHLWAPI!PathIsSameRootW` at `0x180026a91`
- `SHLWAPI!PathIsSameRootW` at `0x180026a91`
- `SHLWAPI!__imp_SHAnsiToUnicodeCP` at `0x180026a32`
- `SHLWAPI!__imp_SHAnsiToUnicodeCP` at `0x180026a4c`
- `SHLWAPI!__imp_SHAnsiToUnicodeCP` at `0x180026a32`
- `SHLWAPI!__imp_SHAnsiToUnicodeCP` at `0x180026a4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026aae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ba6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026aae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ba6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c70`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180026b8d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180026b8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026b0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026b68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026be1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026c15`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026b0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026b68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026be1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026c15`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x180026ad8`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x180026ad8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall replaceUTF8(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  BOOL IsSameRootW; // esi
  HANDLE FileW; // rax
  HANDLE v9; // r14
  __int64 v10; // rcx
  HANDLE v11; // rbp
  WCHAR pszPath2[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR pszPath1[264]; // [rsp+250h] [rbp-248h] BYREF

  if ( (int)SHAnsiToUnicodeCP(65001, a1, pszPath2, 260) <= 0 || (int)SHAnsiToUnicodeCP(65001, a2, pszPath1, 260) <= 0 )
    return 14;
  IsSameRootW = PathIsSameRootW(pszPath1, pszPath2);
  if ( IsSameRootW )
  {
    v5 = 0;
    CloseHandle(*(HANDLE *)(a3 + 21528));
    *(_QWORD *)(a3 + 21528) = -1;
    if ( ReplaceFileW(pszPath2, pszPath1, 0, 0, 0, 0) )
    {
LABEL_7:
      FileW = CreateFileW(pszPath2, 0xC0000000, 1u, 0, 4u, 0x80u, 0);
      *(_QWORD *)(a3 + 21528) = FileW;
      if ( FileW == (HANDLE)-1LL )
        return (unsigned int)ZipErrorFromLastError(13);
      return v5;
    }
  }
  v9 = CreateFileW(pszPath1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( v9 != (HANDLE)-1LL )
  {
    if ( IsSameRootW )
    {
      v11 = CreateFileW(pszPath2, 0xC0000000, 0, 0, 2u, 0x80u, 0);
      if ( v11 == (HANDLE)-1LL )
      {
        v11 = CreateFileW(pszPath2, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
        if ( v11 == (HANDLE)-1LL )
        {
          CloseHandle(v9);
          v10 = 15;
          return ZipErrorFromLastError(v10);
        }
      }
    }
    else
    {
      DZSetFilePointer(*(_QWORD *)(a3 + 21528), 0, 0);
      v11 = *(HANDLE *)(a3 + 21528);
    }
    v5 = fcopy(v9, v11);
    CloseHandle(v9);
    if ( IsSameRootW )
      CloseHandle(v11);
    DeleteFileW(pszPath1);
    if ( v5 )
    {
      if ( !IsSameRootW )
      {
        CloseHandle(*(HANDLE *)(a3 + 21528));
        *(_QWORD *)(a3 + 21528) = -1;
      }
      return v5;
    }
    if ( !IsSameRootW )
      return v5;
    goto LABEL_7;
  }
  v10 = 10;
  return ZipErrorFromLastError(v10);
}

```

## disassembly

```asm
0x1800269f0  mov     [rsp+arg_18], rbx
0x1800269f5  push    rbp
0x1800269f6  push    rsi
0x1800269f7  push    rdi
0x1800269f8  push    r12
0x1800269fa  push    r14
0x1800269fc  sub     rsp, 470h
0x180026a03  mov     rax, cs:__security_cookie
0x180026a0a  xor     rax, rsp
0x180026a0d  mov     [rsp+498h+var_38], rax
0x180026a15  mov     rbx, rdx
0x180026a18  mov     rdi, r8
0x180026a1b  mov     rdx, rcx
0x180026a1e  lea     r8, [rsp+498h+pszPath2]
0x180026a23  mov     esi, 104h
0x180026a28  mov     ebp, 0FDE9h
0x180026a2d  mov     r9d, esi
0x180026a30  mov     ecx, ebp
0x180026a32  call    cs:__imp_SHAnsiToUnicodeCP
0x180026a38  test    eax, eax
0x180026a3a  jle     short loc_180026A56
0x180026a3c  mov     r9d, esi
0x180026a3f  lea     r8, [rsp+498h+pszPath1]
0x180026a47  mov     rdx, rbx
0x180026a4a  mov     ecx, ebp
0x180026a4c  call    cs:__imp_SHAnsiToUnicodeCP
0x180026a52  test    eax, eax
0x180026a54  jg      short loc_180026A84
0x180026a56  mov     ebx, 0Eh
0x180026a5b  mov     eax, ebx
0x180026a5d  mov     rcx, [rsp+498h+var_38]
0x180026a65  xor     rcx, rsp; StackCookie
0x180026a68  call    __security_check_cookie
0x180026a6d  mov     rbx, [rsp+498h+arg_18]
0x180026a75  add     rsp, 470h
0x180026a7c  pop     r14
0x180026a7e  pop     r12
0x180026a80  pop     rdi
0x180026a81  pop     rsi
0x180026a82  pop     rbp
0x180026a83  retn
0x180026a84  lea     rdx, [rsp+498h+pszPath2]; pszPath2
0x180026a89  lea     rcx, [rsp+498h+pszPath1]; pszPath1
0x180026a91  call    cs:__imp_PathIsSameRootW
0x180026a97  or      r12, 0FFFFFFFFFFFFFFFFh
0x180026a9b  mov     esi, eax
0x180026a9d  test    eax, eax
0x180026a9f  jz      loc_180026B3C
0x180026aa5  mov     rcx, [rdi+5418h]; hObject
0x180026aac  xor     ebx, ebx
0x180026aae  call    cs:__imp_CloseHandle
0x180026ab4  xor     r9d, r9d; dwReplaceFlags
0x180026ab7  mov     [rsp+498h+lpReserved], rbx; lpReserved
0x180026abc  xor     r8d, r8d; lpBackupFileName
0x180026abf  mov     [rdi+5418h], r12
0x180026ac6  lea     rdx, [rsp+498h+pszPath1]; lpReplacementFileName
0x180026ace  mov     [rsp+498h+lpExclude], rbx; lpExclude
0x180026ad3  lea     rcx, [rsp+498h+pszPath2]; lpReplacedFileName
0x180026ad8  call    cs:__imp_ReplaceFileW
0x180026ade  test    eax, eax
0x180026ae0  jz      short loc_180026B3C
0x180026ae2  xor     r9d, r9d; lpSecurityAttributes
0x180026ae5  mov     [rsp+498h+hTemplateFile], 0; hTemplateFile
0x180026aee  mov     dword ptr [rsp+498h+lpReserved], 80h; dwFlagsAndAttributes
0x180026af6  lea     rcx, [rsp+498h+pszPath2]; lpFileName
0x180026afb  mov     edx, 0C0000000h; dwDesiredAccess
0x180026b00  mov     dword ptr [rsp+498h+lpExclude], 4; dwCreationDisposition
0x180026b08  lea     r8d, [r9+1]; dwShareMode
0x180026b0c  call    cs:__imp_CreateFileW
0x180026b12  mov     [rdi+5418h], rax
0x180026b19  cmp     rax, r12
0x180026b1c  jnz     loc_180026A5B
0x180026b22  mov     ecx, 0Dh
0x180026b27  call    ZipErrorFromLastError
0x180026b2c  mov     ebx, eax
0x180026b2e  jmp     loc_180026A5B
0x180026b33  test    esi, esi
0x180026b35  jnz     short loc_180026AE2
0x180026b37  jmp     loc_180026A5B
0x180026b3c  mov     [rsp+498h+hTemplateFile], 0; hTemplateFile
0x180026b45  lea     rcx, [rsp+498h+pszPath1]; lpFileName
0x180026b4d  mov     r8d, 3; dwShareMode
0x180026b53  mov     dword ptr [rsp+498h+lpReserved], 80h; dwFlagsAndAttributes
0x180026b5b  xor     r9d, r9d; lpSecurityAttributes
0x180026b5e  mov     dword ptr [rsp+498h+lpExclude], r8d; dwCreationDisposition
0x180026b63  mov     edx, 80000000h; dwDesiredAccess
0x180026b68  call    cs:__imp_CreateFileW
0x180026b6e  mov     r14, rax
0x180026b71  cmp     rax, r12
0x180026b74  jnz     short loc_180026BB8
0x180026b76  mov     ecx, 0Ah
0x180026b7b  call    ZipErrorFromLastError
0x180026b80  jmp     loc_180026A5D
0x180026b85  lea     rcx, [rsp+498h+pszPath1]; lpFileName
0x180026b8d  call    cs:__imp_DeleteFileW
0x180026b93  test    ebx, ebx
0x180026b95  jz      short loc_180026B33
0x180026b97  test    esi, esi
0x180026b99  jnz     loc_180026A5B
0x180026b9f  mov     rcx, [rdi+5418h]; hObject
0x180026ba6  call    cs:__imp_CloseHandle
0x180026bac  mov     [rdi+5418h], r12
0x180026bb3  jmp     loc_180026A5B
0x180026bb8  xor     r8d, r8d; dwShareMode
0x180026bbb  test    esi, esi
0x180026bbd  jz      short loc_180026C34
0x180026bbf  mov     [rsp+498h+hTemplateFile], r8; hTemplateFile
0x180026bc4  lea     ebx, [r8+2]
0x180026bc8  mov     dword ptr [rsp+498h+lpReserved], 80h; dwFlagsAndAttributes
0x180026bd0  lea     rcx, [rsp+498h+pszPath2]; lpFileName
0x180026bd5  xor     r9d, r9d; lpSecurityAttributes
0x180026bd8  mov     dword ptr [rsp+498h+lpExclude], ebx; dwCreationDisposition
0x180026bdc  mov     edx, 0C0000000h; dwDesiredAccess
0x180026be1  call    cs:__imp_CreateFileW
0x180026be7  mov     rbp, rax
0x180026bea  cmp     rax, r12
0x180026bed  jnz     short loc_180026C49
0x180026bef  mov     [rsp+498h+hTemplateFile], 0; hTemplateFile
0x180026bf8  lea     r8d, [rbx-1]; dwShareMode
0x180026bfc  mov     dword ptr [rsp+498h+lpReserved], 80h; dwFlagsAndAttributes
0x180026c04  lea     rcx, [rsp+498h+pszPath2]; lpFileName
0x180026c09  xor     r9d, r9d; lpSecurityAttributes
0x180026c0c  mov     dword ptr [rsp+498h+lpExclude], ebx; dwCreationDisposition
0x180026c10  mov     edx, 0C0000000h; dwDesiredAccess
0x180026c15  call    cs:__imp_CreateFileW
0x180026c1b  mov     rbp, rax
0x180026c1e  cmp     rax, r12
0x180026c21  jnz     short loc_180026C49
0x180026c23  mov     rcx, r14; hObject
0x180026c26  call    cs:__imp_CloseHandle
0x180026c2c  lea     ecx, [rbx+0Dh]
0x180026c2f  jmp     loc_180026B7B
0x180026c34  mov     rcx, [rdi+5418h]
0x180026c3b  xor     edx, edx
0x180026c3d  call    DZSetFilePointer
0x180026c42  mov     rbp, [rdi+5418h]
0x180026c49  mov     r9, rdi
0x180026c4c  mov     r8, r12
0x180026c4f  mov     rdx, rbp; HANDLE
0x180026c52  mov     rcx, r14; hFile
0x180026c55  call    fcopy
0x180026c5a  mov     rcx, r14; hObject
0x180026c5d  mov     ebx, eax
0x180026c5f  call    cs:__imp_CloseHandle
0x180026c65  test    esi, esi
0x180026c67  jz      loc_180026B85
0x180026c6d  mov     rcx, rbp; hObject
0x180026c70  call    cs:__imp_CloseHandle
0x180026c76  jmp     loc_180026B85
```
