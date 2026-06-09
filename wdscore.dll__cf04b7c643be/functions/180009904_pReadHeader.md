# pReadHeader

- ea: `0x180009904`
- end: `0x18000997e`
- name: `pReadHeader`
- size: `122`
- prototype: `__int64 __fastcall(HANDLE hFile, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009030`

## callees

- `0x180009904`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000992b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000992b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009950`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009950`

## pseudocode

```c
__int64 __fastcall pReadHeader(HANDLE hFile, LPVOID lpBuffer)
{
  unsigned int v4; // ebx
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp+18h] BYREF

  NumberOfBytesRead = 0;
  v4 = 0;
  if ( SetFilePointer(hFile, 0, 0, 0) != -1 && ReadFile(hFile, lpBuffer, 4u, &NumberOfBytesRead, 0) )
    return NumberOfBytesRead == 4;
  return v4;
}

```

## disassembly

```asm
0x180009904  mov     [rsp+arg_0], rbx
0x180009909  mov     [rsp+arg_8], rsi
0x18000990e  push    rdi
0x18000990f  sub     rsp, 30h
0x180009913  mov     rsi, rdx
0x180009916  mov     rdi, rcx
0x180009919  mov     [rsp+38h+NumberOfBytesRead], 0
0x180009921  xor     ebx, ebx
0x180009923  xor     r9d, r9d; dwMoveMethod
0x180009926  xor     r8d, r8d; lpDistanceToMoveHigh
0x180009929  xor     edx, edx; lDistanceToMove
0x18000992b  call    cs:__imp_SetFilePointer
0x180009932  nop     dword ptr [rax+rax+00h]
0x180009937  cmp     eax, 0FFFFFFFFh
0x18000993a  jz      short loc_18000996B
0x18000993c  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x180009941  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180009946  lea     r8d, [rbx+4]; nNumberOfBytesToRead
0x18000994a  mov     rdx, rsi; lpBuffer
0x18000994d  mov     rcx, rdi; hFile
0x180009950  call    cs:__imp_ReadFile
0x180009957  nop     dword ptr [rax+rax+00h]
0x18000995c  test    eax, eax
0x18000995e  jz      short loc_18000996B
0x180009960  lea     eax, [rbx+1]
0x180009963  cmp     [rsp+38h+NumberOfBytesRead], 4
0x180009968  cmovz   ebx, eax
0x18000996b  mov     eax, ebx
0x18000996d  mov     rbx, [rsp+38h+arg_0]
0x180009972  mov     rsi, [rsp+38h+arg_8]
0x180009977  add     rsp, 30h
0x18000997b  pop     rdi
0x18000997c  retn
0x180027a41  push    rbp
0x180027a43  sub     rsp, 30h
0x180027a47  mov     rbp, rdx
0x180027a4a  add     rsp, 30h
0x180027a4e  pop     rbp
0x180027a4f  retn
```
