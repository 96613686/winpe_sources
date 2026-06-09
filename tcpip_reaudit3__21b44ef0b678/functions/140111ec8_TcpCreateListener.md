# TcpCreateListener

- ea: `0x140111ec8`
- end: `0x1401123ce`
- name: `TcpCreateListener`
- size: `1286`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140111ea0`

## callees

- `0x1400158e0`
- `0x140017060`
- `0x14002f4a0`
- `0x140039b00`
- `0x14003a730`
- `0x14005f34c`
- `0x140074ac0`
- `0x1400ae7f8`
- `0x1400b5730`
- `0x1400b917c`
- `0x1400ff31c`
- `0x140111ec8`
- `0x1401154a8`
- `0x14011b9c0`
- `0x14011e6e8`
- `0x140130290`
- `0x1401bf4d0`
- `0x1401bf780`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1401120d7`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1401120d7`
- `ntoskrnl!ObfReferenceObject` at `0x140112148`
- `ntoskrnl!ObfReferenceObject` at `0x1401121c0`
- `ntoskrnl!ObfReferenceObject` at `0x140112315`
- `ntoskrnl!ObfReferenceObject` at `0x140112148`
- `ntoskrnl!ObfReferenceObject` at `0x1401121c0`
- `ntoskrnl!ObfReferenceObject` at `0x140112315`
- `ntoskrnl!KeBugCheck` at `0x1401122e4`
- `ntoskrnl!KeBugCheck` at `0x1401122e4`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140112169`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140112169`
- `ntoskrnl!PsGetProcessStartKey` at `0x140111fb3`
- `ntoskrnl!PsGetProcessStartKey` at `0x140111fb3`
- `ntoskrnl!RtlCreateHashTable` at `0x14011206e`
- `ntoskrnl!RtlCreateHashTable` at `0x14011206e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140112337`
- `ntoskrnl!KeGetCurrentIrql` at `0x140112337`
- `ntoskrnl!PsGetProcessId` at `0x140111f92`
- `ntoskrnl!PsGetProcessId` at `0x140111f92`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401120c1`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401120c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011209f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011209f`
- `ntoskrnl!ExAllocatePool2` at `0x140112023`
- `ntoskrnl!ExAllocatePool2` at `0x14011226e`
- `ntoskrnl!ExAllocatePool2` at `0x140112023`
- `ntoskrnl!ExAllocatePool2` at `0x14011226e`
- `NETIO!NetioInsertWorkQueue` at `0x14011236e`
- `NETIO!NetioInsertWorkQueue` at `0x14011236e`

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
      if ( dword_1402201D4 && (BYTE4(WPP_MAIN_CB.Reserved) & 0x40) != 0 )
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
0x140111ec8  mov     [rsp+arg_10], rbx
0x140111ecd  mov     [rsp+arg_18], rbp
0x140111ed2  push    rsi
0x140111ed3  push    rdi
0x140111ed4  push    r12
0x140111ed6  push    r14
0x140111ed8  push    r15
0x140111eda  sub     rsp, 80h
0x140111ee1  mov     rax, cs:__security_cookie
0x140111ee8  xor     rax, rsp
0x140111eeb  mov     [rsp+0A8h+var_38], rax
0x140111ef0  mov     ebp, [rdx+10h]
0x140111ef3  mov     r14, rdx
0x140111ef6  mov     r12, rcx
0x140111ef9  test    ebp, ebp
0x140111efb  jns     short loc_140111F2F
0x140111efd  mov     rdi, [rdx+18h]
0x140111f01  test    byte ptr [rdi+0CDh], 1
0x140111f08  jz      short loc_140111F14
0x140111f0a  mov     eax, 0C00000BBh
0x140111f0f  jmp     loc_1401123A4
0x140111f14  mov     r15, [rdi+20h]
0x140111f18  mov     edx, 1
0x140111f1d  mov     rcx, [r15+10h]
0x140111f21  call    CarAcquireCacheAwareReference
0x140111f26  and     bpl, 1
0x140111f2a  jmp     loc_140112013
0x140111f2f  lea     rbp, [rdx+40h]
0x140111f33  mov     rdx, [rbp+0]
0x140111f37  lea     rcx, TcpInetTransport
0x140111f3e  movzx   edx, word ptr [rdx]
0x140111f41  call    InetFindAndReferenceAf
0x140111f46  mov     r15, rax
0x140111f49  test    rax, rax
0x140111f4c  jnz     loc_14011200E
0x140111f52  mov     rsi, [r14+28h]
0x140111f56  test    rsi, rsi
0x140111f59  jnz     short loc_140111F63
0x140111f5b  call    InetGetClientProcess
0x140111f60  mov     rsi, rax
0x140111f63  cmp     cs:dword_1402201D4, 0
0x140111f6a  jz      loc_140112004
0x140111f70  test    byte ptr cs:WPP_MAIN_CB.Reserved+4, 40h
0x140111f77  jz      loc_140112004
0x140111f7d  mov     rcx, [r14+20h]
0x140111f81  mov     [rsp+0A8h+var_48], rcx
0x140111f86  mov     rcx, rsi; Process
0x140111f89  mov     [rsp+0A8h+var_40], 0
0x140111f92  call    cs:__imp_PsGetProcessId
0x140111f99  nop     dword ptr [rax+rax+00h]
0x140111f9e  mov     rcx, [rbp+0]
0x140111fa2  mov     rdi, rax
0x140111fa5  movzx   ecx, word ptr [rcx]; af
0x140111fa8  call    SOCKADDR_SIZE
0x140111fad  mov     rcx, rsi
0x140111fb0  movzx   ebx, al
0x140111fb3  call    cs:__imp_PsGetProcessStartKey
0x140111fba  nop     dword ptr [rax+rax+00h]
0x140111fbf  mov     [rsp+0A8h+var_58], rax
0x140111fc4  xor     r9d, r9d
0x140111fc7  mov     [rsp+0A8h+var_60], 0
0x140111fcf  lea     r8, [rsp+0A8h+var_48]
0x140111fd4  mov     [rsp+0A8h+var_68], 0
0x140111fdc  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_AF_V1
0x140111fe3  mov     [rsp+0A8h+var_70], edi
0x140111fe7  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140111fee  mov     [rsp+0A8h+var_78], 0
0x140111ff6  mov     [rsp+0A8h+var_80], rbp
0x140111ffb  mov     [rsp+0A8h+var_88], ebx
0x140111fff  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x140112004  mov     eax, 0C000A013h
0x140112009  jmp     loc_1401123A4
0x14011200e  xor     edi, edi
0x140112010  xor     bpl, bpl
0x140112013  mov     edx, 150h
0x140112018  mov     ecx, 40h ; '@'
0x14011201d  mov     r8d, 4C706354h
0x140112023  call    cs:__imp_ExAllocatePool2
0x14011202a  nop     dword ptr [rax+rax+00h]
0x14011202f  mov     rsi, rax
0x140112032  test    rax, rax
0x140112035  jnz     short loc_140112060
0x140112037  mov     rcx, r15
0x14011203a  call    _InetDereferenceAf
0x14011203f  test    rdi, rdi
0x140112042  jz      loc_14011239F
0x140112048  test    bpl, bpl
0x14011204b  jnz     loc_14011239F
0x140112051  xor     edx, edx
0x140112053  mov     rcx, rdi; SpinLock
0x140112056  call    TcpCloseEndpoint
0x14011205b  jmp     loc_14011239F
0x140112060  xor     r8d, r8d; Flags
0x140112063  lea     rcx, [rax+0E8h]; HashTable
0x14011206a  lea     edx, [r8+6]; Shift
0x14011206e  call    cs:__imp_RtlCreateHashTable
0x140112075  nop     dword ptr [rax+rax+00h]
0x14011207a  test    al, al
0x14011207c  jnz     short loc_1401120B0
0x14011207e  mov     rcx, r15
0x140112081  call    _InetDereferenceAf
0x140112086  test    rdi, rdi
0x140112089  jz      short loc_14011209A
0x14011208b  test    bpl, bpl
0x14011208e  jnz     short loc_14011209A
0x140112090  xor     edx, edx
0x140112092  mov     rcx, rdi; SpinLock
0x140112095  call    TcpCloseEndpoint
0x14011209a  xor     edx, edx; Tag
0x14011209c  mov     rcx, rsi; P
0x14011209f  call    cs:__imp_ExFreePoolWithTag
0x1401120a6  nop     dword ptr [rax+rax+00h]
0x1401120ab  jmp     loc_14011239F
0x1401120b0  mov     edx, 3
0x1401120b5  mov     rcx, rsi
0x1401120b8  call    TcpipTraceActivityIDStart
0x1401120bd  lea     rcx, [rsi+8]; SpinLock
0x1401120c1  call    cs:__imp_KeInitializeSpinLock
0x1401120c8  nop     dword ptr [rax+rax+00h]
0x1401120cd  mov     rcx, rsi; RunRef
0x1401120d0  mov     dword ptr [rsi+10h], 0
0x1401120d7  call    cs:__imp_ExInitializeRundownProtection
0x1401120de  nop     dword ptr [rax+rax+00h]
0x1401120e3  mov     eax, 1
0x1401120e8  mov     [rsi+30h], r15
0x1401120ec  mov     [rsi+18h], rax
0x1401120f0  mov     [rsi+70h], r15
0x1401120f4  mov     [rsi+28h], r12
0x1401120f8  lock xadd [r12+10h], rax
0x1401120ff  mov     r12d, 1
0x140112105  add     rax, r12
0x140112108  cmp     rax, r12
0x14011210b  jg      short loc_140112114
0x14011210d  lea     ecx, [r12+0Dh]
0x140112112  int     29h; Win8: RtlFailFast(ecx)
0x140112114  mov     rax, [r14+58h]
0x140112118  mov     [rsi+0D8h], rax
0x14011211f  mov     rax, [r14+48h]
0x140112123  mov     [rsi+0E0h], rax
0x14011212a  test    rdi, rdi
0x14011212d  jnz     loc_1401121B8
0x140112133  mov     rax, [r14+28h]
0x140112137  test    rax, rax
0x14011213a  jnz     short loc_140112141
0x14011213c  call    InetGetClientProcess
0x140112141  mov     rcx, rax; Object
0x140112144  mov     [rsi+38h], rax
0x140112148  call    cs:__imp_ObfReferenceObject
0x14011214f  nop     dword ptr [rax+rax+00h]
0x140112154  mov     rdx, [r14+30h]
0x140112158  mov     rcx, [r14+28h]
0x14011215c  call    InetGetProcessTag
0x140112161  lea     rcx, [rsi+48h]
0x140112165  mov     [rsi+50h], rax
0x140112169  call    cs:__imp_KeQuerySystemTimePrecise
0x140112170  nop     dword ptr [rax+rax+00h]
0x140112175  lea     rdx, [rsi+0F0h]
0x14011217c  mov     rcx, r15
0x14011217f  call    TcpInitializeOptions
0x140112184  lea     rcx, [rsi+118h]
0x14011218b  xor     r8d, r8d
0x14011218e  xor     edx, edx
0x140112190  call    InetInitializeSs
0x140112195  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14011219b  test    eax, eax
0x14011219d  jz      loc_14011223A
0x1401121a3  mov     rdx, [r14+20h]
0x1401121a7  test    rdx, rdx
0x1401121aa  jz      loc_14011223A
0x1401121b0  mov     r8d, 7
0x1401121b6  jmp     short loc_140112232
0x1401121b8  mov     rcx, [rdi+28h]; Object
0x1401121bc  mov     [rsi+38h], rcx
0x1401121c0  call    cs:__imp_ObfReferenceObject
0x1401121c7  nop     dword ptr [rax+rax+00h]
0x1401121cc  mov     rax, [rdi+48h]
0x1401121d0  lea     r8, [rdi+0D0h]
0x1401121d7  mov     [rsi+50h], rax
0x1401121db  lea     rcx, [rsi+118h]
0x1401121e2  mov     rax, [rdi+40h]
0x1401121e6  mov     [rsi+48h], rax
0x1401121ea  movups  xmm0, xmmword ptr [rdi+0A8h]
0x1401121f1  movups  xmmword ptr [rsi+0F0h], xmm0
0x1401121f8  movups  xmm1, xmmword ptr [rdi+0B8h]
0x1401121ff  movups  xmmword ptr [rsi+100h], xmm1
0x140112206  movsd   xmm0, qword ptr [rdi+0C8h]
0x14011220e  movsd   qword ptr [rsi+110h], xmm0
0x140112216  mov     rdx, [rdi+20h]
0x14011221a  call    InetInitializeSs
0x14011221f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140112225  test    eax, eax
0x140112227  jz      short loc_14011223A
0x140112229  mov     r8d, 8
0x14011222f  mov     rdx, rdi
0x140112232  mov     rcx, rsi
0x140112235  call    TcpipEtwTransferActivity
0x14011223a  mov     eax, [r14+10h]
0x14011223e  test    al, 2
0x140112240  jz      short loc_140112249
0x140112242  or      byte ptr [rsi+116h], 40h
0x140112249  mov     r15d, 1Ch
0x14011224f  test    rdi, rdi
0x140112252  jz      short loc_140112260
0x140112254  mov     eax, [rdi+10h]
0x140112257  test    r12b, al
0x14011225a  jz      short loc_140112260
0x14011225c  xor     ebx, ebx
0x14011225e  jmp     short loc_1401122A8
0x140112260  mov     r8d, 534C6354h
0x140112266  mov     rdx, r15
0x140112269  mov     ecx, 40h ; '@'
0x14011226e  call    cs:__imp_ExAllocatePool2
0x140112275  nop     dword ptr [rax+rax+00h]
0x14011227a  mov     rbx, rax
0x14011227d  test    rax, rax
0x140112280  jz      loc_140112381
0x140112286  mov     rcx, [r14+40h]
0x14011228a  movzx   edx, word ptr [rcx]
0x14011228d  mov     [rax], dx
0x140112290  mov     rdx, [r14+40h]
0x140112294  movzx   ecx, word ptr [rdx]; af
0x140112297  call    SOCKADDR_SIZE
0x14011229c  movzx   r8d, al; Size
0x1401122a0  mov     rcx, rbx; void *
0x1401122a3  call    memmove
0x1401122a8  mov     rax, [r14]
0x1401122ab  mov     [rsi+0A0h], rax
0x1401122b2  mov     rax, [r14+8]
0x1401122b6  mov     [rsi+0A8h], rax
0x1401122bd  mov     [rsi+0B8h], bpl
0x1401122c4  mov     [rsi+0B0h], rdi
0x1401122cb  test    rdi, rdi
0x1401122ce  jz      short loc_140112305
0x1401122d0  mov     rdx, r12
0x1401122d3  lock xadd [rdi+8], rdx
0x1401122d9  add     rdx, r12
0x1401122dc  cmp     rdx, r12
0x1401122df  jg      short loc_1401122F1
0x1401122e1  mov     ecx, r15d; BugCheckCode
0x1401122e4  call    cs:__imp_KeBugCheck
0x1401122f1  mov     rcx, cs:EndpointReferenceHistory
0x1401122f8  test    rcx, rcx
0x1401122fb  jz      short loc_140112305
0x1401122fd  mov     r8, rdi
0x140112300  call    RhAppendHistory
0x140112305  mov     rcx, [r14+30h]; Object
0x140112309  mov     [rsi+0C0h], rcx
0x140112310  test    rcx, rcx
0x140112313  jz      short loc_140112321
0x140112315  call    cs:__imp_ObfReferenceObject
0x14011231c  nop     dword ptr [rax+rax+00h]
0x140112321  mov     [rsi+0D0h], rbx
0x140112328  test    rdi, rdi
0x14011232b  cmovz   rdi, r14
0x14011232f  mov     rax, [rdi+38h]
0x140112333  mov     [rsi+40h], rax
0x140112337  call    cs:__imp_KeGetCurrentIrql
0x14011233e  nop     dword ptr [rax+rax+00h]
0x140112343  test    al, al
0x140112345  jnz     short loc_140112360
0x140112347  lea     rcx, [rsi+98h]
0x14011234e  mov     qword ptr [rsi+98h], 0
0x140112359  call    TcpCreateListenerWorkQueueRoutine
0x14011235e  jmp     short loc_14011237A
0x140112360  lea     rdx, [rsi+98h]
0x140112367  lea     rcx, TcpCreateListenerWorkQueue
0x14011236e  call    cs:__imp_NetioInsertWorkQueue
0x140112375  nop     dword ptr [rax+rax+00h]
0x14011237a  mov     eax, 103h
0x14011237f  jmp     short loc_1401123A4
0x140112381  test    rdi, rdi
0x140112384  jz      short loc_140112395
0x140112386  test    bpl, bpl
0x140112389  jnz     short loc_140112395
0x14011238b  xor     edx, edx
0x14011238d  mov     rcx, rdi; SpinLock
0x140112390  call    TcpCloseEndpoint
0x140112395  xor     edx, edx
0x140112397  mov     rcx, rsi
0x14011239a  call    TcpCloseListener
0x14011239f  mov     eax, 0C0000017h
0x1401123a4  mov     rcx, [rsp+0A8h+var_38]
0x1401123a9  xor     rcx, rsp; StackCookie
0x1401123ac  call    __security_check_cookie
0x1401123b1  lea     r11, [rsp+0A8h+var_28]
0x1401123b9  mov     rbx, [r11+40h]
0x1401123bd  mov     rbp, [r11+48h]
0x1401123c1  mov     rsp, r11
0x1401123c4  pop     r15
0x1401123c6  pop     r14
0x1401123c8  pop     r12
0x1401123ca  pop     rdi
0x1401123cb  pop     rsi
0x1401123cc  retn
```
