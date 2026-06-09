# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x1800053b0`
- end: `0x1800054dd`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800059d8`

## callees

- `0x180003d24`
- `0x1800053b0`
- `0x1800054f0`
- `0x18001cc38`
- `0x18002283c`
- `0x180022894`
- `0x18002b1e0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005454`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180005454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005462`

## string_xrefs

- `0x1800054be`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  wil::details *v3; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  unsigned int v6; // esi
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _DWORD *v10; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  *(_QWORD *)v2 = &Windows::Foundation::ITypedEventHandler<Windows::Internal::Shell::Popups::PopupClient *,Windows::Internal::Shell::Popups::PopupClientPropertyChangedEventArgs *>::`vftable';
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
  v2[11] = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>'};
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v2 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *>'::`2'::CompletionDelegate::`vftable';
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2[12] = 0;
  *((_QWORD *)v2 + 7) = 0;
  v10 = v2;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v2 + 14,
      Event);
LABEL_7:
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
    *a1 = v2;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 16LL))(v2);
    return 0;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v3);
  v6 = LastErrorFailHr;
  if ( LastErrorFailHr >= 0 )
    goto LABEL_7;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x62B,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
    (const char *)(unsigned int)LastErrorFailHr,
    v8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  return v6;
}

```

## disassembly

```asm
0x1800053b0  push    rbx
0x1800053b2  push    rbp
0x1800053b3  push    rsi
0x1800053b4  push    rdi
0x1800053b5  sub     rsp, 28h
0x1800053b9  mov     rdi, rcx
0x1800053bc  xor     ebp, ebp
0x1800053be  mov     [rcx], rbp
0x1800053c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800053c8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800053cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800053d2  mov     rbx, rax
0x1800053d5  test    rax, rax
0x1800053d8  jz      loc_1800054AF
0x1800053de  lea     rax, ??_7?$ITypedEventHandler@PEAVPopupClient@Popups@Shell@Internal@Windows@@PEAVPopupClientPropertyChangedEventArgs@2345@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::Internal::Shell::Popups::PopupClient *,Windows::Internal::Shell::Popups::PopupClientPropertyChangedEventArgs *>::`vftable'
0x1800053e5  mov     [rbx], rax
0x1800053e8  lea     rcx, [rbx+8]; this
0x1800053ec  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800053f1  mov     dword ptr [rbx+2Ch], 1
0x1800053f8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>'}
0x1800053ff  mov     [rbx], rax
0x180005402  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180005409  mov     [rbx+8], rax
0x18000540d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005414  test    rcx, rcx
0x180005417  jz      short loc_180005426
0x180005419  mov     rax, [rcx]
0x18000541c  mov     rax, [rax+8]
0x180005420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005425  nop
0x180005426  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>'}
0x18000542d  mov     [rbx], rax
0x180005430  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Internal::StartupTaskInternal *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180005437  mov     [rbx+8], rax
0x18000543b  mov     [rbx+30h], ebp
0x18000543e  mov     [rbx+38h], rbp
0x180005442  mov     [rsp+48h+arg_0], rbx
0x180005447  mov     r9d, 1F0003h; dwDesiredAccess
0x18000544d  xor     r8d, r8d; dwFlags
0x180005450  xor     edx, edx; lpName
0x180005452  xor     ecx, ecx; lpEventAttributes
0x180005454  call    cs:__imp_CreateEventExW
0x18000545a  mov     rbp, rax
0x18000545d  test    rax, rax
0x180005460  jz      short loc_180005476
0x180005462  call    cs:__imp_GetLastError
0x180005468  mov     rdx, rbp
0x18000546b  lea     rcx, [rbx+38h]
0x18000546f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005474  jmp     short loc_180005481
0x180005476  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000547b  mov     esi, eax
0x18000547d  test    eax, eax
0x18000547f  js      short loc_1800054B6
0x180005481  mov     rax, [rbx]
0x180005484  mov     rcx, rbx
0x180005487  mov     rax, [rax+8]
0x18000548b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005490  nop
0x180005491  mov     [rdi], rbx
0x180005494  mov     rax, [rbx]
0x180005497  mov     rcx, rbx
0x18000549a  mov     rax, [rax+10h]
0x18000549e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054a3  nop
0x1800054a4  xor     eax, eax
0x1800054a6  add     rsp, 28h
0x1800054aa  pop     rdi
0x1800054ab  pop     rsi
0x1800054ac  pop     rbp
0x1800054ad  pop     rbx
0x1800054ae  retn
0x1800054af  mov     eax, 8007000Eh
0x1800054b4  jmp     short loc_1800054A6
0x1800054b6  mov     rcx, [rsp+48h]; this
0x1800054bb  mov     r9d, esi; char *
0x1800054be  lea     r8, aOnecoreInterna_11; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800054c5  mov     edx, 62Bh; void *
0x1800054ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054cf  lea     rcx, [rsp+48h+arg_0]
0x1800054d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800054d9  mov     eax, esi
0x1800054db  jmp     short loc_1800054A6
```
