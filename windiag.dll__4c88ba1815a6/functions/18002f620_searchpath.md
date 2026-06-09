# searchpath

- ea: `0x18002f620`
- end: `0x18002f7e8`
- name: `searchpath`
- size: `456`
- prototype: `__int64 __fastcall(struct lua_State *, char *Str, char *, char *SubStr, char *)`
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18002e8f0`
- `0x18002f240`
- `0x18002f320`
- `0x18002f4b0`

## callees

- `0x180004510`
- `0x1800052f2`
- `0x180006d40`
- `0x180007740`
- `0x180007f40`
- `0x1800080d0`
- `0x1800082d0`
- `0x180008ad0`
- `0x180009240`
- `0x180009260`
- `0x18002f620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18002f732`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18002f732`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x18002f724`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x18002f724`

## pseudocode

```c
const char *__fastcall searchpath(struct lua_State *a1, char *Str, char *a3, char *SubStr, char *a5)
{
  const char *v7; // rbx
  unsigned __int64 v9; // rcx
  char *v10; // rbx
  __int64 v11; // rsi
  const char *v12; // rdi
  char *v13; // rax
  FILE *v14; // rax
  const char *v16; // rbx
  _QWORD v17[2]; // [rsp+20h] [rbp-878h] BYREF
  unsigned __int64 v18; // [rsp+30h] [rbp-868h]
  _BYTE v19[1056]; // [rsp+440h] [rbp-458h] BYREF

  v7 = Str;
  if ( *SubStr && strchr_0(Str, *SubStr) )
    v7 = luaL_gsub(a1, v7, SubStr, a5);
  luaL_buffinit(a1, (struct luaL_Buffer *)v17);
  luaL_addgsub((struct luaL_Buffer *)v17, a3, "?", v7);
  v9 = v18;
  if ( v18 >= v17[1] )
  {
    luaL_prepbuffsize((struct luaL_Buffer *)v17, 1u);
    v9 = v18;
  }
  *(_BYTE *)(v17[0] + v9) = 0;
  v10 = (char *)v17[0];
  v11 = ++v18 + v17[0] - 1LL;
  while ( v10 != (char *)v11 )
  {
    if ( *v10 )
    {
      v12 = v10;
    }
    else
    {
      *v10 = 59;
      v12 = v10 + 1;
    }
    v13 = strchr_0(v12, 59);
    v10 = (char *)v11;
    if ( v13 )
      v10 = v13;
    *v10 = 0;
    if ( !v12 )
      break;
    v14 = (FILE *)_o_fopen(v12, "r");
    if ( v14 )
    {
      fclose(v14);
      return lua_pushstring(a1, v12);
    }
  }
  luaL_pushresult((struct luaL_Buffer *)v17);
  v16 = lua_tolstring(a1, 0xFFFFFFFFLL, 0);
  luaL_buffinit(a1, (struct luaL_Buffer *)v19);
  luaL_addstring((struct luaL_Buffer *)v19, "no file '");
  luaL_addgsub((struct luaL_Buffer *)v19, v16, ";", "'\n\tno file '");
  luaL_addstring((struct luaL_Buffer *)v19, "'");
  luaL_pushresult((struct luaL_Buffer *)v19);
  return 0;
}

```

## disassembly

```asm
0x18002f620  push    rbx
0x18002f622  push    rbp
0x18002f623  push    rsi
0x18002f624  push    rdi
0x18002f625  push    r14
0x18002f627  sub     rsp, 870h
0x18002f62e  mov     rax, cs:__security_cookie
0x18002f635  xor     rax, rsp
0x18002f638  mov     [rsp+898h+var_38], rax
0x18002f640  movsx   eax, byte ptr [r9]
0x18002f644  mov     rdi, r9
0x18002f647  mov     rsi, [rsp+898h+arg_20]
0x18002f64f  mov     r14, r8
0x18002f652  mov     rbx, rdx
0x18002f655  mov     rbp, rcx
0x18002f658  test    al, al
0x18002f65a  jz      short loc_18002F67F
0x18002f65c  mov     edx, eax; Val
0x18002f65e  mov     rcx, rbx; Str
0x18002f661  call    strchr_0
0x18002f666  test    rax, rax
0x18002f669  jz      short loc_18002F67F
0x18002f66b  mov     r9, rsi; char *
0x18002f66e  mov     r8, rdi; SubStr
0x18002f671  mov     rdx, rbx; Str
0x18002f674  mov     rcx, rbp; struct lua_State *
0x18002f677  call    ?luaL_gsub@@YAPEBDPEAUlua_State@@PEBD11@Z; luaL_gsub(lua_State *,char const *,char const *,char const *)
0x18002f67c  mov     rbx, rax
0x18002f67f  lea     rdx, [rsp+898h+var_878]; struct luaL_Buffer *
0x18002f684  mov     rcx, rbp; struct lua_State *
0x18002f687  call    ?luaL_buffinit@@YAXPEAUlua_State@@PEAUluaL_Buffer@@@Z; luaL_buffinit(lua_State *,luaL_Buffer *)
0x18002f68c  mov     r9, rbx; char *
0x18002f68f  lea     r8, asc_1800A2534; "?"
0x18002f696  mov     rdx, r14; char *
0x18002f699  lea     rcx, [rsp+898h+var_878]; struct luaL_Buffer *
0x18002f69e  call    ?luaL_addgsub@@YAXPEAUluaL_Buffer@@PEBD11@Z; luaL_addgsub(luaL_Buffer *,char const *,char const *,char const *)
0x18002f6a3  mov     rcx, [rsp+898h+var_868]
0x18002f6a8  cmp     rcx, [rsp+898h+var_870]
0x18002f6ad  jb      short loc_18002F6C3
0x18002f6af  mov     edx, 1; unsigned __int64
0x18002f6b4  lea     rcx, [rsp+898h+var_878]; struct luaL_Buffer *
0x18002f6b9  call    ?luaL_prepbuffsize@@YAPEADPEAUluaL_Buffer@@_K@Z; luaL_prepbuffsize(luaL_Buffer *,unsigned __int64)
0x18002f6be  mov     rcx, [rsp+898h+var_868]
0x18002f6c3  mov     rax, [rsp+898h+var_878]
0x18002f6c8  mov     byte ptr [rax+rcx], 0
0x18002f6cc  mov     rax, [rsp+898h+var_868]
0x18002f6d1  mov     rbx, [rsp+898h+var_878]
0x18002f6d6  inc     rax
0x18002f6d9  mov     [rsp+898h+var_868], rax
0x18002f6de  lea     rsi, [rbx-1]
0x18002f6e2  add     rsi, rax
0x18002f6e5  cmp     rbx, rsi
0x18002f6e8  jz      short loc_18002F748
0x18002f6ea  cmp     byte ptr [rbx], 0
0x18002f6ed  jnz     short loc_18002F6F8
0x18002f6ef  mov     byte ptr [rbx], 3Bh ; ';'
0x18002f6f2  lea     rdi, [rbx+1]
0x18002f6f6  jmp     short loc_18002F6FB
0x18002f6f8  mov     rdi, rbx
0x18002f6fb  mov     edx, 3Bh ; ';'; Val
0x18002f700  mov     rcx, rdi; Str
0x18002f703  call    strchr_0
0x18002f708  test    rax, rax
0x18002f70b  mov     rbx, rsi
0x18002f70e  cmovnz  rbx, rax
0x18002f712  mov     byte ptr [rbx], 0
0x18002f715  test    rdi, rdi
0x18002f718  jz      short loc_18002F748
0x18002f71a  lea     rdx, aR; "r"
0x18002f721  mov     rcx, rdi
0x18002f724  call    cs:__imp__o_fopen
0x18002f72a  test    rax, rax
0x18002f72d  jz      short loc_18002F6E5
0x18002f72f  mov     rcx, rax; Stream
0x18002f732  call    cs:__imp_fclose
0x18002f738  mov     rdx, rdi; char *
0x18002f73b  mov     rcx, rbp; struct lua_State *
0x18002f73e  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18002f743  jmp     loc_18002F7CA
0x18002f748  lea     rcx, [rsp+898h+var_878]; struct luaL_Buffer *
0x18002f74d  call    ?luaL_pushresult@@YAXPEAUluaL_Buffer@@@Z; luaL_pushresult(luaL_Buffer *)
0x18002f752  xor     r8d, r8d; unsigned __int64 *
0x18002f755  mov     edx, 0FFFFFFFFh; int
0x18002f75a  mov     rcx, rbp; struct lua_State *
0x18002f75d  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x18002f762  lea     rdx, [rsp+898h+var_458]; struct luaL_Buffer *
0x18002f76a  mov     rcx, rbp; struct lua_State *
0x18002f76d  mov     rbx, rax
0x18002f770  call    ?luaL_buffinit@@YAXPEAUlua_State@@PEAUluaL_Buffer@@@Z; luaL_buffinit(lua_State *,luaL_Buffer *)
0x18002f775  lea     rdx, aNoFile; "no file '"
0x18002f77c  lea     rcx, [rsp+898h+var_458]; struct luaL_Buffer *
0x18002f784  call    ?luaL_addstring@@YAXPEAUluaL_Buffer@@PEBD@Z; luaL_addstring(luaL_Buffer *,char const *)
0x18002f789  lea     r9, aNoFile_0; "'\n\tno file '"
0x18002f790  mov     rdx, rbx; char *
0x18002f793  lea     r8, asc_1800A4C08; ";"
0x18002f79a  lea     rcx, [rsp+898h+var_458]; struct luaL_Buffer *
0x18002f7a2  call    ?luaL_addgsub@@YAXPEAUluaL_Buffer@@PEBD11@Z; luaL_addgsub(luaL_Buffer *,char const *,char const *,char const *)
0x18002f7a7  lea     rdx, asc_1800A4C30; "'"
0x18002f7ae  lea     rcx, [rsp+898h+var_458]; struct luaL_Buffer *
0x18002f7b6  call    ?luaL_addstring@@YAXPEAUluaL_Buffer@@PEBD@Z; luaL_addstring(luaL_Buffer *,char const *)
0x18002f7bb  lea     rcx, [rsp+898h+var_458]; struct luaL_Buffer *
0x18002f7c3  call    ?luaL_pushresult@@YAXPEAUluaL_Buffer@@@Z; luaL_pushresult(luaL_Buffer *)
0x18002f7c8  xor     eax, eax
0x18002f7ca  mov     rcx, [rsp+898h+var_38]
0x18002f7d2  xor     rcx, rsp; StackCookie
0x18002f7d5  call    __security_check_cookie
0x18002f7da  add     rsp, 870h
0x18002f7e1  pop     r14
0x18002f7e3  pop     rdi
0x18002f7e4  pop     rsi
0x18002f7e5  pop     rbp
0x18002f7e6  pop     rbx
0x18002f7e7  retn
```
