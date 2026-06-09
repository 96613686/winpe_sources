# StackLockFileWin32Base<StackLockFileReader>::ParseVerFromFile(void)

- ea: `0x18000f144`
- end: `0x18000f343`
- name: `?ParseVerFromFile@?$StackLockFileWin32Base@UStackLockFileReader@@@@IEBA_KXZ`
- size: `511`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000bf00`
- `0x180015af8`

## callees

- `0x180006614`
- `0x18000d908`
- `0x18000f144`
- `0x180025610`
- `0x180026a00`
- `0x18002829c`
- `0x180028514`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000f20f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000f20f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000f1d7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000f1d7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000f18b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000f18b`

## string_xrefs

- `0x18000f2aa`: `UUS version file wasn't fully read with the right amount of data (expected=%d actual=%d).`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StackLockFileWin32Base<StackLockFileReader>::ParseVerFromFile(__int64 a1)
{
  const char *v2; // r9
  const char *v4; // r9
  const char *v5; // r9
  __int64 v6; // rbx
  unsigned int v7; // eax
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // eax
  __int64 v11; // rdx
  const char *v12; // r8
  char *v13; // [rsp+28h] [rbp-D8h]
  _OWORD Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+68h] [rbp-98h] BYREF
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Buffer[256]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(*(HANDLE *)(a1 + 8), &FileSize) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x30,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      v2);
  if ( FileSize.QuadPart > 0xFFuLL )
  {
    v10 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x35,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      (const char *)v10,
      (int)"UUS version file larger than expected (%zu) - actual=%lld).",
      v12,
      v11);
  }
  if ( !FileSize.LowPart )
    return 0;
  if ( !SetFilePointerEx(*(HANDLE *)(a1 + 8), 0, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x40,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      v4);
  NumberOfBytesRead = 0;
  if ( !ReadFile(*(HANDLE *)(a1 + 8), Buffer, FileSize.LowPart, &NumberOfBytesRead, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x44,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      v5);
  if ( NumberOfBytesRead != FileSize.LowPart )
  {
    v7 = wil::verify_hresult<long>(2147549183LL);
    LODWORD(v13) = v8;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x47,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFileWin32.hpp",
      (const char *)v7,
      (int)"UUS version file wasn't fully read with the right amount of data (expected=%d actual=%d).",
      v13,
      v9);
  }
  memset(Src, 0, sizeof(Src));
  std::string::_Construct<1,char const *>(Src, Buffer, FileSize.LowPart);
  v6 = UusVersion::StrToVer<char>(Src);
  std::string::~string((__int64)Src);
  return v6;
}

```

## disassembly

```asm
0x18000f144  mov     [rsp-8+arg_8], rbx
0x18000f149  mov     [rsp-8+arg_10], rdi
0x18000f14e  push    rbp
0x18000f14f  lea     rbp, [rsp-90h]
0x18000f157  sub     rsp, 190h
0x18000f15e  mov     rax, cs:__security_cookie
0x18000f165  xor     rax, rsp
0x18000f168  mov     [rbp+90h+var_10], rax
0x18000f16f  mov     rbx, rcx
0x18000f172  mov     qword ptr [rsp+190h+FileSize], 0
0x18000f17b  mov     rdi, [rbp+98h]
0x18000f182  lea     rdx, [rsp+190h+FileSize]; lpFileSize
0x18000f187  mov     rcx, [rcx+8]; hFile
0x18000f18b  call    cs:__imp_GetFileSizeEx
0x18000f191  test    eax, eax
0x18000f193  jz      loc_18000F2C8
0x18000f199  mov     rdx, qword ptr [rsp+190h+FileSize]
0x18000f19e  mov     r8d, 0FFh
0x18000f1a4  cmp     rdx, r8
0x18000f1a7  ja      loc_18000F2DD
0x18000f1ad  test    edx, edx
0x18000f1af  jnz     short loc_18000F1B8
0x18000f1b1  xor     eax, eax
0x18000f1b3  jmp     loc_18000F269
0x18000f1b8  mov     qword ptr [rsp+190h+liDistanceToMove], 0
0x18000f1c1  mov     rdi, [rbp+98h]
0x18000f1c8  xor     r9d, r9d; dwMoveMethod
0x18000f1cb  xor     r8d, r8d; lpNewFilePointer
0x18000f1ce  mov     rdx, qword ptr [rsp+190h+liDistanceToMove]; liDistanceToMove
0x18000f1d3  mov     rcx, [rbx+8]; hFile
0x18000f1d7  call    cs:__imp_SetFilePointerEx
0x18000f1dd  test    eax, eax
0x18000f1df  jz      loc_18000F319
0x18000f1e5  mov     [rsp+190h+NumberOfBytesRead], 0
0x18000f1ed  mov     rdi, [rbp+98h]
0x18000f1f4  mov     [rsp+190h+lpOverlapped], 0; lpOverlapped
0x18000f1fd  lea     r9, [rsp+190h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000f202  mov     r8d, dword ptr [rsp+190h+FileSize]; nNumberOfBytesToRead
0x18000f207  lea     rdx, [rbp+90h+Buffer]; lpBuffer
0x18000f20b  mov     rcx, [rbx+8]; hFile
0x18000f20f  call    cs:__imp_ReadFile
0x18000f215  test    eax, eax
0x18000f217  jz      loc_18000F32E
0x18000f21d  mov     r8d, [rsp+190h+NumberOfBytesRead]
0x18000f222  mov     rdx, qword ptr [rsp+190h+FileSize]
0x18000f227  cmp     r8d, edx
0x18000f22a  jnz     short loc_18000F28D
0x18000f22c  xorps   xmm0, xmm0
0x18000f22f  movups  [rsp+190h+Src], xmm0
0x18000f234  xorps   xmm1, xmm1
0x18000f237  movdqu  [rsp+190h+var_138], xmm1
0x18000f23d  mov     r8d, edx
0x18000f240  lea     rdx, [rbp+90h+Buffer]
0x18000f244  lea     rcx, [rsp+190h+Src]
0x18000f249  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000f24e  nop
0x18000f24f  lea     rcx, [rsp+190h+Src]; Src
0x18000f254  call    ??$StrToVer@D@UusVersion@@SA_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; UusVersion::StrToVer<char>(std::string const &)
0x18000f259  mov     rbx, rax
0x18000f25c  lea     rcx, [rsp+190h+Src]
0x18000f261  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000f266  mov     rax, rbx
0x18000f269  mov     rcx, [rbp+90h+var_10]
0x18000f270  xor     rcx, rsp; StackCookie
0x18000f273  call    __security_check_cookie
0x18000f278  lea     r11, [rsp+190h+var_s0]
0x18000f280  mov     rbx, [r11+18h]
0x18000f284  mov     rdi, [r11+20h]
0x18000f288  mov     rsp, r11
0x18000f28b  pop     rbp
0x18000f28c  retn
0x18000f28d  mov     ecx, 8000FFFFh
0x18000f292  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000f297  mov     r9d, eax; char *
0x18000f29a  mov     rcx, [rbp+98h]; this
0x18000f2a1  mov     dword ptr [rsp+190h+var_160], r8d
0x18000f2a6  mov     dword ptr [rsp+190h+var_168], edx; char *
0x18000f2aa  lea     rax, aUusVersionFile; "UUS version file wasn't fully read with"...
0x18000f2b1  mov     [rsp+190h+lpOverlapped], rax; int
0x18000f2b6  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000f2bd  mov     edx, 47h ; 'G'; void *
0x18000f2c2  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000f2c8  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000f2cf  mov     edx, 30h ; '0'; void *
0x18000f2d4  mov     rcx, rdi; this
0x18000f2d7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000f2dd  mov     ecx, 8000FFFFh
0x18000f2e2  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000f2e7  mov     r9d, eax; char *
0x18000f2ea  mov     rcx, [rbp+98h]; this
0x18000f2f1  mov     [rsp+190h+var_160], rdx
0x18000f2f6  mov     [rsp+190h+var_168], r8; char *
0x18000f2fb  lea     rax, aUusVersionFile_1; "UUS version file larger than expected ("...
0x18000f302  mov     [rsp+190h+lpOverlapped], rax; int
0x18000f307  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000f30e  mov     edx, 35h ; '5'; void *
0x18000f313  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000f319  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000f320  mov     edx, 40h ; '@'; void *
0x18000f325  mov     rcx, rdi; this
0x18000f328  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000f32e  lea     r8, aCW1SSrcBrainLi_5; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x18000f335  mov     edx, 44h ; 'D'; void *
0x18000f33a  mov     rcx, rdi; this
0x18000f33d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
