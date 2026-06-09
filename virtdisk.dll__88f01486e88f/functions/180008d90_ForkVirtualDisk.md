# ForkVirtualDisk

- ea: `0x180008d90`
- end: `0x180008f5e`
- name: `ForkVirtualDisk`
- size: `462`
- prototype: `__int64 __fastcall(char *, int, __int64, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x180008d90`
- `0x18000ada0`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008eea`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008eb8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180008eb8`
- `ntdll!RtlFreeHeap` at `0x180008f1b`
- `ntdll!RtlFreeHeap` at `0x180008f3e`
- `ntdll!RtlFreeHeap` at `0x180008f1b`
- `ntdll!RtlFreeHeap` at `0x180008f3e`
- `ntdll!RtlAllocateHeap` at `0x180008e4f`
- `ntdll!RtlAllocateHeap` at `0x180008e4f`

## pseudocode

```c
__int64 __fastcall ForkVirtualDisk(char *a1, int a2, __int64 a3, struct _OVERLAPPED *a4)
{
  void *v4; // rsi
  void *v5; // r14
  unsigned int LastError; // ebx
  char v8; // bp
  LPCWSTR *v9; // rdi
  const WCHAR *v10; // rcx
  DWORD v11; // r8d
  size_t v12; // r15
  DWORD v13; // r13d
  _DWORD *Heap; // rax
  size_t Size; // [rsp+40h] [rbp-58h] BYREF
  void *Src; // [rsp+48h] [rbp-50h] BYREF

  v4 = 0;
  v5 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = 6;
  }
  else
  {
    if ( (a2 & 0xFFFFFFFE) != 0 )
      return 87;
    if ( !a3 )
      return 87;
    v8 = 1;
    if ( *(_DWORD *)a3 != 1 )
      return 87;
    v9 = (LPCWSTR *)(a3 + 8);
    v10 = *(const WCHAR **)(a3 + 8);
    if ( !v10 || !a4 )
      return 87;
    if ( (a2 & 1) != 0 )
    {
      v8 = 0;
      v11 = 3;
    }
    else
    {
      v11 = 1;
    }
    LastError = ValidateFile(v10, 0xC0000000, v11, (__int64)a4, (LPWSTR *)&Src, (DWORD *)&Size);
    if ( LastError )
    {
      v4 = Src;
    }
    else
    {
      v12 = (unsigned int)Size;
      v13 = Size + 8;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)(Size + 8));
      v4 = Src;
      v5 = Heap;
      if ( Heap )
      {
        *Heap = 8;
        Heap[1] = v12;
        memcpy_0(Heap + 2, v4, v12);
        if ( !DeviceIoControl(a1, 0x2D1954u, v5, v13, 0, 0, 0, a4) )
          LastError = GetLastError();
      }
      else
      {
        LastError = 14;
      }
      if ( v8 && LastError && LastError != 997 )
        DeleteFileW(*v9);
    }
  }
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return LastError;
}

```

## disassembly

```asm
0x180008d90  mov     [rsp+hDevice], rcx
0x180008d95  push    rbx
0x180008d96  push    rbp
0x180008d97  push    rsi
0x180008d98  push    rdi
0x180008d99  push    r12
0x180008d9b  push    r13
0x180008d9d  push    r14
0x180008d9f  push    r15
0x180008da1  sub     rsp, 58h
0x180008da5  xor     esi, esi
0x180008da7  lea     rax, [rcx-1]
0x180008dab  xor     r14d, r14d
0x180008dae  mov     [rsp+98h+Src], rsi
0x180008db3  mov     dword ptr [rsp+98h+Size], esi
0x180008db7  mov     r12, r9
0x180008dba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008dbe  ja      loc_180008EFF
0x180008dc4  test    edx, 0FFFFFFFEh
0x180008dca  jz      short loc_180008DD6
0x180008dcc  mov     ebx, 57h ; 'W'
0x180008dd1  jmp     loc_180008F4A
0x180008dd6  test    r8, r8
0x180008dd9  jz      short loc_180008DCC
0x180008ddb  mov     ebp, 1
0x180008de0  cmp     [r8], ebp
0x180008de3  jnz     short loc_180008DCC
0x180008de5  lea     rdi, [r8+8]
0x180008de9  mov     rcx, [rdi]; lpFileName
0x180008dec  test    rcx, rcx
0x180008def  jz      short loc_180008DCC
0x180008df1  test    r12, r12
0x180008df4  jz      short loc_180008DCC
0x180008df6  lea     rax, [rsp+98h+Size]
0x180008dfb  test    bpl, dl
0x180008dfe  mov     qword ptr [rsp+98h+nOutBufferSize], rax; __int64
0x180008e03  mov     edx, 0C0000000h
0x180008e08  lea     rax, [rsp+98h+Src]
0x180008e0d  mov     [rsp+98h+lpOutBuffer], rax; __int64
0x180008e12  jnz     short loc_180008E19
0x180008e14  mov     r8d, ebp
0x180008e17  jmp     short loc_180008E22
0x180008e19  xor     bpl, bpl
0x180008e1c  mov     r8d, 3
0x180008e22  call    ValidateFile
0x180008e27  mov     ebx, eax
0x180008e29  test    eax, eax
0x180008e2b  jnz     loc_180008EF8
0x180008e31  mov     rcx, gs:60h
0x180008e3a  mov     edx, 8; Flags
0x180008e3f  mov     r15d, dword ptr [rsp+98h+Size]
0x180008e44  mov     rcx, [rcx+30h]; HeapHandle
0x180008e48  lea     r13d, [r15+8]
0x180008e4c  mov     r8d, r13d; Size
0x180008e4f  call    cs:__imp_RtlAllocateHeap
0x180008e56  nop     dword ptr [rax+rax+00h]
0x180008e5b  mov     rsi, [rsp+98h+Src]
0x180008e60  mov     r14, rax
0x180008e63  test    rax, rax
0x180008e66  jnz     short loc_180008E6D
0x180008e68  lea     ebx, [rax+0Eh]
0x180008e6b  jmp     short loc_180008ED6
0x180008e6d  mov     r8, r15; Size
0x180008e70  mov     dword ptr [rax], 8
0x180008e76  lea     rcx, [rax+8]; void *
0x180008e7a  mov     [rax+4], r15d
0x180008e7e  mov     rdx, rsi; Src
0x180008e81  call    memcpy_0
0x180008e86  mov     rcx, [rsp+98h+hDevice]; hDevice
0x180008e8e  mov     r9d, r13d; nInBufferSize
0x180008e91  mov     [rsp+98h+lpOverlapped], r12; lpOverlapped
0x180008e96  mov     r8, r14; lpInBuffer
0x180008e99  mov     [rsp+98h+lpBytesReturned], 0; lpBytesReturned
0x180008ea2  mov     edx, 2D1954h; dwIoControlCode
0x180008ea7  mov     [rsp+98h+nOutBufferSize], 0; nOutBufferSize
0x180008eaf  mov     [rsp+98h+lpOutBuffer], 0; lpOutBuffer
0x180008eb8  call    cs:__imp_DeviceIoControl
0x180008ebf  nop     dword ptr [rax+rax+00h]
0x180008ec4  test    eax, eax
0x180008ec6  jnz     short loc_180008ED6
0x180008ec8  call    cs:__imp_GetLastError
0x180008ecf  nop     dword ptr [rax+rax+00h]
0x180008ed4  mov     ebx, eax
0x180008ed6  test    bpl, bpl
0x180008ed9  jz      short loc_180008F04
0x180008edb  test    ebx, ebx
0x180008edd  jz      short loc_180008F04
0x180008edf  cmp     ebx, 3E5h
0x180008ee5  jz      short loc_180008F04
0x180008ee7  mov     rcx, [rdi]; lpFileName
0x180008eea  call    cs:__imp_DeleteFileW
0x180008ef1  nop     dword ptr [rax+rax+00h]
0x180008ef6  jmp     short loc_180008F04
0x180008ef8  mov     rsi, [rsp+98h+Src]
0x180008efd  jmp     short loc_180008F04
0x180008eff  mov     ebx, 6
0x180008f04  test    rsi, rsi
0x180008f07  jz      short loc_180008F27
0x180008f09  mov     rcx, gs:60h
0x180008f12  mov     r8, rsi; P
0x180008f15  xor     edx, edx; Flags
0x180008f17  mov     rcx, [rcx+30h]; HeapHandle
0x180008f1b  call    cs:__imp_RtlFreeHeap
0x180008f22  nop     dword ptr [rax+rax+00h]
0x180008f27  test    r14, r14
0x180008f2a  jz      short loc_180008F4A
0x180008f2c  mov     rcx, gs:60h
0x180008f35  mov     r8, r14; P
0x180008f38  xor     edx, edx; Flags
0x180008f3a  mov     rcx, [rcx+30h]; HeapHandle
0x180008f3e  call    cs:__imp_RtlFreeHeap
0x180008f45  nop     dword ptr [rax+rax+00h]
0x180008f4a  mov     eax, ebx
0x180008f4c  add     rsp, 58h
0x180008f50  pop     r15
0x180008f52  pop     r14
0x180008f54  pop     r13
0x180008f56  pop     r12
0x180008f58  pop     rdi
0x180008f59  pop     rsi
0x180008f5a  pop     rbp
0x180008f5b  pop     rbx
0x180008f5c  retn
```
