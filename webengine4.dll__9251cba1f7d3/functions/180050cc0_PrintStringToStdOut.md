# PrintStringToStdOut

- ea: `0x180050cc0`
- end: `0x180050dd9`
- name: `PrintStringToStdOut`
- size: `281`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, HANDLE hFile)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180037220`
- `0x18003ca0c`
- `0x180050c48`

## callees

- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x180050cc0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180050dbe`
- `KERNEL32!WriteFile` at `0x180050dbe`
- `KERNEL32!lstrlenW` at `0x180050d17`
- `KERNEL32!lstrlenW` at `0x180050d17`
- `KERNEL32!WideCharToMultiByte` at `0x180050d64`
- `KERNEL32!WideCharToMultiByte` at `0x180050da3`
- `KERNEL32!WideCharToMultiByte` at `0x180050d64`
- `KERNEL32!WideCharToMultiByte` at `0x180050da3`
- `KERNEL32!GetStdHandle` at `0x180050cdc`
- `KERNEL32!GetStdHandle` at `0x180050cdc`
- `KERNEL32!GetConsoleOutputCP` at `0x180050d3c`
- `KERNEL32!GetConsoleOutputCP` at `0x180050d7d`
- `KERNEL32!GetConsoleOutputCP` at `0x180050d3c`
- `KERNEL32!GetConsoleOutputCP` at `0x180050d7d`
- `KERNEL32!WriteConsoleW` at `0x180050d31`
- `KERNEL32!WriteConsoleW` at `0x180050d31`
- `KERNEL32!GetConsoleMode` at `0x180050d0a`
- `KERNEL32!GetConsoleMode` at `0x180050d0a`
- `KERNEL32!GetFileType` at `0x180050cf8`
- `KERNEL32!GetFileType` at `0x180050cf8`

## pseudocode

```c
void __fastcall PrintStringToStdOut(LPCWCH lpWideCharStr, HANDLE hFile)
{
  HANDLE StdHandle; // rbx
  DWORD v4; // eax
  UINT ConsoleOutputCP; // eax
  int cbMultiByte; // ebp
  CHAR *lpMultiByteStr; // rsi
  UINT v8; // eax
  DWORD NumberOfCharsWritten; // [rsp+68h] [rbp+10h] BYREF
  DWORD Mode; // [rsp+70h] [rbp+18h] BYREF

  StdHandle = hFile;
  if ( hFile || (StdHandle = GetStdHandle(0xFFFFFFF5), StdHandle != (HANDLE)-1LL) )
  {
    if ( (GetFileType(StdHandle) & 2) != 0 && GetConsoleMode(StdHandle, &Mode) )
    {
      v4 = lstrlenW(lpWideCharStr);
      WriteConsoleW(StdHandle, lpWideCharStr, v4, &NumberOfCharsWritten, 0);
    }
    else
    {
      ConsoleOutputCP = GetConsoleOutputCP();
      cbMultiByte = WideCharToMultiByte(ConsoleOutputCP, 0, lpWideCharStr, -1, 0, 0, 0, 0);
      lpMultiByteStr = (CHAR *)MemAllocClear(cbMultiByte);
      if ( lpMultiByteStr )
      {
        v8 = GetConsoleOutputCP();
        WideCharToMultiByte(v8, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0);
        WriteFile(StdHandle, lpMultiByteStr, cbMultiByte - 1, &NumberOfCharsWritten, 0);
        MemFree(lpMultiByteStr);
      }
    }
  }
  else
  {
    GetLastWin32Error();
  }
}

```

## disassembly

```asm
0x180050cc0  mov     [rsp+arg_0], rbx
0x180050cc5  push    rbp
0x180050cc6  push    rsi
0x180050cc7  push    rdi
0x180050cc8  sub     rsp, 40h
0x180050ccc  mov     rbx, rdx
0x180050ccf  mov     rdi, rcx
0x180050cd2  test    rdx, rdx
0x180050cd5  jnz     short loc_180050CF5
0x180050cd7  mov     ecx, 0FFFFFFF5h; nStdHandle
0x180050cdc  call    cs:__imp_GetStdHandle
0x180050ce2  mov     rbx, rax
0x180050ce5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180050ce9  jnz     short loc_180050CF5
0x180050ceb  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180050cf0  jmp     loc_180050DCC
0x180050cf5  mov     rcx, rbx; hFile
0x180050cf8  call    cs:__imp_GetFileType
0x180050cfe  test    al, 2
0x180050d00  jz      short loc_180050D3C
0x180050d02  lea     rdx, [rsp+58h+Mode]; lpMode
0x180050d07  mov     rcx, rbx; hConsoleHandle
0x180050d0a  call    cs:__imp_GetConsoleMode
0x180050d10  test    eax, eax
0x180050d12  jz      short loc_180050D3C
0x180050d14  mov     rcx, rdi; lpString
0x180050d17  call    cs:__imp_lstrlenW
0x180050d1d  and     [rsp+58h+lpMultiByteStr], 0
0x180050d23  lea     r9, [rsp+58h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x180050d28  mov     r8d, eax; nNumberOfCharsToWrite
0x180050d2b  mov     rdx, rdi; lpBuffer
0x180050d2e  mov     rcx, rbx; hConsoleOutput
0x180050d31  call    cs:__imp_WriteConsoleW
0x180050d37  jmp     loc_180050DCC
0x180050d3c  call    cs:__imp_GetConsoleOutputCP
0x180050d42  and     [rsp+58h+var_20], 0
0x180050d48  or      r9d, 0FFFFFFFFh; cchWideChar
0x180050d4c  and     [rsp+58h+var_28], 0
0x180050d52  mov     ecx, eax; CodePage
0x180050d54  and     [rsp+58h+cbMultiByte], 0
0x180050d59  mov     r8, rdi; lpWideCharStr
0x180050d5c  and     [rsp+58h+lpMultiByteStr], 0
0x180050d62  xor     edx, edx; dwFlags
0x180050d64  call    cs:__imp_WideCharToMultiByte
0x180050d6a  movsxd  rbp, eax
0x180050d6d  mov     rcx, rbp; unsigned __int64
0x180050d70  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180050d75  mov     rsi, rax
0x180050d78  test    rax, rax
0x180050d7b  jz      short loc_180050DCC
0x180050d7d  call    cs:__imp_GetConsoleOutputCP
0x180050d83  and     [rsp+58h+var_20], 0
0x180050d89  or      r9d, 0FFFFFFFFh; cchWideChar
0x180050d8d  and     [rsp+58h+var_28], 0
0x180050d93  mov     ecx, eax; CodePage
0x180050d95  mov     [rsp+58h+cbMultiByte], ebp; cbMultiByte
0x180050d99  mov     r8, rdi; lpWideCharStr
0x180050d9c  xor     edx, edx; dwFlags
0x180050d9e  mov     [rsp+58h+lpMultiByteStr], rsi; lpOverlapped
0x180050da3  call    cs:__imp_WideCharToMultiByte
0x180050da9  and     [rsp+58h+lpMultiByteStr], 0
0x180050daf  lea     r8d, [rbp-1]; nNumberOfBytesToWrite
0x180050db3  lea     r9, [rsp+58h+NumberOfCharsWritten]; lpNumberOfBytesWritten
0x180050db8  mov     rdx, rsi; lpBuffer
0x180050dbb  mov     rcx, rbx; hFile
0x180050dbe  call    cs:__imp_WriteFile
0x180050dc4  mov     rcx, rsi; lpMem
0x180050dc7  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180050dcc  mov     rbx, [rsp+58h+arg_0]
0x180050dd1  add     rsp, 40h
0x180050dd5  pop     rdi
0x180050dd6  pop     rsi
0x180050dd7  pop     rbp
0x180050dd8  retn
```
