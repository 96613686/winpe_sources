# ServiceMain(ulong,ushort * *)

- ea: `0x180002380`
- end: `0x1800024df`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `351`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180001008`
- `0x180001f80`
- `0x180002044`
- `0x180002380`
- `0x1800027a8`
- `0x180002950`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800023df`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800023df`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180002404`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180002404`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18000241e`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18000241e`

## string_xrefs

- `0x18000246d`: `ServiceMain`

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
0x180002380  sub     rsp, 58h
0x180002384  mov     rax, cs:__security_cookie
0x18000238b  xor     rax, rsp
0x18000238e  mov     [rsp+58h+var_10], rax
0x180002393  call    McGenEventRegister_EventRegister
0x180002398  cmp     cs:RegHandle, 0
0x1800023a0  mov     rax, cs:off_180006050
0x1800023a7  movups  xmm0, xmmword ptr [rax-10h]
0x1800023ab  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x1800023b1  jz      short loc_1800023BA
0x1800023b3  mov     ecx, 5
0x1800023b8  int     29h; Win8: RtlFailFast(ecx)
0x1800023ba  xorps   xmm0, xmm0
0x1800023bd  lea     r9, RegHandle; RegHandle
0x1800023c4  lea     r8, dword_180006048; CallbackContext
0x1800023cb  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800023d2  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x1800023d7  movdqu  cs:xmmword_180006070, xmm0
0x1800023df  call    cs:__imp_EventRegister
0x1800023e6  nop     dword ptr [rax+rax+00h]
0x1800023eb  test    eax, eax
0x1800023ed  jnz     short loc_180002410
0x1800023ef  mov     r8, cs:off_180006050
0x1800023f6  lea     edx, [rax+2]
0x1800023f9  mov     rcx, cs:RegHandle
0x180002400  movzx   r9d, word ptr [r8]
0x180002404  call    cs:__imp_EventSetInformation
0x18000240b  nop     dword ptr [rax+rax+00h]
0x180002410  lea     rdx, ?ServiceCtrlHandler@@YAXK@Z; lpHandlerProc
0x180002417  lea     rcx, ServiceName; "SMPHost"
0x18000241e  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180002425  nop     dword ptr [rax+rax+00h]
0x18000242a  mov     cs:?g_ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_ServiceStatusHandle
0x180002431  test    rax, rax
0x180002434  jnz     short loc_1800024A3
0x180002436  mov     eax, cs:dword_180006048
0x18000243c  cmp     eax, 5
0x18000243f  jbe     loc_1800024CC
0x180002445  mov     rcx, cs:qword_180006060
0x18000244c  mov     rdx, 400000000000h
0x180002456  mov     rax, cs:qword_180006058
0x18000245d  test    rdx, rax
0x180002460  jz      short loc_1800024CC
0x180002462  mov     rax, rcx
0x180002465  and     rax, rdx
0x180002468  cmp     rax, rcx
0x18000246b  jnz     short loc_1800024CC
0x18000246d  lea     rax, aServicemain_0; "ServiceMain"
0x180002474  mov     [rsp+58h+var_28], 56h ; 'V'
0x18000247c  mov     qword ptr [rsp+58h+ProviderId.Data1], rax
0x180002481  lea     rdx, word_18000493E
0x180002488  lea     rax, [rsp+58h+var_28]
0x18000248d  mov     [rsp+58h+var_30], rax
0x180002492  lea     rax, [rsp+58h+ProviderId]
0x180002497  mov     [rsp+58h+var_38], rax
0x18000249c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800024a1  jmp     short loc_1800024CC
0x1800024a3  mov     ecx, 2; unsigned int
0x1800024a8  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A, 10h; _SERVICE_STATUS g_ServiceStatus
0x1800024b2  mov     r8d, 0BB8h; unsigned int
0x1800024b8  mov     cs:dword_1800067E0, 0
0x1800024c2  call    ?ReportServiceStatus@@YAXKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x1800024c7  call    ?ServiceInit@@YAXKPEAPEAG@Z; ServiceInit(ulong,ushort * *)
0x1800024cc  mov     rcx, [rsp+58h+var_10]
0x1800024d1  xor     rcx, rsp; StackCookie
0x1800024d4  call    __security_check_cookie
0x1800024d9  add     rsp, 58h
0x1800024dd  retn
```
