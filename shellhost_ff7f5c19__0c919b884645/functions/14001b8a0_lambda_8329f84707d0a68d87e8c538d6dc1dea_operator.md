# _lambda_8329f84707d0a68d87e8c538d6dc1dea_::operator()

- ea: `0x14001b8a0`
- end: `0x14001b97b`
- name: `_lambda_8329f84707d0a68d87e8c538d6dc1dea_::operator()`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001fb70`

## callees

- `0x14000ba3c`
- `0x14000f7e0`
- `0x14001b8a0`
- `0x14004aaac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stat64` at `0x14001b8dc`
- `api-ms-win-crt-private-l1-1-0!_o__stat64` at `0x14001b8dc`

## string_xrefs

- `0x14001b911`: `Path already exists: `

## pseudocode

```c
__int64 __fastcall lambda_8329f84707d0a68d87e8c538d6dc1dea_::operator()(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  unsigned __int8 v8; // [rsp+40h] [rbp-58h]
  _BYTE v9[56]; // [rsp+50h] [rbp-48h] BYREF

  v5 = a3;
  if ( a3[3] > 0xFu )
    v5 = (_QWORD *)*a3;
  if ( (unsigned int)_o__stat64(v5, v9) )
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 15;
    *(_BYTE *)a2 = 0;
  }
  else
  {
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - a3[2]) < 0x15 )
      std::_Xlen_string();
    if ( a3[3] <= 0xFu )
      v6 = a3;
    else
      v6 = (_QWORD *)*a3;
    std::string::string(a2, v8, a3, "Path already exists: ", 21, v6, a3[2]);
  }
  return a2;
}

```

## disassembly

```asm
0x14001b8a0  mov     [rsp+arg_0], rbx
0x14001b8a5  push    rdi
0x14001b8a6  sub     rsp, 90h
0x14001b8ad  mov     rax, cs:__security_cookie
0x14001b8b4  xor     rax, rsp
0x14001b8b7  mov     [rsp+98h+var_10], rax
0x14001b8bf  cmp     qword ptr [r8+18h], 0Fh
0x14001b8c4  mov     rdi, r8
0x14001b8c7  mov     rbx, rdx
0x14001b8ca  mov     [rsp+98h+var_50], rdx
0x14001b8cf  mov     rcx, r8
0x14001b8d2  jbe     short loc_14001B8D7
0x14001b8d4  mov     rcx, [r8]
0x14001b8d7  lea     rdx, [rsp+98h+var_48]
0x14001b8dc  call    cs:__imp__o__stat64
0x14001b8e2  test    eax, eax
0x14001b8e4  jnz     short loc_14001B938
0x14001b8e6  mov     rcx, [rdi+10h]
0x14001b8ea  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001b8f4  sub     rax, rcx
0x14001b8f7  cmp     rax, 15h
0x14001b8fb  jb      short loc_14001B975
0x14001b8fd  cmp     qword ptr [rdi+18h], 0Fh
0x14001b902  jbe     short loc_14001B909
0x14001b904  mov     rax, [rdi]
0x14001b907  jmp     short loc_14001B90C
0x14001b909  mov     rax, rdi
0x14001b90c  movzx   edx, [rsp+98h+var_58]
0x14001b911  lea     r9, aPathAlreadyExi; "Path already exists: "
0x14001b918  mov     [rsp+98h+var_68], rcx
0x14001b91d  mov     r8, rdi
0x14001b920  mov     [rsp+98h+var_70], rax
0x14001b925  mov     rcx, rbx
0x14001b928  mov     [rsp+98h+var_78], 15h
0x14001b931  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x14001b936  jmp     short loc_14001B951
0x14001b938  xorps   xmm0, xmm0
0x14001b93b  movups  xmmword ptr [rbx], xmm0
0x14001b93e  mov     qword ptr [rbx+10h], 0
0x14001b946  mov     qword ptr [rbx+18h], 0Fh
0x14001b94e  mov     byte ptr [rbx], 0
0x14001b951  mov     rax, rbx
0x14001b954  mov     rcx, [rsp+98h+var_10]
0x14001b95c  xor     rcx, rsp; StackCookie
0x14001b95f  call    __security_check_cookie
0x14001b964  mov     rbx, [rsp+98h+arg_0]
0x14001b96c  add     rsp, 90h
0x14001b973  pop     rdi
0x14001b974  retn
0x14001b975  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
