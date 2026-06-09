# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0> * *)

- ea: `0x1800295b8`
- end: `0x180029843`
- name: `??$CreateExternalObjectVector@VAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@V?$AgileVector@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `651`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029184`

## callees

- `0x1800049bc`
- `0x180023044`
- `0x1800295b8`
- `0x18008a030`
- `0x1800a6468`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029620`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029667`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800296ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029755`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029620`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029667`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800296ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002960b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002973f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002960b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002973f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002976c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002976c`

## string_xrefs

- `0x180029604`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>`
- `0x180029692`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>`
- `0x18002964b`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0>>(
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
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v21[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v22; // [rsp+48h] [rbp-B8h]
  GUID v23; // [rsp+58h] [rbp-A8h]
  GUID v24; // [rsp+68h] [rbp-98h]
  GUID v25; // [rsp+78h] [rbp-88h]
  GUID v26; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v29; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v30; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v31; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v32; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v33; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v34; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x64u);
  v4 = v3 - 1;
  if ( v3 > 0x64 )
    v4 = 100;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x68u);
  v7 = v6 - 1;
  if ( v6 > 0x68 )
    v7 = 104;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x66u);
  v10 = v9 - 1;
  if ( v9 > 0x66 )
    v10 = 102;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>",
          v10,
          &v31,
          &v32);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v21[0] = string;
  v21[1] = v30;
  v21[2] = v32;
  v22 = GUID_d814470d_0c54_4f90_9853_f51845a90be2;
  v23 = GUID_083e2667_5a27_5f40_bee2_e470c9902f4c;
  v24 = GUID_c338a4da_6bcb_54c1_aa44_9ee9087ca23b;
  v25 = GUID_f0990f7b_7ae4_5b95_af92_4c1e39dec69a;
  v26 = GUID_1cc0a786_0b43_5f29_9d0e_672c5a51616b;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v34 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v33, &v34);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v34, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    return (unsigned int)ActivationFactory;
  }
  v19 = 0;
  v15 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v15, v21, &v19);
  if ( ActivationFactory < 0 )
  {
    v16 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return (unsigned int)ActivationFactory;
  }
  v18 = v19;
  v19 = 0;
  *a2 = v18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x1800295b8  mov     [rsp-8+arg_0], rbx
0x1800295bd  mov     [rsp-8+arg_10], rdi
0x1800295c2  push    rbp
0x1800295c3  lea     rbp, [rsp-30h]
0x1800295c8  sub     rsp, 130h
0x1800295cf  mov     rax, cs:__security_cookie
0x1800295d6  xor     rax, rsp
0x1800295d9  mov     [rbp+30h+var_10], rax
0x1800295dd  mov     rdi, rdx
0x1800295e0  mov     [rbp+30h+string], 0
0x1800295e8  mov     ebx, 64h ; 'd'
0x1800295ed  mov     ecx, ebx; unsigned int
0x1800295ef  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800295f4  lea     edx, [rax-1]
0x1800295f7  cmp     eax, ebx
0x1800295f9  cmova   edx, ebx; length
0x1800295fc  lea     r9, [rbp+30h+string]; string
0x180029600  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180029604  lea     rcx, aWindowsFoundat_38; "Windows.Foundation.Collections.IVector`"...
0x18002960b  call    cs:__imp_WindowsCreateStringReference
0x180029611  test    eax, eax
0x180029613  jns     short loc_180029627
0x180029615  xor     r9d, r9d; lpArguments
0x180029618  xor     r8d, r8d; nNumberOfArguments
0x18002961b  lea     edx, [rbx-63h]; dwExceptionFlags
0x18002961e  mov     ecx, eax; dwExceptionCode
0x180029620  call    cs:__imp_RaiseException
0x180029626  int     3; Trap to Debugger
0x180029627  mov     [rbp+30h+var_58], 0
0x18002962f  mov     ebx, 68h ; 'h'
0x180029634  mov     ecx, ebx; unsigned int
0x180029636  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002963b  lea     edx, [rax-1]
0x18002963e  cmp     eax, ebx
0x180029640  cmova   edx, ebx; length
0x180029643  lea     r9, [rbp+30h+var_58]; string
0x180029647  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002964b  lea     rcx, aWindowsFoundat_17; "Windows.Foundation.Collections.IVectorV"...
0x180029652  call    cs:__imp_WindowsCreateStringReference
0x180029658  test    eax, eax
0x18002965a  jns     short loc_18002966E
0x18002965c  xor     r9d, r9d; lpArguments
0x18002965f  xor     r8d, r8d; nNumberOfArguments
0x180029662  lea     edx, [rbx-67h]; dwExceptionFlags
0x180029665  mov     ecx, eax; dwExceptionCode
0x180029667  call    cs:__imp_RaiseException
0x18002966d  int     3; Trap to Debugger
0x18002966e  mov     [rbp+30h+var_38], 0
0x180029676  mov     ebx, 66h ; 'f'
0x18002967b  mov     ecx, ebx; unsigned int
0x18002967d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180029682  lea     edx, [rax-1]
0x180029685  cmp     eax, ebx
0x180029687  cmova   edx, ebx; length
0x18002968a  lea     r9, [rbp+30h+var_38]; string
0x18002968e  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180029692  lea     rcx, aWindowsFoundat_4; "Windows.Foundation.Collections.IIterato"...
0x180029699  call    cs:__imp_WindowsCreateStringReference
0x18002969f  test    eax, eax
0x1800296a1  jns     short loc_1800296B5
0x1800296a3  xor     r9d, r9d; lpArguments
0x1800296a6  xor     r8d, r8d; nNumberOfArguments
0x1800296a9  lea     edx, [rbx-65h]; dwExceptionFlags
0x1800296ac  mov     ecx, eax; dwExceptionCode
0x1800296ae  call    cs:__imp_RaiseException
0x1800296b4  int     3; Trap to Debugger
0x1800296b5  mov     rax, [rbp+30h+string]
0x1800296b9  mov     [rsp+130h+var_100], rax
0x1800296be  mov     rax, [rbp+30h+var_58]
0x1800296c2  mov     [rsp+130h+var_F8], rax
0x1800296c7  mov     rax, [rbp+30h+var_38]
0x1800296cb  mov     [rsp+130h+var_F0], rax
0x1800296d0  movups  xmm0, xmmword ptr cs:_GUID_d814470d_0c54_4f90_9853_f51845a90be2.Data1
0x1800296d7  movdqu  [rsp+130h+var_E8], xmm0
0x1800296dd  movups  xmm1, xmmword ptr cs:_GUID_083e2667_5a27_5f40_bee2_e470c9902f4c.Data1
0x1800296e4  movdqu  [rsp+130h+var_D8], xmm1
0x1800296ea  movups  xmm0, xmmword ptr cs:_GUID_c338a4da_6bcb_54c1_aa44_9ee9087ca23b.Data1
0x1800296f1  movdqu  [rsp+130h+var_C8], xmm0
0x1800296f7  movups  xmm1, xmmword ptr cs:_GUID_f0990f7b_7ae4_5b95_af92_4c1e39dec69a.Data1
0x1800296fe  movdqu  [rsp+130h+var_B8], xmm1
0x180029704  movups  xmm0, xmmword ptr cs:_GUID_1cc0a786_0b43_5f29_9d0e_672c5a51616b.Data1
0x18002970b  movdqu  [rbp+30h+var_A8], xmm0
0x180029710  mov     [rsp+130h+var_108], 0
0x180029719  lea     rcx, [rsp+130h+var_108]
0x18002971e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029723  mov     [rbp+30h+var_18], 0
0x18002972b  lea     r9, [rbp+30h+var_18]; string
0x18002972f  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180029733  mov     edx, 2Ch ; ','; length
0x180029738  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002973f  call    cs:__imp_WindowsCreateStringReference
0x180029745  test    eax, eax
0x180029747  jns     short loc_18002975C
0x180029749  xor     r9d, r9d; lpArguments
0x18002974c  xor     r8d, r8d; nNumberOfArguments
0x18002974f  lea     edx, [r9+1]; dwExceptionFlags
0x180029753  mov     ecx, eax; dwExceptionCode
0x180029755  call    cs:__imp_RaiseException
0x18002975b  int     3; Trap to Debugger
0x18002975c  lea     r8, [rsp+130h+var_108]
0x180029761  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180029768  mov     rcx, [rbp+30h+var_18]
0x18002976c  call    cs:__imp_RoGetActivationFactory
0x180029772  mov     ebx, eax
0x180029774  test    eax, eax
0x180029776  jns     short loc_180029789
0x180029778  lea     rcx, [rsp+130h+var_108]
0x18002977d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029782  mov     eax, ebx
0x180029784  jmp     loc_180029822
0x180029789  mov     [rsp+130h+var_110], 0
0x180029792  mov     rbx, [rsp+130h+var_108]
0x180029797  lea     rcx, [rsp+130h+var_110]
0x18002979c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800297a1  lea     r8, [rsp+130h+var_110]
0x1800297a6  lea     rdx, [rsp+130h+var_100]
0x1800297ab  mov     rcx, rbx
0x1800297ae  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800297b3  mov     ebx, eax
0x1800297b5  test    eax, eax
0x1800297b7  jns     short loc_1800297FB
0x1800297b9  mov     rcx, [rsp+130h+var_110]
0x1800297be  test    rcx, rcx
0x1800297c1  jz      short loc_1800297D9
0x1800297c3  mov     [rsp+130h+var_110], 0
0x1800297cc  mov     rdx, [rcx]
0x1800297cf  mov     rax, [rdx+10h]
0x1800297d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297d8  nop
0x1800297d9  mov     rcx, [rsp+130h+var_108]
0x1800297de  test    rcx, rcx
0x1800297e1  jz      short loc_1800297F9
0x1800297e3  mov     [rsp+130h+var_108], 0
0x1800297ec  mov     rax, [rcx]
0x1800297ef  mov     rax, [rax+10h]
0x1800297f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297f8  nop
0x1800297f9  jmp     short loc_180029782
0x1800297fb  mov     rax, [rsp+130h+var_110]
0x180029800  mov     [rsp+130h+var_110], 0
0x180029809  mov     [rdi], rax
0x18002980c  lea     rcx, [rsp+130h+var_110]
0x180029811  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029816  lea     rcx, [rsp+130h+var_108]
0x18002981b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029820  xor     eax, eax
0x180029822  mov     rcx, [rbp+30h+var_10]
0x180029826  xor     rcx, rsp; StackCookie
0x180029829  call    __security_check_cookie
0x18002982e  lea     r11, [rsp+130h+var_s0]
0x180029836  mov     rbx, [r11+10h]
0x18002983a  mov     rdi, [r11+20h]
0x18002983e  mov     rsp, r11
0x180029841  pop     rbp
0x180029842  retn
```
