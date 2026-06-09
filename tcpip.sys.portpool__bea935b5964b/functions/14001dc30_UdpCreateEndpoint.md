# UdpCreateEndpoint

- ea: `0x14001dc30`
- end: `0x14001df2c`
- name: `UdpCreateEndpoint`
- size: `764`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16, __int64, struct _KPROCESS *Object, PVOID, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002aa0`
- `0x14001dbd0`

## callees

- `0x140018578`
- `0x14001db20`
- `0x14001dc30`
- `0x14001df40`
- `0x14001dfa8`
- `0x14001e0d8`
- `0x14001ebd0`
- `0x140022240`
- `0x140023800`
- `0x140049760`
- `0x140128dd8`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x14001dcdf`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001dcdf`
- `ntoskrnl!KeIsExecutingDpc` at `0x14001defe`
- `ntoskrnl!KeIsExecutingDpc` at `0x14001defe`
- `ntoskrnl!ObfReferenceObject` at `0x14001dd51`
- `ntoskrnl!ObfReferenceObject` at `0x14001dd71`
- `ntoskrnl!ObfReferenceObject` at `0x14001dd51`
- `ntoskrnl!ObfReferenceObject` at `0x14001dd71`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c3a96`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c3b32`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c3a96`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c3b32`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001de17`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001de17`
- `ntoskrnl!PsGetProcessId` at `0x1401c3a77`
- `ntoskrnl!PsGetProcessId` at `0x1401c3b0d`
- `ntoskrnl!PsGetProcessId` at `0x1401c3a77`
- `ntoskrnl!PsGetProcessId` at `0x1401c3b0d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001dcbb`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001dcbb`
- `ntoskrnl!ExAllocatePool2` at `0x14001dc93`
- `ntoskrnl!ExAllocatePool2` at `0x14001dc93`
- `NETIO!NetioInsertWorkQueue` at `0x14001deaa`
- `NETIO!NetioInsertWorkQueue` at `0x14001deaa`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1401c3ae2`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x1401c3ae2`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001dd8a`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001df1b`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001dd8a`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14001df1b`
- `cng!SystemPrng` at `0x14001dd17`
- `cng!SystemPrng` at `0x14001dd17`

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
        if ( dword_1402241D4 )
        {
          v30 = 0;
          if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
    if ( dword_1402241D4 )
    {
      v30 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
0x14001dc30  mov     [rsp+arg_8], rbx
0x14001dc35  push    rbp
0x14001dc36  push    rsi
0x14001dc37  push    rdi
0x14001dc38  push    r12
0x14001dc3a  push    r13
0x14001dc3c  push    r14
0x14001dc3e  push    r15
0x14001dc40  sub     rsp, 70h
0x14001dc44  mov     rax, cs:__security_cookie
0x14001dc4b  xor     rax, rsp
0x14001dc4e  mov     [rsp+0A8h+var_48], rax
0x14001dc53  mov     rbp, [rsp+0A8h+Object]
0x14001dc5b  mov     r13, rdx
0x14001dc5e  movzx   esi, r9w
0x14001dc62  mov     r14, rcx
0x14001dc65  movzx   edx, si
0x14001dc68  lea     rcx, UdpInetTransport
0x14001dc6f  mov     r12, r8
0x14001dc72  call    InetFindAndReferenceAf
0x14001dc77  mov     rdi, rax
0x14001dc7a  test    rax, rax
0x14001dc7d  jz      loc_14001DEE8
0x14001dc83  mov     edx, 188h
0x14001dc88  mov     ecx, 40h ; '@'
0x14001dc8d  mov     r8d, 41706455h
0x14001dc93  call    cs:__imp_ExAllocatePool2
0x14001dc9a  nop     dword ptr [rax+rax+00h]
0x14001dc9f  mov     rbx, rax
0x14001dca2  test    rax, rax
0x14001dca5  jz      loc_14001DE65
0x14001dcab  mov     edx, 2
0x14001dcb0  mov     rcx, rax
0x14001dcb3  call    TcpipTraceActivityIDStart
0x14001dcb8  mov     rcx, rbx; SpinLock
0x14001dcbb  call    cs:__imp_KeInitializeSpinLock
0x14001dcc2  nop     dword ptr [rax+rax+00h]
0x14001dcc7  mov     esi, 1
0x14001dccc  lea     rcx, [rbx+148h]; Semaphore
0x14001dcd3  xor     r15d, r15d
0x14001dcd6  mov     r8d, esi; Limit
0x14001dcd9  mov     edx, esi; Count
0x14001dcdb  mov     [rbx+8], r15d
0x14001dcdf  call    cs:__imp_KeInitializeSemaphore
0x14001dce6  nop     dword ptr [rax+rax+00h]
0x14001dceb  mov     [rbx+10h], rsi
0x14001dcef  mov     [rbx+28h], rdi
0x14001dcf3  mov     [rbx+70h], rdi
0x14001dcf7  mov     [rbx+20h], r14
0x14001dcfb  cmp     cs:TcpipGlobalDisableRandomFlowLabel, r15d
0x14001dd02  jnz     short loc_14001DD23
0x14001dd04  cmp     word ptr [rdi+18h], 17h
0x14001dd09  jnz     short loc_14001DD23
0x14001dd0b  lea     rcx, [rbx+144h]
0x14001dd12  mov     edx, 4
0x14001dd17  call    cs:__imp_SystemPrng
0x14001dd1e  nop     dword ptr [rax+rax+00h]
0x14001dd23  mov     rax, [rbx+20h]
0x14001dd27  lock xadd [rax+10h], rsi
0x14001dd2d  inc     rsi
0x14001dd30  cmp     rsi, 1
0x14001dd34  jle     loc_14001DEB8
0x14001dd3a  or      dword ptr [rbx+18h], 10h
0x14001dd3e  test    rbp, rbp
0x14001dd41  jz      loc_14001DE92
0x14001dd47  mov     rax, rbp
0x14001dd4a  mov     rcx, rax; Object
0x14001dd4d  mov     [rbx+30h], rax
0x14001dd51  call    cs:__imp_ObfReferenceObject
0x14001dd58  nop     dword ptr [rax+rax+00h]
0x14001dd5d  mov     rdi, [rsp+0A8h+arg_30]
0x14001dd65  mov     [rbx+38h], rdi
0x14001dd69  test    rdi, rdi
0x14001dd6c  jz      short loc_14001DD7D
0x14001dd6e  mov     rcx, rdi; Object
0x14001dd71  call    cs:__imp_ObfReferenceObject
0x14001dd78  nop     dword ptr [rax+rax+00h]
0x14001dd7d  mov     rcx, [rbx+38h]
0x14001dd81  test    rcx, rcx
0x14001dd84  jz      loc_14001DEFE
0x14001dd8a  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14001dd91  nop     dword ptr [rax+rax+00h]
0x14001dd96  mov     rcx, [rbx+28h]
0x14001dd9a  mov     edx, eax
0x14001dd9c  mov     r14d, eax
0x14001dd9f  call    _InetFindAndReferenceCompartmentAf
0x14001dda4  mov     [rbx+50h], rax
0x14001dda8  test    rax, rax
0x14001ddab  jz      loc_14001DE74
0x14001ddb1  mov     rdx, rdi
0x14001ddb4  mov     rcx, rbp
0x14001ddb7  call    InetGetProcessTag
0x14001ddbc  mov     [rbx+58h], rax
0x14001ddc0  xorps   xmm0, xmm0
0x14001ddc3  mov     rax, [rsp+0A8h+arg_38]
0x14001ddcb  mov     [rbx+40h], rax
0x14001ddcf  mov     rax, ds:0FFFFF78000000014h
0x14001ddd9  or      dword ptr [rbx+18h], 80h
0x14001dde0  mov     [rbx+60h], rax
0x14001dde4  xor     eax, eax
0x14001dde6  movups  xmmword ptr [rbx+0E8h], xmm0
0x14001dded  movups  xmmword ptr [rbx+0F8h], xmm0
0x14001ddf4  mov     [rbx+108h], rax
0x14001ddfb  mov     [rbx+0D8h], r13
0x14001de02  mov     [rbx+0E0h], r12
0x14001de09  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14001de0f  test    eax, eax
0x14001de11  jnz     loc_14001DEC4
0x14001de17  call    cs:__imp_KeGetCurrentIrql
0x14001de1e  nop     dword ptr [rax+rax+00h]
0x14001de23  test    al, al
0x14001de25  jnz     short loc_14001DE9C
0x14001de27  lea     rcx, [rbx+0D0h]
0x14001de2e  mov     [rbx+0D0h], r15
0x14001de35  call    UdpCreateEndpointWorkQueueRoutine
0x14001de3a  mov     eax, 103h
0x14001de3f  mov     rcx, [rsp+0A8h+var_48]
0x14001de44  xor     rcx, rsp; StackCookie
0x14001de47  call    __security_check_cookie
0x14001de4c  mov     rbx, [rsp+0A8h+arg_8]
0x14001de54  add     rsp, 70h
0x14001de58  pop     r15
0x14001de5a  pop     r14
0x14001de5c  pop     r13
0x14001de5e  pop     r12
0x14001de60  pop     rdi
0x14001de61  pop     rsi
0x14001de62  pop     rbp
0x14001de63  retn
0x14001de65  mov     rcx, rdi
0x14001de68  call    _InetDereferenceAf
0x14001de6d  mov     eax, 0C0000017h
0x14001de72  jmp     short loc_14001DE3F
0x14001de74  cmp     cs:dword_1402241D4, r15d
0x14001de7b  jnz     loc_1401C3AF4
0x14001de81  xor     edx, edx
0x14001de83  mov     rcx, rbx
0x14001de86  call    UdpCloseEndpoint
0x14001de8b  mov     eax, 0C0000104h
0x14001de90  jmp     short loc_14001DE3F
0x14001de92  call    InetGetClientProcess
0x14001de97  jmp     loc_14001DD4A
0x14001de9c  lea     rdx, [rbx+0D0h]
0x14001dea3  lea     rcx, UdpCreateEndpointWorkQueue
0x14001deaa  call    cs:__imp_NetioInsertWorkQueue
0x14001deb1  nop     dword ptr [rax+rax+00h]
0x14001deb6  jmp     short loc_14001DE3A
0x14001deb8  mov     ecx, 0Eh
0x14001debd  int     29h; Win8: RtlFailFast(ecx)
0x14001debf  jmp     loc_14001DD3A
0x14001dec4  mov     rdx, [rsp+0A8h+arg_20]
0x14001decc  test    rdx, rdx
0x14001decf  jz      loc_14001DE17
0x14001ded5  mov     r8d, 2
0x14001dedb  mov     rcx, rbx
0x14001dede  call    TcpipEtwTransferActivity
0x14001dee3  jmp     loc_14001DE17
0x14001dee8  test    rbp, rbp
0x14001deeb  jnz     loc_1401C3A5A
0x14001def1  call    InetGetClientProcess
0x14001def6  mov     rbp, rax
0x14001def9  jmp     loc_1401C3A5A
0x14001defe  call    cs:__imp_KeIsExecutingDpc
0x14001df05  nop     dword ptr [rax+rax+00h]
0x14001df0a  test    eax, eax
0x14001df0c  jnz     loc_1401C3ADE
0x14001df12  mov     rcx, gs:188h
0x14001df1b  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14001df22  nop     dword ptr [rax+rax+00h]
0x14001df27  jmp     loc_14001DD96
0x1401c3a5a  cmp     cs:dword_1402241D4, 0
0x1401c3a61  jz      short loc_1401C3AD4
0x1401c3a63  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x1401c3a6a  xorps   xmm0, xmm0
0x1401c3a6d  movups  [rsp+0A8h+var_58], xmm0
0x1401c3a72  jge     short loc_1401C3AD4
0x1401c3a74  mov     rcx, rbp; Process
0x1401c3a77  call    cs:__imp_PsGetProcessId
0x1401c3a7e  nop     dword ptr [rax+rax+00h]
0x1401c3a83  xor     r15d, r15d
0x1401c3a86  mov     rcx, rbp
0x1401c3a89  mov     rbx, rax
0x1401c3a8c  mov     qword ptr [rsp+0A8h+var_58+8], r15
0x1401c3a91  mov     qword ptr [rsp+0A8h+var_58], r15
0x1401c3a96  call    cs:__imp_PsGetProcessStartKey
0x1401c3a9d  nop     dword ptr [rax+rax+00h]
0x1401c3aa2  mov     [rsp+0A8h+var_68], rax
0x1401c3aa7  xor     r9d, r9d
0x1401c3aaa  mov     [rsp+0A8h+var_70], esi
0x1401c3aae  lea     r8, [rsp+0A8h+var_58]
0x1401c3ab3  mov     [rsp+0A8h+var_78], r15d
0x1401c3ab8  lea     rdx, UDP_CREATE_ENDPOINT_AF_FAILURE_V1
0x1401c3abf  mov     [rsp+0A8h+var_80], ebx
0x1401c3ac3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c3aca  mov     [rsp+0A8h+var_88], r15d
0x1401c3acf  call    McTemplateK0pqqqqx_EtwWriteTransfer
0x1401c3ad4  mov     eax, 0C000A013h
0x1401c3ad9  jmp     loc_14001DE3F
0x1401c3ade  mov     rcx, [rbx+30h]
0x1401c3ae2  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x1401c3ae9  nop     dword ptr [rax+rax+00h]
0x1401c3aee  nop
0x1401c3aef  jmp     loc_14001DD96
0x1401c3af4  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, r15b
0x1401c3afb  xorps   xmm0, xmm0
0x1401c3afe  movups  [rsp+0A8h+var_58], xmm0
0x1401c3b03  jge     loc_14001DE81
0x1401c3b09  mov     rcx, [rbx+30h]; Process
0x1401c3b0d  call    cs:__imp_PsGetProcessId
0x1401c3b14  nop     dword ptr [rax+rax+00h]
0x1401c3b19  mov     rcx, [rbx+28h]
0x1401c3b1d  mov     rsi, rax
0x1401c3b20  mov     qword ptr [rsp+0A8h+var_58+8], r15
0x1401c3b25  mov     qword ptr [rsp+0A8h+var_58], rbx
0x1401c3b2a  movzx   edi, word ptr [rcx+18h]
0x1401c3b2e  mov     rcx, [rbx+30h]
0x1401c3b32  call    cs:__imp_PsGetProcessStartKey
0x1401c3b39  nop     dword ptr [rax+rax+00h]
0x1401c3b3e  mov     [rsp+0A8h+var_68], rax
0x1401c3b43  mov     r9, rbx
0x1401c3b46  mov     [rsp+0A8h+var_70], edi
0x1401c3b4a  lea     r8, [rsp+0A8h+var_58]
0x1401c3b4f  mov     [rsp+0A8h+var_78], r14d
0x1401c3b54  lea     rdx, UDP_CREATE_ENDPOINT_COMPARTMENT_FAILURE_V1
0x1401c3b5b  mov     [rsp+0A8h+var_80], esi
0x1401c3b5f  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c3b66  mov     [rsp+0A8h+var_88], r15d
0x1401c3b6b  call    McTemplateK0pqqqqx_EtwWriteTransfer
0x1401c3b70  nop
0x1401c3b71  jmp     loc_14001DE81
```
