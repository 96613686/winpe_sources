# cxl::TextWriter::Write<wchar_t,wchar_t [61],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(wchar_t const *,wchar_t const (&)[61],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18005a638`
- end: `0x18005a67d`
- name: `??$Write@_W$$BY0DN@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DN@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(struct cxl::TextWriter *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006ae1c`

## callees

- `0x1800109dc`

## string_xrefs

- `0x18005a652`: `{0} SendMaintenanceModeCommand on {1}`
- `0x18005a659`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`

## pseudocode

```c
struct cxl::TextWriter *__fastcall cxl::TextWriter::Write<wchar_t,wchar_t [61],std::wstring>(
        struct cxl::TextWriter *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void **v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+30h] [rbp-18h]
  const wchar_t *v8; // [rsp+38h] [rbp-10h]

  v6 = 2;
  v5 = &cxl::ArgumentWriters<wchar_t [61],std::wstring>::`vftable';
  v7 = a4;
  v8 = L"Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode";
  return cxl::ArgumentWriter::Format((cxl::ArgumentWriter *)&v5, a1, L"{0} SendMaintenanceModeCommand on {1}", 0);
}

```

## disassembly

```asm
0x18005a638  mov     r11, rsp
0x18005a63b  sub     rsp, 48h
0x18005a63f  mov     [rsp+48h+var_20], 2
0x18005a647  lea     rax, ??_7?$ArgumentWriters@$$BY0DN@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@6B@; const cxl::ArgumentWriters<wchar_t [61],std::wstring>::`vftable'
0x18005a64e  mov     [r11-28h], rax
0x18005a652  lea     r8, a0Sendmaintenan; "{0} SendMaintenanceModeCommand on {1}"
0x18005a659  lea     rax, aWspFacadeStora_7; "Wsp::Facade::StorageHealthFacade::SendC"...
0x18005a660  mov     [r11-18h], r9
0x18005a664  mov     rdx, rcx; struct cxl::TextWriter *
0x18005a667  mov     [r11-10h], rax
0x18005a66b  xor     r9d, r9d; bool
0x18005a66e  lea     rcx, [r11-28h]; this
0x18005a672  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEB_W_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,wchar_t const *,bool)
0x18005a677  add     rsp, 48h
0x18005a67b  retn
```
