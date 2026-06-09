# lookforfunc

- ea: `0x18002ee30`
- end: `0x18002ef73`
- name: `lookforfunc`
- size: `323`
- prototype: `__int64 __fastcall(struct lua_State *, char *, LPCSTR lpProcName)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18002e850`
- `0x18002ed80`

## callees

- `0x180006430`
- `0x180006b00`
- `0x180006b30`
- `0x180006c70`
- `0x180006de0`
- `0x180006ff0`
- `0x180007160`
- `0x180007490`
- `0x1800078f0`
- `0x180008ca0`
- `0x18002ee30`
- `0x18002f190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ef3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ef3c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ee91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002ee91`

## pseudocode

```c
__int64 __fastcall lookforfunc(struct lua_State *a1, char *a2, LPCSTR lpProcName)
{
  HMODULE Library; // rdi
  __int64 v8; // rax
  int (*ProcAddress)(struct lua_State *); // rax

  lua_getfield(a1, -1001000, "_CLIBS");
  lua_getfield(a1, -1, a2);
  Library = (HMODULE)lua_touserdata(a1, -1);
  lua_settop(a1, -3);
  if ( !Library )
  {
    Library = LoadLibraryExA(a2, 0, 0);
    if ( !Library )
    {
      pusherror(a1);
      return 1;
    }
    lua_getfield(a1, -1001000, "_CLIBS");
    lua_pushlightuserdata(a1, Library);
    lua_pushvalue(a1, -1);
    lua_setfield(a1, -3, a2);
    v8 = luaL_len(a1, -2);
    lua_rawseti(a1, -2, v8 + 1);
    lua_settop(a1, -2);
  }
  if ( *lpProcName == 42 )
  {
    lua_pushboolean(a1, 1);
    return 0;
  }
  else
  {
    ProcAddress = (int (*)(struct lua_State *))GetProcAddress(Library, lpProcName);
    if ( ProcAddress )
    {
      lua_pushcclosure(a1, ProcAddress, 0);
      return 0;
    }
    else
    {
      pusherror(a1);
      return 2;
    }
  }
}

```

## disassembly

```asm
0x18002ee30  push    rbx
0x18002ee32  push    rbp
0x18002ee33  push    rsi
0x18002ee34  push    rdi
0x18002ee35  sub     rsp, 28h
0x18002ee39  mov     rsi, r8
0x18002ee3c  mov     rbp, rdx
0x18002ee3f  lea     r8, aClibs; "_CLIBS"
0x18002ee46  mov     edx, 0FFF0B9D8h; int
0x18002ee4b  mov     rbx, rcx
0x18002ee4e  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x18002ee53  mov     r8, rbp; char *
0x18002ee56  mov     edx, 0FFFFFFFFh; int
0x18002ee5b  mov     rcx, rbx; struct lua_State *
0x18002ee5e  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x18002ee63  mov     edx, 0FFFFFFFFh; int
0x18002ee68  mov     rcx, rbx; struct lua_State *
0x18002ee6b  call    ?lua_touserdata@@YAPEAXPEAUlua_State@@H@Z; lua_touserdata(lua_State *,int)
0x18002ee70  mov     edx, 0FFFFFFFDh; int
0x18002ee75  mov     rcx, rbx; struct lua_State *
0x18002ee78  mov     rdi, rax
0x18002ee7b  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x18002ee80  test    rdi, rdi
0x18002ee83  jnz     loc_18002EF19
0x18002ee89  xor     r8d, r8d; dwFlags
0x18002ee8c  xor     edx, edx; hFile
0x18002ee8e  mov     rcx, rbp; lpLibFileName
0x18002ee91  call    cs:__imp_LoadLibraryExA
0x18002ee97  mov     rdi, rax
0x18002ee9a  mov     rcx, rbx; struct lua_State *
0x18002ee9d  test    rax, rax
0x18002eea0  jnz     short loc_18002EEB5
0x18002eea2  call    pusherror
0x18002eea7  mov     eax, 1
0x18002eeac  add     rsp, 28h
0x18002eeb0  pop     rdi
0x18002eeb1  pop     rsi
0x18002eeb2  pop     rbp
0x18002eeb3  pop     rbx
0x18002eeb4  retn
0x18002eeb5  lea     r8, aClibs; "_CLIBS"
0x18002eebc  mov     edx, 0FFF0B9D8h; int
0x18002eec1  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x18002eec6  mov     rdx, rdi; void *
0x18002eec9  mov     rcx, rbx; struct lua_State *
0x18002eecc  call    ?lua_pushlightuserdata@@YAXPEAUlua_State@@PEAX@Z; lua_pushlightuserdata(lua_State *,void *)
0x18002eed1  mov     edx, 0FFFFFFFFh; int
0x18002eed6  mov     rcx, rbx; struct lua_State *
0x18002eed9  call    ?lua_pushvalue@@YAXPEAUlua_State@@H@Z; lua_pushvalue(lua_State *,int)
0x18002eede  mov     r8, rbp; char *
0x18002eee1  mov     edx, 0FFFFFFFDh; int
0x18002eee6  mov     rcx, rbx; struct lua_State *
0x18002eee9  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18002eeee  mov     edx, 0FFFFFFFEh; int
0x18002eef3  mov     rcx, rbx; struct lua_State *
0x18002eef6  call    ?luaL_len@@YA_JPEAUlua_State@@H@Z; luaL_len(lua_State *,int)
0x18002eefb  mov     edx, 0FFFFFFFEh; int
0x18002ef00  mov     rcx, rbx; struct lua_State *
0x18002ef03  lea     r8, [rax+1]; __int64
0x18002ef07  call    ?lua_rawseti@@YAXPEAUlua_State@@H_J@Z; lua_rawseti(lua_State *,int,__int64)
0x18002ef0c  mov     edx, 0FFFFFFFEh; int
0x18002ef11  mov     rcx, rbx; struct lua_State *
0x18002ef14  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x18002ef19  cmp     byte ptr [rsi], 2Ah ; '*'
0x18002ef1c  jnz     short loc_18002EF36
0x18002ef1e  mov     edx, 1; int
0x18002ef23  mov     rcx, rbx; struct lua_State *
0x18002ef26  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x18002ef2b  xor     eax, eax
0x18002ef2d  add     rsp, 28h
0x18002ef31  pop     rdi
0x18002ef32  pop     rsi
0x18002ef33  pop     rbp
0x18002ef34  pop     rbx
0x18002ef35  retn
0x18002ef36  mov     rdx, rsi; lpProcName
0x18002ef39  mov     rcx, rdi; hModule
0x18002ef3c  call    cs:__imp_GetProcAddress
0x18002ef42  mov     rcx, rbx; struct lua_State *
0x18002ef45  test    rax, rax
0x18002ef48  jnz     short loc_18002EF5D
0x18002ef4a  call    pusherror
0x18002ef4f  mov     eax, 2
0x18002ef54  add     rsp, 28h
0x18002ef58  pop     rdi
0x18002ef59  pop     rsi
0x18002ef5a  pop     rbp
0x18002ef5b  pop     rbx
0x18002ef5c  retn
0x18002ef5d  xor     r8d, r8d; int
0x18002ef60  mov     rdx, rax; int (*)(struct lua_State *)
0x18002ef63  call    ?lua_pushcclosure@@YAXPEAUlua_State@@P6AH0@ZH@Z; lua_pushcclosure(lua_State *,int (*)(lua_State *),int)
0x18002ef68  xor     eax, eax
0x18002ef6a  add     rsp, 28h
0x18002ef6e  pop     rdi
0x18002ef6f  pop     rsi
0x18002ef70  pop     rbp
0x18002ef71  pop     rbx
0x18002ef72  retn
```
