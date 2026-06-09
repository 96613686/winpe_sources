# InitializeService

- ea: `0x180006960`
- end: `0x180006b3e`
- name: `InitializeService`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005e30`

## callees

- `0x180003bc0`
- `0x180006960`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800069f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800069f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ab7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ab7`

## string_xrefs

- `0x1800069a9`: `InitializeService`
- `0x180006add`: `InitializeService`
- `0x180006a37`: `CreateEvent fails with error %d`
- `0x180006a72`: `InitializeTransport completes with (%d)`

## pseudocode

```c
__int64 InitializeService()
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned int v2; // ebx
  __int64 *v3; // rdx
  int v5; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString(&v5, L"Entering %ws", L"InitializeService");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v5);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)SstpSvcGlobals + 3) = EventW;
  if ( EventW )
  {
    v2 = InitializeTransport();
    if ( v2 )
    {
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v5) = 0;
        FormatRRASErrorString(&v5, L"InitializeTransport completes with (%d)", v2);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v5);
      }
      CloseHandle(*((HANDLE *)SstpSvcGlobals + 3));
      *((_QWORD *)SstpSvcGlobals + 3) = 0;
    }
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(&v5, L"LEaving %ws", L"InitializeService");
      if ( (byte_18002E903 & 0x10) != 0 )
      {
        v3 = RasSSTPSvcTraceInfo;
        goto LABEL_16;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(&v5, L"CreateEvent fails with error %d", LastError);
      if ( (byte_18002E903 & 8) != 0 )
      {
        v3 = RasSSTPSvcTraceError;
LABEL_16:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v3, &v5);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180006960  mov     [rsp-8+arg_0], rbx
0x180006965  push    rbp
0x180006966  lea     rbp, [rsp-730h]
0x18000696e  sub     rsp, 830h
0x180006975  mov     rax, cs:__security_cookie
0x18000697c  xor     rax, rsp
0x18000697f  mov     [rbp+730h+var_10], rax
0x180006986  xor     eax, eax
0x180006988  lea     rcx, [rsp+830h+var_80C]; void *
0x18000698d  xor     edx, edx; Val
0x18000698f  mov     [rsp+830h+var_810], eax
0x180006993  mov     r8d, 7FCh; Size
0x180006999  call    memset_0
0x18000699e  test    cs:byte_18002E903, 10h
0x1800069a5  jz      short loc_1800069E7
0x1800069a7  xor     eax, eax
0x1800069a9  lea     r8, aInitializeserv; "InitializeService"
0x1800069b0  lea     rdx, aEnteringWs; "Entering %ws"
0x1800069b7  mov     word ptr [rsp+830h+var_810], ax
0x1800069bc  lea     rcx, [rsp+830h+var_810]
0x1800069c1  call    FormatRRASErrorString
0x1800069c6  test    cs:byte_18002E903, 10h
0x1800069cd  jz      short loc_1800069E7
0x1800069cf  lea     r8, [rsp+830h+var_810]
0x1800069d4  lea     rdx, RasSSTPSvcTraceInfo
0x1800069db  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800069e2  call    McTemplateU0z_EventWriteTransfer
0x1800069e7  xor     r9d, r9d; lpName
0x1800069ea  xor     r8d, r8d; bInitialState
0x1800069ed  xor     edx, edx; bManualReset
0x1800069ef  xor     ecx, ecx; lpEventAttributes
0x1800069f1  call    cs:__imp_CreateEventW
0x1800069f8  nop     dword ptr [rax+rax+00h]
0x1800069fd  mov     rcx, cs:SstpSvcGlobals
0x180006a04  mov     [rcx+18h], rax
0x180006a08  test    rax, rax
0x180006a0b  jnz     short loc_180006A5C
0x180006a0d  call    cs:__imp_GetLastError
0x180006a14  nop     dword ptr [rax+rax+00h]
0x180006a19  test    cs:byte_18002E903, 8
0x180006a20  mov     ebx, eax
0x180006a22  jz      loc_180006B1B
0x180006a28  xor     edx, edx
0x180006a2a  lea     rcx, [rsp+830h+var_810]
0x180006a2f  mov     word ptr [rsp+830h+var_810], dx
0x180006a34  mov     r8d, eax
0x180006a37  lea     rdx, aCreateeventFai; "CreateEvent fails with error %d"
0x180006a3e  call    FormatRRASErrorString
0x180006a43  test    cs:byte_18002E903, 8
0x180006a4a  jz      loc_180006B1B
0x180006a50  lea     rdx, RasSSTPSvcTraceError
0x180006a57  jmp     loc_180006B0A
0x180006a5c  call    InitializeTransport
0x180006a61  mov     ebx, eax
0x180006a63  test    eax, eax
0x180006a65  jz      short loc_180006AD2
0x180006a67  test    cs:byte_18002E903, 8
0x180006a6e  jz      short loc_180006AAC
0x180006a70  xor     eax, eax
0x180006a72  lea     rdx, aInitializetran; "InitializeTransport completes with (%d)"
0x180006a79  mov     r8d, ebx
0x180006a7c  mov     word ptr [rsp+830h+var_810], ax
0x180006a81  lea     rcx, [rsp+830h+var_810]
0x180006a86  call    FormatRRASErrorString
0x180006a8b  test    cs:byte_18002E903, 8
0x180006a92  jz      short loc_180006AAC
0x180006a94  lea     r8, [rsp+830h+var_810]
0x180006a99  lea     rdx, RasSSTPSvcTraceError
0x180006aa0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006aa7  call    McTemplateU0z_EventWriteTransfer
0x180006aac  mov     rcx, cs:SstpSvcGlobals
0x180006ab3  mov     rcx, [rcx+18h]; hObject
0x180006ab7  call    cs:__imp_CloseHandle
0x180006abe  nop     dword ptr [rax+rax+00h]
0x180006ac3  mov     rax, cs:SstpSvcGlobals
0x180006aca  mov     qword ptr [rax+18h], 0
0x180006ad2  test    cs:byte_18002E903, 10h
0x180006ad9  jz      short loc_180006B1B
0x180006adb  xor     eax, eax
0x180006add  lea     r8, aInitializeserv; "InitializeService"
0x180006ae4  lea     rdx, aLeavingWs; "LEaving %ws"
0x180006aeb  mov     word ptr [rsp+830h+var_810], ax
0x180006af0  lea     rcx, [rsp+830h+var_810]
0x180006af5  call    FormatRRASErrorString
0x180006afa  test    cs:byte_18002E903, 10h
0x180006b01  jz      short loc_180006B1B
0x180006b03  lea     rdx, RasSSTPSvcTraceInfo
0x180006b0a  lea     r8, [rsp+830h+var_810]
0x180006b0f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006b16  call    McTemplateU0z_EventWriteTransfer
0x180006b1b  mov     eax, ebx
0x180006b1d  mov     rcx, [rbp+730h+var_10]
0x180006b24  xor     rcx, rsp; StackCookie
0x180006b27  call    __security_check_cookie
0x180006b2c  mov     rbx, [rsp+830h+arg_0]
0x180006b34  add     rsp, 830h
0x180006b3b  pop     rbp
0x180006b3c  retn
```
