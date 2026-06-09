# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>> * *)

- ea: `0x1801c86cc`
- end: `0x1801c8939`
- name: `??$CreateExternalObjectVector@UIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@V?$Vector@PEAUIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@@4785@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUIVirtualDesktop@Multitasking@ComposableShell@Internal@Windows@@@4785@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802327b0`
- `0x1804d8590`
- `0x1804d88c4`

## callees

- `0x1800134f8`
- `0x18005d940`
- `0x1801c86cc`
- `0x180356360`
- `0x1804c4500`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c8734`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c877b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c87c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c8869`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c8734`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c877b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c87c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801c8869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801c871f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801c8766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801c87ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801c8853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801c871f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801c8766`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801c87ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801c8853`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801c8880`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801c8880`

## string_xrefs

- `0x1801c87a6`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.ComposableShell.Multitasking.IVirtualDesktop>`
- `0x1801c8718`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.ComposableShell.Multitasking.IVirtualDesktop>`
- `0x1801c875f`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.ComposableShell.Multitasking.IVirtualDesktop>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ComposableShell::Multitasking::IVirtualDesktop *>>>(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // eax
  UINT32 v4; // edx
  HRESULT v5; // eax
  unsigned int v6; // eax
  UINT32 v7; // edx
  HRESULT v8; // eax
  unsigned int v9; // eax
  UINT32 v10; // edx
  HRESULT v11; // eax
  HRESULT v12; // eax
  int ActivationFactory; // ebx
  __int64 v14; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v21; // [rsp+48h] [rbp-B8h]
  GUID v22; // [rsp+58h] [rbp-A8h]
  GUID v23; // [rsp+68h] [rbp-98h]
  GUID v24; // [rsp+78h] [rbp-88h]
  GUID v25; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v28; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v29; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v30; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v31; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v32; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v33; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x67u);
  v4 = v3 - 1;
  if ( v3 > 0x67 )
    v4 = 103;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.ComposableShell.Multitasking.IVirtualDesktop>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Bu);
  v7 = v6 - 1;
  if ( v6 > 0x6B )
    v7 = 107;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.ComposableShell.Multitasking.IVirtualDesktop>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x69u);
  v10 = v9 - 1;
  if ( v9 > 0x69 )
    v10 = 105;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.ComposableShell.Multitasking.IVirtualDesktop>",
          v10,
          &v30,
          &v31);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v20[0] = string;
  v20[1] = v29;
  v20[2] = v31;
  v21 = GUID_c9f125fc_77cc_5ce0_87f4_f94b7a67d80b;
  v22 = GUID_ea11c0c6_873d_52c7_a499_e843b39d3ccd;
  v23 = GUID_90d0e58c_446b_5f4e_b49f_ddeedb0d1e74;
  v24 = GUID_53734c23_b216_575b_b5ea_a003bc18dcf8;
  v25 = GUID_7e597465_42fc_5296_93e3_ddd76b5208ac;
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v33 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v32, &v33);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v33, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v18);
  if ( ActivationFactory < 0 )
  {
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = 0;
  v16 = v18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x1801c86cc  mov     [rsp-8+arg_0], rbx
0x1801c86d1  mov     [rsp-8+arg_10], rdi
0x1801c86d6  push    rbp
0x1801c86d7  lea     rbp, [rsp-30h]
0x1801c86dc  sub     rsp, 130h
0x1801c86e3  mov     rax, cs:__security_cookie
0x1801c86ea  xor     rax, rsp
0x1801c86ed  mov     [rbp+30h+var_10], rax
0x1801c86f1  mov     rdi, rdx
0x1801c86f4  mov     [rbp+30h+string], 0
0x1801c86fc  mov     ebx, 67h ; 'g'
0x1801c8701  mov     ecx, ebx; unsigned int
0x1801c8703  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801c8708  lea     edx, [rax-1]
0x1801c870b  cmp     eax, ebx
0x1801c870d  cmova   edx, ebx; length
0x1801c8710  lea     r9, [rbp+30h+string]; string
0x1801c8714  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1801c8718  lea     rcx, aWindowsFoundat_17; "Windows.Foundation.Collections.IVector`"...
0x1801c871f  call    cs:__imp_WindowsCreateStringReference
0x1801c8725  test    eax, eax
0x1801c8727  jns     short loc_1801C873B
0x1801c8729  xor     r9d, r9d; lpArguments
0x1801c872c  xor     r8d, r8d; nNumberOfArguments
0x1801c872f  lea     edx, [rbx-66h]; dwExceptionFlags
0x1801c8732  mov     ecx, eax; dwExceptionCode
0x1801c8734  call    cs:__imp_RaiseException
0x1801c873a  int     3; Trap to Debugger
0x1801c873b  mov     [rbp+30h+var_58], 0
0x1801c8743  mov     ebx, 6Bh ; 'k'
0x1801c8748  mov     ecx, ebx; unsigned int
0x1801c874a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801c874f  lea     edx, [rax-1]
0x1801c8752  cmp     eax, ebx
0x1801c8754  cmova   edx, ebx; length
0x1801c8757  lea     r9, [rbp+30h+var_58]; string
0x1801c875b  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1801c875f  lea     rcx, aWindowsFoundat_16; "Windows.Foundation.Collections.IVectorV"...
0x1801c8766  call    cs:__imp_WindowsCreateStringReference
0x1801c876c  test    eax, eax
0x1801c876e  jns     short loc_1801C8782
0x1801c8770  xor     r9d, r9d; lpArguments
0x1801c8773  xor     r8d, r8d; nNumberOfArguments
0x1801c8776  lea     edx, [rbx-6Ah]; dwExceptionFlags
0x1801c8779  mov     ecx, eax; dwExceptionCode
0x1801c877b  call    cs:__imp_RaiseException
0x1801c8781  int     3; Trap to Debugger
0x1801c8782  mov     [rbp+30h+var_38], 0
0x1801c878a  mov     ebx, 69h ; 'i'
0x1801c878f  mov     ecx, ebx; unsigned int
0x1801c8791  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801c8796  lea     edx, [rax-1]
0x1801c8799  cmp     eax, ebx
0x1801c879b  cmova   edx, ebx; length
0x1801c879e  lea     r9, [rbp+30h+var_38]; string
0x1801c87a2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1801c87a6  lea     rcx, aWindowsFoundat_4; "Windows.Foundation.Collections.IIterato"...
0x1801c87ad  call    cs:__imp_WindowsCreateStringReference
0x1801c87b3  test    eax, eax
0x1801c87b5  jns     short loc_1801C87C9
0x1801c87b7  xor     r9d, r9d; lpArguments
0x1801c87ba  xor     r8d, r8d; nNumberOfArguments
0x1801c87bd  lea     edx, [rbx-68h]; dwExceptionFlags
0x1801c87c0  mov     ecx, eax; dwExceptionCode
0x1801c87c2  call    cs:__imp_RaiseException
0x1801c87c8  int     3; Trap to Debugger
0x1801c87c9  mov     rax, [rbp+30h+string]
0x1801c87cd  mov     [rsp+130h+var_100], rax
0x1801c87d2  mov     rax, [rbp+30h+var_58]
0x1801c87d6  mov     [rsp+130h+var_F8], rax
0x1801c87db  mov     rax, [rbp+30h+var_38]
0x1801c87df  mov     [rsp+130h+var_F0], rax
0x1801c87e4  movups  xmm0, xmmword ptr cs:_GUID_c9f125fc_77cc_5ce0_87f4_f94b7a67d80b.Data1
0x1801c87eb  movdqu  [rsp+130h+var_E8], xmm0
0x1801c87f1  movups  xmm1, xmmword ptr cs:_GUID_ea11c0c6_873d_52c7_a499_e843b39d3ccd.Data1
0x1801c87f8  movdqu  [rsp+130h+var_D8], xmm1
0x1801c87fe  movups  xmm0, xmmword ptr cs:_GUID_90d0e58c_446b_5f4e_b49f_ddeedb0d1e74.Data1
0x1801c8805  movdqu  [rsp+130h+var_C8], xmm0
0x1801c880b  movups  xmm1, xmmword ptr cs:_GUID_53734c23_b216_575b_b5ea_a003bc18dcf8.Data1
0x1801c8812  movdqu  [rsp+130h+var_B8], xmm1
0x1801c8818  movups  xmm0, xmmword ptr cs:_GUID_7e597465_42fc_5296_93e3_ddd76b5208ac.Data1
0x1801c881f  movdqu  [rbp+30h+var_A8], xmm0
0x1801c8824  mov     [rsp+130h+var_110], 0
0x1801c882d  lea     rcx, [rsp+130h+var_110]
0x1801c8832  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c8837  mov     [rbp+30h+var_18], 0
0x1801c883f  lea     r9, [rbp+30h+var_18]; string
0x1801c8843  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1801c8847  mov     edx, 2Ch ; ','; length
0x1801c884c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1801c8853  call    cs:__imp_WindowsCreateStringReference
0x1801c8859  test    eax, eax
0x1801c885b  jns     short loc_1801C8870
0x1801c885d  xor     r9d, r9d; lpArguments
0x1801c8860  xor     r8d, r8d; nNumberOfArguments
0x1801c8863  lea     edx, [r9+1]; dwExceptionFlags
0x1801c8867  mov     ecx, eax; dwExceptionCode
0x1801c8869  call    cs:__imp_RaiseException
0x1801c886f  int     3; Trap to Debugger
0x1801c8870  lea     r8, [rsp+130h+var_110]
0x1801c8875  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1801c887c  mov     rcx, [rbp+30h+var_18]
0x1801c8880  call    cs:__imp_RoGetActivationFactory
0x1801c8886  mov     ebx, eax
0x1801c8888  test    eax, eax
0x1801c888a  jns     short loc_1801C88B0
0x1801c888c  mov     rcx, [rsp+130h+var_110]
0x1801c8891  test    rcx, rcx
0x1801c8894  jz      short loc_1801C88AC
0x1801c8896  mov     [rsp+130h+var_110], 0
0x1801c889f  mov     rdx, [rcx]
0x1801c88a2  mov     rax, [rdx+10h]
0x1801c88a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c88ab  nop
0x1801c88ac  mov     eax, ebx
0x1801c88ae  jmp     short loc_1801C8918
0x1801c88b0  mov     [rsp+130h+var_108], 0
0x1801c88b9  mov     rbx, [rsp+130h+var_110]
0x1801c88be  lea     rcx, [rsp+130h+var_108]
0x1801c88c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c88c8  lea     r8, [rsp+130h+var_108]
0x1801c88cd  lea     rdx, [rsp+130h+var_100]
0x1801c88d2  mov     rcx, rbx
0x1801c88d5  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x1801c88da  mov     ebx, eax
0x1801c88dc  lea     rcx, [rsp+130h+var_108]
0x1801c88e1  test    eax, eax
0x1801c88e3  jns     short loc_1801C88F6
0x1801c88e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c88ea  lea     rcx, [rsp+130h+var_110]
0x1801c88ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c88f4  jmp     short loc_1801C88AC
0x1801c88f6  mov     rax, [rsp+130h+var_108]
0x1801c88fb  mov     [rsp+130h+var_108], 0
0x1801c8904  mov     [rdi], rax
0x1801c8907  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c890c  lea     rcx, [rsp+130h+var_110]
0x1801c8911  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801c8916  xor     eax, eax
0x1801c8918  mov     rcx, [rbp+30h+var_10]
0x1801c891c  xor     rcx, rsp; StackCookie
0x1801c891f  call    __security_check_cookie
0x1801c8924  lea     r11, [rsp+130h+var_s0]
0x1801c892c  mov     rbx, [r11+10h]
0x1801c8930  mov     rdi, [r11+20h]
0x1801c8934  mov     rsp, r11
0x1801c8937  pop     rbp
0x1801c8938  retn
```
