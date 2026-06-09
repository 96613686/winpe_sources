# Windows::System::Internal::Launch::StoreLauncher::_MarketplaceDialogCallback(Windows::UI::Popups::IUICommand *)

- ea: `0x180085150`
- end: `0x18008539e`
- name: `?_MarketplaceDialogCallback@StoreLauncher@Launch@Internal@System@Windows@@AEAAJPEAUIUICommand@Popups@UI@5@@Z`
- size: `590`
- prototype: `__int64 __fastcall(Windows::System::Internal::Launch::StoreLauncher *__hidden this, struct Windows::UI::Popups::IUICommand *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180020fe0`
- `0x180021114`
- `0x18003c4f8`
- `0x1800596d8`
- `0x180085150`
- `0x1800853a4`
- `0x180085644`
- `0x18008a030`
- `0x1800cdfe8`
- `0x1800ceb94`
- `0x1800cf3c8`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008526b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008526b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008527b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800852a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800852ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800852fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008527b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800852a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800852ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800852fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180085353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180085293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180085293`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::Launch::StoreLauncher::_MarketplaceDialogCallback(
        Windows::System::Internal::Launch::StoreLauncher *this,
        struct Windows::UI::Popups::IUICommand *a2)
{
  __int64 (__fastcall *v4)(struct Windows::UI::Popups::IUICommand *, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  int StoreNavigationURI; // eax
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v17[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "MarketplaceDialogCallback");
  v17[0] = &LauncherClientProvider::MarketplaceDialogCallback::`vftable';
  LauncherClientProvider::MarketplaceDialogCallback::StartActivity((LauncherClientProvider::MarketplaceDialogCallback *)v17);
  if ( !a2 )
    goto LABEL_17;
  v16 = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::UI::Popups::IUICommand *, __int64 *))(*(_QWORD *)a2 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  v5 = v4(a2, &v16);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( !v16 )
    {
      v6 = -2147418113;
      v7 = 2147549183LL;
      v8 = 202;
      goto LABEL_6;
    }
    v13 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 96LL))(v16, &v13);
    v6 = v9;
    if ( v9 < 0 )
    {
      v7 = (unsigned int)v9;
      v8 = 205;
      goto LABEL_6;
    }
    LauncherClientProvider::MarketplaceDialogCallback::MarketplaceDialogCallbackDetails<unsigned int &>(v17, &v13);
    if ( v13 == 103 )
    {
      string = 0;
      AcquireSRWLockShared((PSRWLOCK)this + 13);
      v15 = (HSTRING)((char *)this + 104);
      WindowsDeleteString(string);
      string = 0;
      WindowsDuplicateString(*((HSTRING *)this + 11), &string);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v15);
      WindowsDeleteString(0);
      v15 = 0;
      StoreNavigationURI = Windows::System::Internal::Launch::StoreLauncher::_GetStoreNavigationURI(
                             string,
                             *((unsigned int *)this + 20),
                             &v15);
      v6 = StoreNavigationURI;
      if ( StoreNavigationURI < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD9,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\storelauncher.cpp",
          (const char *)(unsigned int)StoreNavigationURI,
          v13);
        WindowsDeleteString(v15);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_12;
      }
      v11 = Windows::System::Internal::Launch::StoreLauncher::LaunchUri(this, v15);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xDA,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\storelauncher.cpp",
          (const char *)(unsigned int)v11,
          v13);
      WindowsDeleteString(v15);
      WindowsDeleteString(string);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
LABEL_17:
    wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
    v6 = 0;
    goto LABEL_18;
  }
  v7 = (unsigned int)v5;
  v8 = 201;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\storelauncher.cpp",
    (const char *)v7,
    v13);
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
LABEL_18:
  LauncherClientProvider::MarketplaceDialogCallback::~MarketplaceDialogCallback((LauncherClientProvider::MarketplaceDialogCallback *)v17);
  return v6;
}

```

## disassembly

```asm
0x180085150  mov     [rsp-8+arg_10], rbx
0x180085155  push    rbp
0x180085156  push    rsi
0x180085157  push    rdi
0x180085158  lea     rbp, [rsp-0A0h]
0x180085160  sub     rsp, 1A0h
0x180085167  mov     rax, cs:__security_cookie
0x18008516e  xor     rax, rsp
0x180085171  mov     [rbp+0B0h+var_20], rax
0x180085178  mov     rdi, rdx
0x18008517b  mov     rsi, rcx
0x18008517e  lea     rdx, aMarketplacedia; "MarketplaceDialogCallback"
0x180085185  lea     rcx, [rsp+1B0h+var_170]
0x18008518a  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18008518f  lea     rax, ??_7MarketplaceDialogCallback@LauncherClientProvider@@6B@; const LauncherClientProvider::MarketplaceDialogCallback::`vftable'
0x180085196  mov     [rsp+1B0h+var_170], rax
0x18008519b  lea     rcx, [rsp+1B0h+var_170]; this
0x1800851a0  call    ?StartActivity@MarketplaceDialogCallback@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::MarketplaceDialogCallback::StartActivity(void)
0x1800851a5  nop
0x1800851a6  test    rdi, rdi
0x1800851a9  jz      loc_180085364
0x1800851af  mov     [rsp+1B0h+var_178], 0
0x1800851b8  mov     rax, [rdi]
0x1800851bb  mov     rbx, [rax+50h]
0x1800851bf  lea     rcx, [rsp+1B0h+var_178]
0x1800851c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800851c9  lea     rdx, [rsp+1B0h+var_178]
0x1800851ce  mov     rcx, rdi
0x1800851d1  mov     rax, rbx
0x1800851d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800851d9  mov     ebx, eax
0x1800851db  test    eax, eax
0x1800851dd  jns     short loc_1800851E9
0x1800851df  mov     r9d, eax
0x1800851e2  mov     edx, 0C9h
0x1800851e7  jmp     short loc_180085200
0x1800851e9  mov     rcx, [rsp+1B0h+var_178]
0x1800851ee  test    rcx, rcx
0x1800851f1  jnz     short loc_180085218
0x1800851f3  mov     ebx, 8000FFFFh
0x1800851f8  mov     r9d, ebx; char *
0x1800851fb  mov     edx, 0CAh; void *
0x180085200  mov     rcx, [rbp+0B8h]; this
0x180085207  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\windows.system.launc"...
0x18008520e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085213  jmp     loc_180085309
0x180085218  mov     [rsp+1B0h+var_190], 0; int
0x180085220  mov     rax, [rcx]
0x180085223  lea     rdx, [rsp+1B0h+var_190]
0x180085228  mov     rax, [rax+60h]
0x18008522c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085231  mov     ebx, eax
0x180085233  test    eax, eax
0x180085235  jns     short loc_180085241
0x180085237  mov     r9d, eax
0x18008523a  mov     edx, 0CDh
0x18008523f  jmp     short loc_180085200
0x180085241  lea     rdx, [rsp+1B0h+var_190]
0x180085246  lea     rcx, [rsp+1B0h+var_170]
0x18008524b  call    ??$MarketplaceDialogCallbackDetails@AEAI@MarketplaceDialogCallback@LauncherClientProvider@@QEAAXAEAI@Z; LauncherClientProvider::MarketplaceDialogCallback::MarketplaceDialogCallbackDetails<uint &>(uint &)
0x180085250  cmp     [rsp+1B0h+var_190], 67h ; 'g'
0x180085255  jnz     loc_18008535A
0x18008525b  mov     [rsp+1B0h+string], 0
0x180085264  lea     rbx, [rsi+68h]
0x180085268  mov     rcx, rbx; SRWLock
0x18008526b  call    cs:__imp_AcquireSRWLockShared
0x180085271  mov     [rsp+1B0h+var_180], rbx
0x180085276  mov     rcx, [rsp+1B0h+string]; string
0x18008527b  call    cs:__imp_WindowsDeleteString
0x180085281  mov     [rsp+1B0h+string], 0
0x18008528a  lea     rdx, [rsp+1B0h+string]; newString
0x18008528f  mov     rcx, [rsi+58h]; string
0x180085293  call    cs:__imp_WindowsDuplicateString
0x180085299  lea     rcx, [rsp+1B0h+var_180]
0x18008529e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800852a3  nop
0x1800852a4  xor     ecx, ecx; string
0x1800852a6  call    cs:__imp_WindowsDeleteString
0x1800852ac  mov     [rsp+1B0h+var_180], 0
0x1800852b5  lea     r8, [rsp+1B0h+var_180]
0x1800852ba  mov     edx, [rsi+50h]
0x1800852bd  mov     rcx, [rsp+1B0h+string]
0x1800852c2  call    ?_GetStoreNavigationURI@StoreLauncher@Launch@Internal@System@Windows@@CAJPEAUHSTRING__@@W4MarketPlaceDialogType@2345@PEAPEAU6@@Z; Windows::System::Internal::Launch::StoreLauncher::_GetStoreNavigationURI(HSTRING__ *,Windows::System::Internal::Launch::MarketPlaceDialogType,HSTRING__ * *)
0x1800852c7  mov     ebx, eax
0x1800852c9  test    eax, eax
0x1800852cb  jns     short loc_180085315
0x1800852cd  mov     rcx, [rbp+0B8h]; this
0x1800852d4  mov     r9d, eax; char *
0x1800852d7  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\windows.system.launc"...
0x1800852de  mov     edx, 0D9h; void *
0x1800852e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800852e8  nop
0x1800852e9  mov     rcx, [rsp+1B0h+var_180]; string
0x1800852ee  call    cs:__imp_WindowsDeleteString
0x1800852f4  nop
0x1800852f5  mov     rcx, [rsp+1B0h+string]; string
0x1800852fa  call    cs:__imp_WindowsDeleteString
0x180085300  mov     [rsp+1B0h+string], 0
0x180085309  lea     rcx, [rsp+1B0h+var_178]
0x18008530e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085313  jmp     short loc_180085370
0x180085315  mov     rdx, [rsp+1B0h+var_180]; HSTRING
0x18008531a  mov     rcx, rsi; this
0x18008531d  call    ?LaunchUri@StoreLauncher@Launch@Internal@System@Windows@@AEAAJPEAUHSTRING__@@@Z; Windows::System::Internal::Launch::StoreLauncher::LaunchUri(HSTRING__ *)
0x180085322  mov     rcx, [rbp+0B8h]; this
0x180085329  test    eax, eax
0x18008532b  jns     short loc_180085342
0x18008532d  mov     r9d, eax; char *
0x180085330  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\windows.system.launc"...
0x180085337  mov     edx, 0DAh; void *
0x18008533c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180085341  nop
0x180085342  mov     rcx, [rsp+1B0h+var_180]; string
0x180085347  call    cs:__imp_WindowsDeleteString
0x18008534d  nop
0x18008534e  mov     rcx, [rsp+1B0h+string]; string
0x180085353  call    cs:__imp_WindowsDeleteString
0x180085359  nop
0x18008535a  lea     rcx, [rsp+1B0h+var_178]
0x18008535f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085364  lea     rcx, [rsp+1B0h+var_170]
0x180085369  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18008536e  xor     ebx, ebx
0x180085370  lea     rcx, [rsp+1B0h+var_170]; this
0x180085375  call    ??1MarketplaceDialogCallback@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::MarketplaceDialogCallback::~MarketplaceDialogCallback(void)
0x18008537a  mov     eax, ebx
0x18008537c  mov     rcx, [rbp+0B0h+var_20]
0x180085383  xor     rcx, rsp; StackCookie
0x180085386  call    __security_check_cookie
0x18008538b  mov     rbx, [rsp+1B0h+arg_10]
0x180085393  add     rsp, 1A0h
0x18008539a  pop     rdi
0x18008539b  pop     rsi
0x18008539c  pop     rbp
0x18008539d  retn
```
