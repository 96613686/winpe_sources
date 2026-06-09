# RawCreateEndpoint

- ea: `0x1401105f0`
- end: `0x140110a8a`
- name: `RawCreateEndpoint`
- size: `1178`
- prototype: `__int64 __fastcall(int, int, int, int, int, PEPROCESS Process, PVOID Object)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400803cc`
- `0x1401105b0`

## callees

- `0x140017060`
- `0x140017ca0`
- `0x140039860`
- `0x140080aa0`
- `0x1400819f8`
- `0x1400d1500`
- `0x1400ff1dc`
- `0x1401105f0`
- `0x14011e5a8`
- `0x1401281e0`
- `0x140156cb0`
- `0x140168dfc`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeInitializeSemaphore` at `0x140110889`
- `ntoskrnl!KeInitializeSemaphore` at `0x140110889`
- `ntoskrnl!KeIsExecutingDpc` at `0x140110911`
- `ntoskrnl!KeIsExecutingDpc` at `0x140110911`
- `ntoskrnl!ObfReferenceObject` at `0x1401108d3`
- `ntoskrnl!ObfReferenceObject` at `0x1401108ee`
- `ntoskrnl!ObfReferenceObject` at `0x1401108d3`
- `ntoskrnl!ObfReferenceObject` at `0x1401108ee`
- `ntoskrnl!PsGetProcessStartKey` at `0x140110760`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401107d3`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011099d`
- `ntoskrnl!PsGetProcessStartKey` at `0x140110760`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401107d3`
- `ntoskrnl!PsGetProcessStartKey` at `0x14011099d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140110a1e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140110a1e`
- `ntoskrnl!PsGetProcessId` at `0x14011073e`
- `ntoskrnl!PsGetProcessId` at `0x1401107b9`
- `ntoskrnl!PsGetProcessId` at `0x140110976`
- `ntoskrnl!PsGetProcessId` at `0x14011073e`
- `ntoskrnl!PsGetProcessId` at `0x1401107b9`
- `ntoskrnl!PsGetProcessId` at `0x140110976`
- `ntoskrnl!KeInitializeSpinLock` at `0x140110866`
- `ntoskrnl!KeInitializeSpinLock` at `0x140110866`
- `ntoskrnl!ExFreePoolWithTag` at `0x140110703`
- `ntoskrnl!ExFreePoolWithTag` at `0x140110703`
- `ntoskrnl!ExAllocatePool2` at `0x14011083d`
- `ntoskrnl!ExAllocatePool2` at `0x14011083d`
- `NETIO!NetioInsertWorkQueue` at `0x140110a51`
- `NETIO!NetioInsertWorkQueue` at `0x140110a51`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x140110930`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x140110930`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140110903`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140110903`

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
  if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) )
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
        tlgWriteAgg((int)&dword_1402201F8, (int)&byte_1401F2F77, v13, 6, &v34);
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
      NetioInsertWorkQueue(qword_1402246E0, v21 + 18);
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
0x1401105f0  mov     [rsp-8+arg_8], rbx
0x1401105f5  push    rbp
0x1401105f6  push    rsi
0x1401105f7  push    rdi
0x1401105f8  push    r12
0x1401105fa  push    r13
0x1401105fc  push    r14
0x1401105fe  push    r15
0x140110600  lea     rbp, [rsp-0Fh]
0x140110605  sub     rsp, 0F0h
0x14011060c  mov     rax, cs:__security_cookie
0x140110613  xor     rax, rsp
0x140110616  mov     [rbp+3Fh+var_40], rax
0x14011061a  mov     rdi, [rbp+3Fh+Process]
0x14011061e  mov     r12, r8
0x140110621  movzx   r14d, r9w
0x140110625  mov     r13, rdx
0x140110628  mov     r15, rcx
0x14011062b  test    rdi, rdi
0x14011062e  jnz     short loc_140110638
0x140110630  call    InetGetClientProcess
0x140110635  mov     rdi, rax
0x140110638  cmp     byte ptr cs:WPP_MAIN_CB.DeviceExtension, 0
0x14011063f  jz      loc_14011070F
0x140110645  mov     rcx, rdi
0x140110648  call    TcpipGetAppNameFromProcess
0x14011064d  mov     rbx, rax
0x140110650  test    rax, rax
0x140110653  jz      loc_14011070F
0x140110659  mov     ecx, cs:dword_1402201F8
0x14011065f  cmp     ecx, 5
0x140110662  jbe     loc_1401106FB
0x140110668  mov     rdx, 400000000000h
0x140110672  lea     rcx, dword_1402201F8
0x140110679  call    _tlgKeywordOn
0x14011067e  test    al, al
0x140110680  jz      short loc_1401106FB
0x140110682  lea     rax, [rsp+120h+var_C0]
0x140110687  mov     [rsp+120h+var_C0], 1
0x140110690  mov     [rbp+3Fh+var_80], rax
0x140110694  lea     rdx, byte_1401F2F77; int
0x14011069b  lea     rax, [rbp+3Fh+var_58]
0x14011069f  mov     [rbp+3Fh+var_78], 8
0x1401106a7  mov     [rbp+3Fh+var_70], rax
0x1401106ab  lea     rcx, dword_1402201F8; int
0x1401106b2  mov     rax, [rbx+8]
0x1401106b6  mov     r9d, 6; int
0x1401106bc  mov     [rbp+3Fh+var_60], rax
0x1401106c0  movzx   eax, word ptr [rbx]
0x1401106c3  mov     [rbp+3Fh+var_58], eax
0x1401106c6  lea     rax, [rbp+3Fh+var_B8]
0x1401106ca  mov     [rbp+3Fh+var_50], rax
0x1401106ce  lea     rax, [rbp+3Fh+var_A0]
0x1401106d2  mov     [rsp+120h+var_100], rax; PEVENT_DATA_DESCRIPTOR
0x1401106d7  mov     [rbp+3Fh+var_68], 2
0x1401106df  mov     [rbp+3Fh+var_54], 0
0x1401106e6  mov     qword ptr [rbp+3Fh+var_B8], 2000000h
0x1401106ee  mov     [rbp+3Fh+var_48], 8
0x1401106f6  call    _tlgWriteAgg
0x1401106fb  mov     edx, 4E416354h; Tag
0x140110700  mov     rcx, rbx; P
0x140110703  call    cs:__imp_ExFreePoolWithTag
0x14011070a  nop     dword ptr [rax+rax+00h]
0x14011070f  mov     esi, [rbp+3Fh+arg_20]
0x140110712  cmp     esi, 100h
0x140110718  jb      short loc_14011077E
0x14011071a  cmp     cs:dword_1402201D4, 0
0x140110721  jz      loc_140110823
0x140110727  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, 0
0x14011072e  xorps   xmm0, xmm0
0x140110731  movups  [rbp+3Fh+var_B8], xmm0
0x140110735  jge     loc_140110823
0x14011073b  mov     rcx, rdi; Process
0x14011073e  call    cs:__imp_PsGetProcessId
0x140110745  nop     dword ptr [rax+rax+00h]
0x14011074a  mov     rcx, rdi
0x14011074d  mov     qword ptr [rbp+3Fh+var_B8+8], 0
0x140110755  mov     rbx, rax
0x140110758  mov     qword ptr [rbp+3Fh+var_B8], 0
0x140110760  call    cs:__imp_PsGetProcessStartKey
0x140110767  nop     dword ptr [rax+rax+00h]
0x14011076c  mov     [rsp+120h+var_D0], 0C000A013h
0x140110774  mov     [rsp+120h+var_D8], 4
0x14011077c  jmp     short loc_1401107EF
0x14011077e  movzx   edx, r14w
0x140110782  lea     rcx, RawInetTransport
0x140110789  call    InetFindAndReferenceAf
0x14011078e  mov     rbx, rax
0x140110791  test    rax, rax
0x140110794  jnz     loc_14011082D
0x14011079a  xor     r15d, r15d
0x14011079d  cmp     cs:dword_1402201D4, r15d
0x1401107a4  jz      short loc_140110823
0x1401107a6  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, r15b
0x1401107ad  xorps   xmm0, xmm0
0x1401107b0  movups  [rbp+3Fh+var_B8], xmm0
0x1401107b4  jge     short loc_140110823
0x1401107b6  mov     rcx, rdi; Process
0x1401107b9  call    cs:__imp_PsGetProcessId
0x1401107c0  nop     dword ptr [rax+rax+00h]
0x1401107c5  mov     rcx, rdi
0x1401107c8  mov     qword ptr [rbp+3Fh+var_B8+8], r15
0x1401107cc  mov     rbx, rax
0x1401107cf  mov     qword ptr [rbp+3Fh+var_B8], r15
0x1401107d3  call    cs:__imp_PsGetProcessStartKey
0x1401107da  nop     dword ptr [rax+rax+00h]
0x1401107df  mov     [rsp+120h+var_D0], 0C000A013h
0x1401107e7  mov     [rsp+120h+var_D8], 1
0x1401107ef  mov     [rsp+120h+var_E0], rax
0x1401107f4  lea     r8, [rbp+3Fh+var_B8]
0x1401107f8  mov     [rsp+120h+var_E8], ebx
0x1401107fc  lea     rdx, RAW_CREATE_ENDPOINT_FAILURE
0x140110803  mov     [rsp+120h+var_F0], 1
0x14011080b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140110812  mov     [rsp+120h+var_F8], esi
0x140110816  xor     r9d, r9d
0x140110819  mov     dword ptr [rsp+120h+var_100], r14d
0x14011081e  call    McTemplateK0pqqqqxqq_EtwWriteTransfer
0x140110823  mov     eax, 0C000A013h
0x140110828  jmp     loc_140110A62
0x14011082d  mov     edx, 100h
0x140110832  mov     ecx, 40h ; '@'
0x140110837  mov     r8d, 45776152h
0x14011083d  call    cs:__imp_ExAllocatePool2
0x140110844  nop     dword ptr [rax+rax+00h]
0x140110849  mov     r14, rax
0x14011084c  test    rax, rax
0x14011084f  jnz     short loc_140110863
0x140110851  mov     rcx, rbx
0x140110854  call    _InetDereferenceAf
0x140110859  mov     eax, 0C0000017h
0x14011085e  jmp     loc_140110A62
0x140110863  mov     rcx, r14; SpinLock
0x140110866  call    cs:__imp_KeInitializeSpinLock
0x14011086d  nop     dword ptr [rax+rax+00h]
0x140110872  mov     edx, 1; Count
0x140110877  mov     dword ptr [r14+8], 0
0x14011087f  mov     r8d, edx; Limit
0x140110882  lea     rcx, [r14+0E0h]; Semaphore
0x140110889  call    cs:__imp_KeInitializeSemaphore
0x140110890  nop     dword ptr [rax+rax+00h]
0x140110895  mov     ecx, 1
0x14011089a  mov     [r14+38h], rbx
0x14011089e  mov     [r14+10h], ecx
0x1401108a2  mov     eax, ecx
0x1401108a4  mov     [r14+30h], r15
0x1401108a8  lock xadd [r15+10h], rax
0x1401108ae  add     rax, rcx
0x1401108b1  cmp     rax, rcx
0x1401108b4  jg      short loc_1401108BD
0x1401108b6  mov     ecx, 0Eh
0x1401108bb  int     29h; Win8: RtlFailFast(ecx)
0x1401108bd  lea     rax, [r14+20h]
0x1401108c1  mov     [r14+40h], esi
0x1401108c5  mov     [rax+8], rax
0x1401108c9  mov     rcx, rdi; Object
0x1401108cc  mov     [rax], rax
0x1401108cf  mov     [r14+48h], rdi
0x1401108d3  call    cs:__imp_ObfReferenceObject
0x1401108da  nop     dword ptr [rax+rax+00h]
0x1401108df  mov     rcx, [rbp+3Fh+Object]; Object
0x1401108e3  xor     ebx, ebx
0x1401108e5  mov     [r14+50h], rcx
0x1401108e9  test    rcx, rcx
0x1401108ec  jz      short loc_1401108FA
0x1401108ee  call    cs:__imp_ObfReferenceObject
0x1401108f5  nop     dword ptr [rax+rax+00h]
0x1401108fa  mov     rcx, [r14+50h]
0x1401108fe  test    rcx, rcx
0x140110901  jz      short loc_140110911
0x140110903  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14011090a  nop     dword ptr [rax+rax+00h]
0x14011090f  jmp     short loc_14011093C
0x140110911  call    cs:__imp_KeIsExecutingDpc
0x140110918  nop     dword ptr [rax+rax+00h]
0x14011091d  test    eax, eax
0x14011091f  jnz     short loc_14011092C
0x140110921  mov     rcx, gs:188h
0x14011092a  jmp     short loc_140110903
0x14011092c  mov     rcx, [r14+48h]
0x140110930  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x140110937  nop     dword ptr [rax+rax+00h]
0x14011093c  mov     rcx, [r14+38h]
0x140110940  mov     edx, eax
0x140110942  mov     r15d, eax
0x140110945  call    _InetFindAndReferenceCompartmentAf
0x14011094a  mov     [r14+60h], rax
0x14011094e  test    rax, rax
0x140110951  jnz     loc_1401109FA
0x140110957  cmp     cs:dword_1402201D4, ebx
0x14011095d  jz      loc_1401109E9
0x140110963  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, bl
0x140110969  xorps   xmm0, xmm0
0x14011096c  movups  [rbp+3Fh+var_B8], xmm0
0x140110970  jge     short loc_1401109E9
0x140110972  mov     rcx, [r14+48h]; Process
0x140110976  call    cs:__imp_PsGetProcessId
0x14011097d  nop     dword ptr [rax+rax+00h]
0x140110982  mov     rcx, [r14+38h]
0x140110986  mov     rsi, rax
0x140110989  mov     edi, [r14+40h]
0x14011098d  mov     qword ptr [rbp+3Fh+var_B8+8], rbx
0x140110991  mov     qword ptr [rbp+3Fh+var_B8], r14
0x140110995  movzx   ebx, word ptr [rcx+18h]
0x140110999  mov     rcx, [r14+48h]
0x14011099d  call    cs:__imp_PsGetProcessStartKey
0x1401109a4  nop     dword ptr [rax+rax+00h]
0x1401109a9  mov     [rsp+120h+var_D0], 0C0000104h
0x1401109b1  lea     r8, [rbp+3Fh+var_B8]
0x1401109b5  mov     [rsp+120h+var_D8], 2
0x1401109bd  lea     rdx, RAW_CREATE_ENDPOINT_FAILURE
0x1401109c4  mov     [rsp+120h+var_E0], rax
0x1401109c9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401109d0  mov     [rsp+120h+var_E8], esi
0x1401109d4  mov     r9, r14
0x1401109d7  mov     [rsp+120h+var_F0], r15d
0x1401109dc  mov     [rsp+120h+var_F8], edi
0x1401109e0  mov     dword ptr [rsp+120h+var_100], ebx
0x1401109e4  call    McTemplateK0pqqqqxqq_EtwWriteTransfer
0x1401109e9  xor     edx, edx
0x1401109eb  mov     rcx, r14
0x1401109ee  call    RawCloseEndpoint
0x1401109f3  mov     eax, 0C0000104h
0x1401109f8  jmp     short loc_140110A62
0x1401109fa  or      dword ptr [r14+18h], 20h
0x1401109ff  lea     rcx, [r14+0A8h]
0x140110a06  xor     r8d, r8d
0x140110a09  xor     edx, edx
0x140110a0b  call    InetInitializeSs
0x140110a10  mov     [r14+98h], r13
0x140110a17  mov     [r14+0A0h], r12
0x140110a1e  call    cs:__imp_KeGetCurrentIrql
0x140110a25  nop     dword ptr [rax+rax+00h]
0x140110a2a  test    al, al
0x140110a2c  jnz     short loc_140110A43
0x140110a2e  lea     rcx, [r14+90h]
0x140110a35  mov     [r14+90h], rbx
0x140110a3c  call    RawCreateEndpointWorkQueueRoutine
0x140110a41  jmp     short loc_140110A5D
0x140110a43  lea     rdx, [r14+90h]
0x140110a4a  lea     rcx, qword_1402246E0
0x140110a51  call    cs:__imp_NetioInsertWorkQueue
0x140110a58  nop     dword ptr [rax+rax+00h]
0x140110a5d  mov     eax, 103h
0x140110a62  mov     rcx, [rbp+3Fh+var_40]
0x140110a66  xor     rcx, rsp; StackCookie
0x140110a69  call    __security_check_cookie
0x140110a6e  mov     rbx, [rsp+120h+arg_8]
0x140110a76  add     rsp, 0F0h
0x140110a7d  pop     r15
0x140110a7f  pop     r14
0x140110a81  pop     r13
0x140110a83  pop     r12
0x140110a85  pop     rdi
0x140110a86  pop     rsi
0x140110a87  pop     rbp
0x140110a88  retn
```
