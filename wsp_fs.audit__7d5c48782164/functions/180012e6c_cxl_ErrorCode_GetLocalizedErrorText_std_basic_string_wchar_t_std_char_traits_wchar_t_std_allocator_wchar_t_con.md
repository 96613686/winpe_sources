# cxl::ErrorCode::GetLocalizedErrorText(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const)

- ea: `0x180012e6c`
- end: `0x180012fcb`
- name: `?GetLocalizedErrorText@ErrorCode@cxl@@QEBAXQEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180010654`
- `0x18009d5bb`

## callees

- `0x18000eb18`
- `0x180010b90`
- `0x1800124ac`
- `0x180012800`
- `0x18001293c`
- `0x180012b00`
- `0x180012e6c`
- `0x180012fd4`
- `0x180017688`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f49`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012f39`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012f39`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180012e9f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180012e9f`

## string_xrefs

- `0x180012e98`: `pdh.dll`
- `0x180012edb`: `[CXL] Could not format {0} to a message, because cannot load pdh.dll {1}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall cxl::ErrorCode::GetLocalizedErrorText(cxl::ErrorCode *a1, __int64 a2)
{
  DWORD WinError; // ebx
  HMODULE LibraryW; // rdx
  struct cxl::TraceManager *v6; // rax
  struct cxl::TextWriter *v7; // rax
  struct cxl::TraceManager *v9; // rax
  struct cxl::TextWriter *v10; // rax
  _BYTE v11[8]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h]
  __int64 Buffer; // [rsp+90h] [rbp+30h] BYREF

  Buffer = 0;
  WinError = cxl::ErrorCode::GetWinError(a1);
  LibraryW = 0;
  if ( *((_DWORD *)a1 + 1) != 6 || (LibraryW = LoadLibraryW(L"pdh.dll")) != 0 )
  {
    if ( FormatMessageW(LibraryW != 0 ? 2304 : 4352, LibraryW, WinError, 0, (LPWSTR)&Buffer, 0, 0) )
    {
      v12 = Buffer;
      std::wstring::assign(a2, Buffer);
      cxl::LocalHeapPtr<unsigned char>::Clear(v11);
    }
    else
    {
      GetLastError();
      v9 = cxl::TraceManager::Instance();
      cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(
        (struct cxl::TraceManager *)((char *)v9 + 80),
        "[CXL] Could not format {0} to a message, because {1}");
      v10 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v11, a2);
      cxl::TextWriter::Write<char,cxl::ErrorCode,>(v10);
    }
    return cxl::TrimWhiteSpace(a2);
  }
  else
  {
    GetLastError();
    v6 = cxl::TraceManager::Instance();
    cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(
      (struct cxl::TraceManager *)((char *)v6 + 80),
      "[CXL] Could not format {0} to a message, because cannot load pdh.dll {1}");
    v7 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v11, a2);
    return cxl::TextWriter::Write<char,cxl::ErrorCode,>(v7);
  }
}

```

## disassembly

```asm
0x180012e6c  mov     [rsp-18h+arg_8], rbx
0x180012e71  push    rbp
0x180012e72  push    rsi
0x180012e73  push    rdi
0x180012e74  mov     rbp, rsp
0x180012e77  sub     rsp, 60h
0x180012e7b  mov     rdi, rdx
0x180012e7e  mov     rsi, rcx
0x180012e81  mov     [rbp+Buffer], 0
0x180012e89  call    ?GetWinError@ErrorCode@cxl@@QEBAKXZ; cxl::ErrorCode::GetWinError(void)
0x180012e8e  mov     ebx, eax
0x180012e90  xor     edx, edx; lpSource
0x180012e92  cmp     dword ptr [rsi+4], 6
0x180012e96  jnz     short loc_180012F05
0x180012e98  lea     rcx, LibFileName; "pdh.dll"
0x180012e9f  call    cs:__imp_LoadLibraryW
0x180012ea6  nop     dword ptr [rax+rax+00h]
0x180012eab  mov     rdx, rax
0x180012eae  test    rax, rax
0x180012eb1  jnz     short loc_180012F05
0x180012eb3  call    cs:__imp_GetLastError
0x180012eba  nop     dword ptr [rax+rax+00h]
0x180012ebf  mov     ebx, eax
0x180012ec1  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180012ec6  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180012eca  mov     [rbp+arg_0], ebx
0x180012ecd  mov     [rbp+arg_4], 0
0x180012ed4  lea     r9, [rbp+arg_0]
0x180012ed8  mov     r8, rsi
0x180012edb  lea     rdx, aCxlCouldNotFor; "[CXL] Could not format {0} to a message"...
0x180012ee2  call    ??$WriteLine@DVErrorCode@cxl@@V12@@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@1@Z; cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(char const *,cxl::ErrorCode const &,cxl::ErrorCode const &)
0x180012ee7  mov     rdx, rdi
0x180012eea  lea     rcx, [rbp+var_20]
0x180012eee  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180012ef3  nop
0x180012ef4  mov     r8, rsi
0x180012ef7  mov     rcx, rax; struct cxl::TextWriter *
0x180012efa  call    ??$Write@DVErrorCode@cxl@@$$V@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@@Z; cxl::TextWriter::Write<char,cxl::ErrorCode,>(char const *,cxl::ErrorCode const &)
0x180012eff  nop
0x180012f00  jmp     loc_180012FBA
0x180012f05  mov     rax, rdx
0x180012f08  neg     rax
0x180012f0b  sbb     ecx, ecx
0x180012f0d  and     ecx, 0FFFFF800h
0x180012f13  add     ecx, 1100h; dwFlags
0x180012f19  mov     [rsp+60h+Arguments], 0; Arguments
0x180012f22  mov     [rsp+60h+nSize], 0; nSize
0x180012f2a  lea     rax, [rbp+Buffer]
0x180012f2e  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x180012f33  xor     r9d, r9d; dwLanguageId
0x180012f36  mov     r8d, ebx; dwMessageId
0x180012f39  call    cs:__imp_FormatMessageW
0x180012f40  nop     dword ptr [rax+rax+00h]
0x180012f45  test    eax, eax
0x180012f47  jnz     short loc_180012F98
0x180012f49  call    cs:__imp_GetLastError
0x180012f50  nop     dword ptr [rax+rax+00h]
0x180012f55  mov     ebx, eax
0x180012f57  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180012f5c  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180012f60  mov     [rbp+arg_0], ebx
0x180012f63  mov     [rbp+arg_4], 0
0x180012f6a  lea     r9, [rbp+arg_0]
0x180012f6e  mov     r8, rsi
0x180012f71  lea     rdx, aCxlCouldNotFor_0; "[CXL] Could not format {0} to a message"...
0x180012f78  call    ??$WriteLine@DVErrorCode@cxl@@V12@@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@1@Z; cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(char const *,cxl::ErrorCode const &,cxl::ErrorCode const &)
0x180012f7d  mov     rdx, rdi
0x180012f80  lea     rcx, [rbp+var_20]
0x180012f84  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180012f89  nop
0x180012f8a  mov     r8, rsi
0x180012f8d  mov     rcx, rax; struct cxl::TextWriter *
0x180012f90  call    ??$Write@DVErrorCode@cxl@@$$V@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@@Z; cxl::TextWriter::Write<char,cxl::ErrorCode,>(char const *,cxl::ErrorCode const &)
0x180012f95  nop
0x180012f96  jmp     short loc_180012FB2
0x180012f98  mov     rdx, [rbp+Buffer]
0x180012f9c  mov     [rbp+var_18], rdx
0x180012fa0  mov     rcx, rdi
0x180012fa3  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180012fa8  nop
0x180012fa9  lea     rcx, [rbp+var_20]
0x180012fad  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180012fb2  mov     rcx, rdi
0x180012fb5  call    ?TrimWhiteSpace@cxl@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TrimWhiteSpace(std::wstring &)
0x180012fba  mov     rbx, [rsp+60h+arg_8]
0x180012fc2  add     rsp, 60h
0x180012fc6  pop     rdi
0x180012fc7  pop     rsi
0x180012fc8  pop     rbp
0x180012fc9  retn
```
