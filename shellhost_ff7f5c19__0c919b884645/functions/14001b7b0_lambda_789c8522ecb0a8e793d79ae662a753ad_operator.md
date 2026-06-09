# _lambda_789c8522ecb0a8e793d79ae662a753ad_::operator()

- ea: `0x14001b7b0`
- end: `0x14001b88b`
- name: `_lambda_789c8522ecb0a8e793d79ae662a753ad_::operator()`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001fb40`

## callees

- `0x14000ba3c`
- `0x14000f7e0`
- `0x14001b7b0`
- `0x14004aaac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stat64` at `0x14001b7ec`
- `api-ms-win-crt-private-l1-1-0!_o__stat64` at `0x14001b7ec`

## string_xrefs

- `0x14001b821`: `Path does not exist: `

## pseudocode

```c
__int64 __fastcall lambda_789c8522ecb0a8e793d79ae662a753ad_::operator()(__int64 a1, __int64 a2, _QWORD *a3)
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
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - a3[2]) < 0x15 )
      std::_Xlen_string();
    if ( a3[3] <= 0xFu )
      v6 = a3;
    else
      v6 = (_QWORD *)*a3;
    std::string::string(a2, v8, a3, "Path does not exist: ", 21, v6, a3[2]);
  }
  else
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 15;
    *(_BYTE *)a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x14001b7b0  mov     [rsp+arg_0], rbx
0x14001b7b5  push    rdi
0x14001b7b6  sub     rsp, 90h
0x14001b7bd  mov     rax, cs:__security_cookie
0x14001b7c4  xor     rax, rsp
0x14001b7c7  mov     [rsp+98h+var_10], rax
0x14001b7cf  cmp     qword ptr [r8+18h], 0Fh
0x14001b7d4  mov     rdi, r8
0x14001b7d7  mov     rbx, rdx
0x14001b7da  mov     [rsp+98h+var_50], rdx
0x14001b7df  mov     rcx, r8
0x14001b7e2  jbe     short loc_14001B7E7
0x14001b7e4  mov     rcx, [r8]
0x14001b7e7  lea     rdx, [rsp+98h+var_48]
0x14001b7ec  call    cs:__imp__o__stat64
0x14001b7f2  test    eax, eax
0x14001b7f4  jz      short loc_14001B848
0x14001b7f6  mov     rcx, [rdi+10h]
0x14001b7fa  mov     rax, 7FFFFFFFFFFFFFFFh
0x14001b804  sub     rax, rcx
0x14001b807  cmp     rax, 15h
0x14001b80b  jb      short loc_14001B885
0x14001b80d  cmp     qword ptr [rdi+18h], 0Fh
0x14001b812  jbe     short loc_14001B819
0x14001b814  mov     rax, [rdi]
0x14001b817  jmp     short loc_14001B81C
0x14001b819  mov     rax, rdi
0x14001b81c  movzx   edx, [rsp+98h+var_58]
0x14001b821  lea     r9, aPathDoesNotExi; "Path does not exist: "
0x14001b828  mov     [rsp+98h+var_68], rcx
0x14001b82d  mov     r8, rdi
0x14001b830  mov     [rsp+98h+var_70], rax
0x14001b835  mov     rcx, rbx
0x14001b838  mov     [rsp+98h+var_78], 15h
0x14001b841  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x14001b846  jmp     short loc_14001B861
0x14001b848  xorps   xmm0, xmm0
0x14001b84b  movups  xmmword ptr [rbx], xmm0
0x14001b84e  mov     qword ptr [rbx+10h], 0
0x14001b856  mov     qword ptr [rbx+18h], 0Fh
0x14001b85e  mov     byte ptr [rbx], 0
0x14001b861  mov     rax, rbx
0x14001b864  mov     rcx, [rsp+98h+var_10]
0x14001b86c  xor     rcx, rsp; StackCookie
0x14001b86f  call    __security_check_cookie
0x14001b874  mov     rbx, [rsp+98h+arg_0]
0x14001b87c  add     rsp, 90h
0x14001b883  pop     rdi
0x14001b884  retn
0x14001b885  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
