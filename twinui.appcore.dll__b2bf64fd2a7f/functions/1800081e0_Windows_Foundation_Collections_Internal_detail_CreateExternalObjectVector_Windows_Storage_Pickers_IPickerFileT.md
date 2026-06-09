# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::Pickers::IPickerFileType,Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Pickers::IPickerFileType *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Pickers::IPickerFileType *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Pickers::IPickerFileType *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Pickers::IPickerFileType *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Pickers::IPickerFileType *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Pickers::IPickerFileType *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Pickers::IPickerFileType *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Pickers::IPickerFileType *>> * *)

- ea: `0x1800081e0`
- end: `0x1800083e9`
- name: `??$CreateExternalObjectVector@UIPickerFileType@Pickers@Storage@Windows@@V?$Vector@PEAUIPickerFileType@Pickers@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIPickerFileType@Pickers@Storage@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPickerFileType@Pickers@Storage@Windows@@@6784@U?$DefaultVectorOptions@PEAUIPickerFileType@Pickers@Storage@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIPickerFileType@Pickers@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIPickerFileType@Pickers@Storage@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPickerFileType@Pickers@Storage@Windows@@@6784@U?$DefaultVectorOptions@PEAUIPickerFileType@Pickers@Storage@Windows@@@6784@@1234@@Z`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180024220`

## callees

- `0x180003d24`
- `0x1800081e0`
- `0x1800083f0`
- `0x18000843c`
- `0x18002b1b0`
- `0x18004c484`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008319`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008319`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008304`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008330`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180008330`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::Pickers::IPickerFileType,Windows::Foundation::Collections::Internal::Vector<Windows::Storage::Pickers::IPickerFileType *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::Pickers::IPickerFileType *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::Pickers::IPickerFileType *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Storage::Pickers::IPickerFileType *>>>(
        __int64 a1,
        _QWORD *a2)
{
  UINT32 v3; // eax
  UINT32 v4; // eax
  UINT32 v5; // eax
  HRESULT v6; // eax
  int ActivationFactory; // ebx
  __int64 v8; // rcx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v14[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v15; // [rsp+48h] [rbp-B8h]
  GUID v16; // [rsp+58h] [rbp-A8h]
  GUID v17; // [rsp+68h] [rbp-98h]
  GUID v18; // [rsp+78h] [rbp-88h]
  GUID v19; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v22; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v23; // [rsp+D8h] [rbp-28h]
  HSTRING_HEADER v24; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-8h]
  HSTRING_HEADER v26; // [rsp+100h] [rbp+0h] BYREF
  __int64 v27; // [rsp+118h] [rbp+18h]

  v23 = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x51u);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v22,
    L"Windows.Foundation.Collections.IVector`1<Windows.Storage.Pickers.IPickerFileType>",
    v3,
    0x51u);
  v25 = 0;
  v4 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x55u);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v24,
    L"Windows.Foundation.Collections.IVectorView`1<Windows.Storage.Pickers.IPickerFileType>",
    v4,
    0x55u);
  v27 = 0;
  v5 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x53u);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v26,
    L"Windows.Foundation.Collections.IIterator`1<Windows.Storage.Pickers.IPickerFileType>",
    v5,
    0x53u);
  v14[0] = v23;
  v14[1] = v25;
  v14[2] = v27;
  v15 = GUID_c72ecb37_09e8_460e_9485_baa88e6d5752;
  v16 = GUID_35cc9ef9_7693_5446_816e_8f54751fdc73;
  v17 = GUID_6229d054_ea09_5209_92f7_9d36cd94e36b;
  v18 = GUID_58d1dedc_7fc2_5e64_a5b9_0fa43f4f3023;
  v19 = GUID_8063fc5f_83d0_53ef_ad6b_b173e1dc0356;
  v13 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v13);
  if ( ActivationFactory < 0 )
  {
    v8 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return (unsigned int)ActivationFactory;
  }
  v12 = 0;
  v10 = v13;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v10, v14, &v12);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    return (unsigned int)ActivationFactory;
  }
  v11 = v12;
  v12 = 0;
  *a2 = v11;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  return 0;
}

```

## disassembly

```asm
0x1800081e0  mov     [rsp-8+arg_0], rbx
0x1800081e5  mov     [rsp-8+arg_10], rdi
0x1800081ea  push    rbp
0x1800081eb  lea     rbp, [rsp-30h]
0x1800081f0  sub     rsp, 130h
0x1800081f7  mov     rax, cs:__security_cookie
0x1800081fe  xor     rax, rsp
0x180008201  mov     [rbp+30h+var_10], rax
0x180008205  mov     rdi, rdx
0x180008208  mov     [rbp+30h+var_58], 0
0x180008210  mov     ebx, 51h ; 'Q'
0x180008215  mov     ecx, ebx; unsigned int
0x180008217  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000821c  mov     r9d, ebx; unsigned int
0x18000821f  mov     r8d, eax; unsigned int
0x180008222  lea     rdx, aWindowsFoundat_10; "Windows.Foundation.Collections.IVector`"...
0x180008229  lea     rcx, [rbp+30h+var_70]; hstringHeader
0x18000822d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180008232  mov     [rbp+30h+var_38], 0
0x18000823a  mov     ebx, 55h ; 'U'
0x18000823f  mov     ecx, ebx; unsigned int
0x180008241  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180008246  mov     r9d, ebx; unsigned int
0x180008249  mov     r8d, eax; unsigned int
0x18000824c  lea     rdx, aWindowsFoundat_8; "Windows.Foundation.Collections.IVectorV"...
0x180008253  lea     rcx, [rbp+30h+var_50]; hstringHeader
0x180008257  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000825c  mov     [rbp+30h+var_18], 0
0x180008264  mov     ebx, 53h ; 'S'
0x180008269  mov     ecx, ebx; unsigned int
0x18000826b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180008270  mov     r9d, ebx; unsigned int
0x180008273  mov     r8d, eax; unsigned int
0x180008276  lea     rdx, aWindowsFoundat_12; "Windows.Foundation.Collections.IIterato"...
0x18000827d  lea     rcx, [rbp+30h+var_30]; hstringHeader
0x180008281  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180008286  mov     rax, [rbp+30h+var_58]
0x18000828a  mov     [rsp+130h+var_100], rax
0x18000828f  mov     rax, [rbp+30h+var_38]
0x180008293  mov     [rsp+130h+var_F8], rax
0x180008298  mov     rax, [rbp+30h+var_18]
0x18000829c  mov     [rsp+130h+var_F0], rax
0x1800082a1  movups  xmm0, xmmword ptr cs:_GUID_c72ecb37_09e8_460e_9485_baa88e6d5752.Data1
0x1800082a8  movdqu  [rsp+130h+var_E8], xmm0
0x1800082ae  movups  xmm1, xmmword ptr cs:_GUID_35cc9ef9_7693_5446_816e_8f54751fdc73.Data1
0x1800082b5  movdqu  [rsp+130h+var_D8], xmm1
0x1800082bb  movups  xmm0, xmmword ptr cs:_GUID_6229d054_ea09_5209_92f7_9d36cd94e36b.Data1
0x1800082c2  movdqu  [rsp+130h+var_C8], xmm0
0x1800082c8  movups  xmm1, xmmword ptr cs:_GUID_58d1dedc_7fc2_5e64_a5b9_0fa43f4f3023.Data1
0x1800082cf  movdqu  [rsp+130h+var_B8], xmm1
0x1800082d5  movups  xmm0, xmmword ptr cs:_GUID_8063fc5f_83d0_53ef_ad6b_b173e1dc0356.Data1
0x1800082dc  movdqu  [rbp+30h+var_A8], xmm0
0x1800082e1  mov     [rsp+130h+var_108], 0
0x1800082ea  mov     [rbp+30h+string], 0
0x1800082f2  lea     r9, [rbp+30h+string]; string
0x1800082f6  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800082fa  lea     edx, [rbx-27h]; length
0x1800082fd  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180008304  call    cs:__imp_WindowsCreateStringReference
0x18000830a  test    eax, eax
0x18000830c  jns     short loc_180008320
0x18000830e  xor     r9d, r9d; lpArguments
0x180008311  xor     r8d, r8d; nNumberOfArguments
0x180008314  lea     edx, [rbx-52h]; dwExceptionFlags
0x180008317  mov     ecx, eax; dwExceptionCode
0x180008319  call    cs:__imp_RaiseException
0x18000831f  int     3; Trap to Debugger
0x180008320  lea     r8, [rsp+130h+var_108]
0x180008325  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18000832c  mov     rcx, [rbp+30h+string]
0x180008330  call    cs:__imp_RoGetActivationFactory
0x180008336  mov     ebx, eax
0x180008338  test    eax, eax
0x18000833a  jns     short loc_180008360
0x18000833c  mov     rcx, [rsp+130h+var_108]
0x180008341  test    rcx, rcx
0x180008344  jz      short loc_18000835C
0x180008346  mov     [rsp+130h+var_108], 0
0x18000834f  mov     rdx, [rcx]
0x180008352  mov     rax, [rdx+10h]
0x180008356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000835b  nop
0x18000835c  mov     eax, ebx
0x18000835e  jmp     short loc_1800083C8
0x180008360  mov     [rsp+130h+var_110], 0
0x180008369  mov     rbx, [rsp+130h+var_108]
0x18000836e  lea     rcx, [rsp+130h+var_110]
0x180008373  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180008378  lea     r8, [rsp+130h+var_110]
0x18000837d  lea     rdx, [rsp+130h+var_100]
0x180008382  mov     rcx, rbx
0x180008385  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18000838a  mov     ebx, eax
0x18000838c  lea     rcx, [rsp+130h+var_110]
0x180008391  test    eax, eax
0x180008393  jns     short loc_1800083A6
0x180008395  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000839a  lea     rcx, [rsp+130h+var_108]
0x18000839f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800083a4  jmp     short loc_18000835C
0x1800083a6  mov     rax, [rsp+130h+var_110]
0x1800083ab  mov     [rsp+130h+var_110], 0
0x1800083b4  mov     [rdi], rax
0x1800083b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800083bc  lea     rcx, [rsp+130h+var_108]
0x1800083c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800083c6  xor     eax, eax
0x1800083c8  mov     rcx, [rbp+30h+var_10]
0x1800083cc  xor     rcx, rsp; StackCookie
0x1800083cf  call    __security_check_cookie
0x1800083d4  lea     r11, [rsp+130h+var_s0]
0x1800083dc  mov     rbx, [r11+10h]
0x1800083e0  mov     rdi, [r11+20h]
0x1800083e4  mov     rsp, r11
0x1800083e7  pop     rbp
0x1800083e8  retn
```
