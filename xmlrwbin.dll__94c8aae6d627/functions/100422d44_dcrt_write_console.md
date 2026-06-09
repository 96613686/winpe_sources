# __dcrt_write_console

- ea: `0x100422d44`
- end: `0x100422e02`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1004222e8`

## callees

- `0x100422d44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100422d81`
- `KERNEL32!GetLastError` at `0x100422d81`
- `KERNEL32!CreateFileW` at `0x100422dc4`
- `KERNEL32!CreateFileW` at `0x100422dc4`
- `KERNEL32!CloseHandle` at `0x100422d99`
- `KERNEL32!CloseHandle` at `0x100422d99`
- `KERNEL32!WriteConsoleW` at `0x100422d75`
- `KERNEL32!WriteConsoleW` at `0x100422de3`
- `KERNEL32!WriteConsoleW` at `0x100422d75`
- `KERNEL32!WriteConsoleW` at `0x100422de3`

## pseudocode

```c
__int64 __fastcall _dcrt_write_console(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  unsigned int v6; // ebx

  v6 = WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v6 && GetLastError() == 6 )
  {
    if ( (unsigned __int64)hObject <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    hObject = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    return WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x100422d44  mov     rax, rsp
0x100422d47  mov     [rax+8], rbx
0x100422d4b  mov     [rax+10h], rbp
0x100422d4f  mov     [rax+18h], rsi
0x100422d53  push    rdi
0x100422d54  sub     rsp, 40h
0x100422d58  and     qword ptr [rax-28h], 0
0x100422d5d  mov     rdi, r8
0x100422d60  mov     r9, r8; lpNumberOfCharsWritten
0x100422d63  mov     esi, edx
0x100422d65  mov     r8d, edx; nNumberOfCharsToWrite
0x100422d68  mov     rbp, rcx
0x100422d6b  mov     rdx, rcx; lpBuffer
0x100422d6e  mov     rcx, cs:hObject; hConsoleOutput
0x100422d75  call    cs:__imp_WriteConsoleW
0x100422d7b  mov     ebx, eax
0x100422d7d  test    eax, eax
0x100422d7f  jnz     short loc_100422DEB
0x100422d81  call    cs:__imp_GetLastError
0x100422d87  cmp     eax, 6
0x100422d8a  jnz     short loc_100422DEB
0x100422d8c  mov     rcx, cs:hObject; hObject
0x100422d93  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x100422d97  ja      short loc_100422D9F
0x100422d99  call    cs:__imp_CloseHandle
0x100422d9f  and     [rsp+48h+var_18], 0
0x100422da5  lea     rcx, FileName; "CONOUT$"
0x100422dac  and     [rsp+48h+var_20], 0
0x100422db1  mov     r8d, 3; dwShareMode
0x100422db7  xor     r9d, r9d; lpSecurityAttributes
0x100422dba  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x100422dbf  mov     edx, 40000000h; dwDesiredAccess
0x100422dc4  call    cs:__imp_CreateFileW
0x100422dca  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x100422dd0  mov     r9, rdi; lpNumberOfCharsWritten
0x100422dd3  mov     rcx, rax; hConsoleOutput
0x100422dd6  mov     cs:hObject, rax
0x100422ddd  mov     r8d, esi; nNumberOfCharsToWrite
0x100422de0  mov     rdx, rbp; lpBuffer
0x100422de3  call    cs:__imp_WriteConsoleW
0x100422de9  mov     ebx, eax
0x100422deb  mov     rbp, [rsp+48h+arg_8]
0x100422df0  mov     eax, ebx
0x100422df2  mov     rbx, [rsp+48h+arg_0]
0x100422df7  mov     rsi, [rsp+48h+arg_10]
0x100422dfc  add     rsp, 40h
0x100422e00  pop     rdi
0x100422e01  retn
```
