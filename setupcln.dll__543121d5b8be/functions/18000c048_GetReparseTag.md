# GetReparseTag

- ea: `0x18000c048`
- end: `0x18000c175`
- name: `GetReparseTag`
- size: `301`
- prototype: `_BOOL8 __fastcall(LPCWSTR lpFileName, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x18000bb18`
- `0x18000c1fc`

## callees

- `0x1800097e0`
- `0x18000a0f0`
- `0x18000c048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c155`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c155`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c0c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c112`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c112`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c136`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c120`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c144`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c120`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c130`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c130`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c099`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c099`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c0fa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000c0fa`

## pseudocode

```c
_BOOL8 __fastcall GetReparseTag(LPCWSTR lpFileName, _DWORD *a2)
{
  void *v4; // rbp
  DWORD v5; // ebx
  HANDLE FileW; // rsi
  HANDLE ProcessHeap; // rax
  _DWORD *v8; // rdi
  HANDLE v9; // rax
  HANDLE v10; // rax
  DWORD BytesReturned; // [rsp+70h] [rbp+18h] BYREF

  v4 = (void *)PrepareUnicodePathEx(lpFileName);
  if ( v4 )
  {
    v5 = 0;
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
          *a2 = *v8;
        else
          v5 = GET_LASTERROR_FORCE();
        v9 = GetProcessHeap();
        HeapFree(v9, 0, v8);
      }
      else
      {
        v5 = 14;
      }
      CloseHandle(FileW);
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v4);
  }
  else
  {
    v5 = GET_LASTERROR_FORCE();
  }
  SetLastError(v5);
  return v5 == 0;
}

```

## disassembly

```asm
0x18000c048  mov     [rsp+arg_0], rbx
0x18000c04d  mov     [rsp+arg_8], rbp
0x18000c052  push    rsi
0x18000c053  push    rdi
0x18000c054  push    r14
0x18000c056  sub     rsp, 40h
0x18000c05a  mov     r14, rdx
0x18000c05d  mov     rdi, rcx
0x18000c060  xor     edx, edx
0x18000c062  call    PrepareUnicodePathEx
0x18000c067  mov     rbp, rax
0x18000c06a  test    rax, rax
0x18000c06d  jz      loc_18000C14C
0x18000c073  xor     ebx, ebx
0x18000c075  xor     r9d, r9d; lpSecurityAttributes
0x18000c078  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x18000c07d  xor     edx, edx; dwDesiredAccess
0x18000c07f  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000c087  mov     rcx, rdi; lpFileName
0x18000c08a  mov     [r14], ebx
0x18000c08d  lea     r8d, [rbx+7]; dwShareMode
0x18000c091  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18000c099  call    cs:__imp_CreateFileW
0x18000c09f  mov     rsi, rax
0x18000c0a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c0a6  jz      loc_18000C136
0x18000c0ac  mov     [rsp+58h+BytesReturned], ebx
0x18000c0b0  call    cs:__imp_GetProcessHeap
0x18000c0b6  lea     edx, [rbx+8]; dwFlags
0x18000c0b9  mov     r8d, 4000h; dwBytes
0x18000c0bf  mov     rcx, rax; hHeap
0x18000c0c2  call    cs:__imp_HeapAlloc
0x18000c0c8  mov     rdi, rax
0x18000c0cb  test    rax, rax
0x18000c0ce  jz      short loc_18000C128
0x18000c0d0  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x18000c0d5  lea     rax, [rsp+58h+BytesReturned]
0x18000c0da  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x18000c0df  xor     r9d, r9d; nInBufferSize
0x18000c0e2  mov     [rsp+58h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x18000c0ea  xor     r8d, r8d; lpInBuffer
0x18000c0ed  mov     edx, 900A8h; dwIoControlCode
0x18000c0f2  mov     qword ptr [rsp+58h+dwCreationDisposition], rdi; lpOutBuffer
0x18000c0f7  mov     rcx, rsi; hDevice
0x18000c0fa  call    cs:__imp_DeviceIoControl
0x18000c100  test    eax, eax
0x18000c102  jz      short loc_18000C10B
0x18000c104  mov     eax, [rdi]
0x18000c106  mov     [r14], eax
0x18000c109  jmp     short loc_18000C112
0x18000c10b  call    GET_LASTERROR_FORCE
0x18000c110  mov     ebx, eax
0x18000c112  call    cs:__imp_GetProcessHeap
0x18000c118  mov     r8, rdi; lpMem
0x18000c11b  xor     edx, edx; dwFlags
0x18000c11d  mov     rcx, rax; hHeap
0x18000c120  call    cs:__imp_HeapFree
0x18000c126  jmp     short loc_18000C12D
0x18000c128  mov     ebx, 0Eh
0x18000c12d  mov     rcx, rsi; hObject
0x18000c130  call    cs:__imp_CloseHandle
0x18000c136  call    cs:__imp_GetProcessHeap
0x18000c13c  mov     r8, rbp; lpMem
0x18000c13f  xor     edx, edx; dwFlags
0x18000c141  mov     rcx, rax; hHeap
0x18000c144  call    cs:__imp_HeapFree
0x18000c14a  jmp     short loc_18000C153
0x18000c14c  call    GET_LASTERROR_FORCE
0x18000c151  mov     ebx, eax
0x18000c153  mov     ecx, ebx; dwErrCode
0x18000c155  call    cs:__imp_SetLastError
0x18000c15b  mov     rbp, [rsp+58h+arg_8]
0x18000c160  xor     eax, eax
0x18000c162  test    ebx, ebx
0x18000c164  mov     rbx, [rsp+58h+arg_0]
0x18000c169  setz    al
0x18000c16c  add     rsp, 40h
0x18000c170  pop     r14
0x18000c172  pop     rdi
0x18000c173  pop     rsi
0x18000c174  retn
```
