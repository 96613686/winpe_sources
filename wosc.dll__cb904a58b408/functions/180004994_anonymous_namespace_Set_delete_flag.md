# _anonymous_namespace_::_Set_delete_flag

- ea: `0x180004994`
- end: `0x180004a0b`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004f54`

## callees

- `0x180004994`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049fb`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800049b4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800049f1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800049b4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800049f1`

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
0x180004994  push    rbx
0x180004996  sub     rsp, 20h
0x18000499a  mov     r9d, 4; dwBufferSize
0x1800049a0  mov     [rsp+28h+FileInformation], 3
0x1800049a8  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x1800049ad  mov     rbx, rcx
0x1800049b0  lea     edx, [r9+11h]; FileInformationClass
0x1800049b4  call    cs:__imp_SetFileInformationByHandle
0x1800049ba  test    eax, eax
0x1800049bc  jnz     short loc_180004A03
0x1800049be  call    cs:__imp_GetLastError
0x1800049c4  mov     ecx, eax
0x1800049c6  sub     ecx, 1
0x1800049c9  jz      short loc_1800049DA
0x1800049cb  sub     ecx, 4
0x1800049ce  jz      short loc_180004A05
0x1800049d0  sub     ecx, 2Dh ; '-'
0x1800049d3  jz      short loc_1800049DA
0x1800049d5  cmp     ecx, 25h ; '%'
0x1800049d8  jnz     short loc_180004A05
0x1800049da  mov     r9d, 1; dwBufferSize
0x1800049e0  mov     [rsp+28h+arg_8], 1
0x1800049e5  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x1800049ea  mov     rcx, rbx; hFile
0x1800049ed  lea     edx, [r9+3]; FileInformationClass
0x1800049f1  call    cs:__imp_SetFileInformationByHandle
0x1800049f7  test    eax, eax
0x1800049f9  jnz     short loc_180004A03
0x1800049fb  call    cs:__imp_GetLastError
0x180004a01  jmp     short loc_180004A05
0x180004a03  xor     eax, eax
0x180004a05  add     rsp, 20h
0x180004a09  pop     rbx
0x180004a0a  retn
```
