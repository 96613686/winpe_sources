# UusPackageUpdateInfo::LoadStringField(web::json::value const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x18000a5b0`
- end: `0x18000a699`
- name: `?LoadStringField@UusPackageUpdateInfo@@AEAAXAEBVvalue@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180009f40`

## callees

- `0x18000a5b0`
- `0x18000e0bc`
- `0x180028728`
- `0x180029644`
- `0x180029984`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UusPackageUpdateInfo::LoadStringField(__int64 a1, _QWORD *a2, __int64 a3)
{
  wchar_t *v6; // rax
  __int64 v7; // rax
  _BYTE v9[32]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v11[32]; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v12[16]; // [rsp+80h] [rbp-38h] BYREF
  __int64 v13; // [rsp+90h] [rbp-28h]

  v13 = a3;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 8LL))(*a2, a3) )
  {
    v6 = web::json::value::at(a2, a3);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 176LL))(*(_QWORD *)v6);
    std::wstring::wstring((__int64)v9, v7);
    std::wstring::wstring((__int64)v10, a3);
    std::wstring::wstring((__int64)v11, (__int64)v9);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::insert<0,0>(
      a1 + 40,
      v12,
      v10);
    std::wstring::_Tidy_deallocate((__int64)v11);
    std::wstring::_Tidy_deallocate((__int64)v10);
    std::wstring::_Tidy_deallocate((__int64)v9);
  }
  return std::wstring::_Tidy_deallocate(a3);
}

```

## disassembly

```asm
0x18000a5b0  mov     r11, rsp
0x18000a5b3  push    rbx
0x18000a5b4  push    rsi
0x18000a5b5  push    rdi
0x18000a5b6  sub     rsp, 0A0h
0x18000a5bd  mov     rax, cs:__security_cookie
0x18000a5c4  xor     rax, rsp
0x18000a5c7  mov     [rsp+0B8h+var_20], rax
0x18000a5cf  mov     rbx, r8
0x18000a5d2  mov     rdi, rdx
0x18000a5d5  mov     rsi, rcx
0x18000a5d8  mov     [r11-28h], rbx
0x18000a5dc  mov     rcx, [rdx]
0x18000a5df  mov     rax, [rcx]
0x18000a5e2  mov     rdx, r8
0x18000a5e5  mov     rax, [rax+8]
0x18000a5e9  call    _guard_dispatch_icall
0x18000a5ee  test    al, al
0x18000a5f0  jz      loc_18000A676
0x18000a5f6  mov     rdx, rbx
0x18000a5f9  mov     rcx, rdi
0x18000a5fc  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18000a601  mov     rcx, [rax]
0x18000a604  mov     rax, [rcx]
0x18000a607  mov     rax, [rax+0B0h]
0x18000a60e  call    _guard_dispatch_icall
0x18000a613  mov     rdx, rax
0x18000a616  lea     rcx, [rsp+0B8h+var_98]
0x18000a61b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a620  nop
0x18000a621  mov     rdx, rbx
0x18000a624  lea     rcx, [rsp+0B8h+var_78]
0x18000a629  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a62e  nop
0x18000a62f  lea     rdx, [rsp+0B8h+var_98]
0x18000a634  lea     rcx, [rsp+0B8h+var_58]
0x18000a639  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000a63e  nop
0x18000a63f  lea     rcx, [rsi+28h]
0x18000a643  lea     r8, [rsp+0B8h+var_78]
0x18000a648  lea     rdx, [rsp+0B8h+var_38]
0x18000a650  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::insert<0,0>(std::pair<std::wstring const,std::wstring> &&)
0x18000a655  nop
0x18000a656  lea     rcx, [rsp+0B8h+var_58]
0x18000a65b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a660  lea     rcx, [rsp+0B8h+var_78]
0x18000a665  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a66a  nop
0x18000a66b  lea     rcx, [rsp+0B8h+var_98]
0x18000a670  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a675  nop
0x18000a676  mov     rcx, rbx
0x18000a679  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a67e  mov     rcx, [rsp+0B8h+var_20]
0x18000a686  xor     rcx, rsp; StackCookie
0x18000a689  call    __security_check_cookie
0x18000a68e  add     rsp, 0A0h
0x18000a695  pop     rdi
0x18000a696  pop     rsi
0x18000a697  pop     rbx
0x18000a698  retn
```
