# AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(void)

- ea: `0x1800ca850`
- end: `0x1800ca9ac`
- name: `??0?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@QEAA@XZ`
- size: `348`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180086a7c`

## callees

- `0x18000d268`
- `0x18005324c`
- `0x1800ca850`
- `0x1800ca9b4`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800ca92e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800ca92e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ca942`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ca962`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ca942`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ca962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ca974`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
        __int64 a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rdi
  HANDLE Event; // rax
  HANDLE v5; // rax
  signed int LastError; // eax

  Windows::Foundation::IAsyncOperation<Windows::System::User *>::IAsyncOperation<Windows::System::User *>();
  v3 = (_QWORD *)(v2 + 16);
  Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>(v2 + 16);
  *(_QWORD *)(a1 + 168) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `IWeakReferenceSource'};
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `IWeakReferenceSource'};
  *v3 = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>>'};
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
0x1800ca850  mov     [rsp+arg_8], rbx
0x1800ca855  mov     [rsp+arg_0], rcx
0x1800ca85a  push    rdi
0x1800ca85b  sub     rsp, 20h
0x1800ca85f  mov     rbx, rcx
0x1800ca862  call    ??0?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@QEAA@XZ; Windows::Foundation::IAsyncOperation<Windows::System::User *>::IAsyncOperation<Windows::System::User *>(void)
0x1800ca867  lea     rdi, [rcx+10h]
0x1800ca86b  mov     rcx, rdi
0x1800ca86e  call    ??0?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@QEAA@XZ; Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>(void)
0x1800ca873  mov     qword ptr [rbx+0A8h], 1
0x1800ca87e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'
0x1800ca885  mov     [rbx], rax
0x1800ca888  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `IWeakReferenceSource'}
0x1800ca88f  mov     [rbx+8], rax
0x1800ca893  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800ca89a  mov     [rdi], rax
0x1800ca89d  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800ca8a4  mov     [rbx+60h], rax
0x1800ca8a8  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800ca8af  mov     [rbx+88h], rax
0x1800ca8b6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800ca8bd  test    rcx, rcx
0x1800ca8c0  jz      short loc_1800CA8CF
0x1800ca8c2  mov     rax, [rcx]
0x1800ca8c5  mov     rax, [rax+8]
0x1800ca8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca8ce  nop
0x1800ca8cf  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x1800ca8d6  mov     [rbx], rax
0x1800ca8d9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `IWeakReferenceSource'}
0x1800ca8e0  mov     [rbx+8], rax
0x1800ca8e4  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800ca8eb  mov     [rdi], rax
0x1800ca8ee  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800ca8f5  mov     [rbx+60h], rax
0x1800ca8f9  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSetPictureResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SetPictureResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SetPictureResult *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800ca900  mov     [rbx+88h], rax
0x1800ca907  mov     dword ptr [rbx+0B0h], 0
0x1800ca911  mov     qword ptr [rbx+0B8h], 0
0x1800ca91c  mov     qword ptr [rbx+0C0h], 0
0x1800ca927  lea     rcx, [rbx+0C8h]; SRWLock
0x1800ca92e  call    cs:__imp_InitializeSRWLock
0x1800ca934  xor     edx, edx; lpName
0x1800ca936  xor     ecx, ecx; lpEventAttributes
0x1800ca938  mov     r9d, 1F0003h; dwDesiredAccess
0x1800ca93e  lea     r8d, [rdx+1]; dwFlags
0x1800ca942  call    cs:__imp_CreateEventExW
0x1800ca948  mov     [rbx+0B8h], rax
0x1800ca94f  test    rax, rax
0x1800ca952  jz      short loc_1800CA974
0x1800ca954  xor     edx, edx; lpName
0x1800ca956  xor     ecx, ecx; lpEventAttributes
0x1800ca958  mov     r9d, 1F0003h; dwDesiredAccess
0x1800ca95e  lea     r8d, [rdx+1]; dwFlags
0x1800ca962  call    cs:__imp_CreateEventExW
0x1800ca968  mov     [rbx+0C0h], rax
0x1800ca96f  test    rax, rax
0x1800ca972  jnz     short loc_1800CA99E
0x1800ca974  call    cs:__imp_GetLastError
0x1800ca97a  test    eax, eax
0x1800ca97c  jnz     short loc_1800CA985
0x1800ca97e  mov     eax, 8000FFFFh
0x1800ca983  jmp     short loc_1800CA993
0x1800ca985  jle     short loc_1800CA98F
0x1800ca987  movzx   eax, ax
0x1800ca98a  or      eax, 80070000h
0x1800ca98f  test    eax, eax
0x1800ca991  jns     short loc_1800CA99E
0x1800ca993  mov     edx, eax
0x1800ca995  mov     rcx, rdi
0x1800ca998  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVValidateCredentialsResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::ValidateCredentialsResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800ca99d  nop
0x1800ca99e  mov     rax, rbx
0x1800ca9a1  mov     rbx, [rsp+28h+arg_8]
0x1800ca9a6  add     rsp, 20h
0x1800ca9aa  pop     rdi
0x1800ca9ab  retn
```
