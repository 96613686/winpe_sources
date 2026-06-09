# _anonymous_namespace_::security_process_detach

- ea: `0x180082c30`
- end: `0x180082c94`
- name: `_anonymous_namespace_::security_process_detach`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008660`
- `0x180082c30`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082c5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082c5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082c78`

## string_xrefs

- `0x180082c36`: `security.process`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::security_process_detach(struct lua_State *a1)
{
  _QWORD *v1; // rax
  _QWORD *v2; // rbx
  void *v3; // rcx
  void *v4; // rcx
  __int64 result; // rax

  v1 = luaL_checkudata(a1, 1, "security.process");
  v2 = v1;
  v3 = (void *)v1[1];
  if ( v3 )
  {
    v1[1] = 0;
    CloseHandle(v3);
  }
  v2[1] = 0;
  v4 = (void *)*v2;
  if ( *v2 )
  {
    *v2 = 0;
    CloseHandle(v4);
  }
  *v2 = 0;
  result = 0;
  *((_DWORD *)v2 + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180082c30  push    rbx
0x180082c32  sub     rsp, 20h
0x180082c36  lea     r8, aSecurityProces_1; "security.process"
0x180082c3d  mov     edx, 1; int
0x180082c42  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x180082c47  mov     rbx, rax
0x180082c4a  mov     rcx, [rax+8]; hObject
0x180082c4e  test    rcx, rcx
0x180082c51  jz      short loc_180082C61
0x180082c53  mov     qword ptr [rax+8], 0
0x180082c5b  call    cs:__imp_CloseHandle
0x180082c61  mov     qword ptr [rbx+8], 0
0x180082c69  mov     rcx, [rbx]; hObject
0x180082c6c  test    rcx, rcx
0x180082c6f  jz      short loc_180082C7E
0x180082c71  mov     qword ptr [rbx], 0
0x180082c78  call    cs:__imp_CloseHandle
0x180082c7e  mov     qword ptr [rbx], 0
0x180082c85  xor     eax, eax
0x180082c87  mov     dword ptr [rbx+10h], 0
0x180082c8e  add     rsp, 20h
0x180082c92  pop     rbx
0x180082c93  retn
```
