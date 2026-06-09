# _anonymous_namespace_::security_token_privileges

- ea: `0x180083678`
- end: `0x18008378a`
- name: `_anonymous_namespace_::security_token_privileges`
- size: `274`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800833b0`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180006050`
- `0x180006c50`
- `0x180006d40`
- `0x180007160`
- `0x1800073e0`
- `0x180083678`

## import_xrefs

- `api-ms-win-security-lsalookup-ansi-l2-1-0!LookupPrivilegeNameA` at `0x180083701`
- `api-ms-win-security-lsalookup-ansi-l2-1-0!LookupPrivilegeNameA` at `0x180083701`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::security_token_privileges(struct lua_State *a1, unsigned int *a2)
{
  unsigned int v4; // edi
  unsigned int v5; // ebp
  unsigned int *v6; // rdi
  DWORD cchName[4]; // [rsp+20h] [rbp-148h] BYREF
  CHAR Name[272]; // [rsp+30h] [rbp-138h] BYREF

  lua_createtable(a1, 0, 0);
  v4 = 0;
  if ( *a2 )
  {
    do
    {
      v5 = v4 + 1;
      lua_pushinteger(a1, v4 + 1);
      lua_createtable(a1, 0, 0);
      v6 = &a2[3 * v4];
      memset_0(Name, 0, 0x104u);
      cchName[0] = 259;
      if ( LookupPrivilegeNameA(0, (PLUID)(v6 + 1), Name, cchName) )
      {
        lua_pushstring(a1, Name);
        lua_setfield(a1, -2, "name");
        lua_pushinteger(a1, v6[3]);
        lua_setfield(a1, -2, "attributes");
      }
      lua_settable(a1, -3);
      v4 = v5;
    }
    while ( v5 < *a2 );
  }
  return 1;
}

```

## disassembly

```asm
0x180083678  mov     [rsp+arg_10], rbx
0x18008367d  push    rbp
0x18008367e  push    rsi
0x18008367f  push    rdi
0x180083680  sub     rsp, 150h
0x180083687  mov     rax, cs:__security_cookie
0x18008368e  xor     rax, rsp
0x180083691  mov     [rsp+168h+var_28], rax
0x180083699  mov     rsi, rdx
0x18008369c  xor     r8d, r8d; int
0x18008369f  xor     edx, edx; int
0x1800836a1  mov     rbx, rcx
0x1800836a4  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x1800836a9  xor     edi, edi
0x1800836ab  cmp     [rsi], edi
0x1800836ad  jbe     loc_180083762
0x1800836b3  lea     ebp, [rdi+1]
0x1800836b6  mov     rcx, rbx; struct lua_State *
0x1800836b9  mov     edx, ebp; __int64
0x1800836bb  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800836c0  xor     r8d, r8d; int
0x1800836c3  xor     edx, edx; int
0x1800836c5  mov     rcx, rbx; struct lua_State *
0x1800836c8  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x1800836cd  mov     eax, edi
0x1800836cf  xor     edx, edx; Val
0x1800836d1  mov     r8d, 104h; Size
0x1800836d7  lea     rcx, [rax+rax*2]
0x1800836db  lea     rdi, [rsi+rcx*4]
0x1800836df  lea     rcx, [rsp+168h+Name]; void *
0x1800836e4  call    memset_0
0x1800836e9  lea     r9, [rsp+168h+cchName]; cchName
0x1800836ee  mov     [rsp+168h+cchName], 103h
0x1800836f6  lea     r8, [rsp+168h+Name]; lpName
0x1800836fb  xor     ecx, ecx; lpSystemName
0x1800836fd  lea     rdx, [rdi+4]; lpLuid
0x180083701  call    cs:__imp_LookupPrivilegeNameA
0x180083707  test    eax, eax
0x180083709  jz      short loc_18008374B
0x18008370b  lea     rdx, [rsp+168h+Name]; char *
0x180083710  mov     rcx, rbx; struct lua_State *
0x180083713  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x180083718  lea     r8, aName; "name"
0x18008371f  mov     edx, 0FFFFFFFEh; int
0x180083724  mov     rcx, rbx; struct lua_State *
0x180083727  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18008372c  mov     edx, [rdi+0Ch]; __int64
0x18008372f  mov     rcx, rbx; struct lua_State *
0x180083732  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180083737  lea     r8, aAttributes; "attributes"
0x18008373e  mov     edx, 0FFFFFFFEh; int
0x180083743  mov     rcx, rbx; struct lua_State *
0x180083746  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18008374b  mov     edx, 0FFFFFFFDh; int
0x180083750  mov     rcx, rbx; struct lua_State *
0x180083753  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x180083758  mov     edi, ebp
0x18008375a  cmp     ebp, [rsi]
0x18008375c  jb      loc_1800836B3
0x180083762  mov     eax, 1
0x180083767  mov     rcx, [rsp+168h+var_28]
0x18008376f  xor     rcx, rsp; StackCookie
0x180083772  call    __security_check_cookie
0x180083777  mov     rbx, [rsp+168h+arg_10]
0x18008377f  add     rsp, 150h
0x180083786  pop     rdi
0x180083787  pop     rsi
0x180083788  pop     rbp
0x180083789  retn
```
