# winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::UnifiedConsentCoordinator(winrt::Windows::Security::Credentials::WebAccount)

- ea: `0x180022138`
- end: `0x18002248e`
- name: `??0UnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@QEAA@UWebAccount@Credentials@Security@56@@Z`
- size: `854`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001fa7c`

## callees

- `0x180002840`
- `0x180003390`
- `0x1800034f7`
- `0x1800035ab`
- `0x18000ebfc`
- `0x18000ed24`
- `0x18000f44c`
- `0x18000fae4`
- `0x18000fb28`
- `0x1800132dc`
- `0x180013efc`
- `0x1800142a4`
- `0x180014364`
- `0x180018290`
- `0x18001c8bc`
- `0x180022138`
- `0x18002770c`
- `0x180027914`
- `0x18002cf00`
- `0x18002d5e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800222d2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800222dd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022436`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022445`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022451`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800222d2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800222dd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022436`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022445`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022451`

## string_xrefs

- `0x1800222e4`: `Using the default path`
- `0x18002228c`: `Using the web account id path`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::UnifiedConsentCoordinator(
        _QWORD *a1,
        _QWORD *a2)
{
  char v4; // di
  char v5; // r12
  __int64 v6; // rcx
  const wchar_t *v7; // rdx
  size_t v8; // r8
  const wchar_t *v9; // r9
  unsigned int *v10; // rbx
  _QWORD *v11; // rax
  const WCHAR *v12; // r13
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  void *v16; // rdi
  int v17; // eax
  HANDLE ProcessHeap; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rax
  void *v22; // rdi
  int v23; // eax
  unsigned int v24; // edx
  struct winrt::impl::shared_hstring_header *v25; // rdi
  int v26; // eax
  HANDLE v27; // rax
  LPVOID v28; // rdi
  __int64 v29; // rax
  void *v30; // r12
  int v31; // eax
  HANDLE v32; // rax
  __int64 v33; // rax
  int v34; // r14d
  HANDLE v35; // rax
  unsigned int *v37; // rax
  LPVOID v38; // [rsp+20h] [rbp-58h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v40[56]; // [rsp+40h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+D0h] [rbp+58h] BYREF
  LPVOID v42; // [rsp+D8h] [rbp+60h] BYREF

  v4 = 0;
  LODWORD(lpMem) = 0;
  a1[2] = &winrt::impl::produce<winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator,winrt::Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinator>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v5 = 1;
  a1[1] = 1;
  *a1 = &winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::`vftable';
  a1[3] = 0;
  a1[4] = 0;
  a1[5] = 0;
  a1[6] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCoordinator>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCoordinator>::GetImpl'::`2'::impl) )
  {
    winrt::impl::slim_source_location::current(v40);
    v37 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&lpMem, -2147418113);
    winrt::hresult_error::hresult_error(pExceptionObject, *v37);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::GetStoredDefaultId(v6, &v42);
  v10 = (unsigned int *)v42;
  if ( !v42 )
  {
    v11 = operator new(0x60u);
    lpMem = v11;
    v11[11] = a1;
    *v11 = winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::UpdateStoredDefaultIdAsync__ResumeCoro_1;
    *((_DWORD *)v11 + 2) = 65538;
    *((_BYTE *)v11 + 80) = 0;
    winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::UpdateStoredDefaultIdAsync__ResumeCoro_1(v11);
  }
  v12 = &Name;
  if ( !*a2 )
    goto LABEL_15;
  v13 = (__int64 *)winrt::impl::consume_Windows_Security_Credentials_IWebAccount2<winrt::Windows::Security::Credentials::WebAccount>::Id(
                     a2,
                     &lpMem,
                     v8,
                     v9);
  if ( v10 )
  {
    v14 = v10[1];
    v7 = (const wchar_t *)*((_QWORD *)v10 + 2);
  }
  else
  {
    v14 = 0;
    v7 = &Name;
  }
  v15 = *v13;
  if ( v15 )
  {
    v8 = *(unsigned int *)(v15 + 4);
    v9 = *(const wchar_t **)(v15 + 16);
  }
  else
  {
    v8 = 0;
    v9 = &Name;
  }
  if ( v8 == v14 && ((v4 = 1, !v8) || !wmemcmp(v9, v7, v8)) )
  {
LABEL_15:
    if ( (v4 & 1) == 0 )
      goto LABEL_26;
  }
  else
  {
    v5 = 0;
  }
  v16 = lpMem;
  if ( lpMem )
  {
    v17 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v17 )
    {
      if ( v17 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, v16);
    }
  }
  if ( !v5 )
  {
    UnifiedConsentLogging::TraceLoggingInfo("Using the web account id path", v7, v8, v9);
    v21 = winrt::impl::consume_Windows_Security_Credentials_IWebAccount2<winrt::Windows::Security::Credentials::WebAccount>::Id(
            a2,
            &lpMem,
            v19,
            v20);
    winrt::hstring::operator=(a1 + 3, v21);
    v22 = lpMem;
    if ( !lpMem )
      goto LABEL_29;
    v23 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v23 )
    {
      if ( v23 < 0 )
        abort();
      goto LABEL_29;
    }
LABEL_28:
    v27 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v27, 0, v22);
    goto LABEL_29;
  }
LABEL_26:
  UnifiedConsentLogging::TraceLoggingInfo("Using the default path");
  v25 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0xE, v24);
  memcpy_s((char *)v25 + 28, 0x1Cu, L"DEFAULTACCOUNT", 0x1Cu);
  lpMem = v25;
  winrt::hstring::operator=(a1 + 3, &lpMem);
  v22 = lpMem;
  if ( !lpMem )
    goto LABEL_29;
  v26 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
  if ( !v26 )
    goto LABEL_28;
  if ( v26 < 0 )
    abort();
LABEL_29:
  if ( *a2 )
  {
    winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
      a2,
      &lpMem);
    v28 = lpMem;
    if ( lpMem )
    {
      v29 = winrt::impl::consume_Windows_Security_Credentials_IWebAccountProvider2<winrt::Windows::Security::Credentials::WebAccountProvider>::Authority(
              &lpMem,
              &v38);
      winrt::hstring::operator=(a1 + 4, v29);
      v30 = v38;
      if ( v38 )
      {
        v31 = _InterlockedDecrement((volatile signed __int32 *)v38 + 6);
        if ( v31 )
        {
          if ( v31 < 0 )
            abort();
        }
        else
        {
          v32 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v32, 0, v30);
        }
      }
      v33 = a1[4];
      if ( v33 )
        v12 = *(const WCHAR **)(v33 + 16);
      UnifiedConsentLogging::TraceLoggingInfo("Web account provider: %ws", v12);
    }
    if ( v28 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  }
  if ( v10 )
  {
    v34 = _InterlockedDecrement((volatile signed __int32 *)v10 + 6);
    if ( v34 )
    {
      if ( v34 < 0 )
        abort();
    }
    else
    {
      v35 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v35, 0, v10);
    }
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return a1;
}

```

## disassembly

```asm
0x180022138  mov     [rsp-40h+arg_8], rdx
0x18002213d  mov     [rsp-40h+arg_0], rcx
0x180022142  push    rbp
0x180022143  push    rbx
0x180022144  push    rsi
0x180022145  push    rdi
0x180022146  push    r12
0x180022148  push    r13
0x18002214a  push    r14
0x18002214c  push    r15
0x18002214e  mov     rbp, rsp
0x180022151  sub     rsp, 78h
0x180022155  mov     rsi, rdx
0x180022158  mov     r15, rcx
0x18002215b  xor     r14d, r14d
0x18002215e  mov     edi, r14d
0x180022161  mov     dword ptr [rbp+lpMem], r14d
0x180022165  lea     rax, ??_7?$produce@UUnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@UIUnifiedConsentCoordinator@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator,winrt::Windows::Internal::Shell::ConsentUx::IUnifiedConsentCoordinator>::`vftable'
0x18002216c  mov     [rcx+10h], rax
0x180022170  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180022177  lea     r12d, [r14+1]
0x18002217b  mov     [rcx+8], r12
0x18002217f  lea     rax, ??_7UnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@6B@; const winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::`vftable'
0x180022186  mov     [rcx], rax
0x180022189  mov     [rcx+18h], r14
0x18002218d  mov     [rcx+20h], r14
0x180022191  mov     [rcx+28h], r14
0x180022195  mov     [rcx+30h], r14
0x180022199  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedConsentCoordinator@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCoordinator@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCoordinator> `wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCoordinator>::GetImpl(void)'::`2'::impl
0x1800221a0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCoordinator@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCoordinator>::__private_IsEnabled(void)
0x1800221a5  test    al, al
0x1800221a7  jz      loc_180022458
0x1800221ad  lea     rdx, [rbp+arg_18]
0x1800221b1  call    ?GetStoredDefaultId@UnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@AEAA?AUhstring@7@XZ; winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::GetStoredDefaultId(void)
0x1800221b6  nop
0x1800221b7  mov     rbx, [rbp+arg_18]
0x1800221bb  test    rbx, rbx
0x1800221be  jnz     short loc_1800221EF
0x1800221c0  lea     ecx, [rbx+60h]; Size
0x1800221c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800221c8  mov     [rbp+lpMem], rax
0x1800221cc  mov     [rax+58h], r15
0x1800221d0  lea     rcx, winrt__Windows__Internal__Shell__ConsentUx__implementation__UnifiedConsentCoordinator__UpdateStoredDefaultIdAsync$_ResumeCoro$1
0x1800221d7  mov     [rax], rcx
0x1800221da  mov     dword ptr [rax+8], 10002h
0x1800221e1  xor     ecx, ecx
0x1800221e3  mov     [rax+50h], cl
0x1800221e6  mov     rcx, rax
0x1800221e9  call    winrt__Windows__Internal__Shell__ConsentUx__implementation__UnifiedConsentCoordinator__UpdateStoredDefaultIdAsync$_ResumeCoro$1
0x1800221ee  nop
0x1800221ef  or      r14d, 0FFFFFFFFh
0x1800221f3  lea     r13, Name
0x1800221fa  cmp     qword ptr [rsi], 0
0x1800221fe  jz      short loc_180022255
0x180022200  lea     rdx, [rbp+lpMem]
0x180022204  mov     rcx, rsi
0x180022207  call    ?Id@?$consume_Windows_Security_Credentials_IWebAccount2@UWebAccount@Credentials@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Credentials_IWebAccount2<winrt::Windows::Security::Credentials::WebAccount>::Id(void)
0x18002220c  test    rbx, rbx
0x18002220f  jz      short loc_18002221A
0x180022211  mov     ecx, [rbx+4]
0x180022214  mov     rdx, [rbx+10h]
0x180022218  jmp     short loc_18002221F
0x18002221a  xor     ecx, ecx
0x18002221c  mov     rdx, r13; S2
0x18002221f  mov     rax, [rax]
0x180022222  test    rax, rax
0x180022225  jz      short loc_180022231
0x180022227  mov     r8d, [rax+4]
0x18002222b  mov     r9, [rax+10h]
0x18002222f  jmp     short loc_180022237
0x180022231  xor     r8d, r8d; N
0x180022234  mov     r9, r13
0x180022237  cmp     r8, rcx
0x18002223a  jnz     short loc_180022250
0x18002223c  mov     edi, r12d
0x18002223f  test    r8, r8
0x180022242  jz      short loc_180022255
0x180022244  mov     rcx, r9; S1
0x180022247  call    wmemcmp
0x18002224c  test    eax, eax
0x18002224e  jz      short loc_180022255
0x180022250  xor     r12b, r12b
0x180022253  jmp     short loc_18002225E
0x180022255  test    r12b, dil
0x180022258  jz      loc_1800222E4
0x18002225e  mov     rdi, [rbp+lpMem]
0x180022262  test    rdi, rdi
0x180022265  jz      short loc_180022287
0x180022267  mov     eax, r14d
0x18002226a  lock xadd [rdi+18h], eax
0x18002226f  sub     eax, 1
0x180022272  jnz     short loc_1800222D9
0x180022274  nop
0x180022275  call    WINRT_IMPL_GetProcessHeap
0x18002227a  mov     rcx, rax; hHeap
0x18002227d  mov     r8, rdi; lpMem
0x180022280  xor     edx, edx; dwFlags
0x180022282  call    WINRT_IMPL_HeapFree
0x180022287  test    r12b, r12b
0x18002228a  jnz     short loc_1800222E4
0x18002228c  lea     rcx, aUsingTheWebAcc; "Using the web account id path"
0x180022293  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x180022298  lea     rdx, [rbp+lpMem]
0x18002229c  mov     rcx, rsi
0x18002229f  call    ?Id@?$consume_Windows_Security_Credentials_IWebAccount2@UWebAccount@Credentials@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Credentials_IWebAccount2<winrt::Windows::Security::Credentials::WebAccount>::Id(void)
0x1800222a4  mov     rdx, rax
0x1800222a7  lea     rcx, [r15+18h]
0x1800222ab  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x1800222b0  mov     rdi, [rbp+lpMem]
0x1800222b4  test    rdi, rdi
0x1800222b7  jz      loc_180022353
0x1800222bd  mov     eax, r14d
0x1800222c0  lock xadd [rdi+18h], eax
0x1800222c5  sub     eax, 1
0x1800222c8  jz      short loc_180022340
0x1800222ca  test    eax, eax
0x1800222cc  jns     loc_180022353
0x1800222d2  call    cs:__imp_abort
0x1800222d9  test    eax, eax
0x1800222db  jns     short loc_180022287
0x1800222dd  call    cs:__imp_abort
0x1800222e4  lea     rcx, aUsingTheDefaul; "Using the default path"
0x1800222eb  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x1800222f0  mov     ecx, 0Eh; this
0x1800222f5  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800222fa  mov     rdi, rax
0x1800222fd  lea     rcx, [rax+1Ch]; Destination
0x180022301  mov     edx, 1Ch; DestinationSize
0x180022306  mov     r9d, edx; SourceSize
0x180022309  lea     r8, Value; "DEFAULTACCOUNT"
0x180022310  call    memcpy_s
0x180022315  mov     [rbp+lpMem], rdi
0x180022319  lea     rdx, [rbp+lpMem]
0x18002231d  lea     rcx, [r15+18h]
0x180022321  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x180022326  mov     rdi, [rbp+lpMem]
0x18002232a  test    rdi, rdi
0x18002232d  jz      short loc_180022353
0x18002232f  mov     eax, r14d
0x180022332  lock xadd [rdi+18h], eax
0x180022337  sub     eax, 1
0x18002233a  jnz     loc_18002242E
0x180022340  nop
0x180022341  call    WINRT_IMPL_GetProcessHeap
0x180022346  mov     rcx, rax; hHeap
0x180022349  mov     r8, rdi; lpMem
0x18002234c  xor     edx, edx; dwFlags
0x18002234e  call    WINRT_IMPL_HeapFree
0x180022353  cmp     qword ptr [rsi], 0
0x180022357  jz      loc_1800223E7
0x18002235d  lea     rdx, [rbp+lpMem]
0x180022361  mov     rcx, rsi
0x180022364  call    ?ClientId@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(void)
0x180022369  nop
0x18002236a  mov     rdi, [rbp+lpMem]
0x18002236e  test    rdi, rdi
0x180022371  jz      short loc_1800223D8
0x180022373  lea     rdx, [rbp+var_58]
0x180022377  lea     rcx, [rbp+lpMem]
0x18002237b  call    ?Authority@?$consume_Windows_Security_Credentials_IWebAccountProvider2@UWebAccountProvider@Credentials@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Credentials_IWebAccountProvider2<winrt::Windows::Security::Credentials::WebAccountProvider>::Authority(void)
0x180022380  mov     rdx, rax
0x180022383  lea     rcx, [r15+20h]
0x180022387  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002238c  mov     r12, [rbp+var_58]
0x180022390  test    r12, r12
0x180022393  jz      short loc_1800223BB
0x180022395  mov     eax, r14d
0x180022398  lock xadd [r12+18h], eax
0x18002239f  sub     eax, 1
0x1800223a2  jnz     loc_18002243D
0x1800223a8  nop
0x1800223a9  call    WINRT_IMPL_GetProcessHeap
0x1800223ae  mov     rcx, rax; hHeap
0x1800223b1  mov     r8, r12; lpMem
0x1800223b4  xor     edx, edx; dwFlags
0x1800223b6  call    WINRT_IMPL_HeapFree
0x1800223bb  mov     rax, [r15+20h]
0x1800223bf  test    rax, rax
0x1800223c2  jz      short loc_1800223C8
0x1800223c4  mov     r13, [rax+10h]
0x1800223c8  mov     rdx, r13
0x1800223cb  lea     rcx, aWebAccountProv; "Web account provider: %ws"
0x1800223d2  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x1800223d7  nop
0x1800223d8  test    rdi, rdi
0x1800223db  jz      short loc_1800223E7
0x1800223dd  lea     rcx, [rbp+lpMem]
0x1800223e1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800223e6  nop
0x1800223e7  test    rbx, rbx
0x1800223ea  jz      short loc_18002240C
0x1800223ec  lock xadd [rbx+18h], r14d
0x1800223f2  sub     r14d, 1
0x1800223f6  jnz     short loc_18002244C
0x1800223f8  nop
0x1800223f9  call    WINRT_IMPL_GetProcessHeap
0x1800223fe  mov     rcx, rax; hHeap
0x180022401  mov     r8, rbx; lpMem
0x180022404  xor     edx, edx; dwFlags
0x180022406  call    WINRT_IMPL_HeapFree
0x18002240b  nop
0x18002240c  cmp     qword ptr [rsi], 0
0x180022410  jz      short loc_18002241A
0x180022412  mov     rcx, rsi
0x180022415  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002241a  mov     rax, r15
0x18002241d  add     rsp, 78h
0x180022421  pop     r15
0x180022423  pop     r14
0x180022425  pop     r13
0x180022427  pop     r12
0x180022429  pop     rdi
0x18002242a  pop     rsi
0x18002242b  pop     rbx
0x18002242c  pop     rbp
0x18002242d  retn
0x18002242e  test    eax, eax
0x180022430  jns     loc_180022353
0x180022436  call    cs:__imp_abort
0x18002243d  test    eax, eax
0x18002243f  jns     loc_1800223BB
0x180022445  call    cs:__imp_abort
0x18002244c  test    r14d, r14d
0x18002244f  jns     short loc_18002240C
0x180022451  call    cs:__imp_abort
0x180022458  lea     rcx, [rbp+var_38]
0x18002245c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180022461  mov     r8, rax
0x180022464  mov     edx, 8000FFFFh; int
0x180022469  lea     rcx, [rbp+lpMem]; this
0x18002246d  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180022472  mov     edx, [rax]
0x180022474  lea     rcx, [rbp+pExceptionObject]
0x180022478  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002247d  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180022484  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180022488  call    _CxxThrowException_0
```
