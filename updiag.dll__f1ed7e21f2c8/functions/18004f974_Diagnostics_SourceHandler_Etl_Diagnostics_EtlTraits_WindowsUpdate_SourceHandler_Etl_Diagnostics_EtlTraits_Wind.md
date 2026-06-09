# Diagnostics::SourceHandler_Etl<Diagnostics::EtlTraits_WindowsUpdate>::SourceHandler_Etl<Diagnostics::EtlTraits_WindowsUpdate>(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::vector<std::filesystem::path,std::allocator<std::filesystem::path>> const &)

- ea: `0x18004f974`
- end: `0x18004fac5`
- name: `??0?$SourceHandler_Etl@UEtlTraits_WindowsUpdate@Diagnostics@@@Diagnostics@@AEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@3@@Z`
- size: `337`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180041c40`

## callees

- `0x1800185a8`
- `0x180018eec`
- `0x180019080`
- `0x180020a30`
- `0x18002edd0`
- `0x1800301cc`
- `0x18004f974`
- `0x18005f2b0`
- `0x180060a40`

## string_xrefs

- `0x18004faa4`: `WindowsUpdate_trace_log`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Diagnostics::SourceHandler_Etl<Diagnostics::EtlTraits_WindowsUpdate>::SourceHandler_Etl<Diagnostics::EtlTraits_WindowsUpdate>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v5; // rcx
  __int128 v7; // [rsp+40h] [rbp-39h] BYREF
  _OWORD v8[2]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v9[40]; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v10[56]; // [rsp+98h] [rbp+1Fh] BYREF

  *a1 = &Diagnostics::SourceHandler_Etl<Diagnostics::EtlTraits_WindowsUpdate>::`vftable';
  v5 = a1 + 1;
  *(_OWORD *)v5 = 0;
  v5[2] = 0;
  v5[3] = 0;
  std::wstring::_Construct<1,wchar_t const *>(v5, *(const void **)a2, *(_QWORD *)(a2 + 8));
  a1[5] = &Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::`vftable';
  a1[6] = 0;
  a1[7] = 0;
  a1[8] = 0;
  a1[9] = 0;
  a1[10] = 0;
  a1[11] = 0;
  memset(v8, 0, sizeof(v8));
  std::wstring::_Construct<1,wchar_t const *>(
    v8,
    Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig::AttributePatterns,
    _mm_srli_si128(*(__m128i *)&Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig::AttributePatterns, 8).m128i_u64[0]);
  v7 = *(_OWORD *)&off_1800B17A0;
  Diagnostics::RegExNamedCapture::RegExNamedCapture(v9, &v7);
  if ( a1[10] == a1[11] )
  {
    std::vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WaasMedic::OrderFromChaosConfig>::CompiledAttributePattern,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WaasMedic::OrderFromChaosConfig>::CompiledAttributePattern>>::_Emplace_reallocate<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WaasMedic::OrderFromChaosConfig>::CompiledAttributePattern>(
      a1 + 9,
      a1[10],
      (__int64)v8);
  }
  else
  {
    Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraits_PantherCbs::OrderFromChaosConfig>::CompiledAttributePattern::CompiledAttributePattern(
      a1[10],
      v8);
    a1[10] += 96LL;
  }
  std::vector<std::filesystem::path>::~vector<std::filesystem::path>(v10);
  std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v9);
  std::wstring::~wstring(v8);
  Diagnostics::EtwFileProcessor::EtwFileProcessor(a1 + 12, a3, L"WindowsUpdate_trace_log");
  return a1;
}

```

## disassembly

```asm
0x18004f974  push    rbp
0x18004f976  push    rbx
0x18004f977  push    rsi
0x18004f978  push    rdi
0x18004f979  push    r14
0x18004f97b  lea     rbp, [rsp-37h]
0x18004f980  sub     rsp, 0B0h
0x18004f987  mov     r14, r8
0x18004f98a  mov     rdi, rcx
0x18004f98d  mov     [rbp+57h+var_A0], rcx
0x18004f991  lea     rax, ??_7?$SourceHandler_Etl@UEtlTraits_WindowsUpdate@Diagnostics@@@Diagnostics@@6B@; const Diagnostics::SourceHandler_Etl<Diagnostics::EtlTraits_WindowsUpdate>::`vftable'
0x18004f998  mov     [rcx], rax
0x18004f99b  add     rcx, 8
0x18004f99f  xorps   xmm0, xmm0
0x18004f9a2  movups  xmmword ptr [rcx], xmm0
0x18004f9a5  mov     qword ptr [rcx+10h], 0
0x18004f9ad  mov     qword ptr [rcx+18h], 0
0x18004f9b5  mov     r8, [rdx+8]
0x18004f9b9  mov     rdx, [rdx]
0x18004f9bc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004f9c1  nop
0x18004f9c2  lea     rsi, [rdi+28h]
0x18004f9c6  mov     [rbp+57h+var_98], rsi
0x18004f9ca  lea     rax, ??_7?$Transformer@UOrderFromChaosConfig@EtlTraits_WindowsUpdate@Diagnostics@@@OrderFromChaos@Diagnostics@@6B@; const Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig>::`vftable'
0x18004f9d1  mov     [rsi], rax
0x18004f9d4  mov     qword ptr [rsi+8], 0
0x18004f9dc  mov     qword ptr [rsi+10h], 0
0x18004f9e4  mov     qword ptr [rsi+18h], 0
0x18004f9ec  mov     qword ptr [rsi+20h], 0
0x18004f9f4  mov     qword ptr [rsi+28h], 0
0x18004f9fc  mov     qword ptr [rsi+30h], 0
0x18004fa04  xorps   xmm0, xmm0
0x18004fa07  movups  [rbp+57h+var_80], xmm0
0x18004fa0b  xorps   xmm1, xmm1
0x18004fa0e  movdqa  [rbp+57h+var_70], xmm1
0x18004fa13  movaps  xmm2, xmmword ptr cs:?AttributePatterns@OrderFromChaosConfig@EtlTraits_WindowsUpdate@Diagnostics@@2QBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V12@@std@@B; std::pair<std::wstring_view,std::wstring_view> const near * const Diagnostics::EtlTraits_WindowsUpdate::OrderFromChaosConfig::AttributePatterns
0x18004fa1a  movdqa  xmm0, xmm2
0x18004fa1e  psrldq  xmm0, 8
0x18004fa23  movq    r8, xmm0
0x18004fa28  movq    rdx, xmm2
0x18004fa2d  lea     rcx, [rbp+57h+var_80]
0x18004fa31  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004fa36  nop
0x18004fa37  movaps  xmm0, xmmword ptr cs:off_1800B17A0; "\\*FAILED\\* \\[(?<ErrorCode>[0-9A-Fa-f"...
0x18004fa3e  movdqa  [rbp+57h+var_90], xmm0
0x18004fa43  lea     rdx, [rbp+57h+var_90]
0x18004fa47  lea     rcx, [rbp+57h+var_60]
0x18004fa4b  call    ??0RegExNamedCapture@Diagnostics@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Diagnostics::RegExNamedCapture::RegExNamedCapture(std::wstring_view)
0x18004fa50  nop
0x18004fa51  mov     rax, [rsi+28h]
0x18004fa55  cmp     rax, [rsi+30h]
0x18004fa59  jz      short loc_18004FA6E
0x18004fa5b  lea     rdx, [rbp+57h+var_80]
0x18004fa5f  mov     rcx, rax
0x18004fa62  call    ??0CompiledAttributePattern@?$Transformer@UOrderFromChaosConfig@LogTraits_PantherCbs@Diagnostics@@@OrderFromChaos@Diagnostics@@QEAA@$$QEAU0123@@Z; Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraits_PantherCbs::OrderFromChaosConfig>::CompiledAttributePattern::CompiledAttributePattern(Diagnostics::OrderFromChaos::Transformer<Diagnostics::LogTraits_PantherCbs::OrderFromChaosConfig>::CompiledAttributePattern &&)
0x18004fa67  add     qword ptr [rsi+28h], 60h ; '`'
0x18004fa6c  jmp     short loc_18004FA7F
0x18004fa6e  lea     r8, [rbp+57h+var_80]
0x18004fa72  mov     rdx, rax
0x18004fa75  lea     rcx, [rsi+20h]
0x18004fa79  call    ??$_Emplace_reallocate@UCompiledAttributePattern@?$Transformer@UOrderFromChaosConfig@EtlTraits_WaasMedic@Diagnostics@@@OrderFromChaos@Diagnostics@@@?$vector@UCompiledAttributePattern@?$Transformer@UOrderFromChaosConfig@EtlTraits_WaasMedic@Diagnostics@@@OrderFromChaos@Diagnostics@@V?$allocator@UCompiledAttributePattern@?$Transformer@UOrderFromChaosConfig@EtlTraits_WaasMedic@Diagnostics@@@OrderFromChaos@Diagnostics@@@std@@@std@@AEAAPEAUCompiledAttributePattern@?$Transformer@UOrderFromChaosConfig@EtlTraits_WaasMedic@Diagnostics@@@OrderFromChaos@Diagnostics@@QEAU2345@$$QEAU2345@@Z; std::vector<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WaasMedic::OrderFromChaosConfig>::CompiledAttributePattern,std::allocator<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WaasMedic::OrderFromChaosConfig>::CompiledAttributePattern>>::_Emplace_reallocate<Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WaasMedic::OrderFromChaosConfig>::CompiledAttributePattern>(Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WaasMedic::OrderFromChaosConfig>::CompiledAttributePattern * const,Diagnostics::OrderFromChaos::Transformer<Diagnostics::EtlTraits_WaasMedic::OrderFromChaosConfig>::CompiledAttributePattern &&)
0x18004fa7e  nop
0x18004fa7f  lea     rcx, [rbp+57h+var_38]
0x18004fa83  call    ??1?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAA@XZ; std::vector<std::filesystem::path>::~vector<std::filesystem::path>(void)
0x18004fa88  lea     rcx, [rbp+57h+var_60]; void *
0x18004fa8c  call    ??1?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@XZ; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(void)
0x18004fa91  lea     rcx, [rbp+57h+var_80]
0x18004fa95  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004fa9a  nop
0x18004fa9b  lea     rcx, [rdi+60h]
0x18004fa9f  mov     [rsp+0D0h+var_B0], rsi
0x18004faa4  lea     r8, aWindowsupdateT; "WindowsUpdate_trace_log"
0x18004faab  mov     rdx, r14
0x18004faae  call    ??0EtwFileProcessor@Diagnostics@@QEAA@AEBV?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@PEB_W_NPEBUITransformer@OrderFromChaos@1@@Z; Diagnostics::EtwFileProcessor::EtwFileProcessor(std::vector<std::filesystem::path> const &,wchar_t const *,bool,Diagnostics::OrderFromChaos::ITransformer const *)
0x18004fab3  nop
0x18004fab4  mov     rax, rdi
0x18004fab7  add     rsp, 0B0h
0x18004fabe  pop     r14
0x18004fac0  pop     rdi
0x18004fac1  pop     rsi
0x18004fac2  pop     rbx
0x18004fac3  pop     rbp
0x18004fac4  retn
```
