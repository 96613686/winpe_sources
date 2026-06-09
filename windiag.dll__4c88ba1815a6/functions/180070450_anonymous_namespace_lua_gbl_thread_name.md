# _anonymous_namespace_::lua_gbl_thread_name

- ea: `0x180070450`
- end: `0x18007058b`
- name: `_anonymous_namespace_::lua_gbl_thread_name`
- size: `315`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004510`
- `0x180006690`
- `0x180006c50`
- `0x180006d40`
- `0x1800083a0`
- `0x18003b0bc`
- `0x180041e58`
- `0x180070450`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007047b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007047b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070484`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070484`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800704b0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800704b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007054c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007054c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180070561`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007053d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007053d`
- `api-ms-win-core-processthreads-l1-1-3!GetThreadDescription` at `0x1800704e3`
- `api-ms-win-core-processthreads-l1-1-3!GetThreadDescription` at `0x1800704e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::lua_gbl_thread_name(struct lua_State *a1)
{
  void *v2; // rbx
  HANDLE CurrentThread; // rdi
  DWORD CurrentThreadId; // ebp
  HANDLE v5; // rax
  void *v6; // rsi
  PWSTR v7; // rdi
  __int64 v8; // rax
  PWSTR ppszThreadDescription; // [rsp+20h] [rbp-58h] BYREF
  HANDLE v11; // [rsp+28h] [rbp-50h]
  PWSTR v12; // [rsp+30h] [rbp-48h]
  char *v13[4]; // [rsp+38h] [rbp-40h] BYREF

  v2 = 0;
  v11 = 0;
  CurrentThread = GetCurrentThread();
  CurrentThreadId = GetCurrentThreadId();
  if ( (int)lua_gettop(a1) <= 0 )
  {
    v6 = 0;
  }
  else
  {
    CurrentThreadId = luaL_checkinteger(a1, 1);
    v5 = OpenThread(0x800u, 0, CurrentThreadId);
    v2 = v5;
    v11 = v5;
    if ( !v5 )
      return 0;
    CurrentThread = v5;
    v6 = v5;
  }
  ppszThreadDescription = 0;
  if ( GetThreadDescription(CurrentThread, &ppszThreadDescription) < 0 || (v7 = ppszThreadDescription) == 0 )
  {
    if ( v6 )
      CloseHandle(v6);
    return 0;
  }
  v12 = ppszThreadDescription;
  v8 = windiag::wchar_to_string(v13, ppszThreadDescription);
  if ( *(_QWORD *)(v8 + 24) > 0xFu )
    v8 = *(_QWORD *)v8;
  lua_pushstring(a1, (const char *)v8);
  std::string::~string(v13);
  lua_pushinteger(a1, CurrentThreadId);
  if ( v7 )
    LocalFree(v7);
  if ( v2 )
    CloseHandle(v2);
  return 2;
}

```

## disassembly

```asm
0x180070450  mov     [rsp+arg_8], rbx
0x180070455  mov     [rsp+arg_10], rbp
0x18007045a  push    rsi
0x18007045b  push    rdi
0x18007045c  push    r14
0x18007045e  sub     rsp, 60h
0x180070462  mov     rax, cs:__security_cookie
0x180070469  xor     rax, rsp
0x18007046c  mov     [rsp+78h+var_20], rax
0x180070471  mov     r14, rcx
0x180070474  xor     ebx, ebx
0x180070476  mov     [rsp+78h+var_50], rbx
0x18007047b  call    cs:__imp_GetCurrentThread
0x180070481  mov     rdi, rax
0x180070484  call    cs:__imp_GetCurrentThreadId
0x18007048a  mov     ebp, eax
0x18007048c  mov     rcx, r14; struct lua_State *
0x18007048f  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x180070494  test    eax, eax
0x180070496  jle     short loc_1800704D0
0x180070498  lea     edx, [rbx+1]; int
0x18007049b  mov     rcx, r14; struct lua_State *
0x18007049e  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x1800704a3  mov     rbp, rax
0x1800704a6  mov     r8d, eax; dwThreadId
0x1800704a9  xor     edx, edx; bInheritHandle
0x1800704ab  mov     ecx, 800h; dwDesiredAccess
0x1800704b0  call    cs:__imp_OpenThread
0x1800704b6  mov     rbx, rax
0x1800704b9  mov     [rsp+78h+var_50], rax
0x1800704be  test    rax, rax
0x1800704c1  jz      short loc_1800704CB
0x1800704c3  mov     rdi, rax
0x1800704c6  mov     rsi, rax
0x1800704c9  jmp     short loc_1800704D2
0x1800704cb  jmp     loc_180070567
0x1800704d0  xor     esi, esi
0x1800704d2  mov     [rsp+78h+ppszThreadDescription], 0
0x1800704db  lea     rdx, [rsp+78h+ppszThreadDescription]; ppszThreadDescription
0x1800704e0  mov     rcx, rdi; hThread
0x1800704e3  call    cs:__imp_GetThreadDescription
0x1800704e9  test    eax, eax
0x1800704eb  js      short loc_180070559
0x1800704ed  mov     rdi, [rsp+78h+ppszThreadDescription]
0x1800704f2  test    rdi, rdi
0x1800704f5  jz      short loc_180070559
0x1800704f7  mov     [rsp+78h+var_48], rdi
0x1800704fc  mov     rdx, rdi
0x1800704ff  lea     rcx, [rsp+78h+var_40]
0x180070504  call    ?wchar_to_string@windiag@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; windiag::wchar_to_string(ushort const *)
0x180070509  nop
0x18007050a  cmp     qword ptr [rax+18h], 0Fh
0x18007050f  jbe     short loc_180070514
0x180070511  mov     rax, [rax]
0x180070514  mov     rdx, rax; char *
0x180070517  mov     rcx, r14; struct lua_State *
0x18007051a  call    ?lua_pushstring@@YAPEBDPEAUlua_State@@PEBD@Z; lua_pushstring(lua_State *,char const *)
0x18007051f  nop
0x180070520  lea     rcx, [rsp+78h+var_40]
0x180070525  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18007052a  mov     edx, ebp; __int64
0x18007052c  mov     rcx, r14; struct lua_State *
0x18007052f  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180070534  nop
0x180070535  test    rdi, rdi
0x180070538  jz      short loc_180070544
0x18007053a  mov     rcx, rdi; hMem
0x18007053d  call    cs:__imp_LocalFree
0x180070543  nop
0x180070544  test    rbx, rbx
0x180070547  jz      short loc_180070552
0x180070549  mov     rcx, rbx; hObject
0x18007054c  call    cs:__imp_CloseHandle
0x180070552  mov     eax, 2
0x180070557  jmp     short loc_180070569
0x180070559  test    rsi, rsi
0x18007055c  jz      short loc_180070567
0x18007055e  mov     rcx, rsi; hObject
0x180070561  call    cs:__imp_CloseHandle
0x180070567  xor     eax, eax
0x180070569  mov     rcx, [rsp+78h+var_20]
0x18007056e  xor     rcx, rsp; StackCookie
0x180070571  call    __security_check_cookie
0x180070576  lea     r11, [rsp+78h+var_18]
0x18007057b  mov     rbx, [r11+28h]
0x18007057f  mov     rbp, [r11+30h]
0x180070583  mov     rsp, r11
0x180070586  pop     r14
0x180070588  pop     rdi
0x180070589  pop     rsi
0x18007058a  retn
```
