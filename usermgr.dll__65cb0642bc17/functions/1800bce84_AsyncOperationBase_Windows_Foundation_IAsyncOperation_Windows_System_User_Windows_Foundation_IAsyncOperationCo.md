# AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(void)

- ea: `0x1800bce84`
- end: `0x1800bcfe0`
- name: `??0?$AsyncOperationBase@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@QEAA@XZ`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800865f8`
- `0x1800bd0b0`

## callees

- `0x18000d268`
- `0x18005324c`
- `0x1800bce84`
- `0x1800bcfe8`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800bcf62`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800bcf62`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800bcf76`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800bcf96`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800bcf76`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800bcf96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcfa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcfa8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
        __int64 a1)
{
  __int64 v2; // rcx
  _QWORD *v3; // rdi
  HANDLE Event; // rax
  HANDLE v5; // rax
  signed int LastError; // eax

  Windows::Foundation::IAsyncOperation<Windows::System::User *>::IAsyncOperation<Windows::System::User *>();
  v3 = (_QWORD *)(v2 + 16);
  Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>(v2 + 16);
  *(_QWORD *)(a1 + 168) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>::`vftable';
  *(_QWORD *)(a1 + 8) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'};
  *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  *(_QWORD *)(a1 + 8) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'};
  *v3 = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>>'};
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
0x1800bce84  mov     [rsp+arg_8], rbx
0x1800bce89  mov     [rsp+arg_0], rcx
0x1800bce8e  push    rdi
0x1800bce8f  sub     rsp, 20h
0x1800bce93  mov     rbx, rcx
0x1800bce96  call    ??0?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@QEAA@XZ; Windows::Foundation::IAsyncOperation<Windows::System::User *>::IAsyncOperation<Windows::System::User *>(void)
0x1800bce9b  lea     rdi, [rcx+10h]
0x1800bce9f  mov     rcx, rdi
0x1800bcea2  call    ??0?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@QEAA@XZ; Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>(void)
0x1800bcea7  mov     qword ptr [rbx+0A8h], 1
0x1800bceb2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>::`vftable'
0x1800bceb9  mov     [rbx], rax
0x1800bcebc  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6BIWeakReferenceSource@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'}
0x1800bcec3  mov     [rbx+8], rax
0x1800bcec7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800bcece  mov     [rdi], rax
0x1800bced1  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800bced8  mov     [rbx+60h], rax
0x1800bcedc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800bcee3  mov     [rbx+88h], rax
0x1800bceea  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800bcef1  test    rcx, rcx
0x1800bcef4  jz      short loc_1800BCF03
0x1800bcef6  mov     rax, [rcx]
0x1800bcef9  mov     rax, [rax+8]
0x1800bcefd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcf02  nop
0x1800bcf03  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x1800bcf0a  mov     [rbx], rax
0x1800bcf0d  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6BIWeakReferenceSource@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'}
0x1800bcf14  mov     [rbx+8], rax
0x1800bcf18  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800bcf1f  mov     [rdi], rax
0x1800bcf22  lea     rax, ??_7?$AsyncOperationBase@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800bcf29  mov     [rbx+60h], rax
0x1800bcf2d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$IAsyncOperation@PEAVUser@System@Windows@@@Foundation@Windows@@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUser@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncOperation<Windows::System::User *>,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::User *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800bcf34  mov     [rbx+88h], rax
0x1800bcf3b  mov     dword ptr [rbx+0B0h], 0
0x1800bcf45  mov     qword ptr [rbx+0B8h], 0
0x1800bcf50  mov     qword ptr [rbx+0C0h], 0
0x1800bcf5b  lea     rcx, [rbx+0C8h]; SRWLock
0x1800bcf62  call    cs:__imp_InitializeSRWLock
0x1800bcf68  xor     edx, edx; lpName
0x1800bcf6a  xor     ecx, ecx; lpEventAttributes
0x1800bcf6c  mov     r9d, 1F0003h; dwDesiredAccess
0x1800bcf72  lea     r8d, [rdx+1]; dwFlags
0x1800bcf76  call    cs:__imp_CreateEventExW
0x1800bcf7c  mov     [rbx+0B8h], rax
0x1800bcf83  test    rax, rax
0x1800bcf86  jz      short loc_1800BCFA8
0x1800bcf88  xor     edx, edx; lpName
0x1800bcf8a  xor     ecx, ecx; lpEventAttributes
0x1800bcf8c  mov     r9d, 1F0003h; dwDesiredAccess
0x1800bcf92  lea     r8d, [rdx+1]; dwFlags
0x1800bcf96  call    cs:__imp_CreateEventExW
0x1800bcf9c  mov     [rbx+0C0h], rax
0x1800bcfa3  test    rax, rax
0x1800bcfa6  jnz     short loc_1800BCFD2
0x1800bcfa8  call    cs:__imp_GetLastError
0x1800bcfae  test    eax, eax
0x1800bcfb0  jnz     short loc_1800BCFB9
0x1800bcfb2  mov     eax, 8000FFFFh
0x1800bcfb7  jmp     short loc_1800BCFC7
0x1800bcfb9  jle     short loc_1800BCFC3
0x1800bcfbb  movzx   eax, ax
0x1800bcfbe  or      eax, 80070000h
0x1800bcfc3  test    eax, eax
0x1800bcfc5  jns     short loc_1800BCFD2
0x1800bcfc7  mov     edx, eax
0x1800bcfc9  mov     rcx, rdi
0x1800bcfcc  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVValidateCredentialsResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::ValidateCredentialsResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800bcfd1  nop
0x1800bcfd2  mov     rax, rbx
0x1800bcfd5  mov     rbx, [rsp+28h+arg_8]
0x1800bcfda  add     rsp, 20h
0x1800bcfde  pop     rdi
0x1800bcfdf  retn
```
