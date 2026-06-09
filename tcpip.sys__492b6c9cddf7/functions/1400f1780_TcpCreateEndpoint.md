# TcpCreateEndpoint

- ea: `0x1400f1780`
- end: `0x1400f1bae`
- name: `TcpCreateEndpoint`
- size: `1070`
- prototype: `__int64 __fastcall(int, int, int, int, char, __int64, PEPROCESS Process, PVOID Object, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f1720`

## callees

- `0x1400158e0`
- `0x140017060`
- `0x140017ca0`
- `0x140018ee0`
- `0x140039860`
- `0x14003a490`
- `0x140053e04`
- `0x1400aebd8`
- `0x1400f1780`
- `0x140115368`
- `0x140130150`
- `0x14014f35c`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x1400f1912`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400f1912`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f17da`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f1952`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f19c6`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f17da`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f1952`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f19c6`
- `ntoskrnl!ObfReferenceObject` at `0x1400f1983`
- `ntoskrnl!ObfReferenceObject` at `0x1400f19a3`
- `ntoskrnl!ObfReferenceObject` at `0x1400f1983`
- `ntoskrnl!ObfReferenceObject` at `0x1400f19a3`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400f1ac8`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400f1ac8`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f183d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f1a5b`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f183d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f1a5b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f18b1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f18b1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f1b41`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f1b41`
- `ntoskrnl!PsGetProcessId` at `0x1400f181f`
- `ntoskrnl!PsGetProcessId` at `0x1400f1a34`
- `ntoskrnl!PsGetProcessId` at `0x1400f181f`
- `ntoskrnl!PsGetProcessId` at `0x1400f1a34`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f17f3`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f196b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f17f3`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f196b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400f18f7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400f18f7`
- `NETIO!NetioInsertWorkQueue` at `0x1400f1b76`
- `NETIO!NetioInsertWorkQueue` at `0x1400f1b76`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1400f19f1`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1400f19f1`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f19b8`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f19df`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f19b8`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f19df`

## pseudocode

```c
__int64 __fastcall TcpCreateEndpoint(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        char a5,
        __int64 a6,
        PEPROCESS Process,
        PVOID Object,
        __int64 a9)
{
  struct _KPROCESS *CurrentProcess; // rdi
  __int64 v13; // rbp
  int v14; // r9d
  char *v16; // rbx
  char *v17; // rax
  char *v18; // rsi
  struct _LIST_ENTRY *Blink; // rax
  __int64 v20; // rcx
  unsigned int ThreadObjectCompartmentId; // eax
  __int64 v22; // rax
  int v23; // r9d
  __int128 v24; // [rsp+50h] [rbp-48h] BYREF

  CurrentProcess = Process;
  v13 = InetFindAndReferenceAf(&TcpInetTransport, a4);
  if ( v13 )
  {
    v16 = (char *)TcpEndpointPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v16[176] )
      PplpLazyInitializeLookasideList(TcpEndpointPool, v16 + 64);
    v17 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v16 + 64));
    v18 = v17;
    if ( v17 )
    {
      TcpipTraceActivityIDStart(v17, 1);
      memset(v18, 0, 0x130u);
      KeInitializeSpinLock((PKSPIN_LOCK)v18);
      KeInitializeSemaphore((PRKSEMAPHORE)v18 + 8, 1, 1);
      *((_QWORD *)v18 + 1) = 1;
      *((_QWORD *)v18 + 4) = v13;
      *((_QWORD *)v18 + 13) = v13;
      *((_QWORD *)v18 + 3) = a1;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 16)) <= 1 )
        __fastfail(0xEu);
      if ( Process )
      {
        Blink = (struct _LIST_ENTRY *)Process;
      }
      else if ( (unsigned int)KeIsExecutingDpc() )
      {
        Blink = WPP_MAIN_CB.Queue.ListEntry.Blink;
      }
      else
      {
        Blink = (struct _LIST_ENTRY *)PsGetCurrentProcess();
      }
      *((_QWORD *)v18 + 5) = Blink;
      ObfReferenceObject(Blink);
      if ( Object )
      {
        *((_QWORD *)v18 + 6) = Object;
        ObfReferenceObject(Object);
      }
      v20 = *((_QWORD *)v18 + 6);
      if ( v20 )
      {
        ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(v20);
      }
      else if ( (unsigned int)KeIsExecutingDpc() )
      {
        ThreadObjectCompartmentId = NdisGetProcessObjectCompartmentId(*((_QWORD *)v18 + 5));
      }
      else
      {
        ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
      }
      v22 = InetFindAndReferenceCompartmentAf(*((_QWORD *)v18 + 4), ThreadObjectCompartmentId);
      *((_QWORD *)v18 + 11) = v22;
      if ( v22 )
      {
        *((_QWORD *)v18 + 7) = a9;
        *((_QWORD *)v18 + 9) = InetGetProcessTag(Process, Object);
        KeQuerySystemTimePrecise(v18 + 64);
        TcpInitializeOptions(v13, v18 + 168);
        *((_OWORD *)v18 + 13) = 0;
        *((_OWORD *)v18 + 14) = 0;
        *((_QWORD *)v18 + 30) = 0;
        if ( (a5 & 1) != 0 )
          v18[206] |= 0x40u;
        *((_QWORD *)v18 + 19) = a2;
        *((_QWORD *)v18 + 20) = a3;
        if ( Microsoft_Windows_Networking_CorrelationEnabled && a6 )
          TcpipEtwTransferActivity(v18, a6, 1);
        if ( KeGetCurrentIrql() )
        {
          NetioInsertWorkQueue(TcpCreateEndpointWorkQueue, v18 + 144);
        }
        else
        {
          *((_QWORD *)v18 + 18) = 0;
          TcpCreateEndpointWorkQueueRoutine(v18 + 144);
        }
        return 259;
      }
      else
      {
        if ( dword_1402201D4 )
        {
          v24 = 0;
          if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
          {
            PsGetProcessId(*((PEPROCESS *)v18 + 5));
            v24 = (unsigned __int64)v18;
            PsGetProcessStartKey(*((_QWORD *)v18 + 5));
            McTemplateK0qbr0qqqqx_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)TCP_CREATE_ENDPOINT_COMPARTMENT_FAILURE,
              (unsigned int)&v24,
              v23);
          }
        }
        TcpCloseEndpoint((PKSPIN_LOCK)v18);
        return 3221225732LL;
      }
    }
    else
    {
      InetDereferenceAf(v13);
      return 3221225495LL;
    }
  }
  else
  {
    if ( !Process )
    {
      if ( (unsigned int)KeIsExecutingDpc() )
        CurrentProcess = (struct _KPROCESS *)WPP_MAIN_CB.Queue.ListEntry.Blink;
      else
        CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
    }
    if ( dword_1402201D4 )
    {
      v24 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
      {
        PsGetProcessId(CurrentProcess);
        v24 = 0u;
        PsGetProcessStartKey(CurrentProcess);
        McTemplateK0qbr0qqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CREATE_ENDPOINT_AF_FAILURE,
          (unsigned int)&v24,
          v14);
      }
    }
    return 3221266451LL;
  }
}

```

## disassembly

```asm
0x1400f1780  mov     [rsp+arg_0], rbx
0x1400f1785  mov     [rsp+arg_8], rbp
0x1400f178a  push    rsi
0x1400f178b  push    rdi
0x1400f178c  push    r12
0x1400f178e  push    r14
0x1400f1790  push    r15
0x1400f1792  sub     rsp, 70h
0x1400f1796  mov     rax, cs:__security_cookie
0x1400f179d  xor     rax, rsp
0x1400f17a0  mov     [rsp+98h+var_38], rax
0x1400f17a5  mov     rdi, [rsp+98h+Process]
0x1400f17ad  mov     r12, rdx
0x1400f17b0  movzx   esi, r9w
0x1400f17b4  mov     r14, rcx
0x1400f17b7  movzx   edx, si
0x1400f17ba  lea     rcx, TcpInetTransport
0x1400f17c1  mov     r15, r8
0x1400f17c4  call    InetFindAndReferenceAf
0x1400f17c9  mov     rbp, rax
0x1400f17cc  test    rax, rax
0x1400f17cf  jnz     loc_1400F1880
0x1400f17d5  test    rdi, rdi
0x1400f17d8  jnz     short loc_1400F1802
0x1400f17da  call    cs:__imp_KeIsExecutingDpc
0x1400f17e1  nop     dword ptr [rax+rax+00h]
0x1400f17e6  test    eax, eax
0x1400f17e8  jz      short loc_1400F17F3
0x1400f17ea  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400f17f1  jmp     short loc_1400F1802
0x1400f17f3  call    cs:__imp_PsGetCurrentProcess
0x1400f17fa  nop     dword ptr [rax+rax+00h]
0x1400f17ff  mov     rdi, rax
0x1400f1802  cmp     cs:dword_1402201D4, 0
0x1400f1809  jz      short loc_1400F1876
0x1400f180b  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, 0
0x1400f1812  xorps   xmm0, xmm0
0x1400f1815  movups  [rsp+98h+var_48], xmm0
0x1400f181a  jge     short loc_1400F1876
0x1400f181c  mov     rcx, rdi; Process
0x1400f181f  call    cs:__imp_PsGetProcessId
0x1400f1826  nop     dword ptr [rax+rax+00h]
0x1400f182b  xor     ebp, ebp
0x1400f182d  mov     rcx, rdi
0x1400f1830  mov     rbx, rax
0x1400f1833  mov     qword ptr [rsp+98h+var_48+8], rbp
0x1400f1838  mov     qword ptr [rsp+98h+var_48], rbp
0x1400f183d  call    cs:__imp_PsGetProcessStartKey
0x1400f1844  nop     dword ptr [rax+rax+00h]
0x1400f1849  mov     [rsp+98h+var_50], rax
0x1400f184e  lea     r8, [rsp+98h+var_48]
0x1400f1853  mov     [rsp+98h+var_58], esi
0x1400f1857  lea     rdx, TCP_CREATE_ENDPOINT_AF_FAILURE
0x1400f185e  mov     [rsp+98h+var_60], ebp
0x1400f1862  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400f1869  mov     [rsp+98h+var_68], ebx
0x1400f186d  mov     [rsp+98h+var_70], ebp
0x1400f1871  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x1400f1876  mov     eax, 0C000A013h
0x1400f187b  jmp     loc_1400F1B87
0x1400f1880  mov     eax, gs:1A4h
0x1400f1888  mov     rcx, cs:TcpEndpointPool
0x1400f188f  lea     ebx, [rax+1]
0x1400f1892  shl     rbx, 7
0x1400f1896  add     rbx, rcx
0x1400f1899  movzx   eax, byte ptr [rbx+0B0h]
0x1400f18a0  test    al, al
0x1400f18a2  jnz     short loc_1400F18AD
0x1400f18a4  lea     rdx, [rbx+40h]
0x1400f18a8  call    PplpLazyInitializeLookasideList
0x1400f18ad  lea     rcx, [rbx+40h]; Lookaside
0x1400f18b1  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400f18b8  nop     dword ptr [rax+rax+00h]
0x1400f18bd  mov     rsi, rax
0x1400f18c0  test    rax, rax
0x1400f18c3  jnz     short loc_1400F18D7
0x1400f18c5  mov     rcx, rbp
0x1400f18c8  call    _InetDereferenceAf
0x1400f18cd  mov     eax, 0C0000017h
0x1400f18d2  jmp     loc_1400F1B87
0x1400f18d7  mov     edx, 1
0x1400f18dc  mov     rcx, rsi
0x1400f18df  call    TcpipTraceActivityIDStart
0x1400f18e4  xor     edx, edx; Val
0x1400f18e6  mov     r8d, 130h; Size
0x1400f18ec  mov     rcx, rsi; void *
0x1400f18ef  call    memset
0x1400f18f4  mov     rcx, rsi; SpinLock
0x1400f18f7  call    cs:__imp_KeInitializeSpinLock
0x1400f18fe  nop     dword ptr [rax+rax+00h]
0x1400f1903  mov     edx, 1; Count
0x1400f1908  lea     rcx, [rsi+100h]; Semaphore
0x1400f190f  mov     r8d, edx; Limit
0x1400f1912  call    cs:__imp_KeInitializeSemaphore
0x1400f1919  nop     dword ptr [rax+rax+00h]
0x1400f191e  mov     eax, 1
0x1400f1923  mov     qword ptr [rsi+8], 1
0x1400f192b  mov     [rsi+20h], rbp
0x1400f192f  mov     [rsi+68h], rbp
0x1400f1933  mov     [rsi+18h], r14
0x1400f1937  lock xadd [r14+10h], rax
0x1400f193d  inc     rax
0x1400f1940  cmp     rax, 1
0x1400f1944  jg      short loc_1400F194D
0x1400f1946  mov     ecx, 0Eh
0x1400f194b  int     29h; Win8: RtlFailFast(ecx)
0x1400f194d  test    rdi, rdi
0x1400f1950  jnz     short loc_1400F1979
0x1400f1952  call    cs:__imp_KeIsExecutingDpc
0x1400f1959  nop     dword ptr [rax+rax+00h]
0x1400f195e  test    eax, eax
0x1400f1960  jz      short loc_1400F196B
0x1400f1962  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400f1969  jmp     short loc_1400F197C
0x1400f196b  call    cs:__imp_PsGetCurrentProcess
0x1400f1972  nop     dword ptr [rax+rax+00h]
0x1400f1977  jmp     short loc_1400F197C
0x1400f1979  mov     rax, rdi
0x1400f197c  mov     rcx, rax; Object
0x1400f197f  mov     [rsi+28h], rax
0x1400f1983  call    cs:__imp_ObfReferenceObject
0x1400f198a  nop     dword ptr [rax+rax+00h]
0x1400f198f  mov     rbx, [rsp+98h+Object]
0x1400f1997  test    rbx, rbx
0x1400f199a  jz      short loc_1400F19AF
0x1400f199c  mov     rcx, rbx; Object
0x1400f199f  mov     [rsi+30h], rbx
0x1400f19a3  call    cs:__imp_ObfReferenceObject
0x1400f19aa  nop     dword ptr [rax+rax+00h]
0x1400f19af  mov     rcx, [rsi+30h]
0x1400f19b3  test    rcx, rcx
0x1400f19b6  jz      short loc_1400F19C6
0x1400f19b8  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400f19bf  nop     dword ptr [rax+rax+00h]
0x1400f19c4  jmp     short loc_1400F19FD
0x1400f19c6  call    cs:__imp_KeIsExecutingDpc
0x1400f19cd  nop     dword ptr [rax+rax+00h]
0x1400f19d2  test    eax, eax
0x1400f19d4  jnz     short loc_1400F19ED
0x1400f19d6  mov     rcx, gs:188h
0x1400f19df  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400f19e6  nop     dword ptr [rax+rax+00h]
0x1400f19eb  jmp     short loc_1400F19FD
0x1400f19ed  mov     rcx, [rsi+28h]
0x1400f19f1  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x1400f19f8  nop     dword ptr [rax+rax+00h]
0x1400f19fd  mov     rcx, [rsi+20h]
0x1400f1a01  mov     edx, eax
0x1400f1a03  mov     r14d, eax
0x1400f1a06  call    _InetFindAndReferenceCompartmentAf
0x1400f1a0b  mov     [rsi+58h], rax
0x1400f1a0f  test    rax, rax
0x1400f1a12  jnz     loc_1400F1AA9
0x1400f1a18  cmp     cs:dword_1402201D4, eax
0x1400f1a1e  jz      short loc_1400F1A95
0x1400f1a20  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, al
0x1400f1a26  xorps   xmm0, xmm0
0x1400f1a29  movups  [rsp+98h+var_48], xmm0
0x1400f1a2e  jge     short loc_1400F1A95
0x1400f1a30  mov     rcx, [rsi+28h]; Process
0x1400f1a34  call    cs:__imp_PsGetProcessId
0x1400f1a3b  nop     dword ptr [rax+rax+00h]
0x1400f1a40  mov     rcx, [rsi+20h]
0x1400f1a44  xor     ebp, ebp
0x1400f1a46  mov     qword ptr [rsp+98h+var_48+8], rbp
0x1400f1a4b  mov     rdi, rax
0x1400f1a4e  mov     qword ptr [rsp+98h+var_48], rsi
0x1400f1a53  movzx   ebx, word ptr [rcx+18h]
0x1400f1a57  mov     rcx, [rsi+28h]
0x1400f1a5b  call    cs:__imp_PsGetProcessStartKey
0x1400f1a62  nop     dword ptr [rax+rax+00h]
0x1400f1a67  mov     [rsp+98h+var_50], rax
0x1400f1a6c  lea     r8, [rsp+98h+var_48]
0x1400f1a71  mov     [rsp+98h+var_58], ebx
0x1400f1a75  lea     rdx, TCP_CREATE_ENDPOINT_COMPARTMENT_FAILURE
0x1400f1a7c  mov     [rsp+98h+var_60], r14d
0x1400f1a81  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400f1a88  mov     [rsp+98h+var_68], edi
0x1400f1a8c  mov     [rsp+98h+var_70], ebp
0x1400f1a90  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x1400f1a95  xor     edx, edx
0x1400f1a97  mov     rcx, rsi; SpinLock
0x1400f1a9a  call    TcpCloseEndpoint
0x1400f1a9f  mov     eax, 0C0000104h
0x1400f1aa4  jmp     loc_1400F1B87
0x1400f1aa9  mov     rax, [rsp+98h+arg_40]
0x1400f1ab1  mov     rdx, rbx
0x1400f1ab4  mov     rcx, rdi
0x1400f1ab7  mov     [rsi+38h], rax
0x1400f1abb  call    InetGetProcessTag
0x1400f1ac0  lea     rcx, [rsi+40h]
0x1400f1ac4  mov     [rsi+48h], rax
0x1400f1ac8  call    cs:__imp_KeQuerySystemTimePrecise
0x1400f1acf  nop     dword ptr [rax+rax+00h]
0x1400f1ad4  lea     rdx, [rsi+0A8h]
0x1400f1adb  mov     rcx, rbp
0x1400f1ade  call    TcpInitializeOptions
0x1400f1ae3  xorps   xmm0, xmm0
0x1400f1ae6  xor     eax, eax
0x1400f1ae8  test    [rsp+98h+arg_20], 1
0x1400f1af0  movups  xmmword ptr [rsi+0D0h], xmm0
0x1400f1af7  movups  xmmword ptr [rsi+0E0h], xmm0
0x1400f1afe  mov     [rsi+0F0h], rax
0x1400f1b05  jz      short loc_1400F1B0E
0x1400f1b07  or      byte ptr [rsi+0CEh], 40h
0x1400f1b0e  mov     [rsi+98h], r12
0x1400f1b15  mov     [rsi+0A0h], r15
0x1400f1b1c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400f1b22  test    eax, eax
0x1400f1b24  jz      short loc_1400F1B41
0x1400f1b26  mov     rdx, [rsp+98h+arg_28]
0x1400f1b2e  test    rdx, rdx
0x1400f1b31  jz      short loc_1400F1B41
0x1400f1b33  mov     r8d, 1
0x1400f1b39  mov     rcx, rsi
0x1400f1b3c  call    TcpipEtwTransferActivity
0x1400f1b41  call    cs:__imp_KeGetCurrentIrql
0x1400f1b48  nop     dword ptr [rax+rax+00h]
0x1400f1b4d  test    al, al
0x1400f1b4f  jnz     short loc_1400F1B68
0x1400f1b51  xor     ebp, ebp
0x1400f1b53  lea     rcx, [rsi+90h]
0x1400f1b5a  mov     [rsi+90h], rbp
0x1400f1b61  call    TcpCreateEndpointWorkQueueRoutine
0x1400f1b66  jmp     short loc_1400F1B82
0x1400f1b68  lea     rdx, [rsi+90h]
0x1400f1b6f  lea     rcx, TcpCreateEndpointWorkQueue
0x1400f1b76  call    cs:__imp_NetioInsertWorkQueue
0x1400f1b7d  nop     dword ptr [rax+rax+00h]
0x1400f1b82  mov     eax, 103h
0x1400f1b87  mov     rcx, [rsp+98h+var_38]
0x1400f1b8c  xor     rcx, rsp; StackCookie
0x1400f1b8f  call    __security_check_cookie
0x1400f1b94  lea     r11, [rsp+98h+var_28]
0x1400f1b99  mov     rbx, [r11+30h]
0x1400f1b9d  mov     rbp, [r11+38h]
0x1400f1ba1  mov     rsp, r11
0x1400f1ba4  pop     r15
0x1400f1ba6  pop     r14
0x1400f1ba8  pop     r12
0x1400f1baa  pop     rdi
0x1400f1bab  pop     rsi
0x1400f1bac  retn
```
