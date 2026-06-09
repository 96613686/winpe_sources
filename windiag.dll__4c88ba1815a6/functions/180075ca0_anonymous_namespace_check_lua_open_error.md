# _anonymous_namespace_::check_lua_open_error

- ea: `0x180075ca0`
- end: `0x180075e0b`
- name: `_anonymous_namespace_::check_lua_open_error`
- size: `363`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800783c0`
- `0x180078c2c`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006690`
- `0x1800067f0`
- `0x180007740`
- `0x18003af08`
- `0x18003b0bc`
- `0x18003db80`
- `0x180075a1c`
- `0x180075ca0`
- `0x18007835c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075da8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180075da8`

## string_xrefs

- `0x180075d26`: `check_lua_open_error`
- `0x180075dd5`: `check_lua_open_error`
- `0x180075de1`: `[%s:%d] failed; %s [open library] (%s)`
- `0x180075d32`: `[%s:%d] failed; [open library] (%s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall anonymous_namespace_::check_lua_open_error(struct lua_State *a1, __int64 a2)
{
  char v4; // al
  unsigned int v5; // esi
  const char *v6; // rax
  __int64 v7; // rdx
  const char *v8; // rbp
  const char *v9; // rax
  int v10; // esi
  struct lua_State *v11; // rdx
  void *v12; // rax
  const char *v13; // rax
  _BYTE pExceptionObject[1072]; // [rsp+50h] [rbp-458h] BYREF

  v4 = *(_BYTE *)(a2 + 48);
  if ( v4 )
  {
    v5 = *(_DWORD *)(a2 + 40);
    if ( v5 )
    {
      v8 = DirectoryName;
      if ( (int)lua_gettop(a1) >= 1 )
      {
        if ( (unsigned int)lua_isstring(a1, -1) )
        {
          v9 = lua_tolstring(a1, 0xFFFFFFFFLL, 0);
          if ( v9 )
            v8 = v9;
        }
      }
      v10 = anonymous_namespace_::HRESULT_FROM_LUA(v5);
      v12 = windiag::lua_stop_event(a1, v11);
      if ( v12 && !WaitForSingleObject(v12, 0) )
        v10 = -2147201017;
      v13 = (const char *)std::string::c_str(a2);
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v10,
        &_ImageBase,
        "[%s:%d] failed; %s [open library] (%s)",
        "check_lua_open_error",
        274,
        v8,
        v13);
      throw (windiag::system_exception *)pExceptionObject;
    }
    if ( *(_DWORD *)(a2 + 32) )
    {
      v6 = (const char *)std::string::c_str(a2);
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        *(unsigned int *)(v7 + 32),
        0,
        "[%s:%d] failed; [open library] (%s)",
        "check_lua_open_error",
        275,
        v6);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  if ( v4 )
    std::string::~string((char **)a2);
}

```

## disassembly

```asm
0x180075ca0  mov     [rsp+arg_10], rbx
0x180075ca5  push    rbp
0x180075ca6  push    rsi
0x180075ca7  push    rdi
0x180075ca8  sub     rsp, 490h
0x180075caf  mov     rax, cs:__security_cookie
0x180075cb6  xor     rax, rsp
0x180075cb9  mov     [rsp+4A8h+var_28], rax
0x180075cc1  mov     rbx, rdx
0x180075cc4  mov     rdi, rcx
0x180075cc7  mov     [rsp+4A8h+var_468], rdx
0x180075ccc  mov     al, [rdx+30h]
0x180075ccf  test    al, al
0x180075cd1  jz      short loc_180075CDF
0x180075cd3  mov     esi, [rdx+28h]
0x180075cd6  test    esi, esi
0x180075cd8  jnz     short loc_180075D58
0x180075cda  cmp     [rdx+20h], esi
0x180075cdd  jnz     short loc_180075D0E
0x180075cdf  test    al, al
0x180075ce1  jz      short loc_180075CEB
0x180075ce3  mov     rcx, rbx
0x180075ce6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180075ceb  mov     rcx, [rsp+4A8h+var_28]
0x180075cf3  xor     rcx, rsp; StackCookie
0x180075cf6  call    __security_check_cookie
0x180075cfb  mov     rbx, [rsp+4A8h+arg_10]
0x180075d03  add     rsp, 490h
0x180075d0a  pop     rdi
0x180075d0b  pop     rsi
0x180075d0c  pop     rbp
0x180075d0d  retn
0x180075d0e  mov     rcx, rbx
0x180075d11  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x180075d16  mov     edx, [rdx+20h]; __int64
0x180075d19  mov     [rsp+4A8h+var_478], rax
0x180075d1e  mov     [rsp+4A8h+var_480], 113h
0x180075d26  lea     rax, aCheckLuaOpenEr; "check_lua_open_error"
0x180075d2d  mov     [rsp+4A8h+var_488], rax
0x180075d32  lea     r9, aSDFailedOpenLi; "[%s:%d] failed; [open library] (%s)"
0x180075d39  xor     r8d, r8d; void *
0x180075d3c  lea     rcx, [rsp+4A8h+pExceptionObject]; this
0x180075d41  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180075d46  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180075d4d  lea     rcx, [rsp+4A8h+pExceptionObject]; pExceptionObject
0x180075d52  call    _CxxThrowException_0
0x180075d58  lea     rbp, DirectoryName
0x180075d5f  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x180075d64  cmp     eax, 1
0x180075d67  jl      short loc_180075D8D
0x180075d69  or      edx, 0FFFFFFFFh; int
0x180075d6c  mov     rcx, rdi; struct lua_State *
0x180075d6f  call    ?lua_isstring@@YAHPEAUlua_State@@H@Z; lua_isstring(lua_State *,int)
0x180075d74  test    eax, eax
0x180075d76  jz      short loc_180075D8D
0x180075d78  xor     r8d, r8d; unsigned __int64 *
0x180075d7b  or      edx, 0FFFFFFFFh; int
0x180075d7e  mov     rcx, rdi; struct lua_State *
0x180075d81  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x180075d86  test    rax, rax
0x180075d89  cmovnz  rbp, rax
0x180075d8d  mov     ecx, esi
0x180075d8f  call    _anonymous_namespace___HRESULT_FROM_LUA
0x180075d94  mov     esi, eax
0x180075d96  mov     rcx, rdi; this
0x180075d99  call    ?lua_stop_event@windiag@@YAPEAXPEAUlua_State@@@Z; windiag::lua_stop_event(lua_State *)
0x180075d9e  test    rax, rax
0x180075da1  jz      short loc_180075DB8
0x180075da3  xor     edx, edx; dwMilliseconds
0x180075da5  mov     rcx, rax; hHandle
0x180075da8  call    cs:__imp_WaitForSingleObject
0x180075dae  mov     ecx, 80045007h
0x180075db3  test    eax, eax
0x180075db5  cmovz   esi, ecx
0x180075db8  mov     rcx, rbx
0x180075dbb  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x180075dc0  movsxd  rdx, esi; __int64
0x180075dc3  mov     [rsp+4A8h+var_470], rax
0x180075dc8  mov     [rsp+4A8h+var_478], rbp
0x180075dcd  mov     [rsp+4A8h+var_480], 112h
0x180075dd5  lea     rax, aCheckLuaOpenEr; "check_lua_open_error"
0x180075ddc  mov     [rsp+4A8h+var_488], rax
0x180075de1  lea     r9, aSDFailedSOpenL; "[%s:%d] failed; %s [open library] (%s)"
0x180075de8  lea     r8, __ImageBase; void *
0x180075def  lea     rcx, [rsp+4A8h+pExceptionObject]; this
0x180075df4  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180075df9  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180075e00  lea     rcx, [rsp+4A8h+pExceptionObject]; pExceptionObject
0x180075e05  call    _CxxThrowException_0
```
