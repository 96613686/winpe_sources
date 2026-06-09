# RDSHTelemetryLogging::OnRegUpdate(void)

- ea: `0x18008f758`
- end: `0x18008f8f5`
- name: `?OnRegUpdate@RDSHTelemetryLogging@@SAXXZ`
- size: `413`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18004aeb0`

## callees

- `0x180001284`
- `0x1800279a8`
- `0x180027a04`
- `0x180027b44`
- `0x18008f758`
- `0x18008ffb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f837`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18008f7f3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18008f7f3`

## string_xrefs

- `0x18008f81c`: `createIntervalTimer failed`
- `0x18008f840`: `DeleteTimerQueueTimer(m_hTelemetryTimerLowFreq) failed`
- `0x18008f889`: `ReadRegDWord for Telemetry InitInterval failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void RDSHTelemetryLogging::OnRegUpdate(void)
{
  int v0; // eax
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 v3; // rcx
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v9; // rax
  unsigned __int8 *v10; // rdx
  const char *v11; // rax
  char *v12; // rdx
  const unsigned __int16 *v13; // [rsp+20h] [rbp-40h]
  _QWORD v14[2]; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+40h] [rbp-20h]
  __int64 v16; // [rsp+48h] [rbp-18h]
  int v17; // [rsp+50h] [rbp-10h]
  int v18; // [rsp+54h] [rbp-Ch]
  DWORD DueTime; // [rsp+70h] [rbp+10h] BYREF
  const char *v20; // [rsp+78h] [rbp+18h] BYREF

  v14[0] = &CRegistry::`vftable';
  v14[1] = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = -1;
  v0 = CRegistry::OpenKey(
         (CRegistry *)v14,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server",
         0x20019u,
         v13);
  v3 = (unsigned int)v0;
  if ( v0 )
  {
    if ( (unsigned int)dword_180128170 <= 2 )
      goto LABEL_21;
    if ( v0 > 0 )
      v3 = (unsigned __int16)v0 | 0x80070000;
    v11 = "Terminal Server key missing";
    v12 = byte_180111411;
    goto LABEL_20;
  }
  DueTime = 0;
  v4 = CRegistry::ReadRegDWord((CRegistry *)v14, L"TSTelemetryInitInterval", &DueTime);
  v3 = (unsigned int)v4;
  if ( v4 )
  {
    if ( (unsigned int)dword_180128170 <= 4 )
      goto LABEL_21;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    v11 = "ReadRegDWord for Telemetry InitInterval failed";
    v12 = byte_180111459;
LABEL_20:
    v20 = v11;
    DueTime = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned __int8 *)v12,
      v1,
      v2,
      (const unsigned __int16 **)&v20,
      (__int64)&DueTime);
    goto LABEL_21;
  }
  v5 = DueTime;
  if ( DueTime != RDSHTelemetryLogging::prevTimerQueueInterval )
  {
    if ( DeleteTimerQueueTimer(0, RDSHTelemetryLogging::m_hTelemetryTimerLowFreq, 0) )
    {
      if ( !(unsigned int)RDSHTelemetryLogging::createIntervalTimer(v5) || (unsigned int)dword_180128170 <= 2 )
        goto LABEL_11;
      DueTime = GetLastError();
      v9 = "createIntervalTimer failed";
      v10 = (unsigned __int8 *)&dword_1801114DC;
      goto LABEL_10;
    }
    if ( (unsigned int)dword_180128170 > 2 )
    {
      DueTime = GetLastError();
      v9 = "DeleteTimerQueueTimer(m_hTelemetryTimerLowFreq) failed";
      v10 = (unsigned __int8 *)byte_1801114A1;
LABEL_10:
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        v10,
        v7,
        v8,
        (const unsigned __int16 **)&v20,
        (__int64)&DueTime);
    }
  }
LABEL_11:
  RDSHTelemetryLogging::prevTimerQueueInterval = v5;
LABEL_21:
  CRegistry::~CRegistry((CRegistry *)v14);
}

```

## disassembly

```asm
0x18008f758  mov     [rsp-8+arg_10], rbx
0x18008f75d  push    rbp
0x18008f75e  mov     rbp, rsp
0x18008f761  sub     rsp, 60h
0x18008f765  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18008f76c  mov     [rbp+var_30], rax
0x18008f770  mov     [rbp+var_28], 0
0x18008f778  mov     [rbp+var_20], 0
0x18008f77f  mov     [rbp+var_18], 0
0x18008f787  or      eax, 0FFFFFFFFh
0x18008f78a  mov     [rbp+var_10], eax
0x18008f78d  mov     [rbp+var_C], eax
0x18008f790  mov     r9d, 20019h; unsigned int
0x18008f796  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x18008f79d  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18008f7a4  lea     rcx, [rbp+var_30]; this
0x18008f7a8  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18008f7ad  mov     ecx, eax
0x18008f7af  test    eax, eax
0x18008f7b1  jnz     loc_18008F899
0x18008f7b7  mov     [rbp+DueTime], eax
0x18008f7ba  lea     r8, [rbp+DueTime]; unsigned int *
0x18008f7be  lea     rdx, aTstelemetryini; "TSTelemetryInitInterval"
0x18008f7c5  lea     rcx, [rbp+var_30]; this
0x18008f7c9  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18008f7ce  mov     ecx, eax
0x18008f7d0  test    eax, eax
0x18008f7d2  jnz     loc_18008F871
0x18008f7d8  mov     ebx, [rbp+DueTime]
0x18008f7db  cmp     ebx, cs:?prevTimerQueueInterval@RDSHTelemetryLogging@@0JA; long RDSHTelemetryLogging::prevTimerQueueInterval
0x18008f7e1  jz      loc_18008F869
0x18008f7e7  xor     r8d, r8d; CompletionEvent
0x18008f7ea  mov     rdx, cs:?m_hTelemetryTimerLowFreq@RDSHTelemetryLogging@@0PEAXEA; Timer
0x18008f7f1  xor     ecx, ecx; TimerQueue
0x18008f7f3  call    cs:__imp_DeleteTimerQueueTimer
0x18008f7f9  test    eax, eax
0x18008f7fb  jz      short loc_18008F82C
0x18008f7fd  mov     ecx, ebx; DueTime
0x18008f7ff  call    ?createIntervalTimer@RDSHTelemetryLogging@@CAJK@Z; RDSHTelemetryLogging::createIntervalTimer(ulong)
0x18008f804  test    eax, eax
0x18008f806  jz      short loc_18008F869
0x18008f808  mov     eax, cs:dword_180128170
0x18008f80e  cmp     eax, 2
0x18008f811  jbe     short loc_18008F869
0x18008f813  call    cs:__imp_GetLastError
0x18008f819  mov     [rbp+DueTime], eax
0x18008f81c  lea     rax, aCreateinterval; "createIntervalTimer failed"
0x18008f823  lea     rdx, dword_1801114DC
0x18008f82a  jmp     short loc_18008F84E
0x18008f82c  mov     eax, cs:dword_180128170
0x18008f832  cmp     eax, 2
0x18008f835  jbe     short loc_18008F869
0x18008f837  call    cs:__imp_GetLastError
0x18008f83d  mov     [rbp+DueTime], eax
0x18008f840  lea     rax, aDeletetimerque; "DeleteTimerQueueTimer(m_hTelemetryTimer"...
0x18008f847  lea     rdx, byte_1801114A1
0x18008f84e  mov     [rbp+arg_8], rax
0x18008f852  lea     rax, [rbp+DueTime]
0x18008f856  mov     [rsp+60h+var_38], rax
0x18008f85b  lea     rax, [rbp+arg_8]
0x18008f85f  mov     [rsp+60h+var_40], rax
0x18008f864  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008f869  mov     cs:?prevTimerQueueInterval@RDSHTelemetryLogging@@0JA, ebx; long RDSHTelemetryLogging::prevTimerQueueInterval
0x18008f86f  jmp     short loc_18008F8DE
0x18008f871  mov     eax, cs:dword_180128170
0x18008f877  cmp     eax, 4
0x18008f87a  jbe     short loc_18008F8DE
0x18008f87c  test    ecx, ecx
0x18008f87e  jle     short loc_18008F889
0x18008f880  movzx   ecx, cx
0x18008f883  or      ecx, 80070000h
0x18008f889  lea     rax, aReadregdwordFo_0; "ReadRegDWord for Telemetry InitInterval"...
0x18008f890  lea     rdx, byte_180111459
0x18008f897  jmp     short loc_18008F8BF
0x18008f899  mov     eax, cs:dword_180128170
0x18008f89f  cmp     eax, 2
0x18008f8a2  jbe     short loc_18008F8DE
0x18008f8a4  test    ecx, ecx
0x18008f8a6  jle     short loc_18008F8B1
0x18008f8a8  movzx   ecx, cx
0x18008f8ab  or      ecx, 80070000h
0x18008f8b1  lea     rax, aTerminalServer_0; "Terminal Server key missing"
0x18008f8b8  lea     rdx, byte_180111411
0x18008f8bf  mov     [rbp+arg_8], rax
0x18008f8c3  lea     rax, [rbp+DueTime]
0x18008f8c7  mov     [rsp+60h+var_38], rax
0x18008f8cc  lea     rax, [rbp+arg_8]
0x18008f8d0  mov     [rsp+60h+var_40], rax
0x18008f8d5  mov     [rbp+DueTime], ecx
0x18008f8d8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008f8dd  nop
0x18008f8de  lea     rcx, [rbp+var_30]; this
0x18008f8e2  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18008f8e7  mov     rbx, [rsp+60h+arg_10]
0x18008f8ef  add     rsp, 60h
0x18008f8f3  pop     rbp
0x18008f8f4  retn
```
