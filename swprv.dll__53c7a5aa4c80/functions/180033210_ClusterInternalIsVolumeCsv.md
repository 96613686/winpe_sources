# ClusterInternalIsVolumeCsv

- ea: `0x180033210`
- end: `0x1800332b9`
- name: `ClusterInternalIsVolumeCsv`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180032fec`

## callees

- `0x180033210`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003329d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003329d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033259`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033245`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033245`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180033294`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180033294`

## pseudocode

```c
__int64 __fastcall ClusterInternalIsVolumeCsv(const WCHAR *a1)
{
  HANDLE FileW; // rdi
  unsigned int v2; // ebx
  char OutBuffer; // [rsp+58h] [rbp+10h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp+18h] BYREF

  BytesReturned = 0;
  OutBuffer = 0;
  FileW = CreateFileW(a1, 0x80u, 7u, 0, 3u, 0x80u, 0);
  v2 = 1;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( GetLastError() )
      return 0;
  }
  else
  {
    DeviceIoControl(FileW, 0x560060u, 0, 0, &OutBuffer, 1u, &BytesReturned, 0);
    CloseHandle(FileW);
  }
  if ( !OutBuffer )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180033210  mov     rax, rsp
0x180033213  mov     [rax+8], rbx
0x180033217  push    rdi
0x180033218  sub     rsp, 40h
0x18003321c  mov     edx, 80h; dwDesiredAccess
0x180033221  mov     qword ptr [rax-18h], 0
0x180033229  mov     [rax-20h], edx
0x18003322c  xor     r9d, r9d; lpSecurityAttributes
0x18003322f  mov     dword ptr [rax+18h], 0
0x180033236  mov     byte ptr [rax+10h], 0
0x18003323a  lea     r8d, [rdx-79h]; dwShareMode
0x18003323e  mov     dword ptr [rax-28h], 3
0x180033245  call    cs:__imp_CreateFileW
0x18003324b  mov     rdi, rax
0x18003324e  mov     ebx, 1
0x180033253  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033257  jnz     short loc_180033265
0x180033259  call    cs:__imp_GetLastError
0x18003325f  test    eax, eax
0x180033261  jnz     short loc_1800332AA
0x180033263  jmp     short loc_1800332A3
0x180033265  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18003326e  lea     rax, [rsp+48h+BytesReturned]
0x180033273  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x180033278  xor     r9d, r9d; nInBufferSize
0x18003327b  lea     rax, [rsp+48h+OutBuffer]
0x180033280  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x180033284  xor     r8d, r8d; lpInBuffer
0x180033287  mov     [rsp+48h+lpOutBuffer], rax; lpOutBuffer
0x18003328c  mov     edx, 560060h; dwIoControlCode
0x180033291  mov     rcx, rdi; hDevice
0x180033294  call    cs:__imp_DeviceIoControl
0x18003329a  mov     rcx, rdi; hObject
0x18003329d  call    cs:__imp_CloseHandle
0x1800332a3  cmp     [rsp+48h+OutBuffer], 0
0x1800332a8  jnz     short loc_1800332AC
0x1800332aa  xor     ebx, ebx
0x1800332ac  mov     eax, ebx
0x1800332ae  mov     rbx, [rsp+48h+arg_0]
0x1800332b3  add     rsp, 40h
0x1800332b7  pop     rdi
0x1800332b8  retn
```
