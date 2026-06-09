# _anonymous_namespace_::file_enum_emit_info

- ea: `0x18006963c`
- end: `0x180069904`
- name: `_anonymous_namespace_::file_enum_emit_info`
- size: `712`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180068fe4`

## callees

- `0x180004510`
- `0x180006050`
- `0x180006c50`
- `0x180006d40`
- `0x180007160`
- `0x1800073e0`
- `0x18003b0bc`
- `0x18003d720`
- `0x180041564`
- `0x180041e58`
- `0x1800527d8`
- `0x1800571a4`
- `0x18006963c`
- `0x18006a1c4`

## string_xrefs

- `0x1800697a6`: `create_time`
- `0x1800697d0`: `access_time`
- `0x1800697fa`: `write_time`
- `0x180069839`: `create_time_utc`
- `0x180069878`: `access_time_utc`
- `0x1800698b7`: `write_time_utc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::file_enum_emit_info(
        struct lua_State *a1,
        unsigned int *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v7; // rax
  char **v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v14; // [rsp+40h] [rbp-49h] BYREF
  char *v15[4]; // [rsp+48h] [rbp-41h] BYREF
  char *v16[4]; // [rsp+68h] [rbp-21h] BYREF
  char *v17[4]; // [rsp+88h] [rbp-1h] BYREF

  LOWORD(v14) = 92;
  v7 = a3[2];
  if ( v7 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  std::wstring::wstring(v17, a2, a3, a3, v7, &v14, 1);
  std::operator+<unsigned short>(v16, v17, a2 + 11);
  std::wstring::~wstring(v17);
  lua_pushinteger(a1, a4);
  lua_createtable(a1, 0, 0);
  v8 = v16;
  if ( v16[3] > (char *)7 )
    v8 = (char **)v16[0];
  v9 = windiag::wchar_to_string(v15, v8);
  if ( *(_QWORD *)(v9 + 24) > 0xFu )
    v9 = *(_QWORD *)v9;
  lua_pushstring(a1, (const char *)v9);
  std::string::~string(v15);
  lua_setfield(a1, 4294967294LL, "path");
  LODWORD(v14) = a2[8];
  HIDWORD(v14) = a2[7];
  lua_pushinteger(a1, v14);
  lua_setfield(a1, 4294967294LL, "size");
  v14 = *a2;
  lua_pushinteger(a1, v14);
  lua_setfield(a1, 4294967294LL, "attributes");
  v14 = *(_QWORD *)(a2 + 1);
  lua_pushinteger(a1, v14);
  lua_setfield(a1, 4294967294LL, "create_time");
  v14 = *(_QWORD *)(a2 + 3);
  lua_pushinteger(a1, v14);
  lua_setfield(a1, 4294967294LL, "access_time");
  v14 = *(_QWORD *)(a2 + 5);
  lua_pushinteger(a1, v14);
  lua_setfield(a1, 4294967294LL, "write_time");
  v10 = anonymous_namespace_::format_utc_time(v15, a2 + 1);
  if ( *(_QWORD *)(v10 + 24) > 0xFu )
    v10 = *(_QWORD *)v10;
  lua_pushstring(a1, (const char *)v10);
  std::string::~string(v15);
  lua_setfield(a1, 4294967294LL, "create_time_utc");
  v11 = anonymous_namespace_::format_utc_time(v15, a2 + 3);
  if ( *(_QWORD *)(v11 + 24) > 0xFu )
    v11 = *(_QWORD *)v11;
  lua_pushstring(a1, (const char *)v11);
  std::string::~string(v15);
  lua_setfield(a1, 4294967294LL, "access_time_utc");
  v12 = anonymous_namespace_::format_utc_time(v15, a2 + 5);
  if ( *(_QWORD *)(v12 + 24) > 0xFu )
    v12 = *(_QWORD *)v12;
  lua_pushstring(a1, (const char *)v12);
  std::string::~string(v15);
  lua_setfield(a1, 4294967294LL, "write_time_utc");
  lua_settable(a1, 4294967293LL);
  return std::wstring::~wstring(v16);
}

```

## disassembly

```asm
0x18006963c  push    rbp
0x18006963e  push    rbx
0x18006963f  push    rsi
0x180069640  push    rdi
0x180069641  push    r12
0x180069643  push    r14
0x180069645  push    r15
0x180069647  lea     rbp, [rsp-27h]
0x18006964c  sub     rsp, 0B0h
0x180069653  mov     rax, cs:__security_cookie
0x18006965a  xor     rax, rsp
0x18006965d  mov     [rbp+57h+var_38], rax
0x180069661  mov     rbx, r9
0x180069664  mov     rsi, rdx
0x180069667  mov     rdi, rcx
0x18006966a  mov     eax, 5Ch ; '\'
0x18006966f  mov     word ptr [rbp+57h+var_A0], ax
0x180069673  mov     rax, [r8+10h]
0x180069677  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180069681  cmp     rax, rcx
0x180069684  jz      loc_1800698FE
0x18006968a  cmp     qword ptr [r8+18h], 7
0x18006968f  jbe     short loc_180069694
0x180069691  mov     r8, [r8]
0x180069694  mov     [rsp+0E0h+var_B0], 1
0x18006969d  lea     rcx, [rbp+57h+var_A0]
0x1800696a1  mov     [rsp+0E0h+var_B8], rcx
0x1800696a6  mov     [rsp+0E0h+var_C0], rax
0x1800696ab  mov     r9, r8
0x1800696ae  lea     rcx, [rbp+57h+var_58]
0x1800696b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800696b7  nop
0x1800696b8  lea     r8, [rsi+2Ch]
0x1800696bc  lea     rdx, [rbp+57h+var_58]
0x1800696c0  lea     rcx, [rbp+57h+var_78]
0x1800696c4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800696c9  nop
0x1800696ca  lea     rcx, [rbp+57h+var_58]
0x1800696ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800696d3  mov     rdx, rbx; __int64
0x1800696d6  mov     rcx, rdi; struct lua_State *
0x1800696d9  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800696de  xor     r8d, r8d; int
0x1800696e1  xor     edx, edx; int
0x1800696e3  mov     rcx, rdi; struct lua_State *
0x1800696e6  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x1800696eb  lea     rdx, [rbp+57h+var_78]
0x1800696ef  cmp     [rbp+57h+var_60], 7
0x1800696f4  cmova   rdx, [rbp+57h+var_78]
0x1800696f9  lea     rcx, [rbp+57h+var_98]
0x1800696fd  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x180069702  nop
0x180069703  cmp     qword ptr [rax+18h], 0Fh
0x180069708  jbe     short loc_18006970D
0x18006970a  mov     rax, [rax]
0x18006970d  mov     rdx, rax; char *
0x180069710  mov     rcx, rdi; struct lua_State *
0x180069713  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x180069718  nop
0x180069719  lea     rcx, [rbp+57h+var_98]
0x18006971d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180069722  lea     r8, aPath; "path"
0x180069729  mov     r12d, 0FFFFFFFEh
0x18006972f  mov     edx, r12d; int
0x180069732  mov     rcx, rdi; struct lua_State *
0x180069735  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006973a  mov     eax, [rsi+20h]
0x18006973d  mov     dword ptr [rbp+57h+var_A0], eax
0x180069740  mov     eax, [rsi+1Ch]
0x180069743  mov     dword ptr [rbp+57h+var_A0+4], eax
0x180069746  mov     rdx, [rbp+57h+var_A0]; __int64
0x18006974a  mov     rcx, rdi; struct lua_State *
0x18006974d  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180069752  lea     r8, aSize; "size"
0x180069759  mov     edx, r12d; int
0x18006975c  mov     rcx, rdi; struct lua_State *
0x18006975f  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x180069764  mov     eax, [rsi]
0x180069766  mov     dword ptr [rbp+57h+var_A0], eax
0x180069769  mov     dword ptr [rbp+57h+var_A0+4], 0
0x180069770  mov     rdx, [rbp+57h+var_A0]; __int64
0x180069774  mov     rcx, rdi; struct lua_State *
0x180069777  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006977c  lea     r8, aAttributes; "attributes"
0x180069783  mov     edx, r12d; int
0x180069786  mov     rcx, rdi; struct lua_State *
0x180069789  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006978e  mov     eax, [rsi+4]
0x180069791  mov     dword ptr [rbp+57h+var_A0], eax
0x180069794  mov     eax, [rsi+8]
0x180069797  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18006979a  mov     rdx, [rbp+57h+var_A0]; __int64
0x18006979e  mov     rcx, rdi; struct lua_State *
0x1800697a1  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800697a6  lea     r8, aCreateTime; "create_time"
0x1800697ad  mov     edx, r12d; int
0x1800697b0  mov     rcx, rdi; struct lua_State *
0x1800697b3  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x1800697b8  mov     eax, [rsi+0Ch]
0x1800697bb  mov     dword ptr [rbp+57h+var_A0], eax
0x1800697be  mov     eax, [rsi+10h]
0x1800697c1  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1800697c4  mov     rdx, [rbp+57h+var_A0]; __int64
0x1800697c8  mov     rcx, rdi; struct lua_State *
0x1800697cb  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800697d0  lea     r8, aAccessTime; "access_time"
0x1800697d7  mov     edx, r12d; int
0x1800697da  mov     rcx, rdi; struct lua_State *
0x1800697dd  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x1800697e2  mov     eax, [rsi+14h]
0x1800697e5  mov     dword ptr [rbp+57h+var_A0], eax
0x1800697e8  mov     eax, [rsi+18h]
0x1800697eb  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1800697ee  mov     rdx, [rbp+57h+var_A0]; __int64
0x1800697f2  mov     rcx, rdi; struct lua_State *
0x1800697f5  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800697fa  lea     r8, aWriteTime; "write_time"
0x180069801  mov     edx, r12d; int
0x180069804  mov     rcx, rdi; struct lua_State *
0x180069807  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006980c  lea     rdx, [rsi+4]
0x180069810  lea     rcx, [rbp+57h+var_98]
0x180069814  call    _anonymous_namespace___format_utc_time
0x180069819  nop
0x18006981a  cmp     qword ptr [rax+18h], 0Fh
0x18006981f  jbe     short loc_180069824
0x180069821  mov     rax, [rax]
0x180069824  mov     rdx, rax; char *
0x180069827  mov     rcx, rdi; struct lua_State *
0x18006982a  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18006982f  nop
0x180069830  lea     rcx, [rbp+57h+var_98]
0x180069834  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180069839  lea     r8, aCreateTimeUtc; "create_time_utc"
0x180069840  mov     edx, r12d; int
0x180069843  mov     rcx, rdi; struct lua_State *
0x180069846  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006984b  lea     rdx, [rsi+0Ch]
0x18006984f  lea     rcx, [rbp+57h+var_98]
0x180069853  call    _anonymous_namespace___format_utc_time
0x180069858  nop
0x180069859  cmp     qword ptr [rax+18h], 0Fh
0x18006985e  jbe     short loc_180069863
0x180069860  mov     rax, [rax]
0x180069863  mov     rdx, rax; char *
0x180069866  mov     rcx, rdi; struct lua_State *
0x180069869  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18006986e  nop
0x18006986f  lea     rcx, [rbp+57h+var_98]
0x180069873  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180069878  lea     r8, aAccessTimeUtc; "access_time_utc"
0x18006987f  mov     edx, r12d; int
0x180069882  mov     rcx, rdi; struct lua_State *
0x180069885  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006988a  lea     rdx, [rsi+14h]
0x18006988e  lea     rcx, [rbp+57h+var_98]
0x180069892  call    _anonymous_namespace___format_utc_time
0x180069897  nop
0x180069898  cmp     qword ptr [rax+18h], 0Fh
0x18006989d  jbe     short loc_1800698A2
0x18006989f  mov     rax, [rax]
0x1800698a2  mov     rdx, rax; char *
0x1800698a5  mov     rcx, rdi; struct lua_State *
0x1800698a8  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x1800698ad  nop
0x1800698ae  lea     rcx, [rbp+57h+var_98]
0x1800698b2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800698b7  lea     r8, aWriteTimeUtc; "write_time_utc"
0x1800698be  mov     edx, r12d; int
0x1800698c1  mov     rcx, rdi; struct lua_State *
0x1800698c4  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x1800698c9  mov     edx, 0FFFFFFFDh; int
0x1800698ce  mov     rcx, rdi; struct lua_State *
0x1800698d1  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x1800698d6  nop
0x1800698d7  lea     rcx, [rbp+57h+var_78]
0x1800698db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800698e0  mov     rcx, [rbp+57h+var_38]
0x1800698e4  xor     rcx, rsp; StackCookie
0x1800698e7  call    __security_check_cookie
0x1800698ec  add     rsp, 0B0h
0x1800698f3  pop     r15
0x1800698f5  pop     r14
0x1800698f7  pop     r12
0x1800698f9  pop     rdi
0x1800698fa  pop     rsi
0x1800698fb  pop     rbx
0x1800698fc  pop     rbp
0x1800698fd  retn
0x1800698fe  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
