# _anonymous_namespace_::file_copy

- ea: `0x180068e50`
- end: `0x180068fdb`
- name: `_anonymous_namespace_::file_copy`
- size: `395`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006690`
- `0x180006b00`
- `0x180007650`
- `0x180008430`
- `0x18003af08`
- `0x180041564`
- `0x1800416a0`
- `0x180068e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068f11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068f11`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180068f07`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180068f4b`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180068f07`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180068f4b`

## string_xrefs

- `0x180068fa9`: `file_copy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::file_copy(struct lua_State *a1)
{
  const char *v2; // rax
  const char *v3; // rax
  int v4; // edi
  const WCHAR *v5; // rdx
  const WCHAR *v6; // rcx
  DWORD LastError; // eax
  BOOL v8; // edx
  const WCHAR *v9; // rdx
  const WCHAR *v10; // rcx
  LPCWSTR lpNewFileName[3]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v13; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpExistingFileName[3]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v15; // [rsp+68h] [rbp-98h]
  _BYTE pExceptionObject[1072]; // [rsp+70h] [rbp-90h] BYREF

  v2 = luaL_checklstring(a1, 1, 0);
  windiag::char_to_wstring(lpExistingFileName, v2);
  v3 = luaL_checklstring(a1, 2, 0);
  windiag::char_to_wstring(lpNewFileName, v3);
  v4 = lua_toboolean(a1, 3);
  if ( (int)lua_gettop(a1) > 3 && (unsigned int)lua_toboolean(a1, 4) )
  {
    v5 = (const WCHAR *)lpNewFileName;
    if ( v13 > 7 )
      v5 = lpNewFileName[0];
    v6 = (const WCHAR *)lpExistingFileName;
    if ( v15 > 7 )
      v6 = lpExistingFileName[0];
    if ( !CopyFileW(v6, v5, v4) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          LastError,
          0,
          "[%s:%d] failed; ",
          "file_copy",
          272);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    v8 = 1;
  }
  else
  {
    v9 = (const WCHAR *)lpNewFileName;
    if ( v13 > 7 )
      v9 = lpNewFileName[0];
    v10 = (const WCHAR *)lpExistingFileName;
    if ( v15 > 7 )
      v10 = lpExistingFileName[0];
    v8 = CopyFileW(v10, v9, v4);
  }
  lua_pushboolean(a1, v8);
  std::wstring::~wstring(lpNewFileName);
  std::wstring::~wstring(lpExistingFileName);
  return 1;
}

```

## disassembly

```asm
0x180068e50  mov     [rsp-8+arg_8], rbx
0x180068e55  mov     [rsp-8+arg_10], rdi
0x180068e5a  push    rbp
0x180068e5b  lea     rbp, [rsp-3B0h]
0x180068e63  sub     rsp, 4B0h
0x180068e6a  mov     rax, cs:__security_cookie
0x180068e71  xor     rax, rsp
0x180068e74  mov     [rbp+3B0h+var_10], rax
0x180068e7b  mov     rbx, rcx
0x180068e7e  xor     r8d, r8d; unsigned __int64 *
0x180068e81  lea     edx, [r8+1]; int
0x180068e85  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x180068e8a  mov     rdx, rax
0x180068e8d  lea     rcx, [rsp+4B0h+lpExistingFileName]
0x180068e92  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180068e97  nop
0x180068e98  xor     r8d, r8d; unsigned __int64 *
0x180068e9b  lea     edx, [r8+2]; int
0x180068e9f  mov     rcx, rbx; struct lua_State *
0x180068ea2  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x180068ea7  mov     rdx, rax
0x180068eaa  lea     rcx, [rsp+4B0h+lpNewFileName]
0x180068eaf  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180068eb4  nop
0x180068eb5  mov     edx, 3; int
0x180068eba  mov     rcx, rbx; struct lua_State *
0x180068ebd  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180068ec2  mov     edi, eax
0x180068ec4  mov     rcx, rbx; struct lua_State *
0x180068ec7  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x180068ecc  cmp     eax, 3
0x180068ecf  jle     short loc_180068F26
0x180068ed1  mov     edx, 4; int
0x180068ed6  mov     rcx, rbx; struct lua_State *
0x180068ed9  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180068ede  test    eax, eax
0x180068ee0  jz      short loc_180068F26
0x180068ee2  lea     rdx, [rsp+4B0h+lpNewFileName]
0x180068ee7  cmp     [rsp+4B0h+var_468], 7
0x180068eed  cmova   rdx, [rsp+4B0h+lpNewFileName]; lpNewFileName
0x180068ef3  lea     rcx, [rsp+4B0h+lpExistingFileName]
0x180068ef8  cmp     [rsp+4B0h+var_448], 7
0x180068efe  cmova   rcx, [rsp+4B0h+lpExistingFileName]; lpExistingFileName
0x180068f04  mov     r8d, edi; bFailIfExists
0x180068f07  call    cs:__imp_CopyFileW
0x180068f0d  test    eax, eax
0x180068f0f  jnz     short loc_180068F1F
0x180068f11  call    cs:__imp_GetLastError
0x180068f17  test    eax, eax
0x180068f19  jnz     loc_180068F9F
0x180068f1f  mov     edx, 1
0x180068f24  jmp     short loc_180068F58
0x180068f26  lea     rdx, [rsp+4B0h+lpNewFileName]
0x180068f2b  cmp     [rsp+4B0h+var_468], 7
0x180068f31  cmova   rdx, [rsp+4B0h+lpNewFileName]; lpNewFileName
0x180068f37  lea     rcx, [rsp+4B0h+lpExistingFileName]
0x180068f3c  cmp     [rsp+4B0h+var_448], 7
0x180068f42  cmova   rcx, [rsp+4B0h+lpExistingFileName]; lpExistingFileName
0x180068f48  mov     r8d, edi; bFailIfExists
0x180068f4b  call    cs:__imp_CopyFileW
0x180068f51  xor     edx, edx
0x180068f53  test    eax, eax
0x180068f55  setnz   dl; int
0x180068f58  mov     rcx, rbx; struct lua_State *
0x180068f5b  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x180068f60  nop
0x180068f61  lea     rcx, [rsp+4B0h+lpNewFileName]
0x180068f66  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180068f6b  nop
0x180068f6c  lea     rcx, [rsp+4B0h+lpExistingFileName]
0x180068f71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180068f76  mov     eax, 1
0x180068f7b  mov     rcx, [rbp+3B0h+var_10]
0x180068f82  xor     rcx, rsp; StackCookie
0x180068f85  call    __security_check_cookie
0x180068f8a  lea     r11, [rsp+4B0h+var_s0]
0x180068f92  mov     rbx, [r11+18h]
0x180068f96  mov     rdi, [r11+20h]
0x180068f9a  mov     rsp, r11
0x180068f9d  pop     rbp
0x180068f9e  retn
0x180068f9f  mov     edx, eax; __int64
0x180068fa1  mov     [rsp+4B0h+var_488], 110h
0x180068fa9  lea     rax, aFileCopy; "file_copy"
0x180068fb0  mov     [rsp+4B0h+var_490], rax
0x180068fb5  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180068fbc  xor     r8d, r8d; void *
0x180068fbf  lea     rcx, [rsp+4B0h+pExceptionObject]; this
0x180068fc4  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180068fc9  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180068fd0  lea     rcx, [rsp+4B0h+pExceptionObject]; pExceptionObject
0x180068fd5  call    _CxxThrowException_0
```
