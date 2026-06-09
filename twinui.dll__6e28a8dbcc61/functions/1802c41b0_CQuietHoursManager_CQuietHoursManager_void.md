# CQuietHoursManager::~CQuietHoursManager(void)

- ea: `0x1802c41b0`
- end: `0x1802c42a6`
- name: `??1CQuietHoursManager@@EEAA@XZ`
- size: `246`
- prototype: `void __fastcall(CQuietHoursManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802c4310`

## callees

- `0x1802c4184`
- `0x1802c41b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802c420b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802c422f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802c4253`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802c427c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802c420b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802c422f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802c4253`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802c427c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802c4218`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802c423c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802c4260`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802c4289`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802c4218`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802c423c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802c4260`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802c4289`

## pseudocode

```c
void __fastcall CQuietHoursManager::~CQuietHoursManager(CQuietHoursManager *this)
{
  struct _TP_TIMER *v2; // rcx
  struct _TP_TIMER *v3; // rcx
  struct _TP_TIMER *v4; // rcx

  *(_QWORD *)this = &CQuietHoursManager::`vftable'{for `Microsoft::WRL::Details::Selector<CImmersiveShellComponentWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 5) = &CQuietHoursManager::`vftable'{for `IImmersiveShellComponent'};
  *((_QWORD *)this + 6) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CImmersiveShellComponentWithGITSite,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider>'};
  *((_QWORD *)this + 13) = &CQuietHoursManager::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 14) = &CQuietHoursManager::`vftable'{for `IImmersiveWindowMessageNotification'};
  *((_QWORD *)this + 15) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CImmersiveShellComponentWithGITSite,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 25);
  if ( v2 )
  {
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 25));
  }
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 26);
  if ( v3 )
  {
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 26));
  }
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 27);
  if ( v4 )
  {
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 27));
  }
  if ( *((_QWORD *)this + 27) )
  {
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 28), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 28));
  }
  *((_DWORD *)this + 39) = -1073741823;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1802c41b0  push    rbx
0x1802c41b2  sub     rsp, 20h
0x1802c41b6  lea     rax, ??_7CQuietHoursManager@@6B?$Selector@VCImmersiveShellComponentWithGITSite@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const CQuietHoursManager::`vftable'{for `Microsoft::WRL::Details::Selector<CImmersiveShellComponentWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>'}
0x1802c41bd  mov     rbx, rcx
0x1802c41c0  mov     [rcx], rax
0x1802c41c3  lea     rax, ??_7CQuietHoursManager@@6BIImmersiveShellComponent@@@; const CQuietHoursManager::`vftable'{for `IImmersiveShellComponent'}
0x1802c41ca  mov     [rcx+28h], rax
0x1802c41ce  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCImmersiveShellComponentWithGITSite@@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIServiceProvider@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CImmersiveShellComponentWithGITSite,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IServiceProvider>'}
0x1802c41d5  mov     [rcx+30h], rax
0x1802c41d9  lea     rax, ??_7CQuietHoursManager@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const CQuietHoursManager::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>'}
0x1802c41e0  mov     [rcx+68h], rax
0x1802c41e4  lea     rax, ??_7CQuietHoursManager@@6BIImmersiveWindowMessageNotification@@@; const CQuietHoursManager::`vftable'{for `IImmersiveWindowMessageNotification'}
0x1802c41eb  mov     [rcx+70h], rax
0x1802c41ef  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VCImmersiveShellComponentWithGITSite@@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,CImmersiveShellComponentWithGITSite,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1802c41f6  mov     [rcx+78h], rax
0x1802c41fa  mov     rcx, [rcx+0C8h]; pti
0x1802c4201  test    rcx, rcx
0x1802c4204  jz      short loc_1802C421E
0x1802c4206  mov     edx, 1; fCancelPendingCallbacks
0x1802c420b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802c4211  mov     rcx, [rbx+0C8h]; pti
0x1802c4218  call    cs:__imp_CloseThreadpoolTimer
0x1802c421e  mov     rcx, [rbx+0D0h]; pti
0x1802c4225  test    rcx, rcx
0x1802c4228  jz      short loc_1802C4242
0x1802c422a  mov     edx, 1; fCancelPendingCallbacks
0x1802c422f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802c4235  mov     rcx, [rbx+0D0h]; pti
0x1802c423c  call    cs:__imp_CloseThreadpoolTimer
0x1802c4242  mov     rcx, [rbx+0D8h]; pti
0x1802c4249  test    rcx, rcx
0x1802c424c  jz      short loc_1802C4266
0x1802c424e  mov     edx, 1; fCancelPendingCallbacks
0x1802c4253  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802c4259  mov     rcx, [rbx+0D8h]; pti
0x1802c4260  call    cs:__imp_CloseThreadpoolTimer
0x1802c4266  cmp     qword ptr [rbx+0D8h], 0
0x1802c426e  jz      short loc_1802C428F
0x1802c4270  mov     rcx, [rbx+0E0h]; pti
0x1802c4277  mov     edx, 1; fCancelPendingCallbacks
0x1802c427c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802c4282  mov     rcx, [rbx+0E0h]; pti
0x1802c4289  call    cs:__imp_CloseThreadpoolTimer
0x1802c428f  mov     rcx, rbx; this
0x1802c4292  mov     dword ptr [rbx+9Ch], 0C0000001h
0x1802c429c  add     rsp, 20h
0x1802c42a0  pop     rbx
0x1802c42a1  jmp     ??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCImmersiveShellComponentWithGITSite@@@Details@23@UIQuietHoursPolicy@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CImmersiveShellComponentWithGITSite>,IQuietHoursPolicy,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>(void)
```
