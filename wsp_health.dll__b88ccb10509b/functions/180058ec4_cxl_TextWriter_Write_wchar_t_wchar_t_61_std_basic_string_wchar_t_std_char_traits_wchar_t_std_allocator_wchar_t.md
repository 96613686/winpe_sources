# cxl::TextWriter::Write<wchar_t,wchar_t [61],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(wchar_t const *,wchar_t const (&)[61],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180058ec4`
- end: `0x180058f08`
- name: `??$Write@_W$$BY0DN@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@TextWriter@cxl@@QEAAXPEB_WAEAY0DN@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `68`
- prototype: `struct cxl::TextWriter *__fastcall(struct cxl::TextWriter *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800695e4`

## callees

- `0x1800104f8`

## string_xrefs

- `0x180058ede`: `{0} SendMaintenanceModeCommand on {1}`
- `0x180058ee5`: `Wsp::Facade::StorageHealthFacade::SendCommandMaintenanceMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180058ec4  mov     r11, rsp
0x180058ec7  sub     rsp, 48h
0x180058ecb  mov     [rsp+48h+var_20], 2
0x180058ed3  lea     rax, ??_7?$ArgumentWriters@$$BY0DN@_WV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@cxl@@6B@; const cxl::ArgumentWriters<wchar_t [61],std::wstring>::`vftable'
0x180058eda  mov     [r11-28h], rax
0x180058ede  lea     r8, a0Sendmaintenan; "{0} SendMaintenanceModeCommand on {1}"
0x180058ee5  lea     rax, aWspFacadeStora_7; "Wsp::Facade::StorageHealthFacade::SendC"...
0x180058eec  mov     [r11-18h], r9
0x180058ef0  mov     rdx, rcx; struct cxl::TextWriter *
0x180058ef3  mov     [r11-10h], rax
0x180058ef7  xor     r9d, r9d; bool
0x180058efa  lea     rcx, [r11-28h]; this
0x180058efe  call    ?Format@ArgumentWriter@cxl@@QEAAAEAVTextWriter@2@AEAV32@PEB_W_N@Z; cxl::ArgumentWriter::Format(cxl::TextWriter &,wchar_t const *,bool)
0x180058f03  add     rsp, 48h
0x180058f07  retn
```
