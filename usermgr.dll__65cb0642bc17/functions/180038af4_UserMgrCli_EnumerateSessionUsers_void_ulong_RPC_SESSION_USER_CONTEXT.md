# UserMgrCli::EnumerateSessionUsers(void *,ulong *,_RPC_SESSION_USER_CONTEXT * *)

- ea: `0x180038af4`
- end: `0x180038f31`
- name: `?EnumerateSessionUsers@UserMgrCli@@QEAAJPEAXPEAKPEAPEAU_RPC_SESSION_USER_CONTEXT@@@Z`
- size: `1085`
- prototype: `__int64 __fastcall(UserMgrCli *__hidden this, void *, unsigned int *, struct _RPC_SESSION_USER_CONTEXT **)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180038ae0`

## callees

- `0x180006130`
- `0x180007920`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c6d0`
- `0x18000cd30`
- `0x18000ce48`
- `0x180012890`
- `0x180015250`
- `0x18002618c`
- `0x180038af4`
- `0x18006f1c9`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038dd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038dd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038c9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038c9e`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180038bc6`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180038bc6`

## string_xrefs

- `0x180038e36`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038e4d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038e64`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038e7b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038e8f`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038ea3`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038eb7`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038ece`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038ee2`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038ef6`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038f0a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180038f1e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UserMgrCli::EnumerateSessionUsers(
        UserMgrCli *this,
        void *a2,
        unsigned int *a3,
        struct _RPC_SESSION_USER_CONTEXT **a4)
{
  unsigned __int64 v4; // rbp
  const struct _tlgProvider_t *v7; // rax
  void *v8; // rdx
  UserMgrCli *v9; // rcx
  int BasicCallerInformation; // eax
  __int64 v11; // rcx
  int v13; // eax
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, unsigned __int64); // rdi
  int v16; // eax
  int v17; // eax
  unsigned int v18; // eax
  struct _RPC_SESSION_USER_CONTEXT *v19; // rax
  unsigned int i; // r14d
  unsigned int v21; // ecx
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, _QWORD, unsigned __int64); // rdi
  int v24; // eax
  int v25; // eax
  __int64 v26; // rdi
  int v27; // eax
  int v28; // eax
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  __int64 result; // rax
  _DWORD *v33; // rbp
  const struct _tlgProvider_t *v34; // rax
  int v35; // ebx
  wil *v36; // rcx
  int v37; // r8d
  int v38; // r9d
  int v39; // [rsp+20h] [rbp-30h]
  int v40; // [rsp+50h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+288h] [rbp+238h]

  v4 = (unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL;
  v7 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v7 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v7,
      byte_1801296B5,
      0);
  memset_0((void *)(v4 + 96), 0, 0x1A0u);
  *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
  *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_DWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
  *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = ((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                       + 8;
  *(_BYTE *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 1;
  try
  {
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               v9,
                               v8,
                               (struct _BASIC_CALLER_INFORMATION *)(v4 + 96));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        v39);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v4 + 96),
      (const struct _CALLER_RESTRICTIONS *)byte_1801135F0);
    if ( !*(_BYTE *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60)
      && *(_DWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) != (unsigned int)RtlGetCurrentServiceSessionId(v11) )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        v39);
    }
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80004003LL,
        v39);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80004003LL,
        v39);
    *a3 = 0;
    *a4 = 0;
    v13 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>((__int64 *)(v4 + 48));
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7AB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v13,
        v39);
    v14 = *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
    v15 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v14 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4 + 16);
    v16 = v15(v14, v4 + 16);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7AD,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v16,
        v39);
    v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v40
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x10)
                                                              + 56LL))(
            *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10),
            v4 + 4);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7AF,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v17,
        v39);
    v18 = *(_DWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
    if ( v18 )
    {
      v19 = (struct _RPC_SESSION_USER_CONTEXT *)LocalAlloc(0x40u, 16LL * v18);
      *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = v19;
      if ( !v19 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7B5,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)0x8007000ELL,
          v39);
      for ( i = 0; ; ++i )
      {
        v21 = *(_DWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
        if ( i >= v21 )
          break;
        v22 = *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
        v23 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64))(*(_QWORD *)v22 + 48LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v4 + 32);
        v24 = v23(v22, i, v4 + 32);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7B9,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
            (const char *)(unsigned int)v24,
            v39);
        v25 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
                (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v4 + 32),
                (__int64 *)(v4 + 24));
        if ( v25 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7BA,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
            (const char *)(unsigned int)v25,
            v39);
        v26 = 16LL * i;
        v27 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                       + 0x18)
                                                         + 88LL))(
                *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
                v26 + *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 8));
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7BB,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
            (const char *)(unsigned int)v27,
            v39);
        v28 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                       + 0x18)
                                                         + 96LL))(
                *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
                v26 + *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 8) + 8LL);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x7BC,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
            (const char *)(unsigned int)v28,
            v39);
        v19 = *(struct _RPC_SESSION_USER_CONTEXT **)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
      }
      *a3 = v21;
      *a4 = v19;
      *(_QWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    }
    v29 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v29 > 4u )
    {
      *(_DWORD *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
      *(_DWORD *)v4 = *a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v29,
        (unsigned int)word_1801295CA,
        v30,
        v31,
        (unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL,
        v4 + 40);
    }
    LocalFree(*(HLOCAL *)(((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL) + 8));
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v4 + 24);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v4 + 32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4 + 16);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4 + 48);
    result = 0;
  }
  catch ( ... )
  {
    v33 = (_DWORD *)((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL);
    v34 = UserMgrUserModelTelemetry::Provider();
    v35 = (int)v34;
    v36 = (wil *)*(unsigned int *)v34;
    if ( (unsigned int)v36 > 4 )
    {
      *v33 = wil::ResultFromCaughtException(v36);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v35,
        (unsigned int)&unk_180129610,
        v37,
        v38,
        (__int64)v33);
    }
    *v33 = wil::ResultFromCaughtException(v36);
    return *(unsigned int *)((unsigned __int64)&v40 & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return result;
}

```

## disassembly

```asm
0x180038af4  mov     [rsp-8+arg_0], rbx
0x180038af9  mov     [rsp-8+arg_8], rsi
0x180038afe  push    rbp
0x180038aff  push    rdi
0x180038b00  push    r12
0x180038b02  push    r14
0x180038b04  push    r15
0x180038b06  sub     rsp, 260h
0x180038b0d  lea     rbp, [rsp+50h]
0x180038b12  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180038b16  mov     rax, cs:__security_cookie
0x180038b1d  xor     rax, rsp
0x180038b20  mov     [rbp+230h+var_30], rax
0x180038b27  mov     r12, r9
0x180038b2a  mov     r15, r8
0x180038b2d  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180038b32  mov     ecx, [rax]
0x180038b34  cmp     ecx, 4
0x180038b37  jbe     short loc_180038B4B
0x180038b39  xor     r8d, r8d
0x180038b3c  lea     rdx, byte_1801296B5
0x180038b43  mov     rcx, rax
0x180038b46  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180038b4b  xor     edx, edx; Val
0x180038b4d  mov     r8d, 1A0h; Size
0x180038b53  lea     rcx, [rbp+230h+var_1D0]; void *
0x180038b57  call    memset_0
0x180038b5c  mov     [rbp+230h+var_200], 0
0x180038b64  mov     [rbp+230h+var_220], 0
0x180038b6c  mov     [rbp+230h+var_210], 0
0x180038b74  mov     [rbp+230h+var_218], 0
0x180038b7c  mov     [rbp+230h+var_228], 0
0x180038b84  mov     [rbp+230h+var_22C], 0
0x180038b8b  lea     rbx, [rbp+230h+var_228]
0x180038b8f  mov     [rbp+230h+var_1F8], rbx
0x180038b93  mov     [rbp+230h+var_1F0], 1
0x180038b97  lea     r8, [rbp+230h+var_1D0]; struct _BASIC_CALLER_INFORMATION *
0x180038b9b  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x180038ba0  mov     rcx, [rsp+288h]; this
0x180038ba8  test    eax, eax
0x180038baa  js      loc_180038E33
0x180038bb0  lea     r8, byte_1801135F0; struct _CALLER_RESTRICTIONS *
0x180038bb7  lea     rdx, [rbp+230h+var_1D0]; struct _BASIC_CALLER_INFORMATION *
0x180038bbb  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x180038bc0  cmp     [rbp+230h+var_1D0], 0
0x180038bc4  jnz     short loc_180038BD5
0x180038bc6  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180038bcc  cmp     [rbp+230h+var_1C8], eax
0x180038bcf  jz      short loc_180038BD5
0x180038bd1  xor     al, al
0x180038bd3  jmp     short loc_180038BD7
0x180038bd5  mov     al, 1
0x180038bd7  mov     rcx, [rsp+288h]; this
0x180038bdf  test    al, al
0x180038be1  jz      loc_180038E47
0x180038be7  mov     rcx, [rsp+288h]; this
0x180038bef  test    r15, r15
0x180038bf2  jz      loc_180038E5E
0x180038bf8  mov     rcx, [rsp+288h]; this
0x180038c00  test    r12, r12
0x180038c03  jz      loc_180038E75
0x180038c09  mov     dword ptr [r15], 0
0x180038c10  mov     qword ptr [r12], 0
0x180038c18  lea     rcx, [rbp+230h+var_200]
0x180038c1c  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x180038c21  mov     rcx, [rsp+288h]; this
0x180038c29  test    eax, eax
0x180038c2b  js      loc_180038E8C
0x180038c31  mov     rsi, [rbp+230h+var_200]
0x180038c35  mov     rax, [rsi]
0x180038c38  mov     rdi, [rax+30h]
0x180038c3c  lea     rcx, [rbp+230h+var_220]
0x180038c40  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038c45  lea     rdx, [rbp+230h+var_220]
0x180038c49  mov     rcx, rsi
0x180038c4c  mov     rax, rdi
0x180038c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c54  mov     rcx, [rsp+288h]; this
0x180038c5c  test    eax, eax
0x180038c5e  js      loc_180038EA0
0x180038c64  mov     rcx, [rbp+230h+var_220]
0x180038c68  mov     rax, [rcx]
0x180038c6b  lea     rdx, [rbp+230h+var_22C]
0x180038c6f  mov     rax, [rax+38h]
0x180038c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c78  mov     rcx, [rsp+288h]; this
0x180038c80  test    eax, eax
0x180038c82  js      loc_180038EB4
0x180038c88  mov     eax, [rbp+230h+var_22C]
0x180038c8b  test    eax, eax
0x180038c8d  jz      loc_180038D95
0x180038c93  mov     edx, eax
0x180038c95  shl     rdx, 4; uBytes
0x180038c99  mov     ecx, 40h ; '@'; uFlags
0x180038c9e  call    cs:__imp_LocalAlloc
0x180038ca4  mov     [rbp+230h+var_228], rax
0x180038ca8  mov     rcx, [rsp+288h]; this
0x180038cb0  test    rax, rax
0x180038cb3  jz      loc_180038EC8
0x180038cb9  xor     r14d, r14d
0x180038cbc  mov     ecx, [rbp+230h+var_22C]
0x180038cbf  cmp     r14d, ecx
0x180038cc2  jnb     loc_180038D86
0x180038cc8  mov     rsi, [rbp+230h+var_220]
0x180038ccc  mov     rax, [rsi]
0x180038ccf  mov     rdi, [rax+30h]
0x180038cd3  lea     rcx, [rbp+230h+var_210]
0x180038cd7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038cdc  lea     r8, [rbp+230h+var_210]
0x180038ce0  mov     edx, r14d
0x180038ce3  mov     rcx, rsi
0x180038ce6  mov     rax, rdi
0x180038ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cee  mov     rcx, [rsp+288h]; this
0x180038cf6  test    eax, eax
0x180038cf8  js      loc_180038EDF
0x180038cfe  lea     rdx, [rbp+230h+var_218]
0x180038d02  lea     rcx, [rbp+230h+var_210]
0x180038d06  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x180038d0b  mov     rcx, [rsp+288h]; this
0x180038d13  test    eax, eax
0x180038d15  js      loc_180038EF3
0x180038d1b  mov     r8, [rbp+230h+var_218]
0x180038d1f  mov     edi, r14d
0x180038d22  shl     rdi, 4
0x180038d26  mov     rcx, [r8]
0x180038d29  mov     rdx, [rbp+230h+var_228]
0x180038d2d  add     rdx, rdi
0x180038d30  mov     rax, [rcx+58h]
0x180038d34  mov     rcx, r8
0x180038d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d3c  mov     rcx, [rsp+288h]; this
0x180038d44  test    eax, eax
0x180038d46  js      loc_180038F07
0x180038d4c  mov     r8, [rbp+230h+var_218]
0x180038d50  mov     rcx, [r8]
0x180038d53  mov     rdx, [rbp+230h+var_228]
0x180038d57  add     rdx, 8
0x180038d5b  add     rdx, rdi
0x180038d5e  mov     rax, [rcx+60h]
0x180038d62  mov     rcx, r8
0x180038d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d6a  mov     rcx, [rsp+288h]; this
0x180038d72  test    eax, eax
0x180038d74  js      loc_180038F1B
0x180038d7a  inc     r14d
0x180038d7d  mov     rax, [rbp+230h+var_228]
0x180038d81  jmp     loc_180038CBC
0x180038d86  mov     [r15], ecx
0x180038d89  mov     [r12], rax
0x180038d8d  mov     [rbp+230h+var_228], 0
0x180038d95  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180038d9a  mov     ecx, [rax]
0x180038d9c  cmp     ecx, 4
0x180038d9f  jbe     short loc_180038DD0
0x180038da1  mov     [rbp+230h+var_208], 0
0x180038da8  mov     edx, [r15]
0x180038dab  mov     [rbp+230h+var_230], edx
0x180038dae  lea     rcx, [rbp+230h+var_208]
0x180038db2  mov     [rsp+280h+var_258], rcx
0x180038db7  lea     rcx, [rbp+230h+var_230]
0x180038dbb  mov     [rsp+280h+var_260], rcx
0x180038dc0  lea     rdx, word_1801295CA
0x180038dc7  mov     rcx, rax
0x180038dca  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038dcf  nop
0x180038dd0  mov     rcx, [rbx]; hMem
0x180038dd3  call    cs:__imp_LocalFree
0x180038dd9  nop
0x180038dda  lea     rcx, [rbp+230h+var_218]
0x180038dde  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038de3  nop
0x180038de4  lea     rcx, [rbp+230h+var_210]
0x180038de8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180038ded  nop
0x180038dee  lea     rcx, [rbp+230h+var_220]
0x180038df2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038df7  nop
0x180038df8  lea     rcx, [rbp+230h+var_200]
0x180038dfc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038e01  xor     eax, eax
0x180038e03  jmp     short loc_180038E08
0x180038e05  mov     eax, [rbp+230h+var_230]
0x180038e08  mov     rcx, [rbp+230h+var_30]
0x180038e0f  xor     rcx, rsp; StackCookie
0x180038e12  call    __security_check_cookie
0x180038e17  lea     r11, [rsp+280h+var_20]
0x180038e1f  mov     rbx, [r11+30h]
0x180038e23  mov     rsi, [r11+38h]
0x180038e27  mov     rsp, r11
0x180038e2a  pop     r15
0x180038e2c  pop     r14
0x180038e2e  pop     r12
0x180038e30  pop     rdi
0x180038e31  pop     rbp
0x180038e32  retn
0x180038e33  mov     r9d, eax; char *
0x180038e36  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038e3d  mov     edx, 7A0h; void *
0x180038e42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038e47  mov     r9d, 80070005h; char *
0x180038e4d  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038e54  mov     edx, 7A4h; void *
0x180038e59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038e5e  mov     r9d, 80004003h; char *
0x180038e64  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038e6b  mov     edx, 7A6h; void *
0x180038e70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038e75  mov     r9d, 80004003h; char *
0x180038e7b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038e82  mov     edx, 7A7h; void *
0x180038e87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038e8c  mov     r9d, eax; char *
0x180038e8f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038e96  mov     edx, 7ABh; void *
0x180038e9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038ea0  mov     r9d, eax; char *
0x180038ea3  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038eaa  mov     edx, 7ADh; void *
0x180038eaf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038eb4  mov     r9d, eax; char *
0x180038eb7  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038ebe  mov     edx, 7AFh; void *
0x180038ec3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038ec8  mov     r9d, 8007000Eh; char *
0x180038ece  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038ed5  mov     edx, 7B5h; void *
0x180038eda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038edf  mov     r9d, eax; char *
0x180038ee2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038ee9  mov     edx, 7B9h; void *
0x180038eee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038ef3  mov     r9d, eax; char *
0x180038ef6  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038efd  mov     edx, 7BAh; void *
0x180038f02  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038f07  mov     r9d, eax; char *
0x180038f0a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038f11  mov     edx, 7BBh; void *
0x180038f16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038f1b  mov     r9d, eax; char *
0x180038f1e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180038f25  mov     edx, 7BCh; void *
0x180038f2a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
