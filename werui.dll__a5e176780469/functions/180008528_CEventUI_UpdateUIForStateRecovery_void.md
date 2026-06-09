# CEventUI::UpdateUIForStateRecovery(void)

- ea: `0x180008528`
- end: `0x180008662`
- name: `?UpdateUIForStateRecovery@CEventUI@@AEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(CEventUI *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006870`
- `0x180007e50`

## callees

- `0x180003604`
- `0x180005c20`
- `0x180005c80`
- `0x18000845c`
- `0x180008528`
- `0x180008f3c`
- `0x180009580`
- `0x18000c8a0`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180008603`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180008603`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEventUI::UpdateUIForStateRecovery(CEventUI *this)
{
  int String; // ebx
  unsigned __int16 *v4[4]; // [rsp+40h] [rbp-9h] BYREF
  unsigned __int16 *v5[4]; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int16 *v6[4]; // [rsp+80h] [rbp+37h] BYREF

  *((_DWORD *)this + 191) = 1;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v6);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v5);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v4);
  UtilLoadString(v6, 213);
  String = UtilLoadString(v5, 212);
  if ( String >= 0 )
  {
    tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
      v4,
      v5[0],
      *((_QWORD *)this + 3) + 400LL);
    SetWindowPos(*((HWND *)this + 13), 0, 0, 0, 0, 0, 0x47u);
    String = CEventUI::UpdateUIForStateCommon(this, v4[0], v6[0]);
    CUIDlgBase::UICallback((char *)this + 8, 21);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      &WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids,
      (unsigned int)String);
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v4);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v5);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v6);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180008528  mov     [rsp-8+arg_0], rbx
0x18000852d  mov     [rsp-8+arg_8], rdi
0x180008532  push    rbp
0x180008533  lea     rbp, [rsp-57h]
0x180008538  sub     rsp, 0A0h
0x18000853f  mov     rdi, rcx
0x180008542  mov     dword ptr [rcx+2FCh], 1
0x18000854c  lea     rcx, [rbp+57h+var_20]; void *
0x180008550  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008555  nop
0x180008556  lea     rcx, [rbp+57h+var_40]; void *
0x18000855a  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18000855f  nop
0x180008560  lea     rcx, [rbp+57h+var_60]; void *
0x180008564  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180008569  nop
0x18000856a  mov     edx, 0D5h
0x18000856f  lea     rcx, [rbp+57h+var_20]
0x180008573  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x180008578  mov     edx, 0D4h
0x18000857d  lea     rcx, [rbp+57h+var_40]
0x180008581  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x180008586  mov     ebx, eax
0x180008588  test    eax, eax
0x18000858a  jns     short loc_1800085C7
0x18000858c  lea     rax, WPP_GLOBAL_Control
0x180008593  mov     rcx, cs:WPP_GLOBAL_Control
0x18000859a  cmp     rcx, rax
0x18000859d  jz      loc_18000862E
0x1800085a3  test    byte ptr [rcx+1Ch], 1
0x1800085a7  jz      loc_18000862E
0x1800085ad  mov     edx, 28h ; '('
0x1800085b2  mov     r9d, ebx
0x1800085b5  lea     r8, WPP_ddf8af267e4d35c632af17f8a6fba57b_Traceguids
0x1800085bc  mov     rcx, [rcx+10h]
0x1800085c0  call    WPP_SF_d
0x1800085c5  jmp     short loc_18000862E
0x1800085c7  mov     r8, [rdi+18h]
0x1800085cb  add     r8, 190h
0x1800085d2  mov     rdx, [rbp+57h+var_40]
0x1800085d6  lea     rcx, [rbp+57h+var_60]
0x1800085da  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x1800085df  mov     [rsp+0A0h+uFlags], 47h ; 'G'; uFlags
0x1800085e7  mov     [rsp+0A0h+cy], 0; cy
0x1800085ef  mov     [rsp+0A0h+var_80], 0; cx
0x1800085f7  xor     r9d, r9d; Y
0x1800085fa  xor     r8d, r8d; X
0x1800085fd  xor     edx, edx; hWndInsertAfter
0x1800085ff  mov     rcx, [rdi+68h]; hWnd
0x180008603  call    cs:__imp_SetWindowPos
0x180008609  mov     r8, [rbp+57h+var_20]; unsigned __int16 *
0x18000860d  mov     rdx, [rbp+57h+var_60]; unsigned __int16 *
0x180008611  mov     rcx, rdi; this
0x180008614  call    ?UpdateUIForStateCommon@CEventUI@@AEAAJPEBG0@Z; CEventUI::UpdateUIForStateCommon(ushort const *,ushort const *)
0x180008619  mov     ebx, eax
0x18000861b  lea     rcx, [rdi+8]
0x18000861f  mov     r8, [rdi+68h]
0x180008623  mov     edx, 15h
0x180008628  call    ?UICallback@CUIDlgBase@@IEAAHW4_UICALLBACKTYPE@@_K@Z; CUIDlgBase::UICallback(_UICALLBACKTYPE,unsigned __int64)
0x18000862d  nop
0x18000862e  lea     rcx, [rbp+57h+var_60]
0x180008632  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008637  nop
0x180008638  lea     rcx, [rbp+57h+var_40]
0x18000863c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008641  nop
0x180008642  lea     rcx, [rbp+57h+var_20]
0x180008646  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000864b  mov     eax, ebx
0x18000864d  lea     r11, [rsp+0A0h+var_s0]
0x180008655  mov     rbx, [r11+10h]
0x180008659  mov     rdi, [r11+18h]
0x18000865d  mov     rsp, r11
0x180008660  pop     rbp
0x180008661  retn
```
