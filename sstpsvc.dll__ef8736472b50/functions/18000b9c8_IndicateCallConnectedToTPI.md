# IndicateCallConnectedToTPI

- ea: `0x18000b9c8`
- end: `0x18000bd1c`
- name: `IndicateCallConnectedToTPI`
- size: `852`
- prototype: `__int64 __fastcall(LPOVERLAPPED)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000afb0`

## callees

- `0x180002320`
- `0x180002aac`
- `0x180002f50`
- `0x180003620`
- `0x1800070b0`
- `0x180007520`
- `0x1800089dc`
- `0x180008b90`
- `0x18000b9c8`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ba6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bc80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ba6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bc80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ba83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ba83`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000bb63`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000bc19`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000bb63`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000bc19`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000bab7`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000bbbb`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000bab7`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000bbbb`
- `HTTPAPI!HttpWaitForDisconnect` at `0x18000bbea`
- `HTTPAPI!HttpWaitForDisconnect` at `0x18000bbea`

## string_xrefs

- `0x18000bb20`: `CoId=%hs:IncomingCallConnected request fails with %d`

## pseudocode

```c
__int64 __fastcall IndicateCallConnectedToTPI(LPOVERLAPPED a1)
{
  unsigned int v2; // eax
  __int64 result; // rax
  ULONG v4; // eax
  ULONG v5; // edi
  int v6; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v7[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"Entering %ws", L"IndicateCallConnectedToTPI");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  LODWORD(a1[1].Internal) = 17774;
  *(_OWORD *)&a1->Internal = 0;
  *(_OWORD *)&a1->Offset = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)&a1[9]);
  HIDWORD(a1[7].hEvent) |= 0x8000u;
  LeaveCriticalSection((LPCRITICAL_SECTION)&a1[9]);
  if ( (unsigned int)IsProxyCall(a1)
    || (_InterlockedIncrement((volatile signed __int32 *)&a1[6].16),
        StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36)),
        v2 = AsyncDeviceControl(*((_QWORD *)SstpSvcGlobals + 35), 1212460, (int)a1 + 240, 4, 0, 0, a1),
        v2 == 997) )
  {
    StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    _InterlockedIncrement((volatile signed __int32 *)&a1[6].16);
    v4 = HttpWaitForDisconnect(*((HANDLE *)SstpSvcGlobals + 8), (HTTP_CONNECTION_ID)a1[8].hEvent, a1 + 4);
    v5 = v4;
    if ( !v4 || v4 == 997 )
    {
      PostReceiveOnCall(a1);
      result = IsProxyCall(a1);
      if ( !(_DWORD)result )
        result = PostSendNotificationRequest(a1);
    }
    else
    {
      CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v6) = 0;
        FormatRRASErrorString(&v6, L"CoId=%hs:WaitForDisconnect fails with error %d", &a1[17].InternalHigh, v5);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
      }
      DereferenceRefCount(&a1[6].Offset);
      EnterCriticalSection((LPCRITICAL_SECTION)&a1[9]);
      result = InitiateCallContextCleanup(a1, 1);
    }
  }
  else
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(&v6, L"CoId=%hs:IncomingCallConnected request fails with %d", &a1[17].InternalHigh, v2);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
    }
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
    EnterCriticalSection((LPCRITICAL_SECTION)&a1[9]);
    HIDWORD(a1[7].hEvent) = HIDWORD(a1[7].hEvent) & 0xFFFF7DDF | 0x200;
    InitiateCallContextCleanup(a1, 2);
    result = DereferenceRefCount(&a1[6].Offset);
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    result = FormatRRASErrorString(&v6, L"LEaving %ws", L"IndicateCallConnectedToTPI");
    if ( (byte_18002E903 & 0x10) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000b9c8  push    rbp
0x18000b9ca  push    rbx
0x18000b9cb  push    rsi
0x18000b9cc  push    rdi
0x18000b9cd  lea     rbp, [rsp-758h]
0x18000b9d5  sub     rsp, 858h
0x18000b9dc  mov     rax, cs:__security_cookie
0x18000b9e3  xor     rax, rsp
0x18000b9e6  mov     [rbp+770h+var_30], rax
0x18000b9ed  mov     rbx, rcx
0x18000b9f0  xor     eax, eax
0x18000b9f2  lea     rcx, [rsp+870h+var_82C]; void *
0x18000b9f7  mov     [rsp+870h+var_830], eax
0x18000b9fb  xor     edx, edx; Val
0x18000b9fd  mov     r8d, 7FCh; Size
0x18000ba03  call    memset_0
0x18000ba08  test    cs:byte_18002E903, 10h
0x18000ba0f  jz      short loc_18000BA51
0x18000ba11  xor     eax, eax
0x18000ba13  lea     r8, aIndicatecallco; "IndicateCallConnectedToTPI"
0x18000ba1a  lea     rdx, aEnteringWs; "Entering %ws"
0x18000ba21  mov     word ptr [rsp+870h+var_830], ax
0x18000ba26  lea     rcx, [rsp+870h+var_830]
0x18000ba2b  call    FormatRRASErrorString
0x18000ba30  test    cs:byte_18002E903, 10h
0x18000ba37  jz      short loc_18000BA51
0x18000ba39  lea     r8, [rsp+870h+var_830]
0x18000ba3e  lea     rdx, RasSSTPSvcTraceInfo
0x18000ba45  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ba4c  call    McTemplateU0z_EventWriteTransfer
0x18000ba51  xorps   xmm0, xmm0
0x18000ba54  mov     dword ptr [rbx+20h], 456Eh
0x18000ba5b  movups  xmmword ptr [rbx], xmm0
0x18000ba5e  lea     rdi, [rbx+120h]
0x18000ba65  mov     rcx, rdi; lpCriticalSection
0x18000ba68  movups  xmmword ptr [rbx+10h], xmm0
0x18000ba6c  call    cs:__imp_EnterCriticalSection
0x18000ba73  nop     dword ptr [rax+rax+00h]
0x18000ba78  bts     dword ptr [rbx+0FCh], 0Fh
0x18000ba80  mov     rcx, rdi; lpCriticalSection
0x18000ba83  call    cs:__imp_LeaveCriticalSection
0x18000ba8a  nop     dword ptr [rax+rax+00h]
0x18000ba8f  mov     rcx, rbx
0x18000ba92  call    IsProxyCall
0x18000ba97  test    eax, eax
0x18000ba99  jnz     loc_18000BBAD
0x18000ba9f  lea     rsi, [rbx+0D0h]
0x18000baa6  lock inc dword ptr [rsi]
0x18000baa9  mov     rcx, cs:SstpSvcGlobals
0x18000bab0  mov     rcx, [rcx+120h]; pio
0x18000bab7  call    cs:__imp_StartThreadpoolIo
0x18000babe  nop     dword ptr [rax+rax+00h]
0x18000bac3  mov     rcx, cs:SstpSvcGlobals
0x18000baca  lea     r8, [rbx+0F0h]; int
0x18000bad1  mov     [rsp+870h+var_840], rbx; LPOVERLAPPED
0x18000bad6  mov     edx, 12802Ch; int
0x18000badb  mov     [rsp+870h+var_848], 0; DWORD
0x18000bae3  mov     r9d, 4; int
0x18000bae9  mov     [rsp+870h+var_850], 0; LPVOID
0x18000baf2  mov     rcx, [rcx+118h]; int
0x18000baf9  call    AsyncDeviceControl
0x18000bafe  cmp     eax, 3E5h
0x18000bb03  jz      loc_18000BBAD
0x18000bb09  test    cs:byte_18002E903, 8
0x18000bb10  jz      short loc_18000BB55
0x18000bb12  xor     ecx, ecx
0x18000bb14  lea     r8, [rbx+228h]
0x18000bb1b  mov     word ptr [rsp+870h+var_830], cx
0x18000bb20  lea     rdx, aCoidHsIncoming; "CoId=%hs:IncomingCallConnected request "...
0x18000bb27  lea     rcx, [rsp+870h+var_830]
0x18000bb2c  mov     r9d, eax
0x18000bb2f  call    FormatRRASErrorString
0x18000bb34  test    cs:byte_18002E903, 8
0x18000bb3b  jz      short loc_18000BB55
0x18000bb3d  lea     r8, [rsp+870h+var_830]
0x18000bb42  lea     rdx, RasSSTPSvcTraceError
0x18000bb49  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bb50  call    McTemplateU0z_EventWriteTransfer
0x18000bb55  mov     rcx, cs:SstpSvcGlobals
0x18000bb5c  mov     rcx, [rcx+120h]; pio
0x18000bb63  call    cs:__imp_CancelThreadpoolIo
0x18000bb6a  nop     dword ptr [rax+rax+00h]
0x18000bb6f  mov     rcx, rdi; lpCriticalSection
0x18000bb72  call    cs:__imp_EnterCriticalSection
0x18000bb79  nop     dword ptr [rax+rax+00h]
0x18000bb7e  mov     eax, [rbx+0FCh]
0x18000bb84  mov     edx, 2
0x18000bb89  and     eax, 0FFFF7FDFh
0x18000bb8e  mov     rcx, rbx
0x18000bb91  bts     eax, 9
0x18000bb95  mov     [rbx+0FCh], eax
0x18000bb9b  call    InitiateCallContextCleanup
0x18000bba0  mov     rcx, rsi
0x18000bba3  call    DereferenceRefCount
0x18000bba8  jmp     loc_18000BCB7
0x18000bbad  mov     rcx, cs:SstpSvcGlobals
0x18000bbb4  mov     rcx, [rcx+0A8h]; pio
0x18000bbbb  call    cs:__imp_StartThreadpoolIo
0x18000bbc2  nop     dword ptr [rax+rax+00h]
0x18000bbc7  lea     rsi, [rbx+0D0h]
0x18000bbce  lock inc dword ptr [rsi]
0x18000bbd1  mov     rcx, cs:SstpSvcGlobals
0x18000bbd8  lea     r8, [rbx+80h]; Overlapped
0x18000bbdf  mov     rdx, [rbx+118h]; ConnectionId
0x18000bbe6  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000bbea  call    cs:__imp_HttpWaitForDisconnect
0x18000bbf1  nop     dword ptr [rax+rax+00h]
0x18000bbf6  mov     edi, eax
0x18000bbf8  test    eax, eax
0x18000bbfa  jz      loc_18000BC9B
0x18000bc00  cmp     eax, 3E5h
0x18000bc05  jz      loc_18000BC9B
0x18000bc0b  mov     rcx, cs:SstpSvcGlobals
0x18000bc12  mov     rcx, [rcx+0A8h]; pio
0x18000bc19  call    cs:__imp_CancelThreadpoolIo
0x18000bc20  nop     dword ptr [rax+rax+00h]
0x18000bc25  test    cs:byte_18002E903, 8
0x18000bc2c  jz      short loc_18000BC71
0x18000bc2e  xor     eax, eax
0x18000bc30  lea     r8, [rbx+228h]
0x18000bc37  mov     r9d, edi
0x18000bc3a  mov     word ptr [rsp+870h+var_830], ax
0x18000bc3f  lea     rdx, aCoidHsWaitford; "CoId=%hs:WaitForDisconnect fails with e"...
0x18000bc46  lea     rcx, [rsp+870h+var_830]
0x18000bc4b  call    FormatRRASErrorString
0x18000bc50  test    cs:byte_18002E903, 8
0x18000bc57  jz      short loc_18000BC71
0x18000bc59  lea     r8, [rsp+870h+var_830]
0x18000bc5e  lea     rdx, RasSSTPSvcTraceError
0x18000bc65  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bc6c  call    McTemplateU0z_EventWriteTransfer
0x18000bc71  mov     rcx, rsi
0x18000bc74  call    DereferenceRefCount
0x18000bc79  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000bc80  call    cs:__imp_EnterCriticalSection
0x18000bc87  nop     dword ptr [rax+rax+00h]
0x18000bc8c  mov     edx, 1
0x18000bc91  mov     rcx, rbx
0x18000bc94  call    InitiateCallContextCleanup
0x18000bc99  jmp     short loc_18000BCB7
0x18000bc9b  mov     rcx, rbx
0x18000bc9e  call    PostReceiveOnCall
0x18000bca3  mov     rcx, rbx
0x18000bca6  call    IsProxyCall
0x18000bcab  test    eax, eax
0x18000bcad  jnz     short loc_18000BCB7
0x18000bcaf  mov     rcx, rbx
0x18000bcb2  call    PostSendNotificationRequest
0x18000bcb7  test    cs:byte_18002E903, 10h
0x18000bcbe  jz      short loc_18000BD00
0x18000bcc0  xor     eax, eax
0x18000bcc2  lea     r8, aIndicatecallco; "IndicateCallConnectedToTPI"
0x18000bcc9  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000bcd0  mov     word ptr [rsp+870h+var_830], ax
0x18000bcd5  lea     rcx, [rsp+870h+var_830]
0x18000bcda  call    FormatRRASErrorString
0x18000bcdf  test    cs:byte_18002E903, 10h
0x18000bce6  jz      short loc_18000BD00
0x18000bce8  lea     r8, [rsp+870h+var_830]
0x18000bced  lea     rdx, RasSSTPSvcTraceInfo
0x18000bcf4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bcfb  call    McTemplateU0z_EventWriteTransfer
0x18000bd00  mov     rcx, [rbp+770h+var_30]
0x18000bd07  xor     rcx, rsp; StackCookie
0x18000bd0a  call    __security_check_cookie
0x18000bd0f  add     rsp, 858h
0x18000bd16  pop     rdi
0x18000bd17  pop     rsi
0x18000bd18  pop     rbx
0x18000bd19  pop     rbp
0x18000bd1a  retn
```
