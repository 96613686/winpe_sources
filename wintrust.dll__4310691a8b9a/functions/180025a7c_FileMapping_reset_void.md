# FileMapping::reset(void *)

- ea: `0x180025a7c`
- end: `0x180025b3d`
- name: `?reset@FileMapping@@QEAAJPEAX@Z`
- size: `193`
- prototype: `int(FileMapping *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180040d58`

## callees

- `0x180025a7c`
- `0x180025b44`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180025ab9`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180025ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ac3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180025afd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180025afd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180025b21`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180025b21`

## pseudocode

```c
int __fastcall FileMapping::reset(SIZE_T *this, void *a2)
{
  int result; // eax
  HANDLE FileMappingW; // rax
  LPVOID v6; // rax
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp+8h] BYREF

  FileMapping::cleanup((FileMapping *)this);
  *this = 0;
  this[1] = 0;
  this[2] = 0;
  FileSize.QuadPart = 0;
  if ( GetFileSizeEx(a2, &FileSize) )
  {
    this[2] = FileSize.QuadPart;
    FileMappingW = CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
    *this = (SIZE_T)FileMappingW;
    if ( FileMappingW )
    {
      v6 = MapViewOfFile(FileMappingW, 4u, 0, 0, this[2]);
      this[1] = (SIZE_T)v6;
      if ( v6 )
        return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025a7c  mov     [rsp+arg_8], rbx
0x180025a81  push    rdi
0x180025a82  sub     rsp, 30h
0x180025a86  mov     rdi, rdx
0x180025a89  mov     rbx, rcx
0x180025a8c  call    ?cleanup@FileMapping@@AEAAXXZ; FileMapping::cleanup(void)
0x180025a91  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x180025a96  mov     qword ptr [rbx], 0
0x180025a9d  mov     rcx, rdi; hFile
0x180025aa0  mov     qword ptr [rbx+8], 0
0x180025aa8  mov     qword ptr [rbx+10h], 0
0x180025ab0  mov     qword ptr [rsp+38h+FileSize], 0
0x180025ab9  call    cs:__imp_GetFileSizeEx
0x180025abf  test    eax, eax
0x180025ac1  jnz     short loc_180025AD7
0x180025ac3  call    cs:__imp_GetLastError
0x180025ac9  test    eax, eax
0x180025acb  jle     short loc_180025B32
0x180025acd  movzx   eax, ax
0x180025ad0  or      eax, 80070000h
0x180025ad5  jmp     short loc_180025B32
0x180025ad7  mov     rax, qword ptr [rsp+38h+FileSize]
0x180025adc  xor     r9d, r9d; dwMaximumSizeHigh
0x180025adf  mov     [rsp+38h+lpName], 0; lpName
0x180025ae8  xor     edx, edx; lpFileMappingAttributes
0x180025aea  mov     rcx, rdi; hFile
0x180025aed  mov     [rbx+10h], rax
0x180025af1  mov     [rsp+38h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x180025af9  lea     r8d, [r9+2]; flProtect
0x180025afd  call    cs:__imp_CreateFileMappingW
0x180025b03  mov     [rbx], rax
0x180025b06  mov     rcx, rax; hFileMappingObject
0x180025b09  test    rax, rax
0x180025b0c  jz      short loc_180025AC3
0x180025b0e  mov     rax, [rbx+10h]
0x180025b12  xor     r9d, r9d; dwFileOffsetLow
0x180025b15  xor     r8d, r8d; dwFileOffsetHigh
0x180025b18  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x180025b1d  lea     edx, [r9+4]; dwDesiredAccess
0x180025b21  call    cs:__imp_MapViewOfFile
0x180025b27  mov     [rbx+8], rax
0x180025b2b  test    rax, rax
0x180025b2e  jz      short loc_180025AC3
0x180025b30  xor     eax, eax
0x180025b32  mov     rbx, [rsp+38h+arg_8]
0x180025b37  add     rsp, 30h
0x180025b3b  pop     rdi
0x180025b3c  retn
```
