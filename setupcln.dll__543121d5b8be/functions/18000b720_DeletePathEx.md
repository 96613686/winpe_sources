# DeletePathEx

- ea: `0x18000b720`
- end: `0x18000ba6a`
- name: `DeletePathEx`
- size: `842`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x180006868`

## callees

- `0x180008f64`
- `0x180009c84`
- `0x180009d30`
- `0x180009dd4`
- `0x18000b044`
- `0x18000b5f8`
- `0x18000b720`
- `0x18000c254`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b944`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b944`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ba4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b952`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba25`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b882`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b882`

## string_xrefs

- `0x18000b79b`: `SeBackupPrivilege`
- `0x18000b912`: `SeBackupPrivilege`
- `0x18000b7bf`: `SeRestorePrivilege`
- `0x18000b933`: `SeRestorePrivilege`
- `0x18000ba30`: `DeletePath: Cannot delete <null>.`
- `0x18000b772`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x18000b95d`: `DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)`
- `0x18000b989`: `DeletePath:   Full path [%s]`
- `0x18000b9a5`: `DeletePath:   Long path [%s]`
- `0x18000b9c4`: `DeletePath:   Final path [%s]`
- `0x18000b812`: `DeletePath: Attempting to obliterate [%s] (final path [%s]).`
- `0x18000b865`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`
- `0x18000b8a3`: `DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall DeletePathEx(LPCWSTR lpFileName)
{
  DWORD v2; // ecx
  wchar_t *v3; // rbp
  wchar_t *v4; // rsi
  int v5; // r13d
  __int64 v6; // rax
  wchar_t *v7; // r15
  __int64 v8; // rax
  __int64 v9; // rax
  DWORD v10; // r14d
  unsigned int v11; // edi
  unsigned int v12; // r12d
  DWORD v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  DWORD LastError; // r14d
  const wchar_t *v19; // rbx
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  HANDLE ProcessHeap; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  __int64 v25; // [rsp+20h] [rbp-48h]
  int v26; // [rsp+80h] [rbp+18h]

  if ( !lpFileName || !*lpFileName )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: Cannot delete <null>.");
    v2 = 87;
    goto LABEL_34;
  }
  if ( !(unsigned int)DirectoryExists(lpFileName) )
  {
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath: [%s] doesn't exist as a directory; nothing to delete.", lpFileName);
    v2 = 3;
LABEL_34:
    SetLastError(v2);
    return 0;
  }
  v3 = 0;
  v4 = 0;
  v26 = EnablePrivilegeEx(L"SeBackupPrivilege");
  v5 = EnablePrivilegeEx(L"SeRestorePrivilege");
  v6 = FormFullPathName(lpFileName);
  v7 = (wchar_t *)v6;
  if ( !v6
    || (v8 = FormLongPathName(v6), (v3 = (wchar_t *)v8) == 0)
    || (v9 = FormFinalPathNameEx(v8), (v4 = (wchar_t *)v9) == 0) )
  {
    LastError = GetLastError();
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)",
      lpFileName,
      LastError);
    v19 = L"<unavailable>";
    v20 = L"<unavailable>";
    if ( v7 )
      v20 = v7;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Full path [%s]", v20);
    v21 = L"<unavailable>";
    if ( v3 )
      v21 = v3;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Long path [%s]", v21);
    if ( v4 )
      v19 = v4;
    LibLog(&g_WdsLibLog, 0x2000000, L"DeletePath:   Final path [%s]", v19);
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    if ( v3 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v3);
    }
    if ( v7 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v7);
    }
    v2 = LastError;
    goto LABEL_34;
  }
  v10 = 0;
  v11 = 0;
  LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Attempting to obliterate [%s] (final path [%s]).", lpFileName, v9);
  v12 = DeletePathEngine(v4);
  if ( !v12 )
  {
    while ( 1 )
    {
      v13 = GetLastError();
      v10 = v13;
      if ( v13 == 1223 )
        break;
      if ( v13 != -2147023673 && v11 < 3 )
      {
        LODWORD(v25) = v13;
        LibLog(&g_WdsLibLog, 0x4000000, L"DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...", v4, v25);
        Sleep(0x3E8u);
        ++v11;
        v12 = DeletePathEngine(v4);
        if ( !v12 )
          continue;
      }
      if ( v12 )
        goto LABEL_15;
      break;
    }
    LODWORD(v25) = v11;
    LibLog(
      &g_WdsLibLog,
      0x2000000,
      L"DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x",
      lpFileName,
      v25,
      v10);
  }
LABEL_15:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v4);
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v3);
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v7);
  if ( v26 == 1 )
    EnablePrivilegeEx(L"SeBackupPrivilege");
  if ( v5 == 1 )
    EnablePrivilegeEx(L"SeRestorePrivilege");
  SetLastError(v10);
  return v12;
}

```

## disassembly

```asm
0x18000b720  mov     rax, rsp
0x18000b723  mov     [rax+8], rbx
0x18000b727  mov     [rax+20h], r9
0x18000b72b  mov     [rax+18h], r8
0x18000b72f  mov     [rax+10h], edx
0x18000b732  push    rbp
0x18000b733  push    rsi
0x18000b734  push    rdi
0x18000b735  push    r12
0x18000b737  push    r13
0x18000b739  push    r14
0x18000b73b  push    r15
0x18000b73d  sub     rsp, 30h
0x18000b741  mov     dword ptr [rax+10h], 0
0x18000b748  mov     rbx, rcx
0x18000b74b  mov     dword ptr [rax+20h], 0
0x18000b752  test    rcx, rcx
0x18000b755  jz      loc_18000BA30
0x18000b75b  xor     eax, eax
0x18000b75d  cmp     ax, [rcx]
0x18000b760  jz      loc_18000BA30
0x18000b766  call    DirectoryExists
0x18000b76b  test    eax, eax
0x18000b76d  jnz     short loc_18000B794
0x18000b76f  mov     r9, rbx
0x18000b772  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x18000b779  mov     edx, 2000000h
0x18000b77e  lea     rcx, g_WdsLibLog
0x18000b785  call    LibLog
0x18000b78a  mov     ecx, 3
0x18000b78f  jmp     loc_18000BA4D
0x18000b794  xor     ebp, ebp
0x18000b796  lea     r8, [rsp+68h+arg_8]
0x18000b79b  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18000b7a2  xor     esi, esi
0x18000b7a4  lea     edi, [rbp+1]
0x18000b7a7  mov     edx, edi
0x18000b7a9  call    EnablePrivilegeEx
0x18000b7ae  lea     r8, [rsp+68h+arg_18]
0x18000b7b6  mov     [rsp+68h+arg_10], eax
0x18000b7bd  mov     edx, edi
0x18000b7bf  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18000b7c6  call    EnablePrivilegeEx
0x18000b7cb  mov     rcx, rbx; lpFileName
0x18000b7ce  mov     r13d, eax
0x18000b7d1  call    FormFullPathName
0x18000b7d6  mov     r15, rax
0x18000b7d9  test    rax, rax
0x18000b7dc  jz      loc_18000B952
0x18000b7e2  mov     rcx, rax
0x18000b7e5  call    FormLongPathName
0x18000b7ea  mov     rbp, rax
0x18000b7ed  test    rax, rax
0x18000b7f0  jz      loc_18000B952
0x18000b7f6  mov     rcx, rax
0x18000b7f9  call    FormFinalPathNameEx
0x18000b7fe  mov     rsi, rax
0x18000b801  test    rax, rax
0x18000b804  jz      loc_18000B952
0x18000b80a  mov     r9, rbx
0x18000b80d  mov     [rsp+68h+var_48], rax
0x18000b812  lea     r8, aDeletepathAtte; "DeletePath: Attempting to obliterate [%"...
0x18000b819  mov     edx, 4000000h
0x18000b81e  lea     rcx, g_WdsLibLog
0x18000b825  xor     r14d, r14d
0x18000b828  xor     edi, edi
0x18000b82a  call    LibLog
0x18000b82f  mov     rcx, rsi
0x18000b832  call    DeletePathEngine
0x18000b837  mov     r12d, eax
0x18000b83a  test    eax, eax
0x18000b83c  jnz     loc_18000B8C2
0x18000b842  call    cs:__imp_GetLastError
0x18000b848  mov     r14d, eax
0x18000b84b  cmp     eax, 4C7h
0x18000b850  jz      short loc_18000B89E
0x18000b852  cmp     eax, 800704C7h
0x18000b857  jz      short loc_18000B899
0x18000b859  cmp     edi, 3
0x18000b85c  jnb     short loc_18000B899
0x18000b85e  mov     r9, rsi
0x18000b861  mov     dword ptr [rsp+68h+var_48], eax
0x18000b865  lea     r8, aDeletepathFail_1; "DeletePath: Failed to obliterate [%s] ("...
0x18000b86c  mov     edx, 4000000h
0x18000b871  lea     rcx, g_WdsLibLog
0x18000b878  call    LibLog
0x18000b87d  mov     ecx, 3E8h; dwMilliseconds
0x18000b882  call    cs:__imp_Sleep
0x18000b888  mov     rcx, rsi
0x18000b88b  inc     edi
0x18000b88d  call    DeletePathEngine
0x18000b892  mov     r12d, eax
0x18000b895  test    eax, eax
0x18000b897  jz      short loc_18000B842
0x18000b899  test    r12d, r12d
0x18000b89c  jnz     short loc_18000B8C2
0x18000b89e  mov     [rsp+68h+var_40], r14d
0x18000b8a3  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] a"...
0x18000b8aa  mov     r9, rbx
0x18000b8ad  mov     dword ptr [rsp+68h+var_48], edi
0x18000b8b1  mov     edx, 2000000h
0x18000b8b6  lea     rcx, g_WdsLibLog
0x18000b8bd  call    LibLog
0x18000b8c2  call    cs:__imp_GetProcessHeap
0x18000b8c8  mov     r8, rsi; lpMem
0x18000b8cb  xor     edx, edx; dwFlags
0x18000b8cd  mov     rcx, rax; hHeap
0x18000b8d0  call    cs:__imp_HeapFree
0x18000b8d6  call    cs:__imp_GetProcessHeap
0x18000b8dc  mov     r8, rbp; lpMem
0x18000b8df  xor     edx, edx; dwFlags
0x18000b8e1  mov     rcx, rax; hHeap
0x18000b8e4  call    cs:__imp_HeapFree
0x18000b8ea  call    cs:__imp_GetProcessHeap
0x18000b8f0  mov     r8, r15; lpMem
0x18000b8f3  xor     edx, edx; dwFlags
0x18000b8f5  mov     rcx, rax; hHeap
0x18000b8f8  call    cs:__imp_HeapFree
0x18000b8fe  cmp     [rsp+68h+arg_10], 1
0x18000b906  jnz     short loc_18000B920
0x18000b908  cmp     [rsp+68h+arg_8], 0
0x18000b90d  jnz     short loc_18000B920
0x18000b90f  xor     r8d, r8d
0x18000b912  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18000b919  xor     edx, edx
0x18000b91b  call    EnablePrivilegeEx
0x18000b920  cmp     r13d, 1
0x18000b924  jnz     short loc_18000B941
0x18000b926  cmp     [rsp+68h+arg_18], 0
0x18000b92e  jnz     short loc_18000B941
0x18000b930  xor     r8d, r8d
0x18000b933  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18000b93a  xor     edx, edx
0x18000b93c  call    EnablePrivilegeEx
0x18000b941  mov     ecx, r14d; dwErrCode
0x18000b944  call    cs:__imp_SetLastError
0x18000b94a  mov     eax, r12d
0x18000b94d  jmp     loc_18000BA55
0x18000b952  call    cs:__imp_GetLastError
0x18000b958  mov     edi, 2000000h
0x18000b95d  lea     r8, aDeletepathFail_0; "DeletePath: Failed to get desired paths"...
0x18000b964  lea     rcx, g_WdsLibLog
0x18000b96b  mov     dword ptr [rsp+68h+var_48], eax
0x18000b96f  mov     edx, edi
0x18000b971  mov     r9, rbx
0x18000b974  mov     r14d, eax
0x18000b977  call    LibLog
0x18000b97c  lea     rbx, aUnavailable; "<unavailable>"
0x18000b983  test    r15, r15
0x18000b986  mov     r9, rbx
0x18000b989  lea     r8, aDeletepathFull; "DeletePath:   Full path [%s]"
0x18000b990  cmovnz  r9, r15
0x18000b994  lea     rcx, g_WdsLibLog
0x18000b99b  mov     edx, edi
0x18000b99d  call    LibLog
0x18000b9a2  test    rbp, rbp
0x18000b9a5  lea     r8, aDeletepathLong; "DeletePath:   Long path [%s]"
0x18000b9ac  mov     r9, rbx
0x18000b9af  lea     rcx, g_WdsLibLog
0x18000b9b6  cmovnz  r9, rbp
0x18000b9ba  mov     edx, edi
0x18000b9bc  call    LibLog
0x18000b9c1  test    rsi, rsi
0x18000b9c4  lea     r8, aDeletepathFina; "DeletePath:   Final path [%s]"
0x18000b9cb  mov     edx, edi
0x18000b9cd  lea     rcx, g_WdsLibLog
0x18000b9d4  cmovnz  rbx, rsi
0x18000b9d8  mov     r9, rbx
0x18000b9db  call    LibLog
0x18000b9e0  test    rsi, rsi
0x18000b9e3  jz      short loc_18000B9F9
0x18000b9e5  call    cs:__imp_GetProcessHeap
0x18000b9eb  mov     r8, rsi; lpMem
0x18000b9ee  xor     edx, edx; dwFlags
0x18000b9f0  mov     rcx, rax; hHeap
0x18000b9f3  call    cs:__imp_HeapFree
0x18000b9f9  test    rbp, rbp
0x18000b9fc  jz      short loc_18000BA12
0x18000b9fe  call    cs:__imp_GetProcessHeap
0x18000ba04  mov     r8, rbp; lpMem
0x18000ba07  xor     edx, edx; dwFlags
0x18000ba09  mov     rcx, rax; hHeap
0x18000ba0c  call    cs:__imp_HeapFree
0x18000ba12  test    r15, r15
0x18000ba15  jz      short loc_18000BA2B
0x18000ba17  call    cs:__imp_GetProcessHeap
0x18000ba1d  mov     r8, r15; lpMem
0x18000ba20  xor     edx, edx; dwFlags
0x18000ba22  mov     rcx, rax; hHeap
0x18000ba25  call    cs:__imp_HeapFree
0x18000ba2b  mov     ecx, r14d
0x18000ba2e  jmp     short loc_18000BA4D
0x18000ba30  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x18000ba37  mov     edx, 2000000h
0x18000ba3c  lea     rcx, g_WdsLibLog
0x18000ba43  call    LibLog
0x18000ba48  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ba4d  call    cs:__imp_SetLastError
0x18000ba53  xor     eax, eax
0x18000ba55  mov     rbx, [rsp+68h+arg_0]
0x18000ba5a  add     rsp, 30h
0x18000ba5e  pop     r15
0x18000ba60  pop     r14
0x18000ba62  pop     r13
0x18000ba64  pop     r12
0x18000ba66  pop     rdi
0x18000ba67  pop     rsi
0x18000ba68  pop     rbp
0x18000ba69  retn
```
