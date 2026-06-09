# WcmStartOnDemandRequest

- ea: `0x180013db0`
- end: `0x1800141fc`
- name: `WcmStartOnDemandRequest`
- size: `1100`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001ac8`
- `0x180002728`
- `0x180004450`
- `0x1800044b0`
- `0x180004d10`
- `0x180008a90`
- `0x18000953c`
- `0x18000d264`
- `0x18000e514`
- `0x1800111dc`
- `0x180013db0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f1e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014068`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014068`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013f05`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013f05`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180013fe2`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180013fe2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180014084`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180014084`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180013f67`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180013f67`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800140f4`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800140f4`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180013eb1`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180013eb1`

## pseudocode

```c
__int64 __fastcall WcmStartOnDemandRequest(__int64 a1)
{
  RPCNOTIFICATION_ROUTINE *EventW; // rdi
  WcmPolicyManager *v3; // rcx
  unsigned int LastError; // eax
  WcmPolicyManager *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  const char *v8; // rdx
  __int64 v9; // rcx
  __int64 v11; // [rsp+58h] [rbp-4E0h] BYREF
  GUID v12; // [rsp+60h] [rbp-4D8h]
  _QWORD *v13; // [rsp+70h] [rbp-4C8h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-4B8h] BYREF
  unsigned int Reply[4]; // [rsp+F0h] [rbp-448h] BYREF
  unsigned __int16 v16[264]; // [rsp+100h] [rbp-438h] BYREF
  WCHAR Filename[264]; // [rsp+310h] [rbp-228h] BYREF

  Reply[0] = 0;
  v13 = 0;
  memset_0(&pAsync, 0, sizeof(pAsync));
  EventW = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmStartOnDemandRequest");
    v3 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    LastError = HtReferenceHandleWithTag(g_hHandleTable, a1, 1129074260, 0, 1, &v13);
    Reply[0] = LastError;
    if ( LastError )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WcmPolicyManager *)&WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 25)
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_32;
      }
      v6 = 111;
    }
    else
    {
      EventW = (RPCNOTIFICATION_ROUTINE *)CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        LastError = RpcAsyncInitializeHandle(&pAsync, 0x70u);
        Reply[0] = LastError;
        if ( !LastError )
        {
          pAsync.NotificationType = RpcNotificationTypeEvent;
          pAsync.u.APC.NotificationRoutine = EventW;
          Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&stru_18001F060, 0xDu, 0, &pAsync, *v13);
          Reply[0] = ServiceStatus(Reply[0]);
          if ( Reply[0] )
            goto LABEL_32;
          WaitForSingleObjectEx(EventW, 0xFFFFFFFF, 0);
          RpcAsyncCompleteCall(&pAsync, Reply);
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WcmPolicyManager *)&WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_32;
          }
          v6 = 115;
          v7 = Reply[0];
LABEL_31:
          WPP_SF_D(*((_QWORD *)v5 + 2), v6, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids, v7);
          goto LABEL_32;
        }
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (WcmPolicyManager *)&WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 25)
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_32;
        }
        v6 = 113;
      }
      else
      {
        LastError = GetLastError();
        Reply[0] = LastError;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (WcmPolicyManager *)&WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 25)
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_32;
        }
        v6 = 112;
      }
    }
    v7 = LastError;
    goto LABEL_31;
  }
  Reply[0] = 6;
  if ( v3 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) && (*((_BYTE *)v3 + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)v3 + 2), 110, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids);
LABEL_32:
  if ( EventW )
    CloseHandle(EventW);
  if ( v13 )
    HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
  GetContextInfo(Filename, v16);
  if ( (unsigned int)dword_18002A000 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v9,
      byte_180024AC5);
  v11 = 4;
  v12 = GUID_NULL;
  NetworkingTriageScenario::OnDemand::OnDemandConnectionInitiatedAction(
    (const struct NetworkingTriageScenario::OnDemand::RequiredFields *)&v11,
    v8);
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmStartOnDemandRequest",
      Reply[0]);
  }
  return Reply[0];
}

```

## disassembly

```asm
0x180013db0  mov     [rsp+arg_8], rsi
0x180013db5  mov     [rsp+arg_10], rdi
0x180013dba  push    r14
0x180013dbc  sub     rsp, 530h
0x180013dc3  mov     rax, cs:__security_cookie
0x180013dca  xor     rax, rsp
0x180013dcd  mov     [rsp+538h+var_18], rax
0x180013dd5  mov     r14, rcx
0x180013dd8  mov     [rsp+538h+var_4F0], rcx
0x180013ddd  mov     [rsp+538h+Reply], 0
0x180013de8  mov     [rsp+538h+var_4C8], 0
0x180013df1  xor     edx, edx; Val
0x180013df3  lea     r8d, [rdx+70h]; Size
0x180013df7  lea     rcx, [rsp+538h+pAsync]; void *
0x180013dff  call    memset_0
0x180013e04  xor     edi, edi
0x180013e06  lea     rsi, WPP_GLOBAL_Control
0x180013e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e14  cmp     rcx, rsi
0x180013e17  jz      short loc_180013E46
0x180013e19  cmp     byte ptr [rcx+19h], 5
0x180013e1d  jb      short loc_180013E46
0x180013e1f  test    byte ptr [rcx+1Ch], 1
0x180013e23  jz      short loc_180013E46
0x180013e25  lea     edx, [rdi+6Dh]
0x180013e28  lea     r9, aWcmstartondema_0; "WcmStartOnDemandRequest"
0x180013e2f  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180013e36  mov     rcx, [rcx+10h]
0x180013e3a  call    WPP_SF_s
0x180013e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e46  test    r14, r14
0x180013e49  jnz     short loc_180013E8C
0x180013e4b  mov     [rsp+538h+Reply], 6
0x180013e56  cmp     rcx, rsi
0x180013e59  jz      loc_1800140C5
0x180013e5f  cmp     byte ptr [rcx+19h], 1
0x180013e63  jb      loc_1800140C5
0x180013e69  test    byte ptr [rcx+1Ch], 1
0x180013e6d  jz      loc_1800140C5
0x180013e73  lea     edx, [r14+6Eh]
0x180013e77  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180013e7e  mov     rcx, [rcx+10h]
0x180013e82  call    WPP_SF_
0x180013e87  jmp     loc_1800140C5
0x180013e8c  lea     rax, [rsp+538h+var_4C8]
0x180013e91  mov     [rsp+538h+var_510], rax
0x180013e96  mov     dword ptr [rsp+538h+var_518], 1
0x180013e9e  xor     r9d, r9d
0x180013ea1  mov     r8d, 434C4E54h
0x180013ea7  mov     rdx, r14
0x180013eaa  mov     rcx, cs:g_hHandleTable
0x180013eb1  call    cs:__imp_HtReferenceHandleWithTag
0x180013eb8  nop     dword ptr [rax+rax+00h]
0x180013ebd  mov     [rsp+538h+Reply], eax
0x180013ec4  test    eax, eax
0x180013ec6  jz      short loc_180013EF9
0x180013ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ecf  cmp     rcx, rsi
0x180013ed2  jz      loc_1800140C5
0x180013ed8  cmp     byte ptr [rcx+19h], 1
0x180013edc  jb      loc_1800140C5
0x180013ee2  test    byte ptr [rcx+1Ch], 1
0x180013ee6  jz      loc_1800140C5
0x180013eec  mov     edx, 6Fh ; 'o'
0x180013ef1  mov     r9d, eax
0x180013ef4  jmp     loc_1800140B5
0x180013ef9  xor     r9d, r9d; lpName
0x180013efc  xor     r8d, r8d; bInitialState
0x180013eff  lea     edx, [r9+1]; bManualReset
0x180013f03  xor     ecx, ecx; lpEventAttributes
0x180013f05  call    cs:__imp_CreateEventW
0x180013f0c  nop     dword ptr [rax+rax+00h]
0x180013f11  mov     rdi, rax
0x180013f14  mov     [rsp+538h+var_4F8], rax
0x180013f19  test    rax, rax
0x180013f1c  jnz     short loc_180013F5A
0x180013f1e  call    cs:__imp_GetLastError
0x180013f25  nop     dword ptr [rax+rax+00h]
0x180013f2a  mov     [rsp+538h+Reply], eax
0x180013f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f38  cmp     rcx, rsi
0x180013f3b  jz      loc_1800140C5
0x180013f41  cmp     byte ptr [rcx+19h], 1
0x180013f45  jb      loc_1800140C5
0x180013f4b  test    byte ptr [rcx+1Ch], 1
0x180013f4f  jz      loc_1800140C5
0x180013f55  lea     edx, [rdi+70h]
0x180013f58  jmp     short loc_180013EF1
0x180013f5a  mov     edx, 70h ; 'p'; Size
0x180013f5f  lea     rcx, [rsp+538h+pAsync]; pAsync
0x180013f67  call    cs:__imp_RpcAsyncInitializeHandle
0x180013f6e  nop     dword ptr [rax+rax+00h]
0x180013f73  mov     [rsp+538h+Reply], eax
0x180013f7a  test    eax, eax
0x180013f7c  jz      short loc_180013FAC
0x180013f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f85  cmp     rcx, rsi
0x180013f88  jz      loc_1800140C5
0x180013f8e  cmp     byte ptr [rcx+19h], 1
0x180013f92  jb      loc_1800140C5
0x180013f98  test    byte ptr [rcx+1Ch], 1
0x180013f9c  jz      loc_1800140C5
0x180013fa2  mov     edx, 71h ; 'q'
0x180013fa7  jmp     loc_180013EF1
0x180013fac  mov     [rsp+538h+pAsync.NotificationType], 1
0x180013fb7  mov     qword ptr [rsp+538h+pAsync.u], rdi
0x180013fbf  mov     rax, [rsp+538h+var_4C8]
0x180013fc4  mov     rcx, [rax]
0x180013fc7  mov     [rsp+538h+var_518], rcx
0x180013fcc  lea     r9, [rsp+538h+pAsync]
0x180013fd4  xor     r8d, r8d; pReturnValue
0x180013fd7  lea     edx, [r8+0Dh]; nProcNum
0x180013fdb  lea     rcx, stru_18001F060; pProxyInfo
0x180013fe2  call    cs:__imp_Ndr64AsyncClientCall
0x180013fe9  nop     dword ptr [rax+rax+00h]
0x180013fee  mov     eax, [rsp+538h+Reply]
0x180013ff5  jmp     short loc_18001404D
0x180013ff7  mov     [rsp+538h+Reply], eax
0x180013ffe  lea     rdx, WPP_GLOBAL_Control
0x180014005  mov     rcx, cs:WPP_GLOBAL_Control
0x18001400c  cmp     rcx, rdx
0x18001400f  jz      short loc_18001403C
0x180014011  cmp     byte ptr [rcx+19h], 1
0x180014015  jb      short loc_18001403C
0x180014017  test    byte ptr [rcx+1Ch], 1
0x18001401b  jz      short loc_18001403C
0x18001401d  mov     edx, 72h ; 'r'
0x180014022  mov     r9d, eax
0x180014025  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18001402c  mov     rcx, [rcx+10h]
0x180014030  call    WPP_SF_D
0x180014035  mov     eax, [rsp+538h+Reply]
0x18001403c  lea     rsi, WPP_GLOBAL_Control
0x180014043  mov     rdi, [rsp+538h+var_4F8]
0x180014048  mov     r14, [rsp+538h+var_4F0]
0x18001404d  mov     ecx, eax; unsigned int
0x18001404f  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180014054  mov     [rsp+538h+Reply], eax
0x18001405b  test    eax, eax
0x18001405d  jnz     short loc_1800140C5
0x18001405f  xor     r8d, r8d; bAlertable
0x180014062  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014065  mov     rcx, rdi; hHandle
0x180014068  call    cs:__imp_WaitForSingleObjectEx
0x18001406f  nop     dword ptr [rax+rax+00h]
0x180014074  lea     rdx, [rsp+538h+Reply]; Reply
0x18001407c  lea     rcx, [rsp+538h+pAsync]; pAsync
0x180014084  call    cs:__imp_RpcAsyncCompleteCall
0x18001408b  nop     dword ptr [rax+rax+00h]
0x180014090  mov     rcx, cs:WPP_GLOBAL_Control
0x180014097  cmp     rcx, rsi
0x18001409a  jz      short loc_1800140C5
0x18001409c  cmp     byte ptr [rcx+19h], 4
0x1800140a0  jb      short loc_1800140C5
0x1800140a2  test    byte ptr [rcx+1Ch], 1
0x1800140a6  jz      short loc_1800140C5
0x1800140a8  mov     edx, 73h ; 's'
0x1800140ad  mov     r9d, [rsp+538h+Reply]
0x1800140b5  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800140bc  mov     rcx, [rcx+10h]
0x1800140c0  call    WPP_SF_D
0x1800140c5  test    rdi, rdi
0x1800140c8  jz      short loc_1800140D9
0x1800140ca  mov     rcx, rdi; hObject
0x1800140cd  call    cs:__imp_CloseHandle
0x1800140d4  nop     dword ptr [rax+rax+00h]
0x1800140d9  cmp     [rsp+538h+var_4C8], 0
0x1800140df  jz      short loc_180014100
0x1800140e1  mov     r9d, 1
0x1800140e7  xor     r8d, r8d
0x1800140ea  mov     rdx, r14
0x1800140ed  mov     rcx, cs:g_hHandleTable
0x1800140f4  call    cs:__imp_HtDereferenceHandleWithTag
0x1800140fb  nop     dword ptr [rax+rax+00h]
0x180014100  lea     rdx, [rsp+538h+var_438]; unsigned __int16 *
0x180014108  lea     rcx, [rsp+538h+Filename]; lpFilename
0x180014110  call    ?GetContextInfo@@YAXPEAG0@Z; GetContextInfo(ushort *,ushort *)
0x180014115  mov     eax, cs:dword_18002A000
0x18001411b  cmp     eax, 5
0x18001411e  jbe     short loc_18001416F
0x180014120  lea     rax, [rsp+538h+var_438]
0x180014128  mov     [rsp+538h+var_4F0], rax
0x18001412d  lea     rax, [rsp+538h+Filename]
0x180014135  mov     [rsp+538h+var_4E8], rax
0x18001413a  mov     eax, [rsp+538h+Reply]
0x180014141  mov     dword ptr [rsp+538h+var_4F8], eax
0x180014145  lea     rax, [rsp+538h+var_4F0]
0x18001414a  mov     [rsp+538h+var_508], rax
0x18001414f  lea     rax, [rsp+538h+var_4E8]
0x180014154  mov     [rsp+538h+var_510], rax
0x180014159  lea     rax, [rsp+538h+var_4F8]
0x18001415e  mov     [rsp+538h+var_518], rax
0x180014163  lea     rdx, byte_180024AC5
0x18001416a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001416f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180014176  mov     [rsp+538h+var_4E0], 4
0x18001417f  movdqu  [rsp+538h+var_4D8], xmm0
0x180014185  lea     rcx, [rsp+538h+var_4E0]; struct NetworkingTriageScenario::OnDemand::RequiredFields *
0x18001418a  call    ?OnDemandConnectionInitiatedAction@OnDemand@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBD@Z; NetworkingTriageScenario::OnDemand::OnDemandConnectionInitiatedAction(NetworkingTriageScenario::OnDemand::RequiredFields const &,char const *)
0x18001418f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014196  cmp     rcx, rsi
0x180014199  jz      short loc_1800141CE
0x18001419b  cmp     byte ptr [rcx+19h], 5
0x18001419f  jb      short loc_1800141CE
0x1800141a1  test    byte ptr [rcx+1Ch], 1
0x1800141a5  jz      short loc_1800141CE
0x1800141a7  mov     edx, 74h ; 't'
0x1800141ac  mov     eax, [rsp+538h+Reply]
0x1800141b3  mov     dword ptr [rsp+538h+var_518], eax
0x1800141b7  lea     r9, aWcmstartondema_0; "WcmStartOnDemandRequest"
0x1800141be  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800141c5  mov     rcx, [rcx+10h]
0x1800141c9  call    WPP_SF_sL
0x1800141ce  mov     eax, [rsp+538h+Reply]
0x1800141d5  mov     rcx, [rsp+538h+var_18]
0x1800141dd  xor     rcx, rsp; StackCookie
0x1800141e0  call    __security_check_cookie
0x1800141e5  lea     r11, [rsp+538h+var_8]
0x1800141ed  mov     rsi, [r11+18h]
0x1800141f1  mov     rdi, [r11+20h]
0x1800141f5  mov     rsp, r11
0x1800141f8  pop     r14
0x1800141fa  retn
0x18001d219  push    rbp
0x18001d21b  sub     rsp, 40h
0x18001d21f  mov     rbp, rdx
0x18001d222  mov     rcx, [rcx]
0x18001d225  mov     ecx, [rcx]; ExceptionCode
0x18001d227  call    cs:__imp_RpcExceptionFilter
0x18001d22e  nop     dword ptr [rax+rax+00h]
0x18001d233  nop
0x18001d234  add     rsp, 40h
0x18001d238  pop     rbp
0x18001d239  retn
```
