# CEventUI::UpdateUIForStateQueuing(void)

- ea: `0x1800084b8`
- end: `0x180008521`
- name: `?UpdateUIForStateQueuing@CEventUI@@AEAAJXZ`
- size: `105`
- prototype: `__int64 __fastcall(CEventUI *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007e50`

## callees

- `0x180005c80`
- `0x180006440`
- `0x18000845c`
- `0x180008f3c`
- `0x180009580`

## pseudocode

```c
__int64 __fastcall CEventUI::UpdateUIForStateQueuing(HWND *this)
{
  unsigned __int16 *v3[4]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *v4[5]; // [rsp+40h] [rbp-28h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v4);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v3);
  CEventUI::GetDiagosingHeaderText(this, v4);
  UtilLoadString(v3, 233);
  LODWORD(this) = CEventUI::UpdateUIForStateCommon(this, v4[0], v3[0]);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v3);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v4);
  return (unsigned int)this;
}

```

## disassembly

```asm
0x1800084b8  push    rbx
0x1800084ba  sub     rsp, 60h
0x1800084be  mov     rbx, rcx
0x1800084c1  lea     rcx, [rsp+68h+var_28]; void *
0x1800084c6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800084cb  lea     rcx, [rsp+68h+var_48]; void *
0x1800084d0  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800084d5  lea     rdx, [rsp+68h+var_28]
0x1800084da  mov     rcx, rbx
0x1800084dd  call    ?GetDiagosingHeaderText@CEventUI@@AEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CEventUI::GetDiagosingHeaderText(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800084e2  mov     edx, 0E9h
0x1800084e7  lea     rcx, [rsp+68h+var_48]
0x1800084ec  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x1800084f1  mov     r8, [rsp+68h+var_48]; unsigned __int16 *
0x1800084f6  mov     rcx, rbx; this
0x1800084f9  mov     rdx, [rsp+68h+var_28]; unsigned __int16 *
0x1800084fe  call    ?UpdateUIForStateCommon@CEventUI@@AEAAJPEBG0@Z; CEventUI::UpdateUIForStateCommon(ushort const *,ushort const *)
0x180008503  lea     rcx, [rsp+68h+var_48]
0x180008508  mov     ebx, eax
0x18000850a  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000850f  lea     rcx, [rsp+68h+var_28]
0x180008514  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008519  mov     eax, ebx
0x18000851b  add     rsp, 60h
0x18000851f  pop     rbx
0x180008520  retn
```
