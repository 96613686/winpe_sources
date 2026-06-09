# RawCreateEndpoint

- ea: `0x140110730`
- end: `0x140110bca`
- name: `RawCreateEndpoint`
- size: `1178`
- prototype: `__int64 __fastcall(int, int, int, int, int, PEPROCESS Process, PVOID Object)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008127c`
- `0x1401106f0`

## callees

- `0x140017060`
- `0x140017ca0`
- `0x140039b00`
- `0x140081950`
- `0x1400828a8`
- `0x1400d12e0`
- `0x1400ff31c`
- `0x140110730`
- `0x14011e6e8`
- `0x140128320`
- `0x140156df0`
- `0x140168f3c`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x1401109c9`
- `ntoskrnl!KeInitializeSemaphore` at `0x1401109c9`
- `ntoskrnl!KeIsExecutingDpc` at `0x140110a51`
- `ntoskrnl!KeIsExecutingDpc` at `0x140110a51`
- `ntoskrnl!ObfReferenceObject` at `0x140110a13`
- `ntoskrnl!ObfReferenceObject` at `0x140110a2e`
- `ntoskrnl!ObfReferenceObject` at `0x140110a13`
- `ntoskrnl!ObfReferenceObject` at `0x140110a2e`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401108a0`
- `ntoskrnl!PsGetProcessStartKey` at `0x140110913`
- `ntoskrnl!PsGetProcessStartKey` at `0x140110add`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401108a0`
- `ntoskrnl!PsGetProcessStartKey` at `0x140110913`
- `ntoskrnl!PsGetProcessStartKey` at `0x140110add`
- `ntoskrnl!KeGetCurrentIrql` at `0x140110b5e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140110b5e`
- `ntoskrnl!PsGetProcessId` at `0x14011087e`
- `ntoskrnl!PsGetProcessId` at `0x1401108f9`
- `ntoskrnl!PsGetProcessId` at `0x140110ab6`
- `ntoskrnl!PsGetProcessId` at `0x14011087e`
- `ntoskrnl!PsGetProcessId` at `0x1401108f9`
- `ntoskrnl!PsGetProcessId` at `0x140110ab6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401109a6`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401109a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140110843`
- `ntoskrnl!ExFreePoolWithTag` at `0x140110843`
- `ntoskrnl!ExAllocatePool2` at `0x14011097d`
- `ntoskrnl!ExAllocatePool2` at `0x14011097d`
- `NETIO!NetioInsertWorkQueue` at `0x140110b91`
- `NETIO!NetioInsertWorkQueue` at `0x140110b91`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x140110a70`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x140110a70`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140110a43`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140110a43`

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
  if ( LOBYTE(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Blink) )
  {
    AppNameFromProcess = (_QWORD *)TcpipGetAppNameFromProcess(ClientProcess);
    if ( AppNameFromProcess )
    {
      if ( (unsigned int)dword_1402201F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1402201F8, 0x400000000000LL) )
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
        tlgWriteAgg((int)&dword_1402201F8, (int)&dword_1401F2F77, v13, 6, &v34);
      }
      ExFreePoolWithTag(AppNameFromProcess, 0x4E416354u);
    }
  }
  if ( a5 >= 0x100 )
  {
    if ( dword_1402201D4 )
    {
      v33 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId(ClientProcess);
        v33 = 0u;
        ProcessStartKey = PsGetProcessStartKey(ClientProcess);
        McTemplateK0pqqqqxqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)&RAW_CREATE_ENDPOINT_FAILURE,
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
    if ( dword_1402201D4 )
    {
      v33 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
      {
        v17 = (unsigned __int8)PsGetProcessId(ClientProcess);
        v33 = 0u;
        v18 = PsGetProcessStartKey(ClientProcess);
        McTemplateK0pqqqqxqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)&RAW_CREATE_ENDPOINT_FAILURE,
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
      NetioInsertWorkQueue(&unk_1402246A0, v21 + 18);
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
    if ( dword_1402201D4 )
    {
      v33 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
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
          (unsigned int)&RAW_CREATE_ENDPOINT_FAILURE,
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
0x140110730  mov     [rsp-8+arg_8], rbx
0x140110735  push    rbp
0x140110736  push    rsi
0x140110737  push    rdi
0x140110738  push    r12
0x14011073a  push    r13
0x14011073c  push    r14
0x14011073e  push    r15
0x140110740  lea     rbp, [rsp-0Fh]
0x140110745  sub     rsp, 0F0h
0x14011074c  mov     rax, cs:__security_cookie
0x140110753  xor     rax, rsp
0x140110756  mov     [rbp+3Fh+var_40], rax
0x14011075a  mov     rdi, [rbp+3Fh+Process]
0x14011075e  mov     r12, r8
0x140110761  movzx   r14d, r9w
0x140110765  mov     r13, rdx
0x140110768  mov     r15, rcx
0x14011076b  test    rdi, rdi
0x14011076e  jnz     short loc_140110778
0x140110770  call    InetGetClientProcess
0x140110775  mov     rdi, rax
0x140110778  cmp     byte ptr cs:WPP_MAIN_CB.Queue+8, 0
0x14011077f  jz      loc_14011084F
0x140110785  mov     rcx, rdi
0x140110788  call    TcpipGetAppNameFromProcess
0x14011078d  mov     rbx, rax
0x140110790  test    rax, rax
0x140110793  jz      loc_14011084F
0x140110799  mov     ecx, cs:dword_1402201F8
0x14011079f  cmp     ecx, 5
0x1401107a2  jbe     loc_14011083B
0x1401107a8  mov     rdx, 400000000000h
0x1401107b2  lea     rcx, dword_1402201F8
0x1401107b9  call    _tlgKeywordOn
0x1401107be  test    al, al
0x1401107c0  jz      short loc_14011083B
0x1401107c2  lea     rax, [rsp+120h+var_C0]
0x1401107c7  mov     [rsp+120h+var_C0], 1
0x1401107d0  mov     [rbp+3Fh+var_80], rax
0x1401107d4  lea     rdx, dword_1401F2F77; int
0x1401107db  lea     rax, [rbp+3Fh+var_58]
0x1401107df  mov     [rbp+3Fh+var_78], 8
0x1401107e7  mov     [rbp+3Fh+var_70], rax
0x1401107eb  lea     rcx, dword_1402201F8; int
0x1401107f2  mov     rax, [rbx+8]
0x1401107f6  mov     r9d, 6; int
0x1401107fc  mov     [rbp+3Fh+var_60], rax
0x140110800  movzx   eax, word ptr [rbx]
0x140110803  mov     [rbp+3Fh+var_58], eax
0x140110806  lea     rax, [rbp+3Fh+var_B8]
0x14011080a  mov     [rbp+3Fh+var_50], rax
0x14011080e  lea     rax, [rbp+3Fh+var_A0]
0x140110812  mov     [rsp+120h+var_100], rax; PEVENT_DATA_DESCRIPTOR
0x140110817  mov     [rbp+3Fh+var_68], 2
0x14011081f  mov     [rbp+3Fh+var_54], 0
0x140110826  mov     qword ptr [rbp+3Fh+var_B8], 2000000h
0x14011082e  mov     [rbp+3Fh+var_48], 8
0x140110836  call    _tlgWriteAgg
0x14011083b  mov     edx, 4E416354h; Tag
0x140110840  mov     rcx, rbx; P
0x140110843  call    cs:__imp_ExFreePoolWithTag
0x14011084a  nop     dword ptr [rax+rax+00h]
0x14011084f  mov     esi, [rbp+3Fh+arg_20]
0x140110852  cmp     esi, 100h
0x140110858  jb      short loc_1401108BE
0x14011085a  cmp     cs:dword_1402201D4, 0
0x140110861  jz      loc_140110963
0x140110867  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, 0
0x14011086e  xorps   xmm0, xmm0
0x140110871  movups  [rbp+3Fh+var_B8], xmm0
0x140110875  jge     loc_140110963
0x14011087b  mov     rcx, rdi; Process
0x14011087e  call    cs:__imp_PsGetProcessId
0x140110885  nop     dword ptr [rax+rax+00h]
0x14011088a  mov     rcx, rdi
0x14011088d  mov     qword ptr [rbp+3Fh+var_B8+8], 0
0x140110895  mov     rbx, rax
0x140110898  mov     qword ptr [rbp+3Fh+var_B8], 0
0x1401108a0  call    cs:__imp_PsGetProcessStartKey
0x1401108a7  nop     dword ptr [rax+rax+00h]
0x1401108ac  mov     [rsp+120h+var_D0], 0C000A013h
0x1401108b4  mov     [rsp+120h+var_D8], 4
0x1401108bc  jmp     short loc_14011092F
0x1401108be  movzx   edx, r14w
0x1401108c2  lea     rcx, RawInetTransport
0x1401108c9  call    InetFindAndReferenceAf
0x1401108ce  mov     rbx, rax
0x1401108d1  test    rax, rax
0x1401108d4  jnz     loc_14011096D
0x1401108da  xor     r15d, r15d
0x1401108dd  cmp     cs:dword_1402201D4, r15d
0x1401108e4  jz      short loc_140110963
0x1401108e6  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, r15b
0x1401108ed  xorps   xmm0, xmm0
0x1401108f0  movups  [rbp+3Fh+var_B8], xmm0
0x1401108f4  jge     short loc_140110963
0x1401108f6  mov     rcx, rdi; Process
0x1401108f9  call    cs:__imp_PsGetProcessId
0x140110900  nop     dword ptr [rax+rax+00h]
0x140110905  mov     rcx, rdi
0x140110908  mov     qword ptr [rbp+3Fh+var_B8+8], r15
0x14011090c  mov     rbx, rax
0x14011090f  mov     qword ptr [rbp+3Fh+var_B8], r15
0x140110913  call    cs:__imp_PsGetProcessStartKey
0x14011091a  nop     dword ptr [rax+rax+00h]
0x14011091f  mov     [rsp+120h+var_D0], 0C000A013h
0x140110927  mov     [rsp+120h+var_D8], 1
0x14011092f  mov     [rsp+120h+var_E0], rax
0x140110934  lea     r8, [rbp+3Fh+var_B8]
0x140110938  mov     [rsp+120h+var_E8], ebx
0x14011093c  lea     rdx, RAW_CREATE_ENDPOINT_FAILURE
0x140110943  mov     [rsp+120h+var_F0], 1
0x14011094b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140110952  mov     [rsp+120h+var_F8], esi
0x140110956  xor     r9d, r9d
0x140110959  mov     dword ptr [rsp+120h+var_100], r14d
0x14011095e  call    McTemplateK0pqqqqxqq_EtwWriteTransfer
0x140110963  mov     eax, 0C000A013h
0x140110968  jmp     loc_140110BA2
0x14011096d  mov     edx, 100h
0x140110972  mov     ecx, 40h ; '@'
0x140110977  mov     r8d, 45776152h
0x14011097d  call    cs:__imp_ExAllocatePool2
0x140110984  nop     dword ptr [rax+rax+00h]
0x140110989  mov     r14, rax
0x14011098c  test    rax, rax
0x14011098f  jnz     short loc_1401109A3
0x140110991  mov     rcx, rbx
0x140110994  call    _InetDereferenceAf
0x140110999  mov     eax, 0C0000017h
0x14011099e  jmp     loc_140110BA2
0x1401109a3  mov     rcx, r14; SpinLock
0x1401109a6  call    cs:__imp_KeInitializeSpinLock
0x1401109ad  nop     dword ptr [rax+rax+00h]
0x1401109b2  mov     edx, 1; Count
0x1401109b7  mov     dword ptr [r14+8], 0
0x1401109bf  mov     r8d, edx; Limit
0x1401109c2  lea     rcx, [r14+0E0h]; Semaphore
0x1401109c9  call    cs:__imp_KeInitializeSemaphore
0x1401109d0  nop     dword ptr [rax+rax+00h]
0x1401109d5  mov     ecx, 1
0x1401109da  mov     [r14+38h], rbx
0x1401109de  mov     [r14+10h], ecx
0x1401109e2  mov     eax, ecx
0x1401109e4  mov     [r14+30h], r15
0x1401109e8  lock xadd [r15+10h], rax
0x1401109ee  add     rax, rcx
0x1401109f1  cmp     rax, rcx
0x1401109f4  jg      short loc_1401109FD
0x1401109f6  mov     ecx, 0Eh
0x1401109fb  int     29h; Win8: RtlFailFast(ecx)
0x1401109fd  lea     rax, [r14+20h]
0x140110a01  mov     [r14+40h], esi
0x140110a05  mov     [rax+8], rax
0x140110a09  mov     rcx, rdi; Object
0x140110a0c  mov     [rax], rax
0x140110a0f  mov     [r14+48h], rdi
0x140110a13  call    cs:__imp_ObfReferenceObject
0x140110a1a  nop     dword ptr [rax+rax+00h]
0x140110a1f  mov     rcx, [rbp+3Fh+Object]; Object
0x140110a23  xor     ebx, ebx
0x140110a25  mov     [r14+50h], rcx
0x140110a29  test    rcx, rcx
0x140110a2c  jz      short loc_140110A3A
0x140110a2e  call    cs:__imp_ObfReferenceObject
0x140110a35  nop     dword ptr [rax+rax+00h]
0x140110a3a  mov     rcx, [r14+50h]
0x140110a3e  test    rcx, rcx
0x140110a41  jz      short loc_140110A51
0x140110a43  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140110a4a  nop     dword ptr [rax+rax+00h]
0x140110a4f  jmp     short loc_140110A7C
0x140110a51  call    cs:__imp_KeIsExecutingDpc
0x140110a58  nop     dword ptr [rax+rax+00h]
0x140110a5d  test    eax, eax
0x140110a5f  jnz     short loc_140110A6C
0x140110a61  mov     rcx, gs:188h
0x140110a6a  jmp     short loc_140110A43
0x140110a6c  mov     rcx, [r14+48h]
0x140110a70  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x140110a77  nop     dword ptr [rax+rax+00h]
0x140110a7c  mov     rcx, [r14+38h]
0x140110a80  mov     edx, eax
0x140110a82  mov     r15d, eax
0x140110a85  call    _InetFindAndReferenceCompartmentAf
0x140110a8a  mov     [r14+60h], rax
0x140110a8e  test    rax, rax
0x140110a91  jnz     loc_140110B3A
0x140110a97  cmp     cs:dword_1402201D4, ebx
0x140110a9d  jz      loc_140110B29
0x140110aa3  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, bl
0x140110aa9  xorps   xmm0, xmm0
0x140110aac  movups  [rbp+3Fh+var_B8], xmm0
0x140110ab0  jge     short loc_140110B29
0x140110ab2  mov     rcx, [r14+48h]; Process
0x140110ab6  call    cs:__imp_PsGetProcessId
0x140110abd  nop     dword ptr [rax+rax+00h]
0x140110ac2  mov     rcx, [r14+38h]
0x140110ac6  mov     rsi, rax
0x140110ac9  mov     edi, [r14+40h]
0x140110acd  mov     qword ptr [rbp+3Fh+var_B8+8], rbx
0x140110ad1  mov     qword ptr [rbp+3Fh+var_B8], r14
0x140110ad5  movzx   ebx, word ptr [rcx+18h]
0x140110ad9  mov     rcx, [r14+48h]
0x140110add  call    cs:__imp_PsGetProcessStartKey
0x140110ae4  nop     dword ptr [rax+rax+00h]
0x140110ae9  mov     [rsp+120h+var_D0], 0C0000104h
0x140110af1  lea     r8, [rbp+3Fh+var_B8]
0x140110af5  mov     [rsp+120h+var_D8], 2
0x140110afd  lea     rdx, RAW_CREATE_ENDPOINT_FAILURE
0x140110b04  mov     [rsp+120h+var_E0], rax
0x140110b09  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140110b10  mov     [rsp+120h+var_E8], esi
0x140110b14  mov     r9, r14
0x140110b17  mov     [rsp+120h+var_F0], r15d
0x140110b1c  mov     [rsp+120h+var_F8], edi
0x140110b20  mov     dword ptr [rsp+120h+var_100], ebx
0x140110b24  call    McTemplateK0pqqqqxqq_EtwWriteTransfer
0x140110b29  xor     edx, edx
0x140110b2b  mov     rcx, r14
0x140110b2e  call    RawCloseEndpoint
0x140110b33  mov     eax, 0C0000104h
0x140110b38  jmp     short loc_140110BA2
0x140110b3a  or      dword ptr [r14+18h], 20h
0x140110b3f  lea     rcx, [r14+0A8h]
0x140110b46  xor     r8d, r8d
0x140110b49  xor     edx, edx
0x140110b4b  call    InetInitializeSs
0x140110b50  mov     [r14+98h], r13
0x140110b57  mov     [r14+0A0h], r12
0x140110b5e  call    cs:__imp_KeGetCurrentIrql
0x140110b65  nop     dword ptr [rax+rax+00h]
0x140110b6a  test    al, al
0x140110b6c  jnz     short loc_140110B83
0x140110b6e  lea     rcx, [r14+90h]
0x140110b75  mov     [r14+90h], rbx
0x140110b7c  call    RawCreateEndpointWorkQueueRoutine
0x140110b81  jmp     short loc_140110B9D
0x140110b83  lea     rdx, [r14+90h]
0x140110b8a  lea     rcx, unk_1402246A0
0x140110b91  call    cs:__imp_NetioInsertWorkQueue
0x140110b98  nop     dword ptr [rax+rax+00h]
0x140110b9d  mov     eax, 103h
0x140110ba2  mov     rcx, [rbp+3Fh+var_40]
0x140110ba6  xor     rcx, rsp; StackCookie
0x140110ba9  call    __security_check_cookie
0x140110bae  mov     rbx, [rsp+120h+arg_8]
0x140110bb6  add     rsp, 0F0h
0x140110bbd  pop     r15
0x140110bbf  pop     r14
0x140110bc1  pop     r13
0x140110bc3  pop     r12
0x140110bc5  pop     rdi
0x140110bc6  pop     rsi
0x140110bc7  pop     rbp
0x140110bc8  retn
```
