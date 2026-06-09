# CConsentUI::~CConsentUI(void)

- ea: `0x180009ab8`
- end: `0x180009b02`
- name: `??1CConsentUI@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CConsentUI *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b20`
- `0x180007490`
- `0x180007a70`
- `0x18000a70c`
- `0x1800171d6`
- `0x1800171e8`

## callees

- `0x180009580`
- `0x18000e14c`

## pseudocode

```c
void __fastcall CConsentUI::~CConsentUI(CConsentUI *this)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)this + 35);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)this + 31);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)this + 27);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)this + 23);
  CReportDetails::~CReportDetails((HWND *)this + 16);
}

```

## disassembly

```asm
0x180009ab8  push    rbx
0x180009aba  sub     rsp, 20h
0x180009abe  mov     rbx, rcx
0x180009ac1  add     rcx, 118h
0x180009ac8  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180009acd  lea     rcx, [rbx+0F8h]
0x180009ad4  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180009ad9  lea     rcx, [rbx+0D8h]
0x180009ae0  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180009ae5  lea     rcx, [rbx+0B8h]
0x180009aec  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180009af1  lea     rcx, [rbx+80h]; this
0x180009af8  add     rsp, 20h
0x180009afc  pop     rbx
0x180009afd  jmp     ??1CReportDetails@@QEAA@XZ; CReportDetails::~CReportDetails(void)
```
