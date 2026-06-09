# ClientState::SaveRegData(HKEY__ *)

- ea: `0x18002a954`
- end: `0x18002ade2`
- name: `?SaveRegData@ClientState@@AEBAXPEAUHKEY__@@@Z`
- size: `1166`
- prototype: `void(ClientState *__hidden this, HKEY)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x18000faf0`
- `0x180014f6c`
- `0x180026518`

## callees

- `0x180003110`
- `0x18000a09c`
- `0x1800101fc`
- `0x180010278`
- `0x180019e68`
- `0x180021f60`
- `0x180024c70`
- `0x180025b84`
- `0x18002a8e0`
- `0x18002a954`
- `0x18002b140`
- `0x18002b254`
- `0x18002bd0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ac6f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ac6f`

## string_xrefs

- `0x18002a9a1`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a985`: `The state must be opened with a full access in order to persist it`
- `0x18002abd8`: `LastUserTokenResult`
- `0x18002abac`: `LastDeviceTokenResult`
- `0x18002aadf`: `LastRefreshAttempted`
- `0x18002aa9c`: `LastUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ClientState::SaveRegData(ClientState *this, HKEY a2)
{
  int v4; // eax
  const char *v5; // rdx
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rax
  const unsigned __int16 *v8; // r8
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  const void *v18; // r9
  int v19; // eax
  int v20; // eax
  int v21; // [rsp+20h] [rbp-59h]
  int v22; // [rsp+20h] [rbp-59h]
  int v23; // [rsp+20h] [rbp-59h]
  int v24; // [rsp+20h] [rbp-59h]
  int v25; // [rsp+20h] [rbp-59h]
  int v26; // [rsp+20h] [rbp-59h]
  int v27; // [rsp+20h] [rbp-59h]
  int v28; // [rsp+20h] [rbp-59h]
  int v29; // [rsp+20h] [rbp-59h]
  const char *v30; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v31[40]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v32[32]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v33[32]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x34E,
    (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
    (const char *)0x80070005LL,
    *((_BYTE *)this + 424),
    (bool)"The state must be opened with a full access in order to persist it",
    v30);
  v4 = RegValet::SetValue::String(a2, L"ETag", *((const unsigned __int16 **)this + 9));
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x351,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v4,
      v21);
  v5 = (const char *)**((_QWORD **)this + 12);
  v30 = v5;
  while ( !v5[25] )
  {
    std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(v32, v5 + 32);
    std::operator+<unsigned short>(v31, v6, v32);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
    v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
    v9 = RegValet::SetValue::String(a2, v7, v8);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x357,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v9,
        v21);
    std::wstring::_Tidy_deallocate(v31);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v32);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&v30);
    v5 = v30;
  }
  v10 = RegValet::SetValue::String(a2, L"ETagBackup", *((const unsigned __int16 **)this + 14));
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x35B,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v10,
      v21);
  if ( *((_DWORD *)this + 47) || *((_DWORD *)this + 46) )
  {
    v30 = (const char *)*((_QWORD *)this + 23);
    v11 = RegValet::SetValue::_Set(a2, L"LastUpdated", 0xBu, &v30, 8u);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x360,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v11,
        v22);
  }
  if ( *((_DWORD *)this + 49) || *((_DWORD *)this + 48) )
  {
    v30 = (const char *)*((_QWORD *)this + 24);
    v12 = RegValet::SetValue::_Set(a2, L"LastRefreshAttempted", 0xBu, &v30, 8u);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x366,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v12,
        v23);
  }
  if ( *((_DWORD *)this + 51) || *((_DWORD *)this + 50) )
  {
    v30 = (const char *)*((_QWORD *)this + 25);
    v13 = RegValet::SetValue::_Set(a2, L"LastRefreshByApp", 0xBu, &v30, 8u);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36C,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v13,
        v24);
  }
  LODWORD(v30) = *((_DWORD *)this + 52);
  v14 = RegValet::SetValue::_Set(a2, L"RefreshInterval", 4u, &v30, 4u);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x370,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v14,
      v25);
  LODWORD(v30) = *((_DWORD *)this + 53);
  v15 = RegValet::SetValue::_Set(a2, L"LastHTTPCode", 4u, &v30, 4u);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x373,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v15,
      v26);
  LODWORD(v30) = *((_DWORD *)this + 54);
  v16 = RegValet::SetValue::_Set(a2, L"LastDeviceTokenResult", 4u, &v30, 4u);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x376,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v16,
      v27);
  LODWORD(v30) = *((_DWORD *)this + 55);
  v17 = RegValet::SetValue::_Set(a2, L"LastUserTokenResult", 4u, &v30, 4u);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x379,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v17,
      v28);
  v18 = (const void *)*((_QWORD *)this + 28);
  if ( v18 && *((_DWORD *)this + 58) )
    RegValet::SetValue::_Set(a2, L"QueryStringHash", 3u, v18, *((unsigned int *)this + 58));
  v19 = RegValet::SetValue::String(a2, L"Version", *((const unsigned __int16 **)this + 32));
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x381,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v19,
      v28);
  ClientState::SaveIfValidButDeleteIfEmpty(a2, L"LastPayload", (ClientState *)((char *)this + 328));
  if ( *((_QWORD *)this + 42) )
    ClientState::SaveIfValidButDeleteIfEmpty(a2, L"LastTestPayload", (ClientState *)((char *)this + 336));
  else
    RegDeleteValueW(a2, L"LastTestPayload");
  ClientState::SaveIfValidButDeleteIfEmpty(a2, L"LastNotification", (ClientState *)((char *)this + 392));
  if ( *((_DWORD *)this + 102) || *((_DWORD *)this + 101) )
  {
    v30 = *(const char **)((char *)this + 404);
    v20 = RegValet::SetValue::_Set(a2, L"LastForceRefresh", 0xBu, &v30, 8u);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x393,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v20,
        v29);
  }
}

```

## disassembly

```asm
0x18002a954  mov     [rsp-8+arg_10], rbx
0x18002a959  push    rbp
0x18002a95a  push    rdi
0x18002a95b  push    r12
0x18002a95d  push    r14
0x18002a95f  push    r15
0x18002a961  lea     rbp, [rsp-37h]
0x18002a966  sub     rsp, 0B0h
0x18002a96d  mov     rax, cs:__security_cookie
0x18002a974  xor     rax, rsp
0x18002a977  mov     [rbp+57h+var_30], rax
0x18002a97b  mov     rdi, rdx
0x18002a97e  mov     rbx, rcx
0x18002a981  mov     rcx, [rbp+5Fh]; this
0x18002a985  lea     rax, aTheStateMustBe; "The state must be opened with a full ac"...
0x18002a98c  mov     qword ptr [rsp+0D0h+var_A8], rax; bool
0x18002a991  mov     al, [rbx+1A8h]
0x18002a997  mov     [rsp+0D0h+var_B0], al; int
0x18002a99b  mov     r9d, 80070005h; char *
0x18002a9a1  lea     r14, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a9a8  mov     r8, r14; unsigned int
0x18002a9ab  mov     edx, 34Eh; void *
0x18002a9b0  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002a9b5  mov     r8, [rbx+48h]; unsigned __int16 *
0x18002a9b9  lea     rdx, ?c_regvalETag@ClientState@@0QBGB; "ETag"
0x18002a9c0  mov     rcx, rdi; HKEY
0x18002a9c3  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x18002a9c8  mov     rcx, [rbp+5Fh]; this
0x18002a9cc  test    eax, eax
0x18002a9ce  js      loc_18002AD03
0x18002a9d4  mov     rdx, [rbx+60h]
0x18002a9d8  mov     rdx, [rdx]
0x18002a9db  mov     [rbp+57h+var_A0], rdx
0x18002a9df  cmp     byte ptr [rdx+19h], 0
0x18002a9e3  jnz     short loc_18002AA4F
0x18002a9e5  add     rdx, 20h ; ' '
0x18002a9e9  lea     rcx, [rbp+57h+var_70]
0x18002a9ed  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,std::wstring>::pair<std::wstring const,std::wstring>(std::pair<std::wstring const,std::wstring> const &)
0x18002a9f2  nop
0x18002a9f3  lea     r8, [rbp+57h+var_70]
0x18002a9f7  lea     rcx, [rbp+57h+var_98]
0x18002a9fb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18002aa00  nop
0x18002aa01  lea     rcx, [rbp+57h+var_50]
0x18002aa05  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002aa0a  mov     r8, rax
0x18002aa0d  lea     rcx, [rbp+57h+var_98]
0x18002aa11  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002aa16  mov     rdx, rax; unsigned __int16 *
0x18002aa19  mov     rcx, rdi; HKEY
0x18002aa1c  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x18002aa21  mov     rcx, [rbp+5Fh]; this
0x18002aa25  test    eax, eax
0x18002aa27  js      loc_18002AD14
0x18002aa2d  lea     rcx, [rbp+57h+var_98]
0x18002aa31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aa36  nop
0x18002aa37  lea     rcx, [rbp+57h+var_70]
0x18002aa3b  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18002aa40  lea     rcx, [rbp+57h+var_A0]
0x18002aa44  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x18002aa49  mov     rdx, [rbp+57h+var_A0]
0x18002aa4d  jmp     short loc_18002A9DF
0x18002aa4f  mov     r8, [rbx+70h]; unsigned __int16 *
0x18002aa53  lea     rdx, ?c_regvalETagBackup@ClientState@@0QBGB; "ETagBackup"
0x18002aa5a  mov     rcx, rdi; HKEY
0x18002aa5d  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x18002aa62  test    eax, eax
0x18002aa64  js      loc_18002AD25
0x18002aa6a  mov     r12d, 8
0x18002aa70  cmp     dword ptr [rbx+0BCh], 0
0x18002aa77  jnz     short loc_18002AA82
0x18002aa79  cmp     dword ptr [rbx+0B8h], 0
0x18002aa80  jz      short loc_18002AAB3
0x18002aa82  mov     rax, [rbx+0B8h]
0x18002aa89  mov     [rbp+57h+var_A0], rax
0x18002aa8d  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x18002aa92  lea     r9, [rbp+57h+var_A0]; void *
0x18002aa96  mov     r8d, 0Bh; unsigned int
0x18002aa9c  lea     rdx, ?c_regvalLastUpdated@ClientState@@0QBGB; "LastUpdated"
0x18002aaa3  mov     rcx, rdi; HKEY
0x18002aaa6  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002aaab  test    eax, eax
0x18002aaad  js      loc_18002AD3A
0x18002aab3  cmp     dword ptr [rbx+0C4h], 0
0x18002aaba  jnz     short loc_18002AAC5
0x18002aabc  cmp     dword ptr [rbx+0C0h], 0
0x18002aac3  jz      short loc_18002AAF6
0x18002aac5  mov     rax, [rbx+0C0h]
0x18002aacc  mov     [rbp+57h+var_A0], rax
0x18002aad0  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x18002aad5  lea     r9, [rbp+57h+var_A0]; void *
0x18002aad9  mov     r8d, 0Bh; unsigned int
0x18002aadf  lea     rdx, ?c_regvalLastRefresh@ClientState@@0QBGB; "LastRefreshAttempted"
0x18002aae6  mov     rcx, rdi; HKEY
0x18002aae9  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002aaee  test    eax, eax
0x18002aaf0  js      loc_18002AD4F
0x18002aaf6  cmp     dword ptr [rbx+0CCh], 0
0x18002aafd  jnz     short loc_18002AB08
0x18002aaff  cmp     dword ptr [rbx+0C8h], 0
0x18002ab06  jz      short loc_18002AB39
0x18002ab08  mov     rax, [rbx+0C8h]
0x18002ab0f  mov     [rbp+57h+var_A0], rax
0x18002ab13  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x18002ab18  lea     r9, [rbp+57h+var_A0]; void *
0x18002ab1c  mov     r8d, 0Bh; unsigned int
0x18002ab22  lea     rdx, ?c_regvalLastRefreshByApp@ClientState@@0QBGB; "LastRefreshByApp"
0x18002ab29  mov     rcx, rdi; HKEY
0x18002ab2c  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002ab31  test    eax, eax
0x18002ab33  js      loc_18002AD64
0x18002ab39  mov     eax, [rbx+0D0h]
0x18002ab3f  mov     dword ptr [rbp+57h+var_A0], eax
0x18002ab42  mov     r15d, 4
0x18002ab48  mov     qword ptr [rsp+0D0h+var_B0], r15; int
0x18002ab4d  lea     r9, [rbp+57h+var_A0]; void *
0x18002ab51  mov     r8d, r15d; unsigned int
0x18002ab54  lea     rdx, ?c_regvalRefreshInterval@ClientState@@0QBGB; "RefreshInterval"
0x18002ab5b  mov     rcx, rdi; HKEY
0x18002ab5e  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002ab63  test    eax, eax
0x18002ab65  js      loc_18002AD79
0x18002ab6b  mov     eax, [rbx+0D4h]
0x18002ab71  mov     dword ptr [rbp+57h+var_A0], eax
0x18002ab74  mov     qword ptr [rsp+0D0h+var_B0], r15; int
0x18002ab79  lea     r9, [rbp+57h+var_A0]; void *
0x18002ab7d  mov     r8d, r15d; unsigned int
0x18002ab80  lea     rdx, ?c_regvalLastHTTPCode@ClientState@@0QBGB; "LastHTTPCode"
0x18002ab87  mov     rcx, rdi; HKEY
0x18002ab8a  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002ab8f  test    eax, eax
0x18002ab91  js      loc_18002AD8E
0x18002ab97  mov     eax, [rbx+0D8h]
0x18002ab9d  mov     dword ptr [rbp+57h+var_A0], eax
0x18002aba0  mov     qword ptr [rsp+0D0h+var_B0], r15; int
0x18002aba5  lea     r9, [rbp+57h+var_A0]; void *
0x18002aba9  mov     r8d, r15d; unsigned int
0x18002abac  lea     rdx, ?c_regvalLastDeviceTokenResult@ClientState@@0QBGB; "LastDeviceTokenResult"
0x18002abb3  mov     rcx, rdi; HKEY
0x18002abb6  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002abbb  test    eax, eax
0x18002abbd  js      loc_18002ADA3
0x18002abc3  mov     eax, [rbx+0DCh]
0x18002abc9  mov     dword ptr [rbp+57h+var_A0], eax
0x18002abcc  mov     qword ptr [rsp+0D0h+var_B0], r15; int
0x18002abd1  lea     r9, [rbp+57h+var_A0]; void *
0x18002abd5  mov     r8d, r15d; unsigned int
0x18002abd8  lea     rdx, ?c_regvalLastUserTokenResult@ClientState@@0QBGB; "LastUserTokenResult"
0x18002abdf  mov     rcx, rdi; HKEY
0x18002abe2  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002abe7  test    eax, eax
0x18002abe9  js      loc_18002ADB8
0x18002abef  mov     r9, [rbx+0E0h]; void *
0x18002abf6  test    r9, r9
0x18002abf9  jz      short loc_18002AC1D
0x18002abfb  mov     eax, [rbx+0E8h]
0x18002ac01  test    eax, eax
0x18002ac03  jz      short loc_18002AC1D
0x18002ac05  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18002ac0a  lea     r8d, [r15-1]; unsigned int
0x18002ac0e  lea     rdx, ?c_regvalQueryStringHash@ClientState@@0QBGB; "QueryStringHash"
0x18002ac15  mov     rcx, rdi; HKEY
0x18002ac18  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002ac1d  mov     r8, [rbx+100h]; unsigned __int16 *
0x18002ac24  lea     rdx, ?c_regvalLastVersion@ClientState@@0QBGB; "Version"
0x18002ac2b  mov     rcx, rdi; HKEY
0x18002ac2e  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x18002ac33  test    eax, eax
0x18002ac35  js      loc_18002ADCD
0x18002ac3b  lea     r8, [rbx+148h]; struct Microsoft::WRL::Wrappers::HString *
0x18002ac42  lea     rdx, ?c_regvalLastPayload@ClientState@@0QBGB; "LastPayload"
0x18002ac49  mov     rcx, rdi; HKEY
0x18002ac4c  call    ?SaveIfValidButDeleteIfEmpty@ClientState@@CAXPEAUHKEY__@@PEBGAEBVHString@Wrappers@WRL@Microsoft@@@Z; ClientState::SaveIfValidButDeleteIfEmpty(HKEY__ *,ushort const *,Microsoft::WRL::Wrappers::HString const &)
0x18002ac51  lea     r8, [rbx+150h]; struct Microsoft::WRL::Wrappers::HString *
0x18002ac58  lea     rdx, ?c_regvalLastTestPayload@ClientState@@0QBGB; "LastTestPayload"
0x18002ac5f  mov     rcx, rdi; HKEY
0x18002ac62  cmp     qword ptr [r8], 0
0x18002ac66  jz      short loc_18002AC6F
0x18002ac68  call    ?SaveIfValidButDeleteIfEmpty@ClientState@@CAXPEAUHKEY__@@PEBGAEBVHString@Wrappers@WRL@Microsoft@@@Z; ClientState::SaveIfValidButDeleteIfEmpty(HKEY__ *,ushort const *,Microsoft::WRL::Wrappers::HString const &)
0x18002ac6d  jmp     short loc_18002AC75
0x18002ac6f  call    cs:__imp_RegDeleteValueW
0x18002ac75  lea     r8, [rbx+188h]; struct Microsoft::WRL::Wrappers::HString *
0x18002ac7c  lea     rdx, ?c_regvalLastNotification@ClientState@@0QBGB; "LastNotification"
0x18002ac83  mov     rcx, rdi; HKEY
0x18002ac86  call    ?SaveIfValidButDeleteIfEmpty@ClientState@@CAXPEAUHKEY__@@PEBGAEBVHString@Wrappers@WRL@Microsoft@@@Z; ClientState::SaveIfValidButDeleteIfEmpty(HKEY__ *,ushort const *,Microsoft::WRL::Wrappers::HString const &)
0x18002ac8b  cmp     dword ptr [rbx+198h], 0
0x18002ac92  jnz     short loc_18002AC9D
0x18002ac94  cmp     dword ptr [rbx+194h], 0
0x18002ac9b  jz      short loc_18002ACCA
0x18002ac9d  mov     rax, [rbx+194h]
0x18002aca4  mov     [rbp+57h+var_A0], rax
0x18002aca8  mov     qword ptr [rsp+0D0h+var_B0], r12; int
0x18002acad  lea     r9, [rbp+57h+var_A0]; void *
0x18002acb1  mov     r8d, 0Bh; unsigned int
0x18002acb7  lea     rdx, ?c_regvalLastForceRefresh@ClientState@@0QBGB; "LastForceRefresh"
0x18002acbe  mov     rcx, rdi; HKEY
0x18002acc1  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002acc6  test    eax, eax
0x18002acc8  js      short loc_18002ACEE
0x18002acca  mov     rcx, [rbp+57h+var_30]
0x18002acce  xor     rcx, rsp; StackCookie
0x18002acd1  call    __security_check_cookie
0x18002acd6  mov     rbx, [rsp+0D0h+arg_10]
0x18002acde  add     rsp, 0B0h
0x18002ace5  pop     r15
0x18002ace7  pop     r14
0x18002ace9  pop     r12
0x18002aceb  pop     rdi
0x18002acec  pop     rbp
0x18002aced  retn
0x18002acee  mov     rcx, [rbp+5Fh]; this
0x18002acf2  mov     r9d, eax; char *
0x18002acf5  mov     r8, r14; unsigned int
0x18002acf8  mov     edx, 393h; void *
0x18002acfd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ad03  mov     r9d, eax; char *
0x18002ad06  mov     r8, r14; unsigned int
0x18002ad09  mov     edx, 351h; void *
0x18002ad0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ad14  mov     r9d, eax; char *
0x18002ad17  mov     r8, r14; unsigned int
0x18002ad1a  mov     edx, 357h; void *
0x18002ad1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ad25  mov     rcx, [rbp+5Fh]; this
0x18002ad29  mov     r9d, eax; char *
0x18002ad2c  mov     r8, r14; unsigned int
0x18002ad2f  mov     edx, 35Bh; void *
0x18002ad34  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ad3a  mov     rcx, [rbp+5Fh]; this
0x18002ad3e  mov     r9d, eax; char *
0x18002ad41  mov     r8, r14; unsigned int
0x18002ad44  mov     edx, 360h; void *
0x18002ad49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ad4f  mov     rcx, [rbp+5Fh]; this
0x18002ad53  mov     r9d, eax; char *
0x18002ad56  mov     r8, r14; unsigned int
0x18002ad59  mov     edx, 366h; void *
0x18002ad5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ad64  mov     rcx, [rbp+5Fh]; this
0x18002ad68  mov     r9d, eax; char *
0x18002ad6b  mov     r8, r14; unsigned int
0x18002ad6e  mov     edx, 36Ch; void *
0x18002ad73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ad79  mov     rcx, [rbp+5Fh]; this
0x18002ad7d  mov     r9d, eax; char *
0x18002ad80  mov     r8, r14; unsigned int
0x18002ad83  mov     edx, 370h; void *
0x18002ad88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ad8e  mov     rcx, [rbp+5Fh]; this
0x18002ad92  mov     r9d, eax; char *
0x18002ad95  mov     r8, r14; unsigned int
0x18002ad98  mov     edx, 373h; void *
0x18002ad9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ada3  mov     rcx, [rbp+5Fh]; this
0x18002ada7  mov     r9d, eax; char *
0x18002adaa  mov     r8, r14; unsigned int
0x18002adad  mov     edx, 376h; void *
0x18002adb2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002adb8  mov     rcx, [rbp+5Fh]; this
0x18002adbc  mov     r9d, eax; char *
0x18002adbf  mov     r8, r14; unsigned int
0x18002adc2  mov     edx, 379h; void *
0x18002adc7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002adcd  mov     rcx, [rbp+5Fh]; this
0x18002add1  mov     r9d, eax; char *
0x18002add4  mov     r8, r14; unsigned int
0x18002add7  mov     edx, 381h; void *
0x18002addc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
