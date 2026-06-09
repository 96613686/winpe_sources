# UserMgrCli::RpcInitialize(void)

- ea: `0x1800b542c`
- end: `0x1800b5698`
- name: `?RpcInitialize@UserMgrCli@@QEAAJXZ`
- size: `620`
- prototype: `__int64 __fastcall(UserMgrCli *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180072004`

## callees

- `0x180012890`
- `0x180015250`
- `0x18002799c`
- `0x18004e508`
- `0x18004e58c`
- `0x1800b2564`
- `0x1800b542c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b5472`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b5472`
- `RPCRT4!RpcEpRegisterW` at `0x1800b551b`
- `RPCRT4!RpcEpRegisterW` at `0x1800b5588`
- `RPCRT4!RpcEpRegisterW` at `0x1800b551b`
- `RPCRT4!RpcEpRegisterW` at `0x1800b5588`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800b54f2`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800b555f`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800b54f2`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800b555f`
- `RPCRT4!RpcServerInqBindings` at `0x1800b54ae`
- `RPCRT4!RpcServerInqBindings` at `0x1800b54ae`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800b5496`
- `RPCRT4!RpcServerUseProtseqW` at `0x1800b5496`

## string_xrefs

- `0x1800b560d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5621`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5635`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5649`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b565d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5671`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b5685`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserMgrCli::RpcInitialize(UserMgrCli *this)
{
  const struct _tlgProvider_t *v1; // rax
  const char *v2; // r9
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  RPC_BINDING_VECTOR **v13; // rbp
  const struct _tlgProvider_t *v14; // rax
  int v15; // ebx
  wil *v16; // rcx
  int v17; // r8d
  int v18; // r9d
  RPC_BINDING_VECTOR **v19; // rdx
  __int64 v20; // [rsp+0h] [rbp-48h] BYREF
  unsigned int v21[2]; // [rsp+20h] [rbp-28h]
  int v22; // [rsp+28h] [rbp-20h]
  __int64 v23; // [rsp+30h] [rbp-18h]
  PSECURITY_DESCRIPTOR v24; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  UserMgrCli *v26; // [rsp+50h] [rbp+8h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+58h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+18h] BYREF

  v26 = this;
  v1 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v1 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v1,
      qword_180128CE8,
      0);
  BindingVector = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;RC)(A;;GR;;;WD)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-1788129303-2183208577-399"
           "9474272-3147359985-1757322193-3815756386-151582180-1888101193)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    try
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD80,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v2);
    }
    catch ( ... )
    {
      v19 = (RPC_BINDING_VECTOR **)&v20;
      v13 = v19;
      RpcServerUnregisterIf(qword_180105870, 0, 1u);
      RpcEpUnregister(qword_180105870, v13[11], 0);
      if ( v13[11] )
      {
        RpcBindingVectorFree(v13 + 11);
        v13[11] = 0;
      }
      v14 = UserMgrUserModelTelemetry::Provider();
      v15 = (int)v14;
      v16 = (wil *)*(unsigned int *)v14;
      if ( (unsigned int)v16 > 4 )
      {
        *((_DWORD *)v13 + 20) = wil::ResultFromCaughtException(v16);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v15,
          (unsigned int)byte_180128C0D,
          v17,
          v18,
          (__int64)(v13 + 10));
      }
      *((_DWORD *)v13 + 20) = wil::ResultFromCaughtException(v16);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
      return (unsigned int)v26;
    }
  }
  v3 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xD89,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)v3,
      v21[0]);
  v4 = RpcServerInqBindings(&BindingVector);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xD8F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)v4,
      v21[0]);
  v24 = SecurityDescriptor;
  v23 = 0;
  v22 = -1;
  v21[0] = 1234;
  v5 = RpcServerRegisterIf3(qword_180105870, 0, 0, 41);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xDA2,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)v5,
      v21[0]);
  v6 = RpcEpRegisterW(qword_180105870, BindingVector, 0, (RPC_WSTR)L"UserMgrCli");
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xDAB,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)v6,
      v21[0]);
  v24 = SecurityDescriptor;
  v23 = 0;
  v22 = -1;
  v21[0] = 1234;
  v7 = RpcServerRegisterIf3(qword_180105EF0, 0, 0, 41);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xDB5,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)v7,
      v21[0]);
  v8 = RpcEpRegisterW(qword_180105EF0, BindingVector, 0, (RPC_WSTR)L"UserMgrCli");
  if ( v8 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xDBA,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)v8,
      v21[0]);
  g_userMgrCli = (__int64)BindingVector;
  BindingVector = 0;
  *(_OWORD *)&pv = 0;
  dword_1801481B0 = -1;
  v9 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v9 > 4u )
  {
    LODWORD(v26) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (_DWORD)v9,
      (unsigned int)word_180128C52,
      v10,
      v11,
      (__int64)&v26);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x1800b542c  mov     [rsp+arg_0], rcx
0x1800b5431  push    rbx
0x1800b5432  sub     rsp, 40h
0x1800b5436  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b543b  mov     ecx, [rax]
0x1800b543d  cmp     ecx, 4
0x1800b5440  jbe     short loc_1800B5454
0x1800b5442  xor     r8d, r8d
0x1800b5445  lea     rdx, qword_180128CE8
0x1800b544c  mov     rcx, rax
0x1800b544f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b5454  xor     ebx, ebx
0x1800b5456  mov     [rsp+48h+BindingVector], rbx
0x1800b545b  mov     [rsp+48h+SecurityDescriptor], rbx
0x1800b5460  xor     r9d, r9d; SecurityDescriptorSize
0x1800b5463  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1800b5468  lea     edx, [rbx+1]; StringSDRevision
0x1800b546b  lea     rcx, aDAGaSyAGaBaAGr; "D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;RC)("...
0x1800b5472  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b5478  mov     rcx, [rsp+48h]; this
0x1800b547d  test    eax, eax
0x1800b547f  jz      loc_1800B560D
0x1800b5485  mov     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x1800b548a  mov     edx, 0Ah; MaxCalls
0x1800b548f  lea     rcx, Protseq; "ncalrpc"
0x1800b5496  call    cs:__imp_RpcServerUseProtseqW
0x1800b549c  mov     rcx, [rsp+48h]; this
0x1800b54a1  test    eax, eax
0x1800b54a3  jnz     loc_1800B561E
0x1800b54a9  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x1800b54ae  call    cs:__imp_RpcServerInqBindings
0x1800b54b4  mov     rcx, [rsp+48h]; this
0x1800b54b9  test    eax, eax
0x1800b54bb  jnz     loc_1800B5632
0x1800b54c1  mov     rax, [rsp+48h+SecurityDescriptor]
0x1800b54c6  mov     [rsp+48h+var_10], rax
0x1800b54cb  mov     [rsp+48h+var_18], rbx
0x1800b54d0  mov     [rsp+48h+var_20], 0FFFFFFFFh
0x1800b54d8  mov     [rsp+48h+var_28], 4D2h; unsigned int
0x1800b54e0  mov     r9d, 29h ; ')'
0x1800b54e6  xor     r8d, r8d
0x1800b54e9  xor     edx, edx
0x1800b54eb  lea     rcx, qword_180105870
0x1800b54f2  call    cs:__imp_RpcServerRegisterIf3
0x1800b54f8  mov     rcx, [rsp+48h]; this
0x1800b54fd  test    eax, eax
0x1800b54ff  jnz     loc_1800B5646
0x1800b5505  lea     r9, Annotation; "UserMgrCli"
0x1800b550c  xor     r8d, r8d; UuidVector
0x1800b550f  mov     rdx, [rsp+48h+BindingVector]; BindingVector
0x1800b5514  lea     rcx, qword_180105870; IfSpec
0x1800b551b  call    cs:__imp_RpcEpRegisterW
0x1800b5521  mov     rcx, [rsp+48h]; this
0x1800b5526  test    eax, eax
0x1800b5528  jnz     loc_1800B565A
0x1800b552e  mov     rax, [rsp+48h+SecurityDescriptor]
0x1800b5533  mov     [rsp+48h+var_10], rax
0x1800b5538  mov     [rsp+48h+var_18], rbx
0x1800b553d  mov     [rsp+48h+var_20], 0FFFFFFFFh
0x1800b5545  mov     [rsp+48h+var_28], 4D2h; unsigned int
0x1800b554d  mov     r9d, 29h ; ')'
0x1800b5553  xor     r8d, r8d
0x1800b5556  xor     edx, edx
0x1800b5558  lea     rcx, qword_180105EF0
0x1800b555f  call    cs:__imp_RpcServerRegisterIf3
0x1800b5565  mov     rcx, [rsp+48h]; this
0x1800b556a  test    eax, eax
0x1800b556c  jnz     loc_1800B566E
0x1800b5572  lea     r9, Annotation; "UserMgrCli"
0x1800b5579  xor     r8d, r8d; UuidVector
0x1800b557c  mov     rdx, [rsp+48h+BindingVector]; BindingVector
0x1800b5581  lea     rcx, qword_180105EF0; IfSpec
0x1800b5588  call    cs:__imp_RpcEpRegisterW
0x1800b558e  mov     rcx, [rsp+48h]; this
0x1800b5593  test    eax, eax
0x1800b5595  jnz     loc_1800B5682
0x1800b559b  mov     rax, [rsp+48h+BindingVector]
0x1800b55a0  mov     cs:?g_userMgrCli@@3VUserMgrCli@@A, rax; UserMgrCli g_userMgrCli
0x1800b55a7  mov     [rsp+48h+BindingVector], rbx
0x1800b55ac  xorps   xmm0, xmm0
0x1800b55af  movdqa  cs:pv, xmm0
0x1800b55b7  mov     cs:dword_1801481B0, 0FFFFFFFFh
0x1800b55c1  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b55c6  mov     ecx, [rax]
0x1800b55c8  cmp     ecx, 4
0x1800b55cb  jbe     short loc_1800B55EB
0x1800b55cd  mov     dword ptr [rsp+48h+arg_0], ebx
0x1800b55d1  lea     rcx, [rsp+48h+arg_0]
0x1800b55d6  mov     qword ptr [rsp+48h+var_28], rcx
0x1800b55db  lea     rdx, word_180128C52
0x1800b55e2  mov     rcx, rax
0x1800b55e5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800b55ea  nop
0x1800b55eb  lea     rcx, [rsp+48h+SecurityDescriptor]
0x1800b55f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800b55f5  xor     eax, eax
0x1800b55f7  jmp     short loc_1800B5607
0x1800b55f9  lea     rcx, [rsp+48h+SecurityDescriptor]
0x1800b55fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800b5603  mov     eax, dword ptr [rsp+48h+arg_0]
0x1800b5607  add     rsp, 40h
0x1800b560b  pop     rbx
0x1800b560c  retn
0x1800b560d  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5614  mov     edx, 0D80h; void *
0x1800b5619  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800b561e  mov     r9d, eax; char *
0x1800b5621  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5628  mov     edx, 0D89h; void *
0x1800b562d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b5632  mov     r9d, eax; char *
0x1800b5635  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b563c  mov     edx, 0D8Fh; void *
0x1800b5641  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b5646  mov     r9d, eax; char *
0x1800b5649  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5650  mov     edx, 0DA2h; void *
0x1800b5655  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b565a  mov     r9d, eax; char *
0x1800b565d  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5664  mov     edx, 0DABh; void *
0x1800b5669  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b566e  mov     r9d, eax; char *
0x1800b5671  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b5678  mov     edx, 0DB5h; void *
0x1800b567d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800b5682  mov     r9d, eax; char *
0x1800b5685  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x1800b568c  mov     edx, 0DBAh; void *
0x1800b5691  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
