# ConsoleToPipeRedirector::StartRead(void)

- ea: `0x1400e5fa8`
- end: `0x1400e600c`
- name: `?StartRead@ConsoleToPipeRedirector@@AEAAXXZ`
- size: `100`
- prototype: `void __fastcall(ConsoleToPipeRedirector *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400e0b10`
- `0x1400e5720`

## callees

- `0x1400e5fa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e5fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e5fef`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400e5fc2`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400e5fc2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400e6000`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400e6000`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400e5fe5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400e5fe5`

## pseudocode

```c
void __fastcall ConsoleToPipeRedirector::StartRead(ConsoleToPipeRedirector *this)
{
  if ( (unsigned __int64)(*((_QWORD *)this + 6) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    StartThreadpoolIo(*((PTP_IO *)this + 8));
    if ( !ReadFile(*((HANDLE *)this + 6), (char *)this + 88, 0x100u, 0, (LPOVERLAPPED)((char *)this + 344))
      && GetLastError() != 997 )
    {
      CancelThreadpoolIo(*((PTP_IO *)this + 8));
    }
  }
}

```

## disassembly

```asm
0x1400e5fa8  push    rbx
0x1400e5faa  sub     rsp, 30h
0x1400e5fae  mov     rax, [rcx+30h]
0x1400e5fb2  mov     rbx, rcx
0x1400e5fb5  dec     rax
0x1400e5fb8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e5fbc  ja      short loc_1400E6006
0x1400e5fbe  mov     rcx, [rcx+40h]; pio
0x1400e5fc2  call    cs:__imp_StartThreadpoolIo
0x1400e5fc8  mov     rcx, [rbx+30h]; hFile
0x1400e5fcc  lea     rax, [rbx+158h]
0x1400e5fd3  lea     rdx, [rbx+58h]; lpBuffer
0x1400e5fd7  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x1400e5fdc  xor     r9d, r9d; lpNumberOfBytesRead
0x1400e5fdf  mov     r8d, 100h; nNumberOfBytesToRead
0x1400e5fe5  call    cs:__imp_ReadFile
0x1400e5feb  test    eax, eax
0x1400e5fed  jnz     short loc_1400E6006
0x1400e5fef  call    cs:__imp_GetLastError
0x1400e5ff5  cmp     eax, 3E5h
0x1400e5ffa  jz      short loc_1400E6006
0x1400e5ffc  mov     rcx, [rbx+40h]; pio
0x1400e6000  call    cs:__imp_CancelThreadpoolIo
0x1400e6006  add     rsp, 30h
0x1400e600a  pop     rbx
0x1400e600b  retn
```
