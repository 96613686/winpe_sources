# __dcrt_write_console

- ea: `0x1004381f4`
- end: `0x1004382b2`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100437270`

## callees

- `0x1004381f4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100438231`
- `KERNEL32!GetLastError` at `0x100438231`
- `KERNEL32!CreateFileW` at `0x100438274`
- `KERNEL32!CreateFileW` at `0x100438274`
- `KERNEL32!CloseHandle` at `0x100438249`
- `KERNEL32!CloseHandle` at `0x100438249`
- `KERNEL32!WriteConsoleW` at `0x100438225`
- `KERNEL32!WriteConsoleW` at `0x100438293`
- `KERNEL32!WriteConsoleW` at `0x100438225`
- `KERNEL32!WriteConsoleW` at `0x100438293`

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
0x1004381f4  mov     rax, rsp
0x1004381f7  mov     [rax+8], rbx
0x1004381fb  mov     [rax+10h], rbp
0x1004381ff  mov     [rax+18h], rsi
0x100438203  push    rdi
0x100438204  sub     rsp, 40h
0x100438208  and     qword ptr [rax-28h], 0
0x10043820d  mov     rdi, r8
0x100438210  mov     r9, r8; lpNumberOfCharsWritten
0x100438213  mov     esi, edx
0x100438215  mov     r8d, edx; nNumberOfCharsToWrite
0x100438218  mov     rbp, rcx
0x10043821b  mov     rdx, rcx; lpBuffer
0x10043821e  mov     rcx, cs:hObject; hConsoleOutput
0x100438225  call    cs:__imp_WriteConsoleW
0x10043822b  mov     ebx, eax
0x10043822d  test    eax, eax
0x10043822f  jnz     short loc_10043829B
0x100438231  call    cs:__imp_GetLastError
0x100438237  cmp     eax, 6
0x10043823a  jnz     short loc_10043829B
0x10043823c  mov     rcx, cs:hObject; hObject
0x100438243  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x100438247  ja      short loc_10043824F
0x100438249  call    cs:__imp_CloseHandle
0x10043824f  and     [rsp+48h+var_18], 0
0x100438255  lea     rcx, FileName; "CONOUT$"
0x10043825c  and     [rsp+48h+var_20], 0
0x100438261  mov     r8d, 3; dwShareMode
0x100438267  xor     r9d, r9d; lpSecurityAttributes
0x10043826a  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x10043826f  mov     edx, 40000000h; dwDesiredAccess
0x100438274  call    cs:__imp_CreateFileW
0x10043827a  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x100438280  mov     r9, rdi; lpNumberOfCharsWritten
0x100438283  mov     rcx, rax; hConsoleOutput
0x100438286  mov     cs:hObject, rax
0x10043828d  mov     r8d, esi; nNumberOfCharsToWrite
0x100438290  mov     rdx, rbp; lpBuffer
0x100438293  call    cs:__imp_WriteConsoleW
0x100438299  mov     ebx, eax
0x10043829b  mov     rbp, [rsp+48h+arg_8]
0x1004382a0  mov     eax, ebx
0x1004382a2  mov     rbx, [rsp+48h+arg_0]
0x1004382a7  mov     rsi, [rsp+48h+arg_10]
0x1004382ac  add     rsp, 40h
0x1004382b0  pop     rdi
0x1004382b1  retn
```
