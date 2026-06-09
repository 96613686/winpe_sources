# UdpCreateEndpoint

- ea: `0x1400159b0`
- end: `0x140015cac`
- name: `UdpCreateEndpoint`
- size: `764`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID Object, PVOID, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011bc0`
- `0x140015950`

## callees

- `0x140010e38`
- `0x1400158e0`
- `0x1400159b0`
- `0x140017060`
- `0x140017ca0`
- `0x140018bd0`
- `0x140039860`
- `0x1400aebd8`
- `0x14010be68`
- `0x140115368`
- `0x14011e5a8`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x140015a5f`
- `ntoskrnl!KeInitializeSemaphore` at `0x140015a5f`
- `ntoskrnl!KeIsExecutingDpc` at `0x140015c7e`
- `ntoskrnl!KeIsExecutingDpc` at `0x140015c7e`
- `ntoskrnl!ObfReferenceObject` at `0x140015ad1`
- `ntoskrnl!ObfReferenceObject` at `0x140015af1`
- `ntoskrnl!ObfReferenceObject` at `0x140015ad1`
- `ntoskrnl!ObfReferenceObject` at `0x140015af1`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c1562`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c15fe`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c1562`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c15fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x140015b97`
- `ntoskrnl!KeGetCurrentIrql` at `0x140015b97`
- `ntoskrnl!PsGetProcessId` at `0x1401c1543`
- `ntoskrnl!PsGetProcessId` at `0x1401c15d9`
- `ntoskrnl!PsGetProcessId` at `0x1401c1543`
- `ntoskrnl!PsGetProcessId` at `0x1401c15d9`
- `ntoskrnl!KeInitializeSpinLock` at `0x140015a3b`
- `ntoskrnl!KeInitializeSpinLock` at `0x140015a3b`
- `ntoskrnl!ExAllocatePool2` at `0x140015a13`
- `ntoskrnl!ExAllocatePool2` at `0x140015a13`
- `NETIO!NetioInsertWorkQueue` at `0x140015c2a`
- `NETIO!NetioInsertWorkQueue` at `0x140015c2a`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1401c15ae`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1401c15ae`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140015b0a`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140015c9b`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140015b0a`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140015c9b`
- `cng!SystemPrng` at `0x140015a97`
- `cng!SystemPrng` at `0x140015a97`

## pseudocode

```c
__int64 __fastcall UdpCreateEndpoint(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        struct _KPROCESS *Object,
        PVOID a7,
        __int64 a8)
{
  struct _KPROCESS *v8; // rbp
  char v10; // si
  __int64 v13; // rdi
  __int64 Pool2; // rax
  __int64 v15; // rbx
  struct _KPROCESS *ClientProcess; // rax
  __int64 v17; // rcx
  unsigned int ThreadObjectCompartmentId; // eax
  char v19; // r14
  __int64 v20; // rax
  __int64 v21; // rax
  char v23; // bl
  char v24; // al
  unsigned __int8 ProcessId; // al
  __int64 v26; // rcx
  char v27; // si
  __int16 v28; // di
  char ProcessStartKey; // al
  __int128 v30; // [rsp+50h] [rbp-58h] BYREF

  v8 = Object;
  v10 = a4;
  v13 = InetFindAndReferenceAf(&UdpInetTransport, a4);
  if ( v13 )
  {
    Pool2 = ExAllocatePool2(64, 392, 1097884757);
    v15 = Pool2;
    if ( Pool2 )
    {
      TcpipTraceActivityIDStart(Pool2, 2);
      KeInitializeSpinLock((PKSPIN_LOCK)v15);
      *(_DWORD *)(v15 + 8) = 0;
      KeInitializeSemaphore((PRKSEMAPHORE)(v15 + 328), 1, 1);
      *(_QWORD *)(v15 + 16) = 1;
      *(_QWORD *)(v15 + 40) = v13;
      *(_QWORD *)(v15 + 112) = v13;
      *(_QWORD *)(v15 + 32) = a1;
      if ( !TcpipGlobalDisableRandomFlowLabel && *(_WORD *)(v13 + 24) == 23 )
        SystemPrng(v15 + 324, 4);
      if ( _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v15 + 32) + 16LL)) <= 1 )
        __fastfail(0xEu);
      *(_DWORD *)(v15 + 24) |= 0x10u;
      if ( Object )
        ClientProcess = Object;
      else
        ClientProcess = (struct _KPROCESS *)InetGetClientProcess();
      *(_QWORD *)(v15 + 48) = ClientProcess;
      ObfReferenceObject(ClientProcess);
      *(_QWORD *)(v15 + 56) = a7;
      if ( a7 )
        ObfReferenceObject(a7);
      v17 = *(_QWORD *)(v15 + 56);
      if ( v17 )
      {
        ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(v17);
      }
      else if ( (unsigned int)KeIsExecutingDpc() )
      {
        ThreadObjectCompartmentId = NdisGetProcessObjectCompartmentId(*(_QWORD *)(v15 + 48));
      }
      else
      {
        ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
      }
      v19 = ThreadObjectCompartmentId;
      v20 = InetFindAndReferenceCompartmentAf(*(_QWORD *)(v15 + 40), ThreadObjectCompartmentId);
      *(_QWORD *)(v15 + 80) = v20;
      if ( v20 )
      {
        *(_QWORD *)(v15 + 88) = InetGetProcessTag(Object, a7);
        *(_QWORD *)(v15 + 64) = a8;
        v21 = MEMORY[0xFFFFF78000000014];
        *(_DWORD *)(v15 + 24) |= 0x80u;
        *(_QWORD *)(v15 + 96) = v21;
        *(_OWORD *)(v15 + 232) = 0;
        *(_OWORD *)(v15 + 248) = 0;
        *(_QWORD *)(v15 + 264) = 0;
        *(_QWORD *)(v15 + 216) = a2;
        *(_QWORD *)(v15 + 224) = a3;
        if ( Microsoft_Windows_Networking_CorrelationEnabled && a5 )
          TcpipEtwTransferActivity(v15, a5, 2);
        if ( KeGetCurrentIrql() )
        {
          NetioInsertWorkQueue(UdpCreateEndpointWorkQueue, v15 + 208);
        }
        else
        {
          *(_QWORD *)(v15 + 208) = 0;
          UdpCreateEndpointWorkQueueRoutine(v15 + 208);
        }
        return 259;
      }
      else
      {
        if ( dword_1402201D4 )
        {
          v30 = 0;
          if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
          {
            ProcessId = (unsigned __int8)PsGetProcessId(*(PEPROCESS *)(v15 + 48));
            v26 = *(_QWORD *)(v15 + 40);
            v27 = ProcessId;
            v30 = (unsigned __int64)v15;
            v28 = *(_WORD *)(v26 + 24);
            ProcessStartKey = PsGetProcessStartKey(*(_QWORD *)(v15 + 48));
            McTemplateK0pqqqqx_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)UDP_CREATE_ENDPOINT_COMPARTMENT_FAILURE_V1,
              (unsigned int)&v30,
              v15,
              0,
              v27,
              v19,
              v28,
              ProcessStartKey);
          }
        }
        UdpCloseEndpoint(v15, 0);
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
    if ( !Object )
      v8 = (struct _KPROCESS *)InetGetClientProcess();
    if ( dword_1402201D4 )
    {
      v30 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
      {
        v23 = (unsigned __int8)PsGetProcessId(v8);
        v30 = 0u;
        v24 = PsGetProcessStartKey(v8);
        McTemplateK0pqqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)UDP_CREATE_ENDPOINT_AF_FAILURE_V1,
          (unsigned int)&v30,
          0,
          0,
          v23,
          0,
          v10,
          v24);
      }
    }
    return 3221266451LL;
  }
}

```

## disassembly

```asm
0x1400159b0  mov     [rsp+arg_8], rbx
0x1400159b5  push    rbp
0x1400159b6  push    rsi
0x1400159b7  push    rdi
0x1400159b8  push    r12
0x1400159ba  push    r13
0x1400159bc  push    r14
0x1400159be  push    r15
0x1400159c0  sub     rsp, 70h
0x1400159c4  mov     rax, cs:__security_cookie
0x1400159cb  xor     rax, rsp
0x1400159ce  mov     [rsp+0A8h+var_48], rax
0x1400159d3  mov     rbp, [rsp+0A8h+Object]
0x1400159db  mov     r13, rdx
0x1400159de  movzx   esi, r9w
0x1400159e2  mov     r14, rcx
0x1400159e5  movzx   edx, si
0x1400159e8  lea     rcx, UdpInetTransport
0x1400159ef  mov     r12, r8
0x1400159f2  call    InetFindAndReferenceAf
0x1400159f7  mov     rdi, rax
0x1400159fa  test    rax, rax
0x1400159fd  jz      loc_140015C68
0x140015a03  mov     edx, 188h
0x140015a08  mov     ecx, 40h ; '@'
0x140015a0d  mov     r8d, 41706455h
0x140015a13  call    cs:__imp_ExAllocatePool2
0x140015a1a  nop     dword ptr [rax+rax+00h]
0x140015a1f  mov     rbx, rax
0x140015a22  test    rax, rax
0x140015a25  jz      loc_140015BE5
0x140015a2b  mov     edx, 2
0x140015a30  mov     rcx, rax
0x140015a33  call    TcpipTraceActivityIDStart
0x140015a38  mov     rcx, rbx; SpinLock
0x140015a3b  call    cs:__imp_KeInitializeSpinLock
0x140015a42  nop     dword ptr [rax+rax+00h]
0x140015a47  mov     esi, 1
0x140015a4c  lea     rcx, [rbx+148h]; Semaphore
0x140015a53  xor     r15d, r15d
0x140015a56  mov     r8d, esi; Limit
0x140015a59  mov     edx, esi; Count
0x140015a5b  mov     [rbx+8], r15d
0x140015a5f  call    cs:__imp_KeInitializeSemaphore
0x140015a66  nop     dword ptr [rax+rax+00h]
0x140015a6b  mov     [rbx+10h], rsi
0x140015a6f  mov     [rbx+28h], rdi
0x140015a73  mov     [rbx+70h], rdi
0x140015a77  mov     [rbx+20h], r14
0x140015a7b  cmp     cs:TcpipGlobalDisableRandomFlowLabel, r15d
0x140015a82  jnz     short loc_140015AA3
0x140015a84  cmp     word ptr [rdi+18h], 17h
0x140015a89  jnz     short loc_140015AA3
0x140015a8b  lea     rcx, [rbx+144h]
0x140015a92  mov     edx, 4
0x140015a97  call    cs:__imp_SystemPrng
0x140015a9e  nop     dword ptr [rax+rax+00h]
0x140015aa3  mov     rax, [rbx+20h]
0x140015aa7  lock xadd [rax+10h], rsi
0x140015aad  inc     rsi
0x140015ab0  cmp     rsi, 1
0x140015ab4  jle     loc_140015C38
0x140015aba  or      dword ptr [rbx+18h], 10h
0x140015abe  test    rbp, rbp
0x140015ac1  jz      loc_140015C12
0x140015ac7  mov     rax, rbp
0x140015aca  mov     rcx, rax; Object
0x140015acd  mov     [rbx+30h], rax
0x140015ad1  call    cs:__imp_ObfReferenceObject
0x140015ad8  nop     dword ptr [rax+rax+00h]
0x140015add  mov     rdi, [rsp+0A8h+arg_30]
0x140015ae5  mov     [rbx+38h], rdi
0x140015ae9  test    rdi, rdi
0x140015aec  jz      short loc_140015AFD
0x140015aee  mov     rcx, rdi; Object
0x140015af1  call    cs:__imp_ObfReferenceObject
0x140015af8  nop     dword ptr [rax+rax+00h]
0x140015afd  mov     rcx, [rbx+38h]
0x140015b01  test    rcx, rcx
0x140015b04  jz      loc_140015C7E
0x140015b0a  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140015b11  nop     dword ptr [rax+rax+00h]
0x140015b16  mov     rcx, [rbx+28h]
0x140015b1a  mov     edx, eax
0x140015b1c  mov     r14d, eax
0x140015b1f  call    _InetFindAndReferenceCompartmentAf
0x140015b24  mov     [rbx+50h], rax
0x140015b28  test    rax, rax
0x140015b2b  jz      loc_140015BF4
0x140015b31  mov     rdx, rdi
0x140015b34  mov     rcx, rbp
0x140015b37  call    InetGetProcessTag
0x140015b3c  mov     [rbx+58h], rax
0x140015b40  xorps   xmm0, xmm0
0x140015b43  mov     rax, [rsp+0A8h+arg_38]
0x140015b4b  mov     [rbx+40h], rax
0x140015b4f  mov     rax, ds:0FFFFF78000000014h
0x140015b59  or      dword ptr [rbx+18h], 80h
0x140015b60  mov     [rbx+60h], rax
0x140015b64  xor     eax, eax
0x140015b66  movups  xmmword ptr [rbx+0E8h], xmm0
0x140015b6d  movups  xmmword ptr [rbx+0F8h], xmm0
0x140015b74  mov     [rbx+108h], rax
0x140015b7b  mov     [rbx+0D8h], r13
0x140015b82  mov     [rbx+0E0h], r12
0x140015b89  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140015b8f  test    eax, eax
0x140015b91  jnz     loc_140015C44
0x140015b97  call    cs:__imp_KeGetCurrentIrql
0x140015b9e  nop     dword ptr [rax+rax+00h]
0x140015ba3  test    al, al
0x140015ba5  jnz     short loc_140015C1C
0x140015ba7  lea     rcx, [rbx+0D0h]
0x140015bae  mov     [rbx+0D0h], r15
0x140015bb5  call    UdpCreateEndpointWorkQueueRoutine
0x140015bba  mov     eax, 103h
0x140015bbf  mov     rcx, [rsp+0A8h+var_48]
0x140015bc4  xor     rcx, rsp; StackCookie
0x140015bc7  call    __security_check_cookie
0x140015bcc  mov     rbx, [rsp+0A8h+arg_8]
0x140015bd4  add     rsp, 70h
0x140015bd8  pop     r15
0x140015bda  pop     r14
0x140015bdc  pop     r13
0x140015bde  pop     r12
0x140015be0  pop     rdi
0x140015be1  pop     rsi
0x140015be2  pop     rbp
0x140015be3  retn
0x140015be5  mov     rcx, rdi
0x140015be8  call    _InetDereferenceAf
0x140015bed  mov     eax, 0C0000017h
0x140015bf2  jmp     short loc_140015BBF
0x140015bf4  cmp     cs:dword_1402201D4, r15d
0x140015bfb  jnz     loc_1401C15C0
0x140015c01  xor     edx, edx
0x140015c03  mov     rcx, rbx
0x140015c06  call    UdpCloseEndpoint
0x140015c0b  mov     eax, 0C0000104h
0x140015c10  jmp     short loc_140015BBF
0x140015c12  call    InetGetClientProcess
0x140015c17  jmp     loc_140015ACA
0x140015c1c  lea     rdx, [rbx+0D0h]
0x140015c23  lea     rcx, UdpCreateEndpointWorkQueue
0x140015c2a  call    cs:__imp_NetioInsertWorkQueue
0x140015c31  nop     dword ptr [rax+rax+00h]
0x140015c36  jmp     short loc_140015BBA
0x140015c38  mov     ecx, 0Eh
0x140015c3d  int     29h; Win8: RtlFailFast(ecx)
0x140015c3f  jmp     loc_140015ABA
0x140015c44  mov     rdx, [rsp+0A8h+arg_20]
0x140015c4c  test    rdx, rdx
0x140015c4f  jz      loc_140015B97
0x140015c55  mov     r8d, 2
0x140015c5b  mov     rcx, rbx
0x140015c5e  call    TcpipEtwTransferActivity
0x140015c63  jmp     loc_140015B97
0x140015c68  test    rbp, rbp
0x140015c6b  jnz     loc_1401C1526
0x140015c71  call    InetGetClientProcess
0x140015c76  mov     rbp, rax
0x140015c79  jmp     loc_1401C1526
0x140015c7e  call    cs:__imp_KeIsExecutingDpc
0x140015c85  nop     dword ptr [rax+rax+00h]
0x140015c8a  test    eax, eax
0x140015c8c  jnz     loc_1401C15AA
0x140015c92  mov     rcx, gs:188h
0x140015c9b  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140015ca2  nop     dword ptr [rax+rax+00h]
0x140015ca7  jmp     loc_140015B16
0x1401c1526  cmp     cs:dword_1402201D4, 0
0x1401c152d  jz      short loc_1401C15A0
0x1401c152f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, 0
0x1401c1536  xorps   xmm0, xmm0
0x1401c1539  movups  [rsp+0A8h+var_58], xmm0
0x1401c153e  jge     short loc_1401C15A0
0x1401c1540  mov     rcx, rbp; Process
0x1401c1543  call    cs:__imp_PsGetProcessId
0x1401c154a  nop     dword ptr [rax+rax+00h]
0x1401c154f  xor     r15d, r15d
0x1401c1552  mov     rcx, rbp
0x1401c1555  mov     rbx, rax
0x1401c1558  mov     qword ptr [rsp+0A8h+var_58+8], r15
0x1401c155d  mov     qword ptr [rsp+0A8h+var_58], r15
0x1401c1562  call    cs:__imp_PsGetProcessStartKey
0x1401c1569  nop     dword ptr [rax+rax+00h]
0x1401c156e  mov     [rsp+0A8h+var_68], rax
0x1401c1573  xor     r9d, r9d
0x1401c1576  mov     [rsp+0A8h+var_70], esi
0x1401c157a  lea     r8, [rsp+0A8h+var_58]
0x1401c157f  mov     [rsp+0A8h+var_78], r15d
0x1401c1584  lea     rdx, UDP_CREATE_ENDPOINT_AF_FAILURE_V1
0x1401c158b  mov     [rsp+0A8h+var_80], ebx
0x1401c158f  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c1596  mov     [rsp+0A8h+var_88], r15d
0x1401c159b  call    McTemplateK0pqqqqx_EtwWriteTransfer
0x1401c15a0  mov     eax, 0C000A013h
0x1401c15a5  jmp     loc_140015BBF
0x1401c15aa  mov     rcx, [rbx+30h]
0x1401c15ae  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x1401c15b5  nop     dword ptr [rax+rax+00h]
0x1401c15ba  nop
0x1401c15bb  jmp     loc_140015B16
0x1401c15c0  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, r15b
0x1401c15c7  xorps   xmm0, xmm0
0x1401c15ca  movups  [rsp+0A8h+var_58], xmm0
0x1401c15cf  jge     loc_140015C01
0x1401c15d5  mov     rcx, [rbx+30h]; Process
0x1401c15d9  call    cs:__imp_PsGetProcessId
0x1401c15e0  nop     dword ptr [rax+rax+00h]
0x1401c15e5  mov     rcx, [rbx+28h]
0x1401c15e9  mov     rsi, rax
0x1401c15ec  mov     qword ptr [rsp+0A8h+var_58+8], r15
0x1401c15f1  mov     qword ptr [rsp+0A8h+var_58], rbx
0x1401c15f6  movzx   edi, word ptr [rcx+18h]
0x1401c15fa  mov     rcx, [rbx+30h]
0x1401c15fe  call    cs:__imp_PsGetProcessStartKey
0x1401c1605  nop     dword ptr [rax+rax+00h]
0x1401c160a  mov     [rsp+0A8h+var_68], rax
0x1401c160f  mov     r9, rbx
0x1401c1612  mov     [rsp+0A8h+var_70], edi
0x1401c1616  lea     r8, [rsp+0A8h+var_58]
0x1401c161b  mov     [rsp+0A8h+var_78], r14d
0x1401c1620  lea     rdx, UDP_CREATE_ENDPOINT_COMPARTMENT_FAILURE_V1
0x1401c1627  mov     [rsp+0A8h+var_80], esi
0x1401c162b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c1632  mov     [rsp+0A8h+var_88], r15d
0x1401c1637  call    McTemplateK0pqqqqx_EtwWriteTransfer
0x1401c163c  nop
0x1401c163d  jmp     loc_140015C01
```
