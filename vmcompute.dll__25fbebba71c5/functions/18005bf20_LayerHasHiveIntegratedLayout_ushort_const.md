# LayerHasHiveIntegratedLayout(ushort const *)

- ea: `0x18005bf20`
- end: `0x18005c13f`
- name: `?LayerHasHiveIntegratedLayout@@YA_NPEBG@Z`
- size: `543`
- prototype: `bool __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005c3e8`

## callees

- `0x180002f50`
- `0x18000481d`
- `0x180006660`
- `0x18000d0ec`
- `0x180022d10`
- `0x18002d058`
- `0x18002e7b8`
- `0x18002f94c`
- `0x18005bf20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bfbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005bfbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bfdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c0bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bfdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c0bb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005c01e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005c01e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005bf95`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005bf95`

## string_xrefs

- `0x18005c106`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x18005c118`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x18005c12d`: `onecore\vm\compute\shared\storage\layerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall LayerHasHiveIntegratedLayout(PCWSTR pszPathIn)
{
  const WCHAR *v1; // rcx
  char *FileW; // rbx
  const char *v3; // r9
  const char *v5; // r9
  void **v6; // rdx
  size_t v7; // r8
  void **v8; // rcx
  bool v9; // di
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  void *Buf1[2]; // [rsp+40h] [rbp-C0h] BYREF
  size_t Size[2]; // [rsp+50h] [rbp-B0h]
  char *v13; // [rsp+60h] [rbp-A0h]
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Buffer[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  Vml::CombineFilePath(lpFileName, pszPathIn, L"layout");
  v1 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v1 = lpFileName[0];
  FileW = (char *)CreateFileW(v1, 0x80000000, 1u, 0, 3u, 0, 0);
  v13 = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    NumberOfBytesRead = 0;
    if ( !ReadFile(FileW, Buffer, 0x100u, &NumberOfBytesRead, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v5);
    *(_OWORD *)Buf1 = 0;
    *(_OWORD *)Size = 0;
    std::string::_Construct<1,char const *>(Buf1, Buffer, NumberOfBytesRead);
    v6 = &Buf2;
    if ( (unsigned __int64)qword_1800BDDA0 > 0xF )
      v6 = (void **)Buf2;
    v7 = Size[0];
    v8 = Buf1;
    if ( Size[1] > 0xF )
      v8 = (void **)Buf1[0];
    v9 = Size[0] != qword_1800BDD98 || Size[0] && memcmp_0(v8, v6, Size[0]);
    std::string::~string(Buf1, v6, v7);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        (const char *)0xC0370112LL,
        dwCreationDisposition);
    CloseHandle(FileW);
    std::wstring::~wstring(lpFileName);
    return 1;
  }
  else
  {
    if ( GetLastError() != 2 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v3);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    std::wstring::~wstring(lpFileName);
    return 0;
  }
}

```

## disassembly

```asm
0x18005bf20  mov     [rsp-8+arg_8], rbx
0x18005bf25  mov     [rsp-8+arg_10], rdi
0x18005bf2a  push    rbp
0x18005bf2b  lea     rbp, [rsp-0A0h]
0x18005bf33  sub     rsp, 1A0h
0x18005bf3a  mov     rax, cs:__security_cookie
0x18005bf41  xor     rax, rsp
0x18005bf44  mov     [rbp+0A0h+var_10], rax
0x18005bf4b  lea     r8, aLayout; "layout"
0x18005bf52  mov     rdx, rcx; pszPathIn
0x18005bf55  lea     rcx, [rsp+1A0h+lpFileName]; Src
0x18005bf5a  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18005bf5f  nop
0x18005bf60  lea     rcx, [rsp+1A0h+lpFileName]
0x18005bf65  cmp     [rbp+0A0h+var_118], 7
0x18005bf6a  cmova   rcx, [rsp+1A0h+lpFileName]; lpFileName
0x18005bf70  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x18005bf79  mov     [rsp+1A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18005bf81  mov     [rsp+1A0h+dwCreationDisposition], 3; dwCreationDisposition
0x18005bf89  xor     r9d, r9d; lpSecurityAttributes
0x18005bf8c  mov     edx, 80000000h; dwDesiredAccess
0x18005bf91  lea     r8d, [r9+1]; dwShareMode
0x18005bf95  call    cs:__imp_CreateFileW
0x18005bf9c  nop     dword ptr [rax+rax+00h]
0x18005bfa1  mov     rbx, rax
0x18005bfa4  mov     [rsp+1A0h+var_140], rax
0x18005bfa9  inc     rax
0x18005bfac  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005bfb2  jnz     short loc_18005BFFB
0x18005bfb4  mov     rdi, [rbp+0A8h]
0x18005bfbb  call    cs:__imp_GetLastError
0x18005bfc2  nop     dword ptr [rax+rax+00h]
0x18005bfc7  cmp     eax, 2
0x18005bfca  jnz     loc_18005C118
0x18005bfd0  lea     rax, [rbx-1]
0x18005bfd4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005bfd8  ja      short loc_18005BFEA
0x18005bfda  mov     rcx, rbx; hObject
0x18005bfdd  call    cs:__imp_CloseHandle
0x18005bfe4  nop     dword ptr [rax+rax+00h]
0x18005bfe9  nop
0x18005bfea  lea     rcx, [rsp+1A0h+lpFileName]
0x18005bfef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005bff4  xor     al, al
0x18005bff6  jmp     loc_18005C0D4
0x18005bffb  mov     [rsp+1A0h+NumberOfBytesRead], 0
0x18005c003  mov     qword ptr [rsp+1A0h+dwCreationDisposition], 0; unsigned int
0x18005c00c  lea     r9, [rsp+1A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005c011  mov     r8d, 100h; nNumberOfBytesToRead
0x18005c017  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x18005c01b  mov     rcx, rbx; hFile
0x18005c01e  call    cs:__imp_ReadFile
0x18005c025  nop     dword ptr [rax+rax+00h]
0x18005c02a  mov     rcx, [rbp+0A8h]; this
0x18005c031  test    eax, eax
0x18005c033  jz      loc_18005C12D
0x18005c039  xorps   xmm0, xmm0
0x18005c03c  movups  xmmword ptr [rsp+1A0h+Buf1], xmm0
0x18005c041  xorps   xmm1, xmm1
0x18005c044  movdqu  xmmword ptr [rsp+1A0h+Size], xmm1
0x18005c04a  mov     r8d, [rsp+1A0h+NumberOfBytesRead]
0x18005c04f  lea     rdx, [rbp+0A0h+Buffer]
0x18005c053  lea     rcx, [rsp+1A0h+Buf1]
0x18005c058  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005c05d  lea     rdx, Buf2
0x18005c064  cmp     cs:qword_1800BDDA0, 0Fh
0x18005c06c  cmova   rdx, cs:Buf2; Buf2
0x18005c074  mov     r8, [rsp+1A0h+Size]; Size
0x18005c079  lea     rcx, [rsp+1A0h+Buf1]
0x18005c07e  cmp     [rsp+1A0h+Size+8], 0Fh
0x18005c084  cmova   rcx, [rsp+1A0h+Buf1]; Buf1
0x18005c08a  cmp     r8, cs:qword_1800BDD98
0x18005c091  jnz     short loc_18005C0A6
0x18005c093  test    r8, r8
0x18005c096  jz      short loc_18005C0A1
0x18005c098  call    memcmp_0
0x18005c09d  test    eax, eax
0x18005c09f  jnz     short loc_18005C0A6
0x18005c0a1  xor     dil, dil
0x18005c0a4  jmp     short loc_18005C0A9
0x18005c0a6  mov     dil, 1
0x18005c0a9  lea     rcx, [rsp+1A0h+Buf1]
0x18005c0ae  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18005c0b3  test    dil, dil
0x18005c0b6  jnz     short loc_18005C0F9
0x18005c0b8  mov     rcx, rbx; hObject
0x18005c0bb  call    cs:__imp_CloseHandle
0x18005c0c2  nop     dword ptr [rax+rax+00h]
0x18005c0c7  nop
0x18005c0c8  lea     rcx, [rsp+1A0h+lpFileName]
0x18005c0cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005c0d2  mov     al, 1
0x18005c0d4  mov     rcx, [rbp+0A0h+var_10]
0x18005c0db  xor     rcx, rsp; StackCookie
0x18005c0de  call    __security_check_cookie
0x18005c0e3  lea     r11, [rsp+1A0h+var_s0]
0x18005c0eb  mov     rbx, [r11+18h]
0x18005c0ef  mov     rdi, [r11+20h]
0x18005c0f3  mov     rsp, r11
0x18005c0f6  pop     rbp
0x18005c0f7  retn
0x18005c0f9  mov     rcx, [rbp+0A8h]; this
0x18005c100  mov     r9d, 0C0370112h; char *
0x18005c106  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005c10d  mov     edx, 96h; void *
0x18005c112  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005c118  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005c11f  mov     edx, 8Ch; void *
0x18005c124  mov     rcx, rdi; this
0x18005c127  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005c12d  lea     r8, aOnecoreVmCompu_11; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005c134  mov     edx, 92h; void *
0x18005c139  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
