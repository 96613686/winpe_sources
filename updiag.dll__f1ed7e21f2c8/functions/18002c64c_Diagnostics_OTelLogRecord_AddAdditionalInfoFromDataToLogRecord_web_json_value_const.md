# Diagnostics::OTelLogRecord::AddAdditionalInfoFromDataToLogRecord(web::json::value const &)

- ea: `0x18002c64c`
- end: `0x18002d326`
- name: `?AddAdditionalInfoFromDataToLogRecord@OTelLogRecord@Diagnostics@@AEAAXAEBVvalue@json@web@@@Z`
- size: `3290`
- prototype: `void __fastcall(Diagnostics::OTelLogRecord *__hidden this, const struct web::json::value *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18002ad6c`

## callees

- `0x180008a2c`
- `0x18001815c`
- `0x180018e64`
- `0x180018eec`
- `0x180019080`
- `0x18001abd4`
- `0x18002ba50`
- `0x18002c578`
- `0x18002c64c`
- `0x180073164`
- `0x180096170`

## string_xrefs

- `0x18002d1c8`: `JSON 'baseData' field must be an object for Span records`
- `0x18002d2b2`: `JSON 'logRecord' field must be an object`
- `0x18002d28a`: `JSON must contain 'logRecord' field`
- `0x18002d2da`: `JSON 'logLevel' field must be a string`
- `0x18002d302`: `JSON 'categoryName' field must be a string`
- `0x18002d130`: `JSON 'formattedMessage' field must be a string`
- `0x18002d1ea`: `JSON 'parentId' field must be a string for Span records`
- `0x18002d212`: `JSON 'statusCode' field must be a number for Span records`
- `0x18002d23a`: `JSON must contain 'activity' field for Span records`
- `0x18002d262`: `JSON 'activity' field must be an object for Span records`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Diagnostics::OTelLogRecord::AddAdditionalInfoFromDataToLogRecord(
        Diagnostics::OTelLogRecord *this,
        const struct web::json::value *a2)
{
  int v4; // r14d
  char v5; // bl
  _QWORD *v6; // r15
  char v7; // bl
  _QWORD *v8; // rax
  bool v9; // si
  _QWORD *v10; // rax
  char v11; // bl
  _QWORD *v12; // rax
  bool v13; // si
  _QWORD *v14; // rax
  char v15; // bl
  _QWORD *v16; // rax
  bool v17; // si
  _QWORD *v18; // rax
  _QWORD *v19; // rsi
  char v20; // bl
  _QWORD *v21; // rbx
  char v22; // bl
  _QWORD *v23; // rbx
  int v24; // edx
  int v25; // edx
  char v26; // bl
  _QWORD *v27; // rsi
  char v28; // bl
  const struct web::json::value *v29; // rbx
  char v30; // bl
  _QWORD *v31; // rsi
  char v32; // bl
  _QWORD *v33; // rbx
  WCHAR *v34; // rax
  char v35; // bl
  _QWORD *v36; // rbx
  char v37; // bl
  _QWORD *v38; // rbx
  char v39; // bl
  unsigned int v40; // eax
  int v41; // r8d
  unsigned int v42; // eax
  unsigned int v43; // eax
  char *v44; // [rsp+28h] [rbp-31h]
  __int128 v45; // [rsp+30h] [rbp-29h] BYREF
  __int128 v46; // [rsp+40h] [rbp-19h]
  __int128 v47; // [rsp+50h] [rbp-9h] BYREF
  __int128 v48; // [rsp+60h] [rbp+7h]
  __int128 v49; // [rsp+70h] [rbp+17h] BYREF
  __int128 v50; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v45 = 0;
  v46 = 0;
  v4 = 2;
  std::wstring::_Construct<1,wchar_t const *>(&v45, L"dt", 2u);
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2, &v45);
  std::wstring::~wstring((__int64)&v45);
  if ( v5 )
  {
    v45 = 0;
    v46 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v45, L"dt", 2u);
    v6 = (_QWORD *)web::json::value::at(a2, &v45);
    std::wstring::~wstring((__int64)&v45);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 88LL))(*v6) == 3 )
    {
      v49 = 0;
      v50 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v49, L"spanId", 6u);
      v7 = 1;
      v9 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v6 + 8LL))(*v6, &v49) )
      {
        v47 = 0;
        v48 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v47, L"spanId", 6u);
        v7 = 3;
        v8 = (_QWORD *)web::json::value::at(v6, &v47);
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 88LL))(*v8) == 2 )
          v9 = 1;
      }
      if ( (v7 & 2) != 0 )
      {
        v7 &= ~2u;
        std::wstring::~wstring((__int64)&v47);
      }
      if ( (v7 & 1) != 0 )
      {
        v7 &= ~1u;
        std::wstring::~wstring((__int64)&v49);
      }
      if ( v9 )
      {
        v49 = 0;
        v50 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v49, L"spanId", 6u);
        v10 = (_QWORD *)web::json::value::at(v6, &v49);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 176LL))(*v10);
        std::wstring::operator=((char *)this + 64);
        std::wstring::~wstring((__int64)&v49);
      }
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"traceId", 7u);
      v11 = v7 | 4;
      v13 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v6 + 8LL))(*v6, &v47) )
      {
        v49 = 0;
        v50 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v49, L"traceId", 7u);
        v11 |= 8u;
        v12 = (_QWORD *)web::json::value::at(v6, &v49);
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 88LL))(*v12) == 2 )
          v13 = 1;
      }
      if ( (v11 & 8) != 0 )
      {
        v11 &= ~8u;
        std::wstring::~wstring((__int64)&v49);
      }
      if ( (v11 & 4) != 0 )
      {
        v11 &= ~4u;
        std::wstring::~wstring((__int64)&v47);
      }
      if ( v13 )
      {
        v49 = 0;
        v50 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v49, L"traceId", 7u);
        v14 = (_QWORD *)web::json::value::at(v6, &v49);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 176LL))(*v14);
        std::wstring::operator=((char *)this + 96);
        std::wstring::~wstring((__int64)&v49);
      }
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"parentId", 8u);
      v15 = v11 | 0x10;
      v17 = 0;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v6 + 8LL))(*v6, &v47) )
      {
        v49 = 0;
        v50 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v49, L"parentId", 8u);
        v15 |= 0x20u;
        v16 = (_QWORD *)web::json::value::at(v6, &v49);
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 88LL))(*v16) == 2 )
          v17 = 1;
      }
      if ( (v15 & 0x20) != 0 )
      {
        v15 &= ~0x20u;
        std::wstring::~wstring((__int64)&v49);
      }
      if ( (v15 & 0x10) != 0 )
        std::wstring::~wstring((__int64)&v47);
      if ( v17 )
      {
        v49 = 0;
        v50 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v49, L"parentId", 8u);
        v18 = (_QWORD *)web::json::value::at(v6, &v49);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 176LL))(*v18);
        std::wstring::operator=((char *)this + 232);
        std::wstring::~wstring((__int64)&v49);
      }
    }
  }
  if ( *((_BYTE *)this + 224) )
  {
    if ( !*((_QWORD *)this + 10) )
    {
      v42 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x148,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
        (const char *)v42,
        (int)"spanId is required for Span records",
        v44);
    }
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v49, L"baseData", 8u);
    v19 = (_QWORD *)web::json::value::at(a2, &v49);
    std::wstring::~wstring((__int64)&v49);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 88LL))(*v19) != 3 )
    {
      v43 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x3ED,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
        (const char *)v43,
        (int)"JSON 'baseData' field must be an object for Span records",
        v44);
    }
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v47, L"parentId", 8u);
    v20 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v19 + 8LL))(*v19, &v47);
    std::wstring::~wstring((__int64)&v47);
    if ( v20 )
    {
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"parentId", 8u);
      v21 = (_QWORD *)web::json::value::at(v19, &v47);
      std::wstring::~wstring((__int64)&v47);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 88LL))(*v21) != 2 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x3F6,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'parentId' field must be a string for Span records",
          v44);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 176LL))(*v21);
      std::wstring::operator=((char *)this + 232);
    }
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v47, L"statusCode", 0xAu);
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v19 + 8LL))(*v19, &v47);
    std::wstring::~wstring((__int64)&v47);
    if ( v22 )
    {
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"statusCode", 0xAu);
      v23 = (_QWORD *)web::json::value::at(v19, &v47);
      std::wstring::~wstring((__int64)&v47);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 88LL))(*v23) )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x401,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'statusCode' field must be a number for Span records",
          v44);
      v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 128LL))(*v23);
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          if ( v25 != 1 )
          {
            v40 = wil::verify_hresult<long>(2147942487LL);
            LODWORD(v44) = v41;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x445,
              (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
              (const char *)v40,
              (int)"Invalid statusCode int value %d, we expect 0 (Unset), 1 (Ok), or 2 (Error)",
              v44);
          }
        }
        else
        {
          v4 = 1;
        }
      }
      else
      {
        v4 = 0;
      }
      *((_DWORD *)this + 66) = v4;
    }
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v49, L"activity", 8u);
    v26 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2, &v49);
    std::wstring::~wstring((__int64)&v49);
    if ( !v26 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x409,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
        (const char *)0xA0,
        (unsigned int)"JSON must contain 'activity' field for Span records",
        v44);
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v49, L"activity", 8u);
    v27 = (_QWORD *)web::json::value::at(a2, &v49);
    std::wstring::~wstring((__int64)&v49);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 88LL))(*v27) != 3 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x40E,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
        (const char *)0x65D,
        (unsigned int)"JSON 'activity' field must be an object for Span records",
        v44);
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v47, L"tags", 4u);
    v28 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v27 + 8LL))(*v27, &v47);
    std::wstring::~wstring((__int64)&v47);
    if ( v28 )
    {
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"tags", 4u);
      v29 = (const struct web::json::value *)web::json::value::at(v27, &v47);
      goto LABEL_65;
    }
  }
  else
  {
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v49, L"logRecord", 9u);
    v30 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2, &v49);
    std::wstring::~wstring((__int64)&v49);
    if ( !v30 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x3B5,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
        (const char *)0xA0,
        (unsigned int)"JSON must contain 'logRecord' field",
        v44);
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v49, L"logRecord", 9u);
    v31 = (_QWORD *)web::json::value::at(a2, &v49);
    std::wstring::~wstring((__int64)&v49);
    if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 88LL))(*v31) != 3 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x3BA,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
        (const char *)0x65D,
        (unsigned int)"JSON 'logRecord' field must be an object",
        v44);
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v47, L"logLevel", 8u);
    v32 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v31 + 8LL))(*v31, &v47);
    std::wstring::~wstring((__int64)&v47);
    if ( v32 )
    {
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"logLevel", 8u);
      v33 = (_QWORD *)web::json::value::at(v31, &v47);
      std::wstring::~wstring((__int64)&v47);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v33 + 88LL))(*v33) != 2 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x3C3,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'logLevel' field must be a string",
          v44);
      v34 = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v33 + 176LL))(*v33);
      *((_DWORD *)this + 67) = Diagnostics::OTelLogRecord::GetLogLevelFromString(v34);
    }
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v47, L"categoryName", 0xCu);
    v35 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v31 + 8LL))(*v31, &v47);
    std::wstring::~wstring((__int64)&v47);
    if ( v35 )
    {
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"categoryName", 0xCu);
      v36 = (_QWORD *)web::json::value::at(v31, &v47);
      std::wstring::~wstring((__int64)&v47);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v36 + 88LL))(*v36) != 2 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x3CE,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'categoryName' field must be a string",
          v44);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v36 + 176LL))(*v36);
      std::wstring::operator=((char *)this + 272);
    }
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v47, L"formattedMessage", 0x10u);
    v37 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v31 + 8LL))(*v31, &v47);
    std::wstring::~wstring((__int64)&v47);
    if ( v37 )
    {
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"formattedMessage", 0x10u);
      v38 = (_QWORD *)web::json::value::at(v31, &v47);
      std::wstring::~wstring((__int64)&v47);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v38 + 88LL))(*v38) != 2 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x3D9,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'formattedMessage' field must be a string",
          v44);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v38 + 176LL))(*v38);
      std::wstring::operator=((char *)this + 304);
    }
    v47 = 0;
    v48 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v47, L"attributes", 0xAu);
    v39 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v31 + 8LL))(*v31, &v47);
    std::wstring::~wstring((__int64)&v47);
    if ( v39 )
    {
      v47 = 0;
      v48 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v47, L"attributes", 0xAu);
      v29 = (const struct web::json::value *)web::json::value::at(v31, &v47);
LABEL_65:
      std::wstring::~wstring((__int64)&v47);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v29 + 88LL))(*(_QWORD *)v29) == 3 )
        Diagnostics::OTelLogRecord::AddAttributesFromJsonToRecord(this, v29);
    }
  }
}

```

## disassembly

```asm
0x18002c64c  mov     [rsp-8+arg_8], rbx
0x18002c651  mov     [rsp-8+arg_10], rsi
0x18002c656  push    rbp
0x18002c657  push    rdi
0x18002c658  push    r12
0x18002c65a  push    r14
0x18002c65c  push    r15
0x18002c65e  lea     rbp, [rsp-37h]
0x18002c663  sub     rsp, 90h
0x18002c66a  mov     r12, rdx
0x18002c66d  mov     rdi, rcx
0x18002c670  mov     [rbp+57h+arg_0], 0
0x18002c677  xorps   xmm0, xmm0
0x18002c67a  movups  [rbp+57h+var_80], xmm0
0x18002c67e  xorps   xmm1, xmm1
0x18002c681  movdqu  [rbp+57h+var_70], xmm1
0x18002c686  mov     r14d, 2
0x18002c68c  mov     r8d, r14d
0x18002c68f  lea     rdx, aDt; "dt"
0x18002c696  lea     rcx, [rbp+57h+var_80]
0x18002c69a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c69f  nop
0x18002c6a0  mov     rcx, [r12]
0x18002c6a4  mov     rax, [rcx]
0x18002c6a7  lea     rdx, [rbp+57h+var_80]
0x18002c6ab  mov     rax, [rax+8]
0x18002c6af  call    _guard_dispatch_icall
0x18002c6b4  mov     bl, al
0x18002c6b6  lea     rcx, [rbp+57h+var_80]
0x18002c6ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c6bf  test    bl, bl
0x18002c6c1  jz      loc_18002CA60
0x18002c6c7  xorps   xmm0, xmm0
0x18002c6ca  movups  [rbp+57h+var_80], xmm0
0x18002c6ce  xorps   xmm1, xmm1
0x18002c6d1  movdqu  [rbp+57h+var_70], xmm1
0x18002c6d6  mov     r8d, r14d
0x18002c6d9  lea     rdx, aDt; "dt"
0x18002c6e0  lea     rcx, [rbp+57h+var_80]
0x18002c6e4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c6e9  nop
0x18002c6ea  lea     rdx, [rbp+57h+var_80]
0x18002c6ee  mov     rcx, r12
0x18002c6f1  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002c6f6  mov     r15, rax
0x18002c6f9  lea     rcx, [rbp+57h+var_80]
0x18002c6fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c702  mov     rcx, [r15]
0x18002c705  mov     rdx, [rcx]
0x18002c708  mov     rax, [rdx+58h]
0x18002c70c  call    _guard_dispatch_icall
0x18002c711  cmp     eax, 3
0x18002c714  jnz     loc_18002CA60
0x18002c71a  xorps   xmm0, xmm0
0x18002c71d  movups  [rbp+57h+var_40], xmm0
0x18002c721  xorps   xmm1, xmm1
0x18002c724  movdqu  [rbp+57h+var_30], xmm1
0x18002c729  lea     esi, [rax+3]
0x18002c72c  mov     r8d, esi
0x18002c72f  lea     rdx, aSpanid; "spanId"
0x18002c736  lea     rcx, [rbp+57h+var_40]
0x18002c73a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c73f  nop
0x18002c740  lea     ebx, [rsi-5]
0x18002c743  mov     [rbp+57h+arg_0], ebx
0x18002c746  mov     rcx, [r15]
0x18002c749  mov     rax, [rcx]
0x18002c74c  lea     rdx, [rbp+57h+var_40]
0x18002c750  mov     rax, [rax+8]
0x18002c754  call    _guard_dispatch_icall
0x18002c759  test    al, al
0x18002c75b  jz      short loc_18002C7AB
0x18002c75d  xorps   xmm0, xmm0
0x18002c760  movups  [rbp+57h+var_60], xmm0
0x18002c764  xorps   xmm1, xmm1
0x18002c767  movdqu  [rbp+57h+var_50], xmm1
0x18002c76c  mov     r8d, esi
0x18002c76f  lea     rdx, aSpanid; "spanId"
0x18002c776  lea     rcx, [rbp+57h+var_60]
0x18002c77a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c77f  nop
0x18002c780  lea     ebx, [rsi-3]
0x18002c783  mov     [rbp+57h+arg_0], ebx
0x18002c786  lea     rdx, [rbp+57h+var_60]
0x18002c78a  mov     rcx, r15
0x18002c78d  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002c792  mov     rcx, [rax]
0x18002c795  mov     rax, [rcx]
0x18002c798  mov     rax, [rax+58h]
0x18002c79c  call    _guard_dispatch_icall
0x18002c7a1  cmp     eax, r14d
0x18002c7a4  jnz     short loc_18002C7AB
0x18002c7a6  mov     sil, 1
0x18002c7a9  jmp     short loc_18002C7AE
0x18002c7ab  xor     sil, sil
0x18002c7ae  test    r14b, bl
0x18002c7b1  jz      short loc_18002C7C0
0x18002c7b3  and     ebx, 0FFFFFFFDh
0x18002c7b6  lea     rcx, [rbp+57h+var_60]
0x18002c7ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c7bf  nop
0x18002c7c0  test    bl, 1
0x18002c7c3  jz      short loc_18002C7D1
0x18002c7c5  and     ebx, 0FFFFFFFEh
0x18002c7c8  lea     rcx, [rbp+57h+var_40]
0x18002c7cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c7d1  test    sil, sil
0x18002c7d4  jz      short loc_18002C830
0x18002c7d6  xorps   xmm0, xmm0
0x18002c7d9  movups  [rbp+57h+var_40], xmm0
0x18002c7dd  xorps   xmm1, xmm1
0x18002c7e0  movdqu  [rbp+57h+var_30], xmm1
0x18002c7e5  mov     r8d, 6
0x18002c7eb  lea     rdx, aSpanid; "spanId"
0x18002c7f2  lea     rcx, [rbp+57h+var_40]
0x18002c7f6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c7fb  nop
0x18002c7fc  lea     rdx, [rbp+57h+var_40]
0x18002c800  mov     rcx, r15
0x18002c803  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002c808  mov     rcx, [rax]
0x18002c80b  mov     rax, [rcx]
0x18002c80e  mov     rax, [rax+0B0h]
0x18002c815  call    _guard_dispatch_icall
0x18002c81a  lea     rcx, [rdi+40h]; void *
0x18002c81e  mov     rdx, rax
0x18002c821  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002c826  nop
0x18002c827  lea     rcx, [rbp+57h+var_40]
0x18002c82b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c830  xorps   xmm0, xmm0
0x18002c833  movups  [rbp+57h+var_60], xmm0
0x18002c837  xorps   xmm1, xmm1
0x18002c83a  movdqu  [rbp+57h+var_50], xmm1
0x18002c83f  mov     esi, 7
0x18002c844  mov     r8d, esi
0x18002c847  lea     rdx, aTraceid; "traceId"
0x18002c84e  lea     rcx, [rbp+57h+var_60]
0x18002c852  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c857  nop
0x18002c858  or      ebx, 4
0x18002c85b  mov     [rbp+57h+arg_0], ebx
0x18002c85e  mov     rcx, [r15]
0x18002c861  mov     rax, [rcx]
0x18002c864  lea     rdx, [rbp+57h+var_60]
0x18002c868  mov     rax, [rax+8]
0x18002c86c  call    _guard_dispatch_icall
0x18002c871  test    al, al
0x18002c873  jz      short loc_18002C8C3
0x18002c875  xorps   xmm0, xmm0
0x18002c878  movups  [rbp+57h+var_40], xmm0
0x18002c87c  xorps   xmm1, xmm1
0x18002c87f  movdqu  [rbp+57h+var_30], xmm1
0x18002c884  mov     r8d, esi
0x18002c887  lea     rdx, aTraceid; "traceId"
0x18002c88e  lea     rcx, [rbp+57h+var_40]
0x18002c892  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c897  nop
0x18002c898  or      ebx, 8
0x18002c89b  mov     [rbp+57h+arg_0], ebx
0x18002c89e  lea     rdx, [rbp+57h+var_40]
0x18002c8a2  mov     rcx, r15
0x18002c8a5  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002c8aa  mov     rcx, [rax]
0x18002c8ad  mov     rax, [rcx]
0x18002c8b0  mov     rax, [rax+58h]
0x18002c8b4  call    _guard_dispatch_icall
0x18002c8b9  cmp     eax, r14d
0x18002c8bc  jnz     short loc_18002C8C3
0x18002c8be  mov     sil, 1
0x18002c8c1  jmp     short loc_18002C8C6
0x18002c8c3  xor     sil, sil
0x18002c8c6  test    bl, 8
0x18002c8c9  jz      short loc_18002C8D8
0x18002c8cb  and     ebx, 0FFFFFFF7h
0x18002c8ce  lea     rcx, [rbp+57h+var_40]
0x18002c8d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c8d7  nop
0x18002c8d8  test    bl, 4
0x18002c8db  jz      short loc_18002C8E9
0x18002c8dd  and     ebx, 0FFFFFFFBh
0x18002c8e0  lea     rcx, [rbp+57h+var_60]
0x18002c8e4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c8e9  test    sil, sil
0x18002c8ec  jz      short loc_18002C948
0x18002c8ee  xorps   xmm0, xmm0
0x18002c8f1  movups  [rbp+57h+var_40], xmm0
0x18002c8f5  xorps   xmm1, xmm1
0x18002c8f8  movdqu  [rbp+57h+var_30], xmm1
0x18002c8fd  mov     r8d, 7
0x18002c903  lea     rdx, aTraceid; "traceId"
0x18002c90a  lea     rcx, [rbp+57h+var_40]
0x18002c90e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c913  nop
0x18002c914  lea     rdx, [rbp+57h+var_40]
0x18002c918  mov     rcx, r15
0x18002c91b  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002c920  mov     rcx, [rax]
0x18002c923  mov     rax, [rcx]
0x18002c926  mov     rax, [rax+0B0h]
0x18002c92d  call    _guard_dispatch_icall
0x18002c932  lea     rcx, [rdi+60h]; void *
0x18002c936  mov     rdx, rax
0x18002c939  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002c93e  nop
0x18002c93f  lea     rcx, [rbp+57h+var_40]
0x18002c943  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c948  xorps   xmm0, xmm0
0x18002c94b  movups  [rbp+57h+var_60], xmm0
0x18002c94f  xorps   xmm1, xmm1
0x18002c952  movdqu  [rbp+57h+var_50], xmm1
0x18002c957  mov     esi, 8
0x18002c95c  mov     r8d, esi
0x18002c95f  lea     rdx, aParentid; "parentId"
0x18002c966  lea     rcx, [rbp+57h+var_60]
0x18002c96a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c96f  nop
0x18002c970  or      ebx, 10h
0x18002c973  mov     [rbp+57h+arg_0], ebx
0x18002c976  mov     rcx, [r15]
0x18002c979  mov     rax, [rcx]
0x18002c97c  lea     rdx, [rbp+57h+var_60]
0x18002c980  mov     rax, [rax+8]
0x18002c984  call    _guard_dispatch_icall
0x18002c989  test    al, al
0x18002c98b  jz      short loc_18002C9DB
0x18002c98d  xorps   xmm0, xmm0
0x18002c990  movups  [rbp+57h+var_40], xmm0
0x18002c994  xorps   xmm1, xmm1
0x18002c997  movdqu  [rbp+57h+var_30], xmm1
0x18002c99c  mov     r8d, esi
0x18002c99f  lea     rdx, aParentid; "parentId"
0x18002c9a6  lea     rcx, [rbp+57h+var_40]
0x18002c9aa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002c9af  nop
0x18002c9b0  or      ebx, 20h
0x18002c9b3  mov     [rbp+57h+arg_0], ebx
0x18002c9b6  lea     rdx, [rbp+57h+var_40]
0x18002c9ba  mov     rcx, r15
0x18002c9bd  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002c9c2  mov     rcx, [rax]
0x18002c9c5  mov     rax, [rcx]
0x18002c9c8  mov     rax, [rax+58h]
0x18002c9cc  call    _guard_dispatch_icall
0x18002c9d1  cmp     eax, r14d
0x18002c9d4  jnz     short loc_18002C9DB
0x18002c9d6  mov     sil, 1
0x18002c9d9  jmp     short loc_18002C9DE
0x18002c9db  xor     sil, sil
0x18002c9de  test    bl, 20h
0x18002c9e1  jz      short loc_18002C9F0
0x18002c9e3  and     ebx, 0FFFFFFDFh
0x18002c9e6  lea     rcx, [rbp+57h+var_40]
0x18002c9ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c9ef  nop
0x18002c9f0  test    bl, 10h
0x18002c9f3  jz      short loc_18002C9FE
0x18002c9f5  lea     rcx, [rbp+57h+var_60]
0x18002c9f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c9fe  test    sil, sil
0x18002ca01  jz      short loc_18002CA60
0x18002ca03  xorps   xmm0, xmm0
0x18002ca06  movups  [rbp+57h+var_40], xmm0
0x18002ca0a  xorps   xmm1, xmm1
0x18002ca0d  movdqu  [rbp+57h+var_30], xmm1
0x18002ca12  mov     r8d, 8
0x18002ca18  lea     rdx, aParentid; "parentId"
0x18002ca1f  lea     rcx, [rbp+57h+var_40]
0x18002ca23  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002ca28  nop
0x18002ca29  lea     rdx, [rbp+57h+var_40]
0x18002ca2d  mov     rcx, r15
0x18002ca30  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002ca35  mov     rcx, [rax]
0x18002ca38  mov     rax, [rcx]
0x18002ca3b  mov     rax, [rax+0B0h]
0x18002ca42  call    _guard_dispatch_icall
0x18002ca47  lea     rcx, [rdi+0E8h]; void *
0x18002ca4e  mov     rdx, rax
0x18002ca51  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002ca56  nop
0x18002ca57  lea     rcx, [rbp+57h+var_40]
0x18002ca5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ca60  cmp     byte ptr [rdi+0E0h], 0
0x18002ca67  jz      loc_18002CD8F
0x18002ca6d  cmp     qword ptr [rdi+50h], 0
0x18002ca72  jz      loc_18002D188
0x18002ca78  xorps   xmm0, xmm0
0x18002ca7b  movups  [rbp+57h+var_40], xmm0
0x18002ca7f  xorps   xmm1, xmm1
0x18002ca82  movdqu  [rbp+57h+var_30], xmm1
0x18002ca87  mov     r8d, 8
0x18002ca8d  lea     rdx, aBasedata_0; "baseData"
0x18002ca94  lea     rcx, [rbp+57h+var_40]
0x18002ca98  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002ca9d  nop
0x18002ca9e  lea     rdx, [rbp+57h+var_40]
0x18002caa2  mov     rcx, r12
0x18002caa5  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002caaa  mov     rsi, rax
  ... truncated ...
```
