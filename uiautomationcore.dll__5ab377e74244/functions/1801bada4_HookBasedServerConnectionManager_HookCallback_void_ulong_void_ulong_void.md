# HookBasedServerConnectionManager::HookCallback(void *,ulong,void * *,ulong *,void * *)

- ea: `0x1801bada4`
- end: `0x1801bb07f`
- name: `?HookCallback@HookBasedServerConnectionManager@@QEAAXPEAXKPEAPEAXPEAK1@Z`
- size: `731`
- prototype: `void __fastcall(HookBasedServerConnectionManager *__hidden this, void *, unsigned int, void **, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801e45d0`

## callees

- `0x18002ad08`
- `0x180052f8c`
- `0x1800546ac`
- `0x18006a860`
- `0x1800db428`
- `0x180117f30`
- `0x18011d2c8`
- `0x180130540`
- `0x18013055c`
- `0x180155230`
- `0x1801ad0e0`
- `0x1801bada4`
- `0x1801bb094`
- `0x1801e8320`
- `0x1801e887c`
- `0x1801ea7e0`
- `0x18022dec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801bae93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801bae93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801baf15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801bb04e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801baf15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801bb04e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801bae7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801bae7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801bafe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801bafe6`
- `ext-ms-win-ntuser-message-l1-1-2!ReplyMessage` at `0x1801baf8c`
- `ext-ms-win-ntuser-message-l1-1-2!ReplyMessage` at `0x1801baf8c`

## string_xrefs

- `0x1801baf4a`: `onecore\windows\accessibletech\uiautomationcore\hookbasedserverconnection.cpp`
- `0x1801bae5d`: `onecore\windows\accessibletech\common\basicmessagebuilderparser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall HookBasedServerConnectionManager::HookCallback(
        HookBasedServerConnectionManager *this,
        void *a2,
        int a3,
        void **a4,
        unsigned int *a5)
{
  int v6; // esi
  unsigned int v7; // edi
  DWORD CurrentThreadId; // r12d
  __int64 v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // r14d
  __int64 MethodId; // rdi
  char v14; // si
  __int64 v15; // rax
  unsigned __int64 v16; // rbx
  void *v17; // rax
  HookBasedServerConnection *v18; // rax
  struct HookBasedServerConnectionManager *v19; // rdx
  int v20; // [rsp+20h] [rbp-99h]
  const char *v21; // [rsp+28h] [rbp-91h]
  unsigned int v22[2]; // [rsp+30h] [rbp-89h] BYREF
  _QWORD v23[2]; // [rsp+38h] [rbp-81h] BYREF
  int v24; // [rsp+48h] [rbp-71h]
  __int64 v25; // [rsp+4Ch] [rbp-6Dh]
  unsigned int *v26; // [rsp+58h] [rbp-61h]
  _BYTE v27[16]; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v28; // [rsp+70h] [rbp-49h]
  char v29; // [rsp+88h] [rbp-31h]
  _QWORD v30[2]; // [rsp+90h] [rbp-29h] BYREF
  int v31; // [rsp+A0h] [rbp-19h]
  __int64 v32; // [rsp+B0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  v26 = a5;
  *a4 = 0;
  *a5 = 0;
  v23[1] = a2;
  v24 = a3;
  v25 = 0;
  v23[0] = &BasicMessageParser::`vftable';
  v22[0] = 0;
  if ( (int)BasicMessageParser::ReadItems<int>(v23, v22) >= 0 )
  {
    v6 = 0;
    v7 = v22[0];
    if ( !v22[0] )
    {
      if ( (int)BasicMessageParser::ReadItems<int>(v23, v22) < 0 )
        goto LABEL_34;
      if ( (_DWORD)v25 != v24 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\basicmessagebuilderparser.cpp",
          (const char *)0x80040800LL,
          (int)"unexpected leftover data after end of message",
          v21);
        goto LABEL_34;
      }
      v6 = 1;
      v7 = v22[0];
    }
    CurrentThreadId = GetCurrentThreadId();
    *(_QWORD *)v22 = &HookBasedServerConnectionManager::_classLock;
    EnterCriticalSection(&HookBasedServerConnectionManager::_classLock);
    v9 = g_TheHookBasedServerConnectionManager;
    if ( !g_TheHookBasedServerConnectionManager )
      goto LABEL_37;
    do
    {
      if ( *(_DWORD *)(v9 + 136) == v7 && *(_DWORD *)(v9 + 140) == CurrentThreadId )
        break;
      v9 = *(_QWORD *)(v9 + 120);
    }
    while ( v9 );
    if ( v9 )
    {
      if ( v6 )
      {
        v10 = *(_QWORD *)(v9 + 120);
        v11 = v9 + 128;
        if ( v10 )
          *(_QWORD *)(v10 + 128) = *(_QWORD *)v11;
        if ( *(_QWORD *)v11 )
          *(_QWORD *)(*(_QWORD *)v11 + 120LL) = *(_QWORD *)(v9 + 120);
        else
          g_TheHookBasedServerConnectionManager = *(_QWORD *)(v9 + 120);
        *(_QWORD *)v11 = 0;
        *(_QWORD *)(v9 + 120) = 0;
      }
      LeaveCriticalSection(&HookBasedServerConnectionManager::_classLock);
      if ( !v6 )
      {
        ProtobufHelper::Parse<UIAutomationCoreProto::UiaCoreRequestMsg>((UIAutomationCoreProto::UiaCoreRequestMsg *)v27);
        if ( v29 )
        {
          v12 = v28;
          MethodId = (unsigned int)ProtobufHelper::GetMethodId(v27);
          v14 = IsAsyncMethod(MethodId);
          if ( !v14 )
            ReplyMessage(1);
          v30[1] = 0;
          v32 = 0;
          v31 = 0;
          v30[0] = &UIAutomationCoreProto::UiaCoreResponseMsg::`vftable';
          v15 = wil::com_ptr_t<IRawElementProviderSimple,wil::err_exception_policy>::com_ptr_t<IRawElementProviderSimple,wil::err_exception_policy>(
                  v22,
                  v9);
          ProcessIncomingRequest(v27, v30, v15, v12, MethodId, 0);
          if ( !v14 )
          {
            v16 = UIAutomationCoreProto::UiaCoreResponseMsg::ByteSizeLong((UIAutomationCoreProto::UiaCoreResponseMsg *)v30);
            v17 = CoTaskMemAlloc(v16);
            *a4 = v17;
            if ( google::protobuf::MessageLite::SerializeToArray(
                   (google::protobuf::MessageLite *)v30,
                   (struct google::protobuf::MessageLite *)v17,
                   v16) )
            {
              if ( *a4 )
                *v26 = v16;
            }
          }
          UIAutomationCoreProto::UiaCoreResponseMsg::~UiaCoreResponseMsg((UIAutomationCoreProto::UiaCoreResponseMsg *)v30);
        }
        else
        {
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x14D,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\hookbasedserverconnection.cpp",
            (const char *)0x8000FFFFLL,
            v20);
        }
        std::optional<UIAutomationCoreProto::UiaCoreRequestMsg>::~optional<UIAutomationCoreProto::UiaCoreRequestMsg>(v27);
      }
    }
    else
    {
LABEL_37:
      if ( !v6 )
      {
        v18 = (HookBasedServerConnection *)operator new(0xF0u, (const struct std::nothrow_t *)std::nothrow);
        v26 = (unsigned int *)v18;
        if ( v18 )
          HookBasedServerConnection::HookBasedServerConnection(v18, v19, v7);
      }
      LeaveCriticalSection(&HookBasedServerConnectionManager::_classLock);
    }
  }
LABEL_34:
  BasicMessageParser::~BasicMessageParser((BasicMessageParser *)v23);
}

```

## disassembly

```asm
0x1801bada4  push    rbp
0x1801bada6  push    rbx
0x1801bada7  push    rsi
0x1801bada8  push    rdi
0x1801bada9  push    r12
0x1801badab  push    r13
0x1801badad  push    r14
0x1801badaf  push    r15
0x1801badb1  lea     rbp, [rsp-0Fh]
0x1801badb6  sub     rsp, 0C8h
0x1801badbd  mov     rax, cs:__security_cookie
0x1801badc4  xor     rax, rsp
0x1801badc7  mov     [rbp+47h+var_48], rax
0x1801badcb  mov     r13, r9
0x1801badce  mov     rax, [rbp+47h+arg_20]
0x1801badd2  mov     [rbp+47h+var_A8], rax
0x1801badd6  xor     ebx, ebx
0x1801badd8  mov     [r9], rbx
0x1801baddb  mov     [rax], ebx
0x1801baddd  mov     [rbp+47h+var_C0], rdx
0x1801bade1  mov     [rbp+47h+var_B8], r8d
0x1801bade5  mov     [rbp+47h+var_B4], rbx
0x1801bade9  lea     rax, ??_7BasicMessageParser@@6B@; const BasicMessageParser::`vftable'
0x1801badf0  mov     [rsp+100h+var_C8], rax
0x1801badf5  mov     [rsp+100h+var_D0], ebx
0x1801badf9  lea     rdx, [rsp+100h+var_D0]
0x1801badfe  lea     rcx, [rsp+100h+var_C8]
0x1801bae03  call    ??$ReadItems@H@BasicMessageParser@@QEAAJPEAHI@Z; BasicMessageParser::ReadItems<int>(int *,uint)
0x1801bae08  test    eax, eax
0x1801bae0a  js      loc_1801BB055
0x1801bae10  mov     esi, ebx
0x1801bae12  mov     edi, [rsp+100h+var_D0]
0x1801bae16  test    edi, edi
0x1801bae18  jnz     short loc_1801BAE73
0x1801bae1a  lea     rdx, [rsp+100h+var_D0]
0x1801bae1f  lea     rcx, [rsp+100h+var_C8]
0x1801bae24  call    ??$ReadItems@H@BasicMessageParser@@QEAAJPEAHI@Z; BasicMessageParser::ReadItems<int>(int *,uint)
0x1801bae29  test    eax, eax
0x1801bae2b  js      loc_1801BB055
0x1801bae31  mov     r15d, dword ptr [rbp+47h+var_B4]
0x1801bae35  mov     r14d, [rbp+47h+var_B8]
0x1801bae39  cmp     r15d, r14d
0x1801bae3c  jnz     short loc_1801BAE47
0x1801bae3e  lea     esi, [rbx+1]
0x1801bae41  mov     edi, [rsp+100h+var_D0]
0x1801bae45  jmp     short loc_1801BAE7B
0x1801bae47  mov     rcx, [rbp+4Fh]; this
0x1801bae4b  lea     rax, aUnexpectedLeft; "unexpected leftover data after end of m"...
0x1801bae52  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1801bae57  mov     r9d, 80040800h; char *
0x1801bae5d  lea     r8, aOnecoreWindows_49; "onecore\\windows\\accessibletech\\commo"...
0x1801bae64  mov     edx, 44h ; 'D'; void *
0x1801bae69  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801bae6e  jmp     loc_1801BB055
0x1801bae73  mov     r15d, dword ptr [rbp+47h+var_B4]
0x1801bae77  mov     r14d, [rbp+47h+var_B8]
0x1801bae7b  call    cs:__imp_GetCurrentThreadId
0x1801bae81  mov     r12d, eax
0x1801bae84  lea     rax, ?_classLock@HookBasedServerConnectionManager@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION HookBasedServerConnectionManager::_classLock
0x1801bae8b  mov     qword ptr [rsp+100h+var_D0], rax
0x1801bae90  mov     rcx, rax; lpCriticalSection
0x1801bae93  call    cs:__imp_EnterCriticalSection
0x1801bae99  nop
0x1801bae9a  mov     rbx, cs:?g_TheHookBasedServerConnectionManager@@3VHookBasedServerConnectionManager@@A; HookBasedServerConnectionManager g_TheHookBasedServerConnectionManager
0x1801baea1  test    rbx, rbx
0x1801baea4  jz      loc_1801BB01D
0x1801baeaa  cmp     [rbx+88h], edi
0x1801baeb0  jnz     short loc_1801BAEBB
0x1801baeb2  cmp     [rbx+8Ch], r12d
0x1801baeb9  jz      short loc_1801BAEC4
0x1801baebb  mov     rbx, [rbx+78h]
0x1801baebf  test    rbx, rbx
0x1801baec2  jnz     short loc_1801BAEAA
0x1801baec4  xor     r12d, r12d
0x1801baec7  test    rbx, rbx
0x1801baeca  jz      loc_1801BB01D
0x1801baed0  test    esi, esi
0x1801baed2  jz      short loc_1801BAF0E
0x1801baed4  mov     rdx, [rbx+78h]
0x1801baed8  lea     rcx, [rbx+80h]
0x1801baedf  test    rdx, rdx
0x1801baee2  jz      short loc_1801BAEEE
0x1801baee4  mov     rax, [rcx]
0x1801baee7  mov     [rdx+80h], rax
0x1801baeee  mov     rdx, [rcx]
0x1801baef1  mov     rax, [rbx+78h]
0x1801baef5  test    rdx, rdx
0x1801baef8  jz      short loc_1801BAF00
0x1801baefa  mov     [rdx+78h], rax
0x1801baefe  jmp     short loc_1801BAF07
0x1801baf00  mov     cs:?g_TheHookBasedServerConnectionManager@@3VHookBasedServerConnectionManager@@A, rax; HookBasedServerConnectionManager g_TheHookBasedServerConnectionManager
0x1801baf07  mov     [rcx], r12
0x1801baf0a  mov     [rbx+78h], r12
0x1801baf0e  lea     rcx, ?_classLock@HookBasedServerConnectionManager@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801baf15  call    cs:__imp_LeaveCriticalSection
0x1801baf1b  test    esi, esi
0x1801baf1d  jnz     loc_1801BB055
0x1801baf23  sub     r14d, r15d
0x1801baf26  mov     edx, r15d
0x1801baf29  add     rdx, [rbp+47h+var_C0]
0x1801baf2d  mov     r8d, r14d
0x1801baf30  lea     rcx, [rbp+47h+var_A0]; this
0x1801baf34  call    ??$Parse@VUiaCoreRequestMsg@UIAutomationCoreProto@@@ProtobufHelper@@SA?AV?$optional@VUiaCoreRequestMsg@UIAutomationCoreProto@@@std@@PEBEH@Z; ProtobufHelper::Parse<UIAutomationCoreProto::UiaCoreRequestMsg>(uchar const *,int)
0x1801baf39  nop
0x1801baf3a  cmp     [rbp+47h+var_78], r12b
0x1801baf3e  jnz     short loc_1801BAF6A
0x1801baf40  mov     rcx, [rbp+4Fh]; this
0x1801baf44  mov     r9d, 8000FFFFh; char *
0x1801baf4a  lea     r8, aOnecoreWindows_85; "onecore\\windows\\accessibletech\\uiaut"...
0x1801baf51  mov     edx, 14Dh; void *
0x1801baf56  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801baf5b  nop
0x1801baf5c  lea     rcx, [rbp+47h+var_A0]
0x1801baf60  call    ??1?$optional@VUiaCoreRequestMsg@UIAutomationCoreProto@@@std@@QEAA@XZ; std::optional<UIAutomationCoreProto::UiaCoreRequestMsg>::~optional<UIAutomationCoreProto::UiaCoreRequestMsg>(void)
0x1801baf65  jmp     loc_1801BB055
0x1801baf6a  mov     r14d, [rbp+47h+var_90]
0x1801baf6e  lea     rcx, [rbp+47h+var_A0]
0x1801baf72  call    ?GetMethodId@ProtobufHelper@@SA?AW4Protocol_MethodId@@AEBVUiaCoreRequestMsg@UIAutomationCoreProto@@@Z; ProtobufHelper::GetMethodId(UIAutomationCoreProto::UiaCoreRequestMsg const &)
0x1801baf77  mov     edi, eax
0x1801baf79  mov     ecx, eax
0x1801baf7b  call    ?IsAsyncMethod@@YA_NW4Protocol_MethodId@@@Z; IsAsyncMethod(Protocol_MethodId)
0x1801baf80  mov     sil, al
0x1801baf83  test    al, al
0x1801baf85  jnz     short loc_1801BAF92
0x1801baf87  mov     ecx, 1; lResult
0x1801baf8c  call    cs:__imp_ReplyMessage
0x1801baf92  mov     [rbp+47h+var_68], r12
0x1801baf96  mov     [rbp+47h+var_50], r12
0x1801baf9a  mov     [rbp+47h+var_60], r12d
0x1801baf9e  lea     rax, ??_7UiaCoreResponseMsg@UIAutomationCoreProto@@6B@; const UIAutomationCoreProto::UiaCoreResponseMsg::`vftable'
0x1801bafa5  mov     [rbp+47h+var_70], rax
0x1801bafa9  mov     rdx, rbx
0x1801bafac  lea     rcx, [rsp+100h+var_D0]
0x1801bafb1  call    ??0?$com_ptr_t@UIRawElementProviderSimple@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIRawElementProviderSimple@@@Z; wil::com_ptr_t<IRawElementProviderSimple,wil::err_exception_policy>::com_ptr_t<IRawElementProviderSimple,wil::err_exception_policy>(IRawElementProviderSimple *)
0x1801bafb6  mov     [rsp+100h+var_D8], r12
0x1801bafbb  mov     [rsp+100h+var_E0], edi
0x1801bafbf  mov     r9d, r14d
0x1801bafc2  mov     r8, rax
0x1801bafc5  lea     rdx, [rbp+47h+var_70]
0x1801bafc9  lea     rcx, [rbp+47h+var_A0]
0x1801bafcd  call    ?ProcessIncomingRequest@@YAJAEBVUiaCoreRequestMsg@UIAutomationCoreProto@@AEAVUiaCoreResponseMsg@2@V?$com_ptr_t@VIServerConnection@@Uerr_exception_policy@wil@@@wil@@IW4Protocol_MethodId@@PEAVReleaseCollection@@@Z; ProcessIncomingRequest(UIAutomationCoreProto::UiaCoreRequestMsg const &,UIAutomationCoreProto::UiaCoreResponseMsg &,wil::com_ptr_t<IServerConnection,wil::err_exception_policy>,uint,Protocol_MethodId,ReleaseCollection *)
0x1801bafd2  test    sil, sil
0x1801bafd5  jnz     short loc_1801BB00F
0x1801bafd7  lea     rcx, [rbp+47h+var_70]; this
0x1801bafdb  call    ?ByteSizeLong@UiaCoreResponseMsg@UIAutomationCoreProto@@UEBA_KXZ; UIAutomationCoreProto::UiaCoreResponseMsg::ByteSizeLong(void)
0x1801bafe0  mov     rbx, rax
0x1801bafe3  mov     rcx, rax; cb
0x1801bafe6  call    cs:__imp_CoTaskMemAlloc
0x1801bafec  mov     [r13+0], rax
0x1801baff0  mov     r8d, ebx; int
0x1801baff3  mov     rdx, rax; struct google::protobuf::MessageLite *
0x1801baff6  lea     rcx, [rbp+47h+var_70]; this
0x1801baffa  call    ?SerializeToArray@MessageLite@protobuf@google@@QEBA_NPEAXH@Z; google::protobuf::MessageLite::SerializeToArray(void *,int)
0x1801bafff  test    al, al
0x1801bb001  jz      short loc_1801BB00F
0x1801bb003  cmp     [r13+0], r12
0x1801bb007  jz      short loc_1801BB00F
0x1801bb009  mov     rax, [rbp+47h+var_A8]
0x1801bb00d  mov     [rax], ebx
0x1801bb00f  lea     rcx, [rbp+47h+var_70]; this
0x1801bb013  call    ??1UiaCoreResponseMsg@UIAutomationCoreProto@@UEAA@XZ; UIAutomationCoreProto::UiaCoreResponseMsg::~UiaCoreResponseMsg(void)
0x1801bb018  jmp     loc_1801BAF5C
0x1801bb01d  test    esi, esi
0x1801bb01f  jnz     short loc_1801BB047
0x1801bb021  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801bb028  mov     ecx, 0F0h; unsigned __int64
0x1801bb02d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801bb032  mov     [rbp+47h+var_A8], rax
0x1801bb036  test    rax, rax
0x1801bb039  jz      short loc_1801BB047
0x1801bb03b  mov     r8d, edi; unsigned int
0x1801bb03e  mov     rcx, rax; this
0x1801bb041  call    ??0HookBasedServerConnection@@QEAA@PEAVHookBasedServerConnectionManager@@K@Z; HookBasedServerConnection::HookBasedServerConnection(HookBasedServerConnectionManager *,ulong)
0x1801bb047  lea     rcx, ?_classLock@HookBasedServerConnectionManager@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801bb04e  call    cs:__imp_LeaveCriticalSection
0x1801bb054  nop
0x1801bb055  lea     rcx, [rsp+100h+var_C8]; this
0x1801bb05a  call    ??1BasicMessageParser@@UEAA@XZ; BasicMessageParser::~BasicMessageParser(void)
0x1801bb05f  mov     rcx, [rbp+47h+var_48]
0x1801bb063  xor     rcx, rsp; StackCookie
0x1801bb066  call    __security_check_cookie
0x1801bb06b  add     rsp, 0C8h
0x1801bb072  pop     r15
0x1801bb074  pop     r14
0x1801bb076  pop     r13
0x1801bb078  pop     r12
0x1801bb07a  pop     rdi
0x1801bb07b  pop     rsi
0x1801bb07c  pop     rbx
0x1801bb07d  pop     rbp
0x1801bb07e  retn
```
