# _anonymous_namespace_::sysinfo_service_snapshot

- ea: `0x180071344`
- end: `0x18007173b`
- name: `_anonymous_namespace_::sysinfo_service_snapshot`
- size: `1015`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x18006fdb0`

## callees

- `0x180004510`
- `0x180005520`
- `0x180006050`
- `0x180006690`
- `0x180006c50`
- `0x180006d40`
- `0x180007160`
- `0x1800073e0`
- `0x1800076e0`
- `0x180007950`
- `0x18003af08`
- `0x18003b0bc`
- `0x180041e58`
- `0x1800428b4`
- `0x180049674`
- `0x1800511ac`
- `0x180071344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007146a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007146a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071477`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180071424`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180071424`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180071699`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180071699`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800714d9`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800714d9`

## string_xrefs

- `0x1800716d1`: `sysinfo_service_snapshot`
- `0x18007170b`: `sysinfo_service_snapshot`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::sysinfo_service_snapshot(struct lua_State *a1)
{
  DWORD v2; // r14d
  DWORD v3; // esi
  __int64 v4; // rax
  SC_HANDLE v5; // rbx
  DWORD LastError; // eax
  DWORD v7; // eax
  int v8; // r13d
  LPBYTE v9; // r12
  DWORD v10; // esi
  DWORD v11; // ecx
  int v12; // ebx
  __int64 v13; // r15
  BYTE *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  char v19; // [rsp+50h] [rbp-B0h]
  _BYTE v20[3]; // [rsp+51h] [rbp-AFh] BYREF
  DWORD pcbBytesNeeded; // [rsp+54h] [rbp-ACh] BYREF
  DWORD ServicesReturned; // [rsp+58h] [rbp-A8h] BYREF
  DWORD ResumeHandle; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h]
  LPBYTE lpServices; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+70h] [rbp-90h]
  SC_HANDLE v27; // [rsp+80h] [rbp-80h]
  _BYTE v28[40]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = 59;
  v3 = 3;
  v19 = 0;
  if ( (int)lua_gettop(a1) <= 1 )
    goto LABEL_10;
  if ( (unsigned int)lua_type(a1, 2) )
    v2 = lua_tointegerx(a1, 2, 0);
  if ( (int)lua_gettop(a1) <= 2 )
    goto LABEL_10;
  if ( (unsigned int)lua_type(a1, 3) )
    v3 = lua_tointegerx(a1, 3, 0);
  if ( (int)lua_gettop(a1) > 3 && (unsigned int)lua_type(a1, 4) )
  {
    v4 = lua_tointegerx(a1, 4, 0);
    v19 = 1;
  }
  else
  {
LABEL_10:
    v4 = ResumeHandle;
  }
  v24 = v4;
  v5 = OpenSCManagerW(0, 0, 4u);
  v27 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        LastError,
        0,
        "[%s:%d] failed; ",
        "sysinfo_service_snapshot",
        691);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  ResumeHandle = 0;
  ServicesReturned = 0;
  v20[0] = 0;
  std::vector<unsigned char>::vector<unsigned char>(&lpServices, 0x20000, v20);
  while ( 1 )
  {
    pcbBytesNeeded = v26 - (_DWORD)lpServices;
    if ( EnumServicesStatusExW(
           v5,
           SC_ENUM_PROCESS_INFO,
           v2,
           v3,
           lpServices,
           v26 - (_DWORD)lpServices,
           &pcbBytesNeeded,
           &ServicesReturned,
           &ResumeHandle,
           0) )
    {
      break;
    }
    if ( GetLastError() != 234 )
    {
      v7 = GetLastError();
      if ( v7 )
      {
        windiag::system_exception::system_exception(
          (windiag::system_exception *)pExceptionObject,
          v7,
          0,
          "[%s:%d] failed; ",
          "sysinfo_service_snapshot",
          701);
        throw (windiag::system_exception *)pExceptionObject;
      }
    }
    std::vector<unsigned char>::resize(&lpServices);
  }
  lua_createtable(a1, 0, 0);
  v8 = 1;
  v9 = lpServices;
  v10 = 0;
  v11 = ServicesReturned;
  if ( ServicesReturned )
  {
    v12 = v24;
    do
    {
      v13 = 56LL * v10;
      v14 = &v9[v13];
      if ( !v19 || v12 == *((_DWORD *)v14 + 11) )
      {
        v15 = v8++;
        lua_pushinteger(a1, v15);
        lua_createtable(a1, 0, 0);
        v16 = windiag::wchar_to_string(v28, *(_QWORD *)&v9[v13]);
        if ( *(_QWORD *)(v16 + 24) > 0xFu )
          v16 = *(_QWORD *)v16;
        lua_pushstring(a1, (const char *)v16);
        std::string::~string(v28);
        lua_setfield(a1, -2, "name");
        v17 = windiag::wchar_to_string(v28, *(_QWORD *)&v9[v13 + 8]);
        if ( *(_QWORD *)(v17 + 24) > 0xFu )
          v17 = *(_QWORD *)v17;
        lua_pushstring(a1, (const char *)v17);
        std::string::~string(v28);
        lua_setfield(a1, -2, "display_name");
        lua_pushinteger(a1, *((unsigned int *)v14 + 11));
        lua_setfield(a1, -2, "pid");
        lua_pushinteger(a1, *(unsigned int *)&v9[v13 + 16]);
        lua_setfield(a1, -2, "type");
        lua_pushinteger(a1, *(unsigned int *)&v9[v13 + 20]);
        lua_setfield(a1, -2, "state");
        lua_pushinteger(a1, *(unsigned int *)&v9[v13 + 24]);
        lua_setfield(a1, -2, "controls");
        lua_pushinteger(a1, *(unsigned int *)&v9[v13 + 48]);
        lua_setfield(a1, -2, "flags");
        lua_settable(a1, -3);
        v11 = ServicesReturned;
      }
      ++v10;
    }
    while ( v10 < v11 );
    v5 = v27;
  }
  std::vector<char>::~vector<char>(&lpServices);
  if ( v5 )
    CloseServiceHandle(v5);
  return 1;
}

```

## disassembly

```asm
0x180071344  push    rbp
0x180071346  push    rbx
0x180071347  push    rsi
0x180071348  push    rdi
0x180071349  push    r12
0x18007134b  push    r13
0x18007134d  push    r14
0x18007134f  push    r15
0x180071351  lea     rbp, [rsp-3F8h]
0x180071359  sub     rsp, 4F8h
0x180071360  mov     rax, cs:__security_cookie
0x180071367  xor     rax, rsp
0x18007136a  mov     [rbp+430h+var_50], rax
0x180071371  mov     rdi, rcx
0x180071374  mov     ebx, 3
0x180071379  lea     r14d, [rbx+38h]
0x18007137d  mov     esi, ebx
0x18007137f  xor     r15d, r15d
0x180071382  mov     [rsp+530h+var_4E0], r15b
0x180071387  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18007138c  lea     r13d, [rbx+1]
0x180071390  cmp     eax, 1
0x180071393  jle     short loc_180071414
0x180071395  lea     r12d, [rbx-1]
0x180071399  mov     edx, r12d; int
0x18007139c  mov     rcx, rdi; struct lua_State *
0x18007139f  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x1800713a4  test    eax, eax
0x1800713a6  jz      short loc_1800713B9
0x1800713a8  xor     r8d, r8d; int *
0x1800713ab  mov     edx, r12d; int
0x1800713ae  mov     rcx, rdi; struct lua_State *
0x1800713b1  call    ?lua_tointegerx@@YA_JPEAUlua_State@@HPEAH@Z; lua_tointegerx(lua_State *,int,int *)
0x1800713b6  mov     r14, rax
0x1800713b9  mov     rcx, rdi; struct lua_State *
0x1800713bc  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x1800713c1  cmp     eax, r12d
0x1800713c4  jle     short loc_180071414
0x1800713c6  mov     edx, ebx; int
0x1800713c8  mov     rcx, rdi; struct lua_State *
0x1800713cb  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x1800713d0  test    eax, eax
0x1800713d2  jz      short loc_1800713E4
0x1800713d4  xor     r8d, r8d; int *
0x1800713d7  mov     edx, ebx; int
0x1800713d9  mov     rcx, rdi; struct lua_State *
0x1800713dc  call    ?lua_tointegerx@@YA_JPEAUlua_State@@HPEAH@Z; lua_tointegerx(lua_State *,int,int *)
0x1800713e1  mov     rsi, rax
0x1800713e4  mov     rcx, rdi; struct lua_State *
0x1800713e7  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x1800713ec  cmp     eax, ebx
0x1800713ee  jle     short loc_180071414
0x1800713f0  mov     edx, r13d; int
0x1800713f3  mov     rcx, rdi; struct lua_State *
0x1800713f6  call    ?lua_type@@YAHPEAUlua_State@@H@Z; lua_type(lua_State *,int)
0x1800713fb  test    eax, eax
0x1800713fd  jz      short loc_180071414
0x1800713ff  xor     r8d, r8d; int *
0x180071402  mov     edx, r13d; int
0x180071405  mov     rcx, rdi; struct lua_State *
0x180071408  call    ?lua_tointegerx@@YA_JPEAUlua_State@@HPEAH@Z; lua_tointegerx(lua_State *,int,int *)
0x18007140d  mov     [rsp+530h+var_4E0], 1
0x180071412  jmp     short loc_180071418
0x180071414  mov     eax, [rsp+530h+ResumeHandle]
0x180071418  mov     [rsp+530h+var_4D0], rax
0x18007141d  mov     r8d, r13d; dwDesiredAccess
0x180071420  xor     edx, edx; lpDatabaseName
0x180071422  xor     ecx, ecx; lpMachineName
0x180071424  call    cs:__imp_OpenSCManagerW
0x18007142a  mov     rbx, rax
0x18007142d  mov     [rbp+430h+var_4B0], rax
0x180071431  test    rax, rax
0x180071434  jnz     short loc_180071444
0x180071436  call    cs:__imp_GetLastError
0x18007143c  test    eax, eax
0x18007143e  jnz     loc_1800716C7
0x180071444  mov     [rsp+530h+ResumeHandle], r15d
0x180071449  mov     [rsp+530h+ServicesReturned], r15d
0x18007144e  mov     [rsp+530h+var_4DF], r15b
0x180071453  lea     r8, [rsp+530h+var_4DF]
0x180071458  mov     edx, 20000h
0x18007145d  lea     rcx, [rsp+530h+var_4C8]
0x180071462  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x180071467  nop
0x180071468  jmp     short loc_180071493
0x18007146a  call    cs:__imp_GetLastError
0x180071470  cmp     eax, 0EAh
0x180071475  jz      short loc_180071485
0x180071477  call    cs:__imp_GetLastError
0x18007147d  test    eax, eax
0x18007147f  jnz     loc_180071701
0x180071485  mov     edx, [rsp+530h+var_4DC]
0x180071489  lea     rcx, [rsp+530h+var_4C8]
0x18007148e  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180071493  mov     [rsp+530h+pszGroupName], r15; pszGroupName
0x180071498  lea     rdx, [rsp+530h+ResumeHandle]
0x18007149d  mov     [rsp+530h+lpResumeHandle], rdx; lpResumeHandle
0x1800714a2  lea     rdx, [rsp+530h+ServicesReturned]
0x1800714a7  mov     [rsp+530h+lpServicesReturned], rdx; lpServicesReturned
0x1800714ac  lea     rdx, [rsp+530h+var_4DC]
0x1800714b1  mov     rax, [rsp+530h+var_4C8]
0x1800714b6  mov     ecx, [rsp+530h+var_4C0]
0x1800714ba  mov     [rsp+530h+pcbBytesNeeded], rdx; pcbBytesNeeded
0x1800714bf  sub     ecx, eax
0x1800714c1  mov     [rsp+530h+cbBufSize], ecx; cbBufSize
0x1800714c5  mov     [rsp+530h+var_4DC], ecx
0x1800714c9  mov     [rsp+530h+lpServices], rax; lpServices
0x1800714ce  mov     r9d, esi; dwServiceState
0x1800714d1  mov     r8d, r14d; dwServiceType
0x1800714d4  xor     edx, edx; InfoLevel
0x1800714d6  mov     rcx, rbx; hSCManager
0x1800714d9  call    cs:__imp_EnumServicesStatusExW
0x1800714df  test    eax, eax
0x1800714e1  jz      short loc_18007146A
0x1800714e3  xor     r8d, r8d; int
0x1800714e6  xor     edx, edx; int
0x1800714e8  mov     rcx, rdi; struct lua_State *
0x1800714eb  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x1800714f0  mov     r13d, 1
0x1800714f6  mov     r12, [rsp+530h+var_4C8]
0x1800714fb  mov     esi, r15d
0x1800714fe  mov     ecx, [rsp+530h+ServicesReturned]
0x180071502  test    ecx, ecx
0x180071504  jz      loc_180071686
0x18007150a  mov     rbx, [rsp+530h+var_4D0]
0x18007150f  mov     eax, esi
0x180071511  imul    r15, rax, 38h ; '8'
0x180071515  lea     r14, [r15+r12]
0x180071519  cmp     [rsp+530h+var_4E0], 0
0x18007151e  jz      short loc_18007152A
0x180071520  cmp     ebx, [r14+2Ch]
0x180071524  jnz     loc_180071678
0x18007152a  movsxd  rdx, r13d; __int64
0x18007152d  inc     r13d
0x180071530  mov     rcx, rdi; struct lua_State *
0x180071533  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180071538  xor     r8d, r8d; int
0x18007153b  xor     edx, edx; int
0x18007153d  mov     rcx, rdi; struct lua_State *
0x180071540  call    ?lua_createtable@@YAXPEAUlua_State@@HH@Z; lua_createtable(lua_State *,int,int)
0x180071545  mov     rdx, [r15+r12]
0x180071549  lea     rcx, [rbp+430h+var_4A8]
0x18007154d  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x180071552  nop
0x180071553  cmp     qword ptr [rax+18h], 0Fh
0x180071558  jbe     short loc_18007155D
0x18007155a  mov     rax, [rax]
0x18007155d  mov     rdx, rax; char *
0x180071560  mov     rcx, rdi; struct lua_State *
0x180071563  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x180071568  nop
0x180071569  lea     rcx, [rbp+430h+var_4A8]
0x18007156d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180071572  lea     r8, aName; "name"
0x180071579  mov     edx, 0FFFFFFFEh; int
0x18007157e  mov     rcx, rdi; struct lua_State *
0x180071581  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x180071586  mov     rdx, [r15+r12+8]
0x18007158b  lea     rcx, [rbp+430h+var_4A8]
0x18007158f  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x180071594  nop
0x180071595  cmp     qword ptr [rax+18h], 0Fh
0x18007159a  jbe     short loc_18007159F
0x18007159c  mov     rax, [rax]
0x18007159f  mov     rdx, rax; char *
0x1800715a2  mov     rcx, rdi; struct lua_State *
0x1800715a5  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x1800715aa  nop
0x1800715ab  lea     rcx, [rbp+430h+var_4A8]
0x1800715af  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800715b4  lea     r8, aDisplayName; "display_name"
0x1800715bb  mov     edx, 0FFFFFFFEh; int
0x1800715c0  mov     rcx, rdi; struct lua_State *
0x1800715c3  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x1800715c8  mov     edx, [r14+2Ch]; __int64
0x1800715cc  mov     rcx, rdi; struct lua_State *
0x1800715cf  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800715d4  lea     r8, aPid; "pid"
0x1800715db  mov     r14d, 0FFFFFFFEh
0x1800715e1  mov     edx, r14d; int
0x1800715e4  mov     rcx, rdi; struct lua_State *
0x1800715e7  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x1800715ec  mov     edx, [r15+r12+10h]; __int64
0x1800715f1  mov     rcx, rdi; struct lua_State *
0x1800715f4  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800715f9  lea     r8, aType; "type"
0x180071600  mov     edx, r14d; int
0x180071603  mov     rcx, rdi; struct lua_State *
0x180071606  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18007160b  mov     edx, [r15+r12+14h]; __int64
0x180071610  mov     rcx, rdi; struct lua_State *
0x180071613  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180071618  lea     r8, aState; "state"
0x18007161f  mov     edx, r14d; int
0x180071622  mov     rcx, rdi; struct lua_State *
0x180071625  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x18007162a  mov     edx, [r15+r12+18h]; __int64
0x18007162f  mov     rcx, rdi; struct lua_State *
0x180071632  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180071637  lea     r8, aControls; "controls"
0x18007163e  mov     edx, r14d; int
0x180071641  mov     rcx, rdi; struct lua_State *
0x180071644  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x180071649  mov     edx, [r15+r12+30h]; __int64
0x18007164e  mov     rcx, rdi; struct lua_State *
0x180071651  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180071656  lea     r8, aFlags; "flags"
0x18007165d  mov     edx, r14d; int
0x180071660  mov     rcx, rdi; struct lua_State *
0x180071663  call    ?lua_setfield@@YAXPEAUlua_State@@HPEBD@Z; lua_setfield(lua_State *,int,char const *)
0x180071668  lea     edx, [r14-1]; int
0x18007166c  mov     rcx, rdi; struct lua_State *
0x18007166f  call    ?lua_settable@@YAXPEAUlua_State@@H@Z; lua_settable(lua_State *,int)
0x180071674  mov     ecx, [rsp+530h+ServicesReturned]
0x180071678  inc     esi
0x18007167a  cmp     esi, ecx
0x18007167c  jb      loc_18007150F
0x180071682  mov     rbx, [rbp+430h+var_4B0]
0x180071686  lea     rcx, [rsp+530h+var_4C8]
0x18007168b  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180071690  nop
0x180071691  test    rbx, rbx
0x180071694  jz      short loc_18007169F
0x180071696  mov     rcx, rbx; hSCObject
0x180071699  call    cs:__imp_CloseServiceHandle
0x18007169f  mov     eax, 1
0x1800716a4  mov     rcx, [rbp+430h+var_50]
0x1800716ab  xor     rcx, rsp; StackCookie
0x1800716ae  call    __security_check_cookie
0x1800716b3  add     rsp, 4F8h
0x1800716ba  pop     r15
0x1800716bc  pop     r14
0x1800716be  pop     r13
0x1800716c0  pop     r12
0x1800716c2  pop     rdi
0x1800716c3  pop     rsi
0x1800716c4  pop     rbx
0x1800716c5  pop     rbp
0x1800716c6  retn
0x1800716c7  mov     edx, eax; __int64
0x1800716c9  mov     [rsp+530h+cbBufSize], 2B3h
0x1800716d1  lea     rax, aSysinfoService; "sysinfo_service_snapshot"
0x1800716d8  mov     [rsp+530h+lpServices], rax
0x1800716dd  lea     r9, aSDFailed; "[%s:%d] failed; "
0x1800716e4  xor     r8d, r8d; void *
0x1800716e7  lea     rcx, [rbp+430h+pExceptionObject]; this
0x1800716eb  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x1800716f0  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x1800716f7  lea     rcx, [rbp+430h+pExceptionObject]; pExceptionObject
0x1800716fb  call    _CxxThrowException_0
0x180071701  mov     edx, eax; __int64
0x180071703  mov     [rsp+530h+cbBufSize], 2BDh
0x18007170b  lea     rax, aSysinfoService; "sysinfo_service_snapshot"
0x180071712  mov     [rsp+530h+lpServices], rax
0x180071717  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18007171e  xor     r8d, r8d; void *
0x180071721  lea     rcx, [rbp+430h+pExceptionObject]; this
0x180071725  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18007172a  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180071731  lea     rcx, [rbp+430h+pExceptionObject]; pExceptionObject
0x180071735  call    _CxxThrowException_0
```
