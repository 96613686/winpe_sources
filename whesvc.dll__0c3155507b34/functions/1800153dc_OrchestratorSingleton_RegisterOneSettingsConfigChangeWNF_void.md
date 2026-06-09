# OrchestratorSingleton::RegisterOneSettingsConfigChangeWNF(void)

- ea: `0x1800153dc`
- end: `0x180015600`
- name: `?RegisterOneSettingsConfigChangeWNF@OrchestratorSingleton@@QEAAJXZ`
- size: `548`
- prototype: `__int64 __fastcall(OrchestratorSingleton *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000b380`

## callees

- `0x1800032e0`
- `0x180009044`
- `0x1800108c0`
- `0x180010a9c`
- `0x1800153dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001558d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001558d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800154cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800154cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OrchestratorSingleton::RegisterOneSettingsConfigChangeWNF(OrchestratorSingleton *this)
{
  int v2; // ebx
  __int64 v3; // rdx
  void (__fastcall ***v5)(_QWORD, __int64); // rbx
  char *v6; // r14
  void (__fastcall ***v7)(_QWORD, __int64); // rsi
  DWORD LastError; // edi
  void (__fastcall ***v9)(_QWORD, __int64); // rbx
  char *v10; // r14
  void (__fastcall ***v11)(_QWORD, __int64); // rsi
  DWORD v12; // edi
  int v13; // [rsp+20h] [rbp-89h] BYREF
  unsigned int v14; // [rsp+24h] [rbp-85h] BYREF
  void (__fastcall ***v15)(_QWORD, __int64); // [rsp+28h] [rbp-81h] BYREF
  __int64 v16; // [rsp+30h] [rbp-79h] BYREF
  char v17; // [rsp+38h] [rbp-71h] BYREF
  char v18; // [rsp+40h] [rbp-69h] BYREF
  char v19[8]; // [rsp+48h] [rbp-61h] BYREF
  __int64 (__fastcall **v20)(); // [rsp+50h] [rbp-59h] BYREF
  OrchestratorSingleton *v21; // [rsp+58h] [rbp-51h]
  __int64 (__fastcall ***v22)(); // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v14 = 0;
  LOBYTE(v13) = 0;
  v16 = 0;
  v2 = wil::wnf_query_nothrow<_LARGE_INTEGER>(&WNF_WOSC_WHESVC_MOD_CONFIG_CHANGED, &v13, &v16, &v14);
  if ( v2 < 0 )
  {
    v3 = 578;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"pcshell\\base\\whesvc\\lib\\orchestrator.cpp",
      (const char *)(unsigned int)v2,
      v13);
    return (unsigned int)v2;
  }
  v20 = off_18002A2A8;
  v21 = this;
  v22 = &v20;
  v15 = 0;
  v5 = 0;
  v6 = (char *)this + 576;
  if ( (int)wil::details::make_wnf_subscription_state<_LARGE_INTEGER>(
              &WNF_WOSC_WHESVC_MOD_CONFIG_CHANGED,
              v19,
              v14,
              &v15) >= 0 )
    v5 = v15;
  if ( v6 == &v17 )
  {
    if ( v5 )
      (**v5)(v5, 1);
  }
  else
  {
    v7 = *(void (__fastcall ****)(_QWORD, __int64))v6;
    if ( *(_QWORD *)v6 )
    {
      LastError = GetLastError();
      (**v7)(v7, 1);
      SetLastError(LastError);
    }
    *(_QWORD *)v6 = v5;
  }
  if ( v22 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v22)[3])(v22);
  v2 = wil::wnf_query_nothrow<_LARGE_INTEGER>(&WNF_WOSC_WHESVC_EXT_CONFIG_CHANGED, &v13, &v16, &v14);
  if ( v2 < 0 )
  {
    v3 = 590;
    goto LABEL_3;
  }
  v20 = off_18002A280;
  v21 = this;
  v22 = &v20;
  v15 = 0;
  v9 = 0;
  v10 = (char *)this + 584;
  if ( (int)wil::details::make_wnf_subscription_state<_LARGE_INTEGER>(
              &WNF_WOSC_WHESVC_EXT_CONFIG_CHANGED,
              v19,
              v14,
              &v15) >= 0 )
    v9 = v15;
  if ( v10 == &v18 )
  {
    if ( v9 )
      (**v9)(v9, 1);
  }
  else
  {
    v11 = *(void (__fastcall ****)(_QWORD, __int64))v10;
    if ( *(_QWORD *)v10 )
    {
      v12 = GetLastError();
      (**v11)(v11, 1);
      SetLastError(v12);
    }
    *(_QWORD *)v10 = v9;
  }
  if ( v22 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v22)[3])(v22);
  return 0;
}

```

## disassembly

```asm
0x1800153dc  push    rbp
0x1800153de  push    rbx
0x1800153df  push    rsi
0x1800153e0  push    rdi
0x1800153e1  push    r14
0x1800153e3  push    r15
0x1800153e5  lea     rbp, [rsp-2Fh]
0x1800153ea  sub     rsp, 0D8h
0x1800153f1  mov     rax, cs:__security_cookie
0x1800153f8  xor     rax, rsp
0x1800153fb  mov     [rbp+57h+var_40], rax
0x1800153ff  mov     r15, rcx
0x180015402  mov     [rsp+100h+var_DC], 0
0x18001540a  lea     rcx, WNF_WOSC_WHESVC_MOD_CONFIG_CHANGED
0x180015411  mov     byte ptr [rsp+100h+var_E0], 0; int
0x180015416  lea     r9, [rsp+100h+var_DC]
0x18001541b  mov     [rbp+57h+var_D0], 0
0x180015423  lea     r8, [rbp+57h+var_D0]
0x180015427  lea     rdx, [rsp+100h+var_E0]
0x18001542c  call    ??$wnf_query_nothrow@T_LARGE_INTEGER@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAT_LARGE_INTEGER@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<_LARGE_INTEGER>(_WNF_STATE_NAME const &,bool *,_LARGE_INTEGER *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180015431  mov     ebx, eax
0x180015433  test    eax, eax
0x180015435  jns     short loc_180015456
0x180015437  mov     edx, 242h; void *
0x18001543c  mov     rcx, [rbp+5Fh]; this
0x180015440  lea     r8, aPcshellBaseWhe_0; "pcshell\\base\\whesvc\\lib\\orchestrato"...
0x180015447  mov     r9d, ebx; char *
0x18001544a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001544f  mov     eax, ebx
0x180015451  jmp     loc_1800155E4
0x180015456  mov     r8d, [rsp+100h+var_DC]
0x18001545b  lea     rax, off_18002A2A8
0x180015462  mov     [rbp+57h+var_B0], rax
0x180015466  lea     r9, [rsp+100h+var_D8]
0x18001546b  lea     rax, [rbp+57h+var_B0]
0x18001546f  mov     [rbp+57h+var_A8], r15
0x180015473  lea     rdx, [rbp+57h+var_B8]
0x180015477  mov     [rbp+57h+var_48], rax
0x18001547b  lea     rcx, WNF_WOSC_WHESVC_MOD_CONFIG_CHANGED
0x180015482  mov     [rsp+100h+var_D8], 0
0x18001548b  call    ??$make_wnf_subscription_state@T_LARGE_INTEGER@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBT_LARGE_INTEGER@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@T_LARGE_INTEGER@@@01@@Z; wil::details::make_wnf_subscription_state<_LARGE_INTEGER>(_WNF_STATE_NAME const &,wistd::function<void (_LARGE_INTEGER const &)> &&,ulong,wil::details::wnf_subscription_state<_LARGE_INTEGER> * *)
0x180015490  xor     ebx, ebx
0x180015492  lea     r14, [r15+240h]
0x180015499  test    eax, eax
0x18001549b  lea     rax, [rbp+57h+var_C8]
0x18001549f  cmovns  rbx, [rsp+100h+var_D8]
0x1800154a5  cmp     r14, rax
0x1800154a8  jz      short loc_1800154DA
0x1800154aa  mov     rsi, [r14]
0x1800154ad  test    rsi, rsi
0x1800154b0  jz      short loc_1800154D5
0x1800154b2  call    cs:__imp_GetLastError
0x1800154b8  mov     rdx, [rsi]
0x1800154bb  mov     rcx, rsi
0x1800154be  mov     edi, eax
0x1800154c0  mov     rax, [rdx]
0x1800154c3  mov     edx, 1
0x1800154c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154cd  mov     ecx, edi; dwErrCode
0x1800154cf  call    cs:__imp_SetLastError
0x1800154d5  mov     [r14], rbx
0x1800154d8  jmp     short loc_1800154F2
0x1800154da  test    rbx, rbx
0x1800154dd  jz      short loc_1800154F2
0x1800154df  mov     rax, [rbx]
0x1800154e2  mov     edx, 1
0x1800154e7  mov     rcx, rbx
0x1800154ea  mov     rax, [rax]
0x1800154ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154f2  mov     rcx, [rbp+57h+var_48]
0x1800154f6  test    rcx, rcx
0x1800154f9  jz      short loc_180015507
0x1800154fb  mov     rax, [rcx]
0x1800154fe  mov     rax, [rax+18h]
0x180015502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015507  lea     r9, [rsp+100h+var_DC]
0x18001550c  lea     r8, [rbp+57h+var_D0]
0x180015510  lea     rdx, [rsp+100h+var_E0]
0x180015515  lea     rcx, WNF_WOSC_WHESVC_EXT_CONFIG_CHANGED
0x18001551c  call    ??$wnf_query_nothrow@T_LARGE_INTEGER@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAT_LARGE_INTEGER@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<_LARGE_INTEGER>(_WNF_STATE_NAME const &,bool *,_LARGE_INTEGER *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180015521  mov     ebx, eax
0x180015523  test    eax, eax
0x180015525  jns     short loc_180015531
0x180015527  mov     edx, 24Eh
0x18001552c  jmp     loc_18001543C
0x180015531  mov     r8d, [rsp+100h+var_DC]
0x180015536  lea     rax, off_18002A280
0x18001553d  mov     [rbp+57h+var_B0], rax
0x180015541  lea     r9, [rsp+100h+var_D8]
0x180015546  lea     rax, [rbp+57h+var_B0]
0x18001554a  mov     [rbp+57h+var_A8], r15
0x18001554e  lea     rdx, [rbp+57h+var_B8]
0x180015552  mov     [rbp+57h+var_48], rax
0x180015556  lea     rcx, WNF_WOSC_WHESVC_EXT_CONFIG_CHANGED
0x18001555d  mov     [rsp+100h+var_D8], 0
0x180015566  call    ??$make_wnf_subscription_state@T_LARGE_INTEGER@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBT_LARGE_INTEGER@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@T_LARGE_INTEGER@@@01@@Z; wil::details::make_wnf_subscription_state<_LARGE_INTEGER>(_WNF_STATE_NAME const &,wistd::function<void (_LARGE_INTEGER const &)> &&,ulong,wil::details::wnf_subscription_state<_LARGE_INTEGER> * *)
0x18001556b  xor     ebx, ebx
0x18001556d  lea     r14, [r15+248h]
0x180015574  test    eax, eax
0x180015576  lea     rax, [rbp+57h+var_C0]
0x18001557a  cmovns  rbx, [rsp+100h+var_D8]
0x180015580  cmp     r14, rax
0x180015583  jz      short loc_1800155B5
0x180015585  mov     rsi, [r14]
0x180015588  test    rsi, rsi
0x18001558b  jz      short loc_1800155B0
0x18001558d  call    cs:__imp_GetLastError
0x180015593  mov     r8, [rsi]
0x180015596  mov     edx, 1
0x18001559b  mov     edi, eax
0x18001559d  mov     rcx, rsi
0x1800155a0  mov     rax, [r8]
0x1800155a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155a8  mov     ecx, edi; dwErrCode
0x1800155aa  call    cs:__imp_SetLastError
0x1800155b0  mov     [r14], rbx
0x1800155b3  jmp     short loc_1800155CD
0x1800155b5  test    rbx, rbx
0x1800155b8  jz      short loc_1800155CD
0x1800155ba  mov     rax, [rbx]
0x1800155bd  mov     edx, 1
0x1800155c2  mov     rcx, rbx
0x1800155c5  mov     rax, [rax]
0x1800155c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155cd  mov     rcx, [rbp+57h+var_48]
0x1800155d1  test    rcx, rcx
0x1800155d4  jz      short loc_1800155E2
0x1800155d6  mov     rax, [rcx]
0x1800155d9  mov     rax, [rax+18h]
0x1800155dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e2  xor     eax, eax
0x1800155e4  mov     rcx, [rbp+57h+var_40]
0x1800155e8  xor     rcx, rsp; StackCookie
0x1800155eb  call    __security_check_cookie
0x1800155f0  add     rsp, 0D8h
0x1800155f7  pop     r15
0x1800155f9  pop     r14
0x1800155fb  pop     rdi
0x1800155fc  pop     rsi
0x1800155fd  pop     rbx
0x1800155fe  pop     rbp
0x1800155ff  retn
```
