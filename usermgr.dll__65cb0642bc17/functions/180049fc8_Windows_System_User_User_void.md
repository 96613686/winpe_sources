# Windows::System::User::~User(void)

- ea: `0x180049fc8`
- end: `0x18004a22e`
- name: `??1User@System@Windows@@UEAA@XZ`
- size: `614`
- prototype: `void __fastcall(Windows::System::User *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b93d0`

## callees

- `0x180007920`
- `0x18000ce48`
- `0x18003561c`
- `0x180049fc8`
- `0x18004a338`
- `0x1800b91dc`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a1cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a1cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a163`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a177`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a203`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a163`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a177`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a115`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a136`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a115`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a136`
- `ntdll!RtlFreeHeap` at `0x18004a156`
- `ntdll!RtlFreeHeap` at `0x18004a156`

## pseudocode

```c
void __fastcall Windows::System::User::~User(Windows::System::User *this, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  void (__fastcall *v5)(void *, __int64 *); // rbx
  void *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // [rsp+30h] [rbp-19h] BYREF
  _QWORD v9[7]; // [rsp+38h] [rbp-11h] BYREF

  *(_QWORD *)this = &Windows::System::User::`vftable'{for `Windows::System::IUser'};
  *((_QWORD *)this + 1) = &Windows::System::User::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::System::IUser2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserInternal>,Microsoft::WRL::CloakedIid<IMarshal>>'};
  *((_QWORD *)this + 2) = &Windows::System::User::`vftable'{for `Windows::System::IUser2'};
  *((_QWORD *)this + 3) = &Windows::System::User::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserInternal>,Microsoft::WRL::CloakedIid<IMarshal>>'};
  *((_QWORD *)this + 4) = &Windows::System::User::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::System::Internal::Implementation::IUserInternal>'};
  *((_QWORD *)this + 5) = &Windows::System::User::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal>>'};
  if ( (Microsoft_Windows_User_UserManager_EventsEnableBits & 0x40) != 0 )
  {
    v9[0] = this;
    LODWORD(v8) = *((_DWORD *)this + 17);
    v9[3] = &v8;
    v9[4] = 4;
    v9[5] = v9;
    v9[6] = 8;
    McGenEventWrite_EventWriteTransfer(this, DtorUser_Log, a3, 3);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    goto LABEL_22;
  v4 = (void *)*((_QWORD *)this + 28);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 28) = 0;
  }
  if ( *((_DWORD *)this + 65) != 1 )
  {
LABEL_22:
    if ( *((_QWORD *)this + 10) && *((_QWORD *)this + 9) )
    {
      v8 = 0;
      v5 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
      v5(&Windows::System::Internal::Adapters::g_AdapterCollection, &v8);
      if ( v8 )
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v8 + 32LL))(
          v8,
          *((_QWORD *)this + 9),
          *((_QWORD *)this + 10));
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
    }
    v6 = (void *)*((_QWORD *)this + 9);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)this + 9) = 0;
    }
    if ( *((_DWORD *)this + 28) && *((_QWORD *)this + 13) )
    {
      v7 = 0;
      do
        CloseHandle(*(HANDLE *)(*((_QWORD *)this + 13) + 8LL * v7++));
      while ( v7 < *((_DWORD *)this + 28) );
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)this + 13));
    }
  }
  WindowsDeleteString(*((HSTRING *)this + 31));
  *((_QWORD *)this + 31) = 0;
  WindowsDeleteString(*((HSTRING *)this + 29));
  *((_QWORD *)this + 29) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 216);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 208);
  WindowsDeleteString(*((HSTRING *)this + 25));
  *((_QWORD *)this + 25) = 0;
  WindowsDeleteString(*((HSTRING *)this + 24));
  *((_QWORD *)this + 24) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 136);
  WindowsDeleteString(*((HSTRING *)this + 16));
  *((_QWORD *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::IUser,Windows::System::IUser2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserInternal>,Microsoft::WRL::CloakedIid<IMarshal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::IUser,Windows::System::IUser2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserInternal>,Microsoft::WRL::CloakedIid<IMarshal>>(this);
}

```

## disassembly

```asm
0x180049fc8  push    rbp
0x180049fca  push    rbx
0x180049fcb  push    rsi
0x180049fcc  push    rdi
0x180049fcd  lea     rbp, [rsp-3Fh]
0x180049fd2  sub     rsp, 88h
0x180049fd9  mov     rax, cs:__security_cookie
0x180049fe0  xor     rax, rsp
0x180049fe3  mov     [rbp+57h+var_30], rax
0x180049fe7  mov     rdi, rcx
0x180049fea  lea     rax, ??_7User@System@Windows@@6BIUser@12@@; const Windows::System::User::`vftable'{for `Windows::System::IUser'}
0x180049ff1  mov     [rcx], rax
0x180049ff4  lea     rax, ??_7User@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIUser2@System@Windows@@U?$CloakedIid@UIAgileObject@@@23@U?$CloakedIid@UIUserInternal@Implementation@Internal@System@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@@Details@WRL@Microsoft@@@; const Windows::System::User::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::System::IUser2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserInternal>,Microsoft::WRL::CloakedIid<IMarshal>>'}
0x180049ffb  mov     [rcx+8], rax
0x180049fff  lea     rax, ??_7User@System@Windows@@6BIUser2@12@@; const Windows::System::User::`vftable'{for `Windows::System::IUser2'}
0x18004a006  mov     [rcx+10h], rax
0x18004a00a  lea     rax, ??_7User@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIAgileObject@@@23@U?$CloakedIid@UIUserInternal@Implementation@Internal@System@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@@Details@WRL@Microsoft@@@; const Windows::System::User::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserInternal>,Microsoft::WRL::CloakedIid<IMarshal>>'}
0x18004a011  mov     [rcx+18h], rax
0x18004a015  lea     rax, ??_7User@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIUserInternal@Implementation@Internal@System@Windows@@@Details@WRL@Microsoft@@@; const Windows::System::User::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::System::Internal::Implementation::IUserInternal>'}
0x18004a01c  mov     [rcx+20h], rax
0x18004a020  lea     rax, ??_7User@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIMarshal@@@23@@Details@WRL@Microsoft@@@; const Windows::System::User::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMarshal>>'}
0x18004a027  mov     [rcx+28h], rax
0x18004a02b  xor     esi, esi
0x18004a02d  test    cs:Microsoft_Windows_User_UserManager_EventsEnableBits, 40h
0x18004a034  jz      short loc_18004A079
0x18004a036  mov     [rbp+57h+var_68], rcx
0x18004a03a  mov     eax, [rcx+44h]
0x18004a03d  mov     dword ptr [rbp+57h+var_70], eax
0x18004a040  lea     rax, [rbp+57h+var_70]
0x18004a044  mov     [rbp+57h+var_50], rax
0x18004a048  mov     [rbp+57h+var_48], 4
0x18004a050  lea     rax, [rbp+57h+var_68]
0x18004a054  mov     [rbp+57h+var_40], rax
0x18004a058  mov     [rbp+57h+var_38], 8
0x18004a060  lea     rax, [rbp+57h+var_60]
0x18004a064  mov     [rsp+0A0h+var_80], rax
0x18004a069  lea     r9d, [rsi+3]
0x18004a06d  lea     rdx, DtorUser_Log
0x18004a074  call    McGenEventWrite_EventWriteTransfer
0x18004a079  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18004a080  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18004a085  test    al, al
0x18004a087  jz      short loc_18004A0AF
0x18004a089  mov     rcx, [rdi+0E0h]; hObject
0x18004a090  test    rcx, rcx
0x18004a093  jz      short loc_18004A0A2
0x18004a095  call    cs:__imp_CloseHandle
0x18004a09b  mov     [rdi+0E0h], rsi
0x18004a0a2  cmp     dword ptr [rdi+104h], 1
0x18004a0a9  jz      loc_18004A15C
0x18004a0af  cmp     [rdi+50h], rsi
0x18004a0b3  jz      short loc_18004A10C
0x18004a0b5  cmp     [rdi+48h], rsi
0x18004a0b9  jz      short loc_18004A10C
0x18004a0bb  mov     [rbp+57h+var_70], rsi
0x18004a0bf  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18004a0c6  mov     rbx, [rax+18h]
0x18004a0ca  lea     rcx, [rbp+57h+var_70]
0x18004a0ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a0d3  lea     rdx, [rbp+57h+var_70]
0x18004a0d7  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18004a0de  mov     rax, rbx
0x18004a0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0e6  mov     rcx, [rbp+57h+var_70]
0x18004a0ea  test    rcx, rcx
0x18004a0ed  jz      short loc_18004A103
0x18004a0ef  mov     rax, [rcx]
0x18004a0f2  mov     r8, [rdi+50h]
0x18004a0f6  mov     rdx, [rdi+48h]
0x18004a0fa  mov     rax, [rax+20h]
0x18004a0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a103  lea     rcx, [rbp+57h+var_70]
0x18004a107  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a10c  mov     rcx, [rdi+48h]; hObject
0x18004a110  test    rcx, rcx
0x18004a113  jz      short loc_18004A11F
0x18004a115  call    cs:__imp_CloseHandle
0x18004a11b  mov     [rdi+48h], rsi
0x18004a11f  cmp     [rdi+70h], esi
0x18004a122  jbe     short loc_18004A15C
0x18004a124  cmp     [rdi+68h], rsi
0x18004a128  jz      short loc_18004A15C
0x18004a12a  mov     ebx, esi
0x18004a12c  mov     eax, ebx
0x18004a12e  mov     rcx, [rdi+68h]
0x18004a132  mov     rcx, [rcx+rax*8]; hObject
0x18004a136  call    cs:__imp_CloseHandle
0x18004a13c  inc     ebx
0x18004a13e  cmp     ebx, [rdi+70h]
0x18004a141  jb      short loc_18004A12C
0x18004a143  mov     rcx, gs:60h
0x18004a14c  mov     r8, [rdi+68h]; P
0x18004a150  xor     edx, edx; Flags
0x18004a152  mov     rcx, [rcx+30h]; HeapHandle
0x18004a156  call    cs:__imp_RtlFreeHeap
0x18004a15c  mov     rcx, [rdi+0F8h]; string
0x18004a163  call    cs:__imp_WindowsDeleteString
0x18004a169  mov     [rdi+0F8h], rsi
0x18004a170  mov     rcx, [rdi+0E8h]; string
0x18004a177  call    cs:__imp_WindowsDeleteString
0x18004a17d  mov     [rdi+0E8h], rsi
0x18004a184  lea     rcx, [rdi+0D8h]
0x18004a18b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a190  lea     rcx, [rdi+0D0h]
0x18004a197  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004a19c  mov     rcx, [rdi+0C8h]; string
0x18004a1a3  call    cs:__imp_WindowsDeleteString
0x18004a1a9  mov     [rdi+0C8h], rsi
0x18004a1b0  mov     rcx, [rdi+0C0h]; string
0x18004a1b7  call    cs:__imp_WindowsDeleteString
0x18004a1bd  mov     [rdi+0C0h], rsi
0x18004a1c4  lea     rcx, [rdi+98h]; lpCriticalSection
0x18004a1cb  call    cs:__imp_DeleteCriticalSection
0x18004a1d1  lea     rcx, [rdi+88h]
0x18004a1d8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a1dd  mov     rcx, [rdi+80h]; string
0x18004a1e4  call    cs:__imp_WindowsDeleteString
0x18004a1ea  mov     [rdi+80h], rsi
0x18004a1f1  mov     rcx, [rdi+78h]; string
0x18004a1f5  call    cs:__imp_WindowsDeleteString
0x18004a1fb  mov     [rdi+78h], rsi
0x18004a1ff  mov     rcx, [rdi+58h]; string
0x18004a203  call    cs:__imp_WindowsDeleteString
0x18004a209  mov     [rdi+58h], rsi
0x18004a20d  mov     rcx, rdi
0x18004a210  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIUser@System@Windows@@UIUser2@56@U?$CloakedIid@UIAgileObject@@@23@U?$CloakedIid@UIUserInternal@Implementation@Internal@System@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::IUser,Windows::System::IUser2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserInternal>,Microsoft::WRL::CloakedIid<IMarshal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::System::IUser,Windows::System::IUser2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserInternal>,Microsoft::WRL::CloakedIid<IMarshal>>(void)
0x18004a215  nop
0x18004a216  mov     rcx, [rbp+57h+var_30]
0x18004a21a  xor     rcx, rsp; StackCookie
0x18004a21d  call    __security_check_cookie
0x18004a222  add     rsp, 88h
0x18004a229  pop     rdi
0x18004a22a  pop     rsi
0x18004a22b  pop     rbx
0x18004a22c  pop     rbp
0x18004a22d  retn
```
