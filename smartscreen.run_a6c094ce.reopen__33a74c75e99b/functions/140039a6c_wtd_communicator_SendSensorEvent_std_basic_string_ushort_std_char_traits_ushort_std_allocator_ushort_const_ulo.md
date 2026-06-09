# wtd_communicator::SendSensorEvent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x140039a6c`
- end: `0x140039e1b`
- name: `?SendSensorEvent@wtd_communicator@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `943`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013a5c`

## callees

- `0x140001008`
- `0x140001238`
- `0x1400013b8`
- `0x140001454`
- `0x1400014d0`
- `0x1400072e4`
- `0x1400184f0`
- `0x14001a5d8`
- `0x140026c20`
- `0x140039a6c`
- `0x140039e24`
- `0x14004dc5c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x140039cfc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x140039cfc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140039d0f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140039d0f`
- `WTDSENSOR!WtdsFreeEvent` at `0x140039b34`
- `WTDSENSOR!WtdsFreeEvent` at `0x140039bf8`
- `WTDSENSOR!WtdsFreeEvent` at `0x140039b34`
- `WTDSENSOR!WtdsFreeEvent` at `0x140039bf8`
- `WTDSENSOR!WtdsAllocateEvent` at `0x140039b7b`
- `WTDSENSOR!WtdsAllocateEvent` at `0x140039b7b`
- `WTDSENSOR!WtdsGetEventData` at `0x140039c0d`
- `WTDSENSOR!WtdsGetEventData` at `0x140039c0d`
- `WTDSENSOR!WtdsGetProcessId` at `0x140039c22`
- `WTDSENSOR!WtdsGetProcessId` at `0x140039d83`
- `WTDSENSOR!WtdsGetProcessId` at `0x140039c22`
- `WTDSENSOR!WtdsGetProcessId` at `0x140039d83`
- `WTDSENSOR!WtdsSendEvent` at `0x140039c6f`
- `WTDSENSOR!WtdsSendEvent` at `0x140039da1`
- `WTDSENSOR!WtdsSendEvent` at `0x140039c6f`
- `WTDSENSOR!WtdsSendEvent` at `0x140039da1`

## string_xrefs

- `0x140039ab3`: `onecore\amcore\smartscreen\src\client\urlrep\src\wtd_communicator.cpp`

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
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int64 EventData; // r13
  int ProcessId; // eax
  unsigned __int16 **v19; // r9
  bool v20; // cc
  int v21; // eax
  __int64 v22; // rcx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  HWND ForegroundWindow; // rax
  __int64 v27; // rcx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  __int64 v32; // rcx
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  unsigned __int64 *v36; // [rsp+20h] [rbp-60h]
  unsigned int v37; // [rsp+28h] [rbp-58h]
  const char *v38; // [rsp+40h] [rbp-40h] BYREF
  __int64 v39; // [rsp+48h] [rbp-38h] BYREF
  __int64 v40; // [rsp+50h] [rbp-30h] BYREF
  char v41; // [rsp+58h] [rbp-28h]
  __int64 v42; // [rsp+60h] [rbp-20h] BYREF
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
      (int)v36);
    return (unsigned int)v7;
  }
  v42 = 0;
  v40 = (__int64)&v42;
  v41 = 1;
  v9 = (std::_Mutex_base *)(a1 + 16);
  v39 = a1 + 16;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 16));
  v12 = *(_QWORD *)(a1 + 8);
  if ( !v12 )
  {
    if ( (unsigned int)dword_140086088 > 4 )
    {
      v40 = (__int64)"Null Handle - Sensor not registered";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        0,
        (unsigned int)&dword_140078EEC,
        v10,
        v11,
        (__int64)&v40);
    }
    goto LABEL_7;
  }
  v7 = WtdsAllocateEvent(v12, 0, (unsigned int)(2 * *v6 + 24), &v42);
  if ( v7 )
  {
    if ( (unsigned int)dword_140086088 > 2 && (unsigned __int8)tlgKeywordOn(v13, 0x400000000000LL) )
    {
      v40 = 0x1000000;
      LODWORD(v38) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v14,
        (unsigned int)&dword_140078EB4,
        v15,
        v16,
        (__int64)&v38,
        (__int64)&v40);
    }
LABEL_14:
    if ( v7 <= 0 )
      goto LABEL_17;
    v7 = (unsigned __int16)v7;
    goto LABEL_16;
  }
  EventData = WtdsGetEventData(v42);
  ProcessId = WtdsGetProcessId(a3, EventData);
  v7 = ProcessId;
  v20 = ProcessId <= 0;
  if ( ProcessId )
  {
LABEL_20:
    if ( v20 )
    {
LABEL_17:
      std::_Mutex_base::unlock(v9);
      if ( v42 )
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
  if ( (unsigned int)StringCchCopyExW((unsigned __int16 *)(EventData + 20), *(_QWORD *)v6 + 1LL, v4, v19, v36, v37) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *(_DWORD *)(EventData + 16) = *v6;
  v21 = WtdsSendEvent(*(_QWORD *)(a1 + 8), v42);
  v7 = v21;
  if ( v21 && v21 != 995 )
  {
    if ( (unsigned int)dword_140086088 > 2 && (unsigned __int8)tlgKeywordOn(v22, 0x400000000000LL) )
    {
      v40 = 0x1000000;
      v39 = (__int64)"Navigation";
      LODWORD(v38) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v23,
        (unsigned int)&byte_140078E77,
        v24,
        v25,
        (__int64)&v38,
        (__int64)&v39,
        (__int64)&v40);
    }
    goto LABEL_14;
  }
  dwProcessId = 0;
  ForegroundWindow = GetForegroundWindow();
  GetWindowThreadProcessId(ForegroundWindow, &dwProcessId);
  if ( a3 != dwProcessId )
  {
    if ( (unsigned int)dword_140086088 > 2 && (unsigned __int8)tlgKeywordOn(v27, 0x400000000000LL) )
    {
      v39 = 0x1000000;
      LODWORD(v38) = dwProcessId;
      LODWORD(v40) = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v28,
        (unsigned int)&unk_140078E20,
        v29,
        v30,
        (__int64)&v40,
        (__int64)&v38,
        (__int64)&v39);
    }
    ProcessId = WtdsGetProcessId(dwProcessId, EventData);
    v7 = ProcessId;
    v20 = ProcessId <= 0;
    if ( ProcessId )
      goto LABEL_20;
    v31 = WtdsSendEvent(*(_QWORD *)(a1 + 8), v42);
    v7 = v31;
    if ( v31 && v31 != 995 )
    {
      if ( (unsigned int)dword_140086088 > 2 && (unsigned __int8)tlgKeywordOn(v32, 0x400000000000LL) )
      {
        v39 = 0x1000000;
        v38 = "Foreground";
        LODWORD(v40) = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v33,
          (unsigned int)byte_140078DE3,
          v34,
          v35,
          (__int64)&v40,
          (__int64)&v38,
          (__int64)&v39);
      }
      goto LABEL_14;
    }
  }
LABEL_7:
  std::_Mutex_base::unlock(v9);
  if ( v42 )
    WtdsFreeEvent();
  return 0;
}

```

## disassembly

```asm
0x140039a6c  mov     [rsp-38h+arg_18], rbx
0x140039a71  push    rbp
0x140039a72  push    rsi
0x140039a73  push    rdi
0x140039a74  push    r12
0x140039a76  push    r13
0x140039a78  push    r14
0x140039a7a  push    r15
0x140039a7c  mov     rbp, rsp
0x140039a7f  sub     rsp, 80h
0x140039a86  mov     rax, cs:__security_cookie
0x140039a8d  xor     rax, rsp
0x140039a90  mov     [rbp+var_10], rax
0x140039a94  mov     r12d, r8d
0x140039a97  mov     rsi, rdx
0x140039a9a  mov     r15, rcx
0x140039a9d  lea     r14, [rdx+10h]
0x140039aa1  cmp     qword ptr [r14], 0
0x140039aa5  jnz     short loc_140039AC8
0x140039aa7  mov     rcx, [rbp+38h]; this
0x140039aab  mov     ebx, 800710D2h
0x140039ab0  mov     r9d, ebx; char *
0x140039ab3  lea     r8, aOnecoreAmcoreS_1; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140039aba  mov     edx, 75h ; 'u'; void *
0x140039abf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140039ac4  mov     eax, ebx
0x140039ac6  jmp     short loc_140039B42
0x140039ac8  mov     [rbp+var_20], 0
0x140039ad0  lea     rax, [rbp+var_20]
0x140039ad4  mov     [rbp+var_30], rax
0x140039ad8  mov     [rbp+var_28], 1
0x140039adc  lea     rdi, [rcx+10h]
0x140039ae0  mov     [rbp+var_38], rdi
0x140039ae4  mov     rcx, rdi; this
0x140039ae7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140039aec  nop
0x140039aed  mov     rcx, [r15+8]
0x140039af1  test    rcx, rcx
0x140039af4  jnz     short loc_140039B6A
0x140039af6  mov     eax, cs:dword_140086088
0x140039afc  cmp     eax, 4
0x140039aff  jbe     short loc_140039B22
0x140039b01  lea     rax, aNullHandleSens; "Null Handle - Sensor not registered"
0x140039b08  mov     [rbp+var_30], rax
0x140039b0c  lea     rax, [rbp+var_30]
0x140039b10  mov     [rsp+80h+var_60], rax
0x140039b15  lea     rdx, dword_140078EEC
0x140039b1c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140039b21  nop
0x140039b22  mov     rcx, rdi; this
0x140039b25  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140039b2a  nop
0x140039b2b  mov     rcx, [rbp+var_20]
0x140039b2f  test    rcx, rcx
0x140039b32  jz      short loc_140039B40
0x140039b34  call    cs:__imp_WtdsFreeEvent
0x140039b3b  nop     dword ptr [rax+rax+00h]
0x140039b40  xor     eax, eax
0x140039b42  mov     rcx, [rbp+var_10]
0x140039b46  xor     rcx, rsp; StackCookie
0x140039b49  call    __security_check_cookie
0x140039b4e  mov     rbx, [rsp+80h+arg_18]
0x140039b56  add     rsp, 80h
0x140039b5d  pop     r15
0x140039b5f  pop     r14
0x140039b61  pop     r13
0x140039b63  pop     r12
0x140039b65  pop     rdi
0x140039b66  pop     rsi
0x140039b67  pop     rbp
0x140039b68  retn
0x140039b6a  mov     r8d, [r14]
0x140039b6d  lea     r8d, ds:18h[r8*2]
0x140039b75  xor     edx, edx
0x140039b77  lea     r9, [rbp+var_20]
0x140039b7b  call    cs:__imp_WtdsAllocateEvent
0x140039b82  nop     dword ptr [rax+rax+00h]
0x140039b87  mov     ebx, eax
0x140039b89  test    eax, eax
0x140039b8b  jz      short loc_140039C09
0x140039b8d  mov     eax, cs:dword_140086088
0x140039b93  cmp     eax, 2
0x140039b96  jbe     short loc_140039BD5
0x140039b98  mov     rdx, 400000000000h
0x140039ba2  call    _tlgKeywordOn
0x140039ba7  test    al, al
0x140039ba9  jz      short loc_140039BD5
0x140039bab  mov     esi, 1000000h
0x140039bb0  mov     [rbp+var_30], rsi
0x140039bb4  mov     dword ptr [rbp+var_40], ebx
0x140039bb7  lea     rax, [rbp+var_30]
0x140039bbb  mov     [rsp+80h+var_58], rax
0x140039bc0  lea     rax, [rbp+var_40]
0x140039bc4  mov     [rsp+80h+var_60], rax
0x140039bc9  lea     rdx, dword_140078EB4
0x140039bd0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140039bd5  test    ebx, ebx
0x140039bd7  jle     short loc_140039BE2
0x140039bd9  movzx   ebx, bx
0x140039bdc  or      ebx, 80070000h
0x140039be2  mov     rcx, rdi; this
0x140039be5  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x140039bea  nop
0x140039beb  mov     rcx, [rbp+var_20]
0x140039bef  test    rcx, rcx
0x140039bf2  jz      loc_140039AC4
0x140039bf8  call    cs:__imp_WtdsFreeEvent
0x140039bff  nop     dword ptr [rax+rax+00h]
0x140039c04  jmp     loc_140039AC4
0x140039c09  mov     rcx, [rbp+var_20]
0x140039c0d  call    cs:__imp_WtdsGetEventData
0x140039c14  nop     dword ptr [rax+rax+00h]
0x140039c19  mov     r13, rax
0x140039c1c  mov     rdx, rax
0x140039c1f  mov     ecx, r12d
0x140039c22  call    cs:__imp_WtdsGetProcessId
0x140039c29  nop     dword ptr [rax+rax+00h]
0x140039c2e  mov     ebx, eax
0x140039c30  test    eax, eax
0x140039c32  jz      short loc_140039C3B
0x140039c34  jle     short loc_140039BE2
0x140039c36  movzx   ebx, ax
0x140039c39  jmp     short loc_140039BDC
0x140039c3b  cmp     qword ptr [rsi+18h], 7
0x140039c40  jbe     short loc_140039C45
0x140039c42  mov     rsi, [rsi]
0x140039c45  mov     rdx, [r14]
0x140039c48  inc     rdx; unsigned __int64
0x140039c4b  lea     rcx, [r13+14h]; unsigned __int16 *
0x140039c4f  mov     r8, rsi; unsigned __int16 *
0x140039c52  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x140039c57  test    eax, eax
0x140039c59  jz      short loc_140039C60
0x140039c5b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140039c60  mov     eax, [r14]
0x140039c63  mov     [r13+10h], eax
0x140039c67  mov     rdx, [rbp+var_20]
0x140039c6b  mov     rcx, [r15+8]
0x140039c6f  call    cs:__imp_WtdsSendEvent
0x140039c76  nop     dword ptr [rax+rax+00h]
0x140039c7b  mov     ebx, eax
0x140039c7d  mov     r14d, 3E3h
0x140039c83  test    eax, eax
0x140039c85  jz      short loc_140039CF5
0x140039c87  cmp     eax, r14d
0x140039c8a  jz      short loc_140039CF5
0x140039c8c  mov     eax, cs:dword_140086088
0x140039c92  cmp     eax, 2
0x140039c95  jbe     loc_140039BD5
0x140039c9b  mov     rdx, 400000000000h
0x140039ca5  call    _tlgKeywordOn
0x140039caa  test    al, al
0x140039cac  jz      loc_140039BD5
0x140039cb2  mov     esi, 1000000h
0x140039cb7  mov     [rbp+var_30], rsi
0x140039cbb  lea     rax, aNavigation; "Navigation"
0x140039cc2  mov     [rbp+var_38], rax
0x140039cc6  mov     dword ptr [rbp+var_40], ebx
0x140039cc9  lea     rax, [rbp+var_30]
0x140039ccd  mov     [rsp+80h+var_50], rax
0x140039cd2  lea     rax, [rbp+var_38]
0x140039cd6  mov     [rsp+80h+var_58], rax
0x140039cdb  lea     rax, [rbp+var_40]
0x140039cdf  lea     rdx, byte_140078E77
0x140039ce6  mov     [rsp+80h+var_60], rax
0x140039ceb  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x140039cf0  jmp     loc_140039BD5
0x140039cf5  mov     [rbp+dwProcessId], 0
0x140039cfc  call    cs:__imp_GetForegroundWindow
0x140039d03  nop     dword ptr [rax+rax+00h]
0x140039d08  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x140039d0c  mov     rcx, rax; hWnd
0x140039d0f  call    cs:__imp_GetWindowThreadProcessId
0x140039d16  nop     dword ptr [rax+rax+00h]
0x140039d1b  cmp     r12d, [rbp+dwProcessId]
0x140039d1f  jz      loc_140039B22
0x140039d25  mov     eax, cs:dword_140086088
0x140039d2b  mov     esi, 1000000h
0x140039d30  cmp     eax, 2
0x140039d33  jbe     short loc_140039D7D
0x140039d35  mov     rdx, 400000000000h
0x140039d3f  call    _tlgKeywordOn
0x140039d44  test    al, al
0x140039d46  jz      short loc_140039D7D
0x140039d48  mov     [rbp+var_38], rsi
0x140039d4c  mov     eax, [rbp+dwProcessId]
0x140039d4f  mov     dword ptr [rbp+var_40], eax
0x140039d52  mov     dword ptr [rbp+var_30], r12d
0x140039d56  lea     rax, [rbp+var_38]
0x140039d5a  mov     [rsp+80h+var_50], rax
0x140039d5f  lea     rax, [rbp+var_40]
0x140039d63  mov     [rsp+80h+var_58], rax
0x140039d68  lea     rax, [rbp+var_30]
0x140039d6c  mov     [rsp+80h+var_60], rax
0x140039d71  lea     rdx, unk_140078E20
0x140039d78  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140039d7d  mov     rdx, r13
0x140039d80  mov     ecx, [rbp+dwProcessId]
0x140039d83  call    cs:__imp_WtdsGetProcessId
0x140039d8a  nop     dword ptr [rax+rax+00h]
0x140039d8f  mov     ebx, eax
0x140039d91  test    eax, eax
0x140039d93  jnz     loc_140039C34
0x140039d99  mov     rdx, [rbp+var_20]
0x140039d9d  mov     rcx, [r15+8]
0x140039da1  call    cs:__imp_WtdsSendEvent
0x140039da8  nop     dword ptr [rax+rax+00h]
0x140039dad  mov     ebx, eax
0x140039daf  test    eax, eax
0x140039db1  jz      loc_140039B22
0x140039db7  cmp     eax, r14d
0x140039dba  jz      loc_140039B22
0x140039dc0  mov     eax, cs:dword_140086088
0x140039dc6  cmp     eax, 2
0x140039dc9  jbe     loc_140039BD5
0x140039dcf  mov     rdx, 400000000000h
0x140039dd9  call    _tlgKeywordOn
0x140039dde  test    al, al
0x140039de0  jz      loc_140039BD5
0x140039de6  mov     [rbp+var_38], rsi
0x140039dea  lea     rax, aForeground; "Foreground"
0x140039df1  mov     [rbp+var_40], rax
0x140039df5  mov     dword ptr [rbp+var_30], ebx
0x140039df8  lea     rax, [rbp+var_38]
0x140039dfc  mov     [rsp+80h+var_50], rax
0x140039e01  lea     rax, [rbp+var_40]
0x140039e05  mov     [rsp+80h+var_58], rax
0x140039e0a  lea     rax, [rbp+var_30]
0x140039e0e  lea     rdx, byte_140078DE3
0x140039e15  jmp     loc_140039CE6
```
