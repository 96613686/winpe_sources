# ApplicationTheme::AppThemeApiImplementation::GetSingletonEventSource(ApplicationTheme::ThemeColorsChangedEvent * *)

- ea: `0x180013950`
- end: `0x180013f0b`
- name: `?GetSingletonEventSource@AppThemeApiImplementation@ApplicationTheme@@EEAAJPEAPEAVThemeColorsChangedEvent@2@@Z`
- size: `1467`
- prototype: `__int64 __fastcall(ApplicationTheme::AppThemeApiImplementation *__hidden this, struct ApplicationTheme::ThemeColorsChangedEvent **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180013950`
- `0x180013f14`
- `0x180013f40`
- `0x18003729c`
- `0x180045dec`
- `0x180049824`
- `0x180054130`
- `0x180059b4c`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013c62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013cee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013d54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013c62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013cee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013d54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ba7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ba7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013a6a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800139db`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800139db`

## pseudocode

```c
__int64 __fastcall ApplicationTheme::AppThemeApiImplementation::GetSingletonEventSource(
        ApplicationTheme::AppThemeApiImplementation *this,
        struct ApplicationTheme::ThemeColorsChangedEvent **a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rdi
  int v11; // eax
  int v12; // ebx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  struct ApplicationTheme::ThemeColorsChangedEvent *v16; // rax
  __int64 v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v19; // rcx
  ApplicationTheme::ThemeColorsChangedEvent *v21; // rax
  __int64 v22; // rbx
  int v23; // edi
  __int64 v24; // rbx
  struct ApplicationTheme::ThemeColorsChangedEvent *v25; // rcx
  __int64 (__fastcall *v26)(__int64, HSTRING, struct ApplicationTheme::ThemeColorsChangedEvent **); // rdi
  struct ApplicationTheme::ThemeColorsChangedEvent *v27; // rcx
  struct ApplicationTheme::ThemeColorsChangedEvent *v28; // r8
  int v29; // eax
  unsigned int v30; // ebx
  struct ApplicationTheme::ThemeColorsChangedEvent *v31; // rcx
  __int64 v32; // rcx
  struct ApplicationTheme::ThemeColorsChangedEvent *v33; // rcx
  struct ApplicationTheme::ThemeColorsChangedEvent *v34; // rcx
  __int64 v35; // rcx
  __int64 (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v37; // rcx
  __int64 (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v39; // rcx
  int v40; // [rsp+20h] [rbp-49h]
  char v41[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v42; // [rsp+38h] [rbp-31h] BYREF
  struct ApplicationTheme::ThemeColorsChangedEvent *v43; // [rsp+40h] [rbp-29h] BYREF
  __int64 v44; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-19h] BYREF
  struct ApplicationTheme::ThemeColorsChangedEvent *v46; // [rsp+58h] [rbp-11h] BYREF
  ApplicationTheme::ThemeColorsChangedEvent *v47; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER v48; // [rsp+68h] [rbp-1h] BYREF
  HSTRING v49; // [rsp+80h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+1Fh] BYREF
  HSTRING string; // [rsp+A0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a2 = 0;
  v42 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_17b0e613_942a_422d_904c_f90dc71a7dae, &v42);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v40);
    v32 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      return v7;
    }
    return v7;
  }
  v45 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v42 + 56LL))(
         v42,
         &v45);
  v7 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)v8,
      v40);
    v38 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v45;
    if ( v45 )
    {
      v45 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v38)[2])(v38);
    }
    v39 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    return v7;
  }
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v45;
  v44 = 0;
  v10 = **v45;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
  v11 = v10(v9, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v44);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)v11,
      v40);
    goto LABEL_54;
  }
  v49 = 0;
  v13 = WindowsCreateStringReference(L"ApplicationTheme.ThemeColorsChangedEvent", 0x28u, &v48, &v49);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    __debugbreak();
  }
  v43 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct ApplicationTheme::ThemeColorsChangedEvent **))(*(_QWORD *)v44 + 48LL))(
          v44,
          v49,
          &v43);
  if ( v12 != -2147483637 )
  {
LABEL_7:
    if ( v12 >= 0 )
    {
      v16 = v43;
      v17 = v44;
      v43 = 0;
      *a2 = v16;
      v49 = 0;
      if ( v17 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v45;
      if ( v45 )
      {
        v45 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v18)[2])(v18);
      }
      v19 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)v12,
      v40);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
    v49 = 0;
LABEL_54:
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
    return (unsigned int)v12;
  }
  v46 = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v46);
  v46 = 0;
  v21 = (ApplicationTheme::ThemeColorsChangedEvent *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v47 = v21;
  if ( !v21 )
  {
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>(&v47);
    v23 = -2147024882;
    goto LABEL_52;
  }
  v22 = ApplicationTheme::ThemeColorsChangedEvent::ThemeColorsChangedEvent(v21);
  v23 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ApplicationTheme::ThemeColorsChangedEvent **))v22)(
          v22,
          &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
          &v46);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v23 < 0 )
  {
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
      (const char *)(unsigned int)v23,
      v40);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
    v49 = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
    return (unsigned int)v23;
  }
  AcquireSRWLockExclusive(&ApplicationTheme::ThemeColorsChangedEvent::_singletonLock);
  v24 = v44;
  v25 = v43;
  v26 = *(__int64 (__fastcall **)(__int64, HSTRING, struct ApplicationTheme::ThemeColorsChangedEvent **))(*(_QWORD *)v44 + 48LL);
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v12 = v26(v24, v49, &v43);
  if ( v12 != -2147483637 )
  {
LABEL_27:
    ReleaseSRWLockExclusive(&ApplicationTheme::ThemeColorsChangedEvent::_singletonLock);
    v31 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v31 + 16LL))(v31);
    }
    goto LABEL_7;
  }
  v27 = v43;
  v41[0] = 0;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v46;
  if ( v46 )
  {
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v46 + 8LL))(v46);
    v28 = v46;
  }
  v43 = v28;
  v29 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct ApplicationTheme::ThemeColorsChangedEvent *, char *))(*(_QWORD *)v44 + 80LL))(
          v44,
          v49,
          v28,
          v41);
  v30 = v29;
  if ( v29 >= 0 )
  {
    if ( v41[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
        (const char *)0x8000FFFFLL,
        v40);
      ReleaseSRWLockExclusive(&ApplicationTheme::ThemeColorsChangedEvent::_singletonLock);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
      v49 = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v42);
      return 2147549183LL;
    }
    v12 = 0;
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18A,
    (unsigned int)"shell\\windowsuiimmersive\\appthemeapi\\lib\\appthemeapiimplementation.cpp",
    (const char *)(unsigned int)v29,
    v40);
  ReleaseSRWLockExclusive(&ApplicationTheme::ThemeColorsChangedEvent::_singletonLock);
  v33 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(struct ApplicationTheme::ThemeColorsChangedEvent *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v44;
  v49 = 0;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v45;
  if ( v45 )
  {
    v45 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v36)[2])(v36);
  }
  v37 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return v30;
}

```

## disassembly

```asm
0x180013950  push    rbp
0x180013952  push    rsi
0x180013953  push    r14
0x180013955  lea     rbp, [rsp-47h]
0x18001395a  sub     rsp, 0B0h
0x180013961  mov     rax, cs:__security_cookie
0x180013968  xor     rax, rsp
0x18001396b  mov     [rbp+57h+var_18], rax
0x18001396f  xor     r14d, r14d
0x180013972  lea     r9, [rbp+57h+string]; string
0x180013976  mov     [rdx], r14
0x180013979  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001397d  mov     rsi, rdx
0x180013980  mov     [rbp+57h+var_88], r14
0x180013984  mov     edx, 2Dh ; '-'; length
0x180013989  mov     [rbp+57h+string], r14
0x18001398d  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180013994  call    cs:__imp_WindowsCreateStringReference
0x18001399b  nop     dword ptr [rax+rax+00h]
0x1800139a0  test    eax, eax
0x1800139a2  js      loc_180013E39
0x1800139a8  mov     rcx, [rbp+57h+var_88]
0x1800139ac  mov     [rsp+0C0h+arg_0], rbx
0x1800139b4  mov     rbx, [rbp+57h+string]
0x1800139b8  test    rcx, rcx
0x1800139bb  jz      short loc_1800139CD
0x1800139bd  mov     [rbp+57h+var_88], r14
0x1800139c1  mov     rax, [rcx]
0x1800139c4  mov     rax, [rax+10h]
0x1800139c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139cd  lea     r8, [rbp+57h+var_88]
0x1800139d1  mov     rcx, rbx
0x1800139d4  lea     rdx, _GUID_17b0e613_942a_422d_904c_f90dc71a7dae
0x1800139db  call    cs:__imp_RoGetActivationFactory
0x1800139e2  nop     dword ptr [rax+rax+00h]
0x1800139e7  mov     ebx, eax
0x1800139e9  test    eax, eax
0x1800139eb  js      loc_180013C90
0x1800139f1  mov     rcx, [rbp+57h+var_88]
0x1800139f5  lea     rdx, [rbp+57h+var_70]
0x1800139f9  mov     [rbp+57h+var_70], r14
0x1800139fd  mov     rax, [rcx]
0x180013a00  mov     rax, [rax+38h]
0x180013a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a09  mov     ebx, eax
0x180013a0b  test    eax, eax
0x180013a0d  js      loc_180013DE8
0x180013a13  mov     rbx, [rbp+57h+var_70]
0x180013a17  lea     rcx, [rbp+57h+var_78]
0x180013a1b  mov     [rbp+57h+var_78], r14
0x180013a1f  mov     [rsp+0C0h+arg_10], rdi
0x180013a27  mov     rax, [rbx]
0x180013a2a  mov     rdi, [rax]
0x180013a2d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013a32  lea     r8, [rbp+57h+var_78]
0x180013a36  mov     rcx, rbx
0x180013a39  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x180013a40  mov     rax, rdi
0x180013a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a48  mov     ebx, eax
0x180013a4a  test    eax, eax
0x180013a4c  js      loc_180013E41
0x180013a52  lea     r9, [rbp+57h+var_40]; string
0x180013a56  mov     [rbp+57h+var_40], r14
0x180013a5a  lea     r8, [rbp+57h+var_58]; hstringHeader
0x180013a5e  mov     edx, 28h ; '('; length
0x180013a63  lea     rcx, aApplicationthe; "ApplicationTheme.ThemeColorsChangedEven"...
0x180013a6a  call    cs:__imp_WindowsCreateStringReference
0x180013a71  nop     dword ptr [rax+rax+00h]
0x180013a76  test    eax, eax
0x180013a78  js      loc_180013E5E
0x180013a7e  mov     rcx, [rbp+57h+var_78]
0x180013a82  lea     r8, [rbp+57h+var_80]
0x180013a86  mov     rdx, [rbp+57h+var_40]
0x180013a8a  mov     [rbp+57h+var_80], r14
0x180013a8e  mov     rax, [rcx]
0x180013a91  mov     rax, [rax+30h]
0x180013a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a9a  mov     ebx, eax
0x180013a9c  cmp     eax, 8000000Bh
0x180013aa1  jz      loc_180013B34
0x180013aa7  test    ebx, ebx
0x180013aa9  js      loc_180013EC4
0x180013aaf  mov     rax, [rbp+57h+var_80]
0x180013ab3  mov     rcx, [rbp+57h+var_78]
0x180013ab7  mov     [rbp+57h+var_80], r14
0x180013abb  mov     [rsi], rax
0x180013abe  mov     [rbp+57h+var_40], r14
0x180013ac2  test    rcx, rcx
0x180013ac5  jz      short loc_180013AD7
0x180013ac7  mov     [rbp+57h+var_78], r14
0x180013acb  mov     rax, [rcx]
0x180013ace  mov     rax, [rax+10h]
0x180013ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ad7  mov     rcx, [rbp+57h+var_70]
0x180013adb  test    rcx, rcx
0x180013ade  jz      short loc_180013AF0
0x180013ae0  mov     [rbp+57h+var_70], r14
0x180013ae4  mov     rax, [rcx]
0x180013ae7  mov     rax, [rax+10h]
0x180013aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013af0  mov     rcx, [rbp+57h+var_88]
0x180013af4  test    rcx, rcx
0x180013af7  jz      short loc_180013B09
0x180013af9  mov     [rbp+57h+var_88], r14
0x180013afd  mov     rax, [rcx]
0x180013b00  mov     rax, [rax+10h]
0x180013b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b09  xor     eax, eax
0x180013b0b  mov     rdi, [rsp+0C0h+arg_10]
0x180013b13  mov     rbx, [rsp+0C0h+arg_0]
0x180013b1b  mov     rcx, [rbp+57h+var_18]
0x180013b1f  xor     rcx, rsp; StackCookie
0x180013b22  call    __security_check_cookie
0x180013b27  add     rsp, 0B0h
0x180013b2e  pop     r14
0x180013b30  pop     rsi
0x180013b31  pop     rbp
0x180013b32  retn
0x180013b34  lea     rcx, [rbp+57h+var_68]
0x180013b38  mov     [rbp+57h+var_68], r14
0x180013b3c  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013b41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013b48  mov     [rbp+57h+var_68], r14
0x180013b4c  mov     ecx, 78h ; 'x'; unsigned __int64
0x180013b51  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013b56  mov     [rbp+57h+var_60], rax
0x180013b5a  test    rax, rax
0x180013b5d  jz      loc_180013E66
0x180013b63  mov     rcx, rax; this
0x180013b66  call    ??0ThemeColorsChangedEvent@ApplicationTheme@@QEAA@XZ; ApplicationTheme::ThemeColorsChangedEvent::ThemeColorsChangedEvent(void)
0x180013b6b  mov     rbx, rax
0x180013b6e  lea     r8, [rbp+57h+var_68]
0x180013b72  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180013b79  mov     rcx, [rax]
0x180013b7c  mov     rax, [rcx]
0x180013b7f  mov     rcx, rbx
0x180013b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b87  mov     rcx, [rbx]
0x180013b8a  mov     edi, eax
0x180013b8c  mov     rax, [rcx+10h]
0x180013b90  mov     rcx, rbx
0x180013b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b98  test    edi, edi
0x180013b9a  js      loc_180013E74
0x180013ba0  lea     rcx, ?_singletonLock@ThemeColorsChangedEvent@ApplicationTheme@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180013ba7  call    cs:__imp_AcquireSRWLockExclusive
0x180013bae  nop     dword ptr [rax+rax+00h]
0x180013bb3  mov     rbx, [rbp+57h+var_78]
0x180013bb7  mov     rcx, [rbp+57h+var_80]
0x180013bbb  mov     rax, [rbx]
0x180013bbe  mov     rdi, [rax+30h]
0x180013bc2  test    rcx, rcx
0x180013bc5  jz      short loc_180013BD7
0x180013bc7  mov     [rbp+57h+var_80], r14
0x180013bcb  mov     rdx, [rcx]
0x180013bce  mov     rax, [rdx+10h]
0x180013bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bd7  mov     rdx, [rbp+57h+var_40]
0x180013bdb  lea     r8, [rbp+57h+var_80]
0x180013bdf  mov     rcx, rbx
0x180013be2  mov     rax, rdi
0x180013be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bea  mov     ebx, eax
0x180013bec  cmp     eax, 8000000Bh
0x180013bf1  jnz     short loc_180013C5B
0x180013bf3  mov     rcx, [rbp+57h+var_80]
0x180013bf7  mov     [rbp+57h+var_90], r14b
0x180013bfb  test    rcx, rcx
0x180013bfe  jz      short loc_180013C10
0x180013c00  mov     [rbp+57h+var_80], r14
0x180013c04  mov     rax, [rcx]
0x180013c07  mov     rax, [rax+10h]
0x180013c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c10  mov     r8, [rbp+57h+var_68]
0x180013c14  test    r8, r8
0x180013c17  jz      short loc_180013C2C
0x180013c19  mov     rax, [r8]
0x180013c1c  mov     rcx, r8
0x180013c1f  mov     rax, [rax+8]
0x180013c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c28  mov     r8, [rbp+57h+var_68]
0x180013c2c  mov     rcx, [rbp+57h+var_78]
0x180013c30  lea     r9, [rbp+57h+var_90]
0x180013c34  mov     rdx, [rbp+57h+var_40]
0x180013c38  mov     [rbp+57h+var_80], r8
0x180013c3c  mov     rax, [rcx]
0x180013c3f  mov     rax, [rax+50h]
0x180013c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c48  mov     ebx, eax
0x180013c4a  test    eax, eax
0x180013c4c  js      loc_180013D35
0x180013c52  cmp     [rbp+57h+var_90], r14b
0x180013c56  jnz     short loc_180013CCC
0x180013c58  mov     ebx, r14d
0x180013c5b  lea     rcx, ?_singletonLock@ThemeColorsChangedEvent@ApplicationTheme@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180013c62  call    cs:__imp_ReleaseSRWLockExclusive
0x180013c69  nop     dword ptr [rax+rax+00h]
0x180013c6e  mov     rcx, [rbp+57h+var_68]
0x180013c72  test    rcx, rcx
0x180013c75  jz      loc_180013AA7
0x180013c7b  mov     [rbp+57h+var_68], r14
0x180013c7f  mov     rax, [rcx]
0x180013c82  mov     rax, [rax+10h]
0x180013c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c8b  jmp     loc_180013AA7
0x180013c90  mov     rcx, [rbp+5Fh]; this
0x180013c94  lea     r8, aShellWindowsui_19; "shell\\windowsuiimmersive\\appthemeapi"...
0x180013c9b  mov     r9d, ebx; char *
0x180013c9e  mov     edx, 16Bh; void *
0x180013ca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ca8  mov     rcx, [rbp+57h+var_88]
0x180013cac  test    rcx, rcx
0x180013caf  jz      loc_180013E32
0x180013cb5  mov     [rbp+57h+var_88], r14
0x180013cb9  mov     rax, [rcx]
0x180013cbc  mov     rax, [rax+10h]
0x180013cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cc5  mov     eax, ebx
0x180013cc7  jmp     loc_180013B13
0x180013ccc  mov     rcx, [rbp+5Fh]; this
0x180013cd0  lea     r8, aShellWindowsui_19; "shell\\windowsuiimmersive\\appthemeapi"...
0x180013cd7  mov     r9d, 8000FFFFh; char *
0x180013cdd  mov     edx, 18Bh; void *
0x180013ce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ce7  lea     rcx, ?_singletonLock@ThemeColorsChangedEvent@ApplicationTheme@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180013cee  call    cs:__imp_ReleaseSRWLockExclusive
0x180013cf5  nop     dword ptr [rax+rax+00h]
0x180013cfa  lea     rcx, [rbp+57h+var_68]
0x180013cfe  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013d03  lea     rcx, [rbp+57h+var_80]
0x180013d07  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013d0c  lea     rcx, [rbp+57h+var_78]
0x180013d10  mov     [rbp+57h+var_40], r14
0x180013d14  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013d19  lea     rcx, [rbp+57h+var_70]
0x180013d1d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013d22  lea     rcx, [rbp+57h+var_88]
0x180013d26  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180013d2b  mov     eax, 8000FFFFh
0x180013d30  jmp     loc_180013B0B
0x180013d35  mov     rcx, [rbp+5Fh]; this
0x180013d39  lea     r8, aShellWindowsui_19; "shell\\windowsuiimmersive\\appthemeapi"...
0x180013d40  mov     r9d, ebx; char *
0x180013d43  mov     edx, 18Ah; void *
0x180013d48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013d4d  lea     rcx, ?_singletonLock@ThemeColorsChangedEvent@ApplicationTheme@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x180013d54  call    cs:__imp_ReleaseSRWLockExclusive
0x180013d5b  nop     dword ptr [rax+rax+00h]
0x180013d60  mov     rcx, [rbp+57h+var_68]
0x180013d64  test    rcx, rcx
0x180013d67  jz      short loc_180013D79
0x180013d69  mov     [rbp+57h+var_68], r14
0x180013d6d  mov     rax, [rcx]
0x180013d70  mov     rax, [rax+10h]
0x180013d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d79  mov     rcx, [rbp+57h+var_80]
0x180013d7d  test    rcx, rcx
0x180013d80  jz      short loc_180013D92
0x180013d82  mov     [rbp+57h+var_80], r14
0x180013d86  mov     rax, [rcx]
0x180013d89  mov     rax, [rax+10h]
0x180013d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d92  mov     rcx, [rbp+57h+var_78]
0x180013d96  mov     [rbp+57h+var_40], r14
0x180013d9a  test    rcx, rcx
0x180013d9d  jz      short loc_180013DAF
0x180013d9f  mov     [rbp+57h+var_78], r14
0x180013da3  mov     rax, [rcx]
0x180013da6  mov     rax, [rax+10h]
0x180013daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013daf  mov     rcx, [rbp+57h+var_70]
0x180013db3  test    rcx, rcx
0x180013db6  jz      short loc_180013DC8
0x180013db8  mov     [rbp+57h+var_70], r14
0x180013dbc  mov     rax, [rcx]
0x180013dbf  mov     rax, [rax+10h]
0x180013dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc8  mov     rcx, [rbp+57h+var_88]
0x180013dcc  test    rcx, rcx
0x180013dcf  jz      short loc_180013DE1
0x180013dd1  mov     [rbp+57h+var_88], r14
0x180013dd5  mov     rax, [rcx]
0x180013dd8  mov     rax, [rax+10h]
0x180013ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013de1  mov     eax, ebx
0x180013de3  jmp     loc_180013B0B
0x180013de8  mov     rcx, [rbp+5Fh]; this
0x180013dec  lea     r8, aShellWindowsui_19; "shell\\windowsuiimmersive\\appthemeapi"...
0x180013df3  mov     r9d, ebx; char *
0x180013df6  mov     edx, 16Eh; void *
0x180013dfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e00  mov     rcx, [rbp+57h+var_70]
0x180013e04  test    rcx, rcx
0x180013e07  jz      short loc_180013E19
0x180013e09  mov     [rbp+57h+var_70], r14
0x180013e0d  mov     rax, [rcx]
0x180013e10  mov     rax, [rax+10h]
0x180013e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e19  mov     rcx, [rbp+57h+var_88]
  ... truncated ...
```
