# _anonymous_namespace_::lua_gbl_kill

- ea: `0x18006f400`
- end: `0x18006f58e`
- name: `_anonymous_namespace_::lua_gbl_kill`
- size: `398`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004510`
- `0x180005520`
- `0x180006690`
- `0x1800083a0`
- `0x18003af08`
- `0x18006f400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006f495`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006f495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f49f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18006f45d`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18006f45d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f4b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f4b1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006f436`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006f436`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::lua_gbl_kill(struct lua_State *a1)
{
  DWORD v2; // eax
  HANDLE v3; // rbx
  DWORD LastError; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  DWORD v7; // eax
  _BYTE pExceptionObject[1072]; // [rsp+40h] [rbp-448h] BYREF

  v2 = luaL_checkinteger(a1, 1);
  v3 = OpenProcess(0x100001u, 0, v2);
  if ( !v3 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "lua_gbl_kill",
        1010);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  if ( !TerminateProcess(v3, 0xFFFFFFFF) )
  {
    v5 = GetLastError();
    if ( v5 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v5,
        0,
        "[%s:%d] failed; ",
        "lua_gbl_kill",
        1013);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  if ( (int)lua_gettop(a1) > 1 )
  {
    v6 = luaL_checkinteger(a1, 2);
    if ( WaitForSingleObject(v3, v6) )
    {
      v7 = GetLastError();
      if ( v7 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v7,
          0,
          "[%s:%d] failed; ",
          "lua_gbl_kill",
          1018);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
  }
  if ( v3 )
    CloseHandle(v3);
  return 0;
}

```

## disassembly

```asm
0x18006f400  mov     [rsp+arg_8], rbx
0x18006f405  push    rdi
0x18006f406  sub     rsp, 480h
0x18006f40d  mov     rax, cs:__security_cookie
0x18006f414  xor     rax, rsp
0x18006f417  mov     [rsp+488h+var_18], rax
0x18006f41f  mov     rdi, rcx
0x18006f422  mov     edx, 1; int
0x18006f427  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006f42c  mov     r8, rax; dwProcessId
0x18006f42f  xor     edx, edx; bInheritHandle
0x18006f431  mov     ecx, 100001h; dwDesiredAccess
0x18006f436  call    cs:__imp_OpenProcess
0x18006f43c  mov     rbx, rax
0x18006f43f  mov     [rsp+488h+var_458], rax
0x18006f444  test    rax, rax
0x18006f447  jnz     short loc_18006F457
0x18006f449  call    cs:__imp_GetLastError
0x18006f44f  test    eax, eax
0x18006f451  jnz     loc_18006F516
0x18006f457  or      edx, 0FFFFFFFFh; uExitCode
0x18006f45a  mov     rcx, rbx; hProcess
0x18006f45d  call    cs:__imp_TerminateProcess
0x18006f463  test    eax, eax
0x18006f465  jnz     short loc_18006F475
0x18006f467  call    cs:__imp_GetLastError
0x18006f46d  test    eax, eax
0x18006f46f  jnz     loc_18006F552
0x18006f475  mov     rcx, rdi; struct lua_State *
0x18006f478  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18006f47d  cmp     eax, 1
0x18006f480  jle     short loc_18006F4A9
0x18006f482  mov     edx, 2; int
0x18006f487  mov     rcx, rdi; struct lua_State *
0x18006f48a  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006f48f  mov     rdx, rax; dwMilliseconds
0x18006f492  mov     rcx, rbx; hHandle
0x18006f495  call    cs:__imp_WaitForSingleObject
0x18006f49b  test    eax, eax
0x18006f49d  jz      short loc_18006F4A9
0x18006f49f  call    cs:__imp_GetLastError
0x18006f4a5  test    eax, eax
0x18006f4a7  jnz     short loc_18006F4DA
0x18006f4a9  test    rbx, rbx
0x18006f4ac  jz      short loc_18006F4B7
0x18006f4ae  mov     rcx, rbx; hObject
0x18006f4b1  call    cs:__imp_CloseHandle
0x18006f4b7  xor     eax, eax
0x18006f4b9  mov     rcx, [rsp+488h+var_18]
0x18006f4c1  xor     rcx, rsp; StackCookie
0x18006f4c4  call    __security_check_cookie
0x18006f4c9  mov     rbx, [rsp+488h+arg_8]
0x18006f4d1  add     rsp, 480h
0x18006f4d8  pop     rdi
0x18006f4d9  retn
0x18006f4da  mov     edx, eax; __int64
0x18006f4dc  mov     [rsp+488h+var_460], 3FAh
0x18006f4e4  lea     rax, aLuaGblKill; "lua_gbl_kill"
0x18006f4eb  mov     [rsp+488h+var_468], rax
0x18006f4f0  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18006f4f7  xor     r8d, r8d; void *
0x18006f4fa  lea     rcx, [rsp+488h+pExceptionObject]; this
0x18006f4ff  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18006f504  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18006f50b  lea     rcx, [rsp+488h+pExceptionObject]; pExceptionObject
0x18006f510  call    _CxxThrowException_0
0x18006f516  mov     edx, eax; __int64
0x18006f518  mov     [rsp+488h+var_460], 3F2h
0x18006f520  lea     rax, aLuaGblKill; "lua_gbl_kill"
0x18006f527  mov     [rsp+488h+var_468], rax
0x18006f52c  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18006f533  xor     r8d, r8d; void *
0x18006f536  lea     rcx, [rsp+488h+pExceptionObject]; this
0x18006f53b  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18006f540  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18006f547  lea     rcx, [rsp+488h+pExceptionObject]; pExceptionObject
0x18006f54c  call    _CxxThrowException_0
0x18006f552  mov     edx, eax; __int64
0x18006f554  mov     [rsp+488h+var_460], 3F5h
0x18006f55c  lea     rax, aLuaGblKill; "lua_gbl_kill"
0x18006f563  mov     [rsp+488h+var_468], rax
0x18006f568  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18006f56f  xor     r8d, r8d; void *
0x18006f572  lea     rcx, [rsp+488h+pExceptionObject]; this
0x18006f577  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18006f57c  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18006f583  lea     rcx, [rsp+488h+pExceptionObject]; pExceptionObject
0x18006f588  call    _CxxThrowException_0
```
