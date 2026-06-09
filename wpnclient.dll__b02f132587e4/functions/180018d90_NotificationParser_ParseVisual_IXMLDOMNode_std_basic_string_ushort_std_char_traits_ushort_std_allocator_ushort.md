# NotificationParser::ParseVisual(IXMLDOMNode *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WPN_APP_TYPE,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180018d90`
- end: `0x1800192cc`
- name: `?ParseVisual@NotificationParser@@AEAAXPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WPN_APP_TYPE@@PEBG3W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1340`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002b70`

## callees

- `0x180005670`
- `0x180008390`
- `0x1800087d0`
- `0x180008910`
- `0x180008fe0`
- `0x18000b440`
- `0x18000dc30`
- `0x1800119b0`
- `0x180014500`
- `0x1800151b8`
- `0x180018d90`
- `0x1800192d4`
- `0x18001a610`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall NotificationParser::ParseVisual(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3,
        int a4,
        const WCHAR *a5,
        __int64 a6,
        int a7,
        int a8,
        _QWORD *a9)
{
  _QWORD *v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // r12d
  char v17; // r15
  int v18; // r14d
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, int *); // rbx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING, _BYTE *); // rbx
  HSTRING *v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, HSTRING, __int64, char *); // rdi
  __int64 v30; // rbx
  HSTRING *v31; // rax
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, HSTRING, __int64, char *); // rdi
  __int64 v36; // rbx
  HSTRING *v37; // rax
  int v38; // eax
  int v39; // eax
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, HSTRING, __int64, char *); // rdi
  __int64 v42; // rbx
  int v43; // eax
  __int64 result; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  int packageFullName; // [rsp+20h] [rbp-C9h]
  int v53; // [rsp+28h] [rbp-C1h]
  char v54; // [rsp+40h] [rbp-A9h] BYREF
  _BYTE v55[7]; // [rsp+41h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+48h] [rbp-A1h] BYREF
  int v57[2]; // [rsp+50h] [rbp-99h] BYREF
  __int64 v58; // [rsp+58h] [rbp-91h] BYREF
  int v59; // [rsp+60h] [rbp-89h] BYREF
  int v60[2]; // [rsp+68h] [rbp-81h] BYREF
  __int64 v61; // [rsp+70h] [rbp-79h] BYREF
  __int64 v62; // [rsp+78h] [rbp-71h] BYREF
  __int64 v63; // [rsp+80h] [rbp-69h] BYREF
  __int64 v64; // [rsp+88h] [rbp-61h] BYREF
  int v65; // [rsp+90h] [rbp-59h]
  PCWSTR v66; // [rsp+98h] [rbp-51h]
  _QWORD *v67; // [rsp+A0h] [rbp-49h]
  __int64 v68; // [rsp+A8h] [rbp-41h]
  HSTRING string[4]; // [rsp+B0h] [rbp-39h] BYREF
  unsigned __int16 v70[12]; // [rsp+D0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+3Fh]

  v65 = a4;
  v66 = a5;
  v12 = a9;
  v67 = a9;
  v63 = 0;
  v56 = 0;
  v58 = 0;
  *(_QWORD *)v57 = 0;
  v68 = 0;
  v62 = 0;
  v64 = 0;
  v61 = 0;
  v54 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v56);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63);
  NotificationParser::CreateValueSet(v13, &v63, &v56);
  NotificationParser::GetAttributes(a1, a2, v56);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v61);
  NotificationParser::FindBindings(v14, a2, a3, &v61);
  if ( !v61 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)0x80070490LL,
      packageFullName);
  v59 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v61 + 64LL))(v61, &v59);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x280,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v15,
      packageFullName);
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( v59 > 0 )
  {
    do
    {
      *(_QWORD *)v60 = 0;
      v19 = v61;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v61 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v60);
      v21 = v20(v19, (unsigned int)v18, v60);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x28C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v21,
          packageFullName);
      NotificationParser::GetAttributes(a1, *(__int64 *)v60, v56);
      NotificationParser::ResolveTextElement(a1, v56, L"displayName", (__int64)v66);
      NotificationParser::SavePushDownAttributes((__int64)a1, v56);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v57);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
      NotificationParser::CreateValueSet(v22, &v58, v57);
      v55[0] = 0;
      NotificationParser::GetAttributes(a1, *(__int64 *)v60, *(__int64 *)v57);
      v23 = *(_QWORD *)v57;
      v24 = *(__int64 (__fastcall **)(__int64, HSTRING, _BYTE *))(**(_QWORD **)v57 + 64LL);
      v25 = Windows::Internal::StringReference::StringReference(string, L"experienceType");
      v26 = v24(v23, *v25, v55);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
          (const char *)(unsigned int)v26,
          packageFullName);
      if ( v55[0] )
      {
        if ( !v62 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
          NotificationParser::CreateValueSet(v33, &v62, &v64);
          v34 = v56;
          v35 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v56 + 80LL);
          v36 = v62;
          v37 = Windows::Internal::StringReference::StringReference(string, L"bindings");
          v38 = v35(v34, *v37, v36, &v54);
          if ( v38 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2BA,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v38,
              packageFullName);
        }
        v39 = StringCchPrintfW(v70, 0xAu, L"%ld", v16);
        if ( v39 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2BE,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v39,
            packageFullName);
        v40 = v64;
        v41 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v64 + 80LL);
        v42 = v58;
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v70);
        v43 = v41(v40, string[0], v42, &v54);
        if ( v43 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2C2,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
            (const char *)(unsigned int)v43,
            packageFullName);
        ++v16;
      }
      else
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v57);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v58);
        NotificationParser::CreateValueSet(v27, &v58, v57);
        if ( !v17 )
        {
          v28 = v56;
          v29 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, char *))(*(_QWORD *)v56 + 80LL);
          v30 = v58;
          v31 = Windows::Internal::StringReference::StringReference(string, L"items");
          v32 = v29(v28, *v31, v30, &v54);
          if ( v32 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2AB,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notif"
                            "icationparser.cpp",
              (const char *)(unsigned int)v32,
              packageFullName);
          v17 = 1;
        }
      }
      NotificationParser::ParseBindingChildren(
        (NotificationParser *)a1,
        *(__int64 *)v60,
        *(__int64 *)v57,
        v65,
        (unsigned __int16 *)v66,
        v53,
        a7,
        a8);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v60);
      ++v18;
    }
    while ( v18 < v59 );
    v12 = v67;
  }
  if ( !v17 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)0xC00CE225LL,
      packageFullName);
  result = v63;
  v63 = 0;
  *v12 = result;
  v45 = v61;
  if ( v61 )
  {
    v61 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v64;
  if ( v64 )
  {
    v64 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v62;
  if ( v62 )
  {
    v62 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v48 = *(_QWORD *)v57;
  if ( *(_QWORD *)v57 )
  {
    *(_QWORD *)v57 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
  v49 = v58;
  if ( v58 )
  {
    v58 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
  v50 = v56;
  if ( v56 )
  {
    v56 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v63;
  if ( v63 )
  {
    v63 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  return result;
}

```

## disassembly

```asm
0x180018d90  mov     [rsp-8+arg_18], rbx
0x180018d95  push    rbp
0x180018d96  push    rsi
0x180018d97  push    rdi
0x180018d98  push    r12
0x180018d9a  push    r13
0x180018d9c  push    r14
0x180018d9e  push    r15
0x180018da0  lea     rbp, [rsp-7]
0x180018da5  sub     rsp, 0F0h
0x180018dac  mov     rax, cs:__security_cookie
0x180018db3  xor     rax, rsp
0x180018db6  mov     [rbp+37h+var_38], rax
0x180018dba  mov     [rbp+37h+var_90], r9d
0x180018dbe  mov     rdi, r8
0x180018dc1  mov     rbx, rdx
0x180018dc4  mov     r13, rcx
0x180018dc7  mov     rax, [rbp+37h+arg_20]
0x180018dcb  mov     [rbp+37h+var_88], rax
0x180018dcf  mov     rsi, [rbp+37h+arg_40]
0x180018dd6  mov     [rbp+37h+var_80], rsi
0x180018dda  xor     eax, eax
0x180018ddc  mov     [rbp+37h+var_A0], rax
0x180018de0  mov     [rsp+120h+var_D8], rax
0x180018de5  mov     [rsp+120h+var_C8], rax
0x180018dea  mov     qword ptr [rsp+120h+var_D0], rax
0x180018def  mov     [rbp+37h+var_78], rax
0x180018df3  mov     [rbp+37h+var_A8], rax
0x180018df7  mov     [rbp+37h+var_98], rax
0x180018dfb  mov     [rbp+37h+var_B0], rax
0x180018dff  mov     [rsp+120h+var_E0], al
0x180018e03  lea     rcx, [rsp+120h+var_D8]
0x180018e08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018e0d  lea     rcx, [rbp+37h+var_A0]
0x180018e11  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018e16  lea     r8, [rsp+120h+var_D8]
0x180018e1b  lea     rdx, [rbp+37h+var_A0]
0x180018e1f  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180018e24  mov     r8, [rsp+120h+var_D8]
0x180018e29  mov     rdx, rbx
0x180018e2c  mov     rcx, r13
0x180018e2f  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x180018e34  lea     rcx, [rbp+37h+var_B0]
0x180018e38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018e3d  lea     r9, [rbp+37h+var_B0]
0x180018e41  mov     r8, rdi
0x180018e44  mov     rdx, rbx
0x180018e47  call    ?FindBindings@NotificationParser@@AEAAXPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIXMLDOMNodeList@@@Z; NotificationParser::FindBindings(IXMLDOMNode *,std::wstring const &,IXMLDOMNodeList * *)
0x180018e4c  mov     rax, [rbp+3Fh]
0x180018e50  mov     rcx, [rbp+37h+var_B0]
0x180018e54  xor     ebx, ebx
0x180018e56  test    rcx, rcx
0x180018e59  jnz     short loc_180018E76
0x180018e5b  mov     r9d, 80070490h; char *
0x180018e61  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180018e68  mov     edx, 27Ch; void *
0x180018e6d  mov     rcx, rax; this
0x180018e70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018e76  mov     [rsp+120h+var_C0], ebx
0x180018e7a  mov     rax, [rcx]
0x180018e7d  lea     rdx, [rsp+120h+var_C0]
0x180018e82  mov     rax, [rax+40h]
0x180018e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e8b  mov     rcx, [rbp+3Fh]; this
0x180018e8f  test    eax, eax
0x180018e91  jns     short loc_180018EA8
0x180018e93  mov     r9d, eax; char *
0x180018e96  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180018e9d  mov     edx, 280h; void *
0x180018ea2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018ea8  mov     r12d, ebx
0x180018eab  mov     r15b, bl
0x180018eae  mov     r14d, ebx
0x180018eb1  cmp     [rsp+120h+var_C0], ebx
0x180018eb5  jle     loc_18001913B
0x180018ebb  mov     qword ptr [rsp+120h+var_B8], rbx
0x180018ec0  mov     rdi, [rbp+37h+var_B0]
0x180018ec4  mov     rax, [rdi]
0x180018ec7  mov     rbx, [rax+38h]
0x180018ecb  lea     rcx, [rsp+120h+var_B8]
0x180018ed0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018ed5  lea     r8, [rsp+120h+var_B8]
0x180018eda  mov     edx, r14d
0x180018edd  mov     rcx, rdi
0x180018ee0  mov     rax, rbx
0x180018ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ee8  mov     rcx, [rbp+3Fh]; this
0x180018eec  test    eax, eax
0x180018eee  js      loc_1800191C9
0x180018ef4  mov     r8, [rsp+120h+var_D8]
0x180018ef9  mov     rdx, qword ptr [rsp+120h+var_B8]
0x180018efe  mov     rcx, r13
0x180018f01  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x180018f06  mov     r9, [rbp+37h+var_88]
0x180018f0a  lea     r8, aDisplayname; "displayName"
0x180018f11  mov     rdx, [rsp+120h+var_D8]
0x180018f16  mov     rcx, r13
0x180018f19  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x180018f1e  mov     rdx, [rsp+120h+var_D8]
0x180018f23  mov     rcx, r13
0x180018f26  call    ?SavePushDownAttributes@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::SavePushDownAttributes(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x180018f2b  lea     rcx, [rsp+120h+var_D0]
0x180018f30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018f35  lea     rcx, [rsp+120h+var_C8]
0x180018f3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018f3f  lea     r8, [rsp+120h+var_D0]
0x180018f44  lea     rdx, [rsp+120h+var_C8]
0x180018f49  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180018f4e  mov     [rsp+120h+var_DF], 0
0x180018f53  mov     r8, qword ptr [rsp+120h+var_D0]
0x180018f58  mov     rdx, qword ptr [rsp+120h+var_B8]
0x180018f5d  mov     rcx, r13
0x180018f60  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x180018f65  mov     rdi, qword ptr [rsp+120h+var_D0]
0x180018f6a  mov     rax, [rdi]
0x180018f6d  mov     rbx, [rax+40h]
0x180018f71  lea     rdx, aExperiencetype; "experienceType"
0x180018f78  lea     rcx, [rbp+37h+string]; string
0x180018f7c  call    ??$?0$0P@@StringReference@Internal@Windows@@QEAA@AEAY0P@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[15])
0x180018f81  lea     r8, [rsp+120h+var_DF]
0x180018f86  mov     rdx, [rax]
0x180018f89  mov     rcx, rdi
0x180018f8c  mov     rax, rbx
0x180018f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f94  mov     rcx, [rbp+3Fh]; this
0x180018f98  xor     ebx, ebx
0x180018f9a  test    eax, eax
0x180018f9c  js      loc_1800191B4
0x180018fa2  cmp     [rsp+120h+var_DF], bl
0x180018fa6  jnz     short loc_180019021
0x180018fa8  lea     rcx, [rsp+120h+var_D0]
0x180018fad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018fb2  lea     rcx, [rsp+120h+var_C8]
0x180018fb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018fbc  lea     r8, [rsp+120h+var_D0]
0x180018fc1  lea     rdx, [rsp+120h+var_C8]
0x180018fc6  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180018fcb  test    r15b, r15b
0x180018fce  jnz     loc_1800190F1
0x180018fd4  mov     rsi, [rsp+120h+var_D8]
0x180018fd9  mov     rax, [rsi]
0x180018fdc  mov     rdi, [rax+50h]
0x180018fe0  mov     rbx, [rsp+120h+var_C8]
0x180018fe5  lea     rdx, aItems; "items"
0x180018fec  lea     rcx, [rbp+37h+string]; string
0x180018ff0  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x180018ff5  lea     r9, [rsp+120h+var_E0]
0x180018ffa  mov     r8, rbx
0x180018ffd  mov     rdx, [rax]
0x180019000  mov     rcx, rsi
0x180019003  mov     rax, rdi
0x180019006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001900b  mov     rcx, [rbp+3Fh]; this
0x18001900f  xor     ebx, ebx
0x180019011  test    eax, eax
0x180019013  js      loc_180019160
0x180019019  mov     r15b, 1
0x18001901c  jmp     loc_1800190F1
0x180019021  cmp     [rbp+37h+var_A8], rbx
0x180019025  jnz     short loc_180019088
0x180019027  lea     rcx, [rbp+37h+var_98]
0x18001902b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019030  lea     rcx, [rbp+37h+var_A8]
0x180019034  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019039  lea     r8, [rbp+37h+var_98]
0x18001903d  lea     rdx, [rbp+37h+var_A8]
0x180019041  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180019046  mov     rsi, [rsp+120h+var_D8]
0x18001904b  mov     rax, [rsi]
0x18001904e  mov     rdi, [rax+50h]
0x180019052  mov     rbx, [rbp+37h+var_A8]
0x180019056  lea     rdx, aBindings; "bindings"
0x18001905d  lea     rcx, [rbp+37h+string]; string
0x180019061  call    ??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[9])
0x180019066  lea     r9, [rsp+120h+var_E0]
0x18001906b  mov     r8, rbx
0x18001906e  mov     rdx, [rax]
0x180019071  mov     rcx, rsi
0x180019074  mov     rax, rdi
0x180019077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001907c  mov     rcx, [rbp+3Fh]; this
0x180019080  test    eax, eax
0x180019082  js      loc_180019175
0x180019088  mov     r9d, r12d
0x18001908b  lea     r8, aLd; "%ld"
0x180019092  mov     edx, 0Ah; unsigned __int64
0x180019097  lea     rcx, [rbp+37h+var_50]; unsigned __int16 *
0x18001909b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800190a0  mov     rcx, [rbp+3Fh]; this
0x1800190a4  test    eax, eax
0x1800190a6  js      loc_18001919F
0x1800190ac  mov     rsi, [rbp+37h+var_98]
0x1800190b0  mov     rax, [rsi]
0x1800190b3  mov     rdi, [rax+50h]
0x1800190b7  mov     rbx, [rsp+120h+var_C8]
0x1800190bc  lea     rdx, [rbp+37h+var_50]; unsigned __int16 *
0x1800190c0  lea     rcx, [rbp+37h+string]; this
0x1800190c4  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800190c9  lea     r9, [rsp+120h+var_E0]
0x1800190ce  mov     r8, rbx
0x1800190d1  mov     rdx, [rbp+37h+string]
0x1800190d5  mov     rcx, rsi
0x1800190d8  mov     rax, rdi
0x1800190db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190e0  mov     rcx, [rbp+3Fh]; this
0x1800190e4  xor     ebx, ebx
0x1800190e6  test    eax, eax
0x1800190e8  js      loc_18001918A
0x1800190ee  inc     r12d
0x1800190f1  mov     eax, [rbp+37h+arg_38]
0x1800190f4  mov     [rsp+120h+var_E8], eax; int
0x1800190f8  mov     eax, [rbp+37h+arg_30]
0x1800190fb  mov     [rsp+120h+var_F0], eax; int
0x1800190ff  mov     rax, [rbp+37h+var_88]
0x180019103  mov     [rsp+120h+packageFullName], rax; int
0x180019108  mov     r9d, [rbp+37h+var_90]; int
0x18001910c  mov     r8, qword ptr [rsp+120h+var_D0]; int
0x180019111  mov     rdx, qword ptr [rsp+120h+var_B8]; int
0x180019116  mov     rcx, r13; int
0x180019119  call    ?ParseBindingChildren@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@W4WPN_APP_TYPE@@PEBG3W4DEVICE_SCALE_FACTOR@@W4RESOURCE_CONTRAST@@@Z; NotificationParser::ParseBindingChildren(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,WPN_APP_TYPE,ushort const *,ushort const *,DEVICE_SCALE_FACTOR,RESOURCE_CONTRAST)
0x18001911e  nop
0x18001911f  lea     rcx, [rsp+120h+var_B8]
0x180019124  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019129  inc     r14d
0x18001912c  cmp     r14d, [rsp+120h+var_C0]
0x180019131  jl      loc_180018EBB
0x180019137  mov     rsi, [rbp+37h+var_80]
0x18001913b  mov     rcx, [rbp+3Fh]; this
0x18001913f  test    r15b, r15b
0x180019142  jnz     loc_1800191DE
0x180019148  mov     r9d, 0C00CE225h; char *
0x18001914e  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019155  mov     edx, 2CAh; void *
0x18001915a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019160  mov     r9d, eax; char *
0x180019163  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001916a  mov     edx, 2ABh; void *
0x18001916f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019175  mov     r9d, eax; char *
0x180019178  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001917f  mov     edx, 2BAh; void *
0x180019184  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001918a  mov     r9d, eax; char *
0x18001918d  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019194  mov     edx, 2C2h; void *
0x180019199  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001919f  mov     r9d, eax; char *
0x1800191a2  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800191a9  mov     edx, 2BEh; void *
0x1800191ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800191b4  mov     r9d, eax; char *
0x1800191b7  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800191be  mov     edx, 2A0h; void *
0x1800191c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800191c9  mov     r9d, eax; char *
0x1800191cc  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800191d3  mov     edx, 28Ch; void *
0x1800191d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800191de  mov     rax, [rbp+37h+var_A0]
0x1800191e2  mov     [rbp+37h+var_A0], rbx
0x1800191e6  mov     [rsi], rax
0x1800191e9  mov     rcx, [rbp+37h+var_B0]
0x1800191ed  test    rcx, rcx
0x1800191f0  jz      short loc_180019203
0x1800191f2  mov     [rbp+37h+var_B0], rbx
0x1800191f6  mov     rax, [rcx]
0x1800191f9  mov     rax, [rax+10h]
0x1800191fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019202  nop
0x180019203  mov     rcx, [rbp+37h+var_98]
0x180019207  test    rcx, rcx
0x18001920a  jz      short loc_18001921D
0x18001920c  mov     [rbp+37h+var_98], rbx
0x180019210  mov     rax, [rcx]
0x180019213  mov     rax, [rax+10h]
0x180019217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001921c  nop
0x18001921d  mov     rcx, [rbp+37h+var_A8]
0x180019221  test    rcx, rcx
0x180019224  jz      short loc_180019237
0x180019226  mov     [rbp+37h+var_A8], rbx
0x18001922a  mov     rax, [rcx]
0x18001922d  mov     rax, [rax+10h]
0x180019231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019236  nop
0x180019237  mov     rcx, qword ptr [rsp+120h+var_D0]
0x18001923c  test    rcx, rcx
0x18001923f  jz      short loc_180019253
0x180019241  mov     qword ptr [rsp+120h+var_D0], rbx
0x180019246  mov     rax, [rcx]
0x180019249  mov     rax, [rax+10h]
0x18001924d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019252  nop
0x180019253  mov     rcx, [rsp+120h+var_C8]
0x180019258  test    rcx, rcx
0x18001925b  jz      short loc_18001926F
0x18001925d  mov     [rsp+120h+var_C8], rbx
0x180019262  mov     rax, [rcx]
0x180019265  mov     rax, [rax+10h]
0x180019269  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
