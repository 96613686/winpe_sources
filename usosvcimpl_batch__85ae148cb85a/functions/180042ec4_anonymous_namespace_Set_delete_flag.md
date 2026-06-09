# _anonymous_namespace_::_Set_delete_flag

- ea: `0x180042ec4`
- end: `0x180042f3b`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180043090`

## callees

- `0x180042ec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042f2b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180042ee4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180042f21`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180042ee4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180042f21`

## pseudocode

```c
DWORD __fastcall anonymous_namespace_::_Set_delete_flag(HANDLE hFile)
{
  DWORD result; // eax
  char v3; // [rsp+38h] [rbp+10h] BYREF
  int FileInformation; // [rsp+40h] [rbp+18h] BYREF

  FileInformation = 3;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    return 0;
  result = GetLastError();
  if ( result == 1 || result != 5 && (result == 50 || result == 87) )
  {
    v3 = 1;
    if ( !SetFileInformationByHandle(hFile, FileDispositionInfo, &v3, 1u) )
      return GetLastError();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180042ec4  push    rbx
0x180042ec6  sub     rsp, 20h
0x180042eca  mov     r9d, 4; dwBufferSize
0x180042ed0  mov     [rsp+28h+FileInformation], 3
0x180042ed8  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x180042edd  mov     rbx, rcx
0x180042ee0  lea     edx, [r9+11h]; FileInformationClass
0x180042ee4  call    cs:__imp_SetFileInformationByHandle
0x180042eea  test    eax, eax
0x180042eec  jnz     short loc_180042F33
0x180042eee  call    cs:__imp_GetLastError
0x180042ef4  mov     ecx, eax
0x180042ef6  sub     ecx, 1
0x180042ef9  jz      short loc_180042F0A
0x180042efb  sub     ecx, 4
0x180042efe  jz      short loc_180042F35
0x180042f00  sub     ecx, 2Dh ; '-'
0x180042f03  jz      short loc_180042F0A
0x180042f05  cmp     ecx, 25h ; '%'
0x180042f08  jnz     short loc_180042F35
0x180042f0a  mov     r9d, 1; dwBufferSize
0x180042f10  mov     [rsp+28h+arg_8], 1
0x180042f15  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x180042f1a  mov     rcx, rbx; hFile
0x180042f1d  lea     edx, [r9+3]; FileInformationClass
0x180042f21  call    cs:__imp_SetFileInformationByHandle
0x180042f27  test    eax, eax
0x180042f29  jnz     short loc_180042F33
0x180042f2b  call    cs:__imp_GetLastError
0x180042f31  jmp     short loc_180042F35
0x180042f33  xor     eax, eax
0x180042f35  add     rsp, 20h
0x180042f39  pop     rbx
0x180042f3a  retn
```
