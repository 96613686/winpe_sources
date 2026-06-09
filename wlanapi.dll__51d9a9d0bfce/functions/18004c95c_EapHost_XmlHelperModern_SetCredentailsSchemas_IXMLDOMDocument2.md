# EapHost::XmlHelperModern::SetCredentailsSchemas(IXMLDOMDocument2 *)

- ea: `0x18004c95c`
- end: `0x18004cb2c`
- name: `?SetCredentailsSchemas@XmlHelperModern@EapHost@@YAXPEAUIXMLDOMDocument2@@@Z`
- size: `464`
- prototype: `void __fastcall(EapHost::XmlHelperModern *__hidden this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bb34`

## callees

- `0x180019a20`
- `0x18001cdf8`
- `0x180039adc`
- `0x18003a098`
- `0x18003a10c`
- `0x18003a124`
- `0x18004c95c`
- `0x18004cb34`
- `0x18004d8cc`

## string_xrefs

- `0x18004c989`: `http://www.microsoft.com/provisioning/EapCommon`
- `0x18004ca0b`: `EapCommon.xsd`
- `0x18004c9b1`: `http://www.microsoft.com/provisioning/BaseEapMethodUserCredentials`
- `0x18004c9d9`: `http://www.microsoft.com/provisioning/EapHostUserCredentials`
- `0x18004ca83`: `xmlns:eapCommon='http://www.microsoft.com/provisioning/EapCommon' xmlns:baseEap='http://www.microsoft.com/provisioning/BaseEapMethodUserCredentials' xmlns:eapCredentials='http://www.microsoft.com/provisioning/EapHostUserCredentials' `

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall EapHost::XmlHelperModern::SetCredentailsSchemas(
        EapHost::XmlHelperModern *this,
        struct IXMLDOMDocument2 *a2)
{
  __int64 v3; // rdx
  __int64 v4; // [rsp+20h] [rbp-29h] BYREF
  __int128 v5; // [rsp+28h] [rbp-21h]
  _QWORD v6[3]; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v8[32]; // [rsp+70h] [rbp+27h] BYREF

  std::vector<std::wstring>::vector<std::wstring>(v6, a2);
  std::wstring::wstring(v7, L"http://www.microsoft.com/provisioning/EapCommon");
  std::vector<std::wstring>::push_back(v6, v7);
  std::wstring::~wstring(v7);
  std::wstring::wstring(v7, L"http://www.microsoft.com/provisioning/BaseEapMethodUserCredentials");
  std::vector<std::wstring>::push_back(v6, v7);
  std::wstring::~wstring(v7);
  std::wstring::wstring(v7, L"http://www.microsoft.com/provisioning/EapHostUserCredentials");
  std::vector<std::wstring>::push_back(v6, v7);
  std::wstring::~wstring(v7);
  std::vector<std::wstring>::vector<std::wstring>(&v4, v3);
  std::wstring::wstring(v7, L"EapCommon.xsd");
  std::vector<std::wstring>::push_back(&v4, v7);
  std::wstring::~wstring(v7);
  std::wstring::wstring(v7, L"BaseEapMethodUserCredentials.xsd");
  std::vector<std::wstring>::push_back(&v4, v7);
  std::wstring::~wstring(v7);
  std::wstring::wstring(v7, L"EapHostUserCredentials.xsd");
  std::vector<std::wstring>::push_back(&v4, v7);
  std::wstring::~wstring(v7);
  std::wstring::wstring(
    v8,
    L"xmlns:eapCommon='http://www.microsoft.com/provisioning/EapCommon' xmlns:baseEap='http://www.microsoft.com/provisioni"
     "ng/BaseEapMethodUserCredentials' xmlns:eapCredentials='http://www.microsoft.com/provisioning/EapHostUserCredentials' ");
  EapHost::XmlHelperModern::SetNsAndSchema(this, v8, v6, &v4);
  std::wstring::~wstring(v8);
  if ( v4 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v4, v5);
    std::_Deallocate<16>(v4, (*((_QWORD *)&v5 + 1) - v4) & 0xFFFFFFFFFFFFFFE0uLL);
    v4 = 0;
    v5 = 0;
  }
  if ( v6[0] )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v6[0], v6[1]);
    std::_Deallocate<16>(v6[0], (v6[2] - v6[0]) & 0xFFFFFFFFFFFFFFE0uLL);
  }
}

```

## disassembly

```asm
0x18004c95c  mov     [rsp-8+arg_8], rbx
0x18004c961  push    rbp
0x18004c962  lea     rbp, [rsp-57h]
0x18004c967  sub     rsp, 0A0h
0x18004c96e  mov     rax, cs:__security_cookie
0x18004c975  xor     rax, rsp
0x18004c978  mov     [rbp+57h+var_10], rax
0x18004c97c  mov     rbx, rcx
0x18004c97f  lea     rcx, [rbp+57h+var_68]
0x18004c983  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18004c988  nop
0x18004c989  lea     rdx, aHttpWwwMicroso_3; "http://www.microsoft.com/provisioning/E"...
0x18004c990  lea     rcx, [rbp+57h+var_50]
0x18004c994  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004c999  nop
0x18004c99a  lea     rdx, [rbp+57h+var_50]
0x18004c99e  lea     rcx, [rbp+57h+var_68]
0x18004c9a2  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004c9a7  nop
0x18004c9a8  lea     rcx, [rbp+57h+var_50]
0x18004c9ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c9b1  lea     rdx, aHttpWwwMicroso; "http://www.microsoft.com/provisioning/B"...
0x18004c9b8  lea     rcx, [rbp+57h+var_50]
0x18004c9bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004c9c1  nop
0x18004c9c2  lea     rdx, [rbp+57h+var_50]
0x18004c9c6  lea     rcx, [rbp+57h+var_68]
0x18004c9ca  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004c9cf  nop
0x18004c9d0  lea     rcx, [rbp+57h+var_50]
0x18004c9d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c9d9  lea     rdx, aHttpWwwMicroso_2; "http://www.microsoft.com/provisioning/E"...
0x18004c9e0  lea     rcx, [rbp+57h+var_50]
0x18004c9e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004c9e9  nop
0x18004c9ea  lea     rdx, [rbp+57h+var_50]
0x18004c9ee  lea     rcx, [rbp+57h+var_68]
0x18004c9f2  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004c9f7  nop
0x18004c9f8  lea     rcx, [rbp+57h+var_50]
0x18004c9fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ca01  lea     rcx, [rbp+57h+var_80]
0x18004ca05  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x18004ca0a  nop
0x18004ca0b  lea     rdx, aEapcommonXsd; "EapCommon.xsd"
0x18004ca12  lea     rcx, [rbp+57h+var_50]
0x18004ca16  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ca1b  nop
0x18004ca1c  lea     rdx, [rbp+57h+var_50]
0x18004ca20  lea     rcx, [rbp+57h+var_80]
0x18004ca24  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004ca29  nop
0x18004ca2a  lea     rcx, [rbp+57h+var_50]
0x18004ca2e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ca33  lea     rdx, aBaseeapmethodu; "BaseEapMethodUserCredentials.xsd"
0x18004ca3a  lea     rcx, [rbp+57h+var_50]
0x18004ca3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ca43  nop
0x18004ca44  lea     rdx, [rbp+57h+var_50]
0x18004ca48  lea     rcx, [rbp+57h+var_80]
0x18004ca4c  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004ca51  nop
0x18004ca52  lea     rcx, [rbp+57h+var_50]
0x18004ca56  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ca5b  lea     rdx, aEaphostusercre; "EapHostUserCredentials.xsd"
0x18004ca62  lea     rcx, [rbp+57h+var_50]
0x18004ca66  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ca6b  nop
0x18004ca6c  lea     rdx, [rbp+57h+var_50]
0x18004ca70  lea     rcx, [rbp+57h+var_80]
0x18004ca74  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18004ca79  nop
0x18004ca7a  lea     rcx, [rbp+57h+var_50]
0x18004ca7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ca83  lea     rdx, aXmlnsEapcommon; "xmlns:eapCommon='http://www.microsoft.c"...
0x18004ca8a  lea     rcx, [rbp+57h+var_30]
0x18004ca8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ca93  nop
0x18004ca94  lea     r9, [rbp+57h+var_80]
0x18004ca98  lea     r8, [rbp+57h+var_68]
0x18004ca9c  lea     rdx, [rbp+57h+var_30]
0x18004caa0  mov     rcx, rbx
0x18004caa3  call    ?SetNsAndSchema@XmlHelperModern@EapHost@@YAXPEAUIXMLDOMDocument2@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@5@2@Z; EapHost::XmlHelperModern::SetNsAndSchema(IXMLDOMDocument2 *,std::wstring const &,std::vector<std::wstring> const &,std::vector<std::wstring> const &)
0x18004caa8  nop
0x18004caa9  lea     rcx, [rbp+57h+var_30]
0x18004caad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cab2  nop
0x18004cab3  mov     rcx, [rbp+57h+var_80]
0x18004cab7  test    rcx, rcx
0x18004caba  jz      short loc_18004CAE9
0x18004cabc  mov     rdx, qword ptr [rbp+57h+var_78]
0x18004cac0  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18004cac5  mov     rcx, [rbp+57h+var_80]
0x18004cac9  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x18004cacd  sub     rdx, rcx
0x18004cad0  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18004cad4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004cad9  mov     [rbp+57h+var_80], 0
0x18004cae1  xorps   xmm0, xmm0
0x18004cae4  movdqu  [rbp+57h+var_78], xmm0
0x18004cae9  mov     rcx, [rbp+57h+var_68]
0x18004caed  test    rcx, rcx
0x18004caf0  jz      short loc_18004CB0F
0x18004caf2  mov     rdx, [rbp+57h+var_60]
0x18004caf6  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18004cafb  mov     rcx, [rbp+57h+var_68]
0x18004caff  mov     rdx, [rbp+57h+var_58]
0x18004cb03  sub     rdx, rcx
0x18004cb06  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18004cb0a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004cb0f  mov     rcx, [rbp+57h+var_10]
0x18004cb13  xor     rcx, rsp; StackCookie
0x18004cb16  call    __security_check_cookie
0x18004cb1b  mov     rbx, [rsp+0A0h+arg_8]
0x18004cb23  add     rsp, 0A0h
0x18004cb2a  pop     rbp
0x18004cb2b  retn
```
