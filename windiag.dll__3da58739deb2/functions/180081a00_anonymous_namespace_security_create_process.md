# _anonymous_namespace_::security_create_process

- ea: `0x180081a00`
- end: `0x180082adf`
- name: `_anonymous_namespace_::security_create_process`
- size: `4319`
- prototype: `__int64 __fastcall(windiag *this)`
- caller_count: `0`
- callee_count: `37`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004510`
- `0x1800054d8`
- `0x1800054e4`
- `0x180005520`
- `0x180006910`
- `0x180006980`
- `0x180006d00`
- `0x180007490`
- `0x180007650`
- `0x1800076e0`
- `0x180007740`
- `0x180007950`
- `0x1800081b0`
- `0x180008610`
- `0x180008790`
- `0x180009510`
- `0x18003a52c`
- `0x18003af08`
- `0x18003b0bc`
- `0x18003d738`
- `0x180040f94`
- `0x180041564`
- `0x1800416a0`
- `0x18004a1b4`
- `0x18004b73c`
- `0x180052684`
- `0x1800527d8`
- `0x1800545dc`
- `0x180056588`
- `0x1800580c8`
- `0x18005f54c`
- `0x18007835c`
- `0x180080734`
- `0x180080944`
- `0x180080afc`
- `0x180081a00`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800824ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800825bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800827d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800824ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800825bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800827d4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800827c3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800827c3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18008265f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18008265f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008251d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18008251d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800826c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800826df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800826f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008286b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800826c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800826df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800826f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008286b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082882`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18008255e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18008255e`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800825b1`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800825b1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800824ea`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800824ea`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x1800823f1`
- `api-ms-win-core-namedpipe-l1-1-0!CreatePipe` at `0x1800823f1`

## string_xrefs

- `0x180082929`: `security_create_process`
- `0x180082969`: `security_create_process`
- `0x1800829a9`: `security_create_process`
- `0x1800829e9`: `security_create_process`
- `0x180082a29`: `security_create_process`
- `0x180082a69`: `security_create_process`
- `0x180082aa9`: `security_create_process`
- `0x18008273a`: `security.process`
- `0x180082841`: `security.process`
- `0x180081b3f`: `exe_path`
- `0x180082160`: `'exe_path' and/or 'cmd_line' must be present in process create table`
- `0x18008258c`: `SeTcbPrivilege`
- `0x18008260e`: `SeAssignPrimaryTokenPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall anonymous_namespace_::security_create_process(windiag *this)
{
  const WCHAR *v2; // r15
  bool v3; // r13
  char v4; // di
  __int64 v5; // r14
  bool v6; // r12
  const char *v7; // rax
  __int64 v8; // r8
  size_t v9; // rbx
  void **v10; // rcx
  void **v11; // rdi
  unsigned __int64 v12; // r14
  const char *v13; // rax
  __int64 v14; // rax
  _BYTE *v15; // rcx
  void **v16; // rcx
  const char *v17; // rax
  __int64 v18; // rax
  void **v19; // rcx
  const char *v20; // rax
  __int64 v21; // rax
  void **v22; // rcx
  void **v23; // rcx
  void **v24; // rcx
  void **v25; // rcx
  void **v26; // rcx
  void **v27; // rcx
  const char *v28; // rax
  __int64 v29; // rax
  void **v30; // rax
  bool v31; // cf
  int v32; // eax
  const char *v33; // rax
  const char *v34; // rax
  __int128 *v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rax
  _BYTE *v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  WCHAR *v44; // rbx
  WCHAR *v45; // rax
  DWORD LastError; // eax
  DWORD dwCreationFlags; // edi
  __int128 *lpEnvironment; // r13
  const WCHAR *lpCurrentDirectory; // r12
  HANDLE v50; // rbx
  DWORD v51; // eax
  DWORD v52; // eax
  __int64 v53; // r8
  DWORD v54; // eax
  DWORD v55; // eax
  volatile signed __int32 *v56; // r14
  DWORD v57; // eax
  volatile signed __int32 *v58; // rdi
  HANDLE v59; // rcx
  void *v60; // rcx
  HANDLE hProcess; // r14
  HANDLE hThread; // r15
  struct lua_State *v63; // rdx
  void *v64; // rbx
  void *v65; // rdi
  WCHAR *v66; // rax
  DWORD v67; // eax
  void *v68; // rbx
  struct lua_State *v69; // rdx
  void *v70; // rcx
  WCHAR *v71; // rax
  void *v72; // rcx
  void *v73; // rcx
  bool v75; // [rsp+60h] [rbp-A0h]
  char v76; // [rsp+61h] [rbp-9Fh]
  HANDLE TokenInformation; // [rsp+68h] [rbp-98h] BYREF
  char v78; // [rsp+70h] [rbp-90h]
  DWORD dwProcessId[2]; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  void *hReadPipe; // [rsp+88h] [rbp-78h] BYREF
  LPWSTR lpCommandLine; // [rsp+90h] [rbp-70h] BYREF
  void *hWritePipe; // [rsp+98h] [rbp-68h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-60h] BYREF
  volatile signed __int32 *v85; // [rsp+A8h] [rbp-58h]
  HANDLE v86; // [rsp+B0h] [rbp-50h]
  LPWSTR v87[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v88; // [rsp+C8h] [rbp-38h]
  char v89; // [rsp+D8h] [rbp-28h]
  LPCWSTR v90[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v91; // [rsp+F0h] [rbp-10h]
  char v92; // [rsp+100h] [rbp+0h]
  __int128 v93; // [rsp+108h] [rbp+8h] BYREF
  __int128 v94; // [rsp+118h] [rbp+18h]
  char v95; // [rsp+128h] [rbp+28h]
  __int128 v96; // [rsp+130h] [rbp+30h] BYREF
  __int128 v97; // [rsp+140h] [rbp+40h]
  char v98; // [rsp+150h] [rbp+50h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+158h] [rbp+58h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v101[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v102[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v103[224]; // [rsp+1F8h] [rbp+F8h] BYREF
  char v104; // [rsp+2D8h] [rbp+1D8h]
  void *Buf1[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  size_t Size; // [rsp+2F0h] [rbp+1F0h]
  unsigned __int64 v107; // [rsp+2F8h] [rbp+1F8h]
  _BYTE PipeAttributes[32]; // [rsp+300h] [rbp+200h] BYREF
  __int128 v109; // [rsp+320h] [rbp+220h] BYREF
  __int128 v110; // [rsp+330h] [rbp+230h]
  __int128 v111; // [rsp+340h] [rbp+240h] BYREF
  __m128i si128; // [rsp+350h] [rbp+250h]
  _BYTE v113[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v114[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v115[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v116[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v2 = 0;
  luaL_checktype(this, 1, 5);
  v98 = 0;
  v89 = 0;
  v95 = 0;
  v92 = 0;
  v78 = 0;
  v76 = 0;
  v3 = 0;
  v75 = 0;
  v4 = 0;
  LOBYTE(TokenInformation) = 0;
  v104 = 0;
  lua_pushnil(this);
  LODWORD(v5) = (_DWORD)TokenInformation;
  v6 = 0;
  if ( (unsigned int)lua_next(this, 1) )
  {
    v84 = (unsigned int)TokenInformation;
    *(_QWORD *)dwProcessId = (unsigned int)TokenInformation;
    while ( 1 )
    {
      if ( (unsigned int)lua_type(this, -2) != 4 )
        luaL_argerror(this, 2, "table key should be string");
      v7 = lua_tolstring(this, -2, 0);
      *(_OWORD *)Buf1 = 0;
      Size = 0;
      v107 = 0;
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      std::string::_Construct<1,char const *>(Buf1, v7, v8);
      v9 = Size;
      v10 = Buf1;
      v11 = (void **)Buf1[0];
      v12 = v107;
      if ( v107 > 0xF )
        v10 = (void **)Buf1[0];
      if ( Size == 8 && !memcmp_0(v10, "exe_path", 8u) )
      {
        v13 = lua_tolstring(this, -1, 0);
        v14 = windiag::char_to_wstring(v116, v13);
        if ( v98 )
        {
          std::wstring::operator=(&v96, v14);
        }
        else
        {
          v96 = 0;
          v97 = 0;
          v96 = *(_OWORD *)v14;
          v97 = *(_OWORD *)(v14 + 16);
          *(_QWORD *)(v14 + 16) = 0;
          *(_QWORD *)(v14 + 24) = 7;
          *(_WORD *)v14 = 0;
          v98 = 1;
        }
        v15 = v116;
        goto LABEL_15;
      }
      v16 = Buf1;
      if ( v12 > 0xF )
        v16 = v11;
      if ( v9 == 8 && !memcmp_0(v16, "cmd_line", 8u) )
      {
        v17 = lua_tolstring(this, -1, 0);
        v18 = windiag::char_to_wstring(v113, v17);
        if ( v89 )
        {
          std::wstring::operator=(v87, v18);
        }
        else
        {
          *(_OWORD *)v87 = 0;
          v88 = 0;
          v87[0] = *(LPWSTR *)v18;
          v87[1] = *(LPWSTR *)(v18 + 8);
          v88 = *(_OWORD *)(v18 + 16);
          *(_QWORD *)(v18 + 16) = 0;
          *(_QWORD *)(v18 + 24) = 7;
          *(_WORD *)v18 = 0;
          v89 = 1;
        }
        v15 = v113;
        goto LABEL_15;
      }
      v19 = Buf1;
      if ( v12 > 0xF )
        v19 = v11;
      if ( v9 == 7 && !memcmp_0(v19, "desktop", 7u) )
      {
        v20 = lua_tolstring(this, -1, 0);
        v21 = windiag::char_to_wstring(v114, v20);
        if ( v95 )
        {
          std::wstring::operator=(&v93, v21);
        }
        else
        {
          v93 = 0;
          v94 = 0;
          v93 = *(_OWORD *)v21;
          v94 = *(_OWORD *)(v21 + 16);
          *(_QWORD *)(v21 + 16) = 0;
          *(_QWORD *)(v21 + 24) = 7;
          *(_WORD *)v21 = 0;
          v95 = 1;
        }
        v15 = v114;
        goto LABEL_15;
      }
      v22 = Buf1;
      if ( v12 > 0xF )
        v22 = v11;
      if ( v9 == 7 && !memcmp_0(v22, "console", 7u) )
      {
        v4 = (char)TokenInformation;
        LODWORD(v5) = dwProcessId[0];
        v6 = (unsigned int)lua_toboolean(this, -1) != 0;
        if ( !(_BYTE)TokenInformation )
        {
          v4 = 1;
          LOBYTE(TokenInformation) = 1;
        }
        goto LABEL_91;
      }
      v23 = Buf1;
      if ( v12 > 0xF )
        v23 = v11;
      if ( v9 == 9 && !memcmp_0(v23, "suspended", 9u) )
        break;
      v24 = Buf1;
      if ( v12 > 0xF )
        v24 = v11;
      if ( v9 == 10 && !memcmp_0(v24, "redirected", 0xAu) )
      {
        v75 = (unsigned int)lua_toboolean(this, -1) != 0;
        goto LABEL_89;
      }
      v25 = Buf1;
      if ( v12 > 0xF )
        v25 = v11;
      if ( v9 != 6 || memcmp_0(v25, "as_pid", 6u) )
      {
        v26 = Buf1;
        if ( v12 > 0xF )
          v26 = v11;
        if ( v9 == 10 && !memcmp_0(v26, "session_id", 0xAu) )
        {
          v84 = lua_tointegerx(this, -1, 0);
          v76 = 1;
          goto LABEL_89;
        }
        v27 = Buf1;
        if ( v12 > 0xF )
          v27 = v11;
        if ( v9 != 8 || memcmp_0(v27, "work_dir", 8u) )
        {
          v30 = Buf1;
          if ( v12 > 0xF )
            v30 = v11;
          if ( v9 == 3 )
          {
            v31 = *(_BYTE *)v30 < 0x65u;
            if ( *(_BYTE *)v30 == 101
              && (v31 = *((_BYTE *)v30 + 1) < 0x6Eu, *((_BYTE *)v30 + 1) == 110)
              && (v31 = *((_BYTE *)v30 + 2) < 0x76u, *((_BYTE *)v30 + 2) == 118) )
            {
              v32 = 0;
            }
            else
            {
              v32 = v31 ? -1 : 1;
            }
            if ( !v32 )
            {
              if ( (unsigned int)lua_type(this, -1) != 5 )
                luaL_argerror(this, 2, "env should be (key/value) table");
              lua_pushnil(this);
              std::optional<std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>>::emplace<>(v101);
              while ( (unsigned int)lua_next(this, -2) )
              {
                if ( (unsigned int)lua_type(this, -2) != 4 )
                  luaL_argerror(this, 2, "env key should be string");
                v33 = lua_tolstring(this, -2, 0);
                windiag::char_to_wstring(&v109, v33);
                if ( (unsigned int)lua_type(this, -1) != 4 )
                  luaL_argerror(this, 1, "env value should be string");
                v34 = lua_tolstring(this, -1, 0);
                windiag::char_to_wstring(PipeAttributes, v34);
                v35 = &v109;
                if ( *((_QWORD *)&v110 + 1) > 7u )
                  v35 = (__int128 *)v109;
                v36 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
                        v102,
                        v35,
                        v110);
                v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36);
                v38 = PipeAttributes;
                if ( *(_QWORD *)&PipeAttributes[24] > 7u )
                  v38 = *(_BYTE **)PipeAttributes;
                v39 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
                        v37,
                        v38,
                        *(_QWORD *)&PipeAttributes[16]);
                std::basic_ostream<unsigned short>::operator<<(v39, 0);
                lua_settop(this, -2);
                std::wstring::~wstring(PipeAttributes);
                std::wstring::~wstring(&v109);
              }
              v40 = std::basic_ostream<unsigned short>::operator<<(v102, 0);
              std::basic_ostream<unsigned short>::operator<<(v40, 0);
            }
          }
          goto LABEL_89;
        }
        v28 = lua_tolstring(this, -1, 0);
        v29 = windiag::char_to_wstring(v115, v28);
        if ( v92 )
        {
          std::wstring::operator=(v90, v29);
        }
        else
        {
          *(_OWORD *)v90 = 0;
          v91 = 0;
          v90[0] = *(LPCWSTR *)v29;
          v90[1] = *(LPCWSTR *)(v29 + 8);
          v91 = *(_OWORD *)(v29 + 16);
          *(_QWORD *)(v29 + 16) = 0;
          *(_QWORD *)(v29 + 24) = 7;
          *(_WORD *)v29 = 0;
          v92 = 1;
        }
        v15 = v115;
LABEL_15:
        std::wstring::~wstring(v15);
LABEL_89:
        LODWORD(v5) = dwProcessId[0];
        goto LABEL_90;
      }
      v5 = lua_tointegerx(this, -1, 0);
      *(_QWORD *)dwProcessId = v5;
      v78 = 1;
LABEL_90:
      v4 = (char)TokenInformation;
LABEL_91:
      lua_settop(this, -2);
      std::string::~string(Buf1);
      if ( !(unsigned int)lua_next(this, 1) )
        goto LABEL_94;
    }
    v3 = (unsigned int)lua_toboolean(this, -1) != 0;
    goto LABEL_89;
  }
  v84 = (unsigned int)TokenInformation;
LABEL_94:
  if ( v98 )
  {
    v2 = (const WCHAR *)&v96;
    if ( *((_QWORD *)&v97 + 1) > 7u )
      v2 = (const WCHAR *)v96;
    if ( v2 )
    {
      if ( !v89 )
      {
LABEL_109:
        v44 = 0;
        goto LABEL_110;
      }
      memset(PipeAttributes, 0, sizeof(PipeAttributes));
      std::wstring::_Construct<1,unsigned short const *>(PipeAttributes, L"\" ");
      LOWORD(TokenInformation) = 34;
      v109 = 0;
      v110 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v109, &TokenInformation);
      v41 = std::operator+<unsigned short>(v113, &v109, v2);
      v42 = std::operator+<unsigned short>(v114, v41, PipeAttributes);
      v43 = std::operator+<unsigned short>(v115, v42, v87);
      if ( v89 )
      {
        std::wstring::operator=(v87, v43);
      }
      else
      {
        *(_OWORD *)v87 = 0;
        v88 = 0;
        v87[0] = *(LPWSTR *)v43;
        v87[1] = *(LPWSTR *)(v43 + 8);
        v88 = *(_OWORD *)(v43 + 16);
        *(_QWORD *)(v43 + 16) = 0;
        *(_QWORD *)(v43 + 24) = 7;
        *(_WORD *)v43 = 0;
        v89 = 1;
      }
      std::wstring::~wstring(v115);
      std::wstring::~wstring(v114);
      std::wstring::~wstring(v113);
      std::wstring::~wstring(&v109);
      std::wstring::~wstring(PipeAttributes);
    }
  }
  else if ( !v89 )
  {
    luaL_error(this, "'exe_path' and/or 'cmd_line' must be present in process create table");
  }
  if ( !v89 )
    goto LABEL_109;
  v44 = (WCHAR *)v87;
  if ( *((_QWORD *)&v88 + 1) > 7u )
    v44 = v87[0];
LABEL_110:
  lpCommandLine = v44;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  if ( v95 )
  {
    v45 = (WCHAR *)&v93;
    if ( *((_QWORD *)&v94 + 1) > 7u )
      v45 = (WCHAR *)v93;
    StartupInfo.lpDesktop = v45;
  }
  hReadPipe = 0;
  hWritePipe = 0;
  if ( v75 )
  {
    StartupInfo.dwFlags = 256;
    *(_OWORD *)PipeAttributes = 0x18u;
    *(_QWORD *)&PipeAttributes[16] = 1;
    hWritePipe = 0;
    hReadPipe = 0;
    if ( !CreatePipe(&hReadPipe, &hWritePipe, (LPSECURITY_ATTRIBUTES)PipeAttributes, 0) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          LastError,
          0,
          "[%s:%d] failed; ",
          "security_create_process",
          308);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    StartupInfo.hStdError = hWritePipe;
    StartupInfo.hStdOutput = hWritePipe;
  }
  if ( v4 )
    dwCreationFlags = (v3 ? 4 : 0) | (v6 ? 16 : 0x8000000);
  else
    dwCreationFlags = v3 ? 4 : 0;
  lpEnvironment = 0;
  v111 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v111) = 0;
  if ( v104 )
  {
    dwCreationFlags |= 0x400u;
    std::basic_stringbuf<unsigned short>::str(v103, &v109);
    std::wstring::operator=(&v111, &v109);
    std::wstring::~wstring(&v109);
    lpEnvironment = &v111;
    if ( si128.m128i_i64[1] > 7uLL )
      lpEnvironment = (__int128 *)v111;
  }
  if ( v92 )
  {
    lpCurrentDirectory = (const WCHAR *)v90;
    if ( *((_QWORD *)&v91 + 1) > 7u )
      lpCurrentDirectory = v90[0];
  }
  else
  {
    lpCurrentDirectory = 0;
  }
  if ( v78 )
  {
    v50 = OpenProcess(0x1000u, 0, v5);
    v86 = v50;
    if ( !v50 )
    {
      v51 = GetLastError();
      if ( v51 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v51,
          0,
          "[%s:%d] failed; ",
          "security_create_process",
          329);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    TokenHandle = 0;
    if ( !OpenProcessToken(v50, 0x2000000u, &TokenHandle) )
    {
      v52 = GetLastError();
      if ( v52 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v52,
          0,
          "[%s:%d] failed; ",
          "security_create_process",
          332);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    *(_QWORD *)dwProcessId = 0;
    if ( !DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, (PHANDLE)dwProcessId) )
    {
      v54 = GetLastError();
      if ( v54 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v54,
          0,
          "[%s:%d] failed; ",
          "security_create_process",
          336);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    if ( v76 )
    {
      LODWORD(TokenInformation) = v84;
      LOBYTE(v53) = 1;
      windiag::enable_privilege(&v84, L"SeTcbPrivilege", v53);
      if ( !SetTokenInformation(*(HANDLE *)dwProcessId, TokenSessionId, &TokenInformation, 4u) )
      {
        v55 = GetLastError();
        if ( v55 )
        {
          windiag::system_exception::system_exception(
            (windiag::system_exception *)pExceptionObject,
            v55,
            0,
            "[%s:%d] failed; ",
            "security_create_process",
            341);
          throw (windiag::system_exception *)pExceptionObject;
        }
      }
      v56 = v85;
      if ( v85 )
      {
        if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
          if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
        }
      }
    }
    LOBYTE(v53) = 1;
    windiag::enable_privilege(&v84, L"SeAssignPrimaryTokenPrivilege", v53);
    if ( !CreateProcessAsUserW(
            *(HANDLE *)dwProcessId,
            v2,
            lpCommandLine,
            0,
            0,
            v75,
            dwCreationFlags,
            lpEnvironment,
            lpCurrentDirectory,
            &StartupInfo,
            &ProcessInformation) )
    {
      v57 = GetLastError();
      if ( v57 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v57,
          0,
          "[%s:%d] failed; ",
          "security_create_process",
          346);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    v58 = v85;
    if ( v85 )
    {
      if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
        if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
      }
    }
    v59 = *(HANDLE *)dwProcessId;
    if ( *(_QWORD *)dwProcessId )
    {
      *(_QWORD *)dwProcessId = 0;
      CloseHandle(v59);
    }
    *(_QWORD *)dwProcessId = 0;
    v60 = TokenHandle;
    if ( TokenHandle )
    {
      TokenHandle = 0;
      CloseHandle(v60);
    }
    TokenHandle = 0;
    if ( v50 )
      CloseHandle(v50);
  }
  else if ( !CreateProcessW(
               v2,
               v44,
               0,
               0,
               v75,
               dwCreationFlags,
               lpEnvironment,
               lpCurrentDirectory,
               &StartupInfo,
               &ProcessInformation) )
  {
    v67 = GetLastError();
    if ( v67 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v67,
        0,
        "[%s:%d] failed; ",
        "security_create_process",
        349);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  hProcess = ProcessInformation.hProcess;
  TokenInformation = ProcessInformation.hProcess;
  hThread = ProcessInformation.hThread;
  *(_QWORD *)dwProcessId = ProcessInformation.hThread;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl'::`2'::impl) )
  {
    v64 = windiag::lua_stop_event(this, v63);
    v65 = lua_newuserdatauv(this, 0x50u, 0);
    luaL_setmetatable(this, "security.process");
    v66 = (WCHAR *)hReadPipe;
    hReadPipe = 0;
    lpCommandLine = v66;
    *(_QWORD *)dwProcessId = 0;
    v84 = (__int64)hThread;
    TokenInformation = 0;
    TokenHandle = hProcess;
    anonymous_namespace_::security_process_state::security_process_state(v65, (__int64)&lpCommandLine, (__int64)v64);
  }
  else
  {
    v68 = lua_newuserdatauv(this, 0x50u, 0);
    v70 = windiag::lua_stop_event(this, v69);
    v71 = (WCHAR *)hReadPipe;
    hReadPipe = 0;
    lpCommandLine = v71;
    *(_QWORD *)dwProcessId = 0;
    v84 = (__int64)hThread;
    TokenInformation = 0;
    TokenHandle = hProcess;
    anonymous_namespace_::security_process_state::security_process_state(v68, (__int64)&lpCommandLine, (__int64)v70);
    luaL_setmetatable(this, "security.process");
  }
  std::wstring::~wstring(&v111);
  v72 = hWritePipe;
  if ( hWritePipe )
  {
    hWritePipe = 0;
    CloseHandle(v72);
  }
  hWritePipe = 0;
  v73 = hReadPipe;
  if ( hReadPipe )
  {
    hReadPipe = 0;
    CloseHandle(v73);
  }
  hReadPipe = 0;
  if ( v104 )
    (**(void (__fastcall ***)(char *, _QWORD))((char *)v101 + *(int *)(v101[0] + 4LL)))(
      (char *)v101 + *(int *)(v101[0] + 4LL),
      0);
  if ( v92 )
    std::wstring::~wstring(v90);
  if ( v95 )
    std::wstring::~wstring(&v93);
  if ( v89 )
    std::wstring::~wstring(v87);
  if ( v98 )
    std::wstring::~wstring(&v96);
  return 1;
}

```

## disassembly

```asm
0x180081a00  push    rbp
0x180081a02  push    rbx
0x180081a03  push    rsi
0x180081a04  push    rdi
0x180081a05  push    r12
0x180081a07  push    r13
0x180081a09  push    r14
0x180081a0b  push    r15
0x180081a0d  lea     rbp, [rsp-728h]
0x180081a15  sub     rsp, 828h
0x180081a1c  mov     rax, cs:__security_cookie
0x180081a23  xor     rax, rsp
0x180081a26  mov     [rbp+760h+var_50], rax
0x180081a2d  mov     rsi, rcx
0x180081a30  xor     r15d, r15d
0x180081a33  lea     edx, [r15+1]; int
0x180081a37  lea     r8d, [r15+5]; int
0x180081a3b  call    ?luaL_checktype@@YAXPEAUlua_State@@HH@Z; luaL_checktype(lua_State *,int,int)
0x180081a40  mov     [rbp+760h+var_710], r15b
0x180081a44  mov     [rbp+760h+var_788], r15b
0x180081a48  mov     [rbp+760h+var_738], r15b
0x180081a4c  mov     [rbp+760h+var_760], r15b
0x180081a50  mov     [rsp+860h+var_7F0], r15b
0x180081a55  mov     [rsp+860h+var_7FF], r15b
0x180081a5a  mov     r13b, r15b
0x180081a5d  mov     [rsp+860h+var_800], r15b
0x180081a62  mov     dil, r15b
0x180081a65  mov     byte ptr [rsp+860h+TokenInformation], r15b
0x180081a6a  mov     [rbp+760h+var_588], r15b
0x180081a71  mov     rcx, rsi; struct lua_State *
0x180081a74  call    ?lua_pushnil@@YAXPEAUlua_State@@@Z; lua_pushnil(lua_State *)
0x180081a79  lea     edx, [r15+1]; int
0x180081a7d  mov     rcx, rsi; struct lua_State *
0x180081a80  call    ?lua_next@@YAHPEAUlua_State@@H@Z; lua_next(lua_State *,int)
0x180081a85  mov     r14d, dword ptr [rsp+860h+TokenInformation]
0x180081a8a  mov     r12b, [rsp+860h+var_7FF]
0x180081a8f  test    eax, eax
0x180081a91  jz      loc_180082144
0x180081a97  mov     ebx, dword ptr [rsp+860h+TokenInformation]
0x180081a9b  mov     [rbp+760h+var_7C0], rbx
0x180081a9f  mov     qword ptr [rsp+860h+dwProcessId], r14
0x180081aa4  mov     edx, 0FFFFFFFEh; int
0x180081aa9  mov     rcx, rsi; struct lua_State *
0x180081aac  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x180081ab1  cmp     eax, 4
0x180081ab4  jz      short loc_180081ACA
0x180081ab6  lea     r8, aTableKeyShould; "table key should be string"
0x180081abd  mov     edx, 2; int
0x180081ac2  mov     rcx, rsi; struct lua_State *
0x180081ac5  call    ?luaL_argerror@@YAHPEAUlua_State@@HPEBD@Z; luaL_argerror(lua_State *,int,char const *)
0x180081aca  xor     r8d, r8d; unsigned __int64 *
0x180081acd  lea     edx, [r8-2]; int
0x180081ad1  mov     rcx, rsi; struct lua_State *
0x180081ad4  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x180081ad9  xorps   xmm0, xmm0
0x180081adc  movups  xmmword ptr [rbp+760h+Buf1], xmm0
0x180081ae3  mov     [rbp+760h+Size], r15
0x180081aea  mov     [rbp+760h+var_568], r15
0x180081af1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180081af5  inc     r8
0x180081af8  cmp     [rax+r8], r15b
0x180081afc  jnz     short loc_180081AF5
0x180081afe  mov     rdx, rax
0x180081b01  lea     rcx, [rbp+760h+Buf1]
0x180081b08  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180081b0d  nop
0x180081b0e  mov     rbx, [rbp+760h+Size]
0x180081b15  lea     rcx, [rbp+760h+Buf1]
0x180081b1c  mov     rdi, [rbp+760h+Buf1]
0x180081b23  mov     r14, [rbp+760h+var_568]
0x180081b2a  cmp     r14, 0Fh
0x180081b2e  cmova   rcx, rdi; Buf1
0x180081b32  cmp     rbx, 8
0x180081b36  jnz     loc_180081BDA
0x180081b3c  mov     r8, rbx; Size
0x180081b3f  lea     rdx, aExePath; "exe_path"
0x180081b46  call    memcmp_0
0x180081b4b  test    eax, eax
0x180081b4d  jnz     loc_180081BDA
0x180081b53  xor     r8d, r8d; unsigned __int64 *
0x180081b56  or      edx, 0FFFFFFFFh; int
0x180081b59  mov     rcx, rsi; struct lua_State *
0x180081b5c  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x180081b61  mov     rdx, rax
0x180081b64  lea     rcx, [rbp+760h+var_4A0]
0x180081b6b  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180081b70  mov     rcx, rax
0x180081b73  cmp     [rbp+760h+var_710], r15b
0x180081b77  jz      short loc_180081B87
0x180081b79  mov     rdx, rax
0x180081b7c  lea     rcx, [rbp+760h+var_730]
0x180081b80  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180081b85  jmp     short loc_180081BC9
0x180081b87  xorps   xmm0, xmm0
0x180081b8a  movups  [rbp+760h+var_730], xmm0
0x180081b8e  xorps   xmm1, xmm1
0x180081b91  movdqu  [rbp+760h+var_720], xmm1
0x180081b96  mov     rax, [rax]
0x180081b99  mov     qword ptr [rbp+760h+var_730], rax
0x180081b9d  mov     rax, [rcx+8]
0x180081ba1  mov     qword ptr [rbp+760h+var_730+8], rax
0x180081ba5  mov     rax, [rcx+10h]
0x180081ba9  mov     qword ptr [rbp+760h+var_720], rax
0x180081bad  mov     rax, [rcx+18h]
0x180081bb1  mov     qword ptr [rbp+760h+var_720+8], rax
0x180081bb5  mov     [rcx+10h], r15
0x180081bb9  mov     qword ptr [rcx+18h], 7
0x180081bc1  mov     [rcx], r15w
0x180081bc5  mov     [rbp+760h+var_710], 1
0x180081bc9  lea     rcx, [rbp+760h+var_4A0]
0x180081bd0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180081bd5  jmp     loc_180082109
0x180081bda  lea     rcx, [rbp+760h+Buf1]
0x180081be1  cmp     r14, 0Fh
0x180081be5  cmova   rcx, rdi; Buf1
0x180081be9  cmp     rbx, 8
0x180081bed  jnz     loc_180081C8C
0x180081bf3  mov     r8, rbx; Size
0x180081bf6  lea     rdx, aCmdLine; "cmd_line"
0x180081bfd  call    memcmp_0
0x180081c02  test    eax, eax
0x180081c04  jnz     loc_180081C8C
0x180081c0a  xor     r8d, r8d; unsigned __int64 *
0x180081c0d  or      edx, 0FFFFFFFFh; int
0x180081c10  mov     rcx, rsi; struct lua_State *
0x180081c13  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x180081c18  mov     rdx, rax
0x180081c1b  lea     rcx, [rbp+760h+var_500]
0x180081c22  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180081c27  mov     rcx, rax
0x180081c2a  cmp     [rbp+760h+var_788], r15b
0x180081c2e  jz      short loc_180081C3E
0x180081c30  mov     rdx, rax
0x180081c33  lea     rcx, [rbp+760h+var_7A8]
0x180081c37  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180081c3c  jmp     short loc_180081C80
0x180081c3e  xorps   xmm0, xmm0
0x180081c41  movups  xmmword ptr [rbp+760h+var_7A8], xmm0
0x180081c45  xorps   xmm1, xmm1
0x180081c48  movdqu  [rbp+760h+var_798], xmm1
0x180081c4d  mov     rax, [rax]
0x180081c50  mov     [rbp+760h+var_7A8], rax
0x180081c54  mov     rax, [rcx+8]
0x180081c58  mov     [rbp+760h+var_7A8+8], rax
0x180081c5c  mov     rax, [rcx+10h]
0x180081c60  mov     qword ptr [rbp+760h+var_798], rax
0x180081c64  mov     rax, [rcx+18h]
0x180081c68  mov     qword ptr [rbp+760h+var_798+8], rax
0x180081c6c  mov     [rcx+10h], r15
0x180081c70  mov     qword ptr [rcx+18h], 7
0x180081c78  mov     [rcx], r15w
0x180081c7c  mov     [rbp+760h+var_788], 1
0x180081c80  lea     rcx, [rbp+760h+var_500]
0x180081c87  jmp     loc_180081BD0
0x180081c8c  lea     rcx, [rbp+760h+Buf1]
0x180081c93  cmp     r14, 0Fh
0x180081c97  cmova   rcx, rdi; Buf1
0x180081c9b  cmp     rbx, 7
0x180081c9f  jnz     loc_180081D3E
0x180081ca5  mov     r8, rbx; Size
0x180081ca8  lea     rdx, aDesktop; "desktop"
0x180081caf  call    memcmp_0
0x180081cb4  test    eax, eax
0x180081cb6  jnz     loc_180081D3E
0x180081cbc  xor     r8d, r8d; unsigned __int64 *
0x180081cbf  or      edx, 0FFFFFFFFh; int
0x180081cc2  mov     rcx, rsi; struct lua_State *
0x180081cc5  call    ?lua_tolstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; lua_tolstring(lua_State *,int,unsigned __int64 *)
0x180081cca  mov     rdx, rax
0x180081ccd  lea     rcx, [rbp+760h+var_4E0]
0x180081cd4  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x180081cd9  mov     rcx, rax
0x180081cdc  cmp     [rbp+760h+var_738], r15b
0x180081ce0  jz      short loc_180081CF0
0x180081ce2  mov     rdx, rax
0x180081ce5  lea     rcx, [rbp+760h+var_758]
0x180081ce9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180081cee  jmp     short loc_180081D32
0x180081cf0  xorps   xmm0, xmm0
0x180081cf3  movups  [rbp+760h+var_758], xmm0
0x180081cf7  xorps   xmm1, xmm1
0x180081cfa  movdqu  [rbp+760h+var_748], xmm1
0x180081cff  mov     rax, [rax]
0x180081d02  mov     qword ptr [rbp+760h+var_758], rax
0x180081d06  mov     rax, [rcx+8]
0x180081d0a  mov     qword ptr [rbp+760h+var_758+8], rax
0x180081d0e  mov     rax, [rcx+10h]
0x180081d12  mov     qword ptr [rbp+760h+var_748], rax
0x180081d16  mov     rax, [rcx+18h]
0x180081d1a  mov     qword ptr [rbp+760h+var_748+8], rax
0x180081d1e  mov     [rcx+10h], r15
0x180081d22  mov     qword ptr [rcx+18h], 7
0x180081d2a  mov     [rcx], r15w
0x180081d2e  mov     [rbp+760h+var_738], 1
0x180081d32  lea     rcx, [rbp+760h+var_4E0]
0x180081d39  jmp     loc_180081BD0
0x180081d3e  lea     rcx, [rbp+760h+Buf1]
0x180081d45  cmp     r14, 0Fh
0x180081d49  cmova   rcx, rdi; Buf1
0x180081d4d  cmp     rbx, 7
0x180081d51  jnz     short loc_180081D9E
0x180081d53  mov     r8, rbx; Size
0x180081d56  lea     rdx, aConsole; "console"
0x180081d5d  call    memcmp_0
0x180081d62  test    eax, eax
0x180081d64  jnz     short loc_180081D9E
0x180081d66  or      edx, 0FFFFFFFFh; int
0x180081d69  mov     rcx, rsi; struct lua_State *
0x180081d6c  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180081d71  mov     dil, byte ptr [rsp+860h+TokenInformation]
0x180081d76  mov     r14, qword ptr [rsp+860h+dwProcessId]
0x180081d7b  test    dil, dil
0x180081d7e  jz      short loc_180081D8B
0x180081d80  test    eax, eax
0x180081d82  setnz   r12b
0x180081d86  jmp     loc_180082113
0x180081d8b  test    eax, eax
0x180081d8d  setnz   r12b
0x180081d91  mov     dil, 1
0x180081d94  mov     byte ptr [rsp+860h+TokenInformation], dil
0x180081d99  jmp     loc_180082113
0x180081d9e  lea     rcx, [rbp+760h+Buf1]
0x180081da5  cmp     r14, 0Fh
0x180081da9  cmova   rcx, rdi; Buf1
0x180081dad  cmp     rbx, 9
0x180081db1  jnz     short loc_180081DDC
0x180081db3  mov     r8, rbx; Size
0x180081db6  lea     rdx, aSuspended; "suspended"
0x180081dbd  call    memcmp_0
0x180081dc2  test    eax, eax
0x180081dc4  jnz     short loc_180081DDC
0x180081dc6  or      edx, 0FFFFFFFFh; int
0x180081dc9  mov     rcx, rsi; struct lua_State *
0x180081dcc  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180081dd1  test    eax, eax
0x180081dd3  setnz   r13b
0x180081dd7  jmp     loc_180082109
0x180081ddc  lea     rcx, [rbp+760h+Buf1]
0x180081de3  cmp     r14, 0Fh
0x180081de7  cmova   rcx, rdi; Buf1
0x180081deb  cmp     rbx, 0Ah
0x180081def  jnz     short loc_180081E1B
0x180081df1  mov     r8, rbx; Size
0x180081df4  lea     rdx, aRedirected; "redirected"
0x180081dfb  call    memcmp_0
0x180081e00  test    eax, eax
0x180081e02  jnz     short loc_180081E1B
0x180081e04  or      edx, 0FFFFFFFFh; int
0x180081e07  mov     rcx, rsi; struct lua_State *
0x180081e0a  call    ?lua_toboolean@@YAHPEAUlua_State@@H@Z; lua_toboolean(lua_State *,int)
0x180081e0f  test    eax, eax
0x180081e11  setnz   [rsp+860h+var_800]
0x180081e16  jmp     loc_180082109
0x180081e1b  lea     rcx, [rbp+760h+Buf1]
0x180081e22  cmp     r14, 0Fh
0x180081e26  cmova   rcx, rdi; Buf1
0x180081e2a  cmp     rbx, 6
0x180081e2e  jnz     short loc_180081E63
0x180081e30  mov     r8, rbx; Size
0x180081e33  lea     rdx, aAsPid; "as_pid"
0x180081e3a  call    memcmp_0
0x180081e3f  test    eax, eax
0x180081e41  jnz     short loc_180081E63
0x180081e43  xor     r8d, r8d; int *
0x180081e46  or      edx, 0FFFFFFFFh; int
0x180081e49  mov     rcx, rsi; struct lua_State *
0x180081e4c  call    ?lua_tointegerx@@YA_JPEAUlua_State@@HPEAH@Z; lua_tointegerx(lua_State *,int,int *)
0x180081e51  mov     r14, rax
0x180081e54  mov     qword ptr [rsp+860h+dwProcessId], rax
0x180081e59  mov     [rsp+860h+var_7F0], 1
0x180081e5e  jmp     loc_18008210E
0x180081e63  lea     rcx, [rbp+760h+Buf1]
0x180081e6a  cmp     r14, 0Fh
0x180081e6e  cmova   rcx, rdi; Buf1
0x180081e72  cmp     rbx, 0Ah
0x180081e76  jnz     short loc_180081EA7
0x180081e78  mov     r8, rbx; Size
0x180081e7b  lea     rdx, aSessionId; "session_id"
0x180081e82  call    memcmp_0
0x180081e87  test    eax, eax
0x180081e89  jnz     short loc_180081EA7
0x180081e8b  xor     r8d, r8d; int *
0x180081e8e  or      edx, 0FFFFFFFFh; int
0x180081e91  mov     rcx, rsi; struct lua_State *
0x180081e94  call    ?lua_tointegerx@@YA_JPEAUlua_State@@HPEAH@Z; lua_tointegerx(lua_State *,int,int *)
0x180081e99  mov     [rbp+760h+var_7C0], rax
0x180081e9d  mov     [rsp+860h+var_7FF], 1
0x180081ea2  jmp     loc_180082109
0x180081ea7  lea     rcx, [rbp+760h+Buf1]
0x180081eae  cmp     r14, 0Fh
0x180081eb2  cmova   rcx, rdi; Buf1
0x180081eb6  cmp     rbx, 8
0x180081eba  jnz     loc_180081F59
0x180081ec0  mov     r8, rbx; Size
0x180081ec3  lea     rdx, aWorkDir; "work_dir"
0x180081eca  call    memcmp_0
0x180081ecf  test    eax, eax
0x180081ed1  jnz     loc_180081F59
0x180081ed7  xor     r8d, r8d; unsigned __int64 *
0x180081eda  or      edx, 0FFFFFFFFh; int
  ... truncated ...
```
