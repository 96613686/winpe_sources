# ProcessReceivedBytesWorker

- ea: `0x180001a80`
- end: `0x180001ed3`
- name: `ProcessReceivedBytesWorker`
- size: `1107`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001a80`
- `0x180002908`
- `0x180002d70`
- `0x1800077bc`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001af9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001af9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001c48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001cce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001cce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d80`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001bc6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001bc6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001e68`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001e68`

## string_xrefs

- `0x180001da2`: `CoId=%hs:ReceivePacket: Completes with %d`

## pseudocode

```c
void __fastcall ProcessReceivedBytesWorker(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  DWORD v4; // r14d
  int v5; // esi
  __int64 v6; // r8
  char *v7; // rcx
  _BYTE *v8; // rbp
  char *v9; // rdi
  _QWORD *v10; // rax
  char *v11; // rdx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  char *v14; // r13
  HANDLE *v15; // rcx
  DWORD LastError; // r14d
  char *v17; // r14
  char *v18; // rdx
  __int64 v19; // rax
  bool v20; // zf
  struct _RTL_CRITICAL_SECTION *v21; // rcx
  __int64 v22; // rdx
  DWORD v23; // [rsp+40h] [rbp-858h]
  DWORD BytesReturned; // [rsp+44h] [rbp-854h] BYREF
  PTP_WORK pwk; // [rsp+48h] [rbp-850h]
  int v26; // [rsp+50h] [rbp-848h] BYREF
  char v27[2044]; // [rsp+54h] [rbp-844h] BYREF

  pwk = Work;
  BytesReturned = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"Entering %ws", L"ProcessReceivedBytesWorker");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v26);
  }
  v4 = 0;
  v5 = 20;
  EnterCriticalSection((LPCRITICAL_SECTION)(Context + 288));
  *((_DWORD *)Context + 63) |= 0x100u;
  v7 = Context + 435;
  v8 = Context + 435;
  v9 = Context + 416;
  while ( 1 )
  {
    v10 = v9;
    if ( !v5 )
      break;
    v9 = Context + 416;
    v8 = v7;
    v11 = (char *)*((_QWORD *)Context + 52);
    v10 = Context + 416;
    if ( v11 == Context + 416 || v4 )
      break;
    v12 = (_QWORD *)*((_QWORD *)v11 + 1);
    v8 = Context + 435;
    v13 = *(_QWORD *)v11;
    v14 = v11 - 40;
    *v12 = *(_QWORD *)v11;
    *(_QWORD *)(v13 + 8) = v12;
    if ( Context[435] )
    {
      LOBYTE(v6) = 1;
      FreeBufferToPool((char *)SstpSvcGlobals + 424, v11 - 40, v6);
      v10 = Context + 416;
      break;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Context + 288));
    v15 = (HANDLE *)SstpSvcGlobals;
    *((_DWORD *)v14 + 22) = *((_DWORD *)Context + 60);
    LastError = 0;
    v23 = 0;
    if ( !DeviceIoControl(v15[35], 0x128035u, v14 + 88, 0x4008u, 0, 0, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      v23 = LastError;
    }
    if ( (byte_18002D803 & 0x10) != 0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"CoId=%hs:ReceivePacket: Completes with %d", Context + 552, LastError);
      if ( (byte_18002D803 & 0x10) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v26);
    }
    --v5;
    v17 = (char *)SstpSvcGlobals + 424;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 488));
    v18 = v14 - 24;
    if ( *(char **)v18 == v18 )
    {
      v19 = *((_QWORD *)v17 + 5);
      *(_QWORD *)v18 = v19;
      *((_QWORD *)v18 + 1) = v17 + 40;
      *(_QWORD *)(v19 + 8) = v18;
      *((_QWORD *)v17 + 5) = v18;
      ++*(_DWORD *)(*((_QWORD *)v18 + 2) + 28LL);
      if ( ++*((_DWORD *)v17 + 5) >= *((_DWORD *)v17 + 4) )
      {
        FreeUnusedBufferPoolBlocks(v17);
        *((_DWORD *)v17 + 5) = 0;
      }
    }
    else
    {
      ++g_ulDoubleBufferFrees;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 64));
    EnterCriticalSection((LPCRITICAL_SECTION)(Context + 288));
    v4 = v23;
    v7 = Context + 435;
  }
  *((_DWORD *)Context + 63) &= ~0x100u;
  v20 = *v8 == 0;
  Context[432] = 0;
  if ( !v20 )
  {
    v22 = 2;
LABEL_24:
    InitiateCallContextCleanup(Context, v22);
    goto LABEL_19;
  }
  if ( v4 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"CoId=%hs:The received bytes wasn't processed by the miniport. Aborting connection...%d",
        Context + 552,
        v4);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v26);
    }
    v22 = 0;
    goto LABEL_24;
  }
  v21 = (struct _RTL_CRITICAL_SECTION *)(Context + 288);
  if ( (_QWORD *)*v10 == v10 )
  {
    LeaveCriticalSection(v21);
  }
  else
  {
    Context[432] = 1;
    LeaveCriticalSection(v21);
    _InterlockedIncrement((volatile signed __int32 *)Context + 52);
    SubmitThreadpoolWork(pwk);
  }
LABEL_19:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Context + 52, 0xFFFFFFFF) == 1 )
    (*((void (__fastcall **)(char *))Context + 27))(Context + 208);
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"LEaving %ws", L"ProcessReceivedBytesWorker");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v26);
  }
}

```

## disassembly

```asm
0x180001a80  mov     r11, rsp
0x180001a83  push    r12
0x180001a85  sub     rsp, 890h
0x180001a8c  mov     rax, cs:__security_cookie
0x180001a93  xor     rax, rsp
0x180001a96  mov     [rsp+898h+var_48], rax
0x180001a9e  mov     [r11+8], rbx
0x180001aa2  lea     rcx, [rsp+898h+var_844]; void *
0x180001aa7  mov     [r11-10h], rbp
0x180001aab  mov     rbx, rdx
0x180001aae  mov     [r11-18h], rsi
0x180001ab2  xor     r12d, r12d
0x180001ab5  mov     [r11-20h], rdi
0x180001ab9  xor     edx, edx; Val
0x180001abb  mov     [rsp+898h+pwk], r8
0x180001ac0  mov     r8d, 7FCh; Size
0x180001ac6  mov     [r11-30h], r14
0x180001aca  mov     [r11-38h], r15
0x180001ace  mov     [rsp+898h+BytesReturned], r12d
0x180001ad3  mov     [rsp+898h+var_848], r12d
0x180001ad8  call    memset_0
0x180001add  test    cs:byte_18002D803, 10h
0x180001ae4  jnz     loc_180001D38
0x180001aea  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001af1  mov     r14d, r12d
0x180001af4  mov     esi, 14h
0x180001af9  call    cs:__imp_EnterCriticalSection
0x180001aff  or      dword ptr [rbx+0FCh], 100h
0x180001b09  lea     rcx, [rbx+1B3h]
0x180001b10  mov     rbp, rcx
0x180001b13  mov     [rsp+898h+var_28], r13
0x180001b1b  lea     rdi, [rbx+1A0h]
0x180001b22  mov     rax, rdi
0x180001b25  test    esi, esi
0x180001b27  jz      loc_180001C7E
0x180001b2d  lea     rdi, [rbx+1A0h]
0x180001b34  mov     rbp, rcx
0x180001b37  mov     rdx, [rdi]
0x180001b3a  mov     rax, rdi
0x180001b3d  cmp     rdx, rdi
0x180001b40  jz      loc_180001C7E
0x180001b46  test    r14d, r14d
0x180001b49  jnz     loc_180001C7E
0x180001b4f  mov     rax, [rdx+8]
0x180001b53  lea     rbp, [rbx+1B3h]
0x180001b5a  mov     rcx, [rdx]
0x180001b5d  lea     r13, [rdx-28h]
0x180001b61  mov     [rax], rcx
0x180001b64  mov     [rcx+8], rax
0x180001b68  cmp     [rbp+0], r14b
0x180001b6c  jnz     loc_180001C62
0x180001b72  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001b79  call    cs:__imp_LeaveCriticalSection
0x180001b7f  mov     eax, [rbx+0F0h]
0x180001b85  lea     r8, [r13+58h]; lpInBuffer
0x180001b89  mov     rcx, cs:SstpSvcGlobals
0x180001b90  mov     edx, 128035h; dwIoControlCode
0x180001b95  mov     [r8], eax
0x180001b98  mov     r9d, 4008h; nInBufferSize
0x180001b9e  mov     [rsp+898h+lpOverlapped], r12; lpOverlapped
0x180001ba3  lea     rax, [rsp+898h+BytesReturned]
0x180001ba8  mov     [rsp+898h+lpBytesReturned], rax; lpBytesReturned
0x180001bad  mov     r14d, r12d
0x180001bb0  mov     rcx, [rcx+118h]; hDevice
0x180001bb7  mov     [rsp+898h+nOutBufferSize], r12d; nOutBufferSize
0x180001bbc  mov     [rsp+898h+lpOutBuffer], r12; lpOutBuffer
0x180001bc1  mov     [rsp+898h+var_858], r12d
0x180001bc6  call    cs:__imp_DeviceIoControl
0x180001bcc  test    eax, eax
0x180001bce  jz      loc_180001D80
0x180001bd4  test    cs:byte_18002D803, 10h
0x180001bdb  jnz     loc_180001D92
0x180001be1  mov     r14, cs:SstpSvcGlobals
0x180001be8  dec     esi
0x180001bea  add     r14, 1A8h
0x180001bf1  lea     rcx, [r14+40h]; lpCriticalSection
0x180001bf5  call    cs:__imp_EnterCriticalSection
0x180001bfb  lea     rdx, [r13-18h]
0x180001bff  cmp     [rdx], rdx
0x180001c02  jnz     loc_180001DDD
0x180001c08  mov     rax, [r14+28h]
0x180001c0c  lea     rcx, [r14+28h]
0x180001c10  mov     [rdx], rax
0x180001c13  mov     [rdx+8], rcx
0x180001c17  mov     [rax+8], rdx
0x180001c1b  mov     [rcx], rdx
0x180001c1e  mov     rax, [rdx+10h]
0x180001c22  inc     dword ptr [rax+1Ch]
0x180001c25  inc     dword ptr [r14+14h]
0x180001c29  mov     eax, [r14+14h]
0x180001c2d  cmp     eax, [r14+10h]
0x180001c31  jnb     loc_180001DE8
0x180001c37  lea     rcx, [r14+40h]; lpCriticalSection
0x180001c3b  call    cs:__imp_LeaveCriticalSection
0x180001c41  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001c48  call    cs:__imp_EnterCriticalSection
0x180001c4e  mov     r14d, [rsp+898h+var_858]
0x180001c53  lea     rcx, [rbx+1B3h]
0x180001c5a  xor     r12d, r12d
0x180001c5d  jmp     loc_180001B22
0x180001c62  mov     rcx, cs:SstpSvcGlobals
0x180001c69  mov     r8b, 1
0x180001c6c  add     rcx, 1A8h
0x180001c73  mov     rdx, r13
0x180001c76  call    FreeBufferToPool
0x180001c7b  mov     rax, rdi
0x180001c7e  and     dword ptr [rbx+0FCh], 0FFFFFEFFh
0x180001c88  cmp     byte ptr [rbp+0], 0
0x180001c8c  mov     rbp, [rsp+898h+var_10]
0x180001c94  mov     r13, [rsp+898h+var_28]
0x180001c9c  mov     rdi, [rsp+898h+var_20]
0x180001ca4  mov     rsi, [rsp+898h+var_18]
0x180001cac  mov     byte ptr [rbx+1B0h], 0
0x180001cb3  jnz     short loc_180001D29
0x180001cb5  test    r14d, r14d
0x180001cb8  jnz     loc_180001DFD
0x180001cbe  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001cc5  cmp     [rax], rax
0x180001cc8  jnz     loc_180001E4F
0x180001cce  call    cs:__imp_LeaveCriticalSection
0x180001cd4  mov     eax, 0FFFFFFFFh
0x180001cd9  lock xadd [rbx+0D0h], eax
0x180001ce1  mov     r15, [rsp+898h+var_38]
0x180001ce9  mov     r14, [rsp+898h+var_30]
0x180001cf1  cmp     eax, 1
0x180001cf4  jz      loc_180001E73
0x180001cfa  test    cs:byte_18002D803, 10h
0x180001d01  mov     rbx, [rsp+898h+arg_0]
0x180001d09  jnz     loc_180001E8B
0x180001d0f  mov     rcx, [rsp+898h+var_48]
0x180001d17  xor     rcx, rsp; StackCookie
0x180001d1a  call    __security_check_cookie
0x180001d1f  add     rsp, 890h
0x180001d26  pop     r12
0x180001d28  retn
0x180001d29  mov     edx, 2
0x180001d2e  mov     rcx, rbx
0x180001d31  call    InitiateCallContextCleanup
0x180001d36  jmp     short loc_180001CD4
0x180001d38  lea     r8, aProcessreceive; "ProcessReceivedBytesWorker"
0x180001d3f  mov     word ptr [rsp+898h+var_848], r12w
0x180001d45  lea     rdx, aEnteringWs; "Entering %ws"
0x180001d4c  lea     rcx, [rsp+898h+var_848]
0x180001d51  call    FormatRRASErrorString
0x180001d56  test    cs:byte_18002D803, 10h
0x180001d5d  jz      loc_180001AEA
0x180001d63  lea     r8, [rsp+898h+var_848]
0x180001d68  lea     rdx, RasSSTPSvcTraceInfo
0x180001d6f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001d76  call    McTemplateU0z_EventWriteTransfer
0x180001d7b  jmp     loc_180001AEA
0x180001d80  call    cs:__imp_GetLastError
0x180001d86  mov     r14d, eax
0x180001d89  mov     [rsp+898h+var_858], eax
0x180001d8d  jmp     loc_180001BD4
0x180001d92  lea     r8, [rbx+228h]
0x180001d99  mov     word ptr [rsp+898h+var_848], r12w
0x180001d9f  mov     r9d, r14d
0x180001da2  lea     rdx, aCoidHsReceivep; "CoId=%hs:ReceivePacket: Completes with "...
0x180001da9  lea     rcx, [rsp+898h+var_848]
0x180001dae  call    FormatRRASErrorString
0x180001db3  test    cs:byte_18002D803, 10h
0x180001dba  jz      loc_180001BE1
0x180001dc0  lea     r8, [rsp+898h+var_848]
0x180001dc5  lea     rdx, RasSSTPSvcTraceInfo
0x180001dcc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001dd3  call    McTemplateU0z_EventWriteTransfer
0x180001dd8  jmp     loc_180001BE1
0x180001ddd  inc     cs:g_ulDoubleBufferFrees
0x180001de3  jmp     loc_180001C37
0x180001de8  mov     rcx, r14
0x180001deb  call    FreeUnusedBufferPoolBlocks
0x180001df0  mov     dword ptr [r14+14h], 0
0x180001df8  jmp     loc_180001C37
0x180001dfd  test    cs:byte_18002D803, 8
0x180001e04  jz      short loc_180001E48
0x180001e06  lea     r8, [rbx+228h]
0x180001e0d  mov     word ptr [rsp+898h+var_848], r12w
0x180001e13  mov     r9d, r14d
0x180001e16  lea     rdx, aCoidHsTheRecei; "CoId=%hs:The received bytes wasn't proc"...
0x180001e1d  lea     rcx, [rsp+898h+var_848]
0x180001e22  call    FormatRRASErrorString
0x180001e27  test    cs:byte_18002D803, 8
0x180001e2e  jz      short loc_180001E48
0x180001e30  lea     r8, [rsp+898h+var_848]
0x180001e35  lea     rdx, RasSSTPSvcTraceError
0x180001e3c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001e43  call    McTemplateU0z_EventWriteTransfer
0x180001e48  xor     edx, edx
0x180001e4a  jmp     loc_180001D2E
0x180001e4f  mov     byte ptr [rbx+1B0h], 1
0x180001e56  call    cs:__imp_LeaveCriticalSection
0x180001e5c  lock inc dword ptr [rbx+0D0h]
0x180001e63  mov     rcx, [rsp+898h+pwk]; pwk
0x180001e68  call    cs:__imp_SubmitThreadpoolWork
0x180001e6e  jmp     loc_180001CD4
0x180001e73  mov     rax, [rbx+0D8h]
0x180001e7a  lea     rcx, [rbx+0D0h]
0x180001e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e86  jmp     loc_180001CFA
0x180001e8b  lea     r8, aProcessreceive; "ProcessReceivedBytesWorker"
0x180001e92  mov     word ptr [rsp+898h+var_848], r12w
0x180001e98  lea     rdx, aLeavingWs; "LEaving %ws"
0x180001e9f  lea     rcx, [rsp+898h+var_848]
0x180001ea4  call    FormatRRASErrorString
0x180001ea9  test    cs:byte_18002D803, 10h
0x180001eb0  jz      loc_180001D0F
0x180001eb6  lea     r8, [rsp+898h+var_848]
0x180001ebb  lea     rdx, RasSSTPSvcTraceInfo
0x180001ec2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001ec9  call    McTemplateU0z_EventWriteTransfer
0x180001ece  jmp     loc_180001D0F
```
