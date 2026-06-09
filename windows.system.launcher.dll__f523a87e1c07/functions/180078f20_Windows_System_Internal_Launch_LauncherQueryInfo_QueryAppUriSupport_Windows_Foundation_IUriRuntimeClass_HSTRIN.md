# Windows::System::Internal::Launch::LauncherQueryInfo::QueryAppUriSupport(Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)

- ea: `0x180078f20`
- end: `0x180079170`
- name: `?QueryAppUriSupport@LauncherQueryInfo@Launch@Internal@System@Windows@@EEAAJPEAUIUriRuntimeClass@Foundation@5@PEAUHSTRING__@@1PEAW4LaunchQuerySupportStatus@45@@Z`
- size: `592`
- prototype: `int(Windows::System::Internal::Launch::LauncherQueryInfo *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, HSTRING, HSTRING, enum Windows::System::LaunchQuerySupportStatus *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180020fe0`
- `0x180021114`
- `0x180028e3c`
- `0x180078f20`
- `0x180079178`
- `0x1800791a4`
- `0x18008a030`
- `0x1800d04d8`
- `0x1800d3a94`
- `0x180111010`

## import_xrefs

- `ext-ms-onecore-appdefaults-l1-1-0!GetUserChoiceForUrl` at `0x1800790b3`
- `ext-ms-onecore-appdefaults-l1-1-0!GetUserChoiceForUrl` at `0x1800790b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800790a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180079092`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800790a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007902b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007902b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800790e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007910a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800790e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007910a`

## string_xrefs

- `0x180078f5e`: `QueryAppUriSupport`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Launch::LauncherQueryInfo::QueryAppUriSupport(
        Windows::System::Internal::Launch::LauncherQueryInfo *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        __int64 a3,
        HSTRING a4,
        enum Windows::System::LaunchQuerySupportStatus *a5)
{
  __int64 v8; // r9
  int StateRepositoryForAppUriHandlerSupport; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v14; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v16; // rax
  int UserChoiceForUrl; // eax
  void *v18; // rcx
  bool v19; // zf
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  bool v23[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  int v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v27[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  *(_DWORD *)a5 = 4;
  wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v27,
    "QueryAppUriSupport");
  v27[0] = &LauncherClientProvider::QueryAppUriSupport::`vftable';
  LauncherClientProvider::QueryAppUriSupport::StartActivity((LauncherClientProvider::QueryAppUriSupport *)v27);
  if ( !a3 )
  {
    v12 = *(_QWORD *)a2;
    string = 0;
    v13 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(v12 + 48);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(a2, &string);
    v10 = v14;
    if ( v14 >= 0 )
    {
      pv = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
      v16 = WindowsGetStringRawBuffer(string, 0);
      UserChoiceForUrl = GetUserChoiceForUrl(v16, StringRawBuffer, &pv);
      v10 = UserChoiceForUrl;
      if ( UserChoiceForUrl >= 0 )
      {
        v18 = pv;
        v19 = pv == 0;
        *(_DWORD *)a5 = pv == 0 ? 3 : 0;
        if ( !v19 )
          CoTaskMemFree(v18);
        WindowsDeleteString(string);
        goto LABEL_17;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)UserChoiceForUrl,
        v21);
      if ( pv )
        CoTaskMemFree(pv);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58C,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v14,
        v21);
    }
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_18;
  }
  *(_QWORD *)v25 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v25);
  StateRepositoryForAppUriHandlerSupport = QueryStateRepositoryForAppUriHandlerSupport(a2, a3, (__int64)a4, v8, v25);
  v10 = StateRepositoryForAppUriHandlerSupport;
  if ( StateRepositoryForAppUriHandlerSupport >= 0 )
  {
    StateRepositoryForAppUriHandlerSupport = EvaluateHandlersForSupport<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo>(
                                               *(_QWORD *)v25,
                                               a3,
                                               a5);
    v10 = StateRepositoryForAppUriHandlerSupport;
    if ( StateRepositoryForAppUriHandlerSupport < 0 )
    {
      v11 = 1415;
      goto LABEL_6;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v25);
LABEL_17:
    v23[0] = *(_DWORD *)a5 == 0;
    LauncherClientProvider::QueryAppUriSupport::QueryStateRepositoryForAppUri<bool>(v27, v23);
    wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v27);
    v10 = 0;
    goto LABEL_18;
  }
  v11 = 1414;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
    (const char *)(unsigned int)StateRepositoryForAppUriHandlerSupport,
    v22);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v25);
LABEL_18:
  LauncherClientProvider::QueryAppUriSupport::~QueryAppUriSupport((LauncherClientProvider::QueryAppUriSupport *)v27);
  return v10;
}

```

## disassembly

```asm
0x180078f20  mov     [rsp-8+arg_0], rbx
0x180078f25  push    rbp
0x180078f26  push    rsi
0x180078f27  push    rdi
0x180078f28  push    r14
0x180078f2a  push    r15
0x180078f2c  lea     rbp, [rsp-0B0h]
0x180078f34  sub     rsp, 1B0h
0x180078f3b  mov     rax, cs:__security_cookie
0x180078f42  xor     rax, rsp
0x180078f45  mov     [rbp+0D0h+var_30], rax
0x180078f4c  mov     rdi, [rbp+0D0h+arg_20]
0x180078f53  lea     rcx, [rsp+1D0h+var_180]
0x180078f58  mov     r14, rdx
0x180078f5b  mov     r15, r9
0x180078f5e  lea     rdx, aQueryappurisup; "QueryAppUriSupport"
0x180078f65  mov     rsi, r8
0x180078f68  mov     dword ptr [rdi], 4
0x180078f6e  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180078f73  lea     rax, ??_7QueryAppUriSupport@LauncherClientProvider@@6B@; const LauncherClientProvider::QueryAppUriSupport::`vftable'
0x180078f7a  lea     rcx, [rsp+1D0h+var_180]; this
0x180078f7f  mov     [rsp+1D0h+var_180], rax
0x180078f84  call    ?StartActivity@QueryAppUriSupport@LauncherClientProvider@@QEAAXXZ; LauncherClientProvider::QueryAppUriSupport::StartActivity(void)
0x180078f89  test    rsi, rsi
0x180078f8c  jz      loc_180079019
0x180078f92  lea     rcx, [rsp+1D0h+var_190]
0x180078f97  mov     qword ptr [rsp+1D0h+var_190], 0
0x180078fa0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180078fa5  lea     rax, [rsp+1D0h+var_190]
0x180078faa  mov     r8, r15
0x180078fad  mov     rdx, rsi
0x180078fb0  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x180078fb5  mov     rcx, r14
0x180078fb8  call    ?QueryStateRepositoryForAppUriHandlerSupport@@YAJPEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@1PEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@23@PEAPEAU?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@623@@Z; QueryStateRepositoryForAppUriHandlerSupport(Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> * *)
0x180078fbd  mov     ebx, eax
0x180078fbf  test    eax, eax
0x180078fc1  jns     short loc_180078FCA
0x180078fc3  mov     edx, 586h
0x180078fc8  jmp     short loc_180078FE5
0x180078fca  mov     rcx, qword ptr [rsp+1D0h+var_190]
0x180078fcf  mov     r8, rdi
0x180078fd2  mov     rdx, rsi
0x180078fd5  call    ??$EvaluateHandlersForSupport@VAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@@YAJPEAU?$IVectorView@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAW4LaunchQuerySupportStatus@System@3@@Z; EvaluateHandlersForSupport<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *> *,HSTRING__ *,Windows::System::LaunchQuerySupportStatus *)
0x180078fda  mov     ebx, eax
0x180078fdc  test    eax, eax
0x180078fde  jns     short loc_18007900A
0x180078fe0  mov     edx, 587h; void *
0x180078fe5  mov     rcx, [rbp+0D8h]; this
0x180078fec  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180078ff3  mov     r9d, eax; char *
0x180078ff6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078ffb  lea     rcx, [rsp+1D0h+var_190]
0x180079000  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079005  jmp     loc_18007913E
0x18007900a  lea     rcx, [rsp+1D0h+var_190]
0x18007900f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079014  jmp     loc_18007911B
0x180079019  mov     rax, [r14]
0x18007901c  xor     ecx, ecx; string
0x18007901e  mov     [rsp+1D0h+string], 0
0x180079027  mov     rbx, [rax+30h]
0x18007902b  call    cs:__imp_WindowsDeleteString
0x180079031  lea     rdx, [rsp+1D0h+string]
0x180079036  mov     [rsp+1D0h+string], 0
0x18007903f  mov     rcx, r14
0x180079042  mov     rax, rbx
0x180079045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007904a  mov     ebx, eax
0x18007904c  test    eax, eax
0x18007904e  jns     short loc_180079084
0x180079050  mov     rcx, [rbp+0D8h]; this
0x180079057  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18007905e  mov     r9d, eax; char *
0x180079061  mov     edx, 58Ch; void *
0x180079066  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007906b  mov     rcx, [rsp+1D0h+string]; string
0x180079070  call    cs:__imp_WindowsDeleteString
0x180079076  mov     [rsp+1D0h+string], 0
0x18007907f  jmp     loc_18007913E
0x180079084  xor     edx, edx; length
0x180079086  mov     [rsp+1D0h+pv], 0
0x18007908f  mov     rcx, r15; string
0x180079092  call    cs:__imp_WindowsGetStringRawBuffer
0x180079098  mov     rcx, [rsp+1D0h+string]; string
0x18007909d  xor     edx, edx; length
0x18007909f  mov     rbx, rax
0x1800790a2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800790a8  lea     r8, [rsp+1D0h+pv]
0x1800790ad  mov     rdx, rbx
0x1800790b0  mov     rcx, rax
0x1800790b3  call    cs:__imp_GetUserChoiceForUrl
0x1800790b9  mov     ebx, eax
0x1800790bb  test    eax, eax
0x1800790bd  jns     short loc_1800790EF
0x1800790bf  mov     rcx, [rbp+0D8h]; this
0x1800790c6  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800790cd  mov     r9d, eax; char *
0x1800790d0  mov     edx, 58Fh; void *
0x1800790d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800790da  mov     rcx, [rsp+1D0h+pv]; pv
0x1800790df  test    rcx, rcx
0x1800790e2  jz      short loc_18007906B
0x1800790e4  call    cs:__imp_CoTaskMemFree
0x1800790ea  jmp     loc_18007906B
0x1800790ef  mov     rcx, [rsp+1D0h+pv]; pv
0x1800790f4  test    rcx, rcx
0x1800790f7  setnz   al
0x1800790fa  neg     al
0x1800790fc  sbb     edx, edx
0x1800790fe  not     edx
0x180079100  and     edx, 3
0x180079103  mov     [rdi], edx
0x180079105  test    rcx, rcx
0x180079108  jz      short loc_180079110
0x18007910a  call    cs:__imp_CoTaskMemFree
0x180079110  mov     rcx, [rsp+1D0h+string]; string
0x180079115  call    cs:__imp_WindowsDeleteString
0x18007911b  cmp     dword ptr [rdi], 0
0x18007911e  lea     rdx, [rsp+1D0h+var_1A0]
0x180079123  lea     rcx, [rsp+1D0h+var_180]
0x180079128  setz    [rsp+1D0h+var_1A0]
0x18007912d  call    ??$QueryStateRepositoryForAppUri@_N@QueryAppUriSupport@LauncherClientProvider@@QEAAX$$QEA_N@Z; LauncherClientProvider::QueryAppUriSupport::QueryStateRepositoryForAppUri<bool>(bool &&)
0x180079132  lea     rcx, [rsp+1D0h+var_180]
0x180079137  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18007913c  xor     ebx, ebx
0x18007913e  lea     rcx, [rsp+1D0h+var_180]; this
0x180079143  call    ??1QueryAppUriSupport@LauncherClientProvider@@QEAA@XZ; LauncherClientProvider::QueryAppUriSupport::~QueryAppUriSupport(void)
0x180079148  mov     eax, ebx
0x18007914a  mov     rcx, [rbp+0D0h+var_30]
0x180079151  xor     rcx, rsp; StackCookie
0x180079154  call    __security_check_cookie
0x180079159  mov     rbx, [rsp+1D0h+arg_0]
0x180079161  add     rsp, 1B0h
0x180079168  pop     r15
0x18007916a  pop     r14
0x18007916c  pop     rdi
0x18007916d  pop     rsi
0x18007916e  pop     rbp
0x18007916f  retn
```
