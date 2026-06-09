# CAudioOrchestrator::~CAudioOrchestrator(void)

- ea: `0x1800a9310`
- end: `0x1800a9522`
- name: `??1CAudioOrchestrator@@UEAA@XZ`
- size: `530`
- prototype: `void __fastcall(CAudioOrchestrator *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180082a14`
- `0x180083944`
- `0x1800872e0`

## callees

- `0x18000a590`
- `0x18000bea0`
- `0x18000bec4`
- `0x180021944`
- `0x180029860`
- `0x180046b0c`
- `0x180046e6c`
- `0x18004d6e8`
- `0x1800a9528`
- `0x1800cfc5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a9501`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a950e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a9501`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a950e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a949f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a94ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9485`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a9492`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a949f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a94ac`

## pseudocode

```c
void __fastcall CAudioOrchestrator::~CAudioOrchestrator(CAudioOrchestrator *this)
{
  std::wstring::_Tidy_deallocate((char *)this + 1616);
  *((_QWORD *)this + 194) = &RenderStateNotificationProxy::`vftable';
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 1536);
  *((_QWORD *)this + 181) = &PDCActivation::`vftable';
  *((_QWORD *)this + 156) = &PowerNotificationProxy::`vftable';
  *((_QWORD *)this + 165) = &PowerSettingMock::`vftable';
  AudioPipeMessage::~AudioPipeMessage((CAudioOrchestrator *)((char *)this + 1344));
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 1224);
  ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>((char *)this + 1112);
  ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>((char *)this + 1104);
  ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>((char *)this + 1096);
  ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>((char *)this + 1088);
  ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>((char *)this + 1080);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 1048);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 1032);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 1024);
  SPPIPEINFO::~SPPIPEINFO((CAudioOrchestrator *)((char *)this + 840));
  SysVadAudioControl::~SysVadAudioControl((CAudioOrchestrator *)((char *)this + 792));
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 712);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 704);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 696);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 688);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 680);
  CAudioOrchestratorInput::~CAudioOrchestratorInput((CAudioOrchestrator *)((char *)this + 600));
  SysVadAudioControl::~SysVadAudioControl((CAudioOrchestrator *)((char *)this + 584));
  SysVadAudioControl::~SysVadAudioControl((CAudioOrchestrator *)((char *)this + 568));
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 552);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 536);
  CoTaskMemFree(*((LPVOID *)this + 58));
  CoTaskMemFree(*((LPVOID *)this + 54));
  CoTaskMemFree(*((LPVOID *)this + 50));
  CoTaskMemFree(*((LPVOID *)this + 46));
  CoTaskMemFree(*((LPVOID *)this + 42));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 296);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 280);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 272);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 256);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 248);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>((char *)this + 240);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 104);
}

```

## disassembly

```asm
0x1800a9310  push    rbx
0x1800a9312  sub     rsp, 20h
0x1800a9316  mov     rbx, rcx
0x1800a9319  add     rcx, 650h
0x1800a9320  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a9325  lea     rax, ??_7RenderStateNotificationProxy@@6B@; const RenderStateNotificationProxy::`vftable'
0x1800a932c  lea     rcx, [rbx+600h]
0x1800a9333  mov     [rbx+610h], rax
0x1800a933a  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a933f  lea     rax, ??_7PDCActivation@@6B@; const PDCActivation::`vftable'
0x1800a9346  mov     [rbx+5A8h], rax
0x1800a934d  lea     rcx, [rbx+540h]; this
0x1800a9354  lea     rax, ??_7PowerNotificationProxy@@6B@; const PowerNotificationProxy::`vftable'
0x1800a935b  mov     [rbx+4E0h], rax
0x1800a9362  lea     rax, ??_7PowerSettingMock@@6B@; const PowerSettingMock::`vftable'
0x1800a9369  mov     [rbx+528h], rax
0x1800a9370  call    ??1AudioPipeMessage@@UEAA@XZ; AudioPipeMessage::~AudioPipeMessage(void)
0x1800a9375  lea     rcx, [rbx+4C8h]
0x1800a937c  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a9381  lea     rcx, [rbx+458h]
0x1800a9388  call    ??1?$CComPtrBase@VCRecoMaster@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>(void)
0x1800a938d  lea     rcx, [rbx+450h]
0x1800a9394  call    ??1?$CComPtrBase@VCRecoMaster@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>(void)
0x1800a9399  lea     rcx, [rbx+448h]
0x1800a93a0  call    ??1?$CComPtrBase@VCRecoMaster@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>(void)
0x1800a93a5  lea     rcx, [rbx+440h]
0x1800a93ac  call    ??1?$CComPtrBase@VCRecoMaster@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>(void)
0x1800a93b1  lea     rcx, [rbx+438h]
0x1800a93b8  call    ??1?$CComPtrBase@VCRecoMaster@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CRecoMaster>::~CComPtrBase<CRecoMaster>(void)
0x1800a93bd  lea     rcx, [rbx+418h]
0x1800a93c4  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a93c9  lea     rcx, [rbx+408h]
0x1800a93d0  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a93d5  lea     rcx, [rbx+400h]
0x1800a93dc  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a93e1  lea     rcx, [rbx+348h]; this
0x1800a93e8  call    ??1SPPIPEINFO@@QEAA@XZ; SPPIPEINFO::~SPPIPEINFO(void)
0x1800a93ed  lea     rcx, [rbx+318h]; this
0x1800a93f4  call    ??1SysVadAudioControl@@UEAA@XZ; SysVadAudioControl::~SysVadAudioControl(void)
0x1800a93f9  lea     rcx, [rbx+2C8h]
0x1800a9400  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800a9405  lea     rcx, [rbx+2C0h]
0x1800a940c  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800a9411  lea     rcx, [rbx+2B8h]
0x1800a9418  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800a941d  lea     rcx, [rbx+2B0h]
0x1800a9424  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800a9429  lea     rcx, [rbx+2A8h]
0x1800a9430  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800a9435  lea     rcx, [rbx+258h]; this
0x1800a943c  call    ??1CAudioOrchestratorInput@@UEAA@XZ; CAudioOrchestratorInput::~CAudioOrchestratorInput(void)
0x1800a9441  lea     rcx, [rbx+248h]; this
0x1800a9448  call    ??1SysVadAudioControl@@UEAA@XZ; SysVadAudioControl::~SysVadAudioControl(void)
0x1800a944d  lea     rcx, [rbx+238h]; this
0x1800a9454  call    ??1SysVadAudioControl@@UEAA@XZ; SysVadAudioControl::~SysVadAudioControl(void)
0x1800a9459  lea     rcx, [rbx+228h]
0x1800a9460  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a9465  lea     rcx, [rbx+218h]
0x1800a946c  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a9471  mov     rcx, [rbx+1D0h]; pv
0x1800a9478  call    cs:__imp_CoTaskMemFree
0x1800a947e  mov     rcx, [rbx+1B0h]; pv
0x1800a9485  call    cs:__imp_CoTaskMemFree
0x1800a948b  mov     rcx, [rbx+190h]; pv
0x1800a9492  call    cs:__imp_CoTaskMemFree
0x1800a9498  mov     rcx, [rbx+170h]; pv
0x1800a949f  call    cs:__imp_CoTaskMemFree
0x1800a94a5  mov     rcx, [rbx+150h]; pv
0x1800a94ac  call    cs:__imp_CoTaskMemFree
0x1800a94b2  lea     rcx, [rbx+128h]
0x1800a94b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a94be  lea     rcx, [rbx+118h]
0x1800a94c5  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a94ca  lea     rcx, [rbx+110h]
0x1800a94d1  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a94d6  lea     rcx, [rbx+100h]
0x1800a94dd  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a94e2  lea     rcx, [rbx+0F8h]
0x1800a94e9  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a94ee  lea     rcx, [rbx+0F0h]
0x1800a94f5  call    ??1?$CComPtrBase@UISpLexicon2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(void)
0x1800a94fa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800a9501  call    cs:__imp_DeleteCriticalSection
0x1800a9507  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800a950e  call    cs:__imp_DeleteCriticalSection
0x1800a9514  lea     rcx, [rbx+68h]
0x1800a9518  add     rsp, 20h
0x1800a951c  pop     rbx
0x1800a951d  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
