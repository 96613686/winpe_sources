# _anonymous_namespace_::_Set_delete_flag

- ea: `0x18027689c`
- end: `0x180276913`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180276f2c`

## callees

- `0x18027689c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802768c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180276903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802768c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180276903`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1802768bc`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1802768f9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1802768bc`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1802768f9`

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
0x18027689c  push    rbx
0x18027689e  sub     rsp, 20h
0x1802768a2  mov     r9d, 4; dwBufferSize
0x1802768a8  mov     [rsp+28h+FileInformation], 3
0x1802768b0  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x1802768b5  mov     rbx, rcx
0x1802768b8  lea     edx, [r9+11h]; FileInformationClass
0x1802768bc  call    cs:__imp_SetFileInformationByHandle
0x1802768c2  test    eax, eax
0x1802768c4  jnz     short loc_18027690B
0x1802768c6  call    cs:__imp_GetLastError
0x1802768cc  mov     ecx, eax
0x1802768ce  sub     ecx, 1
0x1802768d1  jz      short loc_1802768E2
0x1802768d3  sub     ecx, 4
0x1802768d6  jz      short loc_18027690D
0x1802768d8  sub     ecx, 2Dh ; '-'
0x1802768db  jz      short loc_1802768E2
0x1802768dd  cmp     ecx, 25h ; '%'
0x1802768e0  jnz     short loc_18027690D
0x1802768e2  mov     r9d, 1; dwBufferSize
0x1802768e8  mov     [rsp+28h+arg_8], 1
0x1802768ed  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x1802768f2  mov     rcx, rbx; hFile
0x1802768f5  lea     edx, [r9+3]; FileInformationClass
0x1802768f9  call    cs:__imp_SetFileInformationByHandle
0x1802768ff  test    eax, eax
0x180276901  jnz     short loc_18027690B
0x180276903  call    cs:__imp_GetLastError
0x180276909  jmp     short loc_18027690D
0x18027690b  xor     eax, eax
0x18027690d  add     rsp, 20h
0x180276911  pop     rbx
0x180276912  retn
```
