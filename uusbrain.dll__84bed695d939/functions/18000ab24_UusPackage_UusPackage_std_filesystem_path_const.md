# UusPackage::UusPackage(std::filesystem::path const &)

- ea: `0x18000ab24`
- end: `0x18000ae1e`
- name: `??0UusPackage@@QEAA@AEBVpath@filesystem@std@@@Z`
- size: `762`
- prototype: `UusPackage *__fastcall(UusPackage *this, const struct std::filesystem::path *)`
- caller_count: `6`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18000b024`
- `0x180036674`
- `0x180037064`
- `0x1800396d4`
- `0x180039858`
- `0x18003a2cc`

## callees

- `0x18000ab24`
- `0x18000b638`
- `0x18000d70c`
- `0x18000dc04`
- `0x180025c5c`
- `0x1800266b0`
- `0x180028728`
- `0x180028810`
- `0x180029158`
- `0x180029344`
- `0x1800295e8`
- `0x180029644`
- `0x180029984`
- `0x1800427d0`
- `0x180044848`
- `0x180047a30`

## string_xrefs

- `0x18000adfd`: `Required JSON (ver) field is missing.`
- `0x18000addc`: `JSON field (ver) is wrong type (string expected).`

## pseudocode

```c
UusPackage *__fastcall UusPackage::UusPackage(UusPackage *this, const struct std::filesystem::path *a2)
{
  __int64 *v4; // rax
  char v5; // bl
  __int64 v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rax
  const wchar_t *v9; // r8
  std::filesystem *v10; // rcx
  const wchar_t *root_name_end; // rax
  const wchar_t *v12; // rdx
  const wchar_t *v13; // r11
  const wchar_t *v14; // rcx
  _BYTE *v15; // rax
  __int64 v16; // rax
  std::filesystem *v18[4]; // [rsp+28h] [rbp-91h] BYREF
  _BYTE v19[32]; // [rsp+48h] [rbp-71h] BYREF
  UusPackage *v20; // [rsp+68h] [rbp-51h]
  _BYTE Src[32]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v22[32]; // [rsp+90h] [rbp-29h] BYREF
  std::filesystem **v23; // [rsp+B0h] [rbp-9h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+C0h] [rbp+7h] BYREF

  v20 = this;
  *(_QWORD *)this = &UusPackage::`vftable';
  std::wstring::wstring((char *)this + 8, a2);
  v4 = &UusPackage::_filenameBom;
  v5 = 7;
  if ( (unsigned __int64)qword_1800638E8 > 7 )
    v4 = (__int64 *)UusPackage::_filenameBom;
  pExceptionObject[0] = v4;
  pExceptionObject[1] = qword_1800638E0;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v19, pExceptionObject);
  v6 = std::filesystem::operator/(Src, a2, v19);
  UusPackage::GetBomContent((char *)this + 40, v6);
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(v19);
  v23 = (std::filesystem **)((char *)this + 48);
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 5) + 8LL))(
          *((_QWORD *)this + 5),
          UusPackage::_keyVer) )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Required JSON (ver) field is missing.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v23 = 0;
  v7 = (_QWORD *)web::json::value::at((char *)this + 40, UusPackage::_keyVer);
  (**(void (__fastcall ***)(_QWORD, std::filesystem ***))*v7)(*v7, &v23);
  if ( (*((unsigned int (__fastcall **)(std::filesystem **))*v23 + 11))(v23) != 2 )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "JSON field (ver) is wrong type (string expected).");
    throw (std::runtime_error *)pExceptionObject;
  }
  v8 = (*((__int64 (__fastcall **)(std::filesystem **))*v23 + 22))(v23);
  *((_QWORD *)this + 6) = &UusVersion::`vftable';
  *((_QWORD *)this + 7) = UusVersion::StrToVer<wchar_t>(v8);
  if ( v23 )
    (*((void (__fastcall **)(std::filesystem **, __int64))*v23 + 24))(v23, 1);
  std::wstring::wstring(v18, a2);
  v23 = v18;
  pExceptionObject[0] = (char *)this + 64;
  v10 = (std::filesystem *)v18;
  if ( v18[3] > (std::filesystem *)7 )
    v10 = v18[0];
  root_name_end = std::filesystem::_Find_root_name_end(v10, (const wchar_t *const)v10 + (__int64)v18[2], v9);
  if ( root_name_end != v13 )
  {
    do
    {
      if ( *root_name_end != 92 && *root_name_end != 47 )
        break;
      ++root_name_end;
    }
    while ( root_name_end != v12 );
  }
  if ( root_name_end == v12 )
    goto LABEL_19;
  do
  {
    v14 = v12 - 1;
    if ( *(v12 - 1) == 92 )
      break;
    if ( *v14 == 47 )
      break;
    --v12;
  }
  while ( root_name_end != v14 );
  if ( v13 == v12 )
  {
LABEL_19:
    v15 = (_BYTE *)std::filesystem::path::parent_path(v18, Src);
    v5 = 11;
  }
  else
  {
    std::wstring::wstring(v19, v18);
    v15 = v19;
  }
  std::wstring::wstring(pExceptionObject, v15);
  if ( (v5 & 8) != 0 )
  {
    v5 &= ~8u;
    std::wstring::_Tidy_deallocate(Src);
  }
  if ( (v5 & 4) != 0 )
    std::wstring::_Tidy_deallocate(v19);
  v16 = std::filesystem::path::filename(pExceptionObject, v22);
  std::wstring::wstring(v19, v16);
  UusVersion::TryStrToVer<wchar_t>((char *)this + 64, v19);
  std::wstring::_Tidy_deallocate(v19);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(pExceptionObject);
  std::wstring::_Tidy_deallocate(v18);
  return this;
}

```

## disassembly

```asm
0x18000ab24  mov     [rsp-8+arg_10], rbx
0x18000ab29  push    rbp
0x18000ab2a  push    rsi
0x18000ab2b  push    rdi
0x18000ab2c  push    r14
0x18000ab2e  push    r15
0x18000ab30  lea     rbp, [rsp-37h]
0x18000ab35  sub     rsp, 0F0h
0x18000ab3c  mov     rax, cs:__security_cookie
0x18000ab43  xor     rax, rsp
0x18000ab46  mov     [rbp+57h+var_30], rax
0x18000ab4a  mov     r15, rdx
0x18000ab4d  mov     rsi, rcx
0x18000ab50  mov     [rbp+57h+var_A8], rcx
0x18000ab54  mov     [rsp+110h+var_F0], 0
0x18000ab5c  lea     rax, ??_7UusPackage@@6B@; const UusPackage::`vftable'
0x18000ab63  mov     [rcx], rax
0x18000ab66  add     rcx, 8
0x18000ab6a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ab6f  nop
0x18000ab70  mov     rcx, cs:qword_1800638E0
0x18000ab77  lea     rax, ?_filenameBom@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_filenameBom
0x18000ab7e  mov     ebx, 7
0x18000ab83  cmp     cs:qword_1800638E8, rbx
0x18000ab8a  cmova   rax, cs:?_filenameBom@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_filenameBom
0x18000ab92  mov     [rbp+57h+pExceptionObject], rax
0x18000ab96  mov     [rbp+57h+var_48], rcx
0x18000ab9a  lea     rdx, [rbp+57h+pExceptionObject]
0x18000ab9e  lea     rcx, [rbp+57h+var_C8]
0x18000aba2  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000aba7  nop
0x18000aba8  lea     r8, [rbp+57h+var_C8]; void *
0x18000abac  mov     rdx, r15; void *
0x18000abaf  lea     rcx, [rbp+57h+Src]; Src
0x18000abb3  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000abb8  nop
0x18000abb9  lea     r14, [rsi+28h]
0x18000abbd  mov     rdx, rax
0x18000abc0  mov     rcx, r14
0x18000abc3  call    ?GetBomContent@UusPackage@@CA?AVvalue@json@web@@AEBVpath@filesystem@std@@@Z; UusPackage::GetBomContent(std::filesystem::path const &)
0x18000abc8  nop
0x18000abc9  lea     rcx, [rbp+57h+Src]
0x18000abcd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000abd2  nop
0x18000abd3  lea     rcx, [rbp+57h+var_C8]
0x18000abd7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000abdc  lea     rdi, [rsi+30h]
0x18000abe0  mov     [rbp+57h+var_60], rdi
0x18000abe4  mov     rcx, [r14]
0x18000abe7  mov     rax, [rcx]
0x18000abea  lea     rdx, ?_keyVer@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_keyVer
0x18000abf1  mov     rax, [rax+8]
0x18000abf5  call    _guard_dispatch_icall
0x18000abfa  test    al, al
0x18000abfc  jz      loc_18000ADFD
0x18000ac02  mov     [rbp+57h+var_60], 0
0x18000ac0a  lea     rdx, ?_keyVer@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_keyVer
0x18000ac11  mov     rcx, r14
0x18000ac14  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x18000ac19  mov     rcx, [rax]
0x18000ac1c  mov     rax, [rcx]
0x18000ac1f  lea     rdx, [rbp+57h+var_60]
0x18000ac23  mov     rax, [rax]
0x18000ac26  call    _guard_dispatch_icall
0x18000ac2b  nop
0x18000ac2c  mov     rcx, [rbp+57h+var_60]
0x18000ac30  mov     rax, [rcx]
0x18000ac33  mov     rax, [rax+58h]
0x18000ac37  call    _guard_dispatch_icall
0x18000ac3c  cmp     eax, 2
0x18000ac3f  jnz     loc_18000ADDC
0x18000ac45  mov     rcx, [rbp+57h+var_60]
0x18000ac49  mov     rax, [rcx]
0x18000ac4c  mov     rax, [rax+0B0h]
0x18000ac53  call    _guard_dispatch_icall
0x18000ac58  lea     rcx, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18000ac5f  mov     [rdi], rcx
0x18000ac62  mov     rcx, rax
0x18000ac65  call    ??$StrToVer@_W@UusVersion@@SA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; UusVersion::StrToVer<wchar_t>(std::wstring const &)
0x18000ac6a  mov     [rdi+8], rax
0x18000ac6e  mov     [rsp+110h+var_F0], 3
0x18000ac76  mov     rcx, [rbp+57h+var_60]
0x18000ac7a  test    rcx, rcx
0x18000ac7d  jz      short loc_18000AC92
0x18000ac7f  mov     rax, [rcx]
0x18000ac82  lea     edx, [rbx-6]
0x18000ac85  mov     rax, [rax+0C0h]
0x18000ac8c  call    _guard_dispatch_icall
0x18000ac91  nop
0x18000ac92  mov     rdx, r15
0x18000ac95  lea     rcx, [rsp+110h+var_E8]
0x18000ac9a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ac9f  lea     rax, [rsp+110h+var_E8]
0x18000aca4  mov     [rbp+57h+var_60], rax
0x18000aca8  lea     rdi, [rsi+40h]
0x18000acac  mov     [rbp+57h+pExceptionObject], rdi
0x18000acb0  lea     rcx, [rsp+110h+var_E8]
0x18000acb5  cmp     [rbp+57h+var_D0], rbx
0x18000acb9  cmova   rcx, [rsp+110h+var_E8]; this
0x18000acbf  mov     rax, [rsp+110h+var_D8]
0x18000acc4  lea     r11, [rcx+rax*2]
0x18000acc8  mov     rdx, r11; wchar_t *
0x18000accb  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x18000acd0  cmp     rax, r11
0x18000acd3  jz      short loc_18000ACEA
0x18000acd5  cmp     word ptr [rax], 5Ch ; '\'
0x18000acd9  jz      short loc_18000ACE1
0x18000acdb  cmp     word ptr [rax], 2Fh ; '/'
0x18000acdf  jnz     short loc_18000ACEA
0x18000ace1  add     rax, 2
0x18000ace5  cmp     rax, rdx
0x18000ace8  jnz     short loc_18000ACD5
0x18000acea  cmp     rax, rdx
0x18000aced  jz      short loc_18000AD20
0x18000acef  lea     rcx, [rdx-2]
0x18000acf3  cmp     word ptr [rcx], 5Ch ; '\'
0x18000acf7  jz      short loc_18000AD07
0x18000acf9  cmp     word ptr [rcx], 2Fh ; '/'
0x18000acfd  jz      short loc_18000AD07
0x18000acff  mov     rdx, rcx
0x18000ad02  cmp     rax, rcx
0x18000ad05  jnz     short loc_18000ACEF
0x18000ad07  cmp     r11, rdx
0x18000ad0a  jz      short loc_18000AD20
0x18000ad0c  lea     rdx, [rsp+110h+var_E8]
0x18000ad11  lea     rcx, [rbp+57h+var_C8]
0x18000ad15  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ad1a  lea     rax, [rbp+57h+var_C8]
0x18000ad1e  jmp     short loc_18000AD34
0x18000ad20  lea     rdx, [rbp+57h+Src]
0x18000ad24  lea     rcx, [rsp+110h+var_E8]
0x18000ad29  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x18000ad2e  nop
0x18000ad2f  mov     ebx, 0Bh
0x18000ad34  mov     [rsp+110h+var_F0], ebx
0x18000ad38  mov     rdx, rax
0x18000ad3b  lea     rcx, [rbp+57h+pExceptionObject]
0x18000ad3f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ad44  nop
0x18000ad45  test    bl, 8
0x18000ad48  jz      short loc_18000AD57
0x18000ad4a  and     ebx, 0FFFFFFF7h
0x18000ad4d  lea     rcx, [rbp+57h+Src]
0x18000ad51  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ad56  nop
0x18000ad57  test    bl, 4
0x18000ad5a  jz      short loc_18000AD65
0x18000ad5c  lea     rcx, [rbp+57h+var_C8]
0x18000ad60  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ad65  lea     rdx, [rbp+57h+var_80]
0x18000ad69  lea     rcx, [rbp+57h+pExceptionObject]
0x18000ad6d  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x18000ad72  nop
0x18000ad73  mov     rdx, rax
0x18000ad76  lea     rcx, [rbp+57h+var_C8]
0x18000ad7a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ad7f  nop
0x18000ad80  lea     rdx, [rbp+57h+var_C8]
0x18000ad84  mov     rcx, rdi
0x18000ad87  call    ??$TryStrToVer@_W@UusVersion@@SA?AV?$optional@VUusVersion@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; UusVersion::TryStrToVer<wchar_t>(std::wstring const &)
0x18000ad8c  nop
0x18000ad8d  lea     rcx, [rbp+57h+var_C8]
0x18000ad91  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ad96  nop
0x18000ad97  lea     rcx, [rbp+57h+var_80]
0x18000ad9b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ada0  nop
0x18000ada1  lea     rcx, [rbp+57h+pExceptionObject]
0x18000ada5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000adaa  nop
0x18000adab  lea     rcx, [rsp+110h+var_E8]
0x18000adb0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000adb5  nop
0x18000adb6  mov     rax, rsi
0x18000adb9  mov     rcx, [rbp+57h+var_30]
0x18000adbd  xor     rcx, rsp; StackCookie
0x18000adc0  call    __security_check_cookie
0x18000adc5  mov     rbx, [rsp+110h+arg_10]
0x18000adcd  add     rsp, 0F0h
0x18000add4  pop     r15
0x18000add6  pop     r14
0x18000add8  pop     rdi
0x18000add9  pop     rsi
0x18000adda  pop     rbp
0x18000addb  retn
0x18000addc  lea     rdx, aJsonFieldVerIs; "JSON field (ver) is wrong type (string "...
0x18000ade3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000ade7  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000adec  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000adf3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000adf7  call    _CxxThrowException
0x18000adfd  lea     rdx, aRequiredJsonVe; "Required JSON (ver) field is missing."
0x18000ae04  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18000ae08  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000ae0d  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000ae14  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000ae18  call    _CxxThrowException
```
