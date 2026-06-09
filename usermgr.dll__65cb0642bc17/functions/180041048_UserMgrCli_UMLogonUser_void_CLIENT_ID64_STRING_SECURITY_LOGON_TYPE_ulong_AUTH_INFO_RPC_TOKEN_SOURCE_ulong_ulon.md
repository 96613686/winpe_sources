# UserMgrCli::UMLogonUser(void *,_CLIENT_ID64 *,_STRING *,_SECURITY_LOGON_TYPE,ulong,_AUTH_INFO_RPC *,_TOKEN_SOURCE *,ulong,ulong,ulong,uchar *,_TOKEN_GROUPS *,long *,long *,ulong *,uchar * *,unsigned __int64 *,_LUID *,void * *,_QUOTA_LIMITS_RPC *)

- ea: `0x180041048`
- end: `0x1800416e7`
- name: `?UMLogonUser@UserMgrCli@@QEAAJPEAXPEAU_CLIENT_ID64@@PEAU_STRING@@W4_SECURITY_LOGON_TYPE@@KPEAU_AUTH_INFO_RPC@@PEAU_TOKEN_SOURCE@@KKKPEAEPEAU_TOKEN_GROUPS@@PEAJ8PEAKPEAPEAEPEA_KPEAU_LUID@@PEAPEAXPEAU_QUOTA_LIMITS_RPC@@@Z`
- size: `1695`
- prototype: `int(UserMgrCli *__hidden this, void *, struct _CLIENT_ID64 *, struct _STRING *, enum _SECURITY_LOGON_TYPE, unsigned int, struct _AUTH_INFO_RPC *, struct _TOKEN_SOURCE *, unsigned int, unsigned int, unsigned int, unsigned __int8 *, struct _TOKEN_GROUPS *, int *, int *, unsigned int *, unsigned __int8 **, unsigned __int64 *, struct _LUID *, void **, struct _QUOTA_LIMITS_RPC *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040f60`

## callees

- `0x180008b10`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c6d0`
- `0x180012890`
- `0x180015250`
- `0x180015960`
- `0x18002799c`
- `0x180035938`
- `0x18003af38`
- `0x18003afd4`
- `0x18003db88`
- `0x180041048`
- `0x18004e4e8`
- `0x18004e508`
- `0x18004e58c`
- `0x18006c426`
- `0x18006f1c9`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004144d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004144d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041471`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180041471`
- `ntdll!RtlNtStatusToDosError` at `0x180041486`
- `ntdll!RtlNtStatusToDosError` at `0x180041486`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x180041329`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x180041329`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180041318`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180041318`
- `SspiCli!LsaLogonUser` at `0x1800413dc`
- `SspiCli!LsaLogonUser` at `0x1800413dc`
- `RPCRT4!RpcImpersonateClient` at `0x180041331`
- `RPCRT4!RpcImpersonateClient` at `0x180041331`

## string_xrefs

- `0x180041575`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18004158c`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800415a3`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800415ba`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800415d1`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800415e8`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800415ff`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180041616`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180041630`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180041647`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18004165e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180041673`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180041687`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18004169b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800416af`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800416c0`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800416d4`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserMgrCli::UMLogonUser(
        UserMgrCli *this,
        void *a2,
        struct _CLIENT_ID64 *a3,
        struct _LSA_STRING *a4,
        SECURITY_LOGON_TYPE LogonType,
        ULONG AuthenticationPackage,
        void **a7,
        struct _TOKEN_SOURCE *a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned __int8 *a12,
        struct _TOKEN_GROUPS *LocalGroups,
        int *a14,
        int *SubStatus,
        unsigned int *a16,
        unsigned __int8 **a17,
        unsigned __int64 *a18,
        struct _LUID *a19,
        void **a20,
        struct _QUOTA_LIMITS_RPC *a21)
{
  unsigned __int64 v21; // rbp
  const struct _tlgProvider_t *v24; // rax
  void *v25; // rdx
  UserMgrCli *v26; // rcx
  int BasicCallerInformation; // eax
  char v28; // al
  char v29; // al
  DWORD i; // ecx
  int v31; // eax
  int v32; // eax
  unsigned int v33; // eax
  int LsaHandle; // eax
  __int64 result; // rax
  const char *v36; // r9
  SIZE_T v37; // rdx
  HLOCAL v38; // rbx
  void **v39; // rsi
  signed int v40; // eax
  const struct _tlgProvider_t *v41; // rax
  int v42; // r8d
  int v43; // r9d
  _DWORD *v44; // rbp
  const struct _tlgProvider_t *v45; // rax
  int v46; // ebx
  wil *v47; // rcx
  int v48; // r8d
  int v49; // r9d
  int AuthenticationInformation; // [rsp+20h] [rbp-70h]
  unsigned int AuthenticationInformationa; // [rsp+20h] [rbp-70h]
  int AuthenticationInformationb; // [rsp+20h] [rbp-70h]
  ULONG v53; // [rsp+90h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+368h] [rbp+2D8h]

  v21 = (unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = a8;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = a12;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = a16;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = a17;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = a18;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = a19;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = a20;
  v24 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v24 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v24,
      byte_180129223,
      0);
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  *(_DWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_OWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0) = 0;
  *(_OWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0) = 0;
  *(_OWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = 0;
  *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  *(_DWORD *)v21 = 0;
  memset_0((void *)(v21 + 224), 0, 0x1A0u);
  *(_DWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_DWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
  *(_DWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  try
  {
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               v26,
                               v25,
                               (struct _BASIC_CALLER_INFORMATION *)(v21 + 224));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        AuthenticationInformation);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v21 + 224),
      (const struct _CALLER_RESTRICTIONS *)byte_1801135E8);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        AuthenticationInformation);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        AuthenticationInformation);
    if ( !a4->Length || (v28 = 1, a4->Buffer) )
      v28 = 0;
    if ( v28 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9FA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        AuthenticationInformation);
    if ( !a7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9FC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        AuthenticationInformation);
    if ( !*(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9FF,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        AuthenticationInformation);
    if ( LocalGroups )
    {
      if ( !LocalGroups->GroupCount || (v29 = 1, LocalGroups != (struct _TOKEN_GROUPS *)-8LL) )
        v29 = 0;
      if ( v29 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA02,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)0x80070057LL,
          AuthenticationInformation);
      for ( i = 0; i < LocalGroups->GroupCount; ++i )
      {
        if ( !LocalGroups->Groups[i].Sid )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xA05,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
            (const char *)0x80070057LL,
            AuthenticationInformation);
      }
    }
    if ( !SubStatus )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA09,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        AuthenticationInformation);
    if ( !*(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA0A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        AuthenticationInformation);
    if ( !a21 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        AuthenticationInformation);
    *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70) = ((unsigned __int64)&v53
                                                                          & 0xFFFFFFFFFFFFFFE0uLL)
                                                                         + 40;
    *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = ((unsigned __int64)&v53
                                                                          & 0xFFFFFFFFFFFFFFE0uLL)
                                                                         + 32;
    *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = ((unsigned __int64)&v53
                                                                          & 0xFFFFFFFFFFFFFFE0uLL)
                                                                         + 8;
    *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = ((unsigned __int64)&v53
                                                                          & 0xFFFFFFFFFFFFFFE0uLL)
                                                                         + 12;
    *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x90) = ((unsigned __int64)&v53
                                                                          & 0xFFFFFFFFFFFFFFE0uLL)
                                                                         + 16;
    *(_BYTE *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = 1;
    v31 = WrapWlAuthInfo(
            a7[2],
            *(unsigned int *)a7,
            *(_DWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE8),
            (struct _WL_AUTH_INFO **)(v21 + 40),
            (unsigned int *)((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL));
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA30,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v31,
        AuthenticationInformationa);
    if ( a10 )
    {
      v32 = SetNtlmThreadOptions(0, a10);
      if ( v32 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xA34,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v32,
          AuthenticationInformationa);
    }
    SeciAllocateAndSetIPAddress(*(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48), a11, v21 + 8);
    SeciAllocateAndSetCallFlags(a9, v21 + 12);
    v33 = RpcImpersonateClient(0);
    if ( v33 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA40,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)v33,
        AuthenticationInformationa);
    *(_DWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 1;
    LsaHandle = UserMgrCli::GetLsaHandle(retaddr, (void **)(v21 + 64));
    if ( LsaHandle < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA44,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)LsaHandle,
        AuthenticationInformationa);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v21 + 24,
      0);
    *a14 = LsaLogonUser(
             *(HANDLE *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40),
             a4,
             LogonType,
             AuthenticationPackage,
             *(PVOID *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
             *(_DWORD *)v21,
             LocalGroups,
             *(PTOKEN_SOURCE *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38),
             (PVOID *)(v21 + 32),
             (PULONG)(v21 + 4),
             *(PLUID *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
             (PHANDLE)(v21 + 24),
             (PQUOTA_LIMITS)(v21 + 160),
             SubStatus);
    if ( a10 )
      SetNtlmThreadOptions(1, a10);
    if ( *a14 >= 0 )
    {
      if ( !DuplicateTokenEx(
              *(HANDLE *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
              0,
              0,
              (SECURITY_IMPERSONATION_LEVEL)((*(_BYTE *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) != 0)
                                           + 1),
              (TOKEN_TYPE)(2 - (*(_BYTE *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) != 0)),
              *(PHANDLE *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xA65,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          v36);
      v37 = *(unsigned int *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
      **(_DWORD **)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = v37;
      v38 = LocalAlloc(0x40u, v37);
      v39 = *(void ***)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60);
      *v39 = v38;
      v40 = RtlNtStatusToDosError(-1073741670);
      if ( v40 > 0 )
        v40 = (unsigned __int16)v40 | 0x80070000;
      if ( !v38 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA6B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v40,
          AuthenticationInformationb);
      memcpy_0(
        *v39,
        *(const void **)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
        *(unsigned int *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 4));
      **(_QWORD **)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = *(_QWORD *)(((unsigned __int64)&v53
                                                                                          & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                         + 0x20);
      *((_QWORD *)a21 + 3) = *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB8);
      *((_QWORD *)a21 + 2) = *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB0);
      *((_QWORD *)a21 + 1) = *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA8);
      *(_QWORD *)a21 = *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0);
      *((_QWORD *)a21 + 4) = *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0);
      *((_QWORD *)a21 + 5) = *(_QWORD *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8);
      v41 = UserMgrUserModelTelemetry::Provider();
      if ( *(_DWORD *)v41 > 5u )
      {
        *(_DWORD *)v21 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (_DWORD)v41,
          (unsigned int)byte_1801291F3,
          v42,
          v43,
          (unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL);
      }
    }
    *(_BYTE *)(((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = 0;
    lambda_93d6174e76a59b044fd992c4c32d1add_::operator()(v21 + 112);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v21 + 24);
    result = 0;
  }
  catch ( ... )
  {
    v44 = (_DWORD *)((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL);
    v45 = UserMgrUserModelTelemetry::Provider();
    v46 = (int)v45;
    v47 = (wil *)*(unsigned int *)v45;
    if ( (unsigned int)v47 > 5 )
    {
      *v44 = wil::ResultFromCaughtException(v47);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v46,
        (unsigned int)byte_180129169,
        v48,
        v49,
        (__int64)v44);
    }
    *v44 = wil::ResultFromCaughtException(v47);
    return *(unsigned int *)((unsigned __int64)&v53 & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return result;
}

```

## disassembly

```asm
0x180041048  push    rbp
0x18004104a  push    rbx
0x18004104b  push    rsi
0x18004104c  push    rdi
0x18004104d  push    r12
0x18004104f  push    r13
0x180041051  push    r14
0x180041053  push    r15
0x180041055  sub     rsp, 328h
0x18004105c  lea     rbp, [rsp+90h]
0x180041064  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180041068  mov     rax, cs:__security_cookie
0x18004106f  xor     rax, rsp
0x180041072  mov     [rbp+2D0h+var_50], rax
0x180041079  mov     r14, r9
0x18004107c  mov     rbx, r8
0x18004107f  mov     rdi, [rsp+360h+arg_A0]
0x180041087  mov     r15, [rsp+360h+arg_30]
0x18004108f  mov     rsi, [rsp+360h+arg_60]
0x180041097  mov     rax, [rsp+360h+arg_38]
0x18004109f  mov     [rbp+2D0h+var_298], rax
0x1800410a3  mov     rax, [rsp+360h+arg_58]
0x1800410ab  mov     [rbp+2D0h+var_288], rax
0x1800410af  mov     r12, [rsp+360h+arg_68]
0x1800410b7  mov     r13, [rsp+360h+arg_70]
0x1800410bf  mov     rax, [rsp+360h+arg_78]
0x1800410c7  mov     [rbp+2D0h+var_278], rax
0x1800410cb  mov     rax, [rsp+360h+arg_80]
0x1800410d3  mov     [rbp+2D0h+var_270], rax
0x1800410d7  mov     rax, [rsp+360h+arg_88]
0x1800410df  mov     [rbp+2D0h+var_268], rax
0x1800410e3  mov     rax, [rsp+360h+arg_90]
0x1800410eb  mov     [rbp+2D0h+var_2A0], rax
0x1800410ef  mov     rax, [rsp+360h+arg_98]
0x1800410f7  mov     [rbp+2D0h+phNewToken], rax
0x1800410fb  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180041100  mov     ecx, [rax]
0x180041102  cmp     ecx, 5
0x180041105  jbe     short loc_180041119
0x180041107  xor     r8d, r8d
0x18004110a  lea     rdx, byte_180129223
0x180041111  mov     rcx, rax
0x180041114  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180041119  xor     eax, eax
0x18004111b  mov     [rbp+2D0h+LsaHandle], rax
0x18004111f  mov     [rbp+2D0h+Src], rax
0x180041123  mov     [rbp+2D0h+var_2CC], eax
0x180041126  mov     [rbp+2D0h+hExistingToken], rax
0x18004112a  xorps   xmm0, xmm0
0x18004112d  movups  xmmword ptr [rbp+2D0h+var_230.PagedPoolLimit], xmm0
0x180041134  movups  xmmword ptr [rbp+2D0h+var_230.MinimumWorkingSetSize], xmm0
0x18004113b  movups  xmmword ptr [rbp+2D0h+var_230.PagefileLimit], xmm0
0x180041142  mov     [rbp+2D0h+var_2A8], rax
0x180041146  mov     [rbp+2D0h+var_2D0], eax
0x180041149  xor     edx, edx; Val
0x18004114b  mov     r8d, 1A0h; Size
0x180041151  lea     rcx, [rbp+2D0h+var_1F0]; void *
0x180041158  call    memset_0
0x18004115d  xor     eax, eax
0x18004115f  mov     [rbp+2D0h+var_2C8], eax
0x180041162  mov     [rbp+2D0h+var_2C4], eax
0x180041165  mov     [rbp+2D0h+var_2C0], eax
0x180041168  lea     r8, [rbp+2D0h+var_1F0]; struct _BASIC_CALLER_INFORMATION *
0x18004116f  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x180041174  mov     rcx, [rsp+368h]; this
0x18004117c  test    eax, eax
0x18004117e  js      loc_180041572
0x180041184  lea     r8, byte_1801135E8; struct _CALLER_RESTRICTIONS *
0x18004118b  lea     rdx, [rbp+2D0h+var_1F0]; struct _BASIC_CALLER_INFORMATION *
0x180041192  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x180041197  mov     rcx, [rsp+368h]; this
0x18004119f  xor     edx, edx
0x1800411a1  test    rbx, rbx
0x1800411a4  jz      loc_180041586
0x1800411aa  mov     rcx, [rsp+368h]; this
0x1800411b2  test    r14, r14
0x1800411b5  jz      loc_18004159D
0x1800411bb  cmp     [r14], dx
0x1800411bf  jbe     short loc_1800411C9
0x1800411c1  cmp     [r14+8], rdx
0x1800411c5  mov     al, 1
0x1800411c7  jz      short loc_1800411CB
0x1800411c9  mov     al, dl
0x1800411cb  mov     rcx, [rsp+368h]; this
0x1800411d3  test    al, al
0x1800411d5  jnz     loc_1800415B4
0x1800411db  mov     rcx, [rsp+368h]; this
0x1800411e3  test    r15, r15
0x1800411e6  jz      loc_1800415CB
0x1800411ec  mov     rcx, [rsp+368h]; this
0x1800411f4  cmp     [rbp+2D0h+var_298], rdx
0x1800411f8  jz      loc_1800415E2
0x1800411fe  test    rsi, rsi
0x180041201  jz      short loc_180041246
0x180041203  cmp     [rsi], edx
0x180041205  jbe     short loc_180041212
0x180041207  lea     rax, [rsi+8]
0x18004120b  test    rax, rax
0x18004120e  mov     al, 1
0x180041210  jz      short loc_180041214
0x180041212  mov     al, dl
0x180041214  mov     rcx, [rsp+368h]; this
0x18004121c  test    al, al
0x18004121e  jnz     loc_1800415F9
0x180041224  mov     ecx, edx
0x180041226  cmp     ecx, [rsi]
0x180041228  jnb     short loc_180041246
0x18004122a  mov     r10, [rsp+368h]
0x180041232  mov     eax, ecx
0x180041234  add     rax, rax
0x180041237  cmp     [rsi+rax*8+8], rdx
0x18004123c  jz      loc_180041610
0x180041242  inc     ecx
0x180041244  jmp     short loc_180041226
0x180041246  mov     rcx, [rsp+368h]; this
0x18004124e  test    r13, r13
0x180041251  jz      loc_18004162A
0x180041257  mov     rcx, [rsp+368h]; this
0x18004125f  cmp     [rbp+2D0h+var_2A0], rdx
0x180041263  jz      loc_180041641
0x180041269  mov     rcx, [rsp+368h]; this
0x180041271  test    rdi, rdi
0x180041274  jz      loc_180041658
0x18004127a  lea     rax, [rbp+2D0h+var_2A8]
0x18004127e  mov     [rbp+2D0h+var_260], rax
0x180041282  lea     rax, [rbp+2D0h+Src]
0x180041286  mov     [rbp+2D0h+var_258], rax
0x18004128a  lea     rax, [rbp+2D0h+var_2C8]
0x18004128e  mov     [rbp+2D0h+var_250], rax
0x180041295  lea     rax, [rbp+2D0h+var_2C4]
0x180041299  mov     [rbp+2D0h+var_248], rax
0x1800412a0  lea     rax, [rbp+2D0h+var_2C0]
0x1800412a4  mov     [rbp+2D0h+var_240], rax
0x1800412ab  mov     [rbp+2D0h+var_238], 1
0x1800412b2  lea     rax, [rbp+2D0h+var_2D0]
0x1800412b6  mov     [rsp+360h+AuthenticationInformation], rax; int
0x1800412bb  lea     r9, [rbp+2D0h+var_2A8]; struct _WL_AUTH_INFO **
0x1800412bf  mov     r8d, [rbp+2D0h+var_1E8]; unsigned int
0x1800412c6  mov     edx, [r15]; Size
0x1800412c9  mov     rcx, [r15+10h]; Src
0x1800412cd  call    ?WrapWlAuthInfo@@YAJPEAXKKPEAPEAU_WL_AUTH_INFO@@PEAK@Z; WrapWlAuthInfo(void *,ulong,ulong,_WL_AUTH_INFO * *,ulong *)
0x1800412d2  mov     rcx, [rsp+368h]; this
0x1800412da  xor     r15d, r15d
0x1800412dd  test    eax, eax
0x1800412df  js      loc_180041670
0x1800412e5  mov     ebx, [rsp+360h+arg_48]
0x1800412ec  test    ebx, ebx
0x1800412ee  jz      short loc_180041309
0x1800412f0  mov     edx, ebx; unsigned int
0x1800412f2  xor     ecx, ecx; int
0x1800412f4  call    ?SetNtlmThreadOptions@@YAJHK@Z; SetNtlmThreadOptions(int,ulong)
0x1800412f9  mov     rcx, [rsp+368h]; this
0x180041301  test    eax, eax
0x180041303  js      loc_180041684
0x180041309  lea     r8, [rbp+2D0h+var_2C8]
0x18004130d  mov     edx, [rsp+360h+arg_50]
0x180041314  mov     rcx, [rbp+2D0h+var_288]
0x180041318  call    cs:__imp_SeciAllocateAndSetIPAddress
0x18004131e  lea     rdx, [rbp+2D0h+var_2C4]
0x180041322  mov     ecx, [rsp+360h+arg_40]
0x180041329  call    cs:__imp_SeciAllocateAndSetCallFlags
0x18004132f  xor     ecx, ecx; BindingHandle
0x180041331  call    cs:__imp_RpcImpersonateClient
0x180041337  mov     rcx, [rsp+368h]; this
0x18004133f  test    eax, eax
0x180041341  jnz     loc_180041698
0x180041347  mov     [rbp+2D0h+var_2C0], 1
0x18004134e  lea     rdx, [rbp+2D0h+LsaHandle]; void **
0x180041352  call    ?GetLsaHandle@UserMgrCli@@AEAAJPEAPEAX@Z; UserMgrCli::GetLsaHandle(void * *)
0x180041357  mov     rcx, [rsp+368h]; this
0x18004135f  test    eax, eax
0x180041361  js      loc_1800416AC
0x180041367  xor     edx, edx
0x180041369  lea     rcx, [rbp+2D0h+hExistingToken]
0x18004136d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180041372  mov     rcx, [rbp+2D0h+var_2A8]
0x180041376  mov     [rsp+360h+SubStatus], r13; SubStatus
0x18004137b  lea     rax, [rbp+2D0h+var_230]
0x180041382  mov     [rsp+360h+Quotas], rax; Quotas
0x180041387  lea     rax, [rbp+2D0h+hExistingToken]
0x18004138b  mov     [rsp+360h+Token], rax; Token
0x180041390  mov     rax, [rbp+2D0h+var_2A0]
0x180041394  mov     [rsp+360h+LogonId], rax; LogonId
0x180041399  lea     rax, [rbp+2D0h+var_2CC]
0x18004139d  mov     [rsp+360h+ProfileBufferLength], rax; ProfileBufferLength
0x1800413a2  lea     rax, [rbp+2D0h+Src]
0x1800413a6  mov     [rsp+360h+ProfileBuffer], rax; ProfileBuffer
0x1800413ab  mov     rax, [rbp+2D0h+var_298]
0x1800413af  mov     [rsp+360h+SourceContext], rax; SourceContext
0x1800413b4  mov     [rsp+360h+LocalGroups], rsi; LocalGroups
0x1800413b9  mov     eax, [rbp+2D0h+var_2D0]
0x1800413bc  mov     [rsp+360h+AuthenticationInformationLength], eax; AuthenticationInformationLength
0x1800413c0  mov     [rsp+360h+AuthenticationInformation], rcx; AuthenticationInformation
0x1800413c5  mov     r9d, [rsp+360h+AuthenticationPackage]; AuthenticationPackage
0x1800413cd  mov     r8d, [rsp+360h+LogonType]; LogonType
0x1800413d5  mov     rdx, r14; OriginName
0x1800413d8  mov     rcx, [rbp+2D0h+LsaHandle]; LsaHandle
0x1800413dc  call    cs:__imp_LsaLogonUser
0x1800413e2  mov     [r12], eax
0x1800413e6  test    ebx, ebx
0x1800413e8  jz      short loc_1800413F6
0x1800413ea  mov     edx, ebx; unsigned int
0x1800413ec  mov     ecx, 1; int
0x1800413f1  call    ?SetNtlmThreadOptions@@YAJHK@Z; SetNtlmThreadOptions(int,ulong)
0x1800413f6  cmp     [r12], r15d
0x1800413fa  jge     short loc_18004141D
0x1800413fc  mov     [rbp+2D0h+var_238], r15b
0x180041403  lea     rcx, [rbp+2D0h+var_260]
0x180041407  call    _lambda_93d6174e76a59b044fd992c4c32d1add___operator__
0x18004140c  nop
0x18004140d  lea     rcx, [rbp+2D0h+hExistingToken]
0x180041411  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180041416  xor     eax, eax
0x180041418  jmp     loc_18004154F
0x18004141d  mov     cl, [rbp+2D0h+var_1F0]
0x180041423  mov     al, cl
0x180041425  neg     al
0x180041427  sbb     edx, edx
0x180041429  add     edx, 2
0x18004142c  neg     cl
0x18004142e  sbb     r9d, r9d
0x180041431  neg     r9d
0x180041434  inc     r9d; ImpersonationLevel
0x180041437  mov     rax, [rbp+2D0h+phNewToken]
0x18004143b  mov     qword ptr [rsp+360h+AuthenticationInformationLength], rax; phNewToken
0x180041440  mov     dword ptr [rsp+360h+AuthenticationInformation], edx; int
0x180041444  xor     r8d, r8d; lpTokenAttributes
0x180041447  xor     edx, edx; dwDesiredAccess
0x180041449  mov     rcx, [rbp+2D0h+hExistingToken]; hExistingToken
0x18004144d  call    cs:__imp_DuplicateTokenEx
0x180041453  mov     rcx, [rsp+368h]; this
0x18004145b  test    eax, eax
0x18004145d  jz      loc_1800416C0
0x180041463  mov     edx, [rbp+2D0h+var_2CC]; uBytes
0x180041466  mov     rax, [rbp+2D0h+var_278]
0x18004146a  mov     [rax], edx
0x18004146c  mov     ecx, 40h ; '@'; uFlags
0x180041471  call    cs:__imp_LocalAlloc
0x180041477  mov     rbx, rax
0x18004147a  mov     rsi, [rbp+2D0h+var_270]
0x18004147e  mov     [rsi], rax
0x180041481  mov     ecx, 0C000009Ah; Status
0x180041486  call    cs:__imp_RtlNtStatusToDosError
0x18004148c  test    eax, eax
0x18004148e  jle     short loc_180041498
0x180041490  movzx   eax, ax
0x180041493  or      eax, 80070000h
0x180041498  mov     rcx, [rsp+368h]; this
0x1800414a0  test    rbx, rbx
0x1800414a3  jz      loc_1800416D1
0x1800414a9  mov     r8d, [rbp+2D0h+var_2CC]; Size
0x1800414ad  mov     rdx, [rbp+2D0h+Src]; Src
0x1800414b1  mov     rcx, [rsi]; void *
0x1800414b4  call    memcpy_0
0x1800414b9  mov     rax, [rbp+2D0h+Src]
0x1800414bd  mov     rcx, [rbp+2D0h+var_268]
0x1800414c1  mov     [rcx], rax
0x1800414c4  mov     rax, [rbp+2D0h+var_230.MaximumWorkingSetSize]
0x1800414cb  mov     [rdi+18h], rax
0x1800414cf  mov     rax, [rbp+2D0h+var_230.MinimumWorkingSetSize]
0x1800414d6  mov     [rdi+10h], rax
0x1800414da  mov     rax, [rbp+2D0h+var_230.NonPagedPoolLimit]
0x1800414e1  mov     [rdi+8], rax
0x1800414e5  mov     rax, [rbp+2D0h+var_230.PagedPoolLimit]
0x1800414ec  mov     [rdi], rax
0x1800414ef  mov     rax, [rbp+2D0h+var_230.PagefileLimit]
0x1800414f6  mov     [rdi+20h], rax
0x1800414fa  mov     rax, qword ptr [rbp+2D0h+var_230.TimeLimit]
0x180041501  mov     [rdi+28h], rax
0x180041505  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18004150a  mov     ecx, [rax]
0x18004150c  cmp     ecx, 5
0x18004150f  jbe     short loc_18004152E
0x180041511  mov     [rbp+2D0h+var_2D0], r15d
0x180041515  lea     rcx, [rbp+2D0h+var_2D0]
0x180041519  mov     [rsp+360h+AuthenticationInformation], rcx
0x18004151e  lea     rdx, byte_1801291F3
0x180041525  mov     rcx, rax
0x180041528  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004152d  nop
0x18004152e  mov     [rbp+2D0h+var_238], r15b
0x180041535  lea     rcx, [rbp+2D0h+var_260]
0x180041539  call    _lambda_93d6174e76a59b044fd992c4c32d1add___operator__
0x18004153e  nop
0x18004153f  lea     rcx, [rbp+2D0h+hExistingToken]
0x180041543  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180041548  xor     eax, eax
0x18004154a  jmp     short loc_18004154F
0x18004154c  mov     eax, [rbp+2D0h+var_2D0]
0x18004154f  mov     rcx, [rbp+2D0h+var_50]
0x180041556  xor     rcx, rsp; StackCookie
0x180041559  call    __security_check_cookie
0x18004155e  add     rsp, 328h
0x180041565  pop     r15
0x180041567  pop     r14
0x180041569  pop     r13
0x18004156b  pop     r12
0x18004156d  pop     rdi
0x18004156e  pop     rsi
0x18004156f  pop     rbx
  ... truncated ...
```
