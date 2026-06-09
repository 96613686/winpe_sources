# CLI::_dynamic_initializer_for__ExistingPath___0

- ea: `0x1400031b0`
- end: `0x140003289`
- name: `CLI::_dynamic_initializer_for__ExistingPath___0`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400031b0`
- `0x1400086a0`
- `0x140008f10`
- `0x14000f7e0`
- `0x14000fa98`
- `0x140067010`

## string_xrefs

- `0x1400031d4`: `PATH(existing)`

## pseudocode

```c
int CLI::_dynamic_initializer_for__ExistingPath___0()
{
  _QWORD *v0; // rdx
  char v2[16]; // [rsp+20h] [rbp-88h] BYREF
  __int64 v3; // [rsp+30h] [rbp-78h]
  __int64 v4; // [rsp+38h] [rbp-70h]
  _QWORD v5[7]; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v6; // [rsp+88h] [rbp-20h]

  v2[15] = 0;
  v3 = 14;
  v4 = 15;
  strcpy(v2, "PATH(existing)");
  CLI::Validator::Validator(qword_1400833F0, v2);
  v5[0] = &std::_Func_impl_no_alloc<_lambda_789c8522ecb0a8e793d79ae662a753ad_,std::string,std::string &>::`vftable';
  v6 = v5;
  std::function<std::string (std::string &)>::swap(v5, qword_140083430);
  if ( v6 )
  {
    v0 = v5;
    LOBYTE(v0) = v6 != v5;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v6 + 32LL))(v6, v0);
  }
  return atexit(CLI::_dynamic_atexit_destructor_for__ExistingPath___0);
}

```

## disassembly

```asm
0x1400031b0  sub     rsp, 0A8h
0x1400031b7  mov     rax, cs:__security_cookie
0x1400031be  xor     rax, rsp
0x1400031c1  mov     [rsp+0A8h+var_18], rax
0x1400031c9  mov     eax, dword ptr cs:aPathExisting+8; "sting)"
0x1400031cf  lea     rdx, [rsp+0A8h+var_88]
0x1400031d4  movsd   xmm0, qword ptr cs:aPathExisting; "PATH(existing)"
0x1400031dc  lea     rcx, qword_1400833F0
0x1400031e3  mov     dword ptr [rsp+0A8h+var_88+8], eax
0x1400031e7  movzx   eax, word ptr cs:aPathExisting+0Ch; "g)"
0x1400031ee  mov     word ptr [rsp+0A8h+var_88+0Ch], ax
0x1400031f3  mov     word ptr [rsp+0A8h+var_88+0Eh], 0
0x1400031fa  mov     [rsp+0A8h+var_78], 0Eh
0x140003203  mov     [rsp+0A8h+var_70], 0Fh
0x14000320c  movsd   qword ptr [rsp+0A8h+var_88], xmm0
0x140003212  call    ??0Validator@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::Validator::Validator(std::string)
0x140003217  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_789c8522ecb0a8e793d79ae662a753ad_@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_789c8522ecb0a8e793d79ae662a753ad_,std::string,std::string &>::`vftable'
0x14000321e  mov     [rsp+0A8h+var_58], rax
0x140003223  lea     rdx, qword_140083430
0x14000322a  lea     rax, [rsp+0A8h+var_58]
0x14000322f  lea     rcx, [rsp+0A8h+var_58]
0x140003234  mov     [rsp+0A8h+var_20], rax
0x14000323c  call    ?swap@?$function@$$A6A?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@Z@std@@QEAAXAEAV12@@Z; std::function<std::string (std::string &)>::swap(std::function<std::string (std::string &)> &)
0x140003241  mov     rcx, [rsp+0A8h+var_20]
0x140003249  test    rcx, rcx
0x14000324c  jz      short loc_140003265
0x14000324e  mov     rax, [rcx]
0x140003251  lea     rdx, [rsp+0A8h+var_58]
0x140003256  cmp     rcx, rdx
0x140003259  setnz   dl
0x14000325c  mov     rax, [rax+20h]
0x140003260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003265  lea     rcx, CLI___dynamic_atexit_destructor_for__ExistingPath___0; void (__cdecl *)()
0x14000326c  call    atexit
0x140003271  mov     rcx, [rsp+0A8h+var_18]
0x140003279  xor     rcx, rsp; StackCookie
0x14000327c  call    __security_check_cookie
0x140003281  add     rsp, 0A8h
0x140003288  retn
```
