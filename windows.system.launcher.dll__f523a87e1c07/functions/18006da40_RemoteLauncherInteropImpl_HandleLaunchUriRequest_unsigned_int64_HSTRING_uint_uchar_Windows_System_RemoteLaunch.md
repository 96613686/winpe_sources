# RemoteLauncherInteropImpl::HandleLaunchUriRequest(unsigned __int64,HSTRING__ *,uint,uchar *,Windows::System::RemoteLaunchUriStatus *)

- ea: `0x18006da40`
- end: `0x18006e085`
- name: `?HandleLaunchUriRequest@RemoteLauncherInteropImpl@@UEAAJ_KPEAUHSTRING__@@IPEAEPEAW4RemoteLaunchUriStatus@System@Windows@@@Z`
- size: `1605`
- prototype: `int(RemoteLauncherInteropImpl *__hidden this, unsigned __int64, HSTRING, unsigned int, unsigned __int8 *, enum Windows::System::RemoteLaunchUriStatus *)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x1800272d8`
- `0x180028b70`
- `0x18002cec0`
- `0x1800596d8`
- `0x18006da40`
- `0x18006e08c`
- `0x18006e250`
- `0x18006e2c4`
- `0x18006e314`
- `0x18006e350`
- `0x18006e42c`
- `0x18006e4a0`
- `0x18006e6cc`
- `0x18006e6f8`
- `0x18008a030`
- `0x1800abc18`
- `0x1800ac4c0`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006dcc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006dcc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dcba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dfe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dcba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006dfe5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006ddac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006ddac`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006dbe2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006dbe2`

## string_xrefs

- `0x18006dad1`: `Windows.Foundation.Uri`
- `0x18006da85`: `LaunchUriOnRemoteSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall RemoteLauncherInteropImpl::HandleLaunchUriRequest(
        RemoteLauncherInteropImpl *this,
        unsigned __int64 a2,
        HSTRING a3,
        unsigned int a4,
        unsigned __int8 *a5,
        enum Windows::System::RemoteLaunchUriStatus *a6)
{
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING, struct Windows::Foundation::IUriRuntimeClass **); // rbx
  int v12; // eax
  RemoteLauncherInteropImpl *v13; // rcx
  struct Windows::System::ILauncherOptions *v14; // rbx
  HSTRING v15; // rdi
  __int64 v16; // rbx
  int ActivationFactory; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, unsigned __int8 *, struct Windows::Foundation::Collections::IPropertySet **); // rbx
  int v20; // eax
  RemoteLauncherInteropImpl *v21; // rcx
  __int64 v22; // rcx
  HSTRING *CorrelationId; // rbx
  __int64 (__fastcall *v24)(struct Windows::System::ILauncherOptions *, __int64 *); // rsi
  int v25; // eax
  int v26; // ebx
  LPVOID v27; // rsi
  int (__fastcall *v28)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, struct Windows::Foundation::IUriRuntimeClass *, struct Windows::System::ILauncherOptions *, struct Windows::Foundation::Collections::IPropertySet *); // rbx
  int v34; // esi
  __int64 v35; // rbx
  int v36; // eax
  const char *v37; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-248h]
  int ppva; // [rsp+20h] [rbp-248h]
  _BYTE v41[8]; // [rsp+40h] [rbp-228h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v42; // [rsp+48h] [rbp-220h] BYREF
  __int64 v43; // [rsp+50h] [rbp-218h] BYREF
  HSTRING string; // [rsp+58h] [rbp-210h] BYREF
  struct Windows::Foundation::IUriRuntimeClass *v45; // [rsp+60h] [rbp-208h] BYREF
  struct Windows::System::ILauncherOptions *v46; // [rsp+68h] [rbp-200h] BYREF
  __int64 v47; // [rsp+70h] [rbp-1F8h] BYREF
  LPVOID v48; // [rsp+78h] [rbp-1F0h] BYREF
  __int64 v49; // [rsp+80h] [rbp-1E8h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v50; // [rsp+88h] [rbp-1E0h] BYREF
  __int64 v51; // [rsp+90h] [rbp-1D8h] BYREF
  __int64 v52; // [rsp+98h] [rbp-1D0h] BYREF
  HSTRING v53; // [rsp+A0h] [rbp-1C8h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-1C0h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-1A8h]
  _QWORD v56[42]; // [rsp+D0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *(_DWORD *)a6 = 0;
  wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v56);
  v56[0] = &LauncherClientProvider::LaunchUriOnRemoteSystem::`vftable';
  LauncherClientProvider::LaunchUriOnRemoteSystem::StartActivity(
    (LauncherClientProvider::LaunchUriOnRemoteSystem *)v56,
    a2);
  v52 = 0;
  v55 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
         v55,
         &v52);
  try
  {
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
        (const char *)(unsigned int)v9,
        ppv);
    v45 = 0;
    v10 = v52;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Foundation::IUriRuntimeClass **))(*(_QWORD *)v52 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    v12 = v11(v10, a3, &v45);
    v13 = retaddr;
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
        (const char *)(unsigned int)v12,
        ppv);
    v50 = 0;
    v14 = 0;
    v46 = 0;
    v15 = 0;
    v53 = 0;
    if ( a5 )
    {
      v42 = 0;
      v43 = 0;
      v55 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.System.Internal.RemoteSystems.RemoteSystemInterop",
        0x3Au,
        0x39u);
      v16 = v55;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      ActivationFactory = RoGetActivationFactory(v16, &GUID_61370ec4_4a4a_4471_87e2_9be08b92e933, &v43);
      if ( ActivationFactory < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
          (const char *)(unsigned int)ActivationFactory,
          ppv);
      v18 = v43;
      v19 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *, struct Windows::Foundation::Collections::IPropertySet **))(*(_QWORD *)v43 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v20 = v19(v18, a4, a5, &v42);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x82,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
          (const char *)(unsigned int)v20,
          ppv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      RemoteLauncherInteropImpl::FetchLauncherOptionsAndInputData(v21, v45, v42, &v46, &v50);
      CorrelationId = (HSTRING *)RemoteLauncherInteropImpl::FetchCorrelationId(v22, &string, v42);
      WindowsDeleteString(0);
      v53 = *CorrelationId;
      v15 = v53;
      *CorrelationId = 0;
      WindowsDeleteString(string);
      string = (HSTRING)WindowsGetStringRawBuffer(v15, 0);
      LauncherClientProvider::LaunchUriOnRemoteSystem::RemoteLaunchUriRequest<unsigned short const *>(v56, &string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v14 = v46;
    }
    v49 = 0;
    if ( v14 )
    {
      v24 = *(__int64 (__fastcall **)(struct Windows::System::ILauncherOptions *, __int64 *))(*(_QWORD *)v14 + 120LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      v25 = v24(v14, &v49);
      v13 = retaddr;
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
          (const char *)(unsigned int)v25,
          ppv);
      if ( v49 )
        goto LABEL_18;
    }
    if ( RemoteLauncherInteropImpl::IsProtocolSupported(v13, v45, 0) )
    {
LABEL_18:
      v48 = 0;
      v47 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      if ( CoCreateInstance(
             &GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239,
             0,
             4u,
             &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
             &v48) >= 0 )
      {
        v27 = v48;
        v28 = *(int (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v48 + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        if ( v28(v27, &GUID_5ac9e22f_8a57_43c0_bf9a_1e1f5f366e55, &GUID_5ac9e22f_8a57_43c0_bf9a_1e1f5f366e55, &v47) >= 0 )
        {
          v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 24LL))(v47);
          if ( v29 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x99,
              (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
              (const char *)(unsigned int)v29,
              ppva);
        }
      }
      string = 0;
      v55 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.System.Launcher",
        0x18u,
        0x17u);
      v30 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(
              v55,
              &string);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9F,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
          (const char *)(unsigned int)v30,
          ppva);
      v43 = 0;
      v51 = 0;
      v31 = Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>::As<Windows::System::Private::ILauncherStaticsInternal2>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&string,
              (__int64)&v51);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
          (const char *)(unsigned int)v31,
          ppva);
      v32 = v51;
      v33 = *(__int64 (__fastcall **)(__int64, struct Windows::Foundation::IUriRuntimeClass *, struct Windows::System::ILauncherOptions *, struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v51 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      v34 = v33(v32, v45, v46, v50);
      if ( v34 < 0 )
      {
        v26 = 2;
      }
      else
      {
        v41[0] = 0;
        v35 = v43;
        v36 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(v43);
        if ( v36 >= 0 )
          v36 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v35 + 64LL))(v35, v41);
        if ( v36 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAF,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
            (const char *)(unsigned int)v36,
            (int)v15);
        v26 = 2 - (v41[0] != 0);
      }
      LODWORD(v42) = v26;
      LauncherClientProvider::LaunchUriOnRemoteSystem::RemoteLaunchUriStatus<enum Windows::System::RemoteLaunchUriStatus &>(
        v56,
        &v42);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
          (const char *)(unsigned int)v34,
          (int)v15);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    }
    else
    {
      v26 = 3;
      LODWORD(v42) = 3;
    }
    *(_DWORD *)a6 = v26;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    WindowsDeleteString(v15);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    LauncherClientProvider::LaunchUriOnRemoteSystem::RemoteLaunchUriStatus<enum Windows::System::RemoteLaunchUriStatus &>(
      v56,
      &v42);
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v56,
      0);
    LauncherClientProvider::LaunchUriOnRemoteSystem::~LaunchUriOnRemoteSystem((LauncherClientProvider::LaunchUriOnRemoteSystem *)v56);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v42) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xC1,
                     (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\remotelauncherhelpers.cpp",
                     v37);
    LauncherClientProvider::LaunchUriOnRemoteSystem::~LaunchUriOnRemoteSystem((LauncherClientProvider::LaunchUriOnRemoteSystem *)v56);
    return (unsigned int)v42;
  }
  return result;
}

```

## disassembly

```asm
0x18006da40  push    rbx
0x18006da42  push    rsi
0x18006da43  push    rdi
0x18006da44  push    r12
0x18006da46  push    r13
0x18006da48  push    r14
0x18006da4a  push    r15
0x18006da4c  sub     rsp, 230h
0x18006da53  mov     rax, cs:__security_cookie
0x18006da5a  xor     rax, rsp
0x18006da5d  mov     [rsp+268h+var_48], rax
0x18006da65  mov     r15d, r9d
0x18006da68  mov     r14, r8
0x18006da6b  mov     rbx, rdx
0x18006da6e  mov     rsi, [rsp+268h+arg_20]
0x18006da76  mov     r12, [rsp+268h+arg_28]
0x18006da7e  xor     r13d, r13d
0x18006da81  mov     [r12], r13d
0x18006da85  lea     rdx, aLaunchurionrem; "LaunchUriOnRemoteSystem"
0x18006da8c  lea     rcx, [rsp+268h+var_198]; struct wil::details::IFailureCallback *
0x18006da94  call    ??0?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006da99  lea     rax, ??_7LaunchUriOnRemoteSystem@LauncherClientProvider@@6B@; const LauncherClientProvider::LaunchUriOnRemoteSystem::`vftable'
0x18006daa0  mov     [rsp+268h+var_198], rax
0x18006daa8  mov     rdx, rbx; unsigned __int64
0x18006daab  lea     rcx, [rsp+268h+var_198]; this
0x18006dab3  call    ?StartActivity@LaunchUriOnRemoteSystem@LauncherClientProvider@@QEAAX_K@Z; LauncherClientProvider::LaunchUriOnRemoteSystem::StartActivity(unsigned __int64)
0x18006dab8  nop
0x18006dab9  mov     [rsp+268h+var_1D0], r13
0x18006dac1  mov     [rsp+268h+var_1A8], r13
0x18006dac9  lea     r9d, [r13+16h]; unsigned int
0x18006dacd  lea     r8d, [r13+17h]; unsigned int
0x18006dad1  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18006dad8  lea     rcx, [rsp+268h+hstringHeader]; hstringHeader
0x18006dae0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006dae5  nop
0x18006dae6  lea     rdx, [rsp+268h+var_1D0]
0x18006daee  mov     rcx, [rsp+268h+var_1A8]
0x18006daf6  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18006dafb  mov     rcx, [rsp+268h]; this
0x18006db03  test    eax, eax
0x18006db05  jns     short loc_18006DB1B
0x18006db07  mov     r9d, eax; char *
0x18006db0a  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006db11  lea     edx, [r13+6Bh]; void *
0x18006db15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006db1b  mov     [rsp+268h+var_208], r13
0x18006db20  mov     rdi, [rsp+268h+var_1D0]
0x18006db28  mov     rax, [rdi]
0x18006db2b  mov     rbx, [rax+30h]
0x18006db2f  lea     rcx, [rsp+268h+var_208]
0x18006db34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006db39  lea     r8, [rsp+268h+var_208]
0x18006db3e  mov     rdx, r14
0x18006db41  mov     rcx, rdi
0x18006db44  mov     rax, rbx
0x18006db47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db4c  mov     rcx, [rsp+268h]; this
0x18006db54  test    eax, eax
0x18006db56  jns     short loc_18006DB6C
0x18006db58  mov     r9d, eax; char *
0x18006db5b  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006db62  mov     edx, 70h ; 'p'; void *
0x18006db67  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006db6c  mov     [rsp+268h+var_1E0], r13
0x18006db74  mov     rbx, r13
0x18006db77  mov     [rsp+268h+var_200], rbx
0x18006db7c  mov     rdi, r13
0x18006db7f  mov     [rsp+268h+var_1C8], r13
0x18006db87  test    rsi, rsi
0x18006db8a  jz      loc_18006DCFD
0x18006db90  mov     [rsp+268h+var_220], r13
0x18006db95  mov     [rsp+268h+var_218], r13
0x18006db9a  mov     [rsp+268h+var_1A8], r13
0x18006dba2  mov     r9d, 39h ; '9'; unsigned int
0x18006dba8  lea     r8d, [r9+1]; unsigned int
0x18006dbac  lea     rdx, ?RuntimeClass_Windows_System_Internal_RemoteSystems_RemoteSystemInterop@@3QBGB; "Windows.System.Internal.RemoteSystems.R"...
0x18006dbb3  lea     rcx, [rsp+268h+hstringHeader]; hstringHeader
0x18006dbbb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006dbc0  nop
0x18006dbc1  mov     rbx, [rsp+268h+var_1A8]
0x18006dbc9  lea     rcx, [rsp+268h+var_218]
0x18006dbce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dbd3  lea     r8, [rsp+268h+var_218]
0x18006dbd8  lea     rdx, _GUID_61370ec4_4a4a_4471_87e2_9be08b92e933
0x18006dbdf  mov     rcx, rbx
0x18006dbe2  call    cs:__imp_RoGetActivationFactory
0x18006dbe8  mov     rcx, [rsp+268h]; this
0x18006dbf0  test    eax, eax
0x18006dbf2  jns     short loc_18006DC09
0x18006dbf4  mov     r9d, eax; char *
0x18006dbf7  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006dbfe  mov     edx, 7Dh ; '}'; void *
0x18006dc03  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006dc09  mov     rdi, [rsp+268h+var_218]
0x18006dc0e  mov     rax, [rdi]
0x18006dc11  mov     rbx, [rax+38h]
0x18006dc15  lea     rcx, [rsp+268h+var_220]
0x18006dc1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dc1f  lea     r9, [rsp+268h+var_220]
0x18006dc24  mov     r8, rsi
0x18006dc27  mov     edx, r15d
0x18006dc2a  mov     rcx, rdi
0x18006dc2d  mov     rax, rbx
0x18006dc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc35  mov     rcx, [rsp+268h]; this
0x18006dc3d  test    eax, eax
0x18006dc3f  jns     short loc_18006DC55
0x18006dc41  mov     r9d, eax; char *
0x18006dc44  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006dc4b  mov     edx, 82h; void *
0x18006dc50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006dc55  lea     rcx, [rsp+268h+var_1E0]
0x18006dc5d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dc62  lea     rcx, [rsp+268h+var_200]
0x18006dc67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dc6c  lea     rax, [rsp+268h+var_1E0]
0x18006dc74  mov     [rsp+268h+ppv], rax; int
0x18006dc79  lea     r9, [rsp+268h+var_200]; struct Windows::System::ILauncherOptions **
0x18006dc7e  mov     r8, [rsp+268h+var_220]; struct Windows::Foundation::Collections::IPropertySet *
0x18006dc83  mov     rdx, [rsp+268h+var_208]; struct Windows::Foundation::IUriRuntimeClass *
0x18006dc88  call    ?FetchLauncherOptionsAndInputData@RemoteLauncherInteropImpl@@AEAAXPEAUIUriRuntimeClass@Foundation@Windows@@PEAUIPropertySet@Collections@34@PEAPEAUILauncherOptions@System@4@PEAPEAU5634@@Z; RemoteLauncherInteropImpl::FetchLauncherOptionsAndInputData(Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::Collections::IPropertySet *,Windows::System::ILauncherOptions * *,Windows::Foundation::Collections::IPropertySet * *)
0x18006dc8d  mov     r8, [rsp+268h+var_220]
0x18006dc92  lea     rdx, [rsp+268h+string]
0x18006dc97  call    ?FetchCorrelationId@RemoteLauncherInteropImpl@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; RemoteLauncherInteropImpl::FetchCorrelationId(Windows::Foundation::Collections::IPropertySet *)
0x18006dc9c  mov     rbx, rax
0x18006dc9f  xor     ecx, ecx; string
0x18006dca1  call    cs:__imp_WindowsDeleteString
0x18006dca7  mov     rdi, [rbx]
0x18006dcaa  mov     [rsp+268h+var_1C8], rdi
0x18006dcb2  mov     [rbx], r13
0x18006dcb5  mov     rcx, [rsp+268h+string]; string
0x18006dcba  call    cs:__imp_WindowsDeleteString
0x18006dcc0  xor     edx, edx; length
0x18006dcc2  mov     rcx, rdi; string
0x18006dcc5  call    cs:__imp_WindowsGetStringRawBuffer
0x18006dccb  mov     [rsp+268h+string], rax
0x18006dcd0  lea     rdx, [rsp+268h+string]
0x18006dcd5  lea     rcx, [rsp+268h+var_198]
0x18006dcdd  call    ??$RemoteLaunchUriRequest@PEBG@LaunchUriOnRemoteSystem@LauncherClientProvider@@QEAAX$$QEAPEBG@Z; LauncherClientProvider::LaunchUriOnRemoteSystem::RemoteLaunchUriRequest<ushort const *>(ushort const * &&)
0x18006dce2  nop
0x18006dce3  lea     rcx, [rsp+268h+var_218]
0x18006dce8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dced  nop
0x18006dcee  lea     rcx, [rsp+268h+var_220]
0x18006dcf3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dcf8  mov     rbx, [rsp+268h+var_200]
0x18006dcfd  mov     [rsp+268h+var_1E8], r13
0x18006dd05  test    rbx, rbx
0x18006dd08  jz      short loc_18006DD5B
0x18006dd0a  mov     rax, [rbx]
0x18006dd0d  mov     rsi, [rax+78h]
0x18006dd11  lea     rcx, [rsp+268h+var_1E8]
0x18006dd19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dd1e  lea     rdx, [rsp+268h+var_1E8]
0x18006dd26  mov     rcx, rbx
0x18006dd29  mov     rax, rsi
0x18006dd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd31  mov     rcx, [rsp+268h]; this
0x18006dd39  test    eax, eax
0x18006dd3b  jns     short loc_18006DD51
0x18006dd3d  mov     r9d, eax; char *
0x18006dd40  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006dd47  mov     edx, 8Eh; void *
0x18006dd4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006dd51  cmp     [rsp+268h+var_1E8], r13
0x18006dd59  jnz     short loc_18006DD7A
0x18006dd5b  xor     r8d, r8d; HSTRING
0x18006dd5e  mov     rdx, [rsp+268h+var_208]; struct Windows::Foundation::IUriRuntimeClass *
0x18006dd63  call    ?IsProtocolSupported@RemoteLauncherInteropImpl@@AEAA_NPEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@@Z; RemoteLauncherInteropImpl::IsProtocolSupported(Windows::Foundation::IUriRuntimeClass *,HSTRING__ *)
0x18006dd68  test    al, al
0x18006dd6a  jnz     short loc_18006DD7A
0x18006dd6c  mov     ebx, 3
0x18006dd71  mov     dword ptr [rsp+268h+var_220], ebx
0x18006dd75  jmp     loc_18006DFD0
0x18006dd7a  mov     [rsp+268h+var_1F0], r13
0x18006dd7f  mov     [rsp+268h+var_1F8], r13
0x18006dd84  lea     rcx, [rsp+268h+var_1F0]
0x18006dd89  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dd8e  lea     rax, [rsp+268h+var_1F0]
0x18006dd93  mov     [rsp+268h+ppv], rax; int
0x18006dd98  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18006dd9f  xor     edx, edx; pUnkOuter
0x18006dda1  lea     r8d, [rdx+4]; dwClsContext
0x18006dda5  lea     rcx, _GUID_c2f03a33_21f5_47fa_b4bb_156362a2f239; rclsid
0x18006ddac  call    cs:__imp_CoCreateInstance
0x18006ddb2  test    eax, eax
0x18006ddb4  js      short loc_18006DE1B
0x18006ddb6  mov     rsi, [rsp+268h+var_1F0]
0x18006ddbb  mov     rax, [rsi]
0x18006ddbe  mov     rbx, [rax+18h]
0x18006ddc2  lea     rcx, [rsp+268h+var_1F8]
0x18006ddc7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ddcc  lea     r9, [rsp+268h+var_1F8]
0x18006ddd1  lea     rdx, _GUID_5ac9e22f_8a57_43c0_bf9a_1e1f5f366e55
0x18006ddd8  mov     r8, rdx
0x18006dddb  mov     rcx, rsi
0x18006ddde  mov     rax, rbx
0x18006dde1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dde6  test    eax, eax
0x18006dde8  js      short loc_18006DE1B
0x18006ddea  mov     rcx, [rsp+268h+var_1F8]
0x18006ddef  mov     rax, [rcx]
0x18006ddf2  mov     rax, [rax+18h]
0x18006ddf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddfb  mov     rcx, [rsp+268h]; this
0x18006de03  test    eax, eax
0x18006de05  jns     short loc_18006DE1B
0x18006de07  mov     r9d, eax; char *
0x18006de0a  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006de11  mov     edx, 99h; void *
0x18006de16  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006de1b  mov     [rsp+268h+string], r13
0x18006de20  mov     [rsp+268h+var_1A8], r13
0x18006de28  mov     r9d, 17h; unsigned int
0x18006de2e  lea     r8d, [r9+1]; unsigned int
0x18006de32  lea     rdx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x18006de39  lea     rcx, [rsp+268h+hstringHeader]; hstringHeader
0x18006de41  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006de46  nop
0x18006de47  lea     rdx, [rsp+268h+string]
0x18006de4c  mov     rcx, [rsp+268h+var_1A8]
0x18006de54  call    ??$GetActivationFactory@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>>)
0x18006de59  mov     rcx, [rsp+268h]; this
0x18006de61  test    eax, eax
0x18006de63  jns     short loc_18006DE7A
0x18006de65  mov     r9d, eax; char *
0x18006de68  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006de6f  mov     edx, 9Fh; void *
0x18006de74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006de7a  mov     [rsp+268h+var_218], r13
0x18006de7f  mov     [rsp+268h+var_1D8], r13
0x18006de87  lea     rdx, [rsp+268h+var_1D8]
0x18006de8f  lea     rcx, [rsp+268h+string]
0x18006de94  call    ??$As@UILauncherStaticsInternal2@Private@System@Windows@@@?$ComPtr@UILauncherStatics@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UILauncherStaticsInternal2@Private@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::ILauncherStatics>::As<Windows::System::Private::ILauncherStaticsInternal2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Private::ILauncherStaticsInternal2>>)
0x18006de99  mov     rcx, [rsp+268h]; this
0x18006dea1  test    eax, eax
0x18006dea3  jns     short loc_18006DEB9
0x18006dea5  mov     r9d, eax; char *
0x18006dea8  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006deaf  mov     edx, 0A2h; void *
0x18006deb4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006deb9  mov     rsi, [rsp+268h+var_1D8]
0x18006dec1  mov     rax, [rsi]
0x18006dec4  mov     rbx, [rax+30h]
0x18006dec8  lea     rcx, [rsp+268h+var_218]
0x18006decd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006ded2  lea     rax, [rsp+268h+var_218]
0x18006ded7  mov     [rsp+268h+var_240], rax
0x18006dedc  mov     [rsp+268h+ppv], rdi; int
0x18006dee1  mov     r9, [rsp+268h+var_1E0]
0x18006dee9  mov     r8, [rsp+268h+var_200]
0x18006deee  mov     rdx, [rsp+268h+var_208]
0x18006def3  mov     rcx, rsi
0x18006def6  mov     rax, rbx
0x18006def9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006defe  mov     esi, eax
0x18006df00  test    eax, eax
0x18006df02  js      short loc_18006DF5B
0x18006df04  mov     [rsp+268h+var_228], r13b
0x18006df09  mov     rbx, [rsp+268h+var_218]
0x18006df0e  mov     rcx, rbx
0x18006df11  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@U?$IAsyncOperation@_N@23@@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,void *)
0x18006df16  test    eax, eax
0x18006df18  js      short loc_18006DF2E
0x18006df1a  mov     rax, [rbx]
0x18006df1d  lea     rdx, [rsp+268h+var_228]
0x18006df22  mov     rcx, rbx
0x18006df25  mov     rax, [rax+40h]
0x18006df29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df2e  mov     rcx, [rsp+268h]; this
0x18006df36  test    eax, eax
0x18006df38  jns     short loc_18006DF4E
0x18006df3a  mov     r9d, eax; char *
0x18006df3d  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006df44  mov     edx, 0AFh; void *
0x18006df49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006df4e  mov     al, [rsp+268h+var_228]
0x18006df52  neg     al
0x18006df54  sbb     ebx, ebx
0x18006df56  add     ebx, 2
0x18006df59  jmp     short loc_18006DF60
0x18006df5b  mov     ebx, 2
0x18006df60  mov     dword ptr [rsp+268h+var_220], ebx
0x18006df64  lea     rdx, [rsp+268h+var_220]
0x18006df69  lea     rcx, [rsp+268h+var_198]
0x18006df71  call    ??$RemoteLaunchUriStatus@AEAW40System@Windows@@@LaunchUriOnRemoteSystem@LauncherClientProvider@@QEAAXAEAW4RemoteLaunchUriStatus@System@Windows@@@Z; LauncherClientProvider::LaunchUriOnRemoteSystem::RemoteLaunchUriStatus<Windows::System::RemoteLaunchUriStatus &>(Windows::System::RemoteLaunchUriStatus &)
0x18006df76  mov     rcx, [rsp+268h]; this
0x18006df7e  test    esi, esi
0x18006df80  jns     short loc_18006DF97
0x18006df82  mov     r9d, esi; char *
0x18006df85  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\windows.system.launc"...
0x18006df8c  mov     edx, 0B8h; void *
0x18006df91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006df97  lea     rcx, [rsp+268h+var_1D8]
0x18006df9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dfa4  nop
0x18006dfa5  lea     rcx, [rsp+268h+var_218]
0x18006dfaa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dfaf  nop
0x18006dfb0  lea     rcx, [rsp+268h+string]
  ... truncated ...
```
