# CLI::_dynamic_initializer_for__NonexistentPath___0

- ea: `0x140003360`
- end: `0x14000344a`
- name: `CLI::_dynamic_initializer_for__NonexistentPath___0`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x140003360`
- `0x1400086a0`
- `0x140008f10`
- `0x14000f7e0`
- `0x14000f804`
- `0x14000fa98`
- `0x140067010`

## string_xrefs

- `0x140003397`: `PATH(non-existing)`

## pseudocode

```c
int CLI::_dynamic_initializer_for__NonexistentPath___0()
{
  _QWORD *v0; // rdx
  __int128 v2; // [rsp+20h] [rbp-88h] BYREF
  __int64 v3; // [rsp+30h] [rbp-78h]
  __int64 v4; // [rsp+38h] [rbp-70h]
  _QWORD v5[7]; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v6; // [rsp+88h] [rbp-20h]

  v2 = 0;
  *(_QWORD *)&v2 = operator new(0x20u);
  v3 = 18;
  v4 = 31;
  strcpy((char *)v2, "PATH(non-existing)");
  CLI::Validator::Validator(qword_140083130, &v2);
  v5[0] = &std::_Func_impl_no_alloc<_lambda_8329f84707d0a68d87e8c538d6dc1dea_,std::string,std::string &>::`vftable';
  v6 = v5;
  std::function<std::string (std::string &)>::swap(v5, qword_140083170);
  if ( v6 )
  {
    v0 = v5;
    LOBYTE(v0) = v6 != v5;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v6 + 32LL))(v6, v0);
  }
  return atexit(CLI::_dynamic_atexit_destructor_for__NonexistentPath___0);
}

```

## disassembly

```asm
0x140003360  sub     rsp, 0A8h
0x140003367  mov     rax, cs:__security_cookie
0x14000336e  xor     rax, rsp
0x140003371  mov     [rsp+0A8h+var_18], rax
0x140003379  xor     eax, eax
0x14000337b  xorps   xmm0, xmm0
0x14000337e  mov     ecx, 20h ; ' '; Size
0x140003383  mov     [rsp+0A8h+var_78], rax
0x140003388  movups  [rsp+0A8h+var_88], xmm0
0x14000338d  mov     [rsp+0A8h+var_70], rax
0x140003392  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003397  movups  xmm0, xmmword ptr cs:aPathNonExistin; "PATH(non-existing)"
0x14000339e  mov     qword ptr [rsp+0A8h+var_88], rax
0x1400033a3  lea     rdx, [rsp+0A8h+var_88]
0x1400033a8  mov     [rsp+0A8h+var_78], 12h
0x1400033b1  mov     [rsp+0A8h+var_70], 1Fh
0x1400033ba  movups  xmmword ptr [rax], xmm0
0x1400033bd  movzx   ecx, word ptr cs:aPathNonExistin+10h; "g)"
0x1400033c4  mov     [rax+10h], cx
0x1400033c8  lea     rcx, qword_140083130
0x1400033cf  mov     byte ptr [rax+12h], 0
0x1400033d3  call    ??0Validator@CLI@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::Validator::Validator(std::string)
0x1400033d8  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_8329f84707d0a68d87e8c538d6dc1dea_@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_8329f84707d0a68d87e8c538d6dc1dea_,std::string,std::string &>::`vftable'
0x1400033df  mov     [rsp+0A8h+var_58], rax
0x1400033e4  lea     rdx, qword_140083170
0x1400033eb  lea     rax, [rsp+0A8h+var_58]
0x1400033f0  lea     rcx, [rsp+0A8h+var_58]
0x1400033f5  mov     [rsp+0A8h+var_20], rax
0x1400033fd  call    ?swap@?$function@$$A6A?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@Z@std@@QEAAXAEAV12@@Z; std::function<std::string (std::string &)>::swap(std::function<std::string (std::string &)> &)
0x140003402  mov     rcx, [rsp+0A8h+var_20]
0x14000340a  test    rcx, rcx
0x14000340d  jz      short loc_140003426
0x14000340f  mov     rax, [rcx]
0x140003412  lea     rdx, [rsp+0A8h+var_58]
0x140003417  cmp     rcx, rdx
0x14000341a  setnz   dl
0x14000341d  mov     rax, [rax+20h]
0x140003421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003426  lea     rcx, CLI___dynamic_atexit_destructor_for__NonexistentPath___0; void (__cdecl *)()
0x14000342d  call    atexit
0x140003432  mov     rcx, [rsp+0A8h+var_18]
0x14000343a  xor     rcx, rsp; StackCookie
0x14000343d  call    __security_check_cookie
0x140003442  add     rsp, 0A8h
0x140003449  retn
```
