# TcpCreateEndpoint

- ea: `0x1400f7ff0`
- end: `0x1400f841e`
- name: `TcpCreateEndpoint`
- size: `1070`
- prototype: `__int64 __fastcall(int, int, int, int, char, __int64, PEPROCESS Process, PVOID Object, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f7f90`

## callees

- `0x140014974`
- `0x140018578`
- `0x14001df40`
- `0x14001dfa8`
- `0x14001f820`
- `0x140022240`
- `0x140023800`
- `0x140048a40`
- `0x140049760`
- `0x1400f7ff0`
- `0x140136e80`
- `0x14015109c`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x1400f8182`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400f8182`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f804a`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f81c2`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f8236`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f804a`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f81c2`
- `ntoskrnl!KeIsExecutingDpc` at `0x1400f8236`
- `ntoskrnl!ObfReferenceObject` at `0x1400f81f3`
- `ntoskrnl!ObfReferenceObject` at `0x1400f8213`
- `ntoskrnl!ObfReferenceObject` at `0x1400f81f3`
- `ntoskrnl!ObfReferenceObject` at `0x1400f8213`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400f8338`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400f8338`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f80ad`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f82cb`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f80ad`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400f82cb`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f8121`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400f8121`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f83b1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f83b1`
- `ntoskrnl!PsGetProcessId` at `0x1400f808f`
- `ntoskrnl!PsGetProcessId` at `0x1400f82a4`
- `ntoskrnl!PsGetProcessId` at `0x1400f808f`
- `ntoskrnl!PsGetProcessId` at `0x1400f82a4`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f8063`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f81db`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f8063`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f81db`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400f8167`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400f8167`
- `NETIO!NetioInsertWorkQueue` at `0x1400f83e6`
- `NETIO!NetioInsertWorkQueue` at `0x1400f83e6`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1400f8261`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1400f8261`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f8228`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f824f`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f8228`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400f824f`

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
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // r9d
  char *v22; // rbx
  char *v23; // rax
  char *v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  struct _LIST_ENTRY *Flink; // rax
  __int64 v30; // rcx
  unsigned int ThreadObjectCompartmentId; // eax
  __int64 v32; // rax
  int v33; // r9d
  __int128 v34; // [rsp+50h] [rbp-48h] BYREF

  CurrentProcess = Process;
  v13 = InetFindAndReferenceAf(&TcpInetTransport, a4);
  if ( v13 )
  {
    v22 = (char *)TcpEndpointPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v22[176] )
      PplpLazyInitializeLookasideList(TcpEndpointPool, v22 + 64, v14, v15);
    v23 = (char *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v22 + 64));
    v24 = v23;
    if ( v23 )
    {
      TcpipTraceActivityIDStart(v23, 1);
      memset(v24, 0, 0x130u);
      KeInitializeSpinLock((PKSPIN_LOCK)v24);
      KeInitializeSemaphore((PRKSEMAPHORE)v24 + 8, 1, 1);
      *((_QWORD *)v24 + 1) = 1;
      *((_QWORD *)v24 + 4) = v13;
      *((_QWORD *)v24 + 13) = v13;
      *((_QWORD *)v24 + 3) = a1;
      if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 16)) <= 1 )
        __fastfail(0xEu);
      if ( Process )
      {
        Flink = (struct _LIST_ENTRY *)Process;
      }
      else if ( (unsigned int)KeIsExecutingDpc() )
      {
        Flink = WPP_MAIN_CB.Queue.ListEntry.Flink;
      }
      else
      {
        Flink = (struct _LIST_ENTRY *)PsGetCurrentProcess(v26, v25, v27, v28);
      }
      *((_QWORD *)v24 + 5) = Flink;
      ObfReferenceObject(Flink);
      if ( Object )
      {
        *((_QWORD *)v24 + 6) = Object;
        ObfReferenceObject(Object);
      }
      v30 = *((_QWORD *)v24 + 6);
      if ( v30 )
      {
        ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(v30);
      }
      else if ( (unsigned int)KeIsExecutingDpc() )
      {
        ThreadObjectCompartmentId = NdisGetProcessObjectCompartmentId(*((_QWORD *)v24 + 5));
      }
      else
      {
        ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
      }
      v32 = InetFindAndReferenceCompartmentAf(*((_QWORD *)v24 + 4), ThreadObjectCompartmentId);
      *((_QWORD *)v24 + 11) = v32;
      if ( v32 )
      {
        *((_QWORD *)v24 + 7) = a9;
        *((_QWORD *)v24 + 9) = InetGetProcessTag(Process, Object);
        KeQuerySystemTimePrecise(v24 + 64);
        TcpInitializeOptions(v13, v24 + 168);
        *((_OWORD *)v24 + 13) = 0;
        *((_OWORD *)v24 + 14) = 0;
        *((_QWORD *)v24 + 30) = 0;
        if ( (a5 & 1) != 0 )
          v24[206] |= 0x40u;
        *((_QWORD *)v24 + 19) = a2;
        *((_QWORD *)v24 + 20) = a3;
        if ( Microsoft_Windows_Networking_CorrelationEnabled && a6 )
          TcpipEtwTransferActivity(v24, a6, 1);
        if ( KeGetCurrentIrql() )
        {
          NetioInsertWorkQueue(TcpCreateEndpointWorkQueue, v24 + 144);
        }
        else
        {
          *((_QWORD *)v24 + 18) = 0;
          TcpCreateEndpointWorkQueueRoutine((_QWORD *)v24 + 18);
        }
        return 259;
      }
      else
      {
        if ( dword_1402241D4 )
        {
          v34 = 0;
          if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
          {
            PsGetProcessId(*((PEPROCESS *)v24 + 5));
            v34 = (unsigned __int64)v24;
            PsGetProcessStartKey(*((_QWORD *)v24 + 5));
            McTemplateK0qbr0qqqqx_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)TCP_CREATE_ENDPOINT_COMPARTMENT_FAILURE,
              (unsigned int)&v34,
              v33);
          }
        }
        TcpCloseEndpoint((PKSPIN_LOCK)v24);
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
        CurrentProcess = (struct _KPROCESS *)WPP_MAIN_CB.Queue.ListEntry.Flink;
      else
        CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(v17, v16, v18, v19);
    }
    if ( dword_1402241D4 )
    {
      v34 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        PsGetProcessId(CurrentProcess);
        v34 = 0u;
        PsGetProcessStartKey(CurrentProcess);
        McTemplateK0qbr0qqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CREATE_ENDPOINT_AF_FAILURE,
          (unsigned int)&v34,
          v20);
      }
    }
    return 3221266451LL;
  }
}

```

## disassembly

```asm
0x1400f7ff0  mov     [rsp+arg_0], rbx
0x1400f7ff5  mov     [rsp+arg_8], rbp
0x1400f7ffa  push    rsi
0x1400f7ffb  push    rdi
0x1400f7ffc  push    r12
0x1400f7ffe  push    r14
0x1400f8000  push    r15
0x1400f8002  sub     rsp, 70h
0x1400f8006  mov     rax, cs:__security_cookie
0x1400f800d  xor     rax, rsp
0x1400f8010  mov     [rsp+98h+var_38], rax
0x1400f8015  mov     rdi, [rsp+98h+Process]
0x1400f801d  mov     r12, rdx
0x1400f8020  movzx   esi, r9w
0x1400f8024  mov     r14, rcx
0x1400f8027  movzx   edx, si
0x1400f802a  lea     rcx, TcpInetTransport
0x1400f8031  mov     r15, r8
0x1400f8034  call    InetFindAndReferenceAf
0x1400f8039  mov     rbp, rax
0x1400f803c  test    rax, rax
0x1400f803f  jnz     loc_1400F80F0
0x1400f8045  test    rdi, rdi
0x1400f8048  jnz     short loc_1400F8072
0x1400f804a  call    cs:__imp_KeIsExecutingDpc
0x1400f8051  nop     dword ptr [rax+rax+00h]
0x1400f8056  test    eax, eax
0x1400f8058  jz      short loc_1400F8063
0x1400f805a  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue
0x1400f8061  jmp     short loc_1400F8072
0x1400f8063  call    cs:__imp_PsGetCurrentProcess
0x1400f806a  nop     dword ptr [rax+rax+00h]
0x1400f806f  mov     rdi, rax
0x1400f8072  cmp     cs:dword_1402241D4, 0
0x1400f8079  jz      short loc_1400F80E6
0x1400f807b  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x1400f8082  xorps   xmm0, xmm0
0x1400f8085  movups  [rsp+98h+var_48], xmm0
0x1400f808a  jge     short loc_1400F80E6
0x1400f808c  mov     rcx, rdi; Process
0x1400f808f  call    cs:__imp_PsGetProcessId
0x1400f8096  nop     dword ptr [rax+rax+00h]
0x1400f809b  xor     ebp, ebp
0x1400f809d  mov     rcx, rdi
0x1400f80a0  mov     rbx, rax
0x1400f80a3  mov     qword ptr [rsp+98h+var_48+8], rbp
0x1400f80a8  mov     qword ptr [rsp+98h+var_48], rbp
0x1400f80ad  call    cs:__imp_PsGetProcessStartKey
0x1400f80b4  nop     dword ptr [rax+rax+00h]
0x1400f80b9  mov     [rsp+98h+var_50], rax
0x1400f80be  lea     r8, [rsp+98h+var_48]
0x1400f80c3  mov     [rsp+98h+var_58], esi
0x1400f80c7  lea     rdx, TCP_CREATE_ENDPOINT_AF_FAILURE
0x1400f80ce  mov     [rsp+98h+var_60], ebp
0x1400f80d2  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400f80d9  mov     [rsp+98h+var_68], ebx
0x1400f80dd  mov     [rsp+98h+var_70], ebp
0x1400f80e1  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x1400f80e6  mov     eax, 0C000A013h
0x1400f80eb  jmp     loc_1400F83F7
0x1400f80f0  mov     eax, gs:1A4h
0x1400f80f8  mov     rcx, cs:TcpEndpointPool
0x1400f80ff  lea     ebx, [rax+1]
0x1400f8102  shl     rbx, 7
0x1400f8106  add     rbx, rcx
0x1400f8109  movzx   eax, byte ptr [rbx+0B0h]
0x1400f8110  test    al, al
0x1400f8112  jnz     short loc_1400F811D
0x1400f8114  lea     rdx, [rbx+40h]
0x1400f8118  call    PplpLazyInitializeLookasideList
0x1400f811d  lea     rcx, [rbx+40h]; Lookaside
0x1400f8121  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400f8128  nop     dword ptr [rax+rax+00h]
0x1400f812d  mov     rsi, rax
0x1400f8130  test    rax, rax
0x1400f8133  jnz     short loc_1400F8147
0x1400f8135  mov     rcx, rbp
0x1400f8138  call    _InetDereferenceAf
0x1400f813d  mov     eax, 0C0000017h
0x1400f8142  jmp     loc_1400F83F7
0x1400f8147  mov     edx, 1
0x1400f814c  mov     rcx, rsi
0x1400f814f  call    TcpipTraceActivityIDStart
0x1400f8154  xor     edx, edx; Val
0x1400f8156  mov     r8d, 130h; Size
0x1400f815c  mov     rcx, rsi; void *
0x1400f815f  call    memset
0x1400f8164  mov     rcx, rsi; SpinLock
0x1400f8167  call    cs:__imp_KeInitializeSpinLock
0x1400f816e  nop     dword ptr [rax+rax+00h]
0x1400f8173  mov     edx, 1; Count
0x1400f8178  lea     rcx, [rsi+100h]; Semaphore
0x1400f817f  mov     r8d, edx; Limit
0x1400f8182  call    cs:__imp_KeInitializeSemaphore
0x1400f8189  nop     dword ptr [rax+rax+00h]
0x1400f818e  mov     eax, 1
0x1400f8193  mov     qword ptr [rsi+8], 1
0x1400f819b  mov     [rsi+20h], rbp
0x1400f819f  mov     [rsi+68h], rbp
0x1400f81a3  mov     [rsi+18h], r14
0x1400f81a7  lock xadd [r14+10h], rax
0x1400f81ad  inc     rax
0x1400f81b0  cmp     rax, 1
0x1400f81b4  jg      short loc_1400F81BD
0x1400f81b6  mov     ecx, 0Eh
0x1400f81bb  int     29h; Win8: RtlFailFast(ecx)
0x1400f81bd  test    rdi, rdi
0x1400f81c0  jnz     short loc_1400F81E9
0x1400f81c2  call    cs:__imp_KeIsExecutingDpc
0x1400f81c9  nop     dword ptr [rax+rax+00h]
0x1400f81ce  test    eax, eax
0x1400f81d0  jz      short loc_1400F81DB
0x1400f81d2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400f81d9  jmp     short loc_1400F81EC
0x1400f81db  call    cs:__imp_PsGetCurrentProcess
0x1400f81e2  nop     dword ptr [rax+rax+00h]
0x1400f81e7  jmp     short loc_1400F81EC
0x1400f81e9  mov     rax, rdi
0x1400f81ec  mov     rcx, rax; Object
0x1400f81ef  mov     [rsi+28h], rax
0x1400f81f3  call    cs:__imp_ObfReferenceObject
0x1400f81fa  nop     dword ptr [rax+rax+00h]
0x1400f81ff  mov     rbx, [rsp+98h+Object]
0x1400f8207  test    rbx, rbx
0x1400f820a  jz      short loc_1400F821F
0x1400f820c  mov     rcx, rbx; Object
0x1400f820f  mov     [rsi+30h], rbx
0x1400f8213  call    cs:__imp_ObfReferenceObject
0x1400f821a  nop     dword ptr [rax+rax+00h]
0x1400f821f  mov     rcx, [rsi+30h]
0x1400f8223  test    rcx, rcx
0x1400f8226  jz      short loc_1400F8236
0x1400f8228  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400f822f  nop     dword ptr [rax+rax+00h]
0x1400f8234  jmp     short loc_1400F826D
0x1400f8236  call    cs:__imp_KeIsExecutingDpc
0x1400f823d  nop     dword ptr [rax+rax+00h]
0x1400f8242  test    eax, eax
0x1400f8244  jnz     short loc_1400F825D
0x1400f8246  mov     rcx, gs:188h
0x1400f824f  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400f8256  nop     dword ptr [rax+rax+00h]
0x1400f825b  jmp     short loc_1400F826D
0x1400f825d  mov     rcx, [rsi+28h]
0x1400f8261  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x1400f8268  nop     dword ptr [rax+rax+00h]
0x1400f826d  mov     rcx, [rsi+20h]
0x1400f8271  mov     edx, eax
0x1400f8273  mov     r14d, eax
0x1400f8276  call    _InetFindAndReferenceCompartmentAf
0x1400f827b  mov     [rsi+58h], rax
0x1400f827f  test    rax, rax
0x1400f8282  jnz     loc_1400F8319
0x1400f8288  cmp     cs:dword_1402241D4, eax
0x1400f828e  jz      short loc_1400F8305
0x1400f8290  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, al
0x1400f8296  xorps   xmm0, xmm0
0x1400f8299  movups  [rsp+98h+var_48], xmm0
0x1400f829e  jge     short loc_1400F8305
0x1400f82a0  mov     rcx, [rsi+28h]; Process
0x1400f82a4  call    cs:__imp_PsGetProcessId
0x1400f82ab  nop     dword ptr [rax+rax+00h]
0x1400f82b0  mov     rcx, [rsi+20h]
0x1400f82b4  xor     ebp, ebp
0x1400f82b6  mov     qword ptr [rsp+98h+var_48+8], rbp
0x1400f82bb  mov     rdi, rax
0x1400f82be  mov     qword ptr [rsp+98h+var_48], rsi
0x1400f82c3  movzx   ebx, word ptr [rcx+18h]
0x1400f82c7  mov     rcx, [rsi+28h]
0x1400f82cb  call    cs:__imp_PsGetProcessStartKey
0x1400f82d2  nop     dword ptr [rax+rax+00h]
0x1400f82d7  mov     [rsp+98h+var_50], rax
0x1400f82dc  lea     r8, [rsp+98h+var_48]
0x1400f82e1  mov     [rsp+98h+var_58], ebx
0x1400f82e5  lea     rdx, TCP_CREATE_ENDPOINT_COMPARTMENT_FAILURE
0x1400f82ec  mov     [rsp+98h+var_60], r14d
0x1400f82f1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400f82f8  mov     [rsp+98h+var_68], edi
0x1400f82fc  mov     [rsp+98h+var_70], ebp
0x1400f8300  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x1400f8305  xor     edx, edx
0x1400f8307  mov     rcx, rsi; SpinLock
0x1400f830a  call    TcpCloseEndpoint
0x1400f830f  mov     eax, 0C0000104h
0x1400f8314  jmp     loc_1400F83F7
0x1400f8319  mov     rax, [rsp+98h+arg_40]
0x1400f8321  mov     rdx, rbx
0x1400f8324  mov     rcx, rdi
0x1400f8327  mov     [rsi+38h], rax
0x1400f832b  call    InetGetProcessTag
0x1400f8330  lea     rcx, [rsi+40h]
0x1400f8334  mov     [rsi+48h], rax
0x1400f8338  call    cs:__imp_KeQuerySystemTimePrecise
0x1400f833f  nop     dword ptr [rax+rax+00h]
0x1400f8344  lea     rdx, [rsi+0A8h]
0x1400f834b  mov     rcx, rbp
0x1400f834e  call    TcpInitializeOptions
0x1400f8353  xorps   xmm0, xmm0
0x1400f8356  xor     eax, eax
0x1400f8358  test    [rsp+98h+arg_20], 1
0x1400f8360  movups  xmmword ptr [rsi+0D0h], xmm0
0x1400f8367  movups  xmmword ptr [rsi+0E0h], xmm0
0x1400f836e  mov     [rsi+0F0h], rax
0x1400f8375  jz      short loc_1400F837E
0x1400f8377  or      byte ptr [rsi+0CEh], 40h
0x1400f837e  mov     [rsi+98h], r12
0x1400f8385  mov     [rsi+0A0h], r15
0x1400f838c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400f8392  test    eax, eax
0x1400f8394  jz      short loc_1400F83B1
0x1400f8396  mov     rdx, [rsp+98h+arg_28]
0x1400f839e  test    rdx, rdx
0x1400f83a1  jz      short loc_1400F83B1
0x1400f83a3  mov     r8d, 1
0x1400f83a9  mov     rcx, rsi
0x1400f83ac  call    TcpipEtwTransferActivity
0x1400f83b1  call    cs:__imp_KeGetCurrentIrql
0x1400f83b8  nop     dword ptr [rax+rax+00h]
0x1400f83bd  test    al, al
0x1400f83bf  jnz     short loc_1400F83D8
0x1400f83c1  xor     ebp, ebp
0x1400f83c3  lea     rcx, [rsi+90h]
0x1400f83ca  mov     [rsi+90h], rbp
0x1400f83d1  call    TcpCreateEndpointWorkQueueRoutine
0x1400f83d6  jmp     short loc_1400F83F2
0x1400f83d8  lea     rdx, [rsi+90h]
0x1400f83df  lea     rcx, TcpCreateEndpointWorkQueue
0x1400f83e6  call    cs:__imp_NetioInsertWorkQueue
0x1400f83ed  nop     dword ptr [rax+rax+00h]
0x1400f83f2  mov     eax, 103h
0x1400f83f7  mov     rcx, [rsp+98h+var_38]
0x1400f83fc  xor     rcx, rsp; StackCookie
0x1400f83ff  call    __security_check_cookie
0x1400f8404  lea     r11, [rsp+98h+var_28]
0x1400f8409  mov     rbx, [r11+30h]
0x1400f840d  mov     rbp, [r11+38h]
0x1400f8411  mov     rsp, r11
0x1400f8414  pop     r15
0x1400f8416  pop     r14
0x1400f8418  pop     r12
0x1400f841a  pop     rdi
0x1400f841b  pop     rsi
0x1400f841c  retn
```
