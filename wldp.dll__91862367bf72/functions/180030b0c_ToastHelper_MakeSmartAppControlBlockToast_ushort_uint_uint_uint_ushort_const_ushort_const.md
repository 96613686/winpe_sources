# ToastHelper::MakeSmartAppControlBlockToast(ushort *,uint,uint,uint,ushort const *,ushort const *)

- ea: `0x180030b0c`
- end: `0x180030ca8`
- name: `?MakeSmartAppControlBlockToast@ToastHelper@@SAJPEAGIIIPEBG1@Z`
- size: `412`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030ff0`
- `0x18003104c`

## callees

- `0x18001f038`
- `0x180021ec0`
- `0x18002f9d4`
- `0x18002fb1c`
- `0x18002fb7c`
- `0x18002ff7c`
- `0x180030224`
- `0x180030260`
- `0x180030b0c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030c68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030c68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030c44`

## string_xrefs

- `0x180030bda`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x180030b79`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
__int64 __fastcall ToastHelper::MakeSmartAppControlBlockToast(
        unsigned __int16 *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rdx
  unsigned __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v18; // rcx
  unsigned int v20; // [rsp+20h] [rbp-60h]
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  struct Windows::Data::Xml::Dom::IXmlDocument *v22; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v23[8]; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v25; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v22 = 0;
  string = 0;
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Xml.Dom.XmlDocument",
    0x21u,
    0x20u);
  v10 = Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(v25, &v22);
  v11 = v10;
  v25 = 0;
  if ( v10 >= 0 )
  {
    v10 = ToastHelper::BuildBlockToastXml(v22, a1, a2, a3, a4, a5, a6);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v14 = wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocument,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNodeSerializer>(
              &v22,
              v23);
      v15 = *(_QWORD *)v14;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v14 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v11 = v16(v15, &string);
      wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v23);
      if ( v11 < 0 )
      {
        v13 = (unsigned int)v11;
        v12 = 344;
        goto LABEL_6;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v10 = ToastHelper::LaunchToast(v18, StringRawBuffer);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v11 = 0;
        goto LABEL_12;
      }
      v12 = 346;
    }
    else
    {
      v12 = 342;
    }
  }
  else
  {
    v12 = 340;
  }
  v13 = (unsigned int)v10;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
    (const char *)v13,
    v20);
LABEL_12:
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v22);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180030b0c  mov     [rsp-38h+arg_18], rbx
0x180030b11  push    rbp
0x180030b12  push    rsi
0x180030b13  push    rdi
0x180030b14  push    r12
0x180030b16  push    r13
0x180030b18  push    r14
0x180030b1a  push    r15
0x180030b1c  mov     rbp, rsp
0x180030b1f  sub     rsp, 80h
0x180030b26  mov     rax, cs:__security_cookie
0x180030b2d  xor     rax, rsp
0x180030b30  mov     [rbp+var_8], rax
0x180030b34  mov     edi, r9d
0x180030b37  mov     r15d, r8d
0x180030b3a  mov     r14d, edx
0x180030b3d  mov     rsi, rcx
0x180030b40  mov     r12, [rbp+arg_20]
0x180030b44  mov     r13, [rbp+arg_28]
0x180030b48  xor     ebx, ebx
0x180030b4a  mov     [rbp+var_38], rbx
0x180030b4e  mov     [rbp+string], rbx
0x180030b52  mov     rcx, [rbp+var_38]
0x180030b56  mov     [rbp+var_38], rbx
0x180030b5a  test    rcx, rcx
0x180030b5d  jz      short loc_180030B6B
0x180030b5f  mov     rax, [rcx]
0x180030b62  mov     rax, [rax+10h]
0x180030b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b6b  mov     [rbp+var_10], rbx
0x180030b6f  mov     r9d, 20h ; ' '; unsigned int
0x180030b75  lea     r8d, [r9+1]; unsigned int
0x180030b79  lea     rdx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180030b80  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180030b84  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030b89  nop
0x180030b8a  lea     rdx, [rbp+var_38]
0x180030b8e  mov     rcx, [rbp+var_10]
0x180030b92  call    ??$ActivateInstance@UIXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIXmlDocument@Dom@Xml@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(HSTRING__ *,Windows::Data::Xml::Dom::IXmlDocument * *)
0x180030b97  mov     ebx, eax
0x180030b99  mov     [rbp+var_10], 0
0x180030ba1  test    eax, eax
0x180030ba3  jns     short loc_180030BAC
0x180030ba5  mov     edx, 154h
0x180030baa  jmp     short loc_180030BD7
0x180030bac  mov     [rsp+80h+var_50], r13; unsigned __int16 *
0x180030bb1  mov     [rsp+80h+var_58], r12; unsigned __int16 *
0x180030bb6  mov     [rsp+80h+var_60], edi; int
0x180030bba  mov     r9d, r15d; unsigned int
0x180030bbd  mov     r8d, r14d; unsigned int
0x180030bc0  mov     rdx, rsi; unsigned __int16 *
0x180030bc3  mov     rcx, [rbp+var_38]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180030bc7  call    ?BuildBlockToastXml@ToastHelper@@SAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAGIIIPEBG2@Z; ToastHelper::BuildBlockToastXml(Windows::Data::Xml::Dom::IXmlDocument *,ushort *,uint,uint,uint,ushort const *,ushort const *)
0x180030bcc  mov     ebx, eax
0x180030bce  test    eax, eax
0x180030bd0  jns     short loc_180030BEC
0x180030bd2  mov     edx, 156h; void *
0x180030bd7  mov     r9d, eax; char *
0x180030bda  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x180030be1  mov     rcx, [rbp+38h]; this
0x180030be5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030bea  jmp     short loc_180030C64
0x180030bec  lea     rdx, [rbp+var_30]
0x180030bf0  lea     rcx, [rbp+var_38]
0x180030bf4  call    ??$query@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@@?$com_ptr_t@UIXmlDocument@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocument,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNodeSerializer>(void)
0x180030bf9  nop
0x180030bfa  mov     rdi, [rax]
0x180030bfd  mov     rax, [rdi]
0x180030c00  mov     rbx, [rax+30h]
0x180030c04  mov     rcx, [rbp+string]; string
0x180030c08  call    cs:__imp_WindowsDeleteString
0x180030c0e  mov     [rbp+string], 0
0x180030c16  lea     rdx, [rbp+string]
0x180030c1a  mov     rcx, rdi
0x180030c1d  mov     rax, rbx
0x180030c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c25  mov     ebx, eax
0x180030c27  lea     rcx, [rbp+var_30]
0x180030c2b  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x180030c30  test    ebx, ebx
0x180030c32  jns     short loc_180030C3E
0x180030c34  mov     r9d, ebx
0x180030c37  mov     edx, 158h
0x180030c3c  jmp     short loc_180030BDA
0x180030c3e  xor     edx, edx; length
0x180030c40  mov     rcx, [rbp+string]; string
0x180030c44  call    cs:__imp_WindowsGetStringRawBuffer
0x180030c4a  mov     rdx, rax; unsigned __int16 *
0x180030c4d  call    ?LaunchToast@ToastHelper@@SAJPEBG0@Z; ToastHelper::LaunchToast(ushort const *,ushort const *)
0x180030c52  mov     ebx, eax
0x180030c54  test    eax, eax
0x180030c56  jns     short loc_180030C62
0x180030c58  mov     edx, 15Ah
0x180030c5d  jmp     loc_180030BD7
0x180030c62  xor     ebx, ebx
0x180030c64  mov     rcx, [rbp+string]; string
0x180030c68  call    cs:__imp_WindowsDeleteString
0x180030c6e  mov     [rbp+string], 0
0x180030c76  lea     rcx, [rbp+var_38]
0x180030c7a  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x180030c7f  mov     eax, ebx
0x180030c81  mov     rcx, [rbp+var_8]
0x180030c85  xor     rcx, rsp; StackCookie
0x180030c88  call    __security_check_cookie
0x180030c8d  mov     rbx, [rsp+80h+arg_18]
0x180030c95  add     rsp, 80h
0x180030c9c  pop     r15
0x180030c9e  pop     r14
0x180030ca0  pop     r13
0x180030ca2  pop     r12
0x180030ca4  pop     rdi
0x180030ca5  pop     rsi
0x180030ca6  pop     rbp
0x180030ca7  retn
```
