# Windows::System::UserStatics::TryFindUserByContext(unsigned __int64,Windows::System::IUser * *)

- ea: `0x1800436c0`
- end: `0x180043afc`
- name: `?TryFindUserByContext@UserStatics@System@Windows@@UEAAJ_KPEAPEAUIUser@23@@Z`
- size: `1084`
- prototype: `__int64 __fastcall(Windows::System::UserStatics *__hidden this, unsigned __int64, struct Windows::System::IUser **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800018c4`
- `0x18000acdc`
- `0x1800436c0`
- `0x18006c318`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180043714`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004393a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180043714`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004393a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800437b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800439c6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800437b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800439c6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004389a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180043a9e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004389a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180043a9e`

## string_xrefs

- `0x180043ad5`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180043ae9`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::UserStatics::TryFindUserByContext(
        EVENT_DESCRIPTOR *this,
        EVENT_DESCRIPTOR *a2,
        struct Windows::System::IUser **a3)
{
  __int64 v5; // rcx
  ULONGLONG *p_Keyword; // rcx
  ULONGLONG Keyword; // rax
  int v8; // eax
  __int64 v9; // rcx
  __int64 result; // rax
  const struct _tlgProvider_t *v11; // rax
  int v12; // ebx
  wil *v13; // rcx
  ULONG UserDataCount; // [rsp+20h] [rbp-D8h]
  WINBOOL fPending; // [rsp+30h] [rbp-C8h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR *p_EventDescriptor; // [rsp+40h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B0h] BYREF
  EVENT_DESCRIPTOR *v19; // [rsp+60h] [rbp-98h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-88h] BYREF
  __int16 *v21; // [rsp+80h] [rbp-78h]
  int v22; // [rsp+88h] [rbp-70h]
  int v23; // [rsp+8Ch] [rbp-6Ch]
  LPVOID *p_Context; // [rsp+90h] [rbp-68h]
  __int64 v25; // [rsp+98h] [rbp-60h]
  WINBOOL *p_fPending; // [rsp+A0h] [rbp-58h]
  __int64 v27; // [rsp+A8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  p_EventDescriptor = this;
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
    v25 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = *(_QWORD *)(v5 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v21 = (__int16 *)&dword_180122CE4;
    v22 = 43;
    v23 = 1;
    fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v5 + 32), &EventDescriptor, 0, 0, 3u, &UserData);
  }
  try
  {
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6AC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80004003LL,
        UserDataCount);
    *a3 = 0;
    p_Keyword = &p_EventDescriptor[-4].Keyword;
    Keyword = p_EventDescriptor[-4].Keyword;
    p_EventDescriptor = &EventDescriptor;
    *(_QWORD *)&EventDescriptor.Id = off_1800F0088;
    EventDescriptor.Keyword = (ULONGLONG)a2;
    v19 = &EventDescriptor;
    v8 = (*(__int64 (__fastcall **)(ULONGLONG *, EVENT_DESCRIPTOR *, struct Windows::System::IUser **))(Keyword + 72))(
           p_Keyword,
           &EventDescriptor,
           a3);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6BE,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v8,
        UserDataCount);
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
    v9 = *((_QWORD *)Context + 1);
    if ( *(_DWORD *)v9 > 5u )
    {
      fPending = 0;
      p_EventDescriptor = a2;
      p_fPending = &fPending;
      v27 = 4;
      p_Context = (LPVOID *)&p_EventDescriptor;
      v25 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = *(_QWORD *)(v9 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      v21 = &word_180122C9E;
      v22 = 58;
      v23 = 1;
      LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v9 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
    }
    result = 0;
  }
  catch ( ... )
  {
    v11 = UserMgrUserModelTelemetry::Provider();
    v12 = (int)v11;
    v13 = (wil *)*(unsigned int *)v11;
    if ( (unsigned int)v13 > 5 )
    {
      LODWORD(Context) = wil::ResultFromCaughtException(v13);
      p_EventDescriptor = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)word_180122C3A,
        0,
        0,
        (__int64)&p_EventDescriptor,
        (__int64)&Context);
    }
    return (unsigned int)wil::ResultFromCaughtException(v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800436c0  mov     [rsp+arg_8], rdx
0x1800436c5  push    rbx
0x1800436c6  push    rsi
0x1800436c7  push    rdi
0x1800436c8  push    r12
0x1800436ca  push    r13
0x1800436cc  push    r14
0x1800436ce  push    r15
0x1800436d0  sub     rsp, 0C0h
0x1800436d7  mov     rax, cs:__security_cookie
0x1800436de  xor     rax, rsp
0x1800436e1  mov     [rsp+0F8h+var_48], rax
0x1800436e9  mov     r15, r8
0x1800436ec  mov     rdi, rdx
0x1800436ef  mov     [rsp+0F8h+var_B8], rcx
0x1800436f4  xor     r12d, r12d
0x1800436f7  mov     [rsp+0F8h+Context], r12
0x1800436fc  mov     [rsp+0F8h+fPending], r12d
0x180043701  lea     r9, [rsp+0F8h+Context]; lpContext
0x180043706  lea     r8, [rsp+0F8h+fPending]; fPending
0x18004370b  xor     edx, edx; dwFlags
0x18004370d  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180043714  call    cs:__imp_InitOnceBeginInitialize
0x18004371a  test    eax, eax
0x18004371c  jz      loc_1800437C1
0x180043722  cmp     [rsp+0F8h+fPending], r12d
0x180043727  jz      loc_1800437C1
0x18004372d  lea     rbx, qword_180147BD0
0x180043734  mov     [rsp+0F8h+Context], rbx
0x180043739  mov     cs:qword_180147BD8, r12
0x180043740  mov     cs:byte_180147BE0, r12b
0x180043747  mov     cs:dword_180147BE4, r12d
0x18004374e  lea     rsi, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x180043755  mov     cs:qword_180147BD0, rsi
0x18004375c  lea     r14, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180043763  mov     cs:CallbackContext, r14
0x18004376a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x180043771  call    atexit
0x180043776  mov     rcx, cs:CallbackContext; CallbackContext
0x18004377d  mov     cs:qword_180147BD8, rcx
0x180043784  mov     cs:byte_180147BE0, 1
0x18004378b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180043790  mov     cs:dword_180147BE4, 1
0x18004379a  mov     rax, cs:qword_180147BD0
0x1800437a1  mov     rcx, rbx
0x1800437a4  mov     rax, [rax+8]
0x1800437a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800437ad  mov     r8, rbx; lpContext
0x1800437b0  xor     edx, edx; dwFlags
0x1800437b2  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x1800437b9  call    cs:__imp_InitOnceComplete
0x1800437bf  jmp     short loc_1800437D6
0x1800437c1  lea     rbx, qword_180147BD0
0x1800437c8  lea     rsi, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x1800437cf  lea     r14, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800437d6  mov     rax, [rsp+0F8h+Context]
0x1800437db  mov     rcx, [rax+8]
0x1800437df  mov     eax, [rcx]
0x1800437e1  cmp     eax, 5
0x1800437e4  jbe     loc_1800438A2
0x1800437ea  mov     [rsp+0F8h+Context], rdi
0x1800437ef  lea     rax, [rsp+0F8h+Context]
0x1800437f4  mov     [rsp+0F8h+var_68], rax
0x1800437fc  mov     [rsp+0F8h+var_60], 8
0x180043808  mov     dword ptr [rsp+0F8h+EventDescriptor.Id], 0B000000h
0x180043810  movzx   eax, cs:word_180122CDA
0x180043817  mov     dword ptr [rsp+0F8h+EventDescriptor.Level], eax
0x18004381b  mov     [rsp+0F8h+EventDescriptor.Keyword], r12
0x180043820  mov     rax, [rcx+8]
0x180043824  mov     [rsp+0F8h+var_88.Ptr], rax
0x180043829  movzx   eax, word ptr [rax]
0x18004382c  mov     [rsp+0F8h+var_88.Size], eax
0x180043830  mov     dword ptr [rsp+0F8h+var_88.0Ch], 2
0x180043838  lea     rax, dword_180122CE4
0x18004383f  mov     [rsp+0F8h+var_78], rax
0x180043847  mov     [rsp+0F8h+var_70], 2Bh ; '+'
0x180043852  mov     [rsp+0F8h+var_6C], 1
0x18004385d  lea     r12, _TraceLoggingMetadataEnd
0x180043864  mov     rax, r12
0x180043867  lea     r13, _TraceLoggingMetadata
0x18004386e  sub     eax, r13d
0x180043871  mov     [rsp+0F8h+fPending], eax
0x180043875  mov     eax, [rsp+0F8h+fPending]
0x180043879  lea     rax, [rsp+0F8h+var_88]
0x18004387e  mov     [rsp+0F8h+UserData], rax; UserData
0x180043883  mov     [rsp+0F8h+UserDataCount], 3; UserDataCount
0x18004388b  xor     r9d, r9d; RelatedActivityId
0x18004388e  xor     r8d, r8d; ActivityId
0x180043891  lea     rdx, [rsp+0F8h+EventDescriptor]; EventDescriptor
0x180043896  mov     rcx, [rcx+20h]; RegHandle
0x18004389a  call    cs:__imp_EventWriteTransfer
0x1800438a0  jmp     short loc_1800438B0
0x1800438a2  lea     r12, _TraceLoggingMetadataEnd
0x1800438a9  lea     r13, _TraceLoggingMetadata
0x1800438b0  mov     rcx, [rsp+0F8h]; this
0x1800438b8  test    r15, r15
0x1800438bb  jz      loc_180043ACF
0x1800438c1  mov     qword ptr [r15], 0
0x1800438c8  mov     rcx, [rsp+0F8h+var_B8]
0x1800438cd  add     rcx, 0FFFFFFFFFFFFFFC8h
0x1800438d1  mov     rax, [rcx]
0x1800438d4  lea     rdx, [rsp+0F8h+EventDescriptor]
0x1800438d9  mov     [rsp+0F8h+var_B8], rdx
0x1800438de  lea     rdx, off_1800F0088
0x1800438e5  mov     qword ptr [rsp+0F8h+EventDescriptor.Id], rdx
0x1800438ea  mov     [rsp+0F8h+EventDescriptor.Keyword], rdi
0x1800438ef  lea     rdx, [rsp+0F8h+EventDescriptor]
0x1800438f4  mov     [rsp+0F8h+var_98], rdx
0x1800438f9  mov     r8, r15
0x1800438fc  lea     rdx, [rsp+0F8h+EventDescriptor]
0x180043901  mov     rax, [rax+48h]
0x180043905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004390a  mov     rcx, [rsp+0F8h]; this
0x180043912  test    eax, eax
0x180043914  js      loc_180043AE6
0x18004391a  xor     r15d, r15d
0x18004391d  mov     [rsp+0F8h+Context], r15
0x180043922  mov     [rsp+0F8h+fPending], r15d
0x180043927  lea     r9, [rsp+0F8h+Context]; lpContext
0x18004392c  lea     r8, [rsp+0F8h+fPending]; fPending
0x180043931  xor     edx, edx; dwFlags
0x180043933  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x18004393a  call    cs:__imp_InitOnceBeginInitialize
0x180043940  test    eax, eax
0x180043942  jz      loc_1800439CC
0x180043948  cmp     [rsp+0F8h+fPending], r15d
0x18004394d  jz      short loc_1800439CC
0x18004394f  mov     [rsp+0F8h+Context], rbx
0x180043954  mov     cs:qword_180147BD8, r15
0x18004395b  mov     cs:byte_180147BE0, r15b
0x180043962  mov     cs:dword_180147BE4, r15d
0x180043969  mov     cs:qword_180147BD0, rsi
0x180043970  mov     cs:CallbackContext, r14
0x180043977  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x18004397e  call    atexit
0x180043983  mov     rcx, cs:CallbackContext; CallbackContext
0x18004398a  mov     cs:qword_180147BD8, rcx
0x180043991  mov     cs:byte_180147BE0, 1
0x180043998  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18004399d  mov     cs:dword_180147BE4, 1
0x1800439a7  mov     rax, cs:qword_180147BD0
0x1800439ae  mov     rcx, rbx
0x1800439b1  mov     rax, [rax+8]
0x1800439b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800439ba  mov     r8, rbx; lpContext
0x1800439bd  xor     edx, edx; dwFlags
0x1800439bf  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x1800439c6  call    cs:__imp_InitOnceComplete
0x1800439cc  mov     rax, [rsp+0F8h+Context]
0x1800439d1  mov     rcx, [rax+8]
0x1800439d5  mov     eax, [rcx]
0x1800439d7  cmp     eax, 5
0x1800439da  jbe     loc_180043AA4
0x1800439e0  mov     [rsp+0F8h+fPending], r15d
0x1800439e5  mov     [rsp+0F8h+var_B8], rdi
0x1800439ea  lea     rax, [rsp+0F8h+fPending]
0x1800439ef  mov     [rsp+0F8h+var_58], rax
0x1800439f7  mov     [rsp+0F8h+var_50], 4
0x180043a03  lea     rax, [rsp+0F8h+var_B8]
0x180043a08  mov     [rsp+0F8h+var_68], rax
0x180043a10  mov     [rsp+0F8h+var_60], 8
0x180043a1c  mov     dword ptr [rsp+0F8h+EventDescriptor.Id], 0B000000h
0x180043a24  movzx   eax, cs:word_180122C94
0x180043a2b  mov     dword ptr [rsp+0F8h+EventDescriptor.Level], eax
0x180043a2f  mov     [rsp+0F8h+EventDescriptor.Keyword], r15
0x180043a34  mov     rax, [rcx+8]
0x180043a38  mov     [rsp+0F8h+var_88.Ptr], rax
0x180043a3d  movzx   eax, word ptr [rax]
0x180043a40  mov     [rsp+0F8h+var_88.Size], eax
0x180043a44  mov     dword ptr [rsp+0F8h+var_88.0Ch], 2
0x180043a4c  lea     rax, word_180122C9E
0x180043a53  mov     [rsp+0F8h+var_78], rax
0x180043a5b  mov     [rsp+0F8h+var_70], 3Ah ; ':'
0x180043a66  mov     [rsp+0F8h+var_6C], 1
0x180043a71  sub     r12d, r13d
0x180043a74  mov     dword ptr [rsp+0F8h+Context], r12d
0x180043a79  mov     eax, dword ptr [rsp+0F8h+Context]
0x180043a7d  lea     rax, [rsp+0F8h+var_88]
0x180043a82  mov     [rsp+0F8h+UserData], rax; UserData
0x180043a87  mov     [rsp+0F8h+UserDataCount], 4; UserDataCount
0x180043a8f  xor     r9d, r9d; RelatedActivityId
0x180043a92  xor     r8d, r8d; ActivityId
0x180043a95  lea     rdx, [rsp+0F8h+EventDescriptor]; EventDescriptor
0x180043a9a  mov     rcx, [rcx+20h]; RegHandle
0x180043a9e  call    cs:__imp_EventWriteTransfer
0x180043aa4  xor     eax, eax
0x180043aa6  jmp     short loc_180043AAC
0x180043aa8  mov     eax, dword ptr [rsp+0F8h+Context]
0x180043aac  mov     rcx, [rsp+0F8h+var_48]
0x180043ab4  xor     rcx, rsp; StackCookie
0x180043ab7  call    __security_check_cookie
0x180043abc  add     rsp, 0C0h
0x180043ac3  pop     r15
0x180043ac5  pop     r14
0x180043ac7  pop     r13
0x180043ac9  pop     r12
0x180043acb  pop     rdi
0x180043acc  pop     rsi
0x180043acd  pop     rbx
0x180043ace  retn
0x180043acf  mov     r9d, 80004003h; char *
0x180043ad5  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180043adc  mov     edx, 6ACh; void *
0x180043ae1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043ae6  mov     r9d, eax; char *
0x180043ae9  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180043af0  mov     edx, 6BEh; void *
0x180043af5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
