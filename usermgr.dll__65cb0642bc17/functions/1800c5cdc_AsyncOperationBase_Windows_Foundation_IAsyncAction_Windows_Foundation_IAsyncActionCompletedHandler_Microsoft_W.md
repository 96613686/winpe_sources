# AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(void)

- ea: `0x1800c5cdc`
- end: `0x1800c5dd3`
- name: `??0?$AsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@U?$AsyncCausalityOptions@$1?SetAutologonWithContextAsyncActionName@Internal@System@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@QEAA@XZ`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008695c`
- `0x180087088`

## callees

- `0x18005324c`
- `0x1800c5cdc`
- `0x1800c5ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800c5d54`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800c5d54`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c5d68`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c5d88`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c5d68`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800c5d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5d9a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
        __int64 a1)
{
  HANDLE Event; // rax
  HANDLE v3; // rax
  signed int LastError; // eax

  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncAction,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::FtmBase>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncAction,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::FtmBase>>();
  *(_QWORD *)a1 = &AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable';
  *(_QWORD *)(a1 + 8) = &AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'};
  *(_QWORD *)(a1 + 16) = &AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::System::Internal::SignOutUserAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 96) = &AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *(_QWORD *)(a1 + 136) = &AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::FtmBase>>>'};
  *(_DWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 200));
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  *(_QWORD *)(a1 + 184) = Event;
  if ( !Event || (v3 = CreateEventExW(0, 0, 1u, 0x1F0003u), (*(_QWORD *)(a1 + 192) = v3) == 0) )
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
      a1 + 16,
      (unsigned int)LastError);
  }
  return a1;
}

```

## disassembly

```asm
0x1800c5cdc  mov     [rsp+arg_8], rbx
0x1800c5ce1  mov     [rsp+arg_0], rcx
0x1800c5ce6  push    rdi
0x1800c5ce7  sub     rsp, 20h
0x1800c5ceb  mov     rbx, rcx
0x1800c5cee  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAsyncAction@Foundation@Windows@@V?$HardenedAsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@6@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncAction,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::FtmBase>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Foundation::IAsyncAction,Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::FtmBase>>(void)
0x1800c5cf3  nop
0x1800c5cf4  lea     rax, ??_7?$AsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@U?$AsyncCausalityOptions@$1?SetAutologonWithContextAsyncActionName@Internal@System@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B@; const AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'
0x1800c5cfb  mov     [rbx], rax
0x1800c5cfe  lea     rax, ??_7?$AsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@U?$AsyncCausalityOptions@$1?SetAutologonWithContextAsyncActionName@Internal@System@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6BIWeakReferenceSource@@@; const AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `IWeakReferenceSource'}
0x1800c5d05  mov     [rbx+8], rax
0x1800c5d09  lea     rax, ??_7?$AsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@U?$AsyncCausalityOptions@$1?SignOutUserAsyncActionName@Internal@System@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::System::Internal::SignOutUserAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800c5d10  mov     [rbx+10h], rax
0x1800c5d14  lea     rax, ??_7?$AsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@U?$AsyncCausalityOptions@$1?SetAutologonWithContextAsyncActionName@Internal@System@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800c5d1b  mov     [rbx+60h], rax
0x1800c5d1f  lea     rax, ??_7?$AsyncOperationBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@U?$AsyncCausalityOptions@$1?SetAutologonWithContextAsyncActionName@Internal@System@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const AsyncOperationBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::System::Internal::SetAutologonWithContextAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::FtmBase>>>'}
0x1800c5d26  mov     [rbx+88h], rax
0x1800c5d2d  mov     dword ptr [rbx+0B0h], 0
0x1800c5d37  mov     qword ptr [rbx+0B8h], 0
0x1800c5d42  mov     qword ptr [rbx+0C0h], 0
0x1800c5d4d  lea     rcx, [rbx+0C8h]; SRWLock
0x1800c5d54  call    cs:__imp_InitializeSRWLock
0x1800c5d5a  xor     edx, edx; lpName
0x1800c5d5c  xor     ecx, ecx; lpEventAttributes
0x1800c5d5e  mov     r9d, 1F0003h; dwDesiredAccess
0x1800c5d64  lea     r8d, [rdx+1]; dwFlags
0x1800c5d68  call    cs:__imp_CreateEventExW
0x1800c5d6e  mov     [rbx+0B8h], rax
0x1800c5d75  test    rax, rax
0x1800c5d78  jz      short loc_1800C5D9A
0x1800c5d7a  xor     edx, edx; lpName
0x1800c5d7c  xor     ecx, ecx; lpEventAttributes
0x1800c5d7e  mov     r9d, 1F0003h; dwDesiredAccess
0x1800c5d84  lea     r8d, [rdx+1]; dwFlags
0x1800c5d88  call    cs:__imp_CreateEventExW
0x1800c5d8e  mov     [rbx+0C0h], rax
0x1800c5d95  test    rax, rax
0x1800c5d98  jnz     short loc_1800C5DC5
0x1800c5d9a  call    cs:__imp_GetLastError
0x1800c5da0  test    eax, eax
0x1800c5da2  jnz     short loc_1800C5DAB
0x1800c5da4  mov     eax, 8000FFFFh
0x1800c5da9  jmp     short loc_1800C5DB9
0x1800c5dab  jle     short loc_1800C5DB5
0x1800c5dad  movzx   eax, ax
0x1800c5db0  or      eax, 80070000h
0x1800c5db5  test    eax, eax
0x1800c5db7  jns     short loc_1800C5DC5
0x1800c5db9  mov     edx, eax
0x1800c5dbb  lea     rcx, [rbx+10h]
0x1800c5dbf  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVValidateCredentialsResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::ValidateCredentialsResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800c5dc4  nop
0x1800c5dc5  mov     rax, rbx
0x1800c5dc8  mov     rbx, [rsp+28h+arg_8]
0x1800c5dcd  add     rsp, 20h
0x1800c5dd1  pop     rdi
0x1800c5dd2  retn
```
