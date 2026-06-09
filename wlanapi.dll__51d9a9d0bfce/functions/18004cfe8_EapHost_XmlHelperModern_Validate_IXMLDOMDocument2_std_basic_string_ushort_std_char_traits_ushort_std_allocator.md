# EapHost::XmlHelperModern::Validate(IXMLDOMDocument2 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004cfe8`
- end: `0x18004d33c`
- name: `?Validate@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMDocument2@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `852`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bb34`

## callees

- `0x180017434`
- `0x1800174b8`
- `0x180019a20`
- `0x18001a5bc`
- `0x18001a68c`
- `0x18003a638`
- `0x18004af20`
- `0x18004b89c`
- `0x18004c7ac`
- `0x18004cfe8`
- `0x18004dc1c`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004d0c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d106`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d188`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d1d3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d0c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d106`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d188`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d1d3`

## string_xrefs

- `0x18004d2ac`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004d256`: `XML blob parsing error at line %d: %s. Reason: %s, element %s, xpath %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall EapHost::XmlHelperModern::Validate(__int64 a1, const char *a2)
{
  unsigned int v4; // r14d
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, BSTR *); // r12
  OLECHAR *v7; // rbx
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, BSTR *); // r12
  OLECHAR *v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rdi
  void (__fastcall *v13)(__int64, BSTR *); // r13
  OLECHAR *v14; // r12
  void (__fastcall *v15)(__int64, BSTR *); // r12
  OLECHAR *v16; // rdi
  BSTR v17; // r10
  BSTR v18; // r9
  BSTR v19; // rdx
  BSTR v20; // rcx
  __int64 v21; // rax
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  BSTR v26; // [rsp+68h] [rbp-98h] BYREF
  BSTR v27; // [rsp+70h] [rbp-90h] BYREF
  BSTR v28; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[8]; // [rsp+88h] [rbp-78h] BYREF
  void **v31; // [rsp+90h] [rbp-70h]
  char v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+9Ch] [rbp-64h]
  int v34; // [rsp+A8h] [rbp-58h]
  wchar_t Buffer[1024]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8F8h] [rbp+7F8h]

  v24 = 0;
  v32 = 0;
  v33 = 0;
  v31 = &EapHost::EapMethodType::`vftable';
  v34 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 632LL))(a1, &v24);
  if ( v4 )
  {
    v25 = -1;
    bstrString = 0;
    v28 = 0;
    v27 = 0;
    v26 = 0;
    memset_0(Buffer, 0, sizeof(Buffer));
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 88LL))(v24, &v25);
    v5 = v24;
    v6 = *(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v24 + 72LL);
    v7 = bstrString;
    if ( bstrString )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v23);
      SysFreeString(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v23);
    }
    bstrString = 0;
    v6(v5, &bstrString);
    v8 = v24;
    v9 = *(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v24 + 80LL);
    v10 = v28;
    if ( v28 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v23);
      SysFreeString(v10);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v23);
    }
    v28 = 0;
    v9(v8, &v28);
    if ( v24 )
    {
      v23 = 0;
      (**(void (__fastcall ***)(__int64, __int64 *, __int64 *))v24)(v24, winrt::impl::guid_v<IXMLDOMParseError2>, &v23);
      v11 = v23;
      v12 = v23;
    }
    else
    {
      v11 = 0;
      v12 = 0;
    }
    v23 = v11;
    if ( v12 )
    {
      v13 = *(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 112LL);
      v14 = v26;
      if ( v26 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v30);
        SysFreeString(v14);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v30);
      }
      v26 = 0;
      v13(v12, &v26);
    }
    v15 = *(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a1 + 272LL);
    v16 = v27;
    if ( v27 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v30);
      SysFreeString(v16);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v30);
    }
    v27 = 0;
    v15(a1, &v27);
    v17 = L"Unknown";
    v18 = L"Unknown";
    if ( v26 )
      v18 = v26;
    v19 = L"Unknown";
    if ( v27 )
      v19 = v27;
    if ( bstrString )
      v17 = bstrString;
    v20 = L"unable to get the content of the line";
    if ( v28 )
      v20 = v28;
    snwprintf_s(
      Buffer,
      0x400u,
      0xFFFFFFFFFFFFFFFFuLL,
      L"XML blob parsing error at line %d: %s. Reason: %s, element %s, xpath %s",
      v25,
      v20,
      v17,
      v19,
      v18);
    v21 = std::_WChar_traits<unsigned short>::length(Buffer);
    std::wstring::_Assign<unsigned short>(a2, Buffer, v21);
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const char **)a2;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)v4,
      (int)"%ls",
      a2);
    if ( v11 )
      winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v23);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
  }
  if ( v24 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v24);
  return v4 == 0;
}

```

## disassembly

```asm
0x18004cfe8  mov     [rsp-8+arg_10], rbx
0x18004cfed  push    rbp
0x18004cfee  push    rsi
0x18004cfef  push    rdi
0x18004cff0  push    r12
0x18004cff2  push    r13
0x18004cff4  push    r14
0x18004cff6  push    r15
0x18004cff8  lea     rbp, [rsp-7C0h]
0x18004d000  sub     rsp, 8C0h
0x18004d007  mov     rax, cs:__security_cookie
0x18004d00e  xor     rax, rsp
0x18004d011  mov     [rbp+7F0h+var_40], rax
0x18004d018  mov     rsi, rdx
0x18004d01b  mov     r15, rcx
0x18004d01e  xor     r13d, r13d
0x18004d021  mov     [rsp+8F0h+var_898], r13
0x18004d026  mov     [rbp+7F0h+var_858], r13b
0x18004d02a  mov     [rbp+7F0h+var_854], r13
0x18004d02e  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18004d035  mov     [rbp+7F0h+var_860], rax
0x18004d039  mov     [rbp+7F0h+var_848], r13d
0x18004d03d  mov     rax, [rcx]
0x18004d040  lea     rdx, [rsp+8F0h+var_898]
0x18004d045  mov     rax, [rax+278h]
0x18004d04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d051  mov     r14d, eax
0x18004d054  test    eax, eax
0x18004d056  jz      loc_18004D2F9
0x18004d05c  mov     [rsp+8F0h+var_890], 0FFFFFFFFh
0x18004d064  mov     [rbp+7F0h+bstrString], r13
0x18004d068  mov     [rsp+8F0h+var_878], r13
0x18004d06d  mov     [rsp+8F0h+var_880], r13
0x18004d072  mov     [rsp+8F0h+var_888], r13
0x18004d077  xor     edx, edx; Val
0x18004d079  mov     r8d, 800h; Size
0x18004d07f  lea     rcx, [rbp+7F0h+Buffer]; void *
0x18004d083  call    memset_0
0x18004d088  mov     rcx, [rsp+8F0h+var_898]
0x18004d08d  mov     rax, [rcx]
0x18004d090  lea     rdx, [rsp+8F0h+var_890]
0x18004d095  mov     rax, [rax+58h]
0x18004d099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d09e  mov     rdi, [rsp+8F0h+var_898]
0x18004d0a3  mov     rax, [rdi]
0x18004d0a6  mov     r12, [rax+48h]
0x18004d0aa  mov     rbx, [rbp+7F0h+bstrString]
0x18004d0ae  test    rbx, rbx
0x18004d0b1  jz      short loc_18004D0D0
0x18004d0b3  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18004d0b8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004d0bd  mov     rcx, rbx; bstrString
0x18004d0c0  call    cs:__imp_SysFreeString
0x18004d0c6  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18004d0cb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004d0d0  mov     [rbp+7F0h+bstrString], r13
0x18004d0d4  lea     rdx, [rbp+7F0h+bstrString]
0x18004d0d8  mov     rcx, rdi
0x18004d0db  mov     rax, r12
0x18004d0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0e3  mov     rdi, [rsp+8F0h+var_898]
0x18004d0e8  mov     rax, [rdi]
0x18004d0eb  mov     r12, [rax+50h]
0x18004d0ef  mov     rbx, [rsp+8F0h+var_878]
0x18004d0f4  test    rbx, rbx
0x18004d0f7  jz      short loc_18004D116
0x18004d0f9  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18004d0fe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004d103  mov     rcx, rbx; bstrString
0x18004d106  call    cs:__imp_SysFreeString
0x18004d10c  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18004d111  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004d116  mov     [rsp+8F0h+var_878], r13
0x18004d11b  lea     rdx, [rsp+8F0h+var_878]
0x18004d120  mov     rcx, rdi
0x18004d123  mov     rax, r12
0x18004d126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d12b  mov     rcx, [rsp+8F0h+var_898]
0x18004d130  test    rcx, rcx
0x18004d133  jnz     short loc_18004D13D
0x18004d135  mov     rbx, r13
0x18004d138  mov     rdi, r13
0x18004d13b  jmp     short loc_18004D161
0x18004d13d  mov     [rsp+8F0h+var_8A0], r13
0x18004d142  mov     rax, [rcx]
0x18004d145  lea     r8, [rsp+8F0h+var_8A0]
0x18004d14a  lea     rdx, ??$guid_v@UIXMLDOMParseError2@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IXMLDOMParseError2>
0x18004d151  mov     rax, [rax]
0x18004d154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d159  mov     rbx, [rsp+8F0h+var_8A0]
0x18004d15e  mov     rdi, rbx
0x18004d161  mov     [rsp+8F0h+var_8A0], rbx
0x18004d166  test    rdi, rdi
0x18004d169  jz      short loc_18004D1B3
0x18004d16b  mov     rax, [rdi]
0x18004d16e  mov     r13, [rax+70h]
0x18004d172  mov     r12, [rsp+8F0h+var_888]
0x18004d177  test    r12, r12
0x18004d17a  jz      short loc_18004D197
0x18004d17c  lea     rcx, [rbp+7F0h+var_868]; this
0x18004d180  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004d185  mov     rcx, r12; bstrString
0x18004d188  call    cs:__imp_SysFreeString
0x18004d18e  lea     rcx, [rbp+7F0h+var_868]; this
0x18004d192  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004d197  mov     [rsp+8F0h+var_888], 0
0x18004d1a0  lea     rdx, [rsp+8F0h+var_888]
0x18004d1a5  mov     rcx, rdi
0x18004d1a8  mov     rax, r13
0x18004d1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1b0  xor     r13d, r13d
0x18004d1b3  mov     rax, [r15]
0x18004d1b6  mov     r12, [rax+110h]
0x18004d1bd  mov     rdi, [rsp+8F0h+var_880]
0x18004d1c2  test    rdi, rdi
0x18004d1c5  jz      short loc_18004D1E2
0x18004d1c7  lea     rcx, [rbp+7F0h+var_868]; this
0x18004d1cb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004d1d0  mov     rcx, rdi; bstrString
0x18004d1d3  call    cs:__imp_SysFreeString
0x18004d1d9  lea     rcx, [rbp+7F0h+var_868]; this
0x18004d1dd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004d1e2  mov     [rsp+8F0h+var_880], r13
0x18004d1e7  lea     rdx, [rsp+8F0h+var_880]
0x18004d1ec  mov     rcx, r15
0x18004d1ef  mov     rax, r12
0x18004d1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1f7  lea     r10, aUnknown; "Unknown"
0x18004d1fe  mov     r9, r10
0x18004d201  mov     rax, [rsp+8F0h+var_888]
0x18004d206  test    rax, rax
0x18004d209  cmovnz  r9, rax
0x18004d20d  mov     rdx, r10
0x18004d210  mov     rax, [rsp+8F0h+var_880]
0x18004d215  test    rax, rax
0x18004d218  cmovnz  rdx, rax
0x18004d21c  mov     rax, [rbp+7F0h+bstrString]
0x18004d220  test    rax, rax
0x18004d223  cmovnz  r10, rax
0x18004d227  lea     rcx, aUnableToGetThe; "unable to get the content of the line"
0x18004d22e  mov     rax, [rsp+8F0h+var_878]
0x18004d233  test    rax, rax
0x18004d236  cmovnz  rcx, rax
0x18004d23a  mov     [rsp+8F0h+var_8B0], r9
0x18004d23f  mov     [rsp+8F0h+var_8B8], rdx
0x18004d244  mov     [rsp+8F0h+var_8C0], r10
0x18004d249  mov     [rsp+8F0h+var_8C8], rcx
0x18004d24e  mov     eax, [rsp+8F0h+var_890]
0x18004d252  mov     [rsp+8F0h+var_8D0], eax
0x18004d256  lea     r9, aXmlBlobParsing; "XML blob parsing error at line %d: %s. "...
0x18004d25d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18004d261  mov     edx, 400h; BufferCount
0x18004d266  lea     rcx, [rbp+7F0h+Buffer]; Buffer
0x18004d26a  call    _snwprintf_s
0x18004d26f  lea     rcx, [rbp+7F0h+Buffer]
0x18004d273  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004d278  mov     r8, rax
0x18004d27b  lea     rdx, [rbp+7F0h+Buffer]
0x18004d27f  mov     rcx, rsi
0x18004d282  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d287  cmp     qword ptr [rsi+18h], 7
0x18004d28c  jbe     short loc_18004D291
0x18004d28e  mov     rsi, [rsi]
0x18004d291  mov     rcx, [rbp+7F8h]; this
0x18004d298  mov     [rsp+8F0h+var_8C8], rsi; char *
0x18004d29d  lea     rax, aLs; "%ls"
0x18004d2a4  mov     qword ptr [rsp+8F0h+var_8D0], rax; int
0x18004d2a9  mov     r9d, r14d; char *
0x18004d2ac  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004d2b3  mov     edx, 189h; void *
0x18004d2b8  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d2bd  nop
0x18004d2be  test    rbx, rbx
0x18004d2c1  jz      short loc_18004D2CE
0x18004d2c3  lea     rcx, [rsp+8F0h+var_8A0]
0x18004d2c8  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x18004d2cd  nop
0x18004d2ce  lea     rcx, [rsp+8F0h+var_888]
0x18004d2d3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d2d8  nop
0x18004d2d9  lea     rcx, [rsp+8F0h+var_880]
0x18004d2de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d2e3  nop
0x18004d2e4  lea     rcx, [rsp+8F0h+var_878]
0x18004d2e9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d2ee  nop
0x18004d2ef  lea     rcx, [rbp+7F0h+bstrString]
0x18004d2f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004d2f8  nop
0x18004d2f9  test    r14d, r14d
0x18004d2fc  setz    bl
0x18004d2ff  cmp     [rsp+8F0h+var_898], r13
0x18004d304  jz      short loc_18004D310
0x18004d306  lea     rcx, [rsp+8F0h+var_898]
0x18004d30b  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x18004d310  mov     al, bl
0x18004d312  mov     rcx, [rbp+7F0h+var_40]
0x18004d319  xor     rcx, rsp; StackCookie
0x18004d31c  call    __security_check_cookie
0x18004d321  mov     rbx, [rsp+8F0h+arg_10]
0x18004d329  add     rsp, 8C0h
0x18004d330  pop     r15
0x18004d332  pop     r14
0x18004d334  pop     r13
0x18004d336  pop     r12
0x18004d338  pop     rdi
0x18004d339  pop     rsi
0x18004d33a  pop     rbp
0x18004d33b  retn
```
