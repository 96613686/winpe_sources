# _anonymous_namespace_::reg_enum_keys

- ea: `0x18007f220`
- end: `0x18007f47a`
- name: `_anonymous_namespace_::reg_enum_keys`
- size: `602`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006050`
- `0x180006690`
- `0x180006c50`
- `0x180006d40`
- `0x1800073e0`
- `0x180007650`
- `0x1800083a0`
- `0x180008430`
- `0x18003af08`
- `0x18003b0bc`
- `0x180041564`
- `0x1800415d0`
- `0x1800416a0`
- `0x180041e58`
- `0x18007ed88`
- `0x18007f220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f2c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f2c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f2f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f3cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f2f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f3cb`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18007f393`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18007f393`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::reg_enum_keys(struct lua_State *a1)
{
  HKEY v2; // rsi
  const CHAR *v3; // rax
  bool v4; // di
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  HKEY v7; // rcx
  DWORD v9; // esi
  DWORD i; // edx
  __int64 v11; // rax
  LSTATUS v12; // eax
  HKEY v13; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR lpName[3]; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+50h] [rbp-B0h] BYREF
  char *v17[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+90h] [rbp-70h] BYREF

  v2 = (HKEY)luaL_checkinteger(a1, 1);
  v3 = luaL_checklstring(a1, 2, 0);
  windiag::char_to_wstring((__int64)lpSubKey, v3);
  v4 = 0;
  if ( (int)lua_gettop(a1) > 2 )
    v4 = lua_toboolean(a1, 3);
  hKey = 0;
  v5 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(v2, v5, 0, 0x108u, &hKey);
  if ( v6 )
  {
    if ( v6 != 2 && v4 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v6,
        0,
        "[%s:%d] failed; ",
        "reg_enum_keys",
        194);
      throw (windiag::system_exception *)pExceptionObject;
    }
    v7 = hKey;
    if ( hKey )
    {
      hKey = 0;
      RegCloseKey(v7);
    }
    hKey = 0;
    std::wstring::~wstring((char **)lpSubKey);
    return 0;
  }
  else
  {
    lua_createtable(a1, 0, 0);
    std::vector<unsigned short>::vector<unsigned short>(lpName, 260);
    v9 = 0;
    for ( i = 0; ; i = v9 )
    {
      v12 = RegEnumKeyW(hKey, i, lpName[0], lpName[1] - lpName[0]);
      if ( v12 )
        break;
      lua_pushinteger(a1, ++v9);
      v11 = windiag::wchar_to_string(v17, lpName[0]);
      if ( *(_QWORD *)(v11 + 24) > 0xFu )
        v11 = *(_QWORD *)v11;
      lua_pushstring(a1, (const char *)v11);
      std::string::~string(v17);
      lua_settable(a1, 4294967293LL);
    }
    if ( v12 != 259 && v4 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v12,
        0,
        "[%s:%d] failed; ",
        "reg_enum_keys",
        214);
      throw (windiag::system_exception *)pExceptionObject;
    }
    std::vector<unsigned short>::~vector<unsigned short>(lpName);
    v13 = hKey;
    if ( hKey )
    {
      hKey = 0;
      RegCloseKey(v13);
    }
    hKey = 0;
    std::wstring::~wstring((char **)lpSubKey);
    return 1;
  }
}

```

## disassembly

```asm
0x18007f220  push    rbp
0x18007f222  push    rbx
0x18007f223  push    rsi
0x18007f224  push    rdi
0x18007f225  lea     rbp, [rsp-3D8h]
0x18007f22d  sub     rsp, 4D8h
0x18007f234  mov     rax, cs:__security_cookie
0x18007f23b  xor     rax, rsp
0x18007f23e  mov     [rbp+3F0h+var_30], rax
0x18007f245  mov     rbx, rcx
0x18007f248  mov     edx, 1; int
0x18007f24d  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007f252  mov     rsi, rax
0x18007f255  xor     r8d, r8d; unsigned __int64 *
0x18007f258  lea     edx, [r8+2]; int
0x18007f25c  mov     rcx, rbx; struct lua_State *
0x18007f25f  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18007f264  mov     rdx, rax
0x18007f267  lea     rcx, [rsp+4F0h+lpSubKey]
0x18007f26c  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18007f271  nop
0x18007f272  xor     dil, dil
0x18007f275  mov     rcx, rbx; struct lua_State *
0x18007f278  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18007f27d  cmp     eax, 2
0x18007f280  jle     short loc_18007F295
0x18007f282  mov     edx, 3; int
0x18007f287  mov     rcx, rbx; struct lua_State *
0x18007f28a  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x18007f28f  test    eax, eax
0x18007f291  setnz   dil
0x18007f295  mov     [rsp+4F0h+hKey], 0
0x18007f29e  lea     rdx, [rsp+4F0h+lpSubKey]
0x18007f2a3  cmp     [rsp+4F0h+var_488], 7
0x18007f2a9  cmova   rdx, [rsp+4F0h+lpSubKey]; lpSubKey
0x18007f2af  lea     rax, [rsp+4F0h+hKey]
0x18007f2b4  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18007f2b9  mov     r9d, 108h; samDesired
0x18007f2bf  xor     r8d, r8d; ulOptions
0x18007f2c2  mov     rcx, rsi; hKey
0x18007f2c5  call    cs:__imp_RegOpenKeyExW
0x18007f2cb  test    eax, eax
0x18007f2cd  jz      short loc_18007F310
0x18007f2cf  cmp     eax, 2
0x18007f2d2  jz      short loc_18007F2DD
0x18007f2d4  test    dil, dil
0x18007f2d7  jnz     loc_18007F43F
0x18007f2dd  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18007f2e2  test    rcx, rcx
0x18007f2e5  jz      short loc_18007F2F6
0x18007f2e7  mov     [rsp+4F0h+hKey], 0
0x18007f2f0  call    cs:__imp_RegCloseKey
0x18007f2f6  mov     [rsp+4F0h+hKey], 0
0x18007f2ff  lea     rcx, [rsp+4F0h+lpSubKey]
0x18007f304  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007f309  xor     eax, eax
0x18007f30b  jmp     loc_18007F3E9
0x18007f310  xor     r8d, r8d; int
0x18007f313  xor     edx, edx; int
0x18007f315  mov     rcx, rbx; struct lua_State *
0x18007f318  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18007f31d  mov     edx, 104h
0x18007f322  lea     rcx, [rsp+4F0h+lpName]
0x18007f327  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18007f32c  nop
0x18007f32d  xor     esi, esi
0x18007f32f  xor     edx, edx
0x18007f331  jmp     short loc_18007F37E
0x18007f333  inc     esi
0x18007f335  mov     edx, esi; __int64
0x18007f337  mov     rcx, rbx; struct lua_State *
0x18007f33a  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18007f33f  mov     rdx, [rsp+4F0h+lpName]
0x18007f344  lea     rcx, [rsp+4F0h+var_480]
0x18007f349  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x18007f34e  nop
0x18007f34f  cmp     qword ptr [rax+18h], 0Fh
0x18007f354  jbe     short loc_18007F359
0x18007f356  mov     rax, [rax]
0x18007f359  mov     rdx, rax; char *
0x18007f35c  mov     rcx, rbx; struct lua_State *
0x18007f35f  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18007f364  nop
0x18007f365  lea     rcx, [rsp+4F0h+var_480]
0x18007f36a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18007f36f  mov     edx, 0FFFFFFFDh; int
0x18007f374  mov     rcx, rbx; struct lua_State *
0x18007f377  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x18007f37c  mov     edx, esi; dwIndex
0x18007f37e  mov     r8, [rsp+4F0h+lpName]; lpName
0x18007f383  mov     r9, [rsp+4F0h+var_4B0]
0x18007f388  sub     r9, r8
0x18007f38b  sar     r9, 1; cchName
0x18007f38e  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18007f393  call    cs:__imp_RegEnumKeyW
0x18007f399  test    eax, eax
0x18007f39b  jz      short loc_18007F333
0x18007f39d  cmp     eax, 103h
0x18007f3a2  jz      short loc_18007F3AD
0x18007f3a4  test    dil, dil
0x18007f3a7  jz      short loc_18007F3AD
0x18007f3a9  test    eax, eax
0x18007f3ab  jnz     short loc_18007F404
0x18007f3ad  lea     rcx, [rsp+4F0h+lpName]
0x18007f3b2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18007f3b7  nop
0x18007f3b8  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18007f3bd  test    rcx, rcx
0x18007f3c0  jz      short loc_18007F3D1
0x18007f3c2  mov     [rsp+4F0h+hKey], 0
0x18007f3cb  call    cs:__imp_RegCloseKey
0x18007f3d1  mov     [rsp+4F0h+hKey], 0
0x18007f3da  lea     rcx, [rsp+4F0h+lpSubKey]
0x18007f3df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007f3e4  mov     eax, 1
0x18007f3e9  mov     rcx, [rbp+3F0h+var_30]
0x18007f3f0  xor     rcx, rsp; StackCookie
0x18007f3f3  call    __security_check_cookie
0x18007f3f8  add     rsp, 4D8h
0x18007f3ff  pop     rdi
0x18007f400  pop     rsi
0x18007f401  pop     rbx
0x18007f402  pop     rbp
0x18007f403  retn
0x18007f404  movsxd  rdx, eax; __int64
0x18007f407  mov     [rsp+4F0h+var_4C8], 0D6h
0x18007f40f  lea     rax, aRegEnumKeys; "reg_enum_keys"
0x18007f416  mov     [rsp+4F0h+phkResult], rax
0x18007f41b  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18007f422  xor     r8d, r8d; void *
0x18007f425  lea     rcx, [rbp+3F0h+pExceptionObject]; this
0x18007f429  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18007f42e  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18007f435  lea     rcx, [rbp+3F0h+pExceptionObject]; pExceptionObject
0x18007f439  call    _CxxThrowException_0
0x18007f43f  movsxd  rdx, eax; __int64
0x18007f442  mov     [rsp+4F0h+var_4C8], 0C2h
0x18007f44a  lea     rax, aRegEnumKeys; "reg_enum_keys"
0x18007f451  mov     [rsp+4F0h+phkResult], rax
0x18007f456  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18007f45d  xor     r8d, r8d; void *
0x18007f460  lea     rcx, [rbp+3F0h+pExceptionObject]; this
0x18007f464  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18007f469  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18007f470  lea     rcx, [rbp+3F0h+pExceptionObject]; pExceptionObject
0x18007f474  call    _CxxThrowException_0
```
