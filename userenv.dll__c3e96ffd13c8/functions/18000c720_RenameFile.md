# _RenameFile

- ea: `0x18000c720`
- end: `0x18000c8b9`
- name: `_RenameFile`
- size: `409`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c25c`

## callees

- `0x1800095cc`
- `0x18000c720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c827`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c78e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c7eb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c814`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c835`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c870`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c78e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c7eb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c814`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c835`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000c870`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c773`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c7c7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c773`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c7c7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c741`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c805`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c741`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000c805`

## string_xrefs

- `0x18000c7ac`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c840`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c87b`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18000c799`: `Unable to remove READONLY attribute from %ws. Copy may fail`

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
0x18000c720  push    rbx
0x18000c722  push    rbp
0x18000c723  push    rsi
0x18000c724  push    rdi
0x18000c725  push    r14
0x18000c727  sub     rsp, 30h
0x18000c72b  mov     rsi, r8
0x18000c72e  mov     dword ptr [r8], 1
0x18000c735  mov     r8d, 9; dwFlags
0x18000c73b  mov     rdi, rdx
0x18000c73e  mov     rbp, rcx
0x18000c741  call    cs:__imp_MoveFileExW
0x18000c747  test    eax, eax
0x18000c749  jz      short loc_18000C752
0x18000c74b  xor     ebx, ebx
0x18000c74d  jmp     loc_18000C8AC
0x18000c752  call    cs:__imp_GetLastError
0x18000c758  mov     ebx, eax
0x18000c75a  cmp     eax, 2
0x18000c75d  jnz     short loc_18000C767
0x18000c75f  mov     dword ptr [rsi], 0
0x18000c765  jmp     short loc_18000C74B
0x18000c767  cmp     eax, 5
0x18000c76a  jnz     loc_18000C89F
0x18000c770  mov     rcx, rdi; lpFileName
0x18000c773  call    cs:__imp_GetFileAttributesW
0x18000c779  mov     esi, eax
0x18000c77b  cmp     eax, 0FFFFFFFFh
0x18000c77e  jz      short loc_18000C7C4
0x18000c780  test    sil, 1
0x18000c784  jz      short loc_18000C7C4
0x18000c786  mov     edx, eax
0x18000c788  mov     rcx, rdi; lpFileName
0x18000c78b  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18000c78e  call    cs:__imp_SetFileAttributesW
0x18000c794  mov     rcx, [rsp+58h]; this
0x18000c799  lea     rdx, aUnableToRemove; "Unable to remove READONLY attribute fro"...
0x18000c7a0  test    eax, eax
0x18000c7a2  mov     [rsp+58h+var_30], rdi; char *
0x18000c7a7  mov     qword ptr [rsp+58h+var_38], rdx; bool
0x18000c7ac  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c7b3  setz    al
0x18000c7b6  mov     edx, 0C9h; void *
0x18000c7bb  movzx   r9d, al; char *
0x18000c7bf  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000c7c4  mov     rcx, rbp; lpFileName
0x18000c7c7  call    cs:__imp_GetFileAttributesW
0x18000c7cd  mov     r14d, eax
0x18000c7d0  cmp     eax, 0FFFFFFFFh
0x18000c7d3  jz      loc_18000C8A3
0x18000c7d9  test    r14b, 1
0x18000c7dd  jz      loc_18000C8A3
0x18000c7e3  mov     edx, eax
0x18000c7e5  mov     rcx, rbp; lpFileName
0x18000c7e8  and     edx, 0FFFFFFFEh; dwFileAttributes
0x18000c7eb  call    cs:__imp_SetFileAttributesW
0x18000c7f1  test    eax, eax
0x18000c7f3  jz      loc_18000C8A3
0x18000c7f9  mov     r8d, 9; dwFlags
0x18000c7ff  mov     rdx, rdi; lpNewFileName
0x18000c802  mov     rcx, rbp; lpExistingFileName
0x18000c805  call    cs:__imp_MoveFileExW
0x18000c80b  test    eax, eax
0x18000c80d  jz      short loc_18000C827
0x18000c80f  mov     edx, esi; dwFileAttributes
0x18000c811  mov     rcx, rdi; lpFileName
0x18000c814  call    cs:__imp_SetFileAttributesW
0x18000c81a  test    eax, eax
0x18000c81c  jz      loc_18000C8A3
0x18000c822  jmp     loc_18000C74B
0x18000c827  call    cs:__imp_GetLastError
0x18000c82d  mov     edx, r14d; dwFileAttributes
0x18000c830  mov     rcx, rbp; lpFileName
0x18000c833  mov     ebx, eax
0x18000c835  call    cs:__imp_SetFileAttributesW
0x18000c83b  mov     rcx, [rsp+58h]; this
0x18000c840  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c847  test    eax, eax
0x18000c849  mov     [rsp+58h+var_30], rbp; char *
0x18000c84e  lea     rbp, aUnableToRestor; "Unable to restore file attributes of %w"...
0x18000c855  mov     edx, 0DDh; void *
0x18000c85a  setz    al
0x18000c85d  mov     qword ptr [rsp+58h+var_38], rbp; bool
0x18000c862  movzx   r9d, al; char *
0x18000c866  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000c86b  mov     edx, esi; dwFileAttributes
0x18000c86d  mov     rcx, rdi; lpFileName
0x18000c870  call    cs:__imp_SetFileAttributesW
0x18000c876  mov     rcx, [rsp+58h]; this
0x18000c87b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000c882  test    eax, eax
0x18000c884  mov     [rsp+58h+var_30], rdi; char *
0x18000c889  mov     edx, 0DFh; void *
0x18000c88e  mov     qword ptr [rsp+58h+var_38], rbp; bool
0x18000c893  setz    al
0x18000c896  movzx   r9d, al; char *
0x18000c89a  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18000c89f  test    ebx, ebx
0x18000c8a1  jle     short loc_18000C8AC
0x18000c8a3  movzx   ebx, bx
0x18000c8a6  or      ebx, 80070000h
0x18000c8ac  mov     eax, ebx
0x18000c8ae  add     rsp, 30h
0x18000c8b2  pop     r14
0x18000c8b4  pop     rdi
0x18000c8b5  pop     rsi
0x18000c8b6  pop     rbp
0x18000c8b7  pop     rbx
0x18000c8b8  retn
```
