# InitiateSstpResponse

- ea: `0x18000b9fc`
- end: `0x18000bc6f`
- name: `InitiateSstpResponse`
- size: `627`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001240`
- `0x18000df30`

## callees

- `0x180002908`
- `0x180002d40`
- `0x18000827c`
- `0x180008360`
- `0x18000b9fc`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bbec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bbec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb20`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000bbe3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000bbe3`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000baf8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000baf8`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000bb74`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000bb74`

## pseudocode

```c
ULONG __fastcall InitiateSstpResponse(__int64 a1)
{
  __int64 Overlapped; // rbx
  PTP_IO *v3; // rcx
  ULONG result; // eax
  struct _HTTP_CACHE_POLICY CachePolicy; // [rsp+50h] [rbp-B0h] BYREF
  int v6; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v7[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  CachePolicy = 0;
  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"Entering %ws", L"InitiateSstpResponse");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
  Overlapped = *(_QWORD *)(a1 + 256);
  *(_OWORD *)Overlapped = 0;
  *(_OWORD *)(Overlapped + 16) = 0;
  *(_DWORD *)(Overlapped + 32) = 17773;
  memset_0((void *)(Overlapped + 96), 0, 0x238u);
  v3 = (PTP_IO *)SstpSvcGlobals;
  *(_DWORD *)(Overlapped + 100) = 65537;
  *(_WORD *)(Overlapped + 104) = 200;
  *(_WORD *)(Overlapped + 328) = 20;
  *(_QWORD *)(Overlapped + 336) = "18446744073709551615";
  StartThreadpoolIo(v3[21]);
  CachePolicy.Policy = HttpCachePolicyNocache;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  *(_DWORD *)(a1 + 252) &= ~2u;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  result = HttpSendHttpResponse(
             *((HANDLE *)SstpSvcGlobals + 8),
             *(_QWORD *)(a1 + 272),
             2u,
             (PHTTP_RESPONSE)(Overlapped + 96),
             &CachePolicy,
             0,
             0,
             0,
             (LPOVERLAPPED)Overlapped,
             0);
  if ( result != 997 && result )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(&v6, L"CoId=%hs:Terminate: SendResponse fails with error %d", a1 + 552, result);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
    }
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    InitiateCallContextCleanup(a1, 1u);
    result = DereferenceRefCount(a1 + 208);
  }
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    result = FormatRRASErrorString(&v6, L"LEaving %ws", L"InitiateSstpResponse");
    if ( (byte_18002D803 & 0x10) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000b9fc  push    rbp
0x18000b9fe  push    rbx
0x18000b9ff  push    rsi
0x18000ba00  push    rdi
0x18000ba01  push    r14
0x18000ba03  push    r15
0x18000ba05  lea     rbp, [rsp-778h]
0x18000ba0d  sub     rsp, 878h
0x18000ba14  mov     rax, cs:__security_cookie
0x18000ba1b  xor     rax, rsp
0x18000ba1e  mov     [rbp+7A0h+var_40], rax
0x18000ba25  mov     rsi, rcx
0x18000ba28  mov     qword ptr [rsp+8A0h+var_850.Policy], 0
0x18000ba31  xor     eax, eax
0x18000ba33  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18000ba38  xor     edx, edx; Val
0x18000ba3a  mov     [rsp+8A0h+var_840], eax
0x18000ba3e  mov     r8d, 7FCh; Size
0x18000ba44  call    memset_0
0x18000ba49  test    cs:byte_18002D803, 10h
0x18000ba50  jz      short loc_18000BA92
0x18000ba52  xor     eax, eax
0x18000ba54  lea     r8, aInitiatesstpre; "InitiateSstpResponse"
0x18000ba5b  lea     rdx, aEnteringWs; "Entering %ws"
0x18000ba62  mov     word ptr [rsp+8A0h+var_840], ax
0x18000ba67  lea     rcx, [rsp+8A0h+var_840]
0x18000ba6c  call    FormatRRASErrorString
0x18000ba71  test    cs:byte_18002D803, 10h
0x18000ba78  jz      short loc_18000BA92
0x18000ba7a  lea     r8, [rsp+8A0h+var_840]
0x18000ba7f  lea     rdx, RasSSTPSvcTraceInfo
0x18000ba86  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ba8d  call    McTemplateU0z_EventWriteTransfer
0x18000ba92  lea     r14, [rsi+0D0h]
0x18000ba99  lock inc dword ptr [r14]
0x18000ba9d  mov     rbx, [rsi+100h]
0x18000baa4  xorps   xmm0, xmm0
0x18000baa7  xor     edx, edx; Val
0x18000baa9  mov     r8d, 238h; Size
0x18000baaf  movups  xmmword ptr [rbx], xmm0
0x18000bab2  lea     rcx, [rbx+60h]; void *
0x18000bab6  movups  xmmword ptr [rbx+10h], xmm0
0x18000baba  mov     dword ptr [rbx+20h], 456Dh
0x18000bac1  call    memset_0
0x18000bac6  mov     rcx, cs:SstpSvcGlobals
0x18000bacd  lea     rax, a18446744073709; "18446744073709551615"
0x18000bad4  mov     dword ptr [rbx+64h], 10001h
0x18000badb  mov     word ptr [rbx+68h], 0C8h
0x18000bae1  mov     word ptr [rbx+148h], 14h
0x18000baea  mov     [rbx+150h], rax
0x18000baf1  mov     rcx, [rcx+0A8h]; pio
0x18000baf8  call    cs:__imp_StartThreadpoolIo
0x18000bafe  lea     r15, [rsi+120h]
0x18000bb05  mov     [rsp+8A0h+var_850.Policy], 0
0x18000bb0d  mov     rcx, r15; lpCriticalSection
0x18000bb10  call    cs:__imp_EnterCriticalSection
0x18000bb16  and     dword ptr [rsi+0FCh], 0FFFFFFFDh
0x18000bb1d  mov     rcx, r15; lpCriticalSection
0x18000bb20  call    cs:__imp_LeaveCriticalSection
0x18000bb26  mov     rcx, cs:SstpSvcGlobals
0x18000bb2d  lea     rax, [rsp+8A0h+var_850]
0x18000bb32  mov     rdx, [rsi+110h]; RequestId
0x18000bb39  lea     r9, [rbx+60h]; HttpResponse
0x18000bb3d  mov     [rsp+8A0h+LogData], 0; LogData
0x18000bb46  mov     r8d, 2; Flags
0x18000bb4c  mov     [rsp+8A0h+Overlapped], rbx; Overlapped
0x18000bb51  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000bb55  mov     [rsp+8A0h+Reserved2], 0; Reserved2
0x18000bb5d  mov     [rsp+8A0h+Reserved1], 0; Reserved1
0x18000bb66  mov     [rsp+8A0h+BytesSent], 0; BytesSent
0x18000bb6f  mov     [rsp+8A0h+CachePolicy], rax; CachePolicy
0x18000bb74  call    cs:__imp_HttpSendHttpResponse
0x18000bb7a  cmp     eax, 3E5h
0x18000bb7f  jz      loc_18000BC07
0x18000bb85  test    eax, eax
0x18000bb87  jz      short loc_18000BC07
0x18000bb89  test    cs:byte_18002D803, 8
0x18000bb90  jz      short loc_18000BBD5
0x18000bb92  xor     ecx, ecx
0x18000bb94  lea     r8, [rsi+228h]
0x18000bb9b  mov     word ptr [rsp+8A0h+var_840], cx
0x18000bba0  lea     rdx, aCoidHsTerminat; "CoId=%hs:Terminate: SendResponse fails "...
0x18000bba7  lea     rcx, [rsp+8A0h+var_840]
0x18000bbac  mov     r9d, eax
0x18000bbaf  call    FormatRRASErrorString
0x18000bbb4  test    cs:byte_18002D803, 8
0x18000bbbb  jz      short loc_18000BBD5
0x18000bbbd  lea     r8, [rsp+8A0h+var_840]
0x18000bbc2  lea     rdx, RasSSTPSvcTraceError
0x18000bbc9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bbd0  call    McTemplateU0z_EventWriteTransfer
0x18000bbd5  mov     rcx, cs:SstpSvcGlobals
0x18000bbdc  mov     rcx, [rcx+0A8h]; pio
0x18000bbe3  call    cs:__imp_CancelThreadpoolIo
0x18000bbe9  mov     rcx, r15; lpCriticalSection
0x18000bbec  call    cs:__imp_EnterCriticalSection
0x18000bbf2  mov     edx, 1
0x18000bbf7  mov     rcx, rsi
0x18000bbfa  call    InitiateCallContextCleanup
0x18000bbff  mov     rcx, r14
0x18000bc02  call    DereferenceRefCount
0x18000bc07  test    cs:byte_18002D803, 10h
0x18000bc0e  jz      short loc_18000BC50
0x18000bc10  xor     eax, eax
0x18000bc12  lea     r8, aInitiatesstpre; "InitiateSstpResponse"
0x18000bc19  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000bc20  mov     word ptr [rsp+8A0h+var_840], ax
0x18000bc25  lea     rcx, [rsp+8A0h+var_840]
0x18000bc2a  call    FormatRRASErrorString
0x18000bc2f  test    cs:byte_18002D803, 10h
0x18000bc36  jz      short loc_18000BC50
0x18000bc38  lea     r8, [rsp+8A0h+var_840]
0x18000bc3d  lea     rdx, RasSSTPSvcTraceInfo
0x18000bc44  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000bc4b  call    McTemplateU0z_EventWriteTransfer
0x18000bc50  mov     rcx, [rbp+7A0h+var_40]
0x18000bc57  xor     rcx, rsp; StackCookie
0x18000bc5a  call    __security_check_cookie
0x18000bc5f  add     rsp, 878h
0x18000bc66  pop     r15
0x18000bc68  pop     r14
0x18000bc6a  pop     rdi
0x18000bc6b  pop     rsi
0x18000bc6c  pop     rbx
0x18000bc6d  pop     rbp
0x18000bc6e  retn
```
