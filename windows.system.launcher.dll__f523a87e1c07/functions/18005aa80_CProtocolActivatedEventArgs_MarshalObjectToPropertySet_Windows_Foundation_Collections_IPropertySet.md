# CProtocolActivatedEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18005aa80`
- end: `0x18005add7`
- name: `?MarshalObjectToPropertySet@CProtocolActivatedEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(CProtocolActivatedEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x18001bed8`
- `0x180027108`
- `0x18002cec0`
- `0x18005aa80`
- `0x18005ade0`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005abcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ac08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ad80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005abcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ac08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ad80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005abe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18005abe0`

## string_xrefs

- `0x18005aac4`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x18005ab50`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x18005ab92`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x18005abf5`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`
- `0x18005ad06`: `onecoreuap\shell\lib\activationeventsshell\protocolactivated.cpp`

## pseudocode

```c
__int64 __fastcall CProtocolActivatedEventArgs::MarshalObjectToPropertySet(
        CProtocolActivatedEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  HSTRING v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // rdx
  _QWORD *v14; // rsi
  void *v15; // rbx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(_QWORD *, __int64, void *, _BYTE *); // rdi
  __int64 v18; // rbx
  _QWORD *v19; // rsi
  __int64 v20; // rax
  __int64 (__fastcall *v21)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdx
  _QWORD *v26; // rsi
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  int v31; // [rsp+20h] [rbp-29h]
  _BYTE v32[8]; // [rsp+30h] [rbp-19h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-11h] BYREF
  void *v34; // [rsp+40h] [rbp-9h] BYREF
  __int64 v35; // [rsp+48h] [rbp-1h] BYREF
  __int64 v36; // [rsp+50h] [rbp+7h] BYREF
  _QWORD *v37; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v38; // [rsp+60h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v40; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(
         (CProtocolActivatedEventArgs *)((char *)this + 48),
         a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
    v37 = 0;
    v38 = 0;
    v7 = *v6;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    v8 = v7(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v37);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 96;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
        (const char *)(unsigned int)v8,
        v31);
LABEL_26:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      return v5;
    }
    v40 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.PropertyValue",
      0x21u,
      0x20u);
    v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
           v40,
           &v38);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 97;
      goto LABEL_7;
    }
    v34 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v10 = Microsoft::WRL::AgileRef::InternalResolve(
            (CProtocolActivatedEventArgs *)((char *)this + 296),
            &GUID_9e365e57_48b2_4160_956f_c7385120bbfc,
            &v34);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
        (const char *)(unsigned int)v10,
        v31);
LABEL_10:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      goto LABEL_26;
    }
    v35 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v35 = 0;
    newString = 0;
    WindowsDeleteString(0);
    v11 = (HSTRING)*((_QWORD *)this + 38);
    newString = 0;
    v12 = WindowsDuplicateString(v11, &newString);
    v5 = v12;
    if ( v12 >= 0 )
    {
      v14 = v37;
      v15 = v34;
      v32[0] = 0;
      v16 = *v37;
      v40 = 0;
      v17 = *(__int64 (__fastcall **)(_QWORD *, __int64, void *, _BYTE *))(v16 + 80);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Uri", 4u, 3u);
      v12 = v17(v14, v40, v15, v32);
      v5 = v12;
      if ( v12 >= 0 )
      {
        v18 = v35;
        if ( !v35
          || (v19 = v37,
              v20 = *v37,
              v40 = 0,
              v21 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v20 + 80),
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Data", 5u, 4u),
              v12 = v21(v19, v40, v18, v32),
              v5 = v12,
              v12 >= 0) )
        {
          v22 = v38;
          v36 = 0;
          v23 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v38 + 144LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
          v24 = v23(v22, newString, &v36);
          v5 = v24;
          if ( v24 >= 0 )
          {
            v26 = v37;
            v27 = v36;
            v28 = *v37;
            v40 = 0;
            v29 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v28 + 80);
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"CallerPackageFamilyName",
              0x18u,
              0x17u);
            v24 = v29(v26, v40, v27, v32);
            v5 = v24;
            if ( v24 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
              WindowsDeleteString(newString);
              newString = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
              v5 = 0;
              goto LABEL_26;
            }
            v25 = 121;
          }
          else
          {
            v25 = 120;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v25,
            (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
            (const char *)(unsigned int)v24,
            v31);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
          goto LABEL_14;
        }
        v13 = 116;
      }
      else
      {
        v13 = 112;
      }
    }
    else
    {
      v13 = 108;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
      (const char *)(unsigned int)v12,
      v31);
LABEL_14:
    WindowsDeleteString(newString);
    newString = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B,
    (unsigned int)"onecoreuap\\shell\\lib\\activationeventsshell\\protocolactivated.cpp",
    (const char *)(unsigned int)v4,
    v31);
  return v5;
}

```

## disassembly

```asm
0x18005aa80  mov     [rsp-8+arg_10], rbx
0x18005aa85  mov     [rsp-8+arg_18], rsi
0x18005aa8a  push    rbp
0x18005aa8b  push    rdi
0x18005aa8c  push    r14
0x18005aa8e  lea     rbp, [rsp-47h]
0x18005aa93  sub     rsp, 90h
0x18005aa9a  mov     rax, cs:__security_cookie
0x18005aaa1  xor     rax, rsp
0x18005aaa4  mov     [rbp+57h+var_18], rax
0x18005aaa8  mov     rdi, rcx
0x18005aaab  mov     rsi, rdx
0x18005aaae  add     rcx, 30h ; '0'; this
0x18005aab2  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x18005aab7  xor     r14d, r14d
0x18005aaba  mov     ebx, eax
0x18005aabc  test    eax, eax
0x18005aabe  jns     short loc_18005AADC
0x18005aac0  mov     rcx, [rbp+5Fh]; this
0x18005aac4  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\lib\\activationevent"...
0x18005aacb  mov     r9d, eax; char *
0x18005aace  lea     edx, [r14+5Bh]; void *
0x18005aad2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aad7  jmp     loc_18005ADB1
0x18005aadc  mov     rax, [rsi]
0x18005aadf  lea     rcx, [rbp+57h+var_48]
0x18005aae3  mov     [rbp+57h+var_48], r14
0x18005aae7  mov     [rbp+57h+var_40], r14
0x18005aaeb  mov     rbx, [rax]
0x18005aaee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005aaf3  lea     r8, [rbp+57h+var_48]
0x18005aaf7  mov     rcx, rsi
0x18005aafa  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18005ab01  mov     rax, rbx
0x18005ab04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab09  mov     ebx, eax
0x18005ab0b  test    eax, eax
0x18005ab0d  jns     short loc_18005AB16
0x18005ab0f  mov     edx, 60h ; '`'
0x18005ab14  jmp     short loc_18005AB4C
0x18005ab16  mov     r9d, 20h ; ' '; unsigned int
0x18005ab1c  mov     [rbp+57h+var_20], r14
0x18005ab20  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18005ab27  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ab2b  lea     r8d, [r9+1]; unsigned int
0x18005ab2f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005ab34  mov     rcx, [rbp+57h+var_20]
0x18005ab38  lea     rdx, [rbp+57h+var_40]
0x18005ab3c  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18005ab41  mov     ebx, eax
0x18005ab43  test    eax, eax
0x18005ab45  jns     short loc_18005AB64
0x18005ab47  mov     edx, 61h ; 'a'; void *
0x18005ab4c  mov     rcx, [rbp+5Fh]; this
0x18005ab50  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\lib\\activationevent"...
0x18005ab57  mov     r9d, eax; char *
0x18005ab5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ab5f  jmp     loc_18005AD9F
0x18005ab64  lea     rcx, [rbp+57h+var_60]
0x18005ab68  mov     [rbp+57h+var_60], r14
0x18005ab6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ab71  lea     rcx, [rdi+128h]; this
0x18005ab78  lea     r8, [rbp+57h+var_60]; void **
0x18005ab7c  lea     rdx, _GUID_9e365e57_48b2_4160_956f_c7385120bbfc; struct _GUID *
0x18005ab83  call    ?InternalResolve@AgileRef@WRL@Microsoft@@IEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::AgileRef::InternalResolve(_GUID const &,void * *)
0x18005ab88  mov     ebx, eax
0x18005ab8a  test    eax, eax
0x18005ab8c  jns     short loc_18005ABB4
0x18005ab8e  mov     rcx, [rbp+5Fh]; this
0x18005ab92  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\lib\\activationevent"...
0x18005ab99  mov     r9d, eax; char *
0x18005ab9c  mov     edx, 65h ; 'e'; void *
0x18005aba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aba6  lea     rcx, [rbp+57h+var_60]
0x18005abaa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005abaf  jmp     loc_18005AD9F
0x18005abb4  lea     rcx, [rbp+57h+var_58]
0x18005abb8  mov     [rbp+57h+var_58], r14
0x18005abbc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005abc1  xor     ecx, ecx; string
0x18005abc3  mov     [rbp+57h+var_58], r14
0x18005abc7  mov     [rbp+57h+newString], r14
0x18005abcb  call    cs:__imp_WindowsDeleteString
0x18005abd1  mov     rcx, [rdi+130h]; string
0x18005abd8  lea     rdx, [rbp+57h+newString]; newString
0x18005abdc  mov     [rbp+57h+newString], r14
0x18005abe0  call    cs:__imp_WindowsDuplicateString
0x18005abe6  mov     ebx, eax
0x18005abe8  test    eax, eax
0x18005abea  jns     short loc_18005AC1D
0x18005abec  mov     edx, 6Ch ; 'l'; void *
0x18005abf1  mov     rcx, [rbp+5Fh]; this
0x18005abf5  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\lib\\activationevent"...
0x18005abfc  mov     r9d, eax; char *
0x18005abff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ac04  mov     rcx, [rbp+57h+newString]; string
0x18005ac08  call    cs:__imp_WindowsDeleteString
0x18005ac0e  lea     rcx, [rbp+57h+var_58]
0x18005ac12  mov     [rbp+57h+newString], r14
0x18005ac16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ac1b  jmp     short loc_18005ABA6
0x18005ac1d  mov     rsi, [rbp+57h+var_48]
0x18005ac21  lea     rdx, aUri_0; "Uri"
0x18005ac28  mov     rbx, [rbp+57h+var_60]
0x18005ac2c  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ac30  mov     [rbp+57h+var_70], r14b
0x18005ac34  mov     r9d, 3; unsigned int
0x18005ac3a  mov     rax, [rsi]
0x18005ac3d  mov     [rbp+57h+var_20], r14
0x18005ac41  lea     r8d, [r9+1]; unsigned int
0x18005ac45  mov     rdi, [rax+50h]
0x18005ac49  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005ac4e  mov     rdx, [rbp+57h+var_20]
0x18005ac52  lea     r9, [rbp+57h+var_70]
0x18005ac56  mov     r8, rbx
0x18005ac59  mov     rcx, rsi
0x18005ac5c  mov     rax, rdi
0x18005ac5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac64  mov     ebx, eax
0x18005ac66  test    eax, eax
0x18005ac68  jns     short loc_18005AC71
0x18005ac6a  mov     edx, 70h ; 'p'
0x18005ac6f  jmp     short loc_18005ABF1
0x18005ac71  mov     rbx, [rbp+57h+var_58]
0x18005ac75  test    rbx, rbx
0x18005ac78  jz      short loc_18005ACC9
0x18005ac7a  mov     rsi, [rbp+57h+var_48]
0x18005ac7e  lea     rdx, aData; "Data"
0x18005ac85  mov     r9d, 4; unsigned int
0x18005ac8b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ac8f  mov     rax, [rsi]
0x18005ac92  lea     r8d, [r9+1]; unsigned int
0x18005ac96  mov     [rbp+57h+var_20], r14
0x18005ac9a  mov     rdi, [rax+50h]
0x18005ac9e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005aca3  mov     rdx, [rbp+57h+var_20]
0x18005aca7  lea     r9, [rbp+57h+var_70]
0x18005acab  mov     r8, rbx
0x18005acae  mov     rcx, rsi
0x18005acb1  mov     rax, rdi
0x18005acb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005acb9  mov     ebx, eax
0x18005acbb  test    eax, eax
0x18005acbd  jns     short loc_18005ACC9
0x18005acbf  mov     edx, 74h ; 't'
0x18005acc4  jmp     loc_18005ABF1
0x18005acc9  mov     rdi, [rbp+57h+var_40]
0x18005accd  lea     rcx, [rbp+57h+var_50]
0x18005acd1  mov     [rbp+57h+var_50], r14
0x18005acd5  mov     rax, [rdi]
0x18005acd8  mov     rbx, [rax+90h]
0x18005acdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ace4  mov     rdx, [rbp+57h+newString]
0x18005ace8  lea     r8, [rbp+57h+var_50]
0x18005acec  mov     rcx, rdi
0x18005acef  mov     rax, rbx
0x18005acf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005acf7  mov     ebx, eax
0x18005acf9  test    eax, eax
0x18005acfb  jns     short loc_18005AD23
0x18005acfd  mov     edx, 78h ; 'x'; void *
0x18005ad02  mov     rcx, [rbp+5Fh]; this
0x18005ad06  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\lib\\activationevent"...
0x18005ad0d  mov     r9d, eax; char *
0x18005ad10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ad15  lea     rcx, [rbp+57h+var_50]
0x18005ad19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ad1e  jmp     loc_18005AC04
0x18005ad23  mov     rsi, [rbp+57h+var_48]
0x18005ad27  lea     rdx, aCallerpackagef; "CallerPackageFamilyName"
0x18005ad2e  mov     rbx, [rbp+57h+var_50]
0x18005ad32  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18005ad36  mov     r9d, 17h; unsigned int
0x18005ad3c  mov     rax, [rsi]
0x18005ad3f  mov     [rbp+57h+var_20], r14
0x18005ad43  lea     r8d, [r9+1]; unsigned int
0x18005ad47  mov     rdi, [rax+50h]
0x18005ad4b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005ad50  mov     rdx, [rbp+57h+var_20]
0x18005ad54  lea     r9, [rbp+57h+var_70]
0x18005ad58  mov     r8, rbx
0x18005ad5b  mov     rcx, rsi
0x18005ad5e  mov     rax, rdi
0x18005ad61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad66  mov     ebx, eax
0x18005ad68  test    eax, eax
0x18005ad6a  jns     short loc_18005AD73
0x18005ad6c  mov     edx, 79h ; 'y'
0x18005ad71  jmp     short loc_18005AD02
0x18005ad73  lea     rcx, [rbp+57h+var_50]
0x18005ad77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ad7c  mov     rcx, [rbp+57h+newString]; string
0x18005ad80  call    cs:__imp_WindowsDeleteString
0x18005ad86  lea     rcx, [rbp+57h+var_58]
0x18005ad8a  mov     [rbp+57h+newString], r14
0x18005ad8e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ad93  lea     rcx, [rbp+57h+var_60]
0x18005ad97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ad9c  mov     ebx, r14d
0x18005ad9f  lea     rcx, [rbp+57h+var_40]
0x18005ada3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005ada8  lea     rcx, [rbp+57h+var_48]
0x18005adac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005adb1  mov     eax, ebx
0x18005adb3  mov     rcx, [rbp+57h+var_18]
0x18005adb7  xor     rcx, rsp; StackCookie
0x18005adba  call    __security_check_cookie
0x18005adbf  lea     r11, [rsp+0A0h+var_10]
0x18005adc7  mov     rbx, [r11+30h]
0x18005adcb  mov     rsi, [r11+38h]
0x18005adcf  mov     rsp, r11
0x18005add2  pop     r14
0x18005add4  pop     rdi
0x18005add5  pop     rbp
0x18005add6  retn
```
