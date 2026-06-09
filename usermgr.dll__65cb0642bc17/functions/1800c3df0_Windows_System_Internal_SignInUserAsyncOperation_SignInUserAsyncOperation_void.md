# Windows::System::Internal::SignInUserAsyncOperation::~SignInUserAsyncOperation(void)

- ea: `0x1800c3df0`
- end: `0x1800c3ee8`
- name: `??1SignInUserAsyncOperation@Internal@System@Windows@@UEAA@XZ`
- size: `248`
- prototype: `void __fastcall(Windows::System::Internal::SignInUserAsyncOperation *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800c4000`

## callees

- `0x18000ce48`
- `0x18000fd2c`
- `0x1800c3d5c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800c3e39`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800c3e39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3e82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3e9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3eb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3eca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3e6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3e82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3e9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3eb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c3eca`

## pseudocode

```c
void __fastcall Windows::System::Internal::SignInUserAsyncOperation::~SignInUserAsyncOperation(
        Windows::System::Internal::SignInUserAsyncOperation *this)
{
  *(_QWORD *)this = &Windows::System::Internal::SignInUserAsyncOperation::`vftable';
  *((_QWORD *)this + 1) = &Windows::System::Internal::SignInUserAsyncOperation::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::System::Internal::SignInUserAsyncOperation::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 12) = &Windows::System::Internal::SignInUserAsyncOperation::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 17) = &Windows::System::Internal::SignInUserAsyncOperation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,1,Microsoft::WRL::FtmBase>>>'};
  operator delete[](*((void **)this + 27));
  Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>((char *)this + 288);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 280);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 272);
  WindowsDeleteString(*((HSTRING *)this + 33));
  *((_QWORD *)this + 33) = 0;
  WindowsDeleteString(*((HSTRING *)this + 31));
  *((_QWORD *)this + 31) = 0;
  WindowsDeleteString(*((HSTRING *)this + 30));
  *((_QWORD *)this + 30) = 0;
  WindowsDeleteString(*((HSTRING *)this + 29));
  *((_QWORD *)this + 29) = 0;
  WindowsDeleteString(*((HSTRING *)this + 28));
  *((_QWORD *)this + 28) = 0;
  AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SignInResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::~AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SignInResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(this);
}

```

## disassembly

```asm
0x1800c3df0  push    rbx
0x1800c3df2  sub     rsp, 20h
0x1800c3df6  lea     rax, ??_7SignInUserAsyncOperation@Internal@System@Windows@@6B@; const Windows::System::Internal::SignInUserAsyncOperation::`vftable'
0x1800c3dfd  mov     rbx, rcx
0x1800c3e00  mov     [rcx], rax
0x1800c3e03  lea     rax, ??_7SignInUserAsyncOperation@Internal@System@Windows@@6BIWeakReferenceSource@@@; const Windows::System::Internal::SignInUserAsyncOperation::`vftable'{for `IWeakReferenceSource'}
0x1800c3e0a  mov     [rcx+8], rax
0x1800c3e0e  lea     rax, ??_7SignInUserAsyncOperation@Internal@System@Windows@@6B?$Selector@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSignInResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSignInResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@Details@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::SignInUserAsyncOperation::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800c3e15  mov     [rcx+10h], rax
0x1800c3e19  lea     rax, ??_7SignInUserAsyncOperation@Internal@System@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSignInResult@Internal@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?HardenedAsyncBaseOperationName@Async@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::System::Internal::SignInUserAsyncOperation::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Async::HardenedAsyncBaseOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800c3e20  mov     [rcx+60h], rax
0x1800c3e24  lea     rax, ??_7SignInUserAsyncOperation@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$HardenedAsyncBase@U?$IAsyncOperationCompletedHandler@PEAVSignInResult@Internal@System@Windows@@@Foundation@Windows@@$00VFtmBase@WRL@Microsoft@@@Async@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::SignInUserAsyncOperation::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::Async::HardenedAsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,1,Microsoft::WRL::FtmBase>>>'}
0x1800c3e2b  mov     [rcx+88h], rax
0x1800c3e32  mov     rcx, [rcx+0D8h]
0x1800c3e39  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800c3e3f  lea     rcx, [rbx+120h]
0x1800c3e46  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x1800c3e4b  lea     rcx, [rbx+118h]
0x1800c3e52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c3e57  lea     rcx, [rbx+110h]
0x1800c3e5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c3e63  mov     rcx, [rbx+108h]; string
0x1800c3e6a  call    cs:__imp_WindowsDeleteString
0x1800c3e70  mov     qword ptr [rbx+108h], 0
0x1800c3e7b  mov     rcx, [rbx+0F8h]; string
0x1800c3e82  call    cs:__imp_WindowsDeleteString
0x1800c3e88  mov     qword ptr [rbx+0F8h], 0
0x1800c3e93  mov     rcx, [rbx+0F0h]; string
0x1800c3e9a  call    cs:__imp_WindowsDeleteString
0x1800c3ea0  mov     qword ptr [rbx+0F0h], 0
0x1800c3eab  mov     rcx, [rbx+0E8h]; string
0x1800c3eb2  call    cs:__imp_WindowsDeleteString
0x1800c3eb8  mov     qword ptr [rbx+0E8h], 0
0x1800c3ec3  mov     rcx, [rbx+0E0h]; string
0x1800c3eca  call    cs:__imp_WindowsDeleteString
0x1800c3ed0  mov     rcx, rbx
0x1800c3ed3  mov     qword ptr [rbx+0E0h], 0
0x1800c3ede  add     rsp, 20h
0x1800c3ee2  pop     rbx
0x1800c3ee3  jmp     ??1?$AsyncOperationBase@U?$IAsyncOperation@PEAVSignInResult@Internal@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVSignInResult@Internal@System@Windows@@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@@UEAA@XZ; AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SignInResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::~AsyncOperationBase<Windows::Foundation::IAsyncOperation<Windows::System::Internal::SignInResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::Internal::SignInResult *>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(void)
```
