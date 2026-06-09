# _dynamic_initializer_for__ActionToDllMapping__

- ea: `0x180001cb0`
- end: `0x180001f22`
- name: `_dynamic_initializer_for__ActionToDllMapping__`
- size: `626`
- prototype: `int()`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cb0`
- `0x1800032e0`
- `0x1800036c8`
- `0x180003be4`
- `0x18000413c`
- `0x18000f944`
- `0x180016b28`
- `0x1800183f8`

## string_xrefs

- `0x180001d17`: `%systemroot%\system32\SettingsHandlers_OneCore_BatterySaver.dll`
- `0x180001d61`: `%systemroot%\system32\SettingsHandlers_OneCore_BatterySaver.dll`
- `0x180001da7`: `%systemroot%\system32\SettingsHandlers_OneCore_BatterySaver.dll`
- `0x180001e36`: `%systemroot%\system32\SettingsHandlers_OneCore_BatterySaver.dll`
- `0x180001def`: `%systemroot%\system32\SettingsHandlers_BatteryUsage.dll`

## pseudocode

```c
int dynamic_initializer_for__ActionToDllMapping__()
{
  _QWORD *v0; // rax
  __int64 v1; // rcx
  __int64 *v2; // rbx
  _BYTE v4[16]; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v5[2]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v6[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v7[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v8[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v9[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v10[2]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v11[2]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v12[2]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v13[2]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v14[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v15; // [rsp+170h] [rbp+70h] BYREF

  memset(v5, 0, sizeof(v5));
  std::wstring::_Construct<1,unsigned short const *>(v5);
  memset(v6, 0, sizeof(v6));
  std::wstring::_Construct<1,unsigned short const *>(v6);
  memset(v7, 0, sizeof(v7));
  std::wstring::_Construct<1,unsigned short const *>(v7);
  memset(v8, 0, sizeof(v8));
  std::wstring::_Construct<1,unsigned short const *>(v8);
  memset(v9, 0, sizeof(v9));
  std::wstring::_Construct<1,unsigned short const *>(v9);
  memset(v10, 0, sizeof(v10));
  std::wstring::_Construct<1,unsigned short const *>(v10);
  memset(v11, 0, sizeof(v11));
  std::wstring::_Construct<1,unsigned short const *>(v11);
  memset(v12, 0, sizeof(v12));
  std::wstring::_Construct<1,unsigned short const *>(v12);
  memset(v13, 0, sizeof(v13));
  std::wstring::_Construct<1,unsigned short const *>(v13);
  memset(v14, 0, sizeof(v14));
  std::wstring::_Construct<1,unsigned short const *>(v14);
  ActionToDllMapping = 0;
  qword_180035148 = 0;
  qword_180035150 = 0;
  v0 = operator new(0x50u);
  *v0 = v0;
  v0[1] = v0;
  qword_180035148 = (__int64)v0;
  qword_180035158 = 0;
  xmmword_180035160 = 0;
  qword_180035170 = 7;
  qword_180035178 = 8;
  ActionToDllMapping = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(
    &qword_180035158,
    16,
    v0);
  v2 = (__int64 *)v5;
  do
  {
    std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring> const &>(
      v1,
      v4,
      v2);
    v2 += 8;
  }
  while ( v2 != &v15 );
  `eh vector destructor iterator'(
    v5,
    0x40u,
    5u,
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>);
  return atexit(dynamic_atexit_destructor_for__ActionToDllMapping__);
}

```

## disassembly

```asm
0x180001cb0  mov     [rsp-8+arg_0], rbx
0x180001cb5  mov     [rsp-8+arg_8], rsi
0x180001cba  push    rbp
0x180001cbb  lea     rbp, [rsp-80h]
0x180001cc0  sub     rsp, 180h
0x180001cc7  mov     rax, cs:__security_cookie
0x180001cce  xor     rax, rsp
0x180001cd1  mov     [rbp+80h+var_10], rax
0x180001cd5  xorps   xmm0, xmm0
0x180001cd8  movups  [rsp+180h+var_150], xmm0
0x180001cdd  xorps   xmm1, xmm1
0x180001ce0  movdqa  [rsp+180h+var_140], xmm1
0x180001ce6  mov     ebx, 27h ; '''
0x180001ceb  mov     r8d, ebx
0x180001cee  lea     rdx, aActionBatterys_1; "action://batterysaver/overrideppmpolicy"
0x180001cf5  lea     rcx, [rsp+180h+var_150]
0x180001cfa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001cff  nop
0x180001d00  xorps   xmm0, xmm0
0x180001d03  movups  [rsp+180h+var_130], xmm0
0x180001d08  xorps   xmm1, xmm1
0x180001d0b  movdqa  [rsp+180h+var_120], xmm1
0x180001d11  lea     esi, [rbx+18h]
0x180001d14  mov     r8d, esi
0x180001d17  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\SettingsHandler"...
0x180001d1e  lea     rcx, [rsp+180h+var_130]
0x180001d23  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001d28  nop
0x180001d29  xorps   xmm0, xmm0
0x180001d2c  movups  [rsp+180h+var_110], xmm0
0x180001d31  xorps   xmm1, xmm1
0x180001d34  movdqa  [rbp+80h+var_100], xmm1
0x180001d39  lea     r8d, [rbx-5]
0x180001d3d  lea     rdx, aActionBatterys; "action://batterysaver/setpowermode"
0x180001d44  lea     rcx, [rsp+180h+var_110]
0x180001d49  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001d4e  nop
0x180001d4f  xorps   xmm0, xmm0
0x180001d52  movups  [rbp+80h+var_F0], xmm0
0x180001d56  xorps   xmm1, xmm1
0x180001d59  movdqa  [rbp+80h+var_E0], xmm1
0x180001d5e  mov     r8d, esi
0x180001d61  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\SettingsHandler"...
0x180001d68  lea     rcx, [rbp+80h+var_F0]
0x180001d6c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001d71  nop
0x180001d72  xorps   xmm0, xmm0
0x180001d75  movups  [rbp+80h+var_D0], xmm0
0x180001d79  xorps   xmm1, xmm1
0x180001d7c  movdqa  [rbp+80h+var_C0], xmm1
0x180001d81  mov     r8d, ebx
0x180001d84  lea     rdx, aActionBatterys_0; "action://batterysaver/toggleenergysaver"
0x180001d8b  lea     rcx, [rbp+80h+var_D0]
0x180001d8f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001d94  nop
0x180001d95  xorps   xmm0, xmm0
0x180001d98  movups  [rbp+80h+var_B0], xmm0
0x180001d9c  xorps   xmm1, xmm1
0x180001d9f  movdqa  [rbp+80h+var_A0], xmm1
0x180001da4  mov     r8d, esi
0x180001da7  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\SettingsHandler"...
0x180001dae  lea     rcx, [rbp+80h+var_B0]
0x180001db2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001db7  nop
0x180001db8  xorps   xmm0, xmm0
0x180001dbb  movups  [rbp+80h+var_90], xmm0
0x180001dbf  xorps   xmm1, xmm1
0x180001dc2  movdqa  [rbp+80h+var_80], xmm1
0x180001dc7  lea     r8d, [rbx+4]
0x180001dcb  lea     rdx, aActionBatteryu; "action://batteryusage/setesbrightnessto"...
0x180001dd2  lea     rcx, [rbp+80h+var_90]
0x180001dd6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001ddb  nop
0x180001ddc  xorps   xmm0, xmm0
0x180001ddf  movups  [rbp+80h+var_70], xmm0
0x180001de3  xorps   xmm1, xmm1
0x180001de6  movdqa  [rbp+80h+var_60], xmm1
0x180001deb  lea     r8d, [rbx+10h]
0x180001def  lea     rdx, aSystemrootSyst_1; "%systemroot%\\system32\\SettingsHandler"...
0x180001df6  lea     rcx, [rbp+80h+var_70]
0x180001dfa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001dff  nop
0x180001e00  xorps   xmm0, xmm0
0x180001e03  movups  [rbp+80h+var_50], xmm0
0x180001e07  xorps   xmm1, xmm1
0x180001e0a  movdqa  [rbp+80h+var_40], xmm1
0x180001e0f  lea     r8d, [rbx-0Ch]
0x180001e13  lea     rdx, aActionEcpToggl; "action://ecp/toggleadaptive"
0x180001e1a  lea     rcx, [rbp+80h+var_50]
0x180001e1e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001e23  nop
0x180001e24  xorps   xmm0, xmm0
0x180001e27  movups  [rbp+80h+var_30], xmm0
0x180001e2b  xorps   xmm1, xmm1
0x180001e2e  movdqa  [rbp+80h+var_20], xmm1
0x180001e33  mov     r8d, esi
0x180001e36  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\SettingsHandler"...
0x180001e3d  lea     rcx, [rbp+80h+var_30]
0x180001e41  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180001e46  nop
0x180001e47  mov     cs:?ActionToDllMapping@@3V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@B, 0; std::unordered_map<std::wstring,std::wstring> const ActionToDllMapping
0x180001e51  xor     ebx, ebx
0x180001e53  mov     cs:qword_180035148, rbx
0x180001e5a  mov     cs:qword_180035150, rbx
0x180001e61  lea     ecx, [rsi+11h]; Size
0x180001e64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e69  mov     [rax], rax
0x180001e6c  mov     [rax+8], rax
0x180001e70  mov     cs:qword_180035148, rax
0x180001e77  mov     cs:qword_180035158, rbx
0x180001e7e  xorps   xmm0, xmm0
0x180001e81  movdqa  cs:xmmword_180035160, xmm0
0x180001e89  mov     cs:qword_180035170, 7
0x180001e94  mov     cs:qword_180035178, 8
0x180001e9f  mov     cs:?ActionToDllMapping@@3V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@B, 3F800000h; std::unordered_map<std::wstring,std::wstring> const ActionToDllMapping
0x180001ea9  mov     r8, rax
0x180001eac  lea     edx, [rsi-2Fh]
0x180001eaf  lea     rcx, qword_180035158
0x180001eb6  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>)
0x180001ebb  nop
0x180001ebc  lea     rbx, [rsp+180h+var_150]
0x180001ec1  mov     r8, rbx
0x180001ec4  lea     rdx, [rsp+180h+var_160]
0x180001ec9  call    ??$emplace@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring> const &>(std::pair<std::wstring const,std::wstring> const &)
0x180001ece  add     rbx, 40h ; '@'
0x180001ed2  lea     rax, [rbp+80h+var_10]
0x180001ed6  cmp     rbx, rax
0x180001ed9  jnz     short loc_180001EC1
0x180001edb  lea     r9, ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; void (*)(void *)
0x180001ee2  mov     edx, 40h ; '@'; unsigned __int64
0x180001ee7  lea     r8d, [rdx-3Bh]; unsigned __int64
0x180001eeb  lea     rcx, [rsp+180h+var_150]; void *
0x180001ef0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180001ef5  lea     rcx, _dynamic_atexit_destructor_for__ActionToDllMapping__; void (__cdecl *)()
0x180001efc  call    atexit
0x180001f01  mov     rcx, [rbp+80h+var_10]
0x180001f05  xor     rcx, rsp; StackCookie
0x180001f08  call    __security_check_cookie
0x180001f0d  lea     r11, [rsp+180h+var_s0]
0x180001f15  mov     rbx, [r11+10h]
0x180001f19  mov     rsi, [r11+18h]
0x180001f1d  mov     rsp, r11
0x180001f20  pop     rbp
0x180001f21  retn
```
