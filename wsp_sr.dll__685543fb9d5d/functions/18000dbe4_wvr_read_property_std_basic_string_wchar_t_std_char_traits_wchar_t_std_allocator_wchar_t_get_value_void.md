# wvr::read_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::get_value(void)

- ea: `0x18000dbe4`
- end: `0x18000dc6a`
- name: `?get_value@?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wvr@@QEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `134`
- prototype: ``
- caller_count: `14`
- callee_count: `6`
- tags: ``

## callers

- `0x180008b90`
- `0x18000b5f8`
- `0x18000bab8`
- `0x18000fc70`
- `0x180011d40`
- `0x180013b60`
- `0x18001478c`
- `0x1800169ec`
- `0x180019904`
- `0x180021da4`
- `0x180021f64`
- `0x18002214c`
- `0x18002231c`
- `0x180022490`

## callees

- `0x1800014e0`
- `0x180005884`
- `0x18000590c`
- `0x180006724`
- `0x180006cf8`
- `0x180008440`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wvr::read_property<std::wstring>::get_value(__int64 a1, __int64 a2)
{
  _QWORD *v3; // r9
  __int64 v4; // rax
  __int64 v5; // rdx
  _BYTE v7[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v8[32]; // [rsp+50h] [rbp-38h] BYREF

  std::wstring::wstring(v8);
  mi::MiInstance::GetElement<std::wstring>(*v3, v3 + 1, v8);
  v4 = std::wstring::wstring(v7, v8);
  std::wstring::wstring(a2, v4);
  std::wstring::_Tidy_deallocate(v5);
  std::wstring::_Tidy_deallocate(v8);
  return a2;
}

```

## disassembly

```asm
0x18000dbe4  push    rbx
0x18000dbe6  sub     rsp, 80h
0x18000dbed  mov     rax, cs:__security_cookie
0x18000dbf4  xor     rax, rsp
0x18000dbf7  mov     [rsp+88h+var_18], rax
0x18000dbfc  mov     rbx, rdx
0x18000dbff  mov     r9, rcx
0x18000dc02  mov     [rsp+88h+var_60], rdx
0x18000dc07  lea     rcx, [rsp+88h+var_38]
0x18000dc0c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000dc11  nop
0x18000dc12  lea     rdx, [r9+8]
0x18000dc16  lea     r8, [rsp+88h+var_38]
0x18000dc1b  mov     rcx, [r9]
0x18000dc1e  call    ??$GetElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z; mi::MiInstance::GetElement<std::wstring>(std::wstring const &,std::wstring &)
0x18000dc23  lea     rdx, [rsp+88h+var_38]
0x18000dc28  lea     rcx, [rsp+88h+var_58]
0x18000dc2d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dc32  mov     rdx, rax
0x18000dc35  mov     rcx, rbx
0x18000dc38  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000dc3d  mov     rcx, rdx
0x18000dc40  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000dc45  nop
0x18000dc46  lea     rcx, [rsp+88h+var_38]
0x18000dc4b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000dc50  mov     rax, rbx
0x18000dc53  mov     rcx, [rsp+88h+var_18]
0x18000dc58  xor     rcx, rsp; StackCookie
0x18000dc5b  call    __security_check_cookie
0x18000dc60  add     rsp, 80h
0x18000dc67  pop     rbx
0x18000dc68  retn
```
