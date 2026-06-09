# ClientState::SaveCnsRegData(HKEY__ *,bool)

- ea: `0x18002a36c`
- end: `0x18002a8c1`
- name: `?SaveCnsRegData@ClientState@@AEAAXPEAUHKEY__@@_N@Z`
- size: `1365`
- prototype: `void(ClientState *__hidden this, HKEY, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a8c8`

## callees

- `0x18000847c`
- `0x18000a230`
- `0x1800101fc`
- `0x180019e18`
- `0x180019e68`
- `0x18001a718`
- `0x180021f60`
- `0x1800245a8`
- `0x180026d90`
- `0x180027234`
- `0x1800272bc`
- `0x180028bb4`
- `0x18002a36c`
- `0x18002b140`
- `0x18002b7bc`
- `0x18002bd0c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a441`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a72a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a441`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a72a`

## string_xrefs

- `0x18002a3b9`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a7e1`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a7f6`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a80b`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a820`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a834`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a848`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a85c`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a870`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a885`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a89a`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a8af`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x18002a748`: `CnsLastUpdateTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ClientState::SaveCnsRegData(ClientState *this, HKEY a2, char a3)
{
  _DWORD *v5; // rdi
  char v6; // al
  unsigned int v7; // r8d
  int v8; // eax
  char v9; // r15
  __int64 v10; // rax
  __int64 v11; // r12
  const unsigned __int16 ***v12; // rsi
  __int64 v13; // rbx
  const unsigned __int16 **v14; // r14
  __int64 v15; // r13
  __int64 v16; // rax
  bool v17; // r14
  const unsigned __int16 *v18; // rdx
  int v19; // eax
  const unsigned __int16 *v20; // rax
  unsigned int v21; // r8d
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rcx
  const unsigned __int16 *v29; // rdx
  int v30; // eax
  LPFILETIME *v31; // rbx
  int v32; // eax
  int v33; // eax
  __int64 *v34; // rbp
  HKEY v35; // rax
  const unsigned __int16 *v36; // rdx
  unsigned int v37; // eax
  __int64 v38; // rdx
  int v39; // eax
  void *v40; // rdx
  unsigned int v41; // r8d
  const char *v42; // r9
  __int64 *v43; // rdx
  int v44; // [rsp+20h] [rbp-A8h]
  __int64 v45; // [rsp+0h] [rbp-C8h] BYREF
  unsigned __int64 v46; // [rsp+20h] [rbp-A8h]
  HKEY v47; // [rsp+40h] [rbp-88h] BYREF
  HKEY v48; // [rsp+48h] [rbp-80h] BYREF
  const unsigned __int16 *v49; // [rsp+50h] [rbp-78h] BYREF
  __int64 i; // [rsp+58h] [rbp-70h] BYREF
  LPFILETIME lpSystemTimeAsFileTime; // [rsp+60h] [rbp-68h] BYREF
  _QWORD v52[2]; // [rsp+68h] [rbp-60h] BYREF
  _QWORD v53[10]; // [rsp+78h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  unsigned int v57; // [rsp+E8h] [rbp+20h] BYREF

  v5 = (_DWORD *)((char *)this + 492);
  if ( !a3 || (v6 = 1, *v5 != -1) )
    v6 = 0;
  if ( v6 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x665,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)0x8000FFFFLL,
      v46);
    return;
  }
  if ( a3 || *v5 == 1 )
  {
    v47 = 0;
    v57 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v47,
      0);
    v8 = RegWow64Helpers::CreateKey(a2, L"CNS", v7, 0xF003Fu, (struct _SECURITY_ATTRIBUTES *const)v46, &v47, &v57);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66D,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)(unsigned int)v8,
        v46);
    lpSystemTimeAsFileTime = (LPFILETIME)((char *)this + 476);
    GetSystemTimeAsFileTime((LPFILETIME)((char *)this + 476));
    ClientState::LoadCnsFlightStateMap(v52, v47);
    v9 = 0;
    v10 = **((_QWORD **)this + 62);
    for ( i = v10; ; v10 = i )
    {
      if ( *(_BYTE *)(v10 + 25) )
      {
        v28 = *(_QWORD *)v52[0];
        i = *(_QWORD *)v52[0];
        while ( !*(_BYTE *)(v28 + 25) )
        {
          v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28 + 32);
          v30 = RegWow64Helpers::DeleteTree(v47, v29);
          if ( v30 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6AC,
              (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
              (const char *)(unsigned int)v30,
              v46);
          v9 = 1;
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&i);
          v28 = i;
        }
        if ( v9 || a3 )
        {
          v31 = (LPFILETIME *)lpSystemTimeAsFileTime;
          GetSystemTimeAsFileTime(lpSystemTimeAsFileTime);
          lpSystemTimeAsFileTime = *v31;
          v32 = RegValet::SetValue::_Set(v47, L"CnsLastUpdateTime", 0xBu, &lpSystemTimeAsFileTime, 8u);
          if ( v32 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x6B5,
              (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
              (const char *)(unsigned int)v32,
              v46);
        }
        *v5 = 0;
        lpSystemTimeAsFileTime = *(LPFILETIME *)((char *)this + 484);
        v33 = RegValet::SetValue::_Set(v47, L"CnsLastMergeTime", 0xBu, &lpSystemTimeAsFileTime, 8u);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6BC,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
            (const char *)(unsigned int)v33,
            v46);
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
          v52,
          v52);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v47);
        return;
      }
      v11 = v10 + 32;
      v48 = 0;
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<CnsFlightState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>,0>>::find(
        v52,
        v53,
        v10 + 32);
      v12 = (const unsigned __int16 ***)(v11 + 32);
      v13 = v53[0];
      if ( v53[0] != v52[0] )
      {
        v14 = *v12;
        v15 = *(_QWORD *)(v53[0] + 64LL);
        v17 = 0;
        if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
                             v15,
                             *v12) == 2
          && *(_DWORD *)(v15 + 24) == *((_DWORD *)v14 + 6)
          && (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
                             v15 + 40,
                             v14 + 5) == 2 )
        {
          v16 = *(_QWORD *)(v13 + 64);
          if ( *(_DWORD *)(v16 + 68) || *(_DWORD *)(v16 + 64) || !*((_DWORD *)*v12 + 17) && !*((_DWORD *)*v12 + 16) )
            v17 = 1;
        }
        std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<CnsFlightState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>,0>>::_Erase_unchecked(
          v52,
          v13);
        if ( v17 )
          goto LABEL_30;
        v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
        v19 = RegWow64Helpers::DeleteTree(v47, v18);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x685,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
            (const char *)(unsigned int)v19,
            v46);
      }
      v53[1] = v11;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v48,
        0);
      v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
      v22 = RegWow64Helpers::CreateKey(v47, v20, v21, 0x20006u, (struct _SECURITY_ATTRIBUTES *const)v46, &v48, 0);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x689,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
          (const char *)(unsigned int)v22,
          v46);
      v23 = RegValet::SetValue::String(v48, L"CnsFlightVersion", **v12);
      if ( v23 < 0 )
      {
        try
        {
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x690,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
            (const char *)(unsigned int)v23,
            v46);
        }
        catch ( ... )
        {
          v43 = &v45;
          v34 = v43;
          std::wstring::c_str(v43[16]);
          v35 = (HKEY)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::get(v34 + 8);
          v37 = RegWow64Helpers::DeleteTree(v35, v36);
          v39 = wil::verify_hresult<long>(v37, v38);
          if ( v39 < 0 )
            wil::details::in1diag3::_Log_Hr(
              (wil::details::in1diag3 *)v34[25],
              (void *)0x6A1,
              (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
              (const char *)(unsigned int)v39,
              v44);
          wil::details::in1diag3::Throw_CaughtException((wil::details::in1diag3 *)v34[25], v40, v41, v42);
        }
      }
      v49 = *(const unsigned __int16 **)((char *)*v12 + 28);
      v24 = RegValet::SetValue::_Set(v48, L"CnsReceiptTime", 0xBu, &v49, 8u);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x693,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
          (const char *)(unsigned int)v24,
          v46);
      LODWORD(v49) = *((_DWORD *)*v12 + 6);
      v25 = RegValet::SetValue::_Set(v48, L"CnsWnsChangeStamp", 4u, &v49, 4u);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x696,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
          (const char *)(unsigned int)v25,
          v46);
      v26 = RegValet::SetValue::String(v48, L"CnsPayloadFileName", (*v12)[5]);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x699,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
          (const char *)(unsigned int)v26,
          v46);
      v49 = (*v12)[8];
      v27 = RegValet::SetValue::_Set(v48, L"CnsAcknowledgedTime", 0xBu, &v49, 8u);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x69C,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
          (const char *)(unsigned int)v27,
          v46);
      v9 = 1;
LABEL_30:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v48);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&i);
    }
  }
}

```

## disassembly

```asm
0x18002a36c  mov     [rsp+arg_10], r8b
0x18002a371  mov     [rsp+arg_0], rcx
0x18002a376  push    rbx
0x18002a377  push    rsi
0x18002a378  push    rdi
0x18002a379  push    r12
0x18002a37b  push    r13
0x18002a37d  push    r14
0x18002a37f  push    r15
0x18002a381  sub     rsp, 90h
0x18002a388  mov     rbx, rdx
0x18002a38b  mov     r14, rcx
0x18002a38e  lea     rdi, [rcx+1ECh]
0x18002a395  xor     r13d, r13d
0x18002a398  test    r8b, r8b
0x18002a39b  jz      short loc_18002A3A4
0x18002a39d  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18002a3a0  mov     al, 1
0x18002a3a2  jz      short loc_18002A3A7
0x18002a3a4  mov     al, r13b
0x18002a3a7  mov     rcx, [rsp+0C8h]; this
0x18002a3af  test    al, al
0x18002a3b1  jz      short loc_18002A3CF
0x18002a3b3  mov     r9d, 8000FFFFh; char *
0x18002a3b9  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a3c0  mov     edx, 665h; void *
0x18002a3c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002a3ca  jmp     loc_18002A7CB
0x18002a3cf  test    r8b, r8b
0x18002a3d2  jnz     short loc_18002A3DD
0x18002a3d4  cmp     dword ptr [rdi], 1
0x18002a3d7  jnz     loc_18002A7CB
0x18002a3dd  mov     [rsp+0C8h+var_88], r13
0x18002a3e2  mov     [rsp+0C8h+arg_18], r13d
0x18002a3ea  xor     edx, edx
0x18002a3ec  lea     rcx, [rsp+0C8h+var_88]
0x18002a3f1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a3f6  lea     rax, [rsp+0C8h+arg_18]
0x18002a3fe  mov     [rsp+0C8h+var_98], rax; unsigned int *
0x18002a403  lea     rax, [rsp+0C8h+var_88]
0x18002a408  mov     [rsp+0C8h+var_A0], rax; HKEY *
0x18002a40d  mov     r9d, 0F003Fh; unsigned int
0x18002a413  lea     rdx, ?c_regkeyCns@ClientState@@0QBGB; "CNS"
0x18002a41a  mov     rcx, rbx; HKEY
0x18002a41d  call    ?CreateKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; RegWow64Helpers::CreateKey(HKEY__ * const,ushort const * const,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x18002a422  mov     rcx, [rsp+0C8h]; this
0x18002a42a  test    eax, eax
0x18002a42c  js      loc_18002A7DE
0x18002a432  lea     rbx, [r14+1DCh]
0x18002a439  mov     [rsp+0C8h+lpSystemTimeAsFileTime], rbx
0x18002a43e  mov     rcx, rbx; lpSystemTimeAsFileTime
0x18002a441  call    cs:__imp_GetSystemTimeAsFileTime
0x18002a447  mov     rdx, [rsp+0C8h+var_88]
0x18002a44c  lea     rcx, [rsp+0C8h+var_60]
0x18002a451  call    ?LoadCnsFlightStateMap@ClientState@@CA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@@std@@PEAUHKEY__@@@Z; ClientState::LoadCnsFlightStateMap(HKEY__ *)
0x18002a456  nop
0x18002a457  mov     r15b, r13b
0x18002a45a  mov     rax, [r14+1F0h]
0x18002a461  mov     rax, [rax]
0x18002a464  mov     [rsp+0C8h+var_70], rax
0x18002a469  mov     r14d, 8
0x18002a46f  cmp     [rax+19h], r13b
0x18002a473  jnz     loc_18002A6C6
0x18002a479  lea     r12, [rax+20h]
0x18002a47d  mov     [rsp+0C8h+var_80], r13
0x18002a482  mov     r8, r12
0x18002a485  lea     rdx, [rsp+0C8h+var_50]
0x18002a48a  lea     rcx, [rsp+0C8h+var_60]
0x18002a48f  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<CnsFlightState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>,0>>::find(std::wstring const &)
0x18002a494  lea     rsi, [r12+20h]
0x18002a499  mov     rbx, [rsp+0C8h+var_50]
0x18002a49e  cmp     rbx, [rsp+0C8h+var_60]
0x18002a4a3  jz      loc_18002A551
0x18002a4a9  mov     r14, [rsi]
0x18002a4ac  mov     r13, [rbx+40h]
0x18002a4b0  mov     rdx, r14
0x18002a4b3  mov     rcx, r13
0x18002a4b6  call    ?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18002a4bb  cmp     eax, 2
0x18002a4be  jnz     short loc_18002A503
0x18002a4c0  mov     eax, [r14+18h]
0x18002a4c4  cmp     [r13+18h], eax
0x18002a4c8  jnz     short loc_18002A503
0x18002a4ca  lea     rdx, [r14+28h]
0x18002a4ce  lea     rcx, [r13+28h]
0x18002a4d2  call    ?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18002a4d7  xor     r13d, r13d
0x18002a4da  cmp     eax, 2
0x18002a4dd  jnz     short loc_18002A506
0x18002a4df  mov     rax, [rbx+40h]
0x18002a4e3  cmp     [rax+44h], r13d
0x18002a4e7  jnz     short loc_18002A4FE
0x18002a4e9  cmp     [rax+40h], r13d
0x18002a4ed  jnz     short loc_18002A4FE
0x18002a4ef  mov     rax, [rsi]
0x18002a4f2  cmp     [rax+44h], r13d
0x18002a4f6  jnz     short loc_18002A506
0x18002a4f8  cmp     [rax+40h], r13d
0x18002a4fc  jnz     short loc_18002A506
0x18002a4fe  mov     r14b, 1
0x18002a501  jmp     short loc_18002A509
0x18002a503  xor     r13d, r13d
0x18002a506  mov     r14b, r13b
0x18002a509  mov     rdx, rbx
0x18002a50c  lea     rcx, [rsp+0C8h+var_60]
0x18002a511  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<CnsFlightState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>)
0x18002a516  test    r14b, r14b
0x18002a519  jz      short loc_18002A526
0x18002a51b  mov     r14d, 8
0x18002a521  jmp     loc_18002A6A8
0x18002a526  mov     rcx, r12
0x18002a529  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a52e  mov     rdx, rax; unsigned __int16 *
0x18002a531  mov     rcx, [rsp+0C8h+var_88]; HKEY
0x18002a536  call    ?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)
0x18002a53b  mov     rcx, [rsp+0C8h]; this
0x18002a543  test    eax, eax
0x18002a545  js      loc_18002A7F3
0x18002a54b  mov     r14d, 8
0x18002a551  mov     [rsp+0C8h+var_48], r12
0x18002a559  xor     edx, edx
0x18002a55b  lea     rcx, [rsp+0C8h+var_80]
0x18002a560  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a565  mov     rcx, r12
0x18002a568  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a56d  mov     [rsp+0C8h+var_98], r13; unsigned int *
0x18002a572  lea     rcx, [rsp+0C8h+var_80]
0x18002a577  mov     [rsp+0C8h+var_A0], rcx; HKEY *
0x18002a57c  mov     r9d, 20006h; unsigned int
0x18002a582  mov     rdx, rax; unsigned __int16 *
0x18002a585  mov     rcx, [rsp+0C8h+var_88]; HKEY
0x18002a58a  call    ?CreateKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; RegWow64Helpers::CreateKey(HKEY__ * const,ushort const * const,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x18002a58f  mov     rcx, [rsp+0C8h]; this
0x18002a597  test    eax, eax
0x18002a599  js      loc_18002A808
0x18002a59f  mov     r8, [rsi]
0x18002a5a2  mov     r8, [r8]; unsigned __int16 *
0x18002a5a5  lea     rdx, ?c_regvalCnsFlightVersion@ClientState@@0QBGB; "CnsFlightVersion"
0x18002a5ac  mov     rcx, [rsp+0C8h+var_80]; HKEY
0x18002a5b1  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x18002a5b6  mov     rcx, [rsp+0C8h]; this
0x18002a5be  test    eax, eax
0x18002a5c0  js      loc_18002A81D
0x18002a5c6  mov     rax, [rsi]
0x18002a5c9  mov     rdx, [rax+1Ch]
0x18002a5cd  mov     [rsp+0C8h+var_78], rdx
0x18002a5d2  mov     [rsp+0C8h+var_A8], r14; int
0x18002a5d7  lea     r9, [rsp+0C8h+var_78]; void *
0x18002a5dc  mov     r8d, 0Bh; unsigned int
0x18002a5e2  lea     rdx, ?c_regvalCnsReceiptTime@ClientState@@0QBGB; "CnsReceiptTime"
0x18002a5e9  mov     rcx, [rsp+0C8h+var_80]; HKEY
0x18002a5ee  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002a5f3  mov     rcx, [rsp+0C8h]; this
0x18002a5fb  test    eax, eax
0x18002a5fd  js      loc_18002A831
0x18002a603  mov     rax, [rsi]
0x18002a606  mov     edx, [rax+18h]
0x18002a609  mov     dword ptr [rsp+0C8h+var_78], edx
0x18002a60d  mov     ebx, 4
0x18002a612  mov     [rsp+0C8h+var_A8], rbx; int
0x18002a617  lea     r9, [rsp+0C8h+var_78]; void *
0x18002a61c  mov     r8d, ebx; unsigned int
0x18002a61f  lea     rdx, ?c_regvalCnsWnsChangeStamp@ClientState@@0QBGB; "CnsWnsChangeStamp"
0x18002a626  mov     rcx, [rsp+0C8h+var_80]; HKEY
0x18002a62b  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002a630  mov     rcx, [rsp+0C8h]; this
0x18002a638  test    eax, eax
0x18002a63a  js      loc_18002A845
0x18002a640  mov     r8, [rsi]
0x18002a643  mov     r8, [r8+28h]; unsigned __int16 *
0x18002a647  lea     rdx, ?c_regvalCnsPayloadFileName@ClientState@@0QBGB; "CnsPayloadFileName"
0x18002a64e  mov     rcx, [rsp+0C8h+var_80]; HKEY
0x18002a653  call    ?String@SetValue@RegValet@@SAJPEAUHKEY__@@PEBG1@Z; RegValet::SetValue::String(HKEY__ *,ushort const *,ushort const *)
0x18002a658  mov     rcx, [rsp+0C8h]; this
0x18002a660  test    eax, eax
0x18002a662  js      loc_18002A859
0x18002a668  mov     rax, [rsi]
0x18002a66b  mov     rdx, [rax+40h]
0x18002a66f  mov     [rsp+0C8h+var_78], rdx
0x18002a674  mov     [rsp+0C8h+var_A8], r14; int
0x18002a679  lea     r9, [rsp+0C8h+var_78]; void *
0x18002a67e  mov     r8d, 0Bh; unsigned int
0x18002a684  lea     rdx, ?c_regvalCnsAcknowledgedTime@ClientState@@0QBGB; "CnsAcknowledgedTime"
0x18002a68b  mov     rcx, [rsp+0C8h+var_80]; HKEY
0x18002a690  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002a695  mov     rcx, [rsp+0C8h]; this
0x18002a69d  test    eax, eax
0x18002a69f  js      loc_18002A86D
0x18002a6a5  mov     r15b, 1
0x18002a6a8  lea     rcx, [rsp+0C8h+var_80]
0x18002a6ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a6b2  lea     rcx, [rsp+0C8h+var_70]
0x18002a6b7  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x18002a6bc  mov     rax, [rsp+0C8h+var_70]
0x18002a6c1  jmp     loc_18002A46F
0x18002a6c6  mov     rcx, [rsp+0C8h+var_60]
0x18002a6cb  mov     rcx, [rcx]
0x18002a6ce  mov     [rsp+0C8h+var_70], rcx
0x18002a6d3  cmp     [rcx+19h], r13b
0x18002a6d7  jnz     short loc_18002A713
0x18002a6d9  add     rcx, 20h ; ' '
0x18002a6dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a6e2  mov     rdx, rax; unsigned __int16 *
0x18002a6e5  mov     rcx, [rsp+0C8h+var_88]; HKEY
0x18002a6ea  call    ?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)
0x18002a6ef  mov     rcx, [rsp+0C8h]; this
0x18002a6f7  test    eax, eax
0x18002a6f9  js      loc_18002A882
0x18002a6ff  mov     r15b, 1
0x18002a702  lea     rcx, [rsp+0C8h+var_70]
0x18002a707  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x18002a70c  mov     rcx, [rsp+0C8h+var_70]
0x18002a711  jmp     short loc_18002A6D3
0x18002a713  test    r15b, r15b
0x18002a716  jnz     short loc_18002A722
0x18002a718  cmp     [rsp+0C8h+arg_10], r13b
0x18002a720  jz      short loc_18002A769
0x18002a722  mov     rbx, [rsp+0C8h+lpSystemTimeAsFileTime]
0x18002a727  mov     rcx, rbx; lpSystemTimeAsFileTime
0x18002a72a  call    cs:__imp_GetSystemTimeAsFileTime
0x18002a730  mov     rax, [rbx]
0x18002a733  mov     [rsp+0C8h+lpSystemTimeAsFileTime], rax
0x18002a738  mov     [rsp+0C8h+var_A8], r14; int
0x18002a73d  lea     r9, [rsp+0C8h+lpSystemTimeAsFileTime]; void *
0x18002a742  mov     r8d, 0Bh; unsigned int
0x18002a748  lea     rdx, ?c_regvalCnsLastUpdateTime@ClientState@@0QBGB; "CnsLastUpdateTime"
0x18002a74f  mov     rcx, [rsp+0C8h+var_88]; HKEY
0x18002a754  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002a759  mov     rcx, [rsp+0C8h]; this
0x18002a761  test    eax, eax
0x18002a763  js      loc_18002A897
0x18002a769  mov     [rdi], r13d
0x18002a76c  mov     rax, [rsp+0C8h+arg_0]
0x18002a774  mov     rax, [rax+1E4h]
0x18002a77b  mov     [rsp+0C8h+lpSystemTimeAsFileTime], rax
0x18002a780  mov     [rsp+0C8h+var_A8], r14; int
0x18002a785  lea     r9, [rsp+0C8h+lpSystemTimeAsFileTime]; void *
0x18002a78a  mov     r8d, 0Bh; unsigned int
0x18002a790  lea     rdx, ?c_regvalCnsLastMergeTime@ClientState@@0QBGB; "CnsLastMergeTime"
0x18002a797  mov     rcx, [rsp+0C8h+var_88]; HKEY
0x18002a79c  call    ?_Set@SetValue@RegValet@@CAJPEAUHKEY__@@PEBGKPEBX_K@Z; RegValet::SetValue::_Set(HKEY__ *,ushort const *,ulong,void const *,unsigned __int64)
0x18002a7a1  mov     rcx, [rsp+0C8h]; this
0x18002a7a9  test    eax, eax
0x18002a7ab  js      loc_18002A8AC
0x18002a7b1  lea     rdx, [rsp+0C8h+var_60]
0x18002a7b6  lea     rcx, [rsp+0C8h+var_60]
0x18002a7bb  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>> &)
0x18002a7c0  nop
0x18002a7c1  lea     rcx, [rsp+0C8h+var_88]
0x18002a7c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a7cb  add     rsp, 90h
0x18002a7d2  pop     r15
0x18002a7d4  pop     r14
0x18002a7d6  pop     r13
0x18002a7d8  pop     r12
0x18002a7da  pop     rdi
0x18002a7db  pop     rsi
0x18002a7dc  pop     rbx
0x18002a7dd  retn
0x18002a7de  mov     r9d, eax; char *
0x18002a7e1  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a7e8  mov     edx, 66Dh; void *
0x18002a7ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a7f3  mov     r9d, eax; char *
0x18002a7f6  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a7fd  mov     edx, 685h; void *
0x18002a802  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a808  mov     r9d, eax; char *
0x18002a80b  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a812  mov     edx, 689h; void *
0x18002a817  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a81d  mov     r9d, eax; char *
0x18002a820  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a827  mov     edx, 690h; void *
0x18002a82c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a831  mov     r9d, eax; char *
0x18002a834  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a83b  mov     edx, 693h; void *
0x18002a840  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a845  mov     r9d, eax; char *
0x18002a848  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a84f  mov     edx, 696h; void *
0x18002a854  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a859  mov     r9d, eax; char *
0x18002a85c  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a863  mov     edx, 699h; void *
0x18002a868  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a86d  mov     r9d, eax; char *
0x18002a870  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a877  mov     edx, 69Ch; void *
0x18002a87c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a882  mov     r9d, eax; char *
0x18002a885  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a88c  mov     edx, 6ACh; void *
0x18002a891  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a897  mov     r9d, eax; char *
0x18002a89a  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x18002a8a1  mov     edx, 6B5h; void *
0x18002a8a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002a8ac  mov     r9d, eax; char *
  ... truncated ...
```
