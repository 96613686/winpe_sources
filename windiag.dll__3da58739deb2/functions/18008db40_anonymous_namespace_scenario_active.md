# _anonymous_namespace_::scenario_active

- ea: `0x18008db40`
- end: `0x18008dd56`
- name: `_anonymous_namespace_::scenario_active`
- size: `534`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006b00`
- `0x180008430`
- `0x180037e84`
- `0x18003af08`
- `0x18008d4cc`
- `0x18008db40`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008dc1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008dc58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008dc1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008dc58`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008dbea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008dbea`
- `RPCRT4!UuidFromStringA` at `0x18008db88`
- `RPCRT4!UuidFromStringA` at `0x18008db88`

## string_xrefs

- `0x18008dbe3`: `utcapi.dll`
- `0x18008dc12`: `UtcCreateSessionHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::scenario_active(struct lua_State *a1)
{
  unsigned __int8 *v2; // rax
  HMODULE Library; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  int LastError; // eax
  FARPROC ProcAddress; // rax
  FARPROC v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v12[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-B8h]
  INT_PTR (__stdcall *v15)(); // [rsp+50h] [rbp-B0h]
  __int64 v16; // [rsp+58h] [rbp-A8h]
  __int64 v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  __int64 v21; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  __int64 v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+98h] [rbp-68h]
  __int64 v25; // [rsp+A0h] [rbp-60h]
  __int64 v26; // [rsp+A8h] [rbp-58h]
  UUID Uuid; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  v2 = (unsigned __int8 *)luaL_checklstring(a1, 1, 0);
  Uuid = 0;
  if ( UuidFromStringA(v2, &Uuid) )
    return 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  Library = LoadLibraryExW(L"utcapi.dll", 0, 0x800u);
  hModule = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "UtcCreateSessionHandle");
    if ( ProcAddress )
    {
      LastError = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v13);
      goto LABEL_9;
    }
    v6 = 91;
  }
  else
  {
    v6 = 88;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v6,
                (unsigned int)"OneCore\\Internal\\Base\\inc\\utcapiwrapperex.h",
                v5);
LABEL_9:
  if ( LastError < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      LastError,
      0,
      "[%s:%d] failed; ",
      "scenario_active",
      28);
    throw (windiag::system_exception *)pExceptionObject;
  }
  v12[0] = 0;
  v9 = v15;
  if ( v15 || (v9 = GetProcAddress(hModule, "UtcIsScenarioActive"), (v15 = v9) != 0) )
    v11 = ((__int64 (__fastcall *)(__int64, UUID *, int *))v9)(v13, &Uuid, v12);
  else
    v11 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x68,
            (unsigned int)"OneCore\\Internal\\Base\\inc\\utcapiwrapperex.h",
            v10);
  if ( v11 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v11,
      0,
      "[%s:%d] failed; ",
      "scenario_active",
      31);
    throw (windiag::system_exception *)pExceptionObject;
  }
  lua_pushboolean(a1, v12[0]);
  Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper((Microsoft::Diagnostics::UtcApiWrapper *)&v13);
  return 1;
}

```

## disassembly

```asm
0x18008db40  mov     [rsp-8+arg_8], rbx
0x18008db45  mov     [rsp-8+arg_10], rdi
0x18008db4a  push    rbp
0x18008db4b  lea     rbp, [rsp-400h]
0x18008db53  sub     rsp, 500h
0x18008db5a  mov     rax, cs:__security_cookie
0x18008db61  xor     rax, rsp
0x18008db64  mov     [rbp+400h+var_10], rax
0x18008db6b  mov     rbx, rcx
0x18008db6e  xor     r8d, r8d; unsigned __int64 *
0x18008db71  lea     edx, [r8+1]; int
0x18008db75  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18008db7a  xorps   xmm0, xmm0
0x18008db7d  movups  xmmword ptr [rbp+400h+Uuid.Data1], xmm0
0x18008db81  lea     rdx, [rbp+400h+Uuid]; Uuid
0x18008db85  mov     rcx, rax; StringUuid
0x18008db88  call    cs:__imp_UuidFromStringA
0x18008db8e  xor     edi, edi
0x18008db90  test    eax, eax
0x18008db92  jz      short loc_18008DB9B
0x18008db94  xor     eax, eax
0x18008db96  jmp     loc_18008DCBC
0x18008db9b  mov     [rsp+500h+var_4C0], rdi
0x18008dba0  mov     [rsp+500h+hModule], rdi
0x18008dba5  mov     [rsp+500h+var_4B0], rdi
0x18008dbaa  mov     [rsp+500h+var_4A8], rdi
0x18008dbaf  mov     [rsp+500h+var_4A0], rdi
0x18008dbb4  mov     [rsp+500h+var_498], rdi
0x18008dbb9  mov     [rsp+500h+var_490], rdi
0x18008dbbe  mov     [rsp+500h+var_488], rdi
0x18008dbc3  mov     [rbp+400h+var_480], rdi
0x18008dbc7  mov     [rbp+400h+var_478], rdi
0x18008dbcb  mov     [rbp+400h+var_470], rdi
0x18008dbcf  mov     [rbp+400h+var_468], rdi
0x18008dbd3  mov     [rbp+400h+var_460], rdi
0x18008dbd7  mov     [rbp+400h+var_458], rdi
0x18008dbdb  xor     edx, edx; hFile
0x18008dbdd  mov     r8d, 800h; dwFlags
0x18008dbe3  lea     rcx, aUtcapiDll; "utcapi.dll"
0x18008dbea  call    cs:__imp_LoadLibraryExW
0x18008dbf0  mov     [rsp+500h+hModule], rax
0x18008dbf5  test    rax, rax
0x18008dbf8  jnz     short loc_18008DC12
0x18008dbfa  lea     edx, [rax+58h]; void *
0x18008dbfd  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\inc\\utcapiwra"...
0x18008dc04  mov     rcx, [rbp+408h]; this
0x18008dc0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008dc10  jmp     short loc_18008DC36
0x18008dc12  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x18008dc19  mov     rcx, rax; hModule
0x18008dc1c  call    cs:__imp_GetProcAddress
0x18008dc22  test    rax, rax
0x18008dc25  jnz     short loc_18008DC2C
0x18008dc27  lea     edx, [rax+5Bh]
0x18008dc2a  jmp     short loc_18008DBFD
0x18008dc2c  lea     rcx, [rsp+500h+var_4C0]
0x18008dc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dc36  test    eax, eax
0x18008dc38  js      loc_18008DD1B
0x18008dc3e  mov     [rsp+500h+var_4D0], edi
0x18008dc42  mov     rax, [rsp+500h+var_4B0]
0x18008dc47  test    rax, rax
0x18008dc4a  jnz     short loc_18008DC80
0x18008dc4c  lea     rdx, aUtcisscenarioa; "UtcIsScenarioActive"
0x18008dc53  mov     rcx, [rsp+500h+hModule]; hModule
0x18008dc58  call    cs:__imp_GetProcAddress
0x18008dc5e  mov     [rsp+500h+var_4B0], rax
0x18008dc63  test    rax, rax
0x18008dc66  jnz     short loc_18008DC80
0x18008dc68  mov     rcx, [rbp+408h]; this
0x18008dc6f  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\inc\\utcapiwra"...
0x18008dc76  lea     edx, [rax+68h]; void *
0x18008dc79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008dc7e  jmp     short loc_18008DC9C
0x18008dc80  movaps  xmm0, xmmword ptr [rbp+400h+Uuid.Data1]
0x18008dc84  movdqa  xmmword ptr [rbp+400h+Uuid.Data1], xmm0
0x18008dc89  lea     r8, [rsp+500h+var_4D0]
0x18008dc8e  lea     rdx, [rbp+400h+Uuid]
0x18008dc92  mov     rcx, [rsp+500h+var_4C0]
0x18008dc97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dc9c  test    eax, eax
0x18008dc9e  js      short loc_18008DCE0
0x18008dca0  mov     edx, [rsp+500h+var_4D0]; int
0x18008dca4  mov     rcx, rbx; struct lua_State *
0x18008dca7  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x18008dcac  nop
0x18008dcad  lea     rcx, [rsp+500h+var_4C0]; this
0x18008dcb2  call    ??1UtcApiWrapper@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper(void)
0x18008dcb7  mov     eax, 1
0x18008dcbc  mov     rcx, [rbp+400h+var_10]
0x18008dcc3  xor     rcx, rsp; StackCookie
0x18008dcc6  call    __security_check_cookie
0x18008dccb  lea     r11, [rsp+500h+var_s0]
0x18008dcd3  mov     rbx, [r11+18h]
0x18008dcd7  mov     rdi, [r11+20h]
0x18008dcdb  mov     rsp, r11
0x18008dcde  pop     rbp
0x18008dcdf  retn
0x18008dce0  movsxd  rdx, eax; __int64
0x18008dce3  mov     [rsp+500h+var_4D8], 1Fh
0x18008dceb  lea     rax, aScenarioActive; "scenario_active"
0x18008dcf2  mov     [rsp+500h+var_4E0], rax
0x18008dcf7  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008dcfe  xor     r8d, r8d; void *
0x18008dd01  lea     rcx, [rbp+400h+pExceptionObject]; this
0x18008dd05  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008dd0a  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008dd11  lea     rcx, [rbp+400h+pExceptionObject]; pExceptionObject
0x18008dd15  call    _CxxThrowException_0
0x18008dd1b  movsxd  rdx, eax; __int64
0x18008dd1e  mov     [rsp+500h+var_4D8], 1Ch
0x18008dd26  lea     rax, aScenarioActive; "scenario_active"
0x18008dd2d  mov     [rsp+500h+var_4E0], rax
0x18008dd32  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008dd39  xor     r8d, r8d; void *
0x18008dd3c  lea     rcx, [rbp+400h+pExceptionObject]; this
0x18008dd40  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008dd45  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008dd4c  lea     rcx, [rbp+400h+pExceptionObject]; pExceptionObject
0x18008dd50  call    _CxxThrowException_0
```
