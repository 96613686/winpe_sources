# TcpCreateEndpoint

- ea: `0x1400f1670`
- end: `0x1400f1a9e`
- name: `TcpCreateEndpoint`
- size: `1070`
- prototype: `__int64 __fastcall(int, int, int, int, char, __int64, PEPROCESS Process, PVOID Object, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f1610`

## callees

- `0x1400158e0`
- `0x140017060`
- `0x140017ca0`
- `0x140019180`
- `0x140039b00`
- `0x14003a730`
- `0x1400540a4`
- `0x1400ae7f8`
- `0x1400f1670`
- `0x1401154a8`
- `0x140130290`
- `0x14014f49c`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x1400f1802`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400f1802`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f16ca`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f1842`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f18b6`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f16ca`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f1842`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f18b6`
- `ntoskrnl!ObfReferenceObject` at `0x1400f1873`
- `ntoskrnl!ObfReferenceObject` at `0x1400f1893`
- `ntoskrnl!ObfReferenceObject` at `0x1400f1873`
- `ntoskrnl!ObfReferenceObject` at `0x1400f1893`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400f19b8`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400f19b8`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f172d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f194b`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f172d`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f194b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f17a1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f17a1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f1a31`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f1a31`
- `ntoskrnl!PsGetProcessId` at `0x1400f170f`
- `ntoskrnl!PsGetProcessId` at `0x1400f1924`
- `ntoskrnl!PsGetProcessId` at `0x1400f170f`
- `ntoskrnl!PsGetProcessId` at `0x1400f1924`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f16e3`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f185b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f16e3`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f185b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400f17e7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400f17e7`
- `NETIO!NetioInsertWorkQueue` at `0x1400f1a66`
- `NETIO!NetioInsertWorkQueue` at `0x1400f1a66`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1400f18e1`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1400f18e1`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f18a8`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f18cf`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f18a8`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f18cf`

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
  struct _KPROCESS *v9; // rdi
  __int64 v13; // rbp
  int v14; // r9d
  char *v16; // rbx
  char *v17; // rax
  char *v18; // rsi
  PEPROCESS CurrentProcess; // rax
  __int64 v20; // rcx
  unsigned int ThreadObjectCompartmentId; // eax
  __int64 v22; // rax
  int v23; // r9d
  __int128 v24; // [rsp+50h] [rbp-48h] BYREF

  v9 = Process;
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
        CurrentProcess = Process;
      }
      else if ( (unsigned int)KeIsExecutingDpc() )
      {
        CurrentProcess = *(PEPROCESS *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
      }
      else
      {
        CurrentProcess = (PEPROCESS)PsGetCurrentProcess();
      }
      *((_QWORD *)v18 + 5) = CurrentProcess;
      ObfReferenceObject(CurrentProcess);
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
        v9 = *(struct _KPROCESS **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
      else
        v9 = (struct _KPROCESS *)PsGetCurrentProcess();
    }
    if ( dword_1402201D4 )
    {
      v24 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
      {
        PsGetProcessId(v9);
        v24 = 0u;
        PsGetProcessStartKey(v9);
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
0x1400f1670  mov     [rsp+arg_0], rbx
0x1400f1675  mov     [rsp+arg_8], rbp
0x1400f167a  push    rsi
0x1400f167b  push    rdi
0x1400f167c  push    r12
0x1400f167e  push    r14
0x1400f1680  push    r15
0x1400f1682  sub     rsp, 70h
0x1400f1686  mov     rax, cs:__security_cookie
0x1400f168d  xor     rax, rsp
0x1400f1690  mov     [rsp+98h+var_38], rax
0x1400f1695  mov     rdi, [rsp+98h+Process]
0x1400f169d  mov     r12, rdx
0x1400f16a0  movzx   esi, r9w
0x1400f16a4  mov     r14, rcx
0x1400f16a7  movzx   edx, si
0x1400f16aa  lea     rcx, TcpInetTransport
0x1400f16b1  mov     r15, r8
0x1400f16b4  call    InetFindAndReferenceAf
0x1400f16b9  mov     rbp, rax
0x1400f16bc  test    rax, rax
0x1400f16bf  jnz     loc_1400F1770
0x1400f16c5  test    rdi, rdi
0x1400f16c8  jnz     short loc_1400F16F2
0x1400f16ca  call    cs:__imp_KeIsExecutingDpc
0x1400f16d1  nop     dword ptr [rax+rax+00h]
0x1400f16d6  test    eax, eax
0x1400f16d8  jz      short loc_1400F16E3
0x1400f16da  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400f16e1  jmp     short loc_1400F16F2
0x1400f16e3  call    cs:__imp_PsGetCurrentProcess
0x1400f16ea  nop     dword ptr [rax+rax+00h]
0x1400f16ef  mov     rdi, rax
0x1400f16f2  cmp     cs:dword_1402201D4, 0
0x1400f16f9  jz      short loc_1400F1766
0x1400f16fb  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, 0
0x1400f1702  xorps   xmm0, xmm0
0x1400f1705  movups  [rsp+98h+var_48], xmm0
0x1400f170a  jge     short loc_1400F1766
0x1400f170c  mov     rcx, rdi; Process
0x1400f170f  call    cs:__imp_PsGetProcessId
0x1400f1716  nop     dword ptr [rax+rax+00h]
0x1400f171b  xor     ebp, ebp
0x1400f171d  mov     rcx, rdi
0x1400f1720  mov     rbx, rax
0x1400f1723  mov     qword ptr [rsp+98h+var_48+8], rbp
0x1400f1728  mov     qword ptr [rsp+98h+var_48], rbp
0x1400f172d  call    cs:__imp_PsGetProcessStartKey
0x1400f1734  nop     dword ptr [rax+rax+00h]
0x1400f1739  mov     [rsp+98h+var_50], rax
0x1400f173e  lea     r8, [rsp+98h+var_48]
0x1400f1743  mov     [rsp+98h+var_58], esi
0x1400f1747  lea     rdx, TCP_CREATE_ENDPOINT_AF_FAILURE
0x1400f174e  mov     [rsp+98h+var_60], ebp
0x1400f1752  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400f1759  mov     [rsp+98h+var_68], ebx
0x1400f175d  mov     [rsp+98h+var_70], ebp
0x1400f1761  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x1400f1766  mov     eax, 0C000A013h
0x1400f176b  jmp     loc_1400F1A77
0x1400f1770  mov     eax, gs:1A4h
0x1400f1778  mov     rcx, cs:TcpEndpointPool
0x1400f177f  lea     ebx, [rax+1]
0x1400f1782  shl     rbx, 7
0x1400f1786  add     rbx, rcx
0x1400f1789  movzx   eax, byte ptr [rbx+0B0h]
0x1400f1790  test    al, al
0x1400f1792  jnz     short loc_1400F179D
0x1400f1794  lea     rdx, [rbx+40h]
0x1400f1798  call    PplpLazyInitializeLookasideList
0x1400f179d  lea     rcx, [rbx+40h]; Lookaside
0x1400f17a1  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400f17a8  nop     dword ptr [rax+rax+00h]
0x1400f17ad  mov     rsi, rax
0x1400f17b0  test    rax, rax
0x1400f17b3  jnz     short loc_1400F17C7
0x1400f17b5  mov     rcx, rbp
0x1400f17b8  call    _InetDereferenceAf
0x1400f17bd  mov     eax, 0C0000017h
0x1400f17c2  jmp     loc_1400F1A77
0x1400f17c7  mov     edx, 1
0x1400f17cc  mov     rcx, rsi
0x1400f17cf  call    TcpipTraceActivityIDStart
0x1400f17d4  xor     edx, edx; Val
0x1400f17d6  mov     r8d, 130h; Size
0x1400f17dc  mov     rcx, rsi; void *
0x1400f17df  call    memset
0x1400f17e4  mov     rcx, rsi; SpinLock
0x1400f17e7  call    cs:__imp_KeInitializeSpinLock
0x1400f17ee  nop     dword ptr [rax+rax+00h]
0x1400f17f3  mov     edx, 1; Count
0x1400f17f8  lea     rcx, [rsi+100h]; Semaphore
0x1400f17ff  mov     r8d, edx; Limit
0x1400f1802  call    cs:__imp_KeInitializeSemaphore
0x1400f1809  nop     dword ptr [rax+rax+00h]
0x1400f180e  mov     eax, 1
0x1400f1813  mov     qword ptr [rsi+8], 1
0x1400f181b  mov     [rsi+20h], rbp
0x1400f181f  mov     [rsi+68h], rbp
0x1400f1823  mov     [rsi+18h], r14
0x1400f1827  lock xadd [r14+10h], rax
0x1400f182d  inc     rax
0x1400f1830  cmp     rax, 1
0x1400f1834  jg      short loc_1400F183D
0x1400f1836  mov     ecx, 0Eh
0x1400f183b  int     29h; Win8: RtlFailFast(ecx)
0x1400f183d  test    rdi, rdi
0x1400f1840  jnz     short loc_1400F1869
0x1400f1842  call    cs:__imp_KeIsExecutingDpc
0x1400f1849  nop     dword ptr [rax+rax+00h]
0x1400f184e  test    eax, eax
0x1400f1850  jz      short loc_1400F185B
0x1400f1852  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400f1859  jmp     short loc_1400F186C
0x1400f185b  call    cs:__imp_PsGetCurrentProcess
0x1400f1862  nop     dword ptr [rax+rax+00h]
0x1400f1867  jmp     short loc_1400F186C
0x1400f1869  mov     rax, rdi
0x1400f186c  mov     rcx, rax; Object
0x1400f186f  mov     [rsi+28h], rax
0x1400f1873  call    cs:__imp_ObfReferenceObject
0x1400f187a  nop     dword ptr [rax+rax+00h]
0x1400f187f  mov     rbx, [rsp+98h+Object]
0x1400f1887  test    rbx, rbx
0x1400f188a  jz      short loc_1400F189F
0x1400f188c  mov     rcx, rbx; Object
0x1400f188f  mov     [rsi+30h], rbx
0x1400f1893  call    cs:__imp_ObfReferenceObject
0x1400f189a  nop     dword ptr [rax+rax+00h]
0x1400f189f  mov     rcx, [rsi+30h]
0x1400f18a3  test    rcx, rcx
0x1400f18a6  jz      short loc_1400F18B6
0x1400f18a8  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400f18af  nop     dword ptr [rax+rax+00h]
0x1400f18b4  jmp     short loc_1400F18ED
0x1400f18b6  call    cs:__imp_KeIsExecutingDpc
0x1400f18bd  nop     dword ptr [rax+rax+00h]
0x1400f18c2  test    eax, eax
0x1400f18c4  jnz     short loc_1400F18DD
0x1400f18c6  mov     rcx, gs:188h
0x1400f18cf  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400f18d6  nop     dword ptr [rax+rax+00h]
0x1400f18db  jmp     short loc_1400F18ED
0x1400f18dd  mov     rcx, [rsi+28h]
0x1400f18e1  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x1400f18e8  nop     dword ptr [rax+rax+00h]
0x1400f18ed  mov     rcx, [rsi+20h]
0x1400f18f1  mov     edx, eax
0x1400f18f3  mov     r14d, eax
0x1400f18f6  call    _InetFindAndReferenceCompartmentAf
0x1400f18fb  mov     [rsi+58h], rax
0x1400f18ff  test    rax, rax
0x1400f1902  jnz     loc_1400F1999
0x1400f1908  cmp     cs:dword_1402201D4, eax
0x1400f190e  jz      short loc_1400F1985
0x1400f1910  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, al
0x1400f1916  xorps   xmm0, xmm0
0x1400f1919  movups  [rsp+98h+var_48], xmm0
0x1400f191e  jge     short loc_1400F1985
0x1400f1920  mov     rcx, [rsi+28h]; Process
0x1400f1924  call    cs:__imp_PsGetProcessId
0x1400f192b  nop     dword ptr [rax+rax+00h]
0x1400f1930  mov     rcx, [rsi+20h]
0x1400f1934  xor     ebp, ebp
0x1400f1936  mov     qword ptr [rsp+98h+var_48+8], rbp
0x1400f193b  mov     rdi, rax
0x1400f193e  mov     qword ptr [rsp+98h+var_48], rsi
0x1400f1943  movzx   ebx, word ptr [rcx+18h]
0x1400f1947  mov     rcx, [rsi+28h]
0x1400f194b  call    cs:__imp_PsGetProcessStartKey
0x1400f1952  nop     dword ptr [rax+rax+00h]
0x1400f1957  mov     [rsp+98h+var_50], rax
0x1400f195c  lea     r8, [rsp+98h+var_48]
0x1400f1961  mov     [rsp+98h+var_58], ebx
0x1400f1965  lea     rdx, TCP_CREATE_ENDPOINT_COMPARTMENT_FAILURE
0x1400f196c  mov     [rsp+98h+var_60], r14d
0x1400f1971  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400f1978  mov     [rsp+98h+var_68], edi
0x1400f197c  mov     [rsp+98h+var_70], ebp
0x1400f1980  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x1400f1985  xor     edx, edx
0x1400f1987  mov     rcx, rsi; SpinLock
0x1400f198a  call    TcpCloseEndpoint
0x1400f198f  mov     eax, 0C0000104h
0x1400f1994  jmp     loc_1400F1A77
0x1400f1999  mov     rax, [rsp+98h+arg_40]
0x1400f19a1  mov     rdx, rbx
0x1400f19a4  mov     rcx, rdi
0x1400f19a7  mov     [rsi+38h], rax
0x1400f19ab  call    InetGetProcessTag
0x1400f19b0  lea     rcx, [rsi+40h]
0x1400f19b4  mov     [rsi+48h], rax
0x1400f19b8  call    cs:__imp_KeQuerySystemTimePrecise
0x1400f19bf  nop     dword ptr [rax+rax+00h]
0x1400f19c4  lea     rdx, [rsi+0A8h]
0x1400f19cb  mov     rcx, rbp
0x1400f19ce  call    TcpInitializeOptions
0x1400f19d3  xorps   xmm0, xmm0
0x1400f19d6  xor     eax, eax
0x1400f19d8  test    [rsp+98h+arg_20], 1
0x1400f19e0  movups  xmmword ptr [rsi+0D0h], xmm0
0x1400f19e7  movups  xmmword ptr [rsi+0E0h], xmm0
0x1400f19ee  mov     [rsi+0F0h], rax
0x1400f19f5  jz      short loc_1400F19FE
0x1400f19f7  or      byte ptr [rsi+0CEh], 40h
0x1400f19fe  mov     [rsi+98h], r12
0x1400f1a05  mov     [rsi+0A0h], r15
0x1400f1a0c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400f1a12  test    eax, eax
0x1400f1a14  jz      short loc_1400F1A31
0x1400f1a16  mov     rdx, [rsp+98h+arg_28]
0x1400f1a1e  test    rdx, rdx
0x1400f1a21  jz      short loc_1400F1A31
0x1400f1a23  mov     r8d, 1
0x1400f1a29  mov     rcx, rsi
0x1400f1a2c  call    TcpipEtwTransferActivity
0x1400f1a31  call    cs:__imp_KeGetCurrentIrql
0x1400f1a38  nop     dword ptr [rax+rax+00h]
0x1400f1a3d  test    al, al
0x1400f1a3f  jnz     short loc_1400F1A58
0x1400f1a41  xor     ebp, ebp
0x1400f1a43  lea     rcx, [rsi+90h]
0x1400f1a4a  mov     [rsi+90h], rbp
0x1400f1a51  call    TcpCreateEndpointWorkQueueRoutine
0x1400f1a56  jmp     short loc_1400F1A72
0x1400f1a58  lea     rdx, [rsi+90h]
0x1400f1a5f  lea     rcx, TcpCreateEndpointWorkQueue
0x1400f1a66  call    cs:__imp_NetioInsertWorkQueue
0x1400f1a6d  nop     dword ptr [rax+rax+00h]
0x1400f1a72  mov     eax, 103h
0x1400f1a77  mov     rcx, [rsp+98h+var_38]
0x1400f1a7c  xor     rcx, rsp; StackCookie
0x1400f1a7f  call    __security_check_cookie
0x1400f1a84  lea     r11, [rsp+98h+var_28]
0x1400f1a89  mov     rbx, [r11+30h]
0x1400f1a8d  mov     rbp, [r11+38h]
0x1400f1a91  mov     rsp, r11
0x1400f1a94  pop     r15
0x1400f1a96  pop     r14
0x1400f1a98  pop     r12
0x1400f1a9a  pop     rdi
0x1400f1a9b  pop     rsi
0x1400f1a9c  retn
```
