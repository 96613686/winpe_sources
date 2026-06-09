# FormFinalPathNameEx

- ea: `0x180009c84`
- end: `0x180009d28`
- name: `FormFinalPathNameEx`
- size: `164`
- prototype: `WCHAR *__fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18000b720`

## callees

- `0x180009b9c`
- `0x180009c84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d00`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009cbd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009cbd`

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
0x180009c84  mov     [rsp+arg_0], rbx
0x180009c89  mov     [rsp+arg_8], rsi
0x180009c8e  push    rdi
0x180009c8f  sub     rsp, 40h
0x180009c93  test    rcx, rcx
0x180009c96  jz      short loc_180009D0B
0x180009c98  xor     eax, eax
0x180009c9a  cmp     ax, [rcx]
0x180009c9d  jz      short loc_180009D0B
0x180009c9f  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x180009ca4  lea     r8d, [rax+7]; dwShareMode
0x180009ca8  mov     [rsp+48h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180009cb0  xor     r9d, r9d; lpSecurityAttributes
0x180009cb3  xor     edx, edx; dwDesiredAccess
0x180009cb5  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180009cbd  call    cs:__imp_CreateFileW
0x180009cc3  mov     rsi, rax
0x180009cc6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009cca  jz      short loc_180009CF4
0x180009ccc  xor     ebx, ebx
0x180009cce  mov     rcx, rax; hFile
0x180009cd1  lea     edx, [rbx+1]
0x180009cd4  call    FormFinalPathNameByHandle
0x180009cd9  mov     rdi, rax
0x180009cdc  test    rax, rax
0x180009cdf  jnz     short loc_180009CE9
0x180009ce1  call    cs:__imp_GetLastError
0x180009ce7  mov     ebx, eax
0x180009ce9  mov     rcx, rsi; hObject
0x180009cec  call    cs:__imp_CloseHandle
0x180009cf2  jmp     short loc_180009CFE
0x180009cf4  xor     edi, edi
0x180009cf6  call    cs:__imp_GetLastError
0x180009cfc  mov     ebx, eax
0x180009cfe  mov     ecx, ebx; dwErrCode
0x180009d00  call    cs:__imp_SetLastError
0x180009d06  mov     rax, rdi
0x180009d09  jmp     short loc_180009D18
0x180009d0b  mov     ecx, 57h ; 'W'; dwErrCode
0x180009d10  call    cs:__imp_SetLastError
0x180009d16  xor     eax, eax
0x180009d18  mov     rbx, [rsp+48h+arg_0]
0x180009d1d  mov     rsi, [rsp+48h+arg_8]
0x180009d22  add     rsp, 40h
0x180009d26  pop     rdi
0x180009d27  retn
```
