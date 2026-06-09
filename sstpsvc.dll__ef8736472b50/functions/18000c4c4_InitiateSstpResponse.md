# InitiateSstpResponse

- ea: `0x18000c4c4`
- end: `0x18000c760`
- name: `InitiateSstpResponse`
- size: `668`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800012b0`
- `0x18000ebd0`

## callees

- `0x180002aac`
- `0x180002f50`
- `0x1800089dc`
- `0x180008b90`
- `0x18000c4c4`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c5de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c5de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c5f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c5f4`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000c6c7`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000c6c7`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000c5c0`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000c5c0`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000c64e`
- `HTTPAPI!HttpSendHttpResponse` at `0x18000c64e`

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
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"Entering %ws", L"InitiateSstpResponse");
    if ( (byte_18002E903 & 0x10) != 0 )
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
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(&v6, L"CoId=%hs:Terminate: SendResponse fails with error %d", a1 + 552, result);
      if ( (byte_18002E903 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
    }
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    InitiateCallContextCleanup(a1, 1u);
    result = DereferenceRefCount(a1 + 208);
  }
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    result = FormatRRASErrorString(&v6, L"LEaving %ws", L"InitiateSstpResponse");
    if ( (byte_18002E903 & 0x10) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000c4c4  push    rbp
0x18000c4c6  push    rbx
0x18000c4c7  push    rsi
0x18000c4c8  push    rdi
0x18000c4c9  push    r14
0x18000c4cb  push    r15
0x18000c4cd  lea     rbp, [rsp-778h]
0x18000c4d5  sub     rsp, 878h
0x18000c4dc  mov     rax, cs:__security_cookie
0x18000c4e3  xor     rax, rsp
0x18000c4e6  mov     [rbp+7A0h+var_40], rax
0x18000c4ed  mov     rsi, rcx
0x18000c4f0  mov     qword ptr [rsp+8A0h+var_850.Policy], 0
0x18000c4f9  xor     eax, eax
0x18000c4fb  lea     rcx, [rsp+8A0h+var_83C]; void *
0x18000c500  xor     edx, edx; Val
0x18000c502  mov     [rsp+8A0h+var_840], eax
0x18000c506  mov     r8d, 7FCh; Size
0x18000c50c  call    memset_0
0x18000c511  test    cs:byte_18002E903, 10h
0x18000c518  jz      short loc_18000C55A
0x18000c51a  xor     eax, eax
0x18000c51c  lea     r8, aInitiatesstpre; "InitiateSstpResponse"
0x18000c523  lea     rdx, aEnteringWs; "Entering %ws"
0x18000c52a  mov     word ptr [rsp+8A0h+var_840], ax
0x18000c52f  lea     rcx, [rsp+8A0h+var_840]
0x18000c534  call    FormatRRASErrorString
0x18000c539  test    cs:byte_18002E903, 10h
0x18000c540  jz      short loc_18000C55A
0x18000c542  lea     r8, [rsp+8A0h+var_840]
0x18000c547  lea     rdx, RasSSTPSvcTraceInfo
0x18000c54e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c555  call    McTemplateU0z_EventWriteTransfer
0x18000c55a  lea     r14, [rsi+0D0h]
0x18000c561  lock inc dword ptr [r14]
0x18000c565  mov     rbx, [rsi+100h]
0x18000c56c  xorps   xmm0, xmm0
0x18000c56f  xor     edx, edx; Val
0x18000c571  mov     r8d, 238h; Size
0x18000c577  movups  xmmword ptr [rbx], xmm0
0x18000c57a  lea     rcx, [rbx+60h]; void *
0x18000c57e  movups  xmmword ptr [rbx+10h], xmm0
0x18000c582  mov     dword ptr [rbx+20h], 456Dh
0x18000c589  call    memset_0
0x18000c58e  mov     rcx, cs:SstpSvcGlobals
0x18000c595  lea     rax, a18446744073709; "18446744073709551615"
0x18000c59c  mov     dword ptr [rbx+64h], 10001h
0x18000c5a3  mov     word ptr [rbx+68h], 0C8h
0x18000c5a9  mov     word ptr [rbx+148h], 14h
0x18000c5b2  mov     [rbx+150h], rax
0x18000c5b9  mov     rcx, [rcx+0A8h]; pio
0x18000c5c0  call    cs:__imp_StartThreadpoolIo
0x18000c5c7  nop     dword ptr [rax+rax+00h]
0x18000c5cc  lea     r15, [rsi+120h]
0x18000c5d3  mov     [rsp+8A0h+var_850.Policy], 0
0x18000c5db  mov     rcx, r15; lpCriticalSection
0x18000c5de  call    cs:__imp_EnterCriticalSection
0x18000c5e5  nop     dword ptr [rax+rax+00h]
0x18000c5ea  and     dword ptr [rsi+0FCh], 0FFFFFFFDh
0x18000c5f1  mov     rcx, r15; lpCriticalSection
0x18000c5f4  call    cs:__imp_LeaveCriticalSection
0x18000c5fb  nop     dword ptr [rax+rax+00h]
0x18000c600  mov     rcx, cs:SstpSvcGlobals
0x18000c607  lea     rax, [rsp+8A0h+var_850]
0x18000c60c  mov     rdx, [rsi+110h]; RequestId
0x18000c613  lea     r9, [rbx+60h]; HttpResponse
0x18000c617  mov     [rsp+8A0h+LogData], 0; LogData
0x18000c620  mov     r8d, 2; Flags
0x18000c626  mov     [rsp+8A0h+Overlapped], rbx; Overlapped
0x18000c62b  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000c62f  mov     [rsp+8A0h+Reserved2], 0; Reserved2
0x18000c637  mov     [rsp+8A0h+Reserved1], 0; Reserved1
0x18000c640  mov     [rsp+8A0h+BytesSent], 0; BytesSent
0x18000c649  mov     [rsp+8A0h+CachePolicy], rax; CachePolicy
0x18000c64e  call    cs:__imp_HttpSendHttpResponse
0x18000c655  nop     dword ptr [rax+rax+00h]
0x18000c65a  cmp     eax, 3E5h
0x18000c65f  jz      loc_18000C6F7
0x18000c665  test    eax, eax
0x18000c667  jz      loc_18000C6F7
0x18000c66d  test    cs:byte_18002E903, 8
0x18000c674  jz      short loc_18000C6B9
0x18000c676  xor     ecx, ecx
0x18000c678  lea     r8, [rsi+228h]
0x18000c67f  mov     word ptr [rsp+8A0h+var_840], cx
0x18000c684  lea     rdx, aCoidHsTerminat; "CoId=%hs:Terminate: SendResponse fails "...
0x18000c68b  lea     rcx, [rsp+8A0h+var_840]
0x18000c690  mov     r9d, eax
0x18000c693  call    FormatRRASErrorString
0x18000c698  test    cs:byte_18002E903, 8
0x18000c69f  jz      short loc_18000C6B9
0x18000c6a1  lea     r8, [rsp+8A0h+var_840]
0x18000c6a6  lea     rdx, RasSSTPSvcTraceError
0x18000c6ad  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c6b4  call    McTemplateU0z_EventWriteTransfer
0x18000c6b9  mov     rcx, cs:SstpSvcGlobals
0x18000c6c0  mov     rcx, [rcx+0A8h]; pio
0x18000c6c7  call    cs:__imp_CancelThreadpoolIo
0x18000c6ce  nop     dword ptr [rax+rax+00h]
0x18000c6d3  mov     rcx, r15; lpCriticalSection
0x18000c6d6  call    cs:__imp_EnterCriticalSection
0x18000c6dd  nop     dword ptr [rax+rax+00h]
0x18000c6e2  mov     edx, 1
0x18000c6e7  mov     rcx, rsi
0x18000c6ea  call    InitiateCallContextCleanup
0x18000c6ef  mov     rcx, r14
0x18000c6f2  call    DereferenceRefCount
0x18000c6f7  test    cs:byte_18002E903, 10h
0x18000c6fe  jz      short loc_18000C740
0x18000c700  xor     eax, eax
0x18000c702  lea     r8, aInitiatesstpre; "InitiateSstpResponse"
0x18000c709  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000c710  mov     word ptr [rsp+8A0h+var_840], ax
0x18000c715  lea     rcx, [rsp+8A0h+var_840]
0x18000c71a  call    FormatRRASErrorString
0x18000c71f  test    cs:byte_18002E903, 10h
0x18000c726  jz      short loc_18000C740
0x18000c728  lea     r8, [rsp+8A0h+var_840]
0x18000c72d  lea     rdx, RasSSTPSvcTraceInfo
0x18000c734  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c73b  call    McTemplateU0z_EventWriteTransfer
0x18000c740  mov     rcx, [rbp+7A0h+var_40]
0x18000c747  xor     rcx, rsp; StackCookie
0x18000c74a  call    __security_check_cookie
0x18000c74f  add     rsp, 878h
0x18000c756  pop     r15
0x18000c758  pop     r14
0x18000c75a  pop     rdi
0x18000c75b  pop     rsi
0x18000c75c  pop     rbx
0x18000c75d  pop     rbp
0x18000c75e  retn
```
