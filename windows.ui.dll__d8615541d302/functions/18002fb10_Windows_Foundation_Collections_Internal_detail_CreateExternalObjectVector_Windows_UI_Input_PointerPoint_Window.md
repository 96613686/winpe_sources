# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::PointerPoint,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::PointerPoint *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::PointerPoint *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::PointerPoint *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::PointerPoint *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::PointerPoint *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::PointerPoint *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::PointerPoint *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::PointerPoint *>> * *)

- ea: `0x18002fb10`
- end: `0x18002fdc2`
- name: `??$CreateExternalObjectVector@VPointerPoint@Input@UI@Windows@@V?$Vector@PEAVPointerPoint@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVPointerPoint@Input@UI@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPointerPoint@Input@UI@Windows@@@6784@U?$DefaultVectorOptions@PEAVPointerPoint@Input@UI@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVPointerPoint@Input@UI@Windows@@U?$DefaultEqualityPredicate@PEAVPointerPoint@Input@UI@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPointerPoint@Input@UI@Windows@@@6784@U?$DefaultVectorOptions@PEAVPointerPoint@Input@UI@Windows@@@6784@@1234@@Z`
- size: `690`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002f6c0`
- `0x180031f04`

## callees

- `0x1800038e0`
- `0x18002fb10`
- `0x18002fdc8`
- `0x180091a0c`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fd82`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fd95`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fda8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fdbb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fd82`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fd95`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fda8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fdbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fb63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fb9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fbd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fc6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fb63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fb9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fbd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fc6b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002fc89`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002fc89`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Input::PointerPoint,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Input::PointerPoint *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Input::PointerPoint *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Input::PointerPoint *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Input::PointerPoint *>>>(
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
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v22[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v23; // [rsp+48h] [rbp-B8h]
  GUID v24; // [rsp+58h] [rbp-A8h]
  GUID v25; // [rsp+68h] [rbp-98h]
  GUID v26; // [rsp+78h] [rbp-88h]
  GUID v27; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v30; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v31; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v32; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v33; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v34; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v35; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x47u);
  v4 = v3 - 1;
  if ( v3 > 0x47 )
    v4 = 71;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.UI.Input.PointerPoint>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Bu);
  v7 = v6 - 1;
  if ( v6 > 0x4B )
    v7 = 75;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.UI.Input.PointerPoint>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x49u);
  v10 = v9 - 1;
  if ( v9 > 0x49 )
    v10 = 73;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.UI.Input.PointerPoint>",
          v10,
          &v32,
          &v33);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v22[0] = string;
  v22[1] = v31;
  v22[2] = v33;
  v23 = GUID_e995317d_7296_42d9_8233_c5be73b74a4a;
  v24 = GUID_dfa655cf_fde7_5048_b4bf_c909231b7edb;
  v25 = GUID_f0f57411_7786_5174_8752_4c5e834b6da2;
  v26 = GUID_f6f2cba6_7076_5b59_9631_f6ac32b57695;
  v27 = GUID_721fe01c_5ad4_5262_b078_3ab345105db8;
  v20 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
  v35 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v34, &v35);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18002FDC1LL);
  }
  ActivationFactory = RoGetActivationFactory(v35, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v20);
  if ( ActivationFactory < 0 )
  {
    v19 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)ActivationFactory;
  }
  v21 = 0;
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v20, v22, &v21);
  if ( ActivationFactory < 0 )
  {
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v14 = v21;
  v21 = 0;
  *a2 = v14;
  v15 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18002fb10  mov     [rsp-8+arg_0], rbx
0x18002fb15  mov     [rsp-8+arg_10], rdi
0x18002fb1a  push    rbp
0x18002fb1b  lea     rbp, [rsp-30h]
0x18002fb20  sub     rsp, 130h
0x18002fb27  mov     rax, cs:__security_cookie
0x18002fb2e  xor     rax, rsp
0x18002fb31  mov     [rbp+30h+var_10], rax
0x18002fb35  mov     rdi, rdx
0x18002fb38  mov     [rbp+30h+string], 0
0x18002fb40  mov     ebx, 47h ; 'G'
0x18002fb45  mov     ecx, ebx; unsigned int
0x18002fb47  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002fb4c  lea     edx, [rax-1]
0x18002fb4f  cmp     eax, ebx
0x18002fb51  cmova   edx, ebx; length
0x18002fb54  lea     r9, [rbp+30h+string]; string
0x18002fb58  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002fb5c  lea     rcx, aWindowsFoundat_5; "Windows.Foundation.Collections.IVector`"...
0x18002fb63  call    cs:__imp_WindowsCreateStringReference
0x18002fb69  test    eax, eax
0x18002fb6b  js      loc_18002FD76
0x18002fb71  mov     [rbp+30h+var_58], 0
0x18002fb79  mov     ebx, 4Bh ; 'K'
0x18002fb7e  mov     ecx, ebx; unsigned int
0x18002fb80  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002fb85  lea     edx, [rax-1]
0x18002fb88  cmp     eax, ebx
0x18002fb8a  cmova   edx, ebx; length
0x18002fb8d  lea     r9, [rbp+30h+var_58]; string
0x18002fb91  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002fb95  lea     rcx, aWindowsFoundat_21; "Windows.Foundation.Collections.IVectorV"...
0x18002fb9c  call    cs:__imp_WindowsCreateStringReference
0x18002fba2  test    eax, eax
0x18002fba4  js      loc_18002FD89
0x18002fbaa  mov     [rbp+30h+var_38], 0
0x18002fbb2  mov     ebx, 49h ; 'I'
0x18002fbb7  mov     ecx, ebx; unsigned int
0x18002fbb9  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002fbbe  lea     edx, [rax-1]
0x18002fbc1  cmp     eax, ebx
0x18002fbc3  cmova   edx, ebx; length
0x18002fbc6  lea     r9, [rbp+30h+var_38]; string
0x18002fbca  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002fbce  lea     rcx, aWindowsFoundat_17; "Windows.Foundation.Collections.IIterato"...
0x18002fbd5  call    cs:__imp_WindowsCreateStringReference
0x18002fbdb  test    eax, eax
0x18002fbdd  js      loc_18002FD9C
0x18002fbe3  mov     rax, [rbp+30h+string]
0x18002fbe7  mov     [rsp+130h+var_100], rax
0x18002fbec  mov     rax, [rbp+30h+var_58]
0x18002fbf0  mov     [rsp+130h+var_F8], rax
0x18002fbf5  mov     rax, [rbp+30h+var_38]
0x18002fbf9  mov     [rsp+130h+var_F0], rax
0x18002fbfe  movups  xmm0, xmmword ptr cs:_GUID_e995317d_7296_42d9_8233_c5be73b74a4a.Data1
0x18002fc05  movdqu  [rsp+130h+var_E8], xmm0
0x18002fc0b  movups  xmm1, xmmword ptr cs:_GUID_dfa655cf_fde7_5048_b4bf_c909231b7edb.Data1
0x18002fc12  movdqu  [rsp+130h+var_D8], xmm1
0x18002fc18  movups  xmm0, xmmword ptr cs:_GUID_f0f57411_7786_5174_8752_4c5e834b6da2.Data1
0x18002fc1f  movdqu  [rsp+130h+var_C8], xmm0
0x18002fc25  movups  xmm1, xmmword ptr cs:_GUID_f6f2cba6_7076_5b59_9631_f6ac32b57695.Data1
0x18002fc2c  movdqu  [rsp+130h+var_B8], xmm1
0x18002fc32  movups  xmm0, xmmword ptr cs:_GUID_721fe01c_5ad4_5262_b078_3ab345105db8.Data1
0x18002fc39  movdqu  [rbp+30h+var_A8], xmm0
0x18002fc3e  mov     [rsp+130h+var_110], 0
0x18002fc47  lea     rcx, [rsp+130h+var_110]
0x18002fc4c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002fc51  mov     [rbp+30h+var_18], 0
0x18002fc59  lea     r9, [rbp+30h+var_18]; string
0x18002fc5d  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002fc61  lea     edx, [rbx-1Dh]; length
0x18002fc64  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002fc6b  call    cs:__imp_WindowsCreateStringReference
0x18002fc71  test    eax, eax
0x18002fc73  js      loc_18002FDAF
0x18002fc79  lea     r8, [rsp+130h+var_110]
0x18002fc7e  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002fc85  mov     rcx, [rbp+30h+var_18]
0x18002fc89  call    cs:__imp_RoGetActivationFactory
0x18002fc8f  mov     ebx, eax
0x18002fc91  test    eax, eax
0x18002fc93  js      loc_18002FD54
0x18002fc99  mov     [rsp+130h+var_108], 0
0x18002fca2  lea     r8, [rsp+130h+var_108]
0x18002fca7  lea     rdx, [rsp+130h+var_100]
0x18002fcac  mov     rcx, [rsp+130h+var_110]
0x18002fcb1  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18002fcb6  mov     ebx, eax
0x18002fcb8  test    eax, eax
0x18002fcba  js      short loc_18002FD10
0x18002fcbc  mov     rax, [rsp+130h+var_108]
0x18002fcc1  mov     [rsp+130h+var_108], 0
0x18002fcca  mov     [rdi], rax
0x18002fccd  mov     rcx, [rsp+130h+var_110]
0x18002fcd2  test    rcx, rcx
0x18002fcd5  jz      short loc_18002FCED
0x18002fcd7  mov     [rsp+130h+var_110], 0
0x18002fce0  mov     rax, [rcx]
0x18002fce3  mov     rax, [rax+10h]
0x18002fce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcec  nop
0x18002fced  xor     eax, eax
0x18002fcef  mov     rcx, [rbp+30h+var_10]
0x18002fcf3  xor     rcx, rsp; StackCookie
0x18002fcf6  call    __security_check_cookie
0x18002fcfb  lea     r11, [rsp+130h+var_s0]
0x18002fd03  mov     rbx, [r11+10h]
0x18002fd07  mov     rdi, [r11+20h]
0x18002fd0b  mov     rsp, r11
0x18002fd0e  pop     rbp
0x18002fd0f  retn
0x18002fd10  mov     rcx, [rsp+130h+var_108]
0x18002fd15  test    rcx, rcx
0x18002fd18  jz      short loc_18002FD30
0x18002fd1a  mov     [rsp+130h+var_108], 0
0x18002fd23  mov     rdx, [rcx]
0x18002fd26  mov     rax, [rdx+10h]
0x18002fd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd2f  nop
0x18002fd30  mov     rcx, [rsp+130h+var_110]
0x18002fd35  test    rcx, rcx
0x18002fd38  jz      short loc_18002FD50
0x18002fd3a  mov     [rsp+130h+var_110], 0
0x18002fd43  mov     rax, [rcx]
0x18002fd46  mov     rax, [rax+10h]
0x18002fd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd4f  nop
0x18002fd50  mov     eax, ebx
0x18002fd52  jmp     short loc_18002FCEF
0x18002fd54  mov     rcx, [rsp+130h+var_110]
0x18002fd59  test    rcx, rcx
0x18002fd5c  jz      short loc_18002FD74
0x18002fd5e  mov     [rsp+130h+var_110], 0
0x18002fd67  mov     rdx, [rcx]
0x18002fd6a  mov     rax, [rdx+10h]
0x18002fd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd73  nop
0x18002fd74  jmp     short loc_18002FD50
0x18002fd76  xor     r9d, r9d; lpArguments
0x18002fd79  xor     r8d, r8d; nNumberOfArguments
0x18002fd7c  lea     edx, [r9+1]; dwExceptionFlags
0x18002fd80  mov     ecx, eax; dwExceptionCode
0x18002fd82  call    cs:__imp_RaiseException
0x18002fd88  int     3; Trap to Debugger
0x18002fd89  xor     r9d, r9d; lpArguments
0x18002fd8c  xor     r8d, r8d; nNumberOfArguments
0x18002fd8f  lea     edx, [r9+1]; dwExceptionFlags
0x18002fd93  mov     ecx, eax; dwExceptionCode
0x18002fd95  call    cs:__imp_RaiseException
0x18002fd9b  int     3; Trap to Debugger
0x18002fd9c  xor     r9d, r9d; lpArguments
0x18002fd9f  xor     r8d, r8d; nNumberOfArguments
0x18002fda2  lea     edx, [r9+1]; dwExceptionFlags
0x18002fda6  mov     ecx, eax; dwExceptionCode
0x18002fda8  call    cs:__imp_RaiseException
0x18002fdae  int     3; Trap to Debugger
0x18002fdaf  xor     r9d, r9d; lpArguments
0x18002fdb2  xor     r8d, r8d; nNumberOfArguments
0x18002fdb5  lea     edx, [r9+1]; dwExceptionFlags
0x18002fdb9  mov     ecx, eax; dwExceptionCode
0x18002fdbb  call    cs:__imp_RaiseException
```
