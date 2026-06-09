# WdsRemoveDirectory

- ea: `0x18000b230`
- end: `0x18000b340`
- name: `WdsRemoveDirectory`
- size: `272`
- prototype: `_BOOL8 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000b348`

## callees

- `0x180008f64`
- `0x18000a0f0`
- `0x18000aa40`
- `0x18000b230`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b32f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b320`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b32f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b2df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b2ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b2ed`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b26d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000b26d`

## string_xrefs

- `0x18000b280`: `WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x`
- `0x18000b2c3`: `WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x`
- `0x18000b300`: `WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x`

## pseudocode

```c
_BOOL8 __fastcall WdsRemoveDirectory(const wchar_t *a1)
{
  wchar_t *v2; // rax
  wchar_t *v3; // rsi
  DWORD LastError; // ebx
  BOOL v5; // ebp
  HANDLE ProcessHeap; // rax
  __int64 v8; // [rsp+20h] [rbp-38h]

  if ( a1 && *a1 )
  {
    v2 = PrepareUnicodePathEx(a1, 0);
    v3 = v2;
    if ( v2 )
    {
      LastError = 0;
      if ( !SetFileAttributesW(v2, 0x80u) )
      {
        LastError = GetLastError();
        LibLog(
          (__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))&g_WdsLibLog,
          50331648,
          (__int64)L"WdsRemoveDirectory: Unable to clear attributes on [%s]; GLE = 0x%x",
          v3,
          LastError);
      }
      v5 = DeleteFileEx2((__int64)v3, 0);
      if ( !v5 )
      {
        if ( !LastError )
          LastError = GetLastError();
        LODWORD(v8) = GetLastError();
        LibLog(
          (__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))&g_WdsLibLog,
          50331648,
          (__int64)L"WdsRemoveDirectory: Unable to remove directory [%s]; GLE = 0x%x",
          v3,
          v8);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
    }
    else
    {
      v5 = 0;
      LastError = GetLastError();
      LibLog(
        (__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))&g_WdsLibLog,
        50331648,
        (__int64)L"WdsRemoveDirectory: Unable to prepare path [%s]; GLE = 0x%x",
        a1,
        LastError);
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
0x18000b230  push    rbx
0x18000b232  push    rbp
0x18000b233  push    rsi
0x18000b234  push    rdi
0x18000b235  sub     rsp, 38h
0x18000b239  mov     rdi, rcx
0x18000b23c  test    rcx, rcx
0x18000b23f  jz      loc_18000B32A
0x18000b245  xor     eax, eax
0x18000b247  cmp     ax, [rcx]
0x18000b24a  jz      loc_18000B32A
0x18000b250  xor     edx, edx
0x18000b252  call    PrepareUnicodePathEx
0x18000b257  mov     rsi, rax
0x18000b25a  test    rax, rax
0x18000b25d  jz      loc_18000B2F5
0x18000b263  mov     edx, 80h; dwFileAttributes
0x18000b268  mov     rcx, rax; lpFileName
0x18000b26b  xor     ebx, ebx
0x18000b26d  call    cs:__imp_SetFileAttributesW
0x18000b273  test    eax, eax
0x18000b275  jnz     short loc_18000B29E
0x18000b277  call    cs:__imp_GetLastError
0x18000b27d  mov     r9, rsi
0x18000b280  lea     r8, aWdsremovedirec; "WdsRemoveDirectory: Unable to clear att"...
0x18000b287  lea     rcx, g_WdsLibLog
0x18000b28e  mov     dword ptr [rsp+58h+var_38], eax
0x18000b292  mov     edx, 3000000h
0x18000b297  mov     ebx, eax
0x18000b299  call    LibLog
0x18000b29e  xor     edx, edx
0x18000b2a0  mov     rcx, rsi
0x18000b2a3  call    DeleteFileEx2
0x18000b2a8  mov     ebp, eax
0x18000b2aa  test    eax, eax
0x18000b2ac  jnz     short loc_18000B2DF
0x18000b2ae  test    ebx, ebx
0x18000b2b0  jnz     short loc_18000B2BA
0x18000b2b2  call    cs:__imp_GetLastError
0x18000b2b8  mov     ebx, eax
0x18000b2ba  call    cs:__imp_GetLastError
0x18000b2c0  mov     r9, rsi
0x18000b2c3  lea     r8, aWdsremovedirec_0; "WdsRemoveDirectory: Unable to remove di"...
0x18000b2ca  lea     rcx, g_WdsLibLog
0x18000b2d1  mov     dword ptr [rsp+58h+var_38], eax
0x18000b2d5  mov     edx, 3000000h
0x18000b2da  call    LibLog
0x18000b2df  call    cs:__imp_GetProcessHeap
0x18000b2e5  mov     r8, rsi; lpMem
0x18000b2e8  xor     edx, edx; dwFlags
0x18000b2ea  mov     rcx, rax; hHeap
0x18000b2ed  call    cs:__imp_HeapFree
0x18000b2f3  jmp     short loc_18000B31E
0x18000b2f5  xor     ebp, ebp
0x18000b2f7  call    cs:__imp_GetLastError
0x18000b2fd  mov     r9, rdi
0x18000b300  lea     r8, aWdsremovedirec_1; "WdsRemoveDirectory: Unable to prepare p"...
0x18000b307  lea     rcx, g_WdsLibLog
0x18000b30e  mov     dword ptr [rsp+58h+var_38], eax
0x18000b312  mov     edx, 3000000h
0x18000b317  mov     ebx, eax
0x18000b319  call    LibLog
0x18000b31e  mov     ecx, ebx; dwErrCode
0x18000b320  call    cs:__imp_SetLastError
0x18000b326  mov     eax, ebp
0x18000b328  jmp     short loc_18000B337
0x18000b32a  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b32f  call    cs:__imp_SetLastError
0x18000b335  xor     eax, eax
0x18000b337  add     rsp, 38h
0x18000b33b  pop     rdi
0x18000b33c  pop     rsi
0x18000b33d  pop     rbp
0x18000b33e  pop     rbx
0x18000b33f  retn
```
