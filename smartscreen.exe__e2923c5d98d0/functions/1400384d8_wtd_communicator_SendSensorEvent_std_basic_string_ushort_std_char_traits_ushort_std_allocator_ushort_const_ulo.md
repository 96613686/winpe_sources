# wtd_communicator::SendSensorEvent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x1400384d8`
- end: `0x14003884a`
- name: `?SendSensorEvent@wtd_communicator@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012f94`

## callees

- `0x140001008`
- `0x140001238`
- `0x1400013b0`
- `0x140001448`
- `0x1400014c4`
- `0x140006e8c`
- `0x140016ce4`
- `0x1400198d0`
- `0x140025aa0`
- `0x1400384d8`
- `0x140038850`
- `0x14004c318`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x140038743`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x140038743`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140038750`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140038750`
- `WTDSENSOR!WtdsFreeEvent` at `0x1400385a0`
- `WTDSENSOR!WtdsFreeEvent` at `0x140038657`
- `WTDSENSOR!WtdsFreeEvent` at `0x1400385a0`
- `WTDSENSOR!WtdsFreeEvent` at `0x140038657`
- `WTDSENSOR!WtdsAllocateEvent` at `0x1400385e0`
- `WTDSENSOR!WtdsAllocateEvent` at `0x1400385e0`
- `WTDSENSOR!WtdsGetEventData` at `0x140038666`
- `WTDSENSOR!WtdsGetEventData` at `0x140038666`
- `WTDSENSOR!WtdsGetProcessId` at `0x140038675`
- `WTDSENSOR!WtdsGetProcessId` at `0x1400387be`
- `WTDSENSOR!WtdsGetProcessId` at `0x140038675`
- `WTDSENSOR!WtdsGetProcessId` at `0x1400387be`
- `WTDSENSOR!WtdsSendEvent` at `0x1400386bc`
- `WTDSENSOR!WtdsSendEvent` at `0x1400387d6`
- `WTDSENSOR!WtdsSendEvent` at `0x1400386bc`
- `WTDSENSOR!WtdsSendEvent` at `0x1400387d6`

## string_xrefs

- `0x14003851f`: `onecore\amcore\smartscreen\src\client\urlrep\src\wtd_communicator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wtd_communicator::SendSensorEvent(__int64 a1, __int64 *a2, unsigned int a3)
{
  const unsigned __int16 *v4; // rsi
  _DWORD *v6; // r14
  int v7; // ebx
  std::_Mutex_base *v9; // rdi
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 EventData; // r13
  int ProcessId; // eax
  unsigned __int16 **v20; // r9
  bool v21; // cc
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  HWND ForegroundWindow; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // r8
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  unsigned __int64 *v40; // [rsp+20h] [rbp-60h]
  unsigned int v41; // [rsp+28h] [rbp-58h]
  const char *v42; // [rsp+40h] [rbp-40h] BYREF
  __int64 v43; // [rsp+48h] [rbp-38h] BYREF
  __int64 v44; // [rsp+50h] [rbp-30h] BYREF
  char v45; // [rsp+58h] [rbp-28h]
  __int64 v46; // [rsp+60h] [rbp-20h] BYREF
  DWORD dwProcessId; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v4 = (const unsigned __int16 *)a2;
  v6 = a2 + 2;
  if ( !a2[2] )
  {
    v7 = -2147020590;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\urlrep\\src\\wtd_communicator.cpp",
      (const char *)0x800710D2LL,
      (int)v40);
    return (unsigned int)v7;
  }
  v46 = 0;
  v44 = (__int64)&v46;
  v45 = 1;
  v9 = (std::_Mutex_base *)(a1 + 16);
  v43 = a1 + 16;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 16));
  v12 = *(_QWORD *)(a1 + 8);
  if ( !v12 )
  {
    if ( (unsigned int)dword_140084088 > 4 )
    {
      v44 = (__int64)"Null Handle - Sensor not registered";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        0,
        (unsigned int)&dword_140076EF4,
        v10,
        v11,
        (__int64)&v44);
    }
    goto LABEL_7;
  }
  v7 = WtdsAllocateEvent(v12, 0, (unsigned int)(2 * *v6 + 24), &v46);
  if ( v7 )
  {
    if ( (unsigned int)dword_140084088 > 2 && (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL, v14) )
    {
      v44 = 0x1000000;
      LODWORD(v42) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v15,
        (unsigned int)&dword_140076EBC,
        v16,
        v17,
        (__int64)&v42,
        (__int64)&v44);
    }
LABEL_14:
    if ( v7 <= 0 )
      goto LABEL_17;
    v7 = (unsigned __int16)v7;
    goto LABEL_16;
  }
  EventData = WtdsGetEventData(v46);
  ProcessId = WtdsGetProcessId(a3, EventData);
  v7 = ProcessId;
  v21 = ProcessId <= 0;
  if ( ProcessId )
  {
LABEL_20:
    if ( v21 )
    {
LABEL_17:
      std::_Mutex_base::unlock(v9);
      if ( v46 )
        WtdsFreeEvent();
      return (unsigned int)v7;
    }
    v7 = (unsigned __int16)ProcessId;
LABEL_16:
    v7 |= 0x80070000;
    goto LABEL_17;
  }
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const unsigned __int16 **)v4;
  if ( (unsigned int)StringCchCopyExW((unsigned __int16 *)(EventData + 20), *(_QWORD *)v6 + 1LL, v4, v20, v40, v41) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *(_DWORD *)(EventData + 16) = *v6;
  v22 = WtdsSendEvent(*(_QWORD *)(a1 + 8), v46);
  v7 = v22;
  if ( v22 && v22 != 995 )
  {
    if ( (unsigned int)dword_140084088 > 2 && (unsigned __int8)tlgKeywordOn(v23, 0x400000000000LL, v24) )
    {
      v44 = 0x1000000;
      v43 = (__int64)"Navigation";
      LODWORD(v42) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v25,
        (unsigned int)&byte_140076E7F,
        v26,
        v27,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&v44);
    }
    goto LABEL_14;
  }
  dwProcessId = 0;
  ForegroundWindow = GetForegroundWindow();
  GetWindowThreadProcessId(ForegroundWindow, &dwProcessId);
  if ( a3 != dwProcessId )
  {
    if ( (unsigned int)dword_140084088 > 2 && (unsigned __int8)tlgKeywordOn(v29, 0x400000000000LL, v30) )
    {
      v43 = 0x1000000;
      LODWORD(v42) = dwProcessId;
      LODWORD(v44) = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v31,
        (unsigned int)&unk_140076E28,
        v32,
        v33,
        (__int64)&v44,
        (__int64)&v42,
        (__int64)&v43);
    }
    ProcessId = WtdsGetProcessId(dwProcessId, EventData);
    v7 = ProcessId;
    v21 = ProcessId <= 0;
    if ( ProcessId )
      goto LABEL_20;
    v34 = WtdsSendEvent(*(_QWORD *)(a1 + 8), v46);
    v7 = v34;
    if ( v34 && v34 != 995 )
    {
      if ( (unsigned int)dword_140084088 > 2 && (unsigned __int8)tlgKeywordOn(v35, 0x400000000000LL, v36) )
      {
        v43 = 0x1000000;
        v42 = "Foreground";
        LODWORD(v44) = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v37,
          (unsigned int)byte_140076DEB,
          v38,
          v39,
          (__int64)&v44,
          (__int64)&v42,
          (__int64)&v43);
      }
      goto LABEL_14;
    }
  }
LABEL_7:
  std::_Mutex_base::unlock(v9);
  if ( v46 )
    WtdsFreeEvent();
  return 0;
}

```

## disassembly

```asm
0x1400384d8  mov     [rsp-38h+arg_18], rbx
0x1400384dd  push    rbp
0x1400384de  push    rsi
0x1400384df  push    rdi
0x1400384e0  push    r12
0x1400384e2  push    r13
0x1400384e4  push    r14
0x1400384e6  push    r15
0x1400384e8  mov     rbp, rsp
0x1400384eb  sub     rsp, 80h
0x1400384f2  mov     rax, cs:__security_cookie
0x1400384f9  xor     rax, rsp
0x1400384fc  mov     [rbp+var_10], rax
0x140038500  mov     r12d, r8d
0x140038503  mov     rsi, rdx
0x140038506  mov     r15, rcx
0x140038509  lea     r14, [rdx+10h]
0x14003850d  cmp     qword ptr [r14], 0
0x140038511  jnz     short loc_140038534
0x140038513  mov     rcx, [rbp+38h]; this
0x140038517  mov     ebx, 800710D2h
0x14003851c  mov     r9d, ebx; char *
0x14003851f  lea     r8, aOnecoreAmcoreS_1; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140038526  mov     edx, 75h ; 'u'; void *
0x14003852b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038530  mov     eax, ebx
0x140038532  jmp     short loc_1400385A8
0x140038534  mov     [rbp+var_20], 0
0x14003853c  lea     rax, [rbp+var_20]
0x140038540  mov     [rbp+var_30], rax
0x140038544  mov     [rbp+var_28], 1
0x140038548  lea     rdi, [rcx+10h]
0x14003854c  mov     [rbp+var_38], rdi
0x140038550  mov     rcx, rdi; this
0x140038553  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140038558  nop
0x140038559  mov     rcx, [r15+8]
0x14003855d  test    rcx, rcx
0x140038560  jnz     short loc_1400385CF
0x140038562  mov     eax, cs:dword_140084088
0x140038568  cmp     eax, 4
0x14003856b  jbe     short loc_14003858E
0x14003856d  lea     rax, aNullHandleSens; "Null Handle - Sensor not registered"
0x140038574  mov     [rbp+var_30], rax
0x140038578  lea     rax, [rbp+var_30]
0x14003857c  mov     [rsp+80h+var_60], rax
0x140038581  lea     rdx, dword_140076EF4
0x140038588  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14003858d  nop
0x14003858e  mov     rcx, rdi; this
0x140038591  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140038596  nop
0x140038597  mov     rcx, [rbp+var_20]
0x14003859b  test    rcx, rcx
0x14003859e  jz      short loc_1400385A6
0x1400385a0  call    cs:__imp_WtdsFreeEvent
0x1400385a6  xor     eax, eax
0x1400385a8  mov     rcx, [rbp+var_10]
0x1400385ac  xor     rcx, rsp; StackCookie
0x1400385af  call    __security_check_cookie
0x1400385b4  mov     rbx, [rsp+80h+arg_18]
0x1400385bc  add     rsp, 80h
0x1400385c3  pop     r15
0x1400385c5  pop     r14
0x1400385c7  pop     r13
0x1400385c9  pop     r12
0x1400385cb  pop     rdi
0x1400385cc  pop     rsi
0x1400385cd  pop     rbp
0x1400385ce  retn
0x1400385cf  mov     r8d, [r14]
0x1400385d2  lea     r8d, ds:18h[r8*2]
0x1400385da  xor     edx, edx
0x1400385dc  lea     r9, [rbp+var_20]
0x1400385e0  call    cs:__imp_WtdsAllocateEvent
0x1400385e6  mov     ebx, eax
0x1400385e8  test    eax, eax
0x1400385ea  jz      short loc_140038662
0x1400385ec  mov     eax, cs:dword_140084088
0x1400385f2  cmp     eax, 2
0x1400385f5  jbe     short loc_140038634
0x1400385f7  mov     rdx, 400000000000h
0x140038601  call    _tlgKeywordOn
0x140038606  test    al, al
0x140038608  jz      short loc_140038634
0x14003860a  mov     esi, 1000000h
0x14003860f  mov     [rbp+var_30], rsi
0x140038613  mov     dword ptr [rbp+var_40], ebx
0x140038616  lea     rax, [rbp+var_30]
0x14003861a  mov     [rsp+80h+var_58], rax
0x14003861f  lea     rax, [rbp+var_40]
0x140038623  mov     [rsp+80h+var_60], rax
0x140038628  lea     rdx, dword_140076EBC
0x14003862f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140038634  test    ebx, ebx
0x140038636  jle     short loc_140038641
0x140038638  movzx   ebx, bx
0x14003863b  or      ebx, 80070000h
0x140038641  mov     rcx, rdi; this
0x140038644  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140038649  nop
0x14003864a  mov     rcx, [rbp+var_20]
0x14003864e  test    rcx, rcx
0x140038651  jz      loc_140038530
0x140038657  call    cs:__imp_WtdsFreeEvent
0x14003865d  jmp     loc_140038530
0x140038662  mov     rcx, [rbp+var_20]
0x140038666  call    cs:__imp_WtdsGetEventData
0x14003866c  mov     r13, rax
0x14003866f  mov     rdx, rax
0x140038672  mov     ecx, r12d
0x140038675  call    cs:__imp_WtdsGetProcessId
0x14003867b  mov     ebx, eax
0x14003867d  test    eax, eax
0x14003867f  jz      short loc_140038688
0x140038681  jle     short loc_140038641
0x140038683  movzx   ebx, ax
0x140038686  jmp     short loc_14003863B
0x140038688  cmp     qword ptr [rsi+18h], 7
0x14003868d  jbe     short loc_140038692
0x14003868f  mov     rsi, [rsi]
0x140038692  mov     rdx, [r14]
0x140038695  inc     rdx; unsigned __int64
0x140038698  lea     rcx, [r13+14h]; unsigned __int16 *
0x14003869c  mov     r8, rsi; unsigned __int16 *
0x14003869f  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1400386a4  test    eax, eax
0x1400386a6  jz      short loc_1400386AD
0x1400386a8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1400386ad  mov     eax, [r14]
0x1400386b0  mov     [r13+10h], eax
0x1400386b4  mov     rdx, [rbp+var_20]
0x1400386b8  mov     rcx, [r15+8]
0x1400386bc  call    cs:__imp_WtdsSendEvent
0x1400386c2  mov     ebx, eax
0x1400386c4  mov     r14d, 3E3h
0x1400386ca  test    eax, eax
0x1400386cc  jz      short loc_14003873C
0x1400386ce  cmp     eax, r14d
0x1400386d1  jz      short loc_14003873C
0x1400386d3  mov     eax, cs:dword_140084088
0x1400386d9  cmp     eax, 2
0x1400386dc  jbe     loc_140038634
0x1400386e2  mov     rdx, 400000000000h
0x1400386ec  call    _tlgKeywordOn
0x1400386f1  test    al, al
0x1400386f3  jz      loc_140038634
0x1400386f9  mov     esi, 1000000h
0x1400386fe  mov     [rbp+var_30], rsi
0x140038702  lea     rax, aNavigation; "Navigation"
0x140038709  mov     [rbp+var_38], rax
0x14003870d  mov     dword ptr [rbp+var_40], ebx
0x140038710  lea     rax, [rbp+var_30]
0x140038714  mov     [rsp+80h+var_50], rax
0x140038719  lea     rax, [rbp+var_38]
0x14003871d  mov     [rsp+80h+var_58], rax
0x140038722  lea     rax, [rbp+var_40]
0x140038726  lea     rdx, byte_140076E7F
0x14003872d  mov     [rsp+80h+var_60], rax
0x140038732  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x140038737  jmp     loc_140038634
0x14003873c  mov     [rbp+dwProcessId], 0
0x140038743  call    cs:__imp_GetForegroundWindow
0x140038749  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x14003874d  mov     rcx, rax; hWnd
0x140038750  call    cs:__imp_GetWindowThreadProcessId
0x140038756  cmp     r12d, [rbp+dwProcessId]
0x14003875a  jz      loc_14003858E
0x140038760  mov     eax, cs:dword_140084088
0x140038766  mov     esi, 1000000h
0x14003876b  cmp     eax, 2
0x14003876e  jbe     short loc_1400387B8
0x140038770  mov     rdx, 400000000000h
0x14003877a  call    _tlgKeywordOn
0x14003877f  test    al, al
0x140038781  jz      short loc_1400387B8
0x140038783  mov     [rbp+var_38], rsi
0x140038787  mov     eax, [rbp+dwProcessId]
0x14003878a  mov     dword ptr [rbp+var_40], eax
0x14003878d  mov     dword ptr [rbp+var_30], r12d
0x140038791  lea     rax, [rbp+var_38]
0x140038795  mov     [rsp+80h+var_50], rax
0x14003879a  lea     rax, [rbp+var_40]
0x14003879e  mov     [rsp+80h+var_58], rax
0x1400387a3  lea     rax, [rbp+var_30]
0x1400387a7  mov     [rsp+80h+var_60], rax
0x1400387ac  lea     rdx, unk_140076E28
0x1400387b3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400387b8  mov     rdx, r13
0x1400387bb  mov     ecx, [rbp+dwProcessId]
0x1400387be  call    cs:__imp_WtdsGetProcessId
0x1400387c4  mov     ebx, eax
0x1400387c6  test    eax, eax
0x1400387c8  jnz     loc_140038681
0x1400387ce  mov     rdx, [rbp+var_20]
0x1400387d2  mov     rcx, [r15+8]
0x1400387d6  call    cs:__imp_WtdsSendEvent
0x1400387dc  mov     ebx, eax
0x1400387de  test    eax, eax
0x1400387e0  jz      loc_14003858E
0x1400387e6  cmp     eax, r14d
0x1400387e9  jz      loc_14003858E
0x1400387ef  mov     eax, cs:dword_140084088
0x1400387f5  cmp     eax, 2
0x1400387f8  jbe     loc_140038634
0x1400387fe  mov     rdx, 400000000000h
0x140038808  call    _tlgKeywordOn
0x14003880d  test    al, al
0x14003880f  jz      loc_140038634
0x140038815  mov     [rbp+var_38], rsi
0x140038819  lea     rax, aForeground; "Foreground"
0x140038820  mov     [rbp+var_40], rax
0x140038824  mov     dword ptr [rbp+var_30], ebx
0x140038827  lea     rax, [rbp+var_38]
0x14003882b  mov     [rsp+80h+var_50], rax
0x140038830  lea     rax, [rbp+var_40]
0x140038834  mov     [rsp+80h+var_58], rax
0x140038839  lea     rax, [rbp+var_30]
0x14003883d  lea     rdx, byte_140076DEB
0x140038844  jmp     loc_14003872D
```
