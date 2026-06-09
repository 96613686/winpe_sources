# _anonymous_namespace_::wnf_update_data

- ea: `0x18008ea60`
- end: `0x18008eb4e`
- name: `_anonymous_namespace_::wnf_update_data`
- size: `238`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x180004510`
- `0x180006690`
- `0x180006b00`
- `0x180007950`
- `0x1800083a0`
- `0x180008430`
- `0x18008ea60`

## import_xrefs

- `ntdll!NtUpdateWnfStateData` at `0x18008eb15`
- `ntdll!NtUpdateWnfStateData` at `0x18008eb15`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::wnf_update_data(struct lua_State *a1)
{
  const char *v2; // rsi
  unsigned __int8 v3; // di
  int v4; // ecx
  int updated; // eax
  unsigned __int64 v7; // [rsp+40h] [rbp-28h] BYREF
  __int64 v8; // [rsp+48h] [rbp-20h] BYREF

  v8 = luaL_checkinteger(a1, 1);
  v7 = 0;
  v2 = luaL_checklstring(a1, 2, &v7);
  v3 = 0;
  if ( (int)lua_gettop(a1) > 2 && (unsigned int)lua_type(a1, 3) )
  {
    v4 = luaL_checkinteger(a1, 3);
    v3 = 1;
  }
  else
  {
    v4 = 0;
  }
  updated = NtUpdateWnfStateData(&v8, v2, (unsigned int)v7, 0, 0, v4, v3);
  lua_pushboolean(a1, updated >= 0);
  return 1;
}

```

## disassembly

```asm
0x18008ea60  mov     [rsp+arg_8], rbx
0x18008ea65  mov     [rsp+arg_10], rsi
0x18008ea6a  push    rdi
0x18008ea6b  sub     rsp, 60h
0x18008ea6f  mov     rax, cs:__security_cookie
0x18008ea76  xor     rax, rsp
0x18008ea79  mov     [rsp+68h+var_18], rax
0x18008ea7e  mov     edx, 1; int
0x18008ea83  mov     rbx, rcx
0x18008ea86  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18008ea8b  mov     rcx, rax
0x18008ea8e  mov     dword ptr [rsp+68h+var_20], eax
0x18008ea92  shr     rcx, 20h
0x18008ea96  lea     r8, [rsp+68h+var_28]; unsigned __int64 *
0x18008ea9b  mov     dword ptr [rsp+68h+var_20+4], ecx
0x18008ea9f  mov     edx, 2; int
0x18008eaa4  mov     rcx, rbx; struct lua_State *
0x18008eaa7  mov     [rsp+68h+var_28], 0
0x18008eab0  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18008eab5  mov     rcx, rbx; struct lua_State *
0x18008eab8  mov     rsi, rax
0x18008eabb  xor     dil, dil
0x18008eabe  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18008eac3  cmp     eax, 2
0x18008eac6  jle     short loc_18008EAEE
0x18008eac8  mov     edx, 3; int
0x18008eacd  mov     rcx, rbx; struct lua_State *
0x18008ead0  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18008ead5  test    eax, eax
0x18008ead7  jz      short loc_18008EAEE
0x18008ead9  mov     edx, 3; int
0x18008eade  mov     rcx, rbx; struct lua_State *
0x18008eae1  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18008eae6  mov     rcx, rax
0x18008eae9  mov     dil, 1
0x18008eaec  jmp     short loc_18008EAF0
0x18008eaee  xor     ecx, ecx
0x18008eaf0  mov     r8d, dword ptr [rsp+68h+var_28]
0x18008eaf5  xor     r9d, r9d
0x18008eaf8  movzx   eax, dil
0x18008eafc  mov     rdx, rsi
0x18008eaff  mov     [rsp+68h+var_38], eax
0x18008eb03  mov     [rsp+68h+var_40], ecx
0x18008eb07  lea     rcx, [rsp+68h+var_20]
0x18008eb0c  mov     [rsp+68h+var_48], 0
0x18008eb15  call    cs:__imp_NtUpdateWnfStateData
0x18008eb1b  not     eax
0x18008eb1d  mov     rcx, rbx; struct lua_State *
0x18008eb20  shr     eax, 1Fh
0x18008eb23  mov     edx, eax; int
0x18008eb25  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x18008eb2a  mov     eax, 1
0x18008eb2f  mov     rcx, [rsp+68h+var_18]
0x18008eb34  xor     rcx, rsp; StackCookie
0x18008eb37  call    __security_check_cookie
0x18008eb3c  lea     r11, [rsp+68h+var_8]
0x18008eb41  mov     rbx, [r11+18h]
0x18008eb45  mov     rsi, [r11+20h]
0x18008eb49  mov     rsp, r11
0x18008eb4c  pop     rdi
0x18008eb4d  retn
```
