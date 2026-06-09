# LauncherService::LaunchFolderPath(unsigned __int64,HSTRING__ *)

- ea: `0x180068670`
- end: `0x1800689ae`
- name: `?LaunchFolderPath@LauncherService@@UEAAJ_KPEAUHSTRING__@@@Z`
- size: `830`
- prototype: `int(LauncherService *__hidden this, unsigned __int64, HSTRING)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180047254`
- `0x18004e550`
- `0x1800596d8`
- `0x18006323c`
- `0x18006465c`
- `0x180067840`
- `0x180068670`
- `0x1800689b4`
- `0x180068a30`
- `0x180068a80`
- `0x180068af4`
- `0x180068bb8`
- `0x180068be4`
- `0x180087fb0`
- `0x18008a030`
- `0x1800af048`
- `0x1800b8fcc`
- `0x1800baf34`
- `0x180111010`

## import_xrefs

- `Windows.Storage!SHCreateItemFromParsingName` at `0x1800687a7`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x1800687a7`
- `Windows.Storage!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller` at `0x1800687f7`
- `Windows.Storage!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller` at `0x1800687f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006870e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006870e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180068739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800686cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006896d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800686cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068914`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006896d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068961`

## string_xrefs

- `0x1800686ec`: `onecoreuap\shell\windows.system.launcher\lib\launcherservice.cpp`
- `0x180068698`: `LaunchFolderPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall LauncherService::LaunchFolderPath(LauncherService *this, __int64 a2, HSTRING a3)
{
  HSTRING *v5; // rdx
  int CallerAumidOrProcessName; // eax
  PCWSTR StringRawBuffer; // rax
  int v8; // eax
  WCHAR *v9; // rbx
  HRESULT v10; // esi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  IUnknown *v14; // rsi
  __int64 v15; // rax
  int v16; // eax
  int v18; // [rsp+20h] [rbp-1E8h] BYREF
  struct Windows::Storage::IStorageItem *v19; // [rsp+28h] [rbp-1E0h] BYREF
  IUnknown *v20; // [rsp+30h] [rbp-1D8h] BYREF
  PCWSTR pszPath; // [rsp+38h] [rbp-1D0h] BYREF
  void *ppv; // [rsp+40h] [rbp-1C8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-1C0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-1B8h] BYREF
  _BYTE v25[40]; // [rsp+58h] [rbp-1B0h] BYREF
  HSTRING v26; // [rsp+80h] [rbp-188h]
  _QWORD v27[42]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v27);
  v27[0] = &LauncherServiceProvider::LaunchFolderPath::`vftable';
  LauncherServiceProvider::LaunchFolderPath::StartActivity((LauncherServiceProvider::LaunchFolderPath *)v27);
  WindowsDeleteString(0);
  string = 0;
  CallerAumidOrProcessName = LauncherMiscHelpers::GetCallerAumidOrProcessName((LauncherMiscHelpers *)&string, v5);
  if ( CallerAumidOrProcessName < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)CallerAumidOrProcessName,
      v18);
  pszPath = WindowsGetStringRawBuffer(string, 0);
  LauncherServiceProvider::LaunchFolderPath::LaunchFolderPathRequest<unsigned short const *>(v27, &pszPath);
  pszPath = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v8 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         StringRawBuffer,
         &pszPath);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v8,
      v18);
  v9 = (WCHAR *)pszPath;
  if ( !pszPath )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x8007000ELL,
      v18);
  ppv = 0;
  v10 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( v10 < 0 )
  {
    LauncherServiceProvider::LaunchFolderPath::PathNotValid((LauncherServiceProvider::LaunchFolderPath *)v27);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D2,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v10,
      v18);
  }
  v20 = 0;
  v11 = STORAGE_CreateStorageItemFromShellItem_FullTrustCaller(
          ppv,
          4096,
          &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b,
          &v20);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v11,
      v18);
  v19 = 0;
  v12 = Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v20,
          (__int64)&v19);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v12,
      v18);
  wil::GetActivationFactory<Windows::Internal::IBrokeredFileExplorerHelpersStatics>(&v24);
  v18 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::IStorageItem *, int *))(*(_QWORD *)v24 + 104LL))(
          v24,
          v19,
          &v18);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v13,
      v18);
  if ( v18 )
  {
    LauncherServiceProvider::LaunchFolderPath::PathIsRestricted<enum Windows::Internal::StorageItemRestrictionFlags &>(
      v27,
      &v18);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)0x80070057LL,
      v18);
  }
  v14 = v20;
  v15 = CallerInformation::Capture(v25, a2, 0);
  v16 = LaunchFileExplorer(v15, v14, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\launcherservice.cpp",
      (const char *)(unsigned int)v16,
      v18);
  WindowsDeleteString(v26);
  TryAddItemToRecent(v19);
  wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v27);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v24);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  CoTaskMemFree(v9);
  WindowsDeleteString(string);
  LauncherServiceProvider::LaunchFolderPath::~LaunchFolderPath((LauncherServiceProvider::LaunchFolderPath *)v27);
  return 0;
}

```

## disassembly

```asm
0x180068670  mov     [rsp+arg_0], rbx
0x180068675  push    rsi
0x180068676  push    rdi
0x180068677  push    r14
0x180068679  sub     rsp, 1F0h
0x180068680  mov     rax, cs:__security_cookie
0x180068687  xor     rax, rsp
0x18006868a  mov     [rsp+208h+var_28], rax
0x180068692  mov     rbx, r8
0x180068695  mov     r14, rdx
0x180068698  lea     rdx, aLaunchfolderpa_0; "LaunchFolderPath"
0x18006869f  lea     rcx, [rsp+208h+var_178]; struct wil::details::IFailureCallback *
0x1800686a7  call    ??0?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800686ac  lea     rax, ??_7LaunchFolderPath@LauncherServiceProvider@@6B@; const LauncherServiceProvider::LaunchFolderPath::`vftable'
0x1800686b3  mov     [rsp+208h+var_178], rax
0x1800686bb  lea     rcx, [rsp+208h+var_178]; this
0x1800686c3  call    ?StartActivity@LaunchFolderPath@LauncherServiceProvider@@QEAAXXZ; LauncherServiceProvider::LaunchFolderPath::StartActivity(void)
0x1800686c8  nop
0x1800686c9  xor     ecx, ecx; string
0x1800686cb  call    cs:__imp_WindowsDeleteString
0x1800686d1  mov     [rsp+208h+string], 0
0x1800686da  lea     rcx, [rsp+208h+string]; this
0x1800686df  call    ?GetCallerAumidOrProcessName@LauncherMiscHelpers@@YAJPEAPEAUHSTRING__@@@Z; LauncherMiscHelpers::GetCallerAumidOrProcessName(HSTRING__ * *)
0x1800686e4  mov     rcx, [rsp+208h]; this
0x1800686ec  lea     rdi, aOnecoreuapShel_13; "onecoreuap\\shell\\windows.system.launc"...
0x1800686f3  test    eax, eax
0x1800686f5  jns     short loc_180068707
0x1800686f7  mov     r9d, eax; char *
0x1800686fa  mov     r8, rdi; unsigned int
0x1800686fd  mov     edx, 1C5h; void *
0x180068702  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180068707  xor     edx, edx; length
0x180068709  mov     rcx, [rsp+208h+string]; string
0x18006870e  call    cs:__imp_WindowsGetStringRawBuffer
0x180068714  mov     [rsp+208h+pszPath], rax
0x180068719  lea     rdx, [rsp+208h+pszPath]
0x18006871e  lea     rcx, [rsp+208h+var_178]
0x180068726  call    ??$LaunchFolderPathRequest@PEBG@LaunchFolderPath@LauncherServiceProvider@@QEAAX$$QEAPEBG@Z; LauncherServiceProvider::LaunchFolderPath::LaunchFolderPathRequest<ushort const *>(ushort const * &&)
0x18006872b  mov     [rsp+208h+pszPath], 0
0x180068734  xor     edx, edx; length
0x180068736  mov     rcx, rbx; string
0x180068739  call    cs:__imp_WindowsGetStringRawBuffer
0x18006873f  mov     rcx, rax
0x180068742  lea     rdx, [rsp+208h+pszPath]
0x180068747  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18006874c  mov     rcx, [rsp+208h]; this
0x180068754  test    eax, eax
0x180068756  jns     short loc_180068768
0x180068758  mov     r9d, eax; char *
0x18006875b  mov     r8, rdi; unsigned int
0x18006875e  mov     edx, 1CAh; void *
0x180068763  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068768  mov     rcx, [rsp+208h]; this
0x180068770  mov     rbx, [rsp+208h+pszPath]
0x180068775  test    rbx, rbx
0x180068778  jnz     short loc_18006878D
0x18006877a  mov     r9d, 8007000Eh; char *
0x180068780  mov     r8, rdi; unsigned int
0x180068783  mov     edx, 1CBh; void *
0x180068788  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006878d  mov     [rsp+208h+ppv], 0
0x180068796  lea     r9, [rsp+208h+ppv]; ppv
0x18006879b  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800687a2  xor     edx, edx; pbc
0x1800687a4  mov     rcx, rbx; pszPath
0x1800687a7  call    cs:__imp_SHCreateItemFromParsingName
0x1800687ad  mov     esi, eax
0x1800687af  test    eax, eax
0x1800687b1  jns     short loc_1800687D8
0x1800687b3  lea     rcx, [rsp+208h+var_178]; this
0x1800687bb  call    ?PathNotValid@LaunchFolderPath@LauncherServiceProvider@@QEAAXXZ; LauncherServiceProvider::LaunchFolderPath::PathNotValid(void)
0x1800687c0  mov     rcx, [rsp+208h]; this
0x1800687c8  mov     r9d, esi; char *
0x1800687cb  mov     r8, rdi; unsigned int
0x1800687ce  mov     edx, 1D2h; void *
0x1800687d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800687d8  mov     [rsp+208h+var_1D8], 0
0x1800687e1  lea     r9, [rsp+208h+var_1D8]
0x1800687e6  lea     r8, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x1800687ed  mov     edx, 1000h
0x1800687f2  mov     rcx, [rsp+208h+ppv]
0x1800687f7  call    cs:__imp_STORAGE_CreateStorageItemFromShellItem_FullTrustCaller
0x1800687fd  mov     rcx, [rsp+208h]; this
0x180068805  test    eax, eax
0x180068807  jns     short loc_180068819
0x180068809  mov     r9d, eax; char *
0x18006880c  mov     r8, rdi; unsigned int
0x18006880f  mov     edx, 1D6h; void *
0x180068814  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068819  mov     [rsp+208h+var_1E0], 0
0x180068822  lea     rdx, [rsp+208h+var_1E0]
0x180068827  lea     rcx, [rsp+208h+var_1D8]
0x18006882c  call    ??$As@UIStorageItem@Storage@Windows@@@?$ComPtr@UIStorageFolder@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageFolder>::As<Windows::Storage::IStorageItem>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>>)
0x180068831  mov     rcx, [rsp+208h]; this
0x180068839  test    eax, eax
0x18006883b  jns     short loc_18006884D
0x18006883d  mov     r9d, eax; char *
0x180068840  mov     r8, rdi; unsigned int
0x180068843  mov     edx, 1D9h; void *
0x180068848  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006884d  lea     rcx, [rsp+208h+var_1B8]
0x180068852  call    ??$GetActivationFactory@UIBrokeredFileExplorerHelpersStatics@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIBrokeredFileExplorerHelpersStatics@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::IBrokeredFileExplorerHelpersStatics>(ushort const *)
0x180068857  nop
0x180068858  mov     [rsp+208h+var_1E8], 0; int
0x180068860  mov     rcx, [rsp+208h+var_1B8]
0x180068865  mov     rax, [rcx]
0x180068868  lea     r8, [rsp+208h+var_1E8]
0x18006886d  mov     rdx, [rsp+208h+var_1E0]
0x180068872  mov     rax, [rax+68h]
0x180068876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006887b  mov     rcx, [rsp+208h]; this
0x180068883  test    eax, eax
0x180068885  jns     short loc_180068897
0x180068887  mov     r9d, eax; char *
0x18006888a  mov     r8, rdi; unsigned int
0x18006888d  mov     edx, 1DDh; void *
0x180068892  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068897  cmp     [rsp+208h+var_1E8], 0
0x18006889c  jz      short loc_1800688CB
0x18006889e  lea     rdx, [rsp+208h+var_1E8]
0x1800688a3  lea     rcx, [rsp+208h+var_178]
0x1800688ab  call    ??$PathIsRestricted@AEAW4StorageItemRestrictionFlags@Internal@Windows@@@LaunchFolderPath@LauncherServiceProvider@@QEAAXAEAW4StorageItemRestrictionFlags@Internal@Windows@@@Z; LauncherServiceProvider::LaunchFolderPath::PathIsRestricted<Windows::Internal::StorageItemRestrictionFlags &>(Windows::Internal::StorageItemRestrictionFlags &)
0x1800688b0  mov     rcx, [rsp+208h]; this
0x1800688b8  mov     r9d, 80070057h; char *
0x1800688be  mov     r8, rdi; unsigned int
0x1800688c1  mov     edx, 1E2h; void *
0x1800688c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800688cb  mov     rsi, [rsp+208h+var_1D8]
0x1800688d0  xor     r8d, r8d
0x1800688d3  mov     rdx, r14
0x1800688d6  lea     rcx, [rsp+208h+var_1B0]
0x1800688db  call    ?Capture@CallerInformation@@SA?AV1@_K0@Z; CallerInformation::Capture(unsigned __int64,unsigned __int64)
0x1800688e0  nop
0x1800688e1  xor     r8d, r8d
0x1800688e4  mov     rdx, rsi
0x1800688e7  mov     rcx, rax
0x1800688ea  call    ?LaunchFileExplorer@@YAJAEBVCallerInformation@@PEAUIStorageFolder@Storage@Windows@@PEAU?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@4@@Z; LaunchFileExplorer(CallerInformation const &,Windows::Storage::IStorageFolder *,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *> *)
0x1800688ef  mov     rcx, [rsp+208h]; this
0x1800688f7  test    eax, eax
0x1800688f9  jns     short loc_18006890C
0x1800688fb  mov     r9d, eax; char *
0x1800688fe  mov     r8, rdi; unsigned int
0x180068901  mov     edx, 1E6h; void *
0x180068906  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006890c  mov     rcx, [rsp+208h+var_188]; string
0x180068914  call    cs:__imp_WindowsDeleteString
0x18006891a  mov     rcx, [rsp+208h+var_1E0]; struct Windows::Storage::IStorageItem *
0x18006891f  call    ?TryAddItemToRecent@@YAXPEAUIStorageItem@Storage@Windows@@@Z; TryAddItemToRecent(Windows::Storage::IStorageItem *)
0x180068924  lea     rcx, [rsp+208h+var_178]
0x18006892c  call    ?Stop@?$ActivityBase@VLauncherServiceProvider@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherServiceProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180068931  nop
0x180068932  lea     rcx, [rsp+208h+var_1B8]
0x180068937  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18006893c  nop
0x18006893d  lea     rcx, [rsp+208h+var_1E0]
0x180068942  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180068947  nop
0x180068948  lea     rcx, [rsp+208h+var_1D8]
0x18006894d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180068952  nop
0x180068953  lea     rcx, [rsp+208h+ppv]
0x180068958  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006895d  nop
0x18006895e  mov     rcx, rbx; pv
0x180068961  call    cs:__imp_CoTaskMemFree
0x180068967  nop
0x180068968  mov     rcx, [rsp+208h+string]; string
0x18006896d  call    cs:__imp_WindowsDeleteString
0x180068973  nop
0x180068974  lea     rcx, [rsp+208h+var_178]; this
0x18006897c  call    ??1LaunchFolderPath@LauncherServiceProvider@@QEAA@XZ; LauncherServiceProvider::LaunchFolderPath::~LaunchFolderPath(void)
0x180068981  xor     eax, eax
0x180068983  jmp     short loc_180068989
0x180068985  mov     eax, [rsp+208h+var_1E8]
0x180068989  mov     rcx, [rsp+208h+var_28]
0x180068991  xor     rcx, rsp; StackCookie
0x180068994  call    __security_check_cookie
0x180068999  mov     rbx, [rsp+208h+arg_0]
0x1800689a1  add     rsp, 1F0h
0x1800689a8  pop     r14
0x1800689aa  pop     rdi
0x1800689ab  pop     rsi
0x1800689ac  retn
```
