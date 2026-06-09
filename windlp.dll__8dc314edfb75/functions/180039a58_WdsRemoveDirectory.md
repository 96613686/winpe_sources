# WdsRemoveDirectory

- ea: `0x180039a58`
- end: `0x180039b68`
- name: `WdsRemoveDirectory`
- size: `272`
- prototype: `_BOOL8 __fastcall(const wchar_t *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003a380`
- `0x18003a4c8`
- `0x18003a800`

## callees

- `0x180038c34`
- `0x180039394`
- `0x180039a58`
- `0x18003c464`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180039a95`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180039a95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039b07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039b07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039b15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039b15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039b48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039b57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039b48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039b57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ada`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b1f`

## string_xrefs

- `0x180039aa8`: `WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x`
- `0x180039b28`: `WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x`
- `0x180039aeb`: `WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall WdsRemoveDirectory(const wchar_t *a1)
{
  const WCHAR *v2; // rax
  WCHAR *v3; // rsi
  DWORD LastError; // ebx
  BOOL v5; // ebp
  HANDLE ProcessHeap; // rax
  __int64 v8; // [rsp+20h] [rbp-38h]

  if ( a1 && *a1 )
  {
    v2 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v3 = (WCHAR *)v2;
    if ( v2 )
    {
      LastError = 0;
      if ( !SetFileAttributesW(v2, 0x80u) )
      {
        LastError = GetLastError();
        LibLog(
          &g_WdsLibLog,
          50331648,
          L"WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x",
          v3,
          LastError);
      }
      v5 = DeleteFileEx2((__int64)v3, 0);
      if ( !v5 )
      {
        if ( !LastError )
          LastError = GetLastError();
        LODWORD(v8) = GetLastError();
        LibLog(&g_WdsLibLog, 50331648, L"WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x", v3, v8);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    else
    {
      v5 = 0;
      LastError = GetLastError();
      LibLog(&g_WdsLibLog, 50331648, L"WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x", a1, LastError);
    }
    SetLastError(LastError);
    return v5;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x180039a58  push    rbx
0x180039a5a  push    rbp
0x180039a5b  push    rsi
0x180039a5c  push    rdi
0x180039a5d  sub     rsp, 38h
0x180039a61  mov     rdi, rcx
0x180039a64  test    rcx, rcx
0x180039a67  jz      loc_180039B52
0x180039a6d  xor     eax, eax
0x180039a6f  cmp     ax, [rcx]
0x180039a72  jz      loc_180039B52
0x180039a78  xor     edx, edx
0x180039a7a  call    PrepareUnicodePathEx
0x180039a7f  mov     rsi, rax
0x180039a82  test    rax, rax
0x180039a85  jz      loc_180039B1D
0x180039a8b  mov     edx, 80h; dwFileAttributes
0x180039a90  mov     rcx, rax; lpFileName
0x180039a93  xor     ebx, ebx
0x180039a95  call    cs:__imp_SetFileAttributesW
0x180039a9b  test    eax, eax
0x180039a9d  jnz     short loc_180039AC6
0x180039a9f  call    cs:__imp_GetLastError
0x180039aa5  mov     r9, rsi
0x180039aa8  lea     r8, aWdsremovedirec; "WdsRemoveDirectory: Unable to clear att"...
0x180039aaf  lea     rcx, g_WdsLibLog
0x180039ab6  mov     dword ptr [rsp+58h+var_38], eax
0x180039aba  mov     edx, 3000000h
0x180039abf  mov     ebx, eax
0x180039ac1  call    LibLog
0x180039ac6  xor     edx, edx
0x180039ac8  mov     rcx, rsi
0x180039acb  call    DeleteFileEx2
0x180039ad0  mov     ebp, eax
0x180039ad2  test    eax, eax
0x180039ad4  jnz     short loc_180039B07
0x180039ad6  test    ebx, ebx
0x180039ad8  jnz     short loc_180039AE2
0x180039ada  call    cs:__imp_GetLastError
0x180039ae0  mov     ebx, eax
0x180039ae2  call    cs:__imp_GetLastError
0x180039ae8  mov     r9, rsi
0x180039aeb  lea     r8, aWdsremovedirec_0; "WdsRemoveDirectory: Unable to remove di"...
0x180039af2  lea     rcx, g_WdsLibLog
0x180039af9  mov     dword ptr [rsp+58h+var_38], eax
0x180039afd  mov     edx, 3000000h
0x180039b02  call    LibLog
0x180039b07  call    cs:__imp_GetProcessHeap
0x180039b0d  mov     r8, rsi; lpMem
0x180039b10  xor     edx, edx; dwFlags
0x180039b12  mov     rcx, rax; hHeap
0x180039b15  call    cs:__imp_HeapFree
0x180039b1b  jmp     short loc_180039B46
0x180039b1d  xor     ebp, ebp
0x180039b1f  call    cs:__imp_GetLastError
0x180039b25  mov     r9, rdi
0x180039b28  lea     r8, aWdsremovedirec_1; "WdsRemoveDirectory: Unable to prepare p"...
0x180039b2f  lea     rcx, g_WdsLibLog
0x180039b36  mov     dword ptr [rsp+58h+var_38], eax
0x180039b3a  mov     edx, 3000000h
0x180039b3f  mov     ebx, eax
0x180039b41  call    LibLog
0x180039b46  mov     ecx, ebx; dwErrCode
0x180039b48  call    cs:__imp_SetLastError
0x180039b4e  mov     eax, ebp
0x180039b50  jmp     short loc_180039B5F
0x180039b52  mov     ecx, 57h ; 'W'; dwErrCode
0x180039b57  call    cs:__imp_SetLastError
0x180039b5d  xor     eax, eax
0x180039b5f  add     rsp, 38h
0x180039b63  pop     rdi
0x180039b64  pop     rsi
0x180039b65  pop     rbp
0x180039b66  pop     rbx
0x180039b67  retn
```
