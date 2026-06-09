# PostSendNotificationRequest

- ea: `0x1800033b0`
- end: `0x18000390b`
- name: `PostSendNotificationRequest`
- size: `1371`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180002e00`
- `0x18000afbc`
- `0x18000df30`

## callees

- `0x180002d40`
- `0x1800033b0`
- `0x18000827c`
- `0x180008360`
- `0x1800083e0`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001bd80`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003429`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003429`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000352c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003594`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800038af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000352c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003594`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800038af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034f8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800034ee`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800034ee`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000365b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000365b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800034a9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800034a9`

## string_xrefs

- `0x1800035c9`: `CoId=%hs:PostSendNotification: completes with %d`
- `0x18000370b`: `CoId=%hs:Disconnect already in progress`

## pseudocode

```c
void __fastcall PostSendNotificationRequest(__int64 a1)
{
  DWORD LastError; // r14d
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 nOutBufferSize; // [rsp+28h] [rbp-D8h]
  _BYTE v7[16]; // [rsp+40h] [rbp-C0h] BYREF
  int *v8; // [rsp+50h] [rbp-B0h]
  int v9; // [rsp+58h] [rbp-A8h]
  int v10; // [rsp+5Ch] [rbp-A4h]
  int v11; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v12[2044]; // [rsp+64h] [rbp-9Ch] BYREF
  int v13; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v14[2044]; // [rsp+864h] [rbp+764h] BYREF

  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"Entering %ws", L"PostSendNotificationRequest");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  if ( *(_BYTE *)(a1 + 435) )
  {
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"CoId=%hs:Disconnect already in progress", a1 + 552);
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 208), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a1 + 216))(a1 + 208);
  }
  else
  {
    *(_DWORD *)(a1 + 252) |= 0x400u;
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"CoId=%hs:Setting %p callcontext->SendOverlapPosted to %ws", a1 + 552, a1, L"TRUE");
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
    }
    *(_DWORD *)(a1 + 72) = 17770;
    *(_OWORD *)(a1 + 40) = 0;
    v13 = 0;
    *(_OWORD *)(a1 + 56) = 0;
    memset_0(v14, 0, sizeof(v14));
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"Entering %ws", L"AsyncSstpDeviceControl");
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v13);
    }
    StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
    if ( DeviceIoControl(
           *((HANDLE *)SstpSvcGlobals + 35),
           0x12803Cu,
           (LPVOID)(a1 + 240),
           4u,
           0,
           0,
           0,
           (LPOVERLAPPED)(a1 + 40))
      || (LastError = GetLastError(), LastError == 997)
      || !LastError )
    {
      LastError = 0;
    }
    else
    {
      CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"AsyncSstpDeviceIoControl fails with [%d]", LastError);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v13);
      }
    }
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"LEaving %ws", L"AsyncSstpDeviceControl");
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v13);
    }
    if ( LastError )
    {
      if ( (byte_18002D803 & 0x10) != 0 )
      {
        LODWORD(nOutBufferSize) = LastError;
        LOWORD(v11) = 0;
        FormatRRASErrorString(
          &v11,
          L"CoId=%hs:Setting %p callcontext->SendOverlapPosted to %ws due to failure:%d",
          a1 + 552,
          a1,
          L"FALSE",
          nOutBufferSize);
        if ( (byte_18002D803 & 0x10) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
      }
      *(_DWORD *)(a1 + 252) &= ~0x400u;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
      DereferenceRefCount(a1 + 208);
    }
    else
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    }
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"CoId=%hs:PostSendNotification: completes with %d", a1 + 552, LastError);
      if ( (byte_18002D803 & 0x10) != 0 )
      {
        v4 = -1;
        while ( *(_WORD *)&v12[2 * v4++ - 2] != 0 )
          ;
        v10 = 0;
        v9 = 2 * v4 + 2;
        v8 = &v11;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, v3, 2, v7);
      }
    }
  }
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"LEaving %ws", L"PostSendNotificationRequest");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
  }
}

```

## disassembly

```asm
0x1800033b0  push    rbp
0x1800033b2  lea     rbp, [rsp-0F80h]
0x1800033ba  mov     eax, 1080h
0x1800033bf  call    _alloca_probe
0x1800033c4  sub     rsp, rax
0x1800033c7  mov     rax, cs:__security_cookie
0x1800033ce  xor     rax, rsp
0x1800033d1  mov     [rbp+0F80h+var_20], rax
0x1800033d8  mov     [rsp+1080h+arg_8], rbx
0x1800033e0  xor     eax, eax
0x1800033e2  mov     rbx, rcx
0x1800033e5  mov     [rsp+1080h+arg_10], rsi
0x1800033ed  lea     rcx, [rsp+1080h+var_101C]; void *
0x1800033f2  mov     [rsp+1080h+var_8], rdi
0x1800033fa  xor     edx, edx; Val
0x1800033fc  mov     [rsp+1080h+var_1020], eax
0x180003400  mov     r8d, 7FCh; Size
0x180003406  call    memset_0
0x18000340b  test    cs:byte_18002D803, 10h
0x180003412  jnz     loc_1800036B9
0x180003418  lea     rdi, [rbx+0D0h]
0x18000341f  lock inc dword ptr [rdi]
0x180003422  lea     rcx, [rbx+120h]; lpCriticalSection
0x180003429  call    cs:__imp_EnterCriticalSection
0x18000342f  cmp     byte ptr [rbx+1B3h], 0
0x180003436  jnz     loc_180003580
0x18000343c  or      dword ptr [rbx+0FCh], 400h
0x180003446  test    cs:byte_18002D803, 10h
0x18000344d  mov     [rsp+1080h+var_10], r14
0x180003455  jnz     loc_18000374B
0x18000345b  xorps   xmm0, xmm0
0x18000345e  mov     dword ptr [rbx+48h], 456Ah
0x180003465  lea     r14, [rbx+28h]
0x180003469  xor     eax, eax
0x18000346b  movups  xmmword ptr [r14], xmm0
0x18000346f  xor     edx, edx; Val
0x180003471  mov     [rbp+0F80h+var_820], eax
0x180003477  mov     r8d, 7FCh; Size
0x18000347d  lea     rcx, [rbp+0F80h+var_81C]; void *
0x180003484  movups  xmmword ptr [r14+10h], xmm0
0x180003489  call    memset_0
0x18000348e  test    cs:byte_18002D803, 10h
0x180003495  jnz     loc_1800037A3
0x18000349b  mov     rcx, cs:SstpSvcGlobals
0x1800034a2  mov     rcx, [rcx+120h]; pio
0x1800034a9  call    cs:__imp_StartThreadpoolIo
0x1800034af  mov     rcx, cs:SstpSvcGlobals
0x1800034b6  lea     r8, [rbx+0F0h]; lpInBuffer
0x1800034bd  mov     [rsp+1080h+lpOverlapped], r14; lpOverlapped
0x1800034c2  mov     edx, 12803Ch; dwIoControlCode
0x1800034c7  mov     [rsp+1080h+lpBytesReturned], 0; lpBytesReturned
0x1800034d0  mov     r9d, 4; nInBufferSize
0x1800034d6  mov     dword ptr [rsp+1080h+nOutBufferSize], 0; nOutBufferSize
0x1800034de  mov     rcx, [rcx+118h]; hDevice
0x1800034e5  mov     [rsp+1080h+lpOutBuffer], 0; lpOutBuffer
0x1800034ee  call    cs:__imp_DeviceIoControl
0x1800034f4  test    eax, eax
0x1800034f6  jnz     short loc_18000350C
0x1800034f8  call    cs:__imp_GetLastError
0x1800034fe  mov     r14d, eax
0x180003501  cmp     eax, 3E5h
0x180003506  jnz     loc_180003644
0x18000350c  xor     r14d, r14d
0x18000350f  test    cs:byte_18002D803, 10h
0x180003516  jnz     loc_1800037F2
0x18000351c  test    r14d, r14d
0x18000351f  jnz     loc_180003841
0x180003525  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000352c  call    cs:__imp_LeaveCriticalSection
0x180003532  test    cs:byte_18002D803, 10h
0x180003539  jnz     short loc_1800035B8
0x18000353b  mov     r14, [rsp+1080h+var_10]
0x180003543  test    cs:byte_18002D803, 10h
0x18000354a  mov     rdi, [rsp+1080h+var_8]
0x180003552  mov     rsi, [rsp+1080h+arg_10]
0x18000355a  mov     rbx, [rsp+1080h+arg_8]
0x180003562  jnz     loc_1800038C2
0x180003568  mov     rcx, [rbp+0F80h+var_20]
0x18000356f  xor     rcx, rsp; StackCookie
0x180003572  call    __security_check_cookie
0x180003577  add     rsp, 1080h
0x18000357e  pop     rbp
0x18000357f  retn
0x180003580  test    cs:byte_18002D803, 10h
0x180003587  jnz     loc_180003702
0x18000358d  lea     rcx, [rbx+120h]; lpCriticalSection
0x180003594  call    cs:__imp_LeaveCriticalSection
0x18000359a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800035a1  lock xadd [rdi], eax
0x1800035a5  cmp     eax, 1
0x1800035a8  jnz     short loc_180003543
0x1800035aa  mov     rax, [rdi+8]
0x1800035ae  mov     rcx, rdi
0x1800035b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035b6  jmp     short loc_180003543
0x1800035b8  xor     eax, eax
0x1800035ba  lea     r8, [rbx+228h]
0x1800035c1  mov     r9d, r14d
0x1800035c4  mov     word ptr [rsp+1080h+var_1020], ax
0x1800035c9  lea     rdx, aCoidHsPostsend; "CoId=%hs:PostSendNotification: complete"...
0x1800035d0  lea     rcx, [rsp+1080h+var_1020]
0x1800035d5  call    FormatRRASErrorString
0x1800035da  test    cs:byte_18002D803, 10h
0x1800035e1  jz      loc_18000353B
0x1800035e7  lea     rcx, [rsp+1080h+var_1020]
0x1800035ec  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800035f3  cmp     word ptr [rcx+rax*2+2], 0
0x1800035f9  lea     rax, [rax+1]
0x1800035fd  jnz     short loc_1800035F3
0x1800035ff  lea     eax, ds:2[rax*2]
0x180003606  mov     [rsp+1080h+var_1024], 0
0x18000360e  lea     rcx, [rsp+1080h+var_1020]
0x180003613  mov     [rsp+1080h+var_1028], eax
0x180003617  lea     rax, [rsp+1080h+var_1040]
0x18000361c  mov     [rsp+1080h+var_1030], rcx
0x180003621  mov     r9d, 2
0x180003627  mov     [rsp+1080h+lpOutBuffer], rax
0x18000362c  lea     rdx, RasSSTPSvcTraceInfo
0x180003633  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000363a  call    McGenEventWrite_EventWriteTransfer
0x18000363f  jmp     loc_18000353B
0x180003644  test    r14d, r14d
0x180003647  jz      loc_18000350C
0x18000364d  mov     rcx, cs:SstpSvcGlobals
0x180003654  mov     rcx, [rcx+120h]; pio
0x18000365b  call    cs:__imp_CancelThreadpoolIo
0x180003661  test    cs:byte_18002D803, 8
0x180003668  jz      loc_18000350F
0x18000366e  xor     eax, eax
0x180003670  lea     rdx, aAsyncsstpdevic; "AsyncSstpDeviceIoControl fails with [%d"...
0x180003677  mov     r8d, r14d
0x18000367a  mov     word ptr [rbp+0F80h+var_820], ax
0x180003681  lea     rcx, [rbp+0F80h+var_820]
0x180003688  call    FormatRRASErrorString
0x18000368d  test    cs:byte_18002D803, 8
0x180003694  jz      loc_18000350F
0x18000369a  lea     r8, [rbp+0F80h+var_820]
0x1800036a1  lea     rdx, RasSSTPSvcTraceError
0x1800036a8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800036af  call    McTemplateU0z_EventWriteTransfer
0x1800036b4  jmp     loc_18000350F
0x1800036b9  xor     eax, eax
0x1800036bb  lea     r8, aPostsendnotifi; "PostSendNotificationRequest"
0x1800036c2  lea     rdx, aEnteringWs; "Entering %ws"
0x1800036c9  mov     word ptr [rsp+1080h+var_1020], ax
0x1800036ce  lea     rcx, [rsp+1080h+var_1020]
0x1800036d3  call    FormatRRASErrorString
0x1800036d8  test    cs:byte_18002D803, 10h
0x1800036df  jz      loc_180003418
0x1800036e5  lea     r8, [rsp+1080h+var_1020]
0x1800036ea  lea     rdx, RasSSTPSvcTraceInfo
0x1800036f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800036f8  call    McTemplateU0z_EventWriteTransfer
0x1800036fd  jmp     loc_180003418
0x180003702  xor     eax, eax
0x180003704  lea     r8, [rbx+228h]
0x18000370b  lea     rdx, aCoidHsDisconne; "CoId=%hs:Disconnect already in progress"
0x180003712  mov     word ptr [rsp+1080h+var_1020], ax
0x180003717  lea     rcx, [rsp+1080h+var_1020]
0x18000371c  call    FormatRRASErrorString
0x180003721  test    cs:byte_18002D803, 10h
0x180003728  jz      loc_18000358D
0x18000372e  lea     r8, [rsp+1080h+var_1020]
0x180003733  lea     rdx, RasSSTPSvcTraceInfo
0x18000373a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003741  call    McTemplateU0z_EventWriteTransfer
0x180003746  jmp     loc_18000358D
0x18000374b  xor     eax, eax
0x18000374d  lea     r8, [rbx+228h]
0x180003754  mov     word ptr [rsp+1080h+var_1020], ax
0x180003759  lea     rdx, aCoidHsSettingP; "CoId=%hs:Setting %p callcontext->SendOv"...
0x180003760  lea     rax, aTrue; "TRUE"
0x180003767  mov     r9, rbx
0x18000376a  lea     rcx, [rsp+1080h+var_1020]
0x18000376f  mov     [rsp+1080h+lpOutBuffer], rax
0x180003774  call    FormatRRASErrorString
0x180003779  test    cs:byte_18002D803, 10h
0x180003780  jz      loc_18000345B
0x180003786  lea     r8, [rsp+1080h+var_1020]
0x18000378b  lea     rdx, RasSSTPSvcTraceInfo
0x180003792  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003799  call    McTemplateU0z_EventWriteTransfer
0x18000379e  jmp     loc_18000345B
0x1800037a3  xor     eax, eax
0x1800037a5  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x1800037ac  lea     rdx, aEnteringWs; "Entering %ws"
0x1800037b3  mov     word ptr [rbp+0F80h+var_820], ax
0x1800037ba  lea     rcx, [rbp+0F80h+var_820]
0x1800037c1  call    FormatRRASErrorString
0x1800037c6  test    cs:byte_18002D803, 10h
0x1800037cd  jz      loc_18000349B
0x1800037d3  lea     r8, [rbp+0F80h+var_820]
0x1800037da  lea     rdx, RasSSTPSvcTraceInfo
0x1800037e1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800037e8  call    McTemplateU0z_EventWriteTransfer
0x1800037ed  jmp     loc_18000349B
0x1800037f2  xor     eax, eax
0x1800037f4  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x1800037fb  lea     rdx, aLeavingWs; "LEaving %ws"
0x180003802  mov     word ptr [rbp+0F80h+var_820], ax
0x180003809  lea     rcx, [rbp+0F80h+var_820]
0x180003810  call    FormatRRASErrorString
0x180003815  test    cs:byte_18002D803, 10h
0x18000381c  jz      loc_18000351C
0x180003822  lea     r8, [rbp+0F80h+var_820]
0x180003829  lea     rdx, RasSSTPSvcTraceInfo
0x180003830  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003837  call    McTemplateU0z_EventWriteTransfer
0x18000383c  jmp     loc_18000351C
0x180003841  test    cs:byte_18002D803, 10h
0x180003848  jz      short loc_18000389E
0x18000384a  xor     eax, eax
0x18000384c  mov     dword ptr [rsp+1080h+nOutBufferSize], r14d
0x180003851  mov     word ptr [rsp+1080h+var_1020], ax
0x180003856  lea     r8, [rbx+228h]
0x18000385d  lea     rax, aFalse; "FALSE"
0x180003864  mov     r9, rbx
0x180003867  lea     rdx, aCoidHsSettingP_0; "CoId=%hs:Setting %p callcontext->SendOv"...
0x18000386e  mov     [rsp+1080h+lpOutBuffer], rax
0x180003873  lea     rcx, [rsp+1080h+var_1020]
0x180003878  call    FormatRRASErrorString
0x18000387d  test    cs:byte_18002D803, 10h
0x180003884  jz      short loc_18000389E
0x180003886  lea     r8, [rsp+1080h+var_1020]
0x18000388b  lea     rdx, RasSSTPSvcTraceInfo
0x180003892  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003899  call    McTemplateU0z_EventWriteTransfer
0x18000389e  and     dword ptr [rbx+0FCh], 0FFFFFBFFh
0x1800038a8  lea     rcx, [rbx+120h]; lpCriticalSection
0x1800038af  call    cs:__imp_LeaveCriticalSection
0x1800038b5  mov     rcx, rdi
0x1800038b8  call    DereferenceRefCount
0x1800038bd  jmp     loc_180003532
0x1800038c2  xor     eax, eax
0x1800038c4  lea     r8, aPostsendnotifi; "PostSendNotificationRequest"
0x1800038cb  lea     rdx, aLeavingWs; "LEaving %ws"
0x1800038d2  mov     word ptr [rsp+1080h+var_1020], ax
0x1800038d7  lea     rcx, [rsp+1080h+var_1020]
0x1800038dc  call    FormatRRASErrorString
0x1800038e1  test    cs:byte_18002D803, 10h
0x1800038e8  jz      loc_180003568
0x1800038ee  lea     r8, [rsp+1080h+var_1020]
0x1800038f3  lea     rdx, RasSSTPSvcTraceInfo
0x1800038fa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003901  call    McTemplateU0z_EventWriteTransfer
0x180003906  jmp     loc_180003568
```
