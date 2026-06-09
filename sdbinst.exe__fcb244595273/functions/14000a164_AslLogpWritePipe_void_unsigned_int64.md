# AslLogpWritePipe(void *,unsigned __int64)

- ea: `0x14000a164`
- end: `0x14000a266`
- name: `?AslLogpWritePipe@@YAXPEAX_K@Z`
- size: `258`
- prototype: `void __fastcall(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000b83c`

## callees

- `0x14000164a`
- `0x14000166e`
- `0x14000167a`
- `0x14000a164`

## import_xrefs

- `KERNEL32!WaitNamedPipeW` at `0x14000a1ca`
- `KERNEL32!WaitNamedPipeW` at `0x14000a1ca`
- `KERNEL32!CreateFileW` at `0x14000a1a2`
- `KERNEL32!CreateFileW` at `0x14000a1fb`
- `KERNEL32!CreateFileW` at `0x14000a1a2`
- `KERNEL32!CreateFileW` at `0x14000a1fb`
- `KERNEL32!SetNamedPipeHandleState` at `0x14000a220`
- `KERNEL32!SetNamedPipeHandleState` at `0x14000a220`

## pseudocode

```c
void __fastcall AslLogpWritePipe(LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  HANDLE FileW; // rbx
  DWORD Mode; // [rsp+60h] [rbp+18h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL
    || GetLastError_0() == 231
    && (WaitNamedPipeW(L"\\\\.\\pipe\\GmdAslLogger", 0),
        FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0),
        FileW != (HANDLE)-1LL) )
  {
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
    {
      NumberOfBytesWritten = 0;
      WriteFile_0(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      CloseHandle_0(FileW);
    }
  }
}

```

## disassembly

```asm
0x14000a164  mov     rax, rsp
0x14000a167  mov     [rax+8], rbx
0x14000a16b  mov     [rax+10h], rsi
0x14000a16f  push    rdi
0x14000a170  sub     rsp, 40h
0x14000a174  mov     qword ptr [rax-18h], 0
0x14000a17c  mov     rdi, rdx
0x14000a17f  mov     rsi, rcx
0x14000a182  mov     dword ptr [rax-20h], 0
0x14000a189  mov     edx, 40000000h; dwDesiredAccess
0x14000a18e  mov     dword ptr [rax-28h], 3
0x14000a195  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x14000a19c  xor     r9d, r9d; lpSecurityAttributes
0x14000a19f  xor     r8d, r8d; dwShareMode
0x14000a1a2  call    cs:__imp_CreateFileW
0x14000a1a8  mov     rbx, rax
0x14000a1ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a1af  jnz     short loc_14000A20A
0x14000a1b1  call    GetLastError_0
0x14000a1b6  cmp     eax, 0E7h
0x14000a1bb  jnz     loc_14000A256
0x14000a1c1  xor     edx, edx; nTimeOut
0x14000a1c3  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x14000a1ca  call    cs:__imp_WaitNamedPipeW
0x14000a1d0  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14000a1d9  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x14000a1e0  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14000a1e8  xor     r9d, r9d; lpSecurityAttributes
0x14000a1eb  xor     r8d, r8d; dwShareMode
0x14000a1ee  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14000a1f6  mov     edx, 40000000h; dwDesiredAccess
0x14000a1fb  call    cs:__imp_CreateFileW
0x14000a201  mov     rbx, rax
0x14000a204  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000a208  jz      short loc_14000A256
0x14000a20a  xor     r9d, r9d; lpCollectDataTimeout
0x14000a20d  mov     [rsp+48h+Mode], 2
0x14000a215  xor     r8d, r8d; lpMaxCollectionCount
0x14000a218  lea     rdx, [rsp+48h+Mode]; lpMode
0x14000a21d  mov     rcx, rbx; hNamedPipe
0x14000a220  call    cs:__imp_SetNamedPipeHandleState
0x14000a226  test    eax, eax
0x14000a228  jz      short loc_14000A256
0x14000a22a  mov     r8d, edi; nNumberOfBytesToWrite
0x14000a22d  mov     [rsp+48h+NumberOfBytesWritten], 0
0x14000a235  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14000a23a  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x14000a243  mov     rdx, rsi; lpBuffer
0x14000a246  mov     rcx, rbx; hFile
0x14000a249  call    WriteFile_0
0x14000a24e  mov     rcx, rbx; hObject
0x14000a251  call    CloseHandle_0
0x14000a256  mov     rbx, [rsp+48h+arg_0]
0x14000a25b  mov     rsi, [rsp+48h+arg_8]
0x14000a260  add     rsp, 40h
0x14000a264  pop     rdi
0x14000a265  retn
```
