# _anonymous_namespace_::lua_open_wdg

- ea: `0x18007742c`
- end: `0x180077ea6`
- name: `_anonymous_namespace_::lua_open_wdg`
- size: `2682`
- prototype: `void __fastcall(windiag *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180078c2c`

## callees

- `0x18000491c`
- `0x180004aac`
- `0x180004b14`
- `0x180006910`
- `0x180006c70`
- `0x180007060`
- `0x1800073e0`
- `0x180007490`
- `0x180008fb0`
- `0x1800092e0`
- `0x180009440`
- `0x180009510`
- `0x18003d738`
- `0x180073a6c`
- `0x180075aa0`
- `0x18007742c`
- `0x180084dac`

## string_xrefs

- `0x180077c57`: `reg_create_key`
- `0x180077c73`: `reg_delete_key`
- `0x180077cab`: `reg_delete_value`
- `0x180077cc7`: `security_impersonate_process`
- `0x180077ce3`: `security_revert_impersonation`
- `0x180077cff`: `security_code_integrity`
- `0x180077d1b`: `security_create_process`
- `0x180077d37`: `security_process_protection`
- `0x180077d53`: `security_token_information`
- `0x180077ddf`: `wnf_create_name`
- `0x180077dfb`: `wnf_delete_name`
- `0x180077e33`: `wnf_update_data`
- `0x180077e4f`: `wnf_delete_data`
- `0x1800778f7`: `security.state`
- `0x18007793e`: `security.state`
- `0x180077960`: `security.state`
- `0x1800779a4`: `security.process`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall anonymous_namespace_::lua_open_wdg(windiag *this)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  void *v10; // rbx
  void *v11; // rax
  _OWORD *v12; // rbx
  struct lua_State *v13; // rdx
  _QWORD *v14; // [rsp+68h] [rbp+10h]

  if ( dword_1800BEE40 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800BEE40);
    if ( dword_1800BEE40 == -1 )
    {
      qword_1800BD3B8 = (__int64)lambda_5f4c5d12697afcf33005697c9863c78e_::_lambda_invoker_cdecl_;
      qword_1800BD3C0 = (__int64)"native_stop_event";
      qword_1800BD3C8 = (__int64)windiag::lua_wdg_native_stop_event;
      qword_1800BD3D0 = (__int64)"native_pointer_size";
      qword_1800BD3D8 = (__int64)windiag::lua_wdg_native_pointer_size;
      qword_1800BD3E0 = (__int64)"native_buffer";
      qword_1800BD3E8 = (__int64)windiag::lua_wdg_native_buffer;
      qword_1800BD3F0 = (__int64)"native_resource";
      qword_1800BD3F8 = (__int64)windiag::lua_wdg_native_resource;
      qword_1800BD400 = (__int64)"native_invoke";
      qword_1800BD408 = (__int64)windiag::lua_wdg_native_invoke;
      qword_1800BD410 = (__int64)"native_error";
      qword_1800BD418 = (__int64)windiag::lua_wdg_native_error;
      qword_1800BD420 = (__int64)"native_type";
      qword_1800BD428 = (__int64)windiag::lua_wdg_native_type;
      qword_1800BD430 = (__int64)"power_emi_devs";
      qword_1800BD438 = (__int64)windiag::lua_wdg_power_emi_devs;
      qword_1800BD440 = (__int64)"power_processor";
      qword_1800BD448 = (__int64)windiag::lua_wdg_power_processor;
      qword_1800BD450 = (__int64)"power_battery_state";
      qword_1800BD458 = (__int64)windiag::lua_wdg_power_battery_state;
      qword_1800BD460 = (__int64)"thermal_power_info";
      qword_1800BD468 = (__int64)windiag::lua_wdg_power_thermal_info;
      qword_1800BD470 = (__int64)"fan_impact_info";
      qword_1800BD478 = (__int64)windiag::lua_wdg_power_fan_impact_info;
      qword_1800BD480 = (__int64)"fan_rpm_info";
      qword_1800BD488 = (__int64)windiag::lua_wdg_power_fan_rpm_info;
      qword_1800BD490 = (__int64)"reg_enum_keys";
      qword_1800BD498 = (__int64)windiag::lua_wdg_reg_enum_keys;
      qword_1800BD4A0 = (__int64)"reg_enum_values";
      qword_1800BD4A8 = (__int64)windiag::lua_wdg_reg_enum_values;
      qword_1800BD4B0 = (__int64)"reg_query_value";
      qword_1800BD4B8 = (__int64)windiag::lua_wdg_reg_query_value;
      qword_1800BD4C0 = (__int64)"reg_query_data";
      qword_1800BD4C8 = (__int64)windiag::lua_wdg_reg_query_data;
      qword_1800BD4D0 = (__int64)"reg_create_key";
      qword_1800BD4D8 = (__int64)windiag::lua_wdg_reg_create_key;
      qword_1800BD4E0 = (__int64)"reg_delete_key";
      qword_1800BD4E8 = (__int64)windiag::lua_wdg_reg_delete_key;
      qword_1800BD4F0 = (__int64)"reg_set_value";
      qword_1800BD4F8 = (__int64)windiag::lua_wdg_reg_set_value;
      qword_1800BD500 = (__int64)"reg_delete_value";
      qword_1800BD508 = (__int64)windiag::lua_wdg_reg_delete_value;
      qword_1800BD510 = (__int64)"security_impersonate_process";
      qword_1800BD518 = (__int64)windiag::lua_wdg_security_impersonate_process;
      qword_1800BD520 = (__int64)"security_revert_impersonation";
      qword_1800BD528 = (__int64)windiag::lua_wdg_security_revert_impersonation;
      qword_1800BD530 = (__int64)"security_code_integrity";
      qword_1800BD538 = (__int64)windiag::lua_wdg_security_code_integrity;
      qword_1800BD540 = (__int64)"security_create_process";
      qword_1800BD548 = (__int64)windiag::lua_wdg_security_create_process;
      qword_1800BD550 = (__int64)"security_process_protection";
      qword_1800BD558 = (__int64)windiag::lua_wdg_security_process_protection;
      qword_1800BD560 = (__int64)"security_token_information";
      qword_1800BD568 = (__int64)windiag::lua_wdg_security_token_information;
      qword_1800BD570 = (__int64)"utc_scenario_active";
      qword_1800BD578 = (__int64)windiag::lua_wdg_utc_scenario_active;
      qword_1800BD580 = (__int64)"utc_scenario_escalation";
      qword_1800BD588 = (__int64)windiag::lua_wdg_utc_scenario_escalation;
      qword_1800BD590 = (__int64)"utc_active_scenario_list";
      qword_1800BD598 = (__int64)windiag::lua_wdg_utc_active_scenario_list;
      qword_1800BD5A0 = (__int64)"wnf_check_name";
      qword_1800BD5A8 = (__int64)windiag::lua_wdg_wnf_check_name;
      qword_1800BD5B0 = (__int64)"wnf_create_name";
      qword_1800BD5B8 = (__int64)windiag::lua_wdg_wnf_create_name;
      qword_1800BD5C0 = (__int64)"wnf_delete_name";
      qword_1800BD5C8 = (__int64)windiag::lua_wdg_wnf_delete_name;
      qword_1800BD5D0 = (__int64)"wnf_query_data";
      qword_1800BD5D8 = (__int64)windiag::lua_wdg_wnf_query_data;
      qword_1800BD5E0 = (__int64)"wnf_update_data";
      qword_1800BD5E8 = (__int64)windiag::lua_wdg_wnf_update_data;
      qword_1800BD5F0 = (__int64)"wnf_delete_data";
      qword_1800BD5F8 = (__int64)windiag::lua_wdg_wnf_delete_data;
      qword_1800BD600 = (__int64)"sleep";
      qword_1800BD608 = (__int64)anonymous_namespace_::lua_wdg_sleep;
      qword_1800BD610 = 0;
      qword_1800BD618 = 0;
      Init_thread_footer(&dword_1800BEE40);
    }
  }
  if ( (unsigned int)luaL_newmetatable(this, "gbl.state") )
  {
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F798, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl'::`2'::impl) )
    {
      v2 = lua_newuserdatauv(this, 0x10u, 0);
      luaL_setmetatable(this, "gbl.state");
      *v2 = 0;
      v2[1] = 0;
      v3 = operator new(0x80u);
      *v3 = v3;
      v3[1] = v3;
      v3[2] = v3;
      *((_WORD *)v3 + 12) = 257;
      *v2 = v3;
    }
    else
    {
      v4 = lua_newuserdatauv(this, 0x10u, 0);
      *v4 = 0;
      v4[1] = 0;
      v5 = operator new(0x80u);
      *v5 = v5;
      v5[1] = v5;
      v5[2] = v5;
      *((_WORD *)v5 + 12) = 257;
      *v4 = v5;
      luaL_setmetatable(this, "gbl.state");
    }
    lua_pushlightuserdata(this, &dword_1800BEADC);
    lua_rotate(this, -2, 1);
    lua_settable(this, -1001000);
  }
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "language_model.state") )
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F240, 0);
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "etw.state") )
  {
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F410, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl'::`2'::impl) )
    {
      v6 = lua_newuserdatauv(this, 0x38u, 0);
      luaL_setmetatable(this, "etw.state");
      *v6 = 0;
      v6[1] = 0;
      v6[2] = 0;
      v7 = operator new(0x40u);
      *v7 = v7;
      v7[1] = v7;
      v7[2] = v7;
      *((_WORD *)v7 + 12) = 257;
      v6[1] = v7;
      v6[3] = 0;
      v6[4] = 0;
      v6[5] = 0;
      v6[6] = 0;
    }
    else
    {
      v14 = lua_newuserdatauv(this, 0x38u, 0);
      v14[3] = 0;
      v14[4] = 0;
      v14[5] = 0;
      v14[6] = 0;
      *v14 = 0;
      v14[1] = 0;
      v14[2] = 0;
      v8 = operator new(0x40u);
      *v8 = v8;
      v8[1] = v8;
      v8[2] = v8;
      *((_WORD *)v8 + 12) = 257;
      v14[1] = v8;
      v14[3] = 0;
      v14[4] = 0;
      v14[5] = 0;
      v14[6] = 0;
      luaL_setmetatable(this, "etw.state");
    }
    lua_pushlightuserdata(this, &qword_1800BEAB0);
    lua_rotate(this, -2, 1);
    lua_settable(this, -1001000);
  }
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "file.state") )
  {
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F6D8, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl'::`2'::impl) )
    {
      v9 = lua_newuserdatauv(this, 8u, 0);
      luaL_setmetatable(this, "file.state");
      *v9 = 0;
    }
    else
    {
      *(_QWORD *)lua_newuserdatauv(this, 8u, 0) = 0;
      luaL_setmetatable(this, "file.state");
    }
    lua_pushlightuserdata(this, byte_1800BEAD8);
    lua_rotate(this, -2, 1);
    lua_settable(this, -1001000);
  }
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "native.buffer") )
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F830, 0);
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "native.resource") )
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F7F0, 0);
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "oset.payload.state") )
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F880, 0);
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "wmi.object") )
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009FA30, 0);
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "sym.state") )
  {
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F9E0, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl'::`2'::impl) )
    {
      v10 = lua_newuserdatauv(this, 0x28u, 0);
      luaL_setmetatable(this, "sym.state");
      anonymous_namespace_::sym_module_state::sym_module_state(v10);
    }
    else
    {
      v11 = lua_newuserdatauv(this, 0x28u, 0);
      anonymous_namespace_::sym_module_state::sym_module_state(v11);
      luaL_setmetatable(this, "sym.state");
    }
    lua_pushlightuserdata(this, byte_1800BEBB8);
    lua_rotate(this, -2, 1);
    lua_settable(this, -1001000);
  }
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "security.state") )
  {
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F930, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl'::`2'::impl) )
    {
      v12 = lua_newuserdatauv(this, 0x10u, 0);
      luaL_setmetatable(this, "security.state");
      *v12 = 0;
    }
    else
    {
      *(_OWORD *)lua_newuserdatauv(this, 0x10u, 0) = 0;
      luaL_setmetatable(this, "security.state");
    }
    lua_pushlightuserdata(this, &qword_1800BEBA8);
    lua_rotate(this, -2, 1);
    lua_settable(this, -1001000);
  }
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "security.process") )
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F8F0, 0);
  lua_settop(this, -2);
  if ( (unsigned int)luaL_newmetatable(this, "cab.file") )
    luaL_setfuncs(this, (const struct luaL_Reg *)&off_18009F2C0, 0);
  lua_settop(this, -2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_JsonNative>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_JsonNative>::GetImpl'::`2'::impl) )
    windiag::lua_wdg_json_init(this, v13);
  luaL_requiref(
    this,
    "wdg",
    (int (*)(struct lua_State *))lambda_529db6aaf82f3ae389d0f044c88552cd_::_lambda_invoker_cdecl_,
    1);
  lua_settop(this, -2);
}

```

## disassembly

```asm
0x18007742c  mov     [rsp+arg_0], rbx
0x180077431  push    rbp
0x180077432  push    rsi
0x180077433  push    rdi
0x180077434  push    r12
0x180077436  push    r13
0x180077438  push    r14
0x18007743a  push    r15
0x18007743c  sub     rsp, 20h
0x180077440  mov     rsi, rcx
0x180077443  mov     edx, cs:_tls_index
0x180077449  mov     rax, gs:58h
0x180077452  mov     ecx, 4
0x180077457  mov     rax, [rax+rdx*8]
0x18007745b  xor     r12d, r12d
0x18007745e  mov     eax, [rcx+rax]
0x180077461  cmp     cs:dword_1800BEE40, eax
0x180077467  jg      loc_180077A54
0x18007746d  lea     rbp, aGblState; "gbl.state"
0x180077474  mov     rdx, rbp; char *
0x180077477  mov     rcx, rsi; struct lua_State *
0x18007747a  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x18007747f  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes4D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes4D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl(void)'::`2'::impl
0x180077486  mov     ebx, 10h
0x18007748b  lea     r13d, [rbx-0Fh]
0x18007748f  test    eax, eax
0x180077491  jnz     short loc_18007749C
0x180077493  lea     r15d, [rbx-12h]
0x180077497  jmp     loc_180077565
0x18007749c  xor     r8d, r8d; int
0x18007749f  lea     rdx, off_18009F798; struct luaL_Reg *
0x1800774a6  mov     rcx, rsi; struct lua_State *
0x1800774a9  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x1800774ae  mov     rcx, rdi
0x1800774b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes4D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(void)
0x1800774b6  xor     r8d, r8d; int
0x1800774b9  mov     rdx, rbx; unsigned __int64
0x1800774bc  mov     rcx, rsi; struct lua_State *
0x1800774bf  test    al, al
0x1800774c1  jz      short loc_1800774FD
0x1800774c3  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x1800774c8  mov     rbx, rax
0x1800774cb  mov     rdx, rbp; char *
0x1800774ce  mov     rcx, rsi; struct lua_State *
0x1800774d1  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x1800774d6  mov     [rbx], r12
0x1800774d9  mov     [rbx+8], r12
0x1800774dd  mov     ecx, 80h; Size
0x1800774e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800774e7  mov     [rax], rax
0x1800774ea  mov     [rax+8], rax
0x1800774ee  mov     [rax+10h], rax
0x1800774f2  mov     word ptr [rax+18h], 101h
0x1800774f8  mov     [rbx], rax
0x1800774fb  jmp     short loc_180077535
0x1800774fd  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x180077502  mov     rbx, rax
0x180077505  mov     [rax], r12
0x180077508  mov     [rax+8], r12
0x18007750c  mov     ecx, 80h; Size
0x180077511  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077516  mov     [rax], rax
0x180077519  mov     [rax+8], rax
0x18007751d  mov     [rax+10h], rax
0x180077521  mov     word ptr [rax+18h], 101h
0x180077527  mov     [rbx], rax
0x18007752a  mov     rdx, rbp; char *
0x18007752d  mov     rcx, rsi; struct lua_State *
0x180077530  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x180077535  lea     rdx, dword_1800BEADC; void *
0x18007753c  mov     rcx, rsi; struct lua_State *
0x18007753f  call    ?lua_pushlightuserdata@@YAXPEAUlua_State@@PEAX@Z; lua_pushlightuserdata(lua_State *,void *)
0x180077544  mov     r8d, r13d; int
0x180077547  mov     r15d, 0FFFFFFFEh
0x18007754d  mov     edx, r15d; int
0x180077550  mov     rcx, rsi; struct lua_State *
0x180077553  call    ?lua_rotate@@YAXPEAUlua_State@@HH@Z; lua_rotate(lua_State *,int,int)
0x180077558  mov     edx, 0FFF0B9D8h; int
0x18007755d  mov     rcx, rsi; struct lua_State *
0x180077560  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x180077565  mov     r14d, r15d
0x180077568  mov     rbp, rsi
0x18007756b  mov     edx, r15d; int
0x18007756e  mov     rcx, rsi; struct lua_State *
0x180077571  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180077576  lea     rdx, aLanguageModelS; "language_model.state"
0x18007757d  mov     rcx, rsi; struct lua_State *
0x180077580  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x180077585  test    eax, eax
0x180077587  jz      short loc_18007759B
0x180077589  xor     r8d, r8d; int
0x18007758c  lea     rdx, off_18009F240; struct luaL_Reg *
0x180077593  mov     rcx, rsi; struct lua_State *
0x180077596  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x18007759b  mov     edx, r14d; int
0x18007759e  mov     rcx, rbp; struct lua_State *
0x1800775a1  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x1800775a6  lea     rdx, aEtwState; "etw.state"
0x1800775ad  mov     rcx, rsi; struct lua_State *
0x1800775b0  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x1800775b5  test    eax, eax
0x1800775b7  jz      loc_1800776D4
0x1800775bd  xor     r8d, r8d; int
0x1800775c0  lea     rdx, off_18009F410; struct luaL_Reg *
0x1800775c7  mov     rcx, rsi; struct lua_State *
0x1800775ca  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x1800775cf  mov     rcx, rdi
0x1800775d2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes4D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(void)
0x1800775d7  xor     r8d, r8d; int
0x1800775da  lea     edx, [r8+38h]; unsigned __int64
0x1800775de  mov     rcx, rsi; struct lua_State *
0x1800775e1  test    al, al
0x1800775e3  jz      short loc_18007763D
0x1800775e5  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x1800775ea  mov     rdi, rax
0x1800775ed  lea     rdx, aEtwState; "etw.state"
0x1800775f4  mov     rcx, rsi; struct lua_State *
0x1800775f7  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x1800775fc  mov     [rsp+58h+arg_8], rdi
0x180077601  mov     [rdi], r12
0x180077604  mov     [rdi+8], r12
0x180077608  mov     [rdi+10h], r12
0x18007760c  mov     ecx, 40h ; '@'; Size
0x180077611  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077616  mov     [rax], rax
0x180077619  mov     [rax+8], rax
0x18007761d  mov     [rax+10h], rax
0x180077621  mov     word ptr [rax+18h], 101h
0x180077627  mov     [rdi+8], rax
0x18007762b  mov     [rdi+18h], r12
0x18007762f  mov     [rdi+20h], r12
0x180077633  mov     [rdi+28h], r12
0x180077637  mov     [rdi+30h], r12
0x18007763b  jmp     short loc_1800776A3
0x18007763d  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x180077642  mov     rdi, rax
0x180077645  mov     [rsp+58h+arg_8], rax
0x18007764a  mov     [rax+18h], r12
0x18007764e  mov     [rax+20h], r12
0x180077652  mov     [rax+28h], r12
0x180077656  mov     [rax+30h], r12
0x18007765a  mov     [rax], r12
0x18007765d  mov     [rax+8], r12
0x180077661  mov     [rax+10h], r12
0x180077665  mov     ecx, 40h ; '@'; Size
0x18007766a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007766f  mov     [rax], rax
0x180077672  mov     [rax+8], rax
0x180077676  mov     [rax+10h], rax
0x18007767a  mov     word ptr [rax+18h], 101h
0x180077680  mov     [rdi+8], rax
0x180077684  mov     [rdi+18h], r12
0x180077688  mov     [rdi+20h], r12
0x18007768c  mov     [rdi+28h], r12
0x180077690  mov     [rdi+30h], r12
0x180077694  lea     rdx, aEtwState; "etw.state"
0x18007769b  mov     rcx, rsi; struct lua_State *
0x18007769e  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x1800776a3  lea     rdx, qword_1800BEAB0; void *
0x1800776aa  mov     rcx, rsi; struct lua_State *
0x1800776ad  call    ?lua_pushlightuserdata@@YAXPEAUlua_State@@PEAX@Z; lua_pushlightuserdata(lua_State *,void *)
0x1800776b2  mov     r8d, r13d; int
0x1800776b5  mov     edx, r15d; int
0x1800776b8  mov     rcx, rsi; struct lua_State *
0x1800776bb  call    ?lua_rotate@@YAXPEAUlua_State@@HH@Z; lua_rotate(lua_State *,int,int)
0x1800776c0  mov     edx, 0FFF0B9D8h; int
0x1800776c5  mov     rcx, rsi; struct lua_State *
0x1800776c8  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x1800776cd  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes4D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes4D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl(void)'::`2'::impl
0x1800776d4  mov     edx, r14d; int
0x1800776d7  mov     rcx, rbp; struct lua_State *
0x1800776da  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x1800776df  lea     rdx, aFileState; "file.state"
0x1800776e6  mov     rcx, rsi; struct lua_State *
0x1800776e9  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x1800776ee  test    eax, eax
0x1800776f0  jz      loc_18007777B
0x1800776f6  xor     r8d, r8d; int
0x1800776f9  lea     rdx, off_18009F6D8; struct luaL_Reg *
0x180077700  mov     rcx, rsi; struct lua_State *
0x180077703  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x180077708  mov     rcx, rdi
0x18007770b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes4D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(void)
0x180077710  xor     r8d, r8d; int
0x180077713  lea     edx, [r8+8]; unsigned __int64
0x180077717  mov     rcx, rsi; struct lua_State *
0x18007771a  test    al, al
0x18007771c  jz      short loc_18007773A
0x18007771e  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x180077723  mov     rbx, rax
0x180077726  lea     rdx, aFileState; "file.state"
0x18007772d  mov     rcx, rsi; struct lua_State *
0x180077730  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x180077735  mov     [rbx], r12
0x180077738  jmp     short loc_180077751
0x18007773a  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x18007773f  mov     [rax], r12
0x180077742  lea     rdx, aFileState; "file.state"
0x180077749  mov     rcx, rsi; struct lua_State *
0x18007774c  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x180077751  lea     rdx, byte_1800BEAD8; void *
0x180077758  mov     rcx, rsi; struct lua_State *
0x18007775b  call    ?lua_pushlightuserdata@@YAXPEAUlua_State@@PEAX@Z; lua_pushlightuserdata(lua_State *,void *)
0x180077760  mov     r8d, r13d; int
0x180077763  mov     edx, r15d; int
0x180077766  mov     rcx, rsi; struct lua_State *
0x180077769  call    ?lua_rotate@@YAXPEAUlua_State@@HH@Z; lua_rotate(lua_State *,int,int)
0x18007776e  mov     edx, 0FFF0B9D8h; int
0x180077773  mov     rcx, rsi; struct lua_State *
0x180077776  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x18007777b  mov     edx, r14d; int
0x18007777e  mov     rcx, rbp; struct lua_State *
0x180077781  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180077786  lea     rdx, aNativeBuffer; "native.buffer"
0x18007778d  mov     rcx, rsi; struct lua_State *
0x180077790  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x180077795  test    eax, eax
0x180077797  jz      short loc_1800777AB
0x180077799  xor     r8d, r8d; int
0x18007779c  lea     rdx, off_18009F830; struct luaL_Reg *
0x1800777a3  mov     rcx, rsi; struct lua_State *
0x1800777a6  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x1800777ab  mov     edx, r14d; int
0x1800777ae  mov     rcx, rbp; struct lua_State *
0x1800777b1  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x1800777b6  lea     rdx, aNativeResource_0; "native.resource"
0x1800777bd  mov     rcx, rsi; struct lua_State *
0x1800777c0  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x1800777c5  test    eax, eax
0x1800777c7  jz      short loc_1800777DB
0x1800777c9  xor     r8d, r8d; int
0x1800777cc  lea     rdx, off_18009F7F0; struct luaL_Reg *
0x1800777d3  mov     rcx, rsi; struct lua_State *
0x1800777d6  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x1800777db  mov     edx, r14d; int
0x1800777de  mov     rcx, rbp; struct lua_State *
0x1800777e1  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x1800777e6  lea     rdx, aOsetPayloadSta; "oset.payload.state"
0x1800777ed  mov     rcx, rsi; struct lua_State *
0x1800777f0  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x1800777f5  test    eax, eax
0x1800777f7  jz      short loc_18007780B
0x1800777f9  xor     r8d, r8d; int
0x1800777fc  lea     rdx, off_18009F880; struct luaL_Reg *
0x180077803  mov     rcx, rsi; struct lua_State *
0x180077806  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x18007780b  mov     edx, r14d; int
0x18007780e  mov     rcx, rbp; struct lua_State *
0x180077811  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180077816  lea     rdx, aWmiObject_0; "wmi.object"
0x18007781d  mov     rcx, rsi; struct lua_State *
0x180077820  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x180077825  test    eax, eax
0x180077827  jz      short loc_18007783B
0x180077829  xor     r8d, r8d; int
0x18007782c  lea     rdx, off_18009FA30; struct luaL_Reg *
0x180077833  mov     rcx, rsi; struct lua_State *
0x180077836  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x18007783b  mov     edx, r14d; int
0x18007783e  mov     rcx, rbp; struct lua_State *
0x180077841  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180077846  lea     rdx, aSymState; "sym.state"
0x18007784d  mov     rcx, rsi; struct lua_State *
0x180077850  call    ?luaL_newmetatable@@YAHPEAUlua_State@@PEBD@Z; luaL_newmetatable(lua_State *,char const *)
0x180077855  test    eax, eax
0x180077857  jz      loc_1800778EC
0x18007785d  xor     r8d, r8d; int
0x180077860  lea     rdx, off_18009F9E0; struct luaL_Reg *
0x180077867  mov     rcx, rsi; struct lua_State *
0x18007786a  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x18007786f  mov     rcx, rdi
0x180077872  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes4D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(void)
0x180077877  xor     r8d, r8d; int
0x18007787a  lea     edx, [r8+28h]; unsigned __int64
0x18007787e  mov     rcx, rsi; struct lua_State *
0x180077881  test    al, al
0x180077883  jz      short loc_1800778A6
0x180077885  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x18007788a  mov     rbx, rax
0x18007788d  lea     rdx, aSymState; "sym.state"
0x180077894  mov     rcx, rsi; struct lua_State *
0x180077897  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x18007789c  mov     rcx, rbx
0x18007789f  call    _anonymous_namespace___sym_module_state__sym_module_state
0x1800778a4  jmp     short loc_1800778C2
0x1800778a6  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x1800778ab  mov     rcx, rax
0x1800778ae  call    _anonymous_namespace___sym_module_state__sym_module_state
0x1800778b3  lea     rdx, aSymState; "sym.state"
0x1800778ba  mov     rcx, rsi; struct lua_State *
0x1800778bd  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x1800778c2  lea     rdx, byte_1800BEBB8; void *
0x1800778c9  mov     rcx, rsi; struct lua_State *
0x1800778cc  call    ?lua_pushlightuserdata@@YAXPEAUlua_State@@PEAX@Z; lua_pushlightuserdata(lua_State *,void *)
0x1800778d1  mov     r8d, r13d; int
0x1800778d4  mov     edx, r15d; int
0x1800778d7  mov     rcx, rsi; struct lua_State *
0x1800778da  call    ?lua_rotate@@YAXPEAUlua_State@@HH@Z; lua_rotate(lua_State *,int,int)
0x1800778df  mov     edx, 0FFF0B9D8h; int
0x1800778e4  mov     rcx, rsi; struct lua_State *
  ... truncated ...
```
