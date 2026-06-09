# Windows::System::Internal::UserManagerStatics::GetUserForContext(unsigned __int64,Windows::System::IUser * *,bool)

- ea: `0x1800391d4`
- end: `0x18003965e`
- name: `?GetUserForContext@UserManagerStatics@Internal@System@Windows@@AEAAJ_KPEAPEAUIUser@34@_N@Z`
- size: `1162`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned __int64, struct Windows::System::IUser **, bool)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800391c0`
- `0x180093bc0`
- `0x180093d60`

## callees

- `0x180006130`
- `0x180007920`
- `0x180008b10`
- `0x18000acdc`
- `0x18000c988`
- `0x18000ca64`
- `0x180012890`
- `0x180014ee0`
- `0x180015960`
- `0x180016380`
- `0x180024828`
- `0x1800332e8`
- `0x180035874`
- `0x1800391d4`
- `0x1800d47dc`
- `0x1800d494c`
- `0x1800ec010`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x18003936a`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18003936a`

## string_xrefs

- `0x18003954e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180039565`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18003957a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18003958e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800395a2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800395b7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800395cb`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800395e2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800395f7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18003960b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18003961f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180039633`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18003964b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::System::Internal::UserManagerStatics::GetUserForContext(
        Windows::System::Internal::UserManagerStatics *this,
        __int64 a2,
        struct Windows::System::IUser **a3,
        char a4)
{
  const struct _tlgProvider_t *v8; // rax
  int v9; // r8d
  int v10; // r9d
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v12; // r14
  __int64 (__fastcall *v13)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, __int64, struct Windows::System::IUser **); // rbx
  int v14; // eax
  __int64 (__fastcall *v15)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, __int64, struct Windows::System::IUser **); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned int CallerSessionId; // ebx
  __int64 v21; // rcx
  char v22; // al
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v23; // r14
  __int64 (__fastcall *v24)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, void *, _QWORD *); // rbx
  int v25; // eax
  int v26; // eax
  int v27; // edx
  unsigned __int8 v28; // bl
  int v29; // eax
  int v30; // eax
  bool v31; // cl
  const struct _tlgProvider_t *v32; // rax
  __int64 result; // rax
  const struct _tlgProvider_t *v34; // rax
  int v35; // ebx
  wil *v36; // rcx
  int v37; // [rsp+20h] [rbp-78h]
  unsigned __int8 v38; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int8 v39[3]; // [rsp+31h] [rbp-67h] BYREF
  int v40; // [rsp+34h] [rbp-64h] BYREF
  struct Windows::System::IUser *v41; // [rsp+38h] [rbp-60h] BYREF
  int v42[2]; // [rsp+40h] [rbp-58h] BYREF
  void *phNewToken; // [rsp+48h] [rbp-50h] BYREF
  int v44; // [rsp+50h] [rbp-48h] BYREF
  int v45; // [rsp+54h] [rbp-44h] BYREF
  _QWORD v46[8]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v8 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    *(_QWORD *)v42 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)word_180124EBA,
      v9,
      v10,
      (__int64)v42);
  }
  try
  {
    phNewToken = 0;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1919,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80070057LL,
        v37);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x191A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80004003LL,
        v37);
    *a3 = 0;
    v41 = 0;
    UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
    v12 = UserStaticsInternal;
    if ( a4 )
    {
      v13 = *(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, __int64, struct Windows::System::IUser **))(*(_QWORD *)UserStaticsInternal + 168LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      v14 = v13(v12, a2, &v41);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1921,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v14,
          v37);
    }
    else
    {
      v15 = *(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, __int64, struct Windows::System::IUser **))(*(_QWORD *)UserStaticsInternal + 160LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
      v16 = v15(v12, a2, &v41);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1925,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v16,
          v37);
    }
    if ( v41 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &phNewToken,
        0);
      v17 = GetCallerTokenFromComCall(&phNewToken);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1929,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v17,
          v37);
      *(_QWORD *)v42 = 0;
      v44 = 0;
      v38 = 0;
      v39[0] = 0;
      v45 = 0;
      v40 = 0;
      v18 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v41,
              (__int64 *)v42);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1934,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v18,
          v37);
      v19 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v42 + 96LL))(*(_QWORD *)v42, &v44);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1935,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v19,
          v37);
      CallerSessionId = Windows::System::Internal::Implementation::ComUtils::GetCallerSessionId();
      if ( CallerSessionId == (unsigned int)RtlGetCurrentServiceSessionId(v21) || (v22 = 1, CallerSessionId == v44) )
        v22 = 0;
      if ( v22 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1937,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)0x80070005LL,
          v37);
      v46[0] = 0;
      v23 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(this);
      v24 = *(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, void *, _QWORD *))(*(_QWORD *)v23 + 176LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v46);
      v25 = v24(v23, phNewToken, v46);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x193B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v25,
          v37);
      if ( v46[0] && (struct Windows::System::IUser *)v46[0] == v41 )
        goto LABEL_30;
      ValidateIsTokenService(phNewToken, &v45);
      if ( v45 )
        goto LABEL_30;
      v26 = IsTokenForMultiUserManifestedApp(phNewToken, &v38);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1945,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v26,
          v37);
      v28 = v38;
      if ( !v38 )
      {
        v29 = IsTokenForDefaultAccount(phNewToken, v27, 0, v39);
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1948,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v29,
            v37);
        if ( v39[0] )
          goto LABEL_30;
      }
      v30 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v42 + 48LL))(*(_QWORD *)v42, &v40);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x194D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v30,
          v37);
      v31 = 0;
      if ( (unsigned int)(v40 - 1) <= 0xE )
        v31 = v46[0] == *((_QWORD *)this + 66);
      if ( v28 || v31 )
      {
LABEL_30:
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v41);
        *a3 = v41;
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v46);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v42);
    }
    if ( !*a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x195B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80A2030BLL,
        v37);
    v32 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v32 > 5u )
    {
      v40 = 0;
      *(_QWORD *)v42 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v32,
        (unsigned int)byte_180124E7D,
        0,
        0,
        (__int64)v42,
        (__int64)&v40);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phNewToken);
    result = 0;
  }
  catch ( ... )
  {
    v34 = UserMgrUserModelTelemetry::Provider();
    v35 = (int)v34;
    v36 = (wil *)*(unsigned int *)v34;
    if ( (unsigned int)v36 > 5 )
    {
      v40 = wil::ResultFromCaughtException(v36);
      *(_QWORD *)v42 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v35,
        (unsigned int)byte_180124E2D,
        0,
        0,
        (__int64)v42,
        (__int64)&v40);
    }
    return (unsigned int)wil::ResultFromCaughtException(v36);
  }
  return result;
}

```

## disassembly

```asm
0x1800391d4  mov     [rsp+arg_8], rdx
0x1800391d9  push    rbx
0x1800391da  push    rsi
0x1800391db  push    rdi
0x1800391dc  push    r12
0x1800391de  push    r14
0x1800391e0  push    r15
0x1800391e2  sub     rsp, 68h
0x1800391e6  mov     bl, r9b
0x1800391e9  mov     rsi, r8
0x1800391ec  mov     rdi, rdx
0x1800391ef  mov     r15, rcx
0x1800391f2  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800391f7  mov     r10d, [rax]
0x1800391fa  cmp     r10d, 5
0x1800391fe  jbe     short loc_18003921E
0x180039200  mov     qword ptr [rsp+98h+var_58], rdi
0x180039205  lea     rcx, [rsp+98h+var_58]
0x18003920a  mov     qword ptr [rsp+98h+var_78], rcx; int
0x18003920f  lea     rdx, word_180124EBA
0x180039216  mov     rcx, rax
0x180039219  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18003921e  xor     r12d, r12d
0x180039221  mov     [rsp+98h+phNewToken], r12
0x180039226  mov     rcx, [rsp+98h]; this
0x18003922e  test    rdi, rdi
0x180039231  jz      loc_180039548
0x180039237  mov     rcx, [rsp+98h]; this
0x18003923f  test    rsi, rsi
0x180039242  jz      loc_18003955F
0x180039248  mov     [rsi], r12
0x18003924b  mov     [rsp+98h+var_60], r12
0x180039250  mov     rcx, r15; this
0x180039253  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x180039258  mov     r14, rax
0x18003925b  test    bl, bl
0x18003925d  jz      short loc_180039298
0x18003925f  mov     rcx, [rax]
0x180039262  mov     rbx, [rcx+0A8h]
0x180039269  lea     rcx, [rsp+98h+var_60]
0x18003926e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039273  lea     r8, [rsp+98h+var_60]
0x180039278  mov     rdx, rdi
0x18003927b  mov     rcx, r14
0x18003927e  mov     rax, rbx
0x180039281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039286  mov     rcx, [rsp+98h]; this
0x18003928e  test    eax, eax
0x180039290  js      loc_180039577
0x180039296  jmp     short loc_1800392CF
0x180039298  mov     rax, [rax]
0x18003929b  mov     rbx, [rax+0A0h]
0x1800392a2  lea     rcx, [rsp+98h+var_60]
0x1800392a7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800392ac  lea     r8, [rsp+98h+var_60]
0x1800392b1  mov     rdx, rdi
0x1800392b4  mov     rcx, r14
0x1800392b7  mov     rax, rbx
0x1800392ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392bf  mov     rcx, [rsp+98h]; this
0x1800392c7  test    eax, eax
0x1800392c9  js      loc_18003958B
0x1800392cf  cmp     [rsp+98h+var_60], r12
0x1800392d4  jz      loc_1800394C9
0x1800392da  xor     edx, edx
0x1800392dc  lea     rcx, [rsp+98h+phNewToken]
0x1800392e1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800392e6  lea     rcx, [rsp+98h+phNewToken]; phNewToken
0x1800392eb  call    ?GetCallerTokenFromComCall@@YAJPEAPEAX@Z; GetCallerTokenFromComCall(void * *)
0x1800392f0  mov     rcx, [rsp+98h]; this
0x1800392f8  test    eax, eax
0x1800392fa  js      loc_18003959F
0x180039300  mov     qword ptr [rsp+98h+var_58], r12
0x180039305  mov     [rsp+98h+var_48], r12d
0x18003930a  mov     [rsp+98h+var_68], r12b
0x18003930f  mov     [rsp+98h+var_67], r12b
0x180039314  mov     [rsp+98h+var_44], r12d
0x180039319  mov     [rsp+98h+var_64], r12d
0x18003931e  lea     rdx, [rsp+98h+var_58]
0x180039323  lea     rcx, [rsp+98h+var_60]
0x180039328  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18003932d  mov     rcx, [rsp+98h]; this
0x180039335  test    eax, eax
0x180039337  js      loc_1800395B4
0x18003933d  mov     rcx, qword ptr [rsp+98h+var_58]
0x180039342  mov     rax, [rcx]
0x180039345  lea     rdx, [rsp+98h+var_48]
0x18003934a  mov     rax, [rax+60h]
0x18003934e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039353  mov     rcx, [rsp+98h]; this
0x18003935b  test    eax, eax
0x18003935d  js      loc_1800395C8
0x180039363  call    ?GetCallerSessionId@ComUtils@Implementation@Internal@System@Windows@@SAKXZ; Windows::System::Internal::Implementation::ComUtils::GetCallerSessionId(void)
0x180039368  mov     ebx, eax
0x18003936a  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180039370  cmp     ebx, eax
0x180039372  jz      short loc_18003937C
0x180039374  cmp     ebx, [rsp+98h+var_48]
0x180039378  mov     al, 1
0x18003937a  jnz     short loc_18003937F
0x18003937c  mov     al, r12b
0x18003937f  mov     rcx, [rsp+98h]; this
0x180039387  test    al, al
0x180039389  jnz     loc_1800395DC
0x18003938f  mov     [rsp+98h+var_40], r12
0x180039394  mov     rcx, r15; this
0x180039397  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x18003939c  mov     r14, rax
0x18003939f  mov     rcx, [rax]
0x1800393a2  mov     rbx, [rcx+0B0h]
0x1800393a9  lea     rcx, [rsp+98h+var_40]
0x1800393ae  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800393b3  lea     r8, [rsp+98h+var_40]
0x1800393b8  mov     rdx, [rsp+98h+phNewToken]
0x1800393bd  mov     rcx, r14
0x1800393c0  mov     rax, rbx
0x1800393c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393c8  mov     rcx, [rsp+98h]; this
0x1800393d0  test    eax, eax
0x1800393d2  js      loc_1800395F4
0x1800393d8  mov     rax, [rsp+98h+var_40]
0x1800393dd  test    rax, rax
0x1800393e0  jz      short loc_1800393ED
0x1800393e2  cmp     rax, [rsp+98h+var_60]
0x1800393e7  jz      loc_1800394A2
0x1800393ed  lea     rdx, [rsp+98h+var_44]; int *
0x1800393f2  mov     rcx, [rsp+98h+phNewToken]; ClientToken
0x1800393f7  call    ?ValidateIsTokenService@@YAJPEAXPEAH@Z; ValidateIsTokenService(void *,int *)
0x1800393fc  cmp     [rsp+98h+var_44], r12d
0x180039401  jnz     loc_1800394A2
0x180039407  lea     rdx, [rsp+98h+var_68]; unsigned __int8 *
0x18003940c  mov     rcx, [rsp+98h+phNewToken]; void *
0x180039411  call    ?IsTokenForMultiUserManifestedApp@@YAJPEAXPEAE@Z; IsTokenForMultiUserManifestedApp(void *,uchar *)
0x180039416  mov     rcx, [rsp+98h]; this
0x18003941e  test    eax, eax
0x180039420  js      loc_180039608
0x180039426  mov     bl, [rsp+98h+var_68]
0x18003942a  test    bl, bl
0x18003942c  jnz     short loc_180039457
0x18003942e  lea     r9, [rsp+98h+var_67]; unsigned __int8 *
0x180039433  xor     r8d, r8d; int
0x180039436  mov     rcx, [rsp+98h+phNewToken]; TokenHandle
0x18003943b  call    ?IsTokenForDefaultAccount@@YAJPEAXHHPEAE@Z; IsTokenForDefaultAccount(void *,int,int,uchar *)
0x180039440  mov     rcx, [rsp+98h]; this
0x180039448  test    eax, eax
0x18003944a  js      loc_18003961C
0x180039450  cmp     [rsp+98h+var_67], r12b
0x180039455  jnz     short loc_1800394A2
0x180039457  mov     rcx, qword ptr [rsp+98h+var_58]
0x18003945c  mov     rax, [rcx]
0x18003945f  lea     rdx, [rsp+98h+var_64]
0x180039464  mov     rax, [rax+30h]
0x180039468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003946d  mov     rcx, [rsp+98h]; this
0x180039475  test    eax, eax
0x180039477  js      loc_180039630
0x18003947d  mov     cl, r12b
0x180039480  mov     eax, [rsp+98h+var_64]
0x180039484  dec     eax
0x180039486  cmp     eax, 0Eh
0x180039489  ja      short loc_18003949A
0x18003948b  mov     rax, [r15+210h]
0x180039492  cmp     [rsp+98h+var_40], rax
0x180039497  setz    cl
0x18003949a  test    bl, bl
0x18003949c  jnz     short loc_1800394A2
0x18003949e  test    cl, cl
0x1800394a0  jz      short loc_1800394B4
0x1800394a2  lea     rcx, [rsp+98h+var_60]
0x1800394a7  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800394ac  mov     rax, [rsp+98h+var_60]
0x1800394b1  mov     [rsi], rax
0x1800394b4  lea     rcx, [rsp+98h+var_40]
0x1800394b9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800394be  nop
0x1800394bf  lea     rcx, [rsp+98h+var_58]
0x1800394c4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800394c9  mov     rcx, [rsp+98h]; this
0x1800394d1  cmp     [rsi], r12
0x1800394d4  jz      loc_180039645
0x1800394da  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800394df  mov     ecx, [rax]
0x1800394e1  cmp     ecx, 5
0x1800394e4  jbe     short loc_18003951A
0x1800394e6  mov     [rsp+98h+var_64], r12d
0x1800394eb  mov     qword ptr [rsp+98h+var_58], rdi
0x1800394f0  lea     rcx, [rsp+98h+var_64]
0x1800394f5  mov     [rsp+98h+var_70], rcx
0x1800394fa  lea     rcx, [rsp+98h+var_58]
0x1800394ff  mov     qword ptr [rsp+98h+var_78], rcx
0x180039504  xor     r9d, r9d
0x180039507  xor     r8d, r8d
0x18003950a  lea     rdx, byte_180124E7D
0x180039511  mov     rcx, rax
0x180039514  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180039519  nop
0x18003951a  lea     rcx, [rsp+98h+var_60]
0x18003951f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180039524  nop
0x180039525  lea     rcx, [rsp+98h+phNewToken]
0x18003952a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003952f  xor     eax, eax
0x180039531  jmp     short loc_18003953A
0x180039533  mov     eax, dword ptr [rsp+98h+arg_8]
0x18003953a  add     rsp, 68h
0x18003953e  pop     r15
0x180039540  pop     r14
0x180039542  pop     r12
0x180039544  pop     rdi
0x180039545  pop     rsi
0x180039546  pop     rbx
0x180039547  retn
0x180039548  mov     r9d, 80070057h; char *
0x18003954e  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180039555  mov     edx, 1919h; void *
0x18003955a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003955f  mov     r9d, 80004003h; char *
0x180039565  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18003956c  mov     edx, 191Ah; void *
0x180039571  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039577  mov     r9d, eax; char *
0x18003957a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180039581  mov     edx, 1921h; void *
0x180039586  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003958b  mov     r9d, eax; char *
0x18003958e  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180039595  mov     edx, 1925h; void *
0x18003959a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003959f  mov     r9d, eax; char *
0x1800395a2  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800395a9  mov     edx, 1929h; void *
0x1800395ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800395b4  mov     r9d, eax; char *
0x1800395b7  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800395be  mov     edx, 1934h; void *
0x1800395c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800395c8  mov     r9d, eax; char *
0x1800395cb  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800395d2  mov     edx, 1935h; void *
0x1800395d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800395dc  mov     r9d, 80070005h; char *
0x1800395e2  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800395e9  mov     edx, 1937h; void *
0x1800395ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800395f4  mov     r9d, eax; char *
0x1800395f7  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x1800395fe  mov     edx, 193Bh; void *
0x180039603  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039608  mov     r9d, eax; char *
0x18003960b  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180039612  mov     edx, 1945h; void *
0x180039617  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003961c  mov     r9d, eax; char *
0x18003961f  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180039626  mov     edx, 1948h; void *
0x18003962b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039630  mov     r9d, eax; char *
0x180039633  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x18003963a  mov     edx, 194Dh; void *
0x18003963f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180039645  mov     r9d, 80A2030Bh; char *
0x18003964b  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180039652  mov     edx, 195Bh; void *
0x180039657  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
