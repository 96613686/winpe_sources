# TcpCreateListener

- ea: `0x140111d88`
- end: `0x14011228e`
- name: `TcpCreateListener`
- size: `1286`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140111d60`

## callees

- `0x1400158e0`
- `0x140017060`
- `0x14002f200`
- `0x140039860`
- `0x14003a490`
- `0x14005f0ac`
- `0x140074820`
- `0x1400aebd8`
- `0x1400b5b10`
- `0x1400b955c`
- `0x1400ff1dc`
- `0x140111d88`
- `0x140115368`
- `0x14011b880`
- `0x14011e5a8`
- `0x140130150`
- `0x1401bf390`
- `0x1401bf640`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x140111f97`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140111f97`
- `ntoskrnl!ObfReferenceObject` at `0x140112008`
- `ntoskrnl!ObfReferenceObject` at `0x140112080`
- `ntoskrnl!ObfReferenceObject` at `0x1401121d5`
- `ntoskrnl!ObfReferenceObject` at `0x140112008`
- `ntoskrnl!ObfReferenceObject` at `0x140112080`
- `ntoskrnl!ObfReferenceObject` at `0x1401121d5`
- `ntoskrnl!KeBugCheck` at `0x1401121a4`
- `ntoskrnl!KeBugCheck` at `0x1401121a4`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140112029`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140112029`
- `ntoskrnl!PsGetProcessStartKey` at `0x140111e73`
- `ntoskrnl!PsGetProcessStartKey` at `0x140111e73`
- `ntoskrnl!RtlCreateHashTable` at `0x140111f2e`
- `ntoskrnl!RtlCreateHashTable` at `0x140111f2e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401121f7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401121f7`
- `ntoskrnl!PsGetProcessId` at `0x140111e52`
- `ntoskrnl!PsGetProcessId` at `0x140111e52`
- `ntoskrnl!KeInitializeSpinLock` at `0x140111f81`
- `ntoskrnl!KeInitializeSpinLock` at `0x140111f81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140111f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140111f5f`
- `ntoskrnl!ExAllocatePool2` at `0x140111ee3`
- `ntoskrnl!ExAllocatePool2` at `0x14011212e`
- `ntoskrnl!ExAllocatePool2` at `0x140111ee3`
- `ntoskrnl!ExAllocatePool2` at `0x14011212e`
- `NETIO!NetioInsertWorkQueue` at `0x14011222e`
- `NETIO!NetioInsertWorkQueue` at `0x14011222e`

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
0x140111d88  mov     [rsp+arg_10], rbx
0x140111d8d  mov     [rsp+arg_18], rbp
0x140111d92  push    rsi
0x140111d93  push    rdi
0x140111d94  push    r12
0x140111d96  push    r14
0x140111d98  push    r15
0x140111d9a  sub     rsp, 80h
0x140111da1  mov     rax, cs:__security_cookie
0x140111da8  xor     rax, rsp
0x140111dab  mov     [rsp+0A8h+var_38], rax
0x140111db0  mov     ebp, [rdx+10h]
0x140111db3  mov     r14, rdx
0x140111db6  mov     r12, rcx
0x140111db9  test    ebp, ebp
0x140111dbb  jns     short loc_140111DEF
0x140111dbd  mov     rdi, [rdx+18h]
0x140111dc1  test    byte ptr [rdi+0CDh], 1
0x140111dc8  jz      short loc_140111DD4
0x140111dca  mov     eax, 0C00000BBh
0x140111dcf  jmp     loc_140112264
0x140111dd4  mov     r15, [rdi+20h]
0x140111dd8  mov     edx, 1
0x140111ddd  mov     rcx, [r15+10h]
0x140111de1  call    CarAcquireCacheAwareReference
0x140111de6  and     bpl, 1
0x140111dea  jmp     loc_140111ED3
0x140111def  lea     rbp, [rdx+40h]
0x140111df3  mov     rdx, [rbp+0]
0x140111df7  lea     rcx, TcpInetTransport
0x140111dfe  movzx   edx, word ptr [rdx]
0x140111e01  call    InetFindAndReferenceAf
0x140111e06  mov     r15, rax
0x140111e09  test    rax, rax
0x140111e0c  jnz     loc_140111ECE
0x140111e12  mov     rsi, [r14+28h]
0x140111e16  test    rsi, rsi
0x140111e19  jnz     short loc_140111E23
0x140111e1b  call    InetGetClientProcess
0x140111e20  mov     rsi, rax
0x140111e23  cmp     cs:dword_1402201D4, 0
0x140111e2a  jz      loc_140111EC4
0x140111e30  test    byte ptr cs:WPP_MAIN_CB.Reserved+4, 40h
0x140111e37  jz      loc_140111EC4
0x140111e3d  mov     rcx, [r14+20h]
0x140111e41  mov     [rsp+0A8h+var_48], rcx
0x140111e46  mov     rcx, rsi; Process
0x140111e49  mov     [rsp+0A8h+var_40], 0
0x140111e52  call    cs:__imp_PsGetProcessId
0x140111e59  nop     dword ptr [rax+rax+00h]
0x140111e5e  mov     rcx, [rbp+0]
0x140111e62  mov     rdi, rax
0x140111e65  movzx   ecx, word ptr [rcx]; af
0x140111e68  call    SOCKADDR_SIZE
0x140111e6d  mov     rcx, rsi
0x140111e70  movzx   ebx, al
0x140111e73  call    cs:__imp_PsGetProcessStartKey
0x140111e7a  nop     dword ptr [rax+rax+00h]
0x140111e7f  mov     [rsp+0A8h+var_58], rax
0x140111e84  xor     r9d, r9d
0x140111e87  mov     [rsp+0A8h+var_60], 0
0x140111e8f  lea     r8, [rsp+0A8h+var_48]
0x140111e94  mov     [rsp+0A8h+var_68], 0
0x140111e9c  lea     rdx, TCP_LISTENER_ACTIVATION_FAILED_AF_V1
0x140111ea3  mov     [rsp+0A8h+var_70], edi
0x140111ea7  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140111eae  mov     [rsp+0A8h+var_78], 0
0x140111eb6  mov     [rsp+0A8h+var_80], rbp
0x140111ebb  mov     [rsp+0A8h+var_88], ebx
0x140111ebf  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x140111ec4  mov     eax, 0C000A013h
0x140111ec9  jmp     loc_140112264
0x140111ece  xor     edi, edi
0x140111ed0  xor     bpl, bpl
0x140111ed3  mov     edx, 150h
0x140111ed8  mov     ecx, 40h ; '@'
0x140111edd  mov     r8d, 4C706354h
0x140111ee3  call    cs:__imp_ExAllocatePool2
0x140111eea  nop     dword ptr [rax+rax+00h]
0x140111eef  mov     rsi, rax
0x140111ef2  test    rax, rax
0x140111ef5  jnz     short loc_140111F20
0x140111ef7  mov     rcx, r15
0x140111efa  call    _InetDereferenceAf
0x140111eff  test    rdi, rdi
0x140111f02  jz      loc_14011225F
0x140111f08  test    bpl, bpl
0x140111f0b  jnz     loc_14011225F
0x140111f11  xor     edx, edx
0x140111f13  mov     rcx, rdi; SpinLock
0x140111f16  call    TcpCloseEndpoint
0x140111f1b  jmp     loc_14011225F
0x140111f20  xor     r8d, r8d; Flags
0x140111f23  lea     rcx, [rax+0E8h]; HashTable
0x140111f2a  lea     edx, [r8+6]; Shift
0x140111f2e  call    cs:__imp_RtlCreateHashTable
0x140111f35  nop     dword ptr [rax+rax+00h]
0x140111f3a  test    al, al
0x140111f3c  jnz     short loc_140111F70
0x140111f3e  mov     rcx, r15
0x140111f41  call    _InetDereferenceAf
0x140111f46  test    rdi, rdi
0x140111f49  jz      short loc_140111F5A
0x140111f4b  test    bpl, bpl
0x140111f4e  jnz     short loc_140111F5A
0x140111f50  xor     edx, edx
0x140111f52  mov     rcx, rdi; SpinLock
0x140111f55  call    TcpCloseEndpoint
0x140111f5a  xor     edx, edx; Tag
0x140111f5c  mov     rcx, rsi; P
0x140111f5f  call    cs:__imp_ExFreePoolWithTag
0x140111f66  nop     dword ptr [rax+rax+00h]
0x140111f6b  jmp     loc_14011225F
0x140111f70  mov     edx, 3
0x140111f75  mov     rcx, rsi
0x140111f78  call    TcpipTraceActivityIDStart
0x140111f7d  lea     rcx, [rsi+8]; SpinLock
0x140111f81  call    cs:__imp_KeInitializeSpinLock
0x140111f88  nop     dword ptr [rax+rax+00h]
0x140111f8d  mov     rcx, rsi; RunRef
0x140111f90  mov     dword ptr [rsi+10h], 0
0x140111f97  call    cs:__imp_ExInitializeRundownProtection
0x140111f9e  nop     dword ptr [rax+rax+00h]
0x140111fa3  mov     eax, 1
0x140111fa8  mov     [rsi+30h], r15
0x140111fac  mov     [rsi+18h], rax
0x140111fb0  mov     [rsi+70h], r15
0x140111fb4  mov     [rsi+28h], r12
0x140111fb8  lock xadd [r12+10h], rax
0x140111fbf  mov     r12d, 1
0x140111fc5  add     rax, r12
0x140111fc8  cmp     rax, r12
0x140111fcb  jg      short loc_140111FD4
0x140111fcd  lea     ecx, [r12+0Dh]
0x140111fd2  int     29h; Win8: RtlFailFast(ecx)
0x140111fd4  mov     rax, [r14+58h]
0x140111fd8  mov     [rsi+0D8h], rax
0x140111fdf  mov     rax, [r14+48h]
0x140111fe3  mov     [rsi+0E0h], rax
0x140111fea  test    rdi, rdi
0x140111fed  jnz     loc_140112078
0x140111ff3  mov     rax, [r14+28h]
0x140111ff7  test    rax, rax
0x140111ffa  jnz     short loc_140112001
0x140111ffc  call    InetGetClientProcess
0x140112001  mov     rcx, rax; Object
0x140112004  mov     [rsi+38h], rax
0x140112008  call    cs:__imp_ObfReferenceObject
0x14011200f  nop     dword ptr [rax+rax+00h]
0x140112014  mov     rdx, [r14+30h]
0x140112018  mov     rcx, [r14+28h]
0x14011201c  call    InetGetProcessTag
0x140112021  lea     rcx, [rsi+48h]
0x140112025  mov     [rsi+50h], rax
0x140112029  call    cs:__imp_KeQuerySystemTimePrecise
0x140112030  nop     dword ptr [rax+rax+00h]
0x140112035  lea     rdx, [rsi+0F0h]
0x14011203c  mov     rcx, r15
0x14011203f  call    TcpInitializeOptions
0x140112044  lea     rcx, [rsi+118h]
0x14011204b  xor     r8d, r8d
0x14011204e  xor     edx, edx
0x140112050  call    InetInitializeSs
0x140112055  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14011205b  test    eax, eax
0x14011205d  jz      loc_1401120FA
0x140112063  mov     rdx, [r14+20h]
0x140112067  test    rdx, rdx
0x14011206a  jz      loc_1401120FA
0x140112070  mov     r8d, 7
0x140112076  jmp     short loc_1401120F2
0x140112078  mov     rcx, [rdi+28h]; Object
0x14011207c  mov     [rsi+38h], rcx
0x140112080  call    cs:__imp_ObfReferenceObject
0x140112087  nop     dword ptr [rax+rax+00h]
0x14011208c  mov     rax, [rdi+48h]
0x140112090  lea     r8, [rdi+0D0h]
0x140112097  mov     [rsi+50h], rax
0x14011209b  lea     rcx, [rsi+118h]
0x1401120a2  mov     rax, [rdi+40h]
0x1401120a6  mov     [rsi+48h], rax
0x1401120aa  movups  xmm0, xmmword ptr [rdi+0A8h]
0x1401120b1  movups  xmmword ptr [rsi+0F0h], xmm0
0x1401120b8  movups  xmm1, xmmword ptr [rdi+0B8h]
0x1401120bf  movups  xmmword ptr [rsi+100h], xmm1
0x1401120c6  movsd   xmm0, qword ptr [rdi+0C8h]
0x1401120ce  movsd   qword ptr [rsi+110h], xmm0
0x1401120d6  mov     rdx, [rdi+20h]
0x1401120da  call    InetInitializeSs
0x1401120df  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1401120e5  test    eax, eax
0x1401120e7  jz      short loc_1401120FA
0x1401120e9  mov     r8d, 8
0x1401120ef  mov     rdx, rdi
0x1401120f2  mov     rcx, rsi
0x1401120f5  call    TcpipEtwTransferActivity
0x1401120fa  mov     eax, [r14+10h]
0x1401120fe  test    al, 2
0x140112100  jz      short loc_140112109
0x140112102  or      byte ptr [rsi+116h], 40h
0x140112109  mov     r15d, 1Ch
0x14011210f  test    rdi, rdi
0x140112112  jz      short loc_140112120
0x140112114  mov     eax, [rdi+10h]
0x140112117  test    r12b, al
0x14011211a  jz      short loc_140112120
0x14011211c  xor     ebx, ebx
0x14011211e  jmp     short loc_140112168
0x140112120  mov     r8d, 534C6354h
0x140112126  mov     rdx, r15
0x140112129  mov     ecx, 40h ; '@'
0x14011212e  call    cs:__imp_ExAllocatePool2
0x140112135  nop     dword ptr [rax+rax+00h]
0x14011213a  mov     rbx, rax
0x14011213d  test    rax, rax
0x140112140  jz      loc_140112241
0x140112146  mov     rcx, [r14+40h]
0x14011214a  movzx   edx, word ptr [rcx]
0x14011214d  mov     [rax], dx
0x140112150  mov     rdx, [r14+40h]
0x140112154  movzx   ecx, word ptr [rdx]; af
0x140112157  call    SOCKADDR_SIZE
0x14011215c  movzx   r8d, al; Size
0x140112160  mov     rcx, rbx; void *
0x140112163  call    memmove
0x140112168  mov     rax, [r14]
0x14011216b  mov     [rsi+0A0h], rax
0x140112172  mov     rax, [r14+8]
0x140112176  mov     [rsi+0A8h], rax
0x14011217d  mov     [rsi+0B8h], bpl
0x140112184  mov     [rsi+0B0h], rdi
0x14011218b  test    rdi, rdi
0x14011218e  jz      short loc_1401121C5
0x140112190  mov     rdx, r12
0x140112193  lock xadd [rdi+8], rdx
0x140112199  add     rdx, r12
0x14011219c  cmp     rdx, r12
0x14011219f  jg      short loc_1401121B1
0x1401121a1  mov     ecx, r15d; BugCheckCode
0x1401121a4  call    cs:__imp_KeBugCheck
0x1401121b1  mov     rcx, cs:EndpointReferenceHistory
0x1401121b8  test    rcx, rcx
0x1401121bb  jz      short loc_1401121C5
0x1401121bd  mov     r8, rdi
0x1401121c0  call    RhAppendHistory
0x1401121c5  mov     rcx, [r14+30h]; Object
0x1401121c9  mov     [rsi+0C0h], rcx
0x1401121d0  test    rcx, rcx
0x1401121d3  jz      short loc_1401121E1
0x1401121d5  call    cs:__imp_ObfReferenceObject
0x1401121dc  nop     dword ptr [rax+rax+00h]
0x1401121e1  mov     [rsi+0D0h], rbx
0x1401121e8  test    rdi, rdi
0x1401121eb  cmovz   rdi, r14
0x1401121ef  mov     rax, [rdi+38h]
0x1401121f3  mov     [rsi+40h], rax
0x1401121f7  call    cs:__imp_KeGetCurrentIrql
0x1401121fe  nop     dword ptr [rax+rax+00h]
0x140112203  test    al, al
0x140112205  jnz     short loc_140112220
0x140112207  lea     rcx, [rsi+98h]
0x14011220e  mov     qword ptr [rsi+98h], 0
0x140112219  call    TcpCreateListenerWorkQueueRoutine
0x14011221e  jmp     short loc_14011223A
0x140112220  lea     rdx, [rsi+98h]
0x140112227  lea     rcx, TcpCreateListenerWorkQueue
0x14011222e  call    cs:__imp_NetioInsertWorkQueue
0x140112235  nop     dword ptr [rax+rax+00h]
0x14011223a  mov     eax, 103h
0x14011223f  jmp     short loc_140112264
0x140112241  test    rdi, rdi
0x140112244  jz      short loc_140112255
0x140112246  test    bpl, bpl
0x140112249  jnz     short loc_140112255
0x14011224b  xor     edx, edx
0x14011224d  mov     rcx, rdi; SpinLock
0x140112250  call    TcpCloseEndpoint
0x140112255  xor     edx, edx
0x140112257  mov     rcx, rsi
0x14011225a  call    TcpCloseListener
0x14011225f  mov     eax, 0C0000017h
0x140112264  mov     rcx, [rsp+0A8h+var_38]
0x140112269  xor     rcx, rsp; StackCookie
0x14011226c  call    __security_check_cookie
0x140112271  lea     r11, [rsp+0A8h+var_28]
0x140112279  mov     rbx, [r11+40h]
0x14011227d  mov     rbp, [r11+48h]
0x140112281  mov     rsp, r11
0x140112284  pop     r15
0x140112286  pop     r14
0x140112288  pop     r12
0x14011228a  pop     rdi
0x14011228b  pop     rsi
0x14011228c  retn
```
