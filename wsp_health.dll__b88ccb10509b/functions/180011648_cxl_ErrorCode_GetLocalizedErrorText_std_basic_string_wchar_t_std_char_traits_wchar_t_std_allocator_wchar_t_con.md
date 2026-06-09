# cxl::ErrorCode::GetLocalizedErrorText(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> * const)

- ea: `0x180011648`
- end: `0x18001178e`
- name: `?GetLocalizedErrorText@ErrorCode@cxl@@QEBAXQEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `326`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000eef0`
- `0x180085266`

## callees

- `0x18000e044`
- `0x18000f3e8`
- `0x180010ca4`
- `0x180011000`
- `0x180011138`
- `0x1800112f0`
- `0x180011648`
- `0x180011794`
- `0x1800154fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011713`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011709`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011709`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001167b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001167b`

## string_xrefs

- `0x180011674`: `pdh.dll`
- `0x1800116ab`: `[CXL] Could not format {0} to a message, because cannot load pdh.dll {1}`

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
      std::wstring::assign(a2, Buffer);
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
0x180011648  mov     [rsp-18h+arg_8], rbx
0x18001164d  push    rbp
0x18001164e  push    rsi
0x18001164f  push    rdi
0x180011650  mov     rbp, rsp
0x180011653  sub     rsp, 60h
0x180011657  mov     rdi, rdx
0x18001165a  mov     rsi, rcx
0x18001165d  mov     [rbp+Buffer], 0
0x180011665  call    ?GetWinError@ErrorCode@cxl@@QEBAKXZ; cxl::ErrorCode::GetWinError(void)
0x18001166a  mov     ebx, eax
0x18001166c  xor     edx, edx; lpSource
0x18001166e  cmp     dword ptr [rsi+4], 6
0x180011672  jnz     short loc_1800116D5
0x180011674  lea     rcx, aPdhDll; "pdh.dll"
0x18001167b  call    cs:__imp_LoadLibraryW
0x180011681  mov     rdx, rax
0x180011684  test    rax, rax
0x180011687  jnz     short loc_1800116D5
0x180011689  call    cs:__imp_GetLastError
0x18001168f  mov     ebx, eax
0x180011691  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180011696  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x18001169a  mov     [rbp+arg_0], ebx
0x18001169d  mov     [rbp+arg_4], 0
0x1800116a4  lea     r9, [rbp+arg_0]
0x1800116a8  mov     r8, rsi
0x1800116ab  lea     rdx, aCxlCouldNotFor; "[CXL] Could not format {0} to a message"...
0x1800116b2  call    ??$WriteLine@DVErrorCode@cxl@@V12@@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@1@Z; cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(char const *,cxl::ErrorCode const &,cxl::ErrorCode const &)
0x1800116b7  mov     rdx, rdi
0x1800116ba  lea     rcx, [rbp+var_20]
0x1800116be  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800116c3  nop
0x1800116c4  mov     r8, rsi
0x1800116c7  mov     rcx, rax; struct cxl::TextWriter *
0x1800116ca  call    ??$Write@DVErrorCode@cxl@@$$V@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@@Z; cxl::TextWriter::Write<char,cxl::ErrorCode,>(char const *,cxl::ErrorCode const &)
0x1800116cf  nop
0x1800116d0  jmp     loc_18001177E
0x1800116d5  mov     rax, rdx
0x1800116d8  neg     rax
0x1800116db  sbb     ecx, ecx
0x1800116dd  and     ecx, 0FFFFF800h
0x1800116e3  add     ecx, 1100h; dwFlags
0x1800116e9  mov     [rsp+60h+Arguments], 0; Arguments
0x1800116f2  mov     [rsp+60h+nSize], 0; nSize
0x1800116fa  lea     rax, [rbp+Buffer]
0x1800116fe  mov     [rsp+60h+lpBuffer], rax; lpBuffer
0x180011703  xor     r9d, r9d; dwLanguageId
0x180011706  mov     r8d, ebx; dwMessageId
0x180011709  call    cs:__imp_FormatMessageW
0x18001170f  test    eax, eax
0x180011711  jnz     short loc_18001175C
0x180011713  call    cs:__imp_GetLastError
0x180011719  mov     ebx, eax
0x18001171b  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180011720  lea     rcx, [rax+50h]; struct cxl::TextWriter *
0x180011724  mov     [rbp+arg_0], ebx
0x180011727  mov     [rbp+arg_4], 0
0x18001172e  lea     r9, [rbp+arg_0]
0x180011732  mov     r8, rsi
0x180011735  lea     rdx, aCxlCouldNotFor_0; "[CXL] Could not format {0} to a message"...
0x18001173c  call    ??$WriteLine@DVErrorCode@cxl@@V12@@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@1@Z; cxl::TextWriter::WriteLine<char,cxl::ErrorCode,cxl::ErrorCode>(char const *,cxl::ErrorCode const &,cxl::ErrorCode const &)
0x180011741  mov     rdx, rdi
0x180011744  lea     rcx, [rbp+var_20]
0x180011748  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001174d  nop
0x18001174e  mov     r8, rsi
0x180011751  mov     rcx, rax; struct cxl::TextWriter *
0x180011754  call    ??$Write@DVErrorCode@cxl@@$$V@TextWriter@cxl@@QEAAXPEBDAEBVErrorCode@1@@Z; cxl::TextWriter::Write<char,cxl::ErrorCode,>(char const *,cxl::ErrorCode const &)
0x180011759  nop
0x18001175a  jmp     short loc_180011776
0x18001175c  mov     rdx, [rbp+Buffer]
0x180011760  mov     [rbp+var_18], rdx
0x180011764  mov     rcx, rdi
0x180011767  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x18001176c  nop
0x18001176d  lea     rcx, [rbp+var_20]
0x180011771  call    ?Clear@?$LocalHeapPtr@E@cxl@@QEAAXXZ; cxl::LocalHeapPtr<uchar>::Clear(void)
0x180011776  mov     rcx, rdi
0x180011779  call    ?TrimWhiteSpace@cxl@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::TrimWhiteSpace(std::wstring &)
0x18001177e  mov     rbx, [rsp+60h+arg_8]
0x180011786  add     rsp, 60h
0x18001178a  pop     rdi
0x18001178b  pop     rsi
0x18001178c  pop     rbp
0x18001178d  retn
```
