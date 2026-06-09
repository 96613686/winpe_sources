# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Feedback::FeedbackItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0> * *)

- ea: `0x18000d50c`
- end: `0x18000d778`
- name: `??$CreateExternalObjectVector@VFeedbackItem@Feedback@Internal@Windows@@V?$AgileVector@PEAVFeedbackItem@Feedback@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFeedbackItem@Feedback@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFeedbackItem@Feedback@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVFeedbackItem@Feedback@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFeedbackItem@Feedback@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFeedbackItem@Feedback@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003dc50`

## callees

- `0x18000b7e8`
- `0x18000d50c`
- `0x18000e028`
- `0x18013d330`
- `0x1801577f4`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d574`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d5bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d602`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d6a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d574`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d5bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d602`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d6a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d55f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d5a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d5ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d55f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d5a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d5ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d693`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d6c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d6c0`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Feedback::FeedbackItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Feedback::FeedbackItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Feedback::FeedbackItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Feedback::FeedbackItem *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x50u);
  v4 = v3 - 1;
  if ( v3 > 0x50 )
    v4 = 80;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.Feedback.FeedbackItem>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x54u);
  v7 = v6 - 1;
  if ( v6 > 0x54 )
    v7 = 84;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.Feedback.FeedbackItem>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x52u);
  v10 = v9 - 1;
  if ( v9 > 0x52 )
    v10 = 82;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.Feedback.FeedbackItem>",
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
  v21 = GUID_0de8dc84_5de4_4db8_ac8f_9fbbf602ba25;
  v22 = GUID_58754b09_ec64_5d7a_a00a_98c7920bd51e;
  v23 = GUID_268ffc22_2dd6_539a_bdad_b910cc444251;
  v24 = GUID_eb604eca_b1b5_50ae_9ef7_192df74a9618;
  v25 = GUID_3db085da_a6f1_5bf4_b6ee_0fd4172e2c8a;
  v18 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v18);
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
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x18000d50c  mov     [rsp-8+arg_0], rbx
0x18000d511  mov     [rsp-8+arg_10], rdi
0x18000d516  push    rbp
0x18000d517  lea     rbp, [rsp-30h]
0x18000d51c  sub     rsp, 130h
0x18000d523  mov     rax, cs:__security_cookie
0x18000d52a  xor     rax, rsp
0x18000d52d  mov     [rbp+30h+var_10], rax
0x18000d531  mov     rdi, rdx
0x18000d534  mov     [rbp+30h+string], 0
0x18000d53c  mov     ebx, 50h ; 'P'
0x18000d541  mov     ecx, ebx; unsigned int
0x18000d543  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000d548  lea     edx, [rax-1]
0x18000d54b  cmp     eax, ebx
0x18000d54d  cmova   edx, ebx; length
0x18000d550  lea     r9, [rbp+30h+string]; string
0x18000d554  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18000d558  lea     rcx, aWindowsFoundat_4; "Windows.Foundation.Collections.IVector`"...
0x18000d55f  call    cs:__imp_WindowsCreateStringReference
0x18000d565  test    eax, eax
0x18000d567  jns     short loc_18000D57B
0x18000d569  xor     r9d, r9d; lpArguments
0x18000d56c  xor     r8d, r8d; nNumberOfArguments
0x18000d56f  lea     edx, [rbx-4Fh]; dwExceptionFlags
0x18000d572  mov     ecx, eax; dwExceptionCode
0x18000d574  call    cs:__imp_RaiseException
0x18000d57a  int     3; Trap to Debugger
0x18000d57b  mov     [rbp+30h+var_58], 0
0x18000d583  mov     ebx, 54h ; 'T'
0x18000d588  mov     ecx, ebx; unsigned int
0x18000d58a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000d58f  lea     edx, [rax-1]
0x18000d592  cmp     eax, ebx
0x18000d594  cmova   edx, ebx; length
0x18000d597  lea     r9, [rbp+30h+var_58]; string
0x18000d59b  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18000d59f  lea     rcx, aWindowsFoundat_36; "Windows.Foundation.Collections.IVectorV"...
0x18000d5a6  call    cs:__imp_WindowsCreateStringReference
0x18000d5ac  test    eax, eax
0x18000d5ae  jns     short loc_18000D5C2
0x18000d5b0  xor     r9d, r9d; lpArguments
0x18000d5b3  xor     r8d, r8d; nNumberOfArguments
0x18000d5b6  lea     edx, [rbx-53h]; dwExceptionFlags
0x18000d5b9  mov     ecx, eax; dwExceptionCode
0x18000d5bb  call    cs:__imp_RaiseException
0x18000d5c1  int     3; Trap to Debugger
0x18000d5c2  mov     [rbp+30h+var_38], 0
0x18000d5ca  mov     ebx, 52h ; 'R'
0x18000d5cf  mov     ecx, ebx; unsigned int
0x18000d5d1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18000d5d6  lea     edx, [rax-1]
0x18000d5d9  cmp     eax, ebx
0x18000d5db  cmova   edx, ebx; length
0x18000d5de  lea     r9, [rbp+30h+var_38]; string
0x18000d5e2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18000d5e6  lea     rcx, aWindowsFoundat_44; "Windows.Foundation.Collections.IIterato"...
0x18000d5ed  call    cs:__imp_WindowsCreateStringReference
0x18000d5f3  test    eax, eax
0x18000d5f5  jns     short loc_18000D609
0x18000d5f7  xor     r9d, r9d; lpArguments
0x18000d5fa  xor     r8d, r8d; nNumberOfArguments
0x18000d5fd  lea     edx, [rbx-51h]; dwExceptionFlags
0x18000d600  mov     ecx, eax; dwExceptionCode
0x18000d602  call    cs:__imp_RaiseException
0x18000d608  int     3; Trap to Debugger
0x18000d609  mov     rax, [rbp+30h+string]
0x18000d60d  mov     [rsp+130h+var_100], rax
0x18000d612  mov     rax, [rbp+30h+var_58]
0x18000d616  mov     [rsp+130h+var_F8], rax
0x18000d61b  mov     rax, [rbp+30h+var_38]
0x18000d61f  mov     [rsp+130h+var_F0], rax
0x18000d624  movups  xmm0, xmmword ptr cs:_GUID_0de8dc84_5de4_4db8_ac8f_9fbbf602ba25.Data1
0x18000d62b  movdqu  [rsp+130h+var_E8], xmm0
0x18000d631  movups  xmm1, xmmword ptr cs:_GUID_58754b09_ec64_5d7a_a00a_98c7920bd51e.Data1
0x18000d638  movdqu  [rsp+130h+var_D8], xmm1
0x18000d63e  movups  xmm0, xmmword ptr cs:_GUID_268ffc22_2dd6_539a_bdad_b910cc444251.Data1
0x18000d645  movdqu  [rsp+130h+var_C8], xmm0
0x18000d64b  movups  xmm1, xmmword ptr cs:_GUID_eb604eca_b1b5_50ae_9ef7_192df74a9618.Data1
0x18000d652  movdqu  [rsp+130h+var_B8], xmm1
0x18000d658  movups  xmm0, xmmword ptr cs:_GUID_3db085da_a6f1_5bf4_b6ee_0fd4172e2c8a.Data1
0x18000d65f  movdqu  [rbp+30h+var_A8], xmm0
0x18000d664  mov     [rsp+130h+var_110], 0
0x18000d66d  lea     rcx, [rsp+130h+var_110]
0x18000d672  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d677  mov     [rbp+30h+var_18], 0
0x18000d67f  lea     r9, [rbp+30h+var_18]; string
0x18000d683  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18000d687  mov     edx, 2Ch ; ','; length
0x18000d68c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18000d693  call    cs:__imp_WindowsCreateStringReference
0x18000d699  test    eax, eax
0x18000d69b  jns     short loc_18000D6B0
0x18000d69d  xor     r9d, r9d; lpArguments
0x18000d6a0  xor     r8d, r8d; nNumberOfArguments
0x18000d6a3  lea     edx, [r9+1]; dwExceptionFlags
0x18000d6a7  mov     ecx, eax; dwExceptionCode
0x18000d6a9  call    cs:__imp_RaiseException
0x18000d6af  int     3; Trap to Debugger
0x18000d6b0  lea     r8, [rsp+130h+var_110]
0x18000d6b5  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18000d6bc  mov     rcx, [rbp+30h+var_18]
0x18000d6c0  call    cs:__imp_RoGetActivationFactory
0x18000d6c6  mov     ebx, eax
0x18000d6c8  test    eax, eax
0x18000d6ca  jns     short loc_18000D6EF
0x18000d6cc  mov     rcx, [rsp+130h+var_110]
0x18000d6d1  test    rcx, rcx
0x18000d6d4  jz      short loc_18000D6EB
0x18000d6d6  mov     [rsp+130h+var_110], 0
0x18000d6df  mov     rdx, [rcx]
0x18000d6e2  mov     rax, [rdx+10h]
0x18000d6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6eb  mov     eax, ebx
0x18000d6ed  jmp     short loc_18000D757
0x18000d6ef  mov     [rsp+130h+var_108], 0
0x18000d6f8  mov     rbx, [rsp+130h+var_110]
0x18000d6fd  lea     rcx, [rsp+130h+var_108]
0x18000d702  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d707  lea     r8, [rsp+130h+var_108]
0x18000d70c  lea     rdx, [rsp+130h+var_100]
0x18000d711  mov     rcx, rbx
0x18000d714  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18000d719  mov     ebx, eax
0x18000d71b  lea     rcx, [rsp+130h+var_108]
0x18000d720  test    eax, eax
0x18000d722  jns     short loc_18000D735
0x18000d724  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d729  lea     rcx, [rsp+130h+var_110]
0x18000d72e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d733  jmp     short loc_18000D6EB
0x18000d735  mov     rax, [rsp+130h+var_108]
0x18000d73a  mov     [rsp+130h+var_108], 0
0x18000d743  mov     [rdi], rax
0x18000d746  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d74b  lea     rcx, [rsp+130h+var_110]
0x18000d750  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18000d755  xor     eax, eax
0x18000d757  mov     rcx, [rbp+30h+var_10]
0x18000d75b  xor     rcx, rsp; StackCookie
0x18000d75e  call    __security_check_cookie
0x18000d763  lea     r11, [rsp+130h+var_s0]
0x18000d76b  mov     rbx, [r11+10h]
0x18000d76f  mov     rdi, [r11+20h]
0x18000d773  mov     rsp, r11
0x18000d776  pop     rbp
0x18000d777  retn
```
