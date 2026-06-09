# UusExclusion::IsVersionExcludedInList(unsigned __int64,web::json::value const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x180033750`
- end: `0x180033979`
- name: `?IsVersionExcludedInList@UusExclusion@@CA_N_KAEBVvalue@json@web@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x180032a58`

## callees

- `0x180009c50`
- `0x180009e1c`
- `0x18000deb8`
- `0x180010428`
- `0x18001052c`
- `0x180027184`
- `0x180027618`
- `0x180029708`
- `0x180029780`
- `0x1800298d4`
- `0x180029984`
- `0x18002acd0`
- `0x180032308`
- `0x180033750`
- `0x180033980`
- `0x18003ac0c`
- `0x1800427d0`
- `0x180044848`
- `0x180047a30`

## string_xrefs

- `0x180033915`: `, not JSON array type `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall UusExclusion::IsVersionExcludedInList(__int64 a1, _QWORD *a2, __int64 a3, char a4)
{
  _QWORD *v8; // rax
  __int64 v9; // rax
  const struct web::json::array *v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v25[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[32]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v27[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v28[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[240]; // [rsp+A0h] [rbp-60h] BYREF

  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 8LL))(*a2, a3) )
    return 0;
  v27[0] = 0;
  v8 = (_QWORD *)web::json::value::at(a2, a3);
  (**(void (__fastcall ***)(_QWORD, _QWORD *))*v8)(*v8, v27);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v27[0] + 88LL))(v27[0]) != 4
    && (*(unsigned __int8 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v27[0] + 8LL))(
         v27[0],
         UusExclusion::_keyExclusionListLocal) )
  {
    v9 = web::json::value::at(v27, UusExclusion::_keyExclusionListLocal);
    web::json::value::operator=(v27, v9);
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v27[0] + 88LL))(v27[0]) != 4 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(v28);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v28);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v29, L"Exclusion list key (");
    v14 = std::wstring::c_str(a3);
    v16 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v15, v14);
    v17 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v16, L") is type ");
    v18 = web::json::value::type(v27);
    v19 = std::wostream::operator<<(v17, v18);
    v20 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v19, L", not JSON array type ");
    v21 = std::wostream::operator<<(v20, 4);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v21, " expected");
    v22 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v28, v25);
    v23 = UnicodeToMultiByte(v26, v22);
    std::runtime_error::runtime_error(pExceptionObject, v23);
    throw (std::runtime_error *)pExceptionObject;
  }
  v10 = (const struct web::json::array *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v27[0] + 152LL))(v27[0]);
  v11 = web::json::array::array((web::json::array *)pExceptionObject, v10);
  LOBYTE(v12) = a4;
  if ( !(unsigned __int8)UusExclusion::IsVersionInArray(v11, a1, v12) )
  {
    if ( v27[0] )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v27[0] + 192LL))(v27[0], 1);
    return 0;
  }
  if ( v27[0] )
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v27[0] + 192LL))(v27[0], 1);
  return 1;
}

```

## disassembly

```asm
0x180033750  push    rbp
0x180033752  push    rbx
0x180033753  push    rsi
0x180033754  push    rdi
0x180033755  push    r14
0x180033757  lea     rbp, [rsp-0A0h]
0x18003375f  sub     rsp, 1A0h
0x180033766  mov     rax, cs:__security_cookie
0x18003376d  xor     rax, rsp
0x180033770  mov     [rbp+0C0h+var_30], rax
0x180033777  mov     r14b, r9b
0x18003377a  mov     rdi, r8
0x18003377d  mov     rbx, rdx
0x180033780  mov     rsi, rcx
0x180033783  mov     rcx, [rdx]
0x180033786  mov     rax, [rcx]
0x180033789  mov     rdx, r8
0x18003378c  mov     rax, [rax+8]
0x180033790  call    _guard_dispatch_icall
0x180033795  test    al, al
0x180033797  jz      loc_180033878
0x18003379d  mov     [rbp+0C0h+var_140], 0
0x1800337a5  mov     rdx, rdi
0x1800337a8  mov     rcx, rbx
0x1800337ab  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800337b0  mov     rcx, [rax]
0x1800337b3  mov     rax, [rcx]
0x1800337b6  lea     rdx, [rbp+0C0h+var_140]
0x1800337ba  mov     rax, [rax]
0x1800337bd  call    _guard_dispatch_icall
0x1800337c2  nop
0x1800337c3  mov     rcx, [rbp+0C0h+var_140]
0x1800337c7  mov     rax, [rcx]
0x1800337ca  mov     rax, [rax+58h]
0x1800337ce  call    _guard_dispatch_icall
0x1800337d3  cmp     eax, 4
0x1800337d6  jz      short loc_18003380F
0x1800337d8  mov     rcx, [rbp+0C0h+var_140]
0x1800337dc  mov     rax, [rcx]
0x1800337df  lea     rdx, ?_keyExclusionListLocal@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_keyExclusionListLocal
0x1800337e6  mov     rax, [rax+8]
0x1800337ea  call    _guard_dispatch_icall
0x1800337ef  test    al, al
0x1800337f1  jz      short loc_18003380F
0x1800337f3  lea     rdx, ?_keyExclusionListLocal@UusExclusion@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusExclusion::_keyExclusionListLocal
0x1800337fa  lea     rcx, [rbp+0C0h+var_140]
0x1800337fe  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180033803  mov     rdx, rax
0x180033806  lea     rcx, [rbp+0C0h+var_140]
0x18003380a  call    ??4value@json@web@@QEAAAEAV012@AEBV012@@Z; web::json::value::operator=(web::json::value const &)
0x18003380f  mov     rcx, [rbp+0C0h+var_140]
0x180033813  mov     rax, [rcx]
0x180033816  mov     rax, [rax+58h]
0x18003381a  call    _guard_dispatch_icall
0x18003381f  cmp     eax, 4
0x180033822  jnz     loc_1800338B4
0x180033828  mov     rcx, [rbp+0C0h+var_140]
0x18003382c  mov     rax, [rcx]
0x18003382f  mov     rax, [rax+98h]
0x180033836  call    _guard_dispatch_icall
0x18003383b  mov     rdx, rax; struct web::json::array *
0x18003383e  lea     rcx, [rsp+1C0h+pExceptionObject]; this
0x180033843  call    ??0array@json@web@@QEAA@AEBV012@@Z; web::json::array::array(web::json::array const &)
0x180033848  mov     r8b, r14b
0x18003384b  mov     rdx, rsi
0x18003384e  mov     rcx, rax
0x180033851  call    ?IsVersionInArray@UusExclusion@@CA_NVarray@json@web@@_K_N@Z; UusExclusion::IsVersionInArray(web::json::array,unsigned __int64,bool)
0x180033856  nop
0x180033857  mov     rcx, [rbp+0C0h+var_140]
0x18003385b  test    al, al
0x18003385d  jnz     short loc_180033897
0x18003385f  test    rcx, rcx
0x180033862  jz      short loc_180033878
0x180033864  mov     rax, [rcx]
0x180033867  mov     edx, 1
0x18003386c  mov     rax, [rax+0C0h]
0x180033873  call    _guard_dispatch_icall
0x180033878  xor     al, al
0x18003387a  mov     rcx, [rbp+0C0h+var_30]
0x180033881  xor     rcx, rsp; StackCookie
0x180033884  call    __security_check_cookie
0x180033889  add     rsp, 1A0h
0x180033890  pop     r14
0x180033892  pop     rdi
0x180033893  pop     rsi
0x180033894  pop     rbx
0x180033895  pop     rbp
0x180033896  retn
0x180033897  test    rcx, rcx
0x18003389a  jz      short loc_1800338B0
0x18003389c  mov     rax, [rcx]
0x18003389f  mov     edx, 1
0x1800338a4  mov     rax, [rax+0C0h]
0x1800338ab  call    _guard_dispatch_icall
0x1800338b0  mov     al, 1
0x1800338b2  jmp     short loc_18003387A
0x1800338b4  lea     rcx, [rbp+0C0h+var_130]
0x1800338b8  call    ?__autoclassinit2@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(unsigned __int64)
0x1800338bd  lea     rcx, [rbp+0C0h+var_130]
0x1800338c1  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1800338c6  nop
0x1800338c7  lea     rdx, aExclusionListK; "Exclusion list key ("
0x1800338ce  lea     rcx, [rbp+0C0h+var_120]
0x1800338d2  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800338d7  mov     r8, rax
0x1800338da  mov     rcx, rdi
0x1800338dd  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x1800338e2  mov     rdx, rax
0x1800338e5  mov     rcx, r8
0x1800338e8  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800338ed  mov     rcx, rax
0x1800338f0  lea     rdx, aIsType; ") is type "
0x1800338f7  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800338fc  mov     rbx, rax
0x1800338ff  lea     rcx, [rbp+0C0h+var_140]
0x180033903  call    ?type@value@json@web@@QEBA?AW4value_type@123@XZ; web::json::value::type(void)
0x180033908  mov     edx, eax
0x18003390a  mov     rcx, rbx
0x18003390d  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@H@Z; std::wostream::operator<<(int)
0x180033912  mov     rcx, rax
0x180033915  lea     rdx, aNotJsonArrayTy; ", not JSON array type "
0x18003391c  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180033921  mov     edx, 4
0x180033926  mov     rcx, rax
0x180033929  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@H@Z; std::wostream::operator<<(int)
0x18003392e  mov     rcx, rax
0x180033931  lea     rdx, aExpected; " expected"
0x180033938  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEBD@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,char const *)
0x18003393d  lea     rdx, [rsp+1C0h+var_180]
0x180033942  lea     rcx, [rbp+0C0h+var_130]
0x180033946  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x18003394b  nop
0x18003394c  mov     rdx, rax
0x18003394f  lea     rcx, [rsp+1C0h+var_160]
0x180033954  call    UnicodeToMultiByte
0x180033959  nop
0x18003395a  mov     rdx, rax
0x18003395d  lea     rcx, [rsp+1C0h+pExceptionObject]
0x180033962  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180033967  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003396e  lea     rcx, [rsp+1C0h+pExceptionObject]; pExceptionObject
0x180033973  call    _CxxThrowException
```
