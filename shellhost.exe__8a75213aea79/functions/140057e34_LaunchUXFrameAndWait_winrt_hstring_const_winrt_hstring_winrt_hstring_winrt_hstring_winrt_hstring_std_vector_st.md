# LaunchUXFrameAndWait(winrt::hstring const &,winrt::hstring &,winrt::hstring &,winrt::hstring &,winrt::hstring &,std::vector<std::pair<winrt::hstring,winrt::hstring>,std::allocator<std::pair<winrt::hstring,winrt::hstring>>> &,std::vector<std::pair<winrt::hstring,int>,std::allocator<std::pair<winrt::hstring,int>>> &,std::vector<std::pair<winrt::hstring,bool>,std::allocator<std::pair<winrt::hstring,bool>>> &,winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x140057e34`
- end: `0x14005824e`
- name: `?LaunchUXFrameAndWait@@YAXAEBUhstring@winrt@@AEAU12@111AEAV?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@H@std@@V?$allocator@U?$pair@Uhstring@winrt@@H@std@@@2@@4@AEAV?$vector@U?$pair@Uhstring@winrt@@_N@std@@V?$allocator@U?$pair@Uhstring@winrt@@_N@std@@@2@@4@AEBUValueSet@Collections@Foundation@Windows@2@@Z`
- size: `1050`
- prototype: `void __fastcall(struct winrt::hstring *, winrt::hstring *this, winrt::hstring *, winrt::hstring *, ValueSetUtils *, __int64, ValueSetUtils **, __int64, __int64)`
- caller_count: `3`
- callee_count: `29`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140053fcc`
- `0x140057370`
- `0x140057574`

## callees

- `0x14000a310`
- `0x14000b420`
- `0x14000cc7c`
- `0x14004d2bc`
- `0x14004dc7c`
- `0x14004eb84`
- `0x14004ebf4`
- `0x14004f4b4`
- `0x1400504f8`
- `0x140051884`
- `0x1400518b4`
- `0x140052594`
- `0x1400529c8`
- `0x140052bf8`
- `0x140052fbc`
- `0x1400538ac`
- `0x140053948`
- `0x140054468`
- `0x140054a0c`
- `0x1400550d0`
- `0x1400574e0`
- `0x1400579a8`
- `0x140057e34`
- `0x14005ac94`
- `0x14005d3a4`
- `0x14005d5a4`
- `0x14005d614`
- `0x14005fcbc`
- `0x14005fcdc`

## string_xrefs

- `0x140057ead`: `ExtensionId`
- `0x140057e60`: `ExtensionCategory`

## pseudocode

```c
void __fastcall LaunchUXFrameAndWait(
        struct winrt::hstring *a1,
        winrt::hstring *this,
        winrt::hstring *a3,
        winrt::hstring *a4,
        ValueSetUtils *a5,
        __int64 a6,
        ValueSetUtils **a7,
        __int64 a8,
        __int64 a9)
{
  winrt::hstring *v13; // rax
  __int64 v14; // rdx
  winrt::hstring *v15; // rax
  __int64 v16; // rdx
  winrt::hstring *v17; // rax
  __int64 v18; // rdx
  const struct winrt::Windows::Foundation::Collections::ValueSet *v19; // r8
  __int64 v20; // rax
  ValueSetUtils *v21; // rcx
  _QWORD *v22; // rbx
  _QWORD *v23; // rdi
  struct IInspectable v24; // rax
  ValueSetUtils *v25; // rbx
  ValueSetUtils *v26; // rdi
  _QWORD *v27; // rbx
  _QWORD *v28; // rdi
  __int64 v29; // rax
  __int64 v30; // rcx
  void *v31; // rdx
  __int64 v32; // rcx
  _QWORD v33[4]; // [rsp+20h] [rbp-61h] BYREF
  _QWORD v34[4]; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v35[4]; // [rsp+60h] [rbp-21h] BYREF
  __int128 v36; // [rsp+80h] [rbp-1h]
  char v37; // [rsp+C8h] [rbp+47h] BYREF
  __int64 v38; // [rsp+D0h] [rbp+4Fh] BYREF
  __int64 *v39; // [rsp+D8h] [rbp+57h] BYREF

  if ( !*(_QWORD *)this )
  {
    winrt::hstring::hstring((winrt::hstring *)&v37, L"ExtensionCategory");
    v13 = (winrt::hstring *)ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(
                              &v39,
                              &v37,
                              a9);
    if ( this != v13 )
    {
      v14 = *(_QWORD *)v13;
      *(_QWORD *)v13 = 0;
      winrt::handle_type<winrt::impl::hstring_traits>::attach(this, v14);
    }
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v39);
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v37);
  }
  if ( !*(_QWORD *)a3 )
  {
    winrt::hstring::hstring((winrt::hstring *)&v37, L"ExtensionId");
    v15 = (winrt::hstring *)ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(
                              &v39,
                              &v37,
                              a9);
    if ( a3 != v15 )
    {
      v16 = *(_QWORD *)v15;
      *(_QWORD *)v15 = 0;
      winrt::handle_type<winrt::impl::hstring_traits>::attach(a3, v16);
    }
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v39);
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v37);
  }
  if ( !*(_QWORD *)a4 )
  {
    winrt::hstring::hstring((winrt::hstring *)&v37, L"ControlName");
    v17 = (winrt::hstring *)ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(
                              &v39,
                              &v37,
                              a9);
    if ( a4 != v17 )
    {
      v18 = *(_QWORD *)v17;
      *(_QWORD *)v17 = 0;
      winrt::handle_type<winrt::impl::hstring_traits>::attach(a4, v18);
    }
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v39);
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v37);
  }
  v36 = 0;
  v35[0] = winrt::hstring::c_str(a1);
  v35[1] = winrt::hstring::c_str(this);
  v35[2] = winrt::hstring::c_str(a3);
  v35[3] = winrt::hstring::c_str(a4);
  winrt::hstring::hstring((winrt::hstring *)&v39, L"InvocationProperties");
  ValueSetUtils::try_get_value<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::Collections::ValueSet>(
    &v37,
    &v39,
    a9);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v39);
  v39 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v37, &v39) )
  {
    v20 = winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)&v39);
    winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(&v37, v20);
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v39);
  }
  v21 = a5;
  if ( *(_QWORD *)a5 )
    ValueSetUtils::DeserializeBase64ValueSet(a5, (const struct winrt::hstring *)&v37, v19);
  v22 = *(_QWORD **)a6;
  v23 = *(_QWORD **)(a6 + 8);
  while ( v22 != v23 )
  {
    v33[0] = v22[1];
    v24.lpVtbl = winrt::box_value((winrt *)&a5, (const struct winrt::param::hstring *)v33).lpVtbl;
    v34[0] = *v22;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
      &v37,
      v34,
      v24.lpVtbl);
    if ( a5 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&a5);
    v22 += 2;
  }
  v25 = *a7;
  v26 = a7[1];
  while ( v25 != v26 )
  {
    LODWORD(a5) = *((_DWORD *)v25 + 2);
    a7 = &a5;
    v39 = &qword_140083958;
    _InterlockedIncrement64(&qword_140083958);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> )
    {
      _lambda_df12a01b87dd988dada7818cd16bb49c_::operator()(
        &a7,
        &a6,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>);
      _InterlockedDecrement64(&qword_140083958);
    }
    else
    {
      _InterlockedDecrement64(&qword_140083958);
      winrt::impl::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::call<_lambda_df12a01b87dd988dada7818cd16bb49c_ &>(
        v21,
        &a6,
        &a7);
    }
    v34[0] = *(_QWORD *)v25;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
      &v37,
      v34,
      &a6);
    if ( a6 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&a6);
    v25 = (ValueSetUtils *)((char *)v25 + 16);
  }
  v27 = *(_QWORD **)a8;
  v28 = *(_QWORD **)(a8 + 8);
  while ( v27 != v28 )
  {
    v29 = winrt::box_value<bool,0>(&a5, v27 + 1);
    v34[0] = *v27;
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
      &v37,
      v34,
      v29);
    if ( a5 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&a5);
    v27 += 2;
  }
  *(_QWORD *)&v36 = *(_QWORD *)winrt::Windows::Foundation::IUnknown::as<IUnknown>(&v37, &a5);
  if ( a5 )
    winrt::com_ptr<IUnknown>::unconditional_release_ref(&a5);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59697564>::GetImpl'::`2'::impl) )
  {
    *((_QWORD *)&v36 + 1) = *(_QWORD *)winrt::Windows::Foundation::IUnknown::as<IUnknown>(a9, &a5);
    if ( a5 )
      winrt::com_ptr<IUnknown>::unconditional_release_ref(&a5);
  }
  UXFrameHelpers::HandleLaunch(&v38, v35);
  if ( (unsigned __int64)(v38 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
    {
      std::list<ComponentRuntimeInfo>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,winrt::hstring const &>(
        v30,
        g_componentRuntimeInfoList,
        &v38,
        a1);
      if ( g_refreshWaitArrayEvent )
        wil::details::SetEvent((wil::details *)g_refreshWaitArrayEvent, v31);
    }
    else
    {
      wil::init_once<_lambda_4682ec432770a7550a78ed5777c152bb_>();
      DebugData::AddComponentId(DebugData::s_instance, a1);
      if ( *((_QWORD *)&g_componentWaitHandles + 1) == qword_140084198 )
      {
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
          v32,
          *((_QWORD *)&g_componentWaitHandles + 1),
          &v38);
      }
      else
      {
        **((_QWORD **)&g_componentWaitHandles + 1) = v38;
        v38 = 0;
        *((_QWORD *)&g_componentWaitHandles + 1) += 8LL;
      }
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v37);
}

```

## disassembly

```asm
0x140057e34  mov     [rsp-8+arg_0], rbx
0x140057e39  push    rbp
0x140057e3a  push    rsi
0x140057e3b  push    rdi
0x140057e3c  push    r12
0x140057e3e  push    r15
0x140057e40  lea     rbp, [rsp-0Fh]
0x140057e45  sub     rsp, 90h
0x140057e4c  mov     rbx, r9
0x140057e4f  mov     rdi, r8
0x140057e52  mov     rsi, rdx
0x140057e55  mov     r15, rcx
0x140057e58  xor     r12d, r12d
0x140057e5b  cmp     [rdx], r12
0x140057e5e  jnz     short loc_140057EA8
0x140057e60  lea     rdx, aExtensioncateg; "ExtensionCategory"
0x140057e67  lea     rcx, [rbp+2Fh+arg_8]; this
0x140057e6b  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x140057e70  nop
0x140057e71  mov     r8, [rbp+2Fh+arg_40]
0x140057e75  lea     rdx, [rbp+2Fh+arg_8]
0x140057e79  lea     rcx, [rbp+2Fh+arg_18]
0x140057e7d  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x140057e82  cmp     rsi, rax
0x140057e85  jz      short loc_140057E95
0x140057e87  mov     rdx, [rax]
0x140057e8a  mov     [rax], r12
0x140057e8d  mov     rcx, rsi
0x140057e90  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x140057e95  lea     rcx, [rbp+2Fh+arg_18]
0x140057e99  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057e9e  nop
0x140057e9f  lea     rcx, [rbp+2Fh+arg_8]
0x140057ea3  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057ea8  cmp     [rdi], r12
0x140057eab  jnz     short loc_140057EF5
0x140057ead  lea     rdx, aExtensionid_1; "ExtensionId"
0x140057eb4  lea     rcx, [rbp+2Fh+arg_8]; this
0x140057eb8  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x140057ebd  nop
0x140057ebe  mov     r8, [rbp+2Fh+arg_40]
0x140057ec2  lea     rdx, [rbp+2Fh+arg_8]
0x140057ec6  lea     rcx, [rbp+2Fh+arg_18]
0x140057eca  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x140057ecf  cmp     rdi, rax
0x140057ed2  jz      short loc_140057EE2
0x140057ed4  mov     rdx, [rax]
0x140057ed7  mov     [rax], r12
0x140057eda  mov     rcx, rdi
0x140057edd  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x140057ee2  lea     rcx, [rbp+2Fh+arg_18]
0x140057ee6  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057eeb  nop
0x140057eec  lea     rcx, [rbp+2Fh+arg_8]
0x140057ef0  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057ef5  cmp     [rbx], r12
0x140057ef8  jnz     short loc_140057F42
0x140057efa  lea     rdx, aControlname_1; "ControlName"
0x140057f01  lea     rcx, [rbp+2Fh+arg_8]; this
0x140057f05  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x140057f0a  nop
0x140057f0b  mov     r8, [rbp+2Fh+arg_40]
0x140057f0f  lea     rdx, [rbp+2Fh+arg_8]
0x140057f13  lea     rcx, [rbp+2Fh+arg_18]
0x140057f17  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x140057f1c  cmp     rbx, rax
0x140057f1f  jz      short loc_140057F2F
0x140057f21  mov     rdx, [rax]
0x140057f24  mov     [rax], r12
0x140057f27  mov     rcx, rbx
0x140057f2a  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x140057f2f  lea     rcx, [rbp+2Fh+arg_18]
0x140057f33  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057f38  nop
0x140057f39  lea     rcx, [rbp+2Fh+arg_8]
0x140057f3d  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057f42  xorps   xmm0, xmm0
0x140057f45  movdqu  [rbp+2Fh+var_50], xmm0
0x140057f4a  xorps   xmm1, xmm1
0x140057f4d  movdqu  [rbp+2Fh+var_40], xmm1
0x140057f52  movdqu  [rbp+2Fh+var_30], xmm0
0x140057f57  mov     rcx, r15; this
0x140057f5a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x140057f5f  mov     qword ptr [rbp+2Fh+var_50], rax
0x140057f63  mov     rcx, rsi; this
0x140057f66  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x140057f6b  mov     qword ptr [rbp+2Fh+var_50+8], rax
0x140057f6f  mov     rcx, rdi; this
0x140057f72  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x140057f77  mov     qword ptr [rbp+2Fh+var_40], rax
0x140057f7b  mov     rcx, rbx; this
0x140057f7e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x140057f83  mov     qword ptr [rbp+2Fh+var_40+8], rax
0x140057f87  lea     rdx, aInvocationprop; "InvocationProperties"
0x140057f8e  lea     rcx, [rbp+2Fh+arg_18]; this
0x140057f92  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x140057f97  nop
0x140057f98  mov     r8, [rbp+2Fh+arg_40]
0x140057f9c  lea     rdx, [rbp+2Fh+arg_18]
0x140057fa0  lea     rcx, [rbp+2Fh+arg_8]
0x140057fa4  call    ??$try_get_value@UValueSet@Collections@Foundation@Windows@winrt@@U12345@@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@5@AEBU12345@@Z; ValueSetUtils::try_get_value<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x140057fa9  nop
0x140057faa  lea     rcx, [rbp+2Fh+arg_18]
0x140057fae  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057fb3  mov     [rbp+2Fh+arg_18], r12
0x140057fb7  lea     rdx, [rbp+2Fh+arg_18]
0x140057fbb  lea     rcx, [rbp+2Fh+arg_8]
0x140057fbf  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x140057fc4  test    al, al
0x140057fc6  jz      short loc_140057FE6
0x140057fc8  lea     rcx, [rbp+2Fh+arg_18]; this
0x140057fcc  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x140057fd1  mov     rdx, rax
0x140057fd4  lea     rcx, [rbp+2Fh+arg_8]
0x140057fd8  call    ??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)
0x140057fdd  lea     rcx, [rbp+2Fh+arg_18]; this
0x140057fe1  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140057fe6  mov     rcx, [rbp+2Fh+arg_20]; this
0x140057fea  cmp     [rcx], r12
0x140057fed  jz      short loc_140057FF8
0x140057fef  lea     rdx, [rbp+2Fh+arg_8]; struct winrt::hstring *
0x140057ff3  call    ?DeserializeBase64ValueSet@ValueSetUtils@@YAXAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; ValueSetUtils::DeserializeBase64ValueSet(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x140057ff8  mov     rax, [rbp+2Fh+arg_28]
0x140057ffc  mov     rbx, [rax]
0x140057fff  mov     rdi, [rax+8]
0x140058003  jmp     short loc_140058046
0x140058005  mov     rax, [rbx+8]
0x140058009  mov     [rbp+2Fh+var_90], rax
0x14005800d  lea     rdx, [rbp+2Fh+var_90]; struct winrt::param::hstring *
0x140058011  lea     rcx, [rbp+2Fh+arg_20]; this
0x140058015  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x14005801a  nop
0x14005801b  mov     rcx, [rbx]
0x14005801e  mov     [rbp+2Fh+var_70], rcx
0x140058022  mov     r8, rax
0x140058025  lea     rdx, [rbp+2Fh+var_70]
0x140058029  lea     rcx, [rbp+2Fh+arg_8]
0x14005802d  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x140058032  nop
0x140058033  cmp     [rbp+2Fh+arg_20], r12
0x140058037  jz      short loc_140058042
0x140058039  lea     rcx, [rbp+2Fh+arg_20]
0x14005803d  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140058042  add     rbx, 10h
0x140058046  cmp     rbx, rdi
0x140058049  jnz     short loc_140058005
0x14005804b  mov     rax, [rbp+2Fh+arg_30]
0x14005804f  mov     rbx, [rax]
0x140058052  mov     rdi, [rax+8]
0x140058056  jmp     loc_1400580E6
0x14005805b  mov     eax, [rbx+8]
0x14005805e  mov     dword ptr [rbp+2Fh+arg_20], eax
0x140058061  lea     rax, [rbp+2Fh+arg_20]
0x140058065  mov     [rbp+2Fh+arg_30], rax
0x140058069  lea     rax, qword_140083958
0x140058070  mov     [rbp+2Fh+arg_18], rax
0x140058074  lock inc cs:qword_140083958
0x14005807c  cmp     cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, r12; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x140058083  jz      short loc_1400580A4
0x140058085  lea     r8, ??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x14005808c  lea     rdx, [rbp+2Fh+arg_28]
0x140058090  lea     rcx, [rbp+2Fh+arg_30]
0x140058094  call    ??R_lambda_df12a01b87dd988dada7818cd16bb49c_@@QEBA@AEBUIPropertyValueStatics@Foundation@Windows@winrt@@@Z; _lambda_df12a01b87dd988dada7818cd16bb49c_::operator()(winrt::Windows::Foundation::IPropertyValueStatics const &)
0x140058099  nop
0x14005809a  lock dec cs:qword_140083958
0x1400580a2  jmp     short loc_1400580BA
0x1400580a4  lock dec cs:qword_140083958
0x1400580ac  lea     r8, [rbp+2Fh+arg_30]
0x1400580b0  lea     rdx, [rbp+2Fh+arg_28]
0x1400580b4  call    ??$call@AEAV_lambda_df12a01b87dd988dada7818cd16bb49c_@@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_df12a01b87dd988dada7818cd16bb49c_@@@Z
0x1400580b9  nop
0x1400580ba  mov     rax, [rbx]
0x1400580bd  mov     [rbp+2Fh+var_70], rax
0x1400580c1  lea     r8, [rbp+2Fh+arg_28]
0x1400580c5  lea     rdx, [rbp+2Fh+var_70]
0x1400580c9  lea     rcx, [rbp+2Fh+arg_8]
0x1400580cd  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x1400580d2  nop
0x1400580d3  cmp     [rbp+2Fh+arg_28], r12
0x1400580d7  jz      short loc_1400580E2
0x1400580d9  lea     rcx, [rbp+2Fh+arg_28]
0x1400580dd  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1400580e2  add     rbx, 10h
0x1400580e6  cmp     rbx, rdi
0x1400580e9  jnz     loc_14005805B
0x1400580ef  mov     rax, [rbp+2Fh+arg_38]
0x1400580f3  mov     rbx, [rax]
0x1400580f6  mov     rdi, [rax+8]
0x1400580fa  jmp     short loc_140058135
0x1400580fc  lea     rdx, [rbx+8]
0x140058100  lea     rcx, [rbp+2Fh+arg_20]
0x140058104  call    ??$box_value@_N$0A@@winrt@@YA?AUIInspectable@Foundation@Windows@0@AEB_N@Z; winrt::box_value<bool,0>(bool const &)
0x140058109  nop
0x14005810a  mov     rcx, [rbx]
0x14005810d  mov     [rbp+2Fh+var_70], rcx
0x140058111  mov     r8, rax
0x140058114  lea     rdx, [rbp+2Fh+var_70]
0x140058118  lea     rcx, [rbp+2Fh+arg_8]
0x14005811c  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x140058121  nop
0x140058122  cmp     [rbp+2Fh+arg_20], r12
0x140058126  jz      short loc_140058131
0x140058128  lea     rcx, [rbp+2Fh+arg_20]
0x14005812c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140058131  add     rbx, 10h
0x140058135  cmp     rbx, rdi
0x140058138  jnz     short loc_1400580FC
0x14005813a  lea     rdx, [rbp+2Fh+arg_20]
0x14005813e  lea     rcx, [rbp+2Fh+arg_8]
0x140058142  call    ??$as@UIUnknown@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x140058147  mov     rcx, [rax]
0x14005814a  mov     qword ptr [rbp+2Fh+var_30], rcx
0x14005814e  cmp     [rbp+2Fh+arg_20], r12
0x140058152  jz      short loc_14005815D
0x140058154  lea     rcx, [rbp+2Fh+arg_20]
0x140058158  call    ?unconditional_release_ref@?$com_ptr@UIUnknown@@@winrt@@AEAAXXZ; winrt::com_ptr<IUnknown>::unconditional_release_ref(void)
0x14005815d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59697564@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564> `wil::Feature<__WilFeatureTraits_Feature_59697564>::GetImpl(void)'::`2'::impl
0x140058164  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59697564@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59697564>::__private_IsEnabled(void)
0x140058169  test    al, al
0x14005816b  jz      short loc_140058190
0x14005816d  lea     rdx, [rbp+2Fh+arg_20]
0x140058171  mov     rcx, [rbp+2Fh+arg_40]
0x140058175  call    ??$as@UIUnknown@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x14005817a  mov     rcx, [rax]
0x14005817d  mov     qword ptr [rbp+2Fh+var_30+8], rcx
0x140058181  cmp     [rbp+2Fh+arg_20], r12
0x140058185  jz      short loc_140058190
0x140058187  lea     rcx, [rbp+2Fh+arg_20]
0x14005818b  call    ?unconditional_release_ref@?$com_ptr@UIUnknown@@@winrt@@AEAAXXZ; winrt::com_ptr<IUnknown>::unconditional_release_ref(void)
0x140058190  lea     rdx, [rbp+2Fh+var_50]
0x140058194  lea     rcx, [rbp+2Fh+arg_10]
0x140058198  call    ?HandleLaunch@UXFrameHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUUXFrameArgs@1@@Z; UXFrameHelpers::HandleLaunch(UXFrameHelpers::UXFrameArgs const &)
0x14005819d  nop
0x14005819e  mov     rax, [rbp+2Fh+arg_10]
0x1400581a2  dec     rax
0x1400581a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400581a9  ja      short loc_140058224
0x1400581ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x1400581b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x1400581b7  test    al, al
0x1400581b9  jz      short loc_1400581E1
0x1400581bb  mov     r9, r15
0x1400581be  lea     r8, [rbp+2Fh+arg_10]
0x1400581c2  mov     rdx, cs:?g_componentRuntimeInfoList@@3V?$list@UComponentRuntimeInfo@@V?$allocator@UComponentRuntimeInfo@@@std@@@std@@A; std::list<ComponentRuntimeInfo> g_componentRuntimeInfoList
0x1400581c9  call    ??$_Emplace@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUhstring@winrt@@@?$list@UComponentRuntimeInfo@@V?$allocator@UComponentRuntimeInfo@@@std@@@std@@QEAAPEAU?$_List_node@UComponentRuntimeInfo@@PEAX@1@QEAU21@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBUhstring@winrt@@@Z; std::list<ComponentRuntimeInfo>::_Emplace<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,winrt::hstring const &>(std::_List_node<ComponentRuntimeInfo,void *> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,winrt::hstring const &)
0x1400581ce  mov     rcx, cs:?g_refreshWaitArrayEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; this
0x1400581d5  test    rcx, rcx
0x1400581d8  jz      short loc_140058224
0x1400581da  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1400581df  jmp     short loc_140058224
0x1400581e1  call    ??$init_once@V_lambda_4682ec432770a7550a78ed5777c152bb_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_4682ec432770a7550a78ed5777c152bb_@@@Z; wil::init_once<_lambda_4682ec432770a7550a78ed5777c152bb_>(_RTL_RUN_ONCE &,_lambda_4682ec432770a7550a78ed5777c152bb_)
0x1400581e6  mov     rdx, r15; struct winrt::hstring *
0x1400581e9  mov     rcx, cs:?s_instance@DebugData@@0PEAV1@EA; SRWLock
0x1400581f0  call    ?AddComponentId@DebugData@@QEAAXAEBUhstring@winrt@@@Z; DebugData::AddComponentId(winrt::hstring const &)
0x1400581f5  mov     rdx, qword ptr cs:?g_componentWaitHandles@@3V?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@A+8; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> g_componentWaitHandles
0x1400581fc  cmp     rdx, cs:qword_140084198
0x140058203  jz      short loc_14005821A
0x140058205  mov     rax, [rbp+2Fh+arg_10]
0x140058209  mov     [rdx], rax
0x14005820c  mov     [rbp+2Fh+arg_10], r12
0x140058210  add     qword ptr cs:?g_componentWaitHandles@@3V?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@A+8, 8; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> g_componentWaitHandles
0x140058218  jmp     short loc_140058224
0x14005821a  lea     r8, [rbp+2Fh+arg_10]
0x14005821e  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140058223  nop
0x140058224  lea     rcx, [rbp+2Fh+arg_10]
0x140058228  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14005822d  nop
0x14005822e  lea     rcx, [rbp+2Fh+arg_8]; this
0x140058232  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140058237  mov     rbx, [rsp+0B0h+arg_0]
0x14005823f  add     rsp, 90h
0x140058246  pop     r15
0x140058248  pop     r12
0x14005824a  pop     rdi
0x14005824b  pop     rsi
0x14005824c  pop     rbp
0x14005824d  retn
```
