# Windows::UI::Input::KeyboardDeliveryInterceptorImpl::put_IsInterceptionEnabledWhenInForeground(uchar)

- ea: `0x1800bfda0`
- end: `0x1800c0263`
- name: `?put_IsInterceptionEnabledWhenInForeground@KeyboardDeliveryInterceptorImpl@Input@UI@Windows@@EEAAJE@Z`
- size: `1219`
- prototype: `__int64 __fastcall(Windows::UI::Input::KeyboardDeliveryInterceptorImpl *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180004dd4`
- `0x180014754`
- `0x18002eaa0`
- `0x180036998`
- `0x18004fa88`
- `0x1800581b8`
- `0x1800618d0`
- `0x1800bfda0`
- `0x1800c62c0`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bfdd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bfdd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfe18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfe18`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c01bf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c01bf`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x1800c020e`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x1800c020e`
- `twinapi.appcore!__imp_CoreUnregisterWindowService` at `0x1800c0237`
- `twinapi.appcore!__imp_CoreUnregisterWindowService` at `0x1800c0237`
- `ext-ms-win-rtcore-ntuser-inputintercept-l1-1-0!__imp_EnableModernAppWindowKeyboardIntercept` at `0x1800bfe03`
- `ext-ms-win-rtcore-ntuser-inputintercept-l1-1-0!__imp_EnableModernAppWindowKeyboardIntercept` at `0x1800bfe03`

## string_xrefs

- `0x1800c01a4`: `Access to IsInterceptionEnabledWhenInForeground requires the inputForegroundObservation capability to be defined in the app manifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::KeyboardDeliveryInterceptorImpl::put_IsInterceptionEnabledWhenInForeground(
        Windows::UI::Input::KeyboardDeliveryInterceptorImpl *this,
        unsigned __int8 a2)
{
  unsigned int v2; // r14d
  char *v4; // rbx
  bool v5; // di
  const char *v6; // r9
  unsigned int LastError; // ebx
  HWND v9; // rdx
  void **v10; // r9
  int CoreApplicationViewForWindow; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v14; // eax
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rdi
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // [rsp+20h] [rbp-60h] BYREF
  __int64 v26; // [rsp+28h] [rbp-58h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-50h] BYREF
  struct _GUID v28; // [rsp+38h] [rbp-48h] BYREF
  __int64 v29; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v31; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v2 = a2;
  v4 = (char *)this + 80;
  AcquireSRWLockExclusive((PSRWLOCK)this + 10);
  *(_QWORD *)v28.Data4 = v4;
  if ( (_BYTE)v2 == *((_BYTE *)this + 88) )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
    return 0;
  }
  if ( (unsigned __int8)IsEnableModernAppWindowKeyboardInterceptPresent() )
  {
    if ( (unsigned int)EnableModernAppWindowKeyboardIntercept(*((_QWORD *)this + 9), v2) )
    {
      v5 = 1;
      goto LABEL_23;
    }
    v5 = 0;
    if ( GetLastError() != 12 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x36,
                    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
                    v6);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
      return LastError;
    }
  }
  else
  {
    *(_QWORD *)&v28.Data1 = 0;
    v27 = 0;
    v26 = 0;
    v25 = 0;
    v29 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
    CoreApplicationViewForWindow = CallerIdentity::GetCoreApplicationViewForWindow(
                                     *((CallerIdentity **)this + 9),
                                     v9,
                                     &v28,
                                     v10);
    LastError = CoreApplicationViewForWindow;
    if ( CoreApplicationViewForWindow < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
        (const char *)(unsigned int)CoreApplicationViewForWindow,
        v25);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
      return LastError;
    }
    v12 = *(_QWORD *)&v28.Data1;
    v13 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**(_QWORD **)&v28.Data1
                                                                                                  + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
    v14 = v13(v12, &v27);
    LastError = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
        (const char *)(unsigned int)v14,
        v25);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
      return LastError;
    }
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
    v16 = **v27;
    Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v26);
    v17 = v16(v15, &GUID_a9d00ab3_2fef_41a0_b0ad_4b2129ea2663, &v26);
    LastError = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
        (const char *)(unsigned int)v17,
        v25);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
      return LastError;
    }
    v18 = v26;
    v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
    v20 = v19(v18, &v25);
    LastError = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
        (const char *)(unsigned int)v20,
        v25);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
      return LastError;
    }
    v21 = Microsoft::WRL::ComPtr<Windows::UI::Core::ITextInputProducer>::As<ITextInputProducerInternal>(&v25, &v29);
    LastError = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
        (const char *)(unsigned int)v21,
        v25);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
      return LastError;
    }
    LOWORD(v22) = (_BYTE)v2 != 0 ? 7 : 0;
    LastError = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 64LL))(v29, v22);
    if ( (int)(LastError + 0x80000000) >= 0 && LastError != -2018375679 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
        (const char *)LastError,
        v25);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
      return LastError;
    }
    v5 = (LastError & 0x80000000) == 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
  }
LABEL_23:
  if ( !v5 )
  {
    v31 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Access to IsInterceptionEnabledWhenInForeground requires the inputForegroundObservation capability to be defined i"
       "n the app manifest",
      0x85u,
      0x84u);
    LastError = -2147024891;
    RoOriginateError(2147942405LL, v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
      (const char *)0x80070005LL,
      v25);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
    return LastError;
  }
  *((_BYTE *)this + 88) = v2;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v28.Data4);
  v23 = *((_QWORD *)this + 9);
  if ( !(_BYTE)v2 )
  {
    CoreUnregisterWindowService(v23, &GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f);
    return 0;
  }
  v24 = CoreRegisterWindowService(v23, &GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f, this);
  LastError = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\inputdeliveryintercepter\\kbddeliveryintercepter.cpp",
      (const char *)(unsigned int)v24,
      v25);
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x1800bfda0  mov     [rsp-18h+arg_10], rbx
0x1800bfda5  mov     [rsp-18h+arg_18], rsi
0x1800bfdaa  push    rbp
0x1800bfdab  push    rdi
0x1800bfdac  push    r14
0x1800bfdae  mov     rbp, rsp
0x1800bfdb1  sub     rsp, 80h
0x1800bfdb8  mov     rax, cs:__security_cookie
0x1800bfdbf  xor     rax, rsp
0x1800bfdc2  mov     [rbp+var_10], rax
0x1800bfdc6  movzx   r14d, dl
0x1800bfdca  mov     rsi, rcx
0x1800bfdcd  lea     rbx, [rcx+50h]
0x1800bfdd1  mov     rcx, rbx; SRWLock
0x1800bfdd4  call    cs:__imp_AcquireSRWLockExclusive
0x1800bfdda  mov     qword ptr [rbp+var_48.Data4], rbx
0x1800bfdde  cmp     r14b, [rsi+58h]
0x1800bfde2  jnz     short loc_1800BFDF3
0x1800bfde4  lea     rcx, [rbp+var_48.Data4]
0x1800bfde8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800bfded  nop
0x1800bfdee  jmp     loc_1800C023D
0x1800bfdf3  call    IsEnableModernAppWindowKeyboardInterceptPresent
0x1800bfdf8  test    al, al
0x1800bfdfa  jz      short loc_1800BFE4F
0x1800bfdfc  mov     edx, r14d
0x1800bfdff  mov     rcx, [rsi+48h]
0x1800bfe03  call    cs:__imp_EnableModernAppWindowKeyboardIntercept
0x1800bfe09  test    eax, eax
0x1800bfe0b  jz      short loc_1800BFE15
0x1800bfe0d  mov     dil, 1
0x1800bfe10  jmp     loc_1800C018D
0x1800bfe15  xor     dil, dil
0x1800bfe18  call    cs:__imp_GetLastError
0x1800bfe1e  cmp     eax, 0Ch
0x1800bfe21  jz      loc_1800C018D
0x1800bfe27  mov     rcx, [rbp+18h]; this
0x1800bfe2b  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800bfe32  mov     edx, 36h ; '6'; void *
0x1800bfe37  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800bfe3c  mov     ebx, eax
0x1800bfe3e  lea     rcx, [rbp+var_48.Data4]
0x1800bfe42  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800bfe47  nop
0x1800bfe48  mov     eax, ebx
0x1800bfe4a  jmp     loc_1800C023F
0x1800bfe4f  mov     qword ptr [rbp+var_48.Data1], 0
0x1800bfe57  mov     [rbp+var_50], 0
0x1800bfe5f  mov     [rbp+var_58], 0
0x1800bfe67  mov     [rbp+var_60], 0
0x1800bfe6f  mov     [rbp+var_38], 0
0x1800bfe77  lea     rcx, [rbp+var_48]
0x1800bfe7b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bfe80  lea     r8, [rbp+var_48]; struct _GUID *
0x1800bfe84  mov     rcx, [rsi+48h]; this
0x1800bfe88  call    ?GetCoreApplicationViewForWindow@CallerIdentity@@YAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z; CallerIdentity::GetCoreApplicationViewForWindow(HWND__ *,_GUID const &,void * *)
0x1800bfe8d  mov     ebx, eax
0x1800bfe8f  test    eax, eax
0x1800bfe91  jns     short loc_1800BFEE8
0x1800bfe93  mov     rcx, [rbp+18h]; this
0x1800bfe97  mov     r9d, eax; char *
0x1800bfe9a  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800bfea1  mov     edx, 42h ; 'B'; void *
0x1800bfea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bfeab  lea     rcx, [rbp+var_38]
0x1800bfeaf  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bfeb4  lea     rcx, [rbp+var_60]
0x1800bfeb8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bfebd  lea     rcx, [rbp+var_58]
0x1800bfec1  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800bfec6  lea     rcx, [rbp+var_50]
0x1800bfeca  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bfecf  lea     rcx, [rbp+var_48]
0x1800bfed3  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bfed8  nop
0x1800bfed9  lea     rcx, [rbp+var_48.Data4]
0x1800bfedd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800bfee2  nop
0x1800bfee3  jmp     loc_1800BFE48
0x1800bfee8  mov     rdi, qword ptr [rbp+var_48.Data1]
0x1800bfeec  mov     rax, [rdi]
0x1800bfeef  mov     rbx, [rax+30h]
0x1800bfef3  lea     rcx, [rbp+var_50]
0x1800bfef7  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bfefc  lea     rdx, [rbp+var_50]
0x1800bff00  mov     rcx, rdi
0x1800bff03  mov     rax, rbx
0x1800bff06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bff0b  mov     ebx, eax
0x1800bff0d  test    eax, eax
0x1800bff0f  jns     short loc_1800BFF66
0x1800bff11  mov     rcx, [rbp+18h]; this
0x1800bff15  mov     r9d, eax; char *
0x1800bff18  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800bff1f  mov     edx, 45h ; 'E'; void *
0x1800bff24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bff29  lea     rcx, [rbp+var_38]
0x1800bff2d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bff32  lea     rcx, [rbp+var_60]
0x1800bff36  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bff3b  lea     rcx, [rbp+var_58]
0x1800bff3f  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800bff44  lea     rcx, [rbp+var_50]
0x1800bff48  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bff4d  lea     rcx, [rbp+var_48]
0x1800bff51  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bff56  nop
0x1800bff57  lea     rcx, [rbp+var_48.Data4]
0x1800bff5b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800bff60  nop
0x1800bff61  jmp     loc_1800BFE48
0x1800bff66  mov     rbx, [rbp+var_50]
0x1800bff6a  mov     rax, [rbx]
0x1800bff6d  mov     rdi, [rax]
0x1800bff70  lea     rcx, [rbp+var_58]
0x1800bff74  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800bff79  lea     r8, [rbp+var_58]
0x1800bff7d  lea     rdx, _GUID_a9d00ab3_2fef_41a0_b0ad_4b2129ea2663
0x1800bff84  mov     rcx, rbx
0x1800bff87  mov     rax, rdi
0x1800bff8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bff8f  mov     ebx, eax
0x1800bff91  test    eax, eax
0x1800bff93  jns     short loc_1800BFFEA
0x1800bff95  mov     rcx, [rbp+18h]; this
0x1800bff99  mov     r9d, eax; char *
0x1800bff9c  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800bffa3  mov     edx, 46h ; 'F'; void *
0x1800bffa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bffad  lea     rcx, [rbp+var_38]
0x1800bffb1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bffb6  lea     rcx, [rbp+var_60]
0x1800bffba  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bffbf  lea     rcx, [rbp+var_58]
0x1800bffc3  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800bffc8  lea     rcx, [rbp+var_50]
0x1800bffcc  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bffd1  lea     rcx, [rbp+var_48]
0x1800bffd5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bffda  nop
0x1800bffdb  lea     rcx, [rbp+var_48.Data4]
0x1800bffdf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800bffe4  nop
0x1800bffe5  jmp     loc_1800BFE48
0x1800bffea  mov     rdi, [rbp+var_58]
0x1800bffee  mov     rax, [rdi]
0x1800bfff1  mov     rbx, [rax+30h]
0x1800bfff5  lea     rcx, [rbp+var_60]
0x1800bfff9  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800bfffe  lea     rdx, [rbp+var_60]
0x1800c0002  mov     rcx, rdi
0x1800c0005  mov     rax, rbx
0x1800c0008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c000d  mov     ebx, eax
0x1800c000f  test    eax, eax
0x1800c0011  jns     short loc_1800C0068
0x1800c0013  mov     rcx, [rbp+18h]; this
0x1800c0017  mov     r9d, eax; char *
0x1800c001a  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800c0021  mov     edx, 47h ; 'G'; void *
0x1800c0026  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c002b  lea     rcx, [rbp+var_38]
0x1800c002f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c0034  lea     rcx, [rbp+var_60]
0x1800c0038  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c003d  lea     rcx, [rbp+var_58]
0x1800c0041  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800c0046  lea     rcx, [rbp+var_50]
0x1800c004a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c004f  lea     rcx, [rbp+var_48]
0x1800c0053  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c0058  nop
0x1800c0059  lea     rcx, [rbp+var_48.Data4]
0x1800c005d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800c0062  nop
0x1800c0063  jmp     loc_1800BFE48
0x1800c0068  lea     rdx, [rbp+var_38]
0x1800c006c  lea     rcx, [rbp+var_60]
0x1800c0070  call    ??$As@UITextInputProducerInternal@@@?$ComPtr@UITextInputProducer@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UITextInputProducerInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ITextInputProducer>::As<ITextInputProducerInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ITextInputProducerInternal>>)
0x1800c0075  mov     ebx, eax
0x1800c0077  test    eax, eax
0x1800c0079  jns     short loc_1800C00D0
0x1800c007b  mov     rcx, [rbp+18h]; this
0x1800c007f  mov     r9d, eax; char *
0x1800c0082  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800c0089  mov     edx, 48h ; 'H'; void *
0x1800c008e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0093  lea     rcx, [rbp+var_38]
0x1800c0097  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c009c  lea     rcx, [rbp+var_60]
0x1800c00a0  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c00a5  lea     rcx, [rbp+var_58]
0x1800c00a9  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800c00ae  lea     rcx, [rbp+var_50]
0x1800c00b2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c00b7  lea     rcx, [rbp+var_48]
0x1800c00bb  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c00c0  nop
0x1800c00c1  lea     rcx, [rbp+var_48.Data4]
0x1800c00c5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800c00ca  nop
0x1800c00cb  jmp     loc_1800BFE48
0x1800c00d0  mov     rcx, [rbp+var_38]
0x1800c00d4  mov     r8, [rcx]
0x1800c00d7  mov     al, r14b
0x1800c00da  neg     al
0x1800c00dc  sbb     dx, dx
0x1800c00df  and     dx, 7
0x1800c00e3  mov     rax, [r8+40h]
0x1800c00e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c00ec  mov     ebx, eax
0x1800c00ee  mov     eax, 80000000h
0x1800c00f3  lea     ecx, [rbx+rax]
0x1800c00f6  test    eax, ecx
0x1800c00f8  jnz     short loc_1800C0157
0x1800c00fa  cmp     ebx, 87B20801h
0x1800c0100  jz      short loc_1800C0157
0x1800c0102  mov     rcx, [rbp+18h]; this
0x1800c0106  mov     r9d, ebx; char *
0x1800c0109  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800c0110  mov     edx, 5Ah ; 'Z'; void *
0x1800c0115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c011a  lea     rcx, [rbp+var_38]
0x1800c011e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c0123  lea     rcx, [rbp+var_60]
0x1800c0127  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c012c  lea     rcx, [rbp+var_58]
0x1800c0130  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800c0135  lea     rcx, [rbp+var_50]
0x1800c0139  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c013e  lea     rcx, [rbp+var_48]
0x1800c0142  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c0147  nop
0x1800c0148  lea     rcx, [rbp+var_48.Data4]
0x1800c014c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800c0151  nop
0x1800c0152  jmp     loc_1800BFE48
0x1800c0157  shr     ebx, 1Fh
0x1800c015a  mov     dil, 1
0x1800c015d  xor     dil, bl
0x1800c0160  lea     rcx, [rbp+var_38]
0x1800c0164  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c0169  lea     rcx, [rbp+var_60]
0x1800c016d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c0172  lea     rcx, [rbp+var_58]
0x1800c0176  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x1800c017b  lea     rcx, [rbp+var_50]
0x1800c017f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c0184  lea     rcx, [rbp+var_48]
0x1800c0188  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800c018d  test    dil, dil
0x1800c0190  jnz     short loc_1800C01ED
0x1800c0192  mov     [rbp+var_18], 0
0x1800c019a  mov     r9d, 84h; unsigned int
0x1800c01a0  lea     r8d, [r9+1]; unsigned int
0x1800c01a4  lea     rdx, aAccessToIsinte; "Access to IsInterceptionEnabledWhenInFo"...
0x1800c01ab  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800c01af  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c01b4  mov     rdx, [rbp+var_18]
0x1800c01b8  mov     ebx, 80070005h
0x1800c01bd  mov     ecx, ebx
0x1800c01bf  call    cs:__imp_RoOriginateError
0x1800c01c5  mov     rcx, [rbp+18h]; this
0x1800c01c9  mov     r9d, ebx; char *
0x1800c01cc  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800c01d3  mov     edx, 63h ; 'c'; void *
0x1800c01d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c01dd  nop
0x1800c01de  lea     rcx, [rbp+var_48.Data4]
0x1800c01e2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800c01e7  nop
0x1800c01e8  jmp     loc_1800BFE48
0x1800c01ed  mov     [rsi+58h], r14b
0x1800c01f1  lea     rcx, [rbp+var_48.Data4]
0x1800c01f5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800c01fa  nop
0x1800c01fb  mov     rcx, [rsi+48h]
0x1800c01ff  lea     rdx, _GUID_94b9c18a_727b_419e_ba04_9cc0ffe8642f
0x1800c0206  test    r14b, r14b
0x1800c0209  jz      short loc_1800C0237
0x1800c020b  mov     r8, rsi
0x1800c020e  call    cs:__imp_CoreRegisterWindowService
0x1800c0214  mov     ebx, eax
0x1800c0216  test    eax, eax
0x1800c0218  jns     short loc_1800C023D
0x1800c021a  mov     rcx, [rbp+18h]; this
0x1800c021e  mov     r9d, eax; char *
0x1800c0221  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\advcore\\winrt\\in"...
0x1800c0228  mov     edx, 71h ; 'q'; void *
0x1800c022d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0232  jmp     loc_1800BFE48
0x1800c0237  call    cs:__imp_CoreUnregisterWindowService
0x1800c023d  xor     eax, eax
0x1800c023f  mov     rcx, [rbp+var_10]
0x1800c0243  xor     rcx, rsp; StackCookie
0x1800c0246  call    __security_check_cookie
0x1800c024b  lea     r11, [rsp+80h+var_s0]
0x1800c0253  mov     rbx, [r11+30h]
0x1800c0257  mov     rsi, [r11+38h]
0x1800c025b  mov     rsp, r11
  ... truncated ...
```
