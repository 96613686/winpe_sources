# luaB_print

- ea: `0x1800234d0`
- end: `0x1800235bc`
- name: `luaB_print`
- size: `236`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180006690`
- `0x180007490`
- `0x1800095d0`
- `0x1800234d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x1800235a4`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x1800235a4`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180023534`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180023555`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180023590`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180023534`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180023555`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180023590`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x18002351c`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x18002353f`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180023578`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x18002359b`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x18002351c`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x18002353f`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180023578`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x18002359b`

## pseudocode

```c
__int64 __fastcall luaB_print(struct lua_State *a1)
{
  int v2; // ebx
  int v3; // ebp
  const char *v4; // rsi
  FILE *v5; // rax
  FILE *v6; // rax
  FILE *v7; // rax
  FILE *v8; // rax
  unsigned __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = 1;
  v3 = lua_gettop(a1);
  if ( v3 >= 1 )
  {
    do
    {
      v4 = luaL_tolstring(a1, v2, &v10);
      if ( v2 > 1 )
      {
        v5 = __acrt_iob_func(1u);
        _o_fwrite("\t", 1, 1, v5);
      }
      v6 = __acrt_iob_func(1u);
      _o_fwrite(v4, 1, v10, v6);
      lua_settop(a1, -2);
      ++v2;
    }
    while ( v2 <= v3 );
  }
  v7 = __acrt_iob_func(1u);
  _o_fwrite("\n", 1, 1, v7);
  v8 = __acrt_iob_func(1u);
  fflush(v8);
  return 0;
}

```

## disassembly

```asm
0x1800234d0  mov     [rsp+arg_10], rbx
0x1800234d5  mov     [rsp+arg_18], rbp
0x1800234da  push    rdi
0x1800234db  sub     rsp, 20h
0x1800234df  mov     rdi, rcx
0x1800234e2  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x1800234e7  mov     ebx, 1
0x1800234ec  mov     ebp, eax
0x1800234ee  cmp     eax, ebx
0x1800234f0  jl      loc_180023573
0x1800234f6  mov     [rsp+28h+arg_0], rsi
0x1800234fb  nop     dword ptr [rax+rax+00h]
0x180023500  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x180023505  mov     edx, ebx; int
0x180023507  mov     rcx, rdi; struct lua_State *
0x18002350a  call    ?luaL_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_tolstring(lua_State *,int,unsigned __int64 *)
0x18002350f  mov     rsi, rax
0x180023512  cmp     ebx, 1
0x180023515  jle     short loc_18002353A
0x180023517  mov     ecx, 1; Ix
0x18002351c  call    cs:__imp___acrt_iob_func
0x180023522  mov     edx, 1
0x180023527  lea     rcx, asc_1800A396C; "\t"
0x18002352e  mov     r8d, edx
0x180023531  mov     r9, rax
0x180023534  call    cs:__imp__o_fwrite
0x18002353a  mov     ecx, 1; Ix
0x18002353f  call    cs:__imp___acrt_iob_func
0x180023545  mov     r8, [rsp+28h+arg_8]
0x18002354a  mov     edx, 1
0x18002354f  mov     r9, rax
0x180023552  mov     rcx, rsi
0x180023555  call    cs:__imp__o_fwrite
0x18002355b  mov     edx, 0FFFFFFFEh; int
0x180023560  mov     rcx, rdi; struct lua_State *
0x180023563  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180023568  inc     ebx
0x18002356a  cmp     ebx, ebp
0x18002356c  jle     short loc_180023500
0x18002356e  mov     rsi, [rsp+28h+arg_0]
0x180023573  mov     ecx, 1; Ix
0x180023578  call    cs:__imp___acrt_iob_func
0x18002357e  mov     edx, 1
0x180023583  lea     rcx, asc_1800A28D0; "\n"
0x18002358a  mov     r8d, edx
0x18002358d  mov     r9, rax
0x180023590  call    cs:__imp__o_fwrite
0x180023596  mov     ecx, 1; Ix
0x18002359b  call    cs:__imp___acrt_iob_func
0x1800235a1  mov     rcx, rax; Stream
0x1800235a4  call    cs:__imp_fflush
0x1800235aa  mov     rbx, [rsp+28h+arg_10]
0x1800235af  xor     eax, eax
0x1800235b1  mov     rbp, [rsp+28h+arg_18]
0x1800235b6  add     rsp, 20h
0x1800235ba  pop     rdi
0x1800235bb  retn
```
