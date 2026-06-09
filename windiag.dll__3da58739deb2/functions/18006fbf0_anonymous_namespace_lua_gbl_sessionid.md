# _anonymous_namespace_::lua_gbl_sessionid

- ea: `0x18006fbf0`
- end: `0x18006fda1`
- name: `_anonymous_namespace_::lua_gbl_sessionid`
- size: `433`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006690`
- `0x180006c50`
- `0x180007650`
- `0x180007950`
- `0x18003af08`
- `0x18006fbf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fcbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fc44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fcbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006fc27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006fc27`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006fc3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006fc3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fcfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fcfa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18006fcd2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x18006fcd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006fcb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006fcb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::lua_gbl_sessionid(struct lua_State *a1)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  bool v4; // di
  DWORD v5; // eax
  DWORD active; // eax
  void *v7; // rcx
  DWORD TokenInformation; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+50h] [rbp-B0h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "lua_gbl_sessionid",
        335);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v4 = 0;
  if ( (int)lua_gettop(a1) > 0 && (unsigned int)lua_type(a1, 1) == 1 )
    v4 = (unsigned int)lua_toboolean(a1, 1) != 0;
  ReturnLength[0] = 0;
  TokenInformation = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, ReturnLength) )
  {
    v5 = GetLastError();
    if ( v5 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v5,
        0,
        "[%s:%d] failed; ",
        "lua_gbl_sessionid",
        342);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  active = TokenInformation;
  if ( !TokenInformation && v4 )
  {
    active = WTSGetActiveConsoleSessionId();
    TokenInformation = active;
  }
  lua_pushinteger(a1, active);
  v7 = TokenHandle;
  if ( TokenHandle )
  {
    TokenHandle = 0;
    CloseHandle(v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18006fbf0  mov     [rsp-8+arg_8], rbx
0x18006fbf5  mov     [rsp-8+arg_10], rdi
0x18006fbfa  push    rbp
0x18006fbfb  lea     rbp, [rsp-390h]
0x18006fc03  sub     rsp, 490h
0x18006fc0a  mov     rax, cs:__security_cookie
0x18006fc11  xor     rax, rsp
0x18006fc14  mov     [rbp+390h+var_10], rax
0x18006fc1b  mov     rbx, rcx
0x18006fc1e  mov     [rsp+490h+TokenHandle], 0
0x18006fc27  call    cs:__imp_GetCurrentProcess
0x18006fc2d  lea     r8, [rsp+490h+TokenHandle]; TokenHandle
0x18006fc32  mov     edx, 8; DesiredAccess
0x18006fc37  mov     rcx, rax; ProcessHandle
0x18006fc3a  call    cs:__imp_OpenProcessToken
0x18006fc40  test    eax, eax
0x18006fc42  jnz     short loc_18006FC52
0x18006fc44  call    cs:__imp_GetLastError
0x18006fc4a  test    eax, eax
0x18006fc4c  jnz     loc_18006FD65
0x18006fc52  xor     dil, dil
0x18006fc55  mov     rcx, rbx; struct lua_State *
0x18006fc58  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18006fc5d  test    eax, eax
0x18006fc5f  jle     short loc_18006FC83
0x18006fc61  mov     edx, 1; int
0x18006fc66  mov     rcx, rbx; struct lua_State *
0x18006fc69  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18006fc6e  cmp     eax, 1
0x18006fc71  jnz     short loc_18006FC83
0x18006fc73  mov     edx, eax; int
0x18006fc75  mov     rcx, rbx; struct lua_State *
0x18006fc78  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x18006fc7d  test    eax, eax
0x18006fc7f  setnz   dil
0x18006fc83  mov     [rsp+490h+var_450], 0
0x18006fc8b  mov     [rsp+490h+TokenInformation], 0
0x18006fc93  lea     rax, [rsp+490h+var_450]
0x18006fc98  mov     [rsp+490h+ReturnLength], rax; ReturnLength
0x18006fc9d  mov     r9d, 4; TokenInformationLength
0x18006fca3  lea     r8, [rsp+490h+TokenInformation]; TokenInformation
0x18006fca8  lea     edx, [r9+8]; TokenInformationClass
0x18006fcac  mov     rcx, [rsp+490h+TokenHandle]; TokenHandle
0x18006fcb1  call    cs:__imp_GetTokenInformation
0x18006fcb7  test    eax, eax
0x18006fcb9  jnz     short loc_18006FCC5
0x18006fcbb  call    cs:__imp_GetLastError
0x18006fcc1  test    eax, eax
0x18006fcc3  jnz     short loc_18006FD29
0x18006fcc5  mov     eax, [rsp+490h+TokenInformation]
0x18006fcc9  test    eax, eax
0x18006fccb  jnz     short loc_18006FCDC
0x18006fccd  test    dil, dil
0x18006fcd0  jz      short loc_18006FCDC
0x18006fcd2  call    cs:__imp_WTSGetActiveConsoleSessionId
0x18006fcd8  mov     [rsp+490h+TokenInformation], eax
0x18006fcdc  mov     edx, eax; __int64
0x18006fcde  mov     rcx, rbx; struct lua_State *
0x18006fce1  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006fce6  nop
0x18006fce7  mov     rcx, [rsp+490h+TokenHandle]; hObject
0x18006fcec  test    rcx, rcx
0x18006fcef  jz      short loc_18006FD00
0x18006fcf1  mov     [rsp+490h+TokenHandle], 0
0x18006fcfa  call    cs:__imp_CloseHandle
0x18006fd00  mov     eax, 1
0x18006fd05  mov     rcx, [rbp+390h+var_10]
0x18006fd0c  xor     rcx, rsp; StackCookie
0x18006fd0f  call    __security_check_cookie
0x18006fd14  lea     r11, [rsp+490h+var_s0]
0x18006fd1c  mov     rbx, [r11+18h]
0x18006fd20  mov     rdi, [r11+20h]
0x18006fd24  mov     rsp, r11
0x18006fd27  pop     rbp
0x18006fd28  retn
0x18006fd29  mov     edx, eax; __int64
0x18006fd2b  mov     [rsp+490h+var_468], 156h
0x18006fd33  lea     rax, aLuaGblSessioni; "lua_gbl_sessionid"
0x18006fd3a  mov     [rsp+490h+ReturnLength], rax
0x18006fd3f  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18006fd46  xor     r8d, r8d; void *
0x18006fd49  lea     rcx, [rsp+490h+pExceptionObject]; this
0x18006fd4e  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18006fd53  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18006fd5a  lea     rcx, [rsp+490h+pExceptionObject]; pExceptionObject
0x18006fd5f  call    _CxxThrowException_0
0x18006fd65  mov     edx, eax; __int64
0x18006fd67  mov     [rsp+490h+var_468], 14Fh
0x18006fd6f  lea     rax, aLuaGblSessioni; "lua_gbl_sessionid"
0x18006fd76  mov     [rsp+490h+ReturnLength], rax
0x18006fd7b  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18006fd82  xor     r8d, r8d; void *
0x18006fd85  lea     rcx, [rsp+490h+pExceptionObject]; this
0x18006fd8a  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18006fd8f  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18006fd96  lea     rcx, [rsp+490h+pExceptionObject]; pExceptionObject
0x18006fd9b  call    _CxxThrowException_0
```
