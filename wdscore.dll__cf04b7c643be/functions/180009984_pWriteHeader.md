# pWriteHeader

- ea: `0x180009984`
- end: `0x1800099fe`
- name: `pWriteHeader`
- size: `122`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008f30`
- `0x180009030`

## callees

- `0x180009984`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800099ab`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800099ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800099d0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800099d0`

## pseudocode

```c
__int64 __fastcall pWriteHeader(HANDLE hFile, LPCVOID lpBuffer)
{
  unsigned int v4; // ebx
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  v4 = 0;
  if ( SetFilePointer(hFile, 0, 0, 0) != -1 && WriteFile(hFile, lpBuffer, 4u, &NumberOfBytesWritten, 0) )
    return NumberOfBytesWritten == 4;
  return v4;
}

```

## disassembly

```asm
0x180009984  mov     [rsp+arg_0], rbx
0x180009989  mov     [rsp+arg_8], rsi
0x18000998e  push    rdi
0x18000998f  sub     rsp, 30h
0x180009993  mov     rsi, rdx
0x180009996  mov     rdi, rcx
0x180009999  mov     [rsp+38h+NumberOfBytesWritten], 0
0x1800099a1  xor     ebx, ebx
0x1800099a3  xor     r9d, r9d; dwMoveMethod
0x1800099a6  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800099a9  xor     edx, edx; lDistanceToMove
0x1800099ab  call    cs:__imp_SetFilePointer
0x1800099b2  nop     dword ptr [rax+rax+00h]
0x1800099b7  cmp     eax, 0FFFFFFFFh
0x1800099ba  jz      short loc_1800099EB
0x1800099bc  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x1800099c1  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800099c6  lea     r8d, [rbx+4]; nNumberOfBytesToWrite
0x1800099ca  mov     rdx, rsi; lpBuffer
0x1800099cd  mov     rcx, rdi; hFile
0x1800099d0  call    cs:__imp_WriteFile
0x1800099d7  nop     dword ptr [rax+rax+00h]
0x1800099dc  test    eax, eax
0x1800099de  jz      short loc_1800099EB
0x1800099e0  lea     eax, [rbx+1]
0x1800099e3  cmp     [rsp+38h+NumberOfBytesWritten], 4
0x1800099e8  cmovz   ebx, eax
0x1800099eb  mov     eax, ebx
0x1800099ed  mov     rbx, [rsp+38h+arg_0]
0x1800099f2  mov     rsi, [rsp+38h+arg_8]
0x1800099f7  add     rsp, 30h
0x1800099fb  pop     rdi
0x1800099fc  retn
0x180027a41  push    rbp
0x180027a43  sub     rsp, 30h
0x180027a47  mov     rbp, rdx
0x180027a4a  add     rsp, 30h
0x180027a4e  pop     rbp
0x180027a4f  retn
```
