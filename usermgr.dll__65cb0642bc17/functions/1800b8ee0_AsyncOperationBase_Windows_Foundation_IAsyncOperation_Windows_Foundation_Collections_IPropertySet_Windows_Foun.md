# AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(void)

- ea: `0x1800b8ee0`
- end: `0x1800b903c`
- name: `??0?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@QEAA@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b8c84`

## callees

- `0x18000d268`
- `0x18005324c`
- `0x1800b8ee0`
- `0x1800b9044`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800b8fbe`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800b8fbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800b8fd2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800b8ff2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800b8fd2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800b8ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9004`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
        __int64 a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rdi
  HANDLE Event; // rax
  HANDLE v5; // rax
  signed int LastError; // eax

  Windows::Foundation::IAsyncOperation<Windows::System::User *>::IAsyncOperation<Windows::System::User *>();
  v3 = (_QWORD *)(v2 + 16);
  Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>(v2 + 16);
  *(_QWORD *)(a1 + 168) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>>::`vftable';
  *(_QWORD *)(a1 + 8) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'};
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  *(_QWORD *)(a1 + 8) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'};
  *v3 = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>>>'};
  *(_DWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 200));
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  *(_QWORD *)(a1 + 184) = Event;
  if ( !Event || (v5 = CreateEventExW(0, 0, 1u, 0x1F0003u), (*(_QWORD *)(a1 + 192) = v5) == 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2147418113;
    }
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::ValidateCredentialsResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      v3,
      (unsigned int)LastError);
  }
  return a1;
}

```

## disassembly

```asm
0x1800b8ee0  mov     [rsp+arg_8], rbx
0x1800b8ee5  mov     [rsp+arg_0], rcx
0x1800b8eea  push    rdi
0x1800b8eeb  sub     rsp, 20h
0x1800b8eef  mov     rbx, rcx
0x1800b8ef2  call    ??0?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@QEAA@XZ; Windows::Foundation::IAsyncOperation<Windows::System::User *>::IAsyncOperation<Windows::System::User *>(void)
0x1800b8ef7  lea     rdi, [rcx+10h]
0x1800b8efb  mov     rcx, rdi
0x1800b8efe  call    ??0?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@QEAA@XZ; Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>(void)
0x1800b8f03  mov     qword ptr [rbx+0A8h], 1
0x1800b8f0e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>>::`vftable'
0x1800b8f15  mov     [rbx], rax
0x1800b8f18  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6BIWeakReferenceSource@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'}
0x1800b8f1f  mov     [rbx+8], rax
0x1800b8f23  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800b8f2a  mov     [rdi], rax
0x1800b8f2d  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800b8f34  mov     [rbx+60h], rax
0x1800b8f38  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800b8f3f  mov     [rbx+88h], rax
0x1800b8f46  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800b8f4d  test    rcx, rcx
0x1800b8f50  jz      short loc_1800B8F5F
0x1800b8f52  mov     rax, [rcx]
0x1800b8f55  mov     rax, [rax+8]
0x1800b8f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8f5e  nop
0x1800b8f5f  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x1800b8f66  mov     [rbx], rax
0x1800b8f69  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6BIWeakReferenceSource@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'}
0x1800b8f70  mov     [rbx+8], rax
0x1800b8f74  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800b8f7b  mov     [rdi], rax
0x1800b8f7e  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800b8f85  mov     [rbx+60h], rax
0x1800b8f89  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IPropertySet *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IPropertySet *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800b8f90  mov     [rbx+88h], rax
0x1800b8f97  mov     dword ptr [rbx+0B0h], 0
0x1800b8fa1  mov     qword ptr [rbx+0B8h], 0
0x1800b8fac  mov     qword ptr [rbx+0C0h], 0
0x1800b8fb7  lea     rcx, [rbx+0C8h]; SRWLock
0x1800b8fbe  call    cs:__imp_InitializeSRWLock
0x1800b8fc4  xor     edx, edx; lpName
0x1800b8fc6  xor     ecx, ecx; lpEventAttributes
0x1800b8fc8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800b8fce  lea     r8d, [rdx+1]; dwFlags
0x1800b8fd2  call    cs:__imp_CreateEventExW
0x1800b8fd8  mov     [rbx+0B8h], rax
0x1800b8fdf  test    rax, rax
0x1800b8fe2  jz      short loc_1800B9004
0x1800b8fe4  xor     edx, edx; lpName
0x1800b8fe6  xor     ecx, ecx; lpEventAttributes
0x1800b8fe8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800b8fee  lea     r8d, [rdx+1]; dwFlags
0x1800b8ff2  call    cs:__imp_CreateEventExW
0x1800b8ff8  mov     [rbx+0C0h], rax
0x1800b8fff  test    rax, rax
0x1800b9002  jnz     short loc_1800B902E
0x1800b9004  call    cs:__imp_GetLastError
0x1800b900a  test    eax, eax
0x1800b900c  jnz     short loc_1800B9015
0x1800b900e  mov     eax, 8000FFFFh
0x1800b9013  jmp     short loc_1800B9023
0x1800b9015  jle     short loc_1800B901F
0x1800b9017  movzx   eax, ax
0x1800b901a  or      eax, 80070000h
0x1800b901f  test    eax, eax
0x1800b9021  jns     short loc_1800B902E
0x1800b9023  mov     edx, eax
0x1800b9025  mov     rcx, rdi
0x1800b9028  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVValidateCredentialsResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::ValidateCredentialsResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800b902d  nop
0x1800b902e  mov     rax, rbx
0x1800b9031  mov     rbx, [rsp+28h+arg_8]
0x1800b9036  add     rsp, 20h
0x1800b903a  pop     rdi
0x1800b903b  retn
```
