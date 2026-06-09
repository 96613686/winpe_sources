# std::system_error::system_error(int,std::error_category const &,char const *)

- ea: `0x180008668`
- end: `0x1800086fb`
- name: `??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z`
- size: `147`
- prototype: `std::system_error *__fastcall(std::system_error *this, int, const struct std::error_category *, const char *)`
- caller_count: `26`
- callee_count: `4`
- tags: ``

## callers

- `0x1800072d8`
- `0x18000735c`
- `0x1800073e0`
- `0x180007464`
- `0x180012dc4`
- `0x18001346c`
- `0x18001cc70`
- `0x18001cd14`
- `0x180024860`
- `0x180024958`
- `0x180025ea4`
- `0x180025f80`
- `0x180026064`
- `0x1800261e8`
- `0x180026a88`
- `0x180026b90`
- `0x180026e4c`
- `0x180026f4c`
- `0x18002715c`
- `0x180027218`
- `0x180027438`
- `0x180027b64`
- `0x180027cdc`
- `0x180028b28`
- `0x180028b90`
- `0x180028be0`

## callees

- `0x1800014e0`
- `0x1800082c8`
- `0x1800083f4`
- `0x18000dc04`

## pseudocode

```c
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
0x180008668  mov     [rsp+arg_8], rbx
0x18000866d  mov     [rsp+arg_10], rsi
0x180008672  push    rdi
0x180008673  sub     rsp, 60h
0x180008677  mov     rax, cs:__security_cookie
0x18000867e  xor     rax, rsp
0x180008681  mov     [rsp+68h+var_18], rax
0x180008686  mov     rdi, r8
0x180008689  mov     ebx, edx
0x18000868b  mov     rsi, rcx
0x18000868e  mov     [rsp+68h+var_48], rcx
0x180008693  mov     rdx, r9
0x180008696  lea     rcx, [rsp+68h+var_38]
0x18000869b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800086a0  nop
0x1800086a1  mov     dword ptr [rsp+68h+var_48], ebx
0x1800086a5  mov     ecx, dword ptr [rsp+68h+var_48+4]
0x1800086a9  mov     dword ptr [rsp+68h+var_48+4], ecx
0x1800086ad  mov     [rsp+68h+var_40], rdi
0x1800086b2  lea     r8, [rsp+68h+var_38]
0x1800086b7  lea     rdx, [rsp+68h+var_48]
0x1800086bc  mov     rcx, rsi
0x1800086bf  call    ??0_System_error@std@@IEAA@Verror_code@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_System_error::_System_error(std::error_code,std::string const &)
0x1800086c4  nop
0x1800086c5  lea     rcx, [rsp+68h+var_38]
0x1800086ca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800086cf  lea     rax, ??_7system_error@std@@6B@; const std::system_error::`vftable'
0x1800086d6  mov     [rsi], rax
0x1800086d9  mov     rax, rsi
0x1800086dc  mov     rcx, [rsp+68h+var_18]
0x1800086e1  xor     rcx, rsp; StackCookie
0x1800086e4  call    __security_check_cookie
0x1800086e9  lea     r11, [rsp+68h+var_8]
0x1800086ee  mov     rbx, [r11+18h]
0x1800086f2  mov     rsi, [r11+20h]
0x1800086f6  mov     rsp, r11
0x1800086f9  pop     rdi
0x1800086fa  retn
```
