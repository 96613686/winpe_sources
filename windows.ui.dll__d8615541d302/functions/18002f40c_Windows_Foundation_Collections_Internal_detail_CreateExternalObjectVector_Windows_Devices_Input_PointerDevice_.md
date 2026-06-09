# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Devices::Input::PointerDevice,Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Input::PointerDevice *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Devices::Input::PointerDevice *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Input::PointerDevice *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Input::PointerDevice *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Input::PointerDevice *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Devices::Input::PointerDevice *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Input::PointerDevice *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Input::PointerDevice *>> * *)

- ea: `0x18002f40c`
- end: `0x18002f679`
- name: `??$CreateExternalObjectVector@VPointerDevice@Input@Devices@Windows@@V?$Vector@PEAVPointerDevice@Input@Devices@Windows@@U?$DefaultEqualityPredicate@PEAVPointerDevice@Input@Devices@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPointerDevice@Input@Devices@Windows@@@6784@U?$DefaultVectorOptions@PEAVPointerDevice@Input@Devices@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVPointerDevice@Input@Devices@Windows@@U?$DefaultEqualityPredicate@PEAVPointerDevice@Input@Devices@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPointerDevice@Input@Devices@Windows@@@6784@U?$DefaultVectorOptions@PEAVPointerDevice@Input@Devices@Windows@@@6784@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800a7ed0`

## callees

- `0x1800038e0`
- `0x18002f40c`
- `0x18002fdc8`
- `0x180091a0c`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f474`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f4bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f502`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f5a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f474`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f4bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f502`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f5a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f45f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f4a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f4ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f45f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f4a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f4ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f593`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f5c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f5c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Devices::Input::PointerDevice,Windows::Foundation::Collections::Internal::Vector<Windows::Devices::Input::PointerDevice *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Devices::Input::PointerDevice *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Devices::Input::PointerDevice *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Devices::Input::PointerDevice *>>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Du);
  v4 = v3 - 1;
  if ( v3 > 0x4D )
    v4 = 77;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Devices.Input.PointerDevice>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x51u);
  v7 = v6 - 1;
  if ( v6 > 0x51 )
    v7 = 81;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Devices.Input.PointerDevice>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Fu);
  v10 = v9 - 1;
  if ( v9 > 0x4F )
    v10 = 79;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Devices.Input.PointerDevice>",
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
  v21 = GUID_93c9bafc_ebcb_467e_82c6_276feae36b5a;
  v22 = GUID_a7de34a0_53a0_51ac_a17d_074bb4e96334;
  v23 = GUID_cf5674f1_9808_5a2b_80b8_5684ed0ea816;
  v24 = GUID_ad26662c_845b_5c6d_aeaa_406f48c21ae9;
  v25 = GUID_de94641c_7960_5fcd_abe8_d6ba609ef7d3;
  v18 = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
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
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x18002f40c  mov     [rsp-8+arg_0], rbx
0x18002f411  mov     [rsp-8+arg_10], rdi
0x18002f416  push    rbp
0x18002f417  lea     rbp, [rsp-30h]
0x18002f41c  sub     rsp, 130h
0x18002f423  mov     rax, cs:__security_cookie
0x18002f42a  xor     rax, rsp
0x18002f42d  mov     [rbp+30h+var_10], rax
0x18002f431  mov     rdi, rdx
0x18002f434  mov     [rbp+30h+string], 0
0x18002f43c  mov     ebx, 4Dh ; 'M'
0x18002f441  mov     ecx, ebx; unsigned int
0x18002f443  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f448  lea     edx, [rax-1]
0x18002f44b  cmp     eax, ebx
0x18002f44d  cmova   edx, ebx; length
0x18002f450  lea     r9, [rbp+30h+string]; string
0x18002f454  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002f458  lea     rcx, sourceString; "Windows.Foundation.Collections.IVector`"...
0x18002f45f  call    cs:__imp_WindowsCreateStringReference
0x18002f465  test    eax, eax
0x18002f467  jns     short loc_18002F47B
0x18002f469  xor     r9d, r9d; lpArguments
0x18002f46c  xor     r8d, r8d; nNumberOfArguments
0x18002f46f  lea     edx, [rbx-4Ch]; dwExceptionFlags
0x18002f472  mov     ecx, eax; dwExceptionCode
0x18002f474  call    cs:__imp_RaiseException
0x18002f47a  int     3; Trap to Debugger
0x18002f47b  mov     [rbp+30h+var_58], 0
0x18002f483  mov     ebx, 51h ; 'Q'
0x18002f488  mov     ecx, ebx; unsigned int
0x18002f48a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f48f  lea     edx, [rax-1]
0x18002f492  cmp     eax, ebx
0x18002f494  cmova   edx, ebx; length
0x18002f497  lea     r9, [rbp+30h+var_58]; string
0x18002f49b  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002f49f  lea     rcx, aWindowsFoundat_2; "Windows.Foundation.Collections.IVectorV"...
0x18002f4a6  call    cs:__imp_WindowsCreateStringReference
0x18002f4ac  test    eax, eax
0x18002f4ae  jns     short loc_18002F4C2
0x18002f4b0  xor     r9d, r9d; lpArguments
0x18002f4b3  xor     r8d, r8d; nNumberOfArguments
0x18002f4b6  lea     edx, [rbx-50h]; dwExceptionFlags
0x18002f4b9  mov     ecx, eax; dwExceptionCode
0x18002f4bb  call    cs:__imp_RaiseException
0x18002f4c1  int     3; Trap to Debugger
0x18002f4c2  mov     [rbp+30h+var_38], 0
0x18002f4ca  mov     ebx, 4Fh ; 'O'
0x18002f4cf  mov     ecx, ebx; unsigned int
0x18002f4d1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f4d6  lea     edx, [rax-1]
0x18002f4d9  cmp     eax, ebx
0x18002f4db  cmova   edx, ebx; length
0x18002f4de  lea     r9, [rbp+30h+var_38]; string
0x18002f4e2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002f4e6  lea     rcx, aWindowsFoundat_18; "Windows.Foundation.Collections.IIterato"...
0x18002f4ed  call    cs:__imp_WindowsCreateStringReference
0x18002f4f3  test    eax, eax
0x18002f4f5  jns     short loc_18002F509
0x18002f4f7  xor     r9d, r9d; lpArguments
0x18002f4fa  xor     r8d, r8d; nNumberOfArguments
0x18002f4fd  lea     edx, [rbx-4Eh]; dwExceptionFlags
0x18002f500  mov     ecx, eax; dwExceptionCode
0x18002f502  call    cs:__imp_RaiseException
0x18002f508  int     3; Trap to Debugger
0x18002f509  mov     rax, [rbp+30h+string]
0x18002f50d  mov     [rsp+130h+var_100], rax
0x18002f512  mov     rax, [rbp+30h+var_58]
0x18002f516  mov     [rsp+130h+var_F8], rax
0x18002f51b  mov     rax, [rbp+30h+var_38]
0x18002f51f  mov     [rsp+130h+var_F0], rax
0x18002f524  movups  xmm0, xmmword ptr cs:_GUID_93c9bafc_ebcb_467e_82c6_276feae36b5a.Data1
0x18002f52b  movdqu  [rsp+130h+var_E8], xmm0
0x18002f531  movups  xmm1, xmmword ptr cs:_GUID_a7de34a0_53a0_51ac_a17d_074bb4e96334.Data1
0x18002f538  movdqu  [rsp+130h+var_D8], xmm1
0x18002f53e  movups  xmm0, xmmword ptr cs:_GUID_cf5674f1_9808_5a2b_80b8_5684ed0ea816.Data1
0x18002f545  movdqu  [rsp+130h+var_C8], xmm0
0x18002f54b  movups  xmm1, xmmword ptr cs:_GUID_ad26662c_845b_5c6d_aeaa_406f48c21ae9.Data1
0x18002f552  movdqu  [rsp+130h+var_B8], xmm1
0x18002f558  movups  xmm0, xmmword ptr cs:_GUID_de94641c_7960_5fcd_abe8_d6ba609ef7d3.Data1
0x18002f55f  movdqu  [rbp+30h+var_A8], xmm0
0x18002f564  mov     [rsp+130h+var_110], 0
0x18002f56d  lea     rcx, [rsp+130h+var_110]
0x18002f572  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002f577  mov     [rbp+30h+var_18], 0
0x18002f57f  lea     r9, [rbp+30h+var_18]; string
0x18002f583  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002f587  mov     edx, 2Ch ; ','; length
0x18002f58c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002f593  call    cs:__imp_WindowsCreateStringReference
0x18002f599  test    eax, eax
0x18002f59b  jns     short loc_18002F5B0
0x18002f59d  xor     r9d, r9d; lpArguments
0x18002f5a0  xor     r8d, r8d; nNumberOfArguments
0x18002f5a3  lea     edx, [r9+1]; dwExceptionFlags
0x18002f5a7  mov     ecx, eax; dwExceptionCode
0x18002f5a9  call    cs:__imp_RaiseException
0x18002f5af  int     3; Trap to Debugger
0x18002f5b0  lea     r8, [rsp+130h+var_110]
0x18002f5b5  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002f5bc  mov     rcx, [rbp+30h+var_18]
0x18002f5c0  call    cs:__imp_RoGetActivationFactory
0x18002f5c6  mov     ebx, eax
0x18002f5c8  test    eax, eax
0x18002f5ca  jns     short loc_18002F5F0
0x18002f5cc  mov     rcx, [rsp+130h+var_110]
0x18002f5d1  test    rcx, rcx
0x18002f5d4  jz      short loc_18002F5EC
0x18002f5d6  mov     [rsp+130h+var_110], 0
0x18002f5df  mov     rdx, [rcx]
0x18002f5e2  mov     rax, [rdx+10h]
0x18002f5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5eb  nop
0x18002f5ec  mov     eax, ebx
0x18002f5ee  jmp     short loc_18002F658
0x18002f5f0  mov     [rsp+130h+var_108], 0
0x18002f5f9  mov     rbx, [rsp+130h+var_110]
0x18002f5fe  lea     rcx, [rsp+130h+var_108]
0x18002f603  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002f608  lea     r8, [rsp+130h+var_108]
0x18002f60d  lea     rdx, [rsp+130h+var_100]
0x18002f612  mov     rcx, rbx
0x18002f615  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18002f61a  mov     ebx, eax
0x18002f61c  lea     rcx, [rsp+130h+var_108]
0x18002f621  test    eax, eax
0x18002f623  jns     short loc_18002F636
0x18002f625  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002f62a  lea     rcx, [rsp+130h+var_110]
0x18002f62f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002f634  jmp     short loc_18002F5EC
0x18002f636  mov     rax, [rsp+130h+var_108]
0x18002f63b  mov     [rsp+130h+var_108], 0
0x18002f644  mov     [rdi], rax
0x18002f647  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002f64c  lea     rcx, [rsp+130h+var_110]
0x18002f651  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002f656  xor     eax, eax
0x18002f658  mov     rcx, [rbp+30h+var_10]
0x18002f65c  xor     rcx, rsp; StackCookie
0x18002f65f  call    __security_check_cookie
0x18002f664  lea     r11, [rsp+130h+var_s0]
0x18002f66c  mov     rbx, [r11+10h]
0x18002f670  mov     rdi, [r11+20h]
0x18002f674  mov     rsp, r11
0x18002f677  pop     rbp
0x18002f678  retn
```
