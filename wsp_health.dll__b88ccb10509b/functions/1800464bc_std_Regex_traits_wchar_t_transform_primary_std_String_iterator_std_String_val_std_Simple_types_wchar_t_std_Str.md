# std::_Regex_traits<wchar_t>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>)

- ea: `0x1800464bc`
- end: `0x180046624`
- name: `??$transform_primary@V?$_String_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@?$_Regex_traits@_W@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$_String_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@1@0@Z`
- size: `360`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180044f90`

## callees

- `0x180002ae0`
- `0x180005168`
- `0x18000c258`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000fac4`
- `0x1800464bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180046539`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004654d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180046539`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004654d`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180046525`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180046525`

## pseudocode

```c
__int64 __fastcall std::_Regex_traits<wchar_t>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r14
  __int64 v8; // rbp
  unsigned __int64 v9; // rbx
  __int64 v10; // r14
  void *v11; // rax
  unsigned __int64 v12; // rax
  __int128 v14; // [rsp+40h] [rbp-48h] BYREF
  __int128 v15; // [rsp+50h] [rbp-38h]

  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  if ( a3 != a4 )
  {
    v7 = *a1;
    v8 = __RTtypeid(*a1) + 8;
    if ( !(unsigned int)__std_type_info_compare(v8, &qword_18014BF88)
      || !(unsigned int)__std_type_info_compare(v8, &qword_18014BFB8) )
    {
      v14 = 0;
      v15 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v14, a3, (a4 - a3) >> 1);
      std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v14);
      v9 = v15;
      if ( *(_QWORD *)(a2 + 16) < (unsigned __int64)v15 )
      {
        v10 = v7 + 16;
        while ( 1 )
        {
          std::wstring::resize(a2, v9);
          std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
          v11 = (void *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a2);
          v12 = _std_regex_transform_primary_wchar_t(v11, v10);
          v9 = v12;
          if ( v12 == -1 )
            break;
          if ( *(_QWORD *)(a2 + 16) >= v12 )
            goto LABEL_10;
        }
        v9 = 0;
      }
LABEL_10:
      std::wstring::resize(a2, v9);
      std::wstring::_Tidy_deallocate(&v14);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800464bc  mov     [rsp+arg_10], rbx
0x1800464c1  mov     [rsp+arg_18], rbp
0x1800464c6  push    rsi
0x1800464c7  push    rdi
0x1800464c8  push    r14
0x1800464ca  sub     rsp, 70h
0x1800464ce  mov     rax, cs:__security_cookie
0x1800464d5  xor     rax, rsp
0x1800464d8  mov     [rsp+88h+var_28], rax
0x1800464dd  mov     rbx, r9
0x1800464e0  mov     rdi, r8
0x1800464e3  mov     rsi, rdx
0x1800464e6  mov     [rsp+88h+var_50], rdx
0x1800464eb  mov     [rsp+88h+var_58], 0
0x1800464f3  xorps   xmm0, xmm0
0x1800464f6  movups  xmmword ptr [rdx], xmm0
0x1800464f9  mov     qword ptr [rdx+10h], 0
0x180046501  mov     qword ptr [rdx+18h], 7
0x180046509  xor     eax, eax
0x18004650b  mov     [rdx], ax
0x18004650e  mov     [rsp+88h+var_58], 1
0x180046516  cmp     r8, r9
0x180046519  jz      loc_1800465FE
0x18004651f  mov     r14, [rcx]
0x180046522  mov     rcx, r14
0x180046525  call    cs:__imp___RTtypeid
0x18004652b  lea     rbp, [rax+8]
0x18004652f  lea     rdx, qword_18014BF88
0x180046536  mov     rcx, rbp
0x180046539  call    cs:__imp___std_type_info_compare
0x18004653f  test    eax, eax
0x180046541  jz      short loc_18004655B
0x180046543  lea     rdx, qword_18014BFB8
0x18004654a  mov     rcx, rbp
0x18004654d  call    cs:__imp___std_type_info_compare
0x180046553  test    eax, eax
0x180046555  jnz     loc_1800465FE
0x18004655b  xorps   xmm0, xmm0
0x18004655e  movups  [rsp+88h+var_48], xmm0
0x180046563  xorps   xmm1, xmm1
0x180046566  movdqu  [rsp+88h+var_38], xmm1
0x18004656c  sub     rbx, rdi
0x18004656f  sar     rbx, 1
0x180046572  mov     r8, rbx
0x180046575  mov     rdx, rdi
0x180046578  lea     rcx, [rsp+88h+var_48]
0x18004657d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180046582  nop
0x180046583  lea     rcx, [rsp+88h+var_48]
0x180046588  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004658d  mov     rdi, rax
0x180046590  mov     rbx, qword ptr [rsp+88h+var_38]
0x180046595  lea     rbp, [rax+rbx*2]
0x180046599  cmp     [rsi+10h], rbx
0x18004659d  jnb     short loc_1800465E8
0x18004659f  add     r14, 10h
0x1800465a3  mov     rdx, rbx
0x1800465a6  mov     rcx, rsi
0x1800465a9  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800465ae  mov     rcx, rsi
0x1800465b1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800465b6  lea     rdx, [rax+rbx*2]
0x1800465ba  mov     rcx, rsi
0x1800465bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800465c2  mov     [rsp+88h+var_68], r14; __int64
0x1800465c7  mov     r9, rbp
0x1800465ca  mov     r8, rdi
0x1800465cd  mov     rcx, rax; void *
0x1800465d0  call    __std_regex_transform_primary_wchar_t
0x1800465d5  mov     rbx, rax
0x1800465d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800465dc  jz      short loc_1800465E6
0x1800465de  cmp     [rsi+10h], rax
0x1800465e2  jb      short loc_1800465A3
0x1800465e4  jmp     short loc_1800465E8
0x1800465e6  xor     ebx, ebx
0x1800465e8  mov     rdx, rbx
0x1800465eb  mov     rcx, rsi
0x1800465ee  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800465f3  nop
0x1800465f4  lea     rcx, [rsp+88h+var_48]
0x1800465f9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800465fe  mov     rax, rsi
0x180046601  mov     rcx, [rsp+88h+var_28]
0x180046606  xor     rcx, rsp; StackCookie
0x180046609  call    __security_check_cookie
0x18004660e  lea     r11, [rsp+88h+var_18]
0x180046613  mov     rbx, [r11+30h]
0x180046617  mov     rbp, [r11+38h]
0x18004661b  mov     rsp, r11
0x18004661e  pop     r14
0x180046620  pop     rdi
0x180046621  pop     rsi
0x180046622  retn
```
