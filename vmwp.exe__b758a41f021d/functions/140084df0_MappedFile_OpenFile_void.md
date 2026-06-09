# MappedFile::OpenFile(void *)

- ea: `0x140084df0`
- end: `0x140084f17`
- name: `?OpenFile@MappedFile@@QEAAXPEAX@Z`
- size: `295`
- prototype: `void(MappedFile *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140085c30`

## callees

- `0x140083990`
- `0x140084df0`
- `0x140085634`
- `0x14011ea40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140084e20`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140084e20`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140084e6b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140084e6b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140084ebb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140084ebb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140084ed4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140084ed4`

## string_xrefs

- `0x140084e35`: `onecore\vm\common\guestloader\inc\MappedFile.h`
- `0x140084e96`: `onecore\vm\common\guestloader\inc\MappedFile.h`
- `0x140084eec`: `onecore\vm\common\guestloader\inc\MappedFile.h`

## pseudocode

```c
void __fastcall MappedFile::OpenFile(union _LARGE_INTEGER *this, void *a2)
{
  const char *v4; // r9
  const char *v5; // r9
  LPVOID v6; // rax
  const char *v7; // r9
  const void *QuadPart; // rcx
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(a2, &FileSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\vm\\common\\guestloader\\inc\\MappedFile.h",
      v4);
  this[2] = FileSize;
  CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(this);
  if ( ((this->QuadPart + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\vm\\common\\guestloader\\inc\\MappedFile.h",
      v5);
  v6 = MapViewOfFile((HANDLE)this->QuadPart, 4u, 0, 0, 0);
  QuadPart = (const void *)this[1].QuadPart;
  this[1].QuadPart = (LONGLONG)v6;
  if ( QuadPart )
    UnmapViewOfFile(QuadPart);
  if ( !this[1].QuadPart )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\vm\\common\\guestloader\\inc\\MappedFile.h",
      v7);
}

```

## disassembly

```asm
0x140084df0  mov     [rsp+arg_10], rbx
0x140084df5  push    rdi
0x140084df6  sub     rsp, 40h
0x140084dfa  mov     rax, cs:__security_cookie
0x140084e01  xor     rax, rsp
0x140084e04  mov     [rsp+48h+var_10], rax
0x140084e09  mov     rdi, rdx
0x140084e0c  mov     qword ptr [rsp+48h+FileSize], 0
0x140084e15  mov     rbx, rcx
0x140084e18  lea     rdx, [rsp+48h+FileSize]; lpFileSize
0x140084e1d  mov     rcx, rdi; hFile
0x140084e20  call    cs:__imp_GetFileSizeEx
0x140084e27  nop     dword ptr [rax+rax+00h]
0x140084e2c  test    eax, eax
0x140084e2e  jnz     short loc_140084E45
0x140084e30  mov     rcx, [rsp+48h]; this
0x140084e35  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x140084e3c  lea     edx, [rax+35h]; void *
0x140084e3f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140084e45  mov     rax, qword ptr [rsp+48h+FileSize]
0x140084e4a  xor     r9d, r9d; dwMaximumSizeHigh
0x140084e4d  mov     [rsp+48h+lpName], 0; lpName
0x140084e56  xor     edx, edx; lpFileMappingAttributes
0x140084e58  mov     rcx, rdi; hFile
0x140084e5b  mov     [rbx+10h], rax
0x140084e5f  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x140084e67  lea     r8d, [r9+2]; flProtect
0x140084e6b  call    cs:__imp_CreateFileMappingW
0x140084e72  nop     dword ptr [rax+rax+00h]
0x140084e77  mov     rdx, rax
0x140084e7a  mov     rcx, rbx
0x140084e7d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140084e82  mov     rcx, [rbx]; hFileMappingObject
0x140084e85  lea     rax, [rcx+1]
0x140084e89  test    rax, 0FFFFFFFFFFFFFFFEh
0x140084e8f  jnz     short loc_140084EA8
0x140084e91  mov     rcx, [rsp+48h]; this
0x140084e96  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x140084e9d  mov     edx, 3Fh ; '?'; void *
0x140084ea2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140084ea8  xor     r9d, r9d; dwFileOffsetLow
0x140084eab  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x140084eb4  xor     r8d, r8d; dwFileOffsetHigh
0x140084eb7  lea     edx, [r9+4]; dwDesiredAccess
0x140084ebb  call    cs:__imp_MapViewOfFile
0x140084ec2  nop     dword ptr [rax+rax+00h]
0x140084ec7  mov     rcx, [rbx+8]; lpBaseAddress
0x140084ecb  mov     [rbx+8], rax
0x140084ecf  test    rcx, rcx
0x140084ed2  jz      short loc_140084EE0
0x140084ed4  call    cs:__imp_UnmapViewOfFile
0x140084edb  nop     dword ptr [rax+rax+00h]
0x140084ee0  cmp     qword ptr [rbx+8], 0
0x140084ee5  jnz     short loc_140084EFE
0x140084ee7  mov     rcx, [rsp+48h]; this
0x140084eec  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x140084ef3  mov     edx, 47h ; 'G'; void *
0x140084ef8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140084efe  mov     rcx, [rsp+48h+var_10]
0x140084f03  xor     rcx, rsp; StackCookie
0x140084f06  call    __security_check_cookie
0x140084f0b  mov     rbx, [rsp+48h+arg_10]
0x140084f10  add     rsp, 40h
0x140084f14  pop     rdi
0x140084f15  retn
```
