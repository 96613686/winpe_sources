# CLI::BadNameString::MultiPositionalNames(std::basic_string<char,std::char_traits<char>,std::allocator<char>>)

- ea: `0x14001d050`
- end: `0x14001d10b`
- name: `?MultiPositionalNames@BadNameString@CLI@@SA?AV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140033690`

## callees

- `0x1400083f0`
- `0x14000ba3c`
- `0x14000f7e0`
- `0x140016e00`
- `0x14001d050`
- `0x14004aaac`

## string_xrefs

- `0x14001d0b5`: `Only one positional name allowed, remove: `

## pseudocode

```c
__int64 __fastcall CLI::BadNameString::MultiPositionalNames(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  unsigned __int8 v6; // [rsp+40h] [rbp-48h]
  _BYTE v7[32]; // [rsp+50h] [rbp-38h] BYREF
  _QWORD *v8; // [rsp+70h] [rbp-18h]

  v8 = a2;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - a2[2]) < 0x2A )
    std::_Xlen_string();
  if ( a2[3] <= 0xFu )
    v4 = a2;
  else
    v4 = (_QWORD *)*a2;
  std::string::string(v7, v6, a2, "Only one positional name allowed, remove: ", 42, v4, a2[2]);
  CLI::BadNameString::BadNameString(a1, v7);
  std::string::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x14001d050  mov     [rsp+arg_10], rbx
0x14001d055  push    rdi
0x14001d056  sub     rsp, 80h
0x14001d05d  mov     rax, cs:__security_cookie
0x14001d064  xor     rax, rsp
0x14001d067  mov     [rsp+88h+var_10], rax
0x14001d06c  mov     rbx, rdx
0x14001d06f  mov     rdi, rcx
0x14001d072  mov     [rsp+88h+var_18], rcx
0x14001d077  mov     [rsp+88h+var_18], rdx
0x14001d07c  mov     rcx, [rdx+10h]
0x14001d080  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001d08a  sub     rax, rcx
0x14001d08d  cmp     rax, 2Ah ; '*'
0x14001d091  jb      short loc_14001D105
0x14001d093  cmp     qword ptr [rdx+18h], 0Fh
0x14001d098  jbe     short loc_14001D09F
0x14001d09a  mov     rax, [rdx]
0x14001d09d  jmp     short loc_14001D0A2
0x14001d09f  mov     rax, rbx
0x14001d0a2  mov     [rsp+88h+var_58], rcx
0x14001d0a7  mov     [rsp+88h+var_60], rax
0x14001d0ac  mov     [rsp+88h+var_68], 2Ah ; '*'
0x14001d0b5  lea     r9, aOnlyOnePositio; "Only one positional name allowed, remov"...
0x14001d0bc  mov     r8, rbx
0x14001d0bf  movzx   edx, [rsp+88h+var_48]
0x14001d0c4  lea     rcx, [rsp+88h+var_38]
0x14001d0c9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x14001d0ce  lea     rdx, [rsp+88h+var_38]
0x14001d0d3  mov     rcx, rdi
0x14001d0d6  call    ??0BadNameString@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::BadNameString::BadNameString(std::string)
0x14001d0db  nop
0x14001d0dc  mov     rcx, rbx; void *
0x14001d0df  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14001d0e4  mov     rax, rdi
0x14001d0e7  mov     rcx, [rsp+88h+var_10]
0x14001d0ec  xor     rcx, rsp; StackCookie
0x14001d0ef  call    __security_check_cookie
0x14001d0f4  mov     rbx, [rsp+88h+arg_10]
0x14001d0fc  add     rsp, 80h
0x14001d103  pop     rdi
0x14001d104  retn
0x14001d105  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
