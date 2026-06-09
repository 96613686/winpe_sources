# UusExclusion::ParseVersionRangeFromValue(web::json::value)

- ea: `0x180033470`
- end: `0x18003374a`
- name: `?ParseVersionRangeFromValue@UusExclusion@@CA?AU?$pair@_K_K@std@@Vvalue@json@web@@@Z`
- size: `730`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180032b3c`
- `0x180033980`

## callees

- `0x180009e1c`
- `0x18000d70c`
- `0x18000dca4`
- `0x180011d08`
- `0x180011e0c`
- `0x180012638`
- `0x180028424`
- `0x180028728`
- `0x180029344`
- `0x180029644`
- `0x180029780`
- `0x180033470`
- `0x18003a678`
- `0x18003a9ec`
- `0x1800427d0`
- `0x180044848`
- `0x180047a30`

## string_xrefs

- `0x1800336bb`: `JSON version value is unexpected type `

## pseudocode

```c
// Hidden C++ exception states: #wind=6
double *__fastcall UusExclusion::ParseVersionRangeFromValue(double *a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rax
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rdx
  double *result; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  double v12; // xmm0_8
  double v13; // rax
  __int64 v14; // rbx
  unsigned int v15; // eax
  const char *v16; // rax
  const wchar_t *v17; // rax
  const char *v18; // rdx
  const std::exception *v19[2]; // [rsp+40h] [rbp-8B8h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-8A8h]
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-8A0h] BYREF
  _BYTE v22[24]; // [rsp+70h] [rbp-888h] BYREF
  _QWORD v23[4]; // [rsp+88h] [rbp-870h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-850h] BYREF
  __int64 v25; // [rsp+B8h] [rbp-840h]
  _BYTE v26[32]; // [rsp+C0h] [rbp-838h] BYREF
  char v27[16]; // [rsp+E0h] [rbp-818h] BYREF
  _BYTE v28[2032]; // [rsp+F0h] [rbp-808h] BYREF

  v23[3] = a2;
  v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 88LL))(*a2);
  if ( v4 )
  {
    if ( v4 != 2 )
    {
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(v27);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v27);
      v14 = std::operator<<<std::char_traits<char>>(v28, "JSON version value is unexpected type ");
      v15 = web::json::value::type(a2);
      std::ostream::operator<<(v14, v15);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v27, v26);
      v16 = (const char *)std::string::c_str(v26);
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, v16);
      throw (std::runtime_error *)pExceptionObject;
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 176LL))(*a2);
    std::wstring::wstring(v26, v5);
    try
    {
      v24 = 0;
      v25 = 0;
      UusExclusion::Split<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(&v24, v26);
      if ( (__int64)(*((_QWORD *)&v24 + 1) - v24) >> 5 == 1 )
      {
        v9 = UusVersion::StrToVer<wchar_t>(v24);
        *(_QWORD *)a1 = v9;
        *((_QWORD *)a1 + 1) = v9;
        std::vector<std::wstring>::~vector<std::wstring>(&v24);
        std::wstring::_Tidy_deallocate(v26);
        if ( *a2 )
          (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 192LL))(*a2, 1);
        result = a1;
      }
      else
      {
        if ( (__int64)(*((_QWORD *)&v24 + 1) - v24) >> 5 != 2 )
        {
          std::runtime_error::runtime_error((std::runtime_error *)v22, "only 1 or 2 versions expected for range");
          throw (std::runtime_error *)v22;
        }
        v19[1] = (const std::exception *)&UusVersion::`vftable';
        v20 = UusVersion::StrToVer<wchar_t>(v24 + 32);
        v6 = UusVersion::StrToVer<wchar_t>(v24);
        if ( v20 >= v6 )
        {
          v7 = v6;
          v6 = v20;
        }
        else
        {
          v7 = v20;
        }
        *(_QWORD *)a1 = v7;
        *((_QWORD *)a1 + 1) = v6;
        std::vector<std::wstring>::~vector<std::wstring>(&v24);
        std::wstring::_Tidy_deallocate(v26);
        if ( *a2 )
          (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 192LL))(*a2, 1);
        result = a1;
      }
    }
    catch ( const std::exception *v19 )
    {
      (*(void (__fastcall **)(const std::exception *))(*(_QWORD *)v19[0] + 8LL))(v19[0]);
      v17 = (const wchar_t *)std::wstring::c_str(v26);
      snprintf(v27, 0x800u, "JSON version value '%S' could not be parsed: %s", v17, v18);
      std::runtime_error::runtime_error((std::runtime_error *)v23, v27);
      throw (std::runtime_error *)v23;
    }
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 112LL))(*a2);
    if ( *(_DWORD *)(v10 + 8) == 2 )
    {
      v11 = 0;
      v12 = *(double *)v10;
      if ( *(double *)v10 >= 9.223372036854776e18 )
      {
        v12 = v12 - 9.223372036854776e18;
        if ( v12 < 9.223372036854776e18 )
          v11 = 0x8000000000000000uLL;
      }
      *(_QWORD *)&v13 = v11 + (unsigned int)(int)v12;
    }
    else
    {
      v13 = *(double *)v10;
    }
    *a1 = v13;
    a1[1] = v13;
    if ( *a2 )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 192LL))(*a2, 1);
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x180033470  mov     [rsp+arg_10], rbx
0x180033475  push    rdi
0x180033476  sub     rsp, 8F0h
0x18003347d  mov     rax, cs:__security_cookie
0x180033484  xor     rax, rsp
0x180033487  mov     [rsp+8F8h+var_18], rax
0x18003348f  mov     rdi, rdx
0x180033492  mov     rbx, rcx
0x180033495  mov     [rsp+8F8h+var_858], rdx
0x18003349d  mov     rcx, [rdx]
0x1800334a0  mov     rax, [rcx]
0x1800334a3  mov     rax, [rax+58h]
0x1800334a7  call    _guard_dispatch_icall
0x1800334ac  test    eax, eax
0x1800334ae  jz      loc_18003360C
0x1800334b4  cmp     eax, 2
0x1800334b7  jnz     loc_1800336A0
0x1800334bd  mov     rcx, [rdi]
0x1800334c0  mov     rax, [rcx]
0x1800334c3  mov     rax, [rax+0B0h]
0x1800334ca  call    _guard_dispatch_icall
0x1800334cf  mov     rdx, rax
0x1800334d2  lea     rcx, [rsp+8F8h+var_838]
0x1800334da  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800334df  nop
0x1800334e0  xorps   xmm0, xmm0
0x1800334e3  xor     eax, eax
0x1800334e5  movups  [rsp+8F8h+var_850], xmm0
0x1800334ed  mov     [rsp+8F8h+var_840], rax
0x1800334f5  lea     rdx, [rsp+8F8h+var_838]
0x1800334fd  lea     rcx, [rsp+8F8h+var_850]
0x180033505  call    ??$Split@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@UusExclusion@@CA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@_W@Z; UusExclusion::Split<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::wstring const &,wchar_t)
0x18003350a  nop
0x18003350b  mov     rcx, qword ptr [rsp+8F8h+var_850]
0x180033513  mov     rax, qword ptr [rsp+8F8h+var_850+8]
0x18003351b  sub     rax, rcx
0x18003351e  sar     rax, 5
0x180033522  sub     rax, 1
0x180033526  jz      loc_1800335C3
0x18003352c  cmp     rax, 1
0x180033530  jnz     loc_180033726
0x180033536  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18003353d  mov     [rsp+8F8h+var_8B0], rax
0x180033542  add     rcx, 20h ; ' '
0x180033546  call    ??$StrToVer@_W@UusVersion@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusVersion::StrToVer<wchar_t>(std::wstring const &)
0x18003354b  mov     [rsp+8F8h+var_8A8], rax
0x180033550  mov     [rsp+8F8h+var_8C8], rax
0x180033555  mov     rcx, qword ptr [rsp+8F8h+var_850]
0x18003355d  call    ??$StrToVer@_W@UusVersion@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusVersion::StrToVer<wchar_t>(std::wstring const &)
0x180033562  mov     [rsp+8F8h+var_8C0], rax
0x180033567  mov     rcx, [rsp+8F8h+var_8C8]
0x18003356c  cmp     rcx, rax
0x18003356f  jnb     short loc_180033576
0x180033571  mov     rdx, rcx
0x180033574  jmp     short loc_18003357C
0x180033576  mov     rdx, rax
0x180033579  mov     rax, rcx
0x18003357c  mov     [rbx], rdx
0x18003357f  mov     [rbx+8], rax
0x180033583  lea     rcx, [rsp+8F8h+var_850]
0x18003358b  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180033590  nop
0x180033591  lea     rcx, [rsp+8F8h+var_838]
0x180033599  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003359e  nop
0x18003359f  mov     rcx, [rdi]
0x1800335a2  test    rcx, rcx
0x1800335a5  jz      short loc_1800335BB
0x1800335a7  mov     rdx, [rcx]
0x1800335aa  mov     rax, [rdx+0C0h]
0x1800335b1  mov     edx, 1
0x1800335b6  call    _guard_dispatch_icall
0x1800335bb  mov     rax, rbx
0x1800335be  jmp     loc_18003367F
0x1800335c3  call    ??$StrToVer@_W@UusVersion@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusVersion::StrToVer<wchar_t>(std::wstring const &)
0x1800335c8  mov     [rbx], rax
0x1800335cb  mov     [rbx+8], rax
0x1800335cf  lea     rcx, [rsp+8F8h+var_850]
0x1800335d7  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800335dc  nop
0x1800335dd  lea     rcx, [rsp+8F8h+var_838]
0x1800335e5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800335ea  nop
0x1800335eb  mov     rcx, [rdi]
0x1800335ee  test    rcx, rcx
0x1800335f1  jz      short loc_180033607
0x1800335f3  mov     rax, [rcx]
0x1800335f6  mov     edx, 1
0x1800335fb  mov     rax, [rax+0C0h]
0x180033602  call    _guard_dispatch_icall
0x180033607  mov     rax, rbx
0x18003360a  jmp     short loc_18003367F
0x18003360c  mov     rcx, [rdi]
0x18003360f  mov     rax, [rcx]
0x180033612  mov     rax, [rax+70h]
0x180033616  call    _guard_dispatch_icall
0x18003361b  cmp     dword ptr [rax+8], 2
0x18003361f  jnz     short loc_180033656
0x180033621  xor     ecx, ecx
0x180033623  movsd   xmm0, qword ptr [rax]
0x180033627  movsd   xmm1, cs:__real@43e0000000000000
0x18003362f  comisd  xmm0, xmm1
0x180033633  jb      short loc_18003364C
0x180033635  subsd   xmm0, xmm1
0x180033639  comisd  xmm0, xmm1
0x18003363d  jnb     short loc_18003364C
0x18003363f  mov     rax, 8000000000000000h
0x180033649  mov     rcx, rax
0x18003364c  cvttsd2si rax, xmm0
0x180033651  add     rax, rcx
0x180033654  jmp     short loc_180033659
0x180033656  mov     rax, [rax]
0x180033659  mov     [rbx], rax
0x18003365c  mov     [rbx+8], rax
0x180033660  mov     rcx, [rdi]
0x180033663  test    rcx, rcx
0x180033666  jz      short loc_18003367C
0x180033668  mov     rax, [rcx]
0x18003366b  mov     edx, 1
0x180033670  mov     rax, [rax+0C0h]
0x180033677  call    _guard_dispatch_icall
0x18003367c  mov     rax, rbx
0x18003367f  mov     rcx, [rsp+8F8h+var_18]
0x180033687  xor     rcx, rsp; StackCookie
0x18003368a  call    __security_check_cookie
0x18003368f  mov     rbx, [rsp+8F8h+arg_10]
0x180033697  add     rsp, 8F0h
0x18003369e  pop     rdi
0x18003369f  retn
0x1800336a0  lea     rcx, [rsp+8F8h+var_818]
0x1800336a8  call    ?__autoclassinit2@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(unsigned __int64)
0x1800336ad  lea     rcx, [rsp+8F8h+var_818]
0x1800336b5  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800336ba  nop
0x1800336bb  lea     rdx, aJsonVersionVal; "JSON version value is unexpected type "
0x1800336c2  lea     rcx, [rsp+8F8h+var_808]
0x1800336ca  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800336cf  mov     rbx, rax
0x1800336d2  mov     rcx, rdi
0x1800336d5  call    ?type@value@json@web@@QEBA?AW4value_type@123@XZ; web::json::value::type(void)
0x1800336da  mov     edx, eax
0x1800336dc  mov     rcx, rbx
0x1800336df  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x1800336e4  lea     rdx, [rsp+8F8h+var_838]
0x1800336ec  lea     rcx, [rsp+8F8h+var_818]
0x1800336f4  call    ?str@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x1800336f9  nop
0x1800336fa  lea     rcx, [rsp+8F8h+var_838]
0x180033702  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x180033707  mov     rdx, rax; char *
0x18003370a  lea     rcx, [rsp+8F8h+pExceptionObject]; this
0x18003370f  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180033714  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003371b  lea     rcx, [rsp+8F8h+pExceptionObject]; pExceptionObject
0x180033720  call    _CxxThrowException
0x180033726  lea     rdx, aOnly1Or2Versio; "only 1 or 2 versions expected for range"
0x18003372d  lea     rcx, [rsp+8F8h+var_888]; this
0x180033732  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180033737  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003373e  lea     rcx, [rsp+8F8h+var_888]; pExceptionObject
0x180033743  call    _CxxThrowException
```
