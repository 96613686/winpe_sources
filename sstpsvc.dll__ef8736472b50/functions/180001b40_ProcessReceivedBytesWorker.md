# ProcessReceivedBytesWorker

- ea: `0x180001b40`
- end: `0x180001fd0`
- name: `ProcessReceivedBytesWorker`
- size: `1168`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001b40`
- `0x180002aac`
- `0x180002f80`
- `0x180007f48`
- `0x1800089dc`
- `0x180008b90`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001cc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001bb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001cc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001d26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001db2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001c3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001db2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e6b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001c92`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180001c92`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001f5f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001f5f`

## string_xrefs

- `0x180001e93`: `CoId=%hs:ReceivePacket: Completes with %d`

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
  unsigned int v22; // edx
  DWORD v23; // [rsp+40h] [rbp-858h]
  DWORD BytesReturned; // [rsp+44h] [rbp-854h] BYREF
  PTP_WORK pwk; // [rsp+48h] [rbp-850h]
  int v26; // [rsp+50h] [rbp-848h] BYREF
  char v27[2044]; // [rsp+54h] [rbp-844h] BYREF

  pwk = Work;
  BytesReturned = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"Entering %ws", L"ProcessReceivedBytesWorker");
    if ( (byte_18002E903 & 0x10) != 0 )
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
    if ( (byte_18002E903 & 0x10) != 0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"CoId=%hs:ReceivePacket: Completes with %d", Context + 552, LastError);
      if ( (byte_18002E903 & 0x10) != 0 )
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
    InitiateCallContextCleanup((__int64)Context, v22);
    goto LABEL_19;
  }
  if ( v4 )
  {
    if ( (byte_18002E903 & 8) != 0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"CoId=%hs:The received bytes wasn't processed by the miniport. Aborting connection...%d",
        Context + 552,
        v4);
      if ( (byte_18002E903 & 8) != 0 )
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
  if ( (byte_18002E903 & 0x10) != 0 )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"LEaving %ws", L"ProcessReceivedBytesWorker");
    if ( (byte_18002E903 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v26);
  }
}

```

## disassembly

```asm
0x180001b40  mov     r11, rsp
0x180001b43  push    r12
0x180001b45  sub     rsp, 890h
0x180001b4c  mov     rax, cs:__security_cookie
0x180001b53  xor     rax, rsp
0x180001b56  mov     [rsp+898h+var_48], rax
0x180001b5e  mov     [r11+8], rbx
0x180001b62  lea     rcx, [rsp+898h+var_844]; void *
0x180001b67  mov     [r11-10h], rbp
0x180001b6b  mov     rbx, rdx
0x180001b6e  mov     [r11-18h], rsi
0x180001b72  xor     r12d, r12d
0x180001b75  mov     [r11-20h], rdi
0x180001b79  xor     edx, edx; Val
0x180001b7b  mov     [rsp+898h+pwk], r8
0x180001b80  mov     r8d, 7FCh; Size
0x180001b86  mov     [r11-30h], r14
0x180001b8a  mov     [r11-38h], r15
0x180001b8e  mov     [rsp+898h+BytesReturned], r12d
0x180001b93  mov     [rsp+898h+var_848], r12d
0x180001b98  call    memset_0
0x180001b9d  test    cs:byte_18002E903, 10h
0x180001ba4  jnz     loc_180001E23
0x180001baa  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001bb1  mov     r14d, r12d
0x180001bb4  mov     esi, 14h
0x180001bb9  call    cs:__imp_EnterCriticalSection
0x180001bc0  nop     dword ptr [rax+rax+00h]
0x180001bc5  or      dword ptr [rbx+0FCh], 100h
0x180001bcf  lea     rcx, [rbx+1B3h]
0x180001bd6  mov     rbp, rcx
0x180001bd9  mov     [rsp+898h+var_28], r13
0x180001be1  lea     rdi, [rbx+1A0h]
0x180001be8  mov     rax, rdi
0x180001beb  test    esi, esi
0x180001bed  jz      loc_180001D62
0x180001bf3  lea     rdi, [rbx+1A0h]
0x180001bfa  mov     rbp, rcx
0x180001bfd  mov     rdx, [rdi]
0x180001c00  mov     rax, rdi
0x180001c03  cmp     rdx, rdi
0x180001c06  jz      loc_180001D62
0x180001c0c  test    r14d, r14d
0x180001c0f  jnz     loc_180001D62
0x180001c15  mov     rax, [rdx+8]
0x180001c19  lea     rbp, [rbx+1B3h]
0x180001c20  mov     rcx, [rdx]
0x180001c23  lea     r13, [rdx-28h]
0x180001c27  mov     [rax], rcx
0x180001c2a  mov     [rcx+8], rax
0x180001c2e  cmp     [rbp+0], r14b
0x180001c32  jnz     loc_180001D46
0x180001c38  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001c3f  call    cs:__imp_LeaveCriticalSection
0x180001c46  nop     dword ptr [rax+rax+00h]
0x180001c4b  mov     eax, [rbx+0F0h]
0x180001c51  lea     r8, [r13+58h]; lpInBuffer
0x180001c55  mov     rcx, cs:SstpSvcGlobals
0x180001c5c  mov     edx, 128035h; dwIoControlCode
0x180001c61  mov     [r8], eax
0x180001c64  mov     r9d, 4008h; nInBufferSize
0x180001c6a  mov     [rsp+898h+lpOverlapped], r12; lpOverlapped
0x180001c6f  lea     rax, [rsp+898h+BytesReturned]
0x180001c74  mov     [rsp+898h+lpBytesReturned], rax; lpBytesReturned
0x180001c79  mov     r14d, r12d
0x180001c7c  mov     rcx, [rcx+118h]; hDevice
0x180001c83  mov     [rsp+898h+nOutBufferSize], r12d; nOutBufferSize
0x180001c88  mov     [rsp+898h+lpOutBuffer], r12; lpOutBuffer
0x180001c8d  mov     [rsp+898h+var_858], r12d
0x180001c92  call    cs:__imp_DeviceIoControl
0x180001c99  nop     dword ptr [rax+rax+00h]
0x180001c9e  test    eax, eax
0x180001ca0  jz      loc_180001E6B
0x180001ca6  test    cs:byte_18002E903, 10h
0x180001cad  jnz     loc_180001E83
0x180001cb3  mov     r14, cs:SstpSvcGlobals
0x180001cba  dec     esi
0x180001cbc  add     r14, 1A8h
0x180001cc3  lea     rcx, [r14+40h]; lpCriticalSection
0x180001cc7  call    cs:__imp_EnterCriticalSection
0x180001cce  nop     dword ptr [rax+rax+00h]
0x180001cd3  lea     rdx, [r13-18h]
0x180001cd7  cmp     [rdx], rdx
0x180001cda  jnz     loc_180001ECE
0x180001ce0  mov     rax, [r14+28h]
0x180001ce4  lea     rcx, [r14+28h]
0x180001ce8  mov     [rdx], rax
0x180001ceb  mov     [rdx+8], rcx
0x180001cef  mov     [rax+8], rdx
0x180001cf3  mov     [rcx], rdx
0x180001cf6  mov     rax, [rdx+10h]
0x180001cfa  inc     dword ptr [rax+1Ch]
0x180001cfd  inc     dword ptr [r14+14h]
0x180001d01  mov     eax, [r14+14h]
0x180001d05  cmp     eax, [r14+10h]
0x180001d09  jnb     loc_180001ED9
0x180001d0f  lea     rcx, [r14+40h]; lpCriticalSection
0x180001d13  call    cs:__imp_LeaveCriticalSection
0x180001d1a  nop     dword ptr [rax+rax+00h]
0x180001d1f  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001d26  call    cs:__imp_EnterCriticalSection
0x180001d2d  nop     dword ptr [rax+rax+00h]
0x180001d32  mov     r14d, [rsp+898h+var_858]
0x180001d37  lea     rcx, [rbx+1B3h]
0x180001d3e  xor     r12d, r12d
0x180001d41  jmp     loc_180001BE8
0x180001d46  mov     rcx, cs:SstpSvcGlobals
0x180001d4d  mov     r8b, 1
0x180001d50  add     rcx, 1A8h
0x180001d57  mov     rdx, r13
0x180001d5a  call    FreeBufferToPool
0x180001d5f  mov     rax, rdi
0x180001d62  and     dword ptr [rbx+0FCh], 0FFFFFEFFh
0x180001d6c  cmp     byte ptr [rbp+0], 0
0x180001d70  mov     rbp, [rsp+898h+var_10]
0x180001d78  mov     r13, [rsp+898h+var_28]
0x180001d80  mov     rdi, [rsp+898h+var_20]
0x180001d88  mov     rsi, [rsp+898h+var_18]
0x180001d90  mov     byte ptr [rbx+1B0h], 0
0x180001d97  jnz     short loc_180001E14
0x180001d99  test    r14d, r14d
0x180001d9c  jnz     loc_180001EEE
0x180001da2  lea     rcx, [rbx+120h]; lpCriticalSection
0x180001da9  cmp     [rax], rax
0x180001dac  jnz     loc_180001F40
0x180001db2  call    cs:__imp_LeaveCriticalSection
0x180001db9  nop     dword ptr [rax+rax+00h]
0x180001dbe  mov     eax, 0FFFFFFFFh
0x180001dc3  lock xadd [rbx+0D0h], eax
0x180001dcb  mov     r15, [rsp+898h+var_38]
0x180001dd3  mov     r14, [rsp+898h+var_30]
0x180001ddb  cmp     eax, 1
0x180001dde  jz      loc_180001F70
0x180001de4  test    cs:byte_18002E903, 10h
0x180001deb  mov     rbx, [rsp+898h+arg_0]
0x180001df3  jnz     loc_180001F88
0x180001df9  mov     rcx, [rsp+898h+var_48]
0x180001e01  xor     rcx, rsp; StackCookie
0x180001e04  call    __security_check_cookie
0x180001e09  add     rsp, 890h
0x180001e10  pop     r12
0x180001e12  retn
0x180001e14  mov     edx, 2
0x180001e19  mov     rcx, rbx
0x180001e1c  call    InitiateCallContextCleanup
0x180001e21  jmp     short loc_180001DBE
0x180001e23  lea     r8, aProcessreceive; "ProcessReceivedBytesWorker"
0x180001e2a  mov     word ptr [rsp+898h+var_848], r12w
0x180001e30  lea     rdx, aEnteringWs; "Entering %ws"
0x180001e37  lea     rcx, [rsp+898h+var_848]
0x180001e3c  call    FormatRRASErrorString
0x180001e41  test    cs:byte_18002E903, 10h
0x180001e48  jz      loc_180001BAA
0x180001e4e  lea     r8, [rsp+898h+var_848]
0x180001e53  lea     rdx, RasSSTPSvcTraceInfo
0x180001e5a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001e61  call    McTemplateU0z_EventWriteTransfer
0x180001e66  jmp     loc_180001BAA
0x180001e6b  call    cs:__imp_GetLastError
0x180001e72  nop     dword ptr [rax+rax+00h]
0x180001e77  mov     r14d, eax
0x180001e7a  mov     [rsp+898h+var_858], eax
0x180001e7e  jmp     loc_180001CA6
0x180001e83  lea     r8, [rbx+228h]
0x180001e8a  mov     word ptr [rsp+898h+var_848], r12w
0x180001e90  mov     r9d, r14d
0x180001e93  lea     rdx, aCoidHsReceivep; "CoId=%hs:ReceivePacket: Completes with "...
0x180001e9a  lea     rcx, [rsp+898h+var_848]
0x180001e9f  call    FormatRRASErrorString
0x180001ea4  test    cs:byte_18002E903, 10h
0x180001eab  jz      loc_180001CB3
0x180001eb1  lea     r8, [rsp+898h+var_848]
0x180001eb6  lea     rdx, RasSSTPSvcTraceInfo
0x180001ebd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001ec4  call    McTemplateU0z_EventWriteTransfer
0x180001ec9  jmp     loc_180001CB3
0x180001ece  inc     cs:g_ulDoubleBufferFrees
0x180001ed4  jmp     loc_180001D0F
0x180001ed9  mov     rcx, r14
0x180001edc  call    FreeUnusedBufferPoolBlocks
0x180001ee1  mov     dword ptr [r14+14h], 0
0x180001ee9  jmp     loc_180001D0F
0x180001eee  test    cs:byte_18002E903, 8
0x180001ef5  jz      short loc_180001F39
0x180001ef7  lea     r8, [rbx+228h]
0x180001efe  mov     word ptr [rsp+898h+var_848], r12w
0x180001f04  mov     r9d, r14d
0x180001f07  lea     rdx, aCoidHsTheRecei; "CoId=%hs:The received bytes wasn't proc"...
0x180001f0e  lea     rcx, [rsp+898h+var_848]
0x180001f13  call    FormatRRASErrorString
0x180001f18  test    cs:byte_18002E903, 8
0x180001f1f  jz      short loc_180001F39
0x180001f21  lea     r8, [rsp+898h+var_848]
0x180001f26  lea     rdx, RasSSTPSvcTraceError
0x180001f2d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001f34  call    McTemplateU0z_EventWriteTransfer
0x180001f39  xor     edx, edx
0x180001f3b  jmp     loc_180001E19
0x180001f40  mov     byte ptr [rbx+1B0h], 1
0x180001f47  call    cs:__imp_LeaveCriticalSection
0x180001f4e  nop     dword ptr [rax+rax+00h]
0x180001f53  lock inc dword ptr [rbx+0D0h]
0x180001f5a  mov     rcx, [rsp+898h+pwk]; pwk
0x180001f5f  call    cs:__imp_SubmitThreadpoolWork
0x180001f66  nop     dword ptr [rax+rax+00h]
0x180001f6b  jmp     loc_180001DBE
0x180001f70  mov     rax, [rbx+0D8h]
0x180001f77  lea     rcx, [rbx+0D0h]
0x180001f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f83  jmp     loc_180001DE4
0x180001f88  lea     r8, aProcessreceive; "ProcessReceivedBytesWorker"
0x180001f8f  mov     word ptr [rsp+898h+var_848], r12w
0x180001f95  lea     rdx, aLeavingWs; "LEaving %ws"
0x180001f9c  lea     rcx, [rsp+898h+var_848]
0x180001fa1  call    FormatRRASErrorString
0x180001fa6  test    cs:byte_18002E903, 10h
0x180001fad  jz      loc_180001DF9
0x180001fb3  lea     r8, [rsp+898h+var_848]
0x180001fb8  lea     rdx, RasSSTPSvcTraceInfo
0x180001fbf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180001fc6  call    McTemplateU0z_EventWriteTransfer
0x180001fcb  jmp     loc_180001DF9
```
