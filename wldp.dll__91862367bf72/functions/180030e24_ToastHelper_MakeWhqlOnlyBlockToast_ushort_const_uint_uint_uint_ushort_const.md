# ToastHelper::MakeWhqlOnlyBlockToast(ushort const *,uint,uint,uint,ushort const *)

- ea: `0x180030e24`
- end: `0x180030fc5`
- name: `?MakeWhqlOnlyBlockToast@ToastHelper@@SAJPEBGIII0@Z`
- size: `417`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800310c0`

## callees

- `0x18001f038`
- `0x180021ec0`
- `0x18002f9d4`
- `0x18002fb1c`
- `0x18002fb7c`
- `0x18002ff7c`
- `0x180030224`
- `0x180030260`
- `0x180030e24`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030f67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030f67`

## string_xrefs

- `0x180030efd`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x180030edf`: `<toast launch="https://go.microsoft.com/fwlink/?linkid=2352532" activationType="protocol"> <visual>  <binding template="ToastGeneric">   <text id="2004"></text>   <text id="3004"></text>  </binding> </visual> <actions>  <action id="4004" activationType="protocol" arguments="https://go.microsoft.com/fwlink/?linkid=2352532"/> </actions></toast>`
- `0x180030e8a`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ToastHelper::MakeWhqlOnlyBlockToast(
        const unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 *a5)
{
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rdx
  unsigned __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v13; // rcx
  unsigned int v15; // [rsp+20h] [rbp-60h]
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  struct Windows::Data::Xml::Dom::IXmlDocument *v17; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v18[8]; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v20; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  string = 0;
  v17 = 0;
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Xml.Dom.XmlDocument",
    0x21u,
    0x20u);
  v5 = Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(v20, &v17);
  v6 = v5;
  v20 = 0;
  if ( v5 >= 0 )
  {
    v5 = ToastHelper::BuildBlockToastXml(
           (__int64 (__fastcall ***)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, int *))v17,
           L"<toast launch=\"https://go.microsoft.com/fwlink/?linkid=2352532\" activationType=\"protocol\"> <visual>  <bin"
            "ding template=\"ToastGeneric\">   <text id=\"2004\"></text>   <text id=\"3004\"></text>  </binding> </visual"
            "> <actions>  <action id=\"4004\" activationType=\"protocol\" arguments=\"https://go.microsoft.com/fwlink/?li"
            "nkid=2352532\"/> </actions></toast>",
           0x7D4u,
           0xBBCu,
           0xFA4u,
           0,
           a5);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v9 = wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocument,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNodeSerializer>(
             &v17,
             v18);
      v10 = *(_QWORD *)v9;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v9 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v6 = v11(v10, &string);
      wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v18);
      if ( v6 < 0 )
      {
        v8 = (unsigned int)v6;
        v7 = 470;
        goto LABEL_6;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v5 = ToastHelper::LaunchToast(v13, StringRawBuffer);
      v6 = v5;
      if ( v5 >= 0 )
      {
        v6 = 0;
        goto LABEL_12;
      }
      v7 = 472;
    }
    else
    {
      v7 = 468;
    }
  }
  else
  {
    v7 = 466;
  }
  v8 = (unsigned int)v5;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
    (const char *)v8,
    v15);
LABEL_12:
  WindowsDeleteString(string);
  string = 0;
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180030e24  mov     [rsp-8+arg_0], rbx
0x180030e29  mov     [rsp-8+arg_8], rdi
0x180030e2e  push    rbp
0x180030e2f  mov     rbp, rsp
0x180030e32  sub     rsp, 80h
0x180030e39  mov     rax, cs:__security_cookie
0x180030e40  xor     rax, rsp
0x180030e43  mov     [rbp+var_8], rax
0x180030e47  mov     rdi, [rbp+arg_20]
0x180030e4b  mov     [rbp+var_38], 0
0x180030e53  mov     [rbp+string], 0
0x180030e5b  mov     rcx, [rbp+var_38]
0x180030e5f  mov     [rbp+var_38], 0
0x180030e67  test    rcx, rcx
0x180030e6a  jz      short loc_180030E78
0x180030e6c  mov     rax, [rcx]
0x180030e6f  mov     rax, [rax+10h]
0x180030e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e78  mov     [rbp+var_10], 0
0x180030e80  mov     r9d, 20h ; ' '; unsigned int
0x180030e86  lea     r8d, [r9+1]; unsigned int
0x180030e8a  lea     rdx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180030e91  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180030e95  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030e9a  nop
0x180030e9b  lea     rdx, [rbp+var_38]
0x180030e9f  mov     rcx, [rbp+var_10]
0x180030ea3  call    ??$ActivateInstance@UIXmlDocument@Dom@Xml@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIXmlDocument@Dom@Xml@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Xml::Dom::IXmlDocument>(HSTRING__ *,Windows::Data::Xml::Dom::IXmlDocument * *)
0x180030ea8  mov     ebx, eax
0x180030eaa  mov     [rbp+var_10], 0
0x180030eb2  test    eax, eax
0x180030eb4  jns     short loc_180030EBD
0x180030eb6  mov     edx, 1D2h
0x180030ebb  jmp     short loc_180030EFA
0x180030ebd  mov     [rsp+80h+var_50], rdi; unsigned __int16 *
0x180030ec2  mov     [rsp+80h+var_58], 0; unsigned __int16 *
0x180030ecb  mov     [rsp+80h+var_60], 0FA4h; int
0x180030ed3  mov     r9d, 0BBCh; unsigned int
0x180030ed9  mov     r8d, 7D4h; unsigned int
0x180030edf  lea     rdx, aToastLaunchHtt_2; "<toast launch=\"https://go.microsoft.co"...
0x180030ee6  mov     rcx, [rbp+var_38]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x180030eea  call    ?BuildBlockToastXml@ToastHelper@@SAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEAGIIIPEBG2@Z; ToastHelper::BuildBlockToastXml(Windows::Data::Xml::Dom::IXmlDocument *,ushort *,uint,uint,uint,ushort const *,ushort const *)
0x180030eef  mov     ebx, eax
0x180030ef1  test    eax, eax
0x180030ef3  jns     short loc_180030F0F
0x180030ef5  mov     edx, 1D4h; void *
0x180030efa  mov     r9d, eax; char *
0x180030efd  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x180030f04  mov     rcx, [rbp+8]; this
0x180030f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030f0d  jmp     short loc_180030F87
0x180030f0f  lea     rdx, [rbp+var_30]
0x180030f13  lea     rcx, [rbp+var_38]
0x180030f17  call    ??$query@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@@?$com_ptr_t@UIXmlDocument@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIXmlNodeSerializer@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocument,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNodeSerializer>(void)
0x180030f1c  nop
0x180030f1d  mov     rdi, [rax]
0x180030f20  mov     rax, [rdi]
0x180030f23  mov     rbx, [rax+30h]
0x180030f27  mov     rcx, [rbp+string]; string
0x180030f2b  call    cs:__imp_WindowsDeleteString
0x180030f31  mov     [rbp+string], 0
0x180030f39  lea     rdx, [rbp+string]
0x180030f3d  mov     rcx, rdi
0x180030f40  mov     rax, rbx
0x180030f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f48  mov     ebx, eax
0x180030f4a  lea     rcx, [rbp+var_30]
0x180030f4e  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x180030f53  test    ebx, ebx
0x180030f55  jns     short loc_180030F61
0x180030f57  mov     r9d, ebx
0x180030f5a  mov     edx, 1D6h
0x180030f5f  jmp     short loc_180030EFD
0x180030f61  xor     edx, edx; length
0x180030f63  mov     rcx, [rbp+string]; string
0x180030f67  call    cs:__imp_WindowsGetStringRawBuffer
0x180030f6d  mov     rdx, rax; unsigned __int16 *
0x180030f70  call    ?LaunchToast@ToastHelper@@SAJPEBG0@Z; ToastHelper::LaunchToast(ushort const *,ushort const *)
0x180030f75  mov     ebx, eax
0x180030f77  test    eax, eax
0x180030f79  jns     short loc_180030F85
0x180030f7b  mov     edx, 1D8h
0x180030f80  jmp     loc_180030EFA
0x180030f85  xor     ebx, ebx
0x180030f87  mov     rcx, [rbp+string]; string
0x180030f8b  call    cs:__imp_WindowsDeleteString
0x180030f91  mov     [rbp+string], 0
0x180030f99  lea     rcx, [rbp+var_38]
0x180030f9d  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x180030fa2  mov     eax, ebx
0x180030fa4  mov     rcx, [rbp+var_8]
0x180030fa8  xor     rcx, rsp; StackCookie
0x180030fab  call    __security_check_cookie
0x180030fb0  lea     r11, [rsp+80h+var_s0]
0x180030fb8  mov     rbx, [r11+10h]
0x180030fbc  mov     rdi, [r11+18h]
0x180030fc0  mov     rsp, r11
0x180030fc3  pop     rbp
0x180030fc4  retn
```
