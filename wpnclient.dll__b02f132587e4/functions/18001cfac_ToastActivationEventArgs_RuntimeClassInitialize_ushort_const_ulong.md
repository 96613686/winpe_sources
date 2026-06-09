# ToastActivationEventArgs::RuntimeClassInitialize(ushort const * *,ulong)

- ea: `0x18001cfac`
- end: `0x18001d343`
- name: `?RuntimeClassInitialize@ToastActivationEventArgs@@QEAAJPEAPEBGK@Z`
- size: `919`
- prototype: `__int64 __fastcall(ToastActivationEventArgs *__hidden this, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e7c4`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x18000dd20`
- `0x18000ef50`
- `0x18000f310`
- `0x180010040`
- `0x180013bc0`
- `0x180014160`
- `0x18001cfac`
- `0x18001ff00`
- `0x1800230c8`
- `0x18002e140`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d20c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d2bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d1fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d20c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d2bb`

## string_xrefs

- `0x18001d020`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18001d056`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18001d0a5`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18001d1d9`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18001d234`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18001d27c`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18001d2a1`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ToastActivationEventArgs::RuntimeClassInitialize(
        ToastActivationEventArgs *this,
        const unsigned __int16 **a2,
        unsigned int a3)
{
  unsigned int v6; // esi
  _QWORD *v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  _QWORD *v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  HSTRING v14; // rbx
  const unsigned __int16 *v15; // rdx
  int v16; // edi
  __int64 v17; // r13
  const unsigned __int16 *v18; // rdx
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, HSTRING, __int64 *); // rdi
  int v21; // eax
  HSTRING v22; // rdi
  int v23; // eax
  int v24; // esi
  HSTRING v25; // rcx
  int v27; // [rsp+20h] [rbp-49h]
  _BYTE v28[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v29; // [rsp+38h] [rbp-31h] BYREF
  __int64 v30; // [rsp+40h] [rbp-29h] BYREF
  __int64 v31; // [rsp+48h] [rbp-21h] BYREF
  HSTRING v32; // [rsp+50h] [rbp-19h] BYREF
  __int64 v33; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+60h] [rbp-9h] BYREF
  HSTRING v35[4]; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = 1;
  if ( !a3 || (a3 & 1) == 0 )
    return 2147942487LL;
  v33 = 0;
  v7 = (_QWORD *)Windows::Internal::StringReference::StringReference(v35, (const unsigned __int16 (*)[40])a2);
  v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
         *v7,
         &v33);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastactiv"
                    "ationeventargs.cpp",
      (const char *)(unsigned int)v8,
      v27);
    goto LABEL_43;
  }
  v29 = 0;
  v10 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
          &v33,
          &v29);
  v9 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastactiv"
                    "ationeventargs.cpp",
      (const char *)(unsigned int)v10,
      v27);
LABEL_7:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    goto LABEL_43;
  }
  v30 = 0;
  v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(v35, L"Windows.Foundation.PropertyValue");
  v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
          *v11,
          &v30);
  v9 = v12;
  if ( v12 < 0 )
  {
    v13 = 34;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastactiv"
                    "ationeventargs.cpp",
      (const char *)(unsigned int)v12,
      v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    goto LABEL_7;
  }
  v12 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((ToastActivationEventArgs *)((char *)this + 272));
  v9 = v12;
  if ( v12 < 0 )
  {
    v13 = 35;
    goto LABEL_10;
  }
  while ( 1 )
  {
    if ( v6 >= a3 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::operator=((char *)this + 280, &v33);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      return 0;
    }
    v14 = 0;
    v32 = 0;
    v15 = a2[v6];
    if ( !v15 )
    {
      v16 = -2147467261;
      goto LABEL_39;
    }
    v16 = Windows::Internal::String::_InitializeHelper((Windows::Internal::String *)&v32, v15);
    if ( v16 < 0 )
    {
      v14 = v32;
LABEL_39:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastact"
                      "ivationeventargs.cpp",
        (const char *)(unsigned int)v16,
        v27);
      if ( !v14 )
      {
LABEL_42:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
        v9 = v16;
        goto LABEL_43;
      }
      v25 = v14;
LABEL_41:
      WindowsDeleteString(v25);
      goto LABEL_42;
    }
    v17 = v6 + 1;
    string = 0;
    v18 = a2[v17];
    if ( !v18 )
    {
      v16 = -2147467261;
      goto LABEL_36;
    }
    v16 = Windows::Internal::String::_InitializeHelper((Windows::Internal::String *)&string, v18);
    if ( v16 < 0 )
    {
      v14 = string;
LABEL_36:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastact"
                      "ivationeventargs.cpp",
        (const char *)(unsigned int)v16,
        v27);
LABEL_30:
      if ( v14 )
        WindowsDeleteString(v14);
      v25 = v32;
      if ( !v32 )
        goto LABEL_42;
      goto LABEL_41;
    }
    v31 = 0;
    v19 = v30;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v30 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v14 = string;
    v21 = v20(v19, string, &v31);
    v16 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastact"
                      "ivationeventargs.cpp",
        (const char *)(unsigned int)v21,
        v27);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      goto LABEL_30;
    }
    v28[0] = 0;
    v22 = v32;
    v23 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v29 + 80LL))(v29, v32, v31, v28);
    v24 = v23;
    if ( v23 < 0 )
      break;
    v6 = v17 + 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    if ( v14 )
      WindowsDeleteString(v14);
    if ( v22 )
      WindowsDeleteString(v22);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastactivat"
                  "ioneventargs.cpp",
    (const char *)(unsigned int)v23,
    v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  if ( v14 )
    WindowsDeleteString(v14);
  if ( v22 )
    WindowsDeleteString(v22);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v9 = v24;
LABEL_43:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  return v9;
}

```

## disassembly

```asm
0x18001cfac  mov     [rsp-8+arg_10], rbx
0x18001cfb1  push    rbp
0x18001cfb2  push    rsi
0x18001cfb3  push    rdi
0x18001cfb4  push    r12
0x18001cfb6  push    r13
0x18001cfb8  push    r14
0x18001cfba  push    r15
0x18001cfbc  lea     rbp, [rsp-27h]
0x18001cfc1  sub     rsp, 90h
0x18001cfc8  mov     rax, cs:__security_cookie
0x18001cfcf  xor     rax, rsp
0x18001cfd2  mov     [rbp+57h+var_38], rax
0x18001cfd6  mov     r14d, r8d
0x18001cfd9  mov     r15, rdx
0x18001cfdc  mov     r12, rcx
0x18001cfdf  mov     esi, 1
0x18001cfe4  cmp     r8d, esi
0x18001cfe7  jb      loc_18001D317
0x18001cfed  test    sil, r14b
0x18001cff0  jz      loc_18001D317
0x18001cff6  mov     [rbp+57h+var_68], 0
0x18001cffe  lea     rcx, [rbp+57h+var_58]; string
0x18001d002  call    ??$?0$0CI@@StringReference@Internal@Windows@@QEAA@AEAY0CI@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[40])
0x18001d007  lea     rdx, [rbp+57h+var_68]
0x18001d00b  mov     rcx, [rax]
0x18001d00e  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18001d013  mov     ebx, eax
0x18001d015  test    eax, eax
0x18001d017  jns     short loc_18001D034
0x18001d019  mov     rcx, [rbp+5Fh]; this
0x18001d01d  mov     r9d, eax; char *
0x18001d020  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d027  lea     edx, [rsi+1Ah]; void *
0x18001d02a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d02f  jmp     loc_18001D2D7
0x18001d034  mov     [rbp+57h+var_88], 0
0x18001d03c  lea     rdx, [rbp+57h+var_88]
0x18001d040  lea     rcx, [rbp+57h+var_68]
0x18001d044  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18001d049  mov     ebx, eax
0x18001d04b  test    eax, eax
0x18001d04d  jns     short loc_18001D076
0x18001d04f  mov     rcx, [rbp+5Fh]; this
0x18001d053  mov     r9d, eax; char *
0x18001d056  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d05d  mov     edx, 1Eh; void *
0x18001d062  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d067  nop
0x18001d068  lea     rcx, [rbp+57h+var_88]
0x18001d06c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d071  jmp     loc_18001D2D7
0x18001d076  mov     [rbp+57h+var_80], 0
0x18001d07e  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18001d085  lea     rcx, [rbp+57h+var_58]; string
0x18001d089  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x18001d08e  lea     rdx, [rbp+57h+var_80]
0x18001d092  mov     rcx, [rax]
0x18001d095  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18001d09a  mov     ebx, eax
0x18001d09c  test    eax, eax
0x18001d09e  jns     short loc_18001D0C4
0x18001d0a0  mov     edx, 22h ; '"'; void *
0x18001d0a5  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d0ac  mov     r9d, eax; char *
0x18001d0af  mov     rcx, [rbp+5Fh]; this
0x18001d0b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0b8  nop
0x18001d0b9  lea     rcx, [rbp+57h+var_80]
0x18001d0bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d0c2  jmp     short loc_18001D068
0x18001d0c4  lea     rcx, [r12+110h]; this
0x18001d0cc  mov     rdx, r15
0x18001d0cf  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001d0d4  mov     ebx, eax
0x18001d0d6  test    eax, eax
0x18001d0d8  jns     short loc_18001D0E1
0x18001d0da  mov     edx, 23h ; '#'
0x18001d0df  jmp     short loc_18001D0A5
0x18001d0e1  cmp     esi, r14d
0x18001d0e4  jnb     loc_18001D2E4
0x18001d0ea  xor     ebx, ebx
0x18001d0ec  mov     [rbp+57h+var_70], rbx
0x18001d0f0  mov     eax, esi
0x18001d0f2  mov     rdx, [r15+rax*8]; unsigned __int16 *
0x18001d0f6  test    rdx, rdx
0x18001d0f9  jz      loc_18001D295
0x18001d0ff  lea     rcx, [rbp+57h+var_70]; this
0x18001d103  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18001d108  mov     edi, eax
0x18001d10a  test    eax, eax
0x18001d10c  js      loc_18001D28F
0x18001d112  lea     r13d, [rsi+1]
0x18001d116  mov     [rbp+57h+string], rbx
0x18001d11a  mov     rdx, [r15+r13*8]; unsigned __int16 *
0x18001d11e  test    rdx, rdx
0x18001d121  jz      loc_18001D270
0x18001d127  lea     rcx, [rbp+57h+string]; this
0x18001d12b  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18001d130  mov     edi, eax
0x18001d132  test    eax, eax
0x18001d134  js      loc_18001D26A
0x18001d13a  mov     [rbp+57h+var_78], rbx
0x18001d13e  mov     rsi, [rbp+57h+var_80]
0x18001d142  mov     rax, [rsi]
0x18001d145  mov     rdi, [rax+90h]
0x18001d14c  lea     rcx, [rbp+57h+var_78]
0x18001d150  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d155  lea     r8, [rbp+57h+var_78]
0x18001d159  mov     rbx, [rbp+57h+string]
0x18001d15d  mov     rdx, rbx
0x18001d160  mov     rcx, rsi
0x18001d163  mov     rax, rdi
0x18001d166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d16b  mov     edi, eax
0x18001d16d  test    eax, eax
0x18001d16f  js      loc_18001D22D
0x18001d175  mov     [rbp+57h+var_90], 0
0x18001d179  mov     rcx, [rbp+57h+var_88]
0x18001d17d  mov     rax, [rcx]
0x18001d180  lea     r9, [rbp+57h+var_90]
0x18001d184  mov     r8, [rbp+57h+var_78]
0x18001d188  mov     rdi, [rbp+57h+var_70]
0x18001d18c  mov     rdx, rdi
0x18001d18f  mov     rax, [rax+50h]
0x18001d193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d198  mov     esi, eax
0x18001d19a  test    eax, eax
0x18001d19c  js      short loc_18001D1D2
0x18001d19e  lea     esi, [r13+1]
0x18001d1a2  lea     rcx, [rbp+57h+var_78]
0x18001d1a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d1ab  nop
0x18001d1ac  test    rbx, rbx
0x18001d1af  jz      short loc_18001D1BB
0x18001d1b1  mov     rcx, rbx; string
0x18001d1b4  call    cs:__imp_WindowsDeleteString
0x18001d1ba  nop
0x18001d1bb  test    rdi, rdi
0x18001d1be  jz      loc_18001D0E1
0x18001d1c4  mov     rcx, rdi; string
0x18001d1c7  call    cs:__imp_WindowsDeleteString
0x18001d1cd  jmp     loc_18001D0E1
0x18001d1d2  mov     rcx, [rbp+5Fh]; this
0x18001d1d6  mov     r9d, esi; char *
0x18001d1d9  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d1e0  mov     edx, 31h ; '1'; void *
0x18001d1e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1ea  nop
0x18001d1eb  lea     rcx, [rbp+57h+var_78]
0x18001d1ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d1f4  nop
0x18001d1f5  test    rbx, rbx
0x18001d1f8  jz      short loc_18001D204
0x18001d1fa  mov     rcx, rbx; string
0x18001d1fd  call    cs:__imp_WindowsDeleteString
0x18001d203  nop
0x18001d204  test    rdi, rdi
0x18001d207  jz      short loc_18001D213
0x18001d209  mov     rcx, rdi; string
0x18001d20c  call    cs:__imp_WindowsDeleteString
0x18001d212  nop
0x18001d213  lea     rcx, [rbp+57h+var_80]
0x18001d217  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d21c  nop
0x18001d21d  lea     rcx, [rbp+57h+var_88]
0x18001d221  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d226  mov     ebx, esi
0x18001d228  jmp     loc_18001D2D7
0x18001d22d  mov     rcx, [rbp+5Fh]; this
0x18001d231  mov     r9d, edi; char *
0x18001d234  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d23b  mov     edx, 2Eh ; '.'; void *
0x18001d240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d245  nop
0x18001d246  lea     rcx, [rbp+57h+var_78]
0x18001d24a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d24f  nop
0x18001d250  test    rbx, rbx
0x18001d253  jz      short loc_18001D25F
0x18001d255  mov     rcx, rbx; string
0x18001d258  call    cs:__imp_WindowsDeleteString
0x18001d25e  nop
0x18001d25f  mov     rcx, [rbp+57h+var_70]
0x18001d263  test    rcx, rcx
0x18001d266  jz      short loc_18001D2C2
0x18001d268  jmp     short loc_18001D2BB
0x18001d26a  mov     rbx, [rbp+57h+string]
0x18001d26e  jmp     short loc_18001D275
0x18001d270  mov     edi, 80004003h
0x18001d275  mov     rcx, [rbp+5Fh]; this
0x18001d279  mov     r9d, edi; char *
0x18001d27c  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d283  mov     edx, 2Bh ; '+'; void *
0x18001d288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d28d  jmp     short loc_18001D250
0x18001d28f  mov     rbx, [rbp+57h+var_70]
0x18001d293  jmp     short loc_18001D29A
0x18001d295  mov     edi, 80004003h
0x18001d29a  mov     rcx, [rbp+5Fh]; this
0x18001d29e  mov     r9d, edi; char *
0x18001d2a1  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d2a8  mov     edx, 28h ; '('; void *
0x18001d2ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d2b2  nop
0x18001d2b3  test    rbx, rbx
0x18001d2b6  jz      short loc_18001D2C2
0x18001d2b8  mov     rcx, rbx; string
0x18001d2bb  call    cs:__imp_WindowsDeleteString
0x18001d2c1  nop
0x18001d2c2  lea     rcx, [rbp+57h+var_80]
0x18001d2c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d2cb  nop
0x18001d2cc  lea     rcx, [rbp+57h+var_88]
0x18001d2d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d2d5  mov     ebx, edi
0x18001d2d7  lea     rcx, [rbp+57h+var_68]
0x18001d2db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d2e0  mov     eax, ebx
0x18001d2e2  jmp     short loc_18001D31C
0x18001d2e4  lea     rcx, [r12+118h]
0x18001d2ec  lea     rdx, [rbp+57h+var_68]
0x18001d2f0  call    ??4?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> const &)
0x18001d2f5  nop
0x18001d2f6  lea     rcx, [rbp+57h+var_80]
0x18001d2fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d2ff  nop
0x18001d300  lea     rcx, [rbp+57h+var_88]
0x18001d304  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d309  nop
0x18001d30a  lea     rcx, [rbp+57h+var_68]
0x18001d30e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d313  xor     eax, eax
0x18001d315  jmp     short loc_18001D31C
0x18001d317  mov     eax, 80070057h
0x18001d31c  mov     rcx, [rbp+57h+var_38]
0x18001d320  xor     rcx, rsp; StackCookie
0x18001d323  call    __security_check_cookie
0x18001d328  mov     rbx, [rsp+0C0h+arg_10]
0x18001d330  add     rsp, 90h
0x18001d337  pop     r15
0x18001d339  pop     r14
0x18001d33b  pop     r13
0x18001d33d  pop     r12
0x18001d33f  pop     rdi
0x18001d340  pop     rsi
0x18001d341  pop     rbp
0x18001d342  retn
```
