# TryClaimSingletonOrRedirectLaunchIfNecessary(winrt::hstring const &,ushort const *)

- ea: `0x14005b72c`
- end: `0x14005b8b6`
- name: `?TryClaimSingletonOrRedirectLaunchIfNecessary@@YA_NAEBUhstring@winrt@@PEBG@Z`
- size: `394`
- prototype: `char __fastcall(const struct winrt::hstring *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140053d50`
- `0x14005c9a0`
- `0x14005c9f0`

## callees

- `0x14000ab88`
- `0x14000b404`
- `0x14000cc7c`
- `0x14004c7f8`
- `0x14004c83c`
- `0x14004cbac`
- `0x14004ce3c`
- `0x1400504f8`
- `0x1400508ac`
- `0x140052594`
- `0x140052954`
- `0x140052978`
- `0x140052bf8`
- `0x1400579a8`
- `0x14005acc0`
- `0x14005b34c`
- `0x14005b72c`
- `0x14005d614`
- `0x14005ead0`
- `0x14005fcbc`

## pseudocode

```c
char __fastcall TryClaimSingletonOrRedirectLaunchIfNecessary(
        const struct winrt::hstring *a1,
        const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  struct IInspectableVtbl *lpVtbl; // rbx
  int v9; // eax
  char v10; // bl
  _BYTE v12[32]; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v13[8]; // [rsp+40h] [rbp-40h] BYREF
  char v14; // [rsp+A0h] [rbp+20h] BYREF
  const unsigned __int16 *v15; // [rsp+B0h] [rbp+30h] BYREF
  char v16; // [rsp+B8h] [rbp+38h] BYREF

  if ( !*(_QWORD *)a1 || g_singletonHelper )
    return 1;
  v15 = winrt::hstring::c_str(a1);
  ShellHostTelemetry::TryingToClaimSingleton<unsigned short const *>(&v15);
  wil::init_once<_lambda_4682ec432770a7550a78ed5777c152bb_>();
  DebugData::SetInstanceName((DebugData *)DebugData::s_instance, a1);
  v15 = winrt::hstring::c_str(a1);
  v5 = (__int64 *)std::make_unique<SingletonHelpers::SingletonHelper,wil::basic_zstring_view<unsigned short> const &,unsigned short const *,0>(
                    &v16,
                    v4,
                    &v15);
  v6 = *v5;
  *v5 = 0;
  std::unique_ptr<SingletonHelpers::SingletonHelper>::reset(v7, v6);
  std::unique_ptr<SingletonHelpers::SingletonHelper>::~unique_ptr<SingletonHelpers::SingletonHelper>(&v16);
  winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)&v14);
  winrt::param::hstring::hstring((winrt::param::hstring *)v12, a2);
  lpVtbl = winrt::box_value((winrt *)&v15, (const struct winrt::param::hstring *)v12).lpVtbl;
  winrt::param::hstring::hstring(v13, &off_14006A528);
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(
    &v14,
    v13,
    lpVtbl);
  if ( v15 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v15);
  v9 = SingletonHelpers::SingletonHelper::TryClaimSingletonOrRedirectLaunch(g_singletonHelper, &v14);
  v10 = 1;
  if ( v9 == 1 )
  {
    v15 = winrt::hstring::c_str(a1);
    ShellHostTelemetry::RedirectedToOtherInstance<unsigned short const *>(&v15);
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v14);
    return 0;
  }
  else
  {
    if ( v9 == 2 )
    {
      v15 = winrt::hstring::c_str(a1);
      ShellHostTelemetry::FailedToRedirect<unsigned short const *>(&v15);
      v10 = 0;
    }
    else
    {
      v13[0] = off_14006A030;
      v13[7] = v13;
      SingletonHelpers::SingletonHelper::RegisterForRedirectedLaunches(g_singletonHelper, v13);
      v15 = winrt::hstring::c_str(a1);
      ShellHostTelemetry::ClaimedSingleton<unsigned short const *>(&v15);
    }
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v14);
    return v10;
  }
}

```

## disassembly

```asm
0x14005b72c  push    rbp
0x14005b72e  push    rbx
0x14005b72f  push    rdi
0x14005b730  mov     rbp, rsp
0x14005b733  sub     rsp, 80h
0x14005b73a  mov     rbx, rdx
0x14005b73d  mov     rdi, rcx
0x14005b740  cmp     qword ptr [rcx], 0
0x14005b744  jz      loc_14005B8A6
0x14005b74a  cmp     cs:?g_singletonHelper@@3V?$unique_ptr@VSingletonHelper@SingletonHelpers@@U?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@@std@@A, 0; std::unique_ptr<SingletonHelpers::SingletonHelper> g_singletonHelper
0x14005b752  jnz     loc_14005B8A6
0x14005b758  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14005b75d  mov     [rbp+arg_10], rax
0x14005b761  lea     rcx, [rbp+arg_10]
0x14005b765  call    ??$TryingToClaimSingleton@PEBG@ShellHostTelemetry@@SAX$$QEAPEBG@Z; ShellHostTelemetry::TryingToClaimSingleton<ushort const *>(ushort const * &&)
0x14005b76a  call    ??$init_once@V_lambda_4682ec432770a7550a78ed5777c152bb_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_4682ec432770a7550a78ed5777c152bb_@@@Z; wil::init_once<_lambda_4682ec432770a7550a78ed5777c152bb_>(_RTL_RUN_ONCE &,_lambda_4682ec432770a7550a78ed5777c152bb_)
0x14005b76f  mov     rdx, rdi; struct winrt::hstring *
0x14005b772  mov     rcx, cs:?s_instance@DebugData@@0PEAV1@EA; this
0x14005b779  call    ?SetInstanceName@DebugData@@QEAAXAEBUhstring@winrt@@@Z; DebugData::SetInstanceName(winrt::hstring const &)
0x14005b77e  mov     rcx, rdi; this
0x14005b781  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14005b786  mov     [rbp+arg_10], rax
0x14005b78a  lea     r8, [rbp+arg_10]
0x14005b78e  lea     rcx, [rbp+arg_18]
0x14005b792  call    ??$make_unique@VSingletonHelper@SingletonHelpers@@AEBV?$basic_zstring_view@G@wil@@PEBG$0A@@std@@YA?AV?$unique_ptr@VSingletonHelper@SingletonHelpers@@U?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@@0@AEBV?$basic_zstring_view@G@wil@@$$QEAPEBG@Z; std::make_unique<SingletonHelpers::SingletonHelper,wil::basic_zstring_view<ushort> const &,ushort const *,0>(wil::basic_zstring_view<ushort> const &,ushort const * &&)
0x14005b797  mov     rdx, [rax]
0x14005b79a  mov     qword ptr [rax], 0
0x14005b7a1  call    ?reset@?$unique_ptr@VSingletonHelper@SingletonHelpers@@U?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@@std@@QEAAXPEAVSingletonHelper@SingletonHelpers@@@Z; std::unique_ptr<SingletonHelpers::SingletonHelper>::reset(SingletonHelpers::SingletonHelper *)
0x14005b7a6  lea     rcx, [rbp+arg_18]
0x14005b7aa  call    ??1?$unique_ptr@VSingletonHelper@SingletonHelpers@@U?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@@std@@QEAA@XZ; std::unique_ptr<SingletonHelpers::SingletonHelper>::~unique_ptr<SingletonHelpers::SingletonHelper>(void)
0x14005b7af  lea     rcx, [rbp+arg_0]; this
0x14005b7b3  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x14005b7b8  nop
0x14005b7b9  mov     rdx, rbx; unsigned __int16 *
0x14005b7bc  lea     rcx, [rbp+var_60]; this
0x14005b7c0  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x14005b7c5  lea     rdx, [rbp+var_60]; struct winrt::param::hstring *
0x14005b7c9  lea     rcx, [rbp+arg_10]; this
0x14005b7cd  call    ?box_value@winrt@@YA?AUIInspectable@Foundation@Windows@1@AEBUhstring@param@1@@Z; winrt::box_value(winrt::param::hstring const &)
0x14005b7d2  mov     rbx, rax
0x14005b7d5  lea     rdx, off_14006A528; "CommandLine"
0x14005b7dc  lea     rcx, [rbp+var_40]
0x14005b7e0  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x14005b7e5  mov     r8, rbx
0x14005b7e8  lea     rdx, [rbp+var_40]
0x14005b7ec  lea     rcx, [rbp+arg_0]
0x14005b7f0  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUIInspectable@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Insert(winrt::param::hstring const &,winrt::Windows::Foundation::IInspectable const &)
0x14005b7f5  nop
0x14005b7f6  cmp     [rbp+arg_10], 0
0x14005b7fb  jz      short loc_14005B806
0x14005b7fd  lea     rcx, [rbp+arg_10]
0x14005b801  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x14005b806  lea     rdx, [rbp+arg_0]
0x14005b80a  mov     rcx, cs:?g_singletonHelper@@3V?$unique_ptr@VSingletonHelper@SingletonHelpers@@U?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@@std@@A; std::unique_ptr<SingletonHelpers::SingletonHelper> g_singletonHelper
0x14005b811  call    ?TryClaimSingletonOrRedirectLaunch@SingletonHelper@SingletonHelpers@@QEAA?AW4SingletonClaimResult@2@AEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_N@Z; SingletonHelpers::SingletonHelper::TryClaimSingletonOrRedirectLaunch(winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool)
0x14005b816  mov     ebx, 1
0x14005b81b  cmp     eax, ebx
0x14005b81d  jnz     short loc_14005B842
0x14005b81f  mov     rcx, rdi; this
0x14005b822  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14005b827  mov     [rbp+arg_10], rax
0x14005b82b  lea     rcx, [rbp+arg_10]
0x14005b82f  call    ??$RedirectedToOtherInstance@PEBG@ShellHostTelemetry@@SAX$$QEAPEBG@Z; ShellHostTelemetry::RedirectedToOtherInstance<ushort const *>(ushort const * &&)
0x14005b834  nop
0x14005b835  lea     rcx, [rbp+arg_0]; this
0x14005b839  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005b83e  xor     al, al
0x14005b840  jmp     short loc_14005B8AB
0x14005b842  cmp     eax, 2
0x14005b845  jnz     short loc_14005B860
0x14005b847  mov     rcx, rdi; this
0x14005b84a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14005b84f  mov     [rbp+arg_10], rax
0x14005b853  lea     rcx, [rbp+arg_10]
0x14005b857  call    ??$FailedToRedirect@PEBG@ShellHostTelemetry@@SAX$$QEAPEBG@Z; ShellHostTelemetry::FailedToRedirect<ushort const *>(ushort const * &&)
0x14005b85c  xor     bl, bl
0x14005b85e  jmp     short loc_14005B899
0x14005b860  lea     rax, off_14006A030
0x14005b867  mov     [rbp+var_40], rax
0x14005b86b  lea     rax, [rbp+var_40]
0x14005b86f  mov     [rbp+var_8], rax
0x14005b873  lea     rdx, [rbp+var_40]
0x14005b877  mov     rcx, cs:?g_singletonHelper@@3V?$unique_ptr@VSingletonHelper@SingletonHelpers@@U?$default_delete@VSingletonHelper@SingletonHelpers@@@std@@@std@@A; std::unique_ptr<SingletonHelpers::SingletonHelper> g_singletonHelper
0x14005b87e  call    ?RegisterForRedirectedLaunches@SingletonHelper@SingletonHelpers@@QEAAXV?$function@$$A6AXAEBUValueSet@Collections@Foundation@Windows@winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@std@@@Z; SingletonHelpers::SingletonHelper::RegisterForRedirectedLaunches(std::function<void (winrt::Windows::Foundation::Collections::ValueSet const &,std::wstring const &)>)
0x14005b883  mov     rcx, rdi; this
0x14005b886  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14005b88b  mov     [rbp+arg_10], rax
0x14005b88f  lea     rcx, [rbp+arg_10]
0x14005b893  call    ??$ClaimedSingleton@PEBG@ShellHostTelemetry@@SAX$$QEAPEBG@Z; ShellHostTelemetry::ClaimedSingleton<ushort const *>(ushort const * &&)
0x14005b898  nop
0x14005b899  lea     rcx, [rbp+arg_0]; this
0x14005b89d  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005b8a2  mov     al, bl
0x14005b8a4  jmp     short loc_14005B8AB
0x14005b8a6  mov     eax, 1
0x14005b8ab  add     rsp, 80h
0x14005b8b2  pop     rdi
0x14005b8b3  pop     rbx
0x14005b8b4  pop     rbp
0x14005b8b5  retn
```
