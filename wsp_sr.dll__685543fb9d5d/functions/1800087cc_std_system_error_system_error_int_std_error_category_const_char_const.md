# std::system_error::system_error(int,std::error_category const &,char const *)

- ea: `0x1800087cc`
- end: `0x180008860`
- name: `??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z`
- size: `148`
- prototype: `__int64 __fastcall(std::system_error *__hidden this, int, const struct std::error_category *, const char *)`
- caller_count: `26`
- callee_count: `4`
- tags: ``

## callers

- `0x1800073a0`
- `0x180007428`
- `0x1800074b0`
- `0x180007538`
- `0x180012c94`
- `0x180013340`
- `0x18001cd78`
- `0x18001ce20`
- `0x180024b4c`
- `0x180024c48`
- `0x1800261d4`
- `0x1800262b8`
- `0x18002639c`
- `0x180026524`
- `0x180026ddc`
- `0x180026ee8`
- `0x1800271a4`
- `0x1800272a8`
- `0x1800274bc`
- `0x180027578`
- `0x180027798`
- `0x180027eec`
- `0x180028078`
- `0x180028f78`
- `0x180028ff0`
- `0x18002904c`

## callees

- `0x1800014e0`
- `0x180008404`
- `0x180008540`
- `0x18000daf0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::system_error *__fastcall std::system_error::system_error(
        std::system_error *this,
        int a2,
        const struct std::error_category *a3,
        const char *a4)
{
  _DWORD v8[2]; // [rsp+20h] [rbp-48h] BYREF
  const struct std::error_category *v9; // [rsp+28h] [rbp-40h]
  _BYTE v10[32]; // [rsp+30h] [rbp-38h] BYREF

  v8[1] = HIDWORD(this);
  std::string::string(v10, a4);
  v8[0] = a2;
  v9 = a3;
  std::_System_error::_System_error(this, v8, v10);
  std::string::_Tidy_deallocate(v10);
  *(_QWORD *)this = &std::system_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800087cc  mov     [rsp+arg_8], rbx
0x1800087d1  mov     [rsp+arg_10], rsi
0x1800087d6  push    rdi
0x1800087d7  sub     rsp, 60h
0x1800087db  mov     rax, cs:__security_cookie
0x1800087e2  xor     rax, rsp
0x1800087e5  mov     [rsp+68h+var_18], rax
0x1800087ea  mov     rdi, r8
0x1800087ed  mov     ebx, edx
0x1800087ef  mov     rsi, rcx
0x1800087f2  mov     [rsp+68h+var_48], rcx
0x1800087f7  mov     rdx, r9
0x1800087fa  lea     rcx, [rsp+68h+var_38]
0x1800087ff  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180008804  nop
0x180008805  mov     dword ptr [rsp+68h+var_48], ebx
0x180008809  mov     ecx, dword ptr [rsp+68h+var_48+4]
0x18000880d  mov     dword ptr [rsp+68h+var_48+4], ecx
0x180008811  mov     [rsp+68h+var_40], rdi
0x180008816  lea     r8, [rsp+68h+var_38]
0x18000881b  lea     rdx, [rsp+68h+var_48]
0x180008820  mov     rcx, rsi
0x180008823  call    ??0_System_error@std@@IEAA@Verror_code@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_System_error::_System_error(std::error_code,std::string const &)
0x180008828  nop
0x180008829  lea     rcx, [rsp+68h+var_38]
0x18000882e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180008833  lea     rax, ??_7system_error@std@@6B@; const std::system_error::`vftable'
0x18000883a  mov     [rsi], rax
0x18000883d  mov     rax, rsi
0x180008840  mov     rcx, [rsp+68h+var_18]
0x180008845  xor     rcx, rsp; StackCookie
0x180008848  call    __security_check_cookie
0x18000884d  lea     r11, [rsp+68h+var_8]
0x180008852  mov     rbx, [r11+18h]
0x180008856  mov     rsi, [r11+20h]
0x18000885a  mov     rsp, r11
0x18000885d  pop     rdi
0x18000885e  retn
```
