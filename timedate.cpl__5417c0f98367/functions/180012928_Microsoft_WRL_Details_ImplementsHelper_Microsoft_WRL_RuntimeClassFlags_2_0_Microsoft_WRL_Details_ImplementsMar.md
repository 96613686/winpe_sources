# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IShouldSwitchToDesktop,ILayoutPreferencesOnAppLaunch,IExecuteCommandHost,ILocalCopyDownloadSettings,IWakeOnRPCCalls,ILaunchTargetMonitor,IUpdateViewValueSet,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IShouldSwitchToDesktop,ILayoutPreferencesOnAppLaunch,IExecuteCommandHost,ILocalCopyDownloadSettings,IWakeOnRPCCalls,ILaunchTargetMonitor,IUpdateViewValueSet,Microsoft::WRL::FtmBase>(void)

- ea: `0x180012928`
- end: `0x1800129b6`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWRLObjectWithGITSite@@@Details@23@UIServiceProvider@@UIShouldSwitchToDesktop@@UILayoutPreferencesOnAppLaunch@@UIExecuteCommandHost@@UILocalCopyDownloadSettings@@UIWakeOnRPCCalls@@UILaunchTargetMonitor@@UIUpdateViewValueSet@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800129bc`

## callees

- `0x180012928`
- `0x180012a68`
- `0x1800130b4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001296d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001296d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IShouldSwitchToDesktop,ILayoutPreferencesOnAppLaunch,IExecuteCommandHost,ILocalCopyDownloadSettings,IWakeOnRPCCalls,ILaunchTargetMonitor,IUpdateViewValueSet,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IShouldSwitchToDesktop,ILayoutPreferencesOnAppLaunch,IExecuteCommandHost,ILocalCopyDownloadSettings,IWakeOnRPCCalls,ILaunchTargetMonitor,IUpdateViewValueSet,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r14
  LPUNKNOWN v4; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  Microsoft::WRL::Details::Selector<CWRLObjectWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IShouldSwitchToDesktop,ILayoutPreferencesOnAppLaunch,IExecuteCommandHost,ILocalCopyDownloadSettings,IWakeOnRPCCalls,ILaunchTargetMonitor,IUpdateViewValueSet,Microsoft::WRL::FtmBase>>::Selector<CWRLObjectWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IShouldSwitchToDesktop,ILayoutPreferencesOnAppLaunch,IExecuteCommandHost,ILocalCopyDownloadSettings,IWakeOnRPCCalls,ILaunchTargetMonitor,IUpdateViewValueSet,Microsoft::WRL::FtmBase>>();
  v3 = v2 + 128;
  ppunkMarshal = 0;
  *(_QWORD *)(v2 + 104) = &Microsoft::WRL::FtmBase::`vftable';
  *(_QWORD *)(v2 + 128) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v4 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64))QueryInterface)(
      v4,
      &GUID_00000003_0000_0000_c000_000000000046,
      v3);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x180012928  push    rbx
0x18001292a  push    rsi
0x18001292b  push    rdi
0x18001292c  push    r14
0x18001292e  sub     rsp, 28h
0x180012932  mov     rsi, rcx
0x180012935  call    ??0?$Selector@VCWRLObjectWithGITSite@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VCWRLObjectWithGITSite@@@Details@23@UIServiceProvider@@UIShouldSwitchToDesktop@@UILayoutPreferencesOnAppLaunch@@UIExecuteCommandHost@@UILocalCopyDownloadSettings@@UIWakeOnRPCCalls@@UILaunchTargetMonitor@@UIUpdateViewValueSet@@VFtmBase@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::Selector<CWRLObjectWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IShouldSwitchToDesktop,ILayoutPreferencesOnAppLaunch,IExecuteCommandHost,ILocalCopyDownloadSettings,IWakeOnRPCCalls,ILaunchTargetMonitor,IUpdateViewValueSet,Microsoft::WRL::FtmBase>>::Selector<CWRLObjectWithGITSite,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<CWRLObjectWithGITSite>,IServiceProvider,IShouldSwitchToDesktop,ILayoutPreferencesOnAppLaunch,IExecuteCommandHost,ILocalCopyDownloadSettings,IWakeOnRPCCalls,ILaunchTargetMonitor,IUpdateViewValueSet,Microsoft::WRL::FtmBase>>(void)
0x18001293a  lea     r14, [rcx+80h]
0x180012941  mov     [rsp+48h+ppunkMarshal], 0
0x18001294a  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180012951  mov     [rcx+68h], rax
0x180012955  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001295a  mov     qword ptr [r14], 0
0x180012961  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012966  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18001296b  xor     ecx, ecx; punkOuter
0x18001296d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180012973  test    eax, eax
0x180012975  js      short loc_18001299F
0x180012977  mov     rbx, [rsp+48h+ppunkMarshal]
0x18001297c  mov     rcx, r14
0x18001297f  mov     rax, [rbx]
0x180012982  mov     rdi, [rax]
0x180012985  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001298a  mov     r8, r14
0x18001298d  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180012994  mov     rcx, rbx
0x180012997  mov     rax, rdi
0x18001299a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001299f  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800129a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800129a9  mov     rax, rsi
0x1800129ac  add     rsp, 28h
0x1800129b0  pop     r14
0x1800129b2  pop     rdi
0x1800129b3  pop     rsi
0x1800129b4  pop     rbx
0x1800129b5  retn
```
