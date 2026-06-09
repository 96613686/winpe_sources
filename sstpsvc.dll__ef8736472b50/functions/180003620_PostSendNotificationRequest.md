# PostSendNotificationRequest

- ea: `0x180003620`
- end: `0x180003bb4`
- name: `PostSendNotificationRequest`
- size: `1428`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003010`
- `0x18000b9c8`
- `0x18000ebd0`

## callees

- `0x180002f50`
- `0x180003620`
- `0x1800089dc`
- `0x180008b90`
- `0x180008c14`
- `0x18001d1da`
- `0x18001d210`
- `0x18001d2a0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003699`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003699`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800037b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800037b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003827`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000377a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000377a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000376a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000376a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800038f8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800038f8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000371f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000371f`

## string_xrefs

- `0x180003862`: `CoId=%hs:PostSendNotification: completes with %d`
- `0x1800039ae`: `CoId=%hs:Disconnect already in progress`

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
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"Entering %ws", L"PostSendNotificationRequest");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  if ( *(_BYTE *)(a1 + 435) )
  {
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"CoId=%hs:Disconnect already in progress", a1 + 552);
      if ( (byte_18002E903 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 208), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a1 + 216))(a1 + 208);
  }
  else
  {
    *(_DWORD *)(a1 + 252) |= 0x400u;
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"CoId=%hs:Setting %p callcontext->SendOverlapPosted to %ws", a1 + 552, a1, L"TRUE");
      if ( (byte_18002E903 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
    }
    *(_DWORD *)(a1 + 72) = 17770;
    *(_OWORD *)(a1 + 40) = 0;
    v13 = 0;
    *(_OWORD *)(a1 + 56) = 0;
    memset_0(v14, 0, sizeof(v14));
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"Entering %ws", L"AsyncSstpDeviceControl");
      if ( (byte_18002E903 & 0x10) != 0 )
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
      if ( (byte_18002E903 & 8) != 0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(&v13, L"AsyncSstpDeviceIoControl fails with [%d]", LastError);
        if ( (byte_18002E903 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v13);
      }
    }
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"LEaving %ws", L"AsyncSstpDeviceControl");
      if ( (byte_18002E903 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v13);
    }
    if ( LastError )
    {
      if ( (byte_18002E903 & 0x10) != 0 )
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
        if ( (byte_18002E903 & 0x10) != 0 )
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
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"CoId=%hs:PostSendNotification: completes with %d", a1 + 552, LastError);
      if ( (byte_18002E903 & 0x10) != 0 )
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
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"LEaving %ws", L"PostSendNotificationRequest");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v11);
  }
}

```

## disassembly

```asm
0x180003620  push    rbp
0x180003622  lea     rbp, [rsp-0F80h]
0x18000362a  mov     eax, 1080h
0x18000362f  call    _alloca_probe
0x180003634  sub     rsp, rax
0x180003637  mov     rax, cs:__security_cookie
0x18000363e  xor     rax, rsp
0x180003641  mov     [rbp+0F80h+var_20], rax
0x180003648  mov     [rsp+1080h+arg_8], rbx
0x180003650  xor     eax, eax
0x180003652  mov     rbx, rcx
0x180003655  mov     [rsp+1080h+arg_10], rsi
0x18000365d  lea     rcx, [rsp+1080h+var_101C]; void *
0x180003662  mov     [rsp+1080h+var_8], rdi
0x18000366a  xor     edx, edx; Val
0x18000366c  mov     [rsp+1080h+var_1020], eax
0x180003670  mov     r8d, 7FCh; Size
0x180003676  call    memset_0
0x18000367b  test    cs:byte_18002E903, 10h
0x180003682  jnz     loc_18000395C
0x180003688  lea     rdi, [rbx+0D0h]
0x18000368f  lock inc dword ptr [rdi]
0x180003692  lea     rcx, [rbx+120h]; lpCriticalSection
0x180003699  call    cs:__imp_EnterCriticalSection
0x1800036a0  nop     dword ptr [rax+rax+00h]
0x1800036a5  cmp     byte ptr [rbx+1B3h], 0
0x1800036ac  jnz     loc_180003813
0x1800036b2  or      dword ptr [rbx+0FCh], 400h
0x1800036bc  test    cs:byte_18002E903, 10h
0x1800036c3  mov     [rsp+1080h+var_10], r14
0x1800036cb  jnz     loc_1800039EE
0x1800036d1  xorps   xmm0, xmm0
0x1800036d4  mov     dword ptr [rbx+48h], 456Ah
0x1800036db  lea     r14, [rbx+28h]
0x1800036df  xor     eax, eax
0x1800036e1  movups  xmmword ptr [r14], xmm0
0x1800036e5  xor     edx, edx; Val
0x1800036e7  mov     [rbp+0F80h+var_820], eax
0x1800036ed  mov     r8d, 7FCh; Size
0x1800036f3  lea     rcx, [rbp+0F80h+var_81C]; void *
0x1800036fa  movups  xmmword ptr [r14+10h], xmm0
0x1800036ff  call    memset_0
0x180003704  test    cs:byte_18002E903, 10h
0x18000370b  jnz     loc_180003A46
0x180003711  mov     rcx, cs:SstpSvcGlobals
0x180003718  mov     rcx, [rcx+120h]; pio
0x18000371f  call    cs:__imp_StartThreadpoolIo
0x180003726  nop     dword ptr [rax+rax+00h]
0x18000372b  mov     rcx, cs:SstpSvcGlobals
0x180003732  lea     r8, [rbx+0F0h]; lpInBuffer
0x180003739  mov     [rsp+1080h+lpOverlapped], r14; lpOverlapped
0x18000373e  mov     edx, 12803Ch; dwIoControlCode
0x180003743  mov     [rsp+1080h+lpBytesReturned], 0; lpBytesReturned
0x18000374c  mov     r9d, 4; nInBufferSize
0x180003752  mov     dword ptr [rsp+1080h+nOutBufferSize], 0; nOutBufferSize
0x18000375a  mov     rcx, [rcx+118h]; hDevice
0x180003761  mov     [rsp+1080h+lpOutBuffer], 0; lpOutBuffer
0x18000376a  call    cs:__imp_DeviceIoControl
0x180003771  nop     dword ptr [rax+rax+00h]
0x180003776  test    eax, eax
0x180003778  jnz     short loc_180003794
0x18000377a  call    cs:__imp_GetLastError
0x180003781  nop     dword ptr [rax+rax+00h]
0x180003786  mov     r14d, eax
0x180003789  cmp     eax, 3E5h
0x18000378e  jnz     loc_1800038E1
0x180003794  xor     r14d, r14d
0x180003797  test    cs:byte_18002E903, 10h
0x18000379e  jnz     loc_180003A95
0x1800037a4  test    r14d, r14d
0x1800037a7  jnz     loc_180003AE4
0x1800037ad  lea     rcx, [rbx+120h]; lpCriticalSection
0x1800037b4  call    cs:__imp_LeaveCriticalSection
0x1800037bb  nop     dword ptr [rax+rax+00h]
0x1800037c0  test    cs:byte_18002E903, 10h
0x1800037c7  jnz     loc_180003851
0x1800037cd  mov     r14, [rsp+1080h+var_10]
0x1800037d5  test    cs:byte_18002E903, 10h
0x1800037dc  mov     rdi, [rsp+1080h+var_8]
0x1800037e4  mov     rsi, [rsp+1080h+arg_10]
0x1800037ec  mov     rbx, [rsp+1080h+arg_8]
0x1800037f4  jnz     loc_180003B6B
0x1800037fa  mov     rcx, [rbp+0F80h+var_20]
0x180003801  xor     rcx, rsp; StackCookie
0x180003804  call    __security_check_cookie
0x180003809  add     rsp, 1080h
0x180003810  pop     rbp
0x180003811  retn
0x180003813  test    cs:byte_18002E903, 10h
0x18000381a  jnz     loc_1800039A5
0x180003820  lea     rcx, [rbx+120h]; lpCriticalSection
0x180003827  call    cs:__imp_LeaveCriticalSection
0x18000382e  nop     dword ptr [rax+rax+00h]
0x180003833  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000383a  lock xadd [rdi], eax
0x18000383e  cmp     eax, 1
0x180003841  jnz     short loc_1800037D5
0x180003843  mov     rax, [rdi+8]
0x180003847  mov     rcx, rdi
0x18000384a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000384f  jmp     short loc_1800037D5
0x180003851  xor     eax, eax
0x180003853  lea     r8, [rbx+228h]
0x18000385a  mov     r9d, r14d
0x18000385d  mov     word ptr [rsp+1080h+var_1020], ax
0x180003862  lea     rdx, aCoidHsPostsend; "CoId=%hs:PostSendNotification: complete"...
0x180003869  lea     rcx, [rsp+1080h+var_1020]
0x18000386e  call    FormatRRASErrorString
0x180003873  test    cs:byte_18002E903, 10h
0x18000387a  jz      loc_1800037CD
0x180003880  lea     rcx, [rsp+1080h+var_1020]
0x180003885  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000388c  nop     dword ptr [rax+00h]
0x180003890  cmp     word ptr [rcx+rax*2+2], 0
0x180003896  lea     rax, [rax+1]
0x18000389a  jnz     short loc_180003890
0x18000389c  lea     eax, ds:2[rax*2]
0x1800038a3  mov     [rsp+1080h+var_1024], 0
0x1800038ab  lea     rcx, [rsp+1080h+var_1020]
0x1800038b0  mov     [rsp+1080h+var_1028], eax
0x1800038b4  lea     rax, [rsp+1080h+var_1040]
0x1800038b9  mov     [rsp+1080h+var_1030], rcx
0x1800038be  mov     r9d, 2
0x1800038c4  mov     [rsp+1080h+lpOutBuffer], rax
0x1800038c9  lea     rdx, RasSSTPSvcTraceInfo
0x1800038d0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800038d7  call    McGenEventWrite_EventWriteTransfer
0x1800038dc  jmp     loc_1800037CD
0x1800038e1  test    r14d, r14d
0x1800038e4  jz      loc_180003794
0x1800038ea  mov     rcx, cs:SstpSvcGlobals
0x1800038f1  mov     rcx, [rcx+120h]; pio
0x1800038f8  call    cs:__imp_CancelThreadpoolIo
0x1800038ff  nop     dword ptr [rax+rax+00h]
0x180003904  test    cs:byte_18002E903, 8
0x18000390b  jz      loc_180003797
0x180003911  xor     eax, eax
0x180003913  lea     rdx, aAsyncsstpdevic; "AsyncSstpDeviceIoControl fails with [%d"...
0x18000391a  mov     r8d, r14d
0x18000391d  mov     word ptr [rbp+0F80h+var_820], ax
0x180003924  lea     rcx, [rbp+0F80h+var_820]
0x18000392b  call    FormatRRASErrorString
0x180003930  test    cs:byte_18002E903, 8
0x180003937  jz      loc_180003797
0x18000393d  lea     r8, [rbp+0F80h+var_820]
0x180003944  lea     rdx, RasSSTPSvcTraceError
0x18000394b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003952  call    McTemplateU0z_EventWriteTransfer
0x180003957  jmp     loc_180003797
0x18000395c  xor     eax, eax
0x18000395e  lea     r8, aPostsendnotifi; "PostSendNotificationRequest"
0x180003965  lea     rdx, aEnteringWs; "Entering %ws"
0x18000396c  mov     word ptr [rsp+1080h+var_1020], ax
0x180003971  lea     rcx, [rsp+1080h+var_1020]
0x180003976  call    FormatRRASErrorString
0x18000397b  test    cs:byte_18002E903, 10h
0x180003982  jz      loc_180003688
0x180003988  lea     r8, [rsp+1080h+var_1020]
0x18000398d  lea     rdx, RasSSTPSvcTraceInfo
0x180003994  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000399b  call    McTemplateU0z_EventWriteTransfer
0x1800039a0  jmp     loc_180003688
0x1800039a5  xor     eax, eax
0x1800039a7  lea     r8, [rbx+228h]
0x1800039ae  lea     rdx, aCoidHsDisconne; "CoId=%hs:Disconnect already in progress"
0x1800039b5  mov     word ptr [rsp+1080h+var_1020], ax
0x1800039ba  lea     rcx, [rsp+1080h+var_1020]
0x1800039bf  call    FormatRRASErrorString
0x1800039c4  test    cs:byte_18002E903, 10h
0x1800039cb  jz      loc_180003820
0x1800039d1  lea     r8, [rsp+1080h+var_1020]
0x1800039d6  lea     rdx, RasSSTPSvcTraceInfo
0x1800039dd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800039e4  call    McTemplateU0z_EventWriteTransfer
0x1800039e9  jmp     loc_180003820
0x1800039ee  xor     eax, eax
0x1800039f0  lea     r8, [rbx+228h]
0x1800039f7  mov     word ptr [rsp+1080h+var_1020], ax
0x1800039fc  lea     rdx, aCoidHsSettingP; "CoId=%hs:Setting %p callcontext->SendOv"...
0x180003a03  lea     rax, aTrue; "TRUE"
0x180003a0a  mov     r9, rbx
0x180003a0d  lea     rcx, [rsp+1080h+var_1020]
0x180003a12  mov     [rsp+1080h+lpOutBuffer], rax
0x180003a17  call    FormatRRASErrorString
0x180003a1c  test    cs:byte_18002E903, 10h
0x180003a23  jz      loc_1800036D1
0x180003a29  lea     r8, [rsp+1080h+var_1020]
0x180003a2e  lea     rdx, RasSSTPSvcTraceInfo
0x180003a35  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003a3c  call    McTemplateU0z_EventWriteTransfer
0x180003a41  jmp     loc_1800036D1
0x180003a46  xor     eax, eax
0x180003a48  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x180003a4f  lea     rdx, aEnteringWs; "Entering %ws"
0x180003a56  mov     word ptr [rbp+0F80h+var_820], ax
0x180003a5d  lea     rcx, [rbp+0F80h+var_820]
0x180003a64  call    FormatRRASErrorString
0x180003a69  test    cs:byte_18002E903, 10h
0x180003a70  jz      loc_180003711
0x180003a76  lea     r8, [rbp+0F80h+var_820]
0x180003a7d  lea     rdx, RasSSTPSvcTraceInfo
0x180003a84  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003a8b  call    McTemplateU0z_EventWriteTransfer
0x180003a90  jmp     loc_180003711
0x180003a95  xor     eax, eax
0x180003a97  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x180003a9e  lea     rdx, aLeavingWs; "LEaving %ws"
0x180003aa5  mov     word ptr [rbp+0F80h+var_820], ax
0x180003aac  lea     rcx, [rbp+0F80h+var_820]
0x180003ab3  call    FormatRRASErrorString
0x180003ab8  test    cs:byte_18002E903, 10h
0x180003abf  jz      loc_1800037A4
0x180003ac5  lea     r8, [rbp+0F80h+var_820]
0x180003acc  lea     rdx, RasSSTPSvcTraceInfo
0x180003ad3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003ada  call    McTemplateU0z_EventWriteTransfer
0x180003adf  jmp     loc_1800037A4
0x180003ae4  test    cs:byte_18002E903, 10h
0x180003aeb  jz      short loc_180003B41
0x180003aed  xor     eax, eax
0x180003aef  mov     dword ptr [rsp+1080h+nOutBufferSize], r14d
0x180003af4  mov     word ptr [rsp+1080h+var_1020], ax
0x180003af9  lea     r8, [rbx+228h]
0x180003b00  lea     rax, aFalse; "FALSE"
0x180003b07  mov     r9, rbx
0x180003b0a  lea     rdx, aCoidHsSettingP_0; "CoId=%hs:Setting %p callcontext->SendOv"...
0x180003b11  mov     [rsp+1080h+lpOutBuffer], rax
0x180003b16  lea     rcx, [rsp+1080h+var_1020]
0x180003b1b  call    FormatRRASErrorString
0x180003b20  test    cs:byte_18002E903, 10h
0x180003b27  jz      short loc_180003B41
0x180003b29  lea     r8, [rsp+1080h+var_1020]
0x180003b2e  lea     rdx, RasSSTPSvcTraceInfo
0x180003b35  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003b3c  call    McTemplateU0z_EventWriteTransfer
0x180003b41  and     dword ptr [rbx+0FCh], 0FFFFFBFFh
0x180003b4b  lea     rcx, [rbx+120h]; lpCriticalSection
0x180003b52  call    cs:__imp_LeaveCriticalSection
0x180003b59  nop     dword ptr [rax+rax+00h]
0x180003b5e  mov     rcx, rdi
0x180003b61  call    DereferenceRefCount
0x180003b66  jmp     loc_1800037C0
0x180003b6b  xor     eax, eax
0x180003b6d  lea     r8, aPostsendnotifi; "PostSendNotificationRequest"
0x180003b74  lea     rdx, aLeavingWs; "LEaving %ws"
0x180003b7b  mov     word ptr [rsp+1080h+var_1020], ax
0x180003b80  lea     rcx, [rsp+1080h+var_1020]
0x180003b85  call    FormatRRASErrorString
0x180003b8a  test    cs:byte_18002E903, 10h
0x180003b91  jz      loc_1800037FA
0x180003b97  lea     r8, [rsp+1080h+var_1020]
0x180003b9c  lea     rdx, RasSSTPSvcTraceInfo
0x180003ba3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180003baa  call    McTemplateU0z_EventWriteTransfer
0x180003baf  jmp     loc_1800037FA
```
