# CLI::ConfigError::NotConfigurable(std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x14001d120`
- end: `0x14001d1db`
- name: `?NotConfigurable@ConfigError@CLI@@SA?AV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140023ac0`

## callees

- `0x1400083f0`
- `0x14000ba3c`
- `0x14000f7e0`
- `0x140017320`
- `0x14001d120`
- `0x14004aaac`

## string_xrefs

- `0x14001d17b`: `: This option is not allowed in a configuration file`

## pseudocode

```c
_QWORD *__fastcall CLI::ConfigError::NotConfigurable(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // r9
  unsigned __int8 v7; // [rsp+40h] [rbp-48h]
  _BYTE v8[32]; // [rsp+50h] [rbp-38h] BYREF
  _QWORD *v9; // [rsp+70h] [rbp-18h]

  v9 = a2;
  v4 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - v4) < 0x34 )
    std::_Xlen_string();
  if ( a2[3] <= 0xFu )
    v5 = a2;
  else
    v5 = (_QWORD *)*a2;
  std::string::string(v8, v7, a2, v5, v4, ": This option is not allowed in a configuration file", 52);
  CLI::ConfigError::ConfigError(a1, v8);
  std::string::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x14001d120  mov     [rsp+arg_10], rbx
0x14001d125  push    rdi
0x14001d126  sub     rsp, 80h
0x14001d12d  mov     rax, cs:__security_cookie
0x14001d134  xor     rax, rsp
0x14001d137  mov     [rsp+88h+var_10], rax
0x14001d13c  mov     rbx, rdx
0x14001d13f  mov     rdi, rcx
0x14001d142  mov     [rsp+88h+var_18], rcx
0x14001d147  mov     [rsp+88h+var_18], rdx
0x14001d14c  mov     rcx, [rdx+10h]
0x14001d150  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001d15a  sub     rax, rcx
0x14001d15d  cmp     rax, 34h ; '4'
0x14001d161  jb      short loc_14001D1D5
0x14001d163  cmp     qword ptr [rdx+18h], 0Fh
0x14001d168  jbe     short loc_14001D16F
0x14001d16a  mov     r9, [rdx]
0x14001d16d  jmp     short loc_14001D172
0x14001d16f  mov     r9, rbx
0x14001d172  mov     [rsp+88h+var_58], 34h ; '4'
0x14001d17b  lea     rax, aThisOptionIsNo; ": This option is not allowed in a confi"...
0x14001d182  mov     [rsp+88h+var_60], rax
0x14001d187  mov     [rsp+88h+var_68], rcx
0x14001d18c  mov     r8, rbx
0x14001d18f  movzx   edx, [rsp+88h+var_48]
0x14001d194  lea     rcx, [rsp+88h+var_38]
0x14001d199  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x14001d19e  lea     rdx, [rsp+88h+var_38]
0x14001d1a3  mov     rcx, rdi
0x14001d1a6  call    ??0ConfigError@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::ConfigError::ConfigError(std::string)
0x14001d1ab  nop
0x14001d1ac  mov     rcx, rbx; void *
0x14001d1af  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001d1b4  mov     rax, rdi
0x14001d1b7  mov     rcx, [rsp+88h+var_10]
0x14001d1bc  xor     rcx, rsp; StackCookie
0x14001d1bf  call    __security_check_cookie
0x14001d1c4  mov     rbx, [rsp+88h+arg_10]
0x14001d1cc  add     rsp, 80h
0x14001d1d3  pop     rdi
0x14001d1d4  retn
0x14001d1d5  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
