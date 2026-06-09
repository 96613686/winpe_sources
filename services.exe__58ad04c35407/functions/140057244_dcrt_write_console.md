# __dcrt_write_console

- ea: `0x140057244`
- end: `0x1400572f8`
- name: `__dcrt_write_console`
- size: `180`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140056b80`

## callees

- `0x140057244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005727a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005727a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057292`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140057292`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400572c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400572c3`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14005726e`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x1400572e5`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14005726e`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x1400572e5`

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
0x140057244  push    rbx
0x140057246  push    rbp
0x140057247  push    rsi
0x140057248  push    rdi
0x140057249  sub     rsp, 48h
0x14005724d  mov     rdi, r8
0x140057250  mov     [rsp+68h+lpReserved], 0; lpReserved
0x140057259  mov     r9, r8; lpNumberOfCharsWritten
0x14005725c  mov     esi, edx
0x14005725e  mov     r8d, edx; nNumberOfCharsToWrite
0x140057261  mov     rbp, rcx
0x140057264  mov     rdx, rcx; lpBuffer
0x140057267  mov     rcx, cs:hObject; hConsoleOutput
0x14005726e  call    cs:__imp_WriteConsoleW
0x140057274  mov     ebx, eax
0x140057276  test    eax, eax
0x140057278  jnz     short loc_1400572ED
0x14005727a  call    cs:__imp_GetLastError
0x140057280  cmp     eax, 6
0x140057283  jnz     short loc_1400572ED
0x140057285  mov     rcx, cs:hObject; hObject
0x14005728c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140057290  ja      short loc_140057298
0x140057292  call    cs:__imp_CloseHandle
0x140057298  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1400572a1  lea     rcx, aConout; "CONOUT$"
0x1400572a8  mov     r8d, 3; dwShareMode
0x1400572ae  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400572b6  xor     r9d, r9d; lpSecurityAttributes
0x1400572b9  mov     dword ptr [rsp+68h+lpReserved], r8d; dwCreationDisposition
0x1400572be  mov     edx, 40000000h; dwDesiredAccess
0x1400572c3  call    cs:__imp_CreateFileW
0x1400572c9  mov     r9, rdi; lpNumberOfCharsWritten
0x1400572cc  mov     [rsp+68h+lpReserved], 0; lpReserved
0x1400572d5  mov     rcx, rax; hConsoleOutput
0x1400572d8  mov     cs:hObject, rax
0x1400572df  mov     r8d, esi; nNumberOfCharsToWrite
0x1400572e2  mov     rdx, rbp; lpBuffer
0x1400572e5  call    cs:__imp_WriteConsoleW
0x1400572eb  mov     ebx, eax
0x1400572ed  mov     eax, ebx
0x1400572ef  add     rsp, 48h
0x1400572f3  pop     rdi
0x1400572f4  pop     rsi
0x1400572f5  pop     rbp
0x1400572f6  pop     rbx
0x1400572f7  retn
```
