# _anonymous_namespace_::_Set_delete_flag

- ea: `0x180079e3c`
- end: `0x180079eb3`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18007a150`

## callees

- `0x180079e3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079ea3`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180079e5c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180079e99`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180079e5c`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180079e99`

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
0x180079e3c  push    rbx
0x180079e3e  sub     rsp, 20h
0x180079e42  mov     r9d, 4; dwBufferSize
0x180079e48  mov     [rsp+28h+FileInformation], 3
0x180079e50  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x180079e55  mov     rbx, rcx
0x180079e58  lea     edx, [r9+11h]; FileInformationClass
0x180079e5c  call    cs:__imp_SetFileInformationByHandle
0x180079e62  test    eax, eax
0x180079e64  jnz     short loc_180079EAB
0x180079e66  call    cs:__imp_GetLastError
0x180079e6c  mov     ecx, eax
0x180079e6e  sub     ecx, 1
0x180079e71  jz      short loc_180079E82
0x180079e73  sub     ecx, 4
0x180079e76  jz      short loc_180079EAD
0x180079e78  sub     ecx, 2Dh ; '-'
0x180079e7b  jz      short loc_180079E82
0x180079e7d  cmp     ecx, 25h ; '%'
0x180079e80  jnz     short loc_180079EAD
0x180079e82  mov     r9d, 1; dwBufferSize
0x180079e88  mov     [rsp+28h+arg_8], 1
0x180079e8d  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x180079e92  mov     rcx, rbx; hFile
0x180079e95  lea     edx, [r9+3]; FileInformationClass
0x180079e99  call    cs:__imp_SetFileInformationByHandle
0x180079e9f  test    eax, eax
0x180079ea1  jnz     short loc_180079EAB
0x180079ea3  call    cs:__imp_GetLastError
0x180079ea9  jmp     short loc_180079EAD
0x180079eab  xor     eax, eax
0x180079ead  add     rsp, 20h
0x180079eb1  pop     rbx
0x180079eb2  retn
```
