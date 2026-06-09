# _anonymous_namespace_::reg_enum_values

- ea: `0x18007f480`
- end: `0x18007f818`
- name: `_anonymous_namespace_::reg_enum_values`
- size: `920`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006050`
- `0x180006690`
- `0x180006c50`
- `0x180006c90`
- `0x1800073e0`
- `0x180007650`
- `0x1800083a0`
- `0x180008430`
- `0x18003af08`
- `0x18003b0bc`
- `0x18003f0b4`
- `0x18003f850`
- `0x180041564`
- `0x1800415d0`
- `0x1800416a0`
- `0x180041e58`
- `0x180057e2c`
- `0x18007e830`
- `0x18007ed88`
- `0x18007f480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f528`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f528`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18007f665`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18007f665`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f54f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f762`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f54f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f762`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::reg_enum_values(struct lua_State *a1)
{
  HKEY v2; // rsi
  const char *v3; // rax
  bool v4; // di
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  HKEY v7; // rcx
  DWORD v9; // esi
  DWORD i; // edx
  __int64 v11; // rax
  __int64 v12; // rdx
  LSTATUS v13; // eax
  __int64 v14; // rdi
  unsigned __int64 v15; // rsi
  const char *v16; // rdx
  unsigned __int64 v17; // r8
  HKEY v18; // rcx
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchValueName; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  LPWSTR lpValueName[3]; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v28[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+E0h] [rbp-20h] BYREF

  v2 = (HKEY)luaL_checkinteger(a1, 1);
  v3 = luaL_checklstring(a1, 2, 0);
  windiag::char_to_wstring(lpSubKey, v3);
  v4 = 0;
  if ( (int)lua_gettop(a1) > 2 )
    v4 = (unsigned int)lua_toboolean(a1, 3) != 0;
  hKey = 0;
  v5 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(v2, v5, 0, 0x101u, &hKey);
  if ( v6 )
  {
    if ( v6 != 2 && v4 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v6,
        0,
        "[%s:%d] failed; ",
        "reg_enum_values",
        240);
      throw (windiag::system_exception *)pExceptionObject;
    }
    v7 = hKey;
    if ( hKey )
    {
      hKey = 0;
      RegCloseKey(v7);
    }
    hKey = 0;
    std::wstring::~wstring(lpSubKey);
    return 0;
  }
  else
  {
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    std::vector<unsigned short>::vector<unsigned short>(lpValueName, 0x4000);
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      cchValueName = lpValueName[1] - lpValueName[0];
      Type = 0;
      v13 = RegEnumValueW(hKey, i, lpValueName[0], &cchValueName, 0, &Type, 0, 0);
      if ( v13 )
        break;
      if ( *((_QWORD *)&v24 + 1) == v25 )
      {
        std::vector<unsigned long>::_Emplace_reallocate<unsigned long const &>(&v24, *((_QWORD *)&v24 + 1), &Type);
      }
      else
      {
        **((_DWORD **)&v24 + 1) = Type;
        *((_QWORD *)&v24 + 1) += 4LL;
      }
      v11 = windiag::wchar_to_string(v28, lpValueName[0]);
      v12 = *((_QWORD *)&v22 + 1);
      if ( *((_QWORD *)&v22 + 1) == v23 )
      {
        std::vector<std::string>::_Emplace_reallocate<std::string>(&v22, *((_QWORD *)&v22 + 1), v11);
      }
      else
      {
        **((_OWORD **)&v22 + 1) = 0;
        *(_QWORD *)(v12 + 16) = 0;
        *(_QWORD *)(v12 + 24) = 0;
        *(_OWORD *)v12 = *(_OWORD *)v11;
        *(_OWORD *)(v12 + 16) = *(_OWORD *)(v11 + 16);
        *(_QWORD *)(v11 + 16) = 0;
        *(_QWORD *)(v11 + 24) = 15;
        *(_BYTE *)v11 = 0;
        *((_QWORD *)&v22 + 1) += 32LL;
      }
      std::string::~string(v28);
      ++v9;
    }
    if ( v13 != 259 && v4 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v13,
        0,
        "[%s:%d] failed; ",
        "reg_enum_values",
        261);
      throw (windiag::system_exception *)pExceptionObject;
    }
    lua_createtable(a1, 0, 0);
    lua_createtable(a1, 0, 0);
    v14 = 0;
    if ( (__int64)(*((_QWORD *)&v22 + 1) - v22) >> 5 )
    {
      do
      {
        v15 = v14 + 1;
        lua_pushinteger(a1, v14 + 1);
        v16 = (const char *)(v22 + 32 * v14);
        v17 = *((_QWORD *)v16 + 2);
        if ( *((_QWORD *)v16 + 3) > 0xFu )
          v16 = *(const char **)v16;
        lua_pushlstring(a1, v16, v17);
        lua_settable(a1, -4);
        lua_pushinteger(a1, v14 + 1);
        lua_pushinteger(a1, *(unsigned int *)(v24 + 4 * v14));
        lua_settable(a1, -3);
        ++v14;
      }
      while ( v15 < (__int64)(*((_QWORD *)&v22 + 1) - v22) >> 5 );
    }
    std::vector<unsigned short>::~vector<unsigned short>(lpValueName);
    std::vector<unsigned long>::~vector<unsigned long>(&v24);
    std::vector<std::string>::_Tidy(&v22);
    v18 = hKey;
    if ( hKey )
    {
      hKey = 0;
      RegCloseKey(v18);
    }
    hKey = 0;
    std::wstring::~wstring(lpSubKey);
    return 2;
  }
}

```

## disassembly

```asm
0x18007f480  mov     [rsp-8+arg_8], rbx
0x18007f485  mov     [rsp-8+arg_10], rsi
0x18007f48a  push    rbp
0x18007f48b  push    rdi
0x18007f48c  push    r14
0x18007f48e  lea     rbp, [rsp-420h]
0x18007f496  sub     rsp, 520h
0x18007f49d  mov     rax, cs:__security_cookie
0x18007f4a4  xor     rax, rsp
0x18007f4a7  mov     [rbp+430h+var_20], rax
0x18007f4ae  mov     rbx, rcx
0x18007f4b1  mov     edx, 1; int
0x18007f4b6  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007f4bb  mov     rsi, rax
0x18007f4be  xor     r8d, r8d; unsigned __int64 *
0x18007f4c1  lea     edx, [r8+2]; int
0x18007f4c5  mov     rcx, rbx; struct lua_State *
0x18007f4c8  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18007f4cd  mov     rdx, rax
0x18007f4d0  lea     rcx, [rbp+430h+lpSubKey]
0x18007f4d4  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18007f4d9  nop
0x18007f4da  xor     r14d, r14d
0x18007f4dd  mov     dil, r14b
0x18007f4e0  mov     rcx, rbx; struct lua_State *
0x18007f4e3  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18007f4e8  cmp     eax, 2
0x18007f4eb  jle     short loc_18007F4FF
0x18007f4ed  lea     edx, [r14+3]; int
0x18007f4f1  mov     rcx, rbx; struct lua_State *
0x18007f4f4  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x18007f4f9  test    eax, eax
0x18007f4fb  setnz   dil
0x18007f4ff  mov     [rsp+530h+hKey], r14
0x18007f504  lea     rdx, [rbp+430h+lpSubKey]
0x18007f508  cmp     [rbp+430h+var_478], 7
0x18007f50d  cmova   rdx, [rbp+430h+lpSubKey]; lpSubKey
0x18007f512  lea     rax, [rsp+530h+hKey]
0x18007f517  mov     [rsp+530h+phkResult], rax; phkResult
0x18007f51c  mov     r9d, 101h; samDesired
0x18007f522  xor     r8d, r8d; ulOptions
0x18007f525  mov     rcx, rsi; hKey
0x18007f528  call    cs:__imp_RegOpenKeyExW
0x18007f52e  test    eax, eax
0x18007f530  jz      short loc_18007F56A
0x18007f532  cmp     eax, 2
0x18007f535  jz      short loc_18007F540
0x18007f537  test    dil, dil
0x18007f53a  jnz     loc_18007F7DD
0x18007f540  mov     rcx, [rsp+530h+hKey]; hKey
0x18007f545  test    rcx, rcx
0x18007f548  jz      short loc_18007F555
0x18007f54a  mov     [rsp+530h+hKey], r14
0x18007f54f  call    cs:__imp_RegCloseKey
0x18007f555  mov     [rsp+530h+hKey], r14
0x18007f55a  lea     rcx, [rbp+430h+lpSubKey]
0x18007f55e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007f563  xor     eax, eax
0x18007f565  jmp     loc_18007F77B
0x18007f56a  xorps   xmm0, xmm0
0x18007f56d  movdqu  [rsp+530h+var_4D8], xmm0
0x18007f573  mov     [rsp+530h+var_4C8], r14
0x18007f578  movdqu  [rsp+530h+var_4C0], xmm0
0x18007f57e  mov     [rbp+430h+var_4B0], r14
0x18007f582  mov     edx, 4000h
0x18007f587  lea     rcx, [rbp+430h+lpValueName]
0x18007f58b  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18007f590  nop
0x18007f591  mov     esi, r14d
0x18007f594  xor     edx, edx
0x18007f596  jmp     loc_18007F62B
0x18007f59b  mov     rdx, qword ptr [rsp+530h+var_4C0+8]
0x18007f5a0  cmp     rdx, [rbp+430h+var_4B0]
0x18007f5a4  jz      short loc_18007F5B4
0x18007f5a6  mov     eax, [rsp+530h+Type]
0x18007f5aa  mov     [rdx], eax
0x18007f5ac  add     qword ptr [rsp+530h+var_4C0+8], 4
0x18007f5b2  jmp     short loc_18007F5C3
0x18007f5b4  lea     r8, [rsp+530h+Type]
0x18007f5b9  lea     rcx, [rsp+530h+var_4C0]
0x18007f5be  call    ??$_Emplace_reallocate@AEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAKAEBK@Z; std::vector<ulong>::_Emplace_reallocate<ulong const &>(ulong * const,ulong const &)
0x18007f5c3  mov     rdx, [rbp+430h+lpValueName]
0x18007f5c7  lea     rcx, [rbp+430h+var_470]
0x18007f5cb  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x18007f5d0  nop
0x18007f5d1  mov     rdx, qword ptr [rsp+530h+var_4D8+8]
0x18007f5d6  cmp     rdx, [rsp+530h+var_4C8]
0x18007f5db  jz      short loc_18007F610
0x18007f5dd  xorps   xmm0, xmm0
0x18007f5e0  movups  xmmword ptr [rdx], xmm0
0x18007f5e3  mov     [rdx+10h], r14
0x18007f5e7  mov     [rdx+18h], r14
0x18007f5eb  movups  xmm0, xmmword ptr [rax]
0x18007f5ee  movups  xmmword ptr [rdx], xmm0
0x18007f5f1  movups  xmm1, xmmword ptr [rax+10h]
0x18007f5f5  movups  xmmword ptr [rdx+10h], xmm1
0x18007f5f9  mov     [rax+10h], r14
0x18007f5fd  mov     qword ptr [rax+18h], 0Fh
0x18007f605  mov     [rax], r14b
0x18007f608  add     qword ptr [rsp+530h+var_4D8+8], 20h ; ' '
0x18007f60e  jmp     short loc_18007F61E
0x18007f610  mov     r8, rax
0x18007f613  lea     rcx, [rsp+530h+var_4D8]
0x18007f618  call    ??$_Emplace_reallocate@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::string>::_Emplace_reallocate<std::string>(std::string * const,std::string &&)
0x18007f61d  nop
0x18007f61e  lea     rcx, [rbp+430h+var_470]
0x18007f622  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18007f627  inc     esi
0x18007f629  mov     edx, esi; dwIndex
0x18007f62b  mov     r8, [rbp+430h+lpValueName]; lpValueName
0x18007f62f  mov     rax, [rbp+430h+var_4A0]
0x18007f633  sub     rax, r8
0x18007f636  sar     rax, 1
0x18007f639  mov     [rsp+530h+lpcbData], r14; lpcbData
0x18007f63e  mov     [rsp+530h+cchValueName], eax
0x18007f642  mov     [rsp+530h+lpData], r14; lpData
0x18007f647  lea     rax, [rsp+530h+Type]
0x18007f64c  mov     [rsp+530h+lpType], rax; lpType
0x18007f651  mov     [rsp+530h+phkResult], r14; lpReserved
0x18007f656  mov     [rsp+530h+Type], r14d
0x18007f65b  lea     r9, [rsp+530h+cchValueName]; lpcchValueName
0x18007f660  mov     rcx, [rsp+530h+hKey]; hKey
0x18007f665  call    cs:__imp_RegEnumValueW
0x18007f66b  test    eax, eax
0x18007f66d  jz      loc_18007F59B
0x18007f673  cmp     eax, 103h
0x18007f678  jz      short loc_18007F687
0x18007f67a  test    dil, dil
0x18007f67d  jz      short loc_18007F687
0x18007f67f  test    eax, eax
0x18007f681  jnz     loc_18007F7A2
0x18007f687  xor     r8d, r8d; int
0x18007f68a  xor     edx, edx; int
0x18007f68c  mov     rcx, rbx; struct lua_State *
0x18007f68f  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18007f694  xor     r8d, r8d; int
0x18007f697  xor     edx, edx; int
0x18007f699  mov     rcx, rbx; struct lua_State *
0x18007f69c  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18007f6a1  mov     rdi, r14
0x18007f6a4  mov     rax, qword ptr [rsp+530h+var_4D8+8]
0x18007f6a9  sub     rax, qword ptr [rsp+530h+var_4D8]
0x18007f6ae  sar     rax, 5
0x18007f6b2  test    rax, rax
0x18007f6b5  jz      short loc_18007F733
0x18007f6b7  lea     rsi, [rdi+1]
0x18007f6bb  mov     rdx, rsi; __int64
0x18007f6be  mov     rcx, rbx; struct lua_State *
0x18007f6c1  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18007f6c6  mov     rdx, rdi
0x18007f6c9  shl     rdx, 5
0x18007f6cd  add     rdx, qword ptr [rsp+530h+var_4D8]
0x18007f6d2  mov     r8, [rdx+10h]; unsigned __int64
0x18007f6d6  cmp     qword ptr [rdx+18h], 0Fh
0x18007f6db  jbe     short loc_18007F6E0
0x18007f6dd  mov     rdx, [rdx]; char *
0x18007f6e0  mov     rcx, rbx; struct lua_State *
0x18007f6e3  call    ?lua_pushlstring@@YAPEBDPEAUlua_State@@PEBD_K@Z; lua_pushlstring(lua_State *,char const *,unsigned __int64)
0x18007f6e8  mov     edx, 0FFFFFFFCh; int
0x18007f6ed  mov     rcx, rbx; struct lua_State *
0x18007f6f0  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x18007f6f5  mov     rdx, rsi; __int64
0x18007f6f8  mov     rcx, rbx; struct lua_State *
0x18007f6fb  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18007f700  mov     rax, qword ptr [rsp+530h+var_4C0]
0x18007f705  mov     edx, [rax+rdi*4]; __int64
0x18007f708  mov     rcx, rbx; struct lua_State *
0x18007f70b  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18007f710  mov     edx, 0FFFFFFFDh; int
0x18007f715  mov     rcx, rbx; struct lua_State *
0x18007f718  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x18007f71d  mov     rdi, rsi
0x18007f720  mov     rax, qword ptr [rsp+530h+var_4D8+8]
0x18007f725  sub     rax, qword ptr [rsp+530h+var_4D8]
0x18007f72a  sar     rax, 5
0x18007f72e  cmp     rsi, rax
0x18007f731  jb      short loc_18007F6B7
0x18007f733  lea     rcx, [rbp+430h+lpValueName]
0x18007f737  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18007f73c  nop
0x18007f73d  lea     rcx, [rsp+530h+var_4C0]
0x18007f742  call    ??1?$vector@KV?$allocator@K@std@@@std@@QEAA@XZ; std::vector<ulong>::~vector<ulong>(void)
0x18007f747  nop
0x18007f748  lea     rcx, [rsp+530h+var_4D8]
0x18007f74d  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18007f752  nop
0x18007f753  mov     rcx, [rsp+530h+hKey]; hKey
0x18007f758  test    rcx, rcx
0x18007f75b  jz      short loc_18007F768
0x18007f75d  mov     [rsp+530h+hKey], r14
0x18007f762  call    cs:__imp_RegCloseKey
0x18007f768  mov     [rsp+530h+hKey], r14
0x18007f76d  lea     rcx, [rbp+430h+lpSubKey]
0x18007f771  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007f776  mov     eax, 2
0x18007f77b  mov     rcx, [rbp+430h+var_20]
0x18007f782  xor     rcx, rsp; StackCookie
0x18007f785  call    __security_check_cookie
0x18007f78a  lea     r11, [rsp+530h+var_10]
0x18007f792  mov     rbx, [r11+28h]
0x18007f796  mov     rsi, [r11+30h]
0x18007f79a  mov     rsp, r11
0x18007f79d  pop     r14
0x18007f79f  pop     rdi
0x18007f7a0  pop     rbp
0x18007f7a1  retn
0x18007f7a2  movsxd  rdx, eax; __int64
0x18007f7a5  mov     dword ptr [rsp+530h+lpType], 105h
0x18007f7ad  lea     rax, aRegEnumValues; "reg_enum_values"
0x18007f7b4  mov     [rsp+530h+phkResult], rax
0x18007f7b9  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18007f7c0  xor     r8d, r8d; void *
0x18007f7c3  lea     rcx, [rbp+430h+pExceptionObject]; this
0x18007f7c7  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18007f7cc  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18007f7d3  lea     rcx, [rbp+430h+pExceptionObject]; pExceptionObject
0x18007f7d7  call    _CxxThrowException_0
0x18007f7dd  movsxd  rdx, eax; __int64
0x18007f7e0  mov     dword ptr [rsp+530h+lpType], 0F0h
0x18007f7e8  lea     rax, aRegEnumValues; "reg_enum_values"
0x18007f7ef  mov     [rsp+530h+phkResult], rax
0x18007f7f4  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18007f7fb  xor     r8d, r8d; void *
0x18007f7fe  lea     rcx, [rbp+430h+pExceptionObject]; this
0x18007f802  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18007f807  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18007f80e  lea     rcx, [rbp+430h+pExceptionObject]; pExceptionObject
0x18007f812  call    _CxxThrowException_0
```
