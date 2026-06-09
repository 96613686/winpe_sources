# Windows::Internal::PlatformExtensions::Details::TryGetActivationFactoryForContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x1800394b0`
- end: `0x18003970b`
- name: `?TryGetActivationFactoryForContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e2dfc`

## callees

- `0x18002e634`
- `0x1800394b0`
- `0x180039714`
- `0x1800397c0`
- `0x180039804`
- `0x1800398c8`
- `0x180039ab4`
- `0x1800e34bc`
- `0x18015cb00`
- `0x180437618`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039559`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003968c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039559`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003968c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003959e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003959e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800395bd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800395bd`

## string_xrefs

- `0x18003956a`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180039624`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18003969d`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryGetActivationFactoryForContractExtensionInternal(
        HSTRING a1,
        unsigned __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v5; // ebx
  __int64 v7; // rcx
  wchar_t *v8; // r8
  __int64 v9; // rcx
  int v10; // eax
  unsigned __int64 v11; // rdx
  unsigned __int8 v12; // cl
  unsigned int v13; // ebx
  unsigned __int64 v14; // rbx
  unsigned int v15; // eax
  UINT32 v16; // edx
  HRESULT v17; // eax
  int ActivationFactory; // eax
  int v19; // eax
  __int64 v21; // rcx
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry *v22; // rcx
  int v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING__ sourceString; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v5 = a2;
  if ( Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::IsEnabled((unsigned __int8)a1, a2) )
  {
    wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::get(
      v7,
      _lambda_bf0cab7e367b92d194d9a1ba31b40746_::_lambda_invoker_cdecl_);
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::GetActivationFactoryForContractExtension_(
      v9,
      a1,
      v5,
      &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90);
  }
  *a4 = 0;
  v10 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
          a1,
          &sourceString,
          v8,
          0,
          *(const struct _GUID **)v23);
  v13 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v10,
      v23[0]);
    return v13;
  }
  if ( !LOWORD(sourceString.unused) )
    goto LABEL_26;
  *(_QWORD *)v23 = 0;
  v14 = -1;
  do
    ++v14;
  while ( *((_WORD *)&sourceString.unused + v14) );
  if ( v14 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v15 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v14);
  v16 = v15 - 1;
  if ( (unsigned int)v14 < v15 )
    v16 = v14;
  v17 = WindowsCreateStringReference((PCWSTR)&sourceString, v16, &hstringHeader, &string);
  if ( v17 < 0 )
  {
    RaiseException(v17, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, v23);
  v13 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)ActivationFactory,
      v23[0]);
LABEL_24:
    wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(v23);
    return v13;
  }
  v24 = 0;
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v23)(
         *(_QWORD *)v23,
         &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
         &v24) >= 0 )
  {
    wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v24);
    v13 = -2147019873;
    goto LABEL_24;
  }
  v19 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))v23)(
          *(_QWORD *)v23,
          &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
          a4);
  v13 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v19,
      v23[0]);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( *(_QWORD *)v23 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 16LL))(*(_QWORD *)v23);
    return v13;
  }
  wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(&v24);
  wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(v23);
LABEL_26:
  if ( Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::IsEnabled(v12, v11) )
  {
    wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::get(
      v21,
      _lambda_bf0cab7e367b92d194d9a1ba31b40746_::_lambda_invoker_cdecl_);
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::GetActivationFactoryForContractExtensionResult_(
      v22,
      *a4 != 0,
      (const wchar_t *)&sourceString);
  }
  return 0;
}

```

## disassembly

```asm
0x1800394b0  push    rbp
0x1800394b2  push    rbx
0x1800394b3  push    rsi
0x1800394b4  push    rdi
0x1800394b5  push    r14
0x1800394b7  lea     rbp, [rsp-60h]
0x1800394bc  sub     rsp, 160h
0x1800394c3  mov     rax, cs:__security_cookie
0x1800394ca  xor     rax, rsp
0x1800394cd  mov     [rbp+80h+var_30], rax
0x1800394d1  mov     rdi, r9
0x1800394d4  mov     ebx, edx
0x1800394d6  mov     rsi, rcx
0x1800394d9  call    ?IsEnabled@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SA_NE_K@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800394de  xor     r14d, r14d
0x1800394e1  test    al, al
0x1800394e3  jz      short loc_180039503
0x1800394e5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_bf0cab7e367b92d194d9a1ba31b40746_@@CA@XZ; _lambda_bf0cab7e367b92d194d9a1ba31b40746_::_lambda_invoker_cdecl_(void)
0x1800394ec  call    ?get@?$static_lazy@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@@details@wil@@QEAAPEAVPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@P6AXXZ@Z; wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::get(void (*)(void))
0x1800394f1  lea     r9, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1800394f8  mov     r8d, ebx
0x1800394fb  mov     rdx, rsi
0x1800394fe  call    ?GetActivationFactoryForContractExtension_@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@45@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::GetActivationFactoryForContractExtension_(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x180039503  mov     [rdi], r14
0x180039506  xor     r9d, r9d; unsigned __int64
0x180039509  lea     rdx, [rsp+180h+sourceString]; HSTRING
0x18003950e  mov     rcx, rsi; this
0x180039511  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEA_W_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,wchar_t *,unsigned __int64,_GUID const *)
0x180039516  mov     ebx, eax
0x180039518  test    eax, eax
0x18003951a  js      short loc_180039560
0x18003951c  cmp     word ptr [rsp+180h+sourceString.unused], r14w
0x180039522  jz      loc_1800396DF
0x180039528  mov     qword ptr [rsp+180h+var_160], r14; int
0x18003952d  lea     rax, [rsp+180h+sourceString]
0x180039532  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180039536  inc     rbx
0x180039539  cmp     [rax+rbx*2], r14w
0x18003953e  jnz     short loc_180039536
0x180039540  mov     eax, 0FFFFFFFFh
0x180039545  cmp     rbx, rax
0x180039548  jbe     short loc_180039580
0x18003954a  xor     r9d, r9d; lpArguments
0x18003954d  xor     r8d, r8d; nNumberOfArguments
0x180039550  lea     edx, [r9+1]; dwExceptionFlags
0x180039554  mov     ecx, 80070216h; dwExceptionCode
0x180039559  call    cs:__imp_RaiseException
0x18003955f  int     3; Trap to Debugger
0x180039560  mov     rcx, [rbp+88h]; this
0x180039567  mov     r9d, ebx; char *
0x18003956a  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180039571  mov     edx, 21Dh; void *
0x180039576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003957b  jmp     loc_180039664
0x180039580  mov     ecx, ebx; unsigned int
0x180039582  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180039587  lea     edx, [rax-1]
0x18003958a  cmp     ebx, eax
0x18003958c  cmovb   edx, ebx; length
0x18003958f  lea     r9, [rsp+180h+string]; string
0x180039594  lea     r8, [rsp+180h+hstringHeader]; hstringHeader
0x180039599  lea     rcx, [rsp+180h+sourceString]; sourceString
0x18003959e  call    cs:__imp_WindowsCreateStringReference
0x1800395a4  test    eax, eax
0x1800395a6  js      loc_180039680
0x1800395ac  lea     r8, [rsp+180h+var_160]
0x1800395b1  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1800395b8  mov     rcx, [rsp+180h+string]
0x1800395bd  call    cs:__imp_RoGetActivationFactory
0x1800395c3  mov     ebx, eax
0x1800395c5  test    eax, eax
0x1800395c7  js      loc_180039693
0x1800395cd  mov     [rsp+180h+var_158], r14
0x1800395d2  mov     rcx, qword ptr [rsp+180h+var_160]
0x1800395d7  mov     rax, [rcx]
0x1800395da  lea     r8, [rsp+180h+var_158]
0x1800395df  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x1800395e6  mov     rax, [rax]
0x1800395e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395ee  test    eax, eax
0x1800395f0  jns     loc_1800396B0
0x1800395f6  mov     rcx, qword ptr [rsp+180h+var_160]
0x1800395fb  mov     rax, [rcx]
0x1800395fe  mov     r8, rdi
0x180039601  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180039608  mov     rax, [rax]
0x18003960b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039610  mov     ebx, eax
0x180039612  test    eax, eax
0x180039614  jns     loc_1800396CB
0x18003961a  mov     rcx, [rbp+88h]; this
0x180039621  mov     r9d, eax; char *
0x180039624  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18003962b  mov     edx, 22Bh; void *
0x180039630  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039635  nop
0x180039636  mov     rcx, [rsp+180h+var_158]
0x18003963b  test    rcx, rcx
0x18003963e  jz      short loc_18003964D
0x180039640  mov     rax, [rcx]
0x180039643  mov     rax, [rax+10h]
0x180039647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003964c  nop
0x18003964d  mov     rcx, qword ptr [rsp+180h+var_160]
0x180039652  test    rcx, rcx
0x180039655  jz      short loc_180039664
0x180039657  mov     rax, [rcx]
0x18003965a  mov     rax, [rax+10h]
0x18003965e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039663  nop
0x180039664  mov     eax, ebx
0x180039666  mov     rcx, [rbp+80h+var_30]
0x18003966a  xor     rcx, rsp; StackCookie
0x18003966d  call    __security_check_cookie
0x180039672  add     rsp, 160h
0x180039679  pop     r14
0x18003967b  pop     rdi
0x18003967c  pop     rsi
0x18003967d  pop     rbx
0x18003967e  pop     rbp
0x18003967f  retn
0x180039680  xor     r9d, r9d; lpArguments
0x180039683  xor     r8d, r8d; nNumberOfArguments
0x180039686  lea     edx, [r9+1]; dwExceptionFlags
0x18003968a  mov     ecx, eax; dwExceptionCode
0x18003968c  call    cs:__imp_RaiseException
0x180039692  int     3; Trap to Debugger
0x180039693  mov     rcx, [rbp+88h]; this
0x18003969a  mov     r9d, eax; char *
0x18003969d  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800396a4  mov     edx, 221h; void *
0x1800396a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800396ae  jmp     short loc_1800396BF
0x1800396b0  lea     rcx, [rsp+180h+var_158]
0x1800396b5  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1800396ba  mov     ebx, 8007139Fh
0x1800396bf  lea     rcx, [rsp+180h+var_160]
0x1800396c4  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1800396c9  jmp     short loc_180039664
0x1800396cb  lea     rcx, [rsp+180h+var_158]
0x1800396d0  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1800396d5  lea     rcx, [rsp+180h+var_160]
0x1800396da  call    ??1?$com_ptr_t@UIGridIntensityData@Sustainability@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Sustainability::IGridIntensityData,wil::err_exception_policy>(void)
0x1800396df  call    ?IsEnabled@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SA_NE_K@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800396e4  test    al, al
0x1800396e6  jz      short loc_180039704
0x1800396e8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_bf0cab7e367b92d194d9a1ba31b40746_@@CA@XZ; _lambda_bf0cab7e367b92d194d9a1ba31b40746_::_lambda_invoker_cdecl_(void)
0x1800396ef  call    ?get@?$static_lazy@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@@details@wil@@QEAAPEAVPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@P6AXXZ@Z; wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::get(void (*)(void))
0x1800396f4  cmp     [rdi], r14
0x1800396f7  setnz   dl; bool
0x1800396fa  lea     r8, [rsp+180h+sourceString]; wchar_t *
0x1800396ff  call    ?GetActivationFactoryForContractExtensionResult_@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_NPEB_W@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::GetActivationFactoryForContractExtensionResult_(bool,wchar_t const *)
0x180039704  xor     eax, eax
0x180039706  jmp     loc_180039666
```
