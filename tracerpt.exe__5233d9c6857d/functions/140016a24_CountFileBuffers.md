# CountFileBuffers

- ea: `0x140016a24`
- end: `0x140016ad9`
- name: `CountFileBuffers`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140018d04`

## callees

- `0x140016a24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016a6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140016a5f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140016a5f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x140016a7b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x140016a7b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140016aa7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140016aa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016ac8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016ac8`

## pseudocode

```c
DWORD __fastcall CountFileBuffers(const WCHAR *a1)
{
  HANDLE FileW; // rax
  void *v2; // rbx
  DWORD FileSize; // edi
  unsigned int Buffer; // [rsp+58h] [rbp+10h] BYREF
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+18h] BYREF

  Buffer = 0;
  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v2 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  FileSize = GetFileSize(FileW, 0);
  if ( FileSize - 1 <= 0xFFFFFFFD && ReadFile(v2, &Buffer, 4u, &NumberOfBytesRead, 0) )
  {
    if ( Buffer )
      TotalBuffersExpected += FileSize / Buffer;
  }
  return CloseHandle(v2);
}

```

## disassembly

```asm
0x140016a24  mov     rax, rsp
0x140016a27  mov     [rax+8], rbx
0x140016a2b  push    rdi
0x140016a2c  sub     rsp, 40h
0x140016a30  mov     qword ptr [rax-18h], 0
0x140016a38  mov     r8d, 3; dwShareMode
0x140016a3e  mov     dword ptr [rax-20h], 80h
0x140016a45  xor     r9d, r9d; lpSecurityAttributes
0x140016a48  mov     edx, 80000000h; dwDesiredAccess
0x140016a4d  mov     [rax-28h], r8d
0x140016a51  mov     dword ptr [rax+10h], 0
0x140016a58  mov     dword ptr [rax+18h], 0
0x140016a5f  call    cs:__imp_CreateFileW
0x140016a65  mov     rbx, rax
0x140016a68  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140016a6c  jnz     short loc_140016A76
0x140016a6e  call    cs:__imp_GetLastError
0x140016a74  jmp     short loc_140016ACE
0x140016a76  xor     edx, edx; lpFileSizeHigh
0x140016a78  mov     rcx, rbx; hFile
0x140016a7b  call    cs:__imp_GetFileSize
0x140016a81  mov     edi, eax
0x140016a83  lea     ecx, [rax-1]
0x140016a86  cmp     ecx, 0FFFFFFFDh
0x140016a89  ja      short loc_140016AC5
0x140016a8b  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140016a90  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x140016a99  mov     r8d, 4; nNumberOfBytesToRead
0x140016a9f  lea     rdx, [rsp+48h+Buffer]; lpBuffer
0x140016aa4  mov     rcx, rbx; hFile
0x140016aa7  call    cs:__imp_ReadFile
0x140016aad  test    eax, eax
0x140016aaf  jz      short loc_140016AC5
0x140016ab1  mov     ecx, [rsp+48h+Buffer]
0x140016ab5  test    ecx, ecx
0x140016ab7  jz      short loc_140016AC5
0x140016ab9  xor     edx, edx
0x140016abb  mov     eax, edi
0x140016abd  div     ecx
0x140016abf  add     cs:?TotalBuffersExpected@@3KA, eax; ulong TotalBuffersExpected
0x140016ac5  mov     rcx, rbx; hObject
0x140016ac8  call    cs:__imp_CloseHandle
0x140016ace  mov     rbx, [rsp+48h+arg_0]
0x140016ad3  add     rsp, 40h
0x140016ad7  pop     rdi
0x140016ad8  retn
```
