# FormFinalPathNameEx

- ea: `0x18003bf9c`
- end: `0x18003c040`
- name: `FormFinalPathNameEx`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18003abd0`

## callees

- `0x18003beb4`
- `0x18003bf9c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bfd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003bfd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c018`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c028`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c018`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c00e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c00e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c004`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c004`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameEx(const WCHAR *a1)
{
  char *FileW; // rax
  char *v2; // rsi
  DWORD LastError; // ebx
  WCHAR *v4; // rdi

  if ( a1 && *a1 )
  {
    FileW = (char *)CreateFileW(a1, 0, 7u, 0, 3u, 0x2200000u, 0);
    v2 = FileW;
    if ( FileW == (char *)-1LL )
    {
      v4 = 0;
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
      v4 = FormFinalPathNameByHandle(FileW, 1);
      if ( !v4 )
        LastError = GetLastError();
      CloseHandle(v2);
    }
    SetLastError(LastError);
    return v4;
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
0x18003bf9c  mov     [rsp+arg_0], rbx
0x18003bfa1  mov     [rsp+arg_8], rsi
0x18003bfa6  push    rdi
0x18003bfa7  sub     rsp, 40h
0x18003bfab  test    rcx, rcx
0x18003bfae  jz      short loc_18003C023
0x18003bfb0  xor     eax, eax
0x18003bfb2  cmp     ax, [rcx]
0x18003bfb5  jz      short loc_18003C023
0x18003bfb7  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x18003bfbc  lea     r8d, [rax+7]; dwShareMode
0x18003bfc0  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003bfc8  xor     r9d, r9d; lpSecurityAttributes
0x18003bfcb  xor     edx, edx; dwDesiredAccess
0x18003bfcd  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18003bfd5  call    cs:__imp_CreateFileW
0x18003bfdb  mov     rsi, rax
0x18003bfde  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003bfe2  jz      short loc_18003C00C
0x18003bfe4  xor     ebx, ebx
0x18003bfe6  mov     rcx, rax; hFile
0x18003bfe9  lea     edx, [rbx+1]
0x18003bfec  call    FormFinalPathNameByHandle
0x18003bff1  mov     rdi, rax
0x18003bff4  test    rax, rax
0x18003bff7  jnz     short loc_18003C001
0x18003bff9  call    cs:__imp_GetLastError
0x18003bfff  mov     ebx, eax
0x18003c001  mov     rcx, rsi; hObject
0x18003c004  call    cs:__imp_CloseHandle
0x18003c00a  jmp     short loc_18003C016
0x18003c00c  xor     edi, edi
0x18003c00e  call    cs:__imp_GetLastError
0x18003c014  mov     ebx, eax
0x18003c016  mov     ecx, ebx; dwErrCode
0x18003c018  call    cs:__imp_SetLastError
0x18003c01e  mov     rax, rdi
0x18003c021  jmp     short loc_18003C030
0x18003c023  mov     ecx, 57h ; 'W'; dwErrCode
0x18003c028  call    cs:__imp_SetLastError
0x18003c02e  xor     eax, eax
0x18003c030  mov     rbx, [rsp+48h+arg_0]
0x18003c035  mov     rsi, [rsp+48h+arg_8]
0x18003c03a  add     rsp, 40h
0x18003c03e  pop     rdi
0x18003c03f  retn
```
