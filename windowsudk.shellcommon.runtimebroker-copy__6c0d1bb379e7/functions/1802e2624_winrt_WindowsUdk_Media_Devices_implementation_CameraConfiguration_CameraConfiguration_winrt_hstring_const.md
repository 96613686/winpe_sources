# winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::CameraConfiguration(winrt::hstring const &)

- ea: `0x1802e2624`
- end: `0x1802e28af`
- name: `??0CameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@QEAA@AEBUhstring@5@@Z`
- size: `651`
- prototype: `__int64 __fastcall(winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration *__hidden this, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802e2568`

## callees

- `0x1800227a4`
- `0x1800ce544`
- `0x1800e488c`
- `0x1802e2440`
- `0x1802e2624`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e272e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802e272e`
- `MFPlat!MFStartup` at `0x1802e26b3`
- `MFPlat!MFStartup` at `0x1802e26b3`
- `MFPlat!MFCreateAttributes` at `0x1802e27af`
- `MFPlat!MFCreateAttributes` at `0x1802e27af`

## string_xrefs

- `0x1802e285e`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\result_macros.h`
- `0x1802e27f4`: `FSMSessionName_SettingsBroker_{DFF7FB46-C9CA-48EF-AC38-91E05F5DDEF7}`
- `0x1802e2834`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2849`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2873`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2888`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e289d`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration *__fastcall winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::CameraConfiguration(
        winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration *this,
        const struct winrt::hstring *a2)
{
  _QWORD *v3; // rsi
  _QWORD *v4; // rdi
  HRESULT v5; // eax
  __int64 *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  HRESULT v9; // eax
  LPVOID v10; // r14
  __int64 (__fastcall *v11)(LPVOID, _QWORD, GUID *, char *); // rbp
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  HRESULT v15; // eax
  int v16; // eax
  int v17; // eax
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v22; // [rsp+70h] [rbp+18h] BYREF
  LPVOID v23; // [rsp+78h] [rbp+20h] BYREF

  v22 = 0;
  *((_QWORD *)this + 2) = &winrt::impl::produce<winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration,winrt::WindowsUdk::Media::Devices::ICameraConfiguration>::`vftable';
  *((_QWORD *)this + 3) = &winrt::impl::produce<winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration,winrt::WindowsUdk::Media::Devices::ICameraConfiguration2>::`vftable';
  *((_QWORD *)this + 4) = &winrt::impl::produce<winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration,winrt::WindowsUdk::Media::Devices::ICameraConfiguration3>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::`vftable';
  winrt::hstring::hstring(
    (winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration *)((char *)this + 40),
    a2);
  *((_QWORD *)this + 6) = 0;
  v3 = (_QWORD *)((char *)this + 56);
  *((_QWORD *)this + 7) = 0;
  v4 = (_QWORD *)((char *)this + 64);
  *((_QWORD *)this + 8) = 0;
  *((_BYTE *)this + 72) = 0;
  v5 = MFStartup(0x20070u, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  *((_BYTE *)this + 72) = 1;
  v6 = (__int64 *)wil::CoCreateInstance<IMFCameraConfigurationManager,wil::err_exception_policy>(&v22);
  v7 = *v6;
  *v6 = 0;
  v8 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v7;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v22);
  v22 = 1;
  v23 = 0;
  v9 = CoCreateInstance(&CLSID_FrameServerMonitorObjectFactory, 0, 1u, &GUID_473ae402_5e85_4176_ba86_285b5ce2cb94, &v23);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v9,
      ppva);
  v10 = v23;
  v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, char *))(*(_QWORD *)v23 + 24LL);
  v12 = *v3;
  *v3 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = v11(v10, 0, &GUID_746ea290_a034_4497_8afd_952a87bdd3d5, (char *)this + 56);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v13,
      ppva);
  v14 = *v4;
  *v4 = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v15 = MFCreateAttributes((IMFAttributes **)this + 8, 1u);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v15,
      ppva);
  v16 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v4 + 168LL))(
          *v4,
          MF_FRAMESERVER_ATTRIBUTE_ENABLE_SHARED_EXTENDED_OPERATIONS,
          1);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v16,
      ppva);
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, const wchar_t *, _QWORD))(*(_QWORD *)*v3 + 24LL))(
          *v3,
          8,
          L"FSMSessionName_SettingsBroker_{DFF7FB46-C9CA-48EF-AC38-91E05F5DDEF7}",
          *v4);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v17,
      ppva);
  wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v23);
  return this;
}

```

## disassembly

```asm
0x1802e2624  mov     [rsp+arg_8], rbx
0x1802e2629  mov     [rsp+arg_0], rcx
0x1802e262e  push    rbp
0x1802e262f  push    rsi
0x1802e2630  push    rdi
0x1802e2631  push    r12
0x1802e2633  push    r14
0x1802e2635  sub     rsp, 30h
0x1802e2639  mov     rbx, rcx
0x1802e263c  mov     [rsp+58h+arg_10], 0
0x1802e2644  lea     rax, ??_7?$produce@UCameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@UICameraConfiguration@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration,winrt::WindowsUdk::Media::Devices::ICameraConfiguration>::`vftable'
0x1802e264b  mov     [rcx+10h], rax
0x1802e264f  lea     rax, ??_7?$produce@UCameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@UICameraConfiguration2@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration,winrt::WindowsUdk::Media::Devices::ICameraConfiguration2>::`vftable'
0x1802e2656  mov     [rcx+18h], rax
0x1802e265a  lea     rax, ??_7?$produce@UCameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@UICameraConfiguration3@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration,winrt::WindowsUdk::Media::Devices::ICameraConfiguration3>::`vftable'
0x1802e2661  mov     [rcx+20h], rax
0x1802e2665  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802e266c  mov     r12d, 1
0x1802e2672  mov     [rcx+8], r12
0x1802e2676  lea     rax, ??_7CameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@6B@; const winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::`vftable'
0x1802e267d  mov     [rcx], rax
0x1802e2680  add     rcx, 28h ; '('; this
0x1802e2684  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1802e2689  nop
0x1802e268a  mov     qword ptr [rbx+30h], 0
0x1802e2692  lea     rsi, [rbx+38h]
0x1802e2696  mov     qword ptr [rsi], 0
0x1802e269d  lea     rdi, [rbx+40h]
0x1802e26a1  mov     qword ptr [rdi], 0
0x1802e26a8  mov     byte ptr [rbx+48h], 0
0x1802e26ac  xor     edx, edx; dwFlags
0x1802e26ae  mov     ecx, 20070h; Version
0x1802e26b3  call    cs:__imp_MFStartup
0x1802e26b9  mov     rcx, [rsp+58h]; this
0x1802e26be  test    eax, eax
0x1802e26c0  js      loc_1802E2846
0x1802e26c6  mov     [rbx+48h], r12b
0x1802e26ca  lea     rcx, [rsp+58h+arg_10]
0x1802e26cf  call    ??$CoCreateInstance@UIMFCameraConfigurationManager@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMFCameraConfigurationManager@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IMFCameraConfigurationManager,wil::err_exception_policy>(_GUID const &,ulong)
0x1802e26d4  mov     rdx, [rax]
0x1802e26d7  mov     qword ptr [rax], 0
0x1802e26de  mov     rcx, [rbx+30h]
0x1802e26e2  mov     [rbx+30h], rdx
0x1802e26e6  test    rcx, rcx
0x1802e26e9  jz      short loc_1802E26F8
0x1802e26eb  mov     rax, [rcx]
0x1802e26ee  mov     rax, [rax+10h]
0x1802e26f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e26f7  nop
0x1802e26f8  lea     rcx, [rsp+58h+arg_10]
0x1802e26fd  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e2702  nop
0x1802e2703  mov     [rsp+58h+arg_10], r12d
0x1802e2708  mov     [rsp+58h+arg_18], 0
0x1802e2711  lea     rax, [rsp+58h+arg_18]
0x1802e2716  mov     qword ptr [rsp+58h+ppv], rax; int
0x1802e271b  lea     r9, _GUID_473ae402_5e85_4176_ba86_285b5ce2cb94; riid
0x1802e2722  mov     r8d, r12d; dwClsContext
0x1802e2725  xor     edx, edx; pUnkOuter
0x1802e2727  lea     rcx, CLSID_FrameServerMonitorObjectFactory; rclsid
0x1802e272e  call    cs:__imp_CoCreateInstance
0x1802e2734  mov     rcx, [rsp+58h]; this
0x1802e2739  test    eax, eax
0x1802e273b  js      loc_1802E285B
0x1802e2741  mov     r14, [rsp+58h+arg_18]
0x1802e2746  mov     rax, [r14]
0x1802e2749  mov     rbp, [rax+18h]
0x1802e274d  mov     rcx, [rsi]
0x1802e2750  mov     qword ptr [rsi], 0
0x1802e2757  test    rcx, rcx
0x1802e275a  jz      short loc_1802E2769
0x1802e275c  mov     rdx, [rcx]
0x1802e275f  mov     rax, [rdx+10h]
0x1802e2763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2768  nop
0x1802e2769  mov     r9, rsi
0x1802e276c  lea     r8, _GUID_746ea290_a034_4497_8afd_952a87bdd3d5
0x1802e2773  xor     edx, edx
0x1802e2775  mov     rcx, r14
0x1802e2778  mov     rax, rbp
0x1802e277b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2780  mov     rcx, [rsp+58h]; this
0x1802e2785  test    eax, eax
0x1802e2787  js      loc_1802E2870
0x1802e278d  mov     rcx, [rdi]
0x1802e2790  mov     qword ptr [rdi], 0
0x1802e2797  test    rcx, rcx
0x1802e279a  jz      short loc_1802E27A9
0x1802e279c  mov     rax, [rcx]
0x1802e279f  mov     rax, [rax+10h]
0x1802e27a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e27a8  nop
0x1802e27a9  mov     edx, r12d; cInitialSize
0x1802e27ac  mov     rcx, rdi; ppMFAttributes
0x1802e27af  call    cs:__imp_MFCreateAttributes
0x1802e27b5  mov     rcx, [rsp+58h]; this
0x1802e27ba  test    eax, eax
0x1802e27bc  js      loc_1802E2885
0x1802e27c2  mov     rcx, [rdi]
0x1802e27c5  mov     rax, [rcx]
0x1802e27c8  mov     r8d, r12d
0x1802e27cb  lea     rdx, MF_FRAMESERVER_ATTRIBUTE_ENABLE_SHARED_EXTENDED_OPERATIONS
0x1802e27d2  mov     rax, [rax+0A8h]
0x1802e27d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e27de  mov     rcx, [rsp+58h]; this
0x1802e27e3  test    eax, eax
0x1802e27e5  js      loc_1802E289A
0x1802e27eb  mov     rcx, [rsi]
0x1802e27ee  mov     rax, [rcx]
0x1802e27f1  mov     r9, [rdi]
0x1802e27f4  lea     r8, aFsmsessionname; "FSMSessionName_SettingsBroker_{DFF7FB46"...
0x1802e27fb  mov     edx, 8
0x1802e2800  mov     rax, [rax+18h]
0x1802e2804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2809  mov     rcx, [rsp+58h]; this
0x1802e280e  test    eax, eax
0x1802e2810  js      short loc_1802E2831
0x1802e2812  lea     rcx, [rsp+58h+arg_18]
0x1802e2817  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e281c  nop
0x1802e281d  mov     rax, rbx
0x1802e2820  mov     rbx, [rsp+58h+arg_8]
0x1802e2825  add     rsp, 30h
0x1802e2829  pop     r14
0x1802e282b  pop     r12
0x1802e282d  pop     rdi
0x1802e282e  pop     rsi
0x1802e282f  pop     rbp
0x1802e2830  retn
0x1802e2831  mov     r9d, eax; char *
0x1802e2834  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e283b  mov     edx, 31h ; '1'; void *
0x1802e2840  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2846  mov     r9d, eax; char *
0x1802e2849  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2850  mov     edx, 26h ; '&'; void *
0x1802e2855  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e285b  mov     r9d, eax; char *
0x1802e285e  lea     r8, aOnecoreInterna_18; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x1802e2865  mov     edx, 1CBEh; void *
0x1802e286a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2870  mov     r9d, eax; char *
0x1802e2873  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e287a  mov     edx, 2Ch ; ','; void *
0x1802e287f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2885  mov     r9d, eax; char *
0x1802e2888  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e288f  mov     edx, 2Fh ; '/'; void *
0x1802e2894  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e289a  mov     r9d, eax; char *
0x1802e289d  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e28a4  mov     edx, 30h ; '0'; void *
0x1802e28a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
