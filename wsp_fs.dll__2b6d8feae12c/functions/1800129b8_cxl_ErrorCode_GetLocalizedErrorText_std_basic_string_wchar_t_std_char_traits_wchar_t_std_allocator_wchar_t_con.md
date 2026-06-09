# cxl::ErrorCode::GetLocalizedErrorText(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const)

- ea: `0x1800129b8`
- end: `0x180012afe`
- name: `?GetLocalizedErrorText@ErrorCode@cxl@@QEBAXQEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180010214`
- `0x18009b114`

## callees

- `0x18000e6f4`
- `0x18001072c`
- `0x180012028`
- `0x180012364`
- `0x18001249c`
- `0x180012660`
- `0x1800129b8`
- `0x180012b04`
- `0x180016ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a83`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012a79`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012a79`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800129eb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800129eb`

## string_xrefs

- `0x1800129e4`: `pdh.dll`
- `0x180012a1b`: `[CXL] Could not format {0} to a message, because cannot load pdh.dll {1}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct cxl::TextWriter *__fastcall cxl::ErrorCode::GetLocalizedErrorText(cxl::ErrorCode *a1, __int64 a2)
{
  DWORD WinError; // ebx
  HMODULE LibraryW; // rdx
  struct cxl::TraceManager *v6; // rax
  struct cxl::TextWriter *v7; // rax
  __int64 v8; // rdx
  struct cxl::TraceManager *v10; // rax
  struct cxl::TextWriter *v11; // rax
  __int64 v12; // rdx
  _BYTE v13[8]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v14; // [rsp+48h] [rbp-18h]
  __int64 Buffer; // [rsp+90h] [rbp+30h] BYREF

  Buffer = 0;
  WinError = cxl::ErrorCode::GetWinError(a1);
  LibraryW = 0;
  if ( *((_DWORD *)a1 + 1) != 6 || (LibraryW = LoadLibraryW(L"pdh.dll")) != 0 )
  {
    if ( FormatMessageW(LibraryW != 0 ? 2304 : 4352, LibraryW, WinError, 0, (LPWSTR)&Buffer, 0, 0) )
    {
      v14 = Buffer;
      std::wstring::assign(a2);
      cxl::LocalHeapPtr<unsigned char>::Clear(v13);
    }
    else
    {
      GetLastError();
      v10 = cxl::TraceManager::Instance();
      cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(
        (struct cxl::TraceManager *)((char *)v10 + 80),
        "[CXL] Could not format {0} to a message, because {1}");
      v11 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v13, a2);
      cxl::TextWriter::Write<char,cxl::ErrorCode,>(v11, v12, (__int64)a1);
    }
    return (struct cxl::TextWriter *)cxl::TrimWhiteSpace(a2);
  }
  else
  {
    GetLastError();
    v6 = cxl::TraceManager::Instance();
    cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(
      (struct cxl::TraceManager *)((char *)v6 + 80),
      "[CXL] Could not format {0} to a message, because cannot load pdh.dll {1}");
    v7 = (struct cxl::TextWriter *)cxl::StringWriter::StringWriter(v13, a2);
    return cxl::TextWriter::Write<char,cxl::ErrorCode,>(v7, v8, (__int64)a1);
  }
}

```

## disassembly

```asm
0x1800129b8  mov     [rsp-18h+arg_8], rbx
0x1800129bd  push    rbp
0x1800129be  push    rsi
0x1800129bf  push    rdi
0x1800129c0  mov     rbp, rsp
0x1800129c3  sub     rsp, 60h
0x1800129c7  mov     rdi, rdx
0x1800129ca  mov     rsi, rcx
0x1800129cd  mov     [rbp+Buffer], 0
0x1800129d5  call    ?GetWinError@ErrorCode@cxl@@QEBAKXZ; cxl::ErrorCode::GetWinError(void)
0x1800129da  mov     ebx, eax
0x1800129dc  xor     edx, edx; lpSource
0x1800129de  cmp     dword ptr [rsi+4], 6
0x1800129e2  jnz     short loc_180012A45
0x1800129e4  lea     rcx, LibFileName; "pdh.dll"
0x1800129eb  call    cs:__imp_LoadLibraryW
0x1800129f1  mov     rdx, rax
0x1800129f4  test    rax, rax
0x1800129f7  jnz     short loc_180012A45
0x1800129f9  call    cs:__imp_GetLastError
0x1800129ff  mov     ebx, eax
0x180012a01  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180012a06  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180012a0a  mov     [rbp+arg_0], ebx
0x180012a0d  mov     [rbp+arg_4], 0
0x180012a14  lea     r9, [rbp+arg_0]
0x180012a18  mov     r8, rsi
0x180012a1b  lea     rdx, aCxlCouldNotFor; "[CXL] Could not format {0} to a message"...
0x180012a22  call    ??$WriteLine@DVErrorCode@cxl@@V12@@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@1@Z; cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(char const *,cxl::ErrorCode const &,cxl::ErrorCode const &)
0x180012a27  mov     rdx, rdi
0x180012a2a  lea     rcx, [rbp+var_20]
0x180012a2e  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180012a33  nop
0x180012a34  mov     r8, rsi
0x180012a37  mov     rcx, rax; struct cxl::TextWriter *
0x180012a3a  call    ??$Write@DVErrorCode@cxl@@$$V@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@@Z; cxl::TextWriter::Write<char,cxl::ErrorCode,>(char const *,cxl::ErrorCode const &)
0x180012a3f  nop
0x180012a40  jmp     loc_180012AEE
0x180012a45  mov     rax, rdx
0x180012a48  neg     rax
0x180012a4b  sbb     ecx, ecx
0x180012a4d  and     ecx, 0FFFFF800h
0x180012a53  add     ecx, 1100h; dwFlags
0x180012a59  mov     [rsp+60h+Arguments], 0; Arguments
0x180012a62  mov     [rsp+60h+nSize], 0; nSize
0x180012a6a  lea     rax, [rbp+Buffer]
0x180012a6e  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x180012a73  xor     r9d, r9d; dwLanguageId
0x180012a76  mov     r8d, ebx; dwMessageId
0x180012a79  call    cs:__imp_FormatMessageW
0x180012a7f  test    eax, eax
0x180012a81  jnz     short loc_180012ACC
0x180012a83  call    cs:__imp_GetLastError
0x180012a89  mov     ebx, eax
0x180012a8b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180012a90  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180012a94  mov     [rbp+arg_0], ebx
0x180012a97  mov     [rbp+arg_4], 0
0x180012a9e  lea     r9, [rbp+arg_0]
0x180012aa2  mov     r8, rsi
0x180012aa5  lea     rdx, aCxlCouldNotFor_0; "[CXL] Could not format {0} to a message"...
0x180012aac  call    ??$WriteLine@DVErrorCode@cxl@@V12@@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@1@Z; cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(char const *,cxl::ErrorCode const &,cxl::ErrorCode const &)
0x180012ab1  mov     rdx, rdi
0x180012ab4  lea     rcx, [rbp+var_20]
0x180012ab8  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180012abd  nop
0x180012abe  mov     r8, rsi
0x180012ac1  mov     rcx, rax; struct cxl::TextWriter *
0x180012ac4  call    ??$Write@DVErrorCode@cxl@@$$V@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@@Z; cxl::TextWriter::Write<char,cxl::ErrorCode,>(char const *,cxl::ErrorCode const &)
0x180012ac9  nop
0x180012aca  jmp     short loc_180012AE6
0x180012acc  mov     rdx, [rbp+Buffer]
0x180012ad0  mov     [rbp+var_18], rdx
0x180012ad4  mov     rcx, rdi
0x180012ad7  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180012adc  nop
0x180012add  lea     rcx, [rbp+var_20]
0x180012ae1  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180012ae6  mov     rcx, rdi
0x180012ae9  call    ?TrimWhiteSpace@cxl@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TrimWhiteSpace(std::wstring &)
0x180012aee  mov     rbx, [rsp+60h+arg_8]
0x180012af6  add     rsp, 60h
0x180012afa  pop     rdi
0x180012afb  pop     rsi
0x180012afc  pop     rbp
0x180012afd  retn
```
