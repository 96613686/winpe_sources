# _anonymous_namespace_::wnf_create_name

- ea: `0x18008e620`
- end: `0x18008e806`
- name: `_anonymous_namespace_::wnf_create_name`
- size: `486`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006690`
- `0x180006c50`
- `0x180007950`
- `0x1800083a0`
- `0x180008430`
- `0x18003af08`
- `0x18008e620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e6ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008e75c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008e75c`
- `ntdll!NtCreateWnfStateName` at `0x18008e730`
- `ntdll!NtCreateWnfStateName` at `0x18008e730`
- `ntdll!RtlNtStatusToDosError` at `0x18008e73c`
- `ntdll!RtlNtStatusToDosError` at `0x18008e73c`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x18008e6e3`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorA` at `0x18008e6e3`

## string_xrefs

- `0x18008e798`: `wnf_create_name`
- `0x18008e7d4`: `wnf_create_name`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::wnf_create_name(struct lua_State *a1)
{
  const CHAR *v2; // rbx
  unsigned int v3; // esi
  DWORD LastError; // eax
  PSECURITY_DESCRIPTOR v5; // rbx
  NTSTATUS v6; // eax
  ULONG v7; // eax
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = luaL_checklstring(a1, 1, 0);
  if ( (int)lua_gettop(a1) > 1 && (unsigned int)lua_type(a1, 2) )
    luaL_checkinteger(a1, 2);
  v3 = 0;
  if ( (int)lua_gettop(a1) > 2 && (unsigned int)lua_type(a1, 3) )
    v3 = luaL_checkinteger(a1, 3);
  SecurityDescriptorSize = 0;
  SecurityDescriptor[0] = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorA(v2, 1u, SecurityDescriptor, &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "wnf_create_name",
        58);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v5 = SecurityDescriptor[0];
  SecurityDescriptor[1] = SecurityDescriptor[0];
  v11 = 0;
  v6 = NtCreateWnfStateName(&v11, 3, v3);
  if ( v6 < 0 )
  {
    v7 = RtlNtStatusToDosError(v6);
    if ( v7 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v7,
        0,
        "[%s:%d] failed; ",
        "wnf_create_name",
        62);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  lua_pushinteger(a1, v11);
  if ( v5 )
    LocalFree(v5);
  return 1;
}

```

## disassembly

```asm
0x18008e620  mov     [rsp-8+arg_8], rbx
0x18008e625  mov     [rsp-8+arg_10], rsi
0x18008e62a  push    rbp
0x18008e62b  push    rdi
0x18008e62c  push    r14
0x18008e62e  lea     rbp, [rsp-3A0h]
0x18008e636  sub     rsp, 4A0h
0x18008e63d  mov     rax, cs:__security_cookie
0x18008e644  xor     rax, rsp
0x18008e647  mov     [rbp+3B0h+var_20], rax
0x18008e64e  mov     rdi, rcx
0x18008e651  xor     r8d, r8d; unsigned __int64 *
0x18008e654  lea     edx, [r8+1]; int
0x18008e658  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18008e65d  mov     rbx, rax
0x18008e660  mov     r14d, 1000h
0x18008e666  mov     rcx, rdi; struct lua_State *
0x18008e669  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18008e66e  cmp     eax, 1
0x18008e671  jle     short loc_18008E694
0x18008e673  mov     edx, 2; int
0x18008e678  mov     rcx, rdi; struct lua_State *
0x18008e67b  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18008e680  test    eax, eax
0x18008e682  jz      short loc_18008E694
0x18008e684  mov     edx, 2; int
0x18008e689  mov     rcx, rdi; struct lua_State *
0x18008e68c  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18008e691  mov     r14, rax
0x18008e694  xor     esi, esi
0x18008e696  mov     rcx, rdi; struct lua_State *
0x18008e699  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18008e69e  cmp     eax, 2
0x18008e6a1  jle     short loc_18008E6C0
0x18008e6a3  lea     edx, [rsi+3]; int
0x18008e6a6  mov     rcx, rdi; struct lua_State *
0x18008e6a9  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18008e6ae  test    eax, eax
0x18008e6b0  jz      short loc_18008E6C0
0x18008e6b2  lea     edx, [rsi+3]; int
0x18008e6b5  mov     rcx, rdi; struct lua_State *
0x18008e6b8  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18008e6bd  mov     rsi, rax
0x18008e6c0  mov     [rsp+4B0h+SecurityDescriptorSize], 0
0x18008e6c8  mov     [rsp+4B0h+SecurityDescriptor], 0
0x18008e6d1  lea     r9, [rsp+4B0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18008e6d6  lea     r8, [rsp+4B0h+SecurityDescriptor]; SecurityDescriptor
0x18008e6db  mov     edx, 1; StringSDRevision
0x18008e6e0  mov     rcx, rbx; StringSecurityDescriptor
0x18008e6e3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorA
0x18008e6e9  test    eax, eax
0x18008e6eb  jnz     short loc_18008E6FB
0x18008e6ed  call    cs:__imp_GetLastError
0x18008e6f3  test    eax, eax
0x18008e6f5  jnz     loc_18008E7CA
0x18008e6fb  mov     rbx, [rsp+4B0h+SecurityDescriptor]
0x18008e700  mov     [rsp+4B0h+var_460], rbx
0x18008e705  mov     [rsp+4B0h+var_458], 0
0x18008e70e  mov     [rsp+4B0h+var_480], rbx
0x18008e713  mov     [rsp+4B0h+var_488], r14d
0x18008e718  mov     [rsp+4B0h+var_490], 0
0x18008e721  xor     r9d, r9d
0x18008e724  mov     r8d, esi
0x18008e727  lea     edx, [r9+3]
0x18008e72b  lea     rcx, [rsp+4B0h+var_458]
0x18008e730  call    cs:__imp_NtCreateWnfStateName
0x18008e736  test    eax, eax
0x18008e738  jns     short loc_18008E746
0x18008e73a  mov     ecx, eax; Status
0x18008e73c  call    cs:__imp_RtlNtStatusToDosError
0x18008e742  test    eax, eax
0x18008e744  jnz     short loc_18008E78E
0x18008e746  mov     rdx, [rsp+4B0h+var_458]; __int64
0x18008e74b  mov     rcx, rdi; struct lua_State *
0x18008e74e  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18008e753  nop
0x18008e754  test    rbx, rbx
0x18008e757  jz      short loc_18008E762
0x18008e759  mov     rcx, rbx; hMem
0x18008e75c  call    cs:__imp_LocalFree
0x18008e762  mov     eax, 1
0x18008e767  mov     rcx, [rbp+3B0h+var_20]
0x18008e76e  xor     rcx, rsp; StackCookie
0x18008e771  call    __security_check_cookie
0x18008e776  lea     r11, [rsp+4B0h+var_10]
0x18008e77e  mov     rbx, [r11+28h]
0x18008e782  mov     rsi, [r11+30h]
0x18008e786  mov     rsp, r11
0x18008e789  pop     r14
0x18008e78b  pop     rdi
0x18008e78c  pop     rbp
0x18008e78d  retn
0x18008e78e  mov     edx, eax; __int64
0x18008e790  mov     [rsp+4B0h+var_488], 3Eh ; '>'
0x18008e798  lea     rax, aWnfCreateName; "wnf_create_name"
0x18008e79f  mov     [rsp+4B0h+var_490], rax
0x18008e7a4  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008e7ab  xor     r8d, r8d; void *
0x18008e7ae  lea     rcx, [rsp+4B0h+pExceptionObject]; this
0x18008e7b3  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008e7b8  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008e7bf  lea     rcx, [rsp+4B0h+pExceptionObject]; pExceptionObject
0x18008e7c4  call    _CxxThrowException_0
0x18008e7ca  mov     edx, eax; __int64
0x18008e7cc  mov     [rsp+4B0h+var_488], 3Ah ; ':'
0x18008e7d4  lea     rax, aWnfCreateName; "wnf_create_name"
0x18008e7db  mov     [rsp+4B0h+var_490], rax
0x18008e7e0  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008e7e7  xor     r8d, r8d; void *
0x18008e7ea  lea     rcx, [rsp+4B0h+pExceptionObject]; this
0x18008e7ef  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008e7f4  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008e7fb  lea     rcx, [rsp+4B0h+pExceptionObject]; pExceptionObject
0x18008e800  call    _CxxThrowException_0
```
