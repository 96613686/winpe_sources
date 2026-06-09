# RDSHTelemetryLogging::OnRegUpdate(void)

- ea: `0x1800934cc`
- end: `0x18009367c`
- name: `?OnRegUpdate@RDSHTelemetryLogging@@SAXXZ`
- size: `432`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18004d4d0`

## callees

- `0x180001294`
- `0x180028dd8`
- `0x180028e44`
- `0x180028f88`
- `0x1800934cc`
- `0x180093d44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009358d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800935b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009358d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800935b7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180093567`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180093567`

## string_xrefs

- `0x18009359c`: `createIntervalTimer failed`
- `0x1800935c6`: `DeleteTimerQueueTimer(m_hTelemetryTimerLowFreq) failed`
- `0x18009360f`: `ReadRegDWord for Telemetry InitInterval failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void RDSHTelemetryLogging::OnRegUpdate(void)
{
  signed int v0; // ecx
  int v1; // r8d
  int v2; // r9d
  int v3; // ebx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  const char *v7; // rax
  int *v8; // rdx
  const char *v9; // rax
  char *v10; // rdx
  const unsigned __int16 *v11; // [rsp+20h] [rbp-40h]
  _QWORD v12[2]; // [rsp+30h] [rbp-30h] BYREF
  int v13; // [rsp+40h] [rbp-20h]
  __int64 v14; // [rsp+48h] [rbp-18h]
  int v15; // [rsp+50h] [rbp-10h]
  int v16; // [rsp+54h] [rbp-Ch]
  DWORD DueTime; // [rsp+70h] [rbp+10h] BYREF
  const char *v18; // [rsp+78h] [rbp+18h] BYREF

  v12[0] = &CRegistry::`vftable';
  v12[1] = 0;
  v13 = 0;
  v14 = 0;
  v15 = -1;
  v16 = -1;
  v0 = CRegistry::OpenKey(
         (CRegistry *)v12,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server",
         0x20019u,
         v11);
  if ( v0 )
  {
    if ( (unsigned int)dword_18012E170 <= 2 )
      goto LABEL_21;
    if ( v0 > 0 )
      v0 = (unsigned __int16)v0 | 0x80070000;
    v9 = "Terminal Server key missing";
    v10 = byte_180117491;
    goto LABEL_20;
  }
  DueTime = 0;
  v0 = CRegistry::ReadRegDWord((CRegistry *)v12, L"TSTelemetryInitInterval", &DueTime);
  if ( v0 )
  {
    if ( (unsigned int)dword_18012E170 <= 4 )
      goto LABEL_21;
    if ( v0 > 0 )
      v0 = (unsigned __int16)v0 | 0x80070000;
    v9 = "ReadRegDWord for Telemetry InitInterval failed";
    v10 = byte_1801174D9;
LABEL_20:
    v18 = v9;
    DueTime = v0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v0,
      (_DWORD)v10,
      v1,
      v2,
      (__int64)&v18,
      (__int64)&DueTime);
    goto LABEL_21;
  }
  v3 = DueTime;
  if ( DueTime != RDSHTelemetryLogging::prevTimerQueueInterval )
  {
    if ( DeleteTimerQueueTimer(0, RDSHTelemetryLogging::m_hTelemetryTimerLowFreq, 0) )
    {
      if ( !(unsigned int)RDSHTelemetryLogging::createIntervalTimer(v3) || (unsigned int)dword_18012E170 <= 2 )
        goto LABEL_11;
      DueTime = GetLastError();
      v7 = "createIntervalTimer failed";
      v8 = &dword_18011755C;
      goto LABEL_10;
    }
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      DueTime = GetLastError();
      v7 = "DeleteTimerQueueTimer(m_hTelemetryTimerLowFreq) failed";
      v8 = (int *)byte_180117521;
LABEL_10:
      v18 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v4,
        (_DWORD)v8,
        v5,
        v6,
        (__int64)&v18,
        (__int64)&DueTime);
    }
  }
LABEL_11:
  RDSHTelemetryLogging::prevTimerQueueInterval = v3;
LABEL_21:
  CRegistry::~CRegistry((CRegistry *)v12);
}

```

## disassembly

```asm
0x1800934cc  mov     [rsp-8+arg_10], rbx
0x1800934d1  push    rbp
0x1800934d2  mov     rbp, rsp
0x1800934d5  sub     rsp, 60h
0x1800934d9  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800934e0  mov     [rbp+var_30], rax
0x1800934e4  mov     [rbp+var_28], 0
0x1800934ec  mov     [rbp+var_20], 0
0x1800934f3  mov     [rbp+var_18], 0
0x1800934fb  or      eax, 0FFFFFFFFh
0x1800934fe  mov     [rbp+var_10], eax
0x180093501  mov     [rbp+var_C], eax
0x180093504  mov     r9d, 20019h; unsigned int
0x18009350a  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ter"...
0x180093511  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180093518  lea     rcx, [rbp+var_30]; this
0x18009351c  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x180093521  mov     ecx, eax
0x180093523  test    eax, eax
0x180093525  jnz     loc_18009361F
0x18009352b  mov     [rbp+DueTime], eax
0x18009352e  lea     r8, [rbp+DueTime]; unsigned int *
0x180093532  lea     rdx, aTstelemetryini; "TSTelemetryInitInterval"
0x180093539  lea     rcx, [rbp+var_30]; this
0x18009353d  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x180093542  mov     ecx, eax
0x180093544  test    eax, eax
0x180093546  jnz     loc_1800935F7
0x18009354c  mov     ebx, [rbp+DueTime]
0x18009354f  cmp     ebx, cs:?prevTimerQueueInterval@RDSHTelemetryLogging@@0JA; long RDSHTelemetryLogging::prevTimerQueueInterval
0x180093555  jz      loc_1800935EF
0x18009355b  xor     r8d, r8d; CompletionEvent
0x18009355e  mov     rdx, cs:?m_hTelemetryTimerLowFreq@RDSHTelemetryLogging@@0PEAXEA; Timer
0x180093565  xor     ecx, ecx; TimerQueue
0x180093567  call    cs:__imp_DeleteTimerQueueTimer
0x18009356e  nop     dword ptr [rax+rax+00h]
0x180093573  test    eax, eax
0x180093575  jz      short loc_1800935AC
0x180093577  mov     ecx, ebx; DueTime
0x180093579  call    ?createIntervalTimer@RDSHTelemetryLogging@@CAJK@Z; RDSHTelemetryLogging::createIntervalTimer(ulong)
0x18009357e  test    eax, eax
0x180093580  jz      short loc_1800935EF
0x180093582  mov     eax, cs:dword_18012E170
0x180093588  cmp     eax, 2
0x18009358b  jbe     short loc_1800935EF
0x18009358d  call    cs:__imp_GetLastError
0x180093594  nop     dword ptr [rax+rax+00h]
0x180093599  mov     [rbp+DueTime], eax
0x18009359c  lea     rax, aCreateinterval; "createIntervalTimer failed"
0x1800935a3  lea     rdx, dword_18011755C
0x1800935aa  jmp     short loc_1800935D4
0x1800935ac  mov     eax, cs:dword_18012E170
0x1800935b2  cmp     eax, 2
0x1800935b5  jbe     short loc_1800935EF
0x1800935b7  call    cs:__imp_GetLastError
0x1800935be  nop     dword ptr [rax+rax+00h]
0x1800935c3  mov     [rbp+DueTime], eax
0x1800935c6  lea     rax, aDeletetimerque; "DeleteTimerQueueTimer(m_hTelemetryTimer"...
0x1800935cd  lea     rdx, byte_180117521
0x1800935d4  mov     [rbp+arg_8], rax
0x1800935d8  lea     rax, [rbp+DueTime]
0x1800935dc  mov     [rsp+60h+var_38], rax
0x1800935e1  lea     rax, [rbp+arg_8]
0x1800935e5  mov     [rsp+60h+var_40], rax
0x1800935ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800935ef  mov     cs:?prevTimerQueueInterval@RDSHTelemetryLogging@@0JA, ebx; long RDSHTelemetryLogging::prevTimerQueueInterval
0x1800935f5  jmp     short loc_180093664
0x1800935f7  mov     eax, cs:dword_18012E170
0x1800935fd  cmp     eax, 4
0x180093600  jbe     short loc_180093664
0x180093602  test    ecx, ecx
0x180093604  jle     short loc_18009360F
0x180093606  movzx   ecx, cx
0x180093609  or      ecx, 80070000h
0x18009360f  lea     rax, aReadregdwordFo_0; "ReadRegDWord for Telemetry InitInterval"...
0x180093616  lea     rdx, byte_1801174D9
0x18009361d  jmp     short loc_180093645
0x18009361f  mov     eax, cs:dword_18012E170
0x180093625  cmp     eax, 2
0x180093628  jbe     short loc_180093664
0x18009362a  test    ecx, ecx
0x18009362c  jle     short loc_180093637
0x18009362e  movzx   ecx, cx
0x180093631  or      ecx, 80070000h
0x180093637  lea     rax, aTerminalServer_0; "Terminal Server key missing"
0x18009363e  lea     rdx, byte_180117491
0x180093645  mov     [rbp+arg_8], rax
0x180093649  lea     rax, [rbp+DueTime]
0x18009364d  mov     [rsp+60h+var_38], rax
0x180093652  lea     rax, [rbp+arg_8]
0x180093656  mov     [rsp+60h+var_40], rax
0x18009365b  mov     [rbp+DueTime], ecx
0x18009365e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180093663  nop
0x180093664  lea     rcx, [rbp+var_30]; this
0x180093668  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18009366d  mov     rbx, [rsp+60h+arg_10]
0x180093675  add     rsp, 60h
0x180093679  pop     rbp
0x18009367a  retn
```
