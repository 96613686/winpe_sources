# ClientState::ConsolidateStagedRegistryKeysForVersion(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180026e6c`
- end: `0x18002705d`
- name: `?ConsolidateStagedRegistryKeysForVersion@ClientState@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(ClientState *this, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x1800155cc`

## callees

- `0x180003110`
- `0x1800101fc`
- `0x180010278`
- `0x1800148e0`
- `0x180014928`
- `0x180019e68`
- `0x180024c70`
- `0x180025450`
- `0x180026e6c`
- `0x180027290`
- `0x180028298`
- `0x1800288a4`
- `0x18002b140`
- `0x18002b714`

## string_xrefs

- `0x180026ff7`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002700c`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180027021`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x180027036`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002704b`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
__int64 __fastcall ClientState::ConsolidateStagedRegistryKeysForVersion(ClientState *this, __int64 a2)
{
  HKEY v4; // rsi
  __int64 v5; // rax
  __int64 EtagStagedForVersion; // rax
  int v7; // eax
  const unsigned __int16 *v8; // rax
  int v9; // eax
  const unsigned __int16 *v10; // rax
  int v11; // eax
  const unsigned __int16 *v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rax
  int v16; // eax
  __int128 v18; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v19[32]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h]
  _BYTE v21[16]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v22; // [rsp+68h] [rbp+Fh]
  _BYTE v23[32]; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v20 = a2;
  v4 = (HKEY)*((_QWORD *)this + 52);
  v5 = std::wstring::wstring(v19, a2);
  EtagStagedForVersion = ClientState::GetEtagStagedForVersion(this, v5);
  std::wstring::wstring(v21, EtagStagedForVersion);
  if ( v22 )
  {
    if ( ClientState::IsETagValidated(this) )
    {
      v7 = RegValet::SetValue::String(v4, L"ETagBackup", *((const unsigned __int16 **)this + 9));
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4C7,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
          (const char *)(unsigned int)v7,
          v18);
    }
    v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    v9 = RegValet::SetValue::String(v4, L"ETag", v8);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4CC,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v9,
        v18);
    v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    v11 = RegValet::SetValue::String(v4, L"ETagValidated", v10);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D0,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v11,
        v18);
    v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    v13 = RegValet::SetValue::String(v4, L"ETagAcknowledged", v12);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D4,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v13,
        v18);
    std::operator+<unsigned short>(v23, v14, a2);
    v18 = *(_OWORD *)std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Eqrange<std::wstring>(
                       (char *)this + 96,
                       v19,
                       a2);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
      (char *)this + 96,
      &v18);
    v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
    v16 = RegValet::SetValue::Delete(v4, v15);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4DA,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v16,
        v18);
    std::wstring::_Tidy_deallocate(v23);
  }
  std::wstring::_Tidy_deallocate(v21);
  return std::wstring::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x180026e6c  mov     [rsp-8+arg_10], rbx
0x180026e71  push    rbp
0x180026e72  push    rsi
0x180026e73  push    rdi
0x180026e74  lea     rbp, [rsp-47h]
0x180026e79  sub     rsp, 0A0h
0x180026e80  mov     rax, cs:__security_cookie
0x180026e87  xor     rax, rsp
0x180026e8a  mov     [rbp+57h+var_18], rax
0x180026e8e  mov     rdi, rdx
0x180026e91  mov     rbx, rcx
0x180026e94  mov     [rbp+57h+var_60], rdx
0x180026e98  mov     rsi, [rcx+1A0h]
0x180026e9f  lea     rcx, [rbp+57h+var_80]
0x180026ea3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026ea8  mov     rdx, rax
0x180026eab  mov     rcx, rbx
0x180026eae  call    ?GetEtagStagedForVersion@ClientState@@QEAAPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ClientState::GetEtagStagedForVersion(std::wstring)
0x180026eb3  mov     rdx, rax
0x180026eb6  lea     rcx, [rbp+57h+var_58]
0x180026eba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180026ebf  nop
0x180026ec0  cmp     [rbp+57h+var_48], 0
0x180026ec5  jz      loc_180026FC3
0x180026ecb  mov     rcx, rbx; this
0x180026ece  call    ?IsETagValidated@ClientState@@QEBA_NXZ; ClientState::IsETagValidated(void)
0x180026ed3  test    al, al
0x180026ed5  jz      short loc_180026EF6
0x180026ed7  mov     r8, [rbx+48h]; unsigned __int16 *
0x180026edb  lea     rdx, ?c_regvalETagBackup@ClientState@@0QBGB; "ETagBackup"
0x180026ee2  mov     rcx, rsi; HKEY
0x180026ee5  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x180026eea  mov     rcx, [rbp+5Fh]; this
0x180026eee  test    eax, eax
0x180026ef0  js      loc_180027009
0x180026ef6  lea     rcx, [rbp+57h+var_58]
0x180026efa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026eff  mov     r8, rax; unsigned __int16 *
0x180026f02  lea     rdx, ?c_regvalETag@ClientState@@0QBGB; "ETag"
0x180026f09  mov     rcx, rsi; HKEY
0x180026f0c  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x180026f11  mov     rcx, [rbp+5Fh]; this
0x180026f15  test    eax, eax
0x180026f17  js      loc_18002701E
0x180026f1d  lea     rcx, [rbp+57h+var_58]
0x180026f21  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026f26  mov     r8, rax; unsigned __int16 *
0x180026f29  lea     rdx, ?c_regvalETagValidated@ClientState@@0QBGB; "ETagValidated"
0x180026f30  mov     rcx, rsi; HKEY
0x180026f33  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x180026f38  mov     rcx, [rbp+5Fh]; this
0x180026f3c  test    eax, eax
0x180026f3e  js      loc_180027033
0x180026f44  lea     rcx, [rbp+57h+var_58]
0x180026f48  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026f4d  mov     r8, rax; unsigned __int16 *
0x180026f50  lea     rdx, ?c_regvalETagAcknowledged@ClientState@@0QBGB; "ETagAcknowledged"
0x180026f57  mov     rcx, rsi; HKEY
0x180026f5a  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x180026f5f  mov     rcx, [rbp+5Fh]; this
0x180026f63  test    eax, eax
0x180026f65  js      loc_180027048
0x180026f6b  mov     r8, rdi
0x180026f6e  lea     rcx, [rbp+57h+var_38]
0x180026f72  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180026f77  nop
0x180026f78  mov     r8, rdi
0x180026f7b  lea     rdx, [rbp+57h+var_80]
0x180026f7f  lea     rcx, [rbx+60h]
0x180026f83  call    ??$_Eqrange@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@PEAU12@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Eqrange<std::wstring>(std::wstring const &)
0x180026f88  movups  xmm0, xmmword ptr [rax]
0x180026f8b  movdqu  [rbp+57h+var_90], xmm0
0x180026f90  lea     rdx, [rbp+57h+var_90]
0x180026f94  lea     rcx, [rbx+60h]
0x180026f98  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *>)
0x180026f9d  lea     rcx, [rbp+57h+var_38]
0x180026fa1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180026fa6  mov     rdx, rax; unsigned __int16 *
0x180026fa9  mov     rcx, rsi; HKEY
0x180026fac  call    ?Delete@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG@Z; RegValet::SetValue::Delete(HKEY__ *,ushort const *)
0x180026fb1  mov     rcx, [rbp+5Fh]; this
0x180026fb5  test    eax, eax
0x180026fb7  js      short loc_180026FF4
0x180026fb9  lea     rcx, [rbp+57h+var_38]
0x180026fbd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026fc2  nop
0x180026fc3  lea     rcx, [rbp+57h+var_58]
0x180026fc7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026fcc  nop
0x180026fcd  mov     rcx, rdi
0x180026fd0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026fd5  mov     rcx, [rbp+57h+var_18]
0x180026fd9  xor     rcx, rsp; StackCookie
0x180026fdc  call    __security_check_cookie
0x180026fe1  mov     rbx, [rsp+0B0h+arg_10]
0x180026fe9  add     rsp, 0A0h
0x180026ff0  pop     rdi
0x180026ff1  pop     rsi
0x180026ff2  pop     rbp
0x180026ff3  retn
0x180026ff4  mov     r9d, eax; char *
0x180026ff7  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180026ffe  mov     edx, 4DAh; void *
0x180027003  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027009  mov     r9d, eax; char *
0x18002700c  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180027013  mov     edx, 4C7h; void *
0x180027018  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002701e  mov     r9d, eax; char *
0x180027021  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180027028  mov     edx, 4CCh; void *
0x18002702d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027033  mov     r9d, eax; char *
0x180027036  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002703d  mov     edx, 4D0h; void *
0x180027042  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027048  mov     r9d, eax; char *
0x18002704b  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x180027052  mov     edx, 4D4h; void *
0x180027057  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
