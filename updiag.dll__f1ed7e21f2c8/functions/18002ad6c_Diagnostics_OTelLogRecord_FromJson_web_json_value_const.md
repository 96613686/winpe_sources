# Diagnostics::OTelLogRecord::FromJson(web::json::value const &)

- ea: `0x18002ad6c`
- end: `0x18002b99e`
- name: `?FromJson@OTelLogRecord@Diagnostics@@SA?AV12@AEBVvalue@json@web@@@Z`
- size: `3122`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18002b9a4`

## callees

- `0x180008a2c`
- `0x18001815c`
- `0x180018b04`
- `0x180018bec`
- `0x180018e64`
- `0x180018eec`
- `0x180019080`
- `0x18001c92c`
- `0x1800293ec`
- `0x180029e44`
- `0x18002a018`
- `0x18002ad6c`
- `0x18002c64c`
- `0x180073164`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## string_xrefs

- `0x18002b69f`: `JSON root must be an object`
- `0x18002b6f5`: `JSON 'name' field must be a string`
- `0x18002b6ca`: `JSON must contain 'name' field`
- `0x18002b720`: `JSON must contain 'time' field`
- `0x18002b74b`: `JSON 'time' field must be a string`
- `0x18002b7a1`: `JSON 'ver' field must be a string`
- `0x18002b776`: `JSON must contain 'ver' field`
- `0x18002b7cc`: `JSON must contain 'data' field`
- `0x18002b7f7`: `JSON 'data' field must be an object`
- `0x18002b84d`: `JSON 'baseType' field must be a string`
- `0x18002b822`: `JSON 'data' object must contain 'baseType' field`
- `0x18002b878`: `JSON 'data' object must contain 'baseData' field for Span records`
- `0x18002b8a3`: `JSON 'baseData' field must be an object for Span records`
- `0x18002b8f9`: `JSON 'startTime' field must be a string`
- `0x18002b8ce`: `JSON 'baseData' object must contain 'startTime' field for Span records`
- `0x18002b924`: `JSON 'data' object must contain 'dt' field for Span records`
- `0x18002b94f`: `JSON 'dt' field must be an object for Span records`
- `0x18002b631`: `JSON 'spanId' field must be a string for Span records`
- `0x18002b97a`: `JSON 'dt' object must contain 'spanId' field for Span records`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void *__fastcall Diagnostics::OTelLogRecord::FromJson(void *a1, _QWORD *a2)
{
  char v4; // bl
  _QWORD *v5; // rbx
  __int64 v6; // rax
  char v7; // bl
  _QWORD *v8; // rbx
  __int64 v9; // rax
  char v10; // bl
  _QWORD *v11; // rbx
  __int64 v12; // rax
  char v13; // bl
  const struct web::json::value *v14; // rsi
  char v15; // bl
  _QWORD *v16; // rbx
  __int64 v17; // rax
  size_t v18; // r8
  const wchar_t *v19; // rcx
  wchar_t *v20; // rax
  unsigned __int64 v21; // rdx
  char v22; // bl
  _QWORD *v23; // rdi
  char v24; // bl
  _QWORD *v25; // rbx
  __int64 v26; // rax
  char v27; // bl
  _QWORD *v28; // rdi
  char v29; // bl
  _QWORD *v30; // rbx
  __int64 v31; // rax
  _QWORD *v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // r8
  _QWORD *v35; // rcx
  wchar_t **v37; // rcx
  _QWORD *v38; // rax
  _QWORD *v39; // rcx
  unsigned int v40; // eax
  const char *v41; // rdx
  char *v42; // [rsp+28h] [rbp-D8h]
  __int128 v43; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v44; // [rsp+40h] [rbp-C0h]
  __int128 v45; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v46; // [rsp+60h] [rbp-A0h]
  int v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v49[2]; // [rsp+80h] [rbp-80h] BYREF
  void *v50; // [rsp+A0h] [rbp-60h]
  _BYTE v51[32]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *S1[2]; // [rsp+D0h] [rbp-30h] BYREF
  size_t N; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v54; // [rsp+E8h] [rbp-18h]
  _QWORD v55[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v56; // [rsp+100h] [rbp+0h]
  unsigned __int64 v57; // [rsp+108h] [rbp+8h]
  _QWORD v58[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v59; // [rsp+120h] [rbp+20h]
  unsigned __int64 v60; // [rsp+128h] [rbp+28h]
  _BYTE v61[32]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v50 = a1;
  v47 = 1;
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 88LL))(*a2) != 3 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0xD,
      (unsigned int)"JSON root must be an object",
      v42);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"name", 4u);
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a2 + 8LL))(*a2, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( !v4 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0xA0,
      (unsigned int)"JSON must contain 'name' field",
      v42);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"name", 4u);
  v5 = (_QWORD *)web::json::value::at(a2, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 88LL))(*v5) != 2 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0x65D,
      (unsigned int)"JSON 'name' field must be a string",
      v42);
  v6 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 176LL))(*v5);
  std::wstring::wstring((__int64)v58, v6);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"time", 4u);
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a2 + 8LL))(*a2, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( !v7 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0xA0,
      (unsigned int)"JSON must contain 'time' field",
      v42);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"time", 4u);
  v8 = (_QWORD *)web::json::value::at(a2, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 88LL))(*v8) != 2 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1EC,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0x65D,
      (unsigned int)"JSON 'time' field must be a string",
      v42);
  v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 176LL))(*v8);
  System::Convert::ToTimePoint(&v47, v9);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"ver", 3u);
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a2 + 8LL))(*a2, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( !v10 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0xA0,
      (unsigned int)"JSON must contain 'ver' field",
      v42);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"ver", 3u);
  v11 = (_QWORD *)web::json::value::at(a2, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 88LL))(*v11) != 2 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0x65D,
      (unsigned int)"JSON 'ver' field must be a string",
      v42);
  v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 176LL))(*v11);
  std::wstring::wstring((__int64)v55, v12);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"data", 4u);
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a2 + 8LL))(*a2, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( !v13 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0xA0,
      (unsigned int)"JSON must contain 'data' field",
      v42);
  memset(v49, 0, sizeof(v49));
  std::wstring::_Construct<1,wchar_t const *>(v49, L"data", 4u);
  v14 = (const struct web::json::value *)web::json::value::at(a2, v49);
  std::wstring::~wstring((__int64)v49);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 88LL))(*(_QWORD *)v14) != 3 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x204,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0x65D,
      (unsigned int)"JSON 'data' field must be an object",
      v42);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"baseType", 8u);
  v15 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( !v15 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x209,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0xA0,
      (unsigned int)"JSON 'data' object must contain 'baseType' field",
      v42);
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v43, L"baseType", 8u);
  v16 = (_QWORD *)web::json::value::at(v14, &v43);
  std::wstring::~wstring((__int64)&v43);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 88LL))(*v16) != 2 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x20E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)0x65D,
      (unsigned int)"JSON 'baseType' field must be a string",
      v42);
  v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 176LL))(*v16);
  std::wstring::wstring((__int64)S1, v17);
  v18 = N;
  v19 = (const wchar_t *)S1;
  v20 = S1[0];
  v21 = v54;
  if ( v54 > 7 )
    v19 = S1[0];
  if ( N == 4 )
  {
    if ( !wmemcmp(v19, L"Span", 4u) )
    {
      v43 = 0;
      v44 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v43, L"baseData", 8u);
      v22 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14, &v43);
      std::wstring::~wstring((__int64)&v43);
      if ( !v22 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x218,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0xA0,
          (unsigned int)"JSON 'data' object must contain 'baseData' field for Span records",
          v42);
      v43 = 0;
      v44 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v43, L"baseData", 8u);
      v23 = (_QWORD *)web::json::value::at(v14, &v43);
      std::wstring::~wstring((__int64)&v43);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 88LL))(*v23) != 3 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x21D,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'baseData' field must be an object for Span records",
          v42);
      v45 = 0;
      v46 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v45, L"startTime", 9u);
      v24 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v23 + 8LL))(*v23, &v45);
      std::wstring::~wstring((__int64)&v45);
      if ( !v24 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x223,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0xA0,
          (unsigned int)"JSON 'baseData' object must contain 'startTime' field for Span records",
          v42);
      v45 = 0;
      v46 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v45, L"startTime", 9u);
      v25 = (_QWORD *)web::json::value::at(v23, &v45);
      std::wstring::~wstring((__int64)&v45);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 88LL))(*v25) != 2 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x228,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'startTime' field must be a string",
          v42);
      v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 176LL))(*v25);
      System::Convert::ToTimePoint(&v48, v26);
      v43 = 0;
      v44 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v43, L"dt", 2u);
      v27 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14, &v43);
      std::wstring::~wstring((__int64)&v43);
      if ( !v27 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x22F,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0xA0,
          (unsigned int)"JSON 'data' object must contain 'dt' field for Span records",
          v42);
      v43 = 0;
      v44 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v43, L"dt", 2u);
      v28 = (_QWORD *)web::json::value::at(v14, &v43);
      std::wstring::~wstring((__int64)&v43);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v28 + 88LL))(*v28) != 3 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x234,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'dt' field must be an object for Span records",
          v42);
      v45 = 0;
      v46 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v45, L"spanId", 6u);
      v29 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v28 + 8LL))(*v28, &v45);
      std::wstring::~wstring((__int64)&v45);
      if ( !v29 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x238,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0xA0,
          (unsigned int)"JSON 'dt' object must contain 'spanId' field for Span records",
          v42);
      v45 = 0;
      v46 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v45, L"spanId", 6u);
      v30 = (_QWORD *)web::json::value::at(v28, &v45);
      std::wstring::~wstring((__int64)&v45);
      if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 88LL))(*v30) != 2 )
        wil::details::in1diag3::Throw_Win32Msg(
          retaddr,
          (void *)0x23D,
          (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
          (const char *)0x65D,
          (unsigned int)"JSON 'spanId' field must be a string for Span records",
          v42);
      v31 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 176LL))(*v30);
      std::wstring::wstring((__int64)v61, v31);
      memset(a1, 0, 0x150u);
      v32 = v55;
      if ( v57 > 7 )
        v32 = (_QWORD *)v55[0];
      v33 = v56;
      v34 = std::wstring::wstring((__int64)v51, (__int64)v61);
      v35 = v58;
      if ( v60 > 7 )
        v35 = (_QWORD *)v58[0];
      *(_QWORD *)&v45 = v32;
      *((_QWORD *)&v45 + 1) = v33;
      *(_QWORD *)&v43 = v35;
      *((_QWORD *)&v43 + 1) = v59;
      Diagnostics::OTelLogRecord::OTelLogRecord(
        (_DWORD)a1,
        (unsigned int)&v47,
        (unsigned int)&v43,
        v48,
        v34,
        (__int64)&v45);
      v47 = 1;
      Diagnostics::OTelLogRecord::AddAdditionalInfoFromDataToLogRecord((Diagnostics::OTelLogRecord *)a1, v14);
      std::wstring::~wstring((__int64)v61);
      goto LABEL_29;
    }
    v21 = v54;
    v18 = N;
    v20 = S1[0];
  }
  v37 = S1;
  if ( v21 > 7 )
    v37 = (wchar_t **)v20;
  if ( v18 != 7 || wmemcmp((const wchar_t *)v37, L"LogSpan", 7u) )
  {
    std::wstring::c_str(S1);
    v40 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x458,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelLogRecord.hpp",
      (const char *)v40,
      (int)"Unsupported BaseType string %ls",
      v41);
  }
  memset(a1, 0, 0x150u);
  v38 = v55;
  if ( v57 > 7 )
    v38 = (_QWORD *)v55[0];
  v39 = v58;
  if ( v60 > 7 )
    v39 = (_QWORD *)v58[0];
  *(_QWORD *)&v43 = v38;
  *((_QWORD *)&v43 + 1) = v56;
  *(_QWORD *)&v45 = v39;
  *((_QWORD *)&v45 + 1) = v59;
  Diagnostics::OTelLogRecord::OTelLogRecord(a1, &v47, &v45, &v43);
  v47 = 3;
  Diagnostics::OTelLogRecord::AddAdditionalInfoFromDataToLogRecord((Diagnostics::OTelLogRecord *)a1, v14);
LABEL_29:
  std::wstring::~wstring((__int64)S1);
  std::wstring::~wstring((__int64)v55);
  std::wstring::~wstring((__int64)v58);
  return a1;
}

```

## disassembly

```asm
0x18002ad6c  mov     [rsp-8+arg_10], rbx
0x18002ad71  push    rbp
0x18002ad72  push    rsi
0x18002ad73  push    rdi
0x18002ad74  push    r12
0x18002ad76  push    r13
0x18002ad78  push    r14
0x18002ad7a  push    r15
0x18002ad7c  lea     rbp, [rsp-60h]
0x18002ad81  sub     rsp, 160h
0x18002ad88  mov     rax, cs:__security_cookie
0x18002ad8f  xor     rax, rsp
0x18002ad92  mov     [rbp+90h+var_40], rax
0x18002ad96  mov     rdi, rdx
0x18002ad99  mov     r14, rcx
0x18002ad9c  mov     [rbp+90h+var_F0], rcx
0x18002ada0  mov     [rsp+190h+var_120], 1
0x18002ada8  mov     rcx, [rdx]
0x18002adab  mov     rax, [rcx]
0x18002adae  mov     rax, [rax+58h]
0x18002adb2  call    _guard_dispatch_icall
0x18002adb7  mov     r13d, 3
0x18002adbd  cmp     eax, r13d
0x18002adc0  jnz     loc_18002B698
0x18002adc6  xorps   xmm0, xmm0
0x18002adc9  movups  [rsp+190h+var_160], xmm0
0x18002adce  xorps   xmm1, xmm1
0x18002add1  movdqu  [rsp+190h+var_150], xmm1
0x18002add7  lea     r15d, [r13+1]
0x18002addb  mov     r8d, r15d
0x18002adde  lea     rdx, aName_2; "name"
0x18002ade5  lea     rcx, [rsp+190h+var_160]
0x18002adea  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002adef  nop
0x18002adf0  mov     rcx, [rdi]
0x18002adf3  mov     rax, [rcx]
0x18002adf6  lea     rdx, [rsp+190h+var_160]
0x18002adfb  mov     rax, [rax+8]
0x18002adff  call    _guard_dispatch_icall
0x18002ae04  mov     bl, al
0x18002ae06  lea     rcx, [rsp+190h+var_160]
0x18002ae0b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ae10  test    bl, bl
0x18002ae12  jz      loc_18002B6C3
0x18002ae18  xorps   xmm0, xmm0
0x18002ae1b  movups  [rsp+190h+var_160], xmm0
0x18002ae20  xorps   xmm1, xmm1
0x18002ae23  movdqu  [rsp+190h+var_150], xmm1
0x18002ae29  mov     r8d, r15d
0x18002ae2c  lea     rdx, aName_2; "name"
0x18002ae33  lea     rcx, [rsp+190h+var_160]
0x18002ae38  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002ae3d  nop
0x18002ae3e  lea     rdx, [rsp+190h+var_160]
0x18002ae43  mov     rcx, rdi
0x18002ae46  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002ae4b  mov     rbx, rax
0x18002ae4e  lea     rcx, [rsp+190h+var_160]
0x18002ae53  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ae58  mov     rcx, [rbx]
0x18002ae5b  mov     rax, [rcx]
0x18002ae5e  mov     rax, [rax+58h]
0x18002ae62  call    _guard_dispatch_icall
0x18002ae67  lea     r12d, [r13-1]
0x18002ae6b  cmp     eax, r12d
0x18002ae6e  jnz     loc_18002B6EE
0x18002ae74  mov     rcx, [rbx]
0x18002ae77  mov     rax, [rcx]
0x18002ae7a  mov     rax, [rax+0B0h]
0x18002ae81  call    _guard_dispatch_icall
0x18002ae86  mov     rdx, rax
0x18002ae89  lea     rcx, [rbp+90h+var_80]
0x18002ae8d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002ae92  nop
0x18002ae93  xorps   xmm0, xmm0
0x18002ae96  movups  [rsp+190h+var_160], xmm0
0x18002ae9b  xorps   xmm1, xmm1
0x18002ae9e  movdqu  [rsp+190h+var_150], xmm1
0x18002aea4  mov     r8d, r15d
0x18002aea7  lea     rdx, aTime_2; "time"
0x18002aeae  lea     rcx, [rsp+190h+var_160]
0x18002aeb3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002aeb8  nop
0x18002aeb9  mov     rcx, [rdi]
0x18002aebc  mov     rax, [rcx]
0x18002aebf  lea     rdx, [rsp+190h+var_160]
0x18002aec4  mov     rax, [rax+8]
0x18002aec8  call    _guard_dispatch_icall
0x18002aecd  mov     bl, al
0x18002aecf  lea     rcx, [rsp+190h+var_160]
0x18002aed4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002aed9  test    bl, bl
0x18002aedb  jz      loc_18002B719
0x18002aee1  xorps   xmm0, xmm0
0x18002aee4  movups  [rsp+190h+var_160], xmm0
0x18002aee9  xorps   xmm1, xmm1
0x18002aeec  movdqu  [rsp+190h+var_150], xmm1
0x18002aef2  mov     r8d, r15d
0x18002aef5  lea     rdx, aTime_2; "time"
0x18002aefc  lea     rcx, [rsp+190h+var_160]
0x18002af01  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002af06  nop
0x18002af07  lea     rdx, [rsp+190h+var_160]
0x18002af0c  mov     rcx, rdi
0x18002af0f  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002af14  mov     rbx, rax
0x18002af17  lea     rcx, [rsp+190h+var_160]
0x18002af1c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002af21  mov     rcx, [rbx]
0x18002af24  mov     rax, [rcx]
0x18002af27  mov     rax, [rax+58h]
0x18002af2b  call    _guard_dispatch_icall
0x18002af30  cmp     eax, r12d
0x18002af33  jnz     loc_18002B744
0x18002af39  mov     rcx, [rbx]
0x18002af3c  mov     rax, [rcx]
0x18002af3f  mov     rax, [rax+0B0h]
0x18002af46  call    _guard_dispatch_icall
0x18002af4b  mov     rdx, rax
0x18002af4e  lea     rcx, [rsp+190h+var_120]
0x18002af53  call    ?ToTimePoint@Convert@System@@SA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; System::Convert::ToTimePoint(std::wstring const &)
0x18002af58  xorps   xmm0, xmm0
0x18002af5b  movups  [rsp+190h+var_160], xmm0
0x18002af60  xorps   xmm1, xmm1
0x18002af63  movdqu  [rsp+190h+var_150], xmm1
0x18002af69  mov     r8d, r13d
0x18002af6c  lea     rdx, aVer; "ver"
0x18002af73  lea     rcx, [rsp+190h+var_160]
0x18002af78  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002af7d  nop
0x18002af7e  mov     rcx, [rdi]
0x18002af81  mov     rax, [rcx]
0x18002af84  lea     rdx, [rsp+190h+var_160]
0x18002af89  mov     rax, [rax+8]
0x18002af8d  call    _guard_dispatch_icall
0x18002af92  mov     bl, al
0x18002af94  lea     rcx, [rsp+190h+var_160]
0x18002af99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002af9e  test    bl, bl
0x18002afa0  jz      loc_18002B76F
0x18002afa6  xorps   xmm0, xmm0
0x18002afa9  movups  [rsp+190h+var_160], xmm0
0x18002afae  xorps   xmm1, xmm1
0x18002afb1  movdqu  [rsp+190h+var_150], xmm1
0x18002afb7  mov     r8d, r13d
0x18002afba  lea     rdx, aVer; "ver"
0x18002afc1  lea     rcx, [rsp+190h+var_160]
0x18002afc6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002afcb  nop
0x18002afcc  lea     rdx, [rsp+190h+var_160]
0x18002afd1  mov     rcx, rdi
0x18002afd4  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002afd9  mov     rbx, rax
0x18002afdc  lea     rcx, [rsp+190h+var_160]
0x18002afe1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002afe6  mov     rcx, [rbx]
0x18002afe9  mov     rax, [rcx]
0x18002afec  mov     rax, [rax+58h]
0x18002aff0  call    _guard_dispatch_icall
0x18002aff5  cmp     eax, r12d
0x18002aff8  jnz     loc_18002B79A
0x18002affe  mov     rcx, [rbx]
0x18002b001  mov     rax, [rcx]
0x18002b004  mov     rax, [rax+0B0h]
0x18002b00b  call    _guard_dispatch_icall
0x18002b010  mov     rdx, rax
0x18002b013  lea     rcx, [rbp+90h+var_A0]
0x18002b017  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002b01c  nop
0x18002b01d  xorps   xmm0, xmm0
0x18002b020  movups  [rsp+190h+var_160], xmm0
0x18002b025  xorps   xmm1, xmm1
0x18002b028  movdqu  [rsp+190h+var_150], xmm1
0x18002b02e  mov     r8d, r15d
0x18002b031  lea     rdx, aData_0; "data"
0x18002b038  lea     rcx, [rsp+190h+var_160]
0x18002b03d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002b042  nop
0x18002b043  mov     rcx, [rdi]
0x18002b046  mov     rax, [rcx]
0x18002b049  lea     rdx, [rsp+190h+var_160]
0x18002b04e  mov     rax, [rax+8]
0x18002b052  call    _guard_dispatch_icall
0x18002b057  mov     bl, al
0x18002b059  lea     rcx, [rsp+190h+var_160]
0x18002b05e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b063  test    bl, bl
0x18002b065  jz      loc_18002B7C5
0x18002b06b  xorps   xmm0, xmm0
0x18002b06e  movups  [rbp+90h+var_110], xmm0
0x18002b072  xorps   xmm1, xmm1
0x18002b075  movdqu  [rbp+90h+var_100], xmm1
0x18002b07a  mov     r8d, r15d
0x18002b07d  lea     rdx, aData_0; "data"
0x18002b084  lea     rcx, [rbp+90h+var_110]
0x18002b088  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002b08d  nop
0x18002b08e  lea     rdx, [rbp+90h+var_110]
0x18002b092  mov     rcx, rdi
0x18002b095  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002b09a  mov     rsi, rax
0x18002b09d  lea     rcx, [rbp+90h+var_110]
0x18002b0a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b0a6  mov     rcx, [rsi]
0x18002b0a9  mov     rax, [rcx]
0x18002b0ac  mov     rax, [rax+58h]
0x18002b0b0  call    _guard_dispatch_icall
0x18002b0b5  cmp     eax, r13d
0x18002b0b8  jnz     loc_18002B7F0
0x18002b0be  xorps   xmm0, xmm0
0x18002b0c1  movups  [rsp+190h+var_160], xmm0
0x18002b0c6  xorps   xmm1, xmm1
0x18002b0c9  movdqu  [rsp+190h+var_150], xmm1
0x18002b0cf  lea     edi, [r13+5]
0x18002b0d3  mov     r8d, edi
0x18002b0d6  lea     rdx, aBasetype_0; "baseType"
0x18002b0dd  lea     rcx, [rsp+190h+var_160]
0x18002b0e2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002b0e7  nop
0x18002b0e8  mov     rcx, [rsi]
0x18002b0eb  mov     rax, [rcx]
0x18002b0ee  lea     rdx, [rsp+190h+var_160]
0x18002b0f3  mov     rax, [rax+8]
0x18002b0f7  call    _guard_dispatch_icall
0x18002b0fc  mov     bl, al
0x18002b0fe  lea     rcx, [rsp+190h+var_160]
0x18002b103  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b108  test    bl, bl
0x18002b10a  jz      loc_18002B81B
0x18002b110  xorps   xmm0, xmm0
0x18002b113  movups  [rsp+190h+var_160], xmm0
0x18002b118  xorps   xmm1, xmm1
0x18002b11b  movdqu  [rsp+190h+var_150], xmm1
0x18002b121  mov     r8d, edi
0x18002b124  lea     rdx, aBasetype_0; "baseType"
0x18002b12b  lea     rcx, [rsp+190h+var_160]
0x18002b130  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002b135  nop
0x18002b136  lea     rdx, [rsp+190h+var_160]
0x18002b13b  mov     rcx, rsi
0x18002b13e  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18002b143  mov     rbx, rax
0x18002b146  lea     rcx, [rsp+190h+var_160]
0x18002b14b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b150  mov     rcx, [rbx]
0x18002b153  mov     rax, [rcx]
0x18002b156  mov     rax, [rax+58h]
0x18002b15a  call    _guard_dispatch_icall
0x18002b15f  cmp     eax, r12d
0x18002b162  jnz     loc_18002B846
0x18002b168  mov     rcx, [rbx]
0x18002b16b  mov     rax, [rcx]
0x18002b16e  mov     rax, [rax+0B0h]
0x18002b175  call    _guard_dispatch_icall
0x18002b17a  mov     rdx, rax
0x18002b17d  lea     rcx, [rbp+90h+S1]
0x18002b181  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002b186  nop
0x18002b187  mov     r8, [rbp+90h+N]; N
0x18002b18b  lea     rcx, [rbp+90h+S1]
0x18002b18f  mov     rax, [rbp+90h+S1]
0x18002b193  mov     rdx, [rbp+90h+var_A8]
0x18002b197  cmp     rdx, 7
0x18002b19b  cmova   rcx, rax; S1
0x18002b19f  cmp     r8, r15
0x18002b1a2  jnz     loc_18002B58A
0x18002b1a8  lea     rdx, aSpan; "Span"
0x18002b1af  call    wmemcmp
0x18002b1b4  test    eax, eax
0x18002b1b6  jnz     loc_18002B57E
0x18002b1bc  xorps   xmm0, xmm0
0x18002b1bf  movups  [rsp+190h+var_160], xmm0
0x18002b1c4  xorps   xmm1, xmm1
0x18002b1c7  movdqu  [rsp+190h+var_150], xmm1
0x18002b1cd  mov     r8d, edi
0x18002b1d0  lea     rdx, aBasedata_0; "baseData"
0x18002b1d7  lea     rcx, [rsp+190h+var_160]
0x18002b1dc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002b1e1  nop
0x18002b1e2  mov     rcx, [rsi]
0x18002b1e5  mov     rax, [rcx]
0x18002b1e8  lea     rdx, [rsp+190h+var_160]
0x18002b1ed  mov     rax, [rax+8]
0x18002b1f1  call    _guard_dispatch_icall
0x18002b1f6  mov     bl, al
0x18002b1f8  lea     rcx, [rsp+190h+var_160]
0x18002b1fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b202  test    bl, bl
0x18002b204  jz      loc_18002B871
0x18002b20a  xorps   xmm0, xmm0
0x18002b20d  movups  [rsp+190h+var_160], xmm0
0x18002b212  xorps   xmm1, xmm1
0x18002b215  movdqu  [rsp+190h+var_150], xmm1
0x18002b21b  mov     r8d, edi
0x18002b21e  lea     rdx, aBasedata_0; "baseData"
0x18002b225  lea     rcx, [rsp+190h+var_160]
0x18002b22a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002b22f  nop
0x18002b230  lea     rdx, [rsp+190h+var_160]
0x18002b235  mov     rcx, rsi
  ... truncated ...
```
