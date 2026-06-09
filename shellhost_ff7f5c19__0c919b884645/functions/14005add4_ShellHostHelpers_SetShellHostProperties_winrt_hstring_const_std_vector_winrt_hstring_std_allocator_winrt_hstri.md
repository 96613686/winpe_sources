# ShellHostHelpers::SetShellHostProperties(winrt::hstring const &,std::vector<winrt::hstring,std::allocator<winrt::hstring>> const &,bool)

- ea: `0x14005add4`
- end: `0x14005b05f`
- name: `?SetShellHostProperties@ShellHostHelpers@@YAXAEBUhstring@winrt@@AEBV?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@_N@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140059d70`

## callees

- `0x14000b420`
- `0x14004eb14`
- `0x14004ebf4`
- `0x14004f5cc`
- `0x140052594`
- `0x140052954`
- `0x140052bf8`
- `0x1400544d0`
- `0x1400579a8`
- `0x14005ac30`
- `0x14005add4`
- `0x14005d1a8`
- `0x14005d614`
- `0x14005d654`
- `0x14005fcbc`
- `0x14005fcdc`
- `0x140067010`

## import_xrefs

- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x14005af44`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x14005af44`
- `twinapi.appcore!__imp_CoreRegisterApplicationService` at `0x14005affd`
- `twinapi.appcore!__imp_CoreRegisterApplicationService` at `0x14005affd`
- `twinapi.appcore!__imp_CoreUnregisterApplicationService` at `0x14005af98`
- `twinapi.appcore!__imp_CoreUnregisterApplicationService` at `0x14005af98`

## string_xrefs

- `0x14005b04d`: `shellcommon\internal\shell\inc\ValueSetUtils.h`
- `0x14005b038`: `shellcommon\internal\shell\inc\ShellHostHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ShellHostHelpers::SetShellHostProperties(_QWORD *a1, __int64 *a2, char a3)
{
  __int64 v5; // rcx
  struct IInspectableVtbl *lpVtbl; // rbx
  __int64 v7; // rbx
  int v8; // eax
  __int64 *v9; // rbx
  unsigned int v10; // eax
  int v11; // eax
  int v12[4]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  __int128 v14; // [rsp+38h] [rbp-38h]
  _QWORD v15[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int64 *v17; // [rsp+90h] [rbp+20h] BYREF
  char v18; // [rsp+98h] [rbp+28h] BYREF
  char v19; // [rsp+A0h] [rbp+30h] BYREF
  __int64 *v20; // [rsp+A8h] [rbp+38h] BYREF

  v19 = a3;
  winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)&v18);
  v13 = *a2;
  LODWORD(v14) = (a2[1] - v13) >> 3;
  v20 = &v13;
  *(_QWORD *)v12 = &qword_140083958;
  _InterlockedIncrement64(&qword_140083958);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> )
  {
    _lambda_ee1a3feb73dd4935dd100918ed2c0202_::operator()(
      &v20,
      &v17,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
    _InterlockedDecrement64(&qword_140083958);
  }
  else
  {
    _InterlockedDecrement64(&qword_140083958);
    winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_ee1a3feb73dd4935dd100918ed2c0202_ &>(
      v5,
      &v17,
      &v20);
  }
  winrt::param::hstring::hstring(v15, &ShellHostHelpers::details::PropertyKeys::HostedShellComponents);
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
    &v18,
    v15,
    &v17);
  if ( v17 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v17);
  if ( *a1 )
  {
    v15[0] = *a1;
    lpVtbl = winrt::box_value((winrt *)&v17, (const struct winrt::param::hstring *)v15).lpVtbl;
    winrt::param::hstring::hstring(&v13, &ShellHostHelpers::details::PropertyKeys::InstanceName);
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
      &v18,
      &v13,
      lpVtbl);
    if ( v17 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v17);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
  {
    v7 = winrt::box_value<bool,0>(&v17, &v19);
    winrt::param::hstring::hstring(v15, &ShellHostHelpers::details::PropertyKeys::KeepAlive);
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
      &v18,
      v15,
      v7);
    if ( v17 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v17);
  }
  v17 = 0;
  v8 = RoCreatePropertySetSerializer(&v17);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetUtils.h",
      (const char *)(unsigned int)v8,
      v12[0]);
  winrt::com_ptr<Windows::Storage::Streams::IPropertySetSerializer>::as<winrt::Windows::Storage::Streams::IPropertySetSerializer>(
    &v17,
    &v20);
  winrt::impl::consume_Windows_Storage_Streams_IPropertySetSerializer<winrt::Windows::Storage::Streams::IPropertySetSerializer>::Serialize(
    &v20,
    v12,
    &v18);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v20);
  if ( v17 )
    winrt::com_ptr<IUnknown>::unconditional_release_ref(&v17);
  CoreUnregisterApplicationService(&ShellHostHelpers::details::SID_ShellHostProperties);
  if ( *(_QWORD *)v12 )
  {
    v20 = 0;
    LODWORD(v13) = 0;
    v14 = 0;
    v10 = (***(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 **))v12)(
            *(_QWORD *)v12,
            winrt::impl::guid_v<Windows::Storage::Streams::IBuffer>,
            &v20);
    winrt::check_hresult(&v17, v10, &v13);
    v9 = v20;
    v17 = v20;
  }
  else
  {
    v17 = 0;
    v9 = 0;
  }
  v11 = CoreRegisterApplicationService(&ShellHostHelpers::details::SID_ShellHostProperties, v9);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\ShellHostHelpers.h",
      (const char *)(unsigned int)v11,
      v12[0]);
  if ( v9 )
    winrt::com_ptr<IUnknown>::unconditional_release_ref(&v17);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)v12);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v18);
}

```

## disassembly

```asm
0x14005add4  mov     [rsp-18h+arg_10], r8b
0x14005add9  push    rbp
0x14005adda  push    rbx
0x14005addb  push    rdi
0x14005addc  mov     rbp, rsp
0x14005addf  sub     rsp, 70h
0x14005ade3  mov     rbx, rdx
0x14005ade6  mov     rdi, rcx
0x14005ade9  lea     rcx, [rbp+arg_8]; this
0x14005aded  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x14005adf2  nop
0x14005adf3  mov     rax, [rbx]
0x14005adf6  mov     [rbp+var_40], rax
0x14005adfa  mov     rdx, [rbx+8]
0x14005adfe  sub     rdx, rax
0x14005ae01  sar     rdx, 3
0x14005ae05  mov     dword ptr [rbp+var_38], edx
0x14005ae08  mov     eax, dword ptr [rbp+var_38+4]
0x14005ae0b  mov     dword ptr [rbp+var_38+4], eax
0x14005ae0e  lea     rax, [rbp+var_40]
0x14005ae12  mov     [rbp+arg_18], rax
0x14005ae16  lea     rax, qword_140083958
0x14005ae1d  mov     qword ptr [rbp+var_50], rax
0x14005ae21  lock inc cs:qword_140083958
0x14005ae29  cmp     cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, 0; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14005ae31  jz      short loc_14005AE52
0x14005ae33  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14005ae3a  lea     rdx, [rbp+arg_0]
0x14005ae3e  lea     rcx, [rbp+arg_18]
0x14005ae42  call    ??R_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_ee1a3feb73dd4935dd100918ed2c0202_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x14005ae47  nop
0x14005ae48  lock dec cs:qword_140083958
0x14005ae50  jmp     short loc_14005AE68
0x14005ae52  lock dec cs:qword_140083958
0x14005ae5a  lea     r8, [rbp+arg_18]
0x14005ae5e  lea     rdx, [rbp+arg_0]
0x14005ae62  call    ??$call@AEAV_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_ee1a3feb73dd4935dd100918ed2c0202_@@@Z
0x14005ae67  nop
0x14005ae68  lea     rdx, ?HostedShellComponents@PropertyKeys@details@ShellHostHelpers@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const ShellHostHelpers::details::PropertyKeys::HostedShellComponents
0x14005ae6f  lea     rcx, [rbp+var_20]
0x14005ae73  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14005ae78  lea     r8, [rbp+arg_0]
0x14005ae7c  lea     rdx, [rbp+var_20]
0x14005ae80  lea     rcx, [rbp+arg_8]
0x14005ae84  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x14005ae89  nop
0x14005ae8a  cmp     [rbp+arg_0], 0
0x14005ae8f  jz      short loc_14005AE9A
0x14005ae91  lea     rcx, [rbp+arg_0]
0x14005ae95  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14005ae9a  mov     rax, [rdi]
0x14005ae9d  test    rax, rax
0x14005aea0  jz      short loc_14005AEE7
0x14005aea2  mov     [rbp+var_20], rax
0x14005aea6  lea     rdx, [rbp+var_20]; struct winrt::param::hstring *
0x14005aeaa  lea     rcx, [rbp+arg_0]; this
0x14005aeae  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x14005aeb3  mov     rbx, rax
0x14005aeb6  lea     rdx, ?InstanceName@PropertyKeys@details@ShellHostHelpers@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const ShellHostHelpers::details::PropertyKeys::InstanceName
0x14005aebd  lea     rcx, [rbp+var_40]
0x14005aec1  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14005aec6  mov     r8, rbx
0x14005aec9  lea     rdx, [rbp+var_40]
0x14005aecd  lea     rcx, [rbp+arg_8]
0x14005aed1  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x14005aed6  nop
0x14005aed7  cmp     [rbp+arg_0], 0
0x14005aedc  jz      short loc_14005AEE7
0x14005aede  lea     rcx, [rbp+arg_0]
0x14005aee2  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14005aee7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x14005aeee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x14005aef3  test    al, al
0x14005aef5  jz      short loc_14005AF38
0x14005aef7  lea     rdx, [rbp+arg_10]
0x14005aefb  lea     rcx, [rbp+arg_0]
0x14005aeff  call    ??$box_value@_N$0A@@winrt@@YA?AUIInspectable@Foundation@Windows@0@AEB_N@Z; winrt::box_value<bool,0>(bool const &)
0x14005af04  mov     rbx, rax
0x14005af07  lea     rdx, ?KeepAlive@PropertyKeys@details@ShellHostHelpers@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const ShellHostHelpers::details::PropertyKeys::KeepAlive
0x14005af0e  lea     rcx, [rbp+var_20]
0x14005af12  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14005af17  mov     r8, rbx
0x14005af1a  lea     rdx, [rbp+var_20]
0x14005af1e  lea     rcx, [rbp+arg_8]
0x14005af22  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x14005af27  nop
0x14005af28  cmp     [rbp+arg_0], 0
0x14005af2d  jz      short loc_14005AF38
0x14005af2f  lea     rcx, [rbp+arg_0]
0x14005af33  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14005af38  mov     [rbp+arg_0], 0
0x14005af40  lea     rcx, [rbp+arg_0]
0x14005af44  call    cs:__imp_RoCreatePropertySetSerializer
0x14005af4a  mov     rcx, [rbp+18h]; this
0x14005af4e  test    eax, eax
0x14005af50  js      loc_14005B04A
0x14005af56  lea     rdx, [rbp+arg_18]
0x14005af5a  lea     rcx, [rbp+arg_0]
0x14005af5e  call    ??$as@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@?$com_ptr@UIPropertySetSerializer@Streams@Storage@Windows@@@winrt@@QEBA?A_PXZ
0x14005af63  nop
0x14005af64  lea     r8, [rbp+arg_8]
0x14005af68  lea     rdx, [rbp+var_50]
0x14005af6c  lea     rcx, [rbp+arg_18]
0x14005af70  call    ?Serialize@?$consume_Windows_Storage_Streams_IPropertySetSerializer@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBUIPropertySet@Collections@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Storage_Streams_IPropertySetSerializer<winrt::Windows::Storage::Streams::IPropertySetSerializer>::Serialize(winrt::Windows::Foundation::Collections::IPropertySet const &)
0x14005af75  nop
0x14005af76  lea     rcx, [rbp+arg_18]; this
0x14005af7a  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005af7f  nop
0x14005af80  cmp     [rbp+arg_0], 0
0x14005af85  jz      short loc_14005AF91
0x14005af87  lea     rcx, [rbp+arg_0]
0x14005af8b  call    ?unconditional_release_ref@?$com_ptr@UIUnknown@@@winrt@@AEAAXXZ; winrt::com_ptr<IUnknown>::unconditional_release_ref(void)
0x14005af90  nop
0x14005af91  lea     rcx, ?SID_ShellHostProperties@details@ShellHostHelpers@@3U_GUID@@B; _GUID const ShellHostHelpers::details::SID_ShellHostProperties
0x14005af98  call    cs:__imp_CoreUnregisterApplicationService
0x14005af9e  mov     rcx, qword ptr [rbp+var_50]
0x14005afa2  test    rcx, rcx
0x14005afa5  jnz     short loc_14005AFAF
0x14005afa7  mov     [rbp+arg_0], rcx
0x14005afab  xor     ebx, ebx
0x14005afad  jmp     short loc_14005AFF3
0x14005afaf  mov     [rbp+arg_18], 0
0x14005afb7  mov     dword ptr [rbp+var_40], 0
0x14005afbe  xorps   xmm0, xmm0
0x14005afc1  movdqu  [rbp+var_38], xmm0
0x14005afc6  mov     rax, [rcx]
0x14005afc9  lea     r8, [rbp+arg_18]
0x14005afcd  lea     rdx, ??$guid_v@UIBuffer@Streams@Storage@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::Storage::Streams::IBuffer>
0x14005afd4  mov     rax, [rax]
0x14005afd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005afdc  lea     r8, [rbp+var_40]
0x14005afe0  mov     edx, eax
0x14005afe2  lea     rcx, [rbp+arg_0]
0x14005afe6  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005afeb  mov     rbx, [rbp+arg_18]
0x14005afef  mov     [rbp+arg_0], rbx
0x14005aff3  mov     rdx, rbx
0x14005aff6  lea     rcx, ?SID_ShellHostProperties@details@ShellHostHelpers@@3U_GUID@@B; _GUID const ShellHostHelpers::details::SID_ShellHostProperties
0x14005affd  call    cs:__imp_CoreRegisterApplicationService
0x14005b003  mov     rcx, [rbp+18h]; this
0x14005b007  test    eax, eax
0x14005b009  js      short loc_14005B035
0x14005b00b  test    rbx, rbx
0x14005b00e  jz      short loc_14005B01A
0x14005b010  lea     rcx, [rbp+arg_0]
0x14005b014  call    ?unconditional_release_ref@?$com_ptr@UIUnknown@@@winrt@@AEAAXXZ; winrt::com_ptr<IUnknown>::unconditional_release_ref(void)
0x14005b019  nop
0x14005b01a  lea     rcx, [rbp+var_50]; this
0x14005b01e  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005b023  nop
0x14005b024  lea     rcx, [rbp+arg_8]; this
0x14005b028  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005b02d  add     rsp, 70h
0x14005b031  pop     rdi
0x14005b032  pop     rbx
0x14005b033  pop     rbp
0x14005b034  retn
0x14005b035  mov     r9d, eax; char *
0x14005b038  lea     r8, aShellcommonInt_2; "shellcommon\\internal\\shell\\inc\\Shel"...
0x14005b03f  mov     edx, 135h; void *
0x14005b044  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14005b04a  mov     r9d, eax; char *
0x14005b04d  lea     r8, aShellcommonInt_1; "shellcommon\\internal\\shell\\inc\\Valu"...
0x14005b054  mov     edx, 0C5h; void *
0x14005b059  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
