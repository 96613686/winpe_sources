# add_value

- ea: `0x180029d50`
- end: `0x18002a005`
- name: `add_value`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x1800286a0`

## callees

- `0x1800054f0`
- `0x180005d80`
- `0x180006600`
- `0x1800067f0`
- `0x180006c50`
- `0x180006c90`
- `0x180006de0`
- `0x180007490`
- `0x180007650`
- `0x180007740`
- `0x180007950`
- `0x180007990`
- `0x180008070`
- `0x180008130`
- `0x180008790`
- `0x180009240`
- `0x180029d50`
- `0x18002a5d0`
- `0x18002b5c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180029e2f`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180029e2f`

## string_xrefs

- `0x180029e7c`: `invalid use of '%c' in replacement string`
- `0x180029fce`: `invalid replacement value (a %s)`

## pseudocode

```c
__int64 __fastcall add_value(__int64 a1, __int64 a2, const char *a3, __int64 a4, int a5)
{
  struct lua_State *v5; // rbp
  struct lua_State *v10; // rcx
  const char *v11; // rax
  size_t v12; // r12
  const char *v13; // r14
  unsigned __int8 *i; // rdi
  unsigned int v15; // eax
  char *v16; // rdi
  unsigned __int64 onecapture; // rax
  int v18; // eax
  unsigned __int64 v19; // rsi
  const char *v20; // r14
  unsigned __int64 v21; // rdi
  int v23; // eax
  const char *v24; // rax
  char *v25; // [rsp+30h] [rbp-38h] BYREF
  size_t MaxCount; // [rsp+70h] [rbp+8h] BYREF

  v5 = *(struct lua_State **)(a1 + 24);
  if ( a5 == 5 )
  {
    if ( *(_BYTE *)(a1 + 36) )
    {
      v21 = *(_QWORD *)(a1 + 48);
      v20 = *(const char **)(a1 + 40);
      if ( v21 == -1 )
        luaL_error(*(struct lua_State **)(a1 + 24), "unfinished capture");
      if ( v21 == -2 )
        lua_pushinteger(*(struct lua_State **)(a1 + 24), (__int64)&v20[-*(_QWORD *)a1 + 1]);
      v19 = a4 - (_QWORD)a3;
    }
    else
    {
      v19 = a4 - (_QWORD)a3;
      v20 = a3;
      v21 = a4 - (_QWORD)a3;
    }
    if ( v21 != -2 )
      lua_pushlstring(*(struct lua_State **)(a1 + 24), v20, v21);
    lua_gettable(v5, 3);
  }
  else
  {
    v10 = *(struct lua_State **)(a1 + 24);
    if ( a5 != 6 )
    {
      v11 = lua_tolstring(v10, 3, &MaxCount);
      v12 = MaxCount;
      v13 = v11;
      for ( i = (unsigned __int8 *)memchr_0(v11, 37, MaxCount); i; i = (unsigned __int8 *)memchr_0(v16 + 1, 37, v12) )
      {
        luaL_addlstring((struct luaL_Buffer *)a2, v13, i - (unsigned __int8 *)v13);
        v15 = i[1];
        v16 = (char *)(i + 1);
        if ( (_BYTE)v15 == 37 )
        {
          if ( *(_QWORD *)(a2 + 16) >= *(_QWORD *)(a2 + 8) )
            luaL_prepbuffsize((struct luaL_Buffer *)a2, 1u);
          *(_BYTE *)(*(_QWORD *)(a2 + 16) + *(_QWORD *)a2) = *v16;
          ++*(_QWORD *)(a2 + 16);
        }
        else if ( (_BYTE)v15 == 48 )
        {
          luaL_addlstring((struct luaL_Buffer *)a2, a3, a4 - (_QWORD)a3);
        }
        else
        {
          if ( !(unsigned int)_o_isdigit(v15) )
            luaL_error(v5, "invalid use of '%c' in replacement string", 37);
          onecapture = get_onecapture(a1, *v16 - 49, (_DWORD)a3, a4, (__int64)&v25);
          if ( onecapture == -2 )
            luaL_addvalue((struct luaL_Buffer *)a2);
          else
            luaL_addlstring((struct luaL_Buffer *)a2, v25, onecapture);
        }
        v12 = v13 - v16 + MaxCount - 1;
        v13 = v16 + 1;
        MaxCount = v12;
      }
      luaL_addlstring((struct luaL_Buffer *)a2, v13, v12);
      return 1;
    }
    lua_pushvalue(v10, 3);
    v18 = push_captures(a1, a3, a4);
    lua_callk(v5, v18, 1, 0, 0);
    v19 = a4 - (_QWORD)a3;
  }
  if ( !(unsigned int)lua_toboolean(v5, -1) )
  {
    lua_settop(v5, -2);
    luaL_addlstring((struct luaL_Buffer *)a2, a3, v19);
    return 0;
  }
  if ( !(unsigned int)lua_isstring(v5, -1) )
  {
    v23 = lua_type(v5, -1);
    v24 = lua_typename(v5, v23);
    luaL_error(v5, "invalid replacement value (a %s)", v24);
  }
  luaL_addvalue((struct luaL_Buffer *)a2);
  return 1;
}

```

## disassembly

```asm
0x180029d50  mov     [rsp+arg_10], rbx
0x180029d55  mov     [rsp+arg_18], rbp
0x180029d5a  push    rsi
0x180029d5b  push    rdi
0x180029d5c  push    r13
0x180029d5e  push    r14
0x180029d60  push    r15
0x180029d62  sub     rsp, 40h
0x180029d66  mov     rbp, [rcx+18h]
0x180029d6a  mov     rbx, rdx
0x180029d6d  mov     edx, [rsp+68h+arg_20]
0x180029d74  mov     rsi, r9
0x180029d77  mov     r15, r8
0x180029d7a  mov     r13, rcx
0x180029d7d  sub     edx, 5
0x180029d80  jz      loc_180029F0A
0x180029d86  cmp     edx, 1
0x180029d89  mov     rcx, rbp; struct lua_State *
0x180029d8c  mov     edx, 3; int
0x180029d91  jz      loc_180029ED6
0x180029d97  lea     r8, [rsp+68h+MaxCount]; unsigned __int64 *
0x180029d9c  mov     [rsp+68h+arg_8], r12
0x180029da1  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x180029da6  mov     r12, [rsp+68h+MaxCount]
0x180029dab  mov     edx, 25h ; '%'; Val
0x180029db0  mov     r8, r12; MaxCount
0x180029db3  mov     rcx, rax; Buf
0x180029db6  mov     r14, rax
0x180029db9  call    memchr_0
0x180029dbe  mov     rdi, rax
0x180029dc1  test    rax, rax
0x180029dc4  jz      loc_180029EBE
0x180029dca  nop     word ptr [rax+rax+00h]
0x180029dd0  mov     r8, rdi
0x180029dd3  mov     rdx, r14; char *
0x180029dd6  sub     r8, r14; unsigned __int64
0x180029dd9  mov     rcx, rbx; struct luaL_Buffer *
0x180029ddc  call    ?luaL_addlstring@@YAXPEAUluaL_Buffer@@PEBD_K@Z; luaL_addlstring(luaL_Buffer *,char const *,unsigned __int64)
0x180029de1  movzx   eax, byte ptr [rdi+1]
0x180029de5  inc     rdi
0x180029de8  cmp     al, 25h ; '%'
0x180029dea  jnz     short loc_180029E16
0x180029dec  mov     rax, [rbx+8]
0x180029df0  cmp     [rbx+10h], rax
0x180029df4  jb      short loc_180029E03
0x180029df6  mov     edx, 1; unsigned __int64
0x180029dfb  mov     rcx, rbx; struct luaL_Buffer *
0x180029dfe  call    ?luaL_prepbuffsize@@YAPEADPEAUluaL_Buffer@@_K@Z; luaL_prepbuffsize(luaL_Buffer *,unsigned __int64)
0x180029e03  mov     rdx, [rbx+10h]
0x180029e07  movzx   eax, byte ptr [rdi]
0x180029e0a  mov     rcx, [rbx]
0x180029e0d  mov     [rdx+rcx], al
0x180029e10  inc     qword ptr [rbx+10h]
0x180029e14  jmp     short loc_180029E8B
0x180029e16  cmp     al, 30h ; '0'
0x180029e18  jnz     short loc_180029E2D
0x180029e1a  mov     r8, rsi
0x180029e1d  mov     rdx, r15; char *
0x180029e20  sub     r8, r15; unsigned __int64
0x180029e23  mov     rcx, rbx; struct luaL_Buffer *
0x180029e26  call    ?luaL_addlstring@@YAXPEAUluaL_Buffer@@PEBD_K@Z; luaL_addlstring(luaL_Buffer *,char const *,unsigned __int64)
0x180029e2b  jmp     short loc_180029E8B
0x180029e2d  mov     ecx, eax
0x180029e2f  call    cs:__imp__o_isdigit
0x180029e35  test    eax, eax
0x180029e37  jz      short loc_180029E76
0x180029e39  movsx   edx, byte ptr [rdi]
0x180029e3c  lea     rax, [rsp+68h+var_38]
0x180029e41  sub     edx, 31h ; '1'
0x180029e44  mov     [rsp+68h+var_48], rax
0x180029e49  mov     r9, rsi
0x180029e4c  mov     r8, r15
0x180029e4f  mov     rcx, r13
0x180029e52  call    get_onecapture
0x180029e57  mov     rcx, rbx; struct luaL_Buffer *
0x180029e5a  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x180029e5e  jnz     short loc_180029E67
0x180029e60  call    ?luaL_addvalue@@YAXPEAUluaL_Buffer@@@Z; luaL_addvalue(luaL_Buffer *)
0x180029e65  jmp     short loc_180029E8B
0x180029e67  mov     rdx, [rsp+68h+var_38]; char *
0x180029e6c  mov     r8, rax; unsigned __int64
0x180029e6f  call    ?luaL_addlstring@@YAXPEAUluaL_Buffer@@PEBD_K@Z; luaL_addlstring(luaL_Buffer *,char const *,unsigned __int64)
0x180029e74  jmp     short loc_180029E8B
0x180029e76  mov     r8d, 25h ; '%'
0x180029e7c  lea     rdx, aInvalidUseOfCI; "invalid use of '%c' in replacement stri"...
0x180029e83  mov     rcx, rbp; struct lua_State *
0x180029e86  call    ?luaL_error@@YAHPEAUlua_State@@PEBDZZ; luaL_error(lua_State *,char const *,...)
0x180029e8b  mov     r12, [rsp+68h+MaxCount]
0x180029e90  sub     r14, rdi
0x180029e93  dec     r12
0x180029e96  mov     edx, 25h ; '%'; Val
0x180029e9b  add     r12, r14
0x180029e9e  lea     r14, [rdi+1]
0x180029ea2  mov     rcx, r14; Buf
0x180029ea5  mov     [rsp+68h+MaxCount], r12
0x180029eaa  mov     r8, r12; MaxCount
0x180029ead  call    memchr_0
0x180029eb2  mov     rdi, rax
0x180029eb5  test    rax, rax
0x180029eb8  jnz     loc_180029DD0
0x180029ebe  mov     r8, r12; unsigned __int64
0x180029ec1  mov     rdx, r14; char *
0x180029ec4  mov     rcx, rbx; struct luaL_Buffer *
0x180029ec7  call    ?luaL_addlstring@@YAXPEAUluaL_Buffer@@PEBD_K@Z; luaL_addlstring(luaL_Buffer *,char const *,unsigned __int64)
0x180029ecc  mov     r12, [rsp+68h+arg_8]
0x180029ed1  jmp     loc_180029FE7
0x180029ed6  call    ?lua_pushvalue@@YAXPEAUlua_State@@H@Z; lua_pushvalue(lua_State *,int)
0x180029edb  mov     r8, rsi
0x180029ede  mov     rdx, r15
0x180029ee1  mov     rcx, r13
0x180029ee4  call    push_captures
0x180029ee9  xor     r9d, r9d; __int64
0x180029eec  mov     [rsp+68h+var_48], 0; int (*)(struct lua_State *, int, __int64)
0x180029ef5  mov     r8d, 1; int
0x180029efb  mov     edx, eax; int
0x180029efd  mov     rcx, rbp; struct lua_State *
0x180029f00  call    ?lua_callk@@YAXPEAUlua_State@@HH_JP6AH0H1@Z@Z; lua_callk(lua_State *,int,int,__int64,int (*)(lua_State *,int,__int64))
0x180029f05  sub     rsi, r15
0x180029f08  jmp     short loc_180029F76
0x180029f0a  cmp     byte ptr [rcx+24h], 0
0x180029f0e  ja      short loc_180029F1B
0x180029f10  sub     rsi, r15
0x180029f13  mov     r14, r15
0x180029f16  mov     rdi, rsi
0x180029f19  jmp     short loc_180029F54
0x180029f1b  mov     rdi, [rcx+30h]
0x180029f1f  mov     r14, [rcx+28h]
0x180029f23  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180029f27  jnz     short loc_180029F3A
0x180029f29  lea     rdx, aUnfinishedCapt; "unfinished capture"
0x180029f30  mov     rcx, rbp; struct lua_State *
0x180029f33  call    ?luaL_error@@YAHPEAUlua_State@@PEBDZZ; luaL_error(lua_State *,char const *,...)
0x180029f38  jmp     short loc_180029F51
0x180029f3a  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180029f3e  jnz     short loc_180029F51
0x180029f40  mov     rdx, r14
0x180029f43  sub     rdx, [rcx]
0x180029f46  mov     rcx, rbp; struct lua_State *
0x180029f49  inc     rdx; __int64
0x180029f4c  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180029f51  sub     rsi, r15
0x180029f54  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180029f58  jz      short loc_180029F69
0x180029f5a  mov     rcx, [r13+18h]; struct lua_State *
0x180029f5e  mov     r8, rdi; unsigned __int64
0x180029f61  mov     rdx, r14; char *
0x180029f64  call    ?lua_pushlstring@@YAPEBDPEAUlua_State@@PEBD_K@Z; lua_pushlstring(lua_State *,char const *,unsigned __int64)
0x180029f69  mov     edx, 3; int
0x180029f6e  mov     rcx, rbp; struct lua_State *
0x180029f71  call    ?lua_gettable@@YAHPEAUlua_State@@H@Z; lua_gettable(lua_State *,int)
0x180029f76  mov     edx, 0FFFFFFFFh; int
0x180029f7b  mov     rcx, rbp; struct lua_State *
0x180029f7e  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180029f83  mov     rcx, rbp; struct lua_State *
0x180029f86  test    eax, eax
0x180029f88  jnz     short loc_180029FA6
0x180029f8a  mov     edx, 0FFFFFFFEh; int
0x180029f8f  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180029f94  mov     r8, rsi; unsigned __int64
0x180029f97  mov     rdx, r15; char *
0x180029f9a  mov     rcx, rbx; struct luaL_Buffer *
0x180029f9d  call    ?luaL_addlstring@@YAXPEAUluaL_Buffer@@PEBD_K@Z; luaL_addlstring(luaL_Buffer *,char const *,unsigned __int64)
0x180029fa2  xor     eax, eax
0x180029fa4  jmp     short loc_180029FEC
0x180029fa6  mov     edx, 0FFFFFFFFh; int
0x180029fab  call    ?lua_isstring@@YAHPEAUlua_State@@H@Z; lua_isstring(lua_State *,int)
0x180029fb0  test    eax, eax
0x180029fb2  jnz     short loc_180029FDF
0x180029fb4  mov     edx, 0FFFFFFFFh; int
0x180029fb9  mov     rcx, rbp; struct lua_State *
0x180029fbc  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180029fc1  mov     edx, eax; int
0x180029fc3  mov     rcx, rbp; struct lua_State *
0x180029fc6  call    ?lua_typename@@YAPEBDPEAUlua_State@@H@Z; lua_typename(lua_State *,int)
0x180029fcb  mov     r8, rax
0x180029fce  lea     rdx, aInvalidReplace; "invalid replacement value (a %s)"
0x180029fd5  mov     rcx, rbp; struct lua_State *
0x180029fd8  call    ?luaL_error@@YAHPEAUlua_State@@PEBDZZ; luaL_error(lua_State *,char const *,...)
0x180029fdd  jmp     short loc_180029FEC
0x180029fdf  mov     rcx, rbx; struct luaL_Buffer *
0x180029fe2  call    ?luaL_addvalue@@YAXPEAUluaL_Buffer@@@Z; luaL_addvalue(luaL_Buffer *)
0x180029fe7  mov     eax, 1
0x180029fec  lea     r11, [rsp+68h+var_28]
0x180029ff1  mov     rbx, [r11+40h]
0x180029ff5  mov     rbp, [r11+48h]
0x180029ff9  mov     rsp, r11
0x180029ffc  pop     r15
0x180029ffe  pop     r14
0x18002a000  pop     r13
0x18002a002  pop     rdi
0x18002a003  pop     rsi
0x18002a004  retn
```
