# _anonymous_namespace_::security_cleanup

- ea: `0x180081950`
- end: `0x1800819a9`
- name: `_anonymous_namespace_::security_cleanup`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008660`
- `0x180081950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180081975`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180081975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081990`

## string_xrefs

- `0x180081956`: `security.state`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::security_cleanup(struct lua_State *a1)
{
  HANDLE *v1; // rax
  HANDLE *v2; // rbx
  HANDLE v3; // rcx

  v1 = (HANDLE *)luaL_checkudata(a1, 1, "security.state");
  v2 = v1;
  if ( *((_BYTE *)v1 + 8) )
  {
    SetThreadToken(0, *v1);
    if ( *((_BYTE *)v2 + 8) )
    {
      v3 = *v2;
      if ( *v2 )
      {
        *v2 = 0;
        CloseHandle(v3);
      }
      *v2 = 0;
      *((_BYTE *)v2 + 8) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180081950  push    rbx
0x180081952  sub     rsp, 20h
0x180081956  lea     r8, aSecurityState; "security.state"
0x18008195d  mov     edx, 1; int
0x180081962  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x180081967  mov     rbx, rax
0x18008196a  cmp     byte ptr [rax+8], 0
0x18008196e  jz      short loc_1800819A1
0x180081970  mov     rdx, [rax]; Token
0x180081973  xor     ecx, ecx; Thread
0x180081975  call    cs:__imp_SetThreadToken
0x18008197b  cmp     byte ptr [rbx+8], 0
0x18008197f  jz      short loc_1800819A1
0x180081981  mov     rcx, [rbx]; hObject
0x180081984  test    rcx, rcx
0x180081987  jz      short loc_180081996
0x180081989  mov     qword ptr [rbx], 0
0x180081990  call    cs:__imp_CloseHandle
0x180081996  mov     qword ptr [rbx], 0
0x18008199d  mov     byte ptr [rbx+8], 0
0x1800819a1  xor     eax, eax
0x1800819a3  add     rsp, 20h
0x1800819a7  pop     rbx
0x1800819a8  retn
```
