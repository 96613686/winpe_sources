# CApplicationManager::_HandleViewPropertyChanged(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,Windows::Internal::Shell::ViewManagerInterop::IViewPropertyChangedArgs *)

- ea: `0x1800fadfc`
- end: `0x1800fb429`
- name: `?_HandleViewPropertyChanged@CApplicationManager@@AEAAXPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@PEAUIViewPropertyChangedArgs@3456@@Z`
- size: `1581`
- prototype: `void(CApplicationManager *__hidden this, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *, struct Windows::Internal::Shell::ViewManagerInterop::IViewPropertyChangedArgs *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fa670`

## callees

- `0x1800134f8`
- `0x18001f6e0`
- `0x1800255d0`
- `0x180031200`
- `0x180031c70`
- `0x18005d940`
- `0x1800fa598`
- `0x1800fa5c8`
- `0x1800fadfc`
- `0x1800fb430`
- `0x180356360`
- `0x1803735c8`
- `0x1803737d0`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fafff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1806f3691`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800fafff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1806f3691`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fb07b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1806f370a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fb07b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1806f370a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb2c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb2d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb39f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb3b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb3d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb3e9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb40d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb2c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb2d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb39f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb3b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb3d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb3e9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800fb40d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800fae9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800faf12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800faf83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800fafd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800fae9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800faf12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800faf83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800fafd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fae80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800faef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800faf66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fafbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fb129`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fae80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800faef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800faf66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fafbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800fb129`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fae43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb286`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fae43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fb286`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb1d6`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800fb1d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall CApplicationManager::_HandleViewPropertyChanged(
        CApplicationManager *this,
        struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *a2,
        struct Windows::Internal::Shell::ViewManagerInterop::IViewPropertyChangedArgs *a3)
{
  int (__fastcall *v6)(struct Windows::Internal::Shell::ViewManagerInterop::IViewPropertyChangedArgs *, HSTRING *); // rbx
  HRESULT v7; // eax
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rdi
  unsigned int v10; // eax
  UINT32 v11; // edx
  HRESULT v12; // eax
  char v13; // al
  unsigned int v14; // eax
  UINT32 v15; // edx
  HRESULT v16; // eax
  char v17; // al
  HRESULT v18; // eax
  char v19; // al
  int First; // ebx
  void (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rdi
  PVOID Ptr; // rdi
  int (__fastcall *v24)(PVOID, __int64, __int64 *); // rbx
  __int64 v25; // rbx
  HRESULT v26; // eax
  unsigned int v27; // r14d
  __int64 v28; // r8
  void (__fastcall *v29)(char *, GUID *, __int64); // rbx
  __int64 v30; // rax
  HRESULT v31; // ebx
  IUnknown *v32; // rcx
  void *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  void (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // rcx
  void (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rdi
  void (__fastcall *v39)(_QWORD, GUID *, __int64 *); // rbx
  int v40; // eax
  wil::details::in1diag3 *v41; // rcx
  __int64 v42; // rdx
  CTaskWindowFinder *v43; // rax
  __int64 v44; // rax
  unsigned int v45; // ebx
  int v46; // [rsp+20h] [rbp-79h]
  INT32 result; // [rsp+30h] [rbp-69h] BYREF
  __int64 v48; // [rsp+38h] [rbp-61h] BYREF
  HSTRING string1; // [rsp+40h] [rbp-59h] BYREF
  __int64 v50; // [rsp+48h] [rbp-51h] BYREF
  void (__fastcall ***v51)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-49h] BYREF
  unsigned int v52; // [rsp+58h] [rbp-41h] BYREF
  int v53; // [rsp+5Ch] [rbp-3Dh]
  void *ppvOut; // [rsp+60h] [rbp-39h] BYREF
  __int64 v55; // [rsp+68h] [rbp-31h] BYREF
  IUnknown *punk; // [rsp+70h] [rbp-29h] BYREF
  __int64 v57; // [rsp+78h] [rbp-21h] BYREF
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v58; // [rsp+80h] [rbp-19h] BYREF
  char v59; // [rsp+88h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v53 = 0;
  string1 = 0;
  v6 = *(int (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewPropertyChangedArgs *, HSTRING *))(*(_QWORD *)a3 + 48LL);
  WindowsDeleteString(0);
  string1 = 0;
  if ( v6(a3, &string1) < 0 )
    goto LABEL_49;
  result = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"BackVisible", 0xBu, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  if ( WindowsCompareStringOrdinal(string1, string, &result) >= 0 && !result )
  {
    string = 0;
    AcquireSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
    v48 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    v43 = CTaskWindowFinder::CTaskWindowFinder((CTaskWindowFinder *)&v57, a2);
    v44 = CImmersiveAppFinderByTaskWindow::CImmersiveAppFinderByTaskWindow(&hstringHeader, v43, 0);
    v45 = (unsigned int)CApplicationManager::_FindFirstApplication<CImmersiveAppFinderByTaskWindow>(this, v44, &v48, 0) >> 31;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader.Reserved.Reserved2[8]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    if ( (unsigned __int8)v45 != 1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 208LL))(v48);
    ReleaseSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    goto LABEL_49;
  }
  string = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( aWindowframesty[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v10 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v9);
  v11 = v10 - 1;
  if ( (unsigned int)v9 < v10 )
    v11 = v9;
  v12 = WindowsCreateStringReference(L"WindowFrameStyle", v11, &hstringHeader, &string);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  v53 = 2;
  if ( WindowsCompareStringOrdinal(string1, string, &result) < 0 || (v13 = 1, result) )
    v13 = 0;
  if ( v13 )
  {
    v40 = CApplicationManager::_HandleUniversalFrameChangeRequest(this, a2);
    v41 = retaddr;
    if ( v40 >= 0 )
      goto LABEL_49;
    v42 = 6521;
LABEL_56:
    wil::details::in1diag3::_Log_Hr(
      v41,
      (void *)v42,
      (unsigned int)"pcshell\\twinui\\appmanager\\lib\\appmanager.cpp",
      (const char *)(unsigned int)v40,
      v46);
    goto LABEL_49;
  }
  string = 0;
  do
    ++v8;
  while ( aTitlebarvisibl[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v14 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
  v15 = v14 - 1;
  if ( (unsigned int)v8 < v14 )
    v15 = v8;
  v16 = WindowsCreateStringReference(L"TitleBarVisible", v15, &hstringHeader, &string);
  if ( v16 < 0 )
  {
    RaiseException(v16, 1u, 0, 0);
    __debugbreak();
  }
  if ( WindowsCompareStringOrdinal(string1, string, &result) < 0 || (v17 = 1, result) )
    v17 = 0;
  if ( v17 )
  {
    v40 = CApplicationManager::_HandleUniversalTitleBarVisibilityChangeRequest(this, a2);
    v41 = retaddr;
    if ( v40 >= 0 )
      goto LABEL_49;
    v42 = 6525;
    goto LABEL_56;
  }
  string = 0;
  v18 = WindowsCreateStringReference(L"FrameworkViewType", 0x11u, &hstringHeader, &string);
  if ( v18 < 0 )
  {
    RaiseException(v18, 1u, 0, 0);
    __debugbreak();
  }
  if ( WindowsCompareStringOrdinal(string1, string, &result) < 0 || (v19 = 1, result) )
    v19 = 0;
  string = 0;
  if ( v19 )
  {
    AcquireSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
    v51 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    v57 = 0;
    v58 = a2;
    Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v58);
    v59 = 0;
    hstringHeader.Reserved.Reserved1 = 0;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = a2;
    Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&hstringHeader.Reserved.Reserved2[8]);
    hstringHeader.Reserved.Reserved2[16] = 0;
    LODWORD(string) = 0;
    First = CApplicationManager::_FindFirstApplication<CImmersiveAppFinderByTaskWindow>(this, &hstringHeader, &v51, 0);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader.Reserved.Reserved2[8]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
    v48 = 0;
    if ( First >= 0 )
    {
      v38 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
      v39 = (*v51)[44];
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      First = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64, GUID *, __int64 *))v39)(
                v38,
                2,
                &GUID_3232bb1b_301e_409e_af1c_6d15fcc0ffee,
                &v48);
    }
    ReleaseSRWLockExclusive(CApplicationManagerUtility::g_pIAMGlobals);
    if ( First >= 0
      && (*(unsigned __int8 (__fastcall **)(__int64, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v48 + 48LL))(
           v48,
           a2) )
    {
      v55 = 0;
      v21 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
      v22 = **v51;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
      v22(v21, &GUID_8b14e88b_5663_4caf_b196_c31479262831, &v55);
      v50 = 0;
      Ptr = CApplicationManagerUtility::g_pIAMGlobals[14].Ptr;
      v24 = *(int (__fastcall **)(PVOID, __int64, __int64 *))(*(_QWORD *)Ptr + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
      if ( v24(Ptr, v55, &v50) >= 0 )
      {
        v52 = 0;
        v25 = *(_QWORD *)a2;
        string = 0;
        v26 = WindowsCreateStringReference(L"FrameworkViewType", 0x11u, &hstringHeader, &string);
        if ( v26 < 0 )
        {
          RaiseException(v26, 1u, 0, 0);
          __debugbreak();
        }
        if ( (*(int (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *, HSTRING, unsigned int *))(v25 + 368))(
               a2,
               string,
               &v52) >= 0 )
        {
          v27 = v52;
          if ( v52 )
          {
            v28 = 0;
            if ( v52 == 1 )
              v28 = 64;
          }
          else
          {
            v28 = 32;
          }
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v50 + 464LL))(v50, 96, v28);
          ppvOut = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
          punk = 0;
          v53 = 32;
          v29 = *(void (__fastcall **)(char *, GUID *, __int64))(*((_QWORD *)this + 6) + 32LL);
          v30 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(&punk);
          v29((char *)this + 48, &GUID_00000000_0000_0000_c000_000000000046, v30);
          v31 = IUnknown_QueryService(
                  punk,
                  &GUID_ff62716a_0bd0_4105_a6ec_83b09d864267,
                  &GUID_d452bf19_b505_4b1c_8182_1cc821a13092,
                  &ppvOut);
          v32 = punk;
          if ( punk )
          {
            punk = 0;
            ((void (__fastcall *)(IUnknown *))v32->lpVtbl->Release)(v32);
          }
          if ( v31 >= 0 )
            (*(void (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppvOut + 24LL))(ppvOut, v50, v27);
          v33 = ppvOut;
          if ( ppvOut )
          {
            ppvOut = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
          }
        }
      }
      v34 = v50;
      if ( v50 )
      {
        v50 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v35 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
    }
    v36 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v51;
    if ( v51 )
    {
      v51 = 0;
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v37)[2])(v37);
    }
  }
LABEL_49:
  WindowsDeleteString(string1);
}

```

## disassembly

```asm
0x1800fadfc  mov     [rsp-8+arg_18], rbx
0x1800fae01  push    rbp
0x1800fae02  push    rsi
0x1800fae03  push    rdi
0x1800fae04  push    r12
0x1800fae06  push    r13
0x1800fae08  push    r14
0x1800fae0a  push    r15
0x1800fae0c  lea     rbp, [rsp-27h]
0x1800fae11  sub     rsp, 0C0h
0x1800fae18  mov     rax, cs:__security_cookie
0x1800fae1f  xor     rax, rsp
0x1800fae22  mov     [rbp+57h+var_40], rax
0x1800fae26  mov     rdi, r8
0x1800fae29  mov     r14, rdx
0x1800fae2c  mov     r15, rcx
0x1800fae2f  xor     r12d, r12d
0x1800fae32  mov     [rbp+57h+var_94], r12d
0x1800fae36  mov     [rbp+57h+string1], r12
0x1800fae3a  mov     rax, [r8]
0x1800fae3d  mov     rbx, [rax+30h]
0x1800fae41  xor     ecx, ecx; string
0x1800fae43  call    cs:__imp_WindowsDeleteString
0x1800fae49  mov     [rbp+57h+string1], r12
0x1800fae4d  lea     rdx, [rbp+57h+string1]
0x1800fae51  mov     rcx, rdi
0x1800fae54  mov     rax, rbx
0x1800fae57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fae5c  test    eax, eax
0x1800fae5e  js      loc_1800FB282
0x1800fae64  mov     [rbp+57h+result], r12d
0x1800fae68  mov     [rbp+57h+string], r12
0x1800fae6c  lea     r9, [rbp+57h+string]; string
0x1800fae70  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800fae74  lea     edx, [r12+0Bh]; length
0x1800fae79  lea     rcx, aBackvisible; "BackVisible"
0x1800fae80  call    cs:__imp_WindowsCreateStringReference
0x1800fae86  test    eax, eax
0x1800fae88  js      loc_1800FB393
0x1800fae8e  lea     r8, [rbp+57h+result]; result
0x1800fae92  mov     rdx, [rbp+57h+string]; string2
0x1800fae96  mov     rcx, [rbp+57h+string1]; string1
0x1800fae9a  call    cs:__imp_WindowsCompareStringOrdinal
0x1800faea0  test    eax, eax
0x1800faea2  jns     loc_1806F367C
0x1800faea8  mov     [rbp+57h+string], r12
0x1800faeac  mov     [rbp+57h+string], r12
0x1800faeb0  mov     rsi, cs:off_180709E00; "WindowFrameStyle"
0x1800faeb7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800faebb  mov     rdi, rbx
0x1800faebe  inc     rdi
0x1800faec1  cmp     [rsi+rdi*2], r12w
0x1800faec6  jnz     short loc_1800FAEBE
0x1800faec8  mov     r13d, 0FFFFFFFFh
0x1800faece  cmp     rdi, r13
0x1800faed1  ja      loc_1800FB2C9
0x1800faed7  mov     ecx, edi; unsigned int
0x1800faed9  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800faede  lea     edx, [rax-1]
0x1800faee1  cmp     edi, eax
0x1800faee3  cmovb   edx, edi; length
0x1800faee6  lea     r9, [rbp+57h+string]; string
0x1800faeea  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800faeee  mov     rcx, rsi; sourceString
0x1800faef1  call    cs:__imp_WindowsCreateStringReference
0x1800faef7  test    eax, eax
0x1800faef9  js      loc_1800FB3A6
0x1800faeff  mov     [rbp+57h+var_94], 2
0x1800faf06  lea     r8, [rbp+57h+result]; result
0x1800faf0a  mov     rdx, [rbp+57h+string]; string2
0x1800faf0e  mov     rcx, [rbp+57h+string1]; string1
0x1800faf12  call    cs:__imp_WindowsCompareStringOrdinal
0x1800faf18  test    eax, eax
0x1800faf1a  jns     loc_1800FB3B9
0x1800faf20  mov     al, r12b
0x1800faf23  mov     esi, r12d
0x1800faf26  test    al, al
0x1800faf28  jnz     loc_1800FB345
0x1800faf2e  mov     [rbp+57h+string], r12
0x1800faf32  mov     rdi, cs:off_180709DF8; "TitleBarVisible"
0x1800faf39  inc     rbx
0x1800faf3c  cmp     [rdi+rbx*2], r12w
0x1800faf41  jnz     short loc_1800FAF39
0x1800faf43  cmp     rbx, r13
0x1800faf46  ja      loc_1800FB2B3
0x1800faf4c  mov     ecx, ebx; unsigned int
0x1800faf4e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800faf53  lea     edx, [rax-1]
0x1800faf56  cmp     ebx, eax
0x1800faf58  cmovb   edx, ebx; length
0x1800faf5b  lea     r9, [rbp+57h+string]; string
0x1800faf5f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800faf63  mov     rcx, rdi; sourceString
0x1800faf66  call    cs:__imp_WindowsCreateStringReference
0x1800faf6c  test    eax, eax
0x1800faf6e  js      loc_1800FB3CA
0x1800faf74  or      esi, 4
0x1800faf77  lea     r8, [rbp+57h+result]; result
0x1800faf7b  mov     rdx, [rbp+57h+string]; string2
0x1800faf7f  mov     rcx, [rbp+57h+string1]; string1
0x1800faf83  call    cs:__imp_WindowsCompareStringOrdinal
0x1800faf89  test    eax, eax
0x1800faf8b  jns     loc_1800FB2DF
0x1800faf91  mov     al, r12b
0x1800faf94  and     esi, 0FFFFFFFBh
0x1800faf97  test    al, al
0x1800faf99  jnz     loc_1800FB375
0x1800faf9f  mov     [rbp+57h+string], r12
0x1800fafa3  lea     r9, [rbp+57h+string]; string
0x1800fafa7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800fafab  mov     r13d, 11h
0x1800fafb1  mov     edx, r13d; length
0x1800fafb4  lea     rcx, aFrameworkviewt; "FrameworkViewType"
0x1800fafbb  call    cs:__imp_WindowsCreateStringReference
0x1800fafc1  test    eax, eax
0x1800fafc3  js      loc_1800FB3DD
0x1800fafc9  or      esi, 8
0x1800fafcc  lea     r8, [rbp+57h+result]; result
0x1800fafd0  mov     rdx, [rbp+57h+string]; string2
0x1800fafd4  mov     rcx, [rbp+57h+string1]; string1
0x1800fafd8  call    cs:__imp_WindowsCompareStringOrdinal
0x1800fafde  test    eax, eax
0x1800fafe0  jns     loc_1800FB3F0
0x1800fafe6  mov     al, r12b
0x1800fafe9  and     esi, 0FFFFFFF7h
0x1800fafec  mov     [rbp+57h+string], r12
0x1800faff0  test    al, al
0x1800faff2  jz      loc_1800FB282
0x1800faff8  mov     rcx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; SRWLock
0x1800fafff  call    cs:__imp_AcquireSRWLockExclusive
0x1800fb005  mov     [rbp+57h+var_A0], r12
0x1800fb009  lea     rcx, [rbp+57h+var_A0]
0x1800fb00d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fb012  mov     [rbp+57h+var_78], r12
0x1800fb016  mov     [rbp+57h+var_70], r14
0x1800fb01a  lea     rcx, [rbp+57h+var_70]
0x1800fb01e  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x1800fb023  mov     [rbp+57h+var_68], r12b
0x1800fb027  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r12
0x1800fb02b  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r14
0x1800fb02f  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]
0x1800fb033  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x1800fb038  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], r12b
0x1800fb03c  mov     dword ptr [rbp+57h+string], r12d
0x1800fb040  xor     r9d, r9d
0x1800fb043  lea     r8, [rbp+57h+var_A0]
0x1800fb047  lea     rdx, [rbp+57h+hstringHeader]
0x1800fb04b  mov     rcx, r15
0x1800fb04e  call    ??$_FindFirstApplication@VCImmersiveAppFinderByTaskWindow@@@CApplicationManager@@AEAAJAEBVCImmersiveAppFinderByTaskWindow@@PEAPEAUIImmersiveApplicationInternal@@PEA_K@Z; CApplicationManager::_FindFirstApplication<CImmersiveAppFinderByTaskWindow>(CImmersiveAppFinderByTaskWindow const &,IImmersiveApplicationInternal * *,unsigned __int64 *)
0x1800fb053  mov     ebx, eax
0x1800fb055  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]
0x1800fb059  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fb05e  nop
0x1800fb05f  lea     rcx, [rbp+57h+var_70]
0x1800fb063  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fb068  mov     [rbp+57h+var_B8], r12
0x1800fb06c  test    ebx, ebx
0x1800fb06e  jns     loc_1800FB30C
0x1800fb074  mov     rcx, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; SRWLock
0x1800fb07b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800fb081  test    ebx, ebx
0x1800fb083  js      loc_1800FB24E
0x1800fb089  mov     rcx, [rbp+57h+var_B8]
0x1800fb08d  mov     rax, [rcx]
0x1800fb090  mov     rdx, r14
0x1800fb093  mov     rax, [rax+30h]
0x1800fb097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb09c  test    al, al
0x1800fb09e  jz      loc_1800FB24E
0x1800fb0a4  mov     [rbp+57h+var_88], r12
0x1800fb0a8  mov     rbx, [rbp+57h+var_A0]
0x1800fb0ac  mov     rax, [rbx]
0x1800fb0af  mov     rdi, [rax]
0x1800fb0b2  lea     rcx, [rbp+57h+var_88]
0x1800fb0b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800fb0bb  lea     r8, [rbp+57h+var_88]
0x1800fb0bf  lea     rdx, _GUID_8b14e88b_5663_4caf_b196_c31479262831
0x1800fb0c6  mov     rcx, rbx
0x1800fb0c9  mov     rax, rdi
0x1800fb0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb0d1  nop
0x1800fb0d2  mov     [rbp+57h+var_A8], r12
0x1800fb0d6  mov     rax, cs:?g_pIAMGlobals@CApplicationManagerUtility@@3PEAVCIAMGlobals@@EA; CIAMGlobals * CApplicationManagerUtility::g_pIAMGlobals
0x1800fb0dd  mov     rdi, [rax+70h]
0x1800fb0e1  mov     rax, [rdi]
0x1800fb0e4  mov     rbx, [rax+38h]
0x1800fb0e8  lea     rcx, [rbp+57h+var_A8]
0x1800fb0ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800fb0f1  lea     r8, [rbp+57h+var_A8]
0x1800fb0f5  mov     rdx, [rbp+57h+var_88]
0x1800fb0f9  mov     rcx, rdi
0x1800fb0fc  mov     rax, rbx
0x1800fb0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb104  test    eax, eax
0x1800fb106  js      loc_1800FB21A
0x1800fb10c  mov     [rbp+57h+var_98], r12d
0x1800fb110  mov     rbx, [r14]
0x1800fb113  mov     [rbp+57h+string], r12
0x1800fb117  lea     r9, [rbp+57h+string]; string
0x1800fb11b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800fb11f  mov     edx, r13d; length
0x1800fb122  lea     rcx, aFrameworkviewt; "FrameworkViewType"
0x1800fb129  call    cs:__imp_WindowsCreateStringReference
0x1800fb12f  test    eax, eax
0x1800fb131  js      loc_1800FB401
0x1800fb137  lea     r8, [rbp+57h+var_98]
0x1800fb13b  mov     rdx, [rbp+57h+string]
0x1800fb13f  mov     rcx, r14
0x1800fb142  mov     rax, [rbx+170h]
0x1800fb149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb14e  nop
0x1800fb14f  test    eax, eax
0x1800fb151  js      loc_1800FB21A
0x1800fb157  mov     r14d, [rbp+57h+var_98]
0x1800fb15b  test    r14d, r14d
0x1800fb15e  jnz     loc_1800FB414
0x1800fb164  lea     r8d, [r14+20h]
0x1800fb168  mov     rcx, [rbp+57h+var_A8]
0x1800fb16c  mov     rax, [rcx]
0x1800fb16f  mov     edx, 60h ; '`'
0x1800fb174  mov     rax, [rax+1D0h]
0x1800fb17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb180  mov     [rbp+57h+ppvOut], r12
0x1800fb184  lea     rcx, [rbp+57h+ppvOut]
0x1800fb188  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800fb18d  nop
0x1800fb18e  mov     [rbp+57h+punk], r12
0x1800fb192  or      esi, 20h
0x1800fb195  mov     [rbp+57h+var_94], esi
0x1800fb198  mov     rax, [r15+30h]
0x1800fb19c  mov     rbx, [rax+20h]
0x1800fb1a0  lea     rcx, [rbp+57h+punk]
0x1800fb1a4  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIHolographicViewTransitionNotificationService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIHolographicViewTransitionNotificationService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>)
0x1800fb1a9  mov     r8, rax
0x1800fb1ac  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800fb1b3  lea     rcx, [r15+30h]
0x1800fb1b7  mov     rax, rbx
0x1800fb1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb1bf  nop
0x1800fb1c0  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x1800fb1c4  lea     r8, _GUID_d452bf19_b505_4b1c_8182_1cc821a13092; riid
0x1800fb1cb  lea     rdx, _GUID_ff62716a_0bd0_4105_a6ec_83b09d864267; guidService
0x1800fb1d2  mov     rcx, [rbp+57h+punk]; punk
0x1800fb1d6  call    cs:__imp_IUnknown_QueryService
0x1800fb1dc  mov     ebx, eax
0x1800fb1de  mov     rcx, [rbp+57h+punk]
0x1800fb1e2  test    rcx, rcx
0x1800fb1e5  jz      short loc_1800FB1F8
0x1800fb1e7  mov     [rbp+57h+punk], r12
0x1800fb1eb  mov     rdx, [rcx]
0x1800fb1ee  mov     rax, [rdx+10h]
0x1800fb1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb1f7  nop
0x1800fb1f8  test    ebx, ebx
0x1800fb1fa  jns     loc_1800FB2F0
0x1800fb200  mov     rcx, [rbp+57h+ppvOut]
0x1800fb204  test    rcx, rcx
0x1800fb207  jz      short loc_1800FB21A
0x1800fb209  mov     [rbp+57h+ppvOut], r12
0x1800fb20d  mov     rax, [rcx]
0x1800fb210  mov     rax, [rax+10h]
0x1800fb214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb219  nop
0x1800fb21a  mov     rcx, [rbp+57h+var_A8]
0x1800fb21e  test    rcx, rcx
0x1800fb221  jz      short loc_1800FB234
0x1800fb223  mov     [rbp+57h+var_A8], r12
0x1800fb227  mov     rax, [rcx]
0x1800fb22a  mov     rax, [rax+10h]
0x1800fb22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb233  nop
0x1800fb234  mov     rcx, [rbp+57h+var_88]
0x1800fb238  test    rcx, rcx
0x1800fb23b  jz      short loc_1800FB24E
0x1800fb23d  mov     [rbp+57h+var_88], r12
0x1800fb241  mov     rax, [rcx]
0x1800fb244  mov     rax, [rax+10h]
0x1800fb248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb24d  nop
0x1800fb24e  mov     rcx, [rbp+57h+var_B8]
0x1800fb252  test    rcx, rcx
0x1800fb255  jz      short loc_1800FB268
0x1800fb257  mov     [rbp+57h+var_B8], r12
0x1800fb25b  mov     rax, [rcx]
0x1800fb25e  mov     rax, [rax+10h]
0x1800fb262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb267  nop
0x1800fb268  mov     rcx, [rbp+57h+var_A0]
0x1800fb26c  test    rcx, rcx
0x1800fb26f  jz      short loc_1800FB282
0x1800fb271  mov     [rbp+57h+var_A0], r12
0x1800fb275  mov     rax, [rcx]
0x1800fb278  mov     rax, [rax+10h]
0x1800fb27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb281  nop
0x1800fb282  mov     rcx, [rbp+57h+string1]; string
0x1800fb286  call    cs:__imp_WindowsDeleteString
0x1800fb28c  mov     rcx, [rbp+57h+var_40]
0x1800fb290  xor     rcx, rsp; StackCookie
0x1800fb293  call    __security_check_cookie
  ... truncated ...
```
