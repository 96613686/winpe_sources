# TcpCreateListener

- ea: `0x14011bdb8`
- end: `0x14011c2be`
- name: `TcpCreateListener`
- size: `1286`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14011bd90`

## callees

- `0x140018578`
- `0x14001df40`
- `0x14001dfa8`
- `0x140023800`
- `0x140048a40`
- `0x140049760`
- `0x140071ac0`
- `0x14009f0f0`
- `0x1400b59dc`
- `0x1400d7980`
- `0x1400f44bc`
- `0x14010a69c`
- `0x14011bdb8`
- `0x1401253a0`
- `0x140128dd8`
- `0x140136e80`
- `0x1401c0fd0`
- `0x1401c1280`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x14011bfc7`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14011bfc7`
- `ntoskrnl!ObfReferenceObject` at `0x14011c038`
- `ntoskrnl!ObfReferenceObject` at `0x14011c0b0`
- `ntoskrnl!ObfReferenceObject` at `0x14011c205`
- `ntoskrnl!ObfReferenceObject` at `0x14011c038`
- `ntoskrnl!ObfReferenceObject` at `0x14011c0b0`
- `ntoskrnl!ObfReferenceObject` at `0x14011c205`
- `ntoskrnl!KeBugCheck` at `0x14011c1d4`
- `ntoskrnl!KeBugCheck` at `0x14011c1d4`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14011c059`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14011c059`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bea3`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011bea3`
- `ntoskrnl!RtlCreateHashTable` at `0x14011bf5e`
- `ntoskrnl!RtlCreateHashTable` at `0x14011bf5e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14011c227`
- `ntoskrnl!KeGetCurrentIrql` at `0x14011c227`
- `ntoskrnl!PsGetProcessId` at `0x14011be82`
- `ntoskrnl!PsGetProcessId` at `0x14011be82`
- `ntoskrnl!KeInitializeSpinLock` at `0x14011bfb1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14011bfb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011bf8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011bf8f`
- `ntoskrnl!ExAllocatePool2` at `0x14011bf13`
- `ntoskrnl!ExAllocatePool2` at `0x14011c15e`
- `ntoskrnl!ExAllocatePool2` at `0x14011bf13`
- `ntoskrnl!ExAllocatePool2` at `0x14011c15e`
- `NETIO!NetioInsertWorkQueue` at `0x14011c25e`
- `NETIO!NetioInsertWorkQueue` at `0x14011c25e`

## pseudocode

```c
__int64 __fastcall TcpCreateListener(__int64 a1, __int64 a2)
{
  int v2; // ebp
  __int64 v5; // rdi
  __int64 v7; // r15
  char v8; // bp
  ADDRESS_FAMILY **v9; // rbp
  struct _KPROCESS *ClientProcess; // rsi
  char ProcessId; // di
  int v12; // ebx
  char ProcessStartKey; // al
  __int64 Pool2; // rax
  __int64 v15; // rsi
  void *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  void *v19; // rcx
  void *v20; // rbx
  _WORD *v21; // rax
  UCHAR v22; // al
  const void *v23; // rdx
  __int64 v24; // rdx
  void *v25; // rcx
  _QWORD v26[2]; // [rsp+60h] [rbp-48h] BYREF

  v2 = *(_DWORD *)(a2 + 16);
  if ( v2 >= 0 )
  {
    v9 = (ADDRESS_FAMILY **)(a2 + 64);
    v7 = InetFindAndReferenceAf(&TcpInetTransport, **(unsigned __int16 **)(a2 + 64));
    if ( !v7 )
    {
      ClientProcess = *(struct _KPROCESS **)(a2 + 40);
      if ( !ClientProcess )
        ClientProcess = (struct _KPROCESS *)InetGetClientProcess();
      if ( dword_1402241D4 && (BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x40) != 0 )
      {
        v26[0] = *(_QWORD *)(a2 + 32);
        v26[1] = 0;
        ProcessId = (unsigned __int8)PsGetProcessId(ClientProcess);
        v12 = SOCKADDR_SIZE(**v9);
        ProcessStartKey = PsGetProcessStartKey(ClientProcess);
        McTemplateK0pqbr1qqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_LISTENER_ACTIVATION_FAILED_AF_V1,
          (unsigned int)v26,
          0,
          v12,
          (__int64)v9,
          0,
          ProcessId,
          0,
          0,
          ProcessStartKey);
      }
      return 3221266451LL;
    }
    v5 = 0;
    v8 = 0;
  }
  else
  {
    v5 = *(_QWORD *)(a2 + 24);
    if ( (*(_BYTE *)(v5 + 205) & 1) != 0 )
      return 3221225659LL;
    v7 = *(_QWORD *)(v5 + 32);
    CarAcquireCacheAwareReference(*(_QWORD *)(v7 + 16), 1);
    v8 = v2 & 1;
  }
  Pool2 = ExAllocatePool2(64, 336, 1282433876);
  v15 = Pool2;
  if ( !Pool2 )
  {
    InetDereferenceAf(v7);
    if ( v5 )
    {
      if ( !v8 )
        TcpCloseEndpoint((PKSPIN_LOCK)v5);
    }
    return 3221225495LL;
  }
  if ( !RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)(Pool2 + 232), 6u, 0) )
  {
    InetDereferenceAf(v7);
    if ( v5 && !v8 )
      TcpCloseEndpoint((PKSPIN_LOCK)v5);
    ExFreePoolWithTag((PVOID)v15, 0);
    return 3221225495LL;
  }
  TcpipTraceActivityIDStart(v15, 3);
  KeInitializeSpinLock((PKSPIN_LOCK)(v15 + 8));
  *(_DWORD *)(v15 + 16) = 0;
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)v15);
  *(_QWORD *)(v15 + 48) = v7;
  *(_QWORD *)(v15 + 24) = 1;
  *(_QWORD *)(v15 + 112) = v7;
  *(_QWORD *)(v15 + 40) = a1;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 16)) <= 1 )
    __fastfail(0xEu);
  *(_QWORD *)(v15 + 216) = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(v15 + 224) = *(_QWORD *)(a2 + 72);
  if ( !v5 )
  {
    v16 = *(void **)(a2 + 40);
    if ( !v16 )
      v16 = (void *)InetGetClientProcess();
    *(_QWORD *)(v15 + 56) = v16;
    ObfReferenceObject(v16);
    *(_QWORD *)(v15 + 80) = InetGetProcessTag(*(_QWORD *)(a2 + 40), *(_QWORD *)(a2 + 48));
    KeQuerySystemTimePrecise(v15 + 72);
    TcpInitializeOptions(v7, v15 + 240);
    InetInitializeSs(v15 + 280, 0, 0);
    if ( !Microsoft_Windows_Networking_CorrelationEnabled )
      goto LABEL_33;
    v17 = *(_QWORD *)(a2 + 32);
    if ( !v17 )
      goto LABEL_33;
    v18 = 7;
    goto LABEL_32;
  }
  v19 = *(void **)(v5 + 40);
  *(_QWORD *)(v15 + 56) = v19;
  ObfReferenceObject(v19);
  *(_QWORD *)(v15 + 80) = *(_QWORD *)(v5 + 72);
  *(_QWORD *)(v15 + 72) = *(_QWORD *)(v5 + 64);
  *(_OWORD *)(v15 + 240) = *(_OWORD *)(v5 + 168);
  *(_OWORD *)(v15 + 256) = *(_OWORD *)(v5 + 184);
  *(_QWORD *)(v15 + 272) = *(_QWORD *)(v5 + 200);
  InetInitializeSs(v15 + 280, *(_QWORD *)(v5 + 32), v5 + 208);
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
    v18 = 8;
    v17 = v5;
LABEL_32:
    TcpipEtwTransferActivity(v15, v17, v18);
  }
LABEL_33:
  if ( (*(_DWORD *)(a2 + 16) & 2) != 0 )
    *(_BYTE *)(v15 + 278) |= 0x40u;
  if ( v5 && (*(_DWORD *)(v5 + 16) & 1) != 0 )
  {
    v20 = 0;
  }
  else
  {
    v21 = (_WORD *)ExAllocatePool2(64, 28, 1397515092);
    v20 = v21;
    if ( !v21 )
    {
      if ( v5 && !v8 )
        TcpCloseEndpoint((PKSPIN_LOCK)v5);
      TcpCloseListener(v15, 0);
      return 3221225495LL;
    }
    *v21 = **(_WORD **)(a2 + 64);
    v22 = SOCKADDR_SIZE(**(_WORD **)(a2 + 64));
    memmove(v20, v23, v22);
  }
  *(_QWORD *)(v15 + 160) = *(_QWORD *)a2;
  *(_QWORD *)(v15 + 168) = *(_QWORD *)(a2 + 8);
  *(_BYTE *)(v15 + 184) = v8;
  *(_QWORD *)(v15 + 176) = v5;
  if ( v5 )
  {
    v24 = _InterlockedIncrement64((volatile signed __int64 *)(v5 + 8));
    if ( v24 <= 1 )
      KeBugCheck(0x1Cu);
    if ( EndpointReferenceHistory )
      RhAppendHistory(EndpointReferenceHistory, v24, v5);
  }
  v25 = *(void **)(a2 + 48);
  *(_QWORD *)(v15 + 192) = v25;
  if ( v25 )
    ObfReferenceObject(v25);
  *(_QWORD *)(v15 + 208) = v20;
  if ( !v5 )
    v5 = a2;
  *(_QWORD *)(v15 + 64) = *(_QWORD *)(v5 + 56);
  if ( KeGetCurrentIrql() )
  {
    NetioInsertWorkQueue(TcpCreateListenerWorkQueue, v15 + 152);
  }
  else
  {
    *(_QWORD *)(v15 + 152) = 0;
    TcpCreateListenerWorkQueueRoutine((_QWORD *)(v15 + 152));
  }
  return 259;
}

```

## disassembly

```asm
0x14011bdb8  mov     [rsp+arg_10], rbx
0x14011bdbd  mov     [rsp+arg_18], rbp
0x14011bdc2  push    rsi
0x14011bdc3  push    rdi
0x14011bdc4  push    r12
0x14011bdc6  push    r14
0x14011bdc8  push    r15
0x14011bdca  sub     rsp, 80h
0x14011bdd1  mov     rax, cs:__security_cookie
0x14011bdd8  xor     rax, rsp
0x14011bddb  mov     [rsp+0A8h+var_38], rax
0x14011bde0  mov     ebp, [rdx+10h]
0x14011bde3  mov     r14, rdx
0x14011bde6  mov     r12, rcx
0x14011bde9  test    ebp, ebp
0x14011bdeb  jns     short loc_14011BE1F
0x14011bded  mov     rdi, [rdx+18h]
0x14011bdf1  test    byte ptr [rdi+0CDh], 1
0x14011bdf8  jz      short loc_14011BE04
0x14011bdfa  mov     eax, 0C00000BBh
0x14011bdff  jmp     loc_14011C294
0x14011be04  mov     r15, [rdi+20h]
0x14011be08  mov     edx, 1
0x14011be0d  mov     rcx, [r15+10h]
0x14011be11  call    CarAcquireCacheAwareReference
0x14011be16  and     bpl, 1
0x14011be1a  jmp     loc_14011BF03
0x14011be1f  lea     rbp, [rdx+40h]
0x14011be23  mov     rdx, [rbp+0]
0x14011be27  lea     rcx, TcpInetTransport
0x14011be2e  movzx   edx, word ptr [rdx]
0x14011be31  call    InetFindAndReferenceAf
0x14011be36  mov     r15, rax
0x14011be39  test    rax, rax
0x14011be3c  jnz     loc_14011BEFE
0x14011be42  mov     rsi, [r14+28h]
0x14011be46  test    rsi, rsi
0x14011be49  jnz     short loc_14011BE53
0x14011be4b  call    InetGetClientProcess
0x14011be50  mov     rsi, rax
0x14011be53  cmp     cs:dword_1402241D4, 0
0x14011be5a  jz      loc_14011BEF4
0x14011be60  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 40h
0x14011be67  jz      loc_14011BEF4
0x14011be6d  mov     rcx, [r14+20h]
0x14011be71  mov     [rsp+0A8h+var_48], rcx
0x14011be76  mov     rcx, rsi; Process
0x14011be79  mov     [rsp+0A8h+var_40], 0
0x14011be82  call    cs:__imp_PsGetProcessId
0x14011be89  nop     dword ptr [rax+rax+00h]
0x14011be8e  mov     rcx, [rbp+0]
0x14011be92  mov     rdi, rax
0x14011be95  movzx   ecx, word ptr [rcx]; af
0x14011be98  call    SOCKADDR_SIZE
0x14011be9d  mov     rcx, rsi
0x14011bea0  movzx   ebx, al
0x14011bea3  call    cs:__imp_PsGetProcessStartKey
0x14011beaa  nop     dword ptr [rax+rax+00h]
0x14011beaf  mov     [rsp+0A8h+var_58], rax
0x14011beb4  xor     r9d, r9d
0x14011beb7  mov     [rsp+0A8h+var_60], 0
0x14011bebf  lea     r8, [rsp+0A8h+var_48]
0x14011bec4  mov     [rsp+0A8h+var_68], 0
0x14011becc  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_AF_V1
0x14011bed3  mov     [rsp+0A8h+var_70], edi
0x14011bed7  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14011bede  mov     [rsp+0A8h+var_78], 0
0x14011bee6  mov     [rsp+0A8h+var_80], rbp
0x14011beeb  mov     [rsp+0A8h+var_88], ebx
0x14011beef  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x14011bef4  mov     eax, 0C000A013h
0x14011bef9  jmp     loc_14011C294
0x14011befe  xor     edi, edi
0x14011bf00  xor     bpl, bpl
0x14011bf03  mov     edx, 150h
0x14011bf08  mov     ecx, 40h ; '@'
0x14011bf0d  mov     r8d, 4C706354h
0x14011bf13  call    cs:__imp_ExAllocatePool2
0x14011bf1a  nop     dword ptr [rax+rax+00h]
0x14011bf1f  mov     rsi, rax
0x14011bf22  test    rax, rax
0x14011bf25  jnz     short loc_14011BF50
0x14011bf27  mov     rcx, r15
0x14011bf2a  call    _InetDereferenceAf
0x14011bf2f  test    rdi, rdi
0x14011bf32  jz      loc_14011C28F
0x14011bf38  test    bpl, bpl
0x14011bf3b  jnz     loc_14011C28F
0x14011bf41  xor     edx, edx
0x14011bf43  mov     rcx, rdi; SpinLock
0x14011bf46  call    TcpCloseEndpoint
0x14011bf4b  jmp     loc_14011C28F
0x14011bf50  xor     r8d, r8d; Flags
0x14011bf53  lea     rcx, [rax+0E8h]; HashTable
0x14011bf5a  lea     edx, [r8+6]; Shift
0x14011bf5e  call    cs:__imp_RtlCreateHashTable
0x14011bf65  nop     dword ptr [rax+rax+00h]
0x14011bf6a  test    al, al
0x14011bf6c  jnz     short loc_14011BFA0
0x14011bf6e  mov     rcx, r15
0x14011bf71  call    _InetDereferenceAf
0x14011bf76  test    rdi, rdi
0x14011bf79  jz      short loc_14011BF8A
0x14011bf7b  test    bpl, bpl
0x14011bf7e  jnz     short loc_14011BF8A
0x14011bf80  xor     edx, edx
0x14011bf82  mov     rcx, rdi; SpinLock
0x14011bf85  call    TcpCloseEndpoint
0x14011bf8a  xor     edx, edx; Tag
0x14011bf8c  mov     rcx, rsi; P
0x14011bf8f  call    cs:__imp_ExFreePoolWithTag
0x14011bf96  nop     dword ptr [rax+rax+00h]
0x14011bf9b  jmp     loc_14011C28F
0x14011bfa0  mov     edx, 3
0x14011bfa5  mov     rcx, rsi
0x14011bfa8  call    TcpipTraceActivityIDStart
0x14011bfad  lea     rcx, [rsi+8]; SpinLock
0x14011bfb1  call    cs:__imp_KeInitializeSpinLock
0x14011bfb8  nop     dword ptr [rax+rax+00h]
0x14011bfbd  mov     rcx, rsi; RunRef
0x14011bfc0  mov     dword ptr [rsi+10h], 0
0x14011bfc7  call    cs:__imp_ExInitializeRundownProtection
0x14011bfce  nop     dword ptr [rax+rax+00h]
0x14011bfd3  mov     eax, 1
0x14011bfd8  mov     [rsi+30h], r15
0x14011bfdc  mov     [rsi+18h], rax
0x14011bfe0  mov     [rsi+70h], r15
0x14011bfe4  mov     [rsi+28h], r12
0x14011bfe8  lock xadd [r12+10h], rax
0x14011bfef  mov     r12d, 1
0x14011bff5  add     rax, r12
0x14011bff8  cmp     rax, r12
0x14011bffb  jg      short loc_14011C004
0x14011bffd  lea     ecx, [r12+0Dh]
0x14011c002  int     29h; Win8: RtlFailFast(ecx)
0x14011c004  mov     rax, [r14+58h]
0x14011c008  mov     [rsi+0D8h], rax
0x14011c00f  mov     rax, [r14+48h]
0x14011c013  mov     [rsi+0E0h], rax
0x14011c01a  test    rdi, rdi
0x14011c01d  jnz     loc_14011C0A8
0x14011c023  mov     rax, [r14+28h]
0x14011c027  test    rax, rax
0x14011c02a  jnz     short loc_14011C031
0x14011c02c  call    InetGetClientProcess
0x14011c031  mov     rcx, rax; Object
0x14011c034  mov     [rsi+38h], rax
0x14011c038  call    cs:__imp_ObfReferenceObject
0x14011c03f  nop     dword ptr [rax+rax+00h]
0x14011c044  mov     rdx, [r14+30h]
0x14011c048  mov     rcx, [r14+28h]
0x14011c04c  call    InetGetProcessTag
0x14011c051  lea     rcx, [rsi+48h]
0x14011c055  mov     [rsi+50h], rax
0x14011c059  call    cs:__imp_KeQuerySystemTimePrecise
0x14011c060  nop     dword ptr [rax+rax+00h]
0x14011c065  lea     rdx, [rsi+0F0h]
0x14011c06c  mov     rcx, r15
0x14011c06f  call    TcpInitializeOptions
0x14011c074  lea     rcx, [rsi+118h]
0x14011c07b  xor     r8d, r8d
0x14011c07e  xor     edx, edx
0x14011c080  call    InetInitializeSs
0x14011c085  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14011c08b  test    eax, eax
0x14011c08d  jz      loc_14011C12A
0x14011c093  mov     rdx, [r14+20h]
0x14011c097  test    rdx, rdx
0x14011c09a  jz      loc_14011C12A
0x14011c0a0  mov     r8d, 7
0x14011c0a6  jmp     short loc_14011C122
0x14011c0a8  mov     rcx, [rdi+28h]; Object
0x14011c0ac  mov     [rsi+38h], rcx
0x14011c0b0  call    cs:__imp_ObfReferenceObject
0x14011c0b7  nop     dword ptr [rax+rax+00h]
0x14011c0bc  mov     rax, [rdi+48h]
0x14011c0c0  lea     r8, [rdi+0D0h]
0x14011c0c7  mov     [rsi+50h], rax
0x14011c0cb  lea     rcx, [rsi+118h]
0x14011c0d2  mov     rax, [rdi+40h]
0x14011c0d6  mov     [rsi+48h], rax
0x14011c0da  movups  xmm0, xmmword ptr [rdi+0A8h]
0x14011c0e1  movups  xmmword ptr [rsi+0F0h], xmm0
0x14011c0e8  movups  xmm1, xmmword ptr [rdi+0B8h]
0x14011c0ef  movups  xmmword ptr [rsi+100h], xmm1
0x14011c0f6  movsd   xmm0, qword ptr [rdi+0C8h]
0x14011c0fe  movsd   qword ptr [rsi+110h], xmm0
0x14011c106  mov     rdx, [rdi+20h]
0x14011c10a  call    InetInitializeSs
0x14011c10f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14011c115  test    eax, eax
0x14011c117  jz      short loc_14011C12A
0x14011c119  mov     r8d, 8
0x14011c11f  mov     rdx, rdi
0x14011c122  mov     rcx, rsi
0x14011c125  call    TcpipEtwTransferActivity
0x14011c12a  mov     eax, [r14+10h]
0x14011c12e  test    al, 2
0x14011c130  jz      short loc_14011C139
0x14011c132  or      byte ptr [rsi+116h], 40h
0x14011c139  mov     r15d, 1Ch
0x14011c13f  test    rdi, rdi
0x14011c142  jz      short loc_14011C150
0x14011c144  mov     eax, [rdi+10h]
0x14011c147  test    r12b, al
0x14011c14a  jz      short loc_14011C150
0x14011c14c  xor     ebx, ebx
0x14011c14e  jmp     short loc_14011C198
0x14011c150  mov     r8d, 534C6354h
0x14011c156  mov     rdx, r15
0x14011c159  mov     ecx, 40h ; '@'
0x14011c15e  call    cs:__imp_ExAllocatePool2
0x14011c165  nop     dword ptr [rax+rax+00h]
0x14011c16a  mov     rbx, rax
0x14011c16d  test    rax, rax
0x14011c170  jz      loc_14011C271
0x14011c176  mov     rcx, [r14+40h]
0x14011c17a  movzx   edx, word ptr [rcx]
0x14011c17d  mov     [rax], dx
0x14011c180  mov     rdx, [r14+40h]
0x14011c184  movzx   ecx, word ptr [rdx]; af
0x14011c187  call    SOCKADDR_SIZE
0x14011c18c  movzx   r8d, al; Size
0x14011c190  mov     rcx, rbx; void *
0x14011c193  call    memmove
0x14011c198  mov     rax, [r14]
0x14011c19b  mov     [rsi+0A0h], rax
0x14011c1a2  mov     rax, [r14+8]
0x14011c1a6  mov     [rsi+0A8h], rax
0x14011c1ad  mov     [rsi+0B8h], bpl
0x14011c1b4  mov     [rsi+0B0h], rdi
0x14011c1bb  test    rdi, rdi
0x14011c1be  jz      short loc_14011C1F5
0x14011c1c0  mov     rdx, r12
0x14011c1c3  lock xadd [rdi+8], rdx
0x14011c1c9  add     rdx, r12
0x14011c1cc  cmp     rdx, r12
0x14011c1cf  jg      short loc_14011C1E1
0x14011c1d1  mov     ecx, r15d; BugCheckCode
0x14011c1d4  call    cs:__imp_KeBugCheck
0x14011c1e1  mov     rcx, cs:EndpointReferenceHistory
0x14011c1e8  test    rcx, rcx
0x14011c1eb  jz      short loc_14011C1F5
0x14011c1ed  mov     r8, rdi
0x14011c1f0  call    RhAppendHistory
0x14011c1f5  mov     rcx, [r14+30h]; Object
0x14011c1f9  mov     [rsi+0C0h], rcx
0x14011c200  test    rcx, rcx
0x14011c203  jz      short loc_14011C211
0x14011c205  call    cs:__imp_ObfReferenceObject
0x14011c20c  nop     dword ptr [rax+rax+00h]
0x14011c211  mov     [rsi+0D0h], rbx
0x14011c218  test    rdi, rdi
0x14011c21b  cmovz   rdi, r14
0x14011c21f  mov     rax, [rdi+38h]
0x14011c223  mov     [rsi+40h], rax
0x14011c227  call    cs:__imp_KeGetCurrentIrql
0x14011c22e  nop     dword ptr [rax+rax+00h]
0x14011c233  test    al, al
0x14011c235  jnz     short loc_14011C250
0x14011c237  lea     rcx, [rsi+98h]
0x14011c23e  mov     qword ptr [rsi+98h], 0
0x14011c249  call    TcpCreateListenerWorkQueueRoutine
0x14011c24e  jmp     short loc_14011C26A
0x14011c250  lea     rdx, [rsi+98h]
0x14011c257  lea     rcx, TcpCreateListenerWorkQueue
0x14011c25e  call    cs:__imp_NetioInsertWorkQueue
0x14011c265  nop     dword ptr [rax+rax+00h]
0x14011c26a  mov     eax, 103h
0x14011c26f  jmp     short loc_14011C294
0x14011c271  test    rdi, rdi
0x14011c274  jz      short loc_14011C285
0x14011c276  test    bpl, bpl
0x14011c279  jnz     short loc_14011C285
0x14011c27b  xor     edx, edx
0x14011c27d  mov     rcx, rdi; SpinLock
0x14011c280  call    TcpCloseEndpoint
0x14011c285  xor     edx, edx
0x14011c287  mov     rcx, rsi
0x14011c28a  call    TcpCloseListener
0x14011c28f  mov     eax, 0C0000017h
0x14011c294  mov     rcx, [rsp+0A8h+var_38]
0x14011c299  xor     rcx, rsp; StackCookie
0x14011c29c  call    __security_check_cookie
0x14011c2a1  lea     r11, [rsp+0A8h+var_28]
0x14011c2a9  mov     rbx, [r11+40h]
0x14011c2ad  mov     rbp, [r11+48h]
0x14011c2b1  mov     rsp, r11
0x14011c2b4  pop     r15
0x14011c2b6  pop     r14
0x14011c2b8  pop     r12
0x14011c2ba  pop     rdi
0x14011c2bb  pop     rsi
0x14011c2bc  retn
```
