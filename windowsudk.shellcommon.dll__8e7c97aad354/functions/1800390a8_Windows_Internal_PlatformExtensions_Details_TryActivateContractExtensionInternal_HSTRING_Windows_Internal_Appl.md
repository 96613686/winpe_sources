# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x1800390a8`
- end: `0x1800394a8`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `1024`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e834`
- `0x1803c1920`

## callees

- `0x180023e9c`
- `0x18002e634`
- `0x1800390a8`
- `0x1800398c8`
- `0x180039ab4`
- `0x1800a62f0`
- `0x1800e34bc`
- `0x1800f9a2c`
- `0x1800f9b7c`
- `0x1800fe90c`
- `0x1800fe974`
- `0x180118180`
- `0x18015cb00`
- `0x1803c08b8`
- `0x1803c2c64`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800391c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800394a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800391c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800394a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800391aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800391aa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800391d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800391d8`

## string_xrefs

- `0x18003913b`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800391ee`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800392e9`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18003934b`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
        HSTRING a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  wchar_t *v8; // r8
  int v9; // eax
  unsigned int v10; // edi
  bool v11; // bl
  unsigned __int64 v12; // rdi
  unsigned int v13; // eax
  UINT32 v14; // edx
  HRESULT v15; // eax
  int ActivationFactory; // eax
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 (__fastcall *v21)(__int64, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)); // rdi
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD *); // r9
  int v23; // edi
  __int64 v24; // rdx
  __int64 (__fastcall *v25)(__int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)); // rsi
  const struct _GUID *v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v28)(_QWORD, __int64, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  void **v35; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[264]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+190h] [rbp+90h]
  _BYTE v38[8]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v39[48]; // [rsp+1A0h] [rbp+A0h] BYREF
  HSTRING__ sourceString; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v32 = a2;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v35);
  v35 = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
    &v35,
    a1,
    a2,
    a3);
  *a4 = 0;
  v9 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
         a1,
         &sourceString,
         v8,
         v37 + 8,
         v26);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v9,
      v27);
LABEL_14:
    v35 = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v35);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v39);
    wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v38);
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>(v36);
    return v10;
  }
  v11 = 0;
  if ( LOWORD(sourceString.unused) )
  {
    v29 = 0;
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)&sourceString.unused + v12) );
    if ( v12 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      JUMPOUT(0x1800394A7LL);
    }
    v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v12);
    v14 = v13 - 1;
    if ( (unsigned int)v12 < v13 )
      v14 = v12;
    v15 = WindowsCreateStringReference((PCWSTR)&sourceString, v14, &hstringHeader, &string);
    if ( v15 < 0 )
    {
      RaiseException(v15, 1u, 0, 0);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_00000035_0000_0000_c000_000000000046, &v29);
    v10 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x242,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)ActivationFactory,
        v27);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      goto LABEL_14;
    }
    v28 = 0;
    v31 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v29)(
           v29,
           &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
           &v31) < 0 )
    {
      v25 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))(*(_QWORD *)v29 + 48LL);
      v28 = 0;
      v23 = v25(v29, &v28);
      if ( v23 < 0 )
      {
        v24 = 592;
        goto LABEL_25;
      }
    }
    else
    {
      v30 = 0;
      v18 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
              &v30,
              &v32);
      v19 = v18;
      if ( v18 < 0 )
      {
        v20 = 587;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v18,
          v27);
        wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v30);
LABEL_26:
        wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v31);
        wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v28);
        wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v29);
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)&v35);
        return v19;
      }
      v21 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))(*(_QWORD *)v31 + 48LL);
      v28 = 0;
      v18 = v21(v31, a1, v30, &v28);
      v19 = v18;
      if ( v18 < 0 )
      {
        v20 = 588;
        goto LABEL_20;
      }
      v11 = 1;
      wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v30);
    }
    v22 = v28;
    if ( v28 )
    {
      v23 = (**v28)(v28, a3, a4);
      if ( v23 < 0 )
      {
        v24 = 600;
LABEL_25:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v23,
          v27);
        v19 = v23;
        goto LABEL_26;
      }
      v22 = v28;
    }
    if ( v31 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      v22 = v28;
    }
    if ( v22 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD *)))(*v22)[2])(v22);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
    (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)&v35,
    *a4 != 0,
    v11,
    (const wchar_t *)&sourceString);
  v35 = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v35);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v39);
  wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v38);
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>(v36);
  return 0;
}

```

## disassembly

```asm
0x1800390a8  push    rbp
0x1800390aa  push    rbx
0x1800390ab  push    rsi
0x1800390ac  push    rdi
0x1800390ad  push    r12
0x1800390af  push    r13
0x1800390b1  push    r14
0x1800390b3  push    r15
0x1800390b5  lea     rbp, [rsp-1E8h]
0x1800390bd  sub     rsp, 2E8h
0x1800390c4  mov     rax, cs:__security_cookie
0x1800390cb  xor     rax, rsp
0x1800390ce  mov     [rbp+220h+var_50], rax
0x1800390d5  mov     r14, r9
0x1800390d8  mov     r15, r8
0x1800390db  mov     ebx, edx
0x1800390dd  mov     rsi, rcx
0x1800390e0  mov     [rsp+320h+var_2D0], edx
0x1800390e4  lea     rcx, [rbp+220h+var_2A0]; struct wil::details::IFailureCallback *
0x1800390e8  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800390ed  lea     r13, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x1800390f4  mov     [rbp+220h+var_2A0], r13
0x1800390f8  mov     r9, r15
0x1800390fb  mov     r8d, ebx
0x1800390fe  mov     rdx, rsi
0x180039101  lea     rcx, [rbp+220h+var_2A0]
0x180039105  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x18003910a  nop
0x18003910b  xor     r12d, r12d
0x18003910e  mov     [r14], r12
0x180039111  mov     r9, [rbp+220h+var_190]
0x180039118  add     r9, 8; unsigned __int64
0x18003911c  lea     rdx, [rbp+220h+sourceString]; HSTRING
0x180039123  mov     rcx, rsi; this
0x180039126  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEA_W_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,wchar_t *,unsigned __int64,_GUID const *)
0x18003912b  mov     edi, eax
0x18003912d  test    eax, eax
0x18003912f  jns     short loc_180039151
0x180039131  mov     rcx, [rbp+228h]; this
0x180039138  mov     r9d, eax; char *
0x18003913b  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180039142  mov     edx, 23Eh; void *
0x180039147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003914c  jmp     loc_180039217
0x180039151  mov     bl, r12b
0x180039154  cmp     word ptr [rbp+220h+sourceString.unused], r12w
0x18003915c  jz      loc_180039426
0x180039162  mov     [rsp+320h+var_2E8], r12
0x180039167  lea     rax, [rbp+220h+sourceString]
0x18003916e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180039172  inc     rdi
0x180039175  cmp     [rax+rdi*2], r12w
0x18003917a  jnz     short loc_180039172
0x18003917c  mov     eax, 0FFFFFFFFh
0x180039181  cmp     rdi, rax
0x180039184  ja      loc_180039492
0x18003918a  mov     ecx, edi; unsigned int
0x18003918c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180039191  lea     edx, [rax-1]
0x180039194  cmp     edi, eax
0x180039196  cmovb   edx, edi; length
0x180039199  lea     r9, [rsp+320h+string]; string
0x18003919e  lea     r8, [rsp+320h+hstringHeader]; hstringHeader
0x1800391a3  lea     rcx, [rbp+220h+sourceString]; sourceString
0x1800391aa  call    cs:__imp_WindowsCreateStringReference
0x1800391b0  test    eax, eax
0x1800391b2  jns     short loc_1800391C7
0x1800391b4  xor     r9d, r9d; lpArguments
0x1800391b7  xor     r8d, r8d; nNumberOfArguments
0x1800391ba  lea     edx, [r9+1]; dwExceptionFlags
0x1800391be  mov     ecx, eax; dwExceptionCode
0x1800391c0  call    cs:__imp_RaiseException
0x1800391c6  int     3; Trap to Debugger
0x1800391c7  lea     r8, [rsp+320h+var_2E8]
0x1800391cc  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x1800391d3  mov     rcx, [rsp+320h+string]
0x1800391d8  call    cs:__imp_RoGetActivationFactory
0x1800391de  mov     edi, eax
0x1800391e0  test    eax, eax
0x1800391e2  jns     short loc_18003924C
0x1800391e4  mov     rcx, [rbp+228h]; this
0x1800391eb  mov     r9d, eax; char *
0x1800391ee  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800391f5  mov     edx, 242h; void *
0x1800391fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800391ff  nop
0x180039200  mov     rcx, [rsp+320h+var_2E8]
0x180039205  test    rcx, rcx
0x180039208  jz      short loc_180039217
0x18003920a  mov     rax, [rcx]
0x18003920d  mov     rax, [rax+10h]
0x180039211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039216  nop
0x180039217  mov     [rbp+220h+var_2A0], r13
0x18003921b  lea     rcx, [rbp+220h+var_2A0]
0x18003921f  call    ?Destroy@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180039224  lea     rcx, [rbp+220h+var_180]; this
0x18003922b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180039230  lea     rcx, [rbp+220h+var_188]
0x180039237  call    ?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18003923c  lea     rcx, [rbp+220h+var_298]
0x180039240  call    ??1?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x180039245  mov     eax, edi
0x180039247  jmp     loc_18003946F
0x18003924c  mov     [rsp+320h+var_2F0], r12
0x180039251  mov     [rsp+320h+var_2D8], r12
0x180039256  mov     rcx, [rsp+320h+var_2E8]
0x18003925b  mov     rax, [rcx]
0x18003925e  lea     r8, [rsp+320h+var_2D8]
0x180039263  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x18003926a  mov     rax, [rax]
0x18003926d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039272  test    eax, eax
0x180039274  js      loc_18003938E
0x18003927a  mov     [rsp+320h+var_2E0], r12
0x18003927f  lea     rdx, [rsp+320h+var_2D0]
0x180039284  lea     rcx, [rsp+320h+var_2E0]
0x180039289  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x18003928e  mov     ebx, eax
0x180039290  test    eax, eax
0x180039292  jns     short loc_18003929B
0x180039294  mov     edx, 24Bh
0x180039299  jmp     short loc_1800392E6
0x18003929b  mov     rbx, [rsp+320h+var_2D8]
0x1800392a0  mov     rax, [rbx]
0x1800392a3  mov     rdi, [rax+30h]
0x1800392a7  mov     rcx, [rsp+320h+var_2F0]
0x1800392ac  mov     [rsp+320h+var_2F0], r12
0x1800392b1  test    rcx, rcx
0x1800392b4  jz      short loc_1800392C3
0x1800392b6  mov     r8, [rcx]
0x1800392b9  mov     rax, [r8+10h]
0x1800392bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392c2  nop
0x1800392c3  lea     r9, [rsp+320h+var_2F0]
0x1800392c8  mov     r8, [rsp+320h+var_2E0]
0x1800392cd  mov     rdx, rsi
0x1800392d0  mov     rcx, rbx
0x1800392d3  mov     rax, rdi
0x1800392d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392db  mov     ebx, eax
0x1800392dd  test    eax, eax
0x1800392df  jns     short loc_180039308
0x1800392e1  mov     edx, 24Ch; void *
0x1800392e6  mov     r9d, eax; char *
0x1800392e9  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800392f0  mov     rcx, [rbp+228h]; this
0x1800392f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800392fc  lea     rcx, [rsp+320h+var_2E0]
0x180039301  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x180039306  jmp     short loc_180039360
0x180039308  mov     ebx, 1
0x18003930d  lea     rcx, [rsp+320h+var_2E0]
0x180039312  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x180039317  mov     r9, [rsp+320h+var_2F0]
0x18003931c  test    r9, r9
0x18003931f  jz      loc_1800393DF
0x180039325  mov     rax, [r9]
0x180039328  mov     r8, r14
0x18003932b  mov     rdx, r15
0x18003932e  mov     rcx, r9
0x180039331  mov     rax, [rax]
0x180039334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039339  mov     edi, eax
0x18003933b  test    eax, eax
0x18003933d  jns     loc_1800393DA
0x180039343  mov     edx, 258h; void *
0x180039348  mov     r9d, edi; char *
0x18003934b  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180039352  mov     rcx, [rbp+228h]; this
0x180039359  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003935e  mov     ebx, edi
0x180039360  lea     rcx, [rsp+320h+var_2D8]
0x180039365  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18003936a  lea     rcx, [rsp+320h+var_2F0]
0x18003936f  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x180039374  lea     rcx, [rsp+320h+var_2E8]
0x180039379  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x18003937e  lea     rcx, [rbp+220h+var_2A0]; this
0x180039382  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x180039387  mov     eax, ebx
0x180039389  jmp     loc_18003946F
0x18003938e  mov     rdi, [rsp+320h+var_2E8]
0x180039393  mov     rax, [rdi]
0x180039396  mov     rsi, [rax+30h]
0x18003939a  mov     rcx, [rsp+320h+var_2F0]
0x18003939f  mov     [rsp+320h+var_2F0], r12
0x1800393a4  test    rcx, rcx
0x1800393a7  jz      short loc_1800393B6
0x1800393a9  mov     rdx, [rcx]
0x1800393ac  mov     rax, [rdx+10h]
0x1800393b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393b5  nop
0x1800393b6  lea     rdx, [rsp+320h+var_2F0]
0x1800393bb  mov     rcx, rdi
0x1800393be  mov     rax, rsi
0x1800393c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393c6  mov     edi, eax
0x1800393c8  test    eax, eax
0x1800393ca  jns     loc_180039317
0x1800393d0  mov     edx, 250h
0x1800393d5  jmp     loc_180039348
0x1800393da  mov     r9, [rsp+320h+var_2F0]
0x1800393df  mov     rcx, [rsp+320h+var_2D8]
0x1800393e4  test    rcx, rcx
0x1800393e7  jz      short loc_1800393FA
0x1800393e9  mov     rax, [rcx]
0x1800393ec  mov     rax, [rax+10h]
0x1800393f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393f5  mov     r9, [rsp+320h+var_2F0]
0x1800393fa  test    r9, r9
0x1800393fd  jz      short loc_18003940F
0x1800393ff  mov     rax, [r9]
0x180039402  mov     rcx, r9
0x180039405  mov     rax, [rax+10h]
0x180039409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003940e  nop
0x18003940f  mov     rcx, [rsp+320h+var_2E8]
0x180039414  test    rcx, rcx
0x180039417  jz      short loc_180039426
0x180039419  mov     rax, [rcx]
0x18003941c  mov     rax, [rax+10h]
0x180039420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039425  nop
0x180039426  cmp     [r14], r12
0x180039429  setnz   dl; bool
0x18003942c  lea     r9, [rbp+220h+sourceString]; wchar_t *
0x180039433  mov     r8b, bl; bool
0x180039436  lea     rcx, [rbp+220h+var_2A0]; this
0x18003943a  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEB_W@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,wchar_t const *)
0x18003943f  mov     [rbp+220h+var_2A0], r13
0x180039443  lea     rcx, [rbp+220h+var_2A0]
0x180039447  call    ?Destroy@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003944c  lea     rcx, [rbp+220h+var_180]; this
0x180039453  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180039458  lea     rcx, [rbp+220h+var_188]
0x18003945f  call    ?reset@?$shared_object@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180039464  lea     rcx, [rbp+220h+var_298]
0x180039468  call    ??1?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003946d  xor     eax, eax
0x18003946f  mov     rcx, [rbp+220h+var_50]
0x180039476  xor     rcx, rsp; StackCookie
0x180039479  call    __security_check_cookie
0x18003947e  add     rsp, 2E8h
0x180039485  pop     r15
0x180039487  pop     r14
0x180039489  pop     r13
0x18003948b  pop     r12
0x18003948d  pop     rdi
0x18003948e  pop     rsi
0x18003948f  pop     rbx
0x180039490  pop     rbp
0x180039491  retn
0x180039492  xor     r9d, r9d; lpArguments
0x180039495  xor     r8d, r8d; nNumberOfArguments
0x180039498  lea     edx, [r9+1]; dwExceptionFlags
0x18003949c  mov     ecx, 80070216h; dwExceptionCode
0x1800394a1  call    cs:__imp_RaiseException
```
