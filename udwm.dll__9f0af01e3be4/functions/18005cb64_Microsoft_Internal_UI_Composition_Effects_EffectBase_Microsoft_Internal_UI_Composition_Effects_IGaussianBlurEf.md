# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::UsePropertyFactory<_lambda_f0b0058c35c91142d2603957657c1ded_>(_lambda_f0b0058c35c91142d2603957657c1ded_ const &)

- ea: `0x18005cb64`
- end: `0x18005cc29`
- name: `??$UsePropertyFactory@V_lambda_f0b0058c35c91142d2603957657c1ded_@@@?$EffectBase@UIGaussianBlurEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@KAJAEBV_lambda_f0b0058c35c91142d2603957657c1ded_@@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005c7d0`

## callees

- `0x1800028f4`
- `0x18005cb64`
- `0x18005cc30`
- `0x180095130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005cbbc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005cbbc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005cbe1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005cbe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005cba6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005cba6`

## pseudocode

```c
__int64 __fastcall Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::UsePropertyFactory<_lambda_f0b0058c35c91142d2603957657c1ded_>(
        __int64 a1)
{
  HRESULT v2; // eax
  HSTRING v3; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER v7; // [rsp+28h] [rbp-30h] BYREF
  HSTRING v8; // [rsp+40h] [rbp-18h] BYREF

  v6 = 0;
  v8 = 0;
  v2 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &v7, &v8);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  v3 = v8;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v6);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v6);
  if ( ActivationFactory >= 0 )
    ActivationFactory = _lambda_f0b0058c35c91142d2603957657c1ded_::operator()(a1, v6);
  v8 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v6);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18005cb64  mov     r11, rsp
0x18005cb67  mov     [r11+10h], rbx
0x18005cb6b  push    rdi
0x18005cb6c  sub     rsp, 50h
0x18005cb70  mov     rax, cs:__security_cookie
0x18005cb77  xor     rax, rsp
0x18005cb7a  mov     [rsp+58h+var_10], rax
0x18005cb7f  mov     rdi, rcx
0x18005cb82  mov     qword ptr [r11-38h], 0
0x18005cb8a  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18005cb91  mov     qword ptr [r11-18h], 0
0x18005cb99  lea     r9, [r11-18h]; string
0x18005cb9d  mov     edx, 20h ; ' '; length
0x18005cba2  lea     r8, [r11-30h]; hstringHeader
0x18005cba6  call    cs:__imp_WindowsCreateStringReference
0x18005cbac  test    eax, eax
0x18005cbae  jns     short loc_18005CBC3
0x18005cbb0  xor     r9d, r9d; lpArguments
0x18005cbb3  xor     r8d, r8d; nNumberOfArguments
0x18005cbb6  mov     ecx, eax; dwExceptionCode
0x18005cbb8  lea     edx, [r9+1]; dwExceptionFlags
0x18005cbbc  call    cs:__imp_RaiseException
0x18005cbc2  int     3; Trap to Debugger
0x18005cbc3  mov     rbx, [rsp+58h+var_18]
0x18005cbc8  lea     rcx, [rsp+58h+var_38]
0x18005cbcd  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005cbd2  lea     r8, [rsp+58h+var_38]
0x18005cbd7  mov     rcx, rbx
0x18005cbda  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18005cbe1  call    cs:__imp_RoGetActivationFactory
0x18005cbe7  mov     ebx, eax
0x18005cbe9  test    eax, eax
0x18005cbeb  js      short loc_18005CBFC
0x18005cbed  mov     rdx, [rsp+58h+var_38]
0x18005cbf2  mov     rcx, rdi
0x18005cbf5  call    ??R_lambda_f0b0058c35c91142d2603957657c1ded_@@QEBA@PEAUIPropertyValueStatics@Foundation@Windows@@@Z; _lambda_f0b0058c35c91142d2603957657c1ded_::operator()(Windows::Foundation::IPropertyValueStatics *)
0x18005cbfa  mov     ebx, eax
0x18005cbfc  lea     rcx, [rsp+58h+var_38]
0x18005cc01  mov     [rsp+58h+var_18], 0
0x18005cc0a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005cc0f  mov     eax, ebx
0x18005cc11  mov     rcx, [rsp+58h+var_10]
0x18005cc16  xor     rcx, rsp; StackCookie
0x18005cc19  call    __security_check_cookie
0x18005cc1e  mov     rbx, [rsp+58h+arg_8]
0x18005cc23  add     rsp, 50h
0x18005cc27  pop     rdi
0x18005cc28  retn
```
