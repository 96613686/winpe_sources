# TestHookPolicyReader::VerifyAUTestCabExists(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180018eec`
- end: `0x180019015`
- name: `?VerifyAUTestCabExists@TestHookPolicyReader@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(const WCHAR *lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180018bc4`

## callees

- `0x18000aac0`
- `0x18000aae4`
- `0x180018eec`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018ff5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018ff5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018f6a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018f6a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018f12`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018f12`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180018f96`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180018f96`

## string_xrefs

- `0x180018f22`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`
- `0x180018faa`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`
- `0x180018fca`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall TestHookPolicyReader::VerifyAUTestCabExists(const WCHAR *lpFileName)
{
  LPCWSTR v1; // rbx
  const char *v2; // r9
  HANDLE FileW; // rbx
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int LastError; // edi
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-38h]
  _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = lpFileName;
  if ( *((_QWORD *)lpFileName + 3) > 7u )
    lpFileName = *(const WCHAR **)lpFileName;
  if ( GetFileAttributesW(lpFileName) == -1 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x9F,
             (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
             v2);
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(LPCWSTR *)v1;
  FileW = CreateFileW(v1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = 170;
LABEL_11:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
                  v5);
LABEL_14:
    if ( FileW == (HANDLE)-1LL || !FileW )
      return LastError;
    goto LABEL_18;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v6 = 174;
    goto LABEL_11;
  }
  if ( FileSize.QuadPart > 0x4E20uLL )
  {
    LastError = -2147024883;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
      (const char *)0x8007000DLL,
      dwCreationDisposition);
    goto LABEL_14;
  }
  LastError = 0;
LABEL_18:
  CloseHandle(FileW);
  return LastError;
}

```

## disassembly

```asm
0x180018eec  mov     [rsp+arg_8], rbx
0x180018ef1  push    rdi
0x180018ef2  sub     rsp, 50h
0x180018ef6  mov     rax, cs:__security_cookie
0x180018efd  xor     rax, rsp
0x180018f00  mov     [rsp+58h+var_10], rax
0x180018f05  cmp     qword ptr [rcx+18h], 7
0x180018f0a  mov     rbx, rcx
0x180018f0d  jbe     short loc_180018F12
0x180018f0f  mov     rcx, [rcx]; lpFileName
0x180018f12  call    cs:__imp_GetFileAttributesW
0x180018f18  cmp     eax, 0FFFFFFFFh
0x180018f1b  jnz     short loc_180018F38
0x180018f1d  mov     rcx, [rsp+58h]; this
0x180018f22  lea     r8, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018f29  mov     edx, 9Fh; void *
0x180018f2e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018f33  jmp     loc_180018FFD
0x180018f38  cmp     qword ptr [rbx+18h], 7
0x180018f3d  jbe     short loc_180018F42
0x180018f3f  mov     rbx, [rbx]
0x180018f42  xor     r9d, r9d; lpSecurityAttributes
0x180018f45  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180018f4e  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180018f56  mov     edx, 80000000h; dwDesiredAccess
0x180018f5b  mov     rcx, rbx; lpFileName
0x180018f5e  mov     [rsp+58h+dwCreationDisposition], 3; int
0x180018f66  lea     r8d, [r9+1]; dwShareMode
0x180018f6a  call    cs:__imp_CreateFileW
0x180018f70  mov     rbx, rax
0x180018f73  inc     rax
0x180018f76  test    rax, 0FFFFFFFFFFFFFFFEh
0x180018f7c  jnz     short loc_180018F85
0x180018f7e  mov     edx, 0AAh
0x180018f83  jmp     short loc_180018FA5
0x180018f85  lea     rdx, [rsp+58h+FileSize]; lpFileSize
0x180018f8a  mov     qword ptr [rsp+58h+FileSize], 0
0x180018f93  mov     rcx, rbx; hFile
0x180018f96  call    cs:__imp_GetFileSizeEx
0x180018f9c  test    eax, eax
0x180018f9e  jnz     short loc_180018FBA
0x180018fa0  mov     edx, 0AEh; void *
0x180018fa5  mov     rcx, [rsp+58h]; this
0x180018faa  lea     r8, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018fb1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018fb6  mov     edi, eax
0x180018fb8  jmp     short loc_180018FE3
0x180018fba  cmp     qword ptr [rsp+58h+FileSize], 4E20h
0x180018fc3  jbe     short loc_180018FF0
0x180018fc5  mov     rcx, [rsp+58h]; this
0x180018fca  lea     r8, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x180018fd1  mov     edi, 8007000Dh
0x180018fd6  mov     edx, 0B3h; void *
0x180018fdb  mov     r9d, edi; char *
0x180018fde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018fe3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180018fe7  jz      short loc_180018FFB
0x180018fe9  test    rbx, rbx
0x180018fec  jnz     short loc_180018FF2
0x180018fee  jmp     short loc_180018FFB
0x180018ff0  xor     edi, edi
0x180018ff2  mov     rcx, rbx; hObject
0x180018ff5  call    cs:__imp_CloseHandle
0x180018ffb  mov     eax, edi
0x180018ffd  mov     rcx, [rsp+58h+var_10]
0x180019002  xor     rcx, rsp; StackCookie
0x180019005  call    __security_check_cookie
0x18001900a  mov     rbx, [rsp+58h+arg_8]
0x18001900f  add     rsp, 50h
0x180019013  pop     rdi
0x180019014  retn
```
