# WofIsExternalFile

- ea: `0x18003693c`
- end: `0x1800369f8`
- name: `WofIsExternalFile`
- size: `188`
- prototype: `HRESULT __stdcall(LPCWSTR FilePath, PBOOL IsExternalFile, PULONG Provider, PVOID ExternalFileInfo, PULONG BufferLength)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001a76c`

## callees

- `0x18003693c`
- `0x180036a88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800369a1`
- `KERNEL32!GetLastError` at `0x1800369a1`
- `KERNEL32!CloseHandle` at `0x1800369d5`
- `KERNEL32!CloseHandle` at `0x1800369d5`
- `KERNEL32!CreateFileW` at `0x18003698c`
- `KERNEL32!CreateFileW` at `0x18003698c`

## pseudocode

```c
HRESULT __stdcall WofIsExternalFile(
        LPCWSTR FilePath,
        PBOOL IsExternalFile,
        PULONG Provider,
        PVOID ExternalFileInfo,
        PULONG BufferLength)
{
  HANDLE FileW; // rax
  void *v8; // rdi
  HRESULT LastError; // eax
  HRESULT IsExternalFileByHandle; // ebx

  if ( Provider && !ExternalFileInfo )
    return -2147024809;
  FileW = CreateFileW(FilePath, 0x80u, 7u, 0, 3u, 0x200080u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    IsExternalFileByHandle = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return LastError;
  }
  else
  {
    IsExternalFileByHandle = WofpIsExternalFileByHandle(FileW, (__int64)ExternalFileInfo);
    CloseHandle(v8);
  }
  return IsExternalFileByHandle;
}

```

## disassembly

```asm
0x18003693c  mov     [rsp+arg_0], rbx
0x180036941  mov     [rsp+arg_8], rbp
0x180036946  mov     [rsp+arg_10], rsi
0x18003694b  push    rdi
0x18003694c  sub     rsp, 40h
0x180036950  mov     rbx, r9
0x180036953  mov     rsi, r8
0x180036956  mov     rbp, rdx
0x180036959  test    r8, r8
0x18003695c  jz      short loc_18003696A
0x18003695e  test    rbx, rbx
0x180036961  jnz     short loc_18003696A
0x180036963  mov     eax, 80070057h
0x180036968  jmp     short loc_1800369E3
0x18003696a  and     [rsp+48h+var_18], 0
0x180036970  xor     r9d, r9d; lpSecurityAttributes
0x180036973  mov     [rsp+48h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x18003697b  mov     edx, 80h; dwDesiredAccess
0x180036980  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180036988  lea     r8d, [r9+7]; dwShareMode
0x18003698c  call    cs:__imp_CreateFileW
0x180036993  nop     dword ptr [rax+rax+00h]
0x180036998  mov     rdi, rax
0x18003699b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003699f  jnz     short loc_1800369BD
0x1800369a1  call    cs:__imp_GetLastError
0x1800369a8  nop     dword ptr [rax+rax+00h]
0x1800369ad  movzx   ebx, ax
0x1800369b0  or      ebx, 80070000h
0x1800369b6  test    eax, eax
0x1800369b8  cmovle  ebx, eax
0x1800369bb  jmp     short loc_1800369E1
0x1800369bd  mov     r9, rsi
0x1800369c0  mov     qword ptr [rsp+48h+dwCreationDisposition], rbx; __int64
0x1800369c5  mov     r8, rbp
0x1800369c8  mov     rcx, rdi; hDevice
0x1800369cb  call    WofpIsExternalFileByHandle
0x1800369d0  mov     ebx, eax
0x1800369d2  mov     rcx, rdi; hObject
0x1800369d5  call    cs:__imp_CloseHandle
0x1800369dc  nop     dword ptr [rax+rax+00h]
0x1800369e1  mov     eax, ebx
0x1800369e3  mov     rbx, [rsp+48h+arg_0]
0x1800369e8  mov     rbp, [rsp+48h+arg_8]
0x1800369ed  mov     rsi, [rsp+48h+arg_10]
0x1800369f2  add     rsp, 40h
0x1800369f6  pop     rdi
0x1800369f7  retn
```
