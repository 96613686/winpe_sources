# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x180020aa0`
- end: `0x180020bca`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020c48`

## callees

- `0x180006db4`
- `0x18000872c`
- `0x18000b924`
- `0x1800144c8`
- `0x180014b60`
- `0x18001aadc`
- `0x180020aa0`
- `0x180029010`

## string_xrefs

- `0x180020b72`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  unsigned int v3; // edi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v8; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v9; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &tip2::details::test_data_interface::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>'};
    *((_QWORD *)v2 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>'::`2'::CompletionDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>'::`2'::CompletionDelegate::`vftable';
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v8 = v2;
    v9 = 0;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)(v2 + 14));
    v3 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      _InternalRelease___ComPtr_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__WRL_Microsoft__IEAAKXZ(&v8);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        v6);
      _InternalRelease___ComPtr_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVStoreSendRequestResult_Store_Services_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__WRL_Microsoft__IEAAKXZ(&v8);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(&v9);
  return v3;
}

```

## disassembly

```asm
0x180020aa0  mov     [rsp+arg_10], rbx
0x180020aa5  mov     [rsp+arg_18], rsi
0x180020aaa  push    rdi
0x180020aab  sub     rsp, 30h
0x180020aaf  mov     rsi, rcx
0x180020ab2  mov     qword ptr [rcx], 0
0x180020ab9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020ac0  mov     ecx, 40h ; '@'; unsigned __int64
0x180020ac5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020aca  mov     rbx, rax
0x180020acd  mov     [rsp+38h+arg_8], rax
0x180020ad2  test    rax, rax
0x180020ad5  jnz     short loc_180020AE1
0x180020ad7  mov     edi, 8007000Eh
0x180020adc  jmp     loc_180020BAE
0x180020ae1  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180020ae8  mov     [rbx], rax
0x180020aeb  lea     rdi, [rbx+8]
0x180020aef  mov     rcx, rdi; this
0x180020af2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180020af7  mov     dword ptr [rbx+2Ch], 1
0x180020afe  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>'}
0x180020b05  mov     [rbx], rax
0x180020b08  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180020b0f  mov     [rdi], rax
0x180020b12  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180020b19  test    rcx, rcx
0x180020b1c  jz      short loc_180020B2B
0x180020b1e  mov     rax, [rcx]
0x180020b21  mov     rax, [rax+8]
0x180020b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b2a  nop
0x180020b2b  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVStoreSendRequestResult@Store@Services@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Services::Store::StoreSendRequestResult *>'}
0x180020b32  mov     [rbx], rax
0x180020b35  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180020b3c  mov     [rdi], rax
0x180020b3f  mov     dword ptr [rbx+30h], 0
0x180020b46  lea     rcx, [rbx+38h]
0x180020b4a  mov     qword ptr [rcx], 0
0x180020b51  mov     [rsp+38h+arg_0], rbx
0x180020b56  mov     [rsp+38h+arg_8], 0
0x180020b5f  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180020b64  mov     edi, eax
0x180020b66  test    eax, eax
0x180020b68  jns     short loc_180020B8F
0x180020b6a  mov     rcx, [rsp+38h]; this
0x180020b6f  mov     r9d, eax; char *
0x180020b72  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020b79  mov     edx, 62Bh; void *
0x180020b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b83  lea     rcx, [rsp+38h+arg_0]
0x180020b88  call    ?InternalRelease@?$ComPtr@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::InternalRelease(void)
0x180020b8d  jmp     short loc_180020BAE
0x180020b8f  mov     rax, [rbx]
0x180020b92  mov     rcx, rbx
0x180020b95  mov     rax, [rax+8]
0x180020b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b9e  nop
0x180020b9f  mov     [rsi], rbx
0x180020ba2  lea     rcx, [rsp+38h+arg_0]
0x180020ba7  call    ?InternalRelease@?$ComPtr@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVStoreSendRequestResult@Store@Services@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Services::Store::StoreSendRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::InternalRelease(void)
0x180020bac  xor     edi, edi
0x180020bae  lea     rcx, [rsp+38h+arg_8]
0x180020bb3  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x180020bb8  mov     eax, edi
0x180020bba  mov     rbx, [rsp+38h+arg_10]
0x180020bbf  mov     rsi, [rsp+38h+arg_18]
0x180020bc4  add     rsp, 30h
0x180020bc8  pop     rdi
0x180020bc9  retn
```
