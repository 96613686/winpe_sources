# QueryAssociationBroker::GetUserChoiceForUrl(HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x180067520`
- end: `0x180067799`
- name: `?GetUserChoiceForUrl@QueryAssociationBroker@@UEAAJPEAUHSTRING__@@0PEAPEAU2@@Z`
- size: `633`
- prototype: `int(QueryAssociationBroker *__hidden this, HSTRING, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180032bf0`
- `0x18003d318`
- `0x18006465c`
- `0x180067520`
- `0x1800677a0`
- `0x1800677cc`
- `0x180067840`
- `0x180067928`
- `0x180076930`
- `0x180081548`
- `0x18008a030`
- `0x1800baddc`
- `0x180111010`

## import_xrefs

- `ext-ms-onecore-appdefaults-l1-1-0!GetUserChoiceForUrl` at `0x18006766a`
- `ext-ms-onecore-appdefaults-l1-1-0!GetUserChoiceForUrl` at `0x18006766a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800675b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800675b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800675df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067735`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800675df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067757`

## string_xrefs

- `0x18006760d`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x18006767f`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x1800676dd`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall QueryAssociationBroker::GetUserChoiceForUrl(
        QueryAssociationBroker *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING *a4)
{
  void *v7; // rbx
  PCWSTR StringRawBuffer; // r14
  unsigned __int16 **v9; // rdx
  void **v10; // r8
  const WCHAR *v11; // rax
  struct Windows::Foundation::IUriRuntimeClass *v12; // rsi
  __int64 (__fastcall *v13)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rdi
  int v14; // eax
  PCWSTR v15; // rax
  int UserChoiceForUrl; // eax
  HSTRING v17; // rcx
  int v18; // eax
  HSTRING v20; // [rsp+20h] [rbp-1B8h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-1B0h] BYREF
  HSTRING string; // [rsp+30h] [rbp-1A8h] BYREF
  void *v23; // [rsp+38h] [rbp-1A0h] BYREF
  void *v24; // [rsp+40h] [rbp-198h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v25; // [rsp+48h] [rbp-190h] BYREF
  _QWORD v26[42]; // [rsp+50h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v26);
  v26[0] = &LauncherServiceProvider::GetUserChoiceForUrl::`vftable';
  LauncherServiceProvider::GetUserChoiceForUrl::StartActivity((LauncherServiceProvider::GetUserChoiceForUrl *)v26);
  v7 = 0;
  v24 = 0;
  if ( a3 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v24,
      0);
    UserAwareCallerIdentity::GetCallingProcessPackageFamilyName((UserAwareCallerIdentity *)&v24, v9, v10);
    v7 = v24;
    StringRawBuffer = (PCWSTR)v24;
  }
  v11 = WindowsGetStringRawBuffer(a2, 0);
  CreateRuntimeUri(&v25, v11);
  string = 0;
  v12 = v25;
  v13 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)v25 + 88LL);
  WindowsDeleteString(0);
  string = 0;
  v14 = v13(v12, &string);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5CB,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v14,
      (int)v20);
  v23 = (void *)WindowsGetStringRawBuffer(string, 0);
  LauncherServiceProvider::GetUserChoiceForUrl::CallGetUserChoice<unsigned short const *>((__int64)v26, (__int64 *)&v23);
  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v15 = WindowsGetStringRawBuffer(a2, 0);
  UserChoiceForUrl = GetUserChoiceForUrl(v15, StringRawBuffer, &pv);
  if ( UserChoiceForUrl < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5CF,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)UserChoiceForUrl,
      (int)v20);
  v23 = pv;
  LauncherServiceProvider::GetUserChoiceForUrl::UserChoiceDetermined<unsigned short *>(v26, &v23);
  v17 = 0;
  v20 = 0;
  if ( pv )
  {
    v23 = pv;
    v18 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v20, &v23);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5D8,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
        (const char *)(unsigned int)v18,
        (int)v20);
    v17 = v20;
  }
  v20 = 0;
  *a4 = v17;
  wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v26);
  WindowsDeleteString(v20);
  v20 = 0;
  if ( pv )
    CoTaskMemFree(pv);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  if ( v7 )
    CoTaskMemFree(v7);
  LauncherServiceProvider::GetUserChoiceForUrl::~GetUserChoiceForUrl((LauncherServiceProvider::GetUserChoiceForUrl *)v26);
  return 0;
}

```

## disassembly

```asm
0x180067520  mov     [rsp+arg_0], rbx
0x180067525  push    rsi
0x180067526  push    rdi
0x180067527  push    r12
0x180067529  push    r14
0x18006752b  push    r15
0x18006752d  sub     rsp, 1B0h
0x180067534  mov     rax, cs:__security_cookie
0x18006753b  xor     rax, rsp
0x18006753e  mov     [rsp+1D8h+var_38], rax
0x180067546  mov     r12, r9
0x180067549  mov     rdi, r8
0x18006754c  mov     r15, rdx
0x18006754f  lea     rdx, aGetuserchoicef_0; "GetUserChoiceForUrl"
0x180067556  lea     rcx, [rsp+1D8h+var_188]; struct wil::details::IFailureCallback *
0x18006755b  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180067560  lea     rax, ??_7GetUserChoiceForUrl@LauncherServiceProvider@@6B@; const LauncherServiceProvider::GetUserChoiceForUrl::`vftable'
0x180067567  mov     [rsp+1D8h+var_188], rax
0x18006756c  lea     rcx, [rsp+1D8h+var_188]; this
0x180067571  call    ?StartActivity@GetUserChoiceForUrl@LauncherServiceProvider@@QEAAXXZ; LauncherServiceProvider::GetUserChoiceForUrl::StartActivity(void)
0x180067576  nop
0x180067577  xor     ebx, ebx
0x180067579  mov     [rsp+1D8h+var_198], rbx
0x18006757e  xor     edx, edx; length
0x180067580  test    rdi, rdi
0x180067583  jz      short loc_180067593
0x180067585  mov     rcx, rdi; string
0x180067588  call    cs:__imp_WindowsGetStringRawBuffer
0x18006758e  mov     r14, rax
0x180067591  jmp     short loc_1800675AF
0x180067593  lea     rcx, [rsp+1D8h+var_198]
0x180067598  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006759d  lea     rcx, [rsp+1D8h+var_198]; this
0x1800675a2  call    ?GetCallingProcessPackageFamilyName@UserAwareCallerIdentity@@YAJPEAPEAG@Z; UserAwareCallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x1800675a7  mov     rbx, [rsp+1D8h+var_198]
0x1800675ac  mov     r14, rbx
0x1800675af  xor     edx, edx; length
0x1800675b1  mov     rcx, r15; string
0x1800675b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800675ba  mov     rdx, rax; sourceString
0x1800675bd  lea     rcx, [rsp+1D8h+var_190]; struct Windows::Foundation::IUriRuntimeClass **
0x1800675c2  call    ?CreateRuntimeUri@@YA?AV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEBG@Z; CreateRuntimeUri(ushort const *)
0x1800675c7  nop
0x1800675c8  mov     [rsp+1D8h+string], 0
0x1800675d1  mov     rsi, [rsp+1D8h+var_190]
0x1800675d6  mov     rax, [rsi]
0x1800675d9  mov     rdi, [rax+58h]
0x1800675dd  xor     ecx, ecx; string
0x1800675df  call    cs:__imp_WindowsDeleteString
0x1800675e5  mov     [rsp+1D8h+string], 0
0x1800675ee  lea     rdx, [rsp+1D8h+string]
0x1800675f3  mov     rcx, rsi
0x1800675f6  mov     rax, rdi
0x1800675f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675fe  mov     rcx, [rsp+1D8h]; this
0x180067606  test    eax, eax
0x180067608  jns     short loc_18006761E
0x18006760a  mov     r9d, eax; char *
0x18006760d  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180067614  mov     edx, 5CBh; void *
0x180067619  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006761e  xor     edx, edx; length
0x180067620  mov     rcx, [rsp+1D8h+string]; string
0x180067625  call    cs:__imp_WindowsGetStringRawBuffer
0x18006762b  mov     [rsp+1D8h+var_1A0], rax
0x180067630  lea     rdx, [rsp+1D8h+var_1A0]
0x180067635  lea     rcx, [rsp+1D8h+var_188]
0x18006763a  call    ??$CallGetUserChoice@PEBG@GetUserChoiceForUrl@LauncherServiceProvider@@QEAAX$$QEAPEBG@Z; LauncherServiceProvider::GetUserChoiceForUrl::CallGetUserChoice<ushort const *>(ushort const * &&)
0x18006763f  mov     [rsp+1D8h+pv], 0
0x180067648  xor     edx, edx
0x18006764a  lea     rcx, [rsp+1D8h+pv]
0x18006764f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180067654  xor     edx, edx; length
0x180067656  mov     rcx, r15; string
0x180067659  call    cs:__imp_WindowsGetStringRawBuffer
0x18006765f  lea     r8, [rsp+1D8h+pv]
0x180067664  mov     rdx, r14
0x180067667  mov     rcx, rax
0x18006766a  call    cs:__imp_GetUserChoiceForUrl
0x180067670  mov     rcx, [rsp+1D8h]; this
0x180067678  test    eax, eax
0x18006767a  jns     short loc_180067690
0x18006767c  mov     r9d, eax; char *
0x18006767f  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x180067686  mov     edx, 5CFh; void *
0x18006768b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067690  mov     rax, [rsp+1D8h+pv]
0x180067695  mov     [rsp+1D8h+var_1A0], rax
0x18006769a  lea     rdx, [rsp+1D8h+var_1A0]
0x18006769f  lea     rcx, [rsp+1D8h+var_188]
0x1800676a4  call    ??$UserChoiceDetermined@PEAG@GetUserChoiceForUrl@LauncherServiceProvider@@QEAAX$$QEAPEAG@Z; LauncherServiceProvider::GetUserChoiceForUrl::UserChoiceDetermined<ushort *>(ushort * &&)
0x1800676a9  xor     ecx, ecx
0x1800676ab  mov     [rsp+1D8h+var_1B8], rcx; int
0x1800676b0  mov     rax, [rsp+1D8h+pv]
0x1800676b5  test    rax, rax
0x1800676b8  jz      short loc_1800676F3
0x1800676ba  mov     [rsp+1D8h+var_1A0], rax
0x1800676bf  lea     rdx, [rsp+1D8h+var_1A0]
0x1800676c4  lea     rcx, [rsp+1D8h+var_1B8]
0x1800676c9  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800676ce  mov     rcx, [rsp+1D8h]; this
0x1800676d6  test    eax, eax
0x1800676d8  jns     short loc_1800676EE
0x1800676da  mov     r9d, eax; char *
0x1800676dd  lea     r8, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800676e4  mov     edx, 5D8h; void *
0x1800676e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800676ee  mov     rcx, [rsp+1D8h+var_1B8]
0x1800676f3  mov     [rsp+1D8h+var_1B8], 0
0x1800676fc  mov     [r12], rcx
0x180067700  lea     rcx, [rsp+1D8h+var_188]
0x180067705  call    ?Stop@?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006770a  nop
0x18006770b  mov     rcx, [rsp+1D8h+var_1B8]; string
0x180067710  call    cs:__imp_WindowsDeleteString
0x180067716  mov     [rsp+1D8h+var_1B8], 0
0x18006771f  mov     rcx, [rsp+1D8h+pv]; pv
0x180067724  test    rcx, rcx
0x180067727  jz      short loc_180067730
0x180067729  call    cs:__imp_CoTaskMemFree
0x18006772f  nop
0x180067730  mov     rcx, [rsp+1D8h+string]; string
0x180067735  call    cs:__imp_WindowsDeleteString
0x18006773b  mov     [rsp+1D8h+string], 0
0x180067744  lea     rcx, [rsp+1D8h+var_190]
0x180067749  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006774e  nop
0x18006774f  test    rbx, rbx
0x180067752  jz      short loc_18006775E
0x180067754  mov     rcx, rbx; pv
0x180067757  call    cs:__imp_CoTaskMemFree
0x18006775d  nop
0x18006775e  lea     rcx, [rsp+1D8h+var_188]; this
0x180067763  call    ??1GetUserChoiceForUrl@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::GetUserChoiceForUrl::~GetUserChoiceForUrl(void)
0x180067768  xor     eax, eax
0x18006776a  jmp     short loc_180067770
0x18006776c  mov     eax, dword ptr [rsp+1D8h+var_1B8]
0x180067770  mov     rcx, [rsp+1D8h+var_38]
0x180067778  xor     rcx, rsp; StackCookie
0x18006777b  call    __security_check_cookie
0x180067780  mov     rbx, [rsp+1D8h+arg_0]
0x180067788  add     rsp, 1B0h
0x18006778f  pop     r15
0x180067791  pop     r14
0x180067793  pop     r12
0x180067795  pop     rdi
0x180067796  pop     rsi
0x180067797  retn
```
