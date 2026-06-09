# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::User,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,0> * *)

- ea: `0x180018458`
- end: `0x1800186e0`
- name: `??$CreateExternalObjectVector@VUser@System@Windows@@V?$AgileVector@PEAVUser@System@Windows@@U?$DefaultEqualityPredicate@PEAVUser@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVUser@System@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVUser@System@Windows@@U?$DefaultEqualityPredicate@PEAVUser@System@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAVUser@System@Windows@@@5673@$0A@@1234@@Z`
- size: `648`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180048230`
- `0x180065730`
- `0x180069d4c`

## callees

- `0x18000ce48`
- `0x180018458`
- `0x1800189b0`
- `0x1800aac10`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018630`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018643`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018656`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018669`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018630`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018643`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018656`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800184ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800184e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001851d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800185b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800184ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800184e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001851d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800185b3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800185d1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800185d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::User,Windows::Foundation::Collections::Internal::AgileVector<Windows::System::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::User *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x3Du);
  v4 = v3 - 1;
  if ( v3 > 0x3D )
    v4 = 61;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.System.User>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x41u);
  v7 = v6 - 1;
  if ( v6 > 0x41 )
    v7 = 65;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.System.User>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x3Fu);
  v10 = v9 - 1;
  if ( v9 > 0x3F )
    v10 = 63;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.System.User>",
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
  v21 = GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b;
  v22 = GUID_8cb35b00_501c_5532_a664_38c9c429bb1a;
  v23 = GUID_8cbd762a_1222_5ee5_b745_489e7a42c6ec;
  v24 = GUID_d1bacd1f_0376_5823_8c29_1d45b9f4c191;
  v25 = GUID_326fe162_582b_5659_b8a4_68ff0f525745;
  v18 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x180018458  mov     [rsp-8+arg_0], rbx
0x18001845d  mov     [rsp-8+arg_10], rdi
0x180018462  push    rbp
0x180018463  lea     rbp, [rsp-30h]
0x180018468  sub     rsp, 130h
0x18001846f  mov     rax, cs:__security_cookie
0x180018476  xor     rax, rsp
0x180018479  mov     [rbp+30h+var_10], rax
0x18001847d  mov     rdi, rdx
0x180018480  mov     [rbp+30h+string], 0
0x180018488  mov     ebx, 3Dh ; '='
0x18001848d  mov     ecx, ebx; unsigned int
0x18001848f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180018494  lea     edx, [rax-1]
0x180018497  cmp     eax, ebx
0x180018499  cmova   edx, ebx; length
0x18001849c  lea     r9, [rbp+30h+string]; string
0x1800184a0  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800184a4  lea     rcx, aWindowsFoundat_8; "Windows.Foundation.Collections.IVector`"...
0x1800184ab  call    cs:__imp_WindowsCreateStringReference
0x1800184b1  test    eax, eax
0x1800184b3  js      loc_180018624
0x1800184b9  mov     [rbp+30h+var_58], 0
0x1800184c1  mov     ebx, 41h ; 'A'
0x1800184c6  mov     ecx, ebx; unsigned int
0x1800184c8  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800184cd  lea     edx, [rax-1]
0x1800184d0  cmp     eax, ebx
0x1800184d2  cmova   edx, ebx; length
0x1800184d5  lea     r9, [rbp+30h+var_58]; string
0x1800184d9  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800184dd  lea     rcx, aWindowsFoundat_5; "Windows.Foundation.Collections.IVectorV"...
0x1800184e4  call    cs:__imp_WindowsCreateStringReference
0x1800184ea  test    eax, eax
0x1800184ec  js      loc_180018637
0x1800184f2  mov     [rbp+30h+var_38], 0
0x1800184fa  mov     ebx, 3Fh ; '?'
0x1800184ff  mov     ecx, ebx; unsigned int
0x180018501  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180018506  lea     edx, [rax-1]
0x180018509  cmp     eax, ebx
0x18001850b  cmova   edx, ebx; length
0x18001850e  lea     r9, [rbp+30h+var_38]; string
0x180018512  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180018516  lea     rcx, aWindowsFoundat_16; "Windows.Foundation.Collections.IIterato"...
0x18001851d  call    cs:__imp_WindowsCreateStringReference
0x180018523  test    eax, eax
0x180018525  js      loc_18001864A
0x18001852b  mov     rax, [rbp+30h+string]
0x18001852f  mov     [rsp+130h+var_100], rax
0x180018534  mov     rax, [rbp+30h+var_58]
0x180018538  mov     [rsp+130h+var_F8], rax
0x18001853d  mov     rax, [rbp+30h+var_38]
0x180018541  mov     [rsp+130h+var_F0], rax
0x180018546  movups  xmm0, xmmword ptr cs:_GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b.Data1
0x18001854d  movdqu  [rsp+130h+var_E8], xmm0
0x180018553  movups  xmm1, xmmword ptr cs:_GUID_8cb35b00_501c_5532_a664_38c9c429bb1a.Data1
0x18001855a  movdqu  [rsp+130h+var_D8], xmm1
0x180018560  movups  xmm0, xmmword ptr cs:_GUID_8cbd762a_1222_5ee5_b745_489e7a42c6ec.Data1
0x180018567  movdqu  [rsp+130h+var_C8], xmm0
0x18001856d  movups  xmm1, xmmword ptr cs:_GUID_d1bacd1f_0376_5823_8c29_1d45b9f4c191.Data1
0x180018574  movdqu  [rsp+130h+var_B8], xmm1
0x18001857a  movups  xmm0, xmmword ptr cs:_GUID_326fe162_582b_5659_b8a4_68ff0f525745.Data1
0x180018581  movdqu  [rbp+30h+var_A8], xmm0
0x180018586  mov     [rsp+130h+var_110], 0
0x18001858f  lea     rcx, [rsp+130h+var_110]
0x180018594  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018599  mov     [rbp+30h+var_18], 0
0x1800185a1  lea     r9, [rbp+30h+var_18]; string
0x1800185a5  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800185a9  lea     edx, [rbx-13h]; length
0x1800185ac  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800185b3  call    cs:__imp_WindowsCreateStringReference
0x1800185b9  test    eax, eax
0x1800185bb  js      loc_18001865D
0x1800185c1  lea     r8, [rsp+130h+var_110]
0x1800185c6  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800185cd  mov     rcx, [rbp+30h+var_18]
0x1800185d1  call    cs:__imp_RoGetActivationFactory
0x1800185d7  mov     ebx, eax
0x1800185d9  test    eax, eax
0x1800185db  jns     loc_180018670
0x1800185e1  mov     rcx, [rsp+130h+var_110]
0x1800185e6  test    rcx, rcx
0x1800185e9  jz      short loc_180018601
0x1800185eb  mov     [rsp+130h+var_110], 0
0x1800185f4  mov     rdx, [rcx]
0x1800185f7  mov     rax, [rdx+10h]
0x1800185fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018600  nop
0x180018601  mov     eax, ebx
0x180018603  mov     rcx, [rbp+30h+var_10]
0x180018607  xor     rcx, rsp; StackCookie
0x18001860a  call    __security_check_cookie
0x18001860f  lea     r11, [rsp+130h+var_s0]
0x180018617  mov     rbx, [r11+10h]
0x18001861b  mov     rdi, [r11+20h]
0x18001861f  mov     rsp, r11
0x180018622  pop     rbp
0x180018623  retn
0x180018624  xor     r9d, r9d; lpArguments
0x180018627  xor     r8d, r8d; nNumberOfArguments
0x18001862a  lea     edx, [r9+1]; dwExceptionFlags
0x18001862e  mov     ecx, eax; dwExceptionCode
0x180018630  call    cs:__imp_RaiseException
0x180018636  int     3; Trap to Debugger
0x180018637  xor     r9d, r9d; lpArguments
0x18001863a  xor     r8d, r8d; nNumberOfArguments
0x18001863d  lea     edx, [r9+1]; dwExceptionFlags
0x180018641  mov     ecx, eax; dwExceptionCode
0x180018643  call    cs:__imp_RaiseException
0x180018649  int     3; Trap to Debugger
0x18001864a  xor     r9d, r9d; lpArguments
0x18001864d  xor     r8d, r8d; nNumberOfArguments
0x180018650  lea     edx, [r9+1]; dwExceptionFlags
0x180018654  mov     ecx, eax; dwExceptionCode
0x180018656  call    cs:__imp_RaiseException
0x18001865c  int     3; Trap to Debugger
0x18001865d  xor     r9d, r9d; lpArguments
0x180018660  xor     r8d, r8d; nNumberOfArguments
0x180018663  lea     edx, [r9+1]; dwExceptionFlags
0x180018667  mov     ecx, eax; dwExceptionCode
0x180018669  call    cs:__imp_RaiseException
0x18001866f  int     3; Trap to Debugger
0x180018670  mov     [rsp+130h+var_108], 0
0x180018679  mov     rbx, [rsp+130h+var_110]
0x18001867e  lea     rcx, [rsp+130h+var_108]
0x180018683  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018688  lea     r8, [rsp+130h+var_108]
0x18001868d  lea     rdx, [rsp+130h+var_100]
0x180018692  mov     rcx, rbx
0x180018695  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18001869a  mov     ebx, eax
0x18001869c  lea     rcx, [rsp+130h+var_108]
0x1800186a1  test    eax, eax
0x1800186a3  jns     short loc_1800186B9
0x1800186a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800186aa  lea     rcx, [rsp+130h+var_110]
0x1800186af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800186b4  jmp     loc_180018601
0x1800186b9  mov     rax, [rsp+130h+var_108]
0x1800186be  mov     [rsp+130h+var_108], 0
0x1800186c7  mov     [rdi], rax
0x1800186ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800186cf  lea     rcx, [rsp+130h+var_110]
0x1800186d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800186d9  xor     eax, eax
0x1800186db  jmp     loc_180018603
```
