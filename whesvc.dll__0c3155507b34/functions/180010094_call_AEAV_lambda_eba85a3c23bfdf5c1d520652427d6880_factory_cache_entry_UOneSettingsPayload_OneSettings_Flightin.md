# ??$call@AEAV_lambda_eba85a3c23bfdf5c1d520652427d6880_@@@?$factory_cache_entry@UOneSettingsPayload@OneSettings@Flighting@Internal@Windows@winrt@@UIOneSettingsPayloadStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_eba85a3c23bfdf5c1d520652427d6880_@@@Z

- ea: `0x180010094`
- end: `0x1800101eb`
- name: `??$call@AEAV_lambda_eba85a3c23bfdf5c1d520652427d6880_@@@?$factory_cache_entry@UOneSettingsPayload@OneSettings@Flighting@Internal@Windows@winrt@@UIOneSettingsPayloadStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_eba85a3c23bfdf5c1d520652427d6880_@@@Z`
- size: `343`
- prototype: `signed __int64 *__fastcall(__int64, signed __int64 *, void (__fastcall ***)(_QWORD, _QWORD, _QWORD))`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800104f8`

## callees

- `0x1800045c9`
- `0x1800066dc`
- `0x180010094`
- `0x180010550`
- `0x180017b60`
- `0x180029010`

## pseudocode

```c
signed __int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::call<_lambda_eba85a3c23bfdf5c1d520652427d6880_ &>(
        __int64 a1,
        signed __int64 *a2,
        void (__fastcall ***a3)(_QWORD, _QWORD, _QWORD))
{
  signed __int64 v4; // rbx
  void (__fastcall **v5)(signed __int64, __int64 *, _QWORD); // rax
  __int64 v6; // rcx
  int v8; // [rsp+28h] [rbp-38h] BYREF
  __int128 v9; // [rsp+30h] [rbp-30h]
  _DWORD *v10; // [rsp+40h] [rbp-20h] BYREF
  _DWORD v11[4]; // [rsp+48h] [rbp-18h] BYREF
  const wchar_t *v12; // [rsp+58h] [rbp-8h]
  void (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // [rsp+70h] [rbp+10h] BYREF
  void (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // [rsp+80h] [rbp+20h] BYREF

  v14 = a3;
  v11[0] = 1;
  v12 = L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload";
  v11[1] = 57;
  v10 = v11;
  v13 = 0;
  v8 = 0;
  v9 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v10,
    winrt::impl::guid_v<winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>,
    &v13);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v8);
  v4 = (signed __int64)v13;
  v14 = v13;
  if ( !v13 )
  {
    *a2 = 0;
    return a2;
  }
  v5 = (void (__fastcall **)(signed __int64, __int64 *, _QWORD))*v13;
  v13 = 0;
  (*v5)(v4, winrt::impl::guid_v<winrt::impl::IAgileObject>, &v13);
  if ( !v13 )
  {
    *a2 = v4;
    (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v4 + 8LL))(v4);
LABEL_12:
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v14);
    return a2;
  }
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v13);
  _InterlockedIncrement64(&qword_180034D78);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>,
          v4,
          0) )
  {
    v4 = 0;
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
  }
  v6 = winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>;
  *a2 = winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  _InterlockedDecrement64(&qword_180034D78);
  if ( v4 )
    goto LABEL_12;
  return a2;
}

```

## disassembly

```asm
0x180010094  mov     rax, rsp
0x180010097  mov     [rax+10h], rbx
0x18001009b  mov     [rax+20h], rdi
0x18001009f  mov     [rax+18h], r8
0x1800100a3  mov     [rax+8], rcx
0x1800100a7  push    rbp
0x1800100a8  mov     rbp, rsp
0x1800100ab  sub     rsp, 60h
0x1800100af  lea     rax, aWindowsInterna; "Windows.Internal.Flighting.OneSettings."...
0x1800100b6  mov     [rbp+var_18], 1
0x1800100bd  mov     [rbp+var_8], rax
0x1800100c1  lea     r9, [rbp+arg_0]
0x1800100c5  lea     rax, [rbp+var_18]
0x1800100c9  mov     [rbp+var_14], 39h ; '9'
0x1800100d0  mov     rdi, rdx
0x1800100d3  mov     [rbp+var_20], rax
0x1800100d7  xorps   xmm0, xmm0
0x1800100da  mov     [rbp+arg_0], 0
0x1800100e2  lea     r8, ??$guid_v@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>
0x1800100e9  mov     [rbp+var_38], 0
0x1800100f0  lea     rdx, [rbp+var_20]
0x1800100f4  lea     rcx, [rbp+arg_10]
0x1800100f8  movdqu  [rbp+var_30], xmm0
0x1800100fd  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180010102  mov     ecx, dword ptr [rbp+arg_10]
0x180010105  test    ecx, ecx
0x180010107  js      loc_1800101E1
0x18001010d  mov     rbx, [rbp+arg_0]
0x180010111  mov     [rbp+arg_10], rbx
0x180010115  test    rbx, rbx
0x180010118  jnz     short loc_180010122
0x18001011a  mov     [rdi], rbx
0x18001011d  jmp     loc_1800101CC
0x180010122  mov     rax, [rbx]
0x180010125  lea     r8, [rbp+arg_0]
0x180010129  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180010130  mov     [rbp+arg_0], 0
0x180010138  mov     rcx, rbx
0x18001013b  mov     rax, [rax]
0x18001013e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010143  mov     rax, [rbp+arg_0]
0x180010147  mov     [rbp+arg_0], rax
0x18001014b  test    rax, rax
0x18001014e  jz      short loc_1800101B1
0x180010150  lea     rcx, [rbp+arg_0]
0x180010154  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180010159  lock inc cs:qword_180034D78
0x180010161  xor     eax, eax
0x180010163  lock cmpxchg cs:??$factory_cache_entry_v@UOneSettingsPayload@OneSettings@Flighting@Internal@Windows@winrt@@UIOneSettingsPayloadStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UOneSettingsPayload@OneSettings@Flighting@Internal@Windows@winrt@@UIOneSettingsPayloadStatics@23456@@12@A, rbx; factory_cache_entry<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>
0x18001016c  jnz     short loc_180010187
0x18001016e  xor     ebx, ebx
0x180010170  lea     rdx, ListEntry; ListEntry
0x180010177  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001017e  mov     [rbp+arg_10], rbx
0x180010182  call    WINRT_IMPL_InterlockedPushEntrySList
0x180010187  mov     rcx, cs:??$factory_cache_entry_v@UOneSettingsPayload@OneSettings@Flighting@Internal@Windows@winrt@@UIOneSettingsPayloadStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UOneSettingsPayload@OneSettings@Flighting@Internal@Windows@winrt@@UIOneSettingsPayloadStatics@23456@@12@A; factory_cache_entry<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Flighting::OneSettings::OneSettingsPayload,winrt::Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>
0x18001018e  mov     [rdi], rcx
0x180010191  test    rcx, rcx
0x180010194  jz      short loc_1800101A2
0x180010196  mov     rax, [rcx]
0x180010199  mov     rax, [rax+8]
0x18001019d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a2  lock dec cs:qword_180034D78
0x1800101aa  test    rbx, rbx
0x1800101ad  jz      short loc_1800101CC
0x1800101af  jmp     short loc_1800101C3
0x1800101b1  mov     [rdi], rbx
0x1800101b4  mov     rcx, rbx
0x1800101b7  mov     rax, [rbx]
0x1800101ba  mov     rax, [rax+8]
0x1800101be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c3  lea     rcx, [rbp+arg_10]
0x1800101c7  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x1800101cc  lea     r11, [rsp+60h+var_s0]
0x1800101d1  mov     rax, rdi
0x1800101d4  mov     rbx, [r11+18h]
0x1800101d8  mov     rdi, [r11+28h]
0x1800101dc  mov     rsp, r11
0x1800101df  pop     rbp
0x1800101e0  retn
0x1800101e1  lea     rdx, [rbp+var_38]
0x1800101e5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
