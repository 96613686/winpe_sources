# _anonymous_namespace_::file_move

- ea: `0x18006a030`
- end: `0x18006a1bc`
- name: `_anonymous_namespace_::file_move`
- size: `396`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

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
- `0x18006a030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a0f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a0f2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18006a0e8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18006a12c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18006a0e8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18006a12c`

## string_xrefs

- `0x18006a18a`: `file_move`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::file_move(struct lua_State *a1)
{
  const char *v2; // rax
  const char *v3; // rax
  DWORD v4; // edi
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
  v4 = luaL_checkinteger(a1, 3);
  if ( (int)lua_gettop(a1) > 3 && (unsigned int)lua_toboolean(a1, 4) )
  {
    v5 = (const WCHAR *)lpNewFileName;
    if ( v13 > 7 )
      v5 = lpNewFileName[0];
    v6 = (const WCHAR *)lpExistingFileName;
    if ( v15 > 7 )
      v6 = lpExistingFileName[0];
    if ( !MoveFileExW(v6, v5, v4) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          LastError,
          0,
          "[%s:%d] failed; ",
          "file_move",
          249);
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
    v8 = MoveFileExW(v10, v9, v4);
  }
  lua_pushboolean(a1, v8);
  std::wstring::~wstring(lpNewFileName);
  std::wstring::~wstring(lpExistingFileName);
  return 1;
}

```

## disassembly

```asm
0x18006a030  mov     [rsp-8+arg_8], rbx
0x18006a035  mov     [rsp-8+arg_10], rdi
0x18006a03a  push    rbp
0x18006a03b  lea     rbp, [rsp-3B0h]
0x18006a043  sub     rsp, 4B0h
0x18006a04a  mov     rax, cs:__security_cookie
0x18006a051  xor     rax, rsp
0x18006a054  mov     [rbp+3B0h+var_10], rax
0x18006a05b  mov     rbx, rcx
0x18006a05e  xor     r8d, r8d; unsigned __int64 *
0x18006a061  lea     edx, [r8+1]; int
0x18006a065  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18006a06a  mov     rdx, rax
0x18006a06d  lea     rcx, [rsp+4B0h+lpExistingFileName]
0x18006a072  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18006a077  nop
0x18006a078  xor     r8d, r8d; unsigned __int64 *
0x18006a07b  lea     edx, [r8+2]; int
0x18006a07f  mov     rcx, rbx; struct lua_State *
0x18006a082  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18006a087  mov     rdx, rax
0x18006a08a  lea     rcx, [rsp+4B0h+lpNewFileName]
0x18006a08f  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18006a094  nop
0x18006a095  mov     edx, 3; int
0x18006a09a  mov     rcx, rbx; struct lua_State *
0x18006a09d  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006a0a2  mov     rdi, rax
0x18006a0a5  mov     rcx, rbx; struct lua_State *
0x18006a0a8  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18006a0ad  cmp     eax, 3
0x18006a0b0  jle     short loc_18006A107
0x18006a0b2  mov     edx, 4; int
0x18006a0b7  mov     rcx, rbx; struct lua_State *
0x18006a0ba  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x18006a0bf  test    eax, eax
0x18006a0c1  jz      short loc_18006A107
0x18006a0c3  lea     rdx, [rsp+4B0h+lpNewFileName]
0x18006a0c8  cmp     [rsp+4B0h+var_468], 7
0x18006a0ce  cmova   rdx, [rsp+4B0h+lpNewFileName]; lpNewFileName
0x18006a0d4  lea     rcx, [rsp+4B0h+lpExistingFileName]
0x18006a0d9  cmp     [rsp+4B0h+var_448], 7
0x18006a0df  cmova   rcx, [rsp+4B0h+lpExistingFileName]; lpExistingFileName
0x18006a0e5  mov     r8d, edi; dwFlags
0x18006a0e8  call    cs:__imp_MoveFileExW
0x18006a0ee  test    eax, eax
0x18006a0f0  jnz     short loc_18006A100
0x18006a0f2  call    cs:__imp_GetLastError
0x18006a0f8  test    eax, eax
0x18006a0fa  jnz     loc_18006A180
0x18006a100  mov     edx, 1
0x18006a105  jmp     short loc_18006A139
0x18006a107  lea     rdx, [rsp+4B0h+lpNewFileName]
0x18006a10c  cmp     [rsp+4B0h+var_468], 7
0x18006a112  cmova   rdx, [rsp+4B0h+lpNewFileName]; lpNewFileName
0x18006a118  lea     rcx, [rsp+4B0h+lpExistingFileName]
0x18006a11d  cmp     [rsp+4B0h+var_448], 7
0x18006a123  cmova   rcx, [rsp+4B0h+lpExistingFileName]; lpExistingFileName
0x18006a129  mov     r8d, edi; dwFlags
0x18006a12c  call    cs:__imp_MoveFileExW
0x18006a132  xor     edx, edx
0x18006a134  test    eax, eax
0x18006a136  setnz   dl; int
0x18006a139  mov     rcx, rbx; struct lua_State *
0x18006a13c  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x18006a141  nop
0x18006a142  lea     rcx, [rsp+4B0h+lpNewFileName]
0x18006a147  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a14c  nop
0x18006a14d  lea     rcx, [rsp+4B0h+lpExistingFileName]
0x18006a152  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006a157  mov     eax, 1
0x18006a15c  mov     rcx, [rbp+3B0h+var_10]
0x18006a163  xor     rcx, rsp; StackCookie
0x18006a166  call    __security_check_cookie
0x18006a16b  lea     r11, [rsp+4B0h+var_s0]
0x18006a173  mov     rbx, [r11+18h]
0x18006a177  mov     rdi, [r11+20h]
0x18006a17b  mov     rsp, r11
0x18006a17e  pop     rbp
0x18006a17f  retn
0x18006a180  mov     edx, eax; __int64
0x18006a182  mov     [rsp+4B0h+var_488], 0F9h
0x18006a18a  lea     rax, aFileMove; "file_move"
0x18006a191  mov     [rsp+4B0h+var_490], rax
0x18006a196  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18006a19d  xor     r8d, r8d; void *
0x18006a1a0  lea     rcx, [rsp+4B0h+pExceptionObject]; this
0x18006a1a5  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18006a1aa  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18006a1b1  lea     rcx, [rsp+4B0h+pExceptionObject]; pExceptionObject
0x18006a1b6  call    _CxxThrowException_0
```
