# _ActivateApplicationForLaunchHelperWithWindowFactory(IApplicationActivationManagerPriv *,ushort const *,ushort const *,ushort const *,ACTIVATEOPTIONSINTERNAL,HMONITOR__ *,Windows::UI::Core::ICoreWindowFactory *,ulong *)

- ea: `0x1800f2124`
- end: `0x1800f242c`
- name: `?_ActivateApplicationForLaunchHelperWithWindowFactory@@YAJPEAUIApplicationActivationManagerPriv@@PEBG11W4ACTIVATEOPTIONSINTERNAL@@PEAUHMONITOR__@@PEAUICoreWindowFactory@Core@UI@Windows@@PEAK@Z`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18066f568`

## callees

- `0x1800237c8`
- `0x1800255d0`
- `0x180031200`
- `0x18008a6f0`
- `0x1800a316c`
- `0x1800f1dc0`
- `0x1800f2124`
- `0x1800f2670`
- `0x180279e50`
- `0x180356360`
- `0x18066f0d0`
- `0x18066f1f0`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f21cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f2224`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f2421`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f21cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f2224`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f2421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f21df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f2237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f2330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f21df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f2237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800f2330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f22b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f22b5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x1800f22f7`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_GetSite` at `0x1800f22f7`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800f2384`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1806f347e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1806f34b4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1800f2384`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1806f347e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x1806f34b4`

## pseudocode

```c
__int64 __fastcall _ActivateApplicationForLaunchHelperWithWindowFactory(
        IUnknown *a1,
        unsigned __int16 *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4,
        int a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned __int64 v10; // rbx
  const WCHAR *v11; // r12
  unsigned __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
  __int64 v18; // rcx
  void (*v19)(void); // rax
  void **v21; // rax
  HRESULT Site; // eax
  __int64 v23; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // r15
  HSTRING v25; // rbx
  __int64 v26; // rcx
  HRESULT v27; // eax
  __int64 v28; // rdx
  int v29; // [rsp+20h] [rbp-D9h]
  __int64 v30; // [rsp+40h] [rbp-B9h] BYREF
  IUnknown *v31; // [rsp+48h] [rbp-B1h] BYREF
  IUnknown *punkSite; // [rsp+50h] [rbp-A9h] BYREF
  void *v33; // [rsp+58h] [rbp-A1h] BYREF
  PCWSTR sourceString[3]; // [rsp+60h] [rbp-99h] BYREF
  __int64 v35; // [rsp+78h] [rbp-81h] BYREF
  unsigned __int16 *v36; // [rsp+80h] [rbp-79h]
  _DWORD *v37; // [rsp+88h] [rbp-71h]
  __int64 v38; // [rsp+90h] [rbp-69h]
  _BYTE v39[16]; // [rsp+A0h] [rbp-59h] BYREF
  HSTRING v40; // [rsp+B0h] [rbp-49h] BYREF
  HSTRING_HEADER v41; // [rsp+B8h] [rbp-41h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+3Fh]

  v38 = a7;
  v36 = a2;
  v10 = -1;
  v35 = a6;
  v37 = a8;
  *a8 = 0;
  v11 = a4;
  sourceString[0] = 0;
  sourceString[1] = (PCWSTR)-1LL;
  sourceString[2] = (PCWSTR)-1LL;
  v30 = 0;
  v12 = -1;
  if ( (int)ParseAppUserModelId(a4, 0, (unsigned __int16 **)sourceString) >= 0 )
    v11 = sourceString[0];
  do
    ++v12;
  while ( v11[v12] );
  if ( v12 > 0xFFFFFFFF )
  {
    LODWORD(v12) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v11, v12, &hstringHeader, &string);
  v31 = (IUnknown *)string;
  if ( !a3 )
    a3 = &pvData;
  do
    ++v10;
  while ( a3[v10] );
  if ( v10 > 0xFFFFFFFF )
  {
    LODWORD(v10) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a3, v10, &v41, &v40);
  v33 = v40;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v30);
  v13 = _lambda_6b6168dda817c5975ee7d3438d2331fe_::_lambda_6b6168dda817c5975ee7d3438d2331fe_(v39, &v33, &v31);
  v16 = Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(
          v15,
          v14,
          &v30,
          v13);
  v17 = v16;
  if ( v16 >= 0 )
  {
    punkSite = 0;
    v21 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(&punkSite);
    Site = IUnknown_GetSite(a1, &GUID_00000000_0000_0000_c000_000000000046, v21);
    v17 = Site;
    if ( Site < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecoreuap\\shell\\twinui\\activationhelper\\activationhelpers.cpp",
        (const char *)(unsigned int)Site,
        v29);
    }
    else
    {
      if ( !a6 )
      {
LABEL_20:
        v23 = v30;
        QueryInterface = a1->lpVtbl[1].QueryInterface;
        if ( WindowsCreateStringReference(L"Windows.Launch", 0xEu, &v41, &v40) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v25 = v40;
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&string, v36);
        v17 = ((__int64 (__fastcall *)(IUnknown *, HSTRING, __int64, HSTRING, __int64, int, _DWORD *))QueryInterface)(
                a1,
                string,
                v38,
                v25,
                v23,
                a5,
                v37);
        IUnknown_SetSite(a1, punkSite);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punkSite);
        v26 = v30;
        if ( !v30 )
          goto LABEL_15;
        v30 = 0;
        v19 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
        goto LABEL_14;
      }
      v33 = punkSite;
      v31 = 0;
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v31);
      v27 = Microsoft::WRL::Details::MakeAndInitialize<CLaunchToMonitor,CLaunchToMonitor,HMONITOR__ * &,IUnknown *>(
              &v31,
              &v35,
              &v33);
      v17 = v27;
      if ( v27 >= 0 )
      {
        v27 = IUnknown_SetSite(a1, v31);
        v17 = v27;
        if ( v27 >= 0 )
        {
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v31);
          goto LABEL_20;
        }
        v28 = 55;
      }
      else
      {
        v28 = 54;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecoreuap\\shell\\twinui\\activationhelper\\activationhelpers.cpp",
        (const char *)(unsigned int)v27,
        v29);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v31);
      IUnknown_SetSite(a1, punkSite);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punkSite);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v30);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
    return v17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22,
    (unsigned int)"onecoreuap\\shell\\twinui\\activationhelper\\activationhelpers.cpp",
    (const char *)(unsigned int)v16,
    v29);
  v18 = v30;
  if ( !v30 )
    goto LABEL_15;
  v30 = 0;
  v19 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
LABEL_14:
  v19();
LABEL_15:
  if ( sourceString[0] )
    CoTaskMemFree((LPVOID)sourceString[0]);
  return v17;
}

```

## disassembly

```asm
0x1800f2124  push    rbp
0x1800f2126  push    rbx
0x1800f2127  push    rsi
0x1800f2128  push    rdi
0x1800f2129  push    r12
0x1800f212b  push    r13
0x1800f212d  push    r15
0x1800f212f  lea     rbp, [rsp-7]
0x1800f2134  sub     rsp, 100h
0x1800f213b  mov     rax, cs:__security_cookie
0x1800f2142  xor     rax, rsp
0x1800f2145  mov     [rbp+37h+var_40], rax
0x1800f2149  mov     rax, [rbp+37h+arg_30]
0x1800f214d  mov     r15, r8
0x1800f2150  mov     r13, [rbp+37h+arg_28]
0x1800f2154  lea     r8, [rsp+130h+sourceString]; unsigned __int16 **
0x1800f2159  mov     [rbp+37h+var_A0], rax
0x1800f215d  mov     rsi, rcx
0x1800f2160  mov     rax, [rbp+37h+arg_38]
0x1800f2164  xor     edi, edi
0x1800f2166  mov     [rbp+37h+var_B0], rdx
0x1800f216a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800f216e  xor     edx, edx; unsigned __int16 **
0x1800f2170  mov     [rsp+130h+var_B8], r13
0x1800f2175  mov     rcx, r9; unsigned __int16 *
0x1800f2178  mov     [rbp+37h+var_A8], rax
0x1800f217c  mov     [rax], edi
0x1800f217e  mov     r12, r9
0x1800f2181  mov     [rsp+130h+sourceString], rdi
0x1800f2186  mov     [rsp+130h+var_C8], rbx
0x1800f218b  mov     [rsp+130h+var_C0], rbx
0x1800f2190  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x1800f2195  test    eax, eax
0x1800f2197  mov     [rsp+130h+var_F0], rdi
0x1800f219c  mov     rdi, rbx
0x1800f219f  cmovns  r12, [rsp+130h+sourceString]
0x1800f21a5  xor     eax, eax
0x1800f21a7  inc     rdi
0x1800f21aa  cmp     [r12+rdi*2], ax
0x1800f21af  jnz     short loc_1800F21A7
0x1800f21b1  mov     eax, 0FFFFFFFFh
0x1800f21b6  cmp     rdi, rax
0x1800f21b9  jbe     short loc_1800F21D2
0x1800f21bb  xor     r9d, r9d; lpArguments
0x1800f21be  xor     r8d, r8d; nNumberOfArguments
0x1800f21c1  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800f21c6  mov     edi, eax
0x1800f21c8  lea     edx, [r9+1]; dwExceptionFlags
0x1800f21cc  call    cs:__imp_RaiseException
0x1800f21d2  lea     r9, [rbp+37h+string]; string
0x1800f21d6  mov     edx, edi; length
0x1800f21d8  lea     r8, [rbp+37h+hstringHeader]; hstringHeader
0x1800f21dc  mov     rcx, r12; sourceString
0x1800f21df  call    cs:__imp_WindowsCreateStringReference
0x1800f21e5  mov     rax, [rbp+37h+string]
0x1800f21e9  xor     r12d, r12d
0x1800f21ec  mov     [rsp+130h+var_E8], rax
0x1800f21f1  test    r15, r15
0x1800f21f4  lea     rax, pvData
0x1800f21fb  cmovz   r15, rax
0x1800f21ff  inc     rbx
0x1800f2202  cmp     [r15+rbx*2], r12w
0x1800f2207  jnz     short loc_1800F21FF
0x1800f2209  mov     eax, 0FFFFFFFFh
0x1800f220e  cmp     rbx, rax
0x1800f2211  jbe     short loc_1800F222A
0x1800f2213  xor     r9d, r9d; lpArguments
0x1800f2216  xor     r8d, r8d; nNumberOfArguments
0x1800f2219  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800f221e  mov     ebx, eax
0x1800f2220  lea     edx, [r9+1]; dwExceptionFlags
0x1800f2224  call    cs:__imp_RaiseException
0x1800f222a  lea     r9, [rbp+37h+var_80]; string
0x1800f222e  mov     edx, ebx; length
0x1800f2230  lea     r8, [rbp+37h+var_78]; hstringHeader
0x1800f2234  mov     rcx, r15; sourceString
0x1800f2237  call    cs:__imp_WindowsCreateStringReference
0x1800f223d  mov     rax, [rbp+37h+var_80]
0x1800f2241  lea     rcx, [rsp+130h+var_F0]
0x1800f2246  mov     [rsp+130h+var_D8], rax
0x1800f224b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800f2250  lea     r8, [rsp+130h+var_E8]
0x1800f2255  lea     rdx, [rsp+130h+var_D8]
0x1800f225a  lea     rcx, [rbp+37h+var_90]
0x1800f225e  call    ??0_lambda_6b6168dda817c5975ee7d3438d2331fe_@@QEAA@AEBUMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@PEBU?$vector_view_base@U?$vector_impl@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@V?$vector@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@V?$allocator@UMeetAndChatFallbackProp@Shell@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMeetAndChatFallbackProp@Shell@Internal@Windows@3@Ucollection_version@23@@5@@Z; _lambda_6b6168dda817c5975ee7d3438d2331fe_::_lambda_6b6168dda817c5975ee7d3438d2331fe_(winrt::Windows::Internal::Shell::MeetAndChatFallbackProp const &,winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Internal::Shell::MeetAndChatFallbackProp,std::vector<winrt::Windows::Internal::Shell::MeetAndChatFallbackProp>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Shell::MeetAndChatFallbackProp,winrt::impl::collection_version> const *)
0x1800f2263  mov     r9, rax
0x1800f2266  lea     r8, [rsp+130h+var_F0]
0x1800f226b  call    ??$_MakeAndInitializeOnSTAThread@VCLaunchActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@V_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@ComTaskPool@Internal@Windows@@CAJW4TaskOptions@12@KPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@2@AEBV_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@@Z; Windows::Internal::ComTaskPool::_MakeAndInitializeOnSTAThread<CLaunchActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,_lambda_6d98a26ab645bb601d6c6842c9556ef9_>(Windows::Internal::TaskOptions,ulong,Windows::ApplicationModel::Activation::IActivatedEventArgs * *,_lambda_6d98a26ab645bb601d6c6842c9556ef9_ const &)
0x1800f2270  mov     ebx, eax
0x1800f2272  test    eax, eax
0x1800f2274  jns     short loc_1800F22DB
0x1800f2276  mov     rcx, [rbp+3Fh]; this
0x1800f227a  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\twinui\\activationhe"...
0x1800f2281  mov     r9d, eax; char *
0x1800f2284  mov     edx, 22h ; '"'; void *
0x1800f2289  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f228e  mov     rcx, [rsp+130h+var_F0]
0x1800f2293  test    rcx, rcx
0x1800f2296  jz      short loc_1800F22A9
0x1800f2298  mov     [rsp+130h+var_F0], r12
0x1800f229d  mov     rax, [rcx]
0x1800f22a0  mov     rax, [rax+10h]
0x1800f22a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f22a9  cmp     [rsp+130h+sourceString], r12
0x1800f22ae  jz      short loc_1800F22BB
0x1800f22b0  mov     rcx, [rsp+130h+sourceString]; pv
0x1800f22b5  call    cs:__imp_CoTaskMemFree
0x1800f22bb  mov     eax, ebx
0x1800f22bd  mov     rcx, [rbp+37h+var_40]
0x1800f22c1  xor     rcx, rsp; StackCookie
0x1800f22c4  call    __security_check_cookie
0x1800f22c9  add     rsp, 100h
0x1800f22d0  pop     r15
0x1800f22d2  pop     r13
0x1800f22d4  pop     r12
0x1800f22d6  pop     rdi
0x1800f22d7  pop     rsi
0x1800f22d8  pop     rbx
0x1800f22d9  pop     rbp
0x1800f22da  retn
0x1800f22db  lea     rcx, [rsp+130h+punkSite]
0x1800f22e0  mov     [rsp+130h+punkSite], r12
0x1800f22e5  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIHolographicViewTransitionNotificationService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIHolographicViewTransitionNotificationService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>)
0x1800f22ea  mov     r8, rax; ppv
0x1800f22ed  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800f22f4  mov     rcx, rsi; punk
0x1800f22f7  call    cs:__imp_IUnknown_GetSite
0x1800f22fd  mov     ebx, eax
0x1800f22ff  test    eax, eax
0x1800f2301  js      loc_1800F23B3
0x1800f2307  test    r13, r13
0x1800f230a  jnz     loc_1800F23D1
0x1800f2310  mov     rax, [rsi]
0x1800f2313  lea     r9, [rbp+37h+var_80]; string
0x1800f2317  mov     rdi, [rsp+130h+var_F0]
0x1800f231c  lea     r8, [rbp+37h+var_78]; hstringHeader
0x1800f2320  mov     edx, 0Eh; length
0x1800f2325  lea     rcx, aWindowsLaunch; "Windows.Launch"
0x1800f232c  mov     r15, [rax+18h]
0x1800f2330  call    cs:__imp_WindowsCreateStringReference
0x1800f2336  test    eax, eax
0x1800f2338  js      loc_1800F2412
0x1800f233e  mov     rdx, [rbp+37h+var_B0]; unsigned __int16 *
0x1800f2342  lea     rcx, [rbp+37h+string]; this
0x1800f2346  mov     rbx, [rbp+37h+var_80]
0x1800f234a  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800f234f  mov     rax, [rbp+37h+var_A8]
0x1800f2353  mov     r9, rbx
0x1800f2356  mov     ecx, [rbp+37h+arg_20]
0x1800f2359  mov     r8, [rbp+37h+var_A0]
0x1800f235d  mov     rdx, [rbp+37h+string]
0x1800f2361  mov     [rsp+130h+var_100], rax
0x1800f2366  mov     rax, r15
0x1800f2369  mov     [rsp+130h+var_108], ecx
0x1800f236d  mov     rcx, rsi
0x1800f2370  mov     [rsp+130h+var_110], rdi
0x1800f2375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f237a  mov     rdx, [rsp+130h+punkSite]; punkSite
0x1800f237f  mov     rcx, rsi; punk
0x1800f2382  mov     ebx, eax
0x1800f2384  call    cs:__imp_IUnknown_SetSite
0x1800f238a  lea     rcx, [rsp+130h+punkSite]
0x1800f238f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f2394  mov     rcx, [rsp+130h+var_F0]
0x1800f2399  test    rcx, rcx
0x1800f239c  jz      loc_1800F22A9
0x1800f23a2  mov     [rsp+130h+var_F0], r12
0x1800f23a7  mov     rdx, [rcx]
0x1800f23aa  mov     rax, [rdx+10h]
0x1800f23ae  jmp     loc_1800F22A4
0x1800f23b3  mov     rcx, [rbp+3Fh]; this
0x1800f23b7  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\twinui\\activationhe"...
0x1800f23be  mov     r9d, eax; char *
0x1800f23c1  mov     edx, 2Bh ; '+'; void *
0x1800f23c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f23cb  nop
0x1800f23cc  jmp     loc_1806F34BA
0x1800f23d1  mov     rax, [rsp+130h+punkSite]
0x1800f23d6  lea     rcx, [rsp+130h+var_E8]
0x1800f23db  mov     [rsp+130h+var_D8], rax
0x1800f23e0  mov     [rsp+130h+var_E8], r12
0x1800f23e5  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800f23ea  lea     r8, [rsp+130h+var_D8]
0x1800f23ef  lea     rdx, [rsp+130h+var_B8]
0x1800f23f4  lea     rcx, [rsp+130h+var_E8]
0x1800f23f9  call    ??$MakeAndInitialize@VCLaunchToMonitor@@V1@AEAPEAUHMONITOR__@@PEAUIUnknown@@@Details@WRL@Microsoft@@YAJPEAPEAVCLaunchToMonitor@@AEAPEAUHMONITOR__@@$$QEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CLaunchToMonitor,CLaunchToMonitor,HMONITOR__ * &,IUnknown *>(CLaunchToMonitor * *,HMONITOR__ * &,IUnknown * &&)
0x1800f23fe  mov     ebx, eax
0x1800f2400  test    eax, eax
0x1800f2402  jns     loc_1806F3476
0x1800f2408  mov     edx, 36h ; '6'
0x1800f240d  jmp     loc_1806F348F
0x1800f2412  xor     r9d, r9d; lpArguments
0x1800f2415  xor     r8d, r8d; nNumberOfArguments
0x1800f2418  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800f241d  lea     edx, [r9+1]; dwExceptionFlags
0x1800f2421  call    cs:__imp_RaiseException
0x1800f2427  jmp     loc_1800F233E
0x1806f3476  mov     rdx, [rsp+130h+var_E8]; punkSite
0x1806f347b  mov     rcx, rsi; punk
0x1806f347e  call    cs:__imp_IUnknown_SetSite
0x1806f3484  mov     ebx, eax
0x1806f3486  test    eax, eax
0x1806f3488  jns     short loc_1806F34DE
0x1806f348a  mov     edx, 37h ; '7'; void *
0x1806f348f  mov     rcx, [rbp+3Fh]; this
0x1806f3493  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\twinui\\activationhe"...
0x1806f349a  mov     r9d, eax; char *
0x1806f349d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1806f34a2  lea     rcx, [rsp+130h+var_E8]
0x1806f34a7  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1806f34ac  mov     rdx, [rsp+130h+punkSite]; punkSite
0x1806f34b1  mov     rcx, rsi; punk
0x1806f34b4  call    cs:__imp_IUnknown_SetSite
0x1806f34ba  lea     rcx, [rsp+130h+punkSite]
0x1806f34bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1806f34c4  lea     rcx, [rsp+130h+var_F0]
0x1806f34c9  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1806f34ce  lea     rcx, [rsp+130h+sourceString]
0x1806f34d3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1806f34d8  nop
0x1806f34d9  jmp     loc_1800F22BB
0x1806f34de  lea     rcx, [rsp+130h+var_E8]
0x1806f34e3  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1806f34e8  nop
0x1806f34e9  jmp     loc_1800F2310
```
