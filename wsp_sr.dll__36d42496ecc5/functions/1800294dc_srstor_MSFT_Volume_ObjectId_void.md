# srstor::MSFT_Volume::ObjectId(void)

- ea: `0x1800294dc`
- end: `0x180029549`
- name: `?ObjectId@MSFT_Volume@srstor@@QEBA?BV?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@XZ`
- size: `109`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180021bfc`
- `0x180021dbc`
- `0x180021f9c`
- `0x18002216c`
- `0x1800222d8`

## callees

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x18001fff4`

## pseudocode

```c
_QWORD *__fastcall srstor::MSFT_Volume::ObjectId(__int64 a1, _QWORD *a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)L"ObjectId");
  srstor::read_property<std::wstring>::read_property<std::wstring>(a2, a1 + 8, v5);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return a2;
}

```

## disassembly

```asm
0x1800294dc  mov     [rsp+arg_0], rbx
0x1800294e1  push    rdi
0x1800294e2  sub     rsp, 60h
0x1800294e6  mov     rax, cs:__security_cookie
0x1800294ed  xor     rax, rsp
0x1800294f0  mov     [rsp+68h+var_18], rax
0x1800294f5  mov     rdi, rdx
0x1800294f8  mov     rbx, rcx
0x1800294fb  mov     [rsp+68h+var_40], rdx
0x180029500  lea     rdx, aObjectid; "ObjectId"
0x180029507  lea     rcx, [rsp+68h+var_38]
0x18002950c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180029511  nop
0x180029512  lea     rdx, [rbx+8]
0x180029516  lea     r8, [rsp+68h+var_38]
0x18002951b  mov     rcx, rdi
0x18002951e  call    ??0?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEAA@AEBVMiInstance@mi@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; srstor::read_property<std::wstring>::read_property<std::wstring>(mi::MiInstance const &,std::wstring const &)
0x180029523  nop
0x180029524  lea     rcx, [rsp+68h+var_38]
0x180029529  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002952e  mov     rax, rdi
0x180029531  mov     rcx, [rsp+68h+var_18]
0x180029536  xor     rcx, rsp; StackCookie
0x180029539  call    __security_check_cookie
0x18002953e  mov     rbx, [rsp+68h+arg_0]
0x180029543  add     rsp, 60h
0x180029547  pop     rdi
0x180029548  retn
```
