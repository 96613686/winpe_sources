# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::AppInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::AppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::AppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::AppInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::AppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::AppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::AppInfo *>,0> * *)

- ea: `0x18002bb9c`
- end: `0x18002be48`
- name: `??$CreateExternalObjectVector@VAppInfo@ApplicationModel@Windows@@V?$AgileVector@PEAVAppInfo@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVAppInfo@ApplicationModel@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVAppInfo@ApplicationModel@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppInfo@ApplicationModel@Windows@@U?$DefaultEqualityPredicate@PEAVAppInfo@ApplicationModel@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVAppInfo@ApplicationModel@Windows@@@5673@$0A@@1234@@Z`
- size: `684`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002a284`
- `0x18002abec`
- `0x18002b7a8`
- `0x18002d920`

## callees

- `0x1800049bc`
- `0x180023044`
- `0x18002bb9c`
- `0x18008a030`
- `0x1800a6468`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002bdf9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002be0c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002be1f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002be32`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002bdf9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002be0c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002be1f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002be32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bbef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bc28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bc61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bcf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bbef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bc28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bc61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bcf7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002bd15`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002bd15`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::ApplicationModel::AppInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::ApplicationModel::AppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::ApplicationModel::AppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::AppInfo *>,0>>(
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
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // rax
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Au);
  v4 = v3 - 1;
  if ( v3 > 0x4A )
    v4 = 74;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.ApplicationModel.AppInfo>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Eu);
  v7 = v6 - 1;
  if ( v6 > 0x4E )
    v7 = 78;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.ApplicationModel.AppInfo>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Cu);
  v10 = v9 - 1;
  if ( v9 > 0x4C )
    v10 = 76;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.ApplicationModel.AppInfo>",
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
  v23 = GUID_cf7f59b3_6a09_4de8_a6c0_5792d56880d1;
  v24 = GUID_d1e8852e_d987_5357_a3ab_7e9b7168cbea;
  v25 = GUID_8246ed12_33e8_52b3_a5c5_19779de9999e;
  v26 = GUID_63d0bffe_0e34_55b3_83d5_314caff2b137;
  v27 = GUID_69cec62c_41eb_5d69_a475_29ee22323dd8;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v35 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v34, &v35);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v35, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    return (unsigned int)ActivationFactory;
  }
  v21 = 0;
  v14 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v22, &v21);
  if ( ActivationFactory < 0 )
  {
    v15 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return (unsigned int)ActivationFactory;
  }
  v18 = v21;
  v21 = 0;
  *a2 = v18;
  v19 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18002bb9c  mov     [rsp-8+arg_0], rbx
0x18002bba1  mov     [rsp-8+arg_10], rdi
0x18002bba6  push    rbp
0x18002bba7  lea     rbp, [rsp-30h]
0x18002bbac  sub     rsp, 130h
0x18002bbb3  mov     rax, cs:__security_cookie
0x18002bbba  xor     rax, rsp
0x18002bbbd  mov     [rbp+30h+var_10], rax
0x18002bbc1  mov     rdi, rdx
0x18002bbc4  mov     [rbp+30h+string], 0
0x18002bbcc  mov     ebx, 4Ah ; 'J'
0x18002bbd1  mov     ecx, ebx; unsigned int
0x18002bbd3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002bbd8  lea     edx, [rax-1]
0x18002bbdb  cmp     eax, ebx
0x18002bbdd  cmova   edx, ebx; length
0x18002bbe0  lea     r9, [rbp+30h+string]; string
0x18002bbe4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002bbe8  lea     rcx, aWindowsFoundat_7; "Windows.Foundation.Collections.IVector`"...
0x18002bbef  call    cs:__imp_WindowsCreateStringReference
0x18002bbf5  test    eax, eax
0x18002bbf7  js      loc_18002BDED
0x18002bbfd  mov     [rbp+30h+var_58], 0
0x18002bc05  mov     ebx, 4Eh ; 'N'
0x18002bc0a  mov     ecx, ebx; unsigned int
0x18002bc0c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002bc11  lea     edx, [rax-1]
0x18002bc14  cmp     eax, ebx
0x18002bc16  cmova   edx, ebx; length
0x18002bc19  lea     r9, [rbp+30h+var_58]; string
0x18002bc1d  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002bc21  lea     rcx, aWindowsFoundat_25; "Windows.Foundation.Collections.IVectorV"...
0x18002bc28  call    cs:__imp_WindowsCreateStringReference
0x18002bc2e  test    eax, eax
0x18002bc30  js      loc_18002BE00
0x18002bc36  mov     [rbp+30h+var_38], 0
0x18002bc3e  mov     ebx, 4Ch ; 'L'
0x18002bc43  mov     ecx, ebx; unsigned int
0x18002bc45  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002bc4a  lea     edx, [rax-1]
0x18002bc4d  cmp     eax, ebx
0x18002bc4f  cmova   edx, ebx; length
0x18002bc52  lea     r9, [rbp+30h+var_38]; string
0x18002bc56  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002bc5a  lea     rcx, aWindowsFoundat_51; "Windows.Foundation.Collections.IIterato"...
0x18002bc61  call    cs:__imp_WindowsCreateStringReference
0x18002bc67  test    eax, eax
0x18002bc69  js      loc_18002BE13
0x18002bc6f  mov     rax, [rbp+30h+string]
0x18002bc73  mov     [rsp+130h+var_100], rax
0x18002bc78  mov     rax, [rbp+30h+var_58]
0x18002bc7c  mov     [rsp+130h+var_F8], rax
0x18002bc81  mov     rax, [rbp+30h+var_38]
0x18002bc85  mov     [rsp+130h+var_F0], rax
0x18002bc8a  movups  xmm0, xmmword ptr cs:_GUID_cf7f59b3_6a09_4de8_a6c0_5792d56880d1.Data1
0x18002bc91  movdqu  [rsp+130h+var_E8], xmm0
0x18002bc97  movups  xmm1, xmmword ptr cs:_GUID_d1e8852e_d987_5357_a3ab_7e9b7168cbea.Data1
0x18002bc9e  movdqu  [rsp+130h+var_D8], xmm1
0x18002bca4  movups  xmm0, xmmword ptr cs:_GUID_8246ed12_33e8_52b3_a5c5_19779de9999e.Data1
0x18002bcab  movdqu  [rsp+130h+var_C8], xmm0
0x18002bcb1  movups  xmm1, xmmword ptr cs:_GUID_63d0bffe_0e34_55b3_83d5_314caff2b137.Data1
0x18002bcb8  movdqu  [rsp+130h+var_B8], xmm1
0x18002bcbe  movups  xmm0, xmmword ptr cs:_GUID_69cec62c_41eb_5d69_a475_29ee22323dd8.Data1
0x18002bcc5  movdqu  [rbp+30h+var_A8], xmm0
0x18002bcca  mov     [rsp+130h+var_110], 0
0x18002bcd3  lea     rcx, [rsp+130h+var_110]
0x18002bcd8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bcdd  mov     [rbp+30h+var_18], 0
0x18002bce5  lea     r9, [rbp+30h+var_18]; string
0x18002bce9  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002bced  lea     edx, [rbx-20h]; length
0x18002bcf0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002bcf7  call    cs:__imp_WindowsCreateStringReference
0x18002bcfd  test    eax, eax
0x18002bcff  js      loc_18002BE26
0x18002bd05  lea     r8, [rsp+130h+var_110]
0x18002bd0a  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002bd11  mov     rcx, [rbp+30h+var_18]
0x18002bd15  call    cs:__imp_RoGetActivationFactory
0x18002bd1b  mov     ebx, eax
0x18002bd1d  test    eax, eax
0x18002bd1f  js      loc_18002BE39
0x18002bd25  mov     [rsp+130h+var_108], 0
0x18002bd2e  mov     rbx, [rsp+130h+var_110]
0x18002bd33  lea     rcx, [rsp+130h+var_108]
0x18002bd38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bd3d  lea     r8, [rsp+130h+var_108]
0x18002bd42  lea     rdx, [rsp+130h+var_100]
0x18002bd47  mov     rcx, rbx
0x18002bd4a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18002bd4f  mov     ebx, eax
0x18002bd51  test    eax, eax
0x18002bd53  jns     short loc_18002BDB8
0x18002bd55  mov     rcx, [rsp+130h+var_108]
0x18002bd5a  test    rcx, rcx
0x18002bd5d  jz      short loc_18002BD75
0x18002bd5f  mov     [rsp+130h+var_108], 0
0x18002bd68  mov     rdx, [rcx]
0x18002bd6b  mov     rax, [rdx+10h]
0x18002bd6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd74  nop
0x18002bd75  mov     rcx, [rsp+130h+var_110]
0x18002bd7a  test    rcx, rcx
0x18002bd7d  jz      short loc_18002BD95
0x18002bd7f  mov     [rsp+130h+var_110], 0
0x18002bd88  mov     rax, [rcx]
0x18002bd8b  mov     rax, [rax+10h]
0x18002bd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd94  nop
0x18002bd95  mov     eax, ebx
0x18002bd97  mov     rcx, [rbp+30h+var_10]
0x18002bd9b  xor     rcx, rsp; StackCookie
0x18002bd9e  call    __security_check_cookie
0x18002bda3  lea     r11, [rsp+130h+var_s0]
0x18002bdab  mov     rbx, [r11+10h]
0x18002bdaf  mov     rdi, [r11+20h]
0x18002bdb3  mov     rsp, r11
0x18002bdb6  pop     rbp
0x18002bdb7  retn
0x18002bdb8  mov     rax, [rsp+130h+var_108]
0x18002bdbd  mov     [rsp+130h+var_108], 0
0x18002bdc6  mov     [rdi], rax
0x18002bdc9  mov     rcx, [rsp+130h+var_110]
0x18002bdce  test    rcx, rcx
0x18002bdd1  jz      short loc_18002BDE9
0x18002bdd3  mov     [rsp+130h+var_110], 0
0x18002bddc  mov     rax, [rcx]
0x18002bddf  mov     rax, [rax+10h]
0x18002bde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bde8  nop
0x18002bde9  xor     eax, eax
0x18002bdeb  jmp     short loc_18002BD97
0x18002bded  xor     r9d, r9d; lpArguments
0x18002bdf0  xor     r8d, r8d; nNumberOfArguments
0x18002bdf3  lea     edx, [r9+1]; dwExceptionFlags
0x18002bdf7  mov     ecx, eax; dwExceptionCode
0x18002bdf9  call    cs:__imp_RaiseException
0x18002bdff  int     3; Trap to Debugger
0x18002be00  xor     r9d, r9d; lpArguments
0x18002be03  xor     r8d, r8d; nNumberOfArguments
0x18002be06  lea     edx, [r9+1]; dwExceptionFlags
0x18002be0a  mov     ecx, eax; dwExceptionCode
0x18002be0c  call    cs:__imp_RaiseException
0x18002be12  int     3; Trap to Debugger
0x18002be13  xor     r9d, r9d; lpArguments
0x18002be16  xor     r8d, r8d; nNumberOfArguments
0x18002be19  lea     edx, [r9+1]; dwExceptionFlags
0x18002be1d  mov     ecx, eax; dwExceptionCode
0x18002be1f  call    cs:__imp_RaiseException
0x18002be25  int     3; Trap to Debugger
0x18002be26  xor     r9d, r9d; lpArguments
0x18002be29  xor     r8d, r8d; nNumberOfArguments
0x18002be2c  lea     edx, [r9+1]; dwExceptionFlags
0x18002be30  mov     ecx, eax; dwExceptionCode
0x18002be32  call    cs:__imp_RaiseException
0x18002be38  int     3; Trap to Debugger
0x18002be39  lea     rcx, [rsp+130h+var_110]
0x18002be3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002be43  jmp     loc_18002BD95
```
