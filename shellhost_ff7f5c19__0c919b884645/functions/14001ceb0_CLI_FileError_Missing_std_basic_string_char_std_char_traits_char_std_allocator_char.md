# CLI::FileError::Missing(std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x14001ceb0`
- end: `0x14001cf6b`
- name: `?Missing@FileError@CLI@@SA?AV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140024db0`

## callees

- `0x1400083f0`
- `0x14000ba3c`
- `0x14000f7e0`
- `0x140018580`
- `0x14001ceb0`
- `0x14004aaac`

## string_xrefs

- `0x14001cf0b`: ` was not readable (missing?)`

## pseudocode

```c
__int64 __fastcall CLI::FileError::Missing(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // r9
  unsigned __int8 v7; // [rsp+40h] [rbp-48h]
  _BYTE v8[32]; // [rsp+50h] [rbp-38h] BYREF
  _QWORD *v9; // [rsp+70h] [rbp-18h]

  v9 = a2;
  v4 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - v4) < 0x1C )
    std::_Xlen_string();
  if ( a2[3] <= 0xFu )
    v5 = a2;
  else
    v5 = (_QWORD *)*a2;
  std::string::string(v8, v7, a2, v5, v4, " was not readable (missing?)", 28);
  CLI::FileError::FileError(a1, v8);
  std::string::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x14001ceb0  mov     [rsp+arg_10], rbx
0x14001ceb5  push    rdi
0x14001ceb6  sub     rsp, 80h
0x14001cebd  mov     rax, cs:__security_cookie
0x14001cec4  xor     rax, rsp
0x14001cec7  mov     [rsp+88h+var_10], rax
0x14001cecc  mov     rbx, rdx
0x14001cecf  mov     rdi, rcx
0x14001ced2  mov     [rsp+88h+var_18], rcx
0x14001ced7  mov     [rsp+88h+var_18], rdx
0x14001cedc  mov     rcx, [rdx+10h]
0x14001cee0  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001ceea  sub     rax, rcx
0x14001ceed  cmp     rax, 1Ch
0x14001cef1  jb      short loc_14001CF65
0x14001cef3  cmp     qword ptr [rdx+18h], 0Fh
0x14001cef8  jbe     short loc_14001CEFF
0x14001cefa  mov     r9, [rdx]
0x14001cefd  jmp     short loc_14001CF02
0x14001ceff  mov     r9, rbx
0x14001cf02  mov     [rsp+88h+var_58], 1Ch
0x14001cf0b  lea     rax, aWasNotReadable; " was not readable (missing?)"
0x14001cf12  mov     [rsp+88h+var_60], rax
0x14001cf17  mov     [rsp+88h+var_68], rcx
0x14001cf1c  mov     r8, rbx
0x14001cf1f  movzx   edx, [rsp+88h+var_48]
0x14001cf24  lea     rcx, [rsp+88h+var_38]
0x14001cf29  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x14001cf2e  lea     rdx, [rsp+88h+var_38]
0x14001cf33  mov     rcx, rdi
0x14001cf36  call    ??0FileError@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::FileError::FileError(std::string)
0x14001cf3b  nop
0x14001cf3c  mov     rcx, rbx; void *
0x14001cf3f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001cf44  mov     rax, rdi
0x14001cf47  mov     rcx, [rsp+88h+var_10]
0x14001cf4c  xor     rcx, rsp; StackCookie
0x14001cf4f  call    __security_check_cookie
0x14001cf54  mov     rbx, [rsp+88h+arg_10]
0x14001cf5c  add     rsp, 80h
0x14001cf63  pop     rdi
0x14001cf64  retn
0x14001cf65  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
