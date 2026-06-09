# ChatOperationContext::SendLocalParticipantComposing(ushort const *,UdmObjectId,ushort const *,int)

- ea: `0x1800d4018`
- end: `0x1800d43b0`
- name: `?SendLocalParticipantComposing@ChatOperationContext@@QEAAJPEBGUUdmObjectId@@0H@Z`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18011d640`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x18003cda4`
- `0x18003e470`
- `0x18003ed7c`
- `0x18006db44`
- `0x180072ccc`
- `0x1800ca968`
- `0x1800d4018`
- `0x1800d7160`
- `0x1800ef8a0`
- `0x18012e010`

## import_xrefs

- `MessagingDataModel2!Messaging_IsThreadedByRemoteConversationId` at `0x1800d4176`
- `MessagingDataModel2!Messaging_IsThreadedByRemoteConversationId` at `0x1800d4176`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800d4229`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800d4344`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800d4229`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800d4344`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800d41fb`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800d4316`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800d41fb`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800d4316`

## string_xrefs

- `0x1800d4055`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d40db`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d4132`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d41c3`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x1800d42a8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`

## pseudocode

```c
__int64 __fastcall ChatOperationContext::SendLocalParticipantComposing(
        ChatOperationContext *a1,
        const unsigned __int16 *a2,
        const struct UdmObjectId *a3,
        const unsigned __int16 *a4,
        int a5)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // r9
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  struct ISmConversation *v16; // rdi
  __int64 (__fastcall *v17)(struct ISmConversation *, _QWORD *); // rbx
  _QWORD *v18; // rax
  int v19; // eax
  __int64 v20; // r9
  __int64 *v21; // rbx
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 *v26; // rbx
  WINBOOL fPending; // [rsp+30h] [rbp-51h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-49h] BYREF
  WINBOOL v30[2]; // [rsp+40h] [rbp-41h] BYREF
  unsigned int v31; // [rsp+48h] [rbp-39h] BYREF
  unsigned int v32; // [rsp+4Ch] [rbp-35h] BYREF
  struct ISmConversation *v33; // [rsp+50h] [rbp-31h] BYREF
  LPVOID v34; // [rsp+58h] [rbp-29h] BYREF
  _QWORD v35[4]; // [rsp+60h] [rbp-21h] BYREF
  __int64 v36; // [rsp+80h] [rbp-1h] BYREF
  _QWORD v37[9]; // [rsp+88h] [rbp+7h] BYREF

  v8 = ChatTransportStringToId(a2);
  v31 = v8;
  if ( !v8 || v8 - 101 <= 0x63 )
  {
    v33 = 0;
    v10 = ChatOperationContext::_OpenConversationById(a1, a3, 1u, &v31, v30, &v33);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = 2564;
LABEL_8:
      Log_HREvent(
        (unsigned int)v10,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        v11);
LABEL_41:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v33);
      return v9;
    }
    v32 = 0;
    v36 = 0;
    v10 = (*(__int64 (__fastcall **)(struct ISmConversation *, unsigned int *, __int64 *))(*(_QWORD *)v33 + 240LL))(
            v33,
            &v32,
            &v36);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = 2568;
      goto LABEL_8;
    }
    v37[0] = v32;
    v37[1] = v36;
    fPending = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v35);
    v12 = ParseThreadingInfo(v37, &fPending, v35);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 2576;
      v14 = 1;
      v15 = (unsigned int)v12;
LABEL_11:
      Log_HREvent(
        v15,
        v14,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        v13);
LABEL_12:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
      goto LABEL_41;
    }
    if ( (unsigned int)fPending >= 2 )
    {
      if ( fPending != 3 )
      {
        v13 = 2614;
        goto LABEL_17;
      }
      if ( !(unsigned int)Messaging_IsThreadedByRemoteConversationId(v35[0]) )
      {
        v13 = 2603;
LABEL_17:
        v9 = -2147024809;
        v14 = 0;
        v15 = 2147942487LL;
        goto LABEL_11;
      }
      v16 = v33;
      *(_QWORD *)v30 = 0;
      v17 = *(__int64 (__fastcall **)(struct ISmConversation *, _QWORD *))(*(_QWORD *)v33 + 64LL);
      v18 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(v30);
      v19 = v17(v16, v18);
      v9 = v19;
      if ( v19 < 0 )
      {
        v20 = 2606;
LABEL_20:
        Log_HREvent(
          (unsigned int)v19,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
          v20);
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(v30);
        goto LABEL_12;
      }
      fPending = 0;
      Context = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
      v21 = (__int64 *)Context;
      if ( !Context )
      {
        v21 = qword_18015DCE0;
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        v34 = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v34);
      }
      v19 = RcsComposingStatusTracker::SendLocalUserComposingStatus(
              (RcsComposingStatusTracker *)(v21 + 52),
              v31,
              *(const unsigned __int16 **)v30,
              1,
              a5);
      v9 = v19;
      if ( v19 < 0 )
      {
        v20 = 2608;
        goto LABEL_20;
      }
      tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(v30);
LABEL_40:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
      v9 = 0;
      goto LABEL_41;
    }
    Context = 0;
    v22 = (*(__int64 (__fastcall **)(struct ISmConversation *, LPVOID *))(*(_QWORD *)v33 + 40LL))(v33, &Context);
    v9 = v22;
    if ( v22 >= 0 )
    {
      fPending = 0;
      v22 = (*(__int64 (__fastcall **)(LPVOID, WINBOOL *))(*(_QWORD *)Context + 56LL))(Context, &fPending);
      v9 = v22;
      if ( v22 >= 0 )
      {
        v24 = 0;
        if ( fPending != 1 )
        {
          v9 = -2147024809;
          v23 = 2591;
          v25 = 2147942487LL;
          goto LABEL_30;
        }
        v30[0] = 0;
        v34 = 0;
        InitOnceBeginInitialize(&stru_18015DCD8, 0, v30, &v34);
        v26 = (__int64 *)v34;
        if ( !v34 )
        {
          v26 = qword_18015DCE0;
          RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
          v37[0] = 0;
          InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(v37);
        }
        v22 = RcsComposingStatusTracker::SendLocalUserComposingStatus(
                (RcsComposingStatusTracker *)(v26 + 52),
                v31,
                a4,
                0,
                a5);
        v9 = v22;
        if ( v22 >= 0 )
        {
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&Context);
          goto LABEL_40;
        }
        v23 = 2596;
      }
      else
      {
        v23 = 2589;
      }
    }
    else
    {
      v23 = 2586;
    }
    v24 = 1;
    v25 = (unsigned int)v22;
LABEL_30:
    Log_HREvent(
      v25,
      v24,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
      v23);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&Context);
    goto LABEL_12;
  }
  v9 = -2147024809;
  Log_HREvent(
    2147942487LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
    2558);
  return v9;
}

```

## disassembly

```asm
0x1800d4018  push    rbp
0x1800d401a  push    rbx
0x1800d401b  push    rsi
0x1800d401c  push    rdi
0x1800d401d  push    r14
0x1800d401f  push    r15
0x1800d4021  lea     rbp, [rsp-27h]
0x1800d4026  sub     rsp, 0A8h
0x1800d402d  mov     rbx, rcx
0x1800d4030  mov     rsi, r9
0x1800d4033  mov     rcx, rdx; unsigned __int16 *
0x1800d4036  mov     rdi, r8
0x1800d4039  call    ?ChatTransportStringToId@@YAKPEBG@Z; ChatTransportStringToId(ushort const *)
0x1800d403e  xor     r14d, r14d
0x1800d4041  mov     [rbp+4Fh+var_88], eax
0x1800d4044  test    eax, eax
0x1800d4046  jz      short loc_1800D4070
0x1800d4048  add     eax, 0FFFFFF9Bh
0x1800d404b  cmp     eax, 63h ; 'c'
0x1800d404e  jbe     short loc_1800D4070
0x1800d4050  mov     ebx, 80070057h
0x1800d4055  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d405c  mov     ecx, ebx
0x1800d405e  mov     r9d, 9FEh
0x1800d4064  xor     edx, edx
0x1800d4066  call    Log_HREvent
0x1800d406b  jmp     loc_1800D439E
0x1800d4070  lea     rax, [rbp+4Fh+var_80]
0x1800d4074  mov     [rbp+4Fh+var_80], r14
0x1800d4078  mov     [rsp+0D0h+var_A8], rax; struct ISmConversation **
0x1800d407d  lea     r9, [rbp+4Fh+var_88]; unsigned int *
0x1800d4081  lea     rax, [rbp+4Fh+var_90]
0x1800d4085  mov     r15d, 1
0x1800d408b  mov     r8d, r15d; unsigned int
0x1800d408e  mov     [rsp+0D0h+var_B0], rax; int *
0x1800d4093  mov     rdx, rdi; struct UdmObjectId *
0x1800d4096  mov     rcx, rbx; this
0x1800d4099  call    ?_OpenConversationById@ChatOperationContext@@AEAAJAEBUUdmObjectId@@KPEBKPEAHPEAPEAUISmConversation@@@Z; ChatOperationContext::_OpenConversationById(UdmObjectId const &,ulong,ulong const *,int *,ISmConversation * *)
0x1800d409e  mov     ebx, eax
0x1800d40a0  test    eax, eax
0x1800d40a2  jns     short loc_1800D40AC
0x1800d40a4  mov     r9d, 0A04h
0x1800d40aa  jmp     short loc_1800D40DB
0x1800d40ac  mov     rcx, [rbp+4Fh+var_80]
0x1800d40b0  lea     r8, [rbp+4Fh+var_50]
0x1800d40b4  mov     [rbp+4Fh+var_84], r14d
0x1800d40b8  lea     rdx, [rbp+4Fh+var_84]
0x1800d40bc  mov     [rbp+4Fh+var_50], r14
0x1800d40c0  mov     rax, [rcx]
0x1800d40c3  mov     rax, [rax+0F0h]
0x1800d40ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d40cf  mov     ebx, eax
0x1800d40d1  test    eax, eax
0x1800d40d3  jns     short loc_1800D40F1
0x1800d40d5  mov     r9d, 0A08h
0x1800d40db  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d40e2  mov     edx, r15d
0x1800d40e5  mov     ecx, eax
0x1800d40e7  call    Log_HREvent
0x1800d40ec  jmp     loc_1800D4395
0x1800d40f1  mov     eax, [rbp+4Fh+var_84]
0x1800d40f4  lea     rcx, [rbp+4Fh+var_70]; void *
0x1800d40f8  mov     dword ptr [rbp+4Fh+var_48], eax
0x1800d40fb  mov     rax, [rbp+4Fh+var_50]
0x1800d40ff  mov     [rbp+4Fh+var_40], rax
0x1800d4103  mov     dword ptr [rbp+4Fh+var_48+4], r14d
0x1800d4107  mov     [rbp+4Fh+fPending], r14d
0x1800d410b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800d4110  lea     r8, [rbp+4Fh+var_70]
0x1800d4114  lea     rdx, [rbp+4Fh+fPending]
0x1800d4118  lea     rcx, [rbp+4Fh+var_48]
0x1800d411c  call    ?ParseThreadingInfo@@YAJAEBU_SQLCEBLOB@@PEAKPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ParseThreadingInfo(_SQLCEBLOB const &,ulong *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x1800d4121  mov     ebx, eax
0x1800d4123  test    eax, eax
0x1800d4125  jns     short loc_1800D414C
0x1800d4127  mov     r9d, 0A10h
0x1800d412d  mov     edx, r15d
0x1800d4130  mov     ecx, eax
0x1800d4132  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d4139  call    Log_HREvent
0x1800d413e  lea     rcx, [rbp+4Fh+var_70]; void *
0x1800d4142  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d4147  jmp     loc_1800D4395
0x1800d414c  mov     eax, [rbp+4Fh+fPending]
0x1800d414f  test    eax, eax
0x1800d4151  jz      loc_1800D427F
0x1800d4157  sub     eax, r15d
0x1800d415a  jz      loc_1800D427F
0x1800d4160  sub     eax, r15d
0x1800d4163  jz      loc_1800D4274
0x1800d4169  cmp     eax, r15d
0x1800d416c  jnz     loc_1800D4274
0x1800d4172  mov     rcx, [rbp+4Fh+var_70]
0x1800d4176  call    cs:__imp_Messaging_IsThreadedByRemoteConversationId
0x1800d417c  test    eax, eax
0x1800d417e  jnz     short loc_1800D4191
0x1800d4180  mov     r9d, 0A2Bh
0x1800d4186  mov     ebx, 80070057h
0x1800d418b  xor     edx, edx
0x1800d418d  mov     ecx, ebx
0x1800d418f  jmp     short loc_1800D4132
0x1800d4191  mov     rdi, [rbp+4Fh+var_80]
0x1800d4195  lea     rcx, [rbp+4Fh+var_90]
0x1800d4199  mov     qword ptr [rbp+4Fh+var_90], r14
0x1800d419d  mov     rax, [rdi]
0x1800d41a0  mov     rbx, [rax+40h]
0x1800d41a4  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x1800d41a9  mov     rdx, rax
0x1800d41ac  mov     rcx, rdi
0x1800d41af  mov     rax, rbx
0x1800d41b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d41b7  mov     ebx, eax
0x1800d41b9  test    eax, eax
0x1800d41bb  jns     short loc_1800D41E2
0x1800d41bd  mov     r9d, 0A2Eh
0x1800d41c3  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d41ca  mov     edx, r15d
0x1800d41cd  mov     ecx, eax
0x1800d41cf  call    Log_HREvent
0x1800d41d4  lea     rcx, [rbp+4Fh+var_90]
0x1800d41d8  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800d41dd  jmp     loc_1800D413E
0x1800d41e2  lea     r9, [rbp+4Fh+Context]; lpContext
0x1800d41e6  mov     [rbp+4Fh+fPending], r14d
0x1800d41ea  lea     r8, [rbp+4Fh+fPending]; fPending
0x1800d41ee  mov     [rbp+4Fh+Context], r14
0x1800d41f2  xor     edx, edx; dwFlags
0x1800d41f4  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800d41fb  call    cs:__imp_InitOnceBeginInitialize
0x1800d4201  mov     rbx, [rbp+4Fh+Context]
0x1800d4205  test    rbx, rbx
0x1800d4208  jnz     short loc_1800D4238
0x1800d420a  lea     rbx, qword_18015DCE0
0x1800d4211  mov     rcx, rbx; this
0x1800d4214  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800d4219  mov     r8, rbx; lpContext
0x1800d421c  mov     [rbp+4Fh+var_78], r14
0x1800d4220  xor     edx, edx; dwFlags
0x1800d4222  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800d4229  call    cs:__imp_InitOnceComplete
0x1800d422f  lea     rcx, [rbp+4Fh+var_78]
0x1800d4233  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800d4238  mov     eax, [rbp+4Fh+arg_20]
0x1800d423b  lea     rcx, [rbx+1A0h]; this
0x1800d4242  mov     r8, qword ptr [rbp+4Fh+var_90]; unsigned __int16 *
0x1800d4246  mov     r9d, r15d; int
0x1800d4249  mov     edx, [rbp+4Fh+var_88]; unsigned int
0x1800d424c  mov     dword ptr [rsp+0D0h+var_B0], eax; int
0x1800d4250  call    ?SendLocalUserComposingStatus@RcsComposingStatusTracker@@QEAAJKPEBGHH@Z; RcsComposingStatusTracker::SendLocalUserComposingStatus(ulong,ushort const *,int,int)
0x1800d4255  mov     ebx, eax
0x1800d4257  test    eax, eax
0x1800d4259  jns     short loc_1800D4266
0x1800d425b  mov     r9d, 0A30h
0x1800d4261  jmp     loc_1800D41C3
0x1800d4266  lea     rcx, [rbp+4Fh+var_90]
0x1800d426a  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x1800d426f  jmp     loc_1800D4389
0x1800d4274  mov     r9d, 0A36h
0x1800d427a  jmp     loc_1800D4186
0x1800d427f  mov     rcx, [rbp+4Fh+var_80]
0x1800d4283  lea     rdx, [rbp+4Fh+Context]
0x1800d4287  mov     [rbp+4Fh+Context], r14
0x1800d428b  mov     rax, [rcx]
0x1800d428e  mov     rax, [rax+28h]
0x1800d4292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4297  mov     ebx, eax
0x1800d4299  test    eax, eax
0x1800d429b  jns     short loc_1800D42C2
0x1800d429d  mov     r9d, 0A1Ah
0x1800d42a3  mov     edx, r15d
0x1800d42a6  mov     ecx, eax
0x1800d42a8  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800d42af  call    Log_HREvent
0x1800d42b4  lea     rcx, [rbp+4Fh+Context]
0x1800d42b8  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d42bd  jmp     loc_1800D413E
0x1800d42c2  mov     rcx, [rbp+4Fh+Context]
0x1800d42c6  lea     rdx, [rbp+4Fh+fPending]
0x1800d42ca  mov     [rbp+4Fh+fPending], r14d
0x1800d42ce  mov     rax, [rcx]
0x1800d42d1  mov     rax, [rax+38h]
0x1800d42d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d42da  mov     ebx, eax
0x1800d42dc  test    eax, eax
0x1800d42de  jns     short loc_1800D42E8
0x1800d42e0  mov     r9d, 0A1Dh
0x1800d42e6  jmp     short loc_1800D42A3
0x1800d42e8  xor     edx, edx; dwFlags
0x1800d42ea  cmp     [rbp+4Fh+fPending], r15d
0x1800d42ee  jz      short loc_1800D42FF
0x1800d42f0  mov     ebx, 80070057h
0x1800d42f5  mov     r9d, 0A1Fh
0x1800d42fb  mov     ecx, ebx
0x1800d42fd  jmp     short loc_1800D42A8
0x1800d42ff  lea     r9, [rbp+4Fh+var_78]; lpContext
0x1800d4303  mov     [rbp+4Fh+var_90], r14d
0x1800d4307  lea     r8, [rbp+4Fh+var_90]; fPending
0x1800d430b  mov     [rbp+4Fh+var_78], r14
0x1800d430f  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800d4316  call    cs:__imp_InitOnceBeginInitialize
0x1800d431c  mov     rbx, [rbp+4Fh+var_78]
0x1800d4320  test    rbx, rbx
0x1800d4323  jnz     short loc_1800D4353
0x1800d4325  lea     rbx, qword_18015DCE0
0x1800d432c  mov     rcx, rbx; this
0x1800d432f  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800d4334  mov     r8, rbx; lpContext
0x1800d4337  mov     [rbp+4Fh+var_48], r14
0x1800d433b  xor     edx, edx; dwFlags
0x1800d433d  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800d4344  call    cs:__imp_InitOnceComplete
0x1800d434a  lea     rcx, [rbp+4Fh+var_48]
0x1800d434e  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800d4353  mov     eax, [rbp+4Fh+arg_20]
0x1800d4356  lea     rcx, [rbx+1A0h]; this
0x1800d435d  mov     edx, [rbp+4Fh+var_88]; unsigned int
0x1800d4360  xor     r9d, r9d; int
0x1800d4363  mov     r8, rsi; unsigned __int16 *
0x1800d4366  mov     dword ptr [rsp+0D0h+var_B0], eax; int
0x1800d436a  call    ?SendLocalUserComposingStatus@RcsComposingStatusTracker@@QEAAJKPEBGHH@Z; RcsComposingStatusTracker::SendLocalUserComposingStatus(ulong,ushort const *,int,int)
0x1800d436f  mov     ebx, eax
0x1800d4371  test    eax, eax
0x1800d4373  jns     short loc_1800D4380
0x1800d4375  mov     r9d, 0A24h
0x1800d437b  jmp     loc_1800D42A3
0x1800d4380  lea     rcx, [rbp+4Fh+Context]
0x1800d4384  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d4389  lea     rcx, [rbp+4Fh+var_70]; void *
0x1800d438d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d4392  mov     ebx, r14d
0x1800d4395  lea     rcx, [rbp+4Fh+var_80]
0x1800d4399  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800d439e  mov     eax, ebx
0x1800d43a0  add     rsp, 0A8h
0x1800d43a7  pop     r15
0x1800d43a9  pop     r14
0x1800d43ab  pop     rdi
0x1800d43ac  pop     rsi
0x1800d43ad  pop     rbx
0x1800d43ae  pop     rbp
0x1800d43af  retn
```
