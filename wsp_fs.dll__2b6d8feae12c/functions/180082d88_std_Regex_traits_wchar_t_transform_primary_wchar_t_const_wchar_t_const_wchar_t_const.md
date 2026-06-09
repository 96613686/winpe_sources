# std::_Regex_traits<wchar_t>::transform_primary<wchar_t const *>(wchar_t const *,wchar_t const *)

- ea: `0x180082d88`
- end: `0x180082ec8`
- name: `??$transform_primary@PEB_W@?$_Regex_traits@_W@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEB_W0@Z`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800883ec`

## callees

- `0x180002a70`
- `0x180004fe8`
- `0x18000a6dc`
- `0x18000dd74`
- `0x180010e64`
- `0x1800192a8`
- `0x180082d88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180082dfe`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180082e12`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180082dfe`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180082e12`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180082dea`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180082dea`

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
    if ( !(unsigned int)__std_type_info_compare(v8, &qword_180178218)
      || !(unsigned int)__std_type_info_compare(v8, &qword_180178248) )
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
0x180082d88  push    rbx
0x180082d8a  push    rbp
0x180082d8b  push    rsi
0x180082d8c  push    rdi
0x180082d8d  push    r14
0x180082d8f  sub     rsp, 70h
0x180082d93  mov     rax, cs:__security_cookie
0x180082d9a  xor     rax, rsp
0x180082d9d  mov     [rsp+98h+var_38], rax
0x180082da2  mov     r14, r9
0x180082da5  mov     rbp, r8
0x180082da8  mov     rbx, rdx
0x180082dab  mov     [rsp+98h+var_60], rdx
0x180082db0  mov     [rsp+98h+var_68], 0
0x180082db8  xorps   xmm0, xmm0
0x180082dbb  movups  xmmword ptr [rdx], xmm0
0x180082dbe  mov     qword ptr [rdx+10h], 0
0x180082dc6  mov     qword ptr [rdx+18h], 7
0x180082dce  xor     eax, eax
0x180082dd0  mov     [rdx], ax
0x180082dd3  mov     [rsp+98h+var_68], 1
0x180082ddb  cmp     r8, r9
0x180082dde  jz      loc_180082EAC
0x180082de4  mov     rsi, [rcx]
0x180082de7  mov     rcx, rsi
0x180082dea  call    cs:__imp___RTtypeid
0x180082df0  lea     rdi, [rax+8]
0x180082df4  lea     rdx, qword_180178218
0x180082dfb  mov     rcx, rdi
0x180082dfe  call    cs:__imp___std_type_info_compare
0x180082e04  test    eax, eax
0x180082e06  jz      short loc_180082E20
0x180082e08  lea     rdx, qword_180178248
0x180082e0f  mov     rcx, rdi
0x180082e12  call    cs:__imp___std_type_info_compare
0x180082e18  test    eax, eax
0x180082e1a  jnz     loc_180082EAC
0x180082e20  mov     r8, r14
0x180082e23  mov     rdx, rbp
0x180082e26  lea     rcx, [rsp+98h+var_58]
0x180082e2b  call    ??$?0PEB_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t const *,wchar_t const *,std::allocator<wchar_t> const &)
0x180082e30  nop
0x180082e31  lea     rcx, [rsp+98h+var_58]
0x180082e36  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180082e3b  mov     r14, rax
0x180082e3e  mov     rdi, [rsp+98h+var_48]
0x180082e43  lea     rbp, [rax+rdi*2]
0x180082e47  cmp     [rbx+10h], rdi
0x180082e4b  jnb     short loc_180082E96
0x180082e4d  add     rsi, 10h
0x180082e51  mov     rdx, rdi
0x180082e54  mov     rcx, rbx
0x180082e57  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180082e5c  mov     rcx, rbx
0x180082e5f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180082e64  lea     rdx, [rax+rdi*2]
0x180082e68  mov     rcx, rbx
0x180082e6b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180082e70  mov     [rsp+98h+var_78], rsi; __int64
0x180082e75  mov     r9, rbp
0x180082e78  mov     r8, r14
0x180082e7b  mov     rcx, rax; void *
0x180082e7e  call    __std_regex_transform_primary_wchar_t
0x180082e83  mov     rdi, rax
0x180082e86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180082e8a  jz      short loc_180082E94
0x180082e8c  cmp     [rbx+10h], rax
0x180082e90  jb      short loc_180082E51
0x180082e92  jmp     short loc_180082E96
0x180082e94  xor     edi, edi
0x180082e96  mov     rdx, rdi
0x180082e99  mov     rcx, rbx
0x180082e9c  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180082ea1  nop
0x180082ea2  lea     rcx, [rsp+98h+var_58]
0x180082ea7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180082eac  mov     rax, rbx
0x180082eaf  mov     rcx, [rsp+98h+var_38]
0x180082eb4  xor     rcx, rsp; StackCookie
0x180082eb7  call    __security_check_cookie
0x180082ebc  add     rsp, 70h
0x180082ec0  pop     r14
0x180082ec2  pop     rdi
0x180082ec3  pop     rsi
0x180082ec4  pop     rbp
0x180082ec5  pop     rbx
0x180082ec6  retn
```
