# DeinitializeTransport

- ea: `0x180005560`
- end: `0x180005919`
- name: `DeinitializeTransport`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005280`

## callees

- `0x180002908`
- `0x180005560`
- `0x18000827c`
- `0x180008360`
- `0x180008490`
- `0x180008594`
- `0x180008694`
- `0x18000c8d0`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000563c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005790`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000563c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005790`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005663`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000567d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005663`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000567d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800057c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800057d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005822`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800057c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800057d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005822`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056eb`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180005699`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180005699`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000570a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180005757`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18000570a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180005757`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180005851`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180005851`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180005865`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180005865`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180005880`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180005880`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800056af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180005743`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800056af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180005743`
- `WS2_32!__imp_WSACleanup` at `0x180005683`
- `WS2_32!__imp_WSACleanup` at `0x180005683`
- `rtutils!RouterLogDeregisterW` at `0x1800058b1`
- `rtutils!RouterLogDeregisterW` at `0x1800058b1`
- `webio!__imp_WebTerminate` at `0x18000566e`
- `webio!__imp_WebTerminate` at `0x18000566e`
- `NduProv!__imp_NduCloseHandle` at `0x1800056cc`
- `NduProv!__imp_NduCloseHandle` at `0x1800056cc`

## pseudocode

```c
__int64 DeinitializeTransport()
{
  char v0; // al
  char *v1; // rcx
  char *v2; // rcx
  __int64 v3; // rbx
  HANDLE *v4; // rcx
  PTP_IO *v5; // rcx
  char *v6; // rcx
  __int64 *v7; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  PTP_POOL *v10; // rcx
  void *v11; // rcx
  int v13; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v14[2044]; // [rsp+24h] [rbp-814h] BYREF

  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  v0 = byte_18002D803;
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"Entering %ws", L"DeinitializeTransport");
    v0 = byte_18002D803;
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v13);
      v0 = byte_18002D803;
    }
  }
  v1 = (char *)SstpSvcGlobals;
  if ( !*((_BYTE *)SstpSvcGlobals + 16) )
  {
    if ( (v0 & 0x10) == 0 )
      return 0;
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"LEaving %ws", L"DeinitializeTransport");
    if ( (byte_18002D803 & 0x10) == 0 )
      return 0;
LABEL_23:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v13);
    return 0;
  }
  *((_BYTE *)SstpSvcGlobals + 16) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 704));
  v2 = (char *)SstpSvcGlobals;
  v3 = *((_QWORD *)SstpSvcGlobals + 93);
  if ( v3 )
  {
    *((_QWORD *)SstpSvcGlobals + 93) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 704));
    WebTerminate(v3, 0);
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 704));
  }
  WSACleanup();
  CancelIoEx(*((HANDLE *)SstpSvcGlobals + 35), 0);
  WaitForThreadpoolIoCallbacks(*((PTP_IO *)SstpSvcGlobals + 36), 0);
  v4 = (HANDLE *)SstpSvcGlobals;
  if ( *((_QWORD *)SstpSvcGlobals + 94) != -1 )
  {
    NduCloseHandle(*((_QWORD *)SstpSvcGlobals + 94));
    v4 = (HANDLE *)SstpSvcGlobals;
    *((_QWORD *)SstpSvcGlobals + 94) = -1;
  }
  CloseHandle(v4[35]);
  v5 = (PTP_IO *)SstpSvcGlobals;
  *((_QWORD *)SstpSvcGlobals + 35) = -1;
  CloseThreadpoolIo(v5[36]);
  v6 = (char *)SstpSvcGlobals;
  *((_QWORD *)SstpSvcGlobals + 36) = 0;
  if ( *((_QWORD *)v6 + 8) )
  {
    ShutdownSstpServer(0);
    v6 = (char *)SstpSvcGlobals;
  }
  if ( *((_QWORD *)v6 + 21) )
  {
    WaitForThreadpoolIoCallbacks(*((PTP_IO *)v6 + 21), 0);
    CloseThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    v6 = (char *)SstpSvcGlobals;
    *((_QWORD *)SstpSvcGlobals + 21) = 0;
  }
  if ( *((char **)v6 + 33) != v6 + 264 )
  {
    do
    {
      v7 = (__int64 *)*((_QWORD *)v6 + 33);
      v8 = *v7;
      v9 = (_QWORD *)v7[1];
      *v9 = *v7;
      *(_QWORD *)(v8 + 8) = v9;
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
      InitiateCallContextCleanup(v7 - 28, 2);
      v6 = (char *)SstpSvcGlobals;
    }
    while ( *((LPVOID *)SstpSvcGlobals + 33) != (char *)SstpSvcGlobals + 264 );
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v6 + 224));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 704));
  FreeBufferPool((char *)SstpSvcGlobals + 312);
  FreeBufferPool((char *)SstpSvcGlobals + 536);
  FreeBufferPool((char *)SstpSvcGlobals + 424);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 184));
  HfDestroyFactory((char *)SstpSvcGlobals + 176);
  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)SstpSvcGlobals + 19), 1, 0);
  CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)SstpSvcGlobals + 19));
  v10 = (PTP_POOL *)SstpSvcGlobals;
  *((_QWORD *)SstpSvcGlobals + 19) = 0;
  CloseThreadpool(v10[20]);
  *((_QWORD *)SstpSvcGlobals + 20) = 0;
  DeinitializeHostRouteInfo();
  v11 = (void *)*((_QWORD *)SstpSvcGlobals + 9);
  if ( v11 )
    RouterLogDeregisterW(v11);
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"LEaving %ws", L"DeinitializeTransport");
    if ( (byte_18002D803 & 0x10) != 0 )
      goto LABEL_23;
  }
  return 0;
}

```

## disassembly

```asm
0x180005560  push    rdi
0x180005562  sub     rsp, 830h
0x180005569  mov     rax, cs:__security_cookie
0x180005570  xor     rax, rsp
0x180005573  mov     [rsp+838h+var_18], rax
0x18000557b  xor     edi, edi
0x18000557d  lea     rcx, [rsp+838h+var_814]; void *
0x180005582  xor     edx, edx; Val
0x180005584  mov     [rsp+838h+var_818], edi
0x180005588  mov     r8d, 7FCh; Size
0x18000558e  call    memset_0
0x180005593  movzx   eax, cs:byte_18002D803
0x18000559a  test    al, 10h
0x18000559c  jz      short loc_1800055E5
0x18000559e  lea     r8, aDeinitializetr; "DeinitializeTransport"
0x1800055a5  mov     word ptr [rsp+838h+var_818], di
0x1800055aa  lea     rdx, aEnteringWs; "Entering %ws"
0x1800055b1  lea     rcx, [rsp+838h+var_818]
0x1800055b6  call    FormatRRASErrorString
0x1800055bb  movzx   eax, cs:byte_18002D803
0x1800055c2  test    al, 10h
0x1800055c4  jz      short loc_1800055E5
0x1800055c6  lea     r8, [rsp+838h+var_818]
0x1800055cb  lea     rdx, RasSSTPSvcTraceInfo
0x1800055d2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800055d9  call    McTemplateU0z_EventWriteTransfer
0x1800055de  movzx   eax, cs:byte_18002D803
0x1800055e5  mov     rcx, cs:SstpSvcGlobals
0x1800055ec  cmp     [rcx+10h], dil
0x1800055f0  jnz     short loc_180005629
0x1800055f2  test    al, 10h
0x1800055f4  jz      loc_1800058FE
0x1800055fa  lea     r8, aDeinitializetr; "DeinitializeTransport"
0x180005601  mov     word ptr [rsp+838h+var_818], di
0x180005606  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000560d  lea     rcx, [rsp+838h+var_818]
0x180005612  call    FormatRRASErrorString
0x180005617  test    cs:byte_18002D803, 10h
0x18000561e  jnz     loc_1800058E6
0x180005624  jmp     loc_1800058FE
0x180005629  mov     [rcx+10h], dil
0x18000562d  add     rcx, 2C0h; lpCriticalSection
0x180005634  mov     [rsp+838h+arg_0], rbx
0x18000563c  call    cs:__imp_EnterCriticalSection
0x180005642  mov     rcx, cs:SstpSvcGlobals
0x180005649  mov     rbx, [rcx+2E8h]
0x180005650  test    rbx, rbx
0x180005653  jz      short loc_180005676
0x180005655  mov     [rcx+2E8h], rdi
0x18000565c  add     rcx, 2C0h; lpCriticalSection
0x180005663  call    cs:__imp_LeaveCriticalSection
0x180005669  xor     edx, edx
0x18000566b  mov     rcx, rbx
0x18000566e  call    cs:__imp_WebTerminate
0x180005674  jmp     short loc_180005683
0x180005676  add     rcx, 2C0h; lpCriticalSection
0x18000567d  call    cs:__imp_LeaveCriticalSection
0x180005683  call    cs:__imp_WSACleanup
0x180005689  mov     rcx, cs:SstpSvcGlobals
0x180005690  xor     edx, edx; lpOverlapped
0x180005692  mov     rcx, [rcx+118h]; hFile
0x180005699  call    cs:__imp_CancelIoEx
0x18000569f  mov     rcx, cs:SstpSvcGlobals
0x1800056a6  xor     edx, edx; fCancelPendingCallbacks
0x1800056a8  mov     rcx, [rcx+120h]; pio
0x1800056af  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800056b5  mov     rcx, cs:SstpSvcGlobals
0x1800056bc  mov     rax, [rcx+2F0h]
0x1800056c3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800056c7  jz      short loc_1800056E4
0x1800056c9  mov     rcx, rax
0x1800056cc  call    cs:__imp_NduCloseHandle
0x1800056d2  mov     rcx, cs:SstpSvcGlobals
0x1800056d9  mov     qword ptr [rcx+2F0h], 0FFFFFFFFFFFFFFFFh
0x1800056e4  mov     rcx, [rcx+118h]; hObject
0x1800056eb  call    cs:__imp_CloseHandle
0x1800056f1  mov     rcx, cs:SstpSvcGlobals
0x1800056f8  mov     qword ptr [rcx+118h], 0FFFFFFFFFFFFFFFFh
0x180005703  mov     rcx, [rcx+120h]; pio
0x18000570a  call    cs:__imp_CloseThreadpoolIo
0x180005710  mov     rcx, cs:SstpSvcGlobals
0x180005717  mov     [rcx+120h], rdi
0x18000571e  cmp     [rcx+40h], rdi
0x180005722  jz      short loc_180005732
0x180005724  xor     ecx, ecx
0x180005726  call    ShutdownSstpServer
0x18000572b  mov     rcx, cs:SstpSvcGlobals
0x180005732  mov     rax, [rcx+0A8h]
0x180005739  test    rax, rax
0x18000573c  jz      short loc_18000576B
0x18000573e  xor     edx, edx; fCancelPendingCallbacks
0x180005740  mov     rcx, rax; pio
0x180005743  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180005749  mov     rcx, cs:SstpSvcGlobals
0x180005750  mov     rcx, [rcx+0A8h]; pio
0x180005757  call    cs:__imp_CloseThreadpoolIo
0x18000575d  mov     rcx, cs:SstpSvcGlobals
0x180005764  mov     [rcx+0A8h], rdi
0x18000576b  lea     rax, [rcx+108h]
0x180005772  cmp     [rax], rax
0x180005775  jz      short loc_1800057BA
0x180005777  mov     rbx, [rcx+108h]
0x18000577e  mov     rcx, [rbx]
0x180005781  mov     rax, [rbx+8]
0x180005785  mov     [rax], rcx
0x180005788  mov     [rcx+8], rax
0x18000578c  lea     rcx, [rbx+40h]; lpCriticalSection
0x180005790  call    cs:__imp_EnterCriticalSection
0x180005796  mov     edx, 2
0x18000579b  lea     rcx, [rbx-0E0h]
0x1800057a2  call    InitiateCallContextCleanup
0x1800057a7  mov     rcx, cs:SstpSvcGlobals
0x1800057ae  lea     rax, [rcx+108h]
0x1800057b5  cmp     [rax], rax
0x1800057b8  jnz     short loc_180005777
0x1800057ba  add     rcx, 0E0h; lpCriticalSection
0x1800057c1  call    cs:__imp_DeleteCriticalSection
0x1800057c7  mov     rcx, cs:SstpSvcGlobals
0x1800057ce  add     rcx, 2C0h; lpCriticalSection
0x1800057d5  call    cs:__imp_DeleteCriticalSection
0x1800057db  mov     rcx, cs:SstpSvcGlobals
0x1800057e2  add     rcx, 138h
0x1800057e9  call    FreeBufferPool
0x1800057ee  mov     rcx, cs:SstpSvcGlobals
0x1800057f5  add     rcx, 218h
0x1800057fc  call    FreeBufferPool
0x180005801  mov     rcx, cs:SstpSvcGlobals
0x180005808  add     rcx, 1A8h
0x18000580f  call    FreeBufferPool
0x180005814  mov     rcx, cs:SstpSvcGlobals
0x18000581b  add     rcx, 0B8h; lpCriticalSection
0x180005822  call    cs:__imp_DeleteCriticalSection
0x180005828  mov     rcx, cs:SstpSvcGlobals
0x18000582f  add     rcx, 0B0h
0x180005836  call    HfDestroyFactory
0x18000583b  mov     rcx, cs:SstpSvcGlobals
0x180005842  xor     r8d, r8d; pvCleanupContext
0x180005845  mov     edx, 1; fCancelPendingCallbacks
0x18000584a  mov     rcx, [rcx+98h]; ptpcg
0x180005851  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180005857  mov     rcx, cs:SstpSvcGlobals
0x18000585e  mov     rcx, [rcx+98h]; ptpcg
0x180005865  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000586b  mov     rcx, cs:SstpSvcGlobals
0x180005872  mov     [rcx+98h], rdi
0x180005879  mov     rcx, [rcx+0A0h]; ptpp
0x180005880  call    cs:__imp_CloseThreadpool
0x180005886  mov     rax, cs:SstpSvcGlobals
0x18000588d  mov     [rax+0A0h], rdi
0x180005894  call    DeinitializeHostRouteInfo
0x180005899  mov     rax, cs:SstpSvcGlobals
0x1800058a0  mov     rbx, [rsp+838h+arg_0]
0x1800058a8  mov     rcx, [rax+48h]; hLogHandle
0x1800058ac  test    rcx, rcx
0x1800058af  jz      short loc_1800058B7
0x1800058b1  call    cs:__imp_RouterLogDeregisterW
0x1800058b7  test    cs:byte_18002D803, 10h
0x1800058be  jz      short loc_1800058FE
0x1800058c0  lea     r8, aDeinitializetr; "DeinitializeTransport"
0x1800058c7  mov     word ptr [rsp+838h+var_818], di
0x1800058cc  lea     rdx, aLeavingWs; "LEaving %ws"
0x1800058d3  lea     rcx, [rsp+838h+var_818]
0x1800058d8  call    FormatRRASErrorString
0x1800058dd  test    cs:byte_18002D803, 10h
0x1800058e4  jz      short loc_1800058FE
0x1800058e6  lea     r8, [rsp+838h+var_818]
0x1800058eb  lea     rdx, RasSSTPSvcTraceInfo
0x1800058f2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800058f9  call    McTemplateU0z_EventWriteTransfer
0x1800058fe  xor     eax, eax
0x180005900  mov     rcx, [rsp+838h+var_18]
0x180005908  xor     rcx, rsp; StackCookie
0x18000590b  call    __security_check_cookie
0x180005910  add     rsp, 830h
0x180005917  pop     rdi
0x180005918  retn
```
