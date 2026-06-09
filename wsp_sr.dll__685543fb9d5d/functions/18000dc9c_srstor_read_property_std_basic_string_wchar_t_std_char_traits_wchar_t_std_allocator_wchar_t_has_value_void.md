# srstor::read_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::has_value(void)

- ea: `0x18000dc9c`
- end: `0x18000dd05`
- name: `?has_value@?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEBA_NXZ`
- size: `105`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x180008ad4`
- `0x180008b90`
- `0x18000b5f8`
- `0x18000bab8`
- `0x18000cec8`
- `0x18000fc70`
- `0x180011d40`
- `0x180012594`
- `0x1800137bc`
- `0x180013b60`
- `0x18001478c`
- `0x180015c58`
- `0x180015d2c`
- `0x180016684`
- `0x1800169ec`
- `0x1800191e0`
- `0x180019904`
- `0x180021da4`
- `0x180021f64`
- `0x18002214c`
- `0x18002231c`
- `0x180022490`

## callees

- `0x1800014e0`
- `0x180006724`
- `0x180026ddc`

## pseudocode

```c
bool __fastcall srstor::read_property<std::wstring>::has_value(_QWORD *a1)
{
  int v1; // ebx
  void **v3; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v4[88]; // [rsp+28h] [rbp-70h] BYREF

  v1 = *(_DWORD *)(mi::MiInstance::operator[](*a1, &v3, a1 + 1) + 84);
  v3 = &mi::MiValue::`vftable';
  std::wstring::_Tidy_deallocate(v4);
  return (v1 & 0x20000000) == 0;
}

```

## disassembly

```asm
0x18000dc9c  push    rbx
0x18000dc9e  sub     rsp, 90h
0x18000dca5  mov     rax, cs:__security_cookie
0x18000dcac  xor     rax, rsp
0x18000dcaf  mov     [rsp+98h+var_18], rax
0x18000dcb7  lea     r8, [rcx+8]
0x18000dcbb  mov     rcx, [rcx]
0x18000dcbe  lea     rdx, [rsp+98h+var_78]
0x18000dcc3  call    ??AMiInstance@mi@@QEBA?AVMiProperty@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; mi::MiInstance::operator[](std::wstring const &)
0x18000dcc8  lea     rcx, [rsp+98h+var_70]
0x18000dccd  mov     ebx, [rax+54h]
0x18000dcd0  lea     rax, ??_7MiValue@mi@@6B@; const mi::MiValue::`vftable'
0x18000dcd7  shr     ebx, 1Dh
0x18000dcda  not     bl
0x18000dcdc  mov     [rsp+98h+var_78], rax
0x18000dce1  and     bl, 1
0x18000dce4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000dce9  mov     al, bl
0x18000dceb  mov     rcx, [rsp+98h+var_18]
0x18000dcf3  xor     rcx, rsp; StackCookie
0x18000dcf6  call    __security_check_cookie
0x18000dcfb  add     rsp, 90h
0x18000dd02  pop     rbx
0x18000dd03  retn
```
