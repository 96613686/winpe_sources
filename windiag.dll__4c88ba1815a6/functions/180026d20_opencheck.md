# opencheck

- ea: `0x180026d20`
- end: `0x180026dab`
- name: `opencheck`
- size: `139`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800258d0`
- `0x180025960`
- `0x180025a40`

## callees

- `0x180006910`
- `0x180008790`
- `0x180009510`
- `0x180026d20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026d7f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026d7f`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x180026d71`
- `api-ms-win-crt-private-l1-1-0!_o_fopen` at `0x180026d71`
- `api-ms-win-crt-private-l1-1-0!_o_strerror` at `0x180026d87`
- `api-ms-win-crt-private-l1-1-0!_o_strerror` at `0x180026d87`

## string_xrefs

- `0x180026d90`: `cannot open file '%s' (%s)`

## pseudocode

```c
__int64 __fastcall opencheck(struct lua_State *a1, const char *a2, __int64 a3)
{
  _QWORD *v6; // rbx
  __int64 result; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned int *v11; // rax
  const char *v12; // rax

  v6 = lua_newuserdatauv(a1, 0x10u, 0);
  v6[1] = 0;
  luaL_setmetatable(a1, "FILE*");
  *v6 = 0;
  v6[1] = io_fclose;
  result = _o_fopen(a2, a3);
  *v6 = result;
  if ( !result )
  {
    v11 = (unsigned int *)_o__errno(v9, v8, v10);
    v12 = (const char *)_o_strerror(*v11);
    luaL_error(a1, "cannot open file '%s' (%s)", a2, v12);
  }
  return result;
}

```

## disassembly

```asm
0x180026d20  push    rbx
0x180026d22  push    rbp
0x180026d23  push    rsi
0x180026d24  push    rdi
0x180026d25  sub     rsp, 28h
0x180026d29  mov     rdi, r8
0x180026d2c  mov     rbp, rdx
0x180026d2f  xor     r8d, r8d; int
0x180026d32  mov     edx, 10h; unsigned __int64
0x180026d37  mov     rsi, rcx
0x180026d3a  call    ?lua_newuserdatauv@@YAPEAXPEAUlua_State@@_KH@Z; lua_newuserdatauv(lua_State *,unsigned __int64,int)
0x180026d3f  lea     rdx, aFile; "FILE*"
0x180026d46  mov     rcx, rsi; struct lua_State *
0x180026d49  mov     rbx, rax
0x180026d4c  mov     qword ptr [rax+8], 0
0x180026d54  call    ?luaL_setmetatable@@YAXPEAUlua_State@@PEBD@Z; luaL_setmetatable(lua_State *,char const *)
0x180026d59  lea     rax, io_fclose
0x180026d60  mov     qword ptr [rbx], 0
0x180026d67  mov     rdx, rdi
0x180026d6a  mov     [rbx+8], rax
0x180026d6e  mov     rcx, rbp
0x180026d71  call    cs:__imp__o_fopen
0x180026d77  mov     [rbx], rax
0x180026d7a  test    rax, rax
0x180026d7d  jnz     short loc_180026DA2
0x180026d7f  call    cs:__imp__o__errno
0x180026d85  mov     ecx, [rax]
0x180026d87  call    cs:__imp__o_strerror
0x180026d8d  mov     r8, rbp
0x180026d90  lea     rdx, aCannotOpenFile; "cannot open file '%s' (%s)"
0x180026d97  mov     r9, rax
0x180026d9a  mov     rcx, rsi; struct lua_State *
0x180026d9d  call    ?luaL_error@@YAHPEAUlua_State@@PEBDZZ; luaL_error(lua_State *,char const *,...)
0x180026da2  add     rsp, 28h
0x180026da6  pop     rdi
0x180026da7  pop     rsi
0x180026da8  pop     rbp
0x180026da9  pop     rbx
0x180026daa  retn
```
