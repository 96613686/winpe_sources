# CBrokeredLauncher::_LaunchFolderAsync(Windows::System::ILauncherStatics *,Windows::Storage::IStorageFolder *,HSTRING__ *,Windows::System::IFolderLauncherOptions *,ITelemetryCorrelationVector *)

- ea: `0x180085f20`
- end: `0x1800862db`
- name: `?_LaunchFolderAsync@CBrokeredLauncher@@CA?AV?$ComPtr@U?$IAsyncOperation@_N@Foundation@Windows@@@WRL@Microsoft@@PEAUILauncherStatics@System@Windows@@PEAUIStorageFolder@Storage@7@PEAUHSTRING__@@PEAUIFolderLauncherOptions@67@PEAUITelemetryCorrelationVector@@@Z`
- size: `955`
- prototype: ``
- caller_count: `6`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800859c0`
- `0x180085a80`
- `0x180085b70`
- `0x180085c40`
- `0x180085d40`
- `0x180085e00`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180027c60`
- `0x180027d80`
- `0x180040918`
- `0x18005042c`
- `0x1800533e4`
- `0x18005363c`
- `0x180053844`
- `0x1800550d8`
- `0x18005a524`
- `0x1800726f8`
- `0x180085f20`
- `0x1800862e4`
- `0x180086360`
- `0x18008638c`
- `0x180086454`
- `0x1800864b8`
- `0x18008654c`
- `0x18008a030`
- `0x1800e1594`
- `0x1800e328c`
- `0x1800eac00`
- `0x180105bec`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085fc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008627f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008628a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800862a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085fc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008627f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008628a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800862a6`

## string_xrefs

- `0x1800860b8`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x180086233`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall CBrokeredLauncher::_LaunchFolderAsync(
        _QWORD *a1,
        struct Windows::System::ILauncherStatics *a2,
        __int64 a3,
        __int64 a4,
        _QWORD **a5,
        __int64 a6)
{
  __int64 v8; // r14
  const char *v9; // rbx
  void *v10; // rbx
  void *v11; // rdx
  enum WELL_KNOWN_SID_TYPE v12; // ecx
  void **v13; // r9
  signed int v14; // eax
  void *v15; // rax
  __int64 v16; // rdi
  int v17; // eax
  int (__fastcall *v18)(_QWORD **, GUID *, _BYTE *); // rbx
  __int64 v19; // rax
  int v20; // r8d
  int v21; // ebx
  int Buffer; // [rsp+20h] [rbp-E0h]
  int Buffera; // [rsp+20h] [rbp-E0h]
  bool v25[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[12]; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v27; // [rsp+88h] [rbp-78h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h] BYREF
  void *v29; // [rsp+98h] [rbp-68h] BYREF
  int v30; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v31; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR v32[4]; // [rsp+B0h] [rbp-50h] BYREF
  HWND v33; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-40h] BYREF
  int v35[2]; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v37; // [rsp+D8h] [rbp-28h]
  __int64 v38; // [rsp+E0h] [rbp-20h] BYREF
  int v39; // [rsp+E8h] [rbp-18h]
  __int128 v40; // [rsp+F0h] [rbp-10h]
  _QWORD *v41; // [rsp+100h] [rbp+0h]
  _QWORD v42[42]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v43[42]; // [rsp+260h] [rbp+160h] BYREF
  int v44[108]; // [rsp+3B0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  v37 = a3;
  v41 = a1;
  *(_QWORD *)v26 = a4;
  v8 = 0;
  v30 = 0;
  v9 = *(const char **)TelemetryCorrelationVectorServiceProvider::Increment(&v27, a6);
  wil::ActivityBase<LauncherDesktopProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v42);
  v42[0] = &LauncherDesktopProvider::LaunchFolder::`vftable';
  LauncherDesktopProvider::LaunchFolder::StartActivityWithCorrelationVector(
    (LauncherDesktopProvider::LaunchFolder *)v42,
    v9);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v27);
  LODWORD(v28) = 0;
  v31 = 0;
  v29 = 0;
  v25[0] = 0;
  *(_QWORD *)v32 = 0;
  CoTaskMemFree(0);
  CoTaskMemFree(0);
  CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(
    a2,
    (enum PROCESS_UICONTEXT *)&v28,
    &v31,
    &v29,
    v32,
    v25);
  v25[1] = 0;
  v33 = 0;
  v10 = *(void **)v32;
  if ( v25[0] && !CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow() )
  {
    v27 = v10;
    LauncherDesktopProvider::LaunchFolder::LaunchAttemptedFromModernAppOnNonUIThread<unsigned short const *>(v42, &v27);
    CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(a2, &v25[1], &v33);
  }
  v25[2] = CBrokeredLauncher::IsCallingProcessLowIL(a2);
  *(_DWORD *)&v25[4] = 0;
  v14 = CheckAndGetCapability(v12, v11, (int *)&v25[4], v13);
  if ( v14 >= 0 )
    v14 = *(_DWORD *)&v25[4] == 0 ? 0x80070005 : 0;
  v25[3] = v14 >= 0;
  v27 = v31;
  v31 = 0;
  pv = v10;
  *(_QWORD *)v32 = 0;
  v15 = v29;
  v29 = 0;
  *(_QWORD *)v35 = v15;
  CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(&v34);
  v16 = v34;
  v17 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(v34 + 8), (HSTRING *)v26);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5FE,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v17,
      Buffer);
  if ( !v25[0] && a5 )
  {
    *(_QWORD *)v26 = 0;
    v18 = (int (__fastcall *)(_QWORD **, GUID *, _BYTE *))**a5;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
    if ( v18(a5, &GUID_cf5d818d_6177_44ad_873c_6ede9b17f013, v26) >= 0 )
    {
      *(_DWORD *)&v25[4] = 0;
      if ( (*(int (__fastcall **)(_QWORD, bool *))(**(_QWORD **)v26 + 48LL))(*(_QWORD *)v26, &v25[4]) >= 0 )
        v8 = *(int *)&v25[4];
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
  }
  v38 = v8;
  v39 = 7;
  v40 = 0;
  LauncherDesktopProvider::LaunchFolder::Split(v42, v43);
  *a1 = 0;
  v30 = 1;
  v19 = _lambda_07a333d6f0182d7131dc1045b1e9c8bf_::_lambda_07a333d6f0182d7131dc1045b1e9c8bf_(
          (int)v44,
          (int)&v27,
          (int)&pv,
          (int)v35,
          (__int64)&v28,
          (__int64)&v25[3],
          (__int64)v25,
          (__int64)&v25[2],
          (__int64)&v34,
          (__int64)&v25[1],
          (__int64)&v33,
          (struct Windows::Internal::AsyncWindowOperation *)&v38,
          (__int64)v43);
  *(_DWORD *)v26 = 1;
  *(_QWORD *)&v26[4] = 4;
  v21 = Windows::Internal::MakeStagedAsyncOperation<Windows::Internal::CBasicResult<unsigned char,0>,bool,Windows::Internal::ComTaskPoolHandler,Windows::Storage::IStorageFolder,Windows::System::IFolderLauncherOptions,ITelemetryCorrelationVector,_lambda_07a333d6f0182d7131dc1045b1e9c8bf_>(
          (unsigned int)v26,
          (_DWORD)a1,
          v20,
          v37,
          (__int64)a5,
          a6,
          v19);
  _lambda_07a333d6f0182d7131dc1045b1e9c8bf_::~_lambda_07a333d6f0182d7131dc1045b1e9c8bf_((_lambda_07a333d6f0182d7131dc1045b1e9c8bf_ *)v44);
  wil::ActivityBase<LauncherDesktopProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v42,
    (unsigned int)v21);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x65D,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
      (const char *)(unsigned int)v21,
      Buffera);
  LauncherDesktopProvider::LaunchFolder::~LaunchFolder((LauncherDesktopProvider::LaunchFolder *)v43);
  Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation((Windows::Internal::AsyncWindowOperation *)&v38);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(v35);
  CoTaskMemFree(pv);
  CoTaskMemFree(v27);
  CoTaskMemFree(0);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v29);
  CoTaskMemFree(0);
  LauncherDesktopProvider::LaunchFolder::~LaunchFolder((LauncherDesktopProvider::LaunchFolder *)v42);
  return a1;
}

```

## disassembly

```asm
0x180085f20  push    rbp
0x180085f22  push    rbx
0x180085f23  push    rsi
0x180085f24  push    rdi
0x180085f25  push    r13
0x180085f27  push    r14
0x180085f29  push    r15
0x180085f2b  lea     rbp, [rsp-470h]
0x180085f33  sub     rsp, 570h
0x180085f3a  mov     rax, cs:__security_cookie
0x180085f41  xor     rax, rsp
0x180085f44  mov     [rbp+4A0h+var_40], rax
0x180085f4b  mov     [rbp+4A0h+var_4C8], r8
0x180085f4f  mov     rdi, rdx
0x180085f52  mov     r15, rcx
0x180085f55  mov     [rbp+4A0h+var_4A0], rcx
0x180085f59  mov     [rsp+5A0h+var_528], r9
0x180085f5e  mov     rsi, [rbp+4A0h+arg_20]
0x180085f65  mov     r13, [rbp+4A0h+arg_28]
0x180085f6c  xor     r14d, r14d
0x180085f6f  mov     [rbp+4A0h+var_500], r14d
0x180085f73  mov     rdx, r13
0x180085f76  lea     rcx, [rbp+4A0h+var_518]
0x180085f7a  call    ?Increment@TelemetryCorrelationVectorServiceProvider@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; TelemetryCorrelationVectorServiceProvider::Increment(IUnknown *)
0x180085f7f  mov     rbx, [rax]
0x180085f82  lea     rcx, [rbp+4A0h+var_490]; struct wil::details::IFailureCallback *
0x180085f86  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherDesktopProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180085f8b  lea     rax, ??_7LaunchFolder@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::LaunchFolder::`vftable'
0x180085f92  mov     [rbp+4A0h+var_490], rax
0x180085f96  mov     rdx, rbx; char *
0x180085f99  lea     rcx, [rbp+4A0h+var_490]; this
0x180085f9d  call    ?StartActivityWithCorrelationVector@LaunchFolder@LauncherDesktopProvider@@QEAAXPEBD@Z; LauncherDesktopProvider::LaunchFolder::StartActivityWithCorrelationVector(char const *)
0x180085fa2  nop
0x180085fa3  lea     rcx, [rbp+4A0h+var_518]
0x180085fa7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180085fac  mov     dword ptr [rbp+4A0h+var_510], r14d
0x180085fb0  mov     [rbp+4A0h+var_4F8], r14
0x180085fb4  mov     [rbp+4A0h+var_508], r14
0x180085fb8  mov     [rsp+5A0h+var_530], r14b
0x180085fbd  mov     qword ptr [rbp+4A0h+var_4F0], r14
0x180085fc1  xor     ecx, ecx; pv
0x180085fc3  call    cs:__imp_CoTaskMemFree
0x180085fc9  xor     ecx, ecx; pv
0x180085fcb  call    cs:__imp_CoTaskMemFree
0x180085fd1  lea     rax, [rsp+5A0h+var_530]
0x180085fd6  mov     [rsp+5A0h+var_578], rax; bool *
0x180085fdb  lea     rax, [rbp+4A0h+var_4F0]
0x180085fdf  mov     qword ptr [rsp+5A0h+Buffer], rax; int
0x180085fe4  lea     r9, [rbp+4A0h+var_508]; void **
0x180085fe8  lea     r8, [rbp+4A0h+var_4F8]; unsigned __int16 **
0x180085fec  lea     rdx, [rbp+4A0h+var_510]; enum PROCESS_UICONTEXT *
0x180085ff0  mov     rcx, rdi; struct Windows::System::ILauncherStatics *
0x180085ff3  call    ?RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEAW4PROCESS_UICONTEXT@@PEAPEAGPEAPEAX2PEA_N@Z; CBrokeredLauncher::RetrieveCallerUIContextAppIdImpersonationTokenPFNAndWindowModel(Windows::System::ILauncherStatics *,PROCESS_UICONTEXT *,ushort * *,void * *,ushort * *,bool *)
0x180085ff8  mov     [rsp+5A0h+var_530+1], r14b
0x180085ffd  mov     [rbp+4A0h+var_4E8], r14
0x180086001  mov     rbx, qword ptr [rbp+4A0h+var_4F0]
0x180086005  cmp     [rsp+5A0h+var_530], r14b
0x18008600a  jz      short loc_180086037
0x18008600c  call    ?TryGetWindowIdOfCallerViaCoreWindow@CBrokeredLauncher@@CAKXZ; CBrokeredLauncher::TryGetWindowIdOfCallerViaCoreWindow(void)
0x180086011  test    eax, eax
0x180086013  jnz     short loc_180086037
0x180086015  mov     [rbp+4A0h+var_518], rbx
0x180086019  lea     rdx, [rbp+4A0h+var_518]
0x18008601d  lea     rcx, [rbp+4A0h+var_490]
0x180086021  call    ??$LaunchAttemptedFromModernAppOnNonUIThread@PEBG@LaunchFolder@LauncherDesktopProvider@@QEAAX$$QEAPEBG@Z; LauncherDesktopProvider::LaunchFolder::LaunchAttemptedFromModernAppOnNonUIThread<ushort const *>(ushort const * &&)
0x180086026  lea     r8, [rbp+4A0h+var_4E8]; HWND *
0x18008602a  lea     rdx, [rsp+5A0h+var_530+1]; bool *
0x18008602f  mov     rcx, rdi; struct Windows::System::ILauncherStatics *
0x180086032  call    ?ValidateOrGetQuirkEnabledCallerWindow@CBrokeredLauncher@@CAXPEAUILauncherStatics@System@Windows@@PEA_NPEAPEAUHWND__@@@Z; CBrokeredLauncher::ValidateOrGetQuirkEnabledCallerWindow(Windows::System::ILauncherStatics *,bool *,HWND__ * *)
0x180086037  mov     rcx, rdi; struct Windows::System::ILauncherStatics *
0x18008603a  call    ?IsCallingProcessLowIL@CBrokeredLauncher@@CA_NPEAUILauncherStatics@System@Windows@@@Z; CBrokeredLauncher::IsCallingProcessLowIL(Windows::System::ILauncherStatics *)
0x18008603f  mov     [rsp+5A0h+var_530+2], al
0x180086043  mov     dword ptr [rsp+5A0h+var_530+4], r14d
0x180086048  lea     r8, [rsp+5A0h+var_530+4]; int *
0x18008604d  call    ?CheckAndGetCapability@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAHPEAPEAX@Z; CheckAndGetCapability(WELL_KNOWN_SID_TYPE,void *,int *,void * *)
0x180086052  test    eax, eax
0x180086054  js      short loc_180086065
0x180086056  mov     eax, dword ptr [rsp+5A0h+var_530+4]
0x18008605a  neg     eax
0x18008605c  sbb     eax, eax
0x18008605e  not     eax
0x180086060  and     eax, 80070005h
0x180086065  shr     eax, 1Fh
0x180086068  xor     al, 1
0x18008606a  mov     [rsp+5A0h+var_530+3], al
0x18008606e  mov     rax, [rbp+4A0h+var_4F8]
0x180086072  mov     [rbp+4A0h+var_518], rax
0x180086076  mov     [rbp+4A0h+var_4F8], r14
0x18008607a  mov     [rbp+4A0h+pv], rbx
0x18008607e  mov     qword ptr [rbp+4A0h+var_4F0], r14
0x180086082  mov     rax, [rbp+4A0h+var_508]
0x180086086  mov     [rbp+4A0h+var_508], r14
0x18008608a  mov     qword ptr [rbp+4A0h+var_4D8], rax
0x18008608e  lea     rcx, [rbp+4A0h+var_4E0]
0x180086092  call    ??$CreateRefCountedObj@VHString@Wrappers@WRL@Microsoft@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Microsoft::WRL::Wrappers::HString,>(void)
0x180086097  nop
0x180086098  mov     rdi, [rbp+4A0h+var_4E0]
0x18008609c  lea     rcx, [rdi+8]; newString
0x1800860a0  lea     rdx, [rsp+5A0h+var_528]; HSTRING *
0x1800860a5  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800860aa  mov     rcx, [rbp+4A8h]; this
0x1800860b1  test    eax, eax
0x1800860b3  jns     short loc_1800860CA
0x1800860b5  mov     r9d, eax; char *
0x1800860b8  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800860bf  mov     edx, 5FEh; void *
0x1800860c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800860ca  cmp     [rsp+5A0h+var_530], 0
0x1800860cf  jnz     short loc_18008613B
0x1800860d1  test    rsi, rsi
0x1800860d4  jz      short loc_18008613B
0x1800860d6  mov     [rsp+5A0h+var_528], 0
0x1800860df  mov     rax, [rsi]
0x1800860e2  mov     rbx, [rax]
0x1800860e5  lea     rcx, [rsp+5A0h+var_528]
0x1800860ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800860ef  lea     r8, [rsp+5A0h+var_528]
0x1800860f4  lea     rdx, _GUID_cf5d818d_6177_44ad_873c_6ede9b17f013
0x1800860fb  mov     rcx, rsi
0x1800860fe  mov     rax, rbx
0x180086101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086106  test    eax, eax
0x180086108  js      short loc_180086131
0x18008610a  mov     dword ptr [rsp+5A0h+var_530+4], 0
0x180086112  mov     rcx, [rsp+5A0h+var_528]
0x180086117  mov     rax, [rcx]
0x18008611a  lea     rdx, [rsp+5A0h+var_530+4]
0x18008611f  mov     rax, [rax+30h]
0x180086123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086128  test    eax, eax
0x18008612a  js      short loc_180086131
0x18008612c  movsxd  r14, dword ptr [rsp+5A0h+var_530+4]
0x180086131  lea     rcx, [rsp+5A0h+var_528]
0x180086136  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008613b  mov     [rbp+4A0h+var_4C0], r14
0x18008613f  mov     [rbp+4A0h+var_4B8], 7
0x180086146  xorps   xmm0, xmm0
0x180086149  movdqu  [rbp+4A0h+var_4B0], xmm0
0x18008614e  lea     rdx, [rbp+4A0h+var_340]
0x180086155  lea     rcx, [rbp+4A0h+var_490]
0x180086159  call    ?Split@LaunchFolder@LauncherDesktopProvider@@QEAA?AV12@XZ; LauncherDesktopProvider::LaunchFolder::Split(void)
0x18008615e  nop
0x18008615f  mov     qword ptr [r15], 0
0x180086166  mov     ebx, 1
0x18008616b  mov     [rbp+4A0h+var_500], ebx
0x18008616e  lea     rax, [rbp+4A0h+var_340]
0x180086175  mov     [rsp+5A0h+var_540], rax; __int64
0x18008617a  lea     rax, [rbp+4A0h+var_4C0]
0x18008617e  mov     [rsp+5A0h+var_548], rax; struct Windows::Internal::AsyncWindowOperation *
0x180086183  lea     rax, [rbp+4A0h+var_4E8]
0x180086187  mov     [rsp+5A0h+var_550], rax; __int64
0x18008618c  lea     rax, [rsp+5A0h+var_530+1]
0x180086191  mov     [rsp+5A0h+var_558], rax; __int64
0x180086196  lea     rax, [rbp+4A0h+var_4E0]
0x18008619a  mov     [rsp+5A0h+var_560], rax; __int64
0x18008619f  lea     rax, [rsp+5A0h+var_530+2]
0x1800861a4  mov     [rsp+5A0h+var_568], rax; __int64
0x1800861a9  lea     rax, [rsp+5A0h+var_530]
0x1800861ae  mov     [rsp+5A0h+var_570], rax; __int64
0x1800861b3  lea     rax, [rsp+5A0h+var_530+3]
0x1800861b8  mov     [rsp+5A0h+var_578], rax; __int64
0x1800861bd  lea     rax, [rbp+4A0h+var_510]
0x1800861c1  mov     qword ptr [rsp+5A0h+Buffer], rax; __int64
0x1800861c6  lea     r9, [rbp+4A0h+var_4D8]; int
0x1800861ca  lea     r8, [rbp+4A0h+pv]; int
0x1800861ce  lea     rdx, [rbp+4A0h+var_518]; int
0x1800861d2  lea     rcx, [rbp+4A0h+var_1F0]; int
0x1800861d9  call    ??0_lambda_07a333d6f0182d7131dc1045b1e9c8bf_@@QEAA@AEBV?$CCaptureByMoving@V?$CMemString@UCMemString_PolicyCoTaskMem@@@@@@0AEBV?$CCaptureByMoving@V?$CAutoHandle@PEAX@@@@AEBW4PROCESS_UICONTEXT@@AEB_N33AEBV?$ComPtr@V?$CRefCountedObject@VHString@Wrappers@WRL@Microsoft@@@@@WRL@Microsoft@@3AEBQEAUHWND__@@AEBVAsyncWindowOperation@Internal@Windows@@AEBVLaunchFolder@LauncherDesktopProvider@@@Z; _lambda_07a333d6f0182d7131dc1045b1e9c8bf_::_lambda_07a333d6f0182d7131dc1045b1e9c8bf_(CCaptureByMoving<CMemString<CMemString_PolicyCoTaskMem>> const &,CCaptureByMoving<CMemString<CMemString_PolicyCoTaskMem>> const &,CCaptureByMoving<CAutoHandle<void *>> const &,PROCESS_UICONTEXT const &,bool const &,bool const &,bool const &,Microsoft::WRL::ComPtr<CRefCountedObject<Microsoft::WRL::Wrappers::HString>> const &,bool const &,HWND__ * const &,Windows::Internal::AsyncWindowOperation const &,LauncherDesktopProvider::LaunchFolder const &)
0x1800861de  nop
0x1800861df  mov     dword ptr [rsp+5A0h+var_528], ebx
0x1800861e3  mov     [rsp+5A0h+var_528+4], 4
0x1800861ec  mov     [rsp+5A0h+var_570], rax
0x1800861f1  mov     [rsp+5A0h+var_578], r13
0x1800861f6  mov     qword ptr [rsp+5A0h+Buffer], rsi; int
0x1800861fb  mov     r9, [rbp+4A0h+var_4C8]
0x1800861ff  mov     rdx, r15
0x180086202  lea     rcx, [rsp+5A0h+var_528]
0x180086207  call    ??$MakeStagedAsyncOperation@V?$CBasicResult@E$0A@@Internal@Windows@@_NVComTaskPoolHandler@23@UIStorageFolder@Storage@3@UIFolderLauncherOptions@System@3@UITelemetryCorrelationVector@@V_lambda_07a333d6f0182d7131dc1045b1e9c8bf_@@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@_N@Foundation@1@W4TrustLevel@@PEAUIStorageFolder@Storage@1@PEAUIFolderLauncherOptions@System@1@PEAUITelemetryCorrelationVector@@$$QEAV_lambda_07a333d6f0182d7131dc1045b1e9c8bf_@@@Z; Windows::Internal::MakeStagedAsyncOperation<Windows::Internal::CBasicResult<uchar,0>,bool,Windows::Internal::ComTaskPoolHandler,Windows::Storage::IStorageFolder,Windows::System::IFolderLauncherOptions,ITelemetryCorrelationVector,_lambda_07a333d6f0182d7131dc1045b1e9c8bf_>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<bool> * *,TrustLevel,Windows::Storage::IStorageFolder *,Windows::System::IFolderLauncherOptions *,ITelemetryCorrelationVector *,_lambda_07a333d6f0182d7131dc1045b1e9c8bf_ &&)
0x18008620c  mov     ebx, eax
0x18008620e  lea     rcx, [rbp+4A0h+var_1F0]; this
0x180086215  call    ??1_lambda_07a333d6f0182d7131dc1045b1e9c8bf_@@QEAA@XZ; _lambda_07a333d6f0182d7131dc1045b1e9c8bf_::~_lambda_07a333d6f0182d7131dc1045b1e9c8bf_(void)
0x18008621a  mov     edx, ebx
0x18008621c  lea     rcx, [rbp+4A0h+var_490]
0x180086220  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180086225  test    ebx, ebx
0x180086227  jns     short loc_180086245
0x180086229  mov     rcx, [rbp+4A8h]; this
0x180086230  mov     r9d, ebx; char *
0x180086233  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x18008623a  mov     edx, 65Dh; void *
0x18008623f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180086245  lea     rcx, [rbp+4A0h+var_340]; this
0x18008624c  call    ??1LaunchFolder@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchFolder::~LaunchFolder(void)
0x180086251  nop
0x180086252  lea     rcx, [rbp+4A0h+var_4C0]; this
0x180086256  call    ??1AsyncWindowOperation@Internal@Windows@@QEAA@XZ; Windows::Internal::AsyncWindowOperation::~AsyncWindowOperation(void)
0x18008625b  nop
0x18008625c  test    rdi, rdi
0x18008625f  jz      short loc_180086271
0x180086261  mov     rax, [rdi]
0x180086264  mov     rcx, rdi
0x180086267  mov     rax, [rax+10h]
0x18008626b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086270  nop
0x180086271  lea     rcx, [rbp+4A0h+var_4D8]
0x180086275  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18008627a  nop
0x18008627b  mov     rcx, [rbp+4A0h+pv]; pv
0x18008627f  call    cs:__imp_CoTaskMemFree
0x180086285  nop
0x180086286  mov     rcx, [rbp+4A0h+var_518]; pv
0x18008628a  call    cs:__imp_CoTaskMemFree
0x180086290  nop
0x180086291  xor     ecx, ecx; pv
0x180086293  call    cs:__imp_CoTaskMemFree
0x180086299  nop
0x18008629a  lea     rcx, [rbp+4A0h+var_508]
0x18008629e  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x1800862a3  nop
0x1800862a4  xor     ecx, ecx; pv
0x1800862a6  call    cs:__imp_CoTaskMemFree
0x1800862ac  nop
0x1800862ad  lea     rcx, [rbp+4A0h+var_490]; this
0x1800862b1  call    ??1LaunchFolder@LauncherDesktopProvider@@QEAA@XZ; LauncherDesktopProvider::LaunchFolder::~LaunchFolder(void)
0x1800862b6  mov     rax, r15
0x1800862b9  mov     rcx, [rbp+4A0h+var_40]
0x1800862c0  xor     rcx, rsp; StackCookie
0x1800862c3  call    __security_check_cookie
0x1800862c8  add     rsp, 570h
0x1800862cf  pop     r15
0x1800862d1  pop     r14
0x1800862d3  pop     r13
0x1800862d5  pop     rdi
0x1800862d6  pop     rsi
0x1800862d7  pop     rbx
0x1800862d8  pop     rbp
0x1800862d9  retn
```
