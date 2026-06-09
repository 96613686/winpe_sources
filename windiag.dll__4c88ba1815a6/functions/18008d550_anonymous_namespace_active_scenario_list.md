# _anonymous_namespace_::active_scenario_list

- ea: `0x18008d550`
- end: `0x18008d833`
- name: `_anonymous_namespace_::active_scenario_list`
- size: `739`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006050`
- `0x180006c50`
- `0x180006d40`
- `0x1800073e0`
- `0x180008430`
- `0x180037e84`
- `0x18003af08`
- `0x18003b0bc`
- `0x180041564`
- `0x1800416a0`
- `0x18004faec`
- `0x18008d4cc`
- `0x18008d550`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008d63a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008d697`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008d63a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008d697`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008d608`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008d608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d76c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d76c`

## string_xrefs

- `0x18008d601`: `utcapi.dll`
- `0x18008d630`: `UtcCreateSessionHandle`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall anonymous_namespace_::active_scenario_list(struct lua_State *a1)
{
  const CHAR *v2; // rax
  const CHAR *v3; // rax
  HMODULE Library; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  int LastError; // eax
  FARPROC ProcAddress; // rax
  char **v9; // rbx
  char **v10; // rdi
  FARPROC v11; // rax
  const char *v12; // r9
  int v13; // eax
  unsigned int i; // ebx
  char v15; // al
  const char *v16; // rdx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  __int64 v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  INT_PTR (__stdcall *v32)(); // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  char *v34[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-30h]
  char *v36[4]; // [rsp+D8h] [rbp-28h] BYREF
  char *v37[5]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+578h] [rbp+478h]

  v2 = luaL_checklstring(a1, 1, 0);
  windiag::char_to_wstring((__int64)v37, v2);
  v3 = luaL_checklstring(a1, 2, 0);
  windiag::char_to_wstring((__int64)v36, v3);
  v20 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  Library = LoadLibraryExW(L"utcapi.dll", 0, 0x800u);
  hModule = Library;
  if ( !Library )
  {
    v6 = 88;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"OneCore\\Internal\\Base\\inc\\utcapiwrapperex.h",
                  v5);
    goto LABEL_7;
  }
  ProcAddress = GetProcAddress(Library, "UtcCreateSessionHandle");
  if ( !ProcAddress )
  {
    v6 = 91;
    goto LABEL_3;
  }
  LastError = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v20);
LABEL_7:
  if ( LastError < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      LastError,
      0,
      "[%s:%d] failed; ",
      "active_scenario_list",
      97);
    throw (windiag::system_exception *)pExceptionObject;
  }
  pv = 0;
  v19 = 0;
  v9 = v36;
  if ( v36[3] > (char *)7 )
    v9 = (char **)v36[0];
  v10 = v37;
  if ( v37[3] > (char *)7 )
    v10 = (char **)v37[0];
  v11 = v32;
  if ( v32 || (v11 = GetProcAddress(hModule, "UtcGetActiveScenarioList2"), (v32 = v11) != 0) )
    v13 = ((__int64 (__fastcall *)(__int64, char **, char **, LPVOID *, unsigned int *))v11)(v20, v10, v9, &pv, &v19);
  else
    v13 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x10C,
            (unsigned int)"OneCore\\Internal\\Base\\inc\\utcapiwrapperex.h",
            v12);
  if ( v13 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v13,
      0,
      "[%s:%d] failed; ",
      "active_scenario_list",
      100);
    throw (windiag::system_exception *)pExceptionObject;
  }
  lua_createtable(a1, 0, 0);
  for ( i = 0; i < v19; ++i )
  {
    windiag::guid_to_string(v34, (char *)pv + 16 * i);
    v15 = v35;
    if ( (_BYTE)v35 )
    {
      lua_pushinteger(a1, i + 1);
      v16 = (const char *)v34;
      if ( v34[3] > (char *)0xF )
        v16 = v34[0];
      lua_pushstring(a1, v16);
      lua_settable(a1, 4294967293LL);
      v15 = v35;
    }
    if ( v15 )
      std::string::~string(v34);
  }
  if ( pv )
    CoTaskMemFree(pv);
  Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper((Microsoft::Diagnostics::UtcApiWrapper *)&v20);
  std::wstring::~wstring(v36);
  std::wstring::~wstring(v37);
  return 1;
}

```

## disassembly

```asm
0x18008d550  mov     [rsp-8+arg_8], rbx
0x18008d555  mov     [rsp-8+arg_10], rsi
0x18008d55a  push    rbp
0x18008d55b  push    rdi
0x18008d55c  push    r14
0x18008d55e  lea     rbp, [rsp-460h]
0x18008d566  sub     rsp, 560h
0x18008d56d  mov     rax, cs:__security_cookie
0x18008d574  xor     rax, rsp
0x18008d577  mov     [rbp+470h+var_20], rax
0x18008d57e  mov     rsi, rcx
0x18008d581  xor     r8d, r8d; unsigned __int64 *
0x18008d584  lea     edx, [r8+1]; int
0x18008d588  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18008d58d  mov     rdx, rax
0x18008d590  lea     rcx, [rbp+470h+var_478]
0x18008d594  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18008d599  nop
0x18008d59a  xor     r8d, r8d; unsigned __int64 *
0x18008d59d  lea     edx, [r8+2]; int
0x18008d5a1  mov     rcx, rsi; struct lua_State *
0x18008d5a4  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18008d5a9  mov     rdx, rax
0x18008d5ac  lea     rcx, [rbp+470h+var_498]
0x18008d5b0  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18008d5b5  nop
0x18008d5b6  xor     r14d, r14d
0x18008d5b9  mov     [rsp+570h+var_530], r14
0x18008d5be  mov     [rsp+570h+hModule], r14
0x18008d5c3  mov     [rsp+570h+var_520], r14
0x18008d5c8  mov     [rsp+570h+var_518], r14
0x18008d5cd  mov     [rsp+570h+var_510], r14
0x18008d5d2  mov     [rsp+570h+var_508], r14
0x18008d5d7  mov     [rsp+570h+var_500], r14
0x18008d5dc  mov     [rsp+570h+var_4F8], r14
0x18008d5e1  mov     [rbp+470h+var_4F0], r14
0x18008d5e5  mov     [rbp+470h+var_4E8], r14
0x18008d5e9  mov     [rbp+470h+var_4E0], r14
0x18008d5ed  mov     [rbp+470h+var_4D8], r14
0x18008d5f1  mov     [rbp+470h+var_4D0], r14
0x18008d5f5  mov     [rbp+470h+var_4C8], r14
0x18008d5f9  xor     edx, edx; hFile
0x18008d5fb  mov     r8d, 800h; dwFlags
0x18008d601  lea     rcx, aUtcapiDll; "utcapi.dll"
0x18008d608  call    cs:__imp_LoadLibraryExW
0x18008d60e  mov     [rsp+570h+hModule], rax
0x18008d613  test    rax, rax
0x18008d616  jnz     short loc_18008D630
0x18008d618  lea     edx, [rax+58h]; void *
0x18008d61b  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\inc\\utcapiwra"...
0x18008d622  mov     rcx, [rbp+478h]; this
0x18008d629  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008d62e  jmp     short loc_18008D654
0x18008d630  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x18008d637  mov     rcx, rax; hModule
0x18008d63a  call    cs:__imp_GetProcAddress
0x18008d640  test    rax, rax
0x18008d643  jnz     short loc_18008D64A
0x18008d645  lea     edx, [rax+5Bh]
0x18008d648  jmp     short loc_18008D61B
0x18008d64a  lea     rcx, [rsp+570h+var_530]
0x18008d64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d654  test    eax, eax
0x18008d656  js      loc_18008D7F8
0x18008d65c  mov     [rsp+570h+pv], r14
0x18008d661  mov     [rsp+570h+var_538], r14d
0x18008d666  lea     rbx, [rbp+470h+var_498]
0x18008d66a  cmp     [rbp+470h+var_480], 7
0x18008d66f  cmova   rbx, [rbp+470h+var_498]
0x18008d674  lea     rdi, [rbp+470h+var_478]
0x18008d678  cmp     [rbp+470h+var_460], 7
0x18008d67d  cmova   rdi, [rbp+470h+var_478]
0x18008d682  mov     rax, [rbp+470h+var_4D0]
0x18008d686  test    rax, rax
0x18008d689  jnz     short loc_18008D6C0
0x18008d68b  lea     rdx, aUtcgetactivesc; "UtcGetActiveScenarioList2"
0x18008d692  mov     rcx, [rsp+570h+hModule]; hModule
0x18008d697  call    cs:__imp_GetProcAddress
0x18008d69d  mov     [rbp+470h+var_4D0], rax
0x18008d6a1  test    rax, rax
0x18008d6a4  jnz     short loc_18008D6C0
0x18008d6a6  mov     rcx, [rbp+478h]; this
0x18008d6ad  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\inc\\utcapiwra"...
0x18008d6b4  mov     edx, 10Ch; void *
0x18008d6b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008d6be  jmp     short loc_18008D6DF
0x18008d6c0  lea     rcx, [rsp+570h+var_538]
0x18008d6c5  mov     [rsp+570h+var_550], rcx
0x18008d6ca  lea     r9, [rsp+570h+pv]
0x18008d6cf  mov     r8, rbx
0x18008d6d2  mov     rdx, rdi
0x18008d6d5  mov     rcx, [rsp+570h+var_530]
0x18008d6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d6df  test    eax, eax
0x18008d6e1  js      loc_18008D7BD
0x18008d6e7  xor     r8d, r8d; int
0x18008d6ea  xor     edx, edx; int
0x18008d6ec  mov     rcx, rsi; struct lua_State *
0x18008d6ef  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18008d6f4  mov     ebx, r14d
0x18008d6f7  cmp     [rsp+570h+var_538], r14d
0x18008d6fc  jbe     short loc_18008D762
0x18008d6fe  mov     edx, ebx
0x18008d700  shl     rdx, 4
0x18008d704  add     rdx, [rsp+570h+pv]
0x18008d709  lea     rcx, [rbp+470h+var_4C0]
0x18008d70d  call    ?guid_to_string@windiag@@YA?AV?$optional@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@AEBU_GUID@@@Z; windiag::guid_to_string(_GUID const &)
0x18008d712  nop
0x18008d713  mov     rax, [rbp+470h+var_4A0]
0x18008d717  test    al, al
0x18008d719  jz      short loc_18008D74D
0x18008d71b  lea     edx, [rbx+1]; __int64
0x18008d71e  mov     rcx, rsi; struct lua_State *
0x18008d721  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18008d726  lea     rdx, [rbp+470h+var_4C0]
0x18008d72a  cmp     [rbp+470h+var_4A8], 0Fh
0x18008d72f  cmova   rdx, [rbp+470h+var_4C0]; char *
0x18008d734  mov     rcx, rsi; struct lua_State *
0x18008d737  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18008d73c  mov     edx, 0FFFFFFFDh; int
0x18008d741  mov     rcx, rsi; struct lua_State *
0x18008d744  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x18008d749  mov     rax, [rbp+470h+var_4A0]
0x18008d74d  test    al, al
0x18008d74f  jz      short loc_18008D75A
0x18008d751  lea     rcx, [rbp+470h+var_4C0]
0x18008d755  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18008d75a  inc     ebx
0x18008d75c  cmp     ebx, [rsp+570h+var_538]
0x18008d760  jb      short loc_18008D6FE
0x18008d762  mov     rcx, [rsp+570h+pv]; pv
0x18008d767  test    rcx, rcx
0x18008d76a  jz      short loc_18008D773
0x18008d76c  call    cs:__imp_CoTaskMemFree
0x18008d772  nop
0x18008d773  lea     rcx, [rsp+570h+var_530]; this
0x18008d778  call    ??1UtcApiWrapper@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper(void)
0x18008d77d  nop
0x18008d77e  lea     rcx, [rbp+470h+var_498]
0x18008d782  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008d787  nop
0x18008d788  lea     rcx, [rbp+470h+var_478]
0x18008d78c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008d791  mov     eax, 1
0x18008d796  mov     rcx, [rbp+470h+var_20]
0x18008d79d  xor     rcx, rsp; StackCookie
0x18008d7a0  call    __security_check_cookie
0x18008d7a5  lea     r11, [rsp+570h+var_10]
0x18008d7ad  mov     rbx, [r11+28h]
0x18008d7b1  mov     rsi, [r11+30h]
0x18008d7b5  mov     rsp, r11
0x18008d7b8  pop     r14
0x18008d7ba  pop     rdi
0x18008d7bb  pop     rbp
0x18008d7bc  retn
0x18008d7bd  movsxd  rdx, eax; __int64
0x18008d7c0  mov     [rsp+570h+var_548], 64h ; 'd'
0x18008d7c8  lea     rax, aActiveScenario; "active_scenario_list"
0x18008d7cf  mov     [rsp+570h+var_550], rax
0x18008d7d4  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008d7db  xor     r8d, r8d; void *
0x18008d7de  lea     rcx, [rbp+470h+pExceptionObject]; this
0x18008d7e2  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008d7e7  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008d7ee  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x18008d7f2  call    _CxxThrowException_0
0x18008d7f8  movsxd  rdx, eax; __int64
0x18008d7fb  mov     [rsp+570h+var_548], 61h ; 'a'
0x18008d803  lea     rax, aActiveScenario; "active_scenario_list"
0x18008d80a  mov     [rsp+570h+var_550], rax
0x18008d80f  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008d816  xor     r8d, r8d; void *
0x18008d819  lea     rcx, [rbp+470h+pExceptionObject]; this
0x18008d81d  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008d822  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008d829  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x18008d82d  call    _CxxThrowException_0
```
