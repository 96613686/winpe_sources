# _anonymous_namespace_::file_grep_init

- ea: `0x1800699f0`
- end: `0x180069daa`
- name: `_anonymous_namespace_::file_grep_init`
- size: `954`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops`

## callees

- `0x180004510`
- `0x1800048e0`
- `0x18000491c`
- `0x180006600`
- `0x180006690`
- `0x180006b00`
- `0x180006c70`
- `0x180007490`
- `0x180007650`
- `0x180008430`
- `0x180008660`
- `0x180041564`
- `0x1800416a0`
- `0x18005f8c8`
- `0x1800611cc`
- `0x18006170c`
- `0x180061808`
- `0x180061c24`
- `0x180062334`
- `0x1800623a4`
- `0x180062948`
- `0x18006635c`
- `0x1800699f0`
- `0x18009d010`

## import_xrefs

- `msvcp_win!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180069bf9`
- `msvcp_win!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180069bf9`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x180069b24`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x180069bae`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x180069b24`
- `msvcp_win!?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ` at `0x180069bae`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x180069b7c`
- `msvcp_win!?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ` at `0x180069b7c`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z` at `0x180069b51`
- `msvcp_win!?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z` at `0x180069b51`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180069b05`
- `msvcp_win!??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180069b05`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180069c19`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x180069c19`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180069ab8`
- `msvcp_win!??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ` at `0x180069ab8`
- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180069d6a`
- `msvcp_win!??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180069d6a`
- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x180069c30`
- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x180069c30`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180069d74`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180069d74`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x180069ad1`
- `msvcp_win!??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z` at `0x180069ad1`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x180069b91`
- `msvcp_win!?always_noconv@codecvt_base@std@@QEBA_NXZ` at `0x180069b91`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall anonymous_namespace_::file_grep_init(struct lua_State *a1)
{
  const char *v2; // rbx
  const CHAR *v3; // rsi
  bool v4; // di
  bool v5; // r12
  struct _iobuf *v6; // rax
  __int64 v7; // rax
  std::codecvt_base *v8; // rbx
  void (__fastcall ***v9)(_QWORD, __int64); // rax
  bool v10; // al
  int v11; // r15d
  __int64 v12; // rax
  void **v13; // rsi
  char *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 v18; // rax
  void *v19; // rbx
  int v21; // [rsp+2Ch] [rbp-D4h]
  _QWORD v22[3]; // [rsp+30h] [rbp-D0h] BYREF
  void **v23; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v24[96]; // [rsp+50h] [rbp-B0h] BYREF
  std::codecvt_base *v25; // [rsp+B0h] [rbp-50h]
  char v26; // [rsp+B9h] [rbp-47h]
  __int64 v27; // [rsp+BCh] [rbp-44h]
  char v28; // [rsp+C4h] [rbp-3Ch]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  _BYTE v30[104]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v31[40]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v32[40]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v33[280]; // [rsp+1A0h] [rbp+A0h] BYREF
  char *v34; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v35; // [rsp+2C0h] [rbp+1C0h]

  v2 = luaL_checklstring(a1, 1, 0);
  v3 = luaL_checklstring(a1, 2, 0);
  v4 = (int)lua_gettop(a1) > 2 && lua_toboolean(a1, 3);
  v5 = (int)lua_gettop(a1) > 3 && lua_toboolean(a1, 4);
  v22[0] = &std::fstream::`vbtable'{for `std::istream'};
  v22[2] = &std::fstream::`vbtable'{for `std::ostream'};
  std::ios::ios(v30);
  std::iostream::basic_iostream<char>(v22, &v23, 0);
  *(_QWORD *)((char *)v22 + *(int *)(v22[0] + 4LL)) = &std::fstream::`vftable';
  *(int *)((char *)&v21 + *(int *)(v22[0] + 4LL)) = *(_DWORD *)(v22[0] + 4LL) - 184;
  std::streambuf::streambuf(&v23);
  v23 = &std::filebuf::`vftable';
  v28 = 0;
  v26 = 0;
  std::streambuf::_Init(&v23);
  v29 = 0;
  v27 = `std::filebuf::_Init'::`2'::_Stinit;
  v25 = 0;
  v6 = std::_Fiopen(v2, 33, 64);
  if ( v6 )
  {
    std::filebuf::_Init(&v23, v6, 1);
    v7 = std::streambuf::getloc(&v23, &v34);
    v8 = (std::codecvt_base *)std::use_facet<std::codecvt<char,char,_Mbstatet>>(v7);
    if ( std::codecvt_base::always_noconv(v8) )
    {
      v25 = 0;
    }
    else
    {
      v25 = v8;
      std::streambuf::_Init(&v23);
    }
    if ( v35 )
    {
      v9 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      if ( v9 )
        (**v9)(v9, 1);
    }
    std::ios::clear((char *)v22 + *(int *)(v22[0] + 4LL), 0, 0);
  }
  else
  {
    std::ios::setstate((char *)v22 + *(int *)(v22[0] + 4LL), 2);
  }
  v10 = std::ios_base::good((std::ios_base *)((char *)v22 + *(int *)(v22[0] + 4LL)));
  v11 = v10;
  if ( v10 )
  {
    v12 = windiag::char_to_wstring((__int64)&v34, v3);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
      v31,
      v12,
      ((unsigned __int8)v4 << 8) + 16);
    std::wstring::~wstring(&v34);
    lua_pushlightuserdata(a1, byte_1800BEAD8);
    lua_gettable(a1, 4293966296LL);
    v13 = (void **)luaL_checkudata(a1, -1, "file.state");
    lua_settop(a1, -2);
    v14 = (char *)operator new(0x378u);
    v34 = v14;
    v15 = std::fstream::fstream(v33, v22);
    v16 = std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
            v32,
            v31);
    LOBYTE(v17) = v5;
    v18 = anonymous_namespace_::grep_state::grep_state(v14, v16, v15, v17);
    v19 = *v13;
    *v13 = (void *)v18;
    if ( v19 )
    {
      anonymous_namespace_::grep_state::_grep_state(v19);
      operator delete(v19);
    }
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v31);
  }
  lua_pushboolean(a1, v11);
  *(_QWORD *)((char *)v22 + *(int *)(v22[0] + 4LL)) = &std::fstream::`vftable';
  *(int *)((char *)&v21 + *(int *)(v22[0] + 4LL)) = *(_DWORD *)(v22[0] + 4LL) - 184;
  std::filebuf::~filebuf<char,std::char_traits<char>>(&v23);
  std::iostream::~basic_iostream<char,std::char_traits<char>>(v24);
  std::ios::~ios<char,std::char_traits<char>>(v30);
  return 1;
}

```

## disassembly

```asm
0x1800699f0  mov     [rsp-8+arg_8], rbx
0x1800699f5  mov     [rsp-8+arg_10], rsi
0x1800699fa  push    rbp
0x1800699fb  push    rdi
0x1800699fc  push    r12
0x1800699fe  push    r14
0x180069a00  push    r15
0x180069a02  lea     rbp, [rsp-1E0h]
0x180069a0a  sub     rsp, 2E0h
0x180069a11  mov     rax, cs:__security_cookie
0x180069a18  xor     rax, rsp
0x180069a1b  mov     [rbp+200h+var_28], rax
0x180069a22  mov     r14, rcx
0x180069a25  mov     [rsp+300h+var_2E0], 0
0x180069a2d  xor     r8d, r8d; unsigned __int64 *
0x180069a30  lea     r15d, [r8+1]
0x180069a34  mov     edx, r15d; int
0x180069a37  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x180069a3c  mov     rbx, rax
0x180069a3f  xor     r8d, r8d; unsigned __int64 *
0x180069a42  lea     edx, [r15+1]; int
0x180069a46  mov     rcx, r14; struct lua_State *
0x180069a49  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x180069a4e  mov     rsi, rax
0x180069a51  mov     rcx, r14; struct lua_State *
0x180069a54  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x180069a59  cmp     eax, 2
0x180069a5c  jle     short loc_180069A73
0x180069a5e  lea     edx, [r15+2]; int
0x180069a62  mov     rcx, r14; struct lua_State *
0x180069a65  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180069a6a  test    eax, eax
0x180069a6c  jz      short loc_180069A73
0x180069a6e  mov     dil, r15b
0x180069a71  jmp     short loc_180069A76
0x180069a73  xor     dil, dil
0x180069a76  mov     rcx, r14; struct lua_State *
0x180069a79  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x180069a7e  cmp     eax, 3
0x180069a81  jle     short loc_180069A99
0x180069a83  mov     edx, 4; int
0x180069a88  mov     rcx, r14; struct lua_State *
0x180069a8b  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180069a90  test    eax, eax
0x180069a92  jz      short loc_180069A99
0x180069a94  mov     r12b, r15b
0x180069a97  jmp     short loc_180069A9C
0x180069a99  xor     r12b, r12b
0x180069a9c  lea     rax, ??_8?$basic_fstream@DU?$char_traits@D@std@@@std@@7B?$basic_istream@DU?$char_traits@D@std@@@1@@; const std::fstream::`vbtable'{for `std::istream'}
0x180069aa3  mov     [rsp+300h+var_2D0], rax
0x180069aa8  lea     rax, ??_8?$basic_fstream@DU?$char_traits@D@std@@@std@@7B?$basic_ostream@DU?$char_traits@D@std@@@1@@; const std::fstream::`vbtable'{for `std::ostream'}
0x180069aaf  mov     [rsp+300h+var_2C0], rax
0x180069ab4  lea     rcx, [rbp+200h+var_218]
0x180069ab8  call    cs:__imp_??0?$basic_ios@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::ios::ios(void)
0x180069abe  nop
0x180069abf  mov     [rsp+300h+var_2E0], r15d
0x180069ac4  xor     r8d, r8d
0x180069ac7  lea     rdx, [rsp+300h+var_2B8]
0x180069acc  lea     rcx, [rsp+300h+var_2D0]
0x180069ad1  call    cs:__imp_??0?$basic_iostream@DU?$char_traits@D@std@@@std@@QEAA@PEAV?$basic_streambuf@DU?$char_traits@D@std@@@1@@Z; std::iostream::basic_iostream<char>(std::streambuf *)
0x180069ad7  nop
0x180069ad8  mov     rax, [rsp+300h+var_2D0]
0x180069add  movsxd  rcx, dword ptr [rax+4]
0x180069ae1  lea     rax, ??_7?$basic_fstream@DU?$char_traits@D@std@@@std@@6B@; const std::fstream::`vftable'
0x180069ae8  mov     [rsp+rcx+300h+var_2D0], rax
0x180069aed  mov     rax, [rsp+300h+var_2D0]
0x180069af2  movsxd  rcx, dword ptr [rax+4]
0x180069af6  lea     edx, [rcx-0B8h]
0x180069afc  mov     [rsp+rcx+300h+var_2D4], edx
0x180069b00  lea     rcx, [rsp+300h+var_2B8]
0x180069b05  call    cs:__imp_??0?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAA@XZ; std::streambuf::streambuf(void)
0x180069b0b  lea     rax, ??_7?$basic_filebuf@DU?$char_traits@D@std@@@std@@6B@; const std::filebuf::`vftable'
0x180069b12  mov     [rsp+300h+var_2B8], rax
0x180069b17  mov     [rbp+200h+var_23C], 0
0x180069b1b  mov     [rbp+200h+var_247], 0
0x180069b1f  lea     rcx, [rsp+300h+var_2B8]
0x180069b24  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x180069b2a  mov     [rbp+200h+var_238], 0
0x180069b32  mov     rax, cs:?_Stinit@?1??_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@23@@Z@4U_Mbstatet@@A; _Mbstatet `std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)'::`2'::_Stinit
0x180069b39  mov     [rbp+200h+var_244], rax
0x180069b3d  mov     [rbp+200h+var_250], 0
0x180069b45  mov     edx, 21h ; '!'
0x180069b4a  lea     r8d, [rdx+1Fh]
0x180069b4e  mov     rcx, rbx
0x180069b51  call    cs:__imp_?_Fiopen@std@@YAPEAU_iobuf@@PEBDHH@Z; std::_Fiopen(char const *,int,int)
0x180069b57  test    rax, rax
0x180069b5a  jz      loc_180069C01
0x180069b60  mov     r8d, r15d
0x180069b63  mov     rdx, rax
0x180069b66  lea     rcx, [rsp+300h+var_2B8]
0x180069b6b  call    ?_Init@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAAXPEAU_iobuf@@W4_Initfl@12@@Z; std::filebuf::_Init(_iobuf *,std::filebuf::_Initfl)
0x180069b70  lea     rdx, [rbp+200h+var_48]
0x180069b77  lea     rcx, [rsp+300h+var_2B8]
0x180069b7c  call    cs:__imp_?getloc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@QEBA?AVlocale@2@XZ; std::streambuf::getloc(void)
0x180069b82  nop
0x180069b83  mov     rcx, rax
0x180069b86  call    ??$use_facet@V?$codecvt@DDU_Mbstatet@@@std@@@std@@YAAEBV?$codecvt@DDU_Mbstatet@@@0@AEBVlocale@0@@Z; std::use_facet<std::codecvt<char,char,_Mbstatet>>(std::locale const &)
0x180069b8b  mov     rbx, rax
0x180069b8e  mov     rcx, rax
0x180069b91  call    cs:__imp_?always_noconv@codecvt_base@std@@QEBA_NXZ; std::codecvt_base::always_noconv(void)
0x180069b97  test    al, al
0x180069b99  jz      short loc_180069BA5
0x180069b9b  mov     [rbp+200h+var_250], 0
0x180069ba3  jmp     short loc_180069BB5
0x180069ba5  mov     [rbp+200h+var_250], rbx
0x180069ba9  lea     rcx, [rsp+300h+var_2B8]
0x180069bae  call    cs:__imp_?_Init@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXXZ; std::streambuf::_Init(void)
0x180069bb4  nop
0x180069bb5  mov     rcx, [rbp+200h+var_40]
0x180069bbc  test    rcx, rcx
0x180069bbf  jz      short loc_180069BE3
0x180069bc1  mov     rax, [rcx]
0x180069bc4  mov     rax, [rax+10h]
0x180069bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069bcd  mov     rcx, rax
0x180069bd0  test    rax, rax
0x180069bd3  jz      short loc_180069BE3
0x180069bd5  mov     rax, [rax]
0x180069bd8  mov     edx, r15d
0x180069bdb  mov     rax, [rax]
0x180069bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069be3  mov     rax, [rsp+300h+var_2D0]
0x180069be8  movsxd  rcx, dword ptr [rax+4]
0x180069bec  lea     rax, [rsp+300h+var_2D0]
0x180069bf1  add     rcx, rax
0x180069bf4  xor     r8d, r8d
0x180069bf7  xor     edx, edx
0x180069bf9  call    cs:__imp_?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::clear(int,bool)
0x180069bff  jmp     short loc_180069C1F
0x180069c01  mov     rax, [rsp+300h+var_2D0]
0x180069c06  movsxd  rcx, dword ptr [rax+4]
0x180069c0a  lea     rax, [rsp+300h+var_2D0]
0x180069c0f  add     rcx, rax
0x180069c12  xor     r8d, r8d
0x180069c15  lea     edx, [r8+2]
0x180069c19  call    cs:__imp_?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z; std::ios::setstate(int,bool)
0x180069c1f  mov     rax, [rsp+300h+var_2D0]
0x180069c24  movsxd  rcx, dword ptr [rax+4]
0x180069c28  lea     rax, [rsp+300h+var_2D0]
0x180069c2d  add     rcx, rax
0x180069c30  call    cs:__imp_?good@ios_base@std@@QEBA_NXZ; std::ios_base::good(void)
0x180069c36  movzx   r15d, al
0x180069c3a  test    al, al
0x180069c3c  jz      loc_180069D25
0x180069c42  movzx   ebx, dil
0x180069c46  shl     ebx, 8
0x180069c49  mov     rdx, rsi
0x180069c4c  lea     rcx, [rbp+200h+var_48]
0x180069c53  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180069c58  nop
0x180069c59  lea     r8d, [rbx+10h]
0x180069c5d  mov     rdx, rax
0x180069c60  lea     rcx, [rbp+200h+var_1B0]
0x180069c64  call    ??$?0U?$char_traits@G@std@@V?$allocator@G@1@@?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@W4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(std::wstring const &,std::regex_constants::syntax_option_type)
0x180069c69  nop
0x180069c6a  lea     rcx, [rbp+200h+var_48]
0x180069c71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069c76  lea     rdx, byte_1800BEAD8; void *
0x180069c7d  mov     rcx, r14; struct lua_State *
0x180069c80  call    ?lua_pushlightuserdata@@YAXPEAUlua_State@@PEAX@Z; lua_pushlightuserdata(lua_State *,void *)
0x180069c85  mov     edx, 0FFF0B9D8h; int
0x180069c8a  mov     rcx, r14; struct lua_State *
0x180069c8d  call    ?lua_gettable@@YAHPEAUlua_State@@H@Z; lua_gettable(lua_State *,int)
0x180069c92  lea     r8, aFileState; "file.state"
0x180069c99  or      edx, 0FFFFFFFFh; int
0x180069c9c  mov     rcx, r14; struct lua_State *
0x180069c9f  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x180069ca4  mov     rsi, rax
0x180069ca7  mov     edx, 0FFFFFFFEh; int
0x180069cac  mov     rcx, r14; struct lua_State *
0x180069caf  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180069cb4  mov     ecx, 378h; Size
0x180069cb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069cbe  mov     rdi, rax
0x180069cc1  mov     [rbp+200h+var_48], rax
0x180069cc8  lea     rdx, [rsp+300h+var_2D0]
0x180069ccd  lea     rcx, [rbp+200h+var_160]
0x180069cd4  call    ??0?$basic_fstream@DU?$char_traits@D@std@@@std@@QEAA@$$QEAV01@@Z; std::fstream::fstream(std::fstream &&)
0x180069cd9  mov     rbx, rax
0x180069cdc  lea     rdx, [rbp+200h+var_1B0]
0x180069ce0  lea     rcx, [rbp+200h+var_188]
0x180069ce4  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@$$QEAV01@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(std::basic_regex<ushort,std::regex_traits<ushort>> &&)
0x180069ce9  mov     r9b, r12b
0x180069cec  mov     r8, rbx
0x180069cef  mov     rdx, rax
0x180069cf2  mov     rcx, rdi
0x180069cf5  call    _anonymous_namespace___grep_state__grep_state
0x180069cfa  nop
0x180069cfb  mov     rbx, [rsi]
0x180069cfe  mov     [rsi], rax
0x180069d01  test    rbx, rbx
0x180069d04  jz      short loc_180069D1C
0x180069d06  mov     rcx, rbx
0x180069d09  call    _anonymous_namespace___grep_state___grep_state
0x180069d0e  mov     edx, 378h
0x180069d13  mov     rcx, rbx; Block
0x180069d16  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180069d1b  nop
0x180069d1c  lea     rcx, [rbp+200h+var_1B0]
0x180069d20  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180069d25  mov     edx, r15d; int
0x180069d28  mov     rcx, r14; struct lua_State *
0x180069d2b  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x180069d30  nop
0x180069d31  mov     rcx, [rsp+300h+var_2D0]
0x180069d36  movsxd  rdx, dword ptr [rcx+4]
0x180069d3a  lea     rax, ??_7?$basic_fstream@DU?$char_traits@D@std@@@std@@6B@; const std::fstream::`vftable'
0x180069d41  mov     [rsp+rdx+300h+var_2D0], rax
0x180069d46  mov     rcx, [rsp+300h+var_2D0]
0x180069d4b  movsxd  rdx, dword ptr [rcx+4]
0x180069d4f  lea     r8d, [rdx-0B8h]
0x180069d56  mov     [rsp+rdx+300h+var_2D4], r8d
0x180069d5b  lea     rcx, [rsp+300h+var_2B8]
0x180069d60  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x180069d65  lea     rcx, [rsp+300h+var_2B0]
0x180069d6a  call    cs:__imp_??1?$basic_iostream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::iostream::~basic_iostream<char,std::char_traits<char>>(void)
0x180069d70  lea     rcx, [rbp+200h+var_218]
0x180069d74  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x180069d7a  mov     eax, 1
0x180069d7f  mov     rcx, [rbp+200h+var_28]
0x180069d86  xor     rcx, rsp; StackCookie
0x180069d89  call    __security_check_cookie
0x180069d8e  lea     r11, [rsp+300h+var_20]
0x180069d96  mov     rbx, [r11+38h]
0x180069d9a  mov     rsi, [r11+40h]
0x180069d9e  mov     rsp, r11
0x180069da1  pop     r15
0x180069da3  pop     r14
0x180069da5  pop     r12
0x180069da7  pop     rdi
0x180069da8  pop     rbp
0x180069da9  retn
```
