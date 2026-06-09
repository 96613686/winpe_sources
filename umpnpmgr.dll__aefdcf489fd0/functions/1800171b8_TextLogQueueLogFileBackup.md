# TextLogQueueLogFileBackup

- ea: `0x1800171b8`
- end: `0x180017255`
- name: `TextLogQueueLogFileBackup`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`

## callees

- `0x180016dd4`
- `0x1800171b8`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017222`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017207`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800171fd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800171fd`

## pseudocode

```c
__int64 __fastcall TextLogQueueLogFileBackup(LPCWSTR lpExistingFileName)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx
  WCHAR NewFileName[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = 0;
  LastError = 0;
  if ( !(unsigned int)TextLogGenerateBackupLogFileName(lpExistingFileName, NewFileName)
    || !MoveFileExW(lpExistingFileName, NewFileName, 5u) )
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  LOBYTE(v2) = LastError == 0;
  return v2;
}

```

## disassembly

```asm
0x1800171b8  mov     [rsp+arg_8], rbx
0x1800171bd  mov     [rsp+arg_10], rsi
0x1800171c2  push    rdi
0x1800171c3  sub     rsp, 250h
0x1800171ca  mov     rax, cs:__security_cookie
0x1800171d1  xor     rax, rsp
0x1800171d4  mov     [rsp+258h+var_18], rax
0x1800171dc  mov     rsi, rcx
0x1800171df  xor     edi, edi
0x1800171e1  mov     ebx, edi
0x1800171e3  lea     rdx, [rsp+258h+NewFileName]; pszDest
0x1800171e8  call    TextLogGenerateBackupLogFileName
0x1800171ed  test    eax, eax
0x1800171ef  jz      short loc_180017207
0x1800171f1  lea     r8d, [rdi+5]; dwFlags
0x1800171f5  lea     rdx, [rsp+258h+NewFileName]; lpNewFileName
0x1800171fa  mov     rcx, rsi; lpExistingFileName
0x1800171fd  call    cs:__imp_MoveFileExW
0x180017203  test    eax, eax
0x180017205  jnz     short loc_180017213
0x180017207  call    cs:__imp_GetLastError
0x18001720d  mov     [rsp+258h+var_238], eax
0x180017211  mov     ebx, eax
0x180017213  jmp     short loc_180017220
0x180017215  mov     ebx, 54Fh
0x18001721a  mov     [rsp+258h+var_238], ebx
0x18001721e  xor     edi, edi
0x180017220  mov     ecx, ebx; dwErrCode
0x180017222  call    cs:__imp_SetLastError
0x180017228  test    ebx, ebx
0x18001722a  setz    dil
0x18001722e  mov     eax, edi
0x180017230  mov     rcx, [rsp+258h+var_18]
0x180017238  xor     rcx, rsp; StackCookie
0x18001723b  call    __security_check_cookie
0x180017240  lea     r11, [rsp+258h+var_8]
0x180017248  mov     rbx, [r11+18h]
0x18001724c  mov     rsi, [r11+20h]
0x180017250  mov     rsp, r11
0x180017253  pop     rdi
0x180017254  retn
```
