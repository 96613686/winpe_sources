# _anonymous_namespace_::lua_gbl_getcmd

- ea: `0x18006f1b0`
- end: `0x18006f2a3`
- name: `_anonymous_namespace_::lua_gbl_getcmd`
- size: `243`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004510`
- `0x180006d00`
- `0x180006d40`
- `0x18003b0bc`
- `0x180041400`
- `0x180041564`
- `0x180041e58`
- `0x18006f1b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006f1f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006f1f3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18006f234`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18006f234`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::lua_gbl_getcmd(struct lua_State *a1)
{
  WCHAR *v2; // rdx
  LPWSTR *v3; // rdx
  __int64 v4; // rax
  LPWSTR CommandLineW; // rax
  __int64 v6; // rax
  unsigned int v7; // ebx
  LPWSTR lpFilename[3]; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 v10; // [rsp+38h] [rbp-38h]
  char *v11[4]; // [rsp+40h] [rbp-30h] BYREF

  std::wstring::wstring(lpFilename, 0x8000);
  v2 = (WCHAR *)lpFilename;
  if ( v10 > 7 )
    v2 = lpFilename[0];
  if ( GetModuleFileNameW(0, v2, 0x7FFFu) )
  {
    v3 = lpFilename;
    if ( v10 > 7 )
      v3 = (LPWSTR *)lpFilename[0];
    v4 = windiag::wchar_to_string(v11, v3);
    if ( *(_QWORD *)(v4 + 24) > 0xFu )
      v4 = *(_QWORD *)v4;
    lua_pushstring(a1, (const char *)v4);
    std::string::~string(v11);
    CommandLineW = GetCommandLineW();
    if ( CommandLineW )
    {
      v6 = windiag::wchar_to_string(v11, CommandLineW);
      if ( *(_QWORD *)(v6 + 24) > 0xFu )
        v6 = *(_QWORD *)v6;
      lua_pushstring(a1, (const char *)v6);
      std::string::~string(v11);
    }
    else
    {
      lua_pushnil(a1);
    }
    v7 = 2;
  }
  else
  {
    v7 = 0;
  }
  std::wstring::~wstring((char **)lpFilename);
  return v7;
}

```

## disassembly

```asm
0x18006f1b0  mov     [rsp-8+arg_8], rbx
0x18006f1b5  push    rbp
0x18006f1b6  mov     rbp, rsp
0x18006f1b9  sub     rsp, 70h
0x18006f1bd  mov     rax, cs:__security_cookie
0x18006f1c4  xor     rax, rsp
0x18006f1c7  mov     [rbp+var_10], rax
0x18006f1cb  mov     rbx, rcx
0x18006f1ce  mov     edx, 8000h
0x18006f1d3  lea     rcx, [rbp+lpFilename]
0x18006f1d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18006f1dc  nop
0x18006f1dd  lea     rdx, [rbp+lpFilename]
0x18006f1e1  cmp     [rbp+var_38], 7
0x18006f1e6  cmova   rdx, [rbp+lpFilename]; lpFilename
0x18006f1eb  xor     ecx, ecx; hModule
0x18006f1ed  mov     r8d, 7FFFh; nSize
0x18006f1f3  call    cs:__imp_GetModuleFileNameW
0x18006f1f9  test    eax, eax
0x18006f1fb  jz      short loc_18006F27C
0x18006f1fd  lea     rdx, [rbp+lpFilename]
0x18006f201  cmp     [rbp+var_38], 7
0x18006f206  cmova   rdx, [rbp+lpFilename]
0x18006f20b  lea     rcx, [rbp+var_30]
0x18006f20f  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x18006f214  nop
0x18006f215  cmp     qword ptr [rax+18h], 0Fh
0x18006f21a  jbe     short loc_18006F21F
0x18006f21c  mov     rax, [rax]
0x18006f21f  mov     rdx, rax; char *
0x18006f222  mov     rcx, rbx; struct lua_State *
0x18006f225  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18006f22a  nop
0x18006f22b  lea     rcx, [rbp+var_30]
0x18006f22f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18006f234  call    cs:__imp_GetCommandLineW
0x18006f23a  test    rax, rax
0x18006f23d  jz      short loc_18006F26D
0x18006f23f  mov     rdx, rax
0x18006f242  lea     rcx, [rbp+var_30]
0x18006f246  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x18006f24b  nop
0x18006f24c  cmp     qword ptr [rax+18h], 0Fh
0x18006f251  jbe     short loc_18006F256
0x18006f253  mov     rax, [rax]
0x18006f256  mov     rdx, rax; char *
0x18006f259  mov     rcx, rbx; struct lua_State *
0x18006f25c  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18006f261  nop
0x18006f262  lea     rcx, [rbp+var_30]
0x18006f266  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18006f26b  jmp     short loc_18006F275
0x18006f26d  mov     rcx, rbx; struct lua_State *
0x18006f270  call    ?lua_pushnil@@YAXPEAUlua_State@@@Z; lua_pushnil(lua_State *)
0x18006f275  mov     ebx, 2
0x18006f27a  jmp     short loc_18006F27E
0x18006f27c  xor     ebx, ebx
0x18006f27e  lea     rcx, [rbp+lpFilename]
0x18006f282  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006f287  mov     eax, ebx
0x18006f289  mov     rcx, [rbp+var_10]
0x18006f28d  xor     rcx, rsp; StackCookie
0x18006f290  call    __security_check_cookie
0x18006f295  mov     rbx, [rsp+70h+arg_8]
0x18006f29d  add     rsp, 70h
0x18006f2a1  pop     rbp
0x18006f2a2  retn
```
