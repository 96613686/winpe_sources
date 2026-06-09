# _anonymous_namespace_::lua_gbl_create_guid

- ea: `0x18006e2a0`
- end: `0x18006e388`
- name: `_anonymous_namespace_::lua_gbl_create_guid`
- size: `232`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006d40`
- `0x18003af08`
- `0x18003b0bc`
- `0x18004faec`
- `0x18006e2a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006e2d6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006e2d6`

## string_xrefs

- `0x18006e356`: `lua_gbl_create_guid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::lua_gbl_create_guid(struct lua_State *a1)
{
  HRESULT v2; // eax
  const char *v3; // rdx
  char *v5[4]; // [rsp+30h] [rbp-D0h] BYREF
  char v6; // [rsp+50h] [rbp-B0h]
  GUID pguid; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+70h] [rbp-90h] BYREF

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v2,
      0,
      "[%s:%d] failed; ",
      "lua_gbl_create_guid",
      253);
    throw (windiag::system_exception *)pExceptionObject;
  }
  windiag::guid_to_string(v5, &pguid);
  if ( !v6 )
    return 0;
  v3 = (const char *)v5;
  if ( v5[3] > (char *)0xF )
    v3 = v5[0];
  lua_pushstring(a1, v3);
  if ( v6 )
    std::string::~string(v5);
  return 1;
}

```

## disassembly

```asm
0x18006e2a0  mov     [rsp-8+arg_8], rbx
0x18006e2a5  push    rbp
0x18006e2a6  lea     rbp, [rsp-3B0h]
0x18006e2ae  sub     rsp, 4B0h
0x18006e2b5  mov     rax, cs:__security_cookie
0x18006e2bc  xor     rax, rsp
0x18006e2bf  mov     [rbp+3B0h+var_10], rax
0x18006e2c6  mov     rbx, rcx
0x18006e2c9  xorps   xmm0, xmm0
0x18006e2cc  movups  xmmword ptr [rsp+4B0h+pguid.Data1], xmm0
0x18006e2d1  lea     rcx, [rsp+4B0h+pguid]; pguid
0x18006e2d6  call    cs:__imp_CoCreateGuid
0x18006e2dc  test    eax, eax
0x18006e2de  js      short loc_18006E34B
0x18006e2e0  lea     rdx, [rsp+4B0h+pguid]
0x18006e2e5  lea     rcx, [rsp+4B0h+var_480]
0x18006e2ea  call    ?guid_to_string@windiag@@YA?AV?$optional@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@AEBU_GUID@@@Z; windiag::guid_to_string(_GUID const &)
0x18006e2ef  nop
0x18006e2f0  cmp     [rsp+4B0h+var_460], 0
0x18006e2f5  jz      short loc_18006E329
0x18006e2f7  lea     rdx, [rsp+4B0h+var_480]
0x18006e2fc  cmp     [rsp+4B0h+var_468], 0Fh
0x18006e302  cmova   rdx, [rsp+4B0h+var_480]; char *
0x18006e308  mov     rcx, rbx; struct lua_State *
0x18006e30b  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18006e310  nop
0x18006e311  cmp     [rsp+4B0h+var_460], 0
0x18006e316  jz      short loc_18006E322
0x18006e318  lea     rcx, [rsp+4B0h+var_480]
0x18006e31d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18006e322  mov     eax, 1
0x18006e327  jmp     short loc_18006E32B
0x18006e329  xor     eax, eax
0x18006e32b  mov     rcx, [rbp+3B0h+var_10]
0x18006e332  xor     rcx, rsp; StackCookie
0x18006e335  call    __security_check_cookie
0x18006e33a  mov     rbx, [rsp+4B0h+arg_8]
0x18006e342  add     rsp, 4B0h
0x18006e349  pop     rbp
0x18006e34a  retn
0x18006e34b  movsxd  rdx, eax; __int64
0x18006e34e  mov     [rsp+4B0h+var_488], 0FDh
0x18006e356  lea     rax, aLuaGblCreateGu; "lua_gbl_create_guid"
0x18006e35d  mov     [rsp+4B0h+var_490], rax
0x18006e362  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18006e369  xor     r8d, r8d; void *
0x18006e36c  lea     rcx, [rsp+4B0h+pExceptionObject]; this
0x18006e371  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18006e376  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18006e37d  lea     rcx, [rsp+4B0h+pExceptionObject]; pExceptionObject
0x18006e382  call    _CxxThrowException_0
```
