# luaL_loadfilex(lua_State *,char const *,char const *)

- ea: `0x180008d40`
- end: `0x180008fa5`
- name: `?luaL_loadfilex@@YAHPEAUlua_State@@PEBD1@Z`
- size: `613`
- prototype: `__int64 __fastcall(struct lua_State *, const char *, const char *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800230e0`
- `0x180023f60`
- `0x18002f4b0`

## callees

- `0x180004510`
- `0x180006690`
- `0x180006850`
- `0x180006c00`
- `0x180006d40`
- `0x180007060`
- `0x180007490`
- `0x180007740`
- `0x180007c70`
- `0x180008d40`
- `0x18000a300`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e39`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e87`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008eec`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e39`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e87`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008eec`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180008f3a`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180008f3a`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x180008f28`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x180008f28`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x180008e9a`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x180008e9a`
- `api-ms-win-crt-private-l1-1-0!_o_freopen` at `0x180008e51`
- `api-ms-win-crt-private-l1-1-0!_o_freopen` at `0x180008e51`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008daf`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008dc1`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008dd1`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008de1`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008df5`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008e08`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008daf`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008dc1`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008dd1`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008de1`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008df5`
- `api-ms-win-crt-private-l1-1-0!_o_getc` at `0x180008e08`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180008d91`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180008d91`

## string_xrefs

- `0x180008e64`: `reopen`

## pseudocode

```c
__int64 __fastcall luaL_loadfilex(struct lua_State *a1, const char *a2, const char *a3)
{
  int v6; // ebp
  FILE *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // r8
  int v12; // eax
  int v13; // eax
  FILE *v14; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  const char *v19; // rax
  unsigned int v20; // edi
  int v21; // ebx
  _DWORD v22[4]; // [rsp+30h] [rbp-268h] BYREF
  int v23; // [rsp+40h] [rbp-258h] BYREF
  FILE *Stream; // [rsp+48h] [rbp-250h]
  _BYTE v25[512]; // [rsp+50h] [rbp-248h]

  v6 = lua_gettop(a1) + 1;
  if ( a2 )
  {
    lua_pushfstring(a1, "@%s", a2);
    *(_DWORD *)_o__errno(v17, v16, v18) = 0;
    Stream = (FILE *)_o_fopen(a2, "r");
    v7 = Stream;
    if ( !Stream )
      return errfile(a1);
  }
  else
  {
    lua_pushstring(a1, "=stdin");
    v7 = __acrt_iob_func(0);
    Stream = v7;
  }
  v23 = 0;
  v10 = _o_getc(v7);
  if ( v10 == 239 && (unsigned int)_o_getc(v7) == 187 && (unsigned int)_o_getc(v7) == 191 )
    v10 = _o_getc(v7);
  v22[0] = v10;
  if ( v10 == 35 )
  {
    do
      v12 = _o_getc(v7);
    while ( v12 != -1 && v12 != 10 );
    v13 = _o_getc(v7);
    v9 = v23;
    v10 = v13;
    v22[0] = v13;
    v25[v23++] = 10;
  }
  if ( v10 == 27 )
  {
    v23 = 0;
    if ( !a2 )
    {
LABEL_19:
      v25[v23++] = v10;
      goto LABEL_20;
    }
    *(_DWORD *)_o__errno(v9, v8, v11) = 0;
    v14 = (FILE *)_o_freopen(a2, "rb", Stream);
    Stream = v14;
    if ( !v14 )
      return errfile(a1);
    skipcomment(v14, v22);
    v10 = v22[0];
  }
  if ( v10 != -1 )
    goto LABEL_19;
LABEL_20:
  *(_DWORD *)_o__errno(v9, v8, v11) = 0;
  v19 = lua_tolstring(a1, -1, 0);
  v20 = lua_load(a1, getF, &v23, v19, a3);
  v21 = _o_ferror(Stream);
  if ( a2 )
    fclose(Stream);
  if ( v21 )
  {
    lua_settop(a1, v6);
    return errfile(a1);
  }
  else
  {
    lua_rotate(a1, v6, -1);
    lua_settop(a1, -2);
    return v20;
  }
}

```

## disassembly

```asm
0x180008d40  push    rbx
0x180008d42  push    rbp
0x180008d43  push    rsi
0x180008d44  push    r12
0x180008d46  push    r14
0x180008d48  push    r15
0x180008d4a  sub     rsp, 268h
0x180008d51  mov     rax, cs:__security_cookie
0x180008d58  xor     rax, rsp
0x180008d5b  mov     [rsp+298h+var_48], rax
0x180008d63  mov     r15, r8
0x180008d66  mov     r14, rdx
0x180008d69  mov     rsi, rcx
0x180008d6c  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x180008d71  xor     r12d, r12d
0x180008d74  mov     rcx, rsi; struct lua_State *
0x180008d77  lea     ebp, [rax+1]
0x180008d7a  test    r14, r14
0x180008d7d  jnz     loc_180008E78
0x180008d83  lea     rdx, aStdin_0; "=stdin"
0x180008d8a  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x180008d8f  xor     ecx, ecx; Ix
0x180008d91  call    cs:__imp___acrt_iob_func
0x180008d97  mov     rbx, rax
0x180008d9a  mov     [rsp+298h+Stream], rax
0x180008d9f  mov     rcx, rbx
0x180008da2  mov     [rsp+298h+var_38], rdi
0x180008daa  mov     [rsp+298h+var_258], r12d
0x180008daf  call    cs:__imp__o_getc
0x180008db5  mov     edi, eax
0x180008db7  cmp     eax, 0EFh
0x180008dbc  jnz     short loc_180008DE9
0x180008dbe  mov     rcx, rbx
0x180008dc1  call    cs:__imp__o_getc
0x180008dc7  cmp     eax, 0BBh
0x180008dcc  jnz     short loc_180008DE9
0x180008dce  mov     rcx, rbx
0x180008dd1  call    cs:__imp__o_getc
0x180008dd7  cmp     eax, 0BFh
0x180008ddc  jnz     short loc_180008DE9
0x180008dde  mov     rcx, rbx
0x180008de1  call    cs:__imp__o_getc
0x180008de7  mov     edi, eax
0x180008de9  mov     [rsp+298h+var_268], edi
0x180008ded  cmp     edi, 23h ; '#'
0x180008df0  jnz     short loc_180008E22
0x180008df2  mov     rcx, rbx
0x180008df5  call    cs:__imp__o_getc
0x180008dfb  cmp     eax, 0FFFFFFFFh
0x180008dfe  jz      short loc_180008E05
0x180008e00  cmp     eax, 0Ah
0x180008e03  jnz     short loc_180008DF2
0x180008e05  mov     rcx, rbx
0x180008e08  call    cs:__imp__o_getc
0x180008e0e  movsxd  rcx, [rsp+298h+var_258]
0x180008e13  mov     edi, eax
0x180008e15  mov     [rsp+298h+var_268], eax
0x180008e19  mov     [rsp+rcx+298h+var_248], 0Ah
0x180008e1e  inc     [rsp+298h+var_258]
0x180008e22  cmp     edi, 1Bh
0x180008e25  jnz     loc_180008ED9
0x180008e2b  mov     [rsp+298h+var_258], r12d
0x180008e30  test    r14, r14
0x180008e33  jz      loc_180008EDE
0x180008e39  call    cs:__imp__o__errno
0x180008e3f  lea     rdx, aRb; "rb"
0x180008e46  mov     rcx, r14
0x180008e49  mov     [rax], r12d
0x180008e4c  mov     r8, [rsp+298h+Stream]
0x180008e51  call    cs:__imp__o_freopen
0x180008e57  mov     [rsp+298h+Stream], rax
0x180008e5c  test    rax, rax
0x180008e5f  jnz     short loc_180008EC8
0x180008e61  mov     r8d, ebp
0x180008e64  lea     rdx, aReopen; "reopen"
0x180008e6b  mov     rcx, rsi; struct lua_State *
0x180008e6e  call    errfile
0x180008e73  jmp     loc_180008F7C
0x180008e78  mov     r8, r14
0x180008e7b  lea     rdx, aS_0; "@%s"
0x180008e82  call    ?lua_pushfstring@@YAPEBDPEAUlua_State@@PEBDZZ; lua_pushfstring(lua_State *,char const *,...)
0x180008e87  call    cs:__imp__o__errno
0x180008e8d  lea     rdx, aR; "r"
0x180008e94  mov     rcx, r14
0x180008e97  mov     [rax], r12d
0x180008e9a  call    cs:__imp__o_fopen
0x180008ea0  mov     [rsp+298h+Stream], rax
0x180008ea5  mov     rbx, rax
0x180008ea8  test    rax, rax
0x180008eab  jnz     loc_180008D9F
0x180008eb1  mov     r8d, ebp
0x180008eb4  lea     rdx, aOpen; "open"
0x180008ebb  mov     rcx, rsi; struct lua_State *
0x180008ebe  call    errfile
0x180008ec3  jmp     loc_180008F84
0x180008ec8  lea     rdx, [rsp+298h+var_268]
0x180008ecd  mov     rcx, rax
0x180008ed0  call    skipcomment
0x180008ed5  mov     edi, [rsp+298h+var_268]
0x180008ed9  cmp     edi, 0FFFFFFFFh
0x180008edc  jz      short loc_180008EEC
0x180008ede  movsxd  rax, [rsp+298h+var_258]
0x180008ee3  mov     [rsp+rax+298h+var_248], dil
0x180008ee8  inc     [rsp+298h+var_258]
0x180008eec  call    cs:__imp__o__errno
0x180008ef2  xor     r8d, r8d; unsigned __int64 *
0x180008ef5  mov     edx, 0FFFFFFFFh; int
0x180008efa  mov     rcx, rsi; struct lua_State *
0x180008efd  mov     [rax], r12d
0x180008f00  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x180008f05  mov     r9, rax; char *
0x180008f08  mov     [rsp+298h+var_278], r15; char *
0x180008f0d  lea     r8, [rsp+298h+var_258]; void *
0x180008f12  mov     rcx, rsi; struct lua_State *
0x180008f15  lea     rdx, getF; const char *(*)(struct lua_State *, void *, unsigned __int64 *)
0x180008f1c  call    ?lua_load@@YAHPEAUlua_State@@P6APEBD0PEAXPEA_K@Z1PEBD4@Z; lua_load(lua_State *,char const * (*)(lua_State *,void *,unsigned __int64 *),void *,char const *,char const *)
0x180008f21  mov     rcx, [rsp+298h+Stream]
0x180008f26  mov     edi, eax
0x180008f28  call    cs:__imp__o_ferror
0x180008f2e  mov     ebx, eax
0x180008f30  test    r14, r14
0x180008f33  jz      short loc_180008F40
0x180008f35  mov     rcx, [rsp+298h+Stream]; Stream
0x180008f3a  call    cs:__imp_fclose
0x180008f40  mov     edx, ebp; int
0x180008f42  mov     rcx, rsi; struct lua_State *
0x180008f45  test    ebx, ebx
0x180008f47  jz      short loc_180008F62
0x180008f49  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180008f4e  mov     r8d, ebp
0x180008f51  lea     rdx, aRead; "read"
0x180008f58  mov     rcx, rsi; struct lua_State *
0x180008f5b  call    errfile
0x180008f60  jmp     short loc_180008F7C
0x180008f62  mov     r8d, 0FFFFFFFFh; int
0x180008f68  call    ?lua_rotate@@YAXPEAUlua_State@@HH@Z; lua_rotate(lua_State *,int,int)
0x180008f6d  mov     edx, 0FFFFFFFEh; int
0x180008f72  mov     rcx, rsi; struct lua_State *
0x180008f75  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180008f7a  mov     eax, edi
0x180008f7c  mov     rdi, [rsp+298h+var_38]
0x180008f84  mov     rcx, [rsp+298h+var_48]
0x180008f8c  xor     rcx, rsp; StackCookie
0x180008f8f  call    __security_check_cookie
0x180008f94  add     rsp, 268h
0x180008f9b  pop     r15
0x180008f9d  pop     r14
0x180008f9f  pop     r12
0x180008fa1  pop     rsi
0x180008fa2  pop     rbp
0x180008fa3  pop     rbx
0x180008fa4  retn
```
