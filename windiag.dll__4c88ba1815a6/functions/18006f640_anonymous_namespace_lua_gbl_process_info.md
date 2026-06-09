# _anonymous_namespace_::lua_gbl_process_info

- ea: `0x18006f640`
- end: `0x18006fbdf`
- name: `_anonymous_namespace_::lua_gbl_process_info`
- size: `1439`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180006050`
- `0x180006690`
- `0x180006b00`
- `0x180006c50`
- `0x180006d40`
- `0x180007160`
- `0x1800083a0`
- `0x18003b0bc`
- `0x180040e00`
- `0x180040f94`
- `0x180041564`
- `0x1800415d0`
- `0x180041e58`
- `0x1800428b4`
- `0x180049674`
- `0x18006f640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f9d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f9d1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006f9dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006f9dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fa1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fbb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fa1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006fbb0`
- `ntdll!NtQueryInformationProcess` at `0x18006f704`
- `ntdll!NtQueryInformationProcess` at `0x18006f76a`
- `ntdll!NtQueryInformationProcess` at `0x18006f7ff`
- `ntdll!NtQueryInformationProcess` at `0x18006f8b6`
- `ntdll!NtQueryInformationProcess` at `0x18006f995`
- `ntdll!NtQueryInformationProcess` at `0x18006fa84`
- `ntdll!NtQueryInformationProcess` at `0x18006fad5`
- `ntdll!NtQueryInformationProcess` at `0x18006f704`
- `ntdll!NtQueryInformationProcess` at `0x18006f76a`
- `ntdll!NtQueryInformationProcess` at `0x18006f7ff`
- `ntdll!NtQueryInformationProcess` at `0x18006f8b6`
- `ntdll!NtQueryInformationProcess` at `0x18006f995`
- `ntdll!NtQueryInformationProcess` at `0x18006fa84`
- `ntdll!NtQueryInformationProcess` at `0x18006fad5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006f6a2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006f9f1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006f6a2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006f9f1`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x18006fa0b`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x18006fa0b`

## string_xrefs

- `0x18006f816`: `create_time`
- `0x18006f789`: `commit_bytes`
- `0x18006f93d`: `image_path`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall anonymous_namespace_::lua_gbl_process_info(struct lua_State *a1)
{
  DWORD v2; // r13d
  int v3; // r14d
  HANDLE v4; // rbx
  int v5; // r12d
  int v6; // eax
  ULONG v7; // eax
  __int64 v8; // rdx
  __int64 *v9; // rdx
  __int64 v10; // rax
  HANDLE v11; // rax
  void *v12; // r15
  BOOL v13; // edi
  unsigned int v14; // ecx
  __int64 *v15; // rdx
  __int64 v16; // rax
  ULONG ProcessInformation; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v19[2]; // [rsp+34h] [rbp-CCh] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-C8h] BYREF
  PVOID v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h]
  HANDLE v23; // [rsp+58h] [rbp-A8h]
  __int64 v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25[2]; // [rsp+70h] [rbp-90h]
  char *v26[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[72]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v28; // [rsp+E8h] [rbp-18h]
  __int64 v29; // [rsp+100h] [rbp+0h]

  v2 = luaL_checkinteger(a1, 1);
  v3 = -1;
  if ( (int)lua_gettop(a1) > 1 )
    v3 = luaL_checkinteger(a1, 2);
  v4 = OpenProcess(0x1000u, 0, v2);
  v23 = v4;
  if ( !v4 )
    return 0;
  lua_createtable(a1, 0, 0);
  if ( v3 )
  {
    v5 = ProcessInformation;
    do
    {
      ReturnLength = 0;
      if ( (v3 & 1) != 0 )
      {
        ProcessInformation = 0;
        if ( NtQueryInformationProcess(v4, ProcessHandleCount, &ProcessInformation, 4u, &ReturnLength) >= 0 )
        {
          lua_pushinteger(a1, ProcessInformation);
          lua_setfield(a1, 4294967294LL, "handles");
        }
        v6 = -2;
        goto LABEL_59;
      }
      if ( (v3 & 2) != 0 )
      {
        memset_0(v27, 0, 0x70u);
        if ( NtQueryInformationProcess(v4, ProcessVmCounters, v27, 0x70u, &ReturnLength) >= 0 )
        {
          v7 = ReturnLength;
          if ( ReturnLength >= 0x58 )
          {
            lua_pushinteger(a1, v28);
            lua_setfield(a1, 4294967294LL, "commit_bytes");
            v7 = ReturnLength;
          }
          if ( v7 >= 0x70 )
          {
            lua_pushinteger(a1, v29);
            lua_setfield(a1, 4294967294LL, "ws_private_bytes");
          }
        }
        v6 = -3;
        goto LABEL_59;
      }
      if ( (v3 & 4) != 0 )
      {
        *(_OWORD *)v24 = 0;
        *(_OWORD *)v25 = 0;
        if ( NtQueryInformationProcess(v4, ProcessTimes, v24, 0x20u, &ReturnLength) >= 0 )
        {
          lua_pushinteger(a1, v24[0]);
          lua_setfield(a1, 4294967294LL, "create_time");
          lua_pushinteger(a1, v25[0]);
          lua_setfield(a1, 4294967294LL, "kernel_time");
          lua_pushinteger(a1, v25[1]);
          lua_setfield(a1, 4294967294LL, "user_time");
        }
        v6 = -5;
        goto LABEL_59;
      }
      if ( (v3 & 8) != 0 )
      {
        v19[0] = 0;
        std::vector<unsigned short>::vector<unsigned short>(&v21, 8208, v19);
        if ( NtQueryInformationProcess(v4, ProcessImageFileNameWin32, v21, (v22 - (__int64)v21) >> 1, &ReturnLength) >= 0 )
        {
          v8 = *((_QWORD *)v21 + 1);
          if ( v8 )
          {
            if ( *(_WORD *)v21 >= 2u )
            {
              *(_OWORD *)v24 = 0;
              *(_OWORD *)v25 = 0;
              std::wstring::_Construct<1,unsigned short const *>(
                v24,
                v8,
                (unsigned __int64)*(unsigned __int16 *)v21 >> 1);
              v9 = v24;
              if ( v25[1] > 7uLL )
                v9 = (__int64 *)v24[0];
              v10 = windiag::wchar_to_string(v26, v9);
              if ( *(_QWORD *)(v10 + 24) > 0xFu )
                v10 = *(_QWORD *)v10;
              lua_pushstring(a1, (const char *)v10);
              std::string::~string(v26);
              lua_setfield(a1, 4294967294LL, "image_path");
              std::wstring::~wstring((char **)v24);
            }
          }
        }
        std::vector<unsigned short>::~vector<unsigned short>(&v21);
        v6 = -9;
        goto LABEL_59;
      }
      if ( (v3 & 0x10) != 0 )
      {
        ProcessInformation = 0;
        if ( NtQueryInformationProcess(v4, ProcessSessionInformation, &ProcessInformation, 4u, &ReturnLength) >= 0 )
        {
          lua_pushinteger(a1, ProcessInformation);
          lua_setfield(a1, 4294967294LL, "session_id");
        }
        v6 = -17;
        goto LABEL_59;
      }
      if ( (v3 & 0x40) == 0 )
      {
        if ( (v3 & 0x20) == 0 )
          break;
        ProcessInformation = 0;
        if ( NtQueryInformationProcess(v4, ProcessImageFileMapping|ProcessUserModeIOPL, 0, 0, &ProcessInformation) == -1073741820
          && ProcessInformation >= 0x10 )
        {
          LOBYTE(v19[0]) = 0;
          std::vector<unsigned char>::vector<unsigned char>(&v21, ProcessInformation, v19);
          if ( NtQueryInformationProcess(
                 v4,
                 ProcessImageFileMapping|ProcessUserModeIOPL,
                 v21,
                 ProcessInformation,
                 &ProcessInformation) >= 0
            && ProcessInformation >= 0x10
            && *((PVOID *)v21 + 1) == (char *)v21 + 16 )
          {
            v14 = v22 - (_DWORD)v21 - 16;
            if ( v14 >= *(unsigned __int16 *)v21 )
              v14 = *(unsigned __int16 *)v21;
            ProcessInformation = v14;
            *(_OWORD *)v24 = 0;
            *(_OWORD *)v25 = 0;
            std::wstring::_Construct<1,unsigned short const *>(v24, *((_QWORD *)v21 + 1), (unsigned __int64)v14 >> 1);
            v15 = v24;
            if ( v25[1] > 7uLL )
              v15 = (__int64 *)v24[0];
            v16 = windiag::wchar_to_string(v26, v15);
            if ( *(_QWORD *)(v16 + 24) > 0xFu )
              v16 = *(_QWORD *)v16;
            lua_pushstring(a1, (const char *)v16);
            std::string::~string(v26);
            lua_setfield(a1, 4294967294LL, "cmd_line");
            std::wstring::~wstring((char **)v24);
          }
          std::vector<char>::~vector<char>((char **)&v21);
        }
        v6 = -33;
        goto LABEL_59;
      }
      if ( v2 == GetCurrentProcessId() )
      {
        v5 = IsDebuggerPresent();
      }
      else
      {
        v11 = OpenProcess(0x400u, 0, v2);
        v12 = v11;
        if ( !v11 )
          goto LABEL_43;
        ProcessInformation = 0;
        v13 = CheckRemoteDebuggerPresent(v11, (PBOOL)&ProcessInformation);
        if ( v13 )
          v5 = ProcessInformation;
        CloseHandle(v12);
        if ( !v13 )
          goto LABEL_43;
      }
      lua_pushboolean(a1, v5);
      lua_setfield(a1, 4294967294LL, "debugged");
LABEL_43:
      v6 = -65;
LABEL_59:
      v3 &= v6;
    }
    while ( v3 );
  }
  CloseHandle(v4);
  return 1;
}

```

## disassembly

```asm
0x18006f640  push    rbp
0x18006f642  push    rbx
0x18006f643  push    rsi
0x18006f644  push    rdi
0x18006f645  push    r12
0x18006f647  push    r13
0x18006f649  push    r14
0x18006f64b  push    r15
0x18006f64d  lea     rbp, [rsp-28h]
0x18006f652  sub     rsp, 128h
0x18006f659  mov     rax, cs:__security_cookie
0x18006f660  xor     rax, rsp
0x18006f663  mov     [rbp+60h+var_50], rax
0x18006f667  mov     rsi, rcx
0x18006f66a  mov     edx, 1; int
0x18006f66f  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006f674  mov     r13, rax
0x18006f677  or      r14d, 0FFFFFFFFh
0x18006f67b  mov     rcx, rsi; struct lua_State *
0x18006f67e  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18006f683  cmp     eax, 1
0x18006f686  jle     short loc_18006F698
0x18006f688  mov     edx, 2; int
0x18006f68d  mov     rcx, rsi; struct lua_State *
0x18006f690  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18006f695  mov     r14, rax
0x18006f698  mov     r8d, r13d; dwProcessId
0x18006f69b  xor     edx, edx; bInheritHandle
0x18006f69d  mov     ecx, 1000h; dwDesiredAccess
0x18006f6a2  call    cs:__imp_OpenProcess
0x18006f6a8  mov     rbx, rax
0x18006f6ab  mov     [rsp+160h+var_108], rax
0x18006f6b0  xor     edi, edi
0x18006f6b2  test    rax, rax
0x18006f6b5  jz      loc_18006FBBD
0x18006f6bb  xor     r8d, r8d; int
0x18006f6be  xor     edx, edx; int
0x18006f6c0  mov     rcx, rsi; struct lua_State *
0x18006f6c3  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x18006f6c8  test    r14d, r14d
0x18006f6cb  jz      loc_18006FBAD
0x18006f6d1  lea     r15d, [rdi-2]
0x18006f6d5  mov     r12d, [rsp+160h+ProcessInformation]
0x18006f6da  mov     [rsp+160h+var_128], edi
0x18006f6de  test    r14b, 1
0x18006f6e2  jz      short loc_18006F736
0x18006f6e4  mov     [rsp+160h+ProcessInformation], edi
0x18006f6e8  lea     rax, [rsp+160h+var_128]
0x18006f6ed  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18006f6f2  mov     r9d, 4; ProcessInformationLength
0x18006f6f8  lea     r8, [rsp+160h+ProcessInformation]; ProcessInformation
0x18006f6fd  lea     edx, [r9+10h]; ProcessInformationClass
0x18006f701  mov     rcx, rbx; ProcessHandle
0x18006f704  call    cs:__imp_NtQueryInformationProcess
0x18006f70a  test    eax, eax
0x18006f70c  js      short loc_18006F72C
0x18006f70e  mov     edx, [rsp+160h+ProcessInformation]; __int64
0x18006f712  mov     rcx, rsi; struct lua_State *
0x18006f715  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006f71a  lea     r8, aHandles; "handles"
0x18006f721  mov     edx, r15d; int
0x18006f724  mov     rcx, rsi; struct lua_State *
0x18006f727  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006f72c  mov     eax, 0FFFFFFFEh
0x18006f731  jmp     loc_18006FBA4
0x18006f736  test    r14b, 2
0x18006f73a  jz      loc_18006F7CC
0x18006f740  xor     edx, edx; Val
0x18006f742  lea     r8d, [rdx+70h]; Size
0x18006f746  lea     rcx, [rbp+60h+var_C0]; void *
0x18006f74a  call    memset_0
0x18006f74f  lea     rax, [rsp+160h+var_128]
0x18006f754  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18006f759  mov     r9d, 70h ; 'p'; ProcessInformationLength
0x18006f75f  lea     r8, [rbp+60h+var_C0]; ProcessInformation
0x18006f763  lea     edx, [r9-6Dh]; ProcessInformationClass
0x18006f767  mov     rcx, rbx; ProcessHandle
0x18006f76a  call    cs:__imp_NtQueryInformationProcess
0x18006f770  test    eax, eax
0x18006f772  js      short loc_18006F7C2
0x18006f774  mov     eax, [rsp+160h+var_128]
0x18006f778  cmp     eax, 58h ; 'X'
0x18006f77b  jb      short loc_18006F79F
0x18006f77d  mov     rdx, [rbp+60h+var_78]; __int64
0x18006f781  mov     rcx, rsi; struct lua_State *
0x18006f784  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006f789  lea     r8, aCommitBytes; "commit_bytes"
0x18006f790  mov     edx, r15d; int
0x18006f793  mov     rcx, rsi; struct lua_State *
0x18006f796  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006f79b  mov     eax, [rsp+160h+var_128]
0x18006f79f  cmp     eax, 70h ; 'p'
0x18006f7a2  jb      short loc_18006F7C2
0x18006f7a4  mov     rdx, [rbp+60h+var_60]; __int64
0x18006f7a8  mov     rcx, rsi; struct lua_State *
0x18006f7ab  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006f7b0  lea     r8, aWsPrivateBytes; "ws_private_bytes"
0x18006f7b7  mov     edx, r15d; int
0x18006f7ba  mov     rcx, rsi; struct lua_State *
0x18006f7bd  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006f7c2  mov     eax, 0FFFFFFFDh
0x18006f7c7  jmp     loc_18006FBA4
0x18006f7cc  test    r14b, 4
0x18006f7d0  jz      loc_18006F870
0x18006f7d6  xorps   xmm0, xmm0
0x18006f7d9  movups  xmmword ptr [rsp+160h+var_100], xmm0
0x18006f7de  movups  xmmword ptr [rsp+160h+var_F0], xmm0
0x18006f7e3  lea     rax, [rsp+160h+var_128]
0x18006f7e8  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18006f7ed  mov     r9d, 20h ; ' '; ProcessInformationLength
0x18006f7f3  lea     r8, [rsp+160h+var_100]; ProcessInformation
0x18006f7f8  lea     edx, [r9-1Ch]; ProcessInformationClass
0x18006f7fc  mov     rcx, rbx; ProcessHandle
0x18006f7ff  call    cs:__imp_NtQueryInformationProcess
0x18006f805  test    eax, eax
0x18006f807  js      short loc_18006F866
0x18006f809  mov     rdx, [rsp+160h+var_100]; __int64
0x18006f80e  mov     rcx, rsi; struct lua_State *
0x18006f811  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006f816  lea     r8, aCreateTime; "create_time"
0x18006f81d  mov     edx, r15d; int
0x18006f820  mov     rcx, rsi; struct lua_State *
0x18006f823  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006f828  mov     rdx, [rsp+160h+var_F0]; __int64
0x18006f82d  mov     rcx, rsi; struct lua_State *
0x18006f830  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006f835  lea     r8, aKernelTime; "kernel_time"
0x18006f83c  mov     edx, r15d; int
0x18006f83f  mov     rcx, rsi; struct lua_State *
0x18006f842  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006f847  mov     rdx, [rsp+160h+var_F0+8]; __int64
0x18006f84c  mov     rcx, rsi; struct lua_State *
0x18006f84f  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006f854  lea     r8, aUserTime; "user_time"
0x18006f85b  mov     edx, r15d; int
0x18006f85e  mov     rcx, rsi; struct lua_State *
0x18006f861  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006f866  mov     eax, 0FFFFFFFBh
0x18006f86b  jmp     loc_18006FBA4
0x18006f870  test    r14b, 8
0x18006f874  jz      loc_18006F96F
0x18006f87a  mov     [rsp+160h+var_12C], di
0x18006f87f  lea     r8, [rsp+160h+var_12C]
0x18006f884  mov     edx, 2010h
0x18006f889  lea     rcx, [rsp+160h+var_120]
0x18006f88e  call    ??$?0V?$allocator@G@std@@$0A@@?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBGAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,ushort const &,std::allocator<ushort> const &)
0x18006f893  nop
0x18006f894  mov     r8, [rsp+160h+var_120]; ProcessInformation
0x18006f899  mov     r9, [rsp+160h+var_118]
0x18006f89e  sub     r9, r8
0x18006f8a1  sar     r9, 1; ProcessInformationLength
0x18006f8a4  lea     rax, [rsp+160h+var_128]
0x18006f8a9  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18006f8ae  mov     edx, 2Bh ; '+'; ProcessInformationClass
0x18006f8b3  mov     rcx, rbx; ProcessHandle
0x18006f8b6  call    cs:__imp_NtQueryInformationProcess
0x18006f8bc  test    eax, eax
0x18006f8be  js      loc_18006F95B
0x18006f8c4  mov     rax, [rsp+160h+var_120]
0x18006f8c9  mov     rdx, [rax+8]
0x18006f8cd  test    rdx, rdx
0x18006f8d0  jz      loc_18006F95B
0x18006f8d6  mov     ecx, 2
0x18006f8db  cmp     [rax], cx
0x18006f8de  jb      short loc_18006F95B
0x18006f8e0  xorps   xmm0, xmm0
0x18006f8e3  movups  xmmword ptr [rsp+160h+var_100], xmm0
0x18006f8e8  xorps   xmm1, xmm1
0x18006f8eb  movdqu  xmmword ptr [rsp+160h+var_F0], xmm1
0x18006f8f1  movzx   r8d, word ptr [rax]
0x18006f8f5  shr     r8, 1
0x18006f8f8  lea     rcx, [rsp+160h+var_100]
0x18006f8fd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006f902  nop
0x18006f903  lea     rdx, [rsp+160h+var_100]
0x18006f908  cmp     [rsp+160h+var_F0+8], 7
0x18006f90e  cmova   rdx, [rsp+160h+var_100]
0x18006f914  lea     rcx, [rbp+60h+var_E0]
0x18006f918  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x18006f91d  nop
0x18006f91e  cmp     qword ptr [rax+18h], 0Fh
0x18006f923  jbe     short loc_18006F928
0x18006f925  mov     rax, [rax]
0x18006f928  mov     rdx, rax; char *
0x18006f92b  mov     rcx, rsi; struct lua_State *
0x18006f92e  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18006f933  nop
0x18006f934  lea     rcx, [rbp+60h+var_E0]
0x18006f938  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18006f93d  lea     r8, aImagePath; "image_path"
0x18006f944  mov     edx, r15d; int
0x18006f947  mov     rcx, rsi; struct lua_State *
0x18006f94a  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006f94f  nop
0x18006f950  lea     rcx, [rsp+160h+var_100]
0x18006f955  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006f95a  nop
0x18006f95b  lea     rcx, [rsp+160h+var_120]
0x18006f960  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18006f965  mov     eax, 0FFFFFFF7h
0x18006f96a  jmp     loc_18006FBA4
0x18006f96f  test    r14b, 10h
0x18006f973  jz      short loc_18006F9C7
0x18006f975  mov     [rsp+160h+ProcessInformation], edi
0x18006f979  lea     rax, [rsp+160h+var_128]
0x18006f97e  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18006f983  mov     r9d, 4; ProcessInformationLength
0x18006f989  lea     r8, [rsp+160h+ProcessInformation]; ProcessInformation
0x18006f98e  lea     edx, [r9+14h]; ProcessInformationClass
0x18006f992  mov     rcx, rbx; ProcessHandle
0x18006f995  call    cs:__imp_NtQueryInformationProcess
0x18006f99b  test    eax, eax
0x18006f99d  js      short loc_18006F9BD
0x18006f99f  mov     edx, [rsp+160h+ProcessInformation]; __int64
0x18006f9a3  mov     rcx, rsi; struct lua_State *
0x18006f9a6  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x18006f9ab  lea     r8, aSessionId; "session_id"
0x18006f9b2  mov     edx, r15d; int
0x18006f9b5  mov     rcx, rsi; struct lua_State *
0x18006f9b8  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006f9bd  mov     eax, 0FFFFFFEFh
0x18006f9c2  jmp     loc_18006FBA4
0x18006f9c7  test    r14b, 40h
0x18006f9cb  jz      loc_18006FA5F
0x18006f9d1  call    cs:__imp_GetCurrentProcessId
0x18006f9d7  cmp     r13d, eax
0x18006f9da  jnz     short loc_18006F9E7
0x18006f9dc  call    cs:__imp_IsDebuggerPresent
0x18006f9e2  mov     r12d, eax
0x18006f9e5  jmp     short loc_18006FA2E
0x18006f9e7  mov     r8d, r13d; dwProcessId
0x18006f9ea  xor     edx, edx; bInheritHandle
0x18006f9ec  mov     ecx, 400h; dwDesiredAccess
0x18006f9f1  call    cs:__imp_OpenProcess
0x18006f9f7  mov     r15, rax
0x18006f9fa  test    rax, rax
0x18006f9fd  jz      short loc_18006FA4D
0x18006f9ff  mov     [rsp+160h+ProcessInformation], edi
0x18006fa03  lea     rdx, [rsp+160h+ProcessInformation]; pbDebuggerPresent
0x18006fa08  mov     rcx, rax; hProcess
0x18006fa0b  call    cs:__imp_CheckRemoteDebuggerPresent
0x18006fa11  mov     edi, eax
0x18006fa13  test    eax, eax
0x18006fa15  cmovnz  r12d, [rsp+160h+ProcessInformation]
0x18006fa1b  mov     rcx, r15; hObject
0x18006fa1e  call    cs:__imp_CloseHandle
0x18006fa24  mov     r15d, 0FFFFFFFEh
0x18006fa2a  test    edi, edi
0x18006fa2c  jz      short loc_18006FA53
0x18006fa2e  mov     edx, r12d; int
0x18006fa31  mov     rcx, rsi; struct lua_State *
0x18006fa34  call    ?lua_pushboolean@@YAXPEAUlua_State@@H@Z; lua_pushboolean(lua_State *,int)
0x18006fa39  lea     r8, aDebugged; "debugged"
0x18006fa40  mov     edx, r15d; int
0x18006fa43  mov     rcx, rsi; struct lua_State *
0x18006fa46  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18006fa4b  jmp     short loc_18006FA53
0x18006fa4d  mov     r15d, 0FFFFFFFEh
0x18006fa53  mov     eax, 0FFFFFFBFh
0x18006fa58  xor     edi, edi
0x18006fa5a  jmp     loc_18006FBA4
0x18006fa5f  test    r14b, 20h
0x18006fa63  jz      loc_18006FBAD
0x18006fa69  mov     [rsp+160h+ProcessInformation], edi
0x18006fa6d  lea     rax, [rsp+160h+ProcessInformation]
0x18006fa72  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18006fa77  xor     r9d, r9d; ProcessInformationLength
0x18006fa7a  xor     r8d, r8d; ProcessInformation
0x18006fa7d  lea     edx, [r9+3Ch]; ProcessInformationClass
0x18006fa81  mov     rcx, rbx; ProcessHandle
0x18006fa84  call    cs:__imp_NtQueryInformationProcess
0x18006fa8a  cmp     eax, 0C0000004h
0x18006fa8f  jnz     loc_18006FB9F
0x18006fa95  cmp     [rsp+160h+ProcessInformation], 10h
0x18006fa9a  jb      loc_18006FB9F
0x18006faa0  mov     byte ptr [rsp+160h+var_12C], dil
0x18006faa5  mov     edx, [rsp+160h+ProcessInformation]
0x18006faa9  lea     r8, [rsp+160h+var_12C]
0x18006faae  lea     rcx, [rsp+160h+var_120]
0x18006fab3  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x18006fab8  nop
0x18006fab9  lea     rax, [rsp+160h+ProcessInformation]
0x18006fabe  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x18006fac3  mov     r9d, [rsp+160h+ProcessInformation]; ProcessInformationLength
0x18006fac8  mov     r8, [rsp+160h+var_120]; ProcessInformation
0x18006facd  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x18006fad2  mov     rcx, rbx; ProcessHandle
0x18006fad5  call    cs:__imp_NtQueryInformationProcess
0x18006fadb  test    eax, eax
0x18006fadd  js      loc_18006FB95
0x18006fae3  cmp     [rsp+160h+ProcessInformation], 10h
0x18006fae8  jb      loc_18006FB95
0x18006faee  mov     rdx, [rsp+160h+var_120]
0x18006faf3  lea     rax, [rdx+10h]
0x18006faf7  cmp     [rdx+8], rax
0x18006fafb  jnz     loc_18006FB95
0x18006fb01  mov     ecx, dword ptr [rsp+160h+var_118]
0x18006fb05  sub     ecx, edx
0x18006fb07  add     ecx, 0FFFFFFF0h
0x18006fb0a  movzx   eax, word ptr [rdx]
  ... truncated ...
```
