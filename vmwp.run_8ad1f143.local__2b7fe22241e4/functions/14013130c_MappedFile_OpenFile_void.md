# MappedFile::OpenFile(void *)

- ea: `0x14013130c`
- end: `0x140131433`
- name: `?OpenFile@MappedFile@@QEAAXPEAX@Z`
- size: `295`
- prototype: `void(MappedFile *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140131258`

## callees

- `0x14005b648`
- `0x140084204`
- `0x14013130c`
- `0x140132960`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14013133c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14013133c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1401313d7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1401313d7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140131387`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140131387`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1401313f0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1401313f0`

## string_xrefs

- `0x140131351`: `onecore\vm\common\guestloader\inc\MappedFile.h`
- `0x1401313b2`: `onecore\vm\common\guestloader\inc\MappedFile.h`
- `0x140131408`: `onecore\vm\common\guestloader\inc\MappedFile.h`

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
0x14013130c  mov     [rsp+arg_10], rbx
0x140131311  push    rdi
0x140131312  sub     rsp, 40h
0x140131316  mov     rax, cs:__security_cookie
0x14013131d  xor     rax, rsp
0x140131320  mov     [rsp+48h+var_10], rax
0x140131325  mov     rdi, rdx
0x140131328  mov     qword ptr [rsp+48h+FileSize], 0
0x140131331  mov     rbx, rcx
0x140131334  lea     rdx, [rsp+48h+FileSize]; lpFileSize
0x140131339  mov     rcx, rdi; hFile
0x14013133c  call    cs:__imp_GetFileSizeEx
0x140131343  nop     dword ptr [rax+rax+00h]
0x140131348  test    eax, eax
0x14013134a  jnz     short loc_140131361
0x14013134c  mov     rcx, [rsp+48h]; this
0x140131351  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x140131358  lea     edx, [rax+35h]; void *
0x14013135b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131361  mov     rax, qword ptr [rsp+48h+FileSize]
0x140131366  xor     r9d, r9d; dwMaximumSizeHigh
0x140131369  mov     [rsp+48h+lpName], 0; lpName
0x140131372  xor     edx, edx; lpFileMappingAttributes
0x140131374  mov     rcx, rdi; hFile
0x140131377  mov     [rbx+10h], rax
0x14013137b  mov     [rsp+48h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x140131383  lea     r8d, [r9+2]; flProtect
0x140131387  call    cs:__imp_CreateFileMappingW
0x14013138e  nop     dword ptr [rax+rax+00h]
0x140131393  mov     rdx, rax
0x140131396  mov     rcx, rbx
0x140131399  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14013139e  mov     rcx, [rbx]; hFileMappingObject
0x1401313a1  lea     rax, [rcx+1]
0x1401313a5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1401313ab  jnz     short loc_1401313C4
0x1401313ad  mov     rcx, [rsp+48h]; this
0x1401313b2  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x1401313b9  mov     edx, 3Fh ; '?'; void *
0x1401313be  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401313c4  xor     r9d, r9d; dwFileOffsetLow
0x1401313c7  mov     qword ptr [rsp+48h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1401313d0  xor     r8d, r8d; dwFileOffsetHigh
0x1401313d3  lea     edx, [r9+4]; dwDesiredAccess
0x1401313d7  call    cs:__imp_MapViewOfFile
0x1401313de  nop     dword ptr [rax+rax+00h]
0x1401313e3  mov     rcx, [rbx+8]; lpBaseAddress
0x1401313e7  mov     [rbx+8], rax
0x1401313eb  test    rcx, rcx
0x1401313ee  jz      short loc_1401313FC
0x1401313f0  call    cs:__imp_UnmapViewOfFile
0x1401313f7  nop     dword ptr [rax+rax+00h]
0x1401313fc  cmp     qword ptr [rbx+8], 0
0x140131401  jnz     short loc_14013141A
0x140131403  mov     rcx, [rsp+48h]; this
0x140131408  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\guestloader\\inc\\"...
0x14013140f  mov     edx, 47h ; 'G'; void *
0x140131414  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013141a  mov     rcx, [rsp+48h+var_10]
0x14013141f  xor     rcx, rsp; StackCookie
0x140131422  call    __security_check_cookie
0x140131427  mov     rbx, [rsp+48h+arg_10]
0x14013142c  add     rsp, 40h
0x140131430  pop     rdi
0x140131431  retn
```
