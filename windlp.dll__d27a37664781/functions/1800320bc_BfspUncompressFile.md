# BfspUncompressFile

- ea: `0x1800320bc`
- end: `0x1800321e4`
- name: `BfspUncompressFile`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032518`

## callees

- `0x1800320bc`
- `0x18003c464`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180032121`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180032121`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800320fc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800320fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003214f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003214f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800321b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800321b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800321c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800321c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003219c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003219c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800321af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800321a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800321a7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180032192`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180032192`

## pseudocode

```c
DWORD __fastcall BfspUncompressFile(const wchar_t *a1)
{
  const WCHAR *v1; // rax
  WCHAR *v2; // rdi
  DWORD FileAttributesW; // eax
  DWORD LastError; // ebx
  HANDLE FileW; // rsi
  HANDLE ProcessHeap; // rax
  __int16 InBuffer; // [rsp+50h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF

  if ( a1 && *a1 )
  {
    v1 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v2 = (WCHAR *)v1;
    if ( !v1 )
      return GetLastError();
    FileAttributesW = GetFileAttributesW(v1);
    if ( FileAttributesW != -1 )
    {
      LastError = 0;
      if ( (FileAttributesW & 0x800) == 0 )
      {
LABEL_13:
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
        return LastError;
      }
      if ( SetFileAttributesW(v2, 0x80u) )
      {
        FileW = CreateFileW(v2, 0xC0010000, 7u, 0, 3u, 0x80u, 0);
        if ( FileW != (HANDLE)-1LL )
        {
          BytesReturned = 0;
          InBuffer = 0;
          if ( !DeviceIoControl(FileW, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
            LastError = GetLastError();
          CloseHandle(FileW);
          goto LABEL_13;
        }
      }
    }
    LastError = GetLastError();
    goto LABEL_13;
  }
  return 87;
}

```

## disassembly

```asm
0x1800320bc  mov     [rsp+arg_10], rbx
0x1800320c1  mov     [rsp+arg_18], rsi
0x1800320c6  push    rdi
0x1800320c7  sub     rsp, 40h
0x1800320cb  test    rcx, rcx
0x1800320ce  jz      loc_1800321CF
0x1800320d4  xor     eax, eax
0x1800320d6  cmp     ax, [rcx]
0x1800320d9  jz      loc_1800321CF
0x1800320df  xor     edx, edx
0x1800320e1  call    PrepareUnicodePathEx
0x1800320e6  mov     rdi, rax
0x1800320e9  test    rax, rax
0x1800320ec  jnz     short loc_1800320F9
0x1800320ee  call    cs:__imp_GetLastError
0x1800320f4  jmp     loc_1800321D4
0x1800320f9  mov     rcx, rdi; lpFileName
0x1800320fc  call    cs:__imp_GetFileAttributesW
0x180032102  cmp     eax, 0FFFFFFFFh
0x180032105  jz      loc_1800321AF
0x18003210b  xor     ebx, ebx
0x18003210d  bt      eax, 0Bh
0x180032111  jnb     loc_1800321B7
0x180032117  mov     esi, 80h
0x18003211c  mov     rcx, rdi; lpFileName
0x18003211f  mov     edx, esi; dwFileAttributes
0x180032121  call    cs:__imp_SetFileAttributesW
0x180032127  test    eax, eax
0x180032129  jz      loc_1800321AF
0x18003212f  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180032134  lea     r8d, [rbx+7]; dwShareMode
0x180032138  mov     [rsp+48h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18003213c  xor     r9d, r9d; lpSecurityAttributes
0x18003213f  mov     edx, 0C0010000h; dwDesiredAccess
0x180032144  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18003214c  mov     rcx, rdi; lpFileName
0x18003214f  call    cs:__imp_CreateFileW
0x180032155  mov     rsi, rax
0x180032158  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003215c  jz      short loc_1800321AF
0x18003215e  xor     ecx, ecx
0x180032160  mov     [rsp+48h+BytesReturned], ebx
0x180032164  mov     [rsp+48h+lpOverlapped], rcx; lpOverlapped
0x180032169  lea     rax, [rsp+48h+BytesReturned]
0x18003216e  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x180032173  lea     r9d, [rbx+2]; nInBufferSize
0x180032177  mov     [rsp+48h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x18003217b  lea     r8, [rsp+48h+InBuffer]; lpInBuffer
0x180032180  mov     qword ptr [rsp+48h+dwCreationDisposition], rcx; lpOutBuffer
0x180032185  mov     edx, 9C040h; dwIoControlCode
0x18003218a  mov     [rsp+48h+InBuffer], cx
0x18003218f  mov     rcx, rsi; hDevice
0x180032192  call    cs:__imp_DeviceIoControl
0x180032198  test    eax, eax
0x18003219a  jnz     short loc_1800321A4
0x18003219c  call    cs:__imp_GetLastError
0x1800321a2  mov     ebx, eax
0x1800321a4  mov     rcx, rsi; hObject
0x1800321a7  call    cs:__imp_CloseHandle
0x1800321ad  jmp     short loc_1800321B7
0x1800321af  call    cs:__imp_GetLastError
0x1800321b5  mov     ebx, eax
0x1800321b7  call    cs:__imp_GetProcessHeap
0x1800321bd  mov     r8, rdi; lpMem
0x1800321c0  xor     edx, edx; dwFlags
0x1800321c2  mov     rcx, rax; hHeap
0x1800321c5  call    cs:__imp_HeapFree
0x1800321cb  mov     eax, ebx
0x1800321cd  jmp     short loc_1800321D4
0x1800321cf  mov     eax, 57h ; 'W'
0x1800321d4  mov     rbx, [rsp+48h+arg_10]
0x1800321d9  mov     rsi, [rsp+48h+arg_18]
0x1800321de  add     rsp, 40h
0x1800321e2  pop     rdi
0x1800321e3  retn
```
