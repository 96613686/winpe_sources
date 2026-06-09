# DeinitializeTransport

- ea: `0x1800059f0`
- end: `0x180005e22`
- name: `DeinitializeTransport`
- size: `1074`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800056e0`

## callees

- `0x180002aac`
- `0x1800059f0`
- `0x1800089dc`
- `0x180008b90`
- `0x180008cd8`
- `0x180008e48`
- `0x180008f00`
- `0x18000d444`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005acc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005acc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005af9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b1f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c9f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005cb9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005d0c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005c9f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005cb9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005d0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bab`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180005b47`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180005b47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180005bd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180005c29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180005bd0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180005c29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180005d41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180005d41`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180005d5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180005d5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180005d7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180005d7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180005b63`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180005c0f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180005b63`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180005c0f`
- `WS2_32!__imp_WSACleanup` at `0x180005b2b`
- `WS2_32!__imp_WSACleanup` at `0x180005b2b`
- `rtutils!RouterLogDeregisterW` at `0x180005db3`
- `rtutils!RouterLogDeregisterW` at `0x180005db3`
- `webio!__imp_WebTerminate` at `0x180005b0a`
- `webio!__imp_WebTerminate` at `0x180005b0a`
- `NduProv!__imp_NduCloseHandle` at `0x180005b86`
- `NduProv!__imp_NduCloseHandle` at `0x180005b86`

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
  v0 = byte_18002E903;
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"Entering %ws", L"DeinitializeTransport");
    v0 = byte_18002E903;
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v13);
      v0 = byte_18002E903;
    }
  }
  v1 = (char *)SstpSvcGlobals;
  if ( !*((_BYTE *)SstpSvcGlobals + 16) )
  {
    if ( (v0 & 0x10) == 0 )
      return 0;
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"LEaving %ws", L"DeinitializeTransport");
    if ( (byte_18002E903 & 0x10) == 0 )
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
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v13) = 0;
    FormatRRASErrorString(&v13, L"LEaving %ws", L"DeinitializeTransport");
    if ( (byte_18002E903 & 0x10) != 0 )
      goto LABEL_23;
  }
  return 0;
}

```

## disassembly

```asm
0x1800059f0  push    rdi
0x1800059f2  sub     rsp, 830h
0x1800059f9  mov     rax, cs:__security_cookie
0x180005a00  xor     rax, rsp
0x180005a03  mov     [rsp+838h+var_18], rax
0x180005a0b  xor     edi, edi
0x180005a0d  lea     rcx, [rsp+838h+var_814]; void *
0x180005a12  xor     edx, edx; Val
0x180005a14  mov     [rsp+838h+var_818], edi
0x180005a18  mov     r8d, 7FCh; Size
0x180005a1e  call    memset_0
0x180005a23  movzx   eax, cs:byte_18002E903
0x180005a2a  test    al, 10h
0x180005a2c  jz      short loc_180005A75
0x180005a2e  lea     r8, aDeinitializetr; "DeinitializeTransport"
0x180005a35  mov     word ptr [rsp+838h+var_818], di
0x180005a3a  lea     rdx, aEnteringWs; "Entering %ws"
0x180005a41  lea     rcx, [rsp+838h+var_818]
0x180005a46  call    FormatRRASErrorString
0x180005a4b  movzx   eax, cs:byte_18002E903
0x180005a52  test    al, 10h
0x180005a54  jz      short loc_180005A75
0x180005a56  lea     r8, [rsp+838h+var_818]
0x180005a5b  lea     rdx, RasSSTPSvcTraceInfo
0x180005a62  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005a69  call    McTemplateU0z_EventWriteTransfer
0x180005a6e  movzx   eax, cs:byte_18002E903
0x180005a75  mov     rcx, cs:SstpSvcGlobals
0x180005a7c  cmp     [rcx+10h], dil
0x180005a80  jnz     short loc_180005AB9
0x180005a82  test    al, 10h
0x180005a84  jz      loc_180005E06
0x180005a8a  lea     r8, aDeinitializetr; "DeinitializeTransport"
0x180005a91  mov     word ptr [rsp+838h+var_818], di
0x180005a96  lea     rdx, aLeavingWs; "LEaving %ws"
0x180005a9d  lea     rcx, [rsp+838h+var_818]
0x180005aa2  call    FormatRRASErrorString
0x180005aa7  test    cs:byte_18002E903, 10h
0x180005aae  jnz     loc_180005DEE
0x180005ab4  jmp     loc_180005E06
0x180005ab9  mov     [rcx+10h], dil
0x180005abd  add     rcx, 2C0h; lpCriticalSection
0x180005ac4  mov     [rsp+838h+arg_0], rbx
0x180005acc  call    cs:__imp_EnterCriticalSection
0x180005ad3  nop     dword ptr [rax+rax+00h]
0x180005ad8  mov     rcx, cs:SstpSvcGlobals
0x180005adf  mov     rbx, [rcx+2E8h]
0x180005ae6  test    rbx, rbx
0x180005ae9  jz      short loc_180005B18
0x180005aeb  mov     [rcx+2E8h], rdi
0x180005af2  add     rcx, 2C0h; lpCriticalSection
0x180005af9  call    cs:__imp_LeaveCriticalSection
0x180005b00  nop     dword ptr [rax+rax+00h]
0x180005b05  xor     edx, edx
0x180005b07  mov     rcx, rbx
0x180005b0a  call    cs:__imp_WebTerminate
0x180005b11  nop     dword ptr [rax+rax+00h]
0x180005b16  jmp     short loc_180005B2B
0x180005b18  add     rcx, 2C0h; lpCriticalSection
0x180005b1f  call    cs:__imp_LeaveCriticalSection
0x180005b26  nop     dword ptr [rax+rax+00h]
0x180005b2b  call    cs:__imp_WSACleanup
0x180005b32  nop     dword ptr [rax+rax+00h]
0x180005b37  mov     rcx, cs:SstpSvcGlobals
0x180005b3e  xor     edx, edx; lpOverlapped
0x180005b40  mov     rcx, [rcx+118h]; hFile
0x180005b47  call    cs:__imp_CancelIoEx
0x180005b4e  nop     dword ptr [rax+rax+00h]
0x180005b53  mov     rcx, cs:SstpSvcGlobals
0x180005b5a  xor     edx, edx; fCancelPendingCallbacks
0x180005b5c  mov     rcx, [rcx+120h]; pio
0x180005b63  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180005b6a  nop     dword ptr [rax+rax+00h]
0x180005b6f  mov     rcx, cs:SstpSvcGlobals
0x180005b76  mov     rax, [rcx+2F0h]
0x180005b7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005b81  jz      short loc_180005BA4
0x180005b83  mov     rcx, rax
0x180005b86  call    cs:__imp_NduCloseHandle
0x180005b8d  nop     dword ptr [rax+rax+00h]
0x180005b92  mov     rcx, cs:SstpSvcGlobals
0x180005b99  mov     qword ptr [rcx+2F0h], 0FFFFFFFFFFFFFFFFh
0x180005ba4  mov     rcx, [rcx+118h]; hObject
0x180005bab  call    cs:__imp_CloseHandle
0x180005bb2  nop     dword ptr [rax+rax+00h]
0x180005bb7  mov     rcx, cs:SstpSvcGlobals
0x180005bbe  mov     qword ptr [rcx+118h], 0FFFFFFFFFFFFFFFFh
0x180005bc9  mov     rcx, [rcx+120h]; pio
0x180005bd0  call    cs:__imp_CloseThreadpoolIo
0x180005bd7  nop     dword ptr [rax+rax+00h]
0x180005bdc  mov     rcx, cs:SstpSvcGlobals
0x180005be3  mov     [rcx+120h], rdi
0x180005bea  cmp     [rcx+40h], rdi
0x180005bee  jz      short loc_180005BFE
0x180005bf0  xor     ecx, ecx
0x180005bf2  call    ShutdownSstpServer
0x180005bf7  mov     rcx, cs:SstpSvcGlobals
0x180005bfe  mov     rax, [rcx+0A8h]
0x180005c05  test    rax, rax
0x180005c08  jz      short loc_180005C43
0x180005c0a  xor     edx, edx; fCancelPendingCallbacks
0x180005c0c  mov     rcx, rax; pio
0x180005c0f  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180005c16  nop     dword ptr [rax+rax+00h]
0x180005c1b  mov     rcx, cs:SstpSvcGlobals
0x180005c22  mov     rcx, [rcx+0A8h]; pio
0x180005c29  call    cs:__imp_CloseThreadpoolIo
0x180005c30  nop     dword ptr [rax+rax+00h]
0x180005c35  mov     rcx, cs:SstpSvcGlobals
0x180005c3c  mov     [rcx+0A8h], rdi
0x180005c43  lea     rax, [rcx+108h]
0x180005c4a  cmp     [rax], rax
0x180005c4d  jz      short loc_180005C98
0x180005c4f  mov     rbx, [rcx+108h]
0x180005c56  mov     rcx, [rbx]
0x180005c59  mov     rax, [rbx+8]
0x180005c5d  mov     [rax], rcx
0x180005c60  mov     [rcx+8], rax
0x180005c64  lea     rcx, [rbx+40h]; lpCriticalSection
0x180005c68  call    cs:__imp_EnterCriticalSection
0x180005c6f  nop     dword ptr [rax+rax+00h]
0x180005c74  mov     edx, 2
0x180005c79  lea     rcx, [rbx-0E0h]
0x180005c80  call    InitiateCallContextCleanup
0x180005c85  mov     rcx, cs:SstpSvcGlobals
0x180005c8c  lea     rax, [rcx+108h]
0x180005c93  cmp     [rax], rax
0x180005c96  jnz     short loc_180005C4F
0x180005c98  add     rcx, 0E0h; lpCriticalSection
0x180005c9f  call    cs:__imp_DeleteCriticalSection
0x180005ca6  nop     dword ptr [rax+rax+00h]
0x180005cab  mov     rcx, cs:SstpSvcGlobals
0x180005cb2  add     rcx, 2C0h; lpCriticalSection
0x180005cb9  call    cs:__imp_DeleteCriticalSection
0x180005cc0  nop     dword ptr [rax+rax+00h]
0x180005cc5  mov     rcx, cs:SstpSvcGlobals
0x180005ccc  add     rcx, 138h
0x180005cd3  call    FreeBufferPool
0x180005cd8  mov     rcx, cs:SstpSvcGlobals
0x180005cdf  add     rcx, 218h
0x180005ce6  call    FreeBufferPool
0x180005ceb  mov     rcx, cs:SstpSvcGlobals
0x180005cf2  add     rcx, 1A8h
0x180005cf9  call    FreeBufferPool
0x180005cfe  mov     rcx, cs:SstpSvcGlobals
0x180005d05  add     rcx, 0B8h; lpCriticalSection
0x180005d0c  call    cs:__imp_DeleteCriticalSection
0x180005d13  nop     dword ptr [rax+rax+00h]
0x180005d18  mov     rcx, cs:SstpSvcGlobals
0x180005d1f  add     rcx, 0B0h
0x180005d26  call    HfDestroyFactory
0x180005d2b  mov     rcx, cs:SstpSvcGlobals
0x180005d32  xor     r8d, r8d; pvCleanupContext
0x180005d35  mov     edx, 1; fCancelPendingCallbacks
0x180005d3a  mov     rcx, [rcx+98h]; ptpcg
0x180005d41  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180005d48  nop     dword ptr [rax+rax+00h]
0x180005d4d  mov     rcx, cs:SstpSvcGlobals
0x180005d54  mov     rcx, [rcx+98h]; ptpcg
0x180005d5b  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180005d62  nop     dword ptr [rax+rax+00h]
0x180005d67  mov     rcx, cs:SstpSvcGlobals
0x180005d6e  mov     [rcx+98h], rdi
0x180005d75  mov     rcx, [rcx+0A0h]; ptpp
0x180005d7c  call    cs:__imp_CloseThreadpool
0x180005d83  nop     dword ptr [rax+rax+00h]
0x180005d88  mov     rax, cs:SstpSvcGlobals
0x180005d8f  mov     [rax+0A0h], rdi
0x180005d96  call    DeinitializeHostRouteInfo
0x180005d9b  mov     rax, cs:SstpSvcGlobals
0x180005da2  mov     rbx, [rsp+838h+arg_0]
0x180005daa  mov     rcx, [rax+48h]; hLogHandle
0x180005dae  test    rcx, rcx
0x180005db1  jz      short loc_180005DBF
0x180005db3  call    cs:__imp_RouterLogDeregisterW
0x180005dba  nop     dword ptr [rax+rax+00h]
0x180005dbf  test    cs:byte_18002E903, 10h
0x180005dc6  jz      short loc_180005E06
0x180005dc8  lea     r8, aDeinitializetr; "DeinitializeTransport"
0x180005dcf  mov     word ptr [rsp+838h+var_818], di
0x180005dd4  lea     rdx, aLeavingWs; "LEaving %ws"
0x180005ddb  lea     rcx, [rsp+838h+var_818]
0x180005de0  call    FormatRRASErrorString
0x180005de5  test    cs:byte_18002E903, 10h
0x180005dec  jz      short loc_180005E06
0x180005dee  lea     r8, [rsp+838h+var_818]
0x180005df3  lea     rdx, RasSSTPSvcTraceInfo
0x180005dfa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005e01  call    McTemplateU0z_EventWriteTransfer
0x180005e06  xor     eax, eax
0x180005e08  mov     rcx, [rsp+838h+var_18]
0x180005e10  xor     rcx, rsp; StackCookie
0x180005e13  call    __security_check_cookie
0x180005e18  add     rsp, 830h
0x180005e1f  pop     rdi
0x180005e20  retn
```
