# ServiceMain(ulong,ushort * *)

- ea: `0x180002300`
- end: `0x18000244c`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `332`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180001008`
- `0x180001f3c`
- `0x180001fec`
- `0x180002300`
- `0x180002708`
- `0x180002890`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000235f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000235f`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000237e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000237e`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180002392`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180002392`

## string_xrefs

- `0x1800023db`: `ServiceMain`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  unsigned int v2; // edx
  int v3; // r8d
  int v4; // r9d
  unsigned __int16 **v5; // rdx
  unsigned int v6; // ecx
  int v7; // [rsp+30h] [rbp-28h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-20h] BYREF

  McGenEventRegister_EventRegister(a1, a2);
  ProviderId = *(GUID *)&(*off_180006050)[-16];
  if ( RegHandle )
    __fastfail(5u);
  xmmword_180006070 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180006048, &RegHandle) )
    EventSetInformation(RegHandle, 2, (char *)off_180006050, *(unsigned __int16 *)off_180006050);
  g_ServiceStatusHandle = RegisterServiceCtrlHandlerW(L"SMPHost", ServiceCtrlHandler);
  if ( g_ServiceStatusHandle )
  {
    g_ServiceStatus.dwServiceType = 16;
    dword_1800067E0 = 0;
    ReportServiceStatus(2u, v2, 0xBB8u);
    ServiceInit(v6, v5);
  }
  else if ( (unsigned int)dword_180006048 > 5
         && (qword_180006058 & 0x400000000000LL) != 0
         && (qword_180006060 & 0x400000000000LL) == qword_180006060 )
  {
    v7 = 86;
    *(_QWORD *)&ProviderId.Data1 = "ServiceMain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_180006060,
      (unsigned int)&word_18000493E,
      v3,
      v4,
      (__int64)&ProviderId,
      (__int64)&v7);
  }
}

```

## disassembly

```asm
0x180002300  sub     rsp, 58h
0x180002304  mov     rax, cs:__security_cookie
0x18000230b  xor     rax, rsp
0x18000230e  mov     [rsp+58h+var_10], rax
0x180002313  call    McGenEventRegister_EventRegister
0x180002318  cmp     cs:RegHandle, 0
0x180002320  mov     rax, cs:off_180006050
0x180002327  movups  xmm0, xmmword ptr [rax-10h]
0x18000232b  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x180002331  jz      short loc_18000233A
0x180002333  mov     ecx, 5
0x180002338  int     29h; Win8: RtlFailFast(ecx)
0x18000233a  xorps   xmm0, xmm0
0x18000233d  lea     r9, RegHandle; RegHandle
0x180002344  lea     r8, dword_180006048; CallbackContext
0x18000234b  lea     rdx, _tlgEnableCallback; EnableCallback
0x180002352  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x180002357  movdqu  cs:xmmword_180006070, xmm0
0x18000235f  call    cs:__imp_EventRegister
0x180002365  test    eax, eax
0x180002367  jnz     short loc_180002384
0x180002369  mov     r8, cs:off_180006050
0x180002370  lea     edx, [rax+2]
0x180002373  mov     rcx, cs:RegHandle
0x18000237a  movzx   r9d, word ptr [r8]
0x18000237e  call    cs:__imp_EventSetInformation
0x180002384  lea     rdx, ?ServiceCtrlHandler@@YAXK@Z; lpHandlerProc
0x18000238b  lea     rcx, ServiceName; "SMPHost"
0x180002392  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180002398  mov     cs:?g_ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_ServiceStatusHandle
0x18000239f  test    rax, rax
0x1800023a2  jnz     short loc_180002411
0x1800023a4  mov     eax, cs:dword_180006048
0x1800023aa  cmp     eax, 5
0x1800023ad  jbe     loc_18000243A
0x1800023b3  mov     rcx, cs:qword_180006060
0x1800023ba  mov     rdx, 400000000000h
0x1800023c4  mov     rax, cs:qword_180006058
0x1800023cb  test    rdx, rax
0x1800023ce  jz      short loc_18000243A
0x1800023d0  mov     rax, rcx
0x1800023d3  and     rax, rdx
0x1800023d6  cmp     rax, rcx
0x1800023d9  jnz     short loc_18000243A
0x1800023db  lea     rax, aServicemain_0; "ServiceMain"
0x1800023e2  mov     [rsp+58h+var_28], 56h ; 'V'
0x1800023ea  mov     qword ptr [rsp+58h+ProviderId.Data1], rax
0x1800023ef  lea     rdx, word_18000493E
0x1800023f6  lea     rax, [rsp+58h+var_28]
0x1800023fb  mov     [rsp+58h+var_30], rax
0x180002400  lea     rax, [rsp+58h+ProviderId]
0x180002405  mov     [rsp+58h+var_38], rax
0x18000240a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000240f  jmp     short loc_18000243A
0x180002411  mov     ecx, 2; unsigned int
0x180002416  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A, 10h; _SERVICE_STATUS g_ServiceStatus
0x180002420  mov     r8d, 0BB8h; unsigned int
0x180002426  mov     cs:dword_1800067E0, 0
0x180002430  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x180002435  call    ?ServiceInit@@YAXKPEAPEAG@Z; ServiceInit(ulong,ushort * *)
0x18000243a  mov     rcx, [rsp+58h+var_10]
0x18000243f  xor     rcx, rsp; StackCookie
0x180002442  call    __security_check_cookie
0x180002447  add     rsp, 58h
0x18000244b  retn
```
