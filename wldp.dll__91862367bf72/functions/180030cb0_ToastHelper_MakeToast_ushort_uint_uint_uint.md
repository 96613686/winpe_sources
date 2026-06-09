# ToastHelper::MakeToast(ushort *,uint,uint,uint)

- ea: `0x180030cb0`
- end: `0x180030e1e`
- name: `?MakeToast@ToastHelper@@SAJPEAGIII@Z`
- size: `366`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800310b0`

## callees

- `0x18001f038`
- `0x180021ec0`
- `0x18002f9d4`
- `0x18002fb1c`
- `0x18002fb7c`
- `0x1800300d0`
- `0x180030224`
- `0x180030260`
- `0x180030cb0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030d87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030d87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030dc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030dc3`

## string_xrefs

- `0x180030d59`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x180030d0f`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
__int64 __fastcall ToastHelper::MakeToast(unsigned __int16 *a1)
{
  int v1; // eax
  unsigned __int16 *v2; // rdx
  unsigned int v3; // r8d
  unsigned int v4; // r9d
  int v5; // ebx
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v12; // rcx
  unsigned int v14; // [rsp+20h] [rbp-50h]
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  struct Windows::Data::Xml::Dom::IXmlDocument *v16; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v17[8]; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  string = 0;
  v16 = 0;
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Xml.Dom.XmlDocument",
    0x21u,
    0x20u);
  v1 = Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(v19, &v16);
  v5 = v1;
  v19 = 0;
  if ( v1 >= 0 )
  {
    v1 = ToastHelper::BuildXml(v16, v2, v3, v4, v14);
    v5 = v1;
    if ( v1 >= 0 )
    {
      v8 = wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocument,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNodeSerializer>(
             &v16,
             v17);
      v9 = *(_QWORD *)v8;
      v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v8 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v5 = v10(v9, &string);
      wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v17);
      if ( v5 < 0 )
      {
        v7 = (unsigned int)v5;
        v6 = 320;
        goto LABEL_6;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v1 = ToastHelper::LaunchToast(v12, StringRawBuffer);
      v5 = v1;
      if ( v1 >= 0 )
      {
        v5 = 0;
        goto LABEL_12;
      }
      v6 = 322;
    }
    else
    {
      v6 = 318;
    }
  }
  else
  {
    v6 = 316;
  }
  v7 = (unsigned int)v1;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
    (const char *)v7,
    v14);
LABEL_12:
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180030cb0  mov     [rsp-8+arg_0], rbx
0x180030cb5  mov     [rsp-8+arg_8], rdi
0x180030cba  push    rbp
0x180030cbb  mov     rbp, rsp
0x180030cbe  sub     rsp, 70h
0x180030cc2  mov     rax, cs:__security_cookie
0x180030cc9  xor     rax, rsp
0x180030ccc  mov     [rbp+var_8], rax
0x180030cd0  mov     [rbp+var_38], 0
0x180030cd8  mov     [rbp+string], 0
0x180030ce0  mov     rcx, [rbp+var_38]
0x180030ce4  mov     [rbp+var_38], 0
0x180030cec  test    rcx, rcx
0x180030cef  jz      short loc_180030CFD
0x180030cf1  mov     rax, [rcx]
0x180030cf4  mov     rax, [rax+10h]
0x180030cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cfd  mov     [rbp+var_10], 0
0x180030d05  mov     r9d, 20h ; ' '; unsigned int
0x180030d0b  lea     r8d, [r9+1]; unsigned int
0x180030d0f  lea     rdx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180030d16  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180030d1a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030d1f  nop
0x180030d20  lea     rdx, [rbp+var_38]
0x180030d24  mov     rcx, [rbp+var_10]
0x180030d28  call    ??$ActivateInstance@UIXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIXmlDocument@Dom@Xml@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(HSTRING__ *,Windows::Data::Xml::Dom::IXmlDocument * *)
0x180030d2d  mov     ebx, eax
0x180030d2f  mov     [rbp+var_10], 0
0x180030d37  test    eax, eax
0x180030d39  jns     short loc_180030D42
0x180030d3b  mov     edx, 13Ch
0x180030d40  jmp     short loc_180030D56
0x180030d42  mov     rcx, [rbp+var_38]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180030d46  call    ?BuildXml@ToastHelper@@SAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAGIII@Z; ToastHelper::BuildXml(Windows::Data::Xml::Dom::IXmlDocument *,ushort *,uint,uint,uint)
0x180030d4b  mov     ebx, eax
0x180030d4d  test    eax, eax
0x180030d4f  jns     short loc_180030D6B
0x180030d51  mov     edx, 13Eh; void *
0x180030d56  mov     r9d, eax; char *
0x180030d59  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x180030d60  mov     rcx, [rbp+8]; this
0x180030d64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030d69  jmp     short loc_180030DE3
0x180030d6b  lea     rdx, [rbp+var_30]
0x180030d6f  lea     rcx, [rbp+var_38]
0x180030d73  call    ??$query@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@@?$com_ptr_t@UIXmlDocument@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocument,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNodeSerializer>(void)
0x180030d78  nop
0x180030d79  mov     rdi, [rax]
0x180030d7c  mov     rax, [rdi]
0x180030d7f  mov     rbx, [rax+30h]
0x180030d83  mov     rcx, [rbp+string]; string
0x180030d87  call    cs:__imp_WindowsDeleteString
0x180030d8d  mov     [rbp+string], 0
0x180030d95  lea     rdx, [rbp+string]
0x180030d99  mov     rcx, rdi
0x180030d9c  mov     rax, rbx
0x180030d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030da4  mov     ebx, eax
0x180030da6  lea     rcx, [rbp+var_30]
0x180030daa  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x180030daf  test    ebx, ebx
0x180030db1  jns     short loc_180030DBD
0x180030db3  mov     r9d, ebx
0x180030db6  mov     edx, 140h
0x180030dbb  jmp     short loc_180030D59
0x180030dbd  xor     edx, edx; length
0x180030dbf  mov     rcx, [rbp+string]; string
0x180030dc3  call    cs:__imp_WindowsGetStringRawBuffer
0x180030dc9  mov     rdx, rax; unsigned __int16 *
0x180030dcc  call    ?LaunchToast@ToastHelper@@SAJPEBG0@Z; ToastHelper::LaunchToast(ushort const *,ushort const *)
0x180030dd1  mov     ebx, eax
0x180030dd3  test    eax, eax
0x180030dd5  jns     short loc_180030DE1
0x180030dd7  mov     edx, 142h
0x180030ddc  jmp     loc_180030D56
0x180030de1  xor     ebx, ebx
0x180030de3  mov     rcx, [rbp+string]; string
0x180030de7  call    cs:__imp_WindowsDeleteString
0x180030ded  mov     [rbp+string], 0
0x180030df5  lea     rcx, [rbp+var_38]
0x180030df9  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x180030dfe  mov     eax, ebx
0x180030e00  mov     rcx, [rbp+var_8]
0x180030e04  xor     rcx, rsp; StackCookie
0x180030e07  call    __security_check_cookie
0x180030e0c  lea     r11, [rsp+70h+var_s0]
0x180030e11  mov     rbx, [r11+10h]
0x180030e15  mov     rdi, [r11+18h]
0x180030e19  mov     rsp, r11
0x180030e1c  pop     rbp
0x180030e1d  retn
```
