# IpGetAllInterfaceParameters

- ea: `0x140064f60`
- end: `0x14006541f`
- name: `IpGetAllInterfaceParameters`
- size: `1215`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140030da0`
- `0x140048e40`
- `0x140064f60`
- `0x140065b80`
- `0x14014c8d8`
- `0x1401bf390`
- `0x1401bf940`
- `0x1401bfe60`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14006500b`
- `ntoskrnl!KfRaiseIrql` at `0x14006511c`
- `ntoskrnl!KfRaiseIrql` at `0x14006500b`
- `ntoskrnl!KfRaiseIrql` at `0x14006511c`
- `ntoskrnl!KeLowerIrql` at `0x1400650ca`
- `ntoskrnl!KeLowerIrql` at `0x1400651c1`
- `ntoskrnl!KeLowerIrql` at `0x1400651f1`
- `ntoskrnl!KeLowerIrql` at `0x14006539a`
- `ntoskrnl!KeLowerIrql` at `0x1400650ca`
- `ntoskrnl!KeLowerIrql` at `0x1400651c1`
- `ntoskrnl!KeLowerIrql` at `0x1400651f1`
- `ntoskrnl!KeLowerIrql` at `0x14006539a`
- `ntoskrnl!IoQueueWorkItem` at `0x140065381`
- `ntoskrnl!IoQueueWorkItem` at `0x140065381`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006504d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140065160`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006504d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140065160`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065062`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065176`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065062`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065176`
- `ntoskrnl!KeTestSpinLock` at `0x140065031`
- `ntoskrnl!KeTestSpinLock` at `0x140065143`
- `ntoskrnl!KeTestSpinLock` at `0x140065031`
- `ntoskrnl!KeTestSpinLock` at `0x140065143`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x14006530e`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x14006530e`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140064fd7`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140064fd7`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140064ff4`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140064ff4`

## pseudocode

```c
__int64 __fastcall IpGetAllInterfaceParameters(__int64 a1)
{
  _QWORD *v1; // r15
  __int64 v3; // rbp
  int ThreadObjectCompartmentId; // esi
  KIRQL v5; // r14
  _QWORD **v6; // rdx
  _QWORD *i; // rax
  _QWORD *v8; // rbx
  signed __int64 v9; // rax
  bool v10; // cc
  signed __int64 v11; // rax
  int v12; // ecx
  _QWORD *j; // rbx
  volatile signed __int64 *NextInterfaceForThread; // rdi
  __int64 v15; // rcx
  __int64 result; // rax
  __int64 v17; // rbp
  __int64 v18; // rsi
  __int64 v19; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // ecx
  KIRQL v28; // [rsp+40h] [rbp-68h]
  _BYTE v29[24]; // [rsp+48h] [rbp-60h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-48h] BYREF

  v1 = *(_QWORD **)(a1 + 16);
  v3 = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
  memset(v29, 0, sizeof(v29));
  if ( (Feature_CLAT_DHCP_Option108__private_featureState & 0x10) == 0 )
    ((void (*)(void))Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline)();
  memset(v29, 0, sizeof(v29));
  NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), v29, &v29[4]);
  ThreadObjectCompartmentId = *(_DWORD *)&v29[4];
  if ( !*(_DWORD *)&v29[4] )
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v5 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 19888));
  if ( !KeTestSpinLock((PKSPIN_LOCK)(v3 + 19880)) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v3 + 19888));
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 19880), &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 19888));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v6 = (_QWORD **)(*(_QWORD *)(v3 + 19872)
                 + 16LL * (ThreadObjectCompartmentId & (unsigned int)(*(_DWORD *)(v3 + 19868) - 1)));
  for ( i = *v6; ; i = (_QWORD *)*i )
  {
    if ( i == v6 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v3 + 19888));
      KeLowerIrql(v5);
      goto LABEL_15;
    }
    v8 = i - 6;
    if ( *((_DWORD *)i - 12) == ThreadObjectCompartmentId )
      break;
  }
  if ( _InterlockedIncrement64(v8 + 4) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)(v3 + 19888));
  KeLowerIrql(v5);
  if ( v8 )
  {
    *(_OWORD *)&v29[8] = *(_OWORD *)((char *)v8 + 4);
    v9 = _InterlockedExchangeAdd64(v8 + 4, 0xFFFFFFFFFFFFFFFFuLL);
    v10 = v9 <= 1;
    v11 = v9 - 1;
    if ( v10 )
    {
      if ( v11 )
        __fastfail(0xEu);
      IoQueueWorkItem((PIO_WORKITEM)v8[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v8);
    }
  }
LABEL_15:
  v12 = *(_DWORD *)(a1 + 32);
  if ( v12 )
  {
    v27 = v12 - 1;
    if ( v27 )
    {
      if ( v27 != 1 )
        return 3221225485LL;
    }
    else
    {
      memset(v1, 0, *(unsigned int *)(a1 + 24));
    }
    NextInterfaceForThread = (volatile signed __int64 *)IppGetNextInterfaceForThread(v3, v29, v1);
  }
  else
  {
    v28 = KfRaiseIrql(2u);
    memset(&LockHandle, 0, sizeof(LockHandle));
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 19904));
    if ( !KeTestSpinLock((PKSPIN_LOCK)(v3 + 19896)) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v3 + 19904));
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 19896), &LockHandle);
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 19904));
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    }
    for ( j = *(_QWORD **)(v3 + 19912); ; j = (_QWORD *)*j )
    {
      if ( j == (_QWORD *)(v3 + 19912) )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v3 + 19904));
        KeLowerIrql(v28);
        NextInterfaceForThread = 0;
        goto LABEL_25;
      }
      NextInterfaceForThread = j - 20;
      if ( !memcmp(v1, j - 18, 8u) )
        break;
    }
    if ( _InterlockedIncrement64(NextInterfaceForThread + 19) <= 1 )
      __fastfail(0xEu);
    _InterlockedDecrement((volatile signed __int32 *)(v3 + 19904));
    KeLowerIrql(v28);
    if ( j != (_QWORD *)160 )
    {
      v25 = *NextInterfaceForThread + 4;
      v26 = **(unsigned int **)NextInterfaceForThread;
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( !(unsigned __int8)NetioIsCompartmentAccessibleByThread(v26, v25, 1) )
      {
        IppDereferenceInterface(j - 20);
        NextInterfaceForThread = 0;
      }
    }
  }
LABEL_25:
  v15 = *(unsigned int *)(a1 + 32);
  if ( NextInterfaceForThread )
  {
    if ( (_DWORD)v15 )
      *v1 = *((_QWORD *)NextInterfaceForThread + 2);
    v17 = *(_QWORD *)(a1 + 40);
    v18 = *(_QWORD *)(a1 + 56);
    v19 = *(_QWORD *)(a1 + 72);
    if ( (Feature_CLAT_DHCP_Option108__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_CLAT_DHCP_Option108__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline(v15);
    if ( !IsEnabledDeviceUsageNoInline && *(_QWORD *)(a1 + 72) )
      *(_DWORD *)(a1 + 80) = 32;
    if ( (Feature_CLAT_DHCP_Option108__private_featureState & 0x10) != 0 )
      v21 = Feature_CLAT_DHCP_Option108__private_featureState & 1;
    else
      v21 = Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline(v15);
    if ( v21 )
    {
      if ( v19 )
        v24 = a1 + 80;
      else
        v24 = 0;
      if ( v18 )
        v23 = a1 + 64;
      else
        v23 = 0;
      if ( v17 )
        v22 = a1 + 48;
      else
        v22 = 0;
    }
    else
    {
      v22 = 0;
      v23 = 0;
      v24 = 0;
    }
    IppFillInterfaceData(NextInterfaceForThread, 0, v17, v18, v19, v22, v23, v24);
    IppDereferenceInterface((PVOID)NextInterfaceForThread);
    return 0;
  }
  else
  {
    result = 3221226021LL;
    if ( (_DWORD)v15 )
      return 2147483674LL;
  }
  return result;
}

```

## disassembly

```asm
0x140064f60  mov     [rsp+arg_10], rbp
0x140064f65  mov     [rsp+arg_18], rsi
0x140064f6a  push    rdi
0x140064f6b  push    r12
0x140064f6d  push    r13
0x140064f6f  push    r14
0x140064f71  push    r15
0x140064f73  sub     rsp, 80h
0x140064f7a  mov     rax, cs:__security_cookie
0x140064f81  xor     rax, rsp
0x140064f84  mov     [rsp+0A8h+var_30], rax
0x140064f89  mov     rax, [rcx]
0x140064f8c  xorps   xmm0, xmm0
0x140064f8f  mov     r15, [rcx+10h]
0x140064f93  mov     r12, rcx
0x140064f96  mov     rbp, [rax+20h]
0x140064f9a  xor     eax, eax
0x140064f9c  mov     [rsp+0A8h+var_50], rax
0x140064fa1  movups  [rsp+0A8h+var_60], xmm0
0x140064fa6  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x140064fac  test    al, 10h
0x140064fae  jnz     short loc_140064FB5
0x140064fb0  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x140064fb5  xorps   xmm0, xmm0
0x140064fb8  lea     r8, [rsp+0A8h+var_60+4]
0x140064fbd  xor     eax, eax
0x140064fbf  lea     rdx, [rsp+0A8h+var_60]
0x140064fc4  movups  [rsp+0A8h+var_60], xmm0
0x140064fc9  mov     [rsp+0A8h+var_50], rax
0x140064fce  mov     rcx, gs:188h
0x140064fd7  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x140064fde  nop     dword ptr [rax+rax+00h]
0x140064fe3  mov     esi, dword ptr [rsp+0A8h+var_60+4]
0x140064fe7  test    esi, esi
0x140064fe9  jnz     short loc_140065002
0x140064feb  mov     rcx, gs:188h
0x140064ff4  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140064ffb  nop     dword ptr [rax+rax+00h]
0x140065000  mov     esi, eax
0x140065002  mov     cl, 2; NewIrql
0x140065004  lea     rdi, [rbp+4DA8h]
0x14006500b  call    cs:__imp_KfRaiseIrql
0x140065012  nop     dword ptr [rax+rax+00h]
0x140065017  movzx   r14d, al
0x14006501b  xorps   xmm0, xmm0
0x14006501e  xor     eax, eax
0x140065020  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140065025  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14006502a  lock inc dword ptr [rdi+8]
0x14006502e  mov     rcx, rdi; SpinLock
0x140065031  call    cs:__imp_KeTestSpinLock
0x140065038  nop     dword ptr [rax+rax+00h]
0x14006503d  test    al, al
0x14006503f  jnz     short loc_14006506E
0x140065041  lock dec dword ptr [rdi+8]
0x140065045  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14006504a  mov     rcx, rdi; SpinLock
0x14006504d  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140065054  nop     dword ptr [rax+rax+00h]
0x140065059  lock inc dword ptr [rdi+8]
0x14006505d  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140065062  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140065069  nop     dword ptr [rax+rax+00h]
0x14006506e  mov     edx, [rbp+4D9Ch]
0x140065074  dec     edx
0x140065076  mov     eax, esi
0x140065078  and     rdx, rax
0x14006507b  mov     [rsp+0A8h+arg_8], rbx
0x140065083  shl     rdx, 4
0x140065087  add     rdx, [rbp+4DA0h]
0x14006508e  mov     rax, [rdx]
0x140065091  mov     r13d, 1
0x140065097  cmp     rax, rdx
0x14006509a  jz      loc_140065392
0x1400650a0  cmp     [rax-30h], esi
0x1400650a3  lea     rbx, [rax-30h]
0x1400650a7  jnz     loc_140065365
0x1400650ad  mov     eax, r13d
0x1400650b0  lock xadd [rbx+20h], rax
0x1400650b6  inc     rax
0x1400650b9  cmp     rax, r13
0x1400650bc  jle     loc_1400653D2
0x1400650c2  lock dec dword ptr [rdi+8]
0x1400650c6  movzx   ecx, r14b; NewIrql
0x1400650ca  call    cs:__imp_KeLowerIrql
0x1400650d1  nop     dword ptr [rax+rax+00h]
0x1400650d6  test    rbx, rbx
0x1400650d9  jz      short loc_140065106
0x1400650db  movups  xmm0, xmmword ptr [rbx+4]
0x1400650df  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400650e6  movups  [rsp+0A8h+var_60+8], xmm0
0x1400650eb  lock xadd [rbx+20h], rax
0x1400650f1  sub     rax, r13
0x1400650f4  jg      short loc_140065106
0x1400650f6  test    rax, rax
0x1400650f9  jz      loc_14006536D
0x1400650ff  mov     ecx, 0Eh
0x140065104  int     29h; Win8: RtlFailFast(ecx)
0x140065106  mov     ecx, [r12+20h]
0x14006510b  test    ecx, ecx
0x14006510d  jnz     loc_140065351
0x140065113  mov     cl, 2; NewIrql
0x140065115  lea     r14, [rbp+4DB8h]
0x14006511c  call    cs:__imp_KfRaiseIrql
0x140065123  nop     dword ptr [rax+rax+00h]
0x140065128  mov     [rsp+0A8h+var_68], al
0x14006512c  xorps   xmm0, xmm0
0x14006512f  xor     eax, eax
0x140065131  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140065136  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14006513b  lock inc dword ptr [r14+8]
0x140065140  mov     rcx, r14; SpinLock
0x140065143  call    cs:__imp_KeTestSpinLock
0x14006514a  nop     dword ptr [rax+rax+00h]
0x14006514f  test    al, al
0x140065151  jnz     short loc_140065182
0x140065153  lock dec dword ptr [r14+8]
0x140065158  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14006515d  mov     rcx, r14; SpinLock
0x140065160  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140065167  nop     dword ptr [rax+rax+00h]
0x14006516c  lock inc dword ptr [r14+8]
0x140065171  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140065176  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14006517d  nop     dword ptr [rax+rax+00h]
0x140065182  lea     rsi, [rbp+4DC8h]
0x140065189  mov     rbx, [rsi]
0x14006518c  nop     dword ptr [rax+00h]
0x140065190  cmp     rbx, rsi
0x140065193  jz      short loc_1400651B7
0x140065195  lea     rdi, [rbx-0A0h]
0x14006519c  mov     r8d, 8; Size
0x1400651a2  lea     rdx, [rdi+10h]; Buf2
0x1400651a6  mov     rcx, r15; Buf1
0x1400651a9  call    memcmp
0x1400651ae  test    eax, eax
0x1400651b0  jz      short loc_1400651D1
0x1400651b2  mov     rbx, [rbx]
0x1400651b5  jmp     short loc_140065190
0x1400651b7  movzx   ecx, [rsp+0A8h+var_68]; NewIrql
0x1400651bc  lock dec dword ptr [r14+8]
0x1400651c1  call    cs:__imp_KeLowerIrql
0x1400651c8  nop     dword ptr [rax+rax+00h]
0x1400651cd  xor     edi, edi
0x1400651cf  jmp     short loc_140065206
0x1400651d1  lock xadd [rdi+98h], r13
0x1400651da  inc     r13
0x1400651dd  cmp     r13, 1
0x1400651e1  jle     loc_140065407
0x1400651e7  movzx   ecx, [rsp+0A8h+var_68]; NewIrql
0x1400651ec  lock dec dword ptr [r14+8]
0x1400651f1  call    cs:__imp_KeLowerIrql
0x1400651f8  nop     dword ptr [rax+rax+00h]
0x1400651fd  test    rdi, rdi
0x140065200  jnz     loc_1400652E5
0x140065206  mov     ecx, [r12+20h]
0x14006520b  test    rdi, rdi
0x14006520e  jnz     short loc_140065252
0x140065210  test    ecx, ecx
0x140065212  mov     eax, 0C0000225h
0x140065217  mov     edx, 8000001Ah
0x14006521c  cmovnz  eax, edx
0x14006521f  mov     rbx, [rsp+0A8h+arg_8]
0x140065227  mov     rcx, [rsp+0A8h+var_30]
0x14006522c  xor     rcx, rsp; StackCookie
0x14006522f  call    __security_check_cookie
0x140065234  lea     r11, [rsp+0A8h+var_28]
0x14006523c  mov     rbp, [r11+40h]
0x140065240  mov     rsi, [r11+48h]
0x140065244  mov     rsp, r11
0x140065247  pop     r15
0x140065249  pop     r14
0x14006524b  pop     r13
0x14006524d  pop     r12
0x14006524f  pop     rdi
0x140065250  retn
0x140065252  test    ecx, ecx
0x140065254  jnz     loc_140065413
0x14006525a  mov     rbp, [r12+28h]
0x14006525f  mov     rsi, [r12+38h]
0x140065264  mov     rbx, [r12+48h]
0x140065269  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x14006526f  test    al, 10h
0x140065271  jnz     loc_140065341
0x140065277  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x14006527c  test    eax, eax
0x14006527e  jnz     short loc_140065291
0x140065280  cmp     qword ptr [r12+48h], 0
0x140065286  jz      short loc_140065291
0x140065288  mov     dword ptr [r12+50h], 20h ; ' '
0x140065291  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x140065297  test    al, 10h
0x140065299  jnz     loc_140065349
0x14006529f  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x1400652a4  test    eax, eax
0x1400652a6  jnz     loc_140065331
0x1400652ac  xor     eax, eax
0x1400652ae  xor     ecx, ecx
0x1400652b0  xor     edx, edx
0x1400652b2  mov     [rsp+0A8h+var_70], rdx
0x1400652b7  mov     r9, rsi
0x1400652ba  mov     [rsp+0A8h+var_78], rcx
0x1400652bf  mov     r8, rbp
0x1400652c2  mov     [rsp+0A8h+var_80], rax
0x1400652c7  mov     rcx, rdi
0x1400652ca  xor     edx, edx
0x1400652cc  mov     [rsp+0A8h+var_88], rbx
0x1400652d1  call    IppFillInterfaceData
0x1400652d6  mov     rcx, rdi; Context
0x1400652d9  call    IppDereferenceInterface
0x1400652de  xor     eax, eax
0x1400652e0  jmp     loc_14006521F
0x1400652e5  mov     rcx, [rdi]
0x1400652e8  xor     eax, eax
0x1400652ea  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x1400652ef  mov     r9b, 1
0x1400652f2  xorps   xmm0, xmm0
0x1400652f5  lea     rax, [rsp+0A8h+var_60]
0x1400652fa  movzx   r8d, r9b
0x1400652fe  mov     [rsp+0A8h+var_88], rax
0x140065303  lea     rdx, [rcx+4]
0x140065307  mov     ecx, [rcx]
0x140065309  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14006530e  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x140065315  nop     dword ptr [rax+rax+00h]
0x14006531a  test    al, al
0x14006531c  jnz     loc_140065206
0x140065322  mov     rcx, rdi; Context
0x140065325  call    IppDereferenceInterface
0x14006532a  xor     edi, edi
0x14006532c  jmp     loc_140065206
0x140065331  test    rbx, rbx
0x140065334  jnz     loc_1400653DE
0x14006533a  xor     edx, edx
0x14006533c  jmp     loc_1400653E3
0x140065341  and     eax, 1
0x140065344  jmp     loc_14006527C
0x140065349  and     eax, 1
0x14006534c  jmp     loc_1400652A4
0x140065351  sub     ecx, r13d
0x140065354  jz      short loc_1400653AB
0x140065356  cmp     ecx, r13d
0x140065359  jz      short loc_1400653BA
0x14006535b  mov     eax, 0C000000Dh
0x140065360  jmp     loc_14006521F
0x140065365  mov     rax, [rax]
0x140065368  jmp     loc_140065091
0x14006536d  mov     rcx, [rbx+80h]; IoWorkItem
0x140065374  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x14006537b  mov     r9, rbx; Context
0x14006537e  mov     r8d, r13d; QueueType
0x140065381  call    cs:__imp_IoQueueWorkItem
0x140065388  nop     dword ptr [rax+rax+00h]
0x14006538d  jmp     loc_140065106
0x140065392  lock dec dword ptr [rdi+8]
0x140065396  movzx   ecx, r14b; NewIrql
0x14006539a  call    cs:__imp_KeLowerIrql
0x1400653a1  nop     dword ptr [rax+rax+00h]
0x1400653a6  jmp     loc_140065106
0x1400653ab  mov     r8d, [r12+18h]; Size
0x1400653b0  xor     edx, edx; Val
0x1400653b2  mov     rcx, r15; void *
0x1400653b5  call    memset
0x1400653ba  mov     r8, r15
0x1400653bd  lea     rdx, [rsp+0A8h+var_60]
0x1400653c2  mov     rcx, rbp
0x1400653c5  call    IppGetNextInterfaceForThread
0x1400653ca  mov     rdi, rax
0x1400653cd  jmp     loc_140065206
0x1400653d2  mov     ecx, 0Eh
0x1400653d7  int     29h; Win8: RtlFailFast(ecx)
0x1400653d9  jmp     loc_1400650C2
0x1400653de  lea     rdx, [r12+50h]
0x1400653e3  test    rsi, rsi
0x1400653e6  jz      short loc_1400653FC
0x1400653e8  lea     rcx, [r12+40h]
0x1400653ed  test    rbp, rbp
0x1400653f0  jz      short loc_140065400
0x1400653f2  lea     rax, [r12+30h]
0x1400653f7  jmp     loc_1400652B2
0x1400653fc  xor     ecx, ecx
0x1400653fe  jmp     short loc_1400653ED
0x140065400  xor     eax, eax
0x140065402  jmp     loc_1400652B2
0x140065407  mov     ecx, 0Eh
0x14006540c  int     29h; Win8: RtlFailFast(ecx)
0x14006540e  jmp     loc_1400651E7
0x140065413  mov     rax, [rdi+10h]
0x140065417  mov     [r15], rax
0x14006541a  jmp     loc_14006525A
```
