# _anonymous_namespace_::native_invoke

- ea: `0x18007a220`
- end: `0x18007a880`
- name: `_anonymous_namespace_::native_invoke`
- size: `1632`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `34`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004510`
- `0x1800054d8`
- `0x180005520`
- `0x180006690`
- `0x180006790`
- `0x1800067f0`
- `0x180006910`
- `0x180006980`
- `0x180006c50`
- `0x180006d00`
- `0x180007490`
- `0x180007740`
- `0x180007950`
- `0x1800081b0`
- `0x1800083a0`
- `0x180008430`
- `0x180008610`
- `0x180008790`
- `0x180009510`
- `0x180009540`
- `0x18003a52c`
- `0x18003af08`
- `0x18003b0bc`
- `0x18003b3b0`
- `0x18003d738`
- `0x1800431c0`
- `0x1800496e0`
- `0x180079484`
- `0x180079614`
- `0x180079684`
- `0x1800796d8`
- `0x180079814`
- `0x18007a220`
- `0x180096c30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a45a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007a45a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a361`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a5e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a7cc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a361`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a5e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a7cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18007a384`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18007a384`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007a689`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007a689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a38e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a6ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a38e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a6ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a5f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a5f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a608`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a5c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a5c5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007a5d5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007a5d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a5b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a6f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a5b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a6f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall anonymous_namespace_::native_invoke(struct lua_State *a1)
{
  HMODULE v2; // r12
  int v3; // esi
  const char *v4; // rax
  size_t v5; // r8
  size_t v6; // rbx
  void **v7; // rcx
  void **v8; // r14
  unsigned __int64 v9; // r15
  HMODULE v10; // rcx
  const CHAR *v11; // rax
  DWORD LastError; // eax
  void **v13; // rcx
  const char *v14; // rax
  void **v15; // rcx
  const CHAR *v16; // rdx
  FARPROC ProcAddress; // r15
  DWORD v18; // eax
  int v19; // r14d
  HKEY v20; // rax
  __int64 v21; // rdx
  HKEY *v22; // rax
  HKEY *v23; // rax
  HKEY v24; // rbx
  HKEY v25; // rcx
  __int64 v27; // rax
  HKEY v28; // rbx
  __int64 v29; // r14
  int v30; // esi
  int v31; // esi
  int v32; // esi
  int v33; // esi
  int v34; // esi
  HMODULE v35; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v38; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h]
  HMODULE hLibModule; // [rsp+50h] [rbp-B0h] BYREF
  void *Buf1[2]; // [rsp+58h] [rbp-A8h] BYREF
  size_t Size; // [rsp+68h] [rbp-98h]
  unsigned __int64 v43; // [rsp+70h] [rbp-90h]
  LPCSTR lpProcName[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h]
  unsigned __int64 v46; // [rsp+90h] [rbp-70h]
  _BYTE pExceptionObject[1072]; // [rsp+A0h] [rbp-60h] BYREF

  hLibModule = 0;
  v2 = 0;
  *(_OWORD *)lpProcName = 0;
  v45 = 0;
  v46 = 15;
  LOBYTE(lpProcName[0]) = 0;
  v3 = 0;
  luaL_checktype(a1, 1, 5);
  lua_pushnil(a1);
  while ( (unsigned int)lua_next(a1, 1) )
  {
    if ( (unsigned int)lua_type(a1, 4294967294LL) != 4 )
      luaL_argerror(a1, 2, "call options table key should be string");
    v4 = lua_tolstring(a1, 4294967294LL, 0);
    *(_OWORD *)Buf1 = 0;
    Size = 0;
    v43 = 0;
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    std::string::_Construct<1,char const *>(Buf1, v4, v5);
    v6 = Size;
    v7 = Buf1;
    v8 = (void **)Buf1[0];
    v9 = v43;
    if ( v43 > 0xF )
      v7 = (void **)Buf1[0];
    if ( Size == 6 && !memcmp_0(v7, "module", 6u) )
    {
      if ( (unsigned int)lua_isinteger(a1, -1) )
      {
        v2 = (HMODULE)luaL_checkinteger(a1, -1);
      }
      else
      {
        v10 = hLibModule;
        if ( hLibModule )
        {
          hLibModule = 0;
          FreeLibrary(v10);
        }
        hLibModule = 0;
        v11 = luaL_checklstring(a1, -1, 0);
        if ( !GetModuleHandleExA(0, v11, &hLibModule) )
        {
          LastError = GetLastError();
          if ( LastError )
          {
            windiag::system_exception::system_exception(
              (windiag::system_exception *)pExceptionObject,
              LastError,
              0,
              "[%s:%d] failed; ",
              "native_invoke",
              314);
            throw (windiag::system_exception *)pExceptionObject;
          }
        }
        v2 = hLibModule;
      }
    }
    else
    {
      v13 = Buf1;
      if ( v9 > 0xF )
        v13 = v8;
      if ( v6 == 4 && !memcmp_0(v13, "name", 4u) )
      {
        v14 = luaL_checklstring(a1, -1, 0);
        std::string::operator=(lpProcName, v14);
      }
      else
      {
        v15 = Buf1;
        if ( v9 > 0xF )
          v15 = v8;
        if ( v6 == 8 && !memcmp_0(v15, "res_type", 8u) )
          v3 = luaL_checkinteger(a1, -1);
      }
    }
    lua_settop(a1, -2);
    std::string::~string((char **)Buf1);
  }
  v16 = (const CHAR *)lpProcName;
  if ( v46 > 0xF )
    v16 = lpProcName[0];
  ProcAddress = GetProcAddress(v2, v16);
  if ( !ProcAddress )
  {
    v18 = GetLastError();
    if ( v18 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v18,
        0,
        "[%s:%d] failed; ",
        "native_invoke",
        328);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v38 = 0;
  v39 = 0;
  v19 = 2;
  if ( (int)lua_gettop(a1) >= 2 )
  {
    while ( 1 )
    {
      if ( (unsigned int)lua_isinteger(a1, v19) )
      {
        v20 = (HKEY)luaL_checkinteger(a1, v19);
LABEL_36:
        hKey = v20;
        v21 = *((_QWORD *)&v38 + 1);
        if ( *((_QWORD *)&v38 + 1) == v39 )
          goto LABEL_74;
        **((_QWORD **)&v38 + 1) = v20;
        goto LABEL_38;
      }
      v22 = (HKEY *)luaL_testudata(a1, v19, "native.buffer");
      if ( v22 )
      {
        v20 = *v22;
        goto LABEL_36;
      }
      v23 = (HKEY *)luaL_testudata(a1, v19, "native.resource");
      v24 = (HKEY)v23;
      if ( !v23 )
      {
        if ( !(unsigned int)lua_isstring(a1, v19) )
          luaL_error(a1, "unexpected native argument (%d)", v19 - 2);
        v20 = (HKEY)luaL_checklstring(a1, v19, 0);
        goto LABEL_36;
      }
      if ( *((char *)v23 + 8) == -1 )
        std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_std::pair_void_const___unsigned___int64___lambda_0f2987df398fcf62c701e32323b26f6e__std::variant_std::vector_char_std::allocator_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____unsigned_long___int64_std::pair_void_const___unsigned___int64______1_();
      v25 = *v23;
      if ( *((_BYTE *)v23 + 8) == 1 ? v25 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL : v25 == 0 )
        break;
      if ( *((char *)v23 + 8) == -1 )
        std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_std::pair_void_const___unsigned___int64___lambda_0f2987df398fcf62c701e32323b26f6e__std::variant_std::vector_char_std::allocator_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____unsigned_long___int64_std::pair_void_const___unsigned___int64______1_();
      hKey = *v23;
      v21 = *((_QWORD *)&v38 + 1);
      if ( *((_QWORD *)&v38 + 1) == v39 )
      {
LABEL_74:
        std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64>(&v38, v21, &hKey);
        goto LABEL_76;
      }
      **((_QWORD **)&v38 + 1) = v25;
LABEL_38:
      *((_QWORD *)&v38 + 1) += 8LL;
LABEL_76:
      if ( ++v19 > (int)lua_gettop(a1) )
        goto LABEL_77;
    }
    if ( *((char *)v23 + 8) == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_std::pair_void_const___unsigned___int64___lambda_0f2987df398fcf62c701e32323b26f6e__std::variant_std::vector_char_std::allocator_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____unsigned_long___int64_std::pair_void_const___unsigned___int64______1_();
    if ( *((_BYTE *)v23 + 8) )
    {
      switch ( *((_BYTE *)v23 + 8) )
      {
        case 1:
          if ( v25 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          {
            *v23 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
            CloseHandle(v25);
          }
          v27 = -1;
          goto LABEL_70;
        case 2:
          if ( v25 )
          {
            *v23 = 0;
            FreeLibrary((HMODULE)v25);
          }
          break;
        case 3:
          if ( v25 )
          {
            *v23 = 0;
            CloseServiceHandle((SC_HANDLE)v25);
          }
          break;
        case 4:
          if ( v25 )
          {
            *v23 = 0;
            LocalFree(v25);
          }
          break;
        default:
          if ( v25 )
          {
            *v23 = 0;
            RegCloseKey(v25);
          }
          break;
      }
    }
    else if ( v25 )
    {
      *v23 = 0;
      CloseHandle(v25);
    }
    v27 = 0;
LABEL_70:
    *(_QWORD *)v24 = v27;
    hKey = v24;
    v21 = *((_QWORD *)&v38 + 1);
    if ( *((_QWORD *)&v38 + 1) == v39 )
      goto LABEL_74;
    **((_QWORD **)&v38 + 1) = v24;
    goto LABEL_38;
  }
LABEL_77:
  SetLastError(0);
  v28 = (HKEY)DynamicStdcall(ProcAddress, (__int64)(*((_QWORD *)&v38 + 1) - v38) >> 3);
  v29 = GetLastError();
  LOBYTE(Size) = 0;
  v30 = v3 - 1;
  if ( !v30 )
  {
    LOBYTE(Buf1[1]) = 0;
    goto LABEL_92;
  }
  v31 = v30 - 1;
  if ( !v31 )
  {
    LOBYTE(Buf1[1]) = 1;
    goto LABEL_92;
  }
  v32 = v31 - 1;
  if ( !v32 )
  {
    LOBYTE(Buf1[1]) = 2;
    goto LABEL_92;
  }
  v33 = v32 - 1;
  if ( !v33 )
  {
    LOBYTE(Buf1[1]) = 3;
    goto LABEL_92;
  }
  v34 = v33 - 1;
  if ( !v34 )
  {
    LOBYTE(Buf1[1]) = 4;
LABEL_92:
    Buf1[0] = v28;
    LOBYTE(Size) = 1;
    goto LABEL_93;
  }
  if ( v34 != 1 )
    goto LABEL_86;
  hKey = v28;
  std::optional<std::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>>::emplace<windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>(
    (__int64)Buf1,
    (__int64 *)&hKey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( !(_BYTE)Size )
  {
LABEL_86:
    lua_pushinteger(a1, (__int64)v28);
    goto LABEL_98;
  }
LABEL_93:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl'::`2'::impl) )
  {
    windiag::lua_create_user_object__anonymous_namespace_::native_resource_state_std::variant_windiag::win_handle_void___windiag::close_handle_0__windiag::win_handle_void___windiag::close_handle__1__windiag::win_handle_HINSTANCE_____windiag::close_dll_0__windiag::win_handle_SC_HANDLE_____windiag::close_scm_0__windiag::win_handle_void___windiag::close_hlocal_0__windiag::win_handle_HKEY_____windiag::close_hkey_0_____(a1);
  }
  else
  {
    hKey = (HKEY)lua_newuserdatauv(a1, 0x10u, 0);
    std::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>::variant<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>(
      (__int64)hKey,
      (__int64 *)Buf1);
    luaL_setmetatable(a1, "native.resource");
  }
  if ( (_BYTE)Size )
    std::_Variant_destroy_layer_<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>::~_Variant_destroy_layer_<windiag::win_handle<void *,windiag::close_handle,0>,windiag::win_handle<void *,windiag::close_handle,-1>,windiag::win_handle<HINSTANCE__ *,windiag::close_dll,0>,windiag::win_handle<SC_HANDLE__ *,windiag::close_scm,0>,windiag::win_handle<void *,windiag::close_hlocal,0>,windiag::win_handle<HKEY__ *,windiag::close_hkey,0>>((__int64)Buf1);
LABEL_98:
  lua_pushinteger(a1, v29);
  std::vector<unsigned __int64>::~vector<unsigned __int64>(&v38);
  std::string::~string((char **)lpProcName);
  v35 = hLibModule;
  if ( hLibModule )
  {
    hLibModule = 0;
    FreeLibrary(v35);
  }
  return 2;
}

```

## disassembly

```asm
0x18007a220  push    rbp
0x18007a222  push    rbx
0x18007a223  push    rsi
0x18007a224  push    rdi
0x18007a225  push    r12
0x18007a227  push    r13
0x18007a229  push    r14
0x18007a22b  push    r15
0x18007a22d  lea     rbp, [rsp-3E8h]
0x18007a235  sub     rsp, 4E8h
0x18007a23c  mov     rax, cs:__security_cookie
0x18007a243  xor     rax, rsp
0x18007a246  mov     [rbp+420h+var_50], rax
0x18007a24d  mov     rdi, rcx
0x18007a250  xor     r13d, r13d
0x18007a253  mov     [rsp+520h+hLibModule], r13
0x18007a258  mov     r12d, r13d
0x18007a25b  xorps   xmm0, xmm0
0x18007a25e  movups  xmmword ptr [rsp+520h+lpProcName], xmm0
0x18007a263  mov     [rbp+420h+var_498], r13
0x18007a267  mov     [rbp+420h+var_490], 0Fh
0x18007a26f  mov     byte ptr [rsp+520h+lpProcName], r13b
0x18007a274  mov     esi, r13d
0x18007a277  lea     ebx, [r13+1]
0x18007a27b  lea     r8d, [r13+5]; int
0x18007a27f  mov     edx, ebx; int
0x18007a281  call    ?luaL_checktype@@YAXPEAUlua_State@@HH@Z; luaL_checktype(lua_State *,int,int)
0x18007a286  mov     rcx, rdi; struct lua_State *
0x18007a289  call    ?lua_pushnil@@YAXPEAUlua_State@@@Z; lua_pushnil(lua_State *)
0x18007a28e  mov     edx, ebx
0x18007a290  jmp     loc_18007A437
0x18007a295  mov     edx, 0FFFFFFFEh; int
0x18007a29a  mov     rcx, rdi; struct lua_State *
0x18007a29d  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18007a2a2  cmp     eax, 4
0x18007a2a5  jz      short loc_18007A2BB
0x18007a2a7  lea     r8, aCallOptionsTab; "call options table key should be string"
0x18007a2ae  mov     edx, 2; int
0x18007a2b3  mov     rcx, rdi; struct lua_State *
0x18007a2b6  call    ?luaL_argerror@@YAHPEAUlua_State@@HPEBD@Z; luaL_argerror(lua_State *,int,char const *)
0x18007a2bb  xor     r8d, r8d; unsigned __int64 *
0x18007a2be  lea     edx, [r8-2]; int
0x18007a2c2  mov     rcx, rdi; struct lua_State *
0x18007a2c5  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x18007a2ca  xorps   xmm0, xmm0
0x18007a2cd  movups  xmmword ptr [rsp+520h+Buf1], xmm0
0x18007a2d2  mov     [rsp+520h+Size], r13
0x18007a2d7  mov     [rsp+520h+var_4B0], r13
0x18007a2dc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007a2e0  inc     r8
0x18007a2e3  cmp     [rax+r8], r13b
0x18007a2e7  jnz     short loc_18007A2E0
0x18007a2e9  mov     rdx, rax
0x18007a2ec  lea     rcx, [rsp+520h+Buf1]
0x18007a2f1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18007a2f6  nop
0x18007a2f7  mov     rbx, [rsp+520h+Size]
0x18007a2fc  lea     rcx, [rsp+520h+Buf1]
0x18007a301  mov     r14, [rsp+520h+Buf1]
0x18007a306  mov     r15, [rsp+520h+var_4B0]
0x18007a30b  cmp     r15, 0Fh
0x18007a30f  cmova   rcx, r14; Buf1
0x18007a313  cmp     rbx, 6
0x18007a317  jnz     loc_18007A3A3
0x18007a31d  mov     r8, rbx; Size
0x18007a320  lea     rdx, aModule; "module"
0x18007a327  call    memcmp_0
0x18007a32c  test    eax, eax
0x18007a32e  jnz     short loc_18007A3A3
0x18007a330  or      edx, 0FFFFFFFFh; int
0x18007a333  mov     rcx, rdi; struct lua_State *
0x18007a336  call    ?lua_isinteger@@YAHPEAUlua_State@@H@Z; lua_isinteger(lua_State *,int)
0x18007a33b  test    eax, eax
0x18007a33d  jz      short loc_18007A352
0x18007a33f  or      edx, 0FFFFFFFFh; int
0x18007a342  mov     rcx, rdi; struct lua_State *
0x18007a345  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007a34a  mov     r12, rax
0x18007a34d  jmp     loc_18007A41A
0x18007a352  mov     rcx, [rsp+520h+hLibModule]; hLibModule
0x18007a357  test    rcx, rcx
0x18007a35a  jz      short loc_18007A367
0x18007a35c  mov     [rsp+520h+hLibModule], r13
0x18007a361  call    cs:__imp_FreeLibrary
0x18007a367  mov     [rsp+520h+hLibModule], r13
0x18007a36c  xor     r8d, r8d; unsigned __int64 *
0x18007a36f  or      edx, 0FFFFFFFFh; int
0x18007a372  mov     rcx, rdi; struct lua_State *
0x18007a375  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18007a37a  lea     r8, [rsp+520h+hLibModule]; phModule
0x18007a37f  mov     rdx, rax; lpModuleName
0x18007a382  xor     ecx, ecx; dwFlags
0x18007a384  call    cs:__imp_GetModuleHandleExA
0x18007a38a  test    eax, eax
0x18007a38c  jnz     short loc_18007A39C
0x18007a38e  call    cs:__imp_GetLastError
0x18007a394  test    eax, eax
0x18007a396  jnz     loc_18007A83A
0x18007a39c  mov     r12, [rsp+520h+hLibModule]
0x18007a3a1  jmp     short loc_18007A41A
0x18007a3a3  lea     rcx, [rsp+520h+Buf1]
0x18007a3a8  cmp     r15, 0Fh
0x18007a3ac  cmova   rcx, r14; Buf1
0x18007a3b0  cmp     rbx, 4
0x18007a3b4  jnz     short loc_18007A3E6
0x18007a3b6  mov     r8, rbx; Size
0x18007a3b9  lea     rdx, aName; "name"
0x18007a3c0  call    memcmp_0
0x18007a3c5  test    eax, eax
0x18007a3c7  jnz     short loc_18007A3E6
0x18007a3c9  xor     r8d, r8d; unsigned __int64 *
0x18007a3cc  or      edx, 0FFFFFFFFh; int
0x18007a3cf  mov     rcx, rdi; struct lua_State *
0x18007a3d2  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18007a3d7  mov     rdx, rax
0x18007a3da  lea     rcx, [rsp+520h+lpProcName]
0x18007a3df  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator=(char const * const)
0x18007a3e4  jmp     short loc_18007A41A
0x18007a3e6  lea     rcx, [rsp+520h+Buf1]
0x18007a3eb  cmp     r15, 0Fh
0x18007a3ef  cmova   rcx, r14; Buf1
0x18007a3f3  cmp     rbx, 8
0x18007a3f7  jnz     short loc_18007A41A
0x18007a3f9  mov     r8, rbx; Size
0x18007a3fc  lea     rdx, aResType; "res_type"
0x18007a403  call    memcmp_0
0x18007a408  test    eax, eax
0x18007a40a  jnz     short loc_18007A41A
0x18007a40c  or      edx, 0FFFFFFFFh; int
0x18007a40f  mov     rcx, rdi; struct lua_State *
0x18007a412  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007a417  mov     rsi, rax
0x18007a41a  mov     edx, 0FFFFFFFEh; int
0x18007a41f  mov     rcx, rdi; struct lua_State *
0x18007a422  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x18007a427  nop
0x18007a428  lea     rcx, [rsp+520h+Buf1]
0x18007a42d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18007a432  mov     edx, 1; int
0x18007a437  mov     rcx, rdi; struct lua_State *
0x18007a43a  call    ?lua_next@@YAHPEAUlua_State@@H@Z; lua_next(lua_State *,int)
0x18007a43f  test    eax, eax
0x18007a441  jnz     loc_18007A295
0x18007a447  lea     rdx, [rsp+520h+lpProcName]
0x18007a44c  cmp     [rbp+420h+var_490], 0Fh
0x18007a451  cmova   rdx, [rsp+520h+lpProcName]; lpProcName
0x18007a457  mov     rcx, r12; hModule
0x18007a45a  call    cs:__imp_GetProcAddress
0x18007a460  mov     r15, rax
0x18007a463  test    rax, rax
0x18007a466  jnz     short loc_18007A476
0x18007a468  call    cs:__imp_GetLastError
0x18007a46e  test    eax, eax
0x18007a470  jnz     loc_18007A800
0x18007a476  xorps   xmm0, xmm0
0x18007a479  movdqu  [rsp+520h+var_4E8], xmm0
0x18007a47f  mov     [rsp+520h+var_4D8], r13
0x18007a484  mov     r14d, 2
0x18007a48a  mov     rcx, rdi; struct lua_State *
0x18007a48d  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18007a492  cmp     eax, r14d
0x18007a495  jl      loc_18007A687
0x18007a49b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18007a49f  mov     edx, r14d; int
0x18007a4a2  mov     rcx, rdi; struct lua_State *
0x18007a4a5  call    ?lua_isinteger@@YAHPEAUlua_State@@H@Z; lua_isinteger(lua_State *,int)
0x18007a4aa  mov     edx, r14d; int
0x18007a4ad  mov     rcx, rdi; struct lua_State *
0x18007a4b0  test    eax, eax
0x18007a4b2  jz      short loc_18007A4DC
0x18007a4b4  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007a4b9  mov     [rsp+520h+hKey], rax
0x18007a4be  mov     rdx, qword ptr [rsp+520h+var_4E8+8]
0x18007a4c3  cmp     rdx, [rsp+520h+var_4D8]
0x18007a4c8  jz      loc_18007A652
0x18007a4ce  mov     [rdx], rax
0x18007a4d1  add     qword ptr [rsp+520h+var_4E8+8], 8
0x18007a4d7  jmp     loc_18007A673
0x18007a4dc  lea     r8, aNativeBuffer; "native.buffer"
0x18007a4e3  call    ?luaL_testudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_testudata(lua_State *,int,char const *)
0x18007a4e8  test    rax, rax
0x18007a4eb  jz      short loc_18007A4F2
0x18007a4ed  mov     rax, [rax]
0x18007a4f0  jmp     short loc_18007A4B9
0x18007a4f2  lea     r8, aNativeResource_0; "native.resource"
0x18007a4f9  mov     edx, r14d; int
0x18007a4fc  mov     rcx, rdi; struct lua_State *
0x18007a4ff  call    ?luaL_testudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_testudata(lua_State *,int,char const *)
0x18007a504  mov     rbx, rax
0x18007a507  test    rax, rax
0x18007a50a  jz      loc_18007A630
0x18007a510  movsx   rdx, byte ptr [rax+8]
0x18007a515  add     rdx, 1
0x18007a519  mov     rax, rdx
0x18007a51c  jz      loc_18007A7FA
0x18007a522  sub     rax, 1
0x18007a526  mov     rcx, [rbx]; hObject
0x18007a529  jz      short loc_18007A53B
0x18007a52b  sub     rax, 1
0x18007a52f  jz      short loc_18007A581
0x18007a531  sub     rax, 1
0x18007a535  jz      short loc_18007A53B
0x18007a537  sub     rax, 1
0x18007a53b  test    rcx, rcx
0x18007a53e  setnz   al
0x18007a541  test    al, al
0x18007a543  jz      short loc_18007A586
0x18007a545  test    rdx, rdx
0x18007a548  jz      loc_18007A874
0x18007a54e  sub     rdx, 1
0x18007a552  jz      short loc_18007A564
0x18007a554  sub     rdx, 1
0x18007a558  jz      short loc_18007A564
0x18007a55a  sub     rdx, 1
0x18007a55e  jz      short loc_18007A564
0x18007a560  sub     rdx, 1
0x18007a564  mov     [rsp+520h+hKey], rcx
0x18007a569  mov     rdx, qword ptr [rsp+520h+var_4E8+8]
0x18007a56e  cmp     rdx, [rsp+520h+var_4D8]
0x18007a573  jz      loc_18007A652
0x18007a579  mov     [rdx], rcx
0x18007a57c  jmp     loc_18007A4D1
0x18007a581  cmp     rcx, r12
0x18007a584  jmp     short loc_18007A53E
0x18007a586  test    rdx, rdx
0x18007a589  jz      loc_18007A87A
0x18007a58f  sub     rdx, 1
0x18007a593  jz      short loc_18007A600
0x18007a595  sub     rdx, 1
0x18007a599  jz      short loc_18007A5ED
0x18007a59b  sub     rdx, 1
0x18007a59f  jz      short loc_18007A5DD
0x18007a5a1  sub     rdx, 1
0x18007a5a5  jz      short loc_18007A5CD
0x18007a5a7  cmp     rdx, 1
0x18007a5ab  jz      short loc_18007A5BD
0x18007a5ad  test    rcx, rcx
0x18007a5b0  jz      short loc_18007A60E
0x18007a5b2  mov     [rbx], r13
0x18007a5b5  call    cs:__imp_RegCloseKey
0x18007a5bb  jmp     short loc_18007A60E
0x18007a5bd  test    rcx, rcx
0x18007a5c0  jz      short loc_18007A60E
0x18007a5c2  mov     [rbx], r13
0x18007a5c5  call    cs:__imp_LocalFree
0x18007a5cb  jmp     short loc_18007A60E
0x18007a5cd  test    rcx, rcx
0x18007a5d0  jz      short loc_18007A60E
0x18007a5d2  mov     [rbx], r13
0x18007a5d5  call    cs:__imp_CloseServiceHandle
0x18007a5db  jmp     short loc_18007A60E
0x18007a5dd  test    rcx, rcx
0x18007a5e0  jz      short loc_18007A60E
0x18007a5e2  mov     [rbx], r13
0x18007a5e5  call    cs:__imp_FreeLibrary
0x18007a5eb  jmp     short loc_18007A60E
0x18007a5ed  cmp     rcx, r12
0x18007a5f0  jz      short loc_18007A5FB
0x18007a5f2  mov     [rbx], r12
0x18007a5f5  call    cs:__imp_CloseHandle
0x18007a5fb  mov     rax, r12
0x18007a5fe  jmp     short loc_18007A611
0x18007a600  test    rcx, rcx
0x18007a603  jz      short loc_18007A60E
0x18007a605  mov     [rbx], r13
0x18007a608  call    cs:__imp_CloseHandle
0x18007a60e  mov     rax, r13
0x18007a611  mov     rcx, rbx
0x18007a614  mov     [rbx], rax
0x18007a617  mov     [rsp+520h+hKey], rbx
0x18007a61c  mov     rdx, qword ptr [rsp+520h+var_4E8+8]
0x18007a621  cmp     rdx, [rsp+520h+var_4D8]
0x18007a626  jz      short loc_18007A652
0x18007a628  mov     [rdx], rbx
0x18007a62b  jmp     loc_18007A4D1
0x18007a630  mov     edx, r14d; int
0x18007a633  mov     rcx, rdi; struct lua_State *
0x18007a636  call    ?lua_isstring@@YAHPEAUlua_State@@H@Z; lua_isstring(lua_State *,int)
0x18007a63b  mov     rcx, rdi; struct lua_State *
0x18007a63e  test    eax, eax
0x18007a640  jz      short loc_18007A663
0x18007a642  xor     r8d, r8d; unsigned __int64 *
0x18007a645  mov     edx, r14d; int
0x18007a648  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18007a64d  jmp     loc_18007A4B9
0x18007a652  lea     r8, [rsp+520h+hKey]
0x18007a657  lea     rcx, [rsp+520h+var_4E8]
0x18007a65c  call    ??$_Emplace_reallocate@_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_K$$QEA_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64>(unsigned __int64 * const,unsigned __int64 &&)
0x18007a661  jmp     short loc_18007A673
0x18007a663  lea     r8d, [r14-2]
0x18007a667  lea     rdx, aUnexpectedNati; "unexpected native argument (%d)"
0x18007a66e  call    ?luaL_error@@YAHPEAUlua_State@@PEBDZZ; luaL_error(lua_State *,char const *,...)
0x18007a673  inc     r14d
0x18007a676  mov     rcx, rdi; struct lua_State *
0x18007a679  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18007a67e  cmp     r14d, eax
0x18007a681  jle     loc_18007A49F
0x18007a687  xor     ecx, ecx; dwErrCode
0x18007a689  call    cs:__imp_SetLastError
0x18007a68f  mov     r8, qword ptr [rsp+520h+var_4E8]
  ... truncated ...
```
