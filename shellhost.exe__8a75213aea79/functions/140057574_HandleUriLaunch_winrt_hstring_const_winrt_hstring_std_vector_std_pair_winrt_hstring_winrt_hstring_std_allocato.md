# HandleUriLaunch(winrt::hstring const &,winrt::hstring &,std::vector<std::pair<winrt::hstring,winrt::hstring>,std::allocator<std::pair<winrt::hstring,winrt::hstring>>> &,std::vector<std::pair<winrt::hstring,int>,std::allocator<std::pair<winrt::hstring,int>>> &,std::vector<std::pair<winrt::hstring,bool>,std::allocator<std::pair<winrt::hstring,bool>>> &)

- ea: `0x140057574`
- end: `0x1400577fb`
- name: `?HandleUriLaunch@@YAXAEBUhstring@winrt@@AEAU12@AEAV?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@H@std@@V?$allocator@U?$pair@Uhstring@winrt@@H@std@@@2@@4@AEAV?$vector@U?$pair@Uhstring@winrt@@_N@std@@V?$allocator@U?$pair@Uhstring@winrt@@_N@std@@@2@@4@@Z`
- size: `647`
- prototype: `__int64 __usercall@<rax>(winrt::hstring *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14005c9a0`

## callees

- `0x14000a310`
- `0x14000cc7c`
- `0x14004c040`
- `0x14004ec70`
- `0x14004fe34`
- `0x140051884`
- `0x1400529c8`
- `0x140052bf8`
- `0x140052e64`
- `0x140053ac4`
- `0x140057574`
- `0x140057e34`
- `0x140059c40`
- `0x14005b8bc`
- `0x14005d654`
- `0x14005e7d8`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140057660`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140057660`

## string_xrefs

- `0x1400576bf`: `SupportsProtocolLaunch`
- `0x1400576f0`: `UXFrameComponentDefinition`
- `0x140057693`: `com.microsoft.windows.extension.shellhost.component`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall HandleUriLaunch(winrt::hstring *this, ValueSetUtils *a2, __int64 a3, ValueSetUtils **a4, __int64 a5)
{
  unsigned int v9; // eax
  const WCHAR *v10; // rax
  int v11; // ebx
  char v12; // bl
  const unsigned __int16 *v13; // rax
  _QWORD *v14; // [rsp+50h] [rbp-41h] BYREF
  __int64 v15; // [rsp+58h] [rbp-39h] BYREF
  __int64 v16; // [rsp+60h] [rbp-31h] BYREF
  __int64 v17; // [rsp+68h] [rbp-29h] BYREF
  const wchar_t *v18; // [rsp+70h] [rbp-21h] BYREF
  __int128 v19; // [rsp+78h] [rbp-19h]
  _QWORD v20[11]; // [rsp+88h] [rbp-9h] BYREF
  _QWORD *v21; // [rsp+F0h] [rbp+5Fh] BYREF

  v20[0] = *(_QWORD *)this;
  v21 = v20;
  v17 = (__int64)&qword_140083978;
  _InterlockedIncrement64(&qword_140083978);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> )
  {
    _lambda_0a61d549bec6c444b35123f4c9509ca7_::operator()(
      &v21,
      &v16,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>);
    _InterlockedDecrement64(&qword_140083978);
  }
  else
  {
    _InterlockedDecrement64(&qword_140083978);
    winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
      this,
      &v16,
      &v21);
  }
  v14 = 0;
  LODWORD(v18) = 0;
  v19 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v16 + 136LL))(v16, &v14);
  winrt::check_hresult(&v21, v9, &v18);
  v21 = v14;
  v10 = winrt::hstring::c_str((winrt::hstring *)&v21);
  v11 = CompareStringOrdinal(v10, -1, c_shellHostUriScheme, -1, 1);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v21);
  if ( v11 == 2 )
  {
    winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(
      &v16,
      &v21);
    if ( v21 )
    {
      winrt::hstring::hstring((winrt::hstring *)&v14, L"com.microsoft.windows.extension.shellhost.component");
      ValueSetUtils::TryGetValueSetFromAppExtension((ValueSetUtils::details *)&v15, &v14, (winrt::hstring *)&v21);
      std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v14);
      winrt::hstring::hstring((winrt::hstring *)&v14, L"SupportsProtocolLaunch");
      v12 = ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(&v14, &v15);
      std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v14);
      if ( v12 )
      {
        winrt::hstring::hstring((winrt::hstring *)&v14, L"UXFrameComponentDefinition");
        ValueSetUtils::try_get_value<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::Collections::ValueSet>(
          &v17,
          &v14,
          &v15);
        std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v14);
        v13 = winrt::hstring::c_str(this);
        v18 = L"LaunchUri";
        *(_QWORD *)&v19 = v13;
        std::pair<winrt::hstring,winrt::hstring>::pair<winrt::hstring,winrt::hstring>(v20, &v18);
        std::vector<std::pair<winrt::hstring,winrt::hstring>>::push_back(a3, v20);
        std::pair<winrt::hstring,winrt::hstring>::~pair<winrt::hstring,winrt::hstring>(v20);
        v18 = 0;
        v20[0] = 0;
        v14 = 0;
        LaunchUXFrameAndWait(
          (struct winrt::hstring *)&v21,
          (winrt::hstring *)&v18,
          (winrt::hstring *)v20,
          (winrt::hstring *)&v14,
          a2,
          a3,
          a4,
          a5,
          (__int64)&v17);
        std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v14);
        std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(v20);
        std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v18);
        winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v17);
      }
      winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v15);
    }
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(&v21);
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v16);
}

```

## disassembly

```asm
0x140057574  push    rbp
0x140057576  push    rbx
0x140057577  push    rsi
0x140057578  push    rdi
0x140057579  push    r14
0x14005757b  push    r15
0x14005757d  lea     rbp, [rsp-27h]
0x140057582  sub     rsp, 0B8h
0x140057589  mov     r14, r9
0x14005758c  mov     rsi, r8
0x14005758f  mov     r15, rdx
0x140057592  mov     rdi, rcx
0x140057595  mov     rax, [rcx]
0x140057598  mov     [rbp+4Fh+var_58], rax
0x14005759c  lea     rax, [rbp+4Fh+var_58]
0x1400575a0  mov     [rbp+4Fh+arg_0], rax
0x1400575a4  lea     rax, qword_140083978
0x1400575ab  mov     [rbp+4Fh+var_78], rax
0x1400575af  lock inc cs:qword_140083978
0x1400575b7  cmp     cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A, 0; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x1400575bf  jz      short loc_1400575E0
0x1400575c1  lea     r8, ??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x1400575c8  lea     rdx, [rbp+4Fh+var_80]
0x1400575cc  lea     rcx, [rbp+4Fh+arg_0]
0x1400575d0  call    ??R_lambda_0a61d549bec6c444b35123f4c9509ca7_@@QEBA@AEBUIUriRuntimeClassFactory@Foundation@Windows@winrt@@@Z; _lambda_0a61d549bec6c444b35123f4c9509ca7_::operator()(winrt::Windows::Foundation::IUriRuntimeClassFactory const &)
0x1400575d5  nop
0x1400575d6  lock dec cs:qword_140083978
0x1400575de  jmp     short loc_1400575F6
0x1400575e0  lock dec cs:qword_140083978
0x1400575e8  lea     r8, [rbp+4Fh+arg_0]
0x1400575ec  lea     rdx, [rbp+4Fh+var_80]
0x1400575f0  call    ??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z
0x1400575f5  nop
0x1400575f6  mov     rbx, cs:?c_shellHostUriScheme@@3V?$basic_zstring_view@G@wil@@B; wil::basic_zstring_view<ushort> const c_shellHostUriScheme
0x1400575fd  mov     [rbp+4Fh+var_90], 0
0x140057605  mov     rcx, [rbp+4Fh+var_80]
0x140057609  mov     dword ptr [rbp+4Fh+var_70], 0
0x140057610  xorps   xmm0, xmm0
0x140057613  movdqu  [rbp+4Fh+var_68], xmm0
0x140057618  mov     rax, [rcx]
0x14005761b  lea     rdx, [rbp+4Fh+var_90]
0x14005761f  mov     rax, [rax+88h]
0x140057626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005762b  lea     r8, [rbp+4Fh+var_70]
0x14005762f  mov     edx, eax
0x140057631  lea     rcx, [rbp+4Fh+arg_0]
0x140057635  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005763a  mov     rax, [rbp+4Fh+var_90]
0x14005763e  mov     [rbp+4Fh+arg_0], rax
0x140057642  lea     rcx, [rbp+4Fh+arg_0]; this
0x140057646  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x14005764b  mov     rcx, rax; lpString1
0x14005764e  mov     [rsp+0E0h+bIgnoreCase], 1; bIgnoreCase
0x140057656  or      r9d, 0FFFFFFFFh; cchCount2
0x14005765a  mov     r8, rbx; lpString2
0x14005765d  or      edx, r9d; cchCount1
0x140057660  call    cs:__imp_CompareStringOrdinal
0x140057666  mov     ebx, eax
0x140057668  lea     rcx, [rbp+4Fh+arg_0]
0x14005766c  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057671  cmp     ebx, 2
0x140057674  jnz     loc_1400577E2
0x14005767a  lea     rdx, [rbp+4Fh+arg_0]
0x14005767e  lea     rcx, [rbp+4Fh+var_80]
0x140057682  call    ?Path@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::Path(void)
0x140057687  nop
0x140057688  cmp     [rbp+4Fh+arg_0], 0
0x14005768d  jz      loc_1400577D8
0x140057693  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.extension.shellho"...
0x14005769a  lea     rcx, [rbp+4Fh+var_90]; this
0x14005769e  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1400576a3  nop
0x1400576a4  lea     r8, [rbp+4Fh+arg_0]
0x1400576a8  lea     rdx, [rbp+4Fh+var_90]
0x1400576ac  lea     rcx, [rbp+4Fh+var_88]
0x1400576b0  call    ?TryGetValueSetFromAppExtension@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@6@0@Z; ValueSetUtils::TryGetValueSetFromAppExtension(winrt::hstring const &,winrt::hstring const &)
0x1400576b5  nop
0x1400576b6  lea     rcx, [rbp+4Fh+var_90]
0x1400576ba  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x1400576bf  lea     rdx, aSupportsprotoc; "SupportsProtocolLaunch"
0x1400576c6  lea     rcx, [rbp+4Fh+var_90]; this
0x1400576ca  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1400576cf  nop
0x1400576d0  lea     rdx, [rbp+4Fh+var_88]
0x1400576d4  lea     rcx, [rbp+4Fh+var_90]
0x1400576d8  call    ??$get_bool_or@UValueSet@Collections@Foundation@Windows@winrt@@@details@ValueSetUtils@@YA_NAEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@_N@Z; ValueSetUtils::details::get_bool_or<winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,bool)
0x1400576dd  mov     bl, al
0x1400576df  lea     rcx, [rbp+4Fh+var_90]
0x1400576e3  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x1400576e8  test    bl, bl
0x1400576ea  jz      loc_1400577CE
0x1400576f0  lea     rdx, aUxframecompone; "UXFrameComponentDefinition"
0x1400576f7  lea     rcx, [rbp+4Fh+var_90]; this
0x1400576fb  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x140057700  nop
0x140057701  lea     r8, [rbp+4Fh+var_88]
0x140057705  lea     rdx, [rbp+4Fh+var_90]
0x140057709  lea     rcx, [rbp+4Fh+var_78]
0x14005770d  call    ??$try_get_value@UValueSet@Collections@Foundation@Windows@winrt@@U12345@@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@5@AEBU12345@@Z; ValueSetUtils::try_get_value<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x140057712  nop
0x140057713  lea     rcx, [rbp+4Fh+var_90]
0x140057717  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x14005771c  mov     rcx, rdi; this
0x14005771f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x140057724  mov     rcx, cs:off_14006A538; "LaunchUri"
0x14005772b  mov     [rbp+4Fh+var_70], rcx
0x14005772f  mov     qword ptr [rbp+4Fh+var_68], rax
0x140057733  lea     rdx, [rbp+4Fh+var_70]
0x140057737  lea     rcx, [rbp+4Fh+var_58]
0x14005773b  call    ??$?0PEBGPEBG$0A@@?$pair@Uhstring@winrt@@U12@@std@@QEAA@$$QEAU?$pair@PEBGPEBG@1@@Z; std::pair<winrt::hstring,winrt::hstring>::pair<winrt::hstring,winrt::hstring>(std::pair<ushort const *,ushort const *> &&)
0x140057740  nop
0x140057741  lea     rdx, [rbp+4Fh+var_58]
0x140057745  mov     rcx, rsi
0x140057748  call    ?push_back@?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@QEAAX$$QEAU?$pair@Uhstring@winrt@@U12@@2@@Z; std::vector<std::pair<winrt::hstring,winrt::hstring>>::push_back(std::pair<winrt::hstring,winrt::hstring> &&)
0x14005774d  nop
0x14005774e  lea     rcx, [rbp+4Fh+var_58]
0x140057752  call    ??1?$pair@Uhstring@winrt@@U12@@std@@QEAA@XZ; std::pair<winrt::hstring,winrt::hstring>::~pair<winrt::hstring,winrt::hstring>(void)
0x140057757  mov     [rbp+4Fh+var_70], 0
0x14005775f  mov     [rbp+4Fh+var_58], 0
0x140057767  mov     [rbp+4Fh+var_90], 0
0x14005776f  lea     rax, [rbp+4Fh+var_78]
0x140057773  mov     [rsp+0E0h+var_A0], rax; __int64
0x140057778  mov     rax, [rbp+4Fh+arg_20]
0x14005777c  mov     [rsp+0E0h+var_A8], rax; __int64
0x140057781  mov     [rsp+0E0h+var_B0], r14; __int64
0x140057786  mov     [rsp+0E0h+var_B8], rsi; __int64
0x14005778b  mov     qword ptr [rsp+0E0h+bIgnoreCase], r15; ValueSetUtils *
0x140057790  lea     r9, [rbp+4Fh+var_90]; winrt::hstring *
0x140057794  lea     r8, [rbp+4Fh+var_58]; winrt::hstring *
0x140057798  lea     rdx, [rbp+4Fh+var_70]; this
0x14005779c  lea     rcx, [rbp+4Fh+arg_0]; struct winrt::hstring *
0x1400577a0  call    ?LaunchUXFrameAndWait@@YAXAEBUhstring@winrt@@AEAU12@111AEAV?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@H@std@@V?$allocator@U?$pair@Uhstring@winrt@@H@std@@@2@@4@AEAV?$vector@U?$pair@Uhstring@winrt@@_N@std@@V?$allocator@U?$pair@Uhstring@winrt@@_N@std@@@2@@4@AEBUValueSet@Collections@Foundation@Windows@2@@Z; LaunchUXFrameAndWait(winrt::hstring const &,winrt::hstring &,winrt::hstring &,winrt::hstring &,winrt::hstring &,std::vector<std::pair<winrt::hstring,winrt::hstring>> &,std::vector<std::pair<winrt::hstring,int>> &,std::vector<std::pair<winrt::hstring,bool>> &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x1400577a5  nop
0x1400577a6  lea     rcx, [rbp+4Fh+var_90]
0x1400577aa  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x1400577af  nop
0x1400577b0  lea     rcx, [rbp+4Fh+var_58]
0x1400577b4  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x1400577b9  nop
0x1400577ba  lea     rcx, [rbp+4Fh+var_70]
0x1400577be  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x1400577c3  nop
0x1400577c4  lea     rcx, [rbp+4Fh+var_78]; this
0x1400577c8  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400577cd  nop
0x1400577ce  lea     rcx, [rbp+4Fh+var_88]; this
0x1400577d2  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400577d7  nop
0x1400577d8  lea     rcx, [rbp+4Fh+arg_0]
0x1400577dc  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x1400577e1  nop
0x1400577e2  lea     rcx, [rbp+4Fh+var_80]; this
0x1400577e6  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400577eb  add     rsp, 0B8h
0x1400577f2  pop     r15
0x1400577f4  pop     r14
0x1400577f6  pop     rdi
0x1400577f7  pop     rsi
0x1400577f8  pop     rbx
0x1400577f9  pop     rbp
0x1400577fa  retn
```
