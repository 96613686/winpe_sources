# _anonymous_namespace_::wmi_query_execute

- ea: `0x18008cec8`
- end: `0x18008d24d`
- name: `_anonymous_namespace_::wmi_query_execute`
- size: `901`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18008cdc0`

## callees

- `0x180004510`
- `0x18000491c`
- `0x180005520`
- `0x180006050`
- `0x180006c50`
- `0x180006d40`
- `0x180007160`
- `0x1800073e0`
- `0x180008790`
- `0x18003af08`
- `0x18003b0bc`
- `0x180041e58`
- `0x180058600`
- `0x1800762a8`
- `0x18008af74`
- `0x18008b638`
- `0x18008bbd0`
- `0x18008cec8`
- `0x18009d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008cf21`
- `OLEAUT32!__imp_SysAllocString` at `0x18008cf42`
- `OLEAUT32!__imp_SysAllocString` at `0x18008cf21`
- `OLEAUT32!__imp_SysAllocString` at `0x18008cf42`
- `OLEAUT32!__imp_SysFreeString` at `0x18008cf8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18008cf97`
- `OLEAUT32!__imp_SysFreeString` at `0x18008cf8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18008cf97`
- `OLEAUT32!__imp_VariantInit` at `0x18008d0b3`
- `OLEAUT32!__imp_VariantInit` at `0x18008d0b3`
- `OLEAUT32!__imp_VariantClear` at `0x18008d150`
- `OLEAUT32!__imp_VariantClear` at `0x18008d150`

## string_xrefs

- `0x18008d0d9`: `__relpath`
- `0x18008d127`: `__path`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall anonymous_namespace_::wmi_query_execute(
        struct lua_State *a1,
        __int64 *a2,
        const OLECHAR *a3,
        __int64 a4)
{
  __int64 v7; // r13
  OLECHAR *v8; // rbx
  BSTR v9; // r15
  BSTR v10; // rax
  BSTR v11; // rax
  OLECHAR *v12; // rdi
  __int64 v13; // r15
  int v14; // edi
  _QWORD *v15; // rax
  int v16; // eax
  int v17; // ebx
  BSTR v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rax
  BSTR v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v24; // [rsp+58h] [rbp-A8h] BYREF
  char v25[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *v26[2]; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  char *v28[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+B0h] [rbp-50h] BYREF

  v23 = 0;
  v7 = *a2;
  if ( a3 )
  {
    v10 = SysAllocString(a3);
    v8 = v10;
    v21 = v10;
    if ( !v10 )
      ATL::AtlThrowImpl(-2147024882);
    v9 = v10;
  }
  else
  {
    v8 = 0;
    v21 = 0;
    v9 = 0;
  }
  v11 = SysAllocString(L"WQL");
  v12 = v11;
  v24 = v11;
  if ( !v11 )
    ATL::AtlThrowImpl(-2147024882);
  v13 = (*(int (__fastcall **)(__int64 *, BSTR, BSTR, __int64, _QWORD, __int64 *))(v7 + 160))(a2, v11, v9, 48, 0, &v23);
  SysFreeString(v12);
  SysFreeString(v8);
  if ( (int)v13 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v13,
      0,
      "[%s:%d] failed; ",
      "wmi_query_execute",
      360);
    throw (windiag::system_exception *)pExceptionObject;
  }
  lua_createtable(a1, 0, 0);
  v14 = 1;
  v25[0] = 0;
  v26[0] = 0;
  v26[1] = 0;
  v15 = operator new(0x50u);
  *v15 = v15;
  v15[1] = v15;
  v15[2] = v15;
  *((_WORD *)v15 + 12) = 257;
  v26[0] = v15;
  while ( a4 )
  {
    v22 = 0;
    v21 = 0;
    if ( (unsigned __int8)anonymous_namespace_::lua_check_control_events(a1, 0) )
      luaL_error(a1, "lua stop signal received");
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, BSTR *, int *))(*(_QWORD *)v23 + 32LL))(
            v23,
            0xFFFFFFFFLL,
            1,
            &v21,
            &v22);
    v17 = v16;
    if ( v16 < 0 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v16,
        0,
        "[%s:%d] failed; ",
        "wmi_query_execute",
        373);
      throw (windiag::system_exception *)pExceptionObject;
    }
    if ( v16 || v22 != 1 )
      goto LABEL_22;
    v18 = v21;
    if ( v21 )
    {
      v19 = v14++;
      lua_pushinteger(a1, v19);
      lua_createtable(a1, 0, 0);
      anonymous_namespace_::wmi_object_property_meta::init(v25, v21);
      anonymous_namespace_::wmi_object_property_meta::set_fields(v25, a1, v21);
      LODWORD(v24) = 0;
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(BSTR, const wchar_t *, _QWORD, VARIANTARG *, BSTR *, _QWORD))(*(_QWORD *)v21 + 32LL))(
             v21,
             L"__relpath",
             0,
             &pvarg,
             &v24,
             0) >= 0
        && pvarg.vt == 8
        && pvarg.llVal )
      {
        v20 = windiag::wchar_to_string(v28, pvarg.llVal);
        if ( *(_QWORD *)(v20 + 24) > 0xFu )
          v20 = *(_QWORD *)v20;
        lua_pushstring(a1, (const char *)v20);
        std::string::~string(v28);
        lua_setfield(a1, 4294967294LL, "__path");
      }
      lua_settable(a1, 4294967293LL);
      --a4;
      VariantClear(&pvarg);
LABEL_22:
      v18 = v21;
    }
    if ( v18 )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v17 )
      break;
  }
  std::_Tree<std::_Tmap_traits<std::string,std::pair<long,ATL::CComBSTR>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<long,ATL::CComBSTR>>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::pair<long,ATL::CComBSTR>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<long,ATL::CComBSTR>>>,0>>(v26);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
}

```

## disassembly

```asm
0x18008cec8  mov     [rsp-8+arg_18], rbx
0x18008cecd  push    rbp
0x18008cece  push    rsi
0x18008cecf  push    rdi
0x18008ced0  push    r12
0x18008ced2  push    r13
0x18008ced4  push    r14
0x18008ced6  push    r15
0x18008ced8  lea     rbp, [rsp-3F0h]
0x18008cee0  sub     rsp, 4F0h
0x18008cee7  mov     rax, cs:__security_cookie
0x18008ceee  xor     rax, rsp
0x18008cef1  mov     [rbp+420h+var_40], rax
0x18008cef8  mov     r14, r9
0x18008cefb  mov     r12, rdx
0x18008cefe  mov     rsi, rcx
0x18008cf01  mov     [rsp+520h+var_4D0], 0
0x18008cf0a  mov     r13, [rdx]
0x18008cf0d  test    r8, r8
0x18008cf10  jnz     short loc_18008CF1E
0x18008cf12  xor     ebx, ebx
0x18008cf14  mov     [rsp+520h+var_4E0], rbx
0x18008cf19  xor     r15d, r15d
0x18008cf1c  jmp     short loc_18008CF3B
0x18008cf1e  mov     rcx, r8; psz
0x18008cf21  call    cs:__imp_SysAllocString
0x18008cf27  mov     rbx, rax
0x18008cf2a  mov     [rsp+520h+var_4E0], rax
0x18008cf2f  test    rax, rax
0x18008cf32  jz      loc_18008D237
0x18008cf38  mov     r15, rax
0x18008cf3b  lea     rcx, psz; "WQL"
0x18008cf42  call    cs:__imp_SysAllocString
0x18008cf48  mov     rdi, rax
0x18008cf4b  mov     [rsp+520h+var_4C8], rax
0x18008cf50  test    rax, rax
0x18008cf53  jz      loc_18008D242
0x18008cf59  lea     rax, [rsp+520h+var_4D0]
0x18008cf5e  mov     [rsp+520h+var_4F8], rax
0x18008cf63  mov     [rsp+520h+var_500], 0
0x18008cf6c  mov     r9d, 30h ; '0'
0x18008cf72  mov     r8, r15
0x18008cf75  mov     rdx, rdi
0x18008cf78  mov     rcx, r12
0x18008cf7b  mov     rax, [r13+0A0h]
0x18008cf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf87  movsxd  r15, eax
0x18008cf8a  mov     rcx, rdi; bstrString
0x18008cf8d  call    cs:__imp_SysFreeString
0x18008cf93  nop
0x18008cf94  mov     rcx, rbx; bstrString
0x18008cf97  call    cs:__imp_SysFreeString
0x18008cf9d  xor     r12d, r12d
0x18008cfa0  test    r15d, r15d
0x18008cfa3  js      loc_18008D1C1
0x18008cfa9  xor     r8d, r8d; int
0x18008cfac  xor     edx, edx; int
0x18008cfae  mov     rcx, rsi; struct lua_State *
0x18008cfb1  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18008cfb6  lea     edi, [r12+1]
0x18008cfbb  mov     [rsp+520h+var_4C0], r12b
0x18008cfc0  mov     [rsp+520h+var_4B8], r12
0x18008cfc5  mov     [rsp+520h+var_4B0], r12
0x18008cfca  lea     ecx, [rdi+4Fh]; Size
0x18008cfcd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008cfd2  mov     [rax], rax
0x18008cfd5  mov     [rax+8], rax
0x18008cfd9  mov     [rax+10h], rax
0x18008cfdd  mov     word ptr [rax+18h], 101h
0x18008cfe3  mov     [rsp+520h+var_4B8], rax
0x18008cfe8  test    r14, r14
0x18008cfeb  jz      loc_18008D175
0x18008cff1  mov     [rsp+520h+var_4D8], r12d
0x18008cff6  mov     [rsp+520h+var_4E0], r12
0x18008cffb  xor     r8d, r8d
0x18008cffe  xor     edx, edx; dwMilliseconds
0x18008d000  mov     rcx, rsi; struct lua_State *
0x18008d003  call    _anonymous_namespace___lua_check_control_events
0x18008d008  test    al, al
0x18008d00a  jz      short loc_18008D01B
0x18008d00c  lea     rdx, aLuaStopSignalR; "lua stop signal received"
0x18008d013  mov     rcx, rsi; struct lua_State *
0x18008d016  call    ?luaL_error@@YAHPEAUlua_State@@PEBDZZ; luaL_error(lua_State *,char const *,...)
0x18008d01b  mov     rcx, [rsp+520h+var_4D0]
0x18008d020  mov     rax, [rcx]
0x18008d023  lea     rdx, [rsp+520h+var_4D8]
0x18008d028  mov     [rsp+520h+var_500], rdx
0x18008d02d  lea     r9, [rsp+520h+var_4E0]
0x18008d032  mov     r8d, 1
0x18008d038  or      edx, 0FFFFFFFFh
0x18008d03b  mov     rax, [rax+20h]
0x18008d03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d044  movsxd  rbx, eax
0x18008d047  test    eax, eax
0x18008d049  js      loc_18008D1FC
0x18008d04f  jnz     loc_18008D156
0x18008d055  cmp     [rsp+520h+var_4D8], 1
0x18008d05a  jnz     loc_18008D156
0x18008d060  mov     rcx, [rsp+520h+var_4E0]
0x18008d065  test    rcx, rcx
0x18008d068  jz      loc_18008D15B
0x18008d06e  movsxd  rdx, edi; __int64
0x18008d071  inc     edi
0x18008d073  mov     rcx, rsi; struct lua_State *
0x18008d076  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18008d07b  xor     r8d, r8d; int
0x18008d07e  xor     edx, edx; int
0x18008d080  mov     rcx, rsi; struct lua_State *
0x18008d083  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18008d088  mov     rdx, [rsp+520h+var_4E0]
0x18008d08d  lea     rcx, [rsp+520h+var_4C0]
0x18008d092  call    _anonymous_namespace___wmi_object_property_meta__init
0x18008d097  mov     r8, [rsp+520h+var_4E0]
0x18008d09c  mov     rdx, rsi
0x18008d09f  lea     rcx, [rsp+520h+var_4C0]
0x18008d0a4  call    _anonymous_namespace___wmi_object_property_meta__set_fields
0x18008d0a9  mov     dword ptr [rsp+520h+var_4C8], r12d
0x18008d0ae  lea     rcx, [rsp+520h+pvarg]; pvarg
0x18008d0b3  call    cs:__imp_VariantInit
0x18008d0b9  nop
0x18008d0ba  mov     rcx, [rsp+520h+var_4E0]
0x18008d0bf  mov     rax, [rcx]
0x18008d0c2  mov     [rsp+520h+var_4F8], r12
0x18008d0c7  lea     rdx, [rsp+520h+var_4C8]
0x18008d0cc  mov     [rsp+520h+var_500], rdx
0x18008d0d1  lea     r9, [rsp+520h+pvarg]
0x18008d0d6  xor     r8d, r8d
0x18008d0d9  lea     rdx, aRelpath; "__relpath"
0x18008d0e0  mov     rax, [rax+20h]
0x18008d0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d0e9  test    eax, eax
0x18008d0eb  js      short loc_18008D13B
0x18008d0ed  cmp     word ptr [rsp+520h+pvarg], 8
0x18008d0f3  jnz     short loc_18008D13B
0x18008d0f5  mov     rdx, qword ptr [rbp+420h+pvarg+8]
0x18008d0f9  test    rdx, rdx
0x18008d0fc  jz      short loc_18008D13B
0x18008d0fe  lea     rcx, [rbp+420h+var_490]
0x18008d102  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x18008d107  nop
0x18008d108  cmp     qword ptr [rax+18h], 0Fh
0x18008d10d  jbe     short loc_18008D112
0x18008d10f  mov     rax, [rax]
0x18008d112  mov     rdx, rax; char *
0x18008d115  mov     rcx, rsi; struct lua_State *
0x18008d118  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18008d11d  nop
0x18008d11e  lea     rcx, [rbp+420h+var_490]
0x18008d122  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18008d127  lea     r8, aPath_0; "__path"
0x18008d12e  mov     edx, 0FFFFFFFEh; int
0x18008d133  mov     rcx, rsi; struct lua_State *
0x18008d136  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18008d13b  mov     edx, 0FFFFFFFDh; int
0x18008d140  mov     rcx, rsi; struct lua_State *
0x18008d143  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x18008d148  dec     r14
0x18008d14b  lea     rcx, [rsp+520h+pvarg]; pvarg
0x18008d150  call    cs:__imp_VariantClear
0x18008d156  mov     rcx, [rsp+520h+var_4E0]
0x18008d15b  test    rcx, rcx
0x18008d15e  jz      short loc_18008D16D
0x18008d160  mov     rax, [rcx]
0x18008d163  mov     rax, [rax+10h]
0x18008d167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d16c  nop
0x18008d16d  test    ebx, ebx
0x18008d16f  jz      loc_18008CFE8
0x18008d175  lea     rcx, [rsp+520h+var_4B8]
0x18008d17a  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@JVCComBSTR@ATL@@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$pair@JVCComBSTR@ATL@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::pair<long,ATL::CComBSTR>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<long,ATL::CComBSTR>>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::pair<long,ATL::CComBSTR>,std::less<std::string>,std::allocator<std::pair<std::string const,std::pair<long,ATL::CComBSTR>>>,0>>(void)
0x18008d17f  nop
0x18008d180  mov     rcx, [rsp+520h+var_4D0]
0x18008d185  test    rcx, rcx
0x18008d188  jz      short loc_18008D197
0x18008d18a  mov     rax, [rcx]
0x18008d18d  mov     rax, [rax+10h]
0x18008d191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d196  nop
0x18008d197  mov     rcx, [rbp+420h+var_40]
0x18008d19e  xor     rcx, rsp; StackCookie
0x18008d1a1  call    __security_check_cookie
0x18008d1a6  mov     rbx, [rsp+520h+arg_18]
0x18008d1ae  add     rsp, 4F0h
0x18008d1b5  pop     r15
0x18008d1b7  pop     r14
0x18008d1b9  pop     r13
0x18008d1bb  pop     r12
0x18008d1bd  pop     rdi
0x18008d1be  pop     rsi
0x18008d1bf  pop     rbp
0x18008d1c0  retn
0x18008d1c1  mov     rdx, r15; __int64
0x18008d1c4  mov     dword ptr [rsp+520h+var_4F8], 168h
0x18008d1cc  lea     rax, aWmiQueryExecut; "wmi_query_execute"
0x18008d1d3  mov     [rsp+520h+var_500], rax
0x18008d1d8  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008d1df  xor     r8d, r8d; void *
0x18008d1e2  lea     rcx, [rbp+420h+pExceptionObject]; this
0x18008d1e6  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008d1eb  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008d1f2  lea     rcx, [rbp+420h+pExceptionObject]; pExceptionObject
0x18008d1f6  call    _CxxThrowException_0
0x18008d1fc  mov     rdx, rbx; __int64
0x18008d1ff  mov     dword ptr [rsp+520h+var_4F8], 175h
0x18008d207  lea     rax, aWmiQueryExecut; "wmi_query_execute"
0x18008d20e  mov     [rsp+520h+var_500], rax
0x18008d213  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008d21a  xor     r8d, r8d; void *
0x18008d21d  lea     rcx, [rbp+420h+pExceptionObject]; this
0x18008d221  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008d226  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008d22d  lea     rcx, [rbp+420h+pExceptionObject]; pExceptionObject
0x18008d231  call    _CxxThrowException_0
0x18008d237  mov     ecx, 8007000Eh; int
0x18008d23c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008d242  mov     ecx, 8007000Eh; int
0x18008d247  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
