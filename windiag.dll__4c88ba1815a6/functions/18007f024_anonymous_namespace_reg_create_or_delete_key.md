# _anonymous_namespace_::reg_create_or_delete_key

- ea: `0x18007f024`
- end: `0x18007f213`
- name: `_anonymous_namespace_::reg_create_or_delete_key`
- size: `495`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18007e7d0`
- `0x18007e820`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006690`
- `0x180006b00`
- `0x180007650`
- `0x1800083a0`
- `0x180008430`
- `0x18003af08`
- `0x180041564`
- `0x1800416a0`
- `0x18007f024`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f0da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f0da`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18007f0eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18007f0eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18007f112`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18007f112`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f193`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f193`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007f153`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007f153`

## string_xrefs

- `0x18007f1e3`: `reg_create_or_delete_key`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::reg_create_or_delete_key(struct lua_State *a1, char a2)
{
  HKEY v4; // r14
  const CHAR *v5; // rax
  bool v6; // si
  const WCHAR *v7; // rdx
  LSTATUS v8; // eax
  const WCHAR *v9; // rdx
  HKEY v10; // rcx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp-90h]
  _BYTE pExceptionObject[1072]; // [rsp+80h] [rbp-80h] BYREF

  v4 = (HKEY)luaL_checkinteger(a1, 1);
  v5 = luaL_checklstring(a1, 2, 0);
  windiag::char_to_wstring((__int64)lpSubKey, v5);
  v6 = 0;
  if ( (int)lua_gettop(a1) > 2 )
    v6 = lua_toboolean(a1, 3);
  hKey = 0;
  v7 = (const WCHAR *)lpSubKey;
  if ( !a2 )
  {
    if ( v14 > 7 )
      v7 = lpSubKey[0];
    v8 = RegCreateKeyExW(v4, v7, 0, 0, 0, 0xF013Fu, 0, &hKey, 0);
LABEL_14:
    if ( !v8 )
      goto LABEL_19;
    goto LABEL_15;
  }
  if ( v14 > 7 )
    v7 = lpSubKey[0];
  v8 = RegOpenKeyExW(v4, v7, 0, 0xF013Fu, &hKey);
  if ( !v8 )
  {
    v8 = RegDeleteTreeW(hKey, 0);
    if ( !v8 )
    {
      v9 = (const WCHAR *)lpSubKey;
      if ( v14 > 7 )
        v9 = lpSubKey[0];
      v8 = RegDeleteKeyExW(v4, v9, 0x100u, 0);
      goto LABEL_14;
    }
  }
LABEL_15:
  if ( v6 && (!a2 || v8 != 2) )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v8,
      0,
      "[%s:%d] failed; ",
      "reg_create_or_delete_key",
      318);
    throw (windiag::system_exception *)pExceptionObject;
  }
LABEL_19:
  lua_pushboolean(a1, v8 == 0);
  v10 = hKey;
  if ( hKey )
  {
    hKey = 0;
    RegCloseKey(v10);
  }
  hKey = 0;
  std::wstring::~wstring((char **)lpSubKey);
  return 1;
}

```

## disassembly

```asm
0x18007f024  mov     [rsp-8+arg_8], rbx
0x18007f029  mov     [rsp-8+arg_10], rsi
0x18007f02e  push    rbp
0x18007f02f  push    rdi
0x18007f030  push    r14
0x18007f032  lea     rbp, [rsp-3C0h]
0x18007f03a  sub     rsp, 4C0h
0x18007f041  mov     rax, cs:__security_cookie
0x18007f048  xor     rax, rsp
0x18007f04b  mov     [rbp+3D0h+var_20], rax
0x18007f052  mov     dil, dl
0x18007f055  mov     rbx, rcx
0x18007f058  mov     edx, 1; int
0x18007f05d  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007f062  mov     r14, rax
0x18007f065  xor     r8d, r8d; unsigned __int64 *
0x18007f068  lea     edx, [r8+2]; int
0x18007f06c  mov     rcx, rbx; struct lua_State *
0x18007f06f  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18007f074  mov     rdx, rax
0x18007f077  lea     rcx, [rsp+4D0h+lpSubKey]
0x18007f07c  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18007f081  nop
0x18007f082  xor     sil, sil
0x18007f085  mov     rcx, rbx; struct lua_State *
0x18007f088  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18007f08d  cmp     eax, 2
0x18007f090  jle     short loc_18007F0A5
0x18007f092  mov     edx, 3; int
0x18007f097  mov     rcx, rbx; struct lua_State *
0x18007f09a  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x18007f09f  test    eax, eax
0x18007f0a1  setnz   sil
0x18007f0a5  mov     [rsp+4D0h+hKey], 0
0x18007f0ae  lea     rdx, [rsp+4D0h+lpSubKey]
0x18007f0b3  lea     rax, [rsp+4D0h+hKey]
0x18007f0b8  mov     rcx, r14; hKey
0x18007f0bb  test    dil, dil
0x18007f0be  jz      short loc_18007F11A
0x18007f0c0  cmp     [rsp+4D0h+var_460], 7
0x18007f0c6  cmova   rdx, [rsp+4D0h+lpSubKey]; lpSubKey
0x18007f0cc  mov     [rsp+4D0h+phkResult], rax; phkResult
0x18007f0d1  mov     r9d, 0F013Fh; samDesired
0x18007f0d7  xor     r8d, r8d; ulOptions
0x18007f0da  call    cs:__imp_RegOpenKeyExW
0x18007f0e0  test    eax, eax
0x18007f0e2  jnz     short loc_18007F15D
0x18007f0e4  xor     edx, edx; lpSubKey
0x18007f0e6  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18007f0eb  call    cs:__imp_RegDeleteTreeW
0x18007f0f1  test    eax, eax
0x18007f0f3  jnz     short loc_18007F15D
0x18007f0f5  lea     rdx, [rsp+4D0h+lpSubKey]
0x18007f0fa  cmp     [rsp+4D0h+var_460], 7
0x18007f100  cmova   rdx, [rsp+4D0h+lpSubKey]; lpSubKey
0x18007f106  xor     r9d, r9d; Reserved
0x18007f109  mov     r8d, 100h; samDesired
0x18007f10f  mov     rcx, r14; hKey
0x18007f112  call    cs:__imp_RegDeleteKeyExW
0x18007f118  jmp     short loc_18007F159
0x18007f11a  cmp     [rsp+4D0h+var_460], 7
0x18007f120  cmova   rdx, [rsp+4D0h+lpSubKey]; lpSubKey
0x18007f126  mov     [rsp+4D0h+lpdwDisposition], 0; lpdwDisposition
0x18007f12f  mov     [rsp+4D0h+var_498], rax; phkResult
0x18007f134  mov     [rsp+4D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18007f13d  mov     [rsp+4D0h+samDesired], 0F013Fh; samDesired
0x18007f145  mov     dword ptr [rsp+4D0h+phkResult], 0; dwOptions
0x18007f14d  xor     r9d, r9d; lpClass
0x18007f150  xor     r8d, r8d; Reserved
0x18007f153  call    cs:__imp_RegCreateKeyExW
0x18007f159  test    eax, eax
0x18007f15b  jz      short loc_18007F170
0x18007f15d  test    sil, sil
0x18007f160  jz      short loc_18007F170
0x18007f162  test    dil, dil
0x18007f165  jz      short loc_18007F16C
0x18007f167  cmp     eax, 2
0x18007f16a  jz      short loc_18007F170
0x18007f16c  test    eax, eax
0x18007f16e  jnz     short loc_18007F1D8
0x18007f170  xor     edx, edx
0x18007f172  test    eax, eax
0x18007f174  setz    dl; int
0x18007f177  mov     rcx, rbx; struct lua_State *
0x18007f17a  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x18007f17f  nop
0x18007f180  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18007f185  test    rcx, rcx
0x18007f188  jz      short loc_18007F199
0x18007f18a  mov     [rsp+4D0h+hKey], 0
0x18007f193  call    cs:__imp_RegCloseKey
0x18007f199  mov     [rsp+4D0h+hKey], 0
0x18007f1a2  lea     rcx, [rsp+4D0h+lpSubKey]
0x18007f1a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007f1ac  mov     eax, 1
0x18007f1b1  mov     rcx, [rbp+3D0h+var_20]
0x18007f1b8  xor     rcx, rsp; StackCookie
0x18007f1bb  call    __security_check_cookie
0x18007f1c0  lea     r11, [rsp+4D0h+var_10]
0x18007f1c8  mov     rbx, [r11+28h]
0x18007f1cc  mov     rsi, [r11+30h]
0x18007f1d0  mov     rsp, r11
0x18007f1d3  pop     r14
0x18007f1d5  pop     rdi
0x18007f1d6  pop     rbp
0x18007f1d7  retn
0x18007f1d8  movsxd  rdx, eax; __int64
0x18007f1db  mov     [rsp+4D0h+samDesired], 13Eh
0x18007f1e3  lea     rax, aRegCreateOrDel; "reg_create_or_delete_key"
0x18007f1ea  mov     [rsp+4D0h+phkResult], rax
0x18007f1ef  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18007f1f6  xor     r8d, r8d; void *
0x18007f1f9  lea     rcx, [rbp+3D0h+pExceptionObject]; this
0x18007f1fd  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18007f202  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18007f209  lea     rcx, [rbp+3D0h+pExceptionObject]; pExceptionObject
0x18007f20d  call    _CxxThrowException_0
```
