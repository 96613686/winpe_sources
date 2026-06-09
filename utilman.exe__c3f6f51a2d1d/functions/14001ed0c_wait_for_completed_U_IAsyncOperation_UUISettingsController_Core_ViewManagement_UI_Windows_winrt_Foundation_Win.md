# ??$wait_for_completed@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@1@I@Z

- ea: `0x14001ed0c`
- end: `0x14001edf7`
- name: `??$wait_for_completed@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@1@I@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001ee00`

## callees

- `0x140002100`
- `0x140002154`
- `0x140002760`
- `0x14000ccdc`
- `0x14000f914`
- `0x14001ed0c`
- `0x1400234e8`
- `0x140029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>(
        __int64 *a1,
        int a2)
{
  const struct winrt::impl::slim_source_location *v3; // rdx
  HANDLE EventW; // rsi
  _DWORD *v5; // rax
  char *v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _DWORD *v11; // [rsp+20h] [rbp-30h] BYREF
  __int128 v12; // [rsp+28h] [rbp-28h]
  int v13; // [rsp+38h] [rbp-18h] BYREF
  __int128 v14; // [rsp+40h] [rbp-10h]
  int v15; // [rsp+78h] [rbp+28h] BYREF
  _DWORD *v16; // [rsp+80h] [rbp+30h]

  v15 = a2;
  LODWORD(v11) = 0;
  v12 = 0;
  EventW = WINRT_IMPL_CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    winrt::throw_last_error((winrt *)&v11, v3);
  v5 = operator new(0x20u);
  v16 = v5;
  v5[2] = 1;
  v6 = (char *)(v5 + 4);
  *((_QWORD *)v5 + 2) = EventW;
  v5[6] = 0;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v5 = ___7__delegate_U__AsyncOperationCompletedHandler_UUISettingsController_Core_ViewManagement_UI_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UUISettingsController_Core_ViewManagement_UI_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UUISettingsController_Core_ViewManagement_UI_Windows_winrt___234_I_Z__impl_winrt__6B_;
  v11 = v5;
  *(_QWORD *)&v12 = v5 + 4;
  v7 = *a1;
  v13 = 0;
  v14 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))(v7);
  winrt::check_hresult(&v15, v8, &v13);
  WaitForSingleObject_0(*(HANDLE *)v6, 0xFFFFFFFF);
  v9 = *((_DWORD *)v6 + 2);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v11);
  return v9;
}

```

## disassembly

```asm
0x14001ed0c  mov     [rsp-18h+arg_0], rbx
0x14001ed11  mov     [rsp-18h+arg_18], rsi
0x14001ed16  mov     [rsp-18h+arg_8], edx
0x14001ed1a  push    rbp
0x14001ed1b  push    rdi
0x14001ed1c  push    r14
0x14001ed1e  mov     rbp, rsp
0x14001ed21  sub     rsp, 50h
0x14001ed25  mov     r14, rcx
0x14001ed28  mov     dword ptr [rbp+var_30], 0
0x14001ed2f  xorps   xmm0, xmm0
0x14001ed32  movdqu  [rbp+var_28], xmm0
0x14001ed37  xor     r9d, r9d; lpName
0x14001ed3a  xor     r8d, r8d; bInitialState
0x14001ed3d  lea     edi, [r9+1]
0x14001ed41  mov     edx, edi; bManualReset
0x14001ed43  xor     ecx, ecx; lpEventAttributes
0x14001ed45  call    WINRT_IMPL_CreateEventW
0x14001ed4a  mov     rsi, rax
0x14001ed4d  test    rax, rax
0x14001ed50  jz      loc_14001EDED
0x14001ed56  mov     [rbp+var_30], rax
0x14001ed5a  xor     ebx, ebx
0x14001ed5c  mov     qword ptr [rbp+var_28], rbx
0x14001ed60  lea     ecx, [rdi+1Fh]; Size
0x14001ed63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001ed68  mov     rdx, rax
0x14001ed6b  mov     [rbp+arg_10], rax
0x14001ed6f  mov     [rax+8], edi
0x14001ed72  lea     rdi, [rax+10h]
0x14001ed76  mov     [rdi], rsi
0x14001ed79  mov     [rdi+8], ebx
0x14001ed7c  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x14001ed83  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@234@I@Z@@impl@winrt@@6B@
0x14001ed8a  mov     [rdx], rax
0x14001ed8d  mov     [rbp+var_30], rdx
0x14001ed91  mov     qword ptr [rbp+var_28], rdi
0x14001ed95  mov     rcx, [r14]
0x14001ed98  mov     [rbp+var_18], ebx
0x14001ed9b  xorps   xmm0, xmm0
0x14001ed9e  movdqu  [rbp+var_10], xmm0
0x14001eda3  mov     rax, [rcx]
0x14001eda6  mov     rax, [rax+30h]
0x14001edaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001edaf  lea     r8, [rbp+var_18]
0x14001edb3  mov     edx, eax
0x14001edb5  lea     rcx, [rbp+arg_8]
0x14001edb9  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14001edbe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001edc1  mov     rcx, [rdi]; hHandle
0x14001edc4  call    WaitForSingleObject_0
0x14001edc9  mov     ebx, [rdi+8]
0x14001edcc  lea     rcx, [rbp+var_30]
0x14001edd0  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x14001edd5  mov     eax, ebx
0x14001edd7  lea     r11, [rsp+50h+var_s0]
0x14001eddc  mov     rbx, [r11+20h]
0x14001ede0  mov     rsi, [r11+38h]
0x14001ede4  mov     rsp, r11
0x14001ede7  pop     r14
0x14001ede9  pop     rdi
0x14001edea  pop     rbp
0x14001edeb  retn
0x14001eded  lea     rcx, [rbp+var_30]; this
0x14001edf1  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
