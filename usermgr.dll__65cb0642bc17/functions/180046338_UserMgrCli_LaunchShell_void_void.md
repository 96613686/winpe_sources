# UserMgrCli::LaunchShell(void *,void * *)

- ea: `0x180046338`
- end: `0x1800465de`
- name: `?LaunchShell@UserMgrCli@@QEAAJPEAXPEAPEAX@Z`
- size: `678`
- prototype: `__int64 __fastcall(UserMgrCli *__hidden this, void *, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b5f80`

## callees

- `0x180008b10`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c350`
- `0x18000c6d0`
- `0x180012740`
- `0x180012890`
- `0x180015250`
- `0x180015960`
- `0x18002799c`
- `0x180046338`
- `0x180046dd4`
- `0x18004e58c`
- `0x18005f5f0`
- `0x18006da60`
- `0x18006f1c9`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180046475`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180046475`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180046420`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180046420`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180046408`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180046408`

## string_xrefs

- `0x180046556`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18004656a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18004657b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18004658f`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800465a0`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800465b7`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800465cb`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserMgrCli::LaunchShell(UserMgrCli *this, void *a2, void **a3)
{
  unsigned __int64 v3; // rbp
  const struct _tlgProvider_t *v5; // rax
  void *v6; // rdx
  int BasicCallerInformation; // eax
  __int64 v8; // rcx
  const char *v9; // r9
  UserManagerTokenAndShellHandler *v10; // rbx
  unsigned int v11; // edx
  int SessionUserToken; // eax
  const char *v13; // r9
  void *v14; // rbx
  int v15; // eax
  const struct _tlgProvider_t *v16; // rax
  int v17; // r8d
  int v18; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v20; // rax
  int v21; // ebx
  wil *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  int ReturnLength; // [rsp+20h] [rbp-30h]
  int ReturnLengtha; // [rsp+20h] [rbp-30h]
  bool v27[4]; // [rsp+50h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+288h] [rbp+238h]

  v3 = (unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL;
  v5 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v5 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v5,
      &unk_18012A0B0,
      0);
  memset_0((void *)(v3 + 32), 0, 0x1A0u);
  try
  {
    *(_QWORD *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_QWORD *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    *(_DWORD *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    *(_BYTE *)v3 = 0;
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4DB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        ReturnLength);
    *a3 = 0;
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               retaddr,
                               v6,
                               (struct _BASIC_CALLER_INFORMATION *)(v3 + 32));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4DE,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        ReturnLength);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v3 + 32),
      (const struct _CALLER_RESTRICTIONS *)byte_1801135F0);
    if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v3 + 8,
        0);
      if ( !WTSQueryUserToken(*(_DWORD *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28), (PHANDLE)(v3 + 8)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x4E5,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          v9);
    }
    else
    {
      RtlGetCurrentServiceSessionId(v8);
      v10 = (UserManagerTokenAndShellHandler *)qword_180148188;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v3 + 8,
        0);
      SessionUserToken = UserManagerTokenAndShellHandler::QuerySessionUserToken(v10, v11, 0, (void **)(v3 + 8));
      if ( SessionUserToken < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4EA,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)SessionUserToken,
          ReturnLength);
    }
    if ( !GetTokenInformation(
            *(HANDLE *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 8),
            TokenUser,
            (LPVOID)(v3 + 448),
            0x54u,
            (PDWORD)(v3 + 24)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x4ED,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v13);
    v14 = *(void **)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 0x1C0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v3 + 16,
      0);
    GetCallerToken((PHANDLE)(v3 + 16));
    IsTokenILMediumOrGreaterForUserOrLocalSystem(
      *(HANDLE *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10),
      v14,
      (bool *)((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL));
    if ( !*(_BYTE *)v3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        ReturnLengtha);
    v15 = UserManagerTokenAndShellHandler::LaunchShell(
            (UserManagerTokenAndShellHandler *)qword_180148188,
            *(_DWORD *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
            0);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v15,
        ReturnLengtha);
    v16 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v16 > 4u )
    {
      *(_DWORD *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (_DWORD)v16,
        (unsigned int)&word_18012A01E,
        v17,
        v18,
        v3 + 4);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v3 + 16);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v3 + 8);
    result = 0;
  }
  catch ( ... )
  {
    v20 = UserMgrUserModelTelemetry::Provider();
    v21 = (int)v20;
    v22 = (wil *)*(unsigned int *)v20;
    if ( (unsigned int)v22 > 4 )
    {
      *(_DWORD *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = wil::ResultFromCaughtException(v22);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&word_180129F9E,
        v23,
        v24,
        ((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
    }
    *(_DWORD *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = wil::ResultFromCaughtException(v22);
    return *(unsigned int *)(((unsigned __int64)v27 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
  }
  return result;
}

```

## disassembly

```asm
0x180046338  mov     [rsp-8+arg_0], rbx
0x18004633d  push    rbp
0x18004633e  sub     rsp, 280h
0x180046345  lea     rbp, [rsp+50h]
0x18004634a  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18004634e  mov     rax, cs:__security_cookie
0x180046355  xor     rax, rsp
0x180046358  mov     [rbp+230h+var_10], rax
0x18004635f  mov     rbx, r8
0x180046362  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180046367  mov     ecx, [rax]
0x180046369  cmp     ecx, 4
0x18004636c  jbe     short loc_180046380
0x18004636e  xor     r8d, r8d
0x180046371  lea     rdx, unk_18012A0B0
0x180046378  mov     rcx, rax
0x18004637b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180046380  xor     edx, edx; Val
0x180046382  mov     r8d, 1A0h; Size
0x180046388  lea     rcx, [rbp+230h+var_210]; void *
0x18004638c  call    memset_0
0x180046391  mov     [rbp+230h+phToken], 0
0x180046399  mov     [rbp+230h+phNewToken], 0
0x1800463a1  mov     [rbp+230h+var_218], 0
0x1800463a8  mov     [rbp+230h+var_230], 0
0x1800463ac  mov     rcx, [rsp+288h]; this
0x1800463b4  test    rbx, rbx
0x1800463b7  jz      loc_180046550
0x1800463bd  mov     qword ptr [rbx], 0
0x1800463c4  lea     r8, [rbp+230h+var_210]; struct _BASIC_CALLER_INFORMATION *
0x1800463c8  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x1800463cd  mov     rcx, [rsp+288h]; this
0x1800463d5  test    eax, eax
0x1800463d7  js      loc_180046567
0x1800463dd  lea     r8, byte_1801135F0; struct _CALLER_RESTRICTIONS *
0x1800463e4  lea     rdx, [rbp+230h+var_210]; struct _BASIC_CALLER_INFORMATION *
0x1800463e8  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x1800463ed  call    IsWTSEnumerateSessionsWPresent
0x1800463f2  test    al, al
0x1800463f4  jz      short loc_180046420
0x1800463f6  xor     edx, edx
0x1800463f8  lea     rcx, [rbp+230h+phToken]
0x1800463fc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180046401  lea     rdx, [rbp+230h+phToken]; phToken
0x180046405  mov     ecx, [rbp+230h+SessionId]; SessionId
0x180046408  call    cs:__imp_WTSQueryUserToken
0x18004640e  mov     rcx, [rsp+288h]; this
0x180046416  test    eax, eax
0x180046418  jz      loc_18004657B
0x18004641e  jmp     short loc_180046457
0x180046420  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180046426  mov     rbx, cs:qword_180148188
0x18004642d  xor     edx, edx
0x18004642f  lea     rcx, [rbp+230h+phToken]
0x180046433  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180046438  lea     r9, [rbp+230h+phToken]; void **
0x18004643c  xor     r8d, r8d; int
0x18004643f  mov     rcx, rbx; this
0x180046442  call    ?QuerySessionUserToken@UserManagerTokenAndShellHandler@@QEAAJKHPEAPEAX@Z; UserManagerTokenAndShellHandler::QuerySessionUserToken(ulong,int,void * *)
0x180046447  mov     rcx, [rsp+288h]; this
0x18004644f  test    eax, eax
0x180046451  js      loc_18004658C
0x180046457  lea     rax, [rbp+230h+var_218]
0x18004645b  mov     qword ptr [rsp+280h+ReturnLength], rax; int
0x180046460  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180046466  lea     r8, [rbp+230h+TokenInformation]; TokenInformation
0x18004646d  lea     edx, [r9-53h]; TokenInformationClass
0x180046471  mov     rcx, [rbp+230h+phToken]; TokenHandle
0x180046475  call    cs:__imp_GetTokenInformation
0x18004647b  mov     rcx, [rsp+288h]; this
0x180046483  test    eax, eax
0x180046485  jz      loc_1800465A0
0x18004648b  mov     rbx, [rbp+230h+TokenInformation]
0x180046492  xor     edx, edx
0x180046494  lea     rcx, [rbp+230h+phNewToken]
0x180046498  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004649d  lea     rcx, [rbp+230h+phNewToken]; phNewToken
0x1800464a1  call    ?GetCallerToken@@YAJPEAPEAX@Z; GetCallerToken(void * *)
0x1800464a6  lea     r8, [rbp+230h+var_230]; bool *
0x1800464aa  mov     rdx, rbx; void *
0x1800464ad  mov     rcx, [rbp+230h+phNewToken]; ClientToken
0x1800464b1  call    ?IsTokenILMediumOrGreaterForUserOrLocalSystem@@YAJPEAX0PEA_N@Z; IsTokenILMediumOrGreaterForUserOrLocalSystem(void *,void *,bool *)
0x1800464b6  mov     rcx, [rsp+288h]; this
0x1800464be  cmp     [rbp+230h+var_230], 0
0x1800464c2  jz      loc_1800465B1
0x1800464c8  xor     r8d, r8d; int
0x1800464cb  mov     edx, [rbp+230h+SessionId]; unsigned int
0x1800464ce  mov     rcx, cs:qword_180148188; this
0x1800464d5  call    ?LaunchShell@UserManagerTokenAndShellHandler@@QEAAJKH@Z; UserManagerTokenAndShellHandler::LaunchShell(ulong,int)
0x1800464da  mov     rcx, [rsp+288h]; this
0x1800464e2  test    eax, eax
0x1800464e4  js      loc_1800465C8
0x1800464ea  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800464ef  mov     ecx, [rax]
0x1800464f1  cmp     ecx, 4
0x1800464f4  jbe     short loc_180046516
0x1800464f6  mov     [rbp+230h+var_22C], 0
0x1800464fd  lea     rcx, [rbp+230h+var_22C]
0x180046501  mov     qword ptr [rsp+280h+ReturnLength], rcx
0x180046506  lea     rdx, word_18012A01E
0x18004650d  mov     rcx, rax
0x180046510  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180046515  nop
0x180046516  lea     rcx, [rbp+230h+phNewToken]
0x18004651a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004651f  nop
0x180046520  lea     rcx, [rbp+230h+phToken]
0x180046524  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180046529  xor     eax, eax
0x18004652b  jmp     short loc_180046530
0x18004652d  mov     eax, [rbp+230h+var_22C]
0x180046530  mov     rcx, [rbp+230h+var_10]
0x180046537  xor     rcx, rsp; StackCookie
0x18004653a  call    __security_check_cookie
0x18004653f  mov     rbx, [rsp+280h+arg_0]
0x180046547  add     rsp, 280h
0x18004654e  pop     rbp
0x18004654f  retn
0x180046550  mov     r9d, 80070057h; char *
0x180046556  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18004655d  mov     edx, 4DBh; void *
0x180046562  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046567  mov     r9d, eax; char *
0x18004656a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180046571  mov     edx, 4DEh; void *
0x180046576  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004657b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180046582  mov     edx, 4E5h; void *
0x180046587  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004658c  mov     r9d, eax; char *
0x18004658f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180046596  mov     edx, 4EAh; void *
0x18004659b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800465a0  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800465a7  mov     edx, 4EDh; void *
0x1800465ac  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800465b1  mov     r9d, 80070005h; char *
0x1800465b7  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800465be  mov     edx, 4F2h; void *
0x1800465c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800465c8  mov     r9d, eax; char *
0x1800465cb  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800465d2  mov     edx, 4F4h; void *
0x1800465d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
