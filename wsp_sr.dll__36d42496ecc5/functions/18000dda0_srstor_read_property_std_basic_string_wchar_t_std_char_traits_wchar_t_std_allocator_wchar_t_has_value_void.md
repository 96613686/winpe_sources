# srstor::read_property<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>::has_value(void)

- ea: `0x18000dda0`
- end: `0x18000de08`
- name: `?has_value@?$read_property@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@srstor@@QEBA_NXZ`
- size: `104`
- prototype: `bool __fastcall(_QWORD *)`
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x180008948`
- `0x180008a04`
- `0x18000b48c`
- `0x18000b98c`
- `0x18000cfa4`
- `0x18000fc98`
- `0x180011e78`
- `0x1800126cc`
- `0x1800138b4`
- `0x180013c50`
- `0x1800148d8`
- `0x180015da4`
- `0x180015e78`
- `0x1800167c8`
- `0x180016b28`
- `0x1800191b4`
- `0x1800198cc`
- `0x180021bfc`
- `0x180021dbc`
- `0x180021f9c`
- `0x18002216c`
- `0x1800222d8`

## callees

- `0x1800014e0`
- `0x1800066d8`
- `0x180026a88`

## pseudocode

```c
bool __fastcall srstor::read_property<std::wstring>::has_value(_QWORD *a1)
{
  int v1; // ebx
  void **v3; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v4[88]; // [rsp+28h] [rbp-70h] BYREF

  v1 = *(_DWORD *)(mi::MiInstance::operator[](*a1, &v3, a1 + 1) + 84);
  v3 = &mi::MiValue::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v4);
  return (v1 & 0x20000000) == 0;
}

```

## disassembly

```asm
0x18000dda0  push    rbx
0x18000dda2  sub     rsp, 90h
0x18000dda9  mov     rax, cs:__security_cookie
0x18000ddb0  xor     rax, rsp
0x18000ddb3  mov     [rsp+98h+var_18], rax
0x18000ddbb  lea     r8, [rcx+8]
0x18000ddbf  mov     rcx, [rcx]
0x18000ddc2  lea     rdx, [rsp+98h+var_78]
0x18000ddc7  call    ??AMiInstance@mi@@QEBA?AVMiProperty@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; mi::MiInstance::operator[](std::wstring const &)
0x18000ddcc  lea     rcx, [rsp+98h+var_70]
0x18000ddd1  mov     ebx, [rax+54h]
0x18000ddd4  lea     rax, ??_7MiValue@mi@@6B@; const mi::MiValue::`vftable'
0x18000dddb  shr     ebx, 1Dh
0x18000ddde  not     bl
0x18000dde0  mov     [rsp+98h+var_78], rax
0x18000dde5  and     bl, 1
0x18000dde8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000dded  mov     al, bl
0x18000ddef  mov     rcx, [rsp+98h+var_18]
0x18000ddf7  xor     rcx, rsp; StackCookie
0x18000ddfa  call    __security_check_cookie
0x18000ddff  add     rsp, 90h
0x18000de06  pop     rbx
0x18000de07  retn
```
