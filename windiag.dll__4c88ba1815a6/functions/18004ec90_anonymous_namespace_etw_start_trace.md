# _anonymous_namespace_::etw_start_trace

- ea: `0x18004ec90`
- end: `0x18004ef18`
- name: `_anonymous_namespace_::etw_start_trace`
- size: `648`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, authz_impersonation`

## callees

- `0x180004510`
- `0x1800048e0`
- `0x18000491c`
- `0x180006600`
- `0x180006c70`
- `0x180006d40`
- `0x180007490`
- `0x180008610`
- `0x180008660`
- `0x18003b0bc`
- `0x180041564`
- `0x1800416a0`
- `0x180046df8`
- `0x180047ed8`
- `0x180049674`
- `0x180049750`
- `0x18004991c`
- `0x18004b73c`
- `0x18004bf24`
- `0x18004ec90`
- `0x180050988`
- `0x180059590`
- `0x18005b208`
- `0x18009d010`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18004ed6b`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18004ed6b`

## string_xrefs

- `0x18004ed74`: `SeSystemProfilePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::etw_start_trace(struct lua_State *a1)
{
  char ***v2; // r14
  __int64 v4; // r8
  const CHAR *v5; // rdx
  const WCHAR *v6; // rdx
  _QWORD *v7; // rbx
  char **v8; // rsi
  struct etw_recorder::provider *v9; // rsi
  const struct etw_recorder::provider *i; // rbx
  const char *v11; // rdx
  volatile signed __int32 *v12; // rbx
  struct etw_recorder::provider *v13[3]; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v15; // [rsp+48h] [rbp-B8h]
  char *v16[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[16]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR InstanceName[4]; // [rsp+80h] [rbp-80h] BYREF
  char *v19[5]; // [rsp+A0h] [rbp-60h] BYREF
  char *v20[13]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v21[48]; // [rsp+130h] [rbp+30h] BYREF

  lua_pushlightuserdata(a1, &qword_1800BEAB0);
  lua_gettable(a1, 4293966296LL);
  v2 = (char ***)luaL_checkudata(a1, -1, "etw.state");
  lua_settop(a1, -2);
  if ( *v2 )
    return 0;
  luaL_checktype(a1, 1, 5);
  anonymous_namespace_::etw_provider_parser__anonymous_namespace_::etw_recorder_provider_etw_recorder::provider_::parse_many(
    v13,
    a1);
  anonymous_namespace_::etw_session::etw_session((__int64)v19, a1, v4);
  anonymous_namespace_::etw_create_empty_trace_properties(v16);
  v5 = (const CHAR *)v19;
  if ( v19[3] > (char *)0xF )
    v5 = v19[0];
  windiag::char_to_wstring((__int64)InstanceName, v5);
  v6 = (const WCHAR *)InstanceName;
  if ( InstanceName[3] > (LPCWSTR)7 )
    v6 = InstanceName[0];
  ControlTraceW(0, v6, (PEVENT_TRACE_PROPERTIES)v16[3], 1u);
  windiag::enable_privilege(&v14, L"SeSystemProfilePrivilege", 0);
  v7 = operator new(0x68u);
  *(_OWORD *)v7 = 0;
  v7[2] = 0;
  v7[3] = 7;
  *(_WORD *)v7 = 0;
  *((_OWORD *)v7 + 2) = 0;
  v7[6] = 0;
  v7[7] = 7;
  *((_WORD *)v7 + 16) = 0;
  v7[8] = 0;
  v7[9] = 0;
  v7[10] = 0;
  v7[11] = 0;
  v7[12] = 0;
  etw_recorder::init((etw_recorder *)v7, (const struct etw_recorder::session *)v19);
  v8 = *v2;
  *v2 = (char **)v7;
  if ( v8 )
  {
    std::vector<char>::~vector<char>(v8 + 8);
    std::wstring::~wstring(v8 + 4);
    std::wstring::~wstring(v8);
    operator delete(v8);
  }
  if ( v20[2] )
    std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::insert<0,0>(
      v2 + 1,
      v17,
      v20);
  v9 = v13[1];
  for ( i = v13[0]; i != v9; i = (const struct etw_recorder::provider *)((char *)i + 176) )
    etw_recorder::enable_provider((unsigned __int64)(*v2)[12], i, 1u, v21[40] == 0);
  v11 = (const char *)v20;
  if ( v20[3] > (char *)0xF )
    v11 = v20[0];
  lua_pushstring(a1, v11);
  v12 = v15;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  std::wstring::~wstring((char **)InstanceName);
  std::vector<char>::~vector<char>(v16);
  if ( v21[24] )
    std::vector<_CLASSIC_EVENT_ID>::~vector<_CLASSIC_EVENT_ID>(v21);
  std::string::~string(v20);
  std::string::~string(v19);
  std::vector__anonymous_namespace_::etw_recorder_provider_std::allocator__anonymous_namespace_::etw_recorder_provider___::_vector__anonymous_namespace_::etw_recorder_provider_std::allocator__anonymous_namespace_::etw_recorder_provider___(v13);
  return 1;
}

```

## disassembly

```asm
0x18004ec90  push    rbp
0x18004ec92  push    rbx
0x18004ec93  push    rsi
0x18004ec94  push    rdi
0x18004ec95  push    r14
0x18004ec97  push    r15
0x18004ec99  lea     rbp, [rsp-78h]
0x18004ec9e  sub     rsp, 178h
0x18004eca5  mov     rax, cs:__security_cookie
0x18004ecac  xor     rax, rsp
0x18004ecaf  mov     [rbp+0A0h+var_40], rax
0x18004ecb3  mov     rdi, rcx
0x18004ecb6  xor     r15d, r15d
0x18004ecb9  lea     rdx, qword_1800BEAB0; void *
0x18004ecc0  call    ?lua_pushlightuserdata@@YAXPEAUlua_State@@PEAX@Z; lua_pushlightuserdata(lua_State *,void *)
0x18004ecc5  mov     edx, 0FFF0B9D8h; int
0x18004ecca  mov     rcx, rdi; struct lua_State *
0x18004eccd  call    ?lua_gettable@@YAHPEAUlua_State@@H@Z; lua_gettable(lua_State *,int)
0x18004ecd2  lea     r8, aEtwState; "etw.state"
0x18004ecd9  or      edx, 0FFFFFFFFh; int
0x18004ecdc  mov     rcx, rdi; struct lua_State *
0x18004ecdf  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x18004ece4  mov     r14, rax
0x18004ece7  lea     edx, [r15-2]; int
0x18004eceb  mov     rcx, rdi; struct lua_State *
0x18004ecee  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x18004ecf3  cmp     [r14], r15
0x18004ecf6  jz      short loc_18004ECFF
0x18004ecf8  xor     eax, eax
0x18004ecfa  jmp     loc_18004EEFC
0x18004ecff  mov     edx, 1; int
0x18004ed04  lea     r8d, [rdx+4]; int
0x18004ed08  mov     rcx, rdi; struct lua_State *
0x18004ed0b  call    ?luaL_checktype@@YAXPEAUlua_State@@HH@Z; luaL_checktype(lua_State *,int,int)
0x18004ed10  mov     rdx, rdi
0x18004ed13  lea     rcx, [rsp+1A0h+var_178]
0x18004ed18  call    _anonymous_namespace___etw_provider_parser__anonymous_namespace___etw_recorder_provider_etw_recorder__provider___parse_many
0x18004ed1d  nop
0x18004ed1e  mov     rdx, rdi
0x18004ed21  lea     rcx, [rbp+0A0h+var_100]
0x18004ed25  call    _anonymous_namespace___etw_session__etw_session
0x18004ed2a  nop
0x18004ed2b  lea     rcx, [rsp+1A0h+var_150]
0x18004ed30  call    _anonymous_namespace___etw_create_empty_trace_properties
0x18004ed35  nop
0x18004ed36  lea     rdx, [rbp+0A0h+var_100]
0x18004ed3a  cmp     [rbp+0A0h+var_E8], 0Fh
0x18004ed3f  cmova   rdx, [rbp+0A0h+var_100]
0x18004ed44  lea     rcx, [rbp+0A0h+InstanceName]
0x18004ed48  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18004ed4d  nop
0x18004ed4e  lea     rdx, [rbp+0A0h+InstanceName]
0x18004ed52  mov     esi, 7
0x18004ed57  cmp     [rbp+0A0h+var_108], rsi
0x18004ed5b  cmova   rdx, [rbp+0A0h+InstanceName]; InstanceName
0x18004ed60  lea     r9d, [rsi-6]; ControlCode
0x18004ed64  mov     r8, [rsp+1A0h+Properties]; Properties
0x18004ed69  xor     ecx, ecx; TraceHandle
0x18004ed6b  call    cs:__imp_ControlTraceW
0x18004ed71  xor     r8d, r8d
0x18004ed74  lea     rdx, aSesystemprofil; "SeSystemProfilePrivilege"
0x18004ed7b  lea     rcx, [rsp+1A0h+var_160]
0x18004ed80  call    ?enable_privilege@windiag@@YA?AV?$shared_ptr@X@std@@PEBG_N@Z; windiag::enable_privilege(ushort const *,bool)
0x18004ed85  nop
0x18004ed86  lea     ecx, [rsi+61h]; Size
0x18004ed89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ed8e  mov     rbx, rax
0x18004ed91  xorps   xmm0, xmm0
0x18004ed94  movups  xmmword ptr [rax], xmm0
0x18004ed97  mov     [rax+10h], r15
0x18004ed9b  mov     [rax+18h], rsi
0x18004ed9f  mov     [rax], r15w
0x18004eda3  movups  xmmword ptr [rax+20h], xmm0
0x18004eda7  mov     [rax+30h], r15
0x18004edab  mov     [rax+38h], rsi
0x18004edaf  mov     [rax+20h], r15w
0x18004edb4  mov     [rax+40h], r15
0x18004edb8  mov     [rax+48h], r15
0x18004edbc  mov     [rax+50h], r15
0x18004edc0  mov     [rax+58h], r15
0x18004edc4  mov     [rax+60h], r15
0x18004edc8  mov     [rsp+1A0h+var_180], rax
0x18004edcd  lea     rdx, [rbp+0A0h+var_100]; struct etw_recorder::session *
0x18004edd1  mov     rcx, rax; this
0x18004edd4  call    ?init@etw_recorder@@QEAAXAEBUsession@1@@Z; etw_recorder::init(etw_recorder::session const &)
0x18004edd9  mov     [rsp+1A0h+var_180], r15
0x18004edde  mov     rsi, [r14]
0x18004ede1  mov     [r14], rbx
0x18004ede4  test    rsi, rsi
0x18004ede7  jz      short loc_18004EE10
0x18004ede9  lea     rcx, [rsi+40h]
0x18004eded  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18004edf2  lea     rcx, [rsi+20h]
0x18004edf6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004edfb  mov     rcx, rsi
0x18004edfe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004ee03  mov     edx, 68h ; 'h'
0x18004ee08  mov     rcx, rsi; Block
0x18004ee0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004ee10  cmp     [rbp+0A0h+var_C8], r15
0x18004ee14  jz      short loc_18004EE28
0x18004ee16  lea     rcx, [r14+8]
0x18004ee1a  lea     r8, [rbp+0A0h+var_D8]
0x18004ee1e  lea     rdx, [rsp+1A0h+var_130]
0x18004ee23  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::insert<0,0>(std::string const &)
0x18004ee28  mov     rsi, [rsp+1A0h+var_170]
0x18004ee2d  mov     rbx, [rsp+1A0h+var_178]
0x18004ee32  jmp     short loc_18004EE58
0x18004ee34  mov     rcx, [r14]
0x18004ee37  cmp     [rbp+0A0h+var_48], r15b
0x18004ee3b  setz    r9b; bool
0x18004ee3f  mov     r8d, 1; unsigned int
0x18004ee45  mov     rdx, rbx; struct etw_recorder::provider *
0x18004ee48  mov     rcx, [rcx+60h]; unsigned __int64
0x18004ee4c  call    ?enable_provider@etw_recorder@@SA_N_KAEBUprovider@1@I_N@Z; etw_recorder::enable_provider(unsigned __int64,etw_recorder::provider const &,uint,bool)
0x18004ee51  add     rbx, 0B0h
0x18004ee58  cmp     rbx, rsi
0x18004ee5b  jnz     short loc_18004EE34
0x18004ee5d  lea     rdx, [rbp+0A0h+var_D8]
0x18004ee61  cmp     [rbp+0A0h+var_C0], 0Fh
0x18004ee66  cmova   rdx, [rbp+0A0h+var_D8]; char *
0x18004ee6b  mov     rcx, rdi; struct lua_State *
0x18004ee6e  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18004ee73  nop
0x18004ee74  mov     rbx, [rsp+1A0h+var_158]
0x18004ee79  test    rbx, rbx
0x18004ee7c  jz      short loc_18004EEB6
0x18004ee7e  or      eax, 0FFFFFFFFh
0x18004ee81  lock xadd [rbx+8], eax
0x18004ee86  cmp     eax, 1
0x18004ee89  jnz     short loc_18004EEB6
0x18004ee8b  mov     rax, [rbx]
0x18004ee8e  mov     rcx, rbx
0x18004ee91  mov     rax, [rax]
0x18004ee94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee99  or      eax, 0FFFFFFFFh
0x18004ee9c  lock xadd [rbx+0Ch], eax
0x18004eea1  cmp     eax, 1
0x18004eea4  jnz     short loc_18004EEB6
0x18004eea6  mov     rax, [rbx]
0x18004eea9  mov     rcx, rbx
0x18004eeac  mov     rax, [rax+8]
0x18004eeb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eeb5  nop
0x18004eeb6  lea     rcx, [rbp+0A0h+InstanceName]
0x18004eeba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004eebf  nop
0x18004eec0  lea     rcx, [rsp+1A0h+var_150]
0x18004eec5  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18004eeca  nop
0x18004eecb  cmp     [rbp+0A0h+var_58], r15b
0x18004eecf  jz      short loc_18004EEDA
0x18004eed1  lea     rcx, [rbp+0A0h+var_70]
0x18004eed5  call    ??1?$vector@U_CLASSIC_EVENT_ID@@V?$allocator@U_CLASSIC_EVENT_ID@@@std@@@std@@QEAA@XZ; std::vector<_CLASSIC_EVENT_ID>::~vector<_CLASSIC_EVENT_ID>(void)
0x18004eeda  lea     rcx, [rbp+0A0h+var_D8]
0x18004eede  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004eee3  lea     rcx, [rbp+0A0h+var_100]
0x18004eee7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004eeec  nop
0x18004eeed  lea     rcx, [rsp+1A0h+var_178]
0x18004eef2  call    std__vector__anonymous_namespace___etw_recorder_provider_std__allocator__anonymous_namespace___etw_recorder_provider______vector__anonymous_namespace___etw_recorder_provider_std__allocator__anonymous_namespace___etw_recorder_provider___
0x18004eef7  mov     eax, 1
0x18004eefc  mov     rcx, [rbp+0A0h+var_40]
0x18004ef00  xor     rcx, rsp; StackCookie
0x18004ef03  call    __security_check_cookie
0x18004ef08  add     rsp, 178h
0x18004ef0f  pop     r15
0x18004ef11  pop     r14
0x18004ef13  pop     rdi
0x18004ef14  pop     rsi
0x18004ef15  pop     rbx
0x18004ef16  pop     rbp
0x18004ef17  retn
```
