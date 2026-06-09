# CEventUI::UpdateUIForStateRestarting(void)

- ea: `0x180008668`
- end: `0x180008759`
- name: `?UpdateUIForStateRestarting@CEventUI@@AEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(CEventUI *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006870`
- `0x180007e50`

## callees

- `0x180005c20`
- `0x180005c80`
- `0x18000845c`
- `0x180008f3c`
- `0x180009580`
- `0x1800096a8`
- `0x18000c8a0`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x1800086fc`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x1800086fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEventUI::UpdateUIForStateRestarting(CEventUI *this)
{
  unsigned __int16 *v3[4]; // [rsp+40h] [rbp-9h] BYREF
  unsigned __int16 *v4[4]; // [rsp+60h] [rbp+17h] BYREF
  _QWORD v5[4]; // [rsp+80h] [rbp+37h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v5);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v4);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v3);
  *((_DWORD *)this + 192) = 1;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    v5,
    *((_QWORD *)this + 3) + 400LL);
  UtilLoadString(v3, 214);
  tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v4, v3[0], v5[0]);
  SetWindowPos(*((HWND *)this + 13), 0, 0, 0, 0, 0, 0x47u);
  CUIDlgBase::UICallback((char *)this + 8, 20);
  LODWORD(this) = CEventUI::UpdateUIForStateCommon(this, v4[0], (const unsigned __int16 *)&lParam);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v3);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v4);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v5);
  return (unsigned int)this;
}

```

## disassembly

```asm
0x180008668  mov     [rsp-8+arg_0], rbx
0x18000866d  push    rbp
0x18000866e  lea     rbp, [rsp-57h]
0x180008673  sub     rsp, 0A0h
0x18000867a  mov     rbx, rcx
0x18000867d  lea     rcx, [rbp+57h+var_20]; void *
0x180008681  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008686  nop
0x180008687  lea     rcx, [rbp+57h+var_40]; void *
0x18000868b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008690  nop
0x180008691  lea     rcx, [rbp+57h+var_60]; void *
0x180008695  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000869a  nop
0x18000869b  mov     dword ptr [rbx+300h], 1
0x1800086a5  mov     rdx, [rbx+18h]
0x1800086a9  add     rdx, 190h
0x1800086b0  lea     rcx, [rbp+57h+var_20]
0x1800086b4  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800086b9  mov     edx, 0D6h
0x1800086be  lea     rcx, [rbp+57h+var_60]
0x1800086c2  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x1800086c7  mov     r8, [rbp+57h+var_20]
0x1800086cb  mov     rdx, [rbp+57h+var_60]
0x1800086cf  lea     rcx, [rbp+57h+var_40]
0x1800086d3  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800086d8  mov     [rsp+0A0h+uFlags], 47h ; 'G'; uFlags
0x1800086e0  mov     [rsp+0A0h+cy], 0; cy
0x1800086e8  mov     [rsp+0A0h+var_80], 0; cx
0x1800086f0  xor     r9d, r9d; Y
0x1800086f3  xor     r8d, r8d; X
0x1800086f6  xor     edx, edx; hWndInsertAfter
0x1800086f8  mov     rcx, [rbx+68h]; hWnd
0x1800086fc  call    cs:__imp_SetWindowPos
0x180008702  lea     rcx, [rbx+8]
0x180008706  mov     r8, [rbx+68h]
0x18000870a  mov     edx, 14h
0x18000870f  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x180008714  lea     r8, lParam; unsigned __int16 *
0x18000871b  mov     rdx, [rbp+57h+var_40]; unsigned __int16 *
0x18000871f  mov     rcx, rbx; this
0x180008722  call    ?UpdateUIForStateCommon@CEventUI@@AEAAJPEBG0@Z; CEventUI::UpdateUIForStateCommon(ushort const *,ushort const *)
0x180008727  mov     ebx, eax
0x180008729  lea     rcx, [rbp+57h+var_60]
0x18000872d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008732  nop
0x180008733  lea     rcx, [rbp+57h+var_40]
0x180008737  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000873c  nop
0x18000873d  lea     rcx, [rbp+57h+var_20]
0x180008741  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008746  mov     eax, ebx
0x180008748  mov     rbx, [rsp+0A0h+arg_0]
0x180008750  add     rsp, 0A0h
0x180008757  pop     rbp
0x180008758  retn
```
