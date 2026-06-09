# IsDirectoryUseable

- ea: `0x180008e78`
- end: `0x180008f28`
- name: `IsDirectoryUseable`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a288`
- `0x18000d1c0`

## callees

- `0x180008e78`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008eee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008eee`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180008ea0`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180008ea0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008ed9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008ed9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008eff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008eff`

## pseudocode

```c
BOOL __fastcall IsDirectoryUseable(const WCHAR *a1)
{
  HANDLE FileW; // rax
  WCHAR TempFileName[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !GetTempFileNameW(a1, L"SEQ", 0, TempFileName) )
    return 0;
  FileW = CreateFileW(TempFileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CloseHandle(FileW);
  return DeleteFileW(TempFileName);
}

```

## disassembly

```asm
0x180008e78  sub     rsp, 268h
0x180008e7f  mov     rax, cs:__security_cookie
0x180008e86  xor     rax, rsp
0x180008e89  mov     [rsp+268h+var_18], rax
0x180008e91  lea     r9, [rsp+268h+TempFileName]; lpTempFileName
0x180008e96  xor     r8d, r8d; uUnique
0x180008e99  lea     rdx, PrefixString; "SEQ"
0x180008ea0  call    cs:__imp_GetTempFileNameW
0x180008ea7  nop     dword ptr [rax+rax+00h]
0x180008eac  test    eax, eax
0x180008eae  jz      short loc_180008F0D
0x180008eb0  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x180008eb9  lea     rcx, [rsp+268h+TempFileName]; lpFileName
0x180008ebe  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008ec6  xor     r9d, r9d; lpSecurityAttributes
0x180008ec9  xor     r8d, r8d; dwShareMode
0x180008ecc  mov     [rsp+268h+dwCreationDisposition], 2; dwCreationDisposition
0x180008ed4  mov     edx, 0C0000000h; dwDesiredAccess
0x180008ed9  call    cs:__imp_CreateFileW
0x180008ee0  nop     dword ptr [rax+rax+00h]
0x180008ee5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008ee9  jz      short loc_180008F0D
0x180008eeb  mov     rcx, rax; hObject
0x180008eee  call    cs:__imp_CloseHandle
0x180008ef5  nop     dword ptr [rax+rax+00h]
0x180008efa  lea     rcx, [rsp+268h+TempFileName]; lpFileName
0x180008eff  call    cs:__imp_DeleteFileW
0x180008f06  nop     dword ptr [rax+rax+00h]
0x180008f0b  jmp     short loc_180008F0F
0x180008f0d  xor     eax, eax
0x180008f0f  mov     rcx, [rsp+268h+var_18]
0x180008f17  xor     rcx, rsp; StackCookie
0x180008f1a  call    __security_check_cookie
0x180008f1f  add     rsp, 268h
0x180008f26  retn
```
