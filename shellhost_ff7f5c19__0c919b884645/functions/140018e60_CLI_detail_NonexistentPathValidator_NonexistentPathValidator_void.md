# CLI::detail::NonexistentPathValidator::NonexistentPathValidator(void)

- ea: `0x140018e60`
- end: `0x140018f48`
- name: `??0NonexistentPathValidator@detail@CLI@@QEAA@XZ`
- size: `232`
- prototype: `__int64 __fastcall(CLI::detail::NonexistentPathValidator *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x140002d80`

## callees

- `0x1400086a0`
- `0x140008f10`
- `0x14000f7e0`
- `0x14000f804`
- `0x140018e60`
- `0x140067010`

## string_xrefs

- `0x140018ea1`: `PATH(non-existing)`

## pseudocode

```c
CLI::detail::NonexistentPathValidator *__fastcall CLI::detail::NonexistentPathValidator::NonexistentPathValidator(
        CLI::detail::NonexistentPathValidator *this)
{
  _QWORD *v2; // rdx
  __int128 v4; // [rsp+28h] [rbp-80h] BYREF
  __int64 v5; // [rsp+38h] [rbp-70h]
  __int64 v6; // [rsp+40h] [rbp-68h]
  _QWORD v7[7]; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v8; // [rsp+88h] [rbp-20h]

  v4 = 0;
  *(_QWORD *)&v4 = operator new(0x20u);
  v5 = 18;
  v6 = 31;
  strcpy((char *)v4, "PATH(non-existing)");
  CLI::Validator::Validator(this, &v4);
  v7[0] = &std::_Func_impl_no_alloc<_lambda_8329f84707d0a68d87e8c538d6dc1dea_,std::string,std::string &>::`vftable';
  v8 = v7;
  std::function<std::string (std::string &)>::swap(v7, (char *)this + 64);
  if ( v8 )
  {
    v2 = v7;
    LOBYTE(v2) = v8 != v7;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v8 + 32LL))(v8, v2);
  }
  return this;
}

```

## disassembly

```asm
0x140018e60  push    rbx
0x140018e62  sub     rsp, 0A0h
0x140018e69  mov     rax, cs:__security_cookie
0x140018e70  xor     rax, rsp
0x140018e73  mov     [rsp+0A8h+var_18], rax
0x140018e7b  xor     eax, eax
0x140018e7d  mov     [rsp+0A8h+var_88], rcx
0x140018e82  mov     rbx, rcx
0x140018e85  mov     [rsp+0A8h+var_70], rax
0x140018e8a  xorps   xmm0, xmm0
0x140018e8d  mov     [rsp+0A8h+var_68], rax
0x140018e92  mov     ecx, 20h ; ' '; Size
0x140018e97  movups  [rsp+0A8h+var_80], xmm0
0x140018e9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018ea1  movups  xmm0, xmmword ptr cs:aPathNonExistin; "PATH(non-existing)"
0x140018ea8  mov     rcx, rax
0x140018eab  mov     qword ptr [rsp+0A8h+var_80], rax
0x140018eb0  mov     [rsp+0A8h+var_70], 12h
0x140018eb9  lea     rdx, [rsp+0A8h+var_80]
0x140018ebe  mov     [rsp+0A8h+var_68], 1Fh
0x140018ec7  movups  xmmword ptr [rax], xmm0
0x140018eca  movzx   eax, word ptr cs:aPathNonExistin+10h; "g)"
0x140018ed1  mov     [rcx+10h], ax
0x140018ed5  mov     byte ptr [rcx+12h], 0
0x140018ed9  mov     rcx, rbx
0x140018edc  call    ??0Validator@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::Validator::Validator(std::string)
0x140018ee1  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_8329f84707d0a68d87e8c538d6dc1dea_@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_8329f84707d0a68d87e8c538d6dc1dea_,std::string,std::string &>::`vftable'
0x140018ee8  mov     [rsp+0A8h+var_58], rax
0x140018eed  lea     rdx, [rbx+40h]
0x140018ef1  lea     rax, [rsp+0A8h+var_58]
0x140018ef6  lea     rcx, [rsp+0A8h+var_58]
0x140018efb  mov     [rsp+0A8h+var_20], rax
0x140018f03  call    ?swap@?$function@$$A6A?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@Z@std@@QEAAXAEAV12@@Z; std::function<std::string (std::string &)>::swap(std::function<std::string (std::string &)> &)
0x140018f08  mov     rcx, [rsp+0A8h+var_20]
0x140018f10  test    rcx, rcx
0x140018f13  jz      short loc_140018F2C
0x140018f15  mov     rax, [rcx]
0x140018f18  lea     rdx, [rsp+0A8h+var_58]
0x140018f1d  cmp     rcx, rdx
0x140018f20  setnz   dl
0x140018f23  mov     rax, [rax+20h]
0x140018f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018f2c  mov     rax, rbx
0x140018f2f  mov     rcx, [rsp+0A8h+var_18]
0x140018f37  xor     rcx, rsp; StackCookie
0x140018f3a  call    __security_check_cookie
0x140018f3f  add     rsp, 0A0h
0x140018f46  pop     rbx
0x140018f47  retn
```
