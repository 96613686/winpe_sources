# CServiceHandler::Init(ushort const *)

- ea: `0x1800124b0`
- end: `0x180012707`
- name: `?Init@CServiceHandler@@AEAAXPEBG@Z`
- size: `599`
- prototype: `void(CServiceHandler *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013344`

## callees

- `0x1800010c4`
- `0x1800013e0`
- `0x1800094f4`
- `0x18000fb78`
- `0x1800124b0`
- `0x1800137ac`
- `0x18001387c`
- `0x180013a68`
- `0x1800c5ac0`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800124de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800124de`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800125b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012611`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012666`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800125b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012611`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012666`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001258d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001258d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012696`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001256c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001256c`

## pseudocode

```c
void __fastcall CServiceHandler::Init(CServiceHandler *this, const unsigned __int16 *a2)
{
  signed int LastError; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int16 *v7; // rdx
  HANDLE EventW; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  const struct wil::FailureInfo *v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  _BYTE v13[160]; // [rsp+30h] [rbp-49h] BYREF
  CServiceHandler *v14; // [rsp+E0h] [rbp+67h] BYREF

  v14 = this;
  xmmword_180152660 = 0;
  *(__int128 *)((char *)&xmmword_180152660 + 12) = 0;
  CServiceHandler::s_ServiceInstance = _o__wcsdup(a2);
  CServiceHandler::s_lLoggingRegistered = TlgRegisterAggregateProviderEx();
  if ( CServiceHandler::s_lLoggingRegistered < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&qword_180151008);
  McGenEventRegister_EventRegister();
  if ( wil::details::g_pfnTelemetryCallback
    && (__int64 (__fastcall *)())wil::details::g_pfnTelemetryCallback != CServiceHandler::Init_::_2_::_lambda_1_::_lambda_invoker_cdecl_ )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v12);
  }
  wil::details::g_pfnTelemetryCallback = (__int64)CServiceHandler::Init_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
  if ( wil::details::g_pfnLoggingCallback
    && (char *)wil::details::g_pfnLoggingCallback != (char *)CServiceHandler::Init_::_2_::_lambda_2_::_lambda_invoker_cdecl_ )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v11);
  }
  wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))CServiceHandler::Init_::_2_::_lambda_2_::_lambda_invoker_cdecl_;
  qword_180152658 = (__int64)RegisterServiceCtrlHandlerExW(
                               a2,
                               CServiceHandler::_ServiceControlHandler,
                               &CServiceHandler::s_ServiceInstance);
  if ( !qword_180152658 )
  {
    if ( (unsigned int)dword_180151040 <= 5 )
      return;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = (__int16 *)byte_18013DC9D;
    goto LABEL_27;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&qword_180152690, EventW);
  if ( qword_180152690 == -1 || qword_180152690 == 0 )
  {
    if ( (unsigned int)dword_180151040 <= 5 )
      return;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = (__int16 *)&dword_18013DC6C;
    goto LABEL_27;
  }
  v9 = CreateEventW(0, 0, 0, 0);
  tlx::shared_any<tlx::file_handle_traits>::assign(&qword_1801526A8, v9);
  if ( qword_1801526A8 == -1 || qword_1801526A8 == 0 )
  {
    if ( (unsigned int)dword_180151040 <= 5 )
      return;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = (__int16 *)&unk_18013DC40;
    goto LABEL_27;
  }
  v10 = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hEvent, v10);
  if ( (hEvent == (HANDLE)-1LL || (char *)hEvent + 1 == HANDLE_FLAG_INHERIT) && (unsigned int)dword_180151040 > 5 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = word_18013DC02;
LABEL_27:
    LODWORD(v14) = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (__int64)v7,
      v5,
      v6,
      (__int64)&v14);
  }
}

```

## disassembly

```asm
0x1800124b0  mov     [rsp-8+arg_8], rbx
0x1800124b5  mov     [rsp-8+arg_0], rcx
0x1800124ba  push    rbp
0x1800124bb  lea     rbp, [rsp-57h]
0x1800124c0  sub     rsp, 0D0h
0x1800124c7  xorps   xmm0, xmm0
0x1800124ca  mov     rcx, rdx
0x1800124cd  movups  cs:xmmword_180152660, xmm0
0x1800124d4  mov     rbx, rdx
0x1800124d7  movups  cs:xmmword_180152660+0Ch, xmm0
0x1800124de  call    cs:__imp__o__wcsdup
0x1800124e4  mov     cs:?s_ServiceInstance@CServiceHandler@@0V1@A, rax; CServiceHandler CServiceHandler::s_ServiceInstance
0x1800124eb  call    TlgRegisterAggregateProviderEx
0x1800124f0  mov     cs:?s_lLoggingRegistered@CServiceHandler@@0JA, eax; long CServiceHandler::s_lLoggingRegistered
0x1800124f6  test    eax, eax
0x1800124f8  jns     short loc_1800124FF
0x1800124fa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800124ff  xor     r8d, r8d
0x180012502  lea     rcx, qword_180151008; CallbackContext
0x180012509  xor     edx, edx
0x18001250b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180012510  call    McGenEventRegister_EventRegister
0x180012515  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18001251c  lea     rcx, _CServiceHandler__Init____2____lambda_1____lambda_invoker_cdecl_
0x180012523  test    rax, rax
0x180012526  jz      short loc_180012531
0x180012528  cmp     rax, rcx
0x18001252b  jnz     loc_1800126EC
0x180012531  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012538  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x18001253f  lea     rcx, _CServiceHandler__Init____2____lambda_2____lambda_invoker_cdecl_
0x180012546  test    rax, rax
0x180012549  jz      short loc_180012554
0x18001254b  cmp     rax, rcx
0x18001254e  jnz     loc_1800126D1
0x180012554  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18001255b  lea     r8, ?s_ServiceInstance@CServiceHandler@@0V1@A; lpContext
0x180012562  mov     rcx, rbx; lpServiceName
0x180012565  lea     rdx, ?_ServiceControlHandler@CServiceHandler@@CAKKKPEAX0@Z; lpHandlerProc
0x18001256c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180012572  mov     cs:qword_180152658, rax
0x180012579  test    rax, rax
0x18001257c  jnz     short loc_1800125AB
0x18001257e  mov     eax, cs:dword_180151040
0x180012584  cmp     eax, 5
0x180012587  jbe     loc_1800126C0
0x18001258d  call    cs:__imp_GetLastError
0x180012593  test    eax, eax
0x180012595  jle     short loc_18001259F
0x180012597  movzx   eax, ax
0x18001259a  or      eax, 80070000h
0x18001259f  lea     rdx, byte_18013DC9D
0x1800125a6  jmp     loc_1800126AF
0x1800125ab  xor     r9d, r9d; lpName
0x1800125ae  xor     r8d, r8d; bInitialState
0x1800125b1  xor     edx, edx; bManualReset
0x1800125b3  xor     ecx, ecx; lpEventAttributes
0x1800125b5  call    cs:__imp_CreateEventW
0x1800125bb  mov     rdx, rax
0x1800125be  lea     rcx, qword_180152690
0x1800125c5  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800125ca  mov     rax, cs:qword_180152690
0x1800125d1  inc     rax
0x1800125d4  cmp     rax, 1
0x1800125d8  ja      short loc_180012607
0x1800125da  mov     eax, cs:dword_180151040
0x1800125e0  cmp     eax, 5
0x1800125e3  jbe     loc_1800126C0
0x1800125e9  call    cs:__imp_GetLastError
0x1800125ef  test    eax, eax
0x1800125f1  jle     short loc_1800125FB
0x1800125f3  movzx   eax, ax
0x1800125f6  or      eax, 80070000h
0x1800125fb  lea     rdx, dword_18013DC6C
0x180012602  jmp     loc_1800126AF
0x180012607  xor     r9d, r9d; lpName
0x18001260a  xor     r8d, r8d; bInitialState
0x18001260d  xor     edx, edx; bManualReset
0x18001260f  xor     ecx, ecx; lpEventAttributes
0x180012611  call    cs:__imp_CreateEventW
0x180012617  mov     rdx, rax
0x18001261a  lea     rcx, qword_1801526A8
0x180012621  call    ?assign@?$shared_any@Ufile_handle_traits@tlx@@@tlx@@QEAA_NPEAX@Z; tlx::shared_any<tlx::file_handle_traits>::assign(void *)
0x180012626  mov     rax, cs:qword_1801526A8
0x18001262d  inc     rax
0x180012630  cmp     rax, 1
0x180012634  ja      short loc_18001265C
0x180012636  mov     eax, cs:dword_180151040
0x18001263c  cmp     eax, 5
0x18001263f  jbe     short loc_1800126C0
0x180012641  call    cs:__imp_GetLastError
0x180012647  test    eax, eax
0x180012649  jle     short loc_180012653
0x18001264b  movzx   eax, ax
0x18001264e  or      eax, 80070000h
0x180012653  lea     rdx, unk_18013DC40
0x18001265a  jmp     short loc_1800126AF
0x18001265c  xor     r9d, r9d; lpName
0x18001265f  xor     r8d, r8d; bInitialState
0x180012662  xor     edx, edx; bManualReset
0x180012664  xor     ecx, ecx; lpEventAttributes
0x180012666  call    cs:__imp_CreateEventW
0x18001266c  mov     rdx, rax
0x18001266f  lea     rcx, hEvent
0x180012676  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18001267b  mov     rax, cs:hEvent
0x180012682  inc     rax
0x180012685  cmp     rax, 1
0x180012689  ja      short loc_1800126C0
0x18001268b  mov     eax, cs:dword_180151040
0x180012691  cmp     eax, 5
0x180012694  jbe     short loc_1800126C0
0x180012696  call    cs:__imp_GetLastError
0x18001269c  test    eax, eax
0x18001269e  jle     short loc_1800126A8
0x1800126a0  movzx   eax, ax
0x1800126a3  or      eax, 80070000h
0x1800126a8  lea     rdx, word_18013DC02
0x1800126af  mov     dword ptr [rbp+57h+arg_0], eax
0x1800126b2  lea     rax, [rbp+57h+arg_0]
0x1800126b6  mov     [rsp+0D0h+var_B0], rax
0x1800126bb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800126c0  mov     rbx, [rsp+0D0h+arg_8]
0x1800126c8  add     rsp, 0D0h
0x1800126cf  pop     rbp
0x1800126d0  retn
0x1800126d1  xor     edx, edx; Val
0x1800126d3  lea     rcx, [rbp+57h+var_A0]; void *
0x1800126d7  mov     r8d, 98h; Size
0x1800126dd  call    memset_0
0x1800126e2  lea     rcx, [rbp+57h+var_A0]; this
0x1800126e6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800126ec  xor     edx, edx; Val
0x1800126ee  lea     rcx, [rbp+57h+var_A0]; void *
0x1800126f2  mov     r8d, 98h; Size
0x1800126f8  call    memset_0
0x1800126fd  lea     rcx, [rbp+57h+var_A0]; this
0x180012701  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
