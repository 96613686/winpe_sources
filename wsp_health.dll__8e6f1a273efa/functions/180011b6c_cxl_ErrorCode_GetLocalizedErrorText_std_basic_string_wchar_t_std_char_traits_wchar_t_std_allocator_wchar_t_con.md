# cxl::ErrorCode::GetLocalizedErrorText(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const)

- ea: `0x180011b6c`
- end: `0x180011ccb`
- name: `?GetLocalizedErrorText@ErrorCode@cxl@@QEBAXQEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000f380`
- `0x18008768c`

## callees

- `0x18000e4b8`
- `0x18000f89c`
- `0x180011184`
- `0x18001150c`
- `0x180011648`
- `0x180011800`
- `0x180011b6c`
- `0x180011cd4`
- `0x180015ce4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c49`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011c39`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011c39`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011b9f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011b9f`

## string_xrefs

- `0x180011b98`: `pdh.dll`
- `0x180011bdb`: `[CXL] Could not format {0} to a message, because cannot load pdh.dll {1}`

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
0x180011b6c  mov     [rsp-18h+arg_8], rbx
0x180011b71  push    rbp
0x180011b72  push    rsi
0x180011b73  push    rdi
0x180011b74  mov     rbp, rsp
0x180011b77  sub     rsp, 60h
0x180011b7b  mov     rdi, rdx
0x180011b7e  mov     rsi, rcx
0x180011b81  mov     [rbp+Buffer], 0
0x180011b89  call    ?GetWinError@ErrorCode@cxl@@QEBAKXZ; cxl::ErrorCode::GetWinError(void)
0x180011b8e  mov     ebx, eax
0x180011b90  xor     edx, edx; lpSource
0x180011b92  cmp     dword ptr [rsi+4], 6
0x180011b96  jnz     short loc_180011C05
0x180011b98  lea     rcx, aPdhDll; "pdh.dll"
0x180011b9f  call    cs:__imp_LoadLibraryW
0x180011ba6  nop     dword ptr [rax+rax+00h]
0x180011bab  mov     rdx, rax
0x180011bae  test    rax, rax
0x180011bb1  jnz     short loc_180011C05
0x180011bb3  call    cs:__imp_GetLastError
0x180011bba  nop     dword ptr [rax+rax+00h]
0x180011bbf  mov     ebx, eax
0x180011bc1  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180011bc6  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180011bca  mov     [rbp+arg_0], ebx
0x180011bcd  mov     [rbp+arg_4], 0
0x180011bd4  lea     r9, [rbp+arg_0]
0x180011bd8  mov     r8, rsi
0x180011bdb  lea     rdx, aCxlCouldNotFor; "[CXL] Could not format {0} to a message"...
0x180011be2  call    ??$WriteLine@DVErrorCode@cxl@@V12@@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@1@Z; cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(char const *,cxl::ErrorCode const &,cxl::ErrorCode const &)
0x180011be7  mov     rdx, rdi
0x180011bea  lea     rcx, [rbp+var_20]
0x180011bee  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180011bf3  nop
0x180011bf4  mov     r8, rsi
0x180011bf7  mov     rcx, rax; struct cxl::TextWriter *
0x180011bfa  call    ??$Write@DVErrorCode@cxl@@$$V@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@@Z; cxl::TextWriter::Write<char,cxl::ErrorCode,>(char const *,cxl::ErrorCode const &)
0x180011bff  nop
0x180011c00  jmp     loc_180011CBA
0x180011c05  mov     rax, rdx
0x180011c08  neg     rax
0x180011c0b  sbb     ecx, ecx
0x180011c0d  and     ecx, 0FFFFF800h
0x180011c13  add     ecx, 1100h; dwFlags
0x180011c19  mov     [rsp+60h+Arguments], 0; Arguments
0x180011c22  mov     [rsp+60h+nSize], 0; nSize
0x180011c2a  lea     rax, [rbp+Buffer]
0x180011c2e  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x180011c33  xor     r9d, r9d; dwLanguageId
0x180011c36  mov     r8d, ebx; dwMessageId
0x180011c39  call    cs:__imp_FormatMessageW
0x180011c40  nop     dword ptr [rax+rax+00h]
0x180011c45  test    eax, eax
0x180011c47  jnz     short loc_180011C98
0x180011c49  call    cs:__imp_GetLastError
0x180011c50  nop     dword ptr [rax+rax+00h]
0x180011c55  mov     ebx, eax
0x180011c57  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180011c5c  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180011c60  mov     [rbp+arg_0], ebx
0x180011c63  mov     [rbp+arg_4], 0
0x180011c6a  lea     r9, [rbp+arg_0]
0x180011c6e  mov     r8, rsi
0x180011c71  lea     rdx, aCxlCouldNotFor_0; "[CXL] Could not format {0} to a message"...
0x180011c78  call    ??$WriteLine@DVErrorCode@cxl@@V12@@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@1@Z; cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(char const *,cxl::ErrorCode const &,cxl::ErrorCode const &)
0x180011c7d  mov     rdx, rdi
0x180011c80  lea     rcx, [rbp+var_20]
0x180011c84  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180011c89  nop
0x180011c8a  mov     r8, rsi
0x180011c8d  mov     rcx, rax; struct cxl::TextWriter *
0x180011c90  call    ??$Write@DVErrorCode@cxl@@$$V@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@@Z; cxl::TextWriter::Write<char,cxl::ErrorCode,>(char const *,cxl::ErrorCode const &)
0x180011c95  nop
0x180011c96  jmp     short loc_180011CB2
0x180011c98  mov     rdx, [rbp+Buffer]
0x180011c9c  mov     [rbp+var_18], rdx
0x180011ca0  mov     rcx, rdi
0x180011ca3  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180011ca8  nop
0x180011ca9  lea     rcx, [rbp+var_20]
0x180011cad  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180011cb2  mov     rcx, rdi
0x180011cb5  call    ?TrimWhiteSpace@cxl@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TrimWhiteSpace(std::wstring &)
0x180011cba  mov     rbx, [rsp+60h+arg_8]
0x180011cc2  add     rsp, 60h
0x180011cc6  pop     rdi
0x180011cc7  pop     rsi
0x180011cc8  pop     rbp
0x180011cc9  retn
```
