# _anonymous_namespace_::security_token_information

- ea: `0x1800833b0`
- end: `0x180083672`
- name: `_anonymous_namespace_::security_token_information`
- size: `706`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006050`
- `0x180006690`
- `0x180006b00`
- `0x180006c50`
- `0x180006d40`
- `0x1800073e0`
- `0x1800083a0`
- `0x180049674`
- `0x180080ea0`
- `0x180081518`
- `0x1800833b0`
- `0x180083678`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800833d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800833d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083599`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083599`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x18008356f`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x18008356f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::security_token_information(struct lua_State *a1)
{
  TOKEN_INFORMATION_CLASS v2; // ebx
  DWORD CurrentProcessId; // esi
  bool v4; // zf
  __int32 v5; // ecx
  char v6; // dl
  int v7; // edx
  unsigned int v8; // ebx
  void *v10; // rcx
  LPSTR v11; // rbx
  void **v12; // rsi
  unsigned int i; // r14d
  void **v14; // [rsp+20h] [rbp-20h] BYREF
  __int64 v15; // [rsp+28h] [rbp-18h]
  __int64 v16; // [rsp+38h] [rbp-8h]
  LPSTR StringSid; // [rsp+78h] [rbp+38h] BYREF
  LPSTR v18; // [rsp+80h] [rbp+40h]

  v2 = (unsigned int)luaL_checkinteger(a1, 1);
  CurrentProcessId = GetCurrentProcessId();
  if ( (int)lua_gettop(a1) > 1 )
    CurrentProcessId = luaL_checkinteger(a1, 2);
  if ( v2 > TokenVirtualizationEnabled )
  {
    if ( v2 == TokenUIAccess || v2 == TokenLogonSid || v2 == TokenIsAppContainer || v2 == TokenCapabilities )
      goto LABEL_13;
    v5 = v2 - 40;
    v4 = v2 == TokenIsRestricted;
  }
  else
  {
    if ( v2 == TokenVirtualizationEnabled
      || v2 == TokenUser
      || v2 == TokenGroups
      || v2 == TokenPrivileges
      || v2 == TokenRestrictedSids
      || v2 == TokenElevationType )
    {
      goto LABEL_13;
    }
    v5 = v2 - 20;
    v4 = v2 == TokenElevation;
  }
  if ( !v4 && v5 != 1 )
    return 0;
LABEL_13:
  anonymous_namespace_::get_security_token_information((__int64)&v14, CurrentProcessId, v2);
  v6 = v16;
  if ( !(_BYTE)v16 )
    goto LABEL_45;
  if ( v2 > TokenVirtualizationEnabled )
  {
    switch ( v2 )
    {
      case TokenUIAccess:
        goto LABEL_51;
      case TokenLogonSid:
        goto LABEL_48;
      case TokenIsAppContainer:
        goto LABEL_51;
      case TokenCapabilities:
        goto LABEL_48;
      case TokenIsRestricted:
        goto LABEL_51;
      case MaxTokenInfoClass:
        v10 = *v14;
        StringSid = 0;
        if ( v10 )
        {
          if ( ConvertSidToStringSidA(v10, &StringSid) )
          {
            v11 = StringSid;
            v18 = StringSid;
            lua_pushstring(a1, StringSid);
            if ( v11 )
              LocalFree(v11);
            goto LABEL_56;
          }
          v6 = v16;
        }
        break;
    }
LABEL_45:
    if ( v6 )
      std::vector<char>::~vector<char>(&v14);
    return 0;
  }
  switch ( v2 )
  {
    case TokenVirtualizationEnabled:
      goto LABEL_51;
    case TokenUser:
      lua_createtable(a1, 0, 0);
      anonymous_namespace_::push_sid_and_attributes(a1);
LABEL_56:
      if ( (_BYTE)v16 )
        std::vector<char>::~vector<char>(&v14);
      return 1;
    case TokenGroups:
      goto LABEL_48;
  }
  if ( v2 != TokenPrivileges )
  {
    if ( v2 != TokenRestrictedSids )
    {
      if ( v2 != TokenElevationType && v2 != TokenElevation )
      {
        if ( v2 == TokenHasRestrictions && v15 - (_QWORD)v14 == 1 )
        {
          v7 = *(unsigned __int8 *)v14;
LABEL_54:
          lua_pushboolean(a1, v7);
          goto LABEL_56;
        }
        goto LABEL_45;
      }
LABEL_51:
      if ( v15 - (_QWORD)v14 == 4 )
      {
        if ( v2 == TokenElevationType )
        {
          lua_pushinteger(a1, *(unsigned int *)v14);
          goto LABEL_56;
        }
        v7 = *(_DWORD *)v14;
        goto LABEL_54;
      }
      goto LABEL_45;
    }
LABEL_48:
    v12 = v14;
    lua_createtable(a1, 0, 0);
    for ( i = 0; i < *(_DWORD *)v12; ++i )
    {
      lua_pushinteger(a1, i + 1);
      lua_createtable(a1, 0, 0);
      anonymous_namespace_::push_sid_and_attributes(a1);
      lua_settable(a1, -3);
    }
    goto LABEL_56;
  }
  v8 = anonymous_namespace_::security_token_privileges(a1);
  if ( (_BYTE)v16 )
    std::vector<char>::~vector<char>(&v14);
  return v8;
}

```

## disassembly

```asm
0x1800833b0  mov     [rsp-28h+arg_0], rbx
0x1800833b5  push    rbp
0x1800833b6  push    rsi
0x1800833b7  push    rdi
0x1800833b8  push    r14
0x1800833ba  push    r15
0x1800833bc  mov     rbp, rsp
0x1800833bf  sub     rsp, 40h
0x1800833c3  mov     rdi, rcx
0x1800833c6  mov     edx, 1; int
0x1800833cb  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x1800833d0  mov     rbx, rax
0x1800833d3  call    cs:__imp_GetCurrentProcessId
0x1800833d9  mov     esi, eax
0x1800833db  mov     rcx, rdi; struct lua_State *
0x1800833de  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x1800833e3  mov     r14d, 2
0x1800833e9  cmp     eax, 1
0x1800833ec  jle     short loc_1800833FC
0x1800833ee  mov     edx, r14d; int
0x1800833f1  mov     rcx, rdi; struct lua_State *
0x1800833f4  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x1800833f9  mov     rsi, rax
0x1800833fc  cmp     ebx, 18h
0x1800833ff  jg      loc_1800834B4
0x180083405  jz      short loc_180083430
0x180083407  mov     ecx, ebx
0x180083409  sub     ecx, 1
0x18008340c  jz      short loc_180083430
0x18008340e  sub     ecx, 1
0x180083411  jz      short loc_180083430
0x180083413  sub     ecx, 1
0x180083416  jz      short loc_180083430
0x180083418  sub     ecx, 8
0x18008341b  jz      short loc_180083430
0x18008341d  sub     ecx, 7
0x180083420  jz      short loc_180083430
0x180083422  sub     ecx, r14d
0x180083425  jz      short loc_180083430
0x180083427  cmp     ecx, 1
0x18008342a  jnz     loc_1800835B5
0x180083430  mov     r8d, ebx
0x180083433  mov     edx, esi
0x180083435  lea     rcx, [rbp+var_20]
0x180083439  call    _anonymous_namespace___get_security_token_information
0x18008343e  nop
0x18008343f  mov     rdx, [rbp+var_8]
0x180083443  test    dl, dl
0x180083445  jz      loc_1800835A8
0x18008344b  cmp     ebx, 18h
0x18008344e  jg      loc_180083527
0x180083454  jz      loc_180083628
0x18008345a  mov     ecx, ebx
0x18008345c  sub     ecx, 1
0x18008345f  jz      loc_180083506
0x180083465  sub     ecx, 1
0x180083468  jz      loc_1800835C8
0x18008346e  sub     ecx, 1
0x180083471  jz      short loc_1800834E2
0x180083473  sub     ecx, 8
0x180083476  jz      loc_1800835C8
0x18008347c  sub     ecx, 7
0x18008347f  jz      loc_180083628
0x180083485  sub     ecx, r14d
0x180083488  jz      loc_180083628
0x18008348e  cmp     ecx, 1
0x180083491  jnz     loc_1800835A8
0x180083497  mov     rax, [rbp+var_18]
0x18008349b  mov     rcx, [rbp+var_20]
0x18008349f  sub     rax, rcx
0x1800834a2  cmp     rax, 1
0x1800834a6  jnz     loc_1800835A8
0x1800834ac  movzx   edx, byte ptr [rcx]
0x1800834af  jmp     loc_180083644
0x1800834b4  mov     ecx, ebx
0x1800834b6  sub     ecx, 1Ah
0x1800834b9  jz      loc_180083430
0x1800834bf  sub     ecx, r14d
0x1800834c2  jz      loc_180083430
0x1800834c8  sub     ecx, 1
0x1800834cb  jz      loc_180083430
0x1800834d1  sub     ecx, 1
0x1800834d4  jz      loc_180083430
0x1800834da  sub     ecx, 0Ah
0x1800834dd  jmp     loc_180083425
0x1800834e2  mov     rdx, [rbp+var_20]
0x1800834e6  mov     rcx, rdi; struct lua_State *
0x1800834e9  call    _anonymous_namespace___security_token_privileges
0x1800834ee  mov     ebx, eax
0x1800834f0  cmp     byte ptr [rbp+var_8], 0
0x1800834f4  jz      short loc_1800834FF
0x1800834f6  lea     rcx, [rbp+var_20]
0x1800834fa  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800834ff  mov     eax, ebx
0x180083501  jmp     loc_1800835B7
0x180083506  mov     rbx, [rbp+var_20]
0x18008350a  xor     r8d, r8d; int
0x18008350d  xor     edx, edx; int
0x18008350f  mov     rcx, rdi; struct lua_State *
0x180083512  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x180083517  mov     rdx, rbx
0x18008351a  mov     rcx, rdi; struct lua_State *
0x18008351d  call    _anonymous_namespace___push_sid_and_attributes
0x180083522  jmp     loc_180083659
0x180083527  mov     ecx, ebx
0x180083529  sub     ecx, 1Ah
0x18008352c  jz      loc_180083628
0x180083532  sub     ecx, r14d
0x180083535  jz      loc_1800835C8
0x18008353b  sub     ecx, 1
0x18008353e  jz      loc_180083628
0x180083544  sub     ecx, 1
0x180083547  jz      short loc_1800835C8
0x180083549  sub     ecx, 0Ah
0x18008354c  jz      loc_180083628
0x180083552  cmp     ecx, 1
0x180083555  jnz     short loc_1800835A8
0x180083557  mov     rax, [rbp+var_20]
0x18008355b  mov     rcx, [rax]; Sid
0x18008355e  mov     [rbp+StringSid], 0
0x180083566  test    rcx, rcx
0x180083569  jz      short loc_1800835A8
0x18008356b  lea     rdx, [rbp+StringSid]; StringSid
0x18008356f  call    cs:__imp_ConvertSidToStringSidA
0x180083575  test    eax, eax
0x180083577  jz      short loc_1800835A4
0x180083579  mov     rbx, [rbp+StringSid]
0x18008357d  mov     [rbp+arg_10], rbx
0x180083581  mov     rdx, rbx; char *
0x180083584  mov     rcx, rdi; struct lua_State *
0x180083587  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18008358c  nop
0x18008358d  test    rbx, rbx
0x180083590  jz      loc_180083659
0x180083596  mov     rcx, rbx; hMem
0x180083599  call    cs:__imp_LocalFree
0x18008359f  jmp     loc_180083659
0x1800835a4  mov     rdx, [rbp+var_8]
0x1800835a8  test    dl, dl
0x1800835aa  jz      short loc_1800835B5
0x1800835ac  lea     rcx, [rbp+var_20]
0x1800835b0  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800835b5  xor     eax, eax
0x1800835b7  mov     rbx, [rsp+40h+arg_0]
0x1800835bc  add     rsp, 40h
0x1800835c0  pop     r15
0x1800835c2  pop     r14
0x1800835c4  pop     rdi
0x1800835c5  pop     rsi
0x1800835c6  pop     rbp
0x1800835c7  retn
0x1800835c8  mov     rsi, [rbp+var_20]
0x1800835cc  xor     r8d, r8d; int
0x1800835cf  xor     edx, edx; int
0x1800835d1  mov     rcx, rdi; struct lua_State *
0x1800835d4  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x1800835d9  xor     r14d, r14d
0x1800835dc  cmp     [rsi], r14d
0x1800835df  jbe     short loc_180083659
0x1800835e1  lea     r15, [rsi+8]
0x1800835e5  lea     ebx, [r14+1]
0x1800835e9  mov     edx, ebx; __int64
0x1800835eb  mov     rcx, rdi; struct lua_State *
0x1800835ee  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800835f3  xor     r8d, r8d; int
0x1800835f6  xor     edx, edx; int
0x1800835f8  mov     rcx, rdi; struct lua_State *
0x1800835fb  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x180083600  mov     edx, r14d
0x180083603  shl     rdx, 4
0x180083607  add     rdx, r15
0x18008360a  mov     rcx, rdi; struct lua_State *
0x18008360d  call    _anonymous_namespace___push_sid_and_attributes
0x180083612  mov     edx, 0FFFFFFFDh; int
0x180083617  mov     rcx, rdi; struct lua_State *
0x18008361a  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x18008361f  mov     r14d, ebx
0x180083622  cmp     ebx, [rsi]
0x180083624  jb      short loc_1800835E5
0x180083626  jmp     short loc_180083659
0x180083628  mov     rax, [rbp+var_18]
0x18008362c  mov     rcx, [rbp+var_20]
0x180083630  sub     rax, rcx
0x180083633  cmp     rax, 4
0x180083637  jnz     loc_1800835A8
0x18008363d  cmp     ebx, 12h
0x180083640  jz      short loc_18008364E
0x180083642  mov     edx, [rcx]; int
0x180083644  mov     rcx, rdi; struct lua_State *
0x180083647  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x18008364c  jmp     short loc_180083659
0x18008364e  mov     edx, [rcx]; __int64
0x180083650  mov     rcx, rdi; struct lua_State *
0x180083653  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180083658  nop
0x180083659  cmp     byte ptr [rbp+var_8], 0
0x18008365d  jz      short loc_180083668
0x18008365f  lea     rcx, [rbp+var_20]
0x180083663  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180083668  mov     eax, 1
0x18008366d  jmp     loc_1800835B7
```
