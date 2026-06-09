# luaopen_package(lua_State *)

- ea: `0x18002ef80`
- end: `0x18002f181`
- name: `?luaopen_package@@YAHPEAUlua_State@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callees

- `0x180006050`
- `0x180006b30`
- `0x180006d40`
- `0x180006de0`
- `0x180006f10`
- `0x180006ff0`
- `0x180007160`
- `0x180007330`
- `0x180007490`
- `0x180008700`
- `0x180008a40`
- `0x180009440`
- `0x18002ef80`
- `0x18002f7f0`

## string_xrefs

- `0x18002f0b1`: `cpath`
- `0x18002f08d`: `LUA_PATH`
- `0x18002f0a0`: `!\?.dll;!\..\lib\lua\5.4\?.dll;!\loadall.dll;.\?.dll`
- `0x18002f0aa`: `LUA_CPATH`
- `0x18002f0cc`: `config`

## pseudocode

```c
__int64 __fastcall luaopen_package(struct lua_State *a1)
{
  int v2; // esi
  __int64 v3; // rbx

  luaL_getsubtable(a1, -1001000, "_CLIBS");
  lua_createtable(a1, 0, 1);
  lua_pushcclosure(a1, (int (*)(struct lua_State *))gctm, 0);
  lua_setfield(a1, 4294967294LL, "__gc");
  lua_setmetatable(a1, -2);
  luaL_checkversion_(a1, 504.0, 0x88u);
  lua_createtable(a1, 0, 7);
  luaL_setfuncs(a1, (const struct luaL_Reg *)&off_18009EF40, 0);
  lua_createtable(a1, 4, 0);
  v2 = 0;
  do
  {
    lua_pushvalue(a1, 4294967294LL);
    v3 = v2;
    lua_pushcclosure(a1, (int (*)(struct lua_State *))off_18009EFE8[v2], 1);
    lua_rawseti(a1, -2, ++v2);
  }
  while ( off_18009EFE8[v3 + 1] );
  lua_setfield(a1, 4294967294LL, "searchers");
  setpath(
    a1,
    "path",
    "LUA_PATH",
    "!\\lua\\?.lua;!\\lua\\?\\init.lua;!\\?.lua;!\\?\\init.lua;!\\..\\share\\lua\\5.4\\?.lua;!\\..\\share\\lua\\5.4\\?\\i"
    "nit.lua;.\\?.lua;.\\?\\init.lua");
  setpath(a1, "cpath", "LUA_CPATH", "!\\?.dll;!\\..\\lib\\lua\\5.4\\?.dll;!\\loadall.dll;.\\?.dll");
  lua_pushstring(a1, "\\\n;\n?\n!\n-\n");
  lua_setfield(a1, 4294967294LL, "config");
  luaL_getsubtable(a1, -1001000, "_LOADED");
  lua_setfield(a1, 4294967294LL, "loaded");
  luaL_getsubtable(a1, -1001000, "_PRELOAD");
  lua_setfield(a1, 4294967294LL, "preload");
  lua_rawgeti(a1, -1001000, 2);
  lua_pushvalue(a1, 4294967294LL);
  luaL_setfuncs(a1, (const struct luaL_Reg *)&off_18009EFC0, 1);
  lua_settop(a1, -2);
  return 1;
}

```

## disassembly

```asm
0x18002ef80  push    rbx
0x18002ef82  push    rsi
0x18002ef83  push    rdi
0x18002ef84  push    r14
0x18002ef86  sub     rsp, 28h
0x18002ef8a  lea     r8, aClibs; "_CLIBS"
0x18002ef91  mov     edx, 0FFF0B9D8h; int
0x18002ef96  mov     rdi, rcx
0x18002ef99  call    ?luaL_getsubtable@@YAHPEAUlua_State@@HPEBD@Z; luaL_getsubtable(lua_State *,int,char const *)
0x18002ef9e  xor     edx, edx; int
0x18002efa0  mov     r8d, 1; int
0x18002efa6  mov     rcx, rdi; struct lua_State *
0x18002efa9  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18002efae  xor     r8d, r8d; int
0x18002efb1  lea     rdx, gctm; int (*)(struct lua_State *)
0x18002efb8  mov     rcx, rdi; struct lua_State *
0x18002efbb  call    ?lua_pushcclosure@@YAXPEAUlua_State@@P6AH0@ZH@Z; lua_pushcclosure(lua_State *,int (*)(lua_State *),int)
0x18002efc0  lea     r8, aGc; "__gc"
0x18002efc7  mov     edx, 0FFFFFFFEh; int
0x18002efcc  mov     rcx, rdi; struct lua_State *
0x18002efcf  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18002efd4  mov     edx, 0FFFFFFFEh; int
0x18002efd9  mov     rcx, rdi; struct lua_State *
0x18002efdc  call    ?lua_setmetatable@@YAHPEAUlua_State@@H@Z; lua_setmetatable(lua_State *,int)
0x18002efe1  movsd   xmm1, cs:__real@407f800000000000; double
0x18002efe9  mov     r8d, 88h; unsigned __int64
0x18002efef  mov     rcx, rdi; struct lua_State *
0x18002eff2  call    ?luaL_checkversion_@@YAXPEAUlua_State@@N_K@Z; luaL_checkversion_(lua_State *,double,unsigned __int64)
0x18002eff7  xor     edx, edx; int
0x18002eff9  mov     r8d, 7; int
0x18002efff  mov     rcx, rdi; struct lua_State *
0x18002f002  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18002f007  xor     r8d, r8d; int
0x18002f00a  lea     rdx, off_18009EF40; struct luaL_Reg *
0x18002f011  mov     rcx, rdi; struct lua_State *
0x18002f014  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x18002f019  xor     r8d, r8d; int
0x18002f01c  mov     edx, 4; int
0x18002f021  mov     rcx, rdi; struct lua_State *
0x18002f024  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18002f029  xor     esi, esi
0x18002f02b  lea     r14, off_18009EFE8
0x18002f032  mov     edx, 0FFFFFFFEh; int
0x18002f037  mov     rcx, rdi; struct lua_State *
0x18002f03a  call    ?lua_pushvalue@@YAXPEAUlua_State@@H@Z; lua_pushvalue(lua_State *,int)
0x18002f03f  movsxd  rbx, esi
0x18002f042  mov     r8d, 1; int
0x18002f048  mov     rcx, rdi; struct lua_State *
0x18002f04b  mov     rdx, [r14+rbx*8]; int (*)(struct lua_State *)
0x18002f04f  call    ?lua_pushcclosure@@YAXPEAUlua_State@@P6AH0@ZH@Z; lua_pushcclosure(lua_State *,int (*)(lua_State *),int)
0x18002f054  lea     r8, [rbx+1]; __int64
0x18002f058  mov     edx, 0FFFFFFFEh; int
0x18002f05d  mov     rcx, rdi; struct lua_State *
0x18002f060  call    ?lua_rawseti@@YAXPEAUlua_State@@H_J@Z; lua_rawseti(lua_State *,int,__int64)
0x18002f065  inc     esi
0x18002f067  cmp     qword ptr [r14+rbx*8+8], 0
0x18002f06d  jnz     short loc_18002F032
0x18002f06f  lea     r8, aSearchers; "searchers"
0x18002f076  mov     edx, 0FFFFFFFEh; int
0x18002f07b  mov     rcx, rdi; struct lua_State *
0x18002f07e  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18002f083  lea     r9, aLuaLuaLuaInitL; "!\\lua\\?.lua;!\\lua\\?\\init.lua;!\\?."...
0x18002f08a  mov     rcx, rdi; struct lua_State *
0x18002f08d  lea     r8, VarName; "LUA_PATH"
0x18002f094  lea     rdx, aPath; "path"
0x18002f09b  call    setpath
0x18002f0a0  lea     r9, aDllLibLua54Dll; "!\\?.dll;!\\..\\lib\\lua\\5.4\\?.dll;!"...
0x18002f0a7  mov     rcx, rdi; struct lua_State *
0x18002f0aa  lea     r8, aLuaCpath; "LUA_CPATH"
0x18002f0b1  lea     rdx, aCpath; "cpath"
0x18002f0b8  call    setpath
0x18002f0bd  lea     rdx, asc_1800A4E28; "\\\n;\n?\n!\n-\n"
0x18002f0c4  mov     rcx, rdi; struct lua_State *
0x18002f0c7  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18002f0cc  lea     r8, aConfig; "config"
0x18002f0d3  mov     edx, 0FFFFFFFEh; int
0x18002f0d8  mov     rcx, rdi; struct lua_State *
0x18002f0db  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18002f0e0  lea     r8, aLoaded_0; "_LOADED"
0x18002f0e7  mov     edx, 0FFF0B9D8h; int
0x18002f0ec  mov     rcx, rdi; struct lua_State *
0x18002f0ef  call    ?luaL_getsubtable@@YAHPEAUlua_State@@HPEBD@Z; luaL_getsubtable(lua_State *,int,char const *)
0x18002f0f4  lea     r8, aLoaded; "loaded"
0x18002f0fb  mov     edx, 0FFFFFFFEh; int
0x18002f100  mov     rcx, rdi; struct lua_State *
0x18002f103  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18002f108  lea     r8, aPreload; "_PRELOAD"
0x18002f10f  mov     edx, 0FFF0B9D8h; int
0x18002f114  mov     rcx, rdi; struct lua_State *
0x18002f117  call    ?luaL_getsubtable@@YAHPEAUlua_State@@HPEBD@Z; luaL_getsubtable(lua_State *,int,char const *)
0x18002f11c  lea     r8, aPreload_0; "preload"
0x18002f123  mov     edx, 0FFFFFFFEh; int
0x18002f128  mov     rcx, rdi; struct lua_State *
0x18002f12b  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18002f130  mov     edx, 0FFF0B9D8h; int
0x18002f135  mov     r8d, 2; __int64
0x18002f13b  mov     rcx, rdi; struct lua_State *
0x18002f13e  call    ?lua_rawgeti@@YAHPEAUlua_State@@H_J@Z; lua_rawgeti(lua_State *,int,__int64)
0x18002f143  mov     edx, 0FFFFFFFEh; int
0x18002f148  mov     rcx, rdi; struct lua_State *
0x18002f14b  call    ?lua_pushvalue@@YAXPEAUlua_State@@H@Z; lua_pushvalue(lua_State *,int)
0x18002f150  mov     r8d, 1; int
0x18002f156  lea     rdx, off_18009EFC0; struct luaL_Reg *
0x18002f15d  mov     rcx, rdi; struct lua_State *
0x18002f160  call    ?luaL_setfuncs@@YAXPEAUlua_State@@PEBUluaL_Reg@@H@Z; luaL_setfuncs(lua_State *,luaL_Reg const *,int)
0x18002f165  mov     edx, 0FFFFFFFEh; int
0x18002f16a  mov     rcx, rdi; struct lua_State *
0x18002f16d  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x18002f172  mov     eax, 1
0x18002f177  add     rsp, 28h
0x18002f17b  pop     r14
0x18002f17d  pop     rdi
0x18002f17e  pop     rsi
0x18002f17f  pop     rbx
0x18002f180  retn
```
