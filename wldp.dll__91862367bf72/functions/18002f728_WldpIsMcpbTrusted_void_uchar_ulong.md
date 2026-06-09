# WldpIsMcpbTrusted(void *,uchar *,ulong *)

- ea: `0x18002f728`
- end: `0x18002f8d4`
- name: `?WldpIsMcpbTrusted@@YAJPEAXPEAEPEAK@Z`
- size: `428`
- prototype: `__int64 __fastcall(HANDLE hFile, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18002e8b0`

## callees

- `0x1800159a0`
- `0x1800159f0`
- `0x18001f038`
- `0x1800201d4`
- `0x180021ec0`
- `0x18002f5d0`
- `0x18002f648`
- `0x18002f728`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002f76f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002f76f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002f7ee`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002f7ee`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002f86f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002f86f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002f7a5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002f7a5`

## string_xrefs

- `0x18002f7c0`: `onecore\base\ngscb\wldp\dll\mcpb.cpp`
- `0x18002f804`: `onecore\base\ngscb\wldp\dll\mcpb.cpp`
- `0x18002f884`: `onecore\base\ngscb\wldp\dll\mcpb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WldpIsMcpbTrusted(HANDLE hFile, unsigned __int8 *a2, unsigned int *a3)
{
  HANDLE FileMappingW; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  unsigned __int8 *v9; // rdi
  const char *v10; // r9
  int dwMaximumSizeLow; // [rsp+20h] [rbp-50h]
  HANDLE v13; // [rsp+38h] [rbp-38h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v15[2]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  FileSize.QuadPart = 0;
  v13 = 0;
  *a3 = 2;
  *a2 = 0;
  if ( GetFileSizeEx(hFile, &FileSize) && FileSize.QuadPart )
  {
    if ( FileSize.QuadPart < 0 )
    {
      LastError = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\mcpb.cpp",
        (const char *)0x80070216LL,
        dwMaximumSizeLow);
    }
    else
    {
      FileMappingW = CreateFileMappingW(hFile, 0, 2u, 0, 0, 0);
      v13 = FileMappingW;
      if ( (((unsigned __int64)FileMappingW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v9 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        if ( v9 )
        {
          GetPathnameFromHandle(v15, hFile);
          LastError = McpbParseAndVerifySignature(v9, (__int64)a2, a3);
          std::wstring::~wstring(v15);
          UnmapViewOfFile(v9);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x127,
                        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\mcpb.cpp",
                        v10);
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x120,
                      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\mcpb.cpp",
                      v7);
      }
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
    return LastError;
  }
  else
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
    return 2147942413LL;
  }
}

```

## disassembly

```asm
0x18002f728  push    rbp
0x18002f72a  push    rbx
0x18002f72b  push    rsi
0x18002f72c  push    rdi
0x18002f72d  push    r12
0x18002f72f  push    r14
0x18002f731  push    r15
0x18002f733  mov     rbp, rsp
0x18002f736  sub     rsp, 70h
0x18002f73a  mov     rax, cs:__security_cookie
0x18002f741  xor     rax, rsp
0x18002f744  mov     [rbp+var_8], rax
0x18002f748  mov     r15, r8
0x18002f74b  mov     r14, rdx
0x18002f74e  mov     rsi, rcx
0x18002f751  xor     r12d, r12d
0x18002f754  mov     qword ptr [rbp+FileSize], r12
0x18002f758  mov     [rbp+var_38], r12
0x18002f75c  mov     [rbp+var_40], r12
0x18002f760  lea     edi, [r12+2]
0x18002f765  mov     [r8], edi
0x18002f768  mov     [rdx], r12b
0x18002f76b  lea     rdx, [rbp+FileSize]; lpFileSize
0x18002f76f  call    cs:__imp_GetFileSizeEx
0x18002f775  test    eax, eax
0x18002f777  jz      loc_18002F8A7
0x18002f77d  mov     rbx, qword ptr [rbp+FileSize]
0x18002f781  test    rbx, rbx
0x18002f784  jz      loc_18002F8A7
0x18002f78a  js      loc_18002F878
0x18002f790  mov     [rsp+70h+lpName], r12; lpName
0x18002f795  mov     [rsp+70h+dwMaximumSizeLow], r12d; dwMaximumSizeLow
0x18002f79a  xor     r9d, r9d; dwMaximumSizeHigh
0x18002f79d  mov     r8d, edi; flProtect
0x18002f7a0  xor     edx, edx; lpFileMappingAttributes
0x18002f7a2  mov     rcx, rsi; hFile
0x18002f7a5  call    cs:__imp_CreateFileMappingW
0x18002f7ab  mov     [rbp+var_38], rax
0x18002f7af  lea     rcx, [rax+1]
0x18002f7b3  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18002f7ba  jnz     short loc_18002F7DC
0x18002f7bc  mov     rcx, [rbp+38h]; this
0x18002f7c0  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\wldp\\dll\\mcpb.c"...
0x18002f7c7  mov     edx, 120h; void *
0x18002f7cc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f7d1  mov     ebx, eax
0x18002f7d3  mov     [rbp+var_40], r12
0x18002f7d7  jmp     loc_18002F89A
0x18002f7dc  mov     qword ptr [rsp+70h+dwMaximumSizeLow], r12; dwNumberOfBytesToMap
0x18002f7e1  xor     r9d, r9d; dwFileOffsetLow
0x18002f7e4  xor     r8d, r8d; dwFileOffsetHigh
0x18002f7e7  lea     edx, [r9+4]; dwDesiredAccess
0x18002f7eb  mov     rcx, rax; hFileMappingObject
0x18002f7ee  call    cs:__imp_MapViewOfFile
0x18002f7f4  mov     rdi, rax
0x18002f7f7  mov     [rbp+var_40], rax
0x18002f7fb  test    rax, rax
0x18002f7fe  jnz     short loc_18002F81E
0x18002f800  mov     rcx, [rbp+38h]; this
0x18002f804  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\wldp\\dll\\mcpb.c"...
0x18002f80b  mov     edx, 127h; void *
0x18002f810  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f815  nop
0x18002f816  mov     [rbp+var_40], r12
0x18002f81a  mov     ebx, eax
0x18002f81c  jmp     short loc_18002F89A
0x18002f81e  mov     rdx, rsi
0x18002f821  lea     rcx, [rbp+var_28]
0x18002f825  call    ?GetPathnameFromHandle@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; GetPathnameFromHandle(void *)
0x18002f82a  nop
0x18002f82b  cmp     [rbp+var_18], r12
0x18002f82f  jnz     short loc_18002F836
0x18002f831  mov     r8, r12
0x18002f834  jmp     short loc_18002F844
0x18002f836  lea     r8, [rbp+var_28]
0x18002f83a  cmp     [rbp+var_10], 7
0x18002f83f  cmova   r8, [rbp+var_28]
0x18002f844  mov     [rsp+70h+lpName], r15; unsigned int *
0x18002f849  mov     qword ptr [rsp+70h+dwMaximumSizeLow], r14; __int64
0x18002f84e  mov     r9, rsi
0x18002f851  mov     rdx, rbx
0x18002f854  mov     rcx, rdi; unsigned __int8 *
0x18002f857  call    McpbParseAndVerifySignature
0x18002f85c  mov     ebx, eax
0x18002f85e  lea     rcx, [rbp+var_28]
0x18002f862  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f867  nop
0x18002f868  mov     [rbp+var_40], r12
0x18002f86c  mov     rcx, rdi; lpBaseAddress
0x18002f86f  call    cs:__imp_UnmapViewOfFile
0x18002f875  nop
0x18002f876  jmp     short loc_18002F89A
0x18002f878  mov     rcx, [rbp+38h]; this
0x18002f87c  mov     ebx, 80070216h
0x18002f881  mov     r9d, ebx; char *
0x18002f884  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\wldp\\dll\\mcpb.c"...
0x18002f88b  mov     edx, 115h; void *
0x18002f890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f895  nop
0x18002f896  mov     [rbp+var_40], r12
0x18002f89a  lea     rcx, [rbp+var_38]
0x18002f89e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f8a3  mov     eax, ebx
0x18002f8a5  jmp     short loc_18002F8B9
0x18002f8a7  mov     [rbp+var_40], r12
0x18002f8ab  lea     rcx, [rbp+var_38]
0x18002f8af  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f8b4  mov     eax, 8007000Dh
0x18002f8b9  mov     rcx, [rbp+var_8]
0x18002f8bd  xor     rcx, rsp; StackCookie
0x18002f8c0  call    __security_check_cookie
0x18002f8c5  add     rsp, 70h
0x18002f8c9  pop     r15
0x18002f8cb  pop     r14
0x18002f8cd  pop     r12
0x18002f8cf  pop     rdi
0x18002f8d0  pop     rsi
0x18002f8d1  pop     rbx
0x18002f8d2  pop     rbp
0x18002f8d3  retn
```
