# DeletePathEx

- ea: `0x18003abd0`
- end: `0x18003af1a`
- name: `DeletePathEx`
- size: `842`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x180004b4c`
- `0x180007f78`

## callees

- `0x18003924c`
- `0x180039394`
- `0x18003aa98`
- `0x18003abd0`
- `0x18003bf9c`
- `0x18003c048`
- `0x18003c0ec`
- `0x18003ded4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ad32`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003ad32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ae95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aeae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aec7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ae95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aeae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aec7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ad80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ad94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ada8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aea3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aebc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aed5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ad80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ad94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ada8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aea3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aebc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003aed5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003adf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aefd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003adf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aefd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003acf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003acf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae02`

## string_xrefs

- `0x18003ac4b`: `SeBackupPrivilege`
- `0x18003adc2`: `SeBackupPrivilege`
- `0x18003ac6f`: `SeRestorePrivilege`
- `0x18003ade3`: `SeRestorePrivilege`
- `0x18003aee0`: `DeletePath: Cannot delete <null>.`
- `0x18003ae55`: `DeletePath:   Long path [%s]`
- `0x18003ae39`: `DeletePath:   Full path [%s]`
- `0x18003ae0d`: `DeletePath: Failed to get desired paths for [%s] (GLE = 0x%x)`
- `0x18003ac22`: `DeletePath: [%s] doesn't exist as a directory; nothing to delete.`
- `0x18003ad53`: `DeletePath: Failed to obliterate [%s] after %u tries; GLE = 0x%x`
- `0x18003ad15`: `DeletePath: Failed to obliterate [%s] (GLE = 0x%x); retrying...`
- `0x18003acc2`: `DeletePath: Attempting to obliterate [%s] (final path [%s]).`
- `0x18003ae74`: `DeletePath:   Final path [%s]`

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
  if ( !(unsigned int)DirectoryExists() )
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
0x18003abd0  mov     rax, rsp
0x18003abd3  mov     [rax+8], rbx
0x18003abd7  mov     [rax+20h], r9
0x18003abdb  mov     [rax+18h], r8
0x18003abdf  mov     [rax+10h], edx
0x18003abe2  push    rbp
0x18003abe3  push    rsi
0x18003abe4  push    rdi
0x18003abe5  push    r12
0x18003abe7  push    r13
0x18003abe9  push    r14
0x18003abeb  push    r15
0x18003abed  sub     rsp, 30h
0x18003abf1  mov     dword ptr [rax+10h], 0
0x18003abf8  mov     rbx, rcx
0x18003abfb  mov     dword ptr [rax+20h], 0
0x18003ac02  test    rcx, rcx
0x18003ac05  jz      loc_18003AEE0
0x18003ac0b  xor     eax, eax
0x18003ac0d  cmp     ax, [rcx]
0x18003ac10  jz      loc_18003AEE0
0x18003ac16  call    DirectoryExists
0x18003ac1b  test    eax, eax
0x18003ac1d  jnz     short loc_18003AC44
0x18003ac1f  mov     r9, rbx
0x18003ac22  lea     r8, aDeletepathSDoe; "DeletePath: [%s] doesn't exist as a dir"...
0x18003ac29  mov     edx, 2000000h
0x18003ac2e  lea     rcx, g_WdsLibLog
0x18003ac35  call    LibLog
0x18003ac3a  mov     ecx, 3
0x18003ac3f  jmp     loc_18003AEFD
0x18003ac44  xor     ebp, ebp
0x18003ac46  lea     r8, [rsp+68h+arg_8]
0x18003ac4b  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18003ac52  xor     esi, esi
0x18003ac54  lea     edi, [rbp+1]
0x18003ac57  mov     edx, edi
0x18003ac59  call    EnablePrivilegeEx
0x18003ac5e  lea     r8, [rsp+68h+arg_18]
0x18003ac66  mov     [rsp+68h+arg_10], eax
0x18003ac6d  mov     edx, edi
0x18003ac6f  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18003ac76  call    EnablePrivilegeEx
0x18003ac7b  mov     rcx, rbx; lpFileName
0x18003ac7e  mov     r13d, eax
0x18003ac81  call    FormFullPathName
0x18003ac86  mov     r15, rax
0x18003ac89  test    rax, rax
0x18003ac8c  jz      loc_18003AE02
0x18003ac92  mov     rcx, rax
0x18003ac95  call    FormLongPathName
0x18003ac9a  mov     rbp, rax
0x18003ac9d  test    rax, rax
0x18003aca0  jz      loc_18003AE02
0x18003aca6  mov     rcx, rax
0x18003aca9  call    FormFinalPathNameEx
0x18003acae  mov     rsi, rax
0x18003acb1  test    rax, rax
0x18003acb4  jz      loc_18003AE02
0x18003acba  mov     r9, rbx
0x18003acbd  mov     [rsp+68h+var_48], rax
0x18003acc2  lea     r8, aDeletepathAtte; "DeletePath: Attempting to obliterate [%"...
0x18003acc9  mov     edx, 4000000h
0x18003acce  lea     rcx, g_WdsLibLog
0x18003acd5  xor     r14d, r14d
0x18003acd8  xor     edi, edi
0x18003acda  call    LibLog
0x18003acdf  mov     rcx, rsi
0x18003ace2  call    DeletePathEngine
0x18003ace7  mov     r12d, eax
0x18003acea  test    eax, eax
0x18003acec  jnz     loc_18003AD72
0x18003acf2  call    cs:__imp_GetLastError
0x18003acf8  mov     r14d, eax
0x18003acfb  cmp     eax, 4C7h
0x18003ad00  jz      short loc_18003AD4E
0x18003ad02  cmp     eax, 800704C7h
0x18003ad07  jz      short loc_18003AD49
0x18003ad09  cmp     edi, 3
0x18003ad0c  jnb     short loc_18003AD49
0x18003ad0e  mov     r9, rsi
0x18003ad11  mov     dword ptr [rsp+68h+var_48], eax
0x18003ad15  lea     r8, aDeletepathFail_1; "DeletePath: Failed to obliterate [%s] ("...
0x18003ad1c  mov     edx, 4000000h
0x18003ad21  lea     rcx, g_WdsLibLog
0x18003ad28  call    LibLog
0x18003ad2d  mov     ecx, 3E8h; dwMilliseconds
0x18003ad32  call    cs:__imp_Sleep
0x18003ad38  mov     rcx, rsi
0x18003ad3b  inc     edi
0x18003ad3d  call    DeletePathEngine
0x18003ad42  mov     r12d, eax
0x18003ad45  test    eax, eax
0x18003ad47  jz      short loc_18003ACF2
0x18003ad49  test    r12d, r12d
0x18003ad4c  jnz     short loc_18003AD72
0x18003ad4e  mov     [rsp+68h+var_40], r14d
0x18003ad53  lea     r8, aDeletepathFail; "DeletePath: Failed to obliterate [%s] a"...
0x18003ad5a  mov     r9, rbx
0x18003ad5d  mov     dword ptr [rsp+68h+var_48], edi
0x18003ad61  mov     edx, 2000000h
0x18003ad66  lea     rcx, g_WdsLibLog
0x18003ad6d  call    LibLog
0x18003ad72  call    cs:__imp_GetProcessHeap
0x18003ad78  mov     r8, rsi; lpMem
0x18003ad7b  xor     edx, edx; dwFlags
0x18003ad7d  mov     rcx, rax; hHeap
0x18003ad80  call    cs:__imp_HeapFree
0x18003ad86  call    cs:__imp_GetProcessHeap
0x18003ad8c  mov     r8, rbp; lpMem
0x18003ad8f  xor     edx, edx; dwFlags
0x18003ad91  mov     rcx, rax; hHeap
0x18003ad94  call    cs:__imp_HeapFree
0x18003ad9a  call    cs:__imp_GetProcessHeap
0x18003ada0  mov     r8, r15; lpMem
0x18003ada3  xor     edx, edx; dwFlags
0x18003ada5  mov     rcx, rax; hHeap
0x18003ada8  call    cs:__imp_HeapFree
0x18003adae  cmp     [rsp+68h+arg_10], 1
0x18003adb6  jnz     short loc_18003ADD0
0x18003adb8  cmp     [rsp+68h+arg_8], 0
0x18003adbd  jnz     short loc_18003ADD0
0x18003adbf  xor     r8d, r8d
0x18003adc2  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x18003adc9  xor     edx, edx
0x18003adcb  call    EnablePrivilegeEx
0x18003add0  cmp     r13d, 1
0x18003add4  jnz     short loc_18003ADF1
0x18003add6  cmp     [rsp+68h+arg_18], 0
0x18003adde  jnz     short loc_18003ADF1
0x18003ade0  xor     r8d, r8d
0x18003ade3  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x18003adea  xor     edx, edx
0x18003adec  call    EnablePrivilegeEx
0x18003adf1  mov     ecx, r14d; dwErrCode
0x18003adf4  call    cs:__imp_SetLastError
0x18003adfa  mov     eax, r12d
0x18003adfd  jmp     loc_18003AF05
0x18003ae02  call    cs:__imp_GetLastError
0x18003ae08  mov     edi, 2000000h
0x18003ae0d  lea     r8, aDeletepathFail_0; "DeletePath: Failed to get desired paths"...
0x18003ae14  lea     rcx, g_WdsLibLog
0x18003ae1b  mov     dword ptr [rsp+68h+var_48], eax
0x18003ae1f  mov     edx, edi
0x18003ae21  mov     r9, rbx
0x18003ae24  mov     r14d, eax
0x18003ae27  call    LibLog
0x18003ae2c  lea     rbx, aUnavailable; "<unavailable>"
0x18003ae33  test    r15, r15
0x18003ae36  mov     r9, rbx
0x18003ae39  lea     r8, aDeletepathFull; "DeletePath:   Full path [%s]"
0x18003ae40  cmovnz  r9, r15
0x18003ae44  lea     rcx, g_WdsLibLog
0x18003ae4b  mov     edx, edi
0x18003ae4d  call    LibLog
0x18003ae52  test    rbp, rbp
0x18003ae55  lea     r8, aDeletepathLong; "DeletePath:   Long path [%s]"
0x18003ae5c  mov     r9, rbx
0x18003ae5f  lea     rcx, g_WdsLibLog
0x18003ae66  cmovnz  r9, rbp
0x18003ae6a  mov     edx, edi
0x18003ae6c  call    LibLog
0x18003ae71  test    rsi, rsi
0x18003ae74  lea     r8, aDeletepathFina; "DeletePath:   Final path [%s]"
0x18003ae7b  mov     edx, edi
0x18003ae7d  lea     rcx, g_WdsLibLog
0x18003ae84  cmovnz  rbx, rsi
0x18003ae88  mov     r9, rbx
0x18003ae8b  call    LibLog
0x18003ae90  test    rsi, rsi
0x18003ae93  jz      short loc_18003AEA9
0x18003ae95  call    cs:__imp_GetProcessHeap
0x18003ae9b  mov     r8, rsi; lpMem
0x18003ae9e  xor     edx, edx; dwFlags
0x18003aea0  mov     rcx, rax; hHeap
0x18003aea3  call    cs:__imp_HeapFree
0x18003aea9  test    rbp, rbp
0x18003aeac  jz      short loc_18003AEC2
0x18003aeae  call    cs:__imp_GetProcessHeap
0x18003aeb4  mov     r8, rbp; lpMem
0x18003aeb7  xor     edx, edx; dwFlags
0x18003aeb9  mov     rcx, rax; hHeap
0x18003aebc  call    cs:__imp_HeapFree
0x18003aec2  test    r15, r15
0x18003aec5  jz      short loc_18003AEDB
0x18003aec7  call    cs:__imp_GetProcessHeap
0x18003aecd  mov     r8, r15; lpMem
0x18003aed0  xor     edx, edx; dwFlags
0x18003aed2  mov     rcx, rax; hHeap
0x18003aed5  call    cs:__imp_HeapFree
0x18003aedb  mov     ecx, r14d
0x18003aede  jmp     short loc_18003AEFD
0x18003aee0  lea     r8, aDeletepathCann; "DeletePath: Cannot delete <null>."
0x18003aee7  mov     edx, 2000000h
0x18003aeec  lea     rcx, g_WdsLibLog
0x18003aef3  call    LibLog
0x18003aef8  mov     ecx, 57h ; 'W'; dwErrCode
0x18003aefd  call    cs:__imp_SetLastError
0x18003af03  xor     eax, eax
0x18003af05  mov     rbx, [rsp+68h+arg_0]
0x18003af0a  add     rsp, 30h
0x18003af0e  pop     r15
0x18003af10  pop     r14
0x18003af12  pop     r13
0x18003af14  pop     r12
0x18003af16  pop     rdi
0x18003af17  pop     rsi
0x18003af18  pop     rbp
0x18003af19  retn
```
