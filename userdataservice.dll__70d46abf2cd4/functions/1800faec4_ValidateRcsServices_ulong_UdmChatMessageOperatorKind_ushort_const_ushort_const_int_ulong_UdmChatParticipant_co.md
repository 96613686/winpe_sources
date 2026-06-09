# ValidateRcsServices(ulong,UdmChatMessageOperatorKind,ushort const *,ushort const *,int,ulong,UdmChatParticipant const *,ulong,UdmChatAttachment const *,ulong *,ulong *,ulong *,ulong *,int *,int *,UdmChatMessageValidationStatus *)

- ea: `0x1800faec4`
- end: `0x1800fb4da`
- name: `?ValidateRcsServices@@YAJKW4UdmChatMessageOperatorKind@@PEBG1HKPEBUUdmChatParticipant@@KPEBUUdmChatAttachment@@PEAK444PEAH5PEAW4UdmChatMessageValidationStatus@@@Z`
- size: `1558`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x180095274`

## callees

- `0x18005e048`
- `0x18006db44`
- `0x180072ccc`
- `0x180092434`
- `0x180092554`
- `0x1800925e4`
- `0x180095a0c`
- `0x1800a82b8`
- `0x1800a83e4`
- `0x1800a84f4`
- `0x1800a85c0`
- `0x1800a86ac`
- `0x1800fa690`
- `0x1800faec4`
- `0x1800fcc6c`
- `0x1800fd830`
- `0x1800fd990`

## import_xrefs

- `MessagingDataModel2!Messaging_IsRcsEnabled` at `0x1800faf4c`
- `MessagingDataModel2!Messaging_IsRcsEnabled` at `0x1800faf4c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fafe5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb0e9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb167`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb1ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb250`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb2db`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb3a7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb44d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fafe5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb0e9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb167`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb1ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb250`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb2db`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb3a7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fb44d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fafb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb0c6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb13d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb1a7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb22d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb2b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb381`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb427`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fafb8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb0c6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb13d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb1a7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb22d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb2b5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb381`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fb427`

## pseudocode

```c
__int64 ValidateRcsServices(unsigned int a1, int a2, ...)
{
  int *v2; // r15
  _DWORD *v4; // rax
  _DWORD *v5; // rax
  int IsRcsEnabled; // edi
  __int64 v7; // r8
  __int64 v8; // r9
  int v10; // r12d
  RcsServiceManager *v11; // r14
  const unsigned __int16 **v12; // r15
  int v13; // eax
  __int64 v14; // r8
  int GroupChatMaxMessageLength; // r14d
  int IsMultipartMessageCapable; // eax
  __int64 v17; // r8
  int v18; // eax
  RcsServiceManager *v19; // r14
  __int64 v20; // r8
  __int64 v21; // r9
  RcsServiceManager *v22; // r14
  RcsServiceManager *v23; // r14
  RcsServiceManager *v24; // r14
  RcsServiceManager *v25; // r14
  int IsFileTransferSupported; // eax
  int v27; // ecx
  int v28; // edx
  int v29; // r15d
  unsigned int *v30; // rcx
  RcsServiceManager *v31; // r14
  RcsServiceManager *v32; // r14
  __int64 v33; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv[5]; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v35; // [rsp+A8h] [rbp+48h] BYREF
  __int64 fPending; // [rsp+B0h] [rbp+50h] BYREF
  va_list fPendinga; // [rsp+B0h] [rbp+50h]
  RcsServiceManager *v38; // [rsp+B8h] [rbp+58h] BYREF
  va_list va1; // [rsp+B8h] [rbp+58h]
  __int64 v40; // [rsp+C0h] [rbp+60h]
  __int64 v41; // [rsp+C8h] [rbp+68h]
  const unsigned __int16 **v42; // [rsp+D0h] [rbp+70h]
  __int64 v43; // [rsp+D8h] [rbp+78h]
  LPVOID Context; // [rsp+E0h] [rbp+80h] BYREF
  va_list Contexta; // [rsp+E0h] [rbp+80h]
  _DWORD *v46; // [rsp+E8h] [rbp+88h]
  int *v47; // [rsp+F0h] [rbp+90h] BYREF
  va_list va3; // [rsp+F0h] [rbp+90h]
  int *v49; // [rsp+F8h] [rbp+98h]
  int *v50; // [rsp+100h] [rbp+A0h]
  _DWORD *v51; // [rsp+108h] [rbp+A8h]
  _DWORD *v52; // [rsp+110h] [rbp+B0h] BYREF
  va_list va4; // [rsp+110h] [rbp+B0h]
  _DWORD *v54; // [rsp+118h] [rbp+B8h]
  va_list va5; // [rsp+120h] [rbp+C0h] BYREF

  va_start(va5, a2);
  va_start(va4, a2);
  va_start(va3, a2);
  va_start(Contexta, a2);
  va_start(va1, a2);
  va_start(fPendinga, a2);
  fPending = va_arg(va1, _QWORD);
  va_copy(Contexta, va1);
  v38 = va_arg(Contexta, RcsServiceManager *);
  v40 = va_arg(Contexta, _QWORD);
  v41 = va_arg(Contexta, _QWORD);
  v42 = va_arg(Contexta, const unsigned __int16 **);
  v43 = va_arg(Contexta, _QWORD);
  va_copy(va3, Contexta);
  Context = va_arg(va3, LPVOID);
  v46 = va_arg(va3, _DWORD *);
  va_copy(va4, va3);
  v47 = va_arg(va4, int *);
  v49 = va_arg(va4, int *);
  v50 = va_arg(va4, int *);
  v51 = va_arg(va4, _DWORD *);
  va_copy(va5, va4);
  v52 = va_arg(va5, _DWORD *);
  v54 = va_arg(va5, _DWORD *);
  v2 = v47;
  *v50 = 0;
  v4 = v46;
  *v2 = 0;
  *v4 = 0;
  *v49 = 0;
  *v51 = 0;
  *v52 = 0;
  v5 = v54;
  *v54 = 2;
  if ( a2 == 3 )
  {
    v35 = 0;
    if ( a1 - 101 > 0x63 )
    {
      LODWORD(v38) = 0;
      IsRcsEnabled = Messaging_IsRcsEnabled((RcsServiceManager **)va1);
      if ( IsRcsEnabled < 0 )
      {
        v8 = 156;
LABEL_6:
        Log_HREvent_51((unsigned int)IsRcsEnabled, 1, v7, v8);
        return (unsigned int)IsRcsEnabled;
      }
      if ( !(_DWORD)v38 )
        goto LABEL_59;
    }
    LODWORD(v38) = 0;
    v10 = 0;
    if ( (unsigned int)v41 > 1 || (_DWORD)v40 )
    {
      LODWORD(v47) = 0;
      v38 = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)va3, (LPVOID *)va1);
      v22 = v38;
      if ( !v38 )
      {
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        fPending = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        v22 = (RcsServiceManager *)qword_18015DCE0;
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer((__int64 *)fPendinga);
      }
      if ( !(unsigned int)RcsServiceManager::IsGroupChatSupported(v22, a1) )
        goto LABEL_59;
      LODWORD(v47) = 0;
      v38 = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)va3, (LPVOID *)va1);
      v23 = v38;
      if ( !v38 )
      {
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        fPending = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        v23 = (RcsServiceManager *)qword_18015DCE0;
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer((__int64 *)fPendinga);
      }
      GroupChatMaxMessageLength = RcsServiceManager::GetGroupChatMaxMessageLength(v23, a1, &v35);
      if ( GroupChatMaxMessageLength < 0 )
      {
        v21 = 175;
        goto LABEL_32;
      }
      LODWORD(v52) = 0;
      LODWORD(v47) = 0;
      v38 = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)va3, (LPVOID *)va1);
      v24 = v38;
      if ( !v38 )
      {
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        fPending = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        v24 = (RcsServiceManager *)qword_18015DCE0;
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer((__int64 *)fPendinga);
      }
      GroupChatMaxMessageLength = RcsServiceManager::GetMaxParticipants(v24, a1, (unsigned int *)va4);
      if ( GroupChatMaxMessageLength < 0 )
      {
        v21 = 178;
        goto LABEL_32;
      }
      v18 = (_DWORD)v52 - 1;
    }
    else
    {
      LODWORD(fPending) = 0;
      Context = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)fPendinga, (LPVOID *)Contexta);
      v11 = (RcsServiceManager *)Context;
      if ( !Context )
      {
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        v33 = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        v11 = (RcsServiceManager *)qword_18015DCE0;
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v33);
      }
      if ( !(unsigned int)RcsServiceManager::IsChatSupported(v11, a1) )
        goto LABEL_59;
      v12 = v42;
      if ( !v42 )
        goto LABEL_21;
      ChatCapabilitiesContext::ChatCapabilitiesContext((ChatCapabilitiesContext *)ppv);
      v13 = ChatCapabilitiesContext::Initialize(ppv);
      GroupChatMaxMessageLength = v13;
      if ( v13 < 0 )
      {
        Log_HREvent_51((unsigned int)v13, 1, v14, 198);
        ChatCapabilitiesContext::~ChatCapabilitiesContext((ChatCapabilitiesContext *)ppv);
        return (unsigned int)GroupChatMaxMessageLength;
      }
      IsMultipartMessageCapable = ChatCapabilitiesContext::IsMultipartMessageCapable(
                                    (ChatCapabilitiesContext *)ppv,
                                    *v12,
                                    a1,
                                    (int *)va1);
      if ( IsMultipartMessageCapable < 0 )
        Log_HREvent_51((unsigned int)IsMultipartMessageCapable, 0, v17, 200);
      v10 = (int)v38;
      *v52 = (_DWORD)v38;
      ChatCapabilitiesContext::~ChatCapabilitiesContext((ChatCapabilitiesContext *)ppv);
      if ( v10 )
      {
        v35 = 8000;
      }
      else
      {
LABEL_21:
        LODWORD(v52) = 0;
        v38 = 0;
        InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)va4, (LPVOID *)va1);
        v19 = v38;
        if ( !v38 )
        {
          RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
          fPending = 0;
          InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
          v19 = (RcsServiceManager *)qword_18015DCE0;
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer((__int64 *)fPendinga);
        }
        GroupChatMaxMessageLength = RcsServiceManager::GetChatMaxMessageLength(v19, a1, &v35);
        if ( GroupChatMaxMessageLength < 0 )
        {
          v21 = 211;
          goto LABEL_32;
        }
      }
      v2 = v47;
      v18 = 1;
    }
    *v2 = v18;
    LODWORD(v52) = 0;
    v47 = 0;
    InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)va4, (LPVOID *)va3);
    v25 = (RcsServiceManager *)v47;
    if ( !v47 )
    {
      RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
      v38 = 0;
      InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
      v25 = (RcsServiceManager *)qword_18015DCE0;
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer((RcsServiceManager **)va1);
    }
    IsFileTransferSupported = RcsServiceManager::IsFileTransferSupported(v25, a1);
    v27 = 0;
    v28 = 0;
    v29 = IsFileTransferSupported;
    LODWORD(v47) = 0;
    LODWORD(v38) = 0;
    if ( !(_DWORD)v43 )
      goto LABEL_45;
    if ( !IsFileTransferSupported )
    {
      if ( v10 )
      {
        v27 = 10485760;
        v28 = 9437184;
        goto LABEL_45;
      }
LABEL_59:
      *v54 = 5;
      return 0;
    }
    LODWORD(v52) = 0;
    LODWORD(fPending) = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)fPendinga, (LPVOID *)Contexta);
    v31 = (RcsServiceManager *)Context;
    if ( !Context )
    {
      RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
      v33 = 0;
      InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
      v31 = (RcsServiceManager *)qword_18015DCE0;
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v33);
    }
    GroupChatMaxMessageLength = RcsServiceManager::GetMaxFileSizeKb(v31, a1, (unsigned int *)va4);
    if ( GroupChatMaxMessageLength >= 0 )
    {
      GroupChatMaxMessageLength = ULongLongToULong((unsigned __int64)(unsigned int)v52 << 10, (unsigned int *)va3);
      if ( GroupChatMaxMessageLength >= 0 )
      {
        LODWORD(v52) = 0;
        LODWORD(fPending) = 0;
        Context = 0;
        InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)fPendinga, (LPVOID *)Contexta);
        v32 = (RcsServiceManager *)Context;
        if ( !Context )
        {
          RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
          v33 = 0;
          InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
          v32 = (RcsServiceManager *)qword_18015DCE0;
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v33);
        }
        IsRcsEnabled = RcsServiceManager::GetWarningFileSizeKb(v32, a1, (unsigned int *)va4);
        if ( IsRcsEnabled < 0 )
        {
          v8 = 238;
          goto LABEL_6;
        }
        IsRcsEnabled = ULongLongToULong((unsigned __int64)(unsigned int)v52 << 10, (unsigned int *)va1);
        if ( IsRcsEnabled < 0 )
        {
          v8 = 239;
          goto LABEL_6;
        }
        v27 = (int)v47;
        v28 = (int)v38;
LABEL_45:
        *v49 = v27;
        v30 = v46;
        *v50 = v28;
        *v30 = v35;
        *v51 = v29;
        *v54 = 0;
        return 0;
      }
      v21 = 235;
    }
    else
    {
      v21 = 234;
    }
LABEL_32:
    Log_HREvent_51((unsigned int)GroupChatMaxMessageLength, 1, v20, v21);
    return (unsigned int)GroupChatMaxMessageLength;
  }
  *v5 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800faec4  mov     [rsp-38h+arg_0], rbx
0x1800faec9  mov     [rsp-38h+arg_18], r9
0x1800faece  mov     [rsp-38h+fPending], r8
0x1800faed3  push    rbp
0x1800faed4  push    rsi
0x1800faed5  push    rdi
0x1800faed6  push    r12
0x1800faed8  push    r13
0x1800faeda  push    r14
0x1800faedc  push    r15
0x1800faede  mov     rbp, rsp
0x1800faee1  sub     rsp, 60h
0x1800faee5  mov     rax, [rbp+arg_60]
0x1800faeec  xor     esi, esi
0x1800faeee  mov     r15, [rbp+arg_50]
0x1800faef5  mov     r13d, ecx
0x1800faef8  mov     [rax], esi
0x1800faefa  mov     rax, [rbp+arg_48]
0x1800faf01  mov     [r15], esi
0x1800faf04  mov     [rax], esi
0x1800faf06  mov     rax, [rbp+arg_58]
0x1800faf0d  mov     [rax], esi
0x1800faf0f  mov     rax, [rbp+arg_68]
0x1800faf16  mov     [rax], esi
0x1800faf18  mov     rax, [rbp+arg_70]
0x1800faf1f  mov     [rax], esi
0x1800faf21  mov     rax, [rbp+arg_78]
0x1800faf28  mov     dword ptr [rax], 2
0x1800faf2e  cmp     edx, 3
0x1800faf31  jz      short loc_1800FAF3A
0x1800faf33  mov     [rax], esi
0x1800faf35  jmp     loc_1800FB4C0
0x1800faf3a  lea     eax, [rcx-65h]
0x1800faf3d  mov     [rbp+arg_8], esi
0x1800faf40  cmp     eax, 63h ; 'c'
0x1800faf43  jbe     short loc_1800FAF7A
0x1800faf45  lea     rcx, [rbp+arg_18]
0x1800faf49  mov     dword ptr [rbp+arg_18], esi
0x1800faf4c  call    cs:__imp_Messaging_IsRcsEnabled
0x1800faf52  mov     edi, eax
0x1800faf54  test    eax, eax
0x1800faf56  jns     short loc_1800FAF71
0x1800faf58  mov     edx, 1
0x1800faf5d  mov     r9d, 9Ch
0x1800faf63  mov     ecx, edi
0x1800faf65  call    Log_HREvent_51
0x1800faf6a  mov     eax, edi
0x1800faf6c  jmp     loc_1800FB4C2
0x1800faf71  cmp     dword ptr [rbp+arg_18], esi
0x1800faf74  jz      loc_1800FB4B3
0x1800faf7a  mov     ebx, 1
0x1800faf7f  mov     dword ptr [rbp+arg_18], esi
0x1800faf82  mov     r12d, esi
0x1800faf85  cmp     dword ptr [rbp+arg_28], ebx
0x1800faf88  ja      loc_1800FB11C
0x1800faf8e  cmp     dword ptr [rbp+arg_20], esi
0x1800faf91  jnz     loc_1800FB11C
0x1800faf97  mov     dword ptr [rbp+fPending], esi
0x1800faf9a  lea     r9, [rbp+Context]; lpContext
0x1800fafa1  mov     [rbp+Context], rsi
0x1800fafa8  lea     r8, [rbp+fPending]; fPending
0x1800fafac  lea     rsi, stru_18015DCD8
0x1800fafb3  xor     edx, edx; dwFlags
0x1800fafb5  mov     rcx, rsi; lpInitOnce
0x1800fafb8  call    cs:__imp_InitOnceBeginInitialize
0x1800fafbe  mov     r14, [rbp+Context]
0x1800fafc5  lea     rdi, qword_18015DCE0
0x1800fafcc  test    r14, r14
0x1800fafcf  jnz     short loc_1800FAFF7
0x1800fafd1  mov     rcx, rdi; this
0x1800fafd4  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fafd9  mov     r8, rdi; lpContext
0x1800fafdc  mov     [rbp+var_30], r12
0x1800fafe0  xor     edx, edx; dwFlags
0x1800fafe2  mov     rcx, rsi; lpInitOnce
0x1800fafe5  call    cs:__imp_InitOnceComplete
0x1800fafeb  lea     rcx, [rbp+var_30]
0x1800fafef  mov     r14, rdi
0x1800faff2  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800faff7  mov     edx, r13d; unsigned int
0x1800faffa  mov     rcx, r14; this
0x1800faffd  call    ?IsChatSupported@RcsServiceManager@@QEAAHK@Z; RcsServiceManager::IsChatSupported(ulong)
0x1800fb002  test    eax, eax
0x1800fb004  jz      loc_1800FB4B3
0x1800fb00a  mov     r15, [rbp+arg_30]
0x1800fb00e  test    r15, r15
0x1800fb011  jz      loc_1800FB0A4
0x1800fb017  lea     rcx, [rbp+ppv]; this
0x1800fb01b  call    ??0ChatCapabilitiesContext@@QEAA@XZ; ChatCapabilitiesContext::ChatCapabilitiesContext(void)
0x1800fb020  lea     rcx, [rbp+ppv]; ppv
0x1800fb024  call    ?Initialize@ChatCapabilitiesContext@@QEAAJXZ; ChatCapabilitiesContext::Initialize(void)
0x1800fb029  mov     r14d, eax
0x1800fb02c  test    eax, eax
0x1800fb02e  jns     short loc_1800FB04D
0x1800fb030  mov     r9d, 0C6h
0x1800fb036  mov     edx, ebx
0x1800fb038  mov     ecx, eax
0x1800fb03a  call    Log_HREvent_51
0x1800fb03f  lea     rcx, [rbp+ppv]; this
0x1800fb043  call    ??1ChatCapabilitiesContext@@QEAA@XZ; ChatCapabilitiesContext::~ChatCapabilitiesContext(void)
0x1800fb048  jmp     loc_1800FB205
0x1800fb04d  mov     rdx, [r15]; unsigned __int16 *
0x1800fb050  lea     r9, [rbp+arg_18]; int *
0x1800fb054  mov     r8d, r13d; unsigned int
0x1800fb057  lea     rcx, [rbp+ppv]; this
0x1800fb05b  call    ?IsMultipartMessageCapable@ChatCapabilitiesContext@@QEAAJPEBGKPEAH@Z; ChatCapabilitiesContext::IsMultipartMessageCapable(ushort const *,ulong,int *)
0x1800fb060  test    eax, eax
0x1800fb062  jns     short loc_1800FB073
0x1800fb064  xor     edx, edx
0x1800fb066  mov     r9d, 0C8h
0x1800fb06c  mov     ecx, eax
0x1800fb06e  call    Log_HREvent_51
0x1800fb073  mov     rax, [rbp+arg_70]
0x1800fb07a  lea     rcx, [rbp+ppv]; this
0x1800fb07e  mov     r12d, dword ptr [rbp+arg_18]
0x1800fb082  mov     [rax], r12d
0x1800fb085  call    ??1ChatCapabilitiesContext@@QEAA@XZ; ChatCapabilitiesContext::~ChatCapabilitiesContext(void)
0x1800fb08a  test    r12d, r12d
0x1800fb08d  jz      short loc_1800FB0A4
0x1800fb08f  mov     [rbp+arg_8], 1F40h
0x1800fb096  mov     r15, [rbp+arg_50]
0x1800fb09d  mov     eax, ebx
0x1800fb09f  jmp     loc_1800FB28E
0x1800fb0a4  lea     r9, [rbp+arg_18]; lpContext
0x1800fb0a8  mov     dword ptr [rbp+arg_70], 0
0x1800fb0b2  lea     r8, [rbp+arg_70]; fPending
0x1800fb0b9  mov     [rbp+arg_18], 0
0x1800fb0c1  xor     edx, edx; dwFlags
0x1800fb0c3  mov     rcx, rsi; lpInitOnce
0x1800fb0c6  call    cs:__imp_InitOnceBeginInitialize
0x1800fb0cc  mov     r14, [rbp+arg_18]
0x1800fb0d0  test    r14, r14
0x1800fb0d3  jnz     short loc_1800FB0FB
0x1800fb0d5  mov     rcx, rdi; this
0x1800fb0d8  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fb0dd  mov     r8, rdi; lpContext
0x1800fb0e0  mov     [rbp+fPending], r14
0x1800fb0e4  xor     edx, edx; dwFlags
0x1800fb0e6  mov     rcx, rsi; lpInitOnce
0x1800fb0e9  call    cs:__imp_InitOnceComplete
0x1800fb0ef  lea     rcx, [rbp+fPending]
0x1800fb0f3  mov     r14, rdi
0x1800fb0f6  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800fb0fb  lea     r8, [rbp+arg_8]; unsigned int *
0x1800fb0ff  mov     edx, r13d; unsigned int
0x1800fb102  mov     rcx, r14; this
0x1800fb105  call    ?GetChatMaxMessageLength@RcsServiceManager@@QEAAJKPEAK@Z; RcsServiceManager::GetChatMaxMessageLength(ulong,ulong *)
0x1800fb10a  mov     r14d, eax
0x1800fb10d  test    eax, eax
0x1800fb10f  jns     short loc_1800FB096
0x1800fb111  mov     r9d, 0D3h
0x1800fb117  jmp     loc_1800FB1FB
0x1800fb11c  mov     dword ptr [rbp+arg_50], esi
0x1800fb122  lea     r9, [rbp+arg_18]; lpContext
0x1800fb126  mov     [rbp+arg_18], rsi
0x1800fb12a  lea     r8, [rbp+arg_50]; fPending
0x1800fb131  lea     rsi, stru_18015DCD8
0x1800fb138  xor     edx, edx; dwFlags
0x1800fb13a  mov     rcx, rsi; lpInitOnce
0x1800fb13d  call    cs:__imp_InitOnceBeginInitialize
0x1800fb143  mov     r14, [rbp+arg_18]
0x1800fb147  lea     rdi, qword_18015DCE0
0x1800fb14e  test    r14, r14
0x1800fb151  jnz     short loc_1800FB179
0x1800fb153  mov     rcx, rdi; this
0x1800fb156  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fb15b  mov     r8, rdi; lpContext
0x1800fb15e  mov     [rbp+fPending], r12
0x1800fb162  xor     edx, edx; dwFlags
0x1800fb164  mov     rcx, rsi; lpInitOnce
0x1800fb167  call    cs:__imp_InitOnceComplete
0x1800fb16d  lea     rcx, [rbp+fPending]
0x1800fb171  mov     r14, rdi
0x1800fb174  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800fb179  mov     edx, r13d; unsigned int
0x1800fb17c  mov     rcx, r14; this
0x1800fb17f  call    ?IsGroupChatSupported@RcsServiceManager@@QEAAHK@Z; RcsServiceManager::IsGroupChatSupported(ulong)
0x1800fb184  test    eax, eax
0x1800fb186  jz      loc_1800FB4B3
0x1800fb18c  lea     r9, [rbp+arg_18]; lpContext
0x1800fb190  mov     dword ptr [rbp+arg_50], r12d
0x1800fb197  lea     r8, [rbp+arg_50]; fPending
0x1800fb19e  mov     [rbp+arg_18], r12
0x1800fb1a2  xor     edx, edx; dwFlags
0x1800fb1a4  mov     rcx, rsi; lpInitOnce
0x1800fb1a7  call    cs:__imp_InitOnceBeginInitialize
0x1800fb1ad  mov     r14, [rbp+arg_18]
0x1800fb1b1  test    r14, r14
0x1800fb1b4  jnz     short loc_1800FB1DC
0x1800fb1b6  mov     rcx, rdi; this
0x1800fb1b9  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fb1be  mov     r8, rdi; lpContext
0x1800fb1c1  mov     [rbp+fPending], r12
0x1800fb1c5  xor     edx, edx; dwFlags
0x1800fb1c7  mov     rcx, rsi; lpInitOnce
0x1800fb1ca  call    cs:__imp_InitOnceComplete
0x1800fb1d0  lea     rcx, [rbp+fPending]
0x1800fb1d4  mov     r14, rdi
0x1800fb1d7  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800fb1dc  lea     r8, [rbp+arg_8]; unsigned int *
0x1800fb1e0  mov     edx, r13d; unsigned int
0x1800fb1e3  mov     rcx, r14; this
0x1800fb1e6  call    ?GetGroupChatMaxMessageLength@RcsServiceManager@@QEAAJKPEAK@Z; RcsServiceManager::GetGroupChatMaxMessageLength(ulong,ulong *)
0x1800fb1eb  mov     r14d, eax
0x1800fb1ee  xor     eax, eax
0x1800fb1f0  test    r14d, r14d
0x1800fb1f3  jns     short loc_1800FB20D
0x1800fb1f5  mov     r9d, 0AFh
0x1800fb1fb  mov     edx, ebx
0x1800fb1fd  mov     ecx, r14d
0x1800fb200  call    Log_HREvent_51
0x1800fb205  mov     eax, r14d
0x1800fb208  jmp     loc_1800FB4C2
0x1800fb20d  lea     r9, [rbp+arg_18]; lpContext
0x1800fb211  mov     dword ptr [rbp+arg_70], eax
0x1800fb217  lea     r8, [rbp+arg_50]; fPending
0x1800fb21e  mov     dword ptr [rbp+arg_50], eax
0x1800fb224  xor     edx, edx; dwFlags
0x1800fb226  mov     [rbp+arg_18], rax
0x1800fb22a  mov     rcx, rsi; lpInitOnce
0x1800fb22d  call    cs:__imp_InitOnceBeginInitialize
0x1800fb233  mov     r14, [rbp+arg_18]
0x1800fb237  test    r14, r14
0x1800fb23a  jnz     short loc_1800FB262
0x1800fb23c  mov     rcx, rdi; this
0x1800fb23f  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fb244  mov     r8, rdi; lpContext
0x1800fb247  mov     [rbp+fPending], r12
0x1800fb24b  xor     edx, edx; dwFlags
0x1800fb24d  mov     rcx, rsi; lpInitOnce
0x1800fb250  call    cs:__imp_InitOnceComplete
0x1800fb256  lea     rcx, [rbp+fPending]
0x1800fb25a  mov     r14, rdi
0x1800fb25d  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800fb262  lea     r8, [rbp+arg_70]; unsigned int *
0x1800fb269  mov     edx, r13d; unsigned int
0x1800fb26c  mov     rcx, r14; this
0x1800fb26f  call    ?GetMaxParticipants@RcsServiceManager@@QEAAJKPEAK@Z; RcsServiceManager::GetMaxParticipants(ulong,ulong *)
0x1800fb274  mov     r14d, eax
0x1800fb277  test    eax, eax
0x1800fb279  jns     short loc_1800FB286
0x1800fb27b  mov     r9d, 0B2h
0x1800fb281  jmp     loc_1800FB1FB
0x1800fb286  mov     eax, dword ptr [rbp+arg_70]
0x1800fb28c  dec     eax
0x1800fb28e  mov     [r15], eax
0x1800fb291  lea     r9, [rbp+arg_50]; lpContext
0x1800fb298  xor     r15d, r15d
0x1800fb29b  lea     r8, [rbp+arg_70]; fPending
0x1800fb2a2  xor     edx, edx; dwFlags
0x1800fb2a4  mov     dword ptr [rbp+arg_70], r15d
0x1800fb2ab  mov     rcx, rsi; lpInitOnce
0x1800fb2ae  mov     [rbp+arg_50], r15
0x1800fb2b5  call    cs:__imp_InitOnceBeginInitialize
0x1800fb2bb  mov     r14, [rbp+arg_50]
0x1800fb2c2  test    r14, r14
0x1800fb2c5  jnz     short loc_1800FB2ED
0x1800fb2c7  mov     rcx, rdi; this
0x1800fb2ca  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fb2cf  mov     r8, rdi; lpContext
0x1800fb2d2  mov     [rbp+arg_18], r15
0x1800fb2d6  xor     edx, edx; dwFlags
0x1800fb2d8  mov     rcx, rsi; lpInitOnce
0x1800fb2db  call    cs:__imp_InitOnceComplete
0x1800fb2e1  lea     rcx, [rbp+arg_18]
0x1800fb2e5  mov     r14, rdi
0x1800fb2e8  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800fb2ed  mov     edx, r13d; unsigned int
0x1800fb2f0  mov     rcx, r14; this
0x1800fb2f3  call    ?IsFileTransferSupported@RcsServiceManager@@QEAAHK@Z; RcsServiceManager::IsFileTransferSupported(ulong)
0x1800fb2f8  xor     ecx, ecx
0x1800fb2fa  xor     edx, edx; dwFlags
0x1800fb2fc  mov     r15d, eax
0x1800fb2ff  mov     dword ptr [rbp+arg_50], ecx
0x1800fb305  mov     dword ptr [rbp+arg_18], edx
0x1800fb308  cmp     dword ptr [rbp+arg_38], ecx
0x1800fb30b  jbe     short loc_1800FB324
0x1800fb30d  test    eax, eax
0x1800fb30f  jnz     short loc_1800FB35E
0x1800fb311  test    r12d, r12d
0x1800fb314  jz      loc_1800FB4B3
0x1800fb31a  mov     ecx, 0A00000h
0x1800fb31f  mov     edx, 900000h
0x1800fb324  xor     r12d, r12d
0x1800fb327  mov     rax, [rbp+arg_58]
0x1800fb32e  mov     [rax], ecx
0x1800fb330  mov     rax, [rbp+arg_60]
0x1800fb337  mov     rcx, [rbp+arg_48]
0x1800fb33e  mov     [rax], edx
0x1800fb340  mov     eax, [rbp+arg_8]
0x1800fb343  mov     [rcx], eax
0x1800fb345  mov     rax, [rbp+arg_68]
0x1800fb34c  mov     [rax], r15d
0x1800fb34f  mov     rax, [rbp+arg_78]
0x1800fb356  mov     [rax], r12d
0x1800fb359  jmp     loc_1800FB4C0
0x1800fb35e  xor     r12d, r12d
0x1800fb361  lea     r9, [rbp+Context]; lpContext
0x1800fb368  lea     r8, [rbp+fPending]; fPending
0x1800fb36c  mov     dword ptr [rbp+arg_70], r12d
  ... truncated ...
```
