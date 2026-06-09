# ClientState::GetAllSavedClientStates(void)

- ea: `0x1800276c4`
- end: `0x1800279ed`
- name: `?GetAllSavedClientStates@ClientState@@SA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@@2@@std@@XZ`
- size: `809`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023e60`

## callees

- `0x180003110`
- `0x180003210`
- `0x180003c88`
- `0x18000a194`
- `0x18000a230`
- `0x18000fe24`
- `0x1800101fc`
- `0x180010278`
- `0x180014928`
- `0x180019e68`
- `0x180019efc`
- `0x18001a718`
- `0x180020f78`
- `0x180021208`
- `0x1800212e4`
- `0x180021f1c`
- `0x1800256bc`
- `0x180025bc4`
- `0x1800276c4`
- `0x1800288dc`
- `0x18002b620`
- `0x18002be20`
- `0x18004f4dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180027982`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180027982`

## string_xrefs

- `0x1800279c6`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`
- `0x1800279db`: `onecore\base\flighting\onesettings\libs\configurationsmanager\clientstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall ClientState::GetAllSavedClientStates(_QWORD *a1)
{
  RegPersistedKey *v2; // rbx
  const unsigned __int16 *v3; // rdx
  unsigned int v4; // r8d
  int v5; // eax
  int v6; // r12d
  _QWORD *v7; // rbx
  DWORD v8; // r15d
  DWORD i; // edx
  __int64 v10; // rbx
  __int64 v11; // rcx
  unsigned __int16 *v12; // rdi
  _DWORD *v13; // rsi
  _QWORD *v14; // rax
  std::_Ref_count_base *v15; // rcx
  unsigned __int16 *v16; // rax
  ClientState *v17; // r9
  ClientState *v18; // rbx
  _DWORD *v19; // rax
  _QWORD *v20; // rax
  unsigned int v21; // eax
  struct _SECURITY_ATTRIBUTES *lpReserved; // [rsp+20h] [rbp-E0h]
  int lpReserveda; // [rsp+20h] [rbp-E0h]
  unsigned int lpReservedb; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-B0h] BYREF
  ClientState *v30; // [rsp+58h] [rbp-A8h] BYREF
  char *v31; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v32; // [rsp+68h] [rbp-98h]
  ClientState *v33; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v34; // [rsp+78h] [rbp-88h]
  _QWORD *v35; // [rsp+80h] [rbp-80h]
  _DWORD *v36; // [rsp+88h] [rbp-78h]
  void *v37; // [rsp+90h] [rbp-70h]
  _BYTE v38[16]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h]
  _BYTE v40[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v41[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[32]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Name[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v35 = a1;
  v27 = 0;
  hKey = 0;
  v29 = 0;
  v2 = RegPersistedKeySingleton::KeyOneSettingsClient();
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v5 = RegPersistedKey::RegCreateKeyExW(v2, v3, v4, 0x20019u, lpReserved, &hKey, &v29);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
      (const char *)(unsigned int)v5,
      lpReserveda);
  *a1 = 0;
  a1[1] = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientState>>>,0>>::_Alloc_sentinel_and_proxy(a1);
  v6 = 1;
  v27 = 1;
  v7 = (_QWORD *)*a1;
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientState>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientState>>,void *>>>(
    a1,
    a1,
    *(_QWORD *)(*a1 + 8LL));
  v7[1] = v7;
  *v7 = v7;
  v7[2] = v7;
  a1[1] = 0;
  v8 = 0;
  memset_0(Name, 0, 0x208u);
  for ( i = 0; ; i = v8 )
  {
    cchName = 260;
    v21 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    if ( v21 == 259 )
      break;
    if ( v21 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\clientstate.cpp",
        (const char *)v21,
        lpReservedb);
    std::wstring::wstring((__int64)v42, (__int64)Name);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscStateMapDoubleFree>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WoscStateMapDoubleFree>::GetImpl'::`2'::impl) )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Find_lower_bound<std::wstring>(
        a1,
        v38,
        v42);
      v10 = v39;
      if ( (unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
                              v11,
                              v39,
                              v42)
        && v10 != *a1 )
      {
        goto LABEL_11;
      }
      v12 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
      v13 = operator new(0x210u);
      v36 = v13;
      *(_OWORD *)v13 = 0;
      v13[2] = 1;
      v13[3] = 1;
      *(_QWORD *)v13 = &std::_Ref_count_obj2<ClientState>::`vftable';
      ClientState::ClientState((ClientState *)(v13 + 4), v12, 0);
      v6 |= 2u;
      v27 = v6;
      v31 = (char *)(v13 + 4);
      v32 = (std::_Ref_count_base *)v13;
      v14 = (_QWORD *)std::map<std::wstring,std::shared_ptr<ClientState>>::_Try_emplace<std::wstring const &,>(
                        a1,
                        v40,
                        v42);
      std::shared_ptr<CnsFlightState>::operator=(*v14 + 64LL, &v31);
      v15 = v32;
    }
    else
    {
      v37 = operator new(0x200u);
      v16 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
      v18 = ClientState::ClientState(v17, v16, 0);
      v30 = v18;
      v19 = operator new(0x18u);
      *(_OWORD *)v19 = 0;
      v19[2] = 1;
      v19[3] = 1;
      *(_QWORD *)v19 = &std::_Ref_count<ClientState>::`vftable';
      *((_QWORD *)v19 + 2) = v18;
      v33 = v18;
      v34 = (std::_Ref_count_base *)v19;
      v30 = 0;
      std::_Temporary_owner<ClientState>::~_Temporary_owner<ClientState>(&v30);
      v20 = (_QWORD *)std::map<std::wstring,std::shared_ptr<ClientState>>::_Try_emplace<std::wstring const &,>(
                        a1,
                        v41,
                        v42);
      std::shared_ptr<CnsFlightState>::operator=(*v20 + 64LL, &v33);
      v15 = v34;
    }
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
LABEL_11:
    std::wstring::_Tidy_deallocate(v42);
    ++v8;
    memset_0(Name, 0, 0x208u);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a1;
}

```

## disassembly

```asm
0x1800276c4  push    rbp
0x1800276c6  push    rbx
0x1800276c7  push    rsi
0x1800276c8  push    rdi
0x1800276c9  push    r12
0x1800276cb  push    r13
0x1800276cd  push    r14
0x1800276cf  push    r15
0x1800276d1  lea     rbp, [rsp-218h]
0x1800276d9  sub     rsp, 318h
0x1800276e0  mov     rax, cs:__security_cookie
0x1800276e7  xor     rax, rsp
0x1800276ea  mov     [rbp+250h+var_50], rax
0x1800276f1  mov     r14, rcx
0x1800276f4  mov     [rbp+250h+var_2D0], rcx
0x1800276f8  xor     r13d, r13d
0x1800276fb  mov     [rsp+350h+var_30C], r13d
0x180027700  mov     [rsp+350h+hKey], r13
0x180027705  mov     [rsp+350h+var_300], r13d
0x18002770a  call    ?KeyOneSettingsClient@RegPersistedKeySingleton@@SAAEAVRegPersistedKey@@XZ; RegPersistedKeySingleton::KeyOneSettingsClient(void)
0x18002770f  mov     rbx, rax
0x180027712  xor     edx, edx
0x180027714  lea     rcx, [rsp+350h+hKey]
0x180027719  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002771e  lea     rax, [rsp+350h+var_300]
0x180027723  mov     [rsp+350h+lpcchClass], rax; unsigned int *
0x180027728  lea     rax, [rsp+350h+hKey]
0x18002772d  mov     [rsp+350h+lpClass], rax; HKEY *
0x180027732  mov     r9d, 20019h; unsigned int
0x180027738  mov     rcx, rbx; this
0x18002773b  call    ?RegCreateKeyExW@RegPersistedKey@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAUHKEY__@@PEAK@Z; RegPersistedKey::RegCreateKeyExW(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180027740  mov     rcx, [rbp+258h]; this
0x180027747  test    eax, eax
0x180027749  js      loc_1800279C3
0x18002774f  mov     [r14], r13
0x180027752  mov     [r14+8], r13
0x180027756  mov     rcx, r14
0x180027759  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientState>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002775e  lea     r12d, [r13+1]
0x180027762  mov     [rsp+350h+var_30C], r12d
0x180027767  mov     rbx, [r14]
0x18002776a  mov     r8, [rbx+8]
0x18002776e  mov     rdx, r14
0x180027771  mov     rcx, r14
0x180027774  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientState>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientState>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientState>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientState>>,void *> *)
0x180027779  mov     [rbx+8], rbx
0x18002777d  mov     [rbx], rbx
0x180027780  mov     [rbx+10h], rbx
0x180027784  mov     [r14+8], r13
0x180027788  mov     r15d, r13d
0x18002778b  xor     edx, edx; Val
0x18002778d  mov     r8d, 208h; Size
0x180027793  lea     rcx, [rbp+250h+Name]; void *
0x180027797  call    memset_0
0x18002779c  xor     edx, edx
0x18002779e  jmp     loc_180027958
0x1800277a3  mov     rcx, [rbp+258h]; this
0x1800277aa  test    eax, eax
0x1800277ac  jnz     loc_1800279D8
0x1800277b2  lea     rdx, [rbp+250h+Name]
0x1800277b6  lea     rcx, [rbp+250h+var_280]
0x1800277ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800277bf  nop
0x1800277c0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WoscStateMapDoubleFree@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WoscStateMapDoubleFree@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscStateMapDoubleFree> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WoscStateMapDoubleFree>::GetImpl(void)'::`2'::impl
0x1800277c7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WoscStateMapDoubleFree@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscStateMapDoubleFree>::__private_IsEnabled(void)
0x1800277cc  test    al, al
0x1800277ce  jz      loc_18002788B
0x1800277d4  lea     r8, [rbp+250h+var_280]
0x1800277d8  lea     rdx, [rbp+250h+var_2B8]
0x1800277dc  mov     rcx, r14
0x1800277df  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800277e4  lea     r8, [rbp+250h+var_280]
0x1800277e8  mov     rbx, [rbp+250h+var_2A8]
0x1800277ec  mov     rdx, rbx
0x1800277ef  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x1800277f4  test    al, al
0x1800277f6  jz      short loc_180027801
0x1800277f8  cmp     rbx, [r14]
0x1800277fb  jnz     loc_180027938
0x180027801  lea     rcx, [rbp+250h+var_280]
0x180027805  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002780a  mov     rdi, rax
0x18002780d  mov     ecx, 210h; Size
0x180027812  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027817  mov     rsi, rax
0x18002781a  mov     [rbp+250h+var_2C8], rax
0x18002781e  xorps   xmm0, xmm0
0x180027821  movups  xmmword ptr [rax], xmm0
0x180027824  mov     eax, 1
0x180027829  mov     [rsi+8], eax
0x18002782c  mov     [rsi+0Ch], eax
0x18002782f  lea     rax, ??_7?$_Ref_count_obj2@VClientState@@@std@@6B@; const std::_Ref_count_obj2<ClientState>::`vftable'
0x180027836  mov     [rsi], rax
0x180027839  lea     rbx, [rsi+10h]
0x18002783d  xor     r8d, r8d
0x180027840  mov     rdx, rdi
0x180027843  mov     rcx, rbx
0x180027846  call    ??0ClientState@@QEAA@PEBGPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z; ClientState::ClientState(ushort const *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x18002784b  nop
0x18002784c  or      r12d, 2
0x180027850  mov     [rsp+350h+var_30C], r12d
0x180027855  mov     [rsp+350h+var_2F0], rbx
0x18002785a  mov     [rsp+350h+var_2E8], rsi
0x18002785f  lea     r8, [rbp+250h+var_280]
0x180027863  lea     rdx, [rbp+250h+var_2A0]
0x180027867  mov     rcx, r14
0x18002786a  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::shared_ptr<ClientState>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002786f  mov     rcx, [rax]
0x180027872  add     rcx, 40h ; '@'
0x180027876  lea     rdx, [rsp+350h+var_2F0]
0x18002787b  call    ??4?$shared_ptr@UCnsFlightState@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CnsFlightState>::operator=(std::shared_ptr<CnsFlightState> &&)
0x180027880  nop
0x180027881  mov     rcx, [rsp+350h+var_2E8]
0x180027886  jmp     loc_18002792D
0x18002788b  mov     ecx, 200h; Size
0x180027890  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027895  mov     r9, rax
0x180027898  mov     [rbp+250h+var_2C0], rax
0x18002789c  lea     rcx, [rbp+250h+var_280]
0x1800278a0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800278a5  mov     rdx, rax
0x1800278a8  xor     r8d, r8d
0x1800278ab  mov     rcx, r9
0x1800278ae  call    ??0ClientState@@QEAA@PEBGPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z; ClientState::ClientState(ushort const *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x1800278b3  mov     rbx, rax
0x1800278b6  mov     [rsp+350h+var_2F8], rax
0x1800278bb  mov     ecx, 18h; Size
0x1800278c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800278c5  mov     [rsp+350h+var_2F8], rax
0x1800278ca  xorps   xmm0, xmm0
0x1800278cd  movups  xmmword ptr [rax], xmm0
0x1800278d0  mov     dword ptr [rax+8], 1
0x1800278d7  mov     dword ptr [rax+0Ch], 1
0x1800278de  lea     rcx, ??_7?$_Ref_count@VClientState@@@std@@6B@; const std::_Ref_count<ClientState>::`vftable'
0x1800278e5  mov     [rax], rcx
0x1800278e8  mov     [rax+10h], rbx
0x1800278ec  mov     [rsp+350h+var_2E0], rbx
0x1800278f1  mov     [rsp+350h+var_2D8], rax
0x1800278f6  mov     [rsp+350h+var_2F8], r13
0x1800278fb  lea     rcx, [rsp+350h+var_2F8]
0x180027900  call    ??1?$_Temporary_owner@VClientState@@@std@@QEAA@XZ; std::_Temporary_owner<ClientState>::~_Temporary_owner<ClientState>(void)
0x180027905  nop
0x180027906  lea     r8, [rbp+250h+var_280]
0x18002790a  lea     rdx, [rbp+250h+var_290]
0x18002790e  mov     rcx, r14
0x180027911  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientState@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::shared_ptr<ClientState>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180027916  mov     rcx, [rax]
0x180027919  add     rcx, 40h ; '@'
0x18002791d  lea     rdx, [rsp+350h+var_2E0]
0x180027922  call    ??4?$shared_ptr@UCnsFlightState@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CnsFlightState>::operator=(std::shared_ptr<CnsFlightState> &&)
0x180027927  nop
0x180027928  mov     rcx, [rsp+350h+var_2D8]; this
0x18002792d  test    rcx, rcx
0x180027930  jz      short loc_180027938
0x180027932  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027937  nop
0x180027938  lea     rcx, [rbp+250h+var_280]
0x18002793c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027941  inc     r15d
0x180027944  xor     edx, edx; Val
0x180027946  mov     r8d, 208h; Size
0x18002794c  lea     rcx, [rbp+250h+Name]; void *
0x180027950  call    memset_0
0x180027955  mov     edx, r15d; dwIndex
0x180027958  mov     [rsp+350h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002795d  mov     [rsp+350h+lpcchClass], r13; lpcchClass
0x180027962  mov     [rsp+350h+lpClass], r13; lpClass
0x180027967  mov     [rsp+350h+lpReserved], r13; unsigned int
0x18002796c  mov     [rsp+350h+cchName], 104h
0x180027974  lea     r9, [rsp+350h+cchName]; lpcchName
0x180027979  lea     r8, [rbp+250h+Name]; lpName
0x18002797d  mov     rcx, [rsp+350h+hKey]; hKey
0x180027982  call    cs:__imp_RegEnumKeyExW
0x180027988  cmp     eax, 103h
0x18002798d  jnz     loc_1800277A3
0x180027993  lea     rcx, [rsp+350h+hKey]
0x180027998  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002799d  mov     rax, r14
0x1800279a0  mov     rcx, [rbp+250h+var_50]
0x1800279a7  xor     rcx, rsp; StackCookie
0x1800279aa  call    __security_check_cookie
0x1800279af  add     rsp, 318h
0x1800279b6  pop     r15
0x1800279b8  pop     r14
0x1800279ba  pop     r13
0x1800279bc  pop     r12
0x1800279be  pop     rdi
0x1800279bf  pop     rsi
0x1800279c0  pop     rbx
0x1800279c1  pop     rbp
0x1800279c2  retn
0x1800279c3  mov     r9d, eax; char *
0x1800279c6  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x1800279cd  mov     edx, 9Bh; void *
0x1800279d2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800279d8  mov     r9d, eax; char *
0x1800279db  lea     r8, aOnecoreBaseFli_10; "onecore\\base\\flighting\\onesettings\\"...
0x1800279e2  mov     edx, 0A8h; void *
0x1800279e7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
