# _RenameFile

- ea: `0x18000d2f8`
- end: `0x18000d4d4`
- name: `_RenameFile`
- size: `476`
- prototype: `__int64 __fastcall(char *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cdc4`

## callees

- `0x180009eac`
- `0x18000d2f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d330`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d42f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d378`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d3e1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d416`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d443`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d484`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d378`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d3e1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d416`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d443`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d484`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d357`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d3b7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d357`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d3b7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000d319`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000d401`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000d319`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000d401`

## string_xrefs

- `0x18000d39c`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000d454`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000d495`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000d389`: `Unable to remove READONLY attribute from %ws. Copy may fail`

## pseudocode

```c
__int64 __fastcall RenameFile(const WCHAR *a1, const WCHAR *a2, _DWORD *a3)
{
  signed int v6; // ebx
  DWORD LastError; // eax
  DWORD FileAttributesW; // eax
  DWORD v9; // esi
  BOOL v10; // eax
  DWORD v11; // eax
  DWORD v12; // r14d
  BOOL v13; // eax
  BOOL v14; // eax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a3 = 1;
  if ( MoveFileExW(a1, a2, 9u) )
    return 0;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError != 2 )
  {
    if ( LastError == 5 )
    {
      FileAttributesW = GetFileAttributesW(a2);
      v9 = FileAttributesW;
      if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
      {
        v10 = SetFileAttributesW(a2, FileAttributesW & 0xFFFFFFFE);
        wil::details::in1diag3::Log_GetLastErrorIfMsg(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
          (const char *)!v10,
          (bool)"Unable to remove READONLY attribute from %ws. Copy may fail",
          (const char *)a2);
      }
      v11 = GetFileAttributesW(a1);
      v12 = v11;
      if ( v11 == -1 || (v11 & 1) == 0 || !SetFileAttributesW(a1, v11 & 0xFFFFFFFE) )
        return (unsigned __int16)v6 | 0x80070000;
      if ( MoveFileExW(a1, a2, 9u) )
      {
        if ( SetFileAttributesW(a2, v9) )
          return 0;
        return (unsigned __int16)v6 | 0x80070000;
      }
      v6 = GetLastError();
      v13 = SetFileAttributesW(a1, v12);
      wil::details::in1diag3::Log_GetLastErrorIfMsg(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
        (const char *)!v13,
        (bool)"Unable to restore file attributes of %ws",
        (const char *)a1);
      v14 = SetFileAttributesW(a2, v9);
      wil::details::in1diag3::Log_GetLastErrorIfMsg(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
        (const char *)!v14,
        (bool)"Unable to restore file attributes of %ws",
        (const char *)a2);
    }
    if ( v6 <= 0 )
      return (unsigned int)v6;
    return (unsigned __int16)v6 | 0x80070000;
  }
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000d2f8  push    rbx
0x18000d2fa  push    rbp
0x18000d2fb  push    rsi
0x18000d2fc  push    rdi
0x18000d2fd  push    r14
0x18000d2ff  sub     rsp, 30h
0x18000d303  mov     rsi, r8
0x18000d306  mov     dword ptr [r8], 1
0x18000d30d  mov     r8d, 9; dwFlags
0x18000d313  mov     rdi, rdx
0x18000d316  mov     rbp, rcx
0x18000d319  call    cs:__imp_MoveFileExW
0x18000d320  nop     dword ptr [rax+rax+00h]
0x18000d325  test    eax, eax
0x18000d327  jz      short loc_18000D330
0x18000d329  xor     ebx, ebx
0x18000d32b  jmp     loc_18000D4C6
0x18000d330  call    cs:__imp_GetLastError
0x18000d337  nop     dword ptr [rax+rax+00h]
0x18000d33c  mov     ebx, eax
0x18000d33e  cmp     eax, 2
0x18000d341  jnz     short loc_18000D34B
0x18000d343  mov     dword ptr [rsi], 0
0x18000d349  jmp     short loc_18000D329
0x18000d34b  cmp     eax, 5
0x18000d34e  jnz     loc_18000D4B9
0x18000d354  mov     rcx, rdi; lpFileName
0x18000d357  call    cs:__imp_GetFileAttributesW
0x18000d35e  nop     dword ptr [rax+rax+00h]
0x18000d363  mov     esi, eax
0x18000d365  cmp     eax, 0FFFFFFFFh
0x18000d368  jz      short loc_18000D3B4
0x18000d36a  test    sil, 1
0x18000d36e  jz      short loc_18000D3B4
0x18000d370  mov     edx, eax
0x18000d372  mov     rcx, rdi; lpFileName
0x18000d375  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18000d378  call    cs:__imp_SetFileAttributesW
0x18000d37f  nop     dword ptr [rax+rax+00h]
0x18000d384  mov     rcx, [rsp+58h]; this
0x18000d389  lea     rdx, aUnableToRemove; "Unable to remove READONLY attribute fro"...
0x18000d390  test    eax, eax
0x18000d392  mov     [rsp+58h+var_30], rdi; char *
0x18000d397  mov     qword ptr [rsp+58h+var_38], rdx; bool
0x18000d39c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d3a3  setz    al
0x18000d3a6  mov     edx, 0C9h; void *
0x18000d3ab  movzx   r9d, al; char *
0x18000d3af  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000d3b4  mov     rcx, rbp; lpFileName
0x18000d3b7  call    cs:__imp_GetFileAttributesW
0x18000d3be  nop     dword ptr [rax+rax+00h]
0x18000d3c3  mov     r14d, eax
0x18000d3c6  cmp     eax, 0FFFFFFFFh
0x18000d3c9  jz      loc_18000D4BD
0x18000d3cf  test    r14b, 1
0x18000d3d3  jz      loc_18000D4BD
0x18000d3d9  mov     edx, eax
0x18000d3db  mov     rcx, rbp; lpFileName
0x18000d3de  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18000d3e1  call    cs:__imp_SetFileAttributesW
0x18000d3e8  nop     dword ptr [rax+rax+00h]
0x18000d3ed  test    eax, eax
0x18000d3ef  jz      loc_18000D4BD
0x18000d3f5  mov     r8d, 9; dwFlags
0x18000d3fb  mov     rdx, rdi; lpNewFileName
0x18000d3fe  mov     rcx, rbp; lpExistingFileName
0x18000d401  call    cs:__imp_MoveFileExW
0x18000d408  nop     dword ptr [rax+rax+00h]
0x18000d40d  test    eax, eax
0x18000d40f  jz      short loc_18000D42F
0x18000d411  mov     edx, esi; dwFileAttributes
0x18000d413  mov     rcx, rdi; lpFileName
0x18000d416  call    cs:__imp_SetFileAttributesW
0x18000d41d  nop     dword ptr [rax+rax+00h]
0x18000d422  test    eax, eax
0x18000d424  jz      loc_18000D4BD
0x18000d42a  jmp     loc_18000D329
0x18000d42f  call    cs:__imp_GetLastError
0x18000d436  nop     dword ptr [rax+rax+00h]
0x18000d43b  mov     edx, r14d; dwFileAttributes
0x18000d43e  mov     rcx, rbp; lpFileName
0x18000d441  mov     ebx, eax
0x18000d443  call    cs:__imp_SetFileAttributesW
0x18000d44a  nop     dword ptr [rax+rax+00h]
0x18000d44f  mov     rcx, [rsp+58h]; this
0x18000d454  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d45b  test    eax, eax
0x18000d45d  mov     [rsp+58h+var_30], rbp; char *
0x18000d462  lea     rbp, aUnableToRestor; "Unable to restore file attributes of %w"...
0x18000d469  mov     edx, 0DDh; void *
0x18000d46e  setz    al
0x18000d471  mov     qword ptr [rsp+58h+var_38], rbp; bool
0x18000d476  movzx   r9d, al; char *
0x18000d47a  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000d47f  mov     edx, esi; dwFileAttributes
0x18000d481  mov     rcx, rdi; lpFileName
0x18000d484  call    cs:__imp_SetFileAttributesW
0x18000d48b  nop     dword ptr [rax+rax+00h]
0x18000d490  mov     rcx, [rsp+58h]; this
0x18000d495  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000d49c  test    eax, eax
0x18000d49e  mov     [rsp+58h+var_30], rdi; char *
0x18000d4a3  mov     edx, 0DFh; void *
0x18000d4a8  mov     qword ptr [rsp+58h+var_38], rbp; bool
0x18000d4ad  setz    al
0x18000d4b0  movzx   r9d, al; char *
0x18000d4b4  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000d4b9  test    ebx, ebx
0x18000d4bb  jle     short loc_18000D4C6
0x18000d4bd  movzx   ebx, bx
0x18000d4c0  or      ebx, 80070000h
0x18000d4c6  mov     eax, ebx
0x18000d4c8  add     rsp, 30h
0x18000d4cc  pop     r14
0x18000d4ce  pop     rdi
0x18000d4cf  pop     rsi
0x18000d4d0  pop     rbp
0x18000d4d1  pop     rbx
0x18000d4d2  retn
```
