# Windows::Internal::Notifications::CToastActivator_Foreground::Activate(HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> *)

- ea: `0x1800186f0`
- end: `0x180018ac7`
- name: `?Activate@CToastActivator_Foreground@Notifications@Internal@Windows@@UEAAJPEAUHSTRING__@@00PEAUIPropertySet@Collections@Foundation@4@PEAU?$IVectorView@PEAUHSTRING__@@@784@@Z`
- size: `983`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005670`
- `0x18000d7d8`
- `0x1800101f0`
- `0x180015150`
- `0x180016744`
- `0x1800186f0`
- `0x180018ad0`
- `0x180018b78`
- `0x180018bb8`
- `0x18001b848`
- `0x18001cb74`
- `0x18001ff00`
- `0x180025bfc`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018989`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001878f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800187a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018a41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001878f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800187a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018a41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001888f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018911`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001888f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018911`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800189dc`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800189dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Foreground::Activate(
        __int64 a1,
        HSTRING a2,
        __int64 a3,
        HSTRING a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // r8
  __int64 v9; // r12
  HSTRING v10; // r9
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned int i; // edi
  __int64 (__fastcall *v17)(__int64, _QWORD, HSTRING *); // rbx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  int v22; // eax
  DWORD CurrentThreadId; // edi
  __int64 *v24; // rax
  __int64 v25; // rbx
  int v26; // edi
  int v27; // [rsp+20h] [rbp-B8h]
  HSTRING StringRawBuffer; // [rsp+30h] [rbp-A8h] BYREF
  int v29; // [rsp+38h] [rbp-A0h] BYREF
  unsigned int v30; // [rsp+3Ch] [rbp-9Ch] BYREF
  __int64 v31; // [rsp+40h] [rbp-98h] BYREF
  __int64 v32; // [rsp+48h] [rbp-90h] BYREF
  HSTRING string; // [rsp+50h] [rbp-88h] BYREF
  PCWSTR v34; // [rsp+58h] [rbp-80h] BYREF
  PCWSTR v35; // [rsp+60h] [rbp-78h] BYREF
  __int64 v36; // [rsp+68h] [rbp-70h] BYREF
  _QWORD v37[3]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v38[32]; // [rsp+88h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  string = a2;
  v36 = a3;
  v35 = (PCWSTR)a4;
  v29 = 0;
  v30 = 0;
  std::string::string(v38, a2, a1);
  v9 = v8 - 48;
  if ( Windows::Internal::Notifications::CToastActivator_Foreground::CanActivate(
         (Windows::Internal::Notifications::CToastActivator_Foreground *)(v8 - 48),
         string,
         v10) )
  {
    WpnClientTelemetry::GetCorrelationVector(v38);
    StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(a4, 0);
    v34 = WindowsGetStringRawBuffer(string, 0);
    WpnClientTelemetry::ToastActivationStart<unsigned short const *,unsigned short const *,std::string &>(
      &v34,
      &StringRawBuffer,
      v38);
    v31 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v13 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
            v12,
            &v31);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
        (const char *)(unsigned int)v13,
        v27);
    v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 104LL))(v31, a3);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
        (const char *)(unsigned int)v14,
        v27);
    if ( a6 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a6 + 56LL))(a6, &v30);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x65,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
          (const char *)(unsigned int)v15,
          v27);
      for ( i = 0; i < v30; ++i )
      {
        StringRawBuffer = 0;
        v17 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)a6 + 48LL);
        WindowsDeleteString(0);
        StringRawBuffer = 0;
        v18 = v17(a6, i, &StringRawBuffer);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x69,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
            (const char *)(unsigned int)v18,
            v27);
        v19 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v31 + 104LL))(v31, StringRawBuffer);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6A,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
            (const char *)(unsigned int)v19,
            v27);
        if ( StringRawBuffer )
          WindowsDeleteString(StringRawBuffer);
      }
    }
    v32 = 0;
    v20 = v31;
    v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v22 = v21(v20, &v32);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
        (const char *)(unsigned int)v22,
        v27);
    v37[0] = v9;
    v37[1] = &string;
    v37[2] = &v32;
    CurrentThreadId = GetCurrentThreadId();
    v24 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f_____lambda_7b4fabe6bb32ef3f000e12ab001b652f___(
                       &StringRawBuffer,
                       v37);
    v25 = *v24;
    *v24 = 0;
    if ( StringRawBuffer )
    {
      StringRawBuffer = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    v26 = SHTaskPoolQueueTask(0, 32, CurrentThreadId);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactivator_foreground.cpp",
        (const char *)(unsigned int)v26,
        v25);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v35 = WindowsGetStringRawBuffer(a4, 0);
    v34 = WindowsGetStringRawBuffer(string, 0);
    WpnClientTelemetry::ToastActivationStop<unsigned short const *,unsigned short const *,HSTRING__ * &,unsigned int &,long &,std::string &>(
      (unsigned int)&v34,
      (unsigned int)&v35,
      (unsigned int)&v36,
      (unsigned int)&v30,
      (__int64)&v29,
      (__int64)v38);
    std::string::~string(v38);
    return 0;
  }
  else
  {
    std::string::~string(v38);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800186f0  mov     r11, rsp
0x1800186f3  mov     [r11+8], rbx
0x1800186f7  push    rsi
0x1800186f8  push    rdi
0x1800186f9  push    r12
0x1800186fb  push    r14
0x1800186fd  push    r15
0x1800186ff  sub     rsp, 0B0h
0x180018706  mov     rax, cs:__security_cookie
0x18001870d  xor     rax, rsp
0x180018710  mov     [rsp+0D8h+var_30], rax
0x180018718  mov     r14, r9
0x18001871b  mov     rbx, r8
0x18001871e  mov     r8, rcx
0x180018721  mov     [rsp+0D8h+string], rdx
0x180018726  mov     [r11-70h], rbx
0x18001872a  mov     [rsp+0D8h+var_78], r9
0x18001872f  mov     rsi, [rsp+0D8h+arg_28]
0x180018737  xor     r15d, r15d
0x18001873a  mov     [rsp+0D8h+var_A0], r15d
0x18001873f  mov     [rsp+0D8h+var_9C], r15d
0x180018744  lea     rcx, [r11-50h]
0x180018748  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18001874d  nop
0x18001874e  lea     r12, [r8-30h]
0x180018752  mov     r8, r9; HSTRING
0x180018755  mov     rdx, [rsp+0D8h+string]; HSTRING
0x18001875a  mov     rcx, r12; this
0x18001875d  call    ?CanActivate@CToastActivator_Foreground@Notifications@Internal@Windows@@AEAA_NPEAUHSTRING__@@0@Z; Windows::Internal::Notifications::CToastActivator_Foreground::CanActivate(HSTRING__ *,HSTRING__ *)
0x180018762  test    al, al
0x180018764  jnz     short loc_18001877D
0x180018766  lea     rcx, [rsp+0D8h+var_50]
0x18001876e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180018773  mov     eax, 80004001h
0x180018778  jmp     loc_180018A9F
0x18001877d  lea     rcx, [rsp+0D8h+var_50]
0x180018785  call    ?GetCorrelationVector@WpnClientTelemetry@@SAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; WpnClientTelemetry::GetCorrelationVector(std::string &)
0x18001878a  xor     edx, edx; length
0x18001878c  mov     rcx, r14; string
0x18001878f  call    cs:__imp_WindowsGetStringRawBuffer
0x180018795  mov     [rsp+0D8h+var_A8], rax
0x18001879a  xor     edx, edx; length
0x18001879c  mov     rcx, [rsp+0D8h+string]; string
0x1800187a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800187a7  mov     [rsp+0D8h+var_80], rax
0x1800187ac  lea     r8, [rsp+0D8h+var_50]
0x1800187b4  lea     rdx, [rsp+0D8h+var_A8]
0x1800187b9  lea     rcx, [rsp+0D8h+var_80]
0x1800187be  call    ??$ToastActivationStart@PEBGPEBGAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@WpnClientTelemetry@@SAX$$QEAPEBG0AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; WpnClientTelemetry::ToastActivationStart<ushort const *,ushort const *,std::string &>(ushort const * &&,ushort const * &&,std::string &)
0x1800187c3  mov     [rsp+0D8h+var_98], 0
0x1800187cc  lea     rcx, [rsp+0D8h+var_98]
0x1800187d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800187d6  lea     rdx, [rsp+0D8h+var_98]
0x1800187db  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x1800187e0  mov     rcx, [rsp+0D8h]; this
0x1800187e8  test    eax, eax
0x1800187ea  jns     short loc_180018800
0x1800187ec  mov     r9d, eax; char *
0x1800187ef  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800187f6  mov     edx, 5Fh ; '_'; void *
0x1800187fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018800  mov     rcx, [rsp+0D8h+var_98]
0x180018805  mov     rax, [rcx]
0x180018808  mov     rdx, rbx
0x18001880b  mov     rax, [rax+68h]
0x18001880f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018814  mov     rcx, [rsp+0D8h]; this
0x18001881c  test    eax, eax
0x18001881e  jns     short loc_180018834
0x180018820  mov     r9d, eax; char *
0x180018823  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001882a  mov     edx, 61h ; 'a'; void *
0x18001882f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018834  test    rsi, rsi
0x180018837  jz      loc_18001891E
0x18001883d  mov     rax, [rsi]
0x180018840  lea     rdx, [rsp+0D8h+var_9C]
0x180018845  mov     rcx, rsi
0x180018848  mov     rax, [rax+38h]
0x18001884c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018851  mov     rcx, [rsp+0D8h]; this
0x180018859  test    eax, eax
0x18001885b  jns     short loc_180018871
0x18001885d  mov     r9d, eax; char *
0x180018860  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180018867  mov     edx, 65h ; 'e'; void *
0x18001886c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018871  xor     edi, edi
0x180018873  cmp     edi, [rsp+0D8h+var_9C]
0x180018877  jnb     loc_18001891E
0x18001887d  mov     [rsp+0D8h+var_A8], 0
0x180018886  mov     rax, [rsi]
0x180018889  mov     rbx, [rax+30h]
0x18001888d  xor     ecx, ecx; string
0x18001888f  call    cs:__imp_WindowsDeleteString
0x180018895  mov     [rsp+0D8h+var_A8], 0
0x18001889e  lea     r8, [rsp+0D8h+var_A8]
0x1800188a3  mov     edx, edi
0x1800188a5  mov     rcx, rsi
0x1800188a8  mov     rax, rbx
0x1800188ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188b0  mov     rcx, [rsp+0D8h]; this
0x1800188b8  test    eax, eax
0x1800188ba  jns     short loc_1800188D0
0x1800188bc  mov     r9d, eax; char *
0x1800188bf  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800188c6  mov     edx, 69h ; 'i'; void *
0x1800188cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800188d0  mov     rcx, [rsp+0D8h+var_98]
0x1800188d5  mov     rax, [rcx]
0x1800188d8  mov     rdx, [rsp+0D8h+var_A8]
0x1800188dd  mov     rax, [rax+68h]
0x1800188e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188e6  mov     rcx, [rsp+0D8h]; this
0x1800188ee  test    eax, eax
0x1800188f0  jns     short loc_180018907
0x1800188f2  mov     r9d, eax; char *
0x1800188f5  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800188fc  mov     edx, 6Ah ; 'j'; void *
0x180018901  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018907  mov     rcx, [rsp+0D8h+var_A8]; string
0x18001890c  test    rcx, rcx
0x18001890f  jz      short loc_180018917
0x180018911  call    cs:__imp_WindowsDeleteString
0x180018917  inc     edi
0x180018919  jmp     loc_180018873
0x18001891e  mov     [rsp+0D8h+var_90], 0
0x180018927  mov     rdi, [rsp+0D8h+var_98]
0x18001892c  mov     rax, [rdi]
0x18001892f  mov     rbx, [rax+40h]
0x180018933  lea     rcx, [rsp+0D8h+var_90]
0x180018938  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001893d  lea     rdx, [rsp+0D8h+var_90]
0x180018942  mov     rcx, rdi
0x180018945  mov     rax, rbx
0x180018948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001894d  mov     rcx, [rsp+0D8h]; this
0x180018955  test    eax, eax
0x180018957  jns     short loc_18001896D
0x180018959  mov     r9d, eax; char *
0x18001895c  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180018963  mov     edx, 6Eh ; 'n'; void *
0x180018968  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001896d  mov     [rsp+0D8h+var_68], r12
0x180018972  lea     rax, [rsp+0D8h+string]
0x180018977  mov     [rsp+0D8h+var_60], rax
0x18001897c  lea     rax, [rsp+0D8h+var_90]
0x180018981  mov     [rsp+0D8h+var_58], rax
0x180018989  call    cs:__imp_GetCurrentThreadId
0x18001898f  mov     edi, eax
0x180018991  lea     rdx, [rsp+0D8h+var_68]
0x180018996  lea     rcx, [rsp+0D8h+var_A8]
0x18001899b  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_7b4fabe6bb32ef3f000e12ab001b652f_____lambda_7b4fabe6bb32ef3f000e12ab001b652f___
0x1800189a0  mov     rbx, [rax]
0x1800189a3  mov     qword ptr [rax], 0
0x1800189aa  mov     rcx, [rsp+0D8h+var_A8]
0x1800189af  test    rcx, rcx
0x1800189b2  jz      short loc_1800189C2
0x1800189b4  mov     [rsp+0D8h+var_A8], 0
0x1800189bd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x1800189c2  mov     [rsp+0D8h+var_B0], 0
0x1800189cb  mov     qword ptr [rsp+0D8h+var_B8], rbx; int
0x1800189d0  xor     r9d, r9d
0x1800189d3  mov     r8d, edi
0x1800189d6  lea     edx, [r9+20h]
0x1800189da  xor     ecx, ecx
0x1800189dc  call    cs:__imp_SHTaskPoolQueueTask
0x1800189e2  mov     edi, eax
0x1800189e4  test    rbx, rbx
0x1800189e7  jz      short loc_1800189F9
0x1800189e9  mov     rdx, [rbx]
0x1800189ec  mov     rcx, rbx
0x1800189ef  mov     rax, [rdx+10h]
0x1800189f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189f8  nop
0x1800189f9  mov     rcx, [rsp+0D8h]; this
0x180018a01  test    edi, edi
0x180018a03  jns     short loc_180018A1A
0x180018a05  mov     r9d, edi; char *
0x180018a08  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180018a0f  mov     edx, 85h; void *
0x180018a14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180018a1a  lea     rcx, [rsp+0D8h+var_90]
0x180018a1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018a24  nop
0x180018a25  lea     rcx, [rsp+0D8h+var_98]
0x180018a2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018a2f  nop
0x180018a30  jmp     short loc_180018A3C
0x180018a32  mov     r15d, [rsp+0D8h+var_A0]
0x180018a37  mov     r14, [rsp+0D8h+var_78]
0x180018a3c  xor     edx, edx; length
0x180018a3e  mov     rcx, r14; string
0x180018a41  call    cs:__imp_WindowsGetStringRawBuffer
0x180018a47  mov     [rsp+0D8h+var_78], rax
0x180018a4c  xor     edx, edx; length
0x180018a4e  mov     rcx, [rsp+0D8h+string]; string
0x180018a53  call    cs:__imp_WindowsGetStringRawBuffer
0x180018a59  mov     [rsp+0D8h+var_80], rax
0x180018a5e  lea     rax, [rsp+0D8h+var_50]
0x180018a66  mov     [rsp+0D8h+var_B0], rax
0x180018a6b  lea     rax, [rsp+0D8h+var_A0]
0x180018a70  mov     qword ptr [rsp+0D8h+var_B8], rax
0x180018a75  lea     r9, [rsp+0D8h+var_9C]
0x180018a7a  lea     r8, [rsp+0D8h+var_70]
0x180018a7f  lea     rdx, [rsp+0D8h+var_78]
0x180018a84  lea     rcx, [rsp+0D8h+var_80]
0x180018a89  call    ??$ToastActivationStop@PEBGPEBGAEAPEAUHSTRING__@@AEAIAEAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@WpnClientTelemetry@@SAX$$QEAPEBG0AEAPEAUHSTRING__@@AEAIAEAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; WpnClientTelemetry::ToastActivationStop<ushort const *,ushort const *,HSTRING__ * &,uint &,long &,std::string &>(ushort const * &&,ushort const * &&,HSTRING__ * &,uint &,long &,std::string &)
0x180018a8e  nop
0x180018a8f  lea     rcx, [rsp+0D8h+var_50]
0x180018a97  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180018a9c  mov     eax, r15d
0x180018a9f  mov     rcx, [rsp+0D8h+var_30]
0x180018aa7  xor     rcx, rsp; StackCookie
0x180018aaa  call    __security_check_cookie
0x180018aaf  mov     rbx, [rsp+0D8h+arg_0]
0x180018ab7  add     rsp, 0B0h
0x180018abe  pop     r15
0x180018ac0  pop     r14
0x180018ac2  pop     r12
0x180018ac4  pop     rdi
0x180018ac5  pop     rsi
0x180018ac6  retn
```
