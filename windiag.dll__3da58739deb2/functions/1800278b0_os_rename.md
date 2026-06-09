# os_rename

- ea: `0x1800278b0`
- end: `0x18002791e`
- name: `os_rename`
- size: `110`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008430`
- `0x180008900`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800278e5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800278e5`
- `api-ms-win-crt-private-l1-1-0!_o_rename` at `0x1800278f7`
- `api-ms-win-crt-private-l1-1-0!_o_rename` at `0x1800278f7`

## pseudocode

```c
__int64 __fastcall os_rename(struct lua_State *a1)
{
  const char *v2; // rdi
  const char *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  int v7; // eax

  v2 = luaL_checklstring(a1, 1, 0);
  v3 = luaL_checklstring(a1, 2, 0);
  *(_DWORD *)_o__errno(v5, v4, v6) = 0;
  v7 = _o_rename(v2, v3);
  return luaL_fileresult(a1, v7 == 0, 0);
}

```

## disassembly

```asm
0x1800278b0  mov     [rsp+arg_0], rbx
0x1800278b5  mov     [rsp+arg_8], rsi
0x1800278ba  push    rdi
0x1800278bb  sub     rsp, 20h
0x1800278bf  xor     r8d, r8d; unsigned __int64 *
0x1800278c2  mov     edx, 1; int
0x1800278c7  mov     rsi, rcx
0x1800278ca  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x1800278cf  xor     r8d, r8d; unsigned __int64 *
0x1800278d2  mov     edx, 2; int
0x1800278d7  mov     rcx, rsi; struct lua_State *
0x1800278da  mov     rdi, rax
0x1800278dd  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x1800278e2  mov     rbx, rax
0x1800278e5  call    cs:__imp__o__errno
0x1800278eb  mov     rdx, rbx
0x1800278ee  mov     rcx, rdi
0x1800278f1  mov     dword ptr [rax], 0
0x1800278f7  call    cs:__imp__o_rename
0x1800278fd  xor     edx, edx
0x1800278ff  mov     rcx, rsi; struct lua_State *
0x180027902  test    eax, eax
0x180027904  setz    dl; int
0x180027907  xor     r8d, r8d; char *
0x18002790a  mov     rbx, [rsp+28h+arg_0]
0x18002790f  mov     rsi, [rsp+28h+arg_8]
0x180027914  add     rsp, 20h
0x180027918  pop     rdi
0x180027919  jmp     ?luaL_fileresult@@YAHPEAUlua_State@@HPEBD@Z; luaL_fileresult(lua_State *,int,char const *)
```
