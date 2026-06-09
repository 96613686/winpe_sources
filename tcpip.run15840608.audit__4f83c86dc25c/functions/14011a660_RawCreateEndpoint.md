# RawCreateEndpoint

- ea: `0x14011a660`
- end: `0x14011aafa`
- name: `RawCreateEndpoint`
- size: `1178`
- prototype: `__int64 __fastcall(int, int, int, int, int, PEPROCESS Process, PVOID Object)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14010c8bc`
- `0x14011a620`

## callees

- `0x140022240`
- `0x140023800`
- `0x140049760`
- `0x1400defe0`
- `0x14010a69c`
- `0x14010c9b0`
- `0x14010caf8`
- `0x14011a660`
- `0x140128dd8`
- `0x140131ee0`
- `0x140158bf0`
- `0x14016aa3c`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x14011a8f9`
- `ntoskrnl!KeInitializeSemaphore` at `0x14011a8f9`
- `ntoskrnl!KeIsExecutingDpc` at `0x14011a981`
- `ntoskrnl!KeIsExecutingDpc` at `0x14011a981`
- `ntoskrnl!ObfReferenceObject` at `0x14011a943`
- `ntoskrnl!ObfReferenceObject` at `0x14011a95e`
- `ntoskrnl!ObfReferenceObject` at `0x14011a943`
- `ntoskrnl!ObfReferenceObject` at `0x14011a95e`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011a7d0`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011a843`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011aa0d`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011a7d0`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011a843`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011aa0d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14011aa8e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14011aa8e`
- `ntoskrnl!PsGetProcessId` at `0x14011a7ae`
- `ntoskrnl!PsGetProcessId` at `0x14011a829`
- `ntoskrnl!PsGetProcessId` at `0x14011a9e6`
- `ntoskrnl!PsGetProcessId` at `0x14011a7ae`
- `ntoskrnl!PsGetProcessId` at `0x14011a829`
- `ntoskrnl!PsGetProcessId` at `0x14011a9e6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14011a8d6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14011a8d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011a773`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011a773`
- `ntoskrnl!ExAllocatePool2` at `0x14011a8ad`
- `ntoskrnl!ExAllocatePool2` at `0x14011a8ad`
- `NETIO!NetioInsertWorkQueue` at `0x14011aac1`
- `NETIO!NetioInsertWorkQueue` at `0x14011aac1`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14011a9a0`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x14011a9a0`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14011a973`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14011a973`

## pseudocode

```c
__int64 __fastcall RawCreateEndpoint(
        KSPIN_LOCK a1,
        KSPIN_LOCK a2,
        KSPIN_LOCK a3,
        unsigned __int16 a4,
        unsigned int a5,
        PEPROCESS Process,
        PVOID Object)
{
  struct _KPROCESS *ClientProcess; // rdi
  _QWORD *AppNameFromProcess; // rbx
  int v13; // r8d
  char ProcessId; // bl
  char ProcessStartKey; // al
  __int64 v16; // rbx
  char v17; // bl
  char v18; // al
  KSPIN_LOCK *Pool2; // rax
  KSPIN_LOCK *v21; // r14
  struct _KTHREAD *CurrentThread; // rcx
  unsigned int ThreadObjectCompartmentId; // eax
  char v24; // r15
  __int64 v25; // rax
  unsigned __int8 v26; // al
  KSPIN_LOCK v27; // rcx
  char v28; // si
  int v29; // edi
  __int16 v30; // bx
  char v31; // al
  __int64 v32; // [rsp+60h] [rbp-81h] BYREF
  __int128 v33; // [rsp+68h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+80h] [rbp-61h] BYREF
  __int64 *v35; // [rsp+A0h] [rbp-41h]
  __int64 v36; // [rsp+A8h] [rbp-39h]
  _DWORD *v37; // [rsp+B0h] [rbp-31h]
  __int64 v38; // [rsp+B8h] [rbp-29h]
  __int64 v39; // [rsp+C0h] [rbp-21h]
  _DWORD v40[2]; // [rsp+C8h] [rbp-19h] BYREF
  __int128 *v41; // [rsp+D0h] [rbp-11h]
  __int64 v42; // [rsp+D8h] [rbp-9h]

  ClientProcess = Process;
  if ( !Process )
    ClientProcess = (struct _KPROCESS *)InetGetClientProcess();
  if ( LOBYTE(WPP_MAIN_CB.DeviceType) )
  {
    AppNameFromProcess = (_QWORD *)TcpipGetAppNameFromProcess(ClientProcess);
    if ( AppNameFromProcess )
    {
      if ( (unsigned int)dword_1402241F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1402241F8, 0x400000000000LL) )
      {
        v32 = 1;
        v35 = &v32;
        v36 = 8;
        v37 = v40;
        v39 = AppNameFromProcess[1];
        v40[0] = *(unsigned __int16 *)AppNameFromProcess;
        v41 = &v33;
        v38 = 2;
        v40[1] = 0;
        *(_QWORD *)&v33 = 0x2000000;
        v42 = 8;
        tlgWriteAgg((int)&dword_1402241F8, (int)&byte_1401F6AF7, v13, 6, &v34);
      }
      ExFreePoolWithTag(AppNameFromProcess, 0x4E416354u);
    }
  }
  if ( a5 >= 0x100 )
  {
    if ( dword_1402241D4 )
    {
      v33 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId(ClientProcess);
        v33 = 0u;
        ProcessStartKey = PsGetProcessStartKey(ClientProcess);
        McTemplateK0pqqqqxqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)RAW_CREATE_ENDPOINT_FAILURE,
          (unsigned int)&v33,
          0,
          a4,
          a5,
          1,
          ProcessId,
          ProcessStartKey,
          4,
          19);
      }
    }
    return 3221266451LL;
  }
  v16 = InetFindAndReferenceAf(&RawInetTransport, a4);
  if ( !v16 )
  {
    if ( dword_1402241D4 )
    {
      v33 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        v17 = (unsigned __int8)PsGetProcessId(ClientProcess);
        v33 = 0u;
        v18 = PsGetProcessStartKey(ClientProcess);
        McTemplateK0pqqqqxqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)RAW_CREATE_ENDPOINT_FAILURE,
          (unsigned int)&v33,
          0,
          a4,
          a5,
          1,
          v17,
          v18,
          1,
          19);
      }
    }
    return 3221266451LL;
  }
  Pool2 = (KSPIN_LOCK *)ExAllocatePool2(64, 256, 1165451602);
  v21 = Pool2;
  if ( !Pool2 )
  {
    InetDereferenceAf(v16);
    return 3221225495LL;
  }
  KeInitializeSpinLock(Pool2);
  *((_DWORD *)v21 + 2) = 0;
  KeInitializeSemaphore((PRKSEMAPHORE)v21 + 7, 1, 1);
  v21[7] = v16;
  *((_DWORD *)v21 + 4) = 1;
  v21[6] = a1;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 16)) <= 1 )
    __fastfail(0xEu);
  *((_DWORD *)v21 + 16) = a5;
  v21[5] = (KSPIN_LOCK)(v21 + 4);
  v21[4] = (KSPIN_LOCK)(v21 + 4);
  v21[9] = (KSPIN_LOCK)ClientProcess;
  ObfReferenceObject(ClientProcess);
  v21[10] = (KSPIN_LOCK)Object;
  if ( Object )
    ObfReferenceObject(Object);
  CurrentThread = (struct _KTHREAD *)v21[10];
  if ( CurrentThread )
    goto LABEL_25;
  if ( !(unsigned int)KeIsExecutingDpc() )
  {
    CurrentThread = KeGetCurrentThread();
LABEL_25:
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(CurrentThread);
    goto LABEL_29;
  }
  ThreadObjectCompartmentId = NdisGetProcessObjectCompartmentId(v21[9]);
LABEL_29:
  v24 = ThreadObjectCompartmentId;
  v25 = InetFindAndReferenceCompartmentAf(v21[7], ThreadObjectCompartmentId);
  v21[12] = v25;
  if ( v25 )
  {
    *((_DWORD *)v21 + 6) |= 0x20u;
    InetInitializeSs(v21 + 21, 0, 0);
    v21[19] = a2;
    v21[20] = a3;
    if ( KeGetCurrentIrql() )
    {
      NetioInsertWorkQueue(qword_140228720, v21 + 18);
    }
    else
    {
      v21[18] = 0;
      RawCreateEndpointWorkQueueRoutine(v21 + 18);
    }
    return 259;
  }
  else
  {
    if ( dword_1402241D4 )
    {
      v33 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        v26 = (unsigned __int8)PsGetProcessId((PEPROCESS)v21[9]);
        v27 = v21[7];
        v28 = v26;
        v29 = *((_DWORD *)v21 + 16);
        v33 = (unsigned __int64)v21;
        v30 = *(_WORD *)(v27 + 24);
        v31 = PsGetProcessStartKey(v21[9]);
        McTemplateK0pqqqqxqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)RAW_CREATE_ENDPOINT_FAILURE,
          (unsigned int)&v33,
          (_DWORD)v21,
          v30,
          v29,
          v24,
          v28,
          v31,
          2,
          4);
      }
    }
    RawCloseEndpoint(v21, 0);
    return 3221225732LL;
  }
}

```

## disassembly

```asm
0x14011a660  mov     [rsp-8+arg_8], rbx
0x14011a665  push    rbp
0x14011a666  push    rsi
0x14011a667  push    rdi
0x14011a668  push    r12
0x14011a66a  push    r13
0x14011a66c  push    r14
0x14011a66e  push    r15
0x14011a670  lea     rbp, [rsp-0Fh]
0x14011a675  sub     rsp, 0F0h
0x14011a67c  mov     rax, cs:__security_cookie
0x14011a683  xor     rax, rsp
0x14011a686  mov     [rbp+3Fh+var_40], rax
0x14011a68a  mov     rdi, [rbp+3Fh+Process]
0x14011a68e  mov     r12, r8
0x14011a691  movzx   r14d, r9w
0x14011a695  mov     r13, rdx
0x14011a698  mov     r15, rcx
0x14011a69b  test    rdi, rdi
0x14011a69e  jnz     short loc_14011A6A8
0x14011a6a0  call    InetGetClientProcess
0x14011a6a5  mov     rdi, rax
0x14011a6a8  cmp     byte ptr cs:WPP_MAIN_CB.DeviceType, 0
0x14011a6af  jz      loc_14011A77F
0x14011a6b5  mov     rcx, rdi
0x14011a6b8  call    TcpipGetAppNameFromProcess
0x14011a6bd  mov     rbx, rax
0x14011a6c0  test    rax, rax
0x14011a6c3  jz      loc_14011A77F
0x14011a6c9  mov     ecx, cs:dword_1402241F8
0x14011a6cf  cmp     ecx, 5
0x14011a6d2  jbe     loc_14011A76B
0x14011a6d8  mov     rdx, 400000000000h
0x14011a6e2  lea     rcx, dword_1402241F8
0x14011a6e9  call    _tlgKeywordOn
0x14011a6ee  test    al, al
0x14011a6f0  jz      short loc_14011A76B
0x14011a6f2  lea     rax, [rsp+120h+var_C0]
0x14011a6f7  mov     [rsp+120h+var_C0], 1
0x14011a700  mov     [rbp+3Fh+var_80], rax
0x14011a704  lea     rdx, byte_1401F6AF7; int
0x14011a70b  lea     rax, [rbp+3Fh+var_58]
0x14011a70f  mov     [rbp+3Fh+var_78], 8
0x14011a717  mov     [rbp+3Fh+var_70], rax
0x14011a71b  lea     rcx, dword_1402241F8; int
0x14011a722  mov     rax, [rbx+8]
0x14011a726  mov     r9d, 6; int
0x14011a72c  mov     [rbp+3Fh+var_60], rax
0x14011a730  movzx   eax, word ptr [rbx]
0x14011a733  mov     [rbp+3Fh+var_58], eax
0x14011a736  lea     rax, [rbp+3Fh+var_B8]
0x14011a73a  mov     [rbp+3Fh+var_50], rax
0x14011a73e  lea     rax, [rbp+3Fh+var_A0]
0x14011a742  mov     [rsp+120h+var_100], rax; PEVENT_DATA_DESCRIPTOR
0x14011a747  mov     [rbp+3Fh+var_68], 2
0x14011a74f  mov     [rbp+3Fh+var_54], 0
0x14011a756  mov     qword ptr [rbp+3Fh+var_B8], 2000000h
0x14011a75e  mov     [rbp+3Fh+var_48], 8
0x14011a766  call    _tlgWriteAgg
0x14011a76b  mov     edx, 4E416354h; Tag
0x14011a770  mov     rcx, rbx; P
0x14011a773  call    cs:__imp_ExFreePoolWithTag
0x14011a77a  nop     dword ptr [rax+rax+00h]
0x14011a77f  mov     esi, [rbp+3Fh+arg_20]
0x14011a782  cmp     esi, 100h
0x14011a788  jb      short loc_14011A7EE
0x14011a78a  cmp     cs:dword_1402241D4, 0
0x14011a791  jz      loc_14011A893
0x14011a797  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x14011a79e  xorps   xmm0, xmm0
0x14011a7a1  movups  [rbp+3Fh+var_B8], xmm0
0x14011a7a5  jge     loc_14011A893
0x14011a7ab  mov     rcx, rdi; Process
0x14011a7ae  call    cs:__imp_PsGetProcessId
0x14011a7b5  nop     dword ptr [rax+rax+00h]
0x14011a7ba  mov     rcx, rdi
0x14011a7bd  mov     qword ptr [rbp+3Fh+var_B8+8], 0
0x14011a7c5  mov     rbx, rax
0x14011a7c8  mov     qword ptr [rbp+3Fh+var_B8], 0
0x14011a7d0  call    cs:__imp_PsGetProcessStartKey
0x14011a7d7  nop     dword ptr [rax+rax+00h]
0x14011a7dc  mov     [rsp+120h+var_D0], 0C000A013h
0x14011a7e4  mov     [rsp+120h+var_D8], 4
0x14011a7ec  jmp     short loc_14011A85F
0x14011a7ee  movzx   edx, r14w
0x14011a7f2  lea     rcx, RawInetTransport
0x14011a7f9  call    InetFindAndReferenceAf
0x14011a7fe  mov     rbx, rax
0x14011a801  test    rax, rax
0x14011a804  jnz     loc_14011A89D
0x14011a80a  xor     r15d, r15d
0x14011a80d  cmp     cs:dword_1402241D4, r15d
0x14011a814  jz      short loc_14011A893
0x14011a816  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, r15b
0x14011a81d  xorps   xmm0, xmm0
0x14011a820  movups  [rbp+3Fh+var_B8], xmm0
0x14011a824  jge     short loc_14011A893
0x14011a826  mov     rcx, rdi; Process
0x14011a829  call    cs:__imp_PsGetProcessId
0x14011a830  nop     dword ptr [rax+rax+00h]
0x14011a835  mov     rcx, rdi
0x14011a838  mov     qword ptr [rbp+3Fh+var_B8+8], r15
0x14011a83c  mov     rbx, rax
0x14011a83f  mov     qword ptr [rbp+3Fh+var_B8], r15
0x14011a843  call    cs:__imp_PsGetProcessStartKey
0x14011a84a  nop     dword ptr [rax+rax+00h]
0x14011a84f  mov     [rsp+120h+var_D0], 0C000A013h
0x14011a857  mov     [rsp+120h+var_D8], 1
0x14011a85f  mov     [rsp+120h+var_E0], rax
0x14011a864  lea     r8, [rbp+3Fh+var_B8]
0x14011a868  mov     [rsp+120h+var_E8], ebx
0x14011a86c  lea     rdx, RAW_CREATE_ENDPOINT_FAILURE
0x14011a873  mov     [rsp+120h+var_F0], 1
0x14011a87b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14011a882  mov     [rsp+120h+var_F8], esi
0x14011a886  xor     r9d, r9d
0x14011a889  mov     dword ptr [rsp+120h+var_100], r14d
0x14011a88e  call    McTemplateK0pqqqqxqq_EtwWriteTransfer
0x14011a893  mov     eax, 0C000A013h
0x14011a898  jmp     loc_14011AAD2
0x14011a89d  mov     edx, 100h
0x14011a8a2  mov     ecx, 40h ; '@'
0x14011a8a7  mov     r8d, 45776152h
0x14011a8ad  call    cs:__imp_ExAllocatePool2
0x14011a8b4  nop     dword ptr [rax+rax+00h]
0x14011a8b9  mov     r14, rax
0x14011a8bc  test    rax, rax
0x14011a8bf  jnz     short loc_14011A8D3
0x14011a8c1  mov     rcx, rbx
0x14011a8c4  call    _InetDereferenceAf
0x14011a8c9  mov     eax, 0C0000017h
0x14011a8ce  jmp     loc_14011AAD2
0x14011a8d3  mov     rcx, r14; SpinLock
0x14011a8d6  call    cs:__imp_KeInitializeSpinLock
0x14011a8dd  nop     dword ptr [rax+rax+00h]
0x14011a8e2  mov     edx, 1; Count
0x14011a8e7  mov     dword ptr [r14+8], 0
0x14011a8ef  mov     r8d, edx; Limit
0x14011a8f2  lea     rcx, [r14+0E0h]; Semaphore
0x14011a8f9  call    cs:__imp_KeInitializeSemaphore
0x14011a900  nop     dword ptr [rax+rax+00h]
0x14011a905  mov     ecx, 1
0x14011a90a  mov     [r14+38h], rbx
0x14011a90e  mov     [r14+10h], ecx
0x14011a912  mov     eax, ecx
0x14011a914  mov     [r14+30h], r15
0x14011a918  lock xadd [r15+10h], rax
0x14011a91e  add     rax, rcx
0x14011a921  cmp     rax, rcx
0x14011a924  jg      short loc_14011A92D
0x14011a926  mov     ecx, 0Eh
0x14011a92b  int     29h; Win8: RtlFailFast(ecx)
0x14011a92d  lea     rax, [r14+20h]
0x14011a931  mov     [r14+40h], esi
0x14011a935  mov     [rax+8], rax
0x14011a939  mov     rcx, rdi; Object
0x14011a93c  mov     [rax], rax
0x14011a93f  mov     [r14+48h], rdi
0x14011a943  call    cs:__imp_ObfReferenceObject
0x14011a94a  nop     dword ptr [rax+rax+00h]
0x14011a94f  mov     rcx, [rbp+3Fh+Object]; Object
0x14011a953  xor     ebx, ebx
0x14011a955  mov     [r14+50h], rcx
0x14011a959  test    rcx, rcx
0x14011a95c  jz      short loc_14011A96A
0x14011a95e  call    cs:__imp_ObfReferenceObject
0x14011a965  nop     dword ptr [rax+rax+00h]
0x14011a96a  mov     rcx, [r14+50h]
0x14011a96e  test    rcx, rcx
0x14011a971  jz      short loc_14011A981
0x14011a973  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14011a97a  nop     dword ptr [rax+rax+00h]
0x14011a97f  jmp     short loc_14011A9AC
0x14011a981  call    cs:__imp_KeIsExecutingDpc
0x14011a988  nop     dword ptr [rax+rax+00h]
0x14011a98d  test    eax, eax
0x14011a98f  jnz     short loc_14011A99C
0x14011a991  mov     rcx, gs:188h
0x14011a99a  jmp     short loc_14011A973
0x14011a99c  mov     rcx, [r14+48h]
0x14011a9a0  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x14011a9a7  nop     dword ptr [rax+rax+00h]
0x14011a9ac  mov     rcx, [r14+38h]
0x14011a9b0  mov     edx, eax
0x14011a9b2  mov     r15d, eax
0x14011a9b5  call    _InetFindAndReferenceCompartmentAf
0x14011a9ba  mov     [r14+60h], rax
0x14011a9be  test    rax, rax
0x14011a9c1  jnz     loc_14011AA6A
0x14011a9c7  cmp     cs:dword_1402241D4, ebx
0x14011a9cd  jz      loc_14011AA59
0x14011a9d3  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, bl
0x14011a9d9  xorps   xmm0, xmm0
0x14011a9dc  movups  [rbp+3Fh+var_B8], xmm0
0x14011a9e0  jge     short loc_14011AA59
0x14011a9e2  mov     rcx, [r14+48h]; Process
0x14011a9e6  call    cs:__imp_PsGetProcessId
0x14011a9ed  nop     dword ptr [rax+rax+00h]
0x14011a9f2  mov     rcx, [r14+38h]
0x14011a9f6  mov     rsi, rax
0x14011a9f9  mov     edi, [r14+40h]
0x14011a9fd  mov     qword ptr [rbp+3Fh+var_B8+8], rbx
0x14011aa01  mov     qword ptr [rbp+3Fh+var_B8], r14
0x14011aa05  movzx   ebx, word ptr [rcx+18h]
0x14011aa09  mov     rcx, [r14+48h]
0x14011aa0d  call    cs:__imp_PsGetProcessStartKey
0x14011aa14  nop     dword ptr [rax+rax+00h]
0x14011aa19  mov     [rsp+120h+var_D0], 0C0000104h
0x14011aa21  lea     r8, [rbp+3Fh+var_B8]
0x14011aa25  mov     [rsp+120h+var_D8], 2
0x14011aa2d  lea     rdx, RAW_CREATE_ENDPOINT_FAILURE
0x14011aa34  mov     [rsp+120h+var_E0], rax
0x14011aa39  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14011aa40  mov     [rsp+120h+var_E8], esi
0x14011aa44  mov     r9, r14
0x14011aa47  mov     [rsp+120h+var_F0], r15d
0x14011aa4c  mov     [rsp+120h+var_F8], edi
0x14011aa50  mov     dword ptr [rsp+120h+var_100], ebx
0x14011aa54  call    McTemplateK0pqqqqxqq_EtwWriteTransfer
0x14011aa59  xor     edx, edx
0x14011aa5b  mov     rcx, r14
0x14011aa5e  call    RawCloseEndpoint
0x14011aa63  mov     eax, 0C0000104h
0x14011aa68  jmp     short loc_14011AAD2
0x14011aa6a  or      dword ptr [r14+18h], 20h
0x14011aa6f  lea     rcx, [r14+0A8h]
0x14011aa76  xor     r8d, r8d
0x14011aa79  xor     edx, edx
0x14011aa7b  call    InetInitializeSs
0x14011aa80  mov     [r14+98h], r13
0x14011aa87  mov     [r14+0A0h], r12
0x14011aa8e  call    cs:__imp_KeGetCurrentIrql
0x14011aa95  nop     dword ptr [rax+rax+00h]
0x14011aa9a  test    al, al
0x14011aa9c  jnz     short loc_14011AAB3
0x14011aa9e  lea     rcx, [r14+90h]
0x14011aaa5  mov     [r14+90h], rbx
0x14011aaac  call    RawCreateEndpointWorkQueueRoutine
0x14011aab1  jmp     short loc_14011AACD
0x14011aab3  lea     rdx, [r14+90h]
0x14011aaba  lea     rcx, qword_140228720
0x14011aac1  call    cs:__imp_NetioInsertWorkQueue
0x14011aac8  nop     dword ptr [rax+rax+00h]
0x14011aacd  mov     eax, 103h
0x14011aad2  mov     rcx, [rbp+3Fh+var_40]
0x14011aad6  xor     rcx, rsp; StackCookie
0x14011aad9  call    __security_check_cookie
0x14011aade  mov     rbx, [rsp+120h+arg_8]
0x14011aae6  add     rsp, 0F0h
0x14011aaed  pop     r15
0x14011aaef  pop     r14
0x14011aaf1  pop     r13
0x14011aaf3  pop     r12
0x14011aaf5  pop     rdi
0x14011aaf6  pop     rsi
0x14011aaf7  pop     rbp
0x14011aaf8  retn
```
