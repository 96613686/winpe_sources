# AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(void)

- ea: `0x1800c4dc4`
- end: `0x1800c4f20`
- name: `??0?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@QEAA@XZ`
- size: `348`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180086818`

## callees

- `0x18000d268`
- `0x18005324c`
- `0x1800c4dc4`
- `0x1800c4f28`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800c4ea2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800c4ea2`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c4eb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c4ed6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c4eb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c4ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4ee8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
        __int64 a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rdi
  HANDLE Event; // rax
  HANDLE v5; // rax
  signed int LastError; // eax

  Windows::Foundation::IAsyncOperation<Windows::System::User *>::IAsyncOperation<Windows::System::User *>();
  v3 = (_QWORD *)(v2 + 16);
  Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>(v2 + 16);
  *(_QWORD *)(a1 + 168) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>>::`vftable';
  *(_QWORD *)(a1 + 8) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'};
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  *(_QWORD *)(a1 + 8) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'};
  *v3 = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>>>'};
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
0x1800c4dc4  mov     [rsp+arg_8], rbx
0x1800c4dc9  mov     [rsp+arg_0], rcx
0x1800c4dce  push    rdi
0x1800c4dcf  sub     rsp, 20h
0x1800c4dd3  mov     rbx, rcx
0x1800c4dd6  call    ??0?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@QEAA@XZ; Windows::Foundation::IAsyncOperation<Windows::System::User *>::IAsyncOperation<Windows::System::User *>(void)
0x1800c4ddb  lea     rdi, [rcx+10h]
0x1800c4ddf  mov     rcx, rdi
0x1800c4de2  call    ??0?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@QEAA@XZ; Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>(void)
0x1800c4de7  mov     qword ptr [rbx+0A8h], 1
0x1800c4df2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'
0x1800c4df9  mov     [rbx], rax
0x1800c4dfc  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6BIWeakReferenceSource@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'}
0x1800c4e03  mov     [rbx+8], rax
0x1800c4e07  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800c4e0e  mov     [rdi], rax
0x1800c4e11  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800c4e18  mov     [rbx+60h], rax
0x1800c4e1c  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800c4e23  mov     [rbx+88h], rax
0x1800c4e2a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800c4e31  test    rcx, rcx
0x1800c4e34  jz      short loc_1800C4E43
0x1800c4e36  mov     rax, [rcx]
0x1800c4e39  mov     rax, [rax+8]
0x1800c4e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4e42  nop
0x1800c4e43  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x1800c4e4a  mov     [rbx], rax
0x1800c4e4d  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6BIWeakReferenceSource@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'}
0x1800c4e54  mov     [rbx+8], rax
0x1800c4e58  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800c4e5f  mov     [rdi], rax
0x1800c4e62  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800c4e69  mov     [rbx+60h], rax
0x1800c4e6d  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetUserAutologonResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetUserAutologonResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetUserAutologonResult *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800c4e74  mov     [rbx+88h], rax
0x1800c4e7b  mov     dword ptr [rbx+0B0h], 0
0x1800c4e85  mov     qword ptr [rbx+0B8h], 0
0x1800c4e90  mov     qword ptr [rbx+0C0h], 0
0x1800c4e9b  lea     rcx, [rbx+0C8h]; SRWLock
0x1800c4ea2  call    cs:__imp_InitializeSRWLock
0x1800c4ea8  xor     edx, edx; lpName
0x1800c4eaa  xor     ecx, ecx; lpEventAttributes
0x1800c4eac  mov     r9d, 1F0003h; dwDesiredAccess
0x1800c4eb2  lea     r8d, [rdx+1]; dwFlags
0x1800c4eb6  call    cs:__imp_CreateEventExW
0x1800c4ebc  mov     [rbx+0B8h], rax
0x1800c4ec3  test    rax, rax
0x1800c4ec6  jz      short loc_1800C4EE8
0x1800c4ec8  xor     edx, edx; lpName
0x1800c4eca  xor     ecx, ecx; lpEventAttributes
0x1800c4ecc  mov     r9d, 1F0003h; dwDesiredAccess
0x1800c4ed2  lea     r8d, [rdx+1]; dwFlags
0x1800c4ed6  call    cs:__imp_CreateEventExW
0x1800c4edc  mov     [rbx+0C0h], rax
0x1800c4ee3  test    rax, rax
0x1800c4ee6  jnz     short loc_1800C4F12
0x1800c4ee8  call    cs:__imp_GetLastError
0x1800c4eee  test    eax, eax
0x1800c4ef0  jnz     short loc_1800C4EF9
0x1800c4ef2  mov     eax, 8000FFFFh
0x1800c4ef7  jmp     short loc_1800C4F07
0x1800c4ef9  jle     short loc_1800C4F03
0x1800c4efb  movzx   eax, ax
0x1800c4efe  or      eax, 80070000h
0x1800c4f03  test    eax, eax
0x1800c4f05  jns     short loc_1800C4F12
0x1800c4f07  mov     edx, eax
0x1800c4f09  mov     rcx, rdi
0x1800c4f0c  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVValidateCredentialsResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::ValidateCredentialsResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800c4f11  nop
0x1800c4f12  mov     rax, rbx
0x1800c4f15  mov     rbx, [rsp+28h+arg_8]
0x1800c4f1a  add     rsp, 20h
0x1800c4f1e  pop     rdi
0x1800c4f1f  retn
```
