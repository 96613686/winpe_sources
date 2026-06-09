# ToastActivationEventArgs::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18002e190`
- end: `0x18002e478`
- name: `?MarshalObjectToPropertySet@ToastActivationEventArgs@@UEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `744`
- prototype: `__int64 __fastcall(ToastActivationEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x180013bc0`
- `0x18001478c`
- `0x18001ff00`
- `0x18002e190`
- `0x18002f7e4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e2c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e2c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e433`

## string_xrefs

- `0x18002e1d7`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18002e263`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18002e2ab`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18002e2fb`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18002e357`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`

## pseudocode

```c
__int64 __fastcall ToastActivationEventArgs::MarshalObjectToPropertySet(
        ToastActivationEventArgs *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall **v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **); // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(char *, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rax
  __int64 (__fastcall *v13)(char *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdx
  _QWORD *v19; // rsi
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 (__fastcall *v22)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  __int64 v23; // rbx
  _QWORD *v24; // rsi
  __int64 v25; // rax
  __int64 (__fastcall *v26)(_QWORD *, __int64, __int64, _BYTE *); // rdi
  int v28; // [rsp+20h] [rbp-29h]
  _BYTE v29[8]; // [rsp+30h] [rbp-19h] BYREF
  HSTRING string; // [rsp+38h] [rbp-11h] BYREF
  __int64 v31; // [rsp+40h] [rbp-9h] BYREF
  __int64 v32; // [rsp+48h] [rbp-1h] BYREF
  _QWORD *v33; // [rsp+50h] [rbp+7h] BYREF
  __int64 v34; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+17h] BYREF
  __int64 v36; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v4 = CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(
         (ToastActivationEventArgs *)((char *)this - 232),
         a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, _QWORD **))a2;
    v33 = 0;
    v34 = 0;
    v7 = *v6;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v8 = v7(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v33);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 108;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastact"
                      "ivationeventargs.cpp",
        (const char *)(unsigned int)v8,
        v28);
LABEL_24:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      return v5;
    }
    v36 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.PropertyValue",
      0x21u,
      0x20u);
    v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
           v36,
           &v34);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 109;
      goto LABEL_7;
    }
    string = 0;
    v10 = *(__int64 (__fastcall **)(char *, HSTRING *))(*((_QWORD *)this - 1) + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10((char *)this - 8, &string);
    v5 = v11;
    if ( v11 >= 0 )
    {
      v12 = *((_QWORD *)this - 1);
      v31 = 0;
      v13 = *(__int64 (__fastcall **)(char *, __int64 *))(v12 + 56);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      v14 = v13((char *)this - 8, &v31);
      v5 = v14;
      if ( v14 >= 0 )
      {
        v15 = v34;
        v32 = 0;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v34 + 144LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        v17 = v16(v15, string, &v32);
        v5 = v17;
        if ( v17 >= 0 )
        {
          v19 = v33;
          v20 = v32;
          v29[0] = 0;
          v21 = *v33;
          v36 = 0;
          v22 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v21 + 80);
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Arguments", 0xAu, 9u);
          v17 = v22(v19, v36, v20, v29);
          v5 = v17;
          if ( v17 >= 0 )
          {
            v23 = v31;
            if ( !v31
              || (v24 = v33,
                  v25 = *v33,
                  v36 = 0,
                  v26 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, _BYTE *))(v25 + 80),
                  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserInput", 0xAu, 9u),
                  v17 = v26(v24, v36, v23, v29),
                  v5 = v17,
                  v17 >= 0) )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
              WindowsDeleteString(string);
              v5 = 0;
              goto LABEL_23;
            }
            v18 = 126;
          }
          else
          {
            v18 = 122;
          }
        }
        else
        {
          v18 = 120;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toasta"
                        "ctivationeventargs.cpp",
          (const char *)(unsigned int)v17,
          v28);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toasta"
                        "ctivationeventargs.cpp",
          (const char *)(unsigned int)v14,
          v28);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastact"
                      "ivationeventargs.cpp",
        (const char *)(unsigned int)v11,
        v28);
    }
    WindowsDeleteString(string);
LABEL_23:
    string = 0;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x67,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastactivat"
                  "ioneventargs.cpp",
    (const char *)(unsigned int)v4,
    v28);
  return v5;
}

```

## disassembly

```asm
0x18002e190  mov     [rsp-8+arg_10], rbx
0x18002e195  mov     [rsp-8+arg_18], rsi
0x18002e19a  push    rbp
0x18002e19b  push    rdi
0x18002e19c  push    r14
0x18002e19e  lea     rbp, [rsp-47h]
0x18002e1a3  sub     rsp, 90h
0x18002e1aa  mov     rax, cs:__security_cookie
0x18002e1b1  xor     rax, rsp
0x18002e1b4  mov     [rbp+57h+var_20], rax
0x18002e1b8  mov     rsi, rcx
0x18002e1bb  mov     rdi, rdx
0x18002e1be  add     rcx, 0FFFFFFFFFFFFFF18h; this
0x18002e1c5  call    ?MarshalObjectToPropertySet@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithViewIdBase::MarshalObjectToPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x18002e1ca  xor     r14d, r14d
0x18002e1cd  mov     ebx, eax
0x18002e1cf  test    eax, eax
0x18002e1d1  jns     short loc_18002E1EF
0x18002e1d3  mov     rcx, [rbp+5Fh]; this
0x18002e1d7  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e1de  mov     r9d, eax; char *
0x18002e1e1  lea     edx, [r14+67h]; void *
0x18002e1e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e1ea  jmp     loc_18002E452
0x18002e1ef  mov     rax, [rdi]
0x18002e1f2  lea     rcx, [rbp+57h+var_50]
0x18002e1f6  mov     [rbp+57h+var_50], r14
0x18002e1fa  mov     [rbp+57h+var_48], r14
0x18002e1fe  mov     rbx, [rax]
0x18002e201  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e206  lea     r8, [rbp+57h+var_50]
0x18002e20a  mov     rcx, rdi
0x18002e20d  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18002e214  mov     rax, rbx
0x18002e217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e21c  mov     ebx, eax
0x18002e21e  test    eax, eax
0x18002e220  jns     short loc_18002E229
0x18002e222  mov     edx, 6Ch ; 'l'
0x18002e227  jmp     short loc_18002E25F
0x18002e229  mov     r9d, 20h ; ' '; unsigned int
0x18002e22f  mov     [rbp+57h+var_28], r14
0x18002e233  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18002e23a  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002e23e  lea     r8d, [r9+1]; unsigned int
0x18002e242  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e247  mov     rcx, [rbp+57h+var_28]
0x18002e24b  lea     rdx, [rbp+57h+var_48]
0x18002e24f  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18002e254  mov     ebx, eax
0x18002e256  test    eax, eax
0x18002e258  jns     short loc_18002E277
0x18002e25a  mov     edx, 6Dh ; 'm'; void *
0x18002e25f  mov     rcx, [rbp+5Fh]; this
0x18002e263  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e26a  mov     r9d, eax; char *
0x18002e26d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e272  jmp     loc_18002E440
0x18002e277  lea     rdi, [rsi-8]
0x18002e27b  mov     [rbp+57h+string], r14
0x18002e27f  mov     rax, [rdi]
0x18002e282  xor     ecx, ecx; string
0x18002e284  mov     rbx, [rax+30h]
0x18002e288  call    cs:__imp_WindowsDeleteString
0x18002e28e  lea     rdx, [rbp+57h+string]
0x18002e292  mov     [rbp+57h+string], r14
0x18002e296  mov     rcx, rdi
0x18002e299  mov     rax, rbx
0x18002e29c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2a1  mov     ebx, eax
0x18002e2a3  test    eax, eax
0x18002e2a5  jns     short loc_18002E2CE
0x18002e2a7  mov     rcx, [rbp+5Fh]; this
0x18002e2ab  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e2b2  mov     r9d, eax; char *
0x18002e2b5  mov     edx, 71h ; 'q'; void *
0x18002e2ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e2bf  mov     rcx, [rbp+57h+string]; string
0x18002e2c3  call    cs:__imp_WindowsDeleteString
0x18002e2c9  jmp     loc_18002E43C
0x18002e2ce  mov     rax, [rdi]
0x18002e2d1  lea     rcx, [rbp+57h+var_60]
0x18002e2d5  mov     [rbp+57h+var_60], r14
0x18002e2d9  mov     rbx, [rax+38h]
0x18002e2dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e2e2  lea     rdx, [rbp+57h+var_60]
0x18002e2e6  mov     rcx, rdi
0x18002e2e9  mov     rax, rbx
0x18002e2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2f1  mov     ebx, eax
0x18002e2f3  test    eax, eax
0x18002e2f5  jns     short loc_18002E31A
0x18002e2f7  mov     rcx, [rbp+5Fh]; this
0x18002e2fb  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e302  mov     r9d, eax; char *
0x18002e305  mov     edx, 74h ; 't'; void *
0x18002e30a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e30f  lea     rcx, [rbp+57h+var_60]
0x18002e313  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e318  jmp     short loc_18002E2BF
0x18002e31a  mov     rdi, [rbp+57h+var_48]
0x18002e31e  lea     rcx, [rbp+57h+var_58]
0x18002e322  mov     [rbp+57h+var_58], r14
0x18002e326  mov     rax, [rdi]
0x18002e329  mov     rbx, [rax+90h]
0x18002e330  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e335  mov     rdx, [rbp+57h+string]
0x18002e339  lea     r8, [rbp+57h+var_58]
0x18002e33d  mov     rcx, rdi
0x18002e340  mov     rax, rbx
0x18002e343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e348  mov     ebx, eax
0x18002e34a  test    eax, eax
0x18002e34c  jns     short loc_18002E371
0x18002e34e  mov     edx, 78h ; 'x'; void *
0x18002e353  mov     rcx, [rbp+5Fh]; this
0x18002e357  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e35e  mov     r9d, eax; char *
0x18002e361  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e366  lea     rcx, [rbp+57h+var_58]
0x18002e36a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e36f  jmp     short loc_18002E30F
0x18002e371  mov     rsi, [rbp+57h+var_50]
0x18002e375  lea     rdx, aArguments_0; "Arguments"
0x18002e37c  mov     rbx, [rbp+57h+var_58]
0x18002e380  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002e384  mov     [rbp+57h+var_70], r14b
0x18002e388  mov     r9d, 9; unsigned int
0x18002e38e  mov     rax, [rsi]
0x18002e391  mov     [rbp+57h+var_28], r14
0x18002e395  lea     r8d, [r9+1]; unsigned int
0x18002e399  mov     rdi, [rax+50h]
0x18002e39d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e3a2  mov     rdx, [rbp+57h+var_28]
0x18002e3a6  lea     r9, [rbp+57h+var_70]
0x18002e3aa  mov     r8, rbx
0x18002e3ad  mov     rcx, rsi
0x18002e3b0  mov     rax, rdi
0x18002e3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3b8  mov     ebx, eax
0x18002e3ba  test    eax, eax
0x18002e3bc  jns     short loc_18002E3C5
0x18002e3be  mov     edx, 7Ah ; 'z'
0x18002e3c3  jmp     short loc_18002E353
0x18002e3c5  mov     rbx, [rbp+57h+var_60]
0x18002e3c9  test    rbx, rbx
0x18002e3cc  jz      short loc_18002E41D
0x18002e3ce  mov     rsi, [rbp+57h+var_50]
0x18002e3d2  lea     rdx, aUserinput; "UserInput"
0x18002e3d9  mov     r9d, 9; unsigned int
0x18002e3df  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002e3e3  mov     rax, [rsi]
0x18002e3e6  lea     r8d, [r9+1]; unsigned int
0x18002e3ea  mov     [rbp+57h+var_28], r14
0x18002e3ee  mov     rdi, [rax+50h]
0x18002e3f2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e3f7  mov     rdx, [rbp+57h+var_28]
0x18002e3fb  lea     r9, [rbp+57h+var_70]
0x18002e3ff  mov     r8, rbx
0x18002e402  mov     rcx, rsi
0x18002e405  mov     rax, rdi
0x18002e408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e40d  mov     ebx, eax
0x18002e40f  test    eax, eax
0x18002e411  jns     short loc_18002E41D
0x18002e413  mov     edx, 7Eh ; '~'
0x18002e418  jmp     loc_18002E353
0x18002e41d  lea     rcx, [rbp+57h+var_58]
0x18002e421  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e426  lea     rcx, [rbp+57h+var_60]
0x18002e42a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e42f  mov     rcx, [rbp+57h+string]; string
0x18002e433  call    cs:__imp_WindowsDeleteString
0x18002e439  mov     ebx, r14d
0x18002e43c  mov     [rbp+57h+string], r14
0x18002e440  lea     rcx, [rbp+57h+var_48]
0x18002e444  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e449  lea     rcx, [rbp+57h+var_50]
0x18002e44d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e452  mov     eax, ebx
0x18002e454  mov     rcx, [rbp+57h+var_20]
0x18002e458  xor     rcx, rsp; StackCookie
0x18002e45b  call    __security_check_cookie
0x18002e460  lea     r11, [rsp+0A0h+var_10]
0x18002e468  mov     rbx, [r11+30h]
0x18002e46c  mov     rsi, [r11+38h]
0x18002e470  mov     rsp, r11
0x18002e473  pop     r14
0x18002e475  pop     rdi
0x18002e476  pop     rbp
0x18002e477  retn
```
