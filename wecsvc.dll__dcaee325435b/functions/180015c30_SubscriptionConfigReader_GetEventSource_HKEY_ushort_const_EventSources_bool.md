# SubscriptionConfigReader::GetEventSource(HKEY__ *,ushort const *,_EventSources &,bool)

- ea: `0x180015c30`
- end: `0x180015dcb`
- name: `?GetEventSource@SubscriptionConfigReader@@QEBA_NPEAUHKEY__@@PEBGAEAU_EventSources@@_N@Z`
- size: `411`
- prototype: `char __fastcall(SubscriptionConfigReader *this, HKEY, const unsigned __int16 *, struct _EventSources *, bool)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x180015dd4`
- `0x180015f78`

## callees

- `0x180003810`
- `0x1800062d4`
- `0x180006334`
- `0x180006898`
- `0x1800111f8`
- `0x1800112e8`
- `0x180012424`
- `0x1800128c0`
- `0x180015c30`
- `0x1800161e4`
- `0x180016514`
- `0x180019048`
- `0x1800194dc`
- `0x180019904`
- `0x18001997c`
- `0x18001fe50`

## pseudocode

```c
char __fastcall SubscriptionConfigReader::GetEventSource(
        SubscriptionConfigReader *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct _EventSources *a4,
        bool a5)
{
  __int64 v9; // rcx
  bool v11[4]; // [rsp+30h] [rbp-51h] BYREF
  unsigned int v12; // [rsp+34h] [rbp-4Dh] BYREF
  unsigned int v13; // [rsp+38h] [rbp-49h] BYREF
  __int128 v14; // [rsp+40h] [rbp-41h] BYREF
  _BYTE v15[16]; // [rsp+50h] [rbp-31h] BYREF
  __int128 v16; // [rsp+60h] [rbp-21h] BYREF
  __int64 v17; // [rsp+70h] [rbp-11h]
  _QWORD v18[4]; // [rsp+80h] [rbp-1h] BYREF

  v12 = 0;
  std::vector<unsigned long>::push_back(a4, &v12);
  std::wstring::wstring((__int64)&v16, (__int64)a3);
  std::vector<std::wstring>::push_back((char *)a4 + 56, &v16);
  std::wstring::_Tidy(&v16, 1, 0);
  v12 = 1;
  ConfigBase::GetRegEnumValue(
    this,
    L"SubscriptionType",
    (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueSubscriptionType,
    &v12);
  v13 = 0;
  v11[0] = v12 == 0;
  if ( RegReadDWORDValue(a2, L"Enabled", &v13) )
    v11[0] = v13 != 0;
  v14 = *(_OWORD *)std::vector<bool>::end((char *)a4 + 24, v15);
  std::vector<bool>::_Insert_n((_DWORD)a4 + 24, (unsigned int)&v16, (unsigned int)&v14, 1, (__int64)v11);
  std::wstring::wstring((__int64)v18, (__int64)&word_180026AD8);
  v16 = 0;
  v17 = 0;
  std::vector<unsigned short>::resize(&v16, 1);
  *(_WORD *)v16 = 0;
  RegReadStringValue(a2, L"UserName", v18);
  std::vector<std::wstring>::push_back((char *)a4 + 80, v18);
  if ( a5 )
    SubscriptionConfigReader::ReadPassword(v9, (__int64)a2, (__int64)L"TargetId", &v16);
  std::vector<std::vector<unsigned short>>::push_back((char *)a4 + 104, &v16);
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>((__int64)&v16);
  std::wstring::_Tidy(v18, 1, 0);
  return 1;
}

```

## disassembly

```asm
0x180015c30  push    rbp
0x180015c32  push    rbx
0x180015c33  push    rsi
0x180015c34  push    rdi
0x180015c35  push    r14
0x180015c37  lea     rbp, [rsp-2Fh]
0x180015c3c  sub     rsp, 0B0h
0x180015c43  mov     rax, cs:__security_cookie
0x180015c4a  xor     rax, rsp
0x180015c4d  mov     [rbp+4Fh+var_30], rax
0x180015c51  mov     rsi, r9
0x180015c54  mov     rbx, r8
0x180015c57  mov     r14, rdx
0x180015c5a  mov     rdi, rcx
0x180015c5d  mov     [rbp+4Fh+var_9C], 0
0x180015c64  lea     rdx, [rbp+4Fh+var_9C]
0x180015c68  mov     rcx, r9
0x180015c6b  call    ?push_back@?$vector@KV?$allocator@K@std@@@std@@QEAAX$$QEAK@Z; std::vector<ulong>::push_back(ulong &&)
0x180015c70  mov     rdx, rbx
0x180015c73  lea     rcx, [rbp+4Fh+var_70]
0x180015c77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180015c7c  nop
0x180015c7d  lea     rcx, [rsi+38h]
0x180015c81  lea     rdx, [rbp+4Fh+var_70]
0x180015c85  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x180015c8a  nop
0x180015c8b  xor     r8d, r8d
0x180015c8e  lea     ebx, [r8+1]
0x180015c92  mov     dl, bl
0x180015c94  lea     rcx, [rbp+4Fh+var_70]
0x180015c98  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015c9d  mov     [rbp+4Fh+var_9C], ebx
0x180015ca0  lea     r9, [rbp+4Fh+var_9C]; unsigned int *
0x180015ca4  lea     r8, ?EnumNameValueSubscriptionType@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x180015cab  lea     rdx, aSubscriptionty; "SubscriptionType"
0x180015cb2  mov     rcx, rdi; this
0x180015cb5  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x180015cba  mov     [rbp+4Fh+var_98], 0
0x180015cc1  cmp     [rbp+4Fh+var_9C], 0
0x180015cc5  setz    [rbp+4Fh+var_A0]
0x180015cc9  lea     r8, [rbp+4Fh+var_98]; unsigned int *
0x180015ccd  lea     rdx, aEnabled; "Enabled"
0x180015cd4  mov     rcx, r14; HKEY
0x180015cd7  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x180015cdc  test    al, al
0x180015cde  jz      short loc_180015CE8
0x180015ce0  cmp     [rbp+4Fh+var_98], 0
0x180015ce4  setnz   [rbp+4Fh+var_A0]
0x180015ce8  lea     rdx, [rbp+4Fh+var_80]
0x180015cec  lea     rcx, [rsi+18h]
0x180015cf0  call    ?end@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::end(void)
0x180015cf5  movups  xmm0, xmmword ptr [rax]
0x180015cf8  movdqu  [rbp+4Fh+var_90], xmm0
0x180015cfd  lea     rax, [rbp+4Fh+var_A0]
0x180015d01  mov     [rsp+0D0h+var_B0], rax
0x180015d06  mov     r9, rbx
0x180015d09  lea     r8, [rbp+4Fh+var_90]
0x180015d0d  lea     rdx, [rbp+4Fh+var_70]
0x180015d11  lea     rcx, [rsi+18h]
0x180015d15  call    ?_Insert_n@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@V?$_Vb_const_iterator@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@_KAEB_N@Z; std::vector<bool>::_Insert_n(std::_Vb_const_iterator<std::_Wrap_alloc<std::allocator<uint>>>,unsigned __int64,bool const &)
0x180015d1a  lea     rdx, word_180026AD8
0x180015d21  lea     rcx, [rbp+4Fh+var_50]
0x180015d25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180015d2a  nop
0x180015d2b  xorps   xmm0, xmm0
0x180015d2e  movdqu  [rbp+4Fh+var_70], xmm0
0x180015d33  mov     [rbp+4Fh+var_60], 0
0x180015d3b  mov     rdx, rbx
0x180015d3e  lea     rcx, [rbp+4Fh+var_70]
0x180015d42  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180015d47  xor     ecx, ecx
0x180015d49  mov     rax, qword ptr [rbp+4Fh+var_70]
0x180015d4d  mov     [rax], cx
0x180015d50  lea     r8, [rbp+4Fh+var_50]
0x180015d54  lea     rdx, aUsername; "UserName"
0x180015d5b  mov     rcx, r14
0x180015d5e  call    ?RegReadStringValue@@YA_NPEAUHKEY__@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegReadStringValue(HKEY__ *,ushort const *,std::wstring &)
0x180015d63  lea     rcx, [rsi+50h]
0x180015d67  lea     rdx, [rbp+4Fh+var_50]
0x180015d6b  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x180015d70  cmp     [rbp+4Fh+arg_20], 0
0x180015d74  jz      short loc_180015D89
0x180015d76  lea     r9, [rbp+4Fh+var_70]
0x180015d7a  lea     r8, aTargetid; "TargetId"
0x180015d81  mov     rdx, r14
0x180015d84  call    ?ReadPassword@SubscriptionConfigReader@@IEBA_NPEAUHKEY__@@PEBGAEAV?$vector@GV?$allocator@G@std@@@std@@@Z; SubscriptionConfigReader::ReadPassword(HKEY__ *,ushort const *,std::vector<ushort> &)
0x180015d89  lea     rcx, [rsi+68h]
0x180015d8d  lea     rdx, [rbp+4Fh+var_70]
0x180015d91  call    ?push_back@?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@QEAAXAEBV?$vector@GV?$allocator@G@std@@@2@@Z; std::vector<std::vector<ushort>>::push_back(std::vector<ushort> const &)
0x180015d96  nop
0x180015d97  lea     rcx, [rbp+4Fh+var_70]
0x180015d9b  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x180015da0  nop
0x180015da1  xor     r8d, r8d
0x180015da4  mov     dl, bl
0x180015da6  lea     rcx, [rbp+4Fh+var_50]
0x180015daa  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015daf  mov     al, bl
0x180015db1  mov     rcx, [rbp+4Fh+var_30]
0x180015db5  xor     rcx, rsp; StackCookie
0x180015db8  call    __security_check_cookie
0x180015dbd  add     rsp, 0B0h
0x180015dc4  pop     r14
0x180015dc6  pop     rdi
0x180015dc7  pop     rsi
0x180015dc8  pop     rbx
0x180015dc9  pop     rbp
0x180015dca  retn
```
