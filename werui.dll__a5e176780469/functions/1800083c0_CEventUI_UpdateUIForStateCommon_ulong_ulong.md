# CEventUI::UpdateUIForStateCommon(ulong,ulong)

- ea: `0x1800083c0`
- end: `0x180008456`
- name: `?UpdateUIForStateCommon@CEventUI@@AEAAJKK@Z`
- size: `150`
- prototype: `__int64 __fastcall(CEventUI *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007e50`

## callees

- `0x180005c80`
- `0x1800083c0`
- `0x18000845c`
- `0x180008f3c`
- `0x180009580`

## pseudocode

```c
__int64 __fastcall CEventUI::UpdateUIForStateCommon(CEventUI *this, unsigned int a2, unsigned int a3)
{
  unsigned int updated; // ebx
  unsigned __int16 *v8[4]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *v9[5]; // [rsp+40h] [rbp-28h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v9);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v8);
  if ( a2 )
    UtilLoadString(v9, a2);
  if ( a3 )
  {
    UtilLoadString(v8, a3);
  }
  else
  {
    v8[1] = v8[0];
    *v8[0] = 0;
  }
  updated = CEventUI::UpdateUIForStateCommon(this, v9[0], v8[0]);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v8);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v9);
  return updated;
}

```

## disassembly

```asm
0x1800083c0  mov     [rsp+arg_0], rbx
0x1800083c5  mov     [rsp+arg_8], rsi
0x1800083ca  push    rdi
0x1800083cb  sub     rsp, 60h
0x1800083cf  mov     rsi, rcx
0x1800083d2  mov     ebx, r8d
0x1800083d5  lea     rcx, [rsp+68h+var_28]; void *
0x1800083da  mov     edi, edx
0x1800083dc  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800083e1  lea     rcx, [rsp+68h+var_48]; void *
0x1800083e6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x1800083eb  test    edi, edi
0x1800083ed  jz      short loc_1800083FB
0x1800083ef  mov     edx, edi
0x1800083f1  lea     rcx, [rsp+68h+var_28]
0x1800083f6  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x1800083fb  test    ebx, ebx
0x1800083fd  jz      short loc_18000840D
0x1800083ff  mov     edx, ebx
0x180008401  lea     rcx, [rsp+68h+var_48]
0x180008406  call    ?UtilLoadString@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@KPEAUHINSTANCE__@@@Z; UtilLoadString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ulong,HINSTANCE__ *)
0x18000840b  jmp     short loc_18000841C
0x18000840d  mov     rcx, [rsp+68h+var_48]
0x180008412  xor     eax, eax
0x180008414  mov     [rsp+68h+var_40], rcx
0x180008419  mov     [rcx], ax
0x18000841c  mov     r8, [rsp+68h+var_48]; unsigned __int16 *
0x180008421  mov     rcx, rsi; this
0x180008424  mov     rdx, [rsp+68h+var_28]; unsigned __int16 *
0x180008429  call    ?UpdateUIForStateCommon@CEventUI@@AEAAJPEBG0@Z; CEventUI::UpdateUIForStateCommon(ushort const *,ushort const *)
0x18000842e  lea     rcx, [rsp+68h+var_48]
0x180008433  mov     ebx, eax
0x180008435  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000843a  lea     rcx, [rsp+68h+var_28]
0x18000843f  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180008444  mov     rsi, [rsp+68h+arg_8]
0x180008449  mov     eax, ebx
0x18000844b  mov     rbx, [rsp+68h+arg_0]
0x180008450  add     rsp, 60h
0x180008454  pop     rdi
0x180008455  retn
```
