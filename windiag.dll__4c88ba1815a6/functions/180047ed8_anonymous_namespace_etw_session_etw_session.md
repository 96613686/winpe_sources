# _anonymous_namespace_::etw_session::etw_session

- ea: `0x180047ed8`
- end: `0x180048653`
- name: `_anonymous_namespace_::etw_session::etw_session`
- size: `1915`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops`

## callers

- `0x18004ec90`

## callees

- `0x180004510`
- `0x1800048e0`
- `0x180005508`
- `0x180006100`
- `0x180006430`
- `0x180006600`
- `0x180006690`
- `0x180006c50`
- `0x180006d40`
- `0x180006f70`
- `0x180007490`
- `0x180007650`
- `0x180007950`
- `0x1800081b0`
- `0x1800083a0`
- `0x180008430`
- `0x180008610`
- `0x18003a52c`
- `0x18003a8d0`
- `0x18003b0bc`
- `0x18003b3b0`
- `0x18003f6b8`
- `0x180043998`
- `0x180047ed8`
- `0x180049750`
- `0x18004b57c`
- `0x18004f278`

## import_xrefs

- `RPCRT4!UuidFromStringA` at `0x180048390`
- `RPCRT4!UuidFromStringA` at `0x180048390`

## string_xrefs

- `0x1800485ed`: `unable to obtain etl path for etw trace session`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall anonymous_namespace_::etw_session::etw_session(__int64 a1, struct lua_State *a2, __int64 a3)
{
  _BYTE *v5; // rbx
  bool v6; // r15
  const char *v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // r14
  unsigned int i; // ebx
  unsigned __int8 *v11; // rax
  RPC_STATUS v12; // eax
  struct lua_State *v13; // rcx
  UUID v14; // xmm6
  __int64 v15; // rdx
  __int128 *v16; // rbx
  char *v17; // rcx
  char *v18; // rax
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rax
  bool v22; // cl
  __int64 random_file_path; // rcx
  char v24; // bl
  __int16 v26; // [rsp+2Dh] [rbp-A4h]
  char v27; // [rsp+2Fh] [rbp-A2h]
  __int128 v28; // [rsp+30h] [rbp-A1h] BYREF
  _QWORD v29[3]; // [rsp+40h] [rbp-91h] BYREF
  __int64 v30; // [rsp+58h] [rbp-79h]
  __int64 v31; // [rsp+60h] [rbp-71h]
  char v32; // [rsp+68h] [rbp-69h]
  __int64 v33; // [rsp+78h] [rbp-59h]
  char *v34[4]; // [rsp+88h] [rbp-49h] BYREF
  char v35; // [rsp+A8h] [rbp-29h]
  UUID Uuid; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-11h]
  __int64 v38; // [rsp+C8h] [rbp-9h]
  char v39; // [rsp+D0h] [rbp-1h]

  v33 = a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 15;
  *(_BYTE *)a1 = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 15;
  *(_BYTE *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 72) = 0;
  *(_BYTE *)(a1 + 80) = 0;
  *(_BYTE *)(a1 + 88) = 0;
  *(_BYTE *)(a1 + 96) = 0;
  *(_BYTE *)(a1 + 104) = 0;
  *(_BYTE *)(a1 + 140) = 0;
  *(_BYTE *)(a1 + 168) = 0;
  *(_BYTE *)(a1 + 180) = 0;
  *(_BYTE *)(a1 + 184) = 0;
  if ( *(_QWORD *)(a1 + 24) < 0x1Au )
  {
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      a1,
      26,
      a3,
      "WinDiag-Default-EtwSession",
      0);
  }
  else
  {
    v5 = *(_BYTE **)a1;
    *(_QWORD *)(a1 + 16) = 26;
    memmove_0(v5, "WinDiag-Default-EtwSession", 0x1Au);
    v5[26] = 0;
  }
  *(_DWORD *)(a1 + 32) = 1;
  *(_DWORD *)(a1 + 72) = 10;
  v6 = 1;
  if ( (int)lua_gettop(a2) > 1 )
  {
    luaL_checktype(a2, 2, 5);
    lua_getfield(a2, 2, "mode");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
      *(_DWORD *)(a1 + 32) = luaL_checkinteger(a2, -1);
    lua_settop(a2, -2);
    lua_getfield(a2, 2, "name");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
    {
      v7 = luaL_checklstring(a2, -1, 0);
      std::string::operator=(a1, v7);
    }
    lua_settop(a2, -2);
    lua_getfield(a2, 2, "log_file");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
      v6 = lua_toboolean(a2, 0xFFFFFFFFLL);
    lua_settop(a2, -2);
    lua_getfield(a2, 2, "enable_provider_allow_failures");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
      *(_BYTE *)(a1 + 184) = lua_toboolean(a2, 0xFFFFFFFFLL);
    lua_settop(a2, -2);
    lua_getfield(a2, 2, "max_file_size");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
      *(_DWORD *)(a1 + 72) = luaL_checkinteger(a2, -1);
    lua_settop(a2, -2);
    lua_getfield(a2, 2, "min_buffers");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
    {
      *(_DWORD *)(a1 + 76) = luaL_checkinteger(a2, -1);
      *(_BYTE *)(a1 + 80) = 1;
      *(_WORD *)(a1 + 81) = v26;
      *(_BYTE *)(a1 + 83) = v27;
    }
    lua_settop(a2, -2);
    lua_getfield(a2, 2, "max_buffers");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
    {
      *(_DWORD *)(a1 + 84) = luaL_checkinteger(a2, -1);
      *(_BYTE *)(a1 + 88) = 1;
      *(_WORD *)(a1 + 89) = v26;
      *(_BYTE *)(a1 + 91) = v27;
    }
    lua_settop(a2, -2);
    lua_getfield(a2, 2, "buffer_size");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
    {
      *(_DWORD *)(a1 + 92) = luaL_checkinteger(a2, -1);
      *(_BYTE *)(a1 + 96) = 1;
      *(_WORD *)(a1 + 97) = v26;
      *(_BYTE *)(a1 + 99) = v27;
    }
    lua_settop(a2, -2);
    lua_getfield(a2, 2, "flush_timer");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
    {
      *(_DWORD *)(a1 + 100) = luaL_checkinteger(a2, -1);
      *(_BYTE *)(a1 + 104) = 1;
      *(_WORD *)(a1 + 105) = v26;
      *(_BYTE *)(a1 + 107) = v27;
    }
    lua_settop(a2, -2);
    v8 = anonymous_namespace_::etw_sys_flags_option(&Uuid, a2, 2);
    *(_OWORD *)(a1 + 108) = *(_OWORD *)v8;
    *(_OWORD *)(a1 + 124) = *(_OWORD *)(v8 + 16);
    *(_DWORD *)(a1 + 140) = *(_DWORD *)(v8 + 32);
    lua_getfield(a2, 2, "enable_flags");
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
    {
      *(_DWORD *)(a1 + 176) = luaL_checkinteger(a2, -1);
      if ( !*(_BYTE *)(a1 + 180) )
        *(_BYTE *)(a1 + 180) = 1;
    }
    lua_getfield(a2, 2, "sys_stacks");
    if ( !(unsigned int)lua_type(a2, 0xFFFFFFFFLL) )
      goto LABEL_50;
    if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) != 5 )
      luaL_argerror(a2, 2, "sys_stacks must be a table");
    v28 = 0;
    v29[0] = 0;
    v9 = lua_rawlen(a2, -1);
    for ( i = 1; i <= v9; ++i )
    {
      lua_pushinteger(a2, i);
      lua_gettable(a2, 4294967294LL);
      if ( (unsigned int)lua_type(a2, 0xFFFFFFFFLL) != 5 )
        luaL_argerror(a2, i, "sys_stacks values should be table");
      lua_getfield(a2, 0xFFFFFFFFLL, "guid");
      v11 = (unsigned __int8 *)luaL_checklstring(a2, -1, 0);
      Uuid = 0;
      v12 = UuidFromStringA(v11, &Uuid);
      v13 = a2;
      if ( !v12 )
      {
        lua_settop(a2, -2);
        lua_getfield(a2, 0xFFFFFFFFLL, "type");
        v14 = Uuid;
        LOBYTE(v37) = luaL_checkinteger(a2, -1);
        *(_DWORD *)((char *)&v37 + 1) = 0;
        *(_WORD *)((char *)&v37 + 5) = 0;
        HIBYTE(v37) = 0;
        v15 = *((_QWORD *)&v28 + 1);
        if ( *((_QWORD *)&v28 + 1) == v29[0] )
        {
          std::vector<_CLASSIC_EVENT_ID>::_Emplace_reallocate<_CLASSIC_EVENT_ID>(&v28, *((_QWORD *)&v28 + 1), &Uuid);
        }
        else
        {
          **((_OWORD **)&v28 + 1) = v14;
          *(_QWORD *)(v15 + 16) = v37;
          *((_QWORD *)&v28 + 1) += 24LL;
        }
        v13 = a2;
      }
      lua_settop(v13, -2);
      lua_settop(a2, -2);
    }
    v16 = (__int128 *)(a1 + 144);
    if ( *(_BYTE *)(a1 + 168) )
    {
      if ( v16 == &v28 )
      {
LABEL_49:
        std::vector<_CLASSIC_EVENT_ID>::~vector<_CLASSIC_EVENT_ID>(&v28);
LABEL_50:
        lua_settop(a2, -2);
        goto LABEL_51;
      }
      v17 = *(char **)v16;
      if ( *(_QWORD *)v16 )
      {
        if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 160) - (_QWORD)v17) >> 3)) < 0x1000 )
        {
          v18 = *(char **)v16;
        }
        else
        {
          v18 = (char *)*((_QWORD *)v17 - 1);
          if ( (unsigned __int64)(v17 - v18 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v18);
      }
      *(_QWORD *)v16 = v28;
      *(_QWORD *)(a1 + 152) = *((_QWORD *)&v28 + 1);
      *(_QWORD *)(a1 + 160) = v29[0];
      v28 = 0;
    }
    else
    {
      v19 = v29[0];
      v20 = *((_QWORD *)&v28 + 1);
      v21 = v28;
      v28 = 0u;
      *(_QWORD *)v16 = v21;
      *(_QWORD *)(a1 + 152) = v20;
      *(_QWORD *)(a1 + 160) = v19;
      *(_BYTE *)(a1 + 168) = 1;
    }
    v29[0] = 0;
    goto LABEL_49;
  }
LABEL_51:
  v22 = 0;
  if ( (*(_DWORD *)(a1 + 32) & 0x400) == 0 )
    v22 = v6;
  if ( v22 )
  {
    random_file_path = windiag::create_random_file_path((__int64)v34);
    v24 = 1;
  }
  else
  {
    Uuid = 0;
    v37 = 0;
    v38 = 0;
    std::string::_Construct<1,char const *>(&Uuid, DirectoryName, 0);
    v39 = 1;
    random_file_path = (__int64)&Uuid;
    v24 = 2;
  }
  v32 = 0;
  if ( *(_BYTE *)(random_file_path + 32) )
  {
    *(_OWORD *)&v29[1] = 0;
    v30 = 0;
    v31 = 0;
    *(_OWORD *)&v29[1] = *(_OWORD *)random_file_path;
    v30 = *(_QWORD *)(random_file_path + 16);
    v31 = *(_QWORD *)(random_file_path + 24);
    *(_QWORD *)(random_file_path + 16) = 0;
    *(_QWORD *)(random_file_path + 24) = 15;
    *(_BYTE *)random_file_path = 0;
    v32 = 1;
  }
  if ( (v24 & 2) != 0 )
  {
    v24 &= ~2u;
    if ( v39 )
      std::string::~string((char **)&Uuid);
  }
  if ( (v24 & 1) != 0 && v35 )
    std::string::~string(v34);
  if ( !v32 )
  {
    lua_pushstring(a2, "unable to obtain etl path for etw trace session");
    lua_error(a2);
  }
  std::string::operator=(a1 + 40, &v29[1]);
  if ( v32 )
    std::string::~string((char **)&v29[1]);
  return a1;
}

```

## disassembly

```asm
0x180047ed8  mov     rax, rsp
0x180047edb  mov     [rax+18h], rbx
0x180047edf  push    rbp
0x180047ee0  push    rsi
0x180047ee1  push    rdi
0x180047ee2  push    r12
0x180047ee4  push    r13
0x180047ee6  push    r14
0x180047ee8  push    r15
0x180047eea  lea     rbp, [rax-5Fh]
0x180047eee  sub     rsp, 0F0h
0x180047ef5  movaps  xmmword ptr [rax-48h], xmm6
0x180047ef9  mov     rax, cs:__security_cookie
0x180047f00  xor     rax, rsp
0x180047f03  mov     [rbp+57h+var_50], rax
0x180047f07  mov     rdi, rdx
0x180047f0a  mov     rsi, rcx
0x180047f0d  mov     [rbp+57h+var_B0], rcx
0x180047f11  xor     r12d, r12d
0x180047f14  mov     dword ptr [rsp+120h+var_100], r12d
0x180047f19  xorps   xmm0, xmm0
0x180047f1c  movups  xmmword ptr [rcx], xmm0
0x180047f1f  mov     [rcx+10h], r12
0x180047f23  lea     r13d, [r12+0Fh]
0x180047f28  mov     [rcx+18h], r13
0x180047f2c  mov     [rcx], r12b
0x180047f2f  mov     [rcx+20h], r12d
0x180047f33  movups  xmmword ptr [rcx+28h], xmm0
0x180047f37  mov     [rcx+38h], r12
0x180047f3b  mov     [rcx+40h], r13
0x180047f3f  mov     [rcx+28h], r12b
0x180047f43  mov     [rcx+48h], r12d
0x180047f47  mov     [rcx+50h], r12b
0x180047f4b  mov     [rcx+58h], r12b
0x180047f4f  mov     [rcx+60h], r12b
0x180047f53  mov     [rcx+68h], r12b
0x180047f57  mov     [rcx+8Ch], r12b
0x180047f5e  mov     [rcx+0A8h], r12b
0x180047f65  mov     [rcx+0B4h], r12b
0x180047f6c  mov     [rcx+0B8h], r12b
0x180047f73  lea     edx, [r12+1Ah]
0x180047f78  cmp     [rcx+18h], rdx
0x180047f7c  jb      short loc_180047F9D
0x180047f7e  mov     rbx, [rcx]
0x180047f81  mov     [rcx+10h], rdx
0x180047f85  mov     r8d, edx; Size
0x180047f88  lea     rdx, aWindiagDefault; "WinDiag-Default-EtwSession"
0x180047f8f  mov     rcx, rbx; void *
0x180047f92  call    memmove_0
0x180047f97  mov     [rbx+1Ah], r12b
0x180047f9b  jmp     short loc_180047FA9
0x180047f9d  lea     r9, aWindiagDefault; "WinDiag-Default-EtwSession"
0x180047fa4  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x180047fa9  mov     dword ptr [rsi+20h], 1
0x180047fb0  mov     dword ptr [rsi+48h], 0Ah
0x180047fb7  mov     r15b, 1
0x180047fba  mov     rcx, rdi; struct lua_State *
0x180047fbd  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x180047fc2  mov     r14d, 2
0x180047fc8  cmp     eax, 1
0x180047fcb  jle     loc_180048524
0x180047fd1  lea     r8d, [r14+3]; int
0x180047fd5  mov     edx, r14d; int
0x180047fd8  mov     rcx, rdi; struct lua_State *
0x180047fdb  call    ?luaL_checktype@@YAXPEAUlua_State@@HH@Z; luaL_checktype(lua_State *,int,int)
0x180047fe0  lea     r8, aMode_0; "mode"
0x180047fe7  mov     edx, r14d; int
0x180047fea  mov     rcx, rdi; struct lua_State *
0x180047fed  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x180047ff2  or      r13d, 0FFFFFFFFh
0x180047ff6  mov     edx, r13d; int
0x180047ff9  mov     rcx, rdi; struct lua_State *
0x180047ffc  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180048001  test    eax, eax
0x180048003  jz      short loc_180048013
0x180048005  mov     edx, r13d; int
0x180048008  mov     rcx, rdi; struct lua_State *
0x18004800b  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x180048010  mov     [rsi+20h], eax
0x180048013  mov     ebx, 0FFFFFFFEh
0x180048018  mov     edx, ebx; int
0x18004801a  mov     rcx, rdi; struct lua_State *
0x18004801d  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180048022  lea     r8, aName; "name"
0x180048029  mov     edx, r14d; int
0x18004802c  mov     rcx, rdi; struct lua_State *
0x18004802f  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x180048034  mov     edx, r13d; int
0x180048037  mov     rcx, rdi; struct lua_State *
0x18004803a  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18004803f  test    eax, eax
0x180048041  jz      short loc_18004805C
0x180048043  xor     r8d, r8d; unsigned __int64 *
0x180048046  mov     edx, r13d; int
0x180048049  mov     rcx, rdi; struct lua_State *
0x18004804c  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x180048051  mov     rdx, rax
0x180048054  mov     rcx, rsi
0x180048057  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator=(char const * const)
0x18004805c  mov     edx, ebx; int
0x18004805e  mov     rcx, rdi; struct lua_State *
0x180048061  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180048066  lea     r8, aLogFile; "log_file"
0x18004806d  mov     edx, r14d; int
0x180048070  mov     rcx, rdi; struct lua_State *
0x180048073  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x180048078  mov     edx, r13d; int
0x18004807b  mov     rcx, rdi; struct lua_State *
0x18004807e  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180048083  test    eax, eax
0x180048085  jz      short loc_180048098
0x180048087  mov     edx, r13d; int
0x18004808a  mov     rcx, rdi; struct lua_State *
0x18004808d  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180048092  test    eax, eax
0x180048094  setnz   r15b
0x180048098  mov     edx, ebx; int
0x18004809a  mov     rcx, rdi; struct lua_State *
0x18004809d  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x1800480a2  lea     r8, aEnableProvider; "enable_provider_allow_failures"
0x1800480a9  mov     edx, r14d; int
0x1800480ac  mov     rcx, rdi; struct lua_State *
0x1800480af  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x1800480b4  mov     edx, r13d; int
0x1800480b7  mov     rcx, rdi; struct lua_State *
0x1800480ba  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x1800480bf  test    eax, eax
0x1800480c1  jz      short loc_1800480D9
0x1800480c3  mov     edx, r13d; int
0x1800480c6  mov     rcx, rdi; struct lua_State *
0x1800480c9  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x1800480ce  test    eax, eax
0x1800480d0  setnz   al
0x1800480d3  mov     [rsi+0B8h], al
0x1800480d9  mov     edx, ebx; int
0x1800480db  mov     rcx, rdi; struct lua_State *
0x1800480de  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x1800480e3  lea     r8, aMaxFileSize; "max_file_size"
0x1800480ea  mov     edx, r14d; int
0x1800480ed  mov     rcx, rdi; struct lua_State *
0x1800480f0  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x1800480f5  mov     edx, r13d; int
0x1800480f8  mov     rcx, rdi; struct lua_State *
0x1800480fb  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180048100  test    eax, eax
0x180048102  jz      short loc_180048112
0x180048104  mov     edx, r13d; int
0x180048107  mov     rcx, rdi; struct lua_State *
0x18004810a  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18004810f  mov     [rsi+48h], eax
0x180048112  mov     edx, ebx; int
0x180048114  mov     rcx, rdi; struct lua_State *
0x180048117  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x18004811c  lea     r8, aMinBuffers; "min_buffers"
0x180048123  mov     edx, r14d; int
0x180048126  mov     rcx, rdi; struct lua_State *
0x180048129  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x18004812e  mov     edx, r13d; int
0x180048131  mov     rcx, rdi; struct lua_State *
0x180048134  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180048139  test    eax, eax
0x18004813b  jz      short loc_18004815F
0x18004813d  mov     edx, r13d; int
0x180048140  mov     rcx, rdi; struct lua_State *
0x180048143  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x180048148  mov     [rsi+4Ch], eax
0x18004814b  mov     byte ptr [rsi+50h], 1
0x18004814f  movzx   eax, word ptr [rsp+120h+var_100+5]
0x180048154  mov     [rsi+51h], ax
0x180048158  mov     al, byte ptr [rsp+120h+var_100+7]
0x18004815c  mov     [rsi+53h], al
0x18004815f  mov     edx, ebx; int
0x180048161  mov     rcx, rdi; struct lua_State *
0x180048164  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180048169  lea     r8, aMaxBuffers; "max_buffers"
0x180048170  mov     edx, r14d; int
0x180048173  mov     rcx, rdi; struct lua_State *
0x180048176  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x18004817b  mov     edx, r13d; int
0x18004817e  mov     rcx, rdi; struct lua_State *
0x180048181  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180048186  test    eax, eax
0x180048188  jz      short loc_1800481AC
0x18004818a  mov     edx, r13d; int
0x18004818d  mov     rcx, rdi; struct lua_State *
0x180048190  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x180048195  mov     [rsi+54h], eax
0x180048198  mov     byte ptr [rsi+58h], 1
0x18004819c  movzx   eax, word ptr [rsp+120h+var_100+5]
0x1800481a1  mov     [rsi+59h], ax
0x1800481a5  mov     al, byte ptr [rsp+120h+var_100+7]
0x1800481a9  mov     [rsi+5Bh], al
0x1800481ac  mov     edx, ebx; int
0x1800481ae  mov     rcx, rdi; struct lua_State *
0x1800481b1  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x1800481b6  lea     r8, aBufferSize; "buffer_size"
0x1800481bd  mov     edx, r14d; int
0x1800481c0  mov     rcx, rdi; struct lua_State *
0x1800481c3  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x1800481c8  mov     edx, r13d; int
0x1800481cb  mov     rcx, rdi; struct lua_State *
0x1800481ce  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x1800481d3  test    eax, eax
0x1800481d5  jz      short loc_1800481F9
0x1800481d7  mov     edx, r13d; int
0x1800481da  mov     rcx, rdi; struct lua_State *
0x1800481dd  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x1800481e2  mov     [rsi+5Ch], eax
0x1800481e5  mov     byte ptr [rsi+60h], 1
0x1800481e9  movzx   eax, word ptr [rsp+120h+var_100+5]
0x1800481ee  mov     [rsi+61h], ax
0x1800481f2  mov     al, byte ptr [rsp+120h+var_100+7]
0x1800481f6  mov     [rsi+63h], al
0x1800481f9  mov     edx, ebx; int
0x1800481fb  mov     rcx, rdi; struct lua_State *
0x1800481fe  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180048203  lea     r8, aFlushTimer; "flush_timer"
0x18004820a  mov     edx, r14d; int
0x18004820d  mov     rcx, rdi; struct lua_State *
0x180048210  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x180048215  mov     edx, r13d; int
0x180048218  mov     rcx, rdi; struct lua_State *
0x18004821b  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180048220  test    eax, eax
0x180048222  jz      short loc_180048246
0x180048224  mov     edx, r13d; int
0x180048227  mov     rcx, rdi; struct lua_State *
0x18004822a  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18004822f  mov     [rsi+64h], eax
0x180048232  mov     byte ptr [rsi+68h], 1
0x180048236  movzx   eax, word ptr [rsp+120h+var_100+5]
0x18004823b  mov     [rsi+69h], ax
0x18004823f  mov     al, byte ptr [rsp+120h+var_100+7]
0x180048243  mov     [rsi+6Bh], al
0x180048246  mov     edx, ebx; int
0x180048248  mov     rcx, rdi; struct lua_State *
0x18004824b  call    ?lua_settop@@YAXPEAUlua_State@@H@Z; lua_settop(lua_State *,int)
0x180048250  mov     r8d, r14d
0x180048253  mov     rdx, rdi
0x180048256  lea     rcx, [rbp+57h+Uuid]
0x18004825a  call    _anonymous_namespace___etw_sys_flags_option
0x18004825f  movups  xmm0, xmmword ptr [rax]
0x180048262  movups  xmmword ptr [rsi+6Ch], xmm0
0x180048266  movups  xmm1, xmmword ptr [rax+10h]
0x18004826a  movups  xmmword ptr [rsi+7Ch], xmm1
0x18004826e  mov     eax, [rax+20h]
0x180048271  mov     [rsi+8Ch], eax
0x180048277  lea     r8, aEnableFlags; "enable_flags"
0x18004827e  mov     edx, r14d; int
0x180048281  mov     rcx, rdi; struct lua_State *
0x180048284  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x180048289  mov     edx, r13d; int
0x18004828c  mov     rcx, rdi; struct lua_State *
0x18004828f  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180048294  test    eax, eax
0x180048296  jz      short loc_1800482B9
0x180048298  mov     edx, r13d; int
0x18004829b  mov     rcx, rdi; struct lua_State *
0x18004829e  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x1800482a3  mov     [rsi+0B0h], eax
0x1800482a9  cmp     byte ptr [rsi+0B4h], 0
0x1800482b0  jnz     short loc_1800482B9
0x1800482b2  mov     byte ptr [rsi+0B4h], 1
0x1800482b9  lea     r8, aSysStacks; "sys_stacks"
0x1800482c0  mov     edx, r14d; int
0x1800482c3  mov     rcx, rdi; struct lua_State *
0x1800482c6  call    ?lua_getfield@@YAHPEAUlua_State@@HPEBD@Z; lua_getfield(lua_State *,int,char const *)
0x1800482cb  mov     edx, r13d; int
0x1800482ce  mov     rcx, rdi; struct lua_State *
0x1800482d1  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x1800482d6  test    eax, eax
0x1800482d8  jz      loc_180048514
0x1800482de  mov     edx, r13d; int
0x1800482e1  mov     rcx, rdi; struct lua_State *
0x1800482e4  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x1800482e9  cmp     eax, 5
0x1800482ec  jz      short loc_180048300
0x1800482ee  lea     r8, aSysStacksMustB; "sys_stacks must be a table"
0x1800482f5  mov     edx, r14d; int
0x1800482f8  mov     rcx, rdi; struct lua_State *
0x1800482fb  call    ?luaL_argerror@@YAHPEAUlua_State@@HPEBD@Z; luaL_argerror(lua_State *,int,char const *)
0x180048300  xorps   xmm0, xmm0
0x180048303  movdqu  [rsp+120h+var_100+8], xmm0
0x180048309  mov     qword ptr [rsp+120h+var_E8], r12
0x18004830e  mov     edx, r13d; int
0x180048311  mov     rcx, rdi; struct lua_State *
0x180048314  call    ?lua_rawlen@@YA_KPEAUlua_State@@H@Z; lua_rawlen(lua_State *,int)
0x180048319  mov     r14, rax
0x18004831c  mov     ebx, 1
0x180048321  cmp     rax, rbx
0x180048324  jb      loc_180048431
0x18004832a  mov     edx, ebx; __int64
0x18004832c  mov     rcx, rdi; struct lua_State *
0x18004832f  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180048334  mov     edx, 0FFFFFFFEh; int
0x180048339  mov     rcx, rdi; struct lua_State *
0x18004833c  call    ?lua_gettable@@YAHPEAUlua_State@@H@Z; lua_gettable(lua_State *,int)
0x180048341  mov     edx, r13d; int
0x180048344  mov     rcx, rdi; struct lua_State *
0x180048347  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
  ... truncated ...
```
