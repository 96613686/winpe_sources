# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace<char const *>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,char const *,char const *)

- ea: `0x18000f928`
- end: `0x18000f9f8`
- name: `??$replace@PEBD@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0PEBD1@Z`
- size: `208`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001007c`

## callees

- `0x18000e968`
- `0x18000f098`
- `0x18000f828`
- `0x18000f928`
- `0x18001b150`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace<char const *>(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  _QWORD *v8; // rax
  __int64 v9; // rdx
  _WORD v11[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-28h]
  __int64 v13; // [rsp+48h] [rbp-20h]

  v13 = 7;
  v12 = 0;
  v11[0] = 0;
  std::wstring::_Construct<char const *>(v11, a4, a5);
  if ( a3 )
    a3 = (a3 - a2) >> 1;
  if ( a1[3] < 8u )
    v8 = a1;
  else
    v8 = (_QWORD *)*a1;
  if ( a2 )
    a2 = (a2 - (__int64)v8) >> 1;
  std::wstring::replace((_DWORD)a1, a2, a3, (unsigned int)v11, 0, -1);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v11, v9, 0);
  return a1;
}

```

## disassembly

```asm
0x18000f928  mov     r11, rsp
0x18000f92b  mov     [r11+10h], rbx
0x18000f92f  mov     [r11+18h], rsi
0x18000f933  push    rdi
0x18000f934  sub     rsp, 60h
0x18000f938  mov     rax, cs:__security_cookie
0x18000f93f  xor     rax, rsp
0x18000f942  mov     [rsp+68h+var_18], rax
0x18000f947  mov     rdi, r8
0x18000f94a  mov     rbx, rdx
0x18000f94d  mov     rsi, rcx
0x18000f950  mov     r8, [rsp+68h+arg_20]
0x18000f958  mov     qword ptr [r11-20h], 7
0x18000f960  mov     qword ptr [r11-28h], 0
0x18000f968  xor     eax, eax
0x18000f96a  mov     [rsp+68h+var_38], ax
0x18000f96f  mov     rdx, r9
0x18000f972  lea     rcx, [r11-38h]
0x18000f976  call    ??$_Construct@PEBD@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXPEBD0Uforward_iterator_tag@1@@Z; std::wstring::_Construct<char const *>(char const *,char const *,std::forward_iterator_tag)
0x18000f97b  nop
0x18000f97c  test    rdi, rdi
0x18000f97f  jz      short loc_18000F987
0x18000f981  sub     rdi, rbx
0x18000f984  sar     rdi, 1
0x18000f987  cmp     qword ptr [rsi+18h], 8
0x18000f98c  jb      short loc_18000F993
0x18000f98e  mov     rax, [rsi]
0x18000f991  jmp     short loc_18000F996
0x18000f993  mov     rax, rsi
0x18000f996  test    rbx, rbx
0x18000f999  jz      short loc_18000F9A1
0x18000f99b  sub     rbx, rax
0x18000f99e  sar     rbx, 1
0x18000f9a1  mov     [rsp+68h+var_40], 0FFFFFFFFFFFFFFFFh
0x18000f9aa  mov     [rsp+68h+var_48], 0
0x18000f9b3  lea     r9, [rsp+68h+var_38]
0x18000f9b8  mov     r8, rdi
0x18000f9bb  mov     rdx, rbx
0x18000f9be  mov     rcx, rsi
0x18000f9c1  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18000f9c6  nop
0x18000f9c7  xor     r8d, r8d
0x18000f9ca  mov     dl, 1
0x18000f9cc  lea     rcx, [rsp+68h+var_38]
0x18000f9d1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000f9d6  mov     rax, rsi
0x18000f9d9  mov     rcx, [rsp+68h+var_18]
0x18000f9de  xor     rcx, rsp; StackCookie
0x18000f9e1  call    __security_check_cookie
0x18000f9e6  lea     r11, [rsp+68h+var_8]
0x18000f9eb  mov     rbx, [r11+18h]
0x18000f9ef  mov     rsi, [r11+20h]
0x18000f9f3  mov     rsp, r11
0x18000f9f6  pop     rdi
0x18000f9f7  retn
```
