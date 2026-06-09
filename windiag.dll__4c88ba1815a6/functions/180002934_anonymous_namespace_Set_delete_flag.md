# _anonymous_namespace_::_Set_delete_flag

- ea: `0x180002934`
- end: `0x1800029ab`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002fdc`

## callees

- `0x180002934`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000295e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000299b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000295e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000299b`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180002954`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180002991`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180002954`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180002991`

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
0x180002934  push    rbx
0x180002936  sub     rsp, 20h
0x18000293a  mov     r9d, 4; dwBufferSize
0x180002940  mov     [rsp+28h+FileInformation], 3
0x180002948  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x18000294d  mov     rbx, rcx
0x180002950  lea     edx, [r9+11h]; FileInformationClass
0x180002954  call    cs:__imp_SetFileInformationByHandle
0x18000295a  test    eax, eax
0x18000295c  jnz     short loc_1800029A3
0x18000295e  call    cs:__imp_GetLastError
0x180002964  mov     ecx, eax
0x180002966  sub     ecx, 1
0x180002969  jz      short loc_18000297A
0x18000296b  sub     ecx, 4
0x18000296e  jz      short loc_1800029A5
0x180002970  sub     ecx, 2Dh ; '-'
0x180002973  jz      short loc_18000297A
0x180002975  cmp     ecx, 25h ; '%'
0x180002978  jnz     short loc_1800029A5
0x18000297a  mov     r9d, 1; dwBufferSize
0x180002980  mov     [rsp+28h+arg_8], 1
0x180002985  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x18000298a  mov     rcx, rbx; hFile
0x18000298d  lea     edx, [r9+3]; FileInformationClass
0x180002991  call    cs:__imp_SetFileInformationByHandle
0x180002997  test    eax, eax
0x180002999  jnz     short loc_1800029A3
0x18000299b  call    cs:__imp_GetLastError
0x1800029a1  jmp     short loc_1800029A5
0x1800029a3  xor     eax, eax
0x1800029a5  add     rsp, 20h
0x1800029a9  pop     rbx
0x1800029aa  retn
```
