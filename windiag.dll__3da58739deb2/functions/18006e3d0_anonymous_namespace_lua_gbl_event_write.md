# _anonymous_namespace_::lua_gbl_event_write

- ea: `0x18006e3d0`
- end: `0x18006f046`
- name: `_anonymous_namespace_::lua_gbl_event_write`
- size: `3190`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `45`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004510`
- `0x1800048e0`
- `0x18000491c`
- `0x1800054d8`
- `0x180005520`
- `0x180006600`
- `0x180006690`
- `0x180006790`
- `0x180006980`
- `0x180006b00`
- `0x180006c70`
- `0x180006d00`
- `0x180007490`
- `0x180007650`
- `0x1800076e0`
- `0x180007740`
- `0x1800077f0`
- `0x180007950`
- `0x1800081b0`
- `0x1800083a0`
- `0x180008430`
- `0x180008610`
- `0x180008660`
- `0x18003a4cc`
- `0x18003a52c`
- `0x18003aaa4`
- `0x18003af08`
- `0x18003b0bc`
- `0x1800431c0`
- `0x180049674`
- `0x18006bdd0`
- `0x18006c450`
- `0x18006c5bc`
- `0x18006c9a4`
- `0x18006ca44`
- `0x18006ccd0`
- `0x18006cdcc`
- `0x18006ced0`
- `0x18006d00c`
- `0x18006d110`
- `0x18006d218`
- `0x18006d6dc`
- `0x18006db4c`
- `0x18006df18`
- `0x18006e3d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18006ef04`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18006ef04`
- `RPCRT4!UuidFromStringA` at `0x18006e68d`
- `RPCRT4!UuidFromStringA` at `0x18006e6e1`
- `RPCRT4!UuidFromStringA` at `0x18006e68d`
- `RPCRT4!UuidFromStringA` at `0x18006e6e1`

## string_xrefs

- `0x18006efcf`: `lua_gbl_event_write`
- `0x18006f010`: `lua_gbl_event_write`
- `0x18006e8a0`: `manifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall anonymous_namespace_::lua_gbl_event_write(struct lua_State *a1)
{
  const char *v2; // r14
  int v3; // ebx
  char v4; // r13
  bool v5; // r15
  char v6; // r12
  _BYTE *v7; // rdx
  char v8; // al
  UUID v9; // xmm6
  UUID v10; // xmm7
  const char *v11; // rax
  __int64 v12; // r8
  size_t v13; // rbx
  void **v14; // rcx
  void **v15; // rsi
  unsigned __int64 v16; // r14
  const char *v17; // rbx
  __int64 v18; // r8
  void **v19; // rcx
  unsigned __int8 *v20; // rax
  RPC_STATUS v21; // eax
  void **v22; // rcx
  unsigned __int8 *v23; // rax
  RPC_STATUS v24; // eax
  void **v25; // rcx
  void **v26; // rcx
  void **v27; // rcx
  void **v28; // rcx
  void **v29; // rcx
  void **v30; // rcx
  void **v31; // rcx
  void **v32; // rcx
  void **v33; // rcx
  const char *v34; // rax
  _QWORD *v35; // rax
  const char *v36; // rax
  __int64 v37; // r8
  int v38; // eax
  const char *v39; // rax
  __int64 *v40; // rbx
  _QWORD *v41; // rdx
  unsigned __int64 *v42; // rsi
  _BYTE *v43; // rax
  __int64 v44; // r9
  unsigned __int64 *v45; // r8
  __int64 **v46; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v49; // rsi
  __int64 v50; // rbx
  __int64 v51; // rax
  ULONG UserDataCount; // edx
  void **UserData; // rax
  signed int v54; // eax
  int v55; // eax
  char v57; // [rsp+38h] [rbp-D0h]
  unsigned __int64 v58; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v59[3]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v60[40]; // [rsp+60h] [rbp-A8h] BYREF
  char v61; // [rsp+88h] [rbp-80h]
  _BYTE v62[16]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v63[16]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v64[16]; // [rsp+B0h] [rbp-58h] BYREF
  void *Buf1[2]; // [rsp+C0h] [rbp-48h] BYREF
  size_t Size; // [rsp+D0h] [rbp-38h]
  unsigned __int64 v67; // [rsp+D8h] [rbp-30h]
  __int128 *v68; // [rsp+E8h] [rbp-20h] BYREF
  int v69; // [rsp+F0h] [rbp-18h]
  void **v70; // [rsp+F8h] [rbp-10h]
  int *v71; // [rsp+100h] [rbp-8h]
  __int128 v72; // [rsp+108h] [rbp+0h] BYREF
  _BYTE *v73; // [rsp+118h] [rbp+10h]
  void *v74; // [rsp+120h] [rbp+18h] BYREF
  __int128 v75; // [rsp+128h] [rbp+20h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+138h] [rbp+30h] BYREF
  LPCGUID ActivityId[2]; // [rsp+148h] [rbp+40h]
  int v78; // [rsp+158h] [rbp+50h] BYREF
  UUID Uuid; // [rsp+168h] [rbp+60h] BYREF
  __int128 v80; // [rsp+178h] [rbp+70h] BYREF
  __int64 v81; // [rsp+188h] [rbp+80h]
  __int64 v82; // [rsp+190h] [rbp+88h]
  _BYTE v83[4]; // [rsp+198h] [rbp+90h] BYREF
  UUID v84; // [rsp+19Ch] [rbp+94h]
  char v85; // [rsp+1ACh] [rbp+A4h]
  __int16 v86; // [rsp+1ADh] [rbp+A5h]
  char v87; // [rsp+1AFh] [rbp+A7h]
  UUID v88; // [rsp+1B0h] [rbp+A8h]
  char v89; // [rsp+1C0h] [rbp+B8h]
  __int16 v90; // [rsp+1C1h] [rbp+B9h]
  char v91; // [rsp+1C3h] [rbp+BBh]
  _BYTE v92[32]; // [rsp+1C8h] [rbp+C0h] BYREF
  __int128 v93; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v94; // [rsp+1F8h] [rbp+F0h]
  __int64 v95; // [rsp+200h] [rbp+F8h]
  _BYTE pExceptionObject[1072]; // [rsp+208h] [rbp+100h] BYREF
  void *Block[2]; // [rsp+638h] [rbp+530h] BYREF

  v2 = luaL_checklstring(a1, 1, 0);
  v3 = 0;
  v61 = 0;
  v4 = 0;
  v57 = 0;
  v5 = 0;
  v6 = 0;
  v68 = &v72;
  v69 = 0;
  v70 = &v74;
  v71 = &v78;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  *(_DWORD *)&EventDescriptor.Id = 184549376;
  *(_DWORD *)&EventDescriptor.Level = 5;
  EventDescriptor.Keyword = 0;
  *(_OWORD *)ActivityId = 0;
  v78 = 0;
  LOBYTE(v58) = 0;
  std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(&v72, 0, &v58);
  LOBYTE(v58) = 0;
  if ( *((_BYTE **)&v72 + 1) == v73 )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(&v72, *((_QWORD *)&v72 + 1), &v58);
    v7 = (_BYTE *)*((_QWORD *)&v72 + 1);
  }
  else
  {
    **((_BYTE **)&v72 + 1) = 0;
    v7 = (_BYTE *)++*((_QWORD *)&v72 + 1);
  }
  LOBYTE(v58) = 0;
  if ( v7 == v73 )
  {
    std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(&v72, v7, &v58);
  }
  else
  {
    *v7 = 0;
    ++*((_QWORD *)&v72 + 1);
  }
  while ( 1 )
  {
    v8 = v2[v3];
    LOBYTE(v58) = v8;
    if ( *((_BYTE **)&v72 + 1) == v73 )
    {
      std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(&v72, *((_QWORD *)&v72 + 1), &v58);
    }
    else
    {
      **((_BYTE **)&v72 + 1) = v8;
      ++*((_QWORD *)&v72 + 1);
    }
    if ( !v2[v3] )
      break;
    ++v3;
  }
  Uuid = 0;
  if ( (int)lua_gettop(a1) > 1 )
  {
    luaL_checktype(a1, 2, 5);
    lua_pushnil(a1);
    if ( (unsigned int)lua_next(a1, 2) )
    {
      v9 = *(UUID *)&v59[1];
      v10 = *(UUID *)&v59[1];
      while ( 1 )
      {
        if ( (unsigned int)lua_type(a1, -2) != 4 )
          luaL_argerror(a1, 2, "event table key should be string");
        v11 = lua_tolstring(a1, -2, 0);
        *(_OWORD *)Buf1 = 0;
        Size = 0;
        v67 = 0;
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
        std::string::_Construct<1,char const *>(Buf1, v11, v12);
        v13 = Size;
        v14 = Buf1;
        v15 = (void **)Buf1[0];
        v16 = v67;
        if ( v67 > 0xF )
          v14 = (void **)Buf1[0];
        if ( Size == 8 && !memcmp_0(v14, "provider", 8u) )
        {
          v17 = luaL_checklstring(a1, -1, 0);
          if ( v61 )
          {
            std::string::~string(&v60[8]);
            v61 = 0;
          }
          memset(&v60[8], 0, 32);
          v18 = -1;
          do
            ++v18;
          while ( v17[v18] );
          std::string::_Construct<1,char const *>(&v60[8], v17, v18);
          v61 = 1;
        }
        else
        {
          v19 = Buf1;
          if ( v16 > 0xF )
            v19 = v15;
          if ( v13 == 4 && !memcmp_0(v19, "guid", 4u) )
          {
            v20 = (unsigned __int8 *)luaL_checklstring(a1, -1, 0);
            v21 = UuidFromStringA(v20, &Uuid);
            if ( v21 )
            {
              windiag::system_exception::system_exception(
                (windiag::system_exception *)pExceptionObject,
                v21,
                0,
                "[%s:%d] failed; ",
                "lua_gbl_event_write",
                148);
              throw (windiag::system_exception *)pExceptionObject;
            }
            v9 = Uuid;
            v4 = 1;
          }
          else
          {
            v22 = Buf1;
            if ( v16 > 0xF )
              v22 = v15;
            if ( v13 == 5 && !memcmp_0(v22, "group", 5u) )
            {
              v23 = (unsigned __int8 *)luaL_checklstring(a1, -1, 0);
              v24 = UuidFromStringA(v23, &Uuid);
              if ( v24 )
              {
                windiag::system_exception::system_exception(
                  (windiag::system_exception *)pExceptionObject,
                  v24,
                  0,
                  "[%s:%d] failed; ",
                  "lua_gbl_event_write",
                  151);
                throw (windiag::system_exception *)pExceptionObject;
              }
              v10 = Uuid;
              v57 = 1;
            }
            else
            {
              v25 = Buf1;
              if ( v16 > 0xF )
                v25 = v15;
              if ( v13 == 2 && !memcmp_0(v25, "id", 2u) )
              {
                EventDescriptor.Id = luaL_checkinteger(a1, -1);
                goto LABEL_135;
              }
              v26 = Buf1;
              if ( v16 > 0xF )
                v26 = v15;
              if ( v13 == 3 && !memcmp_0(v26, "ver", 3u) )
              {
                EventDescriptor.Version = luaL_checkinteger(a1, -1);
                goto LABEL_135;
              }
              v27 = Buf1;
              if ( v16 > 0xF )
                v27 = v15;
              if ( v13 == 5 && !memcmp_0(v27, "level", 5u) )
              {
                EventDescriptor.Level = luaL_checkinteger(a1, -1);
                goto LABEL_135;
              }
              v28 = Buf1;
              if ( v16 > 0xF )
                v28 = v15;
              if ( v13 == 7 && !memcmp_0(v28, "keyword", 7u) )
              {
                EventDescriptor.Keyword = luaL_checkinteger(a1, -1);
                goto LABEL_135;
              }
              v29 = Buf1;
              if ( v16 > 0xF )
                v29 = v15;
              if ( v13 == 7 && !memcmp_0(v29, "channel", 7u) )
              {
                EventDescriptor.Channel = luaL_checkinteger(a1, -1);
                v6 = 1;
                goto LABEL_135;
              }
              v30 = Buf1;
              if ( v16 > 0xF )
                v30 = v15;
              if ( v13 == 6 && !memcmp_0(v30, "opcode", 6u) )
              {
                EventDescriptor.Opcode = luaL_checkinteger(a1, -1);
                goto LABEL_135;
              }
              v31 = Buf1;
              if ( v16 > 0xF )
                v31 = v15;
              if ( v13 == 4 && !memcmp_0(v31, "task", 4u) )
              {
                EventDescriptor.Task = luaL_checkinteger(a1, -1);
                goto LABEL_135;
              }
              v32 = Buf1;
              if ( v16 > 0xF )
                v32 = v15;
              if ( v13 == 8 && !memcmp_0(v32, "manifest", 8u) )
              {
                v5 = (unsigned int)lua_toboolean(a1, -1) != 0;
                goto LABEL_135;
              }
              v33 = Buf1;
              if ( v16 > 0xF )
                v33 = v15;
              if ( v13 == 4 && !memcmp_0(v33, "data", 4u) )
              {
                if ( (unsigned int)lua_type(a1, -1) == 4 )
                {
                  v58 = 0;
                  v34 = luaL_checklstring(a1, -1, &v58);
                  std::vector<char>::_Insert_counted_range<char const *>(v70, v70[1], v34, (unsigned __int16)v58);
                  goto LABEL_135;
                }
                if ( (unsigned int)lua_type(a1, -1) != 5 )
                  luaL_argerror(a1, 2, "event table data should be table or string");
                Block[0] = 0;
                Block[1] = 0;
                v35 = operator new(0x68u);
                *v35 = v35;
                v35[1] = v35;
                v35[2] = v35;
                *((_WORD *)v35 + 12) = 257;
                Block[0] = v35;
                lua_pushnil(a1);
                while ( (unsigned int)lua_next(a1, -2) )
                {
                  if ( (unsigned int)lua_type(a1, -2) != 4 )
                    luaL_argerror(a1, 2, "event table data key should be string");
                  v36 = lua_tolstring(a1, -2, 0);
                  v80 = 0;
                  v81 = 0;
                  v82 = 0;
                  v37 = -1;
                  do
                    ++v37;
                  while ( v36[v37] );
                  std::string::_Construct<1,char const *>(&v80, v36, v37);
                  v38 = lua_type(a1, -1);
                  switch ( v38 )
                  {
                    case 1:
                      LOBYTE(v58) = (unsigned int)lua_toboolean(a1, -1) != 0;
                      std::_Tree<std::_Tmap_traits<std::string,std::variant<std::monostate,bool,unsigned __int64,double,std::string>,std::less<std::string>,std::allocator<std::pair<std::string const,std::variant<std::monostate,bool,unsigned __int64,double,std::string>>>,0>>::emplace<std::string &,bool>(
                        Block,
                        &v59[1],
                        &v80,
                        &v58);
                      break;
                    case 3:
                      if ( (unsigned int)lua_isinteger(a1, -1) )
                      {
                        v58 = lua_tointegerx(a1, -1, 0);
                        std::_Tree<std::_Tmap_traits<std::string,std::variant<std::monostate,bool,unsigned __int64,double,std::string>,std::less<std::string>,std::allocator<std::pair<std::string const,std::variant<std::monostate,bool,unsigned __int64,double,std::string>>>,0>>::emplace<std::string &,unsigned __int64>(
                          Block,
                          v63,
                          &v80,
                          &v58);
                      }
                      else
                      {
                        v58 = lua_tonumberx(a1, -1, 0);
                        std::_Tree<std::_Tmap_traits<std::string,std::variant<std::monostate,bool,unsigned __int64,double,std::string>,std::less<std::string>,std::allocator<std::pair<std::string const,std::variant<std::monostate,bool,unsigned __int64,double,std::string>>>,0>>::emplace<std::string &,double>(
                          Block,
                          v64,
                          &v80,
                          &v58);
                      }
                      break;
                    case 4:
                      v58 = 0;
                      v39 = lua_tolstring(a1, -1, &v58);
                      v93 = 0;
                      v94 = 0;
                      v95 = 0;
                      std::string::_Construct<1,char const *>(&v93, v39, v58);
                      std::_Tree<std::_Tmap_traits<std::string,std::variant<std::monostate,bool,unsigned __int64,double,std::string>,std::less<std::string>,std::allocator<std::pair<std::string const,std::variant<std::monostate,bool,unsigned __int64,double,std::string>>>,0>>::emplace<std::string &,std::string>(
                        Block,
                        v62,
                        &v80,
                        &v93);
                      std::string::~string(&v93);
                      break;
                  }
                  lua_settop(a1, -2);
                  std::string::~string(&v80);
                }
                v40 = *(__int64 **)Block[0];
                while ( 2 )
                {
                  if ( *((_BYTE *)v40 + 25) )
                  {
                    std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::variant<std::monostate,bool,unsigned __int64,double,std::string>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::variant<std::monostate,bool,unsigned __int64,double,std::string>>,void *>>>(
                      Block,
                      Block,
                      *((_QWORD *)Block[0] + 1));
                    operator delete(Block[0]);
                    break;
                  }
                  v41 = v40 + 4;
                  v42 = (unsigned __int64 *)(v40 + 8);
                  v43 = v40 + 12;
                  if ( v40 != (__int64 *)-64LL )
                  {
                    switch ( *v43 )
                    {
                      case 1:
                        if ( (unsigned __int64)v40[7] > 0xF )
                          v41 = (_QWORD *)*v41;
                        tld::EventBuilder<std::vector<unsigned char>>::AddField<char>(&v68, v41, 13);
                        LODWORD(v58) = *(unsigned __int8 *)v42;
                        v44 = 4;
                        v45 = &v58;
                        goto LABEL_124;
                      case 2:
                        if ( (unsigned __int64)v40[7] > 0xF )
                          v41 = (_QWORD *)*v41;
                        tld::EventBuilder<std::vector<unsigned char>>::AddField<char>(&v68, v41, 10);
                        v58 = *v42;
                        v44 = 8;
                        v45 = &v58;
                        goto LABEL_124;
                      case 3:
                        if ( (unsigned __int64)v40[7] > 0xF )
                          v41 = (_QWORD *)*v41;
                        tld::EventBuilder<std::vector<unsigned char>>::AddField<char>(&v68, v41, 12);
                        v58 = *v42;
                        v44 = 8;
                        v45 = &v58;
                        goto LABEL_124;
                      case 4:
                        if ( (unsigned __int64)v40[7] > 0xF )
                          v41 = (_QWORD *)*v41;
                        tld::EventBuilder<std::vector<unsigned char>>::AddField<char>(&v68, v41, 8983);
                        if ( (unsigned __int64)v40[11] > 0xF )
                          v42 = (unsigned __int64 *)*v42;
                        LOWORD(v58) = *((_WORD *)v40 + 40);
                        std::vector<char>::_Insert_counted_range<char const *>(v70, v70[1], &v58, 2);
                        v44 = (unsigned __int16)v58;
                        v45 = v42;
LABEL_124:
                        std::vector<char>::_Insert_counted_range<char const *>(v70, v70[1], v45, v44);
                        break;
                    }
                  }
                  v46 = (__int64 **)v40[2];
                  if ( *((_BYTE *)v46 + 25) )
                  {
                    for ( i = (__int64 *)v40[1]; !*((_BYTE *)i + 25) && v40 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                      v40 = i;
                    v40 = i;
                  }
                  else
                  {
                    v40 = (__int64 *)v40[2];
                    for ( j = *v46; !*((_BYTE *)j + 25); j = (__int64 *)*j )
                      v40 = j;
                  }
                  continue;
                }
              }
            }
          }
        }
LABEL_135:
        lua_settop(a1, -2);
        std::string::~string(Buf1);
        if ( !(unsigned int)lua_next(a1, 2) )
          goto LABEL_138;
      }
    }
  }
  v9 = *(UUID *)&v59[1];
  v10 = *(UUID *)&v59[1];
LABEL_138:
  if ( v61 )
  {
    v83[0] = v5;
    v84 = v10;
    v85 = v57;
    v86 = *(_WORD *)&v60[1];
    v87 = v60[3];
    v88 = v9;
    v89 = v4;
    v90 = *(_WORD *)&v60[1];
    v91 = v60[3];
    std::string::string(v92);
    if ( v5 && !v6 )
      EventDescriptor.Channel = 0;
    lua_pushlightuserdata(a1, &unk_1800BEADC);
    lua_gettable(a1, -1001000);
    v49 = luaL_checkudata(a1, -1, "gbl.state");
    lua_settop(a1, -2);
    std::_Tree_std::_Tmap_traits_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____std::optional__GUID__std::optional__GUID__bool__std::variant_std::unique_ptr_tld::Provider_std::default_delete_tld::Provider____windiag::win_handle_unsigned___int64__anonymous_namespace_::etw_close_provider_0____std::less_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____std::optional__GUID__std::optional__GUID__bool____std::allocator_std::pair_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____std::optional__GUID__std::optional__GUID__bool__const__std::variant_std::unique_ptr_tld::Provider_std::default_delete_tld::Provider____windiag::win_handle_unsigned___int64__anonymous_namespace_::etw_close_provider_0________0___::_Find_lower_bound_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____std::optional__GUID__std::optional__GUID__bool___(
      v49,
      &v59[1],
      v83);
    v50 = *(_QWORD *)v60;
    if ( *(_BYTE *)(*(_QWORD *)v60 + 25LL)
      || (unsigned __int8)std::operator<<char>(v92, *(_QWORD *)v60 + 80LL)
      || !(unsigned __int8)std::operator<<char>(v50 + 80, v92)
      && (unsigned __int8)std::tuple<std::optional<_GUID>,std::optional<_GUID>,bool>::_Less<std::optional<_GUID>,std::optional<_GUID>,bool>(
                            v83,
                            v50 + 32)
      || v50 == *v49 )
    {
      v51 = anonymous_namespace_::etw_dynamic_provider(&v58, v83);
      v50 = *(_QWORD *)std::_Tree_std::_Tmap_traits_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____std::optional__GUID__std::optional__GUID__bool__std::variant_std::unique_ptr_tld::Provider_std::default_delete_tld::Provider____windiag::win_handle_unsigned___int64__anonymous_namespace_::etw_close_provider_0____std::less_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____std::optional__GUID__std::optional__GUID__bool____std::allocator_std::pair_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____std::optional__GUID__std::optional__GUID__bool__const__std::variant_std::unique_ptr_tld::Provider_std::default_delete_tld::Provider____windiag::win_handle_unsigned___int64__anonymous_namespace_::etw_close_provider_0________0___::emplace_std::tuple_std::basic_string_char_std::char_traits_char__std::allocator_char____std::optional__GUID__std::optional__GUID__bool__const___std::variant_std::unique_ptr_tld::Provider_std::default_delete_tld::Provider____windiag::win_handle_unsigned___int64__anonymous_namespace_::etw_close_provider_0_____(
                         v49,
                         &v59[1],
                         v83,
                         v51);
      std::_Variant_destroy_layer__std::unique_ptr_tld::Provider_std::default_delete_tld::Provider____windiag::win_handle_unsigned___int64__anonymous_namespace_::etw_close_provider_0___::__Variant_destroy_layer__std::unique_ptr_tld::Provider_std::default_delete_tld::Provider____windiag::win_handle_unsigned___int64__anonymous_namespace_::etw_close_provider_0___(&v58);
    }
    if ( *(char *)(v50 + 120) == -1 )
      std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_std::pair_void_const___unsigned___int64___lambda_0f2987df398fcf62c701e32323b26f6e__std::variant_std::vector_char_std::allocator_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____unsigned_long___int64_std::pair_void_const___unsigned___int64______1_();
    if ( *(_BYTE *)(v50 + 120) )
    {
      *(_OWORD *)Block = 0;
      if ( v74 == (void *)v75 )
      {
        UserDataCount = 0;
        UserData = 0;
      }
      else
      {
        UserDataCount = 1;
        Block[0] = v74;
        Block[1] = (void *)(unsigned int)(v75 - (_DWORD)v74);
        UserData = Block;
      }
      v54 = EventWriteTransfer(
              *(_QWORD *)(v50 + 112),
              &EventDescriptor,
              ActivityId[0],
              ActivityId[1],
              UserDataCount,
              (PEVENT_DATA_DESCRIPTOR)UserData);
      if ( v54 > 0 )
        v54 = (unsigned __int16)v54 | 0x80070000;
    }
    else
    {
      v54 = tld::Event<std::vector<unsigned char>>::Write(&v68, *(_QWORD *)(v50 + 112));
    }
    lua_pushboolean(a1, v54 >= 0);
    std::string::~string(v92);
  }
  else
  {
    v55 = tld::Event<std::vector<unsigned char>>::Write(&v68, &unk_1800BEDB0);
    lua_pushboolean(a1, v55 >= 0);
  }
  std::vector<char>::~vector<char>(&v74);
  std::vector<char>::~vector<char>(&v72);
  if ( v61 )
    std::string::~string(&v60[8]);
  return 1;
}

```

## disassembly

```asm
0x18006e3d0  mov     rax, rsp
0x18006e3d3  push    rbp
0x18006e3d4  push    rbx
0x18006e3d5  push    rsi
0x18006e3d6  push    rdi
0x18006e3d7  push    r12
0x18006e3d9  push    r13
0x18006e3db  push    r14
0x18006e3dd  push    r15
0x18006e3df  lea     rbp, [rax-5B8h]
0x18006e3e6  sub     rsp, 678h
0x18006e3ed  movaps  xmmword ptr [rax-58h], xmm6
0x18006e3f1  movaps  xmmword ptr [rax-68h], xmm7
0x18006e3f5  mov     rax, cs:__security_cookie
0x18006e3fc  xor     rax, rsp
0x18006e3ff  mov     [rbp+5B0h+var_70], rax
0x18006e406  mov     rdi, rcx
0x18006e409  xor     r8d, r8d; unsigned __int64 *
0x18006e40c  lea     edx, [r8+1]; int
0x18006e410  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18006e415  mov     r14, rax
0x18006e418  xor     ebx, ebx
0x18006e41a  mov     [rbp+5B0h+var_630], bl
0x18006e41d  mov     r13b, bl
0x18006e420  mov     byte ptr [rsp+6B0h+var_680], bl
0x18006e424  mov     r15b, bl
0x18006e427  mov     r12b, bl
0x18006e42a  lea     rax, [rbp+5B0h+var_5B0]
0x18006e42e  mov     [rbp+5B0h+var_5D0], rax
0x18006e432  mov     [rbp+5B0h+var_5C8], ebx
0x18006e435  lea     rax, [rbp+5B0h+var_598]
0x18006e439  mov     [rbp+5B0h+var_5C0], rax
0x18006e43d  lea     rax, [rbp+5B0h+var_560]
0x18006e441  mov     [rbp+5B0h+var_5B8], rax
0x18006e445  xorps   xmm0, xmm0
0x18006e448  movdqa  [rbp+5B0h+var_5B0], xmm0
0x18006e44d  mov     [rbp+5B0h+var_5A0], rbx
0x18006e451  mov     [rbp+5B0h+var_598], rbx
0x18006e455  movdqa  [rbp+5B0h+var_590], xmm0
0x18006e45a  mov     dword ptr [rbp+5B0h+EventDescriptor.Id], 0B000000h
0x18006e461  mov     dword ptr [rbp+5B0h+EventDescriptor.Level], 5
0x18006e468  mov     [rbp+5B0h+EventDescriptor.Keyword], rbx
0x18006e46c  movdqa  xmmword ptr [rbp+5B0h+ActivityId], xmm0
0x18006e471  mov     [rbp+5B0h+var_560], ebx
0x18006e474  mov     byte ptr [rsp+6B0h+var_678], bl
0x18006e478  lea     r8, [rsp+6B0h+var_678]
0x18006e47d  xor     edx, edx
0x18006e47f  lea     rcx, [rbp+5B0h+var_5B0]
0x18006e483  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x18006e488  mov     byte ptr [rsp+6B0h+var_678], bl
0x18006e48c  mov     rdx, qword ptr [rbp+5B0h+var_5B0+8]
0x18006e490  cmp     rdx, [rbp+5B0h+var_5A0]
0x18006e494  jz      short loc_18006E4A5
0x18006e496  mov     [rdx], bl
0x18006e498  mov     rdx, qword ptr [rbp+5B0h+var_5B0+8]
0x18006e49c  inc     rdx
0x18006e49f  mov     qword ptr [rbp+5B0h+var_5B0+8], rdx
0x18006e4a3  jmp     short loc_18006E4B7
0x18006e4a5  lea     r8, [rsp+6B0h+var_678]
0x18006e4aa  lea     rcx, [rbp+5B0h+var_5B0]
0x18006e4ae  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x18006e4b3  mov     rdx, qword ptr [rbp+5B0h+var_5B0+8]
0x18006e4b7  mov     byte ptr [rsp+6B0h+var_678], bl
0x18006e4bb  cmp     rdx, [rbp+5B0h+var_5A0]
0x18006e4bf  jz      short loc_18006E4C9
0x18006e4c1  mov     [rdx], bl
0x18006e4c3  inc     qword ptr [rbp+5B0h+var_5B0+8]
0x18006e4c7  jmp     short loc_18006E4D7
0x18006e4c9  lea     r8, [rsp+6B0h+var_678]
0x18006e4ce  lea     rcx, [rbp+5B0h+var_5B0]
0x18006e4d2  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x18006e4d7  mov     esi, ebx
0x18006e4d9  mov     al, [rsi+r14]
0x18006e4dd  mov     byte ptr [rsp+6B0h+var_678], al
0x18006e4e1  mov     rdx, qword ptr [rbp+5B0h+var_5B0+8]
0x18006e4e5  cmp     rdx, [rbp+5B0h+var_5A0]
0x18006e4e9  jz      short loc_18006E4F3
0x18006e4eb  mov     [rdx], al
0x18006e4ed  inc     qword ptr [rbp+5B0h+var_5B0+8]
0x18006e4f1  jmp     short loc_18006E501
0x18006e4f3  lea     r8, [rsp+6B0h+var_678]
0x18006e4f8  lea     rcx, [rbp+5B0h+var_5B0]
0x18006e4fc  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x18006e501  cmp     byte ptr [rsi+r14], 0
0x18006e506  jz      short loc_18006E50C
0x18006e508  inc     ebx
0x18006e50a  jmp     short loc_18006E4D7
0x18006e50c  xorps   xmm0, xmm0
0x18006e50f  movups  xmmword ptr [rbp+5B0h+Uuid.Data1], xmm0
0x18006e513  mov     rcx, rdi; struct lua_State *
0x18006e516  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18006e51b  mov     ebx, 0FFFFFFFEh
0x18006e520  cmp     eax, 1
0x18006e523  jle     loc_18006ED3B
0x18006e529  lea     edx, [rbx+4]; int
0x18006e52c  lea     r8d, [rbx+7]; int
0x18006e530  mov     rcx, rdi; struct lua_State *
0x18006e533  call    ?luaL_checktype@@YAXPEAUlua_State@@HH@Z; luaL_checktype(lua_State *,int,int)
0x18006e538  mov     rcx, rdi; struct lua_State *
0x18006e53b  call    ?lua_pushnil@@YAXPEAUlua_State@@@Z; lua_pushnil(lua_State *)
0x18006e540  lea     edx, [rbx+4]; int
0x18006e543  mov     rcx, rdi; struct lua_State *
0x18006e546  call    ?lua_next@@YAHPEAUlua_State@@H@Z; lua_next(lua_State *,int)
0x18006e54b  test    eax, eax
0x18006e54d  jz      loc_18006ED3B
0x18006e553  movups  xmm6, xmmword ptr [rsp+6B0h+var_670+8]
0x18006e558  movups  xmm7, xmmword ptr [rsp+6B0h+var_670+8]
0x18006e55d  mov     edx, ebx; int
0x18006e55f  mov     rcx, rdi; struct lua_State *
0x18006e562  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x18006e567  cmp     eax, 4
0x18006e56a  jz      short loc_18006E580
0x18006e56c  lea     r8, aEventTableKeyS; "event table key should be string"
0x18006e573  mov     edx, 2; int
0x18006e578  mov     rcx, rdi; struct lua_State *
0x18006e57b  call    ?luaL_argerror@@YAHPEAUlua_State@@HPEBD@Z; luaL_argerror(lua_State *,int,char const *)
0x18006e580  xor     r8d, r8d; unsigned __int64 *
0x18006e583  mov     edx, ebx; int
0x18006e585  mov     rcx, rdi; struct lua_State *
0x18006e588  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x18006e58d  xorps   xmm0, xmm0
0x18006e590  movups  xmmword ptr [rbp+5B0h+Buf1], xmm0
0x18006e594  mov     [rbp+5B0h+Size], 0
0x18006e59c  mov     [rbp+5B0h+var_5E0], 0
0x18006e5a4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006e5a8  inc     r8
0x18006e5ab  cmp     byte ptr [rax+r8], 0
0x18006e5b0  jnz     short loc_18006E5A8
0x18006e5b2  mov     rdx, rax
0x18006e5b5  lea     rcx, [rbp+5B0h+Buf1]
0x18006e5b9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006e5be  nop
0x18006e5bf  mov     rbx, [rbp+5B0h+Size]
0x18006e5c3  lea     rcx, [rbp+5B0h+Buf1]
0x18006e5c7  mov     rsi, [rbp+5B0h+Buf1]
0x18006e5cb  mov     r14, [rbp+5B0h+var_5E0]
0x18006e5cf  cmp     r14, 0Fh
0x18006e5d3  cmova   rcx, rsi; Buf1
0x18006e5d7  cmp     rbx, 8
0x18006e5db  jnz     short loc_18006E653
0x18006e5dd  mov     r8, rbx; Size
0x18006e5e0  lea     rdx, aProvider; "provider"
0x18006e5e7  call    memcmp_0
0x18006e5ec  test    eax, eax
0x18006e5ee  jnz     short loc_18006E653
0x18006e5f0  xor     r8d, r8d; unsigned __int64 *
0x18006e5f3  or      edx, 0FFFFFFFFh; int
0x18006e5f6  mov     rcx, rdi; struct lua_State *
0x18006e5f9  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18006e5fe  mov     rbx, rax
0x18006e601  cmp     [rbp+5B0h+var_630], 0
0x18006e605  jz      short loc_18006E615
0x18006e607  lea     rcx, [rsp+6B0h+var_658+8]
0x18006e60c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18006e611  mov     [rbp+5B0h+var_630], 0
0x18006e615  xorps   xmm0, xmm0
0x18006e618  movups  xmmword ptr [rsp+6B0h+var_658+8], xmm0
0x18006e61d  mov     [rsp+6B0h+var_640], 0
0x18006e626  mov     [rsp+6B0h+var_638], 0
0x18006e62f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006e633  inc     r8
0x18006e636  cmp     byte ptr [rbx+r8], 0
0x18006e63b  jnz     short loc_18006E633
0x18006e63d  mov     rdx, rbx
0x18006e640  lea     rcx, [rsp+6B0h+var_658+8]
0x18006e645  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006e64a  mov     [rbp+5B0h+var_630], 1
0x18006e64e  jmp     loc_18006ED0D
0x18006e653  lea     rcx, [rbp+5B0h+Buf1]
0x18006e657  cmp     r14, 0Fh
0x18006e65b  cmova   rcx, rsi; Buf1
0x18006e65f  cmp     rbx, 4
0x18006e663  jnz     short loc_18006E6A7
0x18006e665  mov     r8, rbx; Size
0x18006e668  lea     rdx, aGuid_0; "guid"
0x18006e66f  call    memcmp_0
0x18006e674  test    eax, eax
0x18006e676  jnz     short loc_18006E6A7
0x18006e678  xor     r8d, r8d; unsigned __int64 *
0x18006e67b  or      edx, 0FFFFFFFFh; int
0x18006e67e  mov     rcx, rdi; struct lua_State *
0x18006e681  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18006e686  mov     rcx, rax; StringUuid
0x18006e689  lea     rdx, [rbp+5B0h+Uuid]; Uuid
0x18006e68d  call    cs:__imp_UuidFromStringA
0x18006e693  test    eax, eax
0x18006e695  jnz     loc_18006EFC4
0x18006e69b  movups  xmm6, xmmword ptr [rbp+5B0h+Uuid.Data1]
0x18006e69f  mov     r13b, 1
0x18006e6a2  jmp     loc_18006ED0D
0x18006e6a7  lea     rcx, [rbp+5B0h+Buf1]
0x18006e6ab  cmp     r14, 0Fh
0x18006e6af  cmova   rcx, rsi; Buf1
0x18006e6b3  cmp     rbx, 5
0x18006e6b7  jnz     short loc_18006E6FD
0x18006e6b9  mov     r8, rbx; Size
0x18006e6bc  lea     rdx, aGroup; "group"
0x18006e6c3  call    memcmp_0
0x18006e6c8  test    eax, eax
0x18006e6ca  jnz     short loc_18006E6FD
0x18006e6cc  xor     r8d, r8d; unsigned __int64 *
0x18006e6cf  or      edx, 0FFFFFFFFh; int
0x18006e6d2  mov     rcx, rdi; struct lua_State *
0x18006e6d5  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18006e6da  mov     rcx, rax; StringUuid
0x18006e6dd  lea     rdx, [rbp+5B0h+Uuid]; Uuid
0x18006e6e1  call    cs:__imp_UuidFromStringA
0x18006e6e7  test    eax, eax
0x18006e6e9  jnz     loc_18006F005
0x18006e6ef  movups  xmm7, xmmword ptr [rbp+5B0h+Uuid.Data1]
0x18006e6f3  mov     byte ptr [rsp+6B0h+var_680], 1
0x18006e6f8  jmp     loc_18006ED0D
0x18006e6fd  lea     rcx, [rbp+5B0h+Buf1]
0x18006e701  cmp     r14, 0Fh
0x18006e705  cmova   rcx, rsi; Buf1
0x18006e709  cmp     rbx, 2
0x18006e70d  jnz     short loc_18006E736
0x18006e70f  mov     r8, rbx; Size
0x18006e712  lea     rdx, aId; "id"
0x18006e719  call    memcmp_0
0x18006e71e  test    eax, eax
0x18006e720  jnz     short loc_18006E736
0x18006e722  or      edx, 0FFFFFFFFh; int
0x18006e725  mov     rcx, rdi; struct lua_State *
0x18006e728  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006e72d  mov     [rbp+5B0h+EventDescriptor.Id], ax
0x18006e731  jmp     loc_18006ED0D
0x18006e736  lea     rcx, [rbp+5B0h+Buf1]
0x18006e73a  cmp     r14, 0Fh
0x18006e73e  cmova   rcx, rsi; Buf1
0x18006e742  cmp     rbx, 3
0x18006e746  jnz     short loc_18006E76E
0x18006e748  mov     r8, rbx; Size
0x18006e74b  lea     rdx, aVer; "ver"
0x18006e752  call    memcmp_0
0x18006e757  test    eax, eax
0x18006e759  jnz     short loc_18006E76E
0x18006e75b  or      edx, 0FFFFFFFFh; int
0x18006e75e  mov     rcx, rdi; struct lua_State *
0x18006e761  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006e766  mov     [rbp+5B0h+EventDescriptor.Version], al
0x18006e769  jmp     loc_18006ED0D
0x18006e76e  lea     rcx, [rbp+5B0h+Buf1]
0x18006e772  cmp     r14, 0Fh
0x18006e776  cmova   rcx, rsi; Buf1
0x18006e77a  cmp     rbx, 5
0x18006e77e  jnz     short loc_18006E7A6
0x18006e780  mov     r8, rbx; Size
0x18006e783  lea     rdx, aLevel; "level"
0x18006e78a  call    memcmp_0
0x18006e78f  test    eax, eax
0x18006e791  jnz     short loc_18006E7A6
0x18006e793  or      edx, 0FFFFFFFFh; int
0x18006e796  mov     rcx, rdi; struct lua_State *
0x18006e799  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006e79e  mov     [rbp+5B0h+EventDescriptor.Level], al
0x18006e7a1  jmp     loc_18006ED0D
0x18006e7a6  lea     rcx, [rbp+5B0h+Buf1]
0x18006e7aa  cmp     r14, 0Fh
0x18006e7ae  cmova   rcx, rsi; Buf1
0x18006e7b2  cmp     rbx, 7
0x18006e7b6  jnz     short loc_18006E7DF
0x18006e7b8  mov     r8, rbx; Size
0x18006e7bb  lea     rdx, aKeyword; "keyword"
0x18006e7c2  call    memcmp_0
0x18006e7c7  test    eax, eax
0x18006e7c9  jnz     short loc_18006E7DF
0x18006e7cb  or      edx, 0FFFFFFFFh; int
0x18006e7ce  mov     rcx, rdi; struct lua_State *
0x18006e7d1  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006e7d6  mov     [rbp+5B0h+EventDescriptor.Keyword], rax
0x18006e7da  jmp     loc_18006ED0D
0x18006e7df  lea     rcx, [rbp+5B0h+Buf1]
0x18006e7e3  cmp     r14, 0Fh
0x18006e7e7  cmova   rcx, rsi; Buf1
0x18006e7eb  cmp     rbx, 7
0x18006e7ef  jnz     short loc_18006E81A
0x18006e7f1  mov     r8, rbx; Size
0x18006e7f4  lea     rdx, aChannel; "channel"
0x18006e7fb  call    memcmp_0
0x18006e800  test    eax, eax
0x18006e802  jnz     short loc_18006E81A
0x18006e804  or      edx, 0FFFFFFFFh; int
0x18006e807  mov     rcx, rdi; struct lua_State *
0x18006e80a  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006e80f  mov     [rbp+5B0h+EventDescriptor.Channel], al
0x18006e812  mov     r12b, 1
0x18006e815  jmp     loc_18006ED0D
0x18006e81a  lea     rcx, [rbp+5B0h+Buf1]
0x18006e81e  cmp     r14, 0Fh
0x18006e822  cmova   rcx, rsi; Buf1
0x18006e826  cmp     rbx, 6
0x18006e82a  jnz     short loc_18006E852
0x18006e82c  mov     r8, rbx; Size
0x18006e82f  lea     rdx, aOpcode; "opcode"
0x18006e836  call    memcmp_0
0x18006e83b  test    eax, eax
0x18006e83d  jnz     short loc_18006E852
0x18006e83f  or      edx, 0FFFFFFFFh; int
0x18006e842  mov     rcx, rdi; struct lua_State *
  ... truncated ...
```
