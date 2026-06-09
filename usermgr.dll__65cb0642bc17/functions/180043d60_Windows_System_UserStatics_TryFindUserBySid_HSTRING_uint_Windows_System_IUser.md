# Windows::System::UserStatics::TryFindUserBySid(HSTRING__ *,uint,Windows::System::IUser * *)

- ea: `0x180043d60`
- end: `0x180044285`
- name: `?TryFindUserBySid@UserStatics@System@Windows@@UEAAJPEAUHSTRING__@@IPEAPEAUIUser@23@@Z`
- size: `1317`
- prototype: `__int64 __fastcall(Windows::System::UserStatics *__hidden this, HSTRING, unsigned int, struct Windows::System::IUser **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800018c4`
- `0x18000acdc`
- `0x180043d60`
- `0x18006b878`
- `0x18006ba78`
- `0x18006c318`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180043db9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180044059`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180043db9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180044059`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180043e5e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800440f0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180043e5e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800440f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004411a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004411a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180043f8a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180044220`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180043f8a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180044220`

## string_xrefs

- `0x180044257`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`
- `0x180044272`: `onecore\ds\security\umstartup\usermgr\lib\userstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::System::UserStatics::TryFindUserBySid(
        Windows::System::UserStatics *this,
        HSTRING a2,
        WINBOOL a3,
        struct Windows::System::IUser **a4)
{
  __int64 v6; // r15
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  int v10; // ecx
  __int64 v11; // r15
  _QWORD *v12; // rax
  int v13; // eax
  __int64 v14; // rdi
  PCWSTR v15; // rax
  int v16; // ebx
  __int64 result; // rax
  const struct _tlgProvider_t *v18; // rax
  int v19; // ebx
  wil *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  ULONG UserDataCount; // [rsp+20h] [rbp-E8h]
  WINBOOL fPending; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-C4h] BYREF
  EVENT_DESCRIPTOR Context; // [rsp+48h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+68h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-98h] BYREF
  __int16 *v30; // [rsp+80h] [rbp-88h]
  __int64 v31; // [rsp+88h] [rbp-80h]
  PCWSTR v32; // [rsp+90h] [rbp-78h]
  int v33; // [rsp+98h] [rbp-70h]
  int v34; // [rsp+9Ch] [rbp-6Ch]
  WINBOOL *p_fPending; // [rsp+A0h] [rbp-68h]
  __int64 v36; // [rsp+A8h] [rbp-60h]
  unsigned int *v37; // [rsp+B0h] [rbp-58h]
  __int64 v38; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  *(_QWORD *)&EventDescriptor.Id = this;
  string = a2;
  *(_QWORD *)&Context.Id = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`UserMgrUserModelTelemetry::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&Context)
    && fPending )
  {
    *(_QWORD *)&Context.Id = &qword_180147BD0;
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
  v6 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
  if ( *(_DWORD *)v6 <= 5u )
  {
    v8 = -1;
  }
  else
  {
    fPending = a3;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    p_fPending = &fPending;
    v36 = 4;
    v8 = -1;
    if ( StringRawBuffer )
    {
      v9 = -1;
      do
        ++v9;
      while ( StringRawBuffer[v9] );
      v10 = 2 * v9 + 2;
    }
    else
    {
      StringRawBuffer = &cchOriginalDestLength;
      v10 = 2;
    }
    v32 = StringRawBuffer;
    v33 = v10;
    v34 = 0;
    *(_QWORD *)&Context.Id = 0x50B000000LL;
    Context.Keyword = 0;
    UserData.Ptr = *(_QWORD *)(v6 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v30 = word_180122EB2;
    v31 = 0x100000030LL;
    v25 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v6 + 32), &Context, 0, 0, 4u, &UserData);
  }
  try
  {
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x63E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)0x80004003LL,
        UserDataCount);
    *a4 = 0;
    v11 = *(_QWORD *)&EventDescriptor.Id;
    *(_QWORD *)&EventDescriptor.Id = *(_QWORD *)(*(_QWORD *)&EventDescriptor.Id - 56LL);
    *(_QWORD *)&Context.Id = &UserData;
    v31 = 0;
    v12 = operator new(0x20u);
    if ( !v12 )
      std::_Xbad_alloc();
    *v12 = off_1800F00F8;
    v12[1] = &string;
    *((_DWORD *)v12 + 4) = a3;
    *((_DWORD *)v12 + 5) = HIDWORD(EventDescriptor.Keyword);
    v31 = (__int64)v12;
    v13 = (*(__int64 (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *, struct Windows::System::IUser **))(*(_QWORD *)&EventDescriptor.Id + 72LL))(
            v11 - 56,
            &UserData,
            a4);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x651,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userstatics.cpp",
        (const char *)(unsigned int)v13,
        UserDataCount);
    *(_QWORD *)&Context.Id = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`UserMgrUserModelTelemetry::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&Context)
      && fPending )
    {
      *(_QWORD *)&Context.Id = &qword_180147BD0;
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
    v14 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
    if ( *(_DWORD *)v14 > 5u )
    {
      v25 = 0;
      fPending = a3;
      v15 = WindowsGetStringRawBuffer(string, 0);
      v37 = &v25;
      v38 = 4;
      p_fPending = &fPending;
      v36 = 4;
      if ( v15 )
      {
        do
          ++v8;
        while ( v15[v8] );
        v16 = 2 * v8 + 2;
      }
      else
      {
        v15 = &cchOriginalDestLength;
        v16 = 2;
      }
      v32 = v15;
      v33 = v16;
      v34 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = *(_QWORD *)(v14 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      v30 = (__int16 *)&byte_180122E67;
      v31 = 0x10000003FLL;
      *(_DWORD *)&Context.Id = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v14 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
    }
    result = 0;
  }
  catch ( ... )
  {
    v18 = UserMgrUserModelTelemetry::Provider();
    v19 = (int)v18;
    v20 = (wil *)*(unsigned int *)v18;
    if ( (unsigned int)v20 > 5 )
    {
      *(_DWORD *)&Context.Id = wil::ResultFromCaughtException(v20);
      v25 = a3;
      *(_QWORD *)&EventDescriptor.Id = WindowsGetStringRawBuffer(string, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&word_180122DFE,
        v21,
        v22,
        (__int64)&EventDescriptor,
        (__int64)&v25,
        (__int64)&Context);
    }
    return (unsigned int)wil::ResultFromCaughtException(v20);
  }
  return result;
}

```

## disassembly

```asm
0x180043d60  mov     [rsp+arg_10], r8d
0x180043d65  push    rbx
0x180043d66  push    rsi
0x180043d67  push    rdi
0x180043d68  push    r12
0x180043d6a  push    r13
0x180043d6c  push    r14
0x180043d6e  push    r15
0x180043d70  sub     rsp, 0D0h
0x180043d77  mov     rax, cs:__security_cookie
0x180043d7e  xor     rax, rsp
0x180043d81  mov     [rsp+108h+var_48], rax
0x180043d89  mov     r12, r9
0x180043d8c  mov     esi, r8d
0x180043d8f  mov     qword ptr [rsp+108h+EventDescriptor.Id], rcx
0x180043d94  mov     [rsp+108h+string], rdx
0x180043d99  xor     r14d, r14d
0x180043d9c  mov     [rsp+108h+Context], r14
0x180043da1  mov     [rsp+108h+fPending], r14d
0x180043da6  lea     r9, [rsp+108h+Context]; lpContext
0x180043dab  lea     r8, [rsp+108h+fPending]; fPending
0x180043db0  xor     edx, edx; dwFlags
0x180043db2  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180043db9  call    cs:__imp_InitOnceBeginInitialize
0x180043dbf  test    eax, eax
0x180043dc1  jz      loc_180043E66
0x180043dc7  cmp     [rsp+108h+fPending], r14d
0x180043dcc  jz      loc_180043E66
0x180043dd2  lea     rdi, qword_180147BD0
0x180043dd9  mov     [rsp+108h+Context], rdi
0x180043dde  mov     cs:qword_180147BD8, r14
0x180043de5  mov     cs:byte_180147BE0, r14b
0x180043dec  mov     cs:dword_180147BE4, r14d
0x180043df3  lea     r13, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x180043dfa  mov     cs:qword_180147BD0, r13
0x180043e01  lea     rbx, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180043e08  mov     cs:CallbackContext, rbx
0x180043e0f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x180043e16  call    atexit
0x180043e1b  mov     rcx, cs:CallbackContext; CallbackContext
0x180043e22  mov     cs:qword_180147BD8, rcx
0x180043e29  mov     cs:byte_180147BE0, 1
0x180043e30  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180043e35  mov     cs:dword_180147BE4, 1
0x180043e3f  mov     rax, cs:qword_180147BD0
0x180043e46  mov     rcx, rdi
0x180043e49  mov     rax, [rax+8]
0x180043e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e52  mov     r8, rdi; lpContext
0x180043e55  xor     edx, edx; dwFlags
0x180043e57  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180043e5e  call    cs:__imp_InitOnceComplete
0x180043e64  jmp     short loc_180043E74
0x180043e66  lea     rdi, qword_180147BD0
0x180043e6d  lea     r13, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x180043e74  mov     rax, [rsp+108h+Context]
0x180043e79  mov     r15, [rax+8]
0x180043e7d  mov     eax, [r15]
0x180043e80  cmp     eax, 5
0x180043e83  jbe     loc_180043F92
0x180043e89  mov     [rsp+108h+fPending], esi
0x180043e8d  xor     edx, edx; length
0x180043e8f  mov     rcx, [rsp+108h+string]; string
0x180043e94  call    cs:__imp_WindowsGetStringRawBuffer
0x180043e9a  lea     rcx, [rsp+108h+fPending]
0x180043e9f  mov     [rsp+108h+var_68], rcx
0x180043ea7  mov     [rsp+108h+var_60], 4
0x180043eb3  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180043eba  test    rax, rax
0x180043ebd  jz      short loc_180043ED6
0x180043ebf  mov     rcx, rbx
0x180043ec2  lea     rcx, [rcx+1]
0x180043ec6  cmp     [rax+rcx*2], r14w
0x180043ecb  jnz     short loc_180043EC2
0x180043ecd  lea     ecx, ds:2[rcx*2]
0x180043ed4  jmp     short loc_180043EE2
0x180043ed6  lea     rax, cchOriginalDestLength
0x180043edd  mov     ecx, 2
0x180043ee2  mov     [rsp+108h+var_78], rax
0x180043eea  mov     [rsp+108h+var_70], ecx
0x180043ef1  mov     [rsp+108h+var_6C], r14d
0x180043ef9  mov     dword ptr [rsp+108h+Context], 0B000000h
0x180043f01  movzx   eax, cs:word_180122EA8
0x180043f08  mov     dword ptr [rsp+108h+Context+4], eax
0x180043f0c  mov     [rsp+108h+var_B8], r14
0x180043f11  mov     rax, [r15+8]
0x180043f15  mov     [rsp+108h+var_98.Ptr], rax
0x180043f1a  movzx   eax, word ptr [rax]
0x180043f1d  mov     [rsp+108h+var_98.Size], eax
0x180043f21  mov     dword ptr [rsp+108h+var_98.0Ch], 2
0x180043f29  lea     rax, word_180122EB2
0x180043f30  mov     [rsp+108h+var_88], rax
0x180043f38  mov     dword ptr [rsp+108h+var_80], 30h ; '0'
0x180043f43  mov     dword ptr [rsp+108h+var_80+4], 1
0x180043f4e  lea     r14, _TraceLoggingMetadataEnd
0x180043f55  mov     rax, r14
0x180043f58  lea     rcx, _TraceLoggingMetadata
0x180043f5f  sub     eax, ecx
0x180043f61  mov     [rsp+108h+var_C4], eax
0x180043f65  mov     eax, [rsp+108h+var_C4]
0x180043f69  lea     rax, [rsp+108h+var_98]
0x180043f6e  mov     [rsp+108h+UserData], rax; UserData
0x180043f73  mov     [rsp+108h+UserDataCount], 4; UserDataCount
0x180043f7b  xor     r9d, r9d; RelatedActivityId
0x180043f7e  xor     r8d, r8d; ActivityId
0x180043f81  lea     rdx, [rsp+108h+Context]; EventDescriptor
0x180043f86  mov     rcx, [r15+20h]; RegHandle
0x180043f8a  call    cs:__imp_EventWriteTransfer
0x180043f90  jmp     short loc_180043FA0
0x180043f92  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180043f99  lea     r14, _TraceLoggingMetadataEnd
0x180043fa0  mov     rcx, [rsp+108h]; this
0x180043fa8  test    r12, r12
0x180043fab  jz      loc_180044251
0x180043fb1  xor     edx, edx
0x180043fb3  mov     [r12], rdx
0x180043fb7  mov     r15, qword ptr [rsp+108h+EventDescriptor.Id]
0x180043fbc  mov     rax, [r15-38h]
0x180043fc0  mov     qword ptr [rsp+108h+EventDescriptor.Id], rax
0x180043fc5  lea     rcx, [rsp+108h+var_98]
0x180043fca  mov     [rsp+108h+Context], rcx
0x180043fcf  mov     [rsp+108h+var_80], rdx
0x180043fd7  mov     ecx, 20h ; ' '; Size
0x180043fdc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043fe1  test    rax, rax
0x180043fe4  jz      loc_180044269
0x180043fea  lea     rcx, off_1800F00F8
0x180043ff1  mov     [rax], rcx
0x180043ff4  lea     rcx, [rsp+108h+string]
0x180043ff9  mov     [rax+8], rcx
0x180043ffd  mov     [rax+10h], esi
0x180044000  mov     edx, dword ptr [rsp+108h+EventDescriptor.Keyword+4]
0x180044004  mov     [rax+14h], edx
0x180044007  mov     [rsp+108h+var_80], rax
0x18004400f  mov     r8, r12
0x180044012  lea     rdx, [rsp+108h+var_98]
0x180044017  lea     rcx, [r15-38h]
0x18004401b  mov     rax, qword ptr [rsp+108h+EventDescriptor.Id]
0x180044020  mov     rax, [rax+48h]
0x180044024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044029  mov     rcx, [rsp+108h]; this
0x180044031  test    eax, eax
0x180044033  js      loc_18004426F
0x180044039  xor     r15d, r15d
0x18004403c  mov     [rsp+108h+Context], r15
0x180044041  mov     [rsp+108h+fPending], r15d
0x180044046  lea     r9, [rsp+108h+Context]; lpContext
0x18004404b  lea     r8, [rsp+108h+fPending]; fPending
0x180044050  xor     edx, edx; dwFlags
0x180044052  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180044059  call    cs:__imp_InitOnceBeginInitialize
0x18004405f  test    eax, eax
0x180044061  jz      loc_1800440F6
0x180044067  cmp     [rsp+108h+fPending], r15d
0x18004406c  jz      loc_1800440F6
0x180044072  mov     [rsp+108h+Context], rdi
0x180044077  mov     cs:qword_180147BD8, r15
0x18004407e  mov     cs:byte_180147BE0, r15b
0x180044085  mov     cs:dword_180147BE4, r15d
0x18004408c  mov     cs:qword_180147BD0, r13
0x180044093  lea     rax, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18004409a  mov     cs:CallbackContext, rax
0x1800440a1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x1800440a8  call    atexit
0x1800440ad  mov     rcx, cs:CallbackContext; CallbackContext
0x1800440b4  mov     cs:qword_180147BD8, rcx
0x1800440bb  mov     cs:byte_180147BE0, 1
0x1800440c2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800440c7  mov     cs:dword_180147BE4, 1
0x1800440d1  mov     rax, cs:qword_180147BD0
0x1800440d8  mov     rcx, rdi
0x1800440db  mov     rax, [rax+8]
0x1800440df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440e4  mov     r8, rdi; lpContext
0x1800440e7  xor     edx, edx; dwFlags
0x1800440e9  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x1800440f0  call    cs:__imp_InitOnceComplete
0x1800440f6  mov     rax, [rsp+108h+Context]
0x1800440fb  mov     rdi, [rax+8]
0x1800440ff  mov     eax, [rdi]
0x180044101  cmp     eax, 5
0x180044104  jbe     loc_180044226
0x18004410a  mov     [rsp+108h+var_C4], r15d
0x18004410f  mov     [rsp+108h+fPending], esi
0x180044113  xor     edx, edx; length
0x180044115  mov     rcx, [rsp+108h+string]; string
0x18004411a  call    cs:__imp_WindowsGetStringRawBuffer
0x180044120  lea     rcx, [rsp+108h+var_C4]
0x180044125  mov     [rsp+108h+var_58], rcx
0x18004412d  mov     [rsp+108h+var_50], 4
0x180044139  lea     rcx, [rsp+108h+fPending]
0x18004413e  mov     [rsp+108h+var_68], rcx
0x180044146  mov     [rsp+108h+var_60], 4
0x180044152  test    rax, rax
0x180044155  jz      short loc_180044174
0x180044157  nop     word ptr [rax+rax+00000000h]
0x180044160  lea     rbx, [rbx+1]
0x180044164  cmp     [rax+rbx*2], r15w
0x180044169  jnz     short loc_180044160
0x18004416b  lea     ebx, ds:2[rbx*2]
0x180044172  jmp     short loc_180044180
0x180044174  lea     rax, cchOriginalDestLength
0x18004417b  mov     ebx, 2
0x180044180  mov     [rsp+108h+var_78], rax
0x180044188  mov     [rsp+108h+var_70], ebx
0x18004418f  mov     [rsp+108h+var_6C], r15d
0x180044197  mov     dword ptr [rsp+108h+EventDescriptor.Id], 0B000000h
0x18004419f  movzx   eax, cs:word_180122E5D
0x1800441a6  mov     dword ptr [rsp+108h+EventDescriptor.Level], eax
0x1800441aa  mov     [rsp+60h], r15
0x1800441af  mov     rax, [rdi+8]
0x1800441b3  mov     [rsp+108h+var_98.Ptr], rax
0x1800441b8  movzx   eax, word ptr [rax]
0x1800441bb  mov     [rsp+108h+var_98.Size], eax
0x1800441bf  mov     dword ptr [rsp+108h+var_98.0Ch], 2
0x1800441c7  lea     rax, byte_180122E67
0x1800441ce  mov     [rsp+108h+var_88], rax
0x1800441d6  mov     dword ptr [rsp+108h+var_80], 3Fh ; '?'
0x1800441e1  mov     dword ptr [rsp+108h+var_80+4], 1
0x1800441ec  lea     rax, _TraceLoggingMetadata
0x1800441f3  sub     r14d, eax
0x1800441f6  mov     dword ptr [rsp+108h+Context], r14d
0x1800441fb  mov     eax, dword ptr [rsp+108h+Context]
0x1800441ff  lea     rax, [rsp+108h+var_98]
0x180044204  mov     [rsp+108h+UserData], rax; UserData
0x180044209  mov     [rsp+108h+UserDataCount], 5; UserDataCount
0x180044211  xor     r9d, r9d; RelatedActivityId
0x180044214  xor     r8d, r8d; ActivityId
0x180044217  lea     rdx, [rsp+108h+EventDescriptor]; EventDescriptor
0x18004421c  mov     rcx, [rdi+20h]; RegHandle
0x180044220  call    cs:__imp_EventWriteTransfer
0x180044226  xor     eax, eax
0x180044228  jmp     short loc_18004422E
0x18004422a  mov     eax, dword ptr [rsp+108h+Context]
0x18004422e  mov     rcx, [rsp+108h+var_48]
0x180044236  xor     rcx, rsp; StackCookie
0x180044239  call    __security_check_cookie
0x18004423e  add     rsp, 0D0h
0x180044245  pop     r15
0x180044247  pop     r14
0x180044249  pop     r13
0x18004424b  pop     r12
0x18004424d  pop     rdi
0x18004424e  pop     rsi
0x18004424f  pop     rbx
0x180044250  retn
0x180044251  mov     r9d, 80004003h; char *
0x180044257  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x18004425e  mov     edx, 63Eh; void *
0x180044263  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044269  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18004426f  mov     r9d, eax; char *
0x180044272  lea     r8, aOnecoreDsSecur_68; "onecore\\ds\\security\\umstartup\\userm"...
0x180044279  mov     edx, 651h; void *
0x18004427e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
