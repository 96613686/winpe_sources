# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x18004a340`
- end: `0x18004a48f`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `335`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004a518`

## callees

- `0x18000529c`
- `0x180005f50`
- `0x180009920`
- `0x180009e60`
- `0x18000e5ac`
- `0x18001c464`
- `0x18001f88c`
- `0x18004a340`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004a406`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004a406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a414`

## string_xrefs

- `0x18004a472`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVPushNotificationChannel_PushNotifications_Networking_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  unsigned int v3; // edi
  wil::details *v4; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v10; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v11; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v10 = v2;
    v11 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v2 + 14,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
      v3 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v8);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
    *a1 = v2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
LABEL_8:
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::~MakeAllocator<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>(&v11);
  return v3;
}

```

## disassembly

```asm
0x18004a340  mov     [rsp+arg_10], rbx
0x18004a345  push    rbp
0x18004a346  push    rsi
0x18004a347  push    rdi; int
0x18004a348  sub     rsp, 20h
0x18004a34c  mov     rsi, rcx
0x18004a34f  mov     qword ptr [rcx], 0
0x18004a356  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004a35d  mov     ecx, 40h ; '@'; unsigned __int64
0x18004a362  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004a367  mov     rbx, rax
0x18004a36a  mov     [rsp+38h+arg_8], rax
0x18004a36f  test    rax, rax
0x18004a372  jnz     short loc_18004A37E
0x18004a374  mov     edi, 8007000Eh
0x18004a379  jmp     loc_18004A446
0x18004a37e  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable'
0x18004a385  mov     [rbx], rax
0x18004a388  lea     rdi, [rbx+8]
0x18004a38c  mov     rcx, rdi; this
0x18004a38f  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18004a394  mov     dword ptr [rbx+2Ch], 1
0x18004a39b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'}
0x18004a3a2  mov     [rbx], rax
0x18004a3a5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004a3ac  mov     [rdi], rax
0x18004a3af  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004a3b6  test    rcx, rcx
0x18004a3b9  jz      short loc_18004A3C8
0x18004a3bb  mov     rax, [rcx]
0x18004a3be  mov     rax, [rax+8]
0x18004a3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3c7  nop
0x18004a3c8  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>'}
0x18004a3cf  mov     [rbx], rax
0x18004a3d2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004a3d9  mov     [rdi], rax
0x18004a3dc  mov     dword ptr [rbx+30h], 0
0x18004a3e3  mov     qword ptr [rbx+38h], 0
0x18004a3eb  mov     [rsp+38h+arg_0], rbx
0x18004a3f0  mov     [rsp+38h+arg_8], 0
0x18004a3f9  mov     r9d, 1F0003h; dwDesiredAccess
0x18004a3ff  xor     r8d, r8d; dwFlags
0x18004a402  xor     edx, edx; lpName
0x18004a404  xor     ecx, ecx; lpEventAttributes
0x18004a406  call    cs:__imp_CreateEventExW
0x18004a40c  mov     rbp, rax
0x18004a40f  test    rax, rax
0x18004a412  jz      short loc_18004A45F
0x18004a414  call    cs:__imp_GetLastError
0x18004a41a  mov     rdx, rbp
0x18004a41d  lea     rcx, [rbx+38h]
0x18004a421  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004a426  nop
0x18004a427  mov     rax, [rbx]
0x18004a42a  mov     rcx, rbx
0x18004a42d  mov     rax, [rax+8]
0x18004a431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a436  nop
0x18004a437  mov     [rsi], rbx
0x18004a43a  lea     rcx, [rsp+38h+arg_0]
0x18004a43f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a444  xor     edi, edi
0x18004a446  lea     rcx, [rsp+38h+arg_8]
0x18004a44b  call    ??1?$MakeAllocator@VOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>::~MakeAllocator<Windows::Internal::Flighting::OneSettings::OneSettingsPayload>(void)
0x18004a450  mov     eax, edi
0x18004a452  mov     rbx, [rsp+38h+arg_10]
0x18004a457  add     rsp, 20h
0x18004a45b  pop     rdi
0x18004a45c  pop     rsi
0x18004a45d  pop     rbp
0x18004a45e  retn
0x18004a45f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004a464  mov     edi, eax
0x18004a466  test    eax, eax
0x18004a468  jns     short loc_18004A427
0x18004a46a  mov     rcx, [rsp+38h]; this
0x18004a46f  mov     r9d, eax; char *
0x18004a472  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004a479  mov     edx, 62Bh; void *
0x18004a47e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a483  lea     rcx, [rsp+38h+arg_0]
0x18004a488  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004a48d  jmp     short loc_18004A446
```
