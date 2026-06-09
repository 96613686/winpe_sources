# CShellExperienceDispatcher::QueueEvent(int,ushort const *,IUnknown *)

- ea: `0x18003eeb0`
- end: `0x18003f4e9`
- name: `?QueueEvent@CShellExperienceDispatcher@@UEAAJHPEBGPEAUIUnknown@@@Z`
- size: `1593`
- prototype: `int(CShellExperienceDispatcher *__hidden this, int, const unsigned __int16 *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000ae24`
- `0x18003c5e4`
- `0x18003c898`
- `0x18003eeb0`
- `0x18003f4f0`
- `0x18003fb88`
- `0x180061e78`
- `0x1800b8608`
- `0x18013d330`
- `0x18013f785`
- `0x18014c2e8`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ef95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003f260`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ef95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003f260`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003ef19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003ef19`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003f445`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003f445`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x18003f0f7`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x18003f0f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f2b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f2e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f3f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f000`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f2b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f2e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f3f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003f013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003f013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f07f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003f0a9`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18003f0a9`

## string_xrefs

- `0x18003f1de`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003f200`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003f2a3`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003f319`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003f393`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003f423`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003f453`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003f46d`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003f4b1`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CShellExperienceDispatcher::QueueEvent(
        CShellExperienceDispatcher *this,
        int a2,
        const unsigned __int16 *a3,
        struct IUnknown *a4)
{
  RTL_SRWLOCK *v7; // r13
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v8; // rsi
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // r8
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper ***v13; // rax
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v14; // rdi
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v15; // rbx
  unsigned __int64 v16; // rbx
  UINT32 v17; // edx
  const WCHAR *v18; // rcx
  unsigned int v19; // ebx
  struct Windows::Foundation::Collections::IPropertySet *v20; // r9
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v22; // eax
  HRESULT v23; // eax
  HSTRING v24; // rbx
  int v25; // eax
  int v26; // eax
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **v27; // rcx
  RTL_SRWLOCK *v28; // rcx
  int v29; // eax
  struct Windows::Foundation::Collections::IPropertySet *v30; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v31; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v33; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v34; // rcx
  int v35; // eax
  RTL_SRWLOCK *v36; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v37; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v38; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **v39; // rcx
  RTL_SRWLOCK *v40; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v41; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v42; // rcx
  int v43; // eax
  int v44; // [rsp+20h] [rbp-69h]
  int v45; // [rsp+20h] [rbp-69h]
  int v46; // [rsp+20h] [rbp-69h]
  HSTRING string; // [rsp+30h] [rbp-59h] BYREF
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v48; // [rsp+38h] [rbp-51h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v49; // [rsp+40h] [rbp-49h] BYREF
  RTL_SRWLOCK *v50; // [rsp+48h] [rbp-41h] BYREF
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **v51; // [rsp+50h] [rbp-39h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v52; // [rsp+58h] [rbp-31h] BYREF
  int v53; // [rsp+60h] [rbp-29h]
  char v54[8]; // [rsp+68h] [rbp-21h] BYREF
  char v55[8]; // [rsp+70h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-11h] BYREF
  HSTRING v57; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v53 = a2;
  v48 = 0;
  v7 = (RTL_SRWLOCK *)((char *)this - 176);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  v48 = 0;
  v8 = 0;
  v52 = 0;
  AcquireSRWLockShared(v7 + 38);
  v50 = v7 + 38;
  v9 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                   &v7[30],
                   v55);
  v11 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                    v10,
                    v54,
                    *v9);
  std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByWindow>(
    &v51,
    *v11,
    v12,
    ~a2);
  v13 = (struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper ***)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                                                                                 &v7[30],
                                                                                 v54);
  if ( v51 == *v13 )
  {
    if ( v7 != (RTL_SRWLOCK *)-304LL )
      ReleaseSRWLockShared(v7 + 38);
  }
  else
  {
    v14 = v51[1];
    v15 = *v51;
    if ( *v51 )
    {
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v15 + 8LL))(*v51);
      v8 = v15;
      v52 = v15;
    }
    if ( v7 != (RTL_SRWLOCK *)-304LL )
      ReleaseSRWLockShared(v7 + 38);
    if ( !v14 )
    {
      v35 = CShellExperienceDispatcher::_InitializeExperienceId((CShellExperienceDispatcher *)v7, v8);
      v19 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4C4,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)(unsigned int)v35,
          v44);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x354,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)v19,
          v46);
        v33 = v48;
        if ( v48 )
        {
          v48 = 0;
          (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v33 + 16LL))(v33);
        }
        return v19;
      }
    }
    if ( v8 )
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v8 + 8LL))(v8);
    v48 = v8;
    if ( v8 )
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  string = 0;
  if ( !a3 )
  {
    WindowsDeleteString(0);
    v17 = 0;
    v18 = &pszDefault;
    goto LABEL_16;
  }
  v16 = -1;
  do
    ++v16;
  while ( a3[v16] );
  if ( v16 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(0);
    v17 = v16;
    v18 = a3;
LABEL_16:
    string = 0;
    v19 = WindowsCreateString(v18, v17, &string);
    goto LABEL_17;
  }
  v19 = -2147024362;
LABEL_17:
  if ( (v19 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x357,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)v19,
      v44);
    WindowsDeleteString(string);
    string = 0;
    v34 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v34 + 16LL))(v34);
    }
    return v19;
  }
  v20 = 0;
  v49 = 0;
  if ( !a4 )
    goto LABEL_32;
  v50 = 0;
  QueryInterface = a4->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v22 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, RTL_SRWLOCK **))QueryInterface)(
          a4,
          &GUID_905a0fe0_bc53_11df_8c49_001e4fc686da,
          &v50);
  v19 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v22,
      v44);
    v36 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*((void (__fastcall **)(RTL_SRWLOCK *))v36->Ptr + 2))(v36);
    }
    v37 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v37 + 16LL))(v37);
    }
    WindowsDeleteString(string);
    string = 0;
    v38 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v38 + 16LL))(v38);
    }
    return v19;
  }
  v57 = 0;
  v23 = WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &v57);
  if ( v23 < 0 )
  {
    RaiseException(v23, 1u, 0, 0);
    __debugbreak();
  }
  v24 = v57;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v49 = 0;
  v52 = 0;
  v19 = RoActivateInstance(v24, &v52);
  if ( (v19 & 0x80000000) == 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v49 = v52;
    }
    else
    {
      v19 = (**(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, struct Windows::Foundation::Collections::IPropertySet **))v52)(
              v52,
              &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
              &v49);
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v52 + 16LL))(v52);
    }
  }
  if ( (v19 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)v19,
      v44);
LABEL_73:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
LABEL_76:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    return v19;
  }
  v51 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  v25 = RoCreatePropertySetSerializer(&v51);
  v19 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x363,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v25,
      v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    goto LABEL_73;
  }
  v26 = (*((__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **, struct Windows::Foundation::Collections::IPropertySet *, RTL_SRWLOCK *))*v51
         + 7))(
          v51,
          v49,
          v50);
  v19 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x364,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v26,
      v44);
    v39 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*((void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **))*v39 + 2))(v39);
    }
    v40 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*((void (__fastcall **)(RTL_SRWLOCK *))v40->Ptr + 2))(v40);
    }
    v41 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    WindowsDeleteString(string);
    string = 0;
    v42 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v42 + 16LL))(v42);
    }
    return v19;
  }
  v27 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*((void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **))*v27 + 2))(v27);
  }
  v28 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*((void (__fastcall **)(RTL_SRWLOCK *))v28->Ptr + 2))(v28);
  }
  v20 = v49;
LABEL_32:
  if ( v48 )
  {
    v45 = (int)v20;
    v29 = CShellExperienceDispatcher::_NotifyListener(v7, v48, 2, string);
    if ( v29 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shelle"
                      "xperiencedispatcher.cpp",
        (const char *)(unsigned int)v29,
        v45);
    goto LABEL_35;
  }
  v43 = CShellExperienceDispatcher::_BufferQueuedEvent((CShellExperienceDispatcher *)v7, v53, string, v20);
  v19 = v43;
  if ( v43 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x375,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v43,
      v44);
    goto LABEL_76;
  }
LABEL_35:
  v30 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  WindowsDeleteString(string);
  string = 0;
  v31 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v31 + 16LL))(v31);
  }
  return 0;
}

```

## disassembly

```asm
0x18003eeb0  push    rbp
0x18003eeb2  push    rbx
0x18003eeb3  push    rsi
0x18003eeb4  push    rdi
0x18003eeb5  push    r12
0x18003eeb7  push    r13
0x18003eeb9  push    r14
0x18003eebb  push    r15
0x18003eebd  lea     rbp, [rsp-1Fh]
0x18003eec2  sub     rsp, 0A8h
0x18003eec9  mov     rax, cs:__security_cookie
0x18003eed0  xor     rax, rsp
0x18003eed3  mov     [rbp+57h+var_48], rax
0x18003eed7  mov     r12, r9
0x18003eeda  mov     r15, r8
0x18003eedd  mov     ebx, edx
0x18003eedf  mov     [rbp+57h+var_80], edx
0x18003eee2  mov     [rbp+57h+var_A8], 0
0x18003eeea  lea     r13, [rcx-0B0h]
0x18003eef1  lea     rcx, [rbp+57h+var_A8]
0x18003eef5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003eefa  mov     [rbp+57h+var_A8], 0
0x18003ef02  mov     eax, ebx
0x18003ef04  not     eax
0x18003ef06  movsxd  rdi, eax
0x18003ef09  xor     esi, esi
0x18003ef0b  mov     [rbp+57h+var_88], rsi
0x18003ef0f  lea     r14, [r13+130h]
0x18003ef16  mov     rcx, r14; SRWLock
0x18003ef19  call    cs:__imp_AcquireSRWLockShared
0x18003ef1f  mov     [rbp+57h+var_98], r14
0x18003ef23  lea     rbx, [r13+0F0h]
0x18003ef2a  lea     rdx, [rbp+57h+var_70]
0x18003ef2e  mov     rcx, rbx
0x18003ef31  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18003ef36  mov     r8, [rax]
0x18003ef39  lea     rdx, [rbp+57h+var_78]
0x18003ef3d  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x18003ef42  mov     r9, rdi
0x18003ef45  mov     rdx, [rax]
0x18003ef48  lea     rcx, [rbp+57h+var_90]
0x18003ef4c  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@std@@VShellExperienceViewFindByWindow@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@0@V10@V10@VShellExperienceViewFindByWindow@@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByWindow>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByWindow)
0x18003ef51  lea     rdx, [rbp+57h+var_78]
0x18003ef55  mov     rcx, rbx
0x18003ef58  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18003ef5d  mov     rdx, [rbp+57h+var_90]
0x18003ef61  cmp     rdx, [rax]
0x18003ef64  jz      loc_18003F258
0x18003ef6a  mov     rdi, [rdx+8]
0x18003ef6e  mov     rbx, [rdx]
0x18003ef71  test    rbx, rbx
0x18003ef74  jz      short loc_18003EF8D
0x18003ef76  mov     rax, [rbx]
0x18003ef79  mov     rcx, rbx
0x18003ef7c  mov     rax, [rax+8]
0x18003ef80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef85  nop
0x18003ef86  mov     rsi, rbx
0x18003ef89  mov     [rbp+57h+var_88], rbx
0x18003ef8d  test    r14, r14
0x18003ef90  jz      short loc_18003EF9B
0x18003ef92  mov     rcx, r14; SRWLock
0x18003ef95  call    cs:__imp_ReleaseSRWLockShared
0x18003ef9b  xor     r14d, r14d
0x18003ef9e  test    rdi, rdi
0x18003efa1  jz      loc_18003F2F8
0x18003efa7  test    rsi, rsi
0x18003efaa  jz      short loc_18003EFBC
0x18003efac  mov     rax, [rsi]
0x18003efaf  mov     rcx, rsi
0x18003efb2  mov     rax, [rax+8]
0x18003efb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efbb  nop
0x18003efbc  mov     [rbp+57h+var_A8], rsi
0x18003efc0  test    rsi, rsi
0x18003efc3  jz      short loc_18003EFD5
0x18003efc5  mov     rax, [rsi]
0x18003efc8  mov     rcx, rsi
0x18003efcb  mov     rax, [rax+10h]
0x18003efcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efd4  nop
0x18003efd5  mov     [rbp+57h+string], r14
0x18003efd9  test    r15, r15
0x18003efdc  jz      loc_18003F2E2
0x18003efe2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003efe6  inc     rbx
0x18003efe9  cmp     [r15+rbx*2], r14w
0x18003efee  jnz     short loc_18003EFE6
0x18003eff0  mov     eax, 0FFFFFFFFh
0x18003eff5  cmp     rbx, rax
0x18003eff8  ja      loc_18003F24E
0x18003effe  xor     ecx, ecx; string
0x18003f000  call    cs:__imp_WindowsDeleteString
0x18003f006  mov     edx, ebx; length
0x18003f008  mov     rcx, r15; sourceString
0x18003f00b  mov     [rbp+57h+string], r14
0x18003f00f  lea     r8, [rbp+57h+string]; string
0x18003f013  call    cs:__imp_WindowsCreateString
0x18003f019  mov     ebx, eax
0x18003f01b  test    ebx, ebx
0x18003f01d  js      loc_18003F29C
0x18003f023  mov     r9, r14
0x18003f026  mov     [rbp+57h+var_A0], r14
0x18003f02a  test    r12, r12
0x18003f02d  jz      loc_18003F161
0x18003f033  mov     [rbp+57h+var_98], r14
0x18003f037  mov     rax, [r12]
0x18003f03b  mov     rbx, [rax]
0x18003f03e  lea     rcx, [rbp+57h+var_98]
0x18003f042  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f047  lea     r8, [rbp+57h+var_98]
0x18003f04b  lea     rdx, _GUID_905a0fe0_bc53_11df_8c49_001e4fc686da
0x18003f052  mov     rcx, r12
0x18003f055  mov     rax, rbx
0x18003f058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f05d  mov     ebx, eax
0x18003f05f  test    eax, eax
0x18003f061  js      loc_18003F312
0x18003f067  mov     [rbp+57h+var_50], r14
0x18003f06b  lea     r9, [rbp+57h+var_50]; string
0x18003f06f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003f073  mov     edx, 27h ; '''; length
0x18003f078  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x18003f07f  call    cs:__imp_WindowsCreateStringReference
0x18003f085  test    eax, eax
0x18003f087  js      loc_18003F439
0x18003f08d  mov     rbx, [rbp+57h+var_50]
0x18003f091  lea     rcx, [rbp+57h+var_A0]
0x18003f095  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f09a  mov     [rbp+57h+var_A0], r14
0x18003f09e  mov     [rbp+57h+var_88], r14
0x18003f0a2  lea     rdx, [rbp+57h+var_88]
0x18003f0a6  mov     rcx, rbx
0x18003f0a9  call    cs:__imp_RoActivateInstance
0x18003f0af  mov     ebx, eax
0x18003f0b1  test    eax, eax
0x18003f0b3  js      short loc_18003F0DE
0x18003f0b5  mov     r8d, 10h; Size
0x18003f0bb  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18003f0c2  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x18003f0c9  call    memcmp_0
0x18003f0ce  mov     rcx, [rbp+57h+var_88]
0x18003f0d2  test    eax, eax
0x18003f0d4  jnz     loc_18003F26F
0x18003f0da  mov     [rbp+57h+var_A0], rcx
0x18003f0de  test    ebx, ebx
0x18003f0e0  js      loc_18003F44C
0x18003f0e6  mov     [rbp+57h+var_90], r14
0x18003f0ea  lea     rcx, [rbp+57h+var_90]
0x18003f0ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f0f3  lea     rcx, [rbp+57h+var_90]
0x18003f0f7  call    cs:__imp_RoCreatePropertySetSerializer
0x18003f0fd  mov     ebx, eax
0x18003f0ff  test    eax, eax
0x18003f101  js      loc_18003F466
0x18003f107  mov     rcx, [rbp+57h+var_90]
0x18003f10b  mov     rax, [rcx]
0x18003f10e  mov     r8, [rbp+57h+var_98]
0x18003f112  mov     rdx, [rbp+57h+var_A0]
0x18003f116  mov     rax, [rax+38h]
0x18003f11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f11f  mov     ebx, eax
0x18003f121  test    eax, eax
0x18003f123  js      loc_18003F38C
0x18003f129  mov     rcx, [rbp+57h+var_90]
0x18003f12d  test    rcx, rcx
0x18003f130  jz      short loc_18003F143
0x18003f132  mov     [rbp+57h+var_90], r14
0x18003f136  mov     rax, [rcx]
0x18003f139  mov     rax, [rax+10h]
0x18003f13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f142  nop
0x18003f143  mov     rcx, [rbp+57h+var_98]
0x18003f147  test    rcx, rcx
0x18003f14a  jz      short loc_18003F15D
0x18003f14c  mov     [rbp+57h+var_98], r14
0x18003f150  mov     rax, [rcx]
0x18003f153  mov     rax, [rax+10h]
0x18003f157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f15c  nop
0x18003f15d  mov     r9, [rbp+57h+var_A0]; struct Windows::Foundation::Collections::IPropertySet *
0x18003f161  mov     rdx, [rbp+57h+var_A8]
0x18003f165  mov     rcx, r13; this
0x18003f168  test    rdx, rdx
0x18003f16b  jz      loc_18003F494
0x18003f171  mov     qword ptr [rsp+0E0h+var_C0], r9; int
0x18003f176  mov     r9, [rbp+57h+string]
0x18003f17a  mov     r8d, 2
0x18003f180  call    ?_NotifyListener@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@W4ShellExperienceViewState@Experience@456@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@6@@Z; CShellExperienceDispatcher::_NotifyListener(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,Windows::Internal::Shell::Experience::ShellExperienceViewState,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)
0x18003f185  mov     rcx, [rbp+5Fh]; this
0x18003f189  test    eax, eax
0x18003f18b  js      loc_18003F420
0x18003f191  mov     rcx, [rbp+57h+var_A0]
0x18003f195  test    rcx, rcx
0x18003f198  jz      short loc_18003F1AB
0x18003f19a  mov     [rbp+57h+var_A0], r14
0x18003f19e  mov     rax, [rcx]
0x18003f1a1  mov     rax, [rax+10h]
0x18003f1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1aa  nop
0x18003f1ab  mov     rcx, [rbp+57h+string]; string
0x18003f1af  call    cs:__imp_WindowsDeleteString
0x18003f1b5  mov     [rbp+57h+string], r14
0x18003f1b9  mov     rcx, [rbp+57h+var_A8]
0x18003f1bd  test    rcx, rcx
0x18003f1c0  jz      short loc_18003F1D3
0x18003f1c2  mov     [rbp+57h+var_A8], r14
0x18003f1c6  mov     rax, [rcx]
0x18003f1c9  mov     rax, [rax+10h]
0x18003f1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1d2  nop
0x18003f1d3  xor     eax, eax
0x18003f1d5  jmp     short loc_18003F22E
0x18003f1d7  mov     rcx, [rbp+5Fh]; this
0x18003f1db  mov     r9d, ebx; char *
0x18003f1de  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x18003f1e5  mov     edx, 4C4h; void *
0x18003f1ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f1ef  nop
0x18003f1f0  lea     rcx, [rbp+57h+var_88]
0x18003f1f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f1f9  mov     rcx, [rbp+5Fh]; this
0x18003f1fd  mov     r9d, ebx; char *
0x18003f200  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x18003f207  mov     edx, 354h; void *
0x18003f20c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f211  nop
0x18003f212  mov     rcx, [rbp+57h+var_A8]
0x18003f216  test    rcx, rcx
0x18003f219  jz      short loc_18003F22C
0x18003f21b  mov     [rbp+57h+var_A8], r14
0x18003f21f  mov     rax, [rcx]
0x18003f222  mov     rax, [rax+10h]
0x18003f226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f22b  nop
0x18003f22c  mov     eax, ebx
0x18003f22e  mov     rcx, [rbp+57h+var_48]
0x18003f232  xor     rcx, rsp; StackCookie
0x18003f235  call    __security_check_cookie
0x18003f23a  add     rsp, 0A8h
0x18003f241  pop     r15
0x18003f243  pop     r14
0x18003f245  pop     r13
0x18003f247  pop     r12
0x18003f249  pop     rdi
0x18003f24a  pop     rsi
0x18003f24b  pop     rbx
0x18003f24c  pop     rbp
0x18003f24d  retn
0x18003f24e  mov     ebx, 80070216h
0x18003f253  jmp     loc_18003F01B
0x18003f258  test    r14, r14
0x18003f25b  jz      short loc_18003F267
0x18003f25d  mov     rcx, r14; SRWLock
0x18003f260  call    cs:__imp_ReleaseSRWLockShared
0x18003f266  nop
0x18003f267  xor     r14d, r14d
0x18003f26a  jmp     loc_18003EFD5
0x18003f26f  mov     rax, [rcx]
0x18003f272  lea     r8, [rbp+57h+var_A0]
0x18003f276  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18003f27d  mov     rax, [rax]
0x18003f280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f285  mov     ebx, eax
0x18003f287  mov     rcx, [rbp+57h+var_88]
0x18003f28b  mov     rax, [rcx]
0x18003f28e  mov     rax, [rax+10h]
0x18003f292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f297  jmp     loc_18003F0DE
0x18003f29c  mov     rcx, [rbp+5Fh]; this
0x18003f2a0  mov     r9d, ebx; char *
0x18003f2a3  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x18003f2aa  mov     edx, 357h; void *
0x18003f2af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f2b4  nop
0x18003f2b5  mov     rcx, [rbp+57h+string]; string
0x18003f2b9  call    cs:__imp_WindowsDeleteString
0x18003f2bf  mov     [rbp+57h+string], r14
0x18003f2c3  mov     rcx, [rbp+57h+var_A8]
0x18003f2c7  test    rcx, rcx
0x18003f2ca  jz      short loc_18003F2DD
0x18003f2cc  mov     [rbp+57h+var_A8], r14
0x18003f2d0  mov     rax, [rcx]
0x18003f2d3  mov     rax, [rax+10h]
0x18003f2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2dc  nop
0x18003f2dd  jmp     loc_18003F22C
0x18003f2e2  xor     ecx, ecx; string
0x18003f2e4  call    cs:__imp_WindowsDeleteString
0x18003f2ea  xor     edx, edx
0x18003f2ec  lea     rcx, pszDefault
0x18003f2f3  jmp     loc_18003F00B
0x18003f2f8  mov     rdx, rsi; struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *
0x18003f2fb  mov     rcx, r13; this
0x18003f2fe  call    ?_InitializeExperienceId@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; CShellExperienceDispatcher::_InitializeExperienceId(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x18003f303  mov     ebx, eax
0x18003f305  test    eax, eax
0x18003f307  jns     loc_18003EFA7
0x18003f30d  jmp     loc_18003F1D7
0x18003f312  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
