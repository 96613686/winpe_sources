# FileUtils::ReadFileContent(std::filesystem::path const &,std::function<bool (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)> const &)

- ea: `0x1800349bc`
- end: `0x180034bd5`
- name: `?ReadFileContent@FileUtils@@SA_NAEBVpath@filesystem@std@@AEBV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@4@@Z`
- size: `537`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180034bdc`
- `0x180043340`
- `0x180043d60`
- `0x180044c10`
- `0x180045cb0`

## callees

- `0x180016db0`
- `0x1800349bc`
- `0x180034ca4`
- `0x1800352f0`
- `0x18006646c`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034bab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034bab`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180034b43`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180034b43`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180034ac2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180034ac2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180034a68`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180034a68`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034a12`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034a12`

## string_xrefs

- `0x180034a3c`: `Failed to open file: %ls`
- `0x180034acc`: `Failed to read BOM`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall FileUtils::ReadFileContent(char *a1)
{
  char *v1; // rdi
  char v2; // si
  char *FileW; // rax
  char *v4; // rbx
  unsigned int v5; // eax
  char v6; // di
  unsigned int v7; // eax
  LARGE_INTEGER v8; // rdx
  int v9; // edi
  unsigned int v10; // eax
  char LinesUtf16; // al
  const char *dwFlagsAndAttributesb; // [rsp+28h] [rbp-38h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-38h]
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-38h]
  __int16 Buffer; // [rsp+48h] [rbp-18h] BYREF
  char v17; // [rsp+4Ah] [rbp-16h]
  DWORD NumberOfBytesRead; // [rsp+4Ch] [rbp-14h] BYREF
  LARGE_INTEGER FileSize; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v1 = a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  v2 = 0;
  FileW = (char *)CreateFileW((LPCWSTR)a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(char **)v1;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x36,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\inc\\FileUtils.hpp",
    (const char *)((unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    "Failed to open file: %ls",
    v1);
  FileSize.QuadPart = 0;
  v5 = GetFileSizeEx(v4, &FileSize);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x3A,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\inc\\FileUtils.hpp",
    (const char *)v5,
    "Failed to get file size",
    dwFlagsAndAttributesb);
  if ( !FileSize.QuadPart )
  {
    v6 = 1;
    goto LABEL_22;
  }
  Buffer = 0;
  v17 = 0;
  NumberOfBytesRead = 0;
  v7 = ReadFile(v4, &Buffer, 3u, &NumberOfBytesRead, 0);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x46,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\inc\\FileUtils.hpp",
    (const char *)v7,
    "Failed to read BOM",
    dwFlagsAndAttributes);
  v8.QuadPart = 2;
  if ( NumberOfBytesRead < 2uLL )
    goto LABEL_12;
  if ( Buffer != -257 )
  {
    if ( Buffer == -2 )
    {
      v9 = 2;
      goto LABEL_17;
    }
LABEL_12:
    if ( NumberOfBytesRead < 3uLL || Buffer != -17425 || (v8.QuadPart = 3, v17 != -65) )
      v8.QuadPart = 0;
    v9 = 0;
    goto LABEL_17;
  }
  v9 = 1;
LABEL_17:
  v10 = SetFilePointerEx(v4, v8, 0, 0);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x4F,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\inc\\FileUtils.hpp",
    (const char *)v10,
    "Failed to seek past BOM",
    dwFlagsAndAttributesa);
  if ( v9 )
  {
    if ( (unsigned int)(v9 - 1) > 1 )
      goto LABEL_23;
    LinesUtf16 = FileUtils::ReadLinesUtf16(v4);
  }
  else
  {
    LinesUtf16 = FileUtils::ReadLinesUtf8(v4);
  }
  v6 = LinesUtf16;
LABEL_22:
  v2 = v6;
LABEL_23:
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  return v2;
}

```

## disassembly

```asm
0x1800349bc  mov     [rsp-18h+arg_10], rbx
0x1800349c1  mov     [rsp-18h+arg_18], rsi
0x1800349c6  push    rbp
0x1800349c7  push    rdi
0x1800349c8  push    r14
0x1800349ca  mov     rbp, rsp
0x1800349cd  sub     rsp, 60h
0x1800349d1  mov     rax, cs:__security_cookie
0x1800349d8  xor     rax, rsp
0x1800349db  mov     [rbp+var_8], rax
0x1800349df  mov     r14, rdx
0x1800349e2  mov     rdi, rcx
0x1800349e5  cmp     qword ptr [rcx+18h], 7
0x1800349ea  jbe     short loc_1800349EF
0x1800349ec  mov     rcx, [rcx]; lpFileName
0x1800349ef  xor     esi, esi
0x1800349f1  mov     [rsp+60h+hTemplateFile], rsi; hTemplateFile
0x1800349f6  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800349fe  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x180034a06  xor     r9d, r9d; lpSecurityAttributes
0x180034a09  mov     edx, 80000000h; dwDesiredAccess
0x180034a0e  lea     r8d, [rsi+7]; dwShareMode
0x180034a12  call    cs:__imp_CreateFileW
0x180034a18  mov     rbx, rax
0x180034a1b  mov     [rbp+var_20], rax
0x180034a1f  cmp     qword ptr [rdi+18h], 7
0x180034a24  jbe     short loc_180034A29
0x180034a26  mov     rdi, [rdi]
0x180034a29  dec     rax
0x180034a2c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034a30  setnbe  al
0x180034a33  mov     rcx, [rbp+18h]; this
0x180034a37  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rdi; char *
0x180034a3c  lea     rdx, aFailedToOpenFi; "Failed to open file: %ls"
0x180034a43  mov     qword ptr [rsp+60h+dwCreationDisposition], rdx; void *
0x180034a48  movzx   r9d, al; char *
0x180034a4c  lea     r8, aCW1SSrcCalliop_8; "C:\\__w\\1\\s\\src\\Calliope\\libs\\inc"...
0x180034a53  mov     edx, 36h ; '6'; void *
0x180034a58  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180034a5d  mov     qword ptr [rbp+FileSize], rsi
0x180034a61  lea     rdx, [rbp+FileSize]; lpFileSize
0x180034a65  mov     rcx, rbx; hFile
0x180034a68  call    cs:__imp_GetFileSizeEx
0x180034a6e  mov     rcx, [rbp+18h]; this
0x180034a72  lea     rdx, aFailedToGetFil; "Failed to get file size"
0x180034a79  mov     qword ptr [rsp+60h+dwCreationDisposition], rdx; void *
0x180034a7e  mov     r9d, eax; char *
0x180034a81  lea     r8, aCW1SSrcCalliop_8; "C:\\__w\\1\\s\\src\\Calliope\\libs\\inc"...
0x180034a88  mov     edx, 3Ah ; ':'; void *
0x180034a8d  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180034a92  cmp     qword ptr [rbp+FileSize], rsi
0x180034a96  jnz     short loc_180034AA2
0x180034a98  mov     edi, 1
0x180034a9d  jmp     loc_180034B9B
0x180034aa2  xor     eax, eax
0x180034aa4  mov     [rbp+Buffer], ax
0x180034aa8  mov     [rbp+var_16], al
0x180034aab  mov     [rbp+NumberOfBytesRead], esi
0x180034aae  mov     qword ptr [rsp+60h+dwCreationDisposition], rsi; lpOverlapped
0x180034ab3  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180034ab7  lea     r8d, [rax+3]; nNumberOfBytesToRead
0x180034abb  lea     rdx, [rbp+Buffer]; lpBuffer
0x180034abf  mov     rcx, rbx; hFile
0x180034ac2  call    cs:__imp_ReadFile
0x180034ac8  mov     rcx, [rbp+18h]; this
0x180034acc  lea     rdx, aFailedToReadBo; "Failed to read BOM"
0x180034ad3  mov     qword ptr [rsp+60h+dwCreationDisposition], rdx; void *
0x180034ad8  mov     r9d, eax; char *
0x180034adb  lea     r8, aCW1SSrcCalliop_8; "C:\\__w\\1\\s\\src\\Calliope\\libs\\inc"...
0x180034ae2  mov     edx, 46h ; 'F'; void *
0x180034ae7  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180034aec  mov     r8d, [rbp+NumberOfBytesRead]
0x180034af0  mov     al, byte ptr [rbp+Buffer+1]
0x180034af3  mov     cl, byte ptr [rbp+Buffer]
0x180034af6  mov     edx, 2
0x180034afb  cmp     r8, rdx
0x180034afe  jb      short loc_180034B1B
0x180034b00  cmp     cl, 0FFh
0x180034b03  jnz     short loc_180034B0E
0x180034b05  cmp     al, 0FEh
0x180034b07  jnz     short loc_180034B0E
0x180034b09  lea     edi, [rdx-1]
0x180034b0c  jmp     short loc_180034B3A
0x180034b0e  cmp     cl, 0FEh
0x180034b11  jnz     short loc_180034B1B
0x180034b13  cmp     al, 0FFh
0x180034b15  jnz     short loc_180034B1B
0x180034b17  mov     edi, edx
0x180034b19  jmp     short loc_180034B3A
0x180034b1b  cmp     r8, 3
0x180034b1f  jb      short loc_180034B35
0x180034b21  cmp     cl, 0EFh
0x180034b24  jnz     short loc_180034B35
0x180034b26  cmp     al, 0BBh
0x180034b28  jnz     short loc_180034B35
0x180034b2a  cmp     [rbp+var_16], 0BFh
0x180034b2e  mov     edx, 3
0x180034b33  jz      short loc_180034B38
0x180034b35  mov     rdx, rsi; liDistanceToMove
0x180034b38  mov     edi, esi
0x180034b3a  xor     r9d, r9d; dwMoveMethod
0x180034b3d  xor     r8d, r8d; lpNewFilePointer
0x180034b40  mov     rcx, rbx; hFile
0x180034b43  call    cs:__imp_SetFilePointerEx
0x180034b49  mov     rcx, [rbp+18h]; this
0x180034b4d  lea     rdx, aFailedToSeekPa; "Failed to seek past BOM"
0x180034b54  mov     qword ptr [rsp+60h+dwCreationDisposition], rdx; void *
0x180034b59  mov     r9d, eax; char *
0x180034b5c  lea     r8, aCW1SSrcCalliop_8; "C:\\__w\\1\\s\\src\\Calliope\\libs\\inc"...
0x180034b63  mov     edx, 4Fh ; 'O'; void *
0x180034b68  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180034b6d  mov     ecx, edi
0x180034b6f  test    edi, edi
0x180034b71  jz      short loc_180034B8D
0x180034b73  sub     ecx, 1
0x180034b76  jz      short loc_180034B7D
0x180034b78  cmp     ecx, 1
0x180034b7b  jnz     short loc_180034B9E
0x180034b7d  mov     r8d, edi
0x180034b80  mov     rdx, r14
0x180034b83  mov     rcx, rbx; hFile
0x180034b86  call    ?ReadLinesUtf16@FileUtils@@SA_NPEAXAEBV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@std@@W4FileEncoding@1@@Z; FileUtils::ReadLinesUtf16(void *,std::function<bool (std::wstring_view)> const &,FileUtils::FileEncoding)
0x180034b8b  jmp     short loc_180034B98
0x180034b8d  mov     rdx, r14
0x180034b90  mov     rcx, rbx; hFile
0x180034b93  call    ?ReadLinesUtf8@FileUtils@@SA_NPEAXAEBV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@std@@@Z; FileUtils::ReadLinesUtf8(void *,std::function<bool (std::wstring_view)> const &)
0x180034b98  mov     dil, al
0x180034b9b  mov     sil, dil
0x180034b9e  lea     rcx, [rbx-1]
0x180034ba2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180034ba6  ja      short loc_180034BB1
0x180034ba8  mov     rcx, rbx; hObject
0x180034bab  call    cs:__imp_CloseHandle
0x180034bb1  mov     al, sil
0x180034bb4  mov     rcx, [rbp+var_8]
0x180034bb8  xor     rcx, rsp; StackCookie
0x180034bbb  call    __security_check_cookie
0x180034bc0  lea     r11, [rsp+60h+var_s0]
0x180034bc5  mov     rbx, [r11+30h]
0x180034bc9  mov     rsi, [r11+38h]
0x180034bcd  mov     rsp, r11
0x180034bd0  pop     r14
0x180034bd2  pop     rdi
0x180034bd3  pop     rbp
0x180034bd4  retn
```
