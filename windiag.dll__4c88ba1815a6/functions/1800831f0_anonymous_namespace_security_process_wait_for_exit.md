# _anonymous_namespace_::security_process_wait_for_exit

- ea: `0x1800831f0`
- end: `0x18008332e`
- name: `_anonymous_namespace_::security_process_wait_for_exit`
- size: `318`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006690`
- `0x180006b00`
- `0x1800083a0`
- `0x180008660`
- `0x180008790`
- `0x18003af08`
- `0x1800762a8`
- `0x18007835c`
- `0x1800831f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083284`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180083279`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180083279`

## string_xrefs

- `0x18008323f`: `security.process`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::security_process_wait_for_exit(struct lua_State *a1, struct lua_State *a2)
{
  void *v3; // rsi
  DWORD v4; // edi
  HANDLE *v5; // rax
  DWORD v6; // eax
  DWORD LastError; // eax
  int v8; // edx
  HANDLE Handles[2]; // [rsp+30h] [rbp-458h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+40h] [rbp-448h] BYREF

  v3 = windiag::lua_stop_event(a1, a2);
  v4 = -1;
  if ( (int)lua_gettop(a1) > 1 )
    v4 = luaL_checkinteger(a1, 2);
  v5 = (HANDLE *)luaL_checkudata(a1, 1, "security.process");
  if ( !*v5 )
    goto LABEL_6;
  Handles[0] = *v5;
  Handles[1] = v3;
  v6 = WaitForMultipleObjects((v3 != 0) + 1, Handles, 0, v4);
  if ( v6 == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "wait_for_exit",
        141);
      throw (windiag::system_exception *)pExceptionObject;
    }
    goto LABEL_6;
  }
  if ( v6 > 1 )
  {
LABEL_6:
    v8 = 0;
    goto LABEL_7;
  }
  v8 = 1;
LABEL_7:
  lua_pushboolean(a1, v8);
  if ( (unsigned __int8)anonymous_namespace_::lua_check_control_events(a1, 0) )
    luaL_error(a1, "lua stop signal received");
  return 1;
}

```

## disassembly

```asm
0x1800831f0  mov     [rsp+arg_8], rbx
0x1800831f5  mov     [rsp+arg_10], rsi
0x1800831fa  push    rdi
0x1800831fb  sub     rsp, 480h
0x180083202  mov     rax, cs:__security_cookie
0x180083209  xor     rax, rsp
0x18008320c  mov     [rsp+488h+var_18], rax
0x180083214  mov     rbx, rcx
0x180083217  call    ?lua_stop_event@windiag@@YAPEAXPEAUlua_State@@@Z; windiag::lua_stop_event(lua_State *)
0x18008321c  mov     rcx, rbx; struct lua_State *
0x18008321f  mov     rsi, rax
0x180083222  or      edi, 0FFFFFFFFh
0x180083225  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18008322a  cmp     eax, 1
0x18008322d  jle     short loc_18008323F
0x18008322f  mov     edx, 2; int
0x180083234  mov     rcx, rbx; struct lua_State *
0x180083237  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18008323c  mov     rdi, rax
0x18008323f  lea     r8, aSecurityProces_1; "security.process"
0x180083246  mov     edx, 1; int
0x18008324b  mov     rcx, rbx; struct lua_State *
0x18008324e  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x180083253  mov     rcx, [rax]
0x180083256  test    rcx, rcx
0x180083259  jz      short loc_18008328E
0x18008325b  mov     [rsp+488h+Handles], rcx
0x180083260  lea     rdx, [rsp+488h+Handles]; lpHandles
0x180083265  mov     [rsp+488h+var_450], rsi
0x18008326a  mov     r9d, edi; dwMilliseconds
0x18008326d  neg     rsi
0x180083270  sbb     ecx, ecx
0x180083272  xor     r8d, r8d; bWaitAll
0x180083275  neg     ecx
0x180083277  inc     ecx; nCount
0x180083279  call    cs:__imp_WaitForMultipleObjects
0x18008327f  cmp     eax, 0FFFFFFFFh
0x180083282  jnz     short loc_1800832E2
0x180083284  call    cs:__imp_GetLastError
0x18008328a  test    eax, eax
0x18008328c  jnz     short loc_1800832F2
0x18008328e  xor     edx, edx; int
0x180083290  mov     rcx, rbx; struct lua_State *
0x180083293  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x180083298  xor     r8d, r8d
0x18008329b  xor     edx, edx; dwMilliseconds
0x18008329d  mov     rcx, rbx; struct lua_State *
0x1800832a0  call    _anonymous_namespace___lua_check_control_events
0x1800832a5  test    al, al
0x1800832a7  jz      short loc_1800832B8
0x1800832a9  lea     rdx, aLuaStopSignalR; "lua stop signal received"
0x1800832b0  mov     rcx, rbx; struct lua_State *
0x1800832b3  call    ?luaL_error@@YAHPEAUlua_State@@PEBDZZ; luaL_error(lua_State *,char const *,...)
0x1800832b8  mov     eax, 1
0x1800832bd  mov     rcx, [rsp+488h+var_18]
0x1800832c5  xor     rcx, rsp; StackCookie
0x1800832c8  call    __security_check_cookie
0x1800832cd  lea     r11, [rsp+488h+var_8]
0x1800832d5  mov     rbx, [r11+18h]
0x1800832d9  mov     rsi, [r11+20h]
0x1800832dd  mov     rsp, r11
0x1800832e0  pop     rdi
0x1800832e1  retn
0x1800832e2  test    eax, eax
0x1800832e4  jz      short loc_1800832EB
0x1800832e6  cmp     eax, 1
0x1800832e9  jnz     short loc_18008328E
0x1800832eb  mov     edx, 1
0x1800832f0  jmp     short loc_180083290
0x1800832f2  mov     edx, eax; __int64
0x1800832f4  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800832fb  lea     rax, aWaitForExit; "wait_for_exit"
0x180083302  mov     [rsp+488h+var_460], 8Dh
0x18008330a  xor     r8d, r8d; void *
0x18008330d  mov     [rsp+488h+var_468], rax
0x180083312  lea     rcx, [rsp+488h+pExceptionObject]; this
0x180083317  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008331c  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180083323  lea     rcx, [rsp+488h+pExceptionObject]; pExceptionObject
0x180083328  call    _CxxThrowException_0
```
