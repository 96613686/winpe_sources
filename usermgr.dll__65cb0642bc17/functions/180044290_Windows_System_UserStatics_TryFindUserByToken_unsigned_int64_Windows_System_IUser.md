# Windows::System::UserStatics::TryFindUserByToken(unsigned __int64,Windows::System::IUser * *)

- ea: `0x180044290`
- end: `0x180044956`
- name: `?TryFindUserByToken@UserStatics@System@Windows@@UEAAJ_KPEAPEAUIUser@23@@Z`
- size: `1734`
- prototype: `__int64 __fastcall(Windows::System::UserStatics *__hidden this, unsigned __int64, struct Windows::System::IUser **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800018c4`
- `0x18000acdc`
- `0x180044290`
- `0x18004e4e8`
- `0x18004e58c`
- `0x180064044`
- `0x18006c318`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800442e3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800446a5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800442e3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800446a5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180044386`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180044743`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180044386`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180044743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044564`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044577`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044645`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004446d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004483f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004446d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004483f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004456f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004456f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044850`

## string_xrefs

- `0x1800448c0`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x1800448d7`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x1800448ec`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x1800448fd`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180044911`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180044938`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::System::UserStatics::TryFindUserByToken(
        Windows::System::UserStatics *this,
        Windows::System::UserStatics *a2,
        struct Windows::System::IUser **a3)
{
  __int64 v5; // rcx
  void (__fastcall *v6)(void *, __int64 *); // rbx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rsi
  unsigned int (__fastcall *v10)(__int64, __int64, HLOCAL *); // r15
  HLOCAL v11; // rdi
  DWORD LastError; // ebx
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  unsigned __int64 v16; // rdx
  Windows::System::UserStatics *v17; // rsi
  __int64 v18; // rbx
  unsigned int v19; // edi
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  int v23; // eax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 result; // rax
  const struct _tlgProvider_t *v29; // rax
  int v30; // ebx
  wil *v31; // rcx
  ULONG UserDataCount; // [rsp+20h] [rbp-168h]
  WINBOOL fPending; // [rsp+40h] [rbp-148h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-140h] BYREF
  __int64 v35; // [rsp+50h] [rbp-138h] BYREF
  int v36; // [rsp+58h] [rbp-130h]
  unsigned int v37; // [rsp+5Ch] [rbp-12Ch] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-128h] BYREF
  __int64 v39; // [rsp+68h] [rbp-120h] BYREF
  Windows::System::UserStatics *v40; // [rsp+70h] [rbp-118h] BYREF
  Windows::System::UserStatics *v41; // [rsp+78h] [rbp-110h]
  HSTRING_HEADER EventDescriptor; // [rsp+80h] [rbp-108h] BYREF
  HSTRING string; // [rsp+98h] [rbp-F0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-E8h] BYREF
  __int16 *v45; // [rsp+B0h] [rbp-D8h]
  int v46; // [rsp+B8h] [rbp-D0h]
  int v47; // [rsp+BCh] [rbp-CCh]
  LPVOID *p_Context; // [rsp+C0h] [rbp-C8h]
  __int64 v49; // [rsp+C8h] [rbp-C0h]
  WINBOOL *p_fPending; // [rsp+D0h] [rbp-B8h]
  __int64 v51; // [rsp+D8h] [rbp-B0h]
  __int64 v52[12]; // [rsp+E0h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v40 = this;
  v41 = a2;
  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`UserMgrUserModelTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    Context = &qword_180147BD0;
    qword_180147BD8 = 0;
    byte_180147BE0 = 0;
    dword_180147BE4 = 0;
    qword_180147BD0 = (__int64)&UserMgrUserModelTelemetry::`vftable';
    CallbackContext = &`UserMgrUserModelTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_720b04dfc33336bd43e851a7c42b71cc_::_lambda_invoker_cdecl_);
    qword_180147BD8 = (__int64)CallbackContext;
    byte_180147BE0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180147BE4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180147BD0 + 8))(&qword_180147BD0);
    InitOnceComplete(&`UserMgrUserModelTelemetry::Instance'::`2'::wrapper, 0, &qword_180147BD0);
  }
  v5 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)v5 > 5u )
  {
    Context = a2;
    p_Context = &Context;
    v49 = 8;
    *(_OWORD *)&EventDescriptor.Reserved.Reserved1 = 0x50B000000uLL;
    UserData.Ptr = *(_QWORD *)(v5 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v45 = (__int16 *)&unk_180122A00;
    v46 = 39;
    v47 = 1;
    fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v5 + 32), (PCEVENT_DESCRIPTOR)&EventDescriptor, 0, 0, 3u, &UserData);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x76A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80070057LL,
        UserDataCount);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x76B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80004003LL,
        UserDataCount);
    *a3 = 0;
    v39 = 0;
    v35 = 0;
    (*(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 88LL))(
      &Windows::System::Internal::Adapters::g_AdapterCollection,
      &v39);
    v6 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
    v7 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v6(&Windows::System::Internal::Adapters::g_AdapterCollection, &v35);
    v36 = 0;
    hMem = 0;
    v37 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, Windows::System::UserStatics *, __int64, __int64 *))(*(_QWORD *)v39 + 24LL))(
           v39,
           a2,
           1,
           v52);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x780,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v8,
        84);
    v9 = v35;
    v10 = *(unsigned int (__fastcall **)(__int64, __int64, HLOCAL *))(*(_QWORD *)v35 + 32LL);
    v11 = hMem;
    if ( hMem )
    {
      LastError = GetLastError();
      LocalFree(v11);
      SetLastError(LastError);
    }
    hMem = 0;
    if ( !v10(v9, v52[0], &hMem) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x782,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        v13);
    v14 = (*(__int64 (__fastcall **)(__int64, Windows::System::UserStatics *, __int64, unsigned int *))(*(_QWORD *)v39 + 24LL))(
            v39,
            a2,
            12,
            &v37);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x78A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v14,
        4);
    string = 0;
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)hMem + v16) );
    if ( v16 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v15);
      JUMPOUT(0x180044954LL);
    }
    if ( (int)v16 + 1 < (unsigned int)v16 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v16, v15);
      __debugbreak();
    }
    v17 = v40;
    v18 = *(_QWORD *)v40;
    v19 = v37;
    v20 = WindowsCreateStringReference((PCWSTR)hMem, v16, &EventDescriptor, &string);
    if ( v20 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
    }
    else
    {
      v23 = (*(__int64 (__fastcall **)(Windows::System::UserStatics *, HSTRING, _QWORD, struct Windows::System::IUser **))(v18 + 144))(
              v17,
              string,
              v19,
              a3);
      v24 = retaddr;
      if ( v23 >= 0 )
      {
        string = 0;
        Context = 0;
        fPending = 0;
        if ( InitOnceBeginInitialize(&`UserMgrUserModelTelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context)
          && fPending )
        {
          Context = &qword_180147BD0;
          qword_180147BD8 = 0;
          byte_180147BE0 = 0;
          dword_180147BE4 = 0;
          qword_180147BD0 = (__int64)&UserMgrUserModelTelemetry::`vftable';
          CallbackContext = &`UserMgrUserModelTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
          atexit(_lambda_720b04dfc33336bd43e851a7c42b71cc_::_lambda_invoker_cdecl_);
          qword_180147BD8 = (__int64)CallbackContext;
          byte_180147BE0 = 1;
          TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
          dword_180147BE4 = 1;
          (*(void (__fastcall **)(__int64 *))(qword_180147BD0 + 8))(&qword_180147BD0);
          InitOnceComplete(&`UserMgrUserModelTelemetry::Instance'::`2'::wrapper, 0, &qword_180147BD0);
        }
        v25 = *((_QWORD *)Context + 1);
        if ( *(_DWORD *)v25 > 5u )
        {
          fPending = 0;
          v40 = a2;
          p_fPending = &fPending;
          v51 = 4;
          p_Context = (LPVOID *)&v40;
          v49 = 8;
          *(_OWORD *)&EventDescriptor.Reserved.Reserved1 = 0x50B000000uLL;
          UserData.Ptr = *(_QWORD *)(v25 + 8);
          UserData.Size = *(unsigned __int16 *)UserData.Ptr;
          UserData.Reserved = 2;
          v45 = &word_1801229BE;
          v46 = 54;
          v47 = 1;
          LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(*(_QWORD *)(v25 + 32), (PCEVENT_DESCRIPTOR)&EventDescriptor, 0, 0, 4u, &UserData);
        }
        if ( hMem )
          LocalFree(hMem);
        v26 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v27 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        return 0;
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v24,
      (void *)0x78C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
      (const char *)(unsigned int)v23,
      4);
  }
  catch ( ... )
  {
    v29 = UserMgrUserModelTelemetry::Provider();
    v30 = (int)v29;
    v31 = (wil *)*(unsigned int *)v29;
    if ( (unsigned int)v31 > 5 )
    {
      LODWORD(Context) = wil::ResultFromCaughtException(v31);
      v40 = v41;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)&word_18012295E,
        0,
        0,
        (__int64)&v40,
        (__int64)&Context);
    }
    return (unsigned int)wil::ResultFromCaughtException(v31);
  }
  return result;
}

```

## disassembly

```asm
0x180044290  push    rbx
0x180044292  push    rsi
0x180044293  push    rdi
0x180044294  push    r12
0x180044296  push    r13
0x180044298  push    r14
0x18004429a  push    r15
0x18004429c  sub     rsp, 150h
0x1800442a3  mov     rax, cs:__security_cookie
0x1800442aa  xor     rax, rsp
0x1800442ad  mov     [rsp+188h+var_48], rax
0x1800442b5  mov     r13, r8
0x1800442b8  mov     r12, rdx
0x1800442bb  mov     [rsp+188h+var_118], rcx
0x1800442c0  mov     [rsp+188h+var_110], rdx
0x1800442c5  xor     edi, edi
0x1800442c7  mov     [rsp+188h+Context], rdi
0x1800442cc  mov     [rsp+188h+fPending], edi
0x1800442d0  lea     r9, [rsp+188h+Context]; lpContext
0x1800442d5  lea     r8, [rsp+188h+fPending]; fPending
0x1800442da  xor     edx, edx; dwFlags
0x1800442dc  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x1800442e3  call    cs:__imp_InitOnceBeginInitialize
0x1800442e9  test    eax, eax
0x1800442eb  jz      loc_18004438E
0x1800442f1  cmp     [rsp+188h+fPending], edi
0x1800442f5  jz      loc_18004438E
0x1800442fb  lea     r14, qword_180147BD0
0x180044302  mov     [rsp+188h+Context], r14
0x180044307  mov     cs:qword_180147BD8, rdi
0x18004430e  mov     cs:byte_180147BE0, dil
0x180044315  mov     cs:dword_180147BE4, edi
0x18004431b  lea     rbx, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x180044322  mov     cs:qword_180147BD0, rbx
0x180044329  lea     rbx, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180044330  mov     cs:CallbackContext, rbx
0x180044337  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x18004433e  call    atexit
0x180044343  mov     rcx, cs:CallbackContext; CallbackContext
0x18004434a  mov     cs:qword_180147BD8, rcx
0x180044351  mov     cs:byte_180147BE0, 1
0x180044358  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18004435d  mov     cs:dword_180147BE4, 1
0x180044367  mov     rax, cs:qword_180147BD0
0x18004436e  mov     rcx, r14
0x180044371  mov     rax, [rax+8]
0x180044375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004437a  mov     r8, r14; lpContext
0x18004437d  xor     edx, edx; dwFlags
0x18004437f  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180044386  call    cs:__imp_InitOnceComplete
0x18004438c  jmp     short loc_180044395
0x18004438e  lea     r14, qword_180147BD0
0x180044395  mov     rax, [rsp+188h+Context]
0x18004439a  mov     rcx, [rax+8]
0x18004439e  mov     eax, [rcx]
0x1800443a0  cmp     eax, 5
0x1800443a3  jbe     loc_180044473
0x1800443a9  mov     [rsp+188h+Context], r12
0x1800443ae  lea     rax, [rsp+188h+Context]
0x1800443b3  mov     [rsp+188h+var_C8], rax
0x1800443bb  mov     [rsp+188h+var_C0], 8
0x1800443c7  mov     dword ptr [rsp+188h+EventDescriptor], 0B000000h
0x1800443d2  movzx   eax, cs:word_1801229F6
0x1800443d9  mov     dword ptr [rsp+188h+EventDescriptor+4], eax
0x1800443e0  mov     qword ptr [rsp+188h+EventDescriptor+8], rdi
0x1800443e8  mov     rax, [rcx+8]
0x1800443ec  mov     [rsp+188h+var_E8.Ptr], rax
0x1800443f4  movzx   eax, word ptr [rax]
0x1800443f7  mov     [rsp+188h+var_E8.Size], eax
0x1800443fe  mov     dword ptr [rsp+188h+var_E8.0Ch], 2
0x180044409  lea     rax, unk_180122A00
0x180044410  mov     [rsp+188h+var_D8], rax
0x180044418  mov     [rsp+188h+var_D0], 27h ; '''
0x180044423  mov     [rsp+188h+var_CC], 1
0x18004442e  lea     rax, _TraceLoggingMetadataEnd
0x180044435  lea     rbx, _TraceLoggingMetadata
0x18004443c  sub     eax, ebx
0x18004443e  mov     [rsp+188h+fPending], eax
0x180044442  mov     eax, [rsp+188h+fPending]
0x180044446  lea     rax, [rsp+188h+var_E8]
0x18004444e  mov     [rsp+188h+UserData], rax; UserData
0x180044453  mov     [rsp+188h+UserDataCount], 3; int
0x18004445b  xor     r9d, r9d; RelatedActivityId
0x18004445e  xor     r8d, r8d; ActivityId
0x180044461  lea     rdx, [rsp+188h+EventDescriptor]; EventDescriptor
0x180044469  mov     rcx, [rcx+20h]; RegHandle
0x18004446d  call    cs:__imp_EventWriteTransfer
0x180044473  mov     rcx, [rsp+188h]; this
0x18004447b  test    r12, r12
0x18004447e  jz      loc_1800448BA
0x180044484  mov     rcx, [rsp+188h]; this
0x18004448c  test    r13, r13
0x18004448f  jz      loc_1800448D1
0x180044495  mov     [r13+0], rdi
0x180044499  mov     [rsp+188h+var_120], rdi
0x18004449e  mov     [rsp+188h+var_138], rdi
0x1800444a3  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800444aa  lea     rdx, [rsp+188h+var_120]
0x1800444af  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800444b6  mov     rax, [rax+58h]
0x1800444ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444bf  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800444c6  mov     rbx, [rax+38h]
0x1800444ca  mov     rdx, [rsp+188h+var_138]
0x1800444cf  test    rdx, rdx
0x1800444d2  jz      short loc_1800444E9
0x1800444d4  mov     [rsp+188h+var_138], rdi
0x1800444d9  mov     rcx, [rdx]
0x1800444dc  mov     rax, [rcx+10h]
0x1800444e0  mov     rcx, rdx
0x1800444e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444e8  nop
0x1800444e9  lea     rdx, [rsp+188h+var_138]
0x1800444ee  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800444f5  mov     rax, rbx
0x1800444f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800444fd  mov     [rsp+188h+var_130], edi
0x180044501  mov     [rsp+188h+hMem], rdi
0x180044506  mov     [rsp+188h+var_12C], edi
0x18004450a  mov     rcx, [rsp+188h+var_120]
0x18004450f  mov     rax, [rcx]
0x180044512  lea     rdx, [rsp+188h+var_130]
0x180044517  mov     [rsp+188h+UserData], rdx
0x18004451c  mov     [rsp+188h+UserDataCount], 54h ; 'T'; int
0x180044524  lea     r9, [rsp+188h+var_A8]
0x18004452c  mov     r8d, 1
0x180044532  mov     rdx, r12
0x180044535  mov     rax, [rax+18h]
0x180044539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004453e  mov     rcx, [rsp+188h]; this
0x180044546  test    eax, eax
0x180044548  js      loc_1800448E9
0x18004454e  mov     rsi, [rsp+188h+var_138]
0x180044553  mov     rax, [rsi]
0x180044556  mov     r15, [rax+20h]
0x18004455a  mov     rdi, [rsp+188h+hMem]
0x18004455f  test    rdi, rdi
0x180044562  jz      short loc_18004457D
0x180044564  call    cs:__imp_GetLastError
0x18004456a  mov     ebx, eax
0x18004456c  mov     rcx, rdi; hMem
0x18004456f  call    cs:__imp_LocalFree
0x180044575  mov     ecx, ebx; dwErrCode
0x180044577  call    cs:__imp_SetLastError
0x18004457d  mov     [rsp+188h+hMem], 0
0x180044586  lea     r8, [rsp+188h+hMem]
0x18004458b  mov     rdx, [rsp+188h+var_A8]
0x180044593  mov     rcx, rsi
0x180044596  mov     rax, r15
0x180044599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004459e  mov     rcx, [rsp+188h]; this
0x1800445a6  test    eax, eax
0x1800445a8  jz      loc_1800448FD
0x1800445ae  mov     rcx, [rsp+188h+var_120]
0x1800445b3  mov     rax, [rcx]
0x1800445b6  lea     rdx, [rsp+188h+var_130]
0x1800445bb  mov     [rsp+188h+UserData], rdx
0x1800445c0  mov     [rsp+188h+UserDataCount], 4; int
0x1800445c8  lea     r9, [rsp+188h+var_12C]
0x1800445cd  mov     r8d, 0Ch
0x1800445d3  mov     rdx, r12
0x1800445d6  mov     rax, [rax+18h]
0x1800445da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445df  mov     rcx, [rsp+188h]; this
0x1800445e7  test    eax, eax
0x1800445e9  js      loc_18004490E
0x1800445ef  xor     r15d, r15d
0x1800445f2  mov     [rsp+188h+string], r15
0x1800445fa  mov     rcx, [rsp+188h+hMem]; sourceString
0x1800445ff  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180044606  inc     rdx; int
0x180044609  cmp     [rcx+rdx*2], r15w
0x18004460e  jnz     short loc_180044606
0x180044610  mov     eax, 0FFFFFFFFh
0x180044615  cmp     rdx, rax
0x180044618  ja      loc_18004494A
0x18004461e  lea     eax, [rdx+1]
0x180044621  cmp     eax, edx
0x180044623  jb      loc_180044922
0x180044629  mov     rsi, [rsp+188h+var_118]
0x18004462e  mov     rbx, [rsi]
0x180044631  mov     edi, [rsp+188h+var_12C]
0x180044635  lea     r9, [rsp+188h+string]; string
0x18004463d  lea     r8, [rsp+188h+EventDescriptor]; hstringHeader
0x180044645  call    cs:__imp_WindowsCreateStringReference
0x18004464b  test    eax, eax
0x18004464d  js      loc_18004492D
0x180044653  mov     r9, r13
0x180044656  mov     r8d, edi
0x180044659  mov     rdx, [rsp+188h+string]
0x180044661  mov     rcx, rsi
0x180044664  mov     rax, [rbx+90h]
0x18004466b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044670  mov     rcx, [rsp+188h]
0x180044678  test    eax, eax
0x18004467a  js      loc_180044935
0x180044680  mov     [rsp+188h+string], r15
0x180044688  mov     [rsp+188h+Context], r15
0x18004468d  mov     [rsp+188h+fPending], r15d
0x180044692  lea     r9, [rsp+188h+Context]; lpContext
0x180044697  lea     r8, [rsp+188h+fPending]; fPending
0x18004469c  xor     edx, edx; dwFlags
0x18004469e  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x1800446a5  call    cs:__imp_InitOnceBeginInitialize
0x1800446ab  test    eax, eax
0x1800446ad  jz      loc_180044749
0x1800446b3  cmp     [rsp+188h+fPending], 0
0x1800446b8  jz      loc_180044749
0x1800446be  mov     [rsp+188h+Context], r14
0x1800446c3  mov     cs:qword_180147BD8, r15
0x1800446ca  mov     cs:byte_180147BE0, 0
0x1800446d1  mov     cs:dword_180147BE4, r15d
0x1800446d8  lea     rax, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x1800446df  mov     cs:qword_180147BD0, rax
0x1800446e6  lea     rax, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800446ed  mov     cs:CallbackContext, rax
0x1800446f4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x1800446fb  call    atexit
0x180044700  mov     rcx, cs:CallbackContext; CallbackContext
0x180044707  mov     cs:qword_180147BD8, rcx
0x18004470e  mov     cs:byte_180147BE0, 1
0x180044715  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18004471a  mov     cs:dword_180147BE4, 1
0x180044724  mov     rax, cs:qword_180147BD0
0x18004472b  mov     rcx, r14
0x18004472e  mov     rax, [rax+8]
0x180044732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044737  mov     r8, r14; lpContext
0x18004473a  xor     edx, edx; dwFlags
0x18004473c  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180044743  call    cs:__imp_InitOnceComplete
0x180044749  mov     rax, [rsp+188h+Context]
0x18004474e  mov     rcx, [rax+8]
0x180044752  mov     eax, [rcx]
0x180044754  cmp     eax, 5
0x180044757  jbe     loc_180044846
0x18004475d  mov     [rsp+188h+fPending], r15d
0x180044762  mov     [rsp+188h+var_118], r12
0x180044767  lea     rax, [rsp+188h+fPending]
0x18004476c  mov     [rsp+188h+var_B8], rax
0x180044774  mov     [rsp+188h+var_B0], 4
0x180044780  lea     rax, [rsp+188h+var_118]
0x180044785  mov     [rsp+188h+var_C8], rax
0x18004478d  mov     [rsp+188h+var_C0], 8
0x180044799  mov     dword ptr [rsp+188h+EventDescriptor], 0B000000h
0x1800447a4  movzx   eax, cs:word_1801229B4
0x1800447ab  mov     dword ptr [rsp+188h+EventDescriptor+4], eax
0x1800447b2  mov     qword ptr [rsp+188h+EventDescriptor+8], r15
0x1800447ba  mov     rax, [rcx+8]
0x1800447be  mov     [rsp+188h+var_E8.Ptr], rax
0x1800447c6  movzx   eax, word ptr [rax]
0x1800447c9  mov     [rsp+188h+var_E8.Size], eax
0x1800447d0  mov     dword ptr [rsp+188h+var_E8.0Ch], 2
0x1800447db  lea     rax, word_1801229BE
0x1800447e2  mov     [rsp+188h+var_D8], rax
0x1800447ea  mov     [rsp+188h+var_D0], 36h ; '6'
0x1800447f5  mov     [rsp+188h+var_CC], 1
0x180044800  lea     rax, _TraceLoggingMetadataEnd
0x180044807  lea     rdx, _TraceLoggingMetadata
0x18004480e  sub     eax, edx
0x180044810  mov     dword ptr [rsp+188h+Context], eax
0x180044814  mov     eax, dword ptr [rsp+188h+Context]
0x180044818  lea     rax, [rsp+188h+var_E8]
0x180044820  mov     [rsp+188h+UserData], rax; UserData
0x180044825  mov     [rsp+188h+UserDataCount], 4; UserDataCount
0x18004482d  xor     r9d, r9d; RelatedActivityId
0x180044830  xor     r8d, r8d; ActivityId
0x180044833  lea     rdx, [rsp+188h+EventDescriptor]; EventDescriptor
0x18004483b  mov     rcx, [rcx+20h]; RegHandle
0x18004483f  call    cs:__imp_EventWriteTransfer
0x180044845  nop
0x180044846  mov     rcx, [rsp+188h+hMem]; hMem
0x18004484b  test    rcx, rcx
0x18004484e  jz      short loc_180044857
0x180044850  call    cs:__imp_LocalFree
0x180044856  nop
0x180044857  mov     rcx, [rsp+188h+var_138]
0x18004485c  test    rcx, rcx
0x18004485f  jz      short loc_180044873
0x180044861  mov     [rsp+188h+var_138], r15
0x180044866  mov     rax, [rcx]
0x180044869  mov     rax, [rax+10h]
0x18004486d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044872  nop
0x180044873  mov     rcx, [rsp+188h+var_120]
0x180044878  test    rcx, rcx
0x18004487b  jz      short loc_18004488F
0x18004487d  mov     [rsp+188h+var_120], r15
0x180044882  mov     rax, [rcx]
0x180044885  mov     rax, [rax+10h]
0x180044889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004488e  nop
0x18004488f  xor     eax, eax
0x180044891  jmp     short loc_180044897
0x180044893  mov     eax, dword ptr [rsp+188h+Context]
0x180044897  mov     rcx, [rsp+188h+var_48]
0x18004489f  xor     rcx, rsp; StackCookie
0x1800448a2  call    __security_check_cookie
0x1800448a7  add     rsp, 150h
  ... truncated ...
```
