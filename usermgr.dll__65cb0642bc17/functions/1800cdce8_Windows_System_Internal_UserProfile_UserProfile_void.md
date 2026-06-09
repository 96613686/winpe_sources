# Windows::System::Internal::UserProfile::~UserProfile(void)

- ea: `0x1800cdce8`
- end: `0x1800cdde0`
- name: `??1UserProfile@Internal@System@Windows@@UEAA@XZ`
- size: `248`
- prototype: `void __fastcall(Windows::System::Internal::UserProfile *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800cdf20`

## callees

- `0x18000ce48`
- `0x180089630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cdd2e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cdd2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cddb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cddc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cdd98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cddb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cddc5`

## pseudocode

```c
void __fastcall Windows::System::Internal::UserProfile::~UserProfile(Windows::System::Internal::UserProfile *this)
{
  *(_QWORD *)this = &Windows::System::Internal::UserProfile::`vftable';
  *((_QWORD *)this + 1) = &Windows::System::Internal::UserProfile::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::System::Internal::UserProfile::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserProfile2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserProfileInternal>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 3) = &Windows::System::Internal::UserProfile::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::Implementation::IUserProfileInternal>'};
  *((_QWORD *)this + 4) = &Windows::System::Internal::UserProfile::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  WindowsDeleteString(*((HSTRING *)this + 19));
  *((_QWORD *)this + 19) = 0;
  WindowsDeleteString(*((HSTRING *)this + 18));
  *((_QWORD *)this + 18) = 0;
  WindowsDeleteString(*((HSTRING *)this + 17));
  *((_QWORD *)this + 17) = 0;
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 112);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800cdce8  push    rbx
0x1800cdcea  sub     rsp, 20h
0x1800cdcee  lea     rax, ??_7UserProfile@Internal@System@Windows@@6B@; const Windows::System::Internal::UserProfile::`vftable'
0x1800cdcf5  mov     rbx, rcx
0x1800cdcf8  mov     [rcx], rax
0x1800cdcfb  lea     rax, ??_7UserProfile@Internal@System@Windows@@6BIWeakReferenceSource@@@; const Windows::System::Internal::UserProfile::`vftable'{for `IWeakReferenceSource'}
0x1800cdd02  mov     [rcx+8], rax
0x1800cdd06  lea     rax, ??_7UserProfile@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUserProfile2@Internal@System@Windows@@U?$CloakedIid@UIUserProfileInternal@Implementation@Internal@System@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserProfile::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserProfile2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserProfileInternal>,Microsoft::WRL::FtmBase>'}
0x1800cdd0d  mov     [rcx+10h], rax
0x1800cdd11  lea     rax, ??_7UserProfile@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUserProfileInternal@Implementation@Internal@System@Windows@@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserProfile::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::Implementation::IUserProfileInternal>'}
0x1800cdd18  mov     [rcx+18h], rax
0x1800cdd1c  lea     rax, ??_7UserProfile@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserProfile::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800cdd23  mov     [rcx+20h], rax
0x1800cdd27  add     rcx, 0A8h; lpCriticalSection
0x1800cdd2e  call    cs:__imp_DeleteCriticalSection
0x1800cdd34  mov     rcx, [rbx+0A0h]; string
0x1800cdd3b  call    cs:__imp_WindowsDeleteString
0x1800cdd41  mov     qword ptr [rbx+0A0h], 0
0x1800cdd4c  mov     rcx, [rbx+98h]; string
0x1800cdd53  call    cs:__imp_WindowsDeleteString
0x1800cdd59  mov     qword ptr [rbx+98h], 0
0x1800cdd64  mov     rcx, [rbx+90h]; string
0x1800cdd6b  call    cs:__imp_WindowsDeleteString
0x1800cdd71  mov     qword ptr [rbx+90h], 0
0x1800cdd7c  mov     rcx, [rbx+88h]; string
0x1800cdd83  call    cs:__imp_WindowsDeleteString
0x1800cdd89  mov     qword ptr [rbx+88h], 0
0x1800cdd94  mov     rcx, [rbx+78h]; string
0x1800cdd98  call    cs:__imp_WindowsDeleteString
0x1800cdd9e  lea     rcx, [rbx+70h]
0x1800cdda2  mov     qword ptr [rbx+78h], 0
0x1800cddaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cddaf  mov     rcx, [rbx+60h]; string
0x1800cddb3  call    cs:__imp_WindowsDeleteString
0x1800cddb9  mov     qword ptr [rbx+60h], 0
0x1800cddc1  mov     rcx, [rbx+58h]; string
0x1800cddc5  call    cs:__imp_WindowsDeleteString
0x1800cddcb  mov     rcx, rbx
0x1800cddce  mov     qword ptr [rbx+58h], 0
0x1800cddd6  add     rsp, 20h
0x1800cddda  pop     rbx
0x1800cdddb  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(void)
```
