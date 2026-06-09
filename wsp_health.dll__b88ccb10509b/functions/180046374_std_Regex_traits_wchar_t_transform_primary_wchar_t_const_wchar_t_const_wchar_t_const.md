# std::_Regex_traits<wchar_t>::transform_primary<wchar_t const *>(wchar_t const *,wchar_t const *)

- ea: `0x180046374`
- end: `0x1800464b4`
- name: `??$transform_primary@PEB_W@?$_Regex_traits@_W@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEB_W0@Z`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004bafc`

## callees

- `0x180002ae0`
- `0x180005168`
- `0x18000d618`
- `0x18000d6dc`
- `0x18000fac4`
- `0x1800161d0`
- `0x180046374`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800463ea`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800463fe`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800463ea`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800463fe`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1800463d6`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1800463d6`

## pseudocode

```c
__int64 __fastcall std::_Regex_traits<wchar_t>::transform_primary<wchar_t const *>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rsi
  __int64 v8; // rdi
  unsigned __int64 v9; // rdi
  __int64 v10; // rsi
  void *v11; // rax
  unsigned __int64 v12; // rax
  _BYTE v14[16]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v15; // [rsp+50h] [rbp-48h]

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
      std::wstring::wstring(v14, a3, a4);
      std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
      v9 = v15;
      if ( *(_QWORD *)(a2 + 16) < v15 )
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
      std::wstring::_Tidy_deallocate(v14);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180046374  push    rbx
0x180046376  push    rbp
0x180046377  push    rsi
0x180046378  push    rdi
0x180046379  push    r14
0x18004637b  sub     rsp, 70h
0x18004637f  mov     rax, cs:__security_cookie
0x180046386  xor     rax, rsp
0x180046389  mov     [rsp+98h+var_38], rax
0x18004638e  mov     r14, r9
0x180046391  mov     rbp, r8
0x180046394  mov     rbx, rdx
0x180046397  mov     [rsp+98h+var_60], rdx
0x18004639c  mov     [rsp+98h+var_68], 0
0x1800463a4  xorps   xmm0, xmm0
0x1800463a7  movups  xmmword ptr [rdx], xmm0
0x1800463aa  mov     qword ptr [rdx+10h], 0
0x1800463b2  mov     qword ptr [rdx+18h], 7
0x1800463ba  xor     eax, eax
0x1800463bc  mov     [rdx], ax
0x1800463bf  mov     [rsp+98h+var_68], 1
0x1800463c7  cmp     r8, r9
0x1800463ca  jz      loc_180046498
0x1800463d0  mov     rsi, [rcx]
0x1800463d3  mov     rcx, rsi
0x1800463d6  call    cs:__imp___RTtypeid
0x1800463dc  lea     rdi, [rax+8]
0x1800463e0  lea     rdx, qword_18014BF88
0x1800463e7  mov     rcx, rdi
0x1800463ea  call    cs:__imp___std_type_info_compare
0x1800463f0  test    eax, eax
0x1800463f2  jz      short loc_18004640C
0x1800463f4  lea     rdx, qword_18014BFB8
0x1800463fb  mov     rcx, rdi
0x1800463fe  call    cs:__imp___std_type_info_compare
0x180046404  test    eax, eax
0x180046406  jnz     loc_180046498
0x18004640c  mov     r8, r14
0x18004640f  mov     rdx, rbp
0x180046412  lea     rcx, [rsp+98h+var_58]
0x180046417  call    ??$?0PEB_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t const *,wchar_t const *,std::allocator<wchar_t> const &)
0x18004641c  nop
0x18004641d  lea     rcx, [rsp+98h+var_58]
0x180046422  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046427  mov     r14, rax
0x18004642a  mov     rdi, [rsp+98h+var_48]
0x18004642f  lea     rbp, [rax+rdi*2]
0x180046433  cmp     [rbx+10h], rdi
0x180046437  jnb     short loc_180046482
0x180046439  add     rsi, 10h
0x18004643d  mov     rdx, rdi
0x180046440  mov     rcx, rbx
0x180046443  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180046448  mov     rcx, rbx
0x18004644b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180046450  lea     rdx, [rax+rdi*2]
0x180046454  mov     rcx, rbx
0x180046457  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18004645c  mov     [rsp+98h+var_78], rsi; __int64
0x180046461  mov     r9, rbp
0x180046464  mov     r8, r14
0x180046467  mov     rcx, rax; void *
0x18004646a  call    __std_regex_transform_primary_wchar_t
0x18004646f  mov     rdi, rax
0x180046472  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046476  jz      short loc_180046480
0x180046478  cmp     [rbx+10h], rax
0x18004647c  jb      short loc_18004643D
0x18004647e  jmp     short loc_180046482
0x180046480  xor     edi, edi
0x180046482  mov     rdx, rdi
0x180046485  mov     rcx, rbx
0x180046488  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18004648d  nop
0x18004648e  lea     rcx, [rsp+98h+var_58]
0x180046493  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046498  mov     rax, rbx
0x18004649b  mov     rcx, [rsp+98h+var_38]
0x1800464a0  xor     rcx, rsp; StackCookie
0x1800464a3  call    __security_check_cookie
0x1800464a8  add     rsp, 70h
0x1800464ac  pop     r14
0x1800464ae  pop     rdi
0x1800464af  pop     rsi
0x1800464b0  pop     rbp
0x1800464b1  pop     rbx
0x1800464b2  retn
```
