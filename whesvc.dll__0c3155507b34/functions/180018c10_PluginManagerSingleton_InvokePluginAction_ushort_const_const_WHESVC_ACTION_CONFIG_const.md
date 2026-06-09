# PluginManagerSingleton::InvokePluginAction(ushort const * const,_WHESVC_ACTION_CONFIG * const)

- ea: `0x180018c10`
- end: `0x180018fab`
- name: `?InvokePluginAction@PluginManagerSingleton@@QEAAJQEBGQEAU_WHESVC_ACTION_CONFIG@@@Z`
- size: `923`
- prototype: `__int64 __fastcall(PluginManagerSingleton *this, const unsigned __int16 *, struct _WHESVC_ACTION_CONFIG *const)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c32c`

## callees

- `0x1800032e0`
- `0x180003304`
- `0x180003be4`
- `0x180009044`
- `0x18000f944`
- `0x1800115e0`
- `0x18001806c`
- `0x180018114`
- `0x1800181b4`
- `0x180018c10`
- `0x180025cd0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018e27`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018ed4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018f39`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018f73`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018e27`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018ed4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018f39`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018f73`
- `msvcp_win!_Mtx_unlock` at `0x180018db0`
- `msvcp_win!_Mtx_unlock` at `0x180018dc0`
- `msvcp_win!_Mtx_unlock` at `0x180018ee9`
- `msvcp_win!_Mtx_unlock` at `0x180018f1e`
- `msvcp_win!_Mtx_unlock` at `0x180018f58`
- `msvcp_win!_Mtx_unlock` at `0x180018db0`
- `msvcp_win!_Mtx_unlock` at `0x180018dc0`
- `msvcp_win!_Mtx_unlock` at `0x180018ee9`
- `msvcp_win!_Mtx_unlock` at `0x180018f1e`
- `msvcp_win!_Mtx_unlock` at `0x180018f58`
- `msvcp_win!_Mtx_lock` at `0x180018cfd`
- `msvcp_win!_Mtx_lock` at `0x180018e6d`
- `msvcp_win!_Mtx_lock` at `0x180018cfd`
- `msvcp_win!_Mtx_lock` at `0x180018e6d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018d0c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018d27`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018e7c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018e97`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018d0c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018d27`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018e7c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180018e97`

## string_xrefs

- `0x180018e0d`: `pcshell\base\whesvc\lib\pluginmanager.cpp`
- `0x180018efe`: `pcshell\base\whesvc\lib\pluginmanager.cpp`

## pseudocode

```c
__int64 __fastcall PluginManagerSingleton::InvokePluginAction(
        PluginManagerSingleton *this,
        const unsigned __int16 *a2,
        struct _WHESVC_ACTION_CONFIG *const a3)
{
  __int64 v5; // r8
  __int128 *v6; // rdx
  __int64 v7; // r15
  __int64 v8; // r9
  unsigned __int64 i; // rcx
  __int64 v10; // rax
  __int64 v11; // r12
  struct _Mtx_internal_imp_t *v13; // rsi
  const WCHAR *v14; // r12
  const WCHAR *v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r8
  __int64 v18; // rax
  _QWORD *v19; // rax
  __int64 (__fastcall *v20)(const unsigned __int16 *const, struct _WHESVC_ACTION_CONFIG *const); // rax
  unsigned int v21; // edi
  HMODULE *v22; // rax
  HMODULE *v23; // r15
  const WCHAR *v24; // rdx
  int Plugin; // eax
  __int64 (__fastcall *v26)(const unsigned __int16 *const, struct _WHESVC_ACTION_CONFIG *const); // rax
  __int64 v27; // rax
  HMODULE *v28; // r12
  void *v29; // rdi
  void *v30; // rdi
  int v31; // [rsp+20h] [rbp-98h]
  int v32; // [rsp+20h] [rbp-98h]
  void *v34; // [rsp+30h] [rbp-88h] BYREF
  PluginManagerSingleton *v35; // [rsp+40h] [rbp-78h]
  char v36[16]; // [rsp+48h] [rbp-70h] BYREF
  __int128 v37; // [rsp+58h] [rbp-60h] BYREF
  __int64 v38; // [rsp+68h] [rbp-50h]
  unsigned __int64 v39; // [rsp+70h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v35 = this;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  std::wstring::_Construct<1,unsigned short const *>(&v37);
  v6 = &v37;
  if ( v39 > 7 )
    v6 = (__int128 *)v37;
  v7 = 0xCBF29CE484222325uLL;
  v8 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 2 * v38; ++i )
    v8 = 0x100000001B3LL * (*((unsigned __int8 *)v6 + i) ^ (unsigned __int64)v8);
  v10 = std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
          i,
          v36,
          &v37,
          v8);
  v11 = qword_180035148;
  if ( *(_QWORD *)(v10 + 8) )
    v11 = *(_QWORD *)(v10 + 8);
  std::wstring::~wstring(&v37);
  if ( v11 == qword_180035148 )
    return 2147943568LL;
  v13 = (PluginManagerSingleton *)((char *)this + 64);
  if ( _Mtx_lock((PluginManagerSingleton *)((char *)this + 64)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)this + 35) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 35) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v14 = (const WCHAR *)(v11 + 48);
  if ( *((_QWORD *)v14 + 3) <= 7u )
    v15 = v14;
  else
    v15 = *(const WCHAR **)v14;
  v16 = 0;
  v17 = 2LL * *((_QWORD *)v14 + 2);
  if ( v17 )
  {
    do
      v7 = 0x100000001B3LL * (*((unsigned __int8 *)v15 + v16++) ^ (unsigned __int64)v7);
    while ( v16 < v17 );
  }
  v18 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(
                      this,
                      &v34,
                      v14,
                      v7)
                  + 8);
  if ( v18 && v18 != *((_QWORD *)this + 1) )
  {
    v19 = *(_QWORD **)(v18 + 48);
    if ( *v19
      && (v20 = (__int64 (__fastcall *)(const unsigned __int16 *const, struct _WHESVC_ACTION_CONFIG *const))v19[1]) != 0 )
    {
      v21 = v20(a2, a3);
    }
    else
    {
      v21 = -2147467261;
    }
    _Mtx_unlock((PluginManagerSingleton *)((char *)this + 64));
    return v21;
  }
  _Mtx_unlock((PluginManagerSingleton *)((char *)this + 64));
  v22 = (HMODULE *)operator new(0x10u);
  v23 = v22;
  *v22 = 0;
  v22[1] = 0;
  v34 = v22;
  if ( *((_QWORD *)v14 + 3) <= 7u )
    v24 = v14;
  else
    v24 = *(const WCHAR **)v14;
  Plugin = ActionPlugin::LoadPlugin(v22, v24);
  v21 = Plugin;
  if ( Plugin < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\pluginmanager.cpp",
      (const char *)(unsigned int)Plugin,
      (int)a3);
    if ( *v23 )
      FreeLibrary(*v23);
    operator delete(v23, 0x10u);
    return v21;
  }
  if ( *v23
    && (v26 = (__int64 (__fastcall *)(const unsigned __int16 *const, struct _WHESVC_ACTION_CONFIG *const))v23[1]) != 0 )
  {
    v21 = v26(a2, a3);
  }
  else
  {
    v21 = -2147467261;
  }
  if ( _Mtx_lock(v13) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)this + 35) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 35) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  try
  {
    v27 = *(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Try_emplace<std::wstring const &,>(
                       v35,
                       &v37,
                       v14);
    v34 = 0;
    v28 = *(HMODULE **)(v27 + 48);
    *(_QWORD *)(v27 + 48) = v23;
    if ( v28 )
    {
      if ( *v28 )
        FreeLibrary(*v28);
      operator delete(v28, 0x10u);
    }
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\pluginmanager.cpp",
      (const char *)0x8007000ELL,
      v32);
    _Mtx_unlock(v13);
    v29 = v34;
    if ( v34 )
    {
      if ( *(_QWORD *)v34 )
        FreeLibrary(*(HMODULE *)v34);
      operator delete(v29, 0x10u);
    }
    return 2147942414LL;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\pluginmanager.cpp",
      (const char *)0x80004005LL,
      v31);
    _Mtx_unlock(v13);
    v30 = v34;
    if ( v34 )
    {
      if ( *(_QWORD *)v34 )
        FreeLibrary(*(HMODULE *)v34);
      operator delete(v30, 0x10u);
    }
    return 2147500037LL;
  }
  _Mtx_unlock(v13);
  if ( (v21 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\pluginmanager.cpp",
      (const char *)v21,
      (int)v13);
    return v21;
  }
  return 0;
}

```

## disassembly

```asm
0x180018c10  push    rbx
0x180018c12  push    rsi
0x180018c13  push    rdi
0x180018c14  push    r12
0x180018c16  push    r13
0x180018c18  push    r14
0x180018c1a  push    r15
0x180018c1c  sub     rsp, 80h
0x180018c23  mov     rax, cs:__security_cookie
0x180018c2a  xor     rax, rsp
0x180018c2d  mov     [rsp+0B8h+var_40], rax
0x180018c32  mov     [rsp+0B8h+var_98], r8; int
0x180018c37  mov     r13, rdx
0x180018c3a  mov     r14, rcx
0x180018c3d  mov     [rsp+0B8h+var_78], rcx
0x180018c42  xor     ebx, ebx
0x180018c44  xorps   xmm0, xmm0
0x180018c47  movups  [rsp+0B8h+var_60], xmm0
0x180018c4c  mov     [rsp+0B8h+var_50], rbx
0x180018c51  mov     [rsp+0B8h+var_48], rbx
0x180018c56  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018c5a  inc     r8
0x180018c5d  cmp     [rdx+r8*2], bx
0x180018c62  jnz     short loc_180018C5A
0x180018c64  lea     rcx, [rsp+0B8h+var_60]
0x180018c69  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180018c6e  mov     rax, [rsp+0B8h+var_50]
0x180018c73  lea     rdx, [rsp+0B8h+var_60]
0x180018c78  cmp     [rsp+0B8h+var_48], 7
0x180018c7e  cmova   rdx, qword ptr [rsp+0B8h+var_60]
0x180018c84  mov     r15, 0CBF29CE484222325h
0x180018c8e  mov     r9, r15
0x180018c91  lea     r8, [rax+rax]
0x180018c95  mov     rcx, rbx
0x180018c98  mov     rdi, 100000001B3h
0x180018ca2  test    r8, r8
0x180018ca5  jz      short loc_180018CBA
0x180018ca7  movzx   eax, byte ptr [rcx+rdx]
0x180018cab  xor     r9, rax
0x180018cae  imul    r9, rdi
0x180018cb2  inc     rcx
0x180018cb5  cmp     rcx, r8
0x180018cb8  jb      short loc_180018CA7
0x180018cba  lea     r8, [rsp+0B8h+var_60]
0x180018cbf  lea     rdx, [rsp+0B8h+var_70]
0x180018cc4  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180018cc9  mov     r12, cs:qword_180035148
0x180018cd0  cmp     [rax+8], rbx
0x180018cd4  cmovnz  r12, [rax+8]
0x180018cd9  lea     rcx, [rsp+0B8h+var_60]
0x180018cde  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018ce3  cmp     r12, cs:qword_180035148
0x180018cea  jnz     short loc_180018CF6
0x180018cec  mov     eax, 80070490h
0x180018cf1  jmp     loc_180018F8B
0x180018cf6  lea     rsi, [r14+40h]
0x180018cfa  mov     rcx, rsi; _Mtx_t
0x180018cfd  call    cs:__imp__Mtx_lock
0x180018d03  test    eax, eax
0x180018d05  jz      short loc_180018D13
0x180018d07  mov     ecx, 5
0x180018d0c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180018d12  int     3; Trap to Debugger
0x180018d13  mov     eax, [rsi+4Ch]
0x180018d16  cmp     eax, 7FFFFFFFh
0x180018d1b  jnz     short loc_180018D2E
0x180018d1d  dec     eax
0x180018d1f  mov     [rsi+4Ch], eax
0x180018d22  mov     ecx, 6
0x180018d27  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180018d2d  int     3; Trap to Debugger
0x180018d2e  add     r12, 30h ; '0'
0x180018d32  mov     r8, [r12+10h]
0x180018d37  cmp     qword ptr [r12+18h], 7
0x180018d3d  jbe     short loc_180018D45
0x180018d3f  mov     rdx, [r12]
0x180018d43  jmp     short loc_180018D48
0x180018d45  mov     rdx, r12
0x180018d48  mov     rcx, rbx
0x180018d4b  add     r8, r8
0x180018d4e  jz      short loc_180018D63
0x180018d50  movzx   eax, byte ptr [rdx+rcx]
0x180018d54  xor     r15, rax
0x180018d57  imul    r15, rdi
0x180018d5b  inc     rcx
0x180018d5e  cmp     rcx, r8
0x180018d61  jb      short loc_180018D50
0x180018d63  mov     r9, r15
0x180018d66  mov     r8, r12
0x180018d69  lea     rdx, [rsp+0B8h+var_88]
0x180018d6e  mov     rcx, r14
0x180018d71  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180018d76  mov     rax, [rax+8]
0x180018d7a  test    rax, rax
0x180018d7d  jz      short loc_180018DBD
0x180018d7f  cmp     rax, [r14+8]
0x180018d83  jz      short loc_180018DBD
0x180018d85  mov     rax, [rax+30h]
0x180018d89  cmp     [rax], rbx
0x180018d8c  jz      short loc_180018DA8
0x180018d8e  mov     rax, [rax+8]
0x180018d92  test    rax, rax
0x180018d95  jz      short loc_180018DA8
0x180018d97  mov     rdx, [rsp+0B8h+var_98]
0x180018d9c  mov     rcx, r13
0x180018d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018da4  mov     edi, eax
0x180018da6  jmp     short loc_180018DAD
0x180018da8  mov     edi, 80004003h
0x180018dad  mov     rcx, rsi; _Mtx_t
0x180018db0  call    cs:__imp__Mtx_unlock
0x180018db6  mov     eax, edi
0x180018db8  jmp     loc_180018F8B
0x180018dbd  mov     rcx, rsi; _Mtx_t
0x180018dc0  call    cs:__imp__Mtx_unlock
0x180018dc6  mov     r14d, 10h
0x180018dcc  mov     ecx, r14d; Size
0x180018dcf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018dd4  mov     r15, rax
0x180018dd7  mov     [rax], rbx
0x180018dda  mov     [rax+8], rbx
0x180018dde  mov     [rsp+0B8h+var_88], rax
0x180018de3  cmp     qword ptr [r12+18h], 7
0x180018de9  jbe     short loc_180018DF1
0x180018deb  mov     rdx, [r12]
0x180018def  jmp     short loc_180018DF4
0x180018df1  mov     rdx, r12; unsigned __int16 *
0x180018df4  mov     rcx, r15; this
0x180018df7  call    ?LoadPlugin@ActionPlugin@@QEAAJQEBG@Z; ActionPlugin::LoadPlugin(ushort const * const)
0x180018dfc  mov     edi, eax
0x180018dfe  test    eax, eax
0x180018e00  jns     short loc_180018E3D
0x180018e02  mov     rcx, [rsp+0B8h]; this
0x180018e0a  mov     r9d, eax; char *
0x180018e0d  lea     r8, aPcshellBaseWhe_3; "pcshell\\base\\whesvc\\lib\\pluginmanag"...
0x180018e14  mov     edx, 3Ah ; ':'; void *
0x180018e19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e1e  nop
0x180018e1f  cmp     [r15], rbx
0x180018e22  jz      short loc_180018E2D
0x180018e24  mov     rcx, [r15]; hLibModule
0x180018e27  call    cs:__imp_FreeLibrary
0x180018e2d  mov     rdx, r14; unsigned __int64
0x180018e30  mov     rcx, r15; void *
0x180018e33  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018e38  jmp     loc_180018DB6
0x180018e3d  cmp     [r15], rbx
0x180018e40  jz      short loc_180018E5C
0x180018e42  mov     rax, [r15+8]
0x180018e46  test    rax, rax
0x180018e49  jz      short loc_180018E5C
0x180018e4b  mov     rdx, [rsp+0B8h+var_98]
0x180018e50  mov     rcx, r13
0x180018e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e58  mov     edi, eax
0x180018e5a  jmp     short loc_180018E61
0x180018e5c  mov     edi, 80004003h
0x180018e61  mov     [rsp+0B8h+var_98], rsi; int
0x180018e66  mov     [rsp+0B8h+var_90], bl
0x180018e6a  mov     rcx, rsi; _Mtx_t
0x180018e6d  call    cs:__imp__Mtx_lock
0x180018e73  test    eax, eax
0x180018e75  jz      short loc_180018E83
0x180018e77  mov     ecx, 5
0x180018e7c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180018e82  int     3; Trap to Debugger
0x180018e83  mov     eax, [rsi+4Ch]
0x180018e86  cmp     eax, 7FFFFFFFh
0x180018e8b  jnz     short loc_180018E9E
0x180018e8d  dec     eax
0x180018e8f  mov     [rsi+4Ch], eax
0x180018e92  mov     ecx, 6
0x180018e97  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180018e9d  int     3; Trap to Debugger
0x180018e9e  mov     [rsp+0B8h+var_90], 1
0x180018ea3  mov     r8, r12
0x180018ea6  lea     rdx, [rsp+0B8h+var_60]
0x180018eab  mov     rcx, [rsp+0B8h+var_78]
0x180018eb0  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180018eb5  mov     rax, [rax]
0x180018eb8  mov     [rsp+0B8h+var_88], rbx
0x180018ebd  mov     r12, [rax+30h]
0x180018ec1  mov     [rax+30h], r15
0x180018ec5  test    r12, r12
0x180018ec8  jz      short loc_180018EE6
0x180018eca  cmp     [r12], rbx
0x180018ece  jz      short loc_180018EDA
0x180018ed0  mov     rcx, [r12]; hLibModule
0x180018ed4  call    cs:__imp_FreeLibrary
0x180018eda  mov     rdx, r14; unsigned __int64
0x180018edd  mov     rcx, r12; void *
0x180018ee0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018ee5  nop
0x180018ee6  mov     rcx, rsi; _Mtx_t
0x180018ee9  call    cs:__imp__Mtx_unlock
0x180018eef  test    edi, edi
0x180018ef1  jns     short loc_180018F15
0x180018ef3  mov     rcx, [rsp+0B8h]; this
0x180018efb  mov     r9d, edi; char *
0x180018efe  lea     r8, aPcshellBaseWhe_3; "pcshell\\base\\whesvc\\lib\\pluginmanag"...
0x180018f05  mov     edx, 53h ; 'S'; void *
0x180018f0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f0f  nop
0x180018f10  jmp     loc_180018DB6
0x180018f15  xor     eax, eax
0x180018f17  jmp     short loc_180018F8B
0x180018f19  mov     rcx, [rsp+0B8h+var_98]; _Mtx_t
0x180018f1e  call    cs:__imp__Mtx_unlock
0x180018f24  nop
0x180018f25  mov     rdi, [rsp+0B8h+var_88]
0x180018f2a  xor     ebx, ebx
0x180018f2c  test    rdi, rdi
0x180018f2f  jz      short loc_180018F4C
0x180018f31  cmp     [rdi], rbx
0x180018f34  jz      short loc_180018F3F
0x180018f36  mov     rcx, [rdi]; hLibModule
0x180018f39  call    cs:__imp_FreeLibrary
0x180018f3f  mov     edx, 10h; unsigned __int64
0x180018f44  mov     rcx, rdi; void *
0x180018f47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018f4c  mov     eax, 8007000Eh
0x180018f51  jmp     short loc_180018F8B
0x180018f53  mov     rcx, [rsp+0B8h+var_98]; _Mtx_t
0x180018f58  call    cs:__imp__Mtx_unlock
0x180018f5e  nop
0x180018f5f  mov     rdi, [rsp+0B8h+var_88]
0x180018f64  xor     ebx, ebx
0x180018f66  test    rdi, rdi
0x180018f69  jz      short loc_180018F86
0x180018f6b  cmp     [rdi], rbx
0x180018f6e  jz      short loc_180018F79
0x180018f70  mov     rcx, [rdi]; hLibModule
0x180018f73  call    cs:__imp_FreeLibrary
0x180018f79  mov     edx, 10h; unsigned __int64
0x180018f7e  mov     rcx, rdi; void *
0x180018f81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018f86  mov     eax, 80004005h
0x180018f8b  mov     rcx, [rsp+0B8h+var_40]
0x180018f90  xor     rcx, rsp; StackCookie
0x180018f93  call    __security_check_cookie
0x180018f98  add     rsp, 80h
0x180018f9f  pop     r15
0x180018fa1  pop     r14
0x180018fa3  pop     r13
0x180018fa5  pop     r12
0x180018fa7  pop     rdi
0x180018fa8  pop     rsi
0x180018fa9  pop     rbx
0x180018faa  retn
```
