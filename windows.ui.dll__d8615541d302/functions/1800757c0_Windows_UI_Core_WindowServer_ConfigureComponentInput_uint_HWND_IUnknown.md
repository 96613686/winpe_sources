# Windows::UI::Core::WindowServer::ConfigureComponentInput(uint,HWND__ *,IUnknown *)

- ea: `0x1800757c0`
- end: `0x180075aca`
- name: `?ConfigureComponentInput@WindowServer@Core@UI@Windows@@UEAAJIPEAUHWND__@@PEAUIUnknown@@@Z`
- size: `778`
- prototype: `int(Windows::UI::Core::WindowServer *__hidden this, unsigned int, HWND, struct IUnknown *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002684`
- `0x1800038e0`
- `0x18001278c`
- `0x18001b90c`
- `0x18001bb4c`
- `0x18002714c`
- `0x180029120`
- `0x18004cb8c`
- `0x180058748`
- `0x1800726fc`
- `0x180073f44`
- `0x1800757c0`
- `0x180076ccc`
- `0x180079860`
- `0x18007c220`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007591b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007591b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075a5b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180075806`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180075806`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18007581b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18007581b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800758b0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800758b0`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180075a7c`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180075a7c`
- `api-ms-win-rtcore-ntuser-private-l1-1-2!__imp_SetCoreWindowPartner` at `0x1800758ea`
- `api-ms-win-rtcore-ntuser-private-l1-1-2!__imp_SetCoreWindowPartner` at `0x180075a26`
- `api-ms-win-rtcore-ntuser-private-l1-1-2!__imp_SetCoreWindowPartner` at `0x1800758ea`
- `api-ms-win-rtcore-ntuser-private-l1-1-2!__imp_SetCoreWindowPartner` at `0x180075a26`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x180075a53`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x180075a53`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180075913`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x180075913`

## string_xrefs

- `0x180075aa9`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180075ab8`: `You are trying to configure a component that was not launched as a component`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::WindowServer::ConfigureComponentInput(
        Windows::UI::Core::WindowServer *this,
        int a2,
        HWND a3,
        struct IUnknown *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  const WCHAR *FileNameW; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // ebx
  __int64 v15; // rcx
  HWND v16; // rcx
  signed int LastError; // eax
  void *v18; // rax
  __int64 v19; // rdx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  __int64 v21; // rdx
  HWND v22; // rcx
  signed int v23; // eax
  unsigned int v25; // eax
  char *v26; // [rsp+28h] [rbp-50h]
  _BYTE v27[4]; // [rsp+30h] [rbp-48h] BYREF
  char v28[4]; // [rsp+34h] [rbp-44h] BYREF
  LPCWSTR pszPath[8]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( Windows::Internal::ApplicationModel::WindowManagement::IsComponentUICShellPolicyEnabled(this) )
  {
    pszPath[0] = 0;
    if ( (int)wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
                v9,
                v8,
                pszPath) >= 0 )
    {
      FileNameW = PathFindFileNameW(pszPath[0]);
      if ( FileNameW )
      {
        if ( StrStrIW(FileNameW, L"zStartApp.exe") )
        {
          if ( (unsigned int)dword_1801340C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801340C0, 0x400000000000LL) )
          {
            *(_DWORD *)v28 = *((_DWORD *)this + 818);
            v27[0] = *((_BYTE *)this + 2425);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
              v11,
              (unsigned int)word_18011EE82,
              v12,
              v13,
              (__int64)v27,
              (__int64)v28);
          }
          if ( !*((_BYTE *)this + 2425) )
          {
            v25 = wil::verify_hresult<long>(0);
            wil::details::in1diag3::FailFast_HrMsg(
              retaddr,
              (void *)0x4B3,
              (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
              (const char *)v25,
              (int)"You are trying to configure a component that was not launched as a component",
              v26);
          }
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pszPath);
  }
  v14 = 0;
  if ( !*((_BYTE *)this + 2425) )
  {
    v14 = -2147418113;
    RoOriginateError(2147549183LL, 0);
  }
  if ( v14 >= 0 )
  {
    if ( !a3 && a2 )
      return (unsigned int)-2147024809;
    v15 = *((_QWORD *)this + 409);
    if ( a3 )
    {
      if ( (unsigned int)SetCoreWindowPartner(v15, 2, a3) )
      {
        v16 = (HWND)*((_QWORD *)this + 409);
        *((_DWORD *)this + 607) = a2;
        *((_QWORD *)this + 304) = a3;
        SetPropW(v16, L"CrossProcessParentHWND", a3);
      }
      else
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        if ( v14 < 0 )
          return (unsigned int)v14;
      }
      if ( CoreInputSink::Handle((Windows::UI::Core::WindowServer *)((char *)this + 2440)) )
      {
LABEL_29:
        if ( a4 )
        {
          QueryInterface = a4->lpVtbl->QueryInterface;
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 2528);
          v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))QueryInterface)(
                  a4,
                  &GUID_e8de1639_4331_4b26_bc5f_6a321d347a85,
                  (char *)this + 2528);
          LOBYTE(v21) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_ComposerScalingPolicy>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_ComposerScalingPolicy>::GetImpl'::`2'::impl,
            v21);
        }
        return (unsigned int)v14;
      }
      *(_DWORD *)v28 = 0;
      v14 = (*(__int64 (__fastcall **)(Windows::UI::Core::WindowServer *, char *))(*(_QWORD *)this + 32LL))(this, v28);
      if ( v14 >= 0 )
      {
        v14 = CoreInputSink::SetInputSource(
                (Windows::UI::Core::WindowServer *)((char *)this + 2440),
                *((HWND *)this + 409),
                a4,
                15,
                1,
                *(unsigned int *)v28);
        if ( *((_QWORD *)this + 364) )
        {
          v18 = CoreInputSink::Handle((Windows::UI::Core::WindowServer *)((char *)this + 2440));
          *(_QWORD *)(v19 + 40) = v18;
        }
        if ( v14 >= 0 )
        {
          if ( Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::ApplicationViewConsolidatedEventArgsInternal *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize((char *)this + 1872) )
            Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::Core::WindowServer *,std::nullptr_t>(
              (char *)this + 1872,
              (char *)this - 192);
          goto LABEL_29;
        }
      }
    }
    else
    {
      if ( (unsigned int)SetCoreWindowPartner(v15, 0, *((_QWORD *)this + 304)) )
      {
        v22 = (HWND)*((_QWORD *)this + 409);
        *((_DWORD *)this + 607) = 0;
        *((_QWORD *)this + 304) = 0;
        RemovePropW(v22, L"CrossProcessParentHWND");
      }
      else
      {
        v23 = GetLastError();
        v14 = v23;
        if ( v23 > 0 )
          v14 = (unsigned __int16)v23 | 0x80070000;
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 2528);
      if ( !(unsigned int)IsOneCoreTransformMode() )
        Windows::UI::Core::WindowServer::LegacyTransforms_ResetComponentDisplayInformationState((Windows::UI::Core::WindowServer *)((char *)this - 192));
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800757c0  push    rbx
0x1800757c2  push    rbp
0x1800757c3  push    rsi
0x1800757c4  push    rdi
0x1800757c5  push    r14
0x1800757c7  push    r15
0x1800757c9  sub     rsp, 48h
0x1800757cd  mov     r15, r9
0x1800757d0  mov     rdi, r8
0x1800757d3  mov     r14d, edx
0x1800757d6  mov     rsi, rcx
0x1800757d9  call    ?IsComponentUICShellPolicyEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsComponentUICShellPolicyEnabled(void)
0x1800757de  test    al, al
0x1800757e0  jz      loc_180075896
0x1800757e6  lea     r8, [rsp+78h+pszPath]
0x1800757eb  mov     [rsp+78h+pszPath], 0
0x1800757f4  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800757f9  test    eax, eax
0x1800757fb  js      loc_18007588C
0x180075801  mov     rcx, [rsp+78h+pszPath]; pszPath
0x180075806  call    cs:__imp_PathFindFileNameW
0x18007580c  test    rax, rax
0x18007580f  jz      short loc_18007588C
0x180075811  lea     rdx, pszSrch; "zStartApp.exe"
0x180075818  mov     rcx, rax; pszFirst
0x18007581b  call    cs:__imp_StrStrIW
0x180075821  test    rax, rax
0x180075824  jz      short loc_18007588C
0x180075826  mov     eax, cs:dword_1801340C0
0x18007582c  cmp     eax, 5
0x18007582f  jbe     short loc_18007587F
0x180075831  mov     rdx, 400000000000h
0x18007583b  lea     rcx, dword_1801340C0
0x180075842  call    _tlgKeywordOn
0x180075847  test    al, al
0x180075849  jz      short loc_18007587F
0x18007584b  mov     eax, [rsi+0CC8h]
0x180075851  lea     rdx, word_18011EE82
0x180075858  mov     dword ptr [rsp+78h+var_44], eax
0x18007585c  mov     al, [rsi+979h]
0x180075862  mov     [rsp+78h+var_48], al
0x180075866  lea     rax, [rsp+78h+var_44]
0x18007586b  mov     [rsp+78h+var_50], rax; char *
0x180075870  lea     rax, [rsp+78h+var_48]
0x180075875  mov     qword ptr [rsp+78h+var_58], rax
0x18007587a  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18007587f  cmp     byte ptr [rsi+979h], 0
0x180075886  jz      loc_180075A9D
0x18007588c  lea     rcx, [rsp+78h+pszPath]
0x180075891  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180075896  xor     ebx, ebx
0x180075898  lea     rbp, [rsi-0C0h]
0x18007589f  cmp     [rbp+0A39h], bl
0x1800758a5  jnz     short loc_1800758B6
0x1800758a7  mov     ebx, 8000FFFFh
0x1800758ac  xor     edx, edx
0x1800758ae  mov     ecx, ebx
0x1800758b0  call    cs:__imp_RoOriginateError
0x1800758b6  test    ebx, ebx
0x1800758b8  js      loc_180075A8E
0x1800758be  test    rdi, rdi
0x1800758c1  jnz     short loc_1800758D2
0x1800758c3  test    r14d, r14d
0x1800758c6  jz      short loc_1800758D2
0x1800758c8  mov     ebx, 80070057h
0x1800758cd  jmp     loc_180075A8E
0x1800758d2  mov     rcx, [rsi+0CC8h]
0x1800758d9  test    rdi, rdi
0x1800758dc  jz      loc_180075A1D
0x1800758e2  mov     r8, rdi
0x1800758e5  mov     edx, 2
0x1800758ea  call    cs:__imp_SetCoreWindowPartner
0x1800758f0  test    eax, eax
0x1800758f2  jz      short loc_18007591B
0x1800758f4  mov     rcx, [rsi+0CC8h]; hWnd
0x1800758fb  lea     rdx, aCrossprocesspa; "CrossProcessParentHWND"
0x180075902  mov     r8, rdi; hData
0x180075905  mov     [rsi+97Ch], r14d
0x18007590c  mov     [rsi+980h], rdi
0x180075913  call    cs:__imp_SetPropW
0x180075919  jmp     short loc_180075938
0x18007591b  call    cs:__imp_GetLastError
0x180075921  mov     ebx, eax
0x180075923  test    eax, eax
0x180075925  jle     short loc_180075930
0x180075927  movzx   ebx, ax
0x18007592a  or      ebx, 80070000h
0x180075930  test    ebx, ebx
0x180075932  js      loc_180075A8E
0x180075938  lea     rdi, [rsi+988h]
0x18007593f  mov     rcx, rdi; this
0x180075942  call    ?Handle@CoreInputSink@@QEAAPEAXXZ; CoreInputSink::Handle(void)
0x180075947  test    rax, rax
0x18007594a  jnz     loc_1800759D8
0x180075950  mov     dword ptr [rsp+78h+var_44], eax
0x180075954  lea     rdx, [rsp+78h+var_44]
0x180075959  mov     rax, [rsi]
0x18007595c  mov     rcx, rsi
0x18007595f  mov     rax, [rax+20h]
0x180075963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075968  mov     ebx, eax
0x18007596a  test    eax, eax
0x18007596c  js      loc_180075A8E
0x180075972  mov     eax, dword ptr [rsp+78h+var_44]
0x180075976  mov     r9d, 0Fh; unsigned int
0x18007597c  mov     rdx, [rsi+0CC8h]; HWND
0x180075983  mov     r8, r15; struct IUnknown *
0x180075986  mov     dword ptr [rsp+78h+var_50], eax; unsigned int
0x18007598a  mov     rcx, rdi; this
0x18007598d  mov     [rsp+78h+var_58], 1; bool
0x180075992  call    ?SetInputSource@CoreInputSink@@QEAAJPEAUHWND__@@PEAUIUnknown@@I_NI@Z; CoreInputSink::SetInputSource(HWND__ *,IUnknown *,uint,bool,uint)
0x180075997  mov     rdx, [rsi+0B60h]
0x18007599e  mov     ebx, eax
0x1800759a0  test    rdx, rdx
0x1800759a3  jz      short loc_1800759B1
0x1800759a5  mov     rcx, rdi; this
0x1800759a8  call    ?Handle@CoreInputSink@@QEAAPEAXXZ; CoreInputSink::Handle(void)
0x1800759ad  mov     [rdx+28h], rax
0x1800759b1  test    ebx, ebx
0x1800759b3  js      loc_180075A8E
0x1800759b9  lea     rdi, [rsi+750h]
0x1800759c0  mov     rcx, rdi
0x1800759c3  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVApplicationViewConsolidatedEventArgsInternal@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::ApplicationViewConsolidatedEventArgsInternal *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x1800759c8  test    rax, rax
0x1800759cb  jz      short loc_1800759D8
0x1800759cd  mov     rdx, rbp
0x1800759d0  mov     rcx, rdi
0x1800759d3  call    ??$InvokeAll@PEAVWindowServer@Core@UI@Windows@@$$T@?$EventSource@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVWindowServer@Core@UI@Windows@@$$T@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::Core::WindowServer *,std::nullptr_t>(Windows::UI::Core::WindowServer *,std::nullptr_t)
0x1800759d8  test    r15, r15
0x1800759db  jz      loc_180075A8E
0x1800759e1  mov     rax, [r15]
0x1800759e4  lea     rbx, [rsi+9E0h]
0x1800759eb  mov     rcx, rbx
0x1800759ee  mov     rdi, [rax]
0x1800759f1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800759f6  mov     r8, rbx
0x1800759f9  lea     rdx, _GUID_e8de1639_4331_4b26_bc5f_6a321d347a85
0x180075a00  mov     rcx, r15
0x180075a03  mov     rax, rdi
0x180075a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a0b  mov     ebx, eax
0x180075a0d  mov     dl, 1
0x180075a0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ComposerScalingPolicy@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ComposerScalingPolicy@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ComposerScalingPolicy> `wil::Feature<__WilFeatureTraits_Feature_ComposerScalingPolicy>::GetImpl(void)'::`2'::impl
0x180075a16  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ComposerScalingPolicy@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ComposerScalingPolicy>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180075a1b  jmp     short loc_180075A8E
0x180075a1d  mov     r8, [rsi+980h]
0x180075a24  xor     edx, edx
0x180075a26  call    cs:__imp_SetCoreWindowPartner
0x180075a2c  test    eax, eax
0x180075a2e  jz      short loc_180075A5B
0x180075a30  mov     rcx, [rsi+0CC8h]; hWnd
0x180075a37  lea     rdx, aCrossprocesspa; "CrossProcessParentHWND"
0x180075a3e  mov     dword ptr [rsi+97Ch], 0
0x180075a48  mov     qword ptr [rsi+980h], 0
0x180075a53  call    cs:__imp_RemovePropW
0x180075a59  jmp     short loc_180075A70
0x180075a5b  call    cs:__imp_GetLastError
0x180075a61  mov     ebx, eax
0x180075a63  test    eax, eax
0x180075a65  jle     short loc_180075A70
0x180075a67  movzx   ebx, ax
0x180075a6a  or      ebx, 80070000h
0x180075a70  lea     rcx, [rsi+9E0h]
0x180075a77  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180075a7c  call    cs:__imp_IsOneCoreTransformMode
0x180075a82  test    eax, eax
0x180075a84  jnz     short loc_180075A8E
0x180075a86  mov     rcx, rbp; this
0x180075a89  call    ?LegacyTransforms_ResetComponentDisplayInformationState@WindowServer@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::WindowServer::LegacyTransforms_ResetComponentDisplayInformationState(void)
0x180075a8e  mov     eax, ebx
0x180075a90  add     rsp, 48h
0x180075a94  pop     r15
0x180075a96  pop     r14
0x180075a98  pop     rdi
0x180075a99  pop     rsi
0x180075a9a  pop     rbp
0x180075a9b  pop     rbx
0x180075a9c  retn
0x180075a9d  xor     ecx, ecx
0x180075a9f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180075aa4  mov     rcx, [rsp+78h]; this
0x180075aa9  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180075ab0  mov     r9d, eax; char *
0x180075ab3  mov     edx, 4B3h; void *
0x180075ab8  lea     rax, aYouAreTryingTo; "You are trying to configure a component"...
0x180075abf  mov     qword ptr [rsp+78h+var_58], rax; int
0x180075ac4  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
```
