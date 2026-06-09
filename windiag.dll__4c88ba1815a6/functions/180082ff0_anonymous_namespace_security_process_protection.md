# _anonymous_namespace_::security_process_protection

- ea: `0x180082ff0`
- end: `0x1800830d3`
- name: `_anonymous_namespace_::security_process_protection`
- size: `227`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180006690`
- `0x180006c50`
- `0x1800083a0`
- `0x180082ff0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180082ffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180082ffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800830ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800830c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800830ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800830c0`
- `ntdll!NtQueryInformationProcess` at `0x180083068`
- `ntdll!NtQueryInformationProcess` at `0x180083068`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008302c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18008302c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::security_process_protection(struct lua_State *a1)
{
  DWORD CurrentProcessId; // ebx
  DWORD v3; // eax
  HANDLE v4; // rbx
  unsigned __int8 ProcessInformation; // [rsp+48h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  HANDLE v8; // [rsp+58h] [rbp+20h]

  CurrentProcessId = GetCurrentProcessId();
  if ( (int)lua_gettop(a1) <= 0 )
    v3 = CurrentProcessId;
  else
    v3 = luaL_checkinteger(a1, 1);
  v4 = OpenProcess(0x1000u, 0, v3);
  v8 = v4;
  if ( v4
    && (ProcessInformation = 0,
        ReturnLength = 1,
        NtQueryInformationProcess(
          v4,
          ProcessAffinityUpdateMode|ProcessUserModeIOPL,
          &ProcessInformation,
          1u,
          &ReturnLength) >= 0)
    && ReturnLength == 1 )
  {
    lua_pushinteger(a1, ProcessInformation);
    lua_pushinteger(a1, (unsigned __int64)ProcessInformation >> 4);
    lua_pushinteger(a1, ProcessInformation & 7);
    CloseHandle(v4);
    return 3;
  }
  else
  {
    if ( v4 )
      CloseHandle(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180082ff0  mov     [rsp+arg_0], rbx
0x180082ff5  push    rdi
0x180082ff6  sub     rsp, 30h
0x180082ffa  mov     rdi, rcx
0x180082ffd  call    cs:__imp_GetCurrentProcessId
0x180083003  mov     ebx, eax
0x180083005  mov     rcx, rdi; struct lua_State *
0x180083008  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18008300d  test    eax, eax
0x18008300f  jle     short loc_180083020
0x180083011  mov     edx, 1; int
0x180083016  mov     rcx, rdi; struct lua_State *
0x180083019  call    ?luaL_checkinteger@@YA_JPEAUlua_State@@H@Z; luaL_checkinteger(lua_State *,int)
0x18008301e  jmp     short loc_180083022
0x180083020  mov     eax, ebx
0x180083022  mov     r8d, eax; dwProcessId
0x180083025  xor     edx, edx; bInheritHandle
0x180083027  mov     ecx, 1000h; dwDesiredAccess
0x18008302c  call    cs:__imp_OpenProcess
0x180083032  mov     rbx, rax
0x180083035  mov     [rsp+38h+arg_18], rax
0x18008303a  test    rax, rax
0x18008303d  jz      short loc_1800830B8
0x18008303f  mov     [rsp+38h+ProcessInformation], 0
0x180083044  mov     [rsp+38h+arg_10], 1
0x18008304c  lea     rax, [rsp+38h+arg_10]
0x180083051  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180083056  mov     r9d, 1; ProcessInformationLength
0x18008305c  lea     r8, [rsp+38h+ProcessInformation]; ProcessInformation
0x180083061  lea     edx, [r9+3Ch]; ProcessInformationClass
0x180083065  mov     rcx, rbx; ProcessHandle
0x180083068  call    cs:__imp_NtQueryInformationProcess
0x18008306e  test    eax, eax
0x180083070  js      short loc_1800830B8
0x180083072  cmp     [rsp+38h+arg_10], 1
0x180083077  jnz     short loc_1800830B8
0x180083079  movzx   edx, [rsp+38h+ProcessInformation]; __int64
0x18008307e  mov     rcx, rdi; struct lua_State *
0x180083081  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180083086  movzx   edx, [rsp+38h+ProcessInformation]
0x18008308b  shr     rdx, 4; __int64
0x18008308f  mov     rcx, rdi; struct lua_State *
0x180083092  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x180083097  movzx   edx, [rsp+38h+ProcessInformation]
0x18008309c  and     edx, 7; __int64
0x18008309f  mov     rcx, rdi; struct lua_State *
0x1800830a2  call    ?lua_pushinteger@@YAXPEAUlua_State@@_J@Z; lua_pushinteger(lua_State *,__int64)
0x1800830a7  nop
0x1800830a8  mov     rcx, rbx; hObject
0x1800830ab  call    cs:__imp_CloseHandle
0x1800830b1  mov     eax, 3
0x1800830b6  jmp     short loc_1800830C8
0x1800830b8  test    rbx, rbx
0x1800830bb  jz      short loc_1800830C6
0x1800830bd  mov     rcx, rbx; hObject
0x1800830c0  call    cs:__imp_CloseHandle
0x1800830c6  xor     eax, eax
0x1800830c8  mov     rbx, [rsp+38h+arg_0]
0x1800830cd  add     rsp, 30h
0x1800830d1  pop     rdi
0x1800830d2  retn
```
