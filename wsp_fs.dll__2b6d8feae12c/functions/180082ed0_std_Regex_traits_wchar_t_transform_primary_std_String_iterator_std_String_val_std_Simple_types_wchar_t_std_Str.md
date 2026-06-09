# std::_Regex_traits<wchar_t>::transform_primary<std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>(std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>)

- ea: `0x180082ed0`
- end: `0x180083038`
- name: `??$transform_primary@V?$_String_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@?$_Regex_traits@_W@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$_String_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@1@0@Z`
- size: `360`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800819a4`

## callees

- `0x180002a70`
- `0x180004fe8`
- `0x180005cdc`
- `0x18000a6dc`
- `0x18000dd74`
- `0x180010e64`
- `0x180082ed0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180082f4d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180082f61`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180082f4d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180082f61`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180082f39`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180082f39`

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
    if ( !(unsigned int)__std_type_info_compare(v8, &qword_180178218)
      || !(unsigned int)__std_type_info_compare(v8, &qword_180178248) )
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
0x180082ed0  mov     [rsp+arg_10], rbx
0x180082ed5  mov     [rsp+arg_18], rbp
0x180082eda  push    rsi
0x180082edb  push    rdi
0x180082edc  push    r14
0x180082ede  sub     rsp, 70h
0x180082ee2  mov     rax, cs:__security_cookie
0x180082ee9  xor     rax, rsp
0x180082eec  mov     [rsp+88h+var_28], rax
0x180082ef1  mov     rbx, r9
0x180082ef4  mov     rdi, r8
0x180082ef7  mov     rsi, rdx
0x180082efa  mov     [rsp+88h+var_50], rdx
0x180082eff  mov     [rsp+88h+var_58], 0
0x180082f07  xorps   xmm0, xmm0
0x180082f0a  movups  xmmword ptr [rdx], xmm0
0x180082f0d  mov     qword ptr [rdx+10h], 0
0x180082f15  mov     qword ptr [rdx+18h], 7
0x180082f1d  xor     eax, eax
0x180082f1f  mov     [rdx], ax
0x180082f22  mov     [rsp+88h+var_58], 1
0x180082f2a  cmp     r8, r9
0x180082f2d  jz      loc_180083012
0x180082f33  mov     r14, [rcx]
0x180082f36  mov     rcx, r14
0x180082f39  call    cs:__imp___RTtypeid
0x180082f3f  lea     rbp, [rax+8]
0x180082f43  lea     rdx, qword_180178218
0x180082f4a  mov     rcx, rbp
0x180082f4d  call    cs:__imp___std_type_info_compare
0x180082f53  test    eax, eax
0x180082f55  jz      short loc_180082F6F
0x180082f57  lea     rdx, qword_180178248
0x180082f5e  mov     rcx, rbp
0x180082f61  call    cs:__imp___std_type_info_compare
0x180082f67  test    eax, eax
0x180082f69  jnz     loc_180083012
0x180082f6f  xorps   xmm0, xmm0
0x180082f72  movups  [rsp+88h+var_48], xmm0
0x180082f77  xorps   xmm1, xmm1
0x180082f7a  movdqu  [rsp+88h+var_38], xmm1
0x180082f80  sub     rbx, rdi
0x180082f83  sar     rbx, 1
0x180082f86  mov     r8, rbx
0x180082f89  mov     rdx, rdi
0x180082f8c  lea     rcx, [rsp+88h+var_48]
0x180082f91  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180082f96  nop
0x180082f97  lea     rcx, [rsp+88h+var_48]
0x180082f9c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180082fa1  mov     rdi, rax
0x180082fa4  mov     rbx, qword ptr [rsp+88h+var_38]
0x180082fa9  lea     rbp, [rax+rbx*2]
0x180082fad  cmp     [rsi+10h], rbx
0x180082fb1  jnb     short loc_180082FFC
0x180082fb3  add     r14, 10h
0x180082fb7  mov     rdx, rbx
0x180082fba  mov     rcx, rsi
0x180082fbd  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180082fc2  mov     rcx, rsi
0x180082fc5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180082fca  lea     rdx, [rax+rbx*2]
0x180082fce  mov     rcx, rsi
0x180082fd1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180082fd6  mov     [rsp+88h+var_68], r14; __int64
0x180082fdb  mov     r9, rbp
0x180082fde  mov     r8, rdi
0x180082fe1  mov     rcx, rax; void *
0x180082fe4  call    __std_regex_transform_primary_wchar_t
0x180082fe9  mov     rbx, rax
0x180082fec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180082ff0  jz      short loc_180082FFA
0x180082ff2  cmp     [rsi+10h], rax
0x180082ff6  jb      short loc_180082FB7
0x180082ff8  jmp     short loc_180082FFC
0x180082ffa  xor     ebx, ebx
0x180082ffc  mov     rdx, rbx
0x180082fff  mov     rcx, rsi
0x180083002  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180083007  nop
0x180083008  lea     rcx, [rsp+88h+var_48]
0x18008300d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180083012  mov     rax, rsi
0x180083015  mov     rcx, [rsp+88h+var_28]
0x18008301a  xor     rcx, rsp; StackCookie
0x18008301d  call    __security_check_cookie
0x180083022  lea     r11, [rsp+88h+var_18]
0x180083027  mov     rbx, [r11+30h]
0x18008302b  mov     rbp, [r11+38h]
0x18008302f  mov     rsp, r11
0x180083032  pop     r14
0x180083034  pop     rdi
0x180083035  pop     rsi
0x180083036  retn
```
