# CLI::detail::ExistingPathValidator::ExistingPathValidator(void)

- ea: `0x1400181c0`
- end: `0x140018291`
- name: `??0ExistingPathValidator@detail@CLI@@QEAA@XZ`
- size: `209`
- prototype: `__int64 __fastcall(CLI::detail::ExistingPathValidator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002db0`

## callees

- `0x1400086a0`
- `0x140008f10`
- `0x14000f7e0`
- `0x1400181c0`
- `0x140067010`

## string_xrefs

- `0x1400181e6`: `PATH(existing)`

## pseudocode

```c
CLI::detail::ExistingPathValidator *__fastcall CLI::detail::ExistingPathValidator::ExistingPathValidator(
        CLI::detail::ExistingPathValidator *this)
{
  _QWORD *v2; // rdx
  char v4[16]; // [rsp+20h] [rbp-88h] BYREF
  __int64 v5; // [rsp+30h] [rbp-78h]
  __int64 v6; // [rsp+38h] [rbp-70h]
  CLI::detail::ExistingPathValidator *v7; // [rsp+40h] [rbp-68h]
  _QWORD v8[7]; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v9; // [rsp+88h] [rbp-20h]

  v7 = this;
  v4[15] = 0;
  v5 = 14;
  v6 = 15;
  strcpy(v4, "PATH(existing)");
  CLI::Validator::Validator(this, v4);
  v8[0] = &std::_Func_impl_no_alloc<_lambda_789c8522ecb0a8e793d79ae662a753ad_,std::string,std::string &>::`vftable';
  v9 = v8;
  std::function<std::string (std::string &)>::swap(v8, (char *)this + 64);
  if ( v9 )
  {
    v2 = v8;
    LOBYTE(v2) = v9 != v8;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v9 + 32LL))(v9, v2);
  }
  return this;
}

```

## disassembly

```asm
0x1400181c0  push    rbx
0x1400181c2  sub     rsp, 0A0h
0x1400181c9  mov     rax, cs:__security_cookie
0x1400181d0  xor     rax, rsp
0x1400181d3  mov     [rsp+0A8h+var_18], rax
0x1400181db  mov     eax, dword ptr cs:aPathExisting+8; "sting)"
0x1400181e1  lea     rdx, [rsp+0A8h+var_88]
0x1400181e6  movsd   xmm0, qword ptr cs:aPathExisting; "PATH(existing)"
0x1400181ee  mov     rbx, rcx
0x1400181f1  mov     dword ptr [rsp+0A8h+var_88+8], eax
0x1400181f5  movzx   eax, word ptr cs:aPathExisting+0Ch; "g)"
0x1400181fc  mov     word ptr [rsp+0A8h+var_88+0Ch], ax
0x140018201  mov     [rsp+0A8h+var_68], rcx
0x140018206  mov     word ptr [rsp+0A8h+var_88+0Eh], 0
0x14001820d  mov     [rsp+0A8h+var_78], 0Eh
0x140018216  mov     [rsp+0A8h+var_70], 0Fh
0x14001821f  movsd   qword ptr [rsp+0A8h+var_88], xmm0
0x140018225  call    ??0Validator@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::Validator::Validator(std::string)
0x14001822a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_789c8522ecb0a8e793d79ae662a753ad_@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_789c8522ecb0a8e793d79ae662a753ad_,std::string,std::string &>::`vftable'
0x140018231  mov     [rsp+0A8h+var_58], rax
0x140018236  lea     rdx, [rbx+40h]
0x14001823a  lea     rax, [rsp+0A8h+var_58]
0x14001823f  lea     rcx, [rsp+0A8h+var_58]
0x140018244  mov     [rsp+0A8h+var_20], rax
0x14001824c  call    ?swap@?$function@$$A6A?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@Z@std@@QEAAXAEAV12@@Z; std::function<std::string (std::string &)>::swap(std::function<std::string (std::string &)> &)
0x140018251  mov     rcx, [rsp+0A8h+var_20]
0x140018259  test    rcx, rcx
0x14001825c  jz      short loc_140018275
0x14001825e  mov     rax, [rcx]
0x140018261  lea     rdx, [rsp+0A8h+var_58]
0x140018266  cmp     rcx, rdx
0x140018269  setnz   dl
0x14001826c  mov     rax, [rax+20h]
0x140018270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018275  mov     rax, rbx
0x140018278  mov     rcx, [rsp+0A8h+var_18]
0x140018280  xor     rcx, rsp; StackCookie
0x140018283  call    __security_check_cookie
0x140018288  add     rsp, 0A0h
0x14001828f  pop     rbx
0x140018290  retn
```
