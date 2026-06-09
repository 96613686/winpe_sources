# GetReparseTag

- ea: `0x18003b998`
- end: `0x18003badb`
- name: `GetReparseTag`
- size: `323`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x18003b04c`
- `0x18003bb64`

## callees

- `0x18003b998`
- `0x18003c464`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b9e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003b9e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ba00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ba6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ba91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ba00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ba6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ba91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ba12`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ba12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ba7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ba9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ba7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ba9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003babb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003babb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003baa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003baa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ba8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ba8b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003ba4a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003ba4a`

## pseudocode

```c
_BOOL8 __fastcall GetReparseTag(LPCWSTR lpFileName, _DWORD *a2)
{
  void *v4; // rbp
  DWORD LastError; // ebx
  HANDLE FileW; // rsi
  HANDLE ProcessHeap; // rax
  _DWORD *v8; // rdi
  HANDLE v9; // rax
  HANDLE v10; // rax
  DWORD BytesReturned; // [rsp+70h] [rbp+18h] BYREF

  v4 = (void *)PrepareUnicodePathEx(lpFileName);
  if ( v4 )
  {
    LastError = 0;
    *a2 = 0;
    FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2200000u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      BytesReturned = 0;
      ProcessHeap = GetProcessHeap();
      v8 = HeapAlloc(ProcessHeap, 8u, 0x4000u);
      if ( v8 )
      {
        if ( DeviceIoControl(FileW, 0x900A8u, 0, 0, v8, 0x4000u, &BytesReturned, 0) )
        {
          *a2 = *v8;
        }
        else
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 31;
        }
        v9 = GetProcessHeap();
        HeapFree(v9, 0, v8);
      }
      else
      {
        LastError = 14;
      }
      CloseHandle(FileW);
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v4);
  }
  else
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 31;
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18003b998  mov     [rsp+arg_0], rbx
0x18003b99d  mov     [rsp+arg_8], rbp
0x18003b9a2  push    rsi
0x18003b9a3  push    rdi
0x18003b9a4  push    r14
0x18003b9a6  sub     rsp, 40h
0x18003b9aa  mov     r14, rdx
0x18003b9ad  mov     rdi, rcx
0x18003b9b0  xor     edx, edx
0x18003b9b2  call    PrepareUnicodePathEx
0x18003b9b7  mov     rbp, rax
0x18003b9ba  test    rax, rax
0x18003b9bd  jz      loc_18003BAA7
0x18003b9c3  xor     ebx, ebx
0x18003b9c5  xor     r9d, r9d; lpSecurityAttributes
0x18003b9c8  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x18003b9cd  xor     edx, edx; dwDesiredAccess
0x18003b9cf  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18003b9d7  mov     rcx, rdi; lpFileName
0x18003b9da  mov     [r14], ebx
0x18003b9dd  lea     r8d, [rbx+7]; dwShareMode
0x18003b9e1  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18003b9e9  call    cs:__imp_CreateFileW
0x18003b9ef  mov     rsi, rax
0x18003b9f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b9f6  jz      loc_18003BA91
0x18003b9fc  mov     [rsp+58h+BytesReturned], ebx
0x18003ba00  call    cs:__imp_GetProcessHeap
0x18003ba06  lea     edx, [rbx+8]; dwFlags
0x18003ba09  mov     r8d, 4000h; dwBytes
0x18003ba0f  mov     rcx, rax; hHeap
0x18003ba12  call    cs:__imp_HeapAlloc
0x18003ba18  mov     rdi, rax
0x18003ba1b  test    rax, rax
0x18003ba1e  jz      short loc_18003BA83
0x18003ba20  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x18003ba25  lea     rax, [rsp+58h+BytesReturned]
0x18003ba2a  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x18003ba2f  xor     r9d, r9d; nInBufferSize
0x18003ba32  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x18003ba3a  xor     r8d, r8d; lpInBuffer
0x18003ba3d  mov     edx, 900A8h; dwIoControlCode
0x18003ba42  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOutBuffer
0x18003ba47  mov     rcx, rsi; hDevice
0x18003ba4a  call    cs:__imp_DeviceIoControl
0x18003ba50  test    eax, eax
0x18003ba52  jz      short loc_18003BA5B
0x18003ba54  mov     eax, [rdi]
0x18003ba56  mov     [r14], eax
0x18003ba59  jmp     short loc_18003BA6D
0x18003ba5b  call    cs:__imp_GetLastError
0x18003ba61  mov     ebx, eax
0x18003ba63  mov     eax, 1Fh
0x18003ba68  test    ebx, ebx
0x18003ba6a  cmovz   ebx, eax
0x18003ba6d  call    cs:__imp_GetProcessHeap
0x18003ba73  mov     r8, rdi; lpMem
0x18003ba76  xor     edx, edx; dwFlags
0x18003ba78  mov     rcx, rax; hHeap
0x18003ba7b  call    cs:__imp_HeapFree
0x18003ba81  jmp     short loc_18003BA88
0x18003ba83  mov     ebx, 0Eh
0x18003ba88  mov     rcx, rsi; hObject
0x18003ba8b  call    cs:__imp_CloseHandle
0x18003ba91  call    cs:__imp_GetProcessHeap
0x18003ba97  mov     r8, rbp; lpMem
0x18003ba9a  xor     edx, edx; dwFlags
0x18003ba9c  mov     rcx, rax; hHeap
0x18003ba9f  call    cs:__imp_HeapFree
0x18003baa5  jmp     short loc_18003BAB9
0x18003baa7  call    cs:__imp_GetLastError
0x18003baad  mov     ebx, eax
0x18003baaf  mov     eax, 1Fh
0x18003bab4  test    ebx, ebx
0x18003bab6  cmovz   ebx, eax
0x18003bab9  mov     ecx, ebx; dwErrCode
0x18003babb  call    cs:__imp_SetLastError
0x18003bac1  mov     rbp, [rsp+58h+arg_8]
0x18003bac6  xor     eax, eax
0x18003bac8  test    ebx, ebx
0x18003baca  mov     rbx, [rsp+58h+arg_0]
0x18003bacf  setz    al
0x18003bad2  add     rsp, 40h
0x18003bad6  pop     r14
0x18003bad8  pop     rdi
0x18003bad9  pop     rsi
0x18003bada  retn
```
