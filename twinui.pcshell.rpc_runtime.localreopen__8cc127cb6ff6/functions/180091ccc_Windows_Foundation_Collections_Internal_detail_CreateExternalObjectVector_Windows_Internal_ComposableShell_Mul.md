# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ComposableShell::Multitasking::ISwitchItem,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>> * *)

- ea: `0x180091ccc`
- end: `0x180091f2a`
- name: `??$CreateExternalObjectVector@UISwitchItem@Multitasking@ComposableShell@Internal@Windows@@V?$Vector@PEAUISwitchItem@Multitasking@ComposableShell@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUISwitchItem@Multitasking@ComposableShell@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUISwitchItem@Multitasking@ComposableShell@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUISwitchItem@Multitasking@ComposableShell@Internal@Windows@@@4785@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUISwitchItem@Multitasking@ComposableShell@Internal@Windows@@U?$DefaultEqualityPredicate@PEAUISwitchItem@Multitasking@ComposableShell@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAUISwitchItem@Multitasking@ComposableShell@Internal@Windows@@@4785@U?$DefaultVectorOptions@PEAUISwitchItem@Multitasking@ComposableShell@Internal@Windows@@@4785@@1234@@Z`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800902f0`

## callees

- `0x1800134f8`
- `0x18005d940`
- `0x180091ccc`
- `0x180356360`
- `0x1804c4500`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091d34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091d7b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091dc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091e69`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091d34`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091d7b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091dc2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091e69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180091d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180091d66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180091dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180091e53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180091d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180091d66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180091dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180091e53`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180091e80`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180091e80`

## string_xrefs

- `0x180091d5f`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.ComposableShell.Multitasking.ISwitchItem>`
- `0x180091d18`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.ComposableShell.Multitasking.ISwitchItem>`
- `0x180091da6`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.ComposableShell.Multitasking.ISwitchItem>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::ComposableShell::Multitasking::ISwitchItem,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::ComposableShell::Multitasking::ISwitchItem *>>>(
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
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x63u);
  v4 = v3 - 1;
  if ( v3 > 0x63 )
    v4 = 99;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.ComposableShell.Multitasking.ISwitchItem>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x67u);
  v7 = v6 - 1;
  if ( v6 > 0x67 )
    v7 = 103;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.ComposableShell.Multitasking.ISwitchItem>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x65u);
  v10 = v9 - 1;
  if ( v9 > 0x65 )
    v10 = 101;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.ComposableShell.Multitasking.ISwitchItem>",
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
  v21 = GUID_76593595_88f6_40c9_bd90_6f1a79aec5b8;
  v22 = GUID_4b0267be_de4a_57da_85ca_0a73add50798;
  v23 = GUID_afff7760_2814_5538_87f4_be981e608328;
  v24 = GUID_257dba86_fcaf_5c4e_b3ba_b3a89d297d08;
  v25 = GUID_b5e44ad8_161c_50e1_83ba_9c535935f8db;
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
    goto LABEL_16;
  v19 = 0;
  v15 = v18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v15, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
LABEL_16:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v16 = v19;
  v19 = 0;
  *a2 = v16;
  v17 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180091ccc  mov     [rsp-8+arg_0], rbx
0x180091cd1  mov     [rsp-8+arg_10], rdi
0x180091cd6  push    rbp
0x180091cd7  lea     rbp, [rsp-30h]
0x180091cdc  sub     rsp, 130h
0x180091ce3  mov     rax, cs:__security_cookie
0x180091cea  xor     rax, rsp
0x180091ced  mov     [rbp+30h+var_10], rax
0x180091cf1  mov     rdi, rdx
0x180091cf4  mov     [rbp+30h+string], 0
0x180091cfc  mov     ebx, 63h ; 'c'
0x180091d01  mov     ecx, ebx; unsigned int
0x180091d03  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180091d08  lea     edx, [rax-1]
0x180091d0b  cmp     eax, ebx
0x180091d0d  cmova   edx, ebx; length
0x180091d10  lea     r9, [rbp+30h+string]; string
0x180091d14  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180091d18  lea     rcx, aWindowsFoundat_12; "Windows.Foundation.Collections.IVector`"...
0x180091d1f  call    cs:__imp_WindowsCreateStringReference
0x180091d25  test    eax, eax
0x180091d27  jns     short loc_180091D3B
0x180091d29  xor     r9d, r9d; lpArguments
0x180091d2c  xor     r8d, r8d; nNumberOfArguments
0x180091d2f  lea     edx, [rbx-62h]; dwExceptionFlags
0x180091d32  mov     ecx, eax; dwExceptionCode
0x180091d34  call    cs:__imp_RaiseException
0x180091d3a  int     3; Trap to Debugger
0x180091d3b  mov     [rbp+30h+var_58], 0
0x180091d43  mov     ebx, 67h ; 'g'
0x180091d48  mov     ecx, ebx; unsigned int
0x180091d4a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180091d4f  lea     edx, [rax-1]
0x180091d52  cmp     eax, ebx
0x180091d54  cmova   edx, ebx; length
0x180091d57  lea     r9, [rbp+30h+var_58]; string
0x180091d5b  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180091d5f  lea     rcx, aWindowsFoundat_41; "Windows.Foundation.Collections.IVectorV"...
0x180091d66  call    cs:__imp_WindowsCreateStringReference
0x180091d6c  test    eax, eax
0x180091d6e  jns     short loc_180091D82
0x180091d70  xor     r9d, r9d; lpArguments
0x180091d73  xor     r8d, r8d; nNumberOfArguments
0x180091d76  lea     edx, [rbx-66h]; dwExceptionFlags
0x180091d79  mov     ecx, eax; dwExceptionCode
0x180091d7b  call    cs:__imp_RaiseException
0x180091d81  int     3; Trap to Debugger
0x180091d82  mov     [rbp+30h+var_38], 0
0x180091d8a  mov     ebx, 65h ; 'e'
0x180091d8f  mov     ecx, ebx; unsigned int
0x180091d91  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180091d96  lea     edx, [rax-1]
0x180091d99  cmp     eax, ebx
0x180091d9b  cmova   edx, ebx; length
0x180091d9e  lea     r9, [rbp+30h+var_38]; string
0x180091da2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180091da6  lea     rcx, aWindowsFoundat_27; "Windows.Foundation.Collections.IIterato"...
0x180091dad  call    cs:__imp_WindowsCreateStringReference
0x180091db3  test    eax, eax
0x180091db5  jns     short loc_180091DC9
0x180091db7  xor     r9d, r9d; lpArguments
0x180091dba  xor     r8d, r8d; nNumberOfArguments
0x180091dbd  lea     edx, [rbx-64h]; dwExceptionFlags
0x180091dc0  mov     ecx, eax; dwExceptionCode
0x180091dc2  call    cs:__imp_RaiseException
0x180091dc8  int     3; Trap to Debugger
0x180091dc9  mov     rax, [rbp+30h+string]
0x180091dcd  mov     [rsp+130h+var_100], rax
0x180091dd2  mov     rax, [rbp+30h+var_58]
0x180091dd6  mov     [rsp+130h+var_F8], rax
0x180091ddb  mov     rax, [rbp+30h+var_38]
0x180091ddf  mov     [rsp+130h+var_F0], rax
0x180091de4  movups  xmm0, xmmword ptr cs:_GUID_76593595_88f6_40c9_bd90_6f1a79aec5b8.Data1
0x180091deb  movdqu  [rsp+130h+var_E8], xmm0
0x180091df1  movups  xmm1, xmmword ptr cs:_GUID_4b0267be_de4a_57da_85ca_0a73add50798.Data1
0x180091df8  movdqu  [rsp+130h+var_D8], xmm1
0x180091dfe  movups  xmm0, xmmword ptr cs:_GUID_afff7760_2814_5538_87f4_be981e608328.Data1
0x180091e05  movdqu  [rsp+130h+var_C8], xmm0
0x180091e0b  movups  xmm1, xmmword ptr cs:_GUID_257dba86_fcaf_5c4e_b3ba_b3a89d297d08.Data1
0x180091e12  movdqu  [rsp+130h+var_B8], xmm1
0x180091e18  movups  xmm0, xmmword ptr cs:_GUID_b5e44ad8_161c_50e1_83ba_9c535935f8db.Data1
0x180091e1f  movdqu  [rbp+30h+var_A8], xmm0
0x180091e24  mov     [rsp+130h+var_110], 0
0x180091e2d  lea     rcx, [rsp+130h+var_110]
0x180091e32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180091e37  mov     [rbp+30h+var_18], 0
0x180091e3f  lea     r9, [rbp+30h+var_18]; string
0x180091e43  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180091e47  mov     edx, 2Ch ; ','; length
0x180091e4c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180091e53  call    cs:__imp_WindowsCreateStringReference
0x180091e59  test    eax, eax
0x180091e5b  jns     short loc_180091E70
0x180091e5d  xor     r9d, r9d; lpArguments
0x180091e60  xor     r8d, r8d; nNumberOfArguments
0x180091e63  lea     edx, [r9+1]; dwExceptionFlags
0x180091e67  mov     ecx, eax; dwExceptionCode
0x180091e69  call    cs:__imp_RaiseException
0x180091e6f  int     3; Trap to Debugger
0x180091e70  lea     r8, [rsp+130h+var_110]
0x180091e75  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180091e7c  mov     rcx, [rbp+30h+var_18]
0x180091e80  call    cs:__imp_RoGetActivationFactory
0x180091e86  mov     ebx, eax
0x180091e88  test    eax, eax
0x180091e8a  jns     short loc_180091E9A
0x180091e8c  lea     rcx, [rsp+130h+var_110]
0x180091e91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180091e96  mov     eax, ebx
0x180091e98  jmp     short loc_180091F09
0x180091e9a  mov     [rsp+130h+var_108], 0
0x180091ea3  mov     rbx, [rsp+130h+var_110]
0x180091ea8  lea     rcx, [rsp+130h+var_108]
0x180091ead  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180091eb2  lea     r8, [rsp+130h+var_108]
0x180091eb7  lea     rdx, [rsp+130h+var_100]
0x180091ebc  mov     rcx, rbx
0x180091ebf  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x180091ec4  mov     ebx, eax
0x180091ec6  test    eax, eax
0x180091ec8  jns     short loc_180091ED6
0x180091eca  lea     rcx, [rsp+130h+var_108]
0x180091ecf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180091ed4  jmp     short loc_180091E8C
0x180091ed6  mov     rax, [rsp+130h+var_108]
0x180091edb  mov     [rsp+130h+var_108], 0
0x180091ee4  mov     [rdi], rax
0x180091ee7  mov     rcx, [rsp+130h+var_110]
0x180091eec  test    rcx, rcx
0x180091eef  jz      short loc_180091F07
0x180091ef1  mov     [rsp+130h+var_110], 0
0x180091efa  mov     rax, [rcx]
0x180091efd  mov     rax, [rax+10h]
0x180091f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091f06  nop
0x180091f07  xor     eax, eax
0x180091f09  mov     rcx, [rbp+30h+var_10]
0x180091f0d  xor     rcx, rsp; StackCookie
0x180091f10  call    __security_check_cookie
0x180091f15  lea     r11, [rsp+130h+var_s0]
0x180091f1d  mov     rbx, [r11+10h]
0x180091f21  mov     rdi, [r11+20h]
0x180091f25  mov     rsp, r11
0x180091f28  pop     rbp
0x180091f29  retn
```
