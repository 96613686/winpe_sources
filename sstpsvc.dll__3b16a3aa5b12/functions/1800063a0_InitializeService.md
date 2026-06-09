# InitializeService

- ea: `0x1800063a0`
- end: `0x18000656b`
- name: `InitializeService`
- size: `459`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005920`

## callees

- `0x180003920`
- `0x1800063a0`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006431`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006447`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064eb`

## string_xrefs

- `0x1800063e9`: `InitializeService`
- `0x18000650b`: `InitializeService`
- `0x18000646b`: `CreateEvent fails with error %d`
- `0x1800064a6`: `InitializeTransport completes with (%d)`

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
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString(&v5, L"Entering %ws", L"InitializeService");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v5);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)SstpSvcGlobals + 3) = EventW;
  if ( EventW )
  {
    v2 = InitializeTransport();
    if ( v2 )
    {
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v5) = 0;
        FormatRRASErrorString(&v5, L"InitializeTransport completes with (%d)", v2);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v5);
      }
      CloseHandle(*((HANDLE *)SstpSvcGlobals + 3));
      *((_QWORD *)SstpSvcGlobals + 3) = 0;
    }
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(&v5, L"LEaving %ws", L"InitializeService");
      if ( (byte_18002D803 & 0x10) != 0 )
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
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString(&v5, L"CreateEvent fails with error %d", LastError);
      if ( (byte_18002D803 & 8) != 0 )
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
0x1800063a0  mov     [rsp-8+arg_0], rbx
0x1800063a5  push    rbp
0x1800063a6  lea     rbp, [rsp-730h]
0x1800063ae  sub     rsp, 830h
0x1800063b5  mov     rax, cs:__security_cookie
0x1800063bc  xor     rax, rsp
0x1800063bf  mov     [rbp+730h+var_10], rax
0x1800063c6  xor     eax, eax
0x1800063c8  lea     rcx, [rsp+830h+var_80C]; void *
0x1800063cd  xor     edx, edx; Val
0x1800063cf  mov     [rsp+830h+var_810], eax
0x1800063d3  mov     r8d, 7FCh; Size
0x1800063d9  call    memset_0
0x1800063de  test    cs:byte_18002D803, 10h
0x1800063e5  jz      short loc_180006427
0x1800063e7  xor     eax, eax
0x1800063e9  lea     r8, aInitializeserv; "InitializeService"
0x1800063f0  lea     rdx, aEnteringWs; "Entering %ws"
0x1800063f7  mov     word ptr [rsp+830h+var_810], ax
0x1800063fc  lea     rcx, [rsp+830h+var_810]
0x180006401  call    FormatRRASErrorString
0x180006406  test    cs:byte_18002D803, 10h
0x18000640d  jz      short loc_180006427
0x18000640f  lea     r8, [rsp+830h+var_810]
0x180006414  lea     rdx, RasSSTPSvcTraceInfo
0x18000641b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006422  call    McTemplateU0z_EventWriteTransfer
0x180006427  xor     r9d, r9d; lpName
0x18000642a  xor     r8d, r8d; bInitialState
0x18000642d  xor     edx, edx; bManualReset
0x18000642f  xor     ecx, ecx; lpEventAttributes
0x180006431  call    cs:__imp_CreateEventW
0x180006437  mov     rcx, cs:SstpSvcGlobals
0x18000643e  mov     [rcx+18h], rax
0x180006442  test    rax, rax
0x180006445  jnz     short loc_180006490
0x180006447  call    cs:__imp_GetLastError
0x18000644d  test    cs:byte_18002D803, 8
0x180006454  mov     ebx, eax
0x180006456  jz      loc_180006549
0x18000645c  xor     edx, edx
0x18000645e  lea     rcx, [rsp+830h+var_810]
0x180006463  mov     word ptr [rsp+830h+var_810], dx
0x180006468  mov     r8d, eax
0x18000646b  lea     rdx, aCreateeventFai; "CreateEvent fails with error %d"
0x180006472  call    FormatRRASErrorString
0x180006477  test    cs:byte_18002D803, 8
0x18000647e  jz      loc_180006549
0x180006484  lea     rdx, RasSSTPSvcTraceError
0x18000648b  jmp     loc_180006538
0x180006490  call    InitializeTransport
0x180006495  mov     ebx, eax
0x180006497  test    eax, eax
0x180006499  jz      short loc_180006500
0x18000649b  test    cs:byte_18002D803, 8
0x1800064a2  jz      short loc_1800064E0
0x1800064a4  xor     eax, eax
0x1800064a6  lea     rdx, aInitializetran; "InitializeTransport completes with (%d)"
0x1800064ad  mov     r8d, ebx
0x1800064b0  mov     word ptr [rsp+830h+var_810], ax
0x1800064b5  lea     rcx, [rsp+830h+var_810]
0x1800064ba  call    FormatRRASErrorString
0x1800064bf  test    cs:byte_18002D803, 8
0x1800064c6  jz      short loc_1800064E0
0x1800064c8  lea     r8, [rsp+830h+var_810]
0x1800064cd  lea     rdx, RasSSTPSvcTraceError
0x1800064d4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800064db  call    McTemplateU0z_EventWriteTransfer
0x1800064e0  mov     rcx, cs:SstpSvcGlobals
0x1800064e7  mov     rcx, [rcx+18h]; hObject
0x1800064eb  call    cs:__imp_CloseHandle
0x1800064f1  mov     rax, cs:SstpSvcGlobals
0x1800064f8  mov     qword ptr [rax+18h], 0
0x180006500  test    cs:byte_18002D803, 10h
0x180006507  jz      short loc_180006549
0x180006509  xor     eax, eax
0x18000650b  lea     r8, aInitializeserv; "InitializeService"
0x180006512  lea     rdx, aLeavingWs; "LEaving %ws"
0x180006519  mov     word ptr [rsp+830h+var_810], ax
0x18000651e  lea     rcx, [rsp+830h+var_810]
0x180006523  call    FormatRRASErrorString
0x180006528  test    cs:byte_18002D803, 10h
0x18000652f  jz      short loc_180006549
0x180006531  lea     rdx, RasSSTPSvcTraceInfo
0x180006538  lea     r8, [rsp+830h+var_810]
0x18000653d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006544  call    McTemplateU0z_EventWriteTransfer
0x180006549  mov     eax, ebx
0x18000654b  mov     rcx, [rbp+730h+var_10]
0x180006552  xor     rcx, rsp; StackCookie
0x180006555  call    __security_check_cookie
0x18000655a  mov     rbx, [rsp+830h+arg_0]
0x180006562  add     rsp, 830h
0x180006569  pop     rbp
0x18000656a  retn
```
