# WriteFailureToAxeResultsXML(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>,int)

- ea: `0x14003b8bc`
- end: `0x14003ba86`
- name: `?WriteFailureToAxeResultsXML@@YAJV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0H@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14003b020`

## callees

- `0x1400039b8`
- `0x140005d78`
- `0x1400085b4`
- `0x140015bf4`
- `0x140015c28`
- `0x140016d04`
- `0x14003b8bc`

## import_xrefs

- `msvcrt!fwprintf` at `0x14003b972`
- `msvcrt!fwprintf` at `0x14003b983`
- `msvcrt!fwprintf` at `0x14003b994`
- `msvcrt!fwprintf` at `0x14003b9a5`
- `msvcrt!fwprintf` at `0x14003b9b6`
- `msvcrt!fwprintf` at `0x14003b9ca`
- `msvcrt!fwprintf` at `0x14003b9db`
- `msvcrt!fwprintf` at `0x14003b9ec`
- `msvcrt!fwprintf` at `0x14003b9fd`
- `msvcrt!fwprintf` at `0x14003ba0e`
- `msvcrt!fwprintf` at `0x14003ba1f`
- `msvcrt!fwprintf` at `0x14003ba30`
- `msvcrt!fwprintf` at `0x14003ba41`
- `msvcrt!fwprintf` at `0x14003b972`
- `msvcrt!fwprintf` at `0x14003b983`
- `msvcrt!fwprintf` at `0x14003b994`
- `msvcrt!fwprintf` at `0x14003b9a5`
- `msvcrt!fwprintf` at `0x14003b9b6`
- `msvcrt!fwprintf` at `0x14003b9ca`
- `msvcrt!fwprintf` at `0x14003b9db`
- `msvcrt!fwprintf` at `0x14003b9ec`
- `msvcrt!fwprintf` at `0x14003b9fd`
- `msvcrt!fwprintf` at `0x14003ba0e`
- `msvcrt!fwprintf` at `0x14003ba1f`
- `msvcrt!fwprintf` at `0x14003ba30`
- `msvcrt!fwprintf` at `0x14003ba41`
- `msvcrt!fclose` at `0x14003ba50`
- `msvcrt!fclose` at `0x14003ba50`
- `msvcrt!_wfopen_s` at `0x14003b93d`
- `msvcrt!_wfopen_s` at `0x14003b93d`

## string_xrefs

- `0x14003b91b`: `results.xml`
- `0x14003b967`: `<?xml version="1.0" encoding="UTF-8" standalone="yes"?>\n`
- `0x14003b959`: `AxeErrorXML: Error creating results.xml file.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WriteFailureToAxeResultsXML(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int v8; // edi
  FILE *v9; // rcx
  _QWORD v11[2]; // [rsp+20h] [rbp-10h] BYREF
  FILE *Stream; // [rsp+78h] [rbp+48h] BYREF

  Stream = 0;
  v6 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_AxeResultsFolderPath);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    v11,
    *(_WORD **)(*(_QWORD *)v6 + 24LL));
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
    a1,
    L" ");
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(a1, a2);
  v7 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
         v11,
         L"results.xml");
  if ( _wfopen_s(&Stream, *(const wchar_t **)(*(_QWORD *)v7 + 24LL), L"w, ccs=UTF-8") )
  {
    v8 = -2147467259;
    v9 = _acrt_iob_func(1u);
    fwprintf(v9, L"AxeErrorXML: Error creating results.xml file.\n");
  }
  else
  {
    v8 = 0;
    fwprintf(Stream, L"<?xml version=\"1.0\" encoding=\"UTF-8\" standalone=\"yes\"?>\n");
    fwprintf(Stream, L"<AssessmentResult>\n");
    fwprintf(Stream, L" <ErrorsAndWarnings>\n");
    fwprintf(Stream, L"  <Error>\n");
    fwprintf(Stream, L"   <Hresult>");
    fwprintf(Stream, L"%d", a3);
    fwprintf(Stream, L"</Hresult>\n");
    fwprintf(Stream, L"    <Message>");
    fwprintf(Stream, *(const wchar_t *const *)(*(_QWORD *)a1 + 24LL));
    fwprintf(Stream, L"</Message>\n");
    fwprintf(Stream, L"  </Error>\n");
    fwprintf(Stream, L" </ErrorsAndWarnings>\n");
    fwprintf(Stream, L"</AssessmentResult>\n");
  }
  if ( Stream )
  {
    fclose(Stream);
    Stream = 0;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v11);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(a1);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(a2);
  return v8;
}

```

## disassembly

```asm
0x14003b8bc  mov     [rsp-28h+arg_8], rdx
0x14003b8c1  mov     [rsp-28h+arg_0], rcx
0x14003b8c6  push    rbp
0x14003b8c7  push    rbx
0x14003b8c8  push    rsi
0x14003b8c9  push    rdi
0x14003b8ca  push    r14
0x14003b8cc  mov     rbp, rsp
0x14003b8cf  sub     rsp, 30h
0x14003b8d3  mov     r14d, r8d
0x14003b8d6  mov     rsi, rdx
0x14003b8d9  mov     rbx, rcx
0x14003b8dc  mov     [rbp+Stream], 0
0x14003b8e4  lea     rcx, ?s_AxeResultsFolderPath@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_AxeResultsFolderPath
0x14003b8eb  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14003b8f0  mov     rdx, [rax]
0x14003b8f3  mov     rdx, [rdx+18h]
0x14003b8f7  lea     rcx, [rbp+var_10]
0x14003b8fb  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14003b900  nop
0x14003b901  lea     rdx, asc_14012B49C; " "
0x14003b908  mov     rcx, rbx
0x14003b90b  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x14003b910  mov     rdx, rsi
0x14003b913  mov     rcx, rbx
0x14003b916  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@AEBV12@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14003b91b  lea     rdx, aResultsXml; "results.xml"
0x14003b922  lea     rcx, [rbp+var_10]
0x14003b926  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x14003b92b  mov     rdx, [rax]
0x14003b92e  lea     r8, aWCcsUtf8; "w, ccs=UTF-8"
0x14003b935  mov     rdx, [rdx+18h]; FileName
0x14003b939  lea     rcx, [rbp+Stream]; Stream
0x14003b93d  call    cs:__imp__wfopen_s
0x14003b943  test    eax, eax
0x14003b945  jz      short loc_14003B965
0x14003b947  mov     edi, 80004005h
0x14003b94c  mov     ecx, 1; Ix
0x14003b951  call    __acrt_iob_func
0x14003b956  mov     rcx, rax
0x14003b959  lea     rdx, aAxeerrorxmlErr; "AxeErrorXML: Error creating results.xml"...
0x14003b960  jmp     loc_14003BA41
0x14003b965  xor     edi, edi
0x14003b967  lea     rdx, aXmlVersion10En_1; "<?xml version=\"1.0\" encoding=\"UTF-8"...
0x14003b96e  mov     rcx, [rbp+Stream]; Stream
0x14003b972  call    cs:__imp_fwprintf
0x14003b978  lea     rdx, aAssessmentresu_0; "<AssessmentResult>\n"
0x14003b97f  mov     rcx, [rbp+Stream]; Stream
0x14003b983  call    cs:__imp_fwprintf
0x14003b989  lea     rdx, aErrorsandwarni; " <ErrorsAndWarnings>\n"
0x14003b990  mov     rcx, [rbp+Stream]; Stream
0x14003b994  call    cs:__imp_fwprintf
0x14003b99a  lea     rdx, aError_0; "  <Error>\n"
0x14003b9a1  mov     rcx, [rbp+Stream]; Stream
0x14003b9a5  call    cs:__imp_fwprintf
0x14003b9ab  lea     rdx, aHresult; "   <Hresult>"
0x14003b9b2  mov     rcx, [rbp+Stream]; Stream
0x14003b9b6  call    cs:__imp_fwprintf
0x14003b9bc  mov     r8d, r14d
0x14003b9bf  lea     rdx, aD; "%d"
0x14003b9c6  mov     rcx, [rbp+Stream]; Stream
0x14003b9ca  call    cs:__imp_fwprintf
0x14003b9d0  lea     rdx, aHresult_1; "</Hresult>\n"
0x14003b9d7  mov     rcx, [rbp+Stream]; Stream
0x14003b9db  call    cs:__imp_fwprintf
0x14003b9e1  lea     rdx, aMessage; "    <Message>"
0x14003b9e8  mov     rcx, [rbp+Stream]; Stream
0x14003b9ec  call    cs:__imp_fwprintf
0x14003b9f2  mov     rdx, [rbx]
0x14003b9f5  mov     rdx, [rdx+18h]; Format
0x14003b9f9  mov     rcx, [rbp+Stream]; Stream
0x14003b9fd  call    cs:__imp_fwprintf
0x14003ba03  lea     rdx, aMessage_0; "</Message>\n"
0x14003ba0a  mov     rcx, [rbp+Stream]; Stream
0x14003ba0e  call    cs:__imp_fwprintf
0x14003ba14  lea     rdx, aError; "  </Error>\n"
0x14003ba1b  mov     rcx, [rbp+Stream]; Stream
0x14003ba1f  call    cs:__imp_fwprintf
0x14003ba25  lea     rdx, aErrorsandwarni_0; " </ErrorsAndWarnings>\n"
0x14003ba2c  mov     rcx, [rbp+Stream]; Stream
0x14003ba30  call    cs:__imp_fwprintf
0x14003ba36  lea     rdx, aAssessmentresu_1; "</AssessmentResult>\n"
0x14003ba3d  mov     rcx, [rbp+Stream]; Stream
0x14003ba41  call    cs:__imp_fwprintf
0x14003ba47  mov     rcx, [rbp+Stream]; Stream
0x14003ba4b  test    rcx, rcx
0x14003ba4e  jz      short loc_14003BA5E
0x14003ba50  call    cs:__imp_fclose
0x14003ba56  mov     [rbp+Stream], 0
0x14003ba5e  lea     rcx, [rbp+var_10]
0x14003ba62  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003ba67  nop
0x14003ba68  mov     rcx, rbx
0x14003ba6b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003ba70  nop
0x14003ba71  mov     rcx, rsi
0x14003ba74  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003ba79  mov     eax, edi
0x14003ba7b  add     rsp, 30h
0x14003ba7f  pop     r14
0x14003ba81  pop     rdi
0x14003ba82  pop     rsi
0x14003ba83  pop     rbx
0x14003ba84  pop     rbp
0x14003ba85  retn
```
