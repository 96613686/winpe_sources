# COplockProvider::~COplockProvider(void)

- ea: `0x18003ef2c`
- end: `0x18003f048`
- name: `??1COplockProvider@@EEAA@XZ`
- size: `284`
- prototype: `void __fastcall(COplockProvider *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003eef0`

## callees

- `0x18000ddd4`
- `0x18001e800`
- `0x1800259e8`
- `0x18002630c`
- `0x180026cb4`
- `0x18003ef2c`
- `0x18003f05c`
- `0x18003f078`
- `0x18003f120`
- `0x18003f958`
- `0x180045e44`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003f017`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003f017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f001`

## pseudocode

```c
void __fastcall COplockProvider::~COplockProvider(COplockProvider *this)
{
  char *v2; // r14
  PTP_WAIT *v3; // rdi
  struct _TP_TIMER *v4; // rcx
  struct _TP_TIMER *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  int v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  COplockProvider *v12; // [rsp+68h] [rbp+20h] BYREF

  *(_QWORD *)this = &COplockProvider::`vftable'{for `IOplockProvider'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IOplockProvider,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v10 = *((_QWORD *)this + 7);
  v2 = (char *)this + 216;
  v11 = *((_QWORD *)this + 27);
  v9 = *((_DWORD *)this + 62);
  v12 = this;
  SHCoreOplockTelemetry::COplockProviderDestroy<COplockProvider *,int,IWeakReference *,void *>(&v12, &v9, &v11, &v10);
  COplockProvider::RelinquishOplock(this);
  v3 = (PTP_WAIT *)((char *)this + 64);
  if ( *((_QWORD *)this + 8) )
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<2>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      (char *)this + 64,
      0);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 312);
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 35);
  if ( v4 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 34);
  if ( v5 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v5);
  v6 = (void *)*((_QWORD *)this + 33);
  if ( v6 )
    tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(v6);
  v7 = (void *)*((_QWORD *)this + 32);
  if ( v7 )
    tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::Release(v7);
  v8 = (void *)*((_QWORD *)this + 30);
  if ( v8 )
    CoTaskMemFree(v8);
  wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::~com_ptr_t<IWeakReference,wil::err_returncode_policy>(v2);
  if ( *v3 )
    CloseThreadpoolWait(*v3);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 56);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 48);
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x18003ef2c  mov     r11, rsp
0x18003ef2f  push    rbx
0x18003ef30  push    rsi
0x18003ef31  push    rdi
0x18003ef32  push    r14
0x18003ef34  sub     rsp, 28h
0x18003ef38  mov     rbx, rcx
0x18003ef3b  lea     rax, ??_7COplockProvider@@6BIOplockProvider@@@; const COplockProvider::`vftable'{for `IOplockProvider'}
0x18003ef42  mov     [rcx], rax
0x18003ef45  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIOplockProvider@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IOplockProvider,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003ef4c  mov     [rcx+8], rax
0x18003ef50  mov     rax, [rcx+38h]
0x18003ef54  mov     [r11+10h], rax
0x18003ef58  lea     r14, [rcx+0D8h]
0x18003ef5f  mov     rax, [r14]
0x18003ef62  mov     [r11+18h], rax
0x18003ef66  mov     eax, [rcx+0F8h]
0x18003ef6c  mov     [rsp+48h+arg_0], eax
0x18003ef70  mov     [r11+20h], rcx
0x18003ef74  lea     r9, [r11+10h]
0x18003ef78  lea     r8, [r11+18h]
0x18003ef7c  lea     rdx, [r11+8]
0x18003ef80  lea     rcx, [r11+20h]
0x18003ef84  call    ??$COplockProviderDestroy@PEAVCOplockProvider@@HPEAUIWeakReference@@PEAX@SHCoreOplockTelemetry@@SAX$$QEAPEAVCOplockProvider@@$$QEAH$$QEAPEAUIWeakReference@@$$QEAPEAX@Z; SHCoreOplockTelemetry::COplockProviderDestroy<COplockProvider *,int,IWeakReference *,void *>(COplockProvider * &&,int &&,IWeakReference * &&,void * &&)
0x18003ef89  mov     rcx, rbx; this
0x18003ef8c  call    ?RelinquishOplock@COplockProvider@@UEAAJXZ; COplockProvider::RelinquishOplock(void)
0x18003ef91  lea     rdi, [rbx+40h]
0x18003ef95  cmp     qword ptr [rdi], 0
0x18003ef99  jz      short loc_18003EFA5
0x18003ef9b  xor     edx, edx
0x18003ef9d  mov     rcx, rdi
0x18003efa0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<2>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18003efa5  lea     rcx, [rbx+138h]
0x18003efac  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003efb1  mov     rcx, [rbx+118h]; pti
0x18003efb8  test    rcx, rcx
0x18003efbb  jz      short loc_18003EFC2
0x18003efbd  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18003efc2  mov     rcx, [rbx+110h]; pti
0x18003efc9  test    rcx, rcx
0x18003efcc  jz      short loc_18003EFD3
0x18003efce  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18003efd3  mov     rcx, [rbx+108h]; pv
0x18003efda  test    rcx, rcx
0x18003efdd  jz      short loc_18003EFE4
0x18003efdf  call    ?Release@?$merged_data@U_tip_RequestOplockTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_RequestOplockTipTest,OplockTipTests::_tip_RequestOplockTipTest>::Release(void)
0x18003efe4  mov     rcx, [rbx+100h]; pv
0x18003efeb  test    rcx, rcx
0x18003efee  jz      short loc_18003EFF5
0x18003eff0  call    ?Release@?$merged_data@U_tip_OplockBrokenCallbackTipTest@OplockTipTests@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<OplockTipTests::_tip_OplockBrokenCallbackTipTest,OplockTipTests::_tip_OplockBrokenCallbackTipTest>::Release(void)
0x18003eff5  mov     rcx, [rbx+0F0h]; pv
0x18003effc  test    rcx, rcx
0x18003efff  jz      short loc_18003F007
0x18003f001  call    cs:__imp_CoTaskMemFree
0x18003f007  mov     rcx, r14
0x18003f00a  call    ??1?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>::~com_ptr_t<IWeakReference,wil::err_returncode_policy>(void)
0x18003f00f  mov     rcx, [rdi]; pwa
0x18003f012  test    rcx, rcx
0x18003f015  jz      short loc_18003F01D
0x18003f017  call    cs:__imp_CloseThreadpoolWait
0x18003f01d  lea     rcx, [rbx+38h]
0x18003f021  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003f026  lea     rcx, [rbx+30h]
0x18003f02a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f02f  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18003f036  lea     rcx, [rbx+20h]
0x18003f03a  add     rsp, 28h
0x18003f03e  pop     r14
0x18003f040  pop     rdi
0x18003f041  pop     rsi
0x18003f042  pop     rbx
0x18003f043  jmp     ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
```
