# winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::SetupPins(void)

- ea: `0x1800f77f8`
- end: `0x1800f7b62`
- name: `?SetupPins@VirtualMicrophoneDevice@implementation@Devices@Media@WindowsUdk@winrt@@AEAAXXZ`
- size: `874`
- prototype: `void __fastcall(winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f5a98`

## callees

- `0x18000b428`
- `0x180028978`
- `0x180031f90`
- `0x18003b61c`
- `0x1800d4450`
- `0x1800f5e5c`
- `0x1800f76c0`
- `0x1800f77f8`
- `0x1800f7c10`
- `0x18015cb00`
- `0x18015cfdc`
- `0x1802b92ac`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800f7adf`
- `msvcp_win!_Mtx_unlock` at `0x1800f7adf`
- `Apx01000!imp_ApxObjectDelete` at `0x1800f7a15`
- `Apx01000!imp_ApxObjectDelete` at `0x1800f7a15`
- `Apx01000!imp_ApxPinAddJacks` at `0x1800f7a04`
- `Apx01000!imp_ApxPinAddJacks` at `0x1800f7a04`
- `Apx01000!imp_ApxJackCreate` at `0x1800f79cc`
- `Apx01000!imp_ApxJackCreate` at `0x1800f79cc`
- `Apx01000!imp_ApxCircuitAddPins` at `0x1800f78f0`
- `Apx01000!imp_ApxCircuitAddPins` at `0x1800f7b11`
- `Apx01000!imp_ApxCircuitAddPins` at `0x1800f78f0`
- `Apx01000!imp_ApxCircuitAddPins` at `0x1800f7b11`
- `Apx01000!imp_ApxPinAssignModeDataFormatList` at `0x1800f78ba`
- `Apx01000!imp_ApxPinAssignModeDataFormatList` at `0x1800f78ba`
- `Apx01000!imp_ApxPinCreate` at `0x1800f787a`
- `Apx01000!imp_ApxPinCreate` at `0x1800f7959`
- `Apx01000!imp_ApxPinCreate` at `0x1800f787a`
- `Apx01000!imp_ApxPinCreate` at `0x1800f7959`

## string_xrefs

- `0x1800f7893`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f796b`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f79e5`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\virtualmicrophonedevice.cpp`
- `0x1800f7884`: `ApxPinCreate failed`
- `0x1800f79d6`: `ApxJackCreate failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice::SetupPins(
        winrt::WindowsUdk::Media::Devices::implementation::VirtualMicrophoneDevice *this)
{
  _QWORD *v2; // rbx
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  _QWORD *v7; // rdi
  unsigned int v8; // eax
  int v9; // ebx
  std::_Mutex_base *v10; // rbx
  __int64 v11; // r8
  _QWORD *v12; // rax
  unsigned int v13; // eax
  const char *v14; // [rsp+28h] [rbp-D8h]
  const char *v15; // [rsp+28h] [rbp-D8h]
  const char *v16; // [rsp+28h] [rbp-D8h]
  const char *v17; // [rsp+28h] [rbp-D8h]
  const char *v18; // [rsp+28h] [rbp-D8h]
  const char *v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  char *v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+5Ch] [rbp-A4h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  GUID *v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  int v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+8Ch] [rbp-74h]
  int v33; // [rsp+94h] [rbp-6Ch]
  GUID *v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+ACh] [rbp-54h]
  _BYTE v38[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-48h]
  _BYTE v40[8]; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v41; // [rsp+D0h] [rbp-30h]
  std::_Mutex_base *v42; // [rsp+D8h] [rbp-28h]
  _DWORD v43[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v44; // [rsp+E8h] [rbp-18h]
  _QWORD *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  __m128i si128; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v26 = 1;
  v28 = 0;
  v29 = 1;
  v23 = 48;
  v24 = -1;
  v25 = 2;
  v27 = &GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196;
  v2 = (_QWORD *)((char *)this + 248);
  v3 = imp_ApxPinCreate(0, 0, &v23, (char *)this + 248);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1FC,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v3,
    (int)"ApxPinCreate failed",
    v14);
  v4 = imp_ApxPinAssignModeDataFormatList(0, *v2, &GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3, *((_QWORD *)this + 29));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x207,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v4,
    (int)"ApxPinAssignModeDataFormatList failed",
    v15);
  v5 = imp_ApxCircuitAddPins(0, *((_QWORD *)this + 28), v2, 1);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x20E,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v5,
    (int)"ApxCircuitAddPins failed",
    v16);
  *v2 = 0;
  v33 = 0;
  v35 = 0;
  v37 = 0;
  v30 = 48;
  v31 = -1;
  v36 = -1;
  v32 = 1;
  v34 = &GUID_dff21be1_f70f_11d0_b917_00a0c9223196;
  v6 = imp_ApxPinCreate(0, 0, &v30, (char *)this + 256);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x21E,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v6,
    (int)"ApxPinCreate failed",
    v17);
  v22[0] = 16;
  v22[1] = winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtJackRetrievePresenceState;
  v44 = 1;
  v43[0] = 48;
  v43[1] = -1;
  v46 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v45 = v22;
  v7 = (_QWORD *)((char *)this + 264);
  v8 = imp_ApxJackCreate(0, 0, v43, (char *)this + 264);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x230,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v8,
    (int)"ApxJackCreate failed",
    v18);
  v9 = imp_ApxPinAddJacks(0, *((_QWORD *)this + 32), (char *)this + 264, 1);
  if ( v9 < 0 )
  {
    imp_ApxObjectDelete(0, *v7);
    *v7 = 0;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x238,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
      (const char *)(unsigned int)v9,
      (int)"ApxPinAddJacks failed",
      v19);
  }
  v10 = *(std::_Mutex_base **)winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(v40);
  *(_QWORD *)&v39 = _scrt_stub_for_acrt_uninitialize_critical;
  DWORD2(v39) = 0;
  HIDWORD(v39) = HIDWORD(v41);
  v21 = (char *)operator new(0x28u);
  winrt::impl::implements_delegate_base::implements_delegate_base((winrt::impl::implements_delegate_base *)(v21 + 8));
  *(_QWORD *)(v11 + 16) = this;
  *(_OWORD *)(v11 + 24) = v39;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v11 = &winrt::impl::variadic_delegate<_lambda_08ecad9fd8630207e1b35e495c4301ae_,void,winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamDeletedEventArgs>::`vftable';
  v20 = v11;
  v21 = (char *)*v7;
  v42 = v10;
  std::_Mutex_base::lock(v10);
  v12 = (_QWORD *)std::map<APXJACK__ *,winrt::delegate<bool (winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::RetrieveJackPresenceStateEventArgs)>>::_Try_emplace<APXJACK__ * const &,>(
                    (char *)v10 + 240,
                    v38,
                    &v21);
  winrt::Windows::Foundation::IUnknown::operator=(*v12 + 40LL, &v20);
  _Mtx_unlock(v10);
  winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension((winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension *)&v20);
  if ( v41 )
    std::_Ref_count_base::_Decref(v41);
  v13 = imp_ApxCircuitAddPins(0, *((_QWORD *)this + 28), (char *)this + 256, 1);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x245,
    (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\virtualmicrophonedevice.cpp",
    (const char *)v13,
    (int)"ApxCircuitAddPins failed",
    v19);
  *((_QWORD *)this + 32) = 0;
}

```

## disassembly

```asm
0x1800f77f8  mov     [rsp-8+arg_8], rbx
0x1800f77fd  mov     [rsp-8+arg_10], rsi
0x1800f7802  push    rbp
0x1800f7803  push    rdi
0x1800f7804  push    r13
0x1800f7806  push    r14
0x1800f7808  push    r15
0x1800f780a  lea     rbp, [rsp-20h]
0x1800f780f  sub     rsp, 120h
0x1800f7816  mov     rax, cs:__security_cookie
0x1800f781d  xor     rax, rsp
0x1800f7820  mov     [rbp+40h+var_30], rax
0x1800f7824  mov     r14, rcx
0x1800f7827  xor     r13d, r13d
0x1800f782a  mov     [rsp+140h+var_E0], 1
0x1800f7833  mov     [rsp+140h+var_D0], r13
0x1800f7838  mov     [rsp+140h+var_C8], 1
0x1800f7841  mov     [rsp+140h+var_F0], 30h ; '0'
0x1800f784a  or      r15d, 0FFFFFFFFh
0x1800f784e  mov     [rsp+140h+var_E8], r15d
0x1800f7853  mov     [rsp+140h+var_E4], 2
0x1800f785b  lea     rax, _GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196
0x1800f7862  mov     [rsp+140h+var_D8], rax
0x1800f7867  lea     rbx, [rcx+0F8h]
0x1800f786e  mov     r9, rbx
0x1800f7871  lea     r8, [rsp+140h+var_F0]
0x1800f7876  xor     edx, edx
0x1800f7878  xor     ecx, ecx
0x1800f787a  call    cs:__imp_imp_ApxPinCreate
0x1800f7880  mov     rcx, [rbp+48h]; this
0x1800f7884  lea     rdi, aApxpincreateFa; "ApxPinCreate failed"
0x1800f788b  mov     qword ptr [rsp+140h+var_120], rdi; int
0x1800f7890  mov     r9d, eax; char *
0x1800f7893  lea     rsi, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f789a  mov     r8, rsi; unsigned int
0x1800f789d  mov     edx, 1FCh; void *
0x1800f78a2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f78a7  mov     r9, [r14+0E8h]
0x1800f78ae  lea     r8, _GUID_c18e2f7e_933d_4965_b7d1_1eef228d2af3
0x1800f78b5  mov     rdx, [rbx]
0x1800f78b8  xor     ecx, ecx
0x1800f78ba  call    cs:__imp_imp_ApxPinAssignModeDataFormatList
0x1800f78c0  mov     rcx, [rbp+48h]; this
0x1800f78c4  lea     rdx, aApxpinassignmo; "ApxPinAssignModeDataFormatList failed"
0x1800f78cb  mov     qword ptr [rsp+140h+var_120], rdx; int
0x1800f78d0  mov     r9d, eax; char *
0x1800f78d3  mov     r8, rsi; unsigned int
0x1800f78d6  mov     edx, 207h; void *
0x1800f78db  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f78e0  lea     r9d, [r13+1]
0x1800f78e4  mov     r8, rbx
0x1800f78e7  mov     rdx, [r14+0E0h]
0x1800f78ee  xor     ecx, ecx
0x1800f78f0  call    cs:__imp_imp_ApxCircuitAddPins
0x1800f78f6  mov     rcx, [rbp+48h]; this
0x1800f78fa  lea     rdx, aApxcircuitaddp; "ApxCircuitAddPins failed"
0x1800f7901  mov     qword ptr [rsp+140h+var_120], rdx; int
0x1800f7906  mov     r9d, eax; char *
0x1800f7909  mov     r8, rsi; unsigned int
0x1800f790c  mov     edx, 20Eh; void *
0x1800f7911  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f7916  mov     [rbx], r13
0x1800f7919  mov     [rbp+40h+var_B0], r13
0x1800f791d  mov     [rbp+40h+var_A0], r13
0x1800f7921  mov     [rbp+40h+var_94], r13d
0x1800f7925  mov     [rbp+40h+var_C0], 30h ; '0'
0x1800f792d  mov     [rbp+40h+var_B8], r15d
0x1800f7931  mov     [rbp+40h+var_98], r15d
0x1800f7935  lea     ebx, [r13+1]
0x1800f7939  mov     [rbp+40h+var_B4], ebx
0x1800f793c  lea     rax, _GUID_dff21be1_f70f_11d0_b917_00a0c9223196
0x1800f7943  mov     [rbp+40h+var_A8], rax
0x1800f7947  lea     rsi, [r14+100h]
0x1800f794e  mov     r9, rsi
0x1800f7951  lea     r8, [rbp+40h+var_C0]
0x1800f7955  xor     edx, edx
0x1800f7957  xor     ecx, ecx
0x1800f7959  call    cs:__imp_imp_ApxPinCreate
0x1800f795f  mov     rcx, [rbp+48h]; this
0x1800f7963  mov     qword ptr [rsp+140h+var_120], rdi; int
0x1800f7968  mov     r9d, eax; char *
0x1800f796b  lea     r8, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f7972  mov     edx, 21Eh; void *
0x1800f7977  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f797c  mov     [rsp+140h+var_100], 10h
0x1800f7985  lea     rax, ?EvtJackRetrievePresenceState@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SAJPEAUAPXJACK__@@PEAE@Z; winrt::WindowsUdk::Media::Devices::implementation::ApxService::EvtJackRetrievePresenceState(APXJACK__ *,uchar *)
0x1800f798c  mov     [rsp+140h+var_F8], rax
0x1800f7991  mov     [rbp+40h+var_58], rbx
0x1800f7995  mov     [rbp+40h+var_60], 30h ; '0'
0x1800f799c  mov     [rbp+40h+var_5C], r15d
0x1800f79a0  mov     [rbp+40h+var_48], r13
0x1800f79a4  movdqa  xmm0, cs:__xmm@00000001000000030000000e00000006
0x1800f79ac  movdqu  [rbp+40h+var_40], xmm0
0x1800f79b1  lea     rax, [rsp+140h+var_100]
0x1800f79b6  mov     [rbp+40h+var_50], rax
0x1800f79ba  lea     rdi, [r14+108h]
0x1800f79c1  mov     r9, rdi
0x1800f79c4  lea     r8, [rbp+40h+var_60]
0x1800f79c8  xor     edx, edx
0x1800f79ca  xor     ecx, ecx
0x1800f79cc  call    cs:__imp_imp_ApxJackCreate
0x1800f79d2  mov     rcx, [rbp+48h]; this
0x1800f79d6  lea     rdx, aApxjackcreateF; "ApxJackCreate failed"
0x1800f79dd  mov     qword ptr [rsp+140h+var_120], rdx; int
0x1800f79e2  mov     r9d, eax; char *
0x1800f79e5  lea     r15, aShellcommonUnd_146; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1800f79ec  mov     r8, r15; unsigned int
0x1800f79ef  mov     edx, 230h; void *
0x1800f79f4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f79f9  mov     r9d, ebx
0x1800f79fc  mov     r8, rdi
0x1800f79ff  mov     rdx, [rsi]
0x1800f7a02  xor     ecx, ecx
0x1800f7a04  call    cs:__imp_imp_ApxPinAddJacks
0x1800f7a0a  mov     ebx, eax
0x1800f7a0c  test    eax, eax
0x1800f7a0e  jns     short loc_1800F7A3F
0x1800f7a10  mov     rdx, [rdi]
0x1800f7a13  xor     ecx, ecx
0x1800f7a15  call    cs:__imp_imp_ApxObjectDelete
0x1800f7a1b  mov     [rdi], r13
0x1800f7a1e  mov     rcx, [rbp+48h]; this
0x1800f7a22  lea     rax, aApxpinaddjacks; "ApxPinAddJacks failed"
0x1800f7a29  mov     qword ptr [rsp+140h+var_120], rax; int
0x1800f7a2e  mov     r9d, ebx; char *
0x1800f7a31  mov     r8, r15; unsigned int
0x1800f7a34  mov     edx, 238h; void *
0x1800f7a39  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f7a3f  lea     rcx, [rbp+40h+var_78]
0x1800f7a43  call    ?GetInstance@ApxService@implementation@Devices@Media@WindowsUdk@winrt@@SA?AV?$shared_ptr@VApxService@implementation@Devices@Media@WindowsUdk@winrt@@@std@@XZ; winrt::WindowsUdk::Media::Devices::implementation::ApxService::GetInstance(void)
0x1800f7a48  nop
0x1800f7a49  mov     rbx, [rax]
0x1800f7a4c  lea     rax, __scrt_stub_for_acrt_uninitialize_critical
0x1800f7a53  mov     qword ptr [rbp+40h+var_88], rax
0x1800f7a57  mov     dword ptr [rbp+40h+var_88+8], r13d
0x1800f7a5b  mov     eax, [rbp+40h+var_6C]
0x1800f7a5e  mov     dword ptr [rbp+40h+var_88+0Ch], eax
0x1800f7a61  mov     ecx, 28h ; '('; Size
0x1800f7a66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f7a6b  mov     r8, rax
0x1800f7a6e  mov     [rsp+140h+var_108], rax
0x1800f7a73  lea     rcx, [rax+8]; this
0x1800f7a77  call    ??0implements_delegate_base@impl@winrt@@QEAA@XZ; winrt::impl::implements_delegate_base::implements_delegate_base(void)
0x1800f7a7c  mov     [r8+10h], r14
0x1800f7a80  movups  xmm0, [rbp+40h+var_88]
0x1800f7a84  movdqu  xmmword ptr [r8+18h], xmm0
0x1800f7a8a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800f7a91  lea     rax, ??_7?$variadic_delegate@V_lambda_08ecad9fd8630207e1b35e495c4301ae_@@XVApxService@implementation@Devices@Media@WindowsUdk@winrt@@UStreamDeletedEventArgs@34567@@impl@winrt@@6B@; const winrt::impl::variadic_delegate<_lambda_08ecad9fd8630207e1b35e495c4301ae_,void,winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::StreamDeletedEventArgs>::`vftable'
0x1800f7a98  mov     [r8], rax
0x1800f7a9b  mov     [rsp+140h+var_110], r8
0x1800f7aa0  mov     rax, [rdi]
0x1800f7aa3  mov     [rsp+140h+var_108], rax
0x1800f7aa8  mov     [rbp+40h+var_68], rbx
0x1800f7aac  mov     rcx, rbx; this
0x1800f7aaf  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800f7ab4  nop
0x1800f7ab5  lea     rcx, [rbx+0F0h]
0x1800f7abc  lea     r8, [rsp+140h+var_108]
0x1800f7ac1  lea     rdx, [rbp+40h+var_90]
0x1800f7ac5  call    ??$_Try_emplace@AEBQEAUAPXJACK__@@$$V@?$map@PEAUAPXJACK__@@U?$delegate@$$A6A_NVApxService@implementation@Devices@Media@WindowsUdk@winrt@@URetrieveJackPresenceStateEventArgs@23456@@Z@winrt@@U?$less@PEAUAPXJACK__@@@std@@V?$allocator@U?$pair@QEAUAPXJACK__@@U?$delegate@$$A6A_NVApxService@implementation@Devices@Media@WindowsUdk@winrt@@URetrieveJackPresenceStateEventArgs@23456@@Z@winrt@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAUAPXJACK__@@U?$delegate@$$A6A_NVApxService@implementation@Devices@Media@WindowsUdk@winrt@@URetrieveJackPresenceStateEventArgs@23456@@Z@winrt@@@std@@PEAX@std@@_N@1@AEBQEAUAPXJACK__@@@Z; std::map<APXJACK__ *,winrt::delegate<bool (winrt::WindowsUdk::Media::Devices::implementation::ApxService,winrt::WindowsUdk::Media::Devices::implementation::RetrieveJackPresenceStateEventArgs)>>::_Try_emplace<APXJACK__ * const &,>(APXJACK__ * const &)
0x1800f7aca  mov     rcx, [rax]
0x1800f7acd  add     rcx, 28h ; '('
0x1800f7ad1  lea     rdx, [rsp+140h+var_110]
0x1800f7ad6  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x1800f7adb  nop
0x1800f7adc  mov     rcx, rbx; _Mtx_t
0x1800f7adf  call    cs:__imp__Mtx_unlock
0x1800f7ae5  nop
0x1800f7ae6  lea     rcx, [rsp+140h+var_110]; this
0x1800f7aeb  call    ??1ISnapLayoutManagerExtension@PlatformExtensions@Shell@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Shell::PlatformExtensions::ISnapLayoutManagerExtension::~ISnapLayoutManagerExtension(void)
0x1800f7af0  nop
0x1800f7af1  mov     rcx, [rbp-30h]; this
0x1800f7af5  test    rcx, rcx
0x1800f7af8  jz      short loc_1800F7AFF
0x1800f7afa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f7aff  mov     r9d, 1
0x1800f7b05  mov     r8, rsi
0x1800f7b08  mov     rdx, [r14+0E0h]
0x1800f7b0f  xor     ecx, ecx
0x1800f7b11  call    cs:__imp_imp_ApxCircuitAddPins
0x1800f7b17  mov     rcx, [rbp+48h]; this
0x1800f7b1b  lea     rdx, aApxcircuitaddp; "ApxCircuitAddPins failed"
0x1800f7b22  mov     qword ptr [rsp+140h+var_120], rdx; int
0x1800f7b27  mov     r9d, eax; char *
0x1800f7b2a  mov     r8, r15; unsigned int
0x1800f7b2d  mov     edx, 245h; void *
0x1800f7b32  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f7b37  mov     [rsi], r13
0x1800f7b3a  mov     rcx, [rbp+40h+var_30]
0x1800f7b3e  xor     rcx, rsp; StackCookie
0x1800f7b41  call    __security_check_cookie
0x1800f7b46  lea     r11, [rsp+140h+var_20]
0x1800f7b4e  mov     rbx, [r11+38h]
0x1800f7b52  mov     rsi, [r11+40h]
0x1800f7b56  mov     rsp, r11
0x1800f7b59  pop     r15
0x1800f7b5b  pop     r14
0x1800f7b5d  pop     r13
0x1800f7b5f  pop     rdi
0x1800f7b60  pop     rbp
0x1800f7b61  retn
```
