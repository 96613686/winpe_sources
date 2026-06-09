# _anonymous_namespace_::reg_set_or_delete_value

- ea: `0x18007fe90`
- end: `0x18008065f`
- name: `_anonymous_namespace_::reg_set_or_delete_value`
- size: `1999`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, installer_update`

## callers

- `0x18007e7e0`
- `0x18007e800`

## callees

- `0x180004510`
- `0x180005508`
- `0x180005520`
- `0x180006690`
- `0x180006b00`
- `0x180006f10`
- `0x180007490`
- `0x180007650`
- `0x180007950`
- `0x1800081b0`
- `0x1800083a0`
- `0x180008430`
- `0x180008610`
- `0x180008790`
- `0x18003af08`
- `0x180041564`
- `0x1800416a0`
- `0x1800431c0`
- `0x180048c8c`
- `0x180049674`
- `0x18004a1b4`
- `0x18006c450`
- `0x18006ca44`
- `0x18006dc58`
- `0x18007ebc8`
- `0x18007fe90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800803eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800803eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080412`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080548`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080412`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080548`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18008047a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18008047a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180080521`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180080521`

## string_xrefs

- `0x1800805f4`: `reg_set_or_delete_value`
- `0x18008062f`: `reg_set_or_delete_value`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::reg_set_or_delete_value(struct lua_State *a1, char a2)
{
  char v2; // r14
  HKEY v4; // r15
  const CHAR *v5; // rax
  const CHAR *v6; // rax
  __int64 v7; // rax
  const WCHAR *v8; // rbx
  bool v9; // r13
  unsigned __int64 cbData; // rsi
  DWORD v11; // r12d
  __int64 v12; // rdx
  const char *v13; // r15
  size_t v14; // r14
  char *v15; // rbx
  void *v16; // rdx
  BYTE *v17; // rcx
  BYTE *v18; // rax
  int v19; // ebx
  __int64 i; // r8
  char v21; // al
  const CHAR *v22; // rax
  char **v23; // r8
  const CHAR *v24; // rax
  __int64 v25; // rbx
  const WCHAR *v26; // rdx
  LSTATUS v27; // eax
  HKEY v28; // rcx
  LSTATUS v30; // eax
  const BYTE *v31; // rcx
  int v32; // edx
  HKEY v33; // rcx
  char v34[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE *lpData[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *v37; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v38; // [rsp+58h] [rbp-A8h]
  char v39; // [rsp+60h] [rbp-A0h]
  char v40; // [rsp+68h] [rbp-98h]
  void *v41[2]; // [rsp+70h] [rbp-90h] BYREF
  void *v42; // [rsp+80h] [rbp-80h]
  LPCWSTR lpValueName; // [rsp+88h] [rbp-78h]
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h] BYREF
  HKEY v46; // [rsp+A0h] [rbp-60h]
  __int128 v47; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v48; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v49; // [rsp+C0h] [rbp-40h]
  char *v50[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v51; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v52; // [rsp+E0h] [rbp-20h]
  LPCWSTR lpSubKey[5]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+110h] [rbp+10h] BYREF

  v2 = a2;
  v34[0] = a2;
  v4 = (HKEY)luaL_checkinteger(a1, 1);
  v46 = v4;
  v5 = luaL_checklstring(a1, 2, 0);
  windiag::char_to_wstring((__int64)lpSubKey, v5);
  lpValueName = 0;
  v47 = 0;
  v48 = 0;
  v49 = 7;
  LOWORD(v47) = 0;
  if ( (int)lua_gettop(a1) > 2 && (unsigned int)lua_type(a1, 3) )
  {
    v6 = luaL_checklstring(a1, 3, 0);
    v7 = windiag::char_to_wstring((__int64)v50, v6);
    std::wstring::operator=(&v47, v7);
    std::wstring::~wstring(v50);
    v8 = (const WCHAR *)&v47;
    if ( v49 > 7 )
      v8 = (const WCHAR *)v47;
    lpValueName = v8;
  }
  v40 = 0;
  v9 = 0;
  cbData = 4;
  if ( v2 )
  {
    v11 = 0;
    if ( (int)lua_gettop(a1) <= 3 )
      goto LABEL_42;
    v12 = 4;
    goto LABEL_41;
  }
  v11 = luaL_checkinteger(a1, 4);
  if ( v11 == 1 || v11 == 2 )
  {
    v24 = luaL_checklstring(a1, 5, 0);
    v25 = windiag::char_to_wstring((__int64)v50, v24);
    *(_OWORD *)lpData = 0;
    v37 = 0;
    v38 = 0;
    lpData[0] = *(BYTE **)v25;
    lpData[1] = *(BYTE **)(v25 + 8);
    v37 = *(void **)(v25 + 16);
    v38 = *(_QWORD *)(v25 + 24);
    *(_QWORD *)(v25 + 16) = 0;
    *(_QWORD *)(v25 + 24) = 7;
    *(_WORD *)v25 = 0;
    v39 = 1;
    v40 = 1;
    std::wstring::~wstring(v50);
    goto LABEL_39;
  }
  if ( v11 == 3 )
    goto LABEL_19;
  if ( v11 != 4 )
  {
    if ( v11 != 7 )
    {
      if ( v11 != 11 )
        luaL_argerror(a1, 1, "value type not supported");
      lpData[0] = (BYTE *)luaL_checkinteger(a1, 5);
      v39 = 3;
      goto LABEL_17;
    }
LABEL_19:
    if ( (unsigned int)lua_type(a1, 5) == 4 )
    {
      Size = 0;
      v13 = luaL_checklstring(a1, 5, &Size);
      *(_OWORD *)v41 = 0;
      v42 = 0;
      v14 = Size;
      if ( Size )
      {
        std::vector<char>::_Buy_nonzero(v41, Size);
        v15 = (char *)v41[0];
        memmove_0(v41[0], v13, v14);
        v41[1] = &v15[v14];
        v45 = 0;
        std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v45);
      }
      v16 = v42;
      v42 = 0;
      v17 = (BYTE *)v41[1];
      v41[1] = 0;
      v18 = (BYTE *)v41[0];
      v41[0] = 0;
      lpData[0] = v18;
      lpData[1] = v17;
      v37 = v16;
      v39 = 0;
      v40 = 1;
      std::vector<char>::~vector<char>((char **)v41);
      v2 = v34[0];
      v4 = v46;
    }
    else
    {
      luaL_checktype(a1, 5, 5);
      *(_OWORD *)v41 = 0;
      v42 = 0;
      v19 = 2;
      for ( i = 1; ; i = v19++ )
      {
        lua_rawgeti(a1, 5, i);
        if ( !(unsigned int)lua_type(a1, 0xFFFFFFFFLL) )
          break;
        if ( v11 == 3 )
        {
          v21 = luaL_checkinteger(a1, -1);
          v34[0] = v21;
          if ( v41[1] == v42 )
            std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(v41, v41[1], v34);
          else
            *(_BYTE *)v41[1]++ = v21;
        }
        else
        {
          v22 = luaL_checklstring(a1, -1, 0);
          windiag::char_to_wstring((__int64)v50, v22);
          if ( !v51 )
            luaL_error(a1, "zero length strings in REG_MULTI_SZ are not supported");
          v23 = v50;
          if ( v52 > 7 )
            v23 = (char **)v50[0];
          std::vector<char>::_Insert_counted_range<char const *>(v41, v41[1], v23, 2 * v51);
          std::vector<char>::_Insert_counted_range<char const *>(v41, v41[1], &dword_1800BEBA4, 2);
          std::wstring::~wstring(v50);
        }
        lua_settop(a1, -2);
      }
      lua_settop(a1, -2);
      if ( v11 == 7 )
        std::vector<char>::_Insert_counted_range<char const *>(v41, v41[1], &dword_1800BEBA4, 2);
      std::optional<std::variant<std::vector<char>,std::wstring,unsigned long,__int64,std::pair<void const *,unsigned __int64>>>::emplace<std::vector<char>>(
        lpData,
        v41);
      std::vector<char>::~vector<char>((char **)v41);
    }
    goto LABEL_39;
  }
  LODWORD(lpData[0]) = luaL_checkinteger(a1, 5);
  v39 = 2;
LABEL_17:
  v40 = 1;
LABEL_39:
  if ( (int)lua_gettop(a1) <= 5 )
    goto LABEL_42;
  v12 = 6;
LABEL_41:
  v9 = lua_toboolean(a1, v12);
LABEL_42:
  hKey = 0;
  v26 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v26 = lpSubKey[0];
  v27 = RegOpenKeyExW(v4, v26, 0, 0x102u, &hKey);
  if ( v27 )
  {
    if ( v27 != 2 && v9 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v27,
        0,
        "[%s:%d] failed; ",
        "reg_set_or_delete_value",
        427);
      throw (windiag::system_exception *)pExceptionObject;
    }
    v28 = hKey;
    if ( hKey )
    {
      hKey = 0;
      RegCloseKey(v28);
    }
    hKey = 0;
    if ( v40 && v39 != -1 )
    {
      if ( v39 )
      {
        if ( v39 == 1 )
          std::wstring::~wstring((char **)lpData);
      }
      else
      {
        std::vector<char>::~vector<char>((char **)lpData);
      }
    }
    std::wstring::~wstring((char **)&v47);
    std::wstring::~wstring((char **)lpSubKey);
    return 0;
  }
  if ( v2 )
  {
    v30 = RegDeleteValueW(hKey, lpValueName);
    goto LABEL_73;
  }
  if ( v40 )
  {
    if ( v39 == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_std::pair_void_const___unsigned___int64___lambda_0f2987df398fcf62c701e32323b26f6e__std::variant_std::vector_char_std::allocator_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____unsigned_long___int64_std::pair_void_const___unsigned___int64______1_();
    if ( v39 )
    {
      switch ( v39 )
      {
        case 1:
          v31 = (const BYTE *)lpData;
          if ( v38 > 7 )
            v31 = lpData[0];
          cbData = 2LL * (_QWORD)v37;
          break;
        case 2:
          v31 = (const BYTE *)lpData;
          break;
        case 3:
          v31 = (const BYTE *)lpData;
          cbData = 8;
          break;
        default:
          v31 = lpData[0];
          cbData = (unsigned __int64)lpData[1];
          break;
      }
    }
    else
    {
      v31 = lpData[0];
      cbData = lpData[1] - lpData[0];
    }
    if ( cbData > 0xFFFFFFFF )
    {
      v30 = 534;
      goto LABEL_83;
    }
    v30 = RegSetValueExW(hKey, lpValueName, 0, v11, v31, cbData);
LABEL_73:
    if ( !v30 )
      goto LABEL_74;
LABEL_83:
    if ( v9 && (!v2 || v30 != 2) )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v30,
        0,
        "[%s:%d] failed; ",
        "reg_set_or_delete_value",
        459);
      throw (windiag::system_exception *)pExceptionObject;
    }
    v32 = 0;
    goto LABEL_75;
  }
LABEL_74:
  v32 = 1;
LABEL_75:
  lua_pushboolean(a1, v32);
  v33 = hKey;
  if ( hKey )
  {
    hKey = 0;
    RegCloseKey(v33);
  }
  hKey = 0;
  if ( v40 && v39 != -1 )
  {
    if ( v39 )
    {
      if ( v39 == 1 )
        std::wstring::~wstring((char **)lpData);
    }
    else
    {
      std::vector<char>::~vector<char>((char **)lpData);
    }
  }
  std::wstring::~wstring((char **)&v47);
  std::wstring::~wstring((char **)lpSubKey);
  return 1;
}

```

## disassembly

```asm
0x18007fe90  push    rbp
0x18007fe92  push    rbx
0x18007fe93  push    rsi
0x18007fe94  push    rdi
0x18007fe95  push    r12
0x18007fe97  push    r13
0x18007fe99  push    r14
0x18007fe9b  push    r15
0x18007fe9d  lea     rbp, [rsp-458h]
0x18007fea5  sub     rsp, 558h
0x18007feac  mov     rax, cs:__security_cookie
0x18007feb3  xor     rax, rsp
0x18007feb6  mov     [rbp+490h+var_50], rax
0x18007febd  mov     r14b, dl
0x18007fec0  mov     [rsp+590h+var_560], dl
0x18007fec4  mov     rdi, rcx
0x18007fec7  mov     edx, 1; int
0x18007fecc  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007fed1  mov     r15, rax
0x18007fed4  mov     [rbp+490h+var_4F0], rax
0x18007fed8  xor     r8d, r8d; unsigned __int64 *
0x18007fedb  lea     edx, [r8+2]; int
0x18007fedf  mov     rcx, rdi; struct lua_State *
0x18007fee2  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18007fee7  mov     rdx, rax
0x18007feea  lea     rcx, [rbp+490h+lpSubKey]
0x18007feee  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18007fef3  nop
0x18007fef4  xor     ebx, ebx
0x18007fef6  mov     [rbp+490h+lpValueName], rbx
0x18007fefa  xorps   xmm0, xmm0
0x18007fefd  movups  [rbp+490h+var_4E8], xmm0
0x18007ff01  mov     [rbp+490h+var_4D8], rbx
0x18007ff05  mov     [rbp+490h+var_4D0], 7
0x18007ff0d  mov     word ptr [rbp+490h+var_4E8], bx
0x18007ff11  mov     rcx, rdi; struct lua_State *
0x18007ff14  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18007ff19  lea     esi, [rbx+3]
0x18007ff1c  cmp     eax, 2
0x18007ff1f  jle     short loc_18007FF71
0x18007ff21  mov     edx, esi; int
0x18007ff23  mov     rcx, rdi; struct lua_State *
0x18007ff26  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18007ff2b  test    eax, eax
0x18007ff2d  jz      short loc_18007FF71
0x18007ff2f  xor     r8d, r8d; unsigned __int64 *
0x18007ff32  mov     edx, esi; int
0x18007ff34  mov     rcx, rdi; struct lua_State *
0x18007ff37  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18007ff3c  mov     rdx, rax
0x18007ff3f  lea     rcx, [rbp+490h+var_4C8]
0x18007ff43  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18007ff48  mov     rdx, rax
0x18007ff4b  lea     rcx, [rbp+490h+var_4E8]
0x18007ff4f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007ff54  lea     rcx, [rbp+490h+var_4C8]
0x18007ff58  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ff5d  lea     rbx, [rbp+490h+var_4E8]
0x18007ff61  cmp     [rbp+490h+var_4D0], 7
0x18007ff66  cmova   rbx, qword ptr [rbp+490h+var_4E8]
0x18007ff6b  mov     [rbp+490h+lpValueName], rbx
0x18007ff6f  xor     ebx, ebx
0x18007ff71  mov     [rsp+590h+var_528], bl
0x18007ff75  mov     r13b, bl
0x18007ff78  mov     esi, 4
0x18007ff7d  mov     rcx, rdi; struct lua_State *
0x18007ff80  test    r14b, r14b
0x18007ff83  jz      short loc_18007FF9D
0x18007ff85  mov     r12d, ebx
0x18007ff88  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18007ff8d  cmp     eax, 3
0x18007ff90  jle     loc_1800803C2
0x18007ff96  mov     edx, esi
0x18007ff98  jmp     loc_1800803B4
0x18007ff9d  mov     edx, esi; int
0x18007ff9f  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007ffa4  mov     r12, rax
0x18007ffa7  mov     ecx, eax
0x18007ffa9  mov     eax, 5
0x18007ffae  sub     ecx, 1
0x18007ffb1  jz      loc_1800802F1
0x18007ffb7  sub     ecx, 1
0x18007ffba  jz      loc_1800802F1
0x18007ffc0  sub     ecx, 1
0x18007ffc3  jz      loc_180080092
0x18007ffc9  sub     ecx, 1
0x18007ffcc  jz      short loc_180080045
0x18007ffce  sub     ecx, 3
0x18007ffd1  jz      loc_180080092
0x18007ffd7  cmp     ecx, esi
0x18007ffd9  mov     rcx, rdi; struct lua_State *
0x18007ffdc  jz      short loc_18007FFF2
0x18007ffde  lea     r8, aValueTypeNotSu; "value type not supported"
0x18007ffe5  lea     edx, [rax-4]; int
0x18007ffe8  call    ?luaL_argerror@@YAHPEAUlua_State@@HPEBD@Z; luaL_argerror(lua_State *,int,char const *)
0x18007ffed  jmp     loc_1800803A2
0x18007fff2  mov     edx, eax; int
0x18007fff4  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18007fff9  mov     rbx, rax
0x18007fffc  cmp     [rsp+590h+var_528], 0
0x180080001  jz      short loc_180080031
0x180080003  movsx   rcx, [rsp+590h+var_530]
0x180080009  add     rcx, 1
0x18008000d  jz      short loc_180080031
0x18008000f  sub     rcx, 1
0x180080013  jz      short loc_180080027
0x180080015  sub     rcx, 1
0x180080019  jnz     short loc_180080031
0x18008001b  lea     rcx, [rsp+590h+lpData]
0x180080020  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080025  jmp     short loc_180080031
0x180080027  lea     rcx, [rsp+590h+lpData]
0x18008002c  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180080031  mov     [rsp+590h+lpData], rbx
0x180080036  mov     [rsp+590h+var_530], 3
0x18008003b  mov     [rsp+590h+var_528], 1
0x180080040  jmp     loc_1800803A0
0x180080045  mov     edx, eax; int
0x180080047  mov     rcx, rdi; struct lua_State *
0x18008004a  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18008004f  mov     rbx, rax
0x180080052  cmp     [rsp+590h+var_528], 0
0x180080057  jz      short loc_180080087
0x180080059  movsx   rcx, [rsp+590h+var_530]
0x18008005f  add     rcx, 1
0x180080063  jz      short loc_180080087
0x180080065  sub     rcx, 1
0x180080069  jz      short loc_18008007D
0x18008006b  sub     rcx, 1
0x18008006f  jnz     short loc_180080087
0x180080071  lea     rcx, [rsp+590h+lpData]
0x180080076  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008007b  jmp     short loc_180080087
0x18008007d  lea     rcx, [rsp+590h+lpData]
0x180080082  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180080087  mov     dword ptr [rsp+590h+lpData], ebx
0x18008008b  mov     [rsp+590h+var_530], 2
0x180080090  jmp     short loc_18008003B
0x180080092  mov     edx, eax; int
0x180080094  mov     rcx, rdi; struct lua_State *
0x180080097  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18008009c  mov     rcx, rdi; struct lua_State *
0x18008009f  cmp     eax, esi
0x1800800a1  jnz     loc_18008018A
0x1800800a7  mov     [rbp+490h+Size], rbx
0x1800800ab  lea     r8, [rbp+490h+Size]; unsigned __int64 *
0x1800800af  mov     edx, 5; int
0x1800800b4  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x1800800b9  mov     r15, rax
0x1800800bc  xorps   xmm0, xmm0
0x1800800bf  movdqu  xmmword ptr [rsp+590h+var_520], xmm0
0x1800800c5  mov     [rbp+490h+var_510], rbx
0x1800800c9  mov     r14, [rbp+490h+Size]
0x1800800cd  test    r14, r14
0x1800800d0  jz      short loc_18008010A
0x1800800d2  mov     rdx, r14
0x1800800d5  lea     rcx, [rsp+590h+var_520]
0x1800800da  call    ?_Buy_nonzero@?$vector@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::vector<char>::_Buy_nonzero(unsigned __int64)
0x1800800df  mov     rbx, [rsp+590h+var_520]
0x1800800e4  mov     r8, r14; Size
0x1800800e7  mov     rdx, r15; Src
0x1800800ea  mov     rcx, rbx; void *
0x1800800ed  call    memmove_0
0x1800800f2  lea     rax, [rbx+r14]
0x1800800f6  mov     [rsp+590h+var_520+8], rax
0x1800800fb  xor     ebx, ebx
0x1800800fd  mov     [rbp+490h+var_4F8], rbx
0x180080101  lea     rcx, [rbp+490h+var_4F8]
0x180080105  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18008010a  cmp     [rsp+590h+var_528], bl
0x18008010e  jz      short loc_18008013E
0x180080110  movsx   rax, [rsp+590h+var_530]
0x180080116  add     rax, 1
0x18008011a  jz      short loc_18008013E
0x18008011c  sub     rax, 1
0x180080120  jz      short loc_180080134
0x180080122  sub     rax, 1
0x180080126  jnz     short loc_18008013E
0x180080128  lea     rcx, [rsp+590h+lpData]
0x18008012d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080132  jmp     short loc_18008013E
0x180080134  lea     rcx, [rsp+590h+lpData]
0x180080139  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18008013e  mov     rdx, [rbp+490h+var_510]
0x180080142  mov     [rbp+490h+var_510], rbx
0x180080146  mov     rcx, [rsp+590h+var_520+8]
0x18008014b  mov     [rsp+590h+var_520+8], rbx
0x180080150  mov     rax, [rsp+590h+var_520]
0x180080155  mov     [rsp+590h+var_520], rbx
0x18008015a  mov     [rsp+590h+lpData], rax
0x18008015f  mov     [rsp+590h+lpData+8], rcx
0x180080164  mov     [rsp+590h+var_540], rdx
0x180080169  mov     [rsp+590h+var_530], bl
0x18008016d  mov     [rsp+590h+var_528], 1
0x180080172  lea     rcx, [rsp+590h+var_520]
0x180080177  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18008017c  mov     r14b, [rsp+590h+var_560]
0x180080181  mov     r15, [rbp+490h+var_4F0]
0x180080185  jmp     loc_1800803A2
0x18008018a  mov     eax, 5
0x18008018f  mov     r8d, eax; int
0x180080192  mov     edx, eax; int
0x180080194  call    ?luaL_checktype@@YAXPEAUlua_State@@HH@Z; luaL_checktype(lua_State *,int,int)
0x180080199  xorps   xmm0, xmm0
0x18008019c  movdqu  xmmword ptr [rsp+590h+var_520], xmm0
0x1800801a2  mov     [rbp+490h+var_510], rbx
0x1800801a6  mov     ebx, 2
0x1800801ab  lea     r8d, [rbx-1]
0x1800801af  jmp     loc_180080286
0x1800801b4  cmp     r12d, 3
0x1800801b8  jnz     short loc_1800801F4
0x1800801ba  or      edx, 0FFFFFFFFh; int
0x1800801bd  mov     rcx, rdi; struct lua_State *
0x1800801c0  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x1800801c5  mov     [rsp+590h+var_560], al
0x1800801c9  mov     rdx, [rsp+590h+var_520+8]
0x1800801ce  cmp     rdx, [rbp+490h+var_510]
0x1800801d2  jz      short loc_1800801E0
0x1800801d4  mov     [rdx], al
0x1800801d6  inc     [rsp+590h+var_520+8]
0x1800801db  jmp     loc_180080274
0x1800801e0  lea     r8, [rsp+590h+var_560]
0x1800801e5  lea     rcx, [rsp+590h+var_520]
0x1800801ea  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x1800801ef  jmp     loc_180080274
0x1800801f4  cmp     r12d, 7
0x1800801f8  jnz     short loc_180080274
0x1800801fa  xor     r8d, r8d; unsigned __int64 *
0x1800801fd  or      edx, 0FFFFFFFFh; int
0x180080200  mov     rcx, rdi; struct lua_State *
0x180080203  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x180080208  mov     rdx, rax
0x18008020b  lea     rcx, [rbp+490h+var_4C8]
0x18008020f  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180080214  nop
0x180080215  mov     r9, [rbp+490h+var_4B8]
0x180080219  test    r9, r9
0x18008021c  jz      short loc_18008025B
0x18008021e  lea     r8, [rbp+490h+var_4C8]
0x180080222  cmp     [rbp+490h+var_4B0], 7
0x180080227  cmova   r8, [rbp+490h+var_4C8]
0x18008022c  add     r9, r9
0x18008022f  mov     rdx, [rsp+590h+var_520+8]
0x180080234  lea     rcx, [rsp+590h+var_520]
0x180080239  call    ??$_Insert_counted_range@PEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@D@std@@@std@@@1@PEBD_K@Z; std::vector<char>::_Insert_counted_range<char const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<char>>>,char const *,unsigned __int64)
0x18008023e  lea     r9d, [r12-5]
0x180080243  lea     r8, dword_1800BEBA4
0x18008024a  mov     rdx, [rsp+590h+var_520+8]
0x18008024f  lea     rcx, [rsp+590h+var_520]
0x180080254  call    ??$_Insert_counted_range@PEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@D@std@@@std@@@1@PEBD_K@Z; std::vector<char>::_Insert_counted_range<char const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<char>>>,char const *,unsigned __int64)
0x180080259  jmp     short loc_18008026B
0x18008025b  lea     rdx, aZeroLengthStri; "zero length strings in REG_MULTI_SZ are"...
0x180080262  mov     rcx, rdi; struct lua_State *
0x180080265  call    ?luaL_error@@YAHPEAUlua_State@@PEBDZZ; luaL_error(lua_State *,char const *,...)
0x18008026b  lea     rcx, [rbp+490h+var_4C8]
0x18008026f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080274  mov     edx, 0FFFFFFFEh; int
0x180080279  mov     rcx, rdi; struct lua_State *
0x18008027c  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180080281  movsxd  r8, ebx; __int64
0x180080284  inc     ebx
0x180080286  mov     edx, 5; int
0x18008028b  mov     rcx, rdi; struct lua_State *
0x18008028e  call    ?lua_rawgeti@@YAHPEAUlua_State@@H_J@Z; lua_rawgeti(lua_State *,int,__int64)
0x180080293  or      edx, 0FFFFFFFFh; int
0x180080296  mov     rcx, rdi; struct lua_State *
0x180080299  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18008029e  test    eax, eax
0x1800802a0  jnz     loc_1800801B4
0x1800802a6  lea     edx, [rax-2]; int
0x1800802a9  mov     rcx, rdi; struct lua_State *
0x1800802ac  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x1800802b1  cmp     r12d, 7
0x1800802b5  jnz     short loc_1800802D2
0x1800802b7  lea     r9d, [r12-5]
0x1800802bc  lea     r8, dword_1800BEBA4
0x1800802c3  mov     rdx, [rsp+590h+var_520+8]
0x1800802c8  lea     rcx, [rsp+590h+var_520]
0x1800802cd  call    ??$_Insert_counted_range@PEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@D@std@@@std@@@1@PEBD_K@Z; std::vector<char>::_Insert_counted_range<char const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<char>>>,char const *,unsigned __int64)
0x1800802d2  lea     rdx, [rsp+590h+var_520]
0x1800802d7  lea     rcx, [rsp+590h+lpData]
0x1800802dc  call    ??$emplace@V?$vector@DV?$allocator@D@std@@@std@@@?$optional@V?$variant@V?$vector@DV?$allocator@D@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@K_JU?$pair@PEBX_K@2@@std@@@std@@QEAAAEAV?$variant@V?$vector@DV?$allocator@D@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@K_JU?$pair@PEBX_K@2@@1@$$QEAV?$vector@DV?$allocator@D@std@@@1@@Z; std::optional<std::variant<std::vector<char>,std::wstring,ulong,__int64,std::pair<void const *,unsigned __int64>>>::emplace<std::vector<char>>(std::vector<char> &&)
0x1800802e1  nop
0x1800802e2  lea     rcx, [rsp+590h+var_520]
0x1800802e7  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800802ec  jmp     loc_1800803A0
0x1800802f1  xor     r8d, r8d; unsigned __int64 *
0x1800802f4  mov     edx, eax; int
0x1800802f6  mov     rcx, rdi; struct lua_State *
0x1800802f9  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x1800802fe  mov     rdx, rax
0x180080301  lea     rcx, [rbp+490h+var_4C8]
0x180080305  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18008030a  mov     rbx, rax
0x18008030d  xor     ecx, ecx
0x18008030f  cmp     [rsp+590h+var_528], cl
0x180080313  jz      short loc_180080349
0x180080315  movsx   rcx, [rsp+590h+var_530]
0x18008031b  add     rcx, 1
0x18008031f  jz      short loc_180080343
  ... truncated ...
```
