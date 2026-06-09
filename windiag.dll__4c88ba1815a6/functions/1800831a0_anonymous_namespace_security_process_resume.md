# _anonymous_namespace_::security_process_resume

- ea: `0x1800831a0`
- end: `0x1800831e4`
- name: `_anonymous_namespace_::security_process_resume`
- size: `68`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006c50`
- `0x180008660`
- `0x1800831a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800831c3`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800831c3`

## string_xrefs

- `0x1800831a6`: `security.process`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::security_process_resume(struct lua_State *a1)
{
  void *v2; // rcx
  signed int v3; // eax

  v2 = (void *)*((_QWORD *)luaL_checkudata(a1, 1, "security.process") + 1);
  if ( v2 )
    v3 = ResumeThread(v2);
  else
    v3 = -1;
  lua_pushinteger(a1, v3);
  return 1;
}

```

## disassembly

```asm
0x1800831a0  push    rbx
0x1800831a2  sub     rsp, 20h
0x1800831a6  lea     r8, aSecurityProces_1; "security.process"
0x1800831ad  mov     edx, 1; int
0x1800831b2  mov     rbx, rcx
0x1800831b5  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x1800831ba  mov     rcx, [rax+8]; hThread
0x1800831be  test    rcx, rcx
0x1800831c1  jz      short loc_1800831CB
0x1800831c3  call    cs:__imp_ResumeThread
0x1800831c9  jmp     short loc_1800831CE
0x1800831cb  or      eax, 0FFFFFFFFh
0x1800831ce  movsxd  rdx, eax; __int64
0x1800831d1  mov     rcx, rbx; struct lua_State *
0x1800831d4  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800831d9  mov     eax, 1
0x1800831de  add     rsp, 20h
0x1800831e2  pop     rbx
0x1800831e3  retn
```
