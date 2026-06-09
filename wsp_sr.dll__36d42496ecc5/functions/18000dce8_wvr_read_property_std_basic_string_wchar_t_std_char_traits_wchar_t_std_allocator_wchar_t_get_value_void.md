# wvr::read_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::get_value(void)

- ea: `0x18000dce8`
- end: `0x18000dd6d`
- name: `?get_value@?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wvr@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `133`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `14`
- callee_count: `6`
- tags: ``

## callers

- `0x180008a04`
- `0x18000b48c`
- `0x18000b98c`
- `0x18000fc98`
- `0x180011e78`
- `0x180013c50`
- `0x1800148d8`
- `0x180016b28`
- `0x1800198cc`
- `0x180021bfc`
- `0x180021dbc`
- `0x180021f9c`
- `0x18002216c`
- `0x1800222d8`

## callees

- `0x1800014e0`
- `0x18000584c`
- `0x1800058d4`
- `0x1800066d8`
- `0x180006c3c`
- `0x180008304`

## pseudocode

```c
__int64 __fastcall wvr::read_property<std::wstring>::get_value(__int64 a1, __int64 a2)
{
  _QWORD *v3; // r9
  __int64 v4; // rax
  __int64 v5; // rdx
  _BYTE v7[32]; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v8[4]; // [rsp+50h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v8);
  mi::MiInstance::GetElement<std::wstring>(*v3, v3 + 1, v8);
  v4 = std::wstring::wstring((__int64)v7, v8);
  std::wstring::wstring(a2, v4);
  std::wstring::_Tidy_deallocate(v5);
  std::wstring::_Tidy_deallocate((__int64)v8);
  return a2;
}

```

## disassembly

```asm
0x18000dce8  push    rbx
0x18000dcea  sub     rsp, 80h
0x18000dcf1  mov     rax, cs:__security_cookie
0x18000dcf8  xor     rax, rsp
0x18000dcfb  mov     [rsp+88h+var_18], rax
0x18000dd00  mov     rbx, rdx
0x18000dd03  mov     r9, rcx
0x18000dd06  mov     [rsp+88h+var_60], rdx
0x18000dd0b  lea     rcx, [rsp+88h+var_38]
0x18000dd10  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000dd15  nop
0x18000dd16  lea     rdx, [r9+8]
0x18000dd1a  lea     r8, [rsp+88h+var_38]
0x18000dd1f  mov     rcx, [r9]
0x18000dd22  call    ??$GetElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z; mi::MiInstance::GetElement<std::wstring>(std::wstring const &,std::wstring &)
0x18000dd27  lea     rdx, [rsp+88h+var_38]
0x18000dd2c  lea     rcx, [rsp+88h+var_58]
0x18000dd31  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dd36  mov     rdx, rax
0x18000dd39  mov     rcx, rbx
0x18000dd3c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000dd41  mov     rcx, rdx
0x18000dd44  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000dd49  nop
0x18000dd4a  lea     rcx, [rsp+88h+var_38]
0x18000dd4f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000dd54  mov     rax, rbx
0x18000dd57  mov     rcx, [rsp+88h+var_18]
0x18000dd5c  xor     rcx, rsp; StackCookie
0x18000dd5f  call    __security_check_cookie
0x18000dd64  add     rsp, 80h
0x18000dd6b  pop     rbx
0x18000dd6c  retn
```
