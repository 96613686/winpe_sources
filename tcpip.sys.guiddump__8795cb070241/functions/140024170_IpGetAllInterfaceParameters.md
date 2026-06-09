# IpGetAllInterfaceParameters

- ea: `0x140024170`
- end: `0x14002462f`
- name: `IpGetAllInterfaceParameters`
- size: `1215`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140024170`
- `0x1400250c0`
- `0x140052dd0`
- `0x140073660`
- `0x14014e5b8`
- `0x1401c0fd0`
- `0x1401c1580`
- `0x1401c1aa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14002421b`
- `ntoskrnl!KfRaiseIrql` at `0x14002432c`
- `ntoskrnl!KfRaiseIrql` at `0x14002421b`
- `ntoskrnl!KfRaiseIrql` at `0x14002432c`
- `ntoskrnl!KeLowerIrql` at `0x1400242da`
- `ntoskrnl!KeLowerIrql` at `0x1400243d1`
- `ntoskrnl!KeLowerIrql` at `0x140024401`
- `ntoskrnl!KeLowerIrql` at `0x1400245aa`
- `ntoskrnl!KeLowerIrql` at `0x1400242da`
- `ntoskrnl!KeLowerIrql` at `0x1400243d1`
- `ntoskrnl!KeLowerIrql` at `0x140024401`
- `ntoskrnl!KeLowerIrql` at `0x1400245aa`
- `ntoskrnl!IoQueueWorkItem` at `0x140024591`
- `ntoskrnl!IoQueueWorkItem` at `0x140024591`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14002425d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140024370`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14002425d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140024370`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140024272`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140024386`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140024272`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140024386`
- `ntoskrnl!KeTestSpinLock` at `0x140024241`
- `ntoskrnl!KeTestSpinLock` at `0x140024353`
- `ntoskrnl!KeTestSpinLock` at `0x140024241`
- `ntoskrnl!KeTestSpinLock` at `0x140024353`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x14002451e`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x14002451e`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x1400241e7`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x1400241e7`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140024204`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140024204`

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
    IppFillInterfaceData(NextInterfaceForThread, 0, v17, v18, v19, v22, v23, v24, v28);
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
0x140024170  mov     [rsp+arg_10], rbp
0x140024175  mov     [rsp+arg_18], rsi
0x14002417a  push    rdi
0x14002417b  push    r12
0x14002417d  push    r13
0x14002417f  push    r14
0x140024181  push    r15
0x140024183  sub     rsp, 80h
0x14002418a  mov     rax, cs:__security_cookie
0x140024191  xor     rax, rsp
0x140024194  mov     [rsp+0A8h+var_30], rax
0x140024199  mov     rax, [rcx]
0x14002419c  xorps   xmm0, xmm0
0x14002419f  mov     r15, [rcx+10h]
0x1400241a3  mov     r12, rcx
0x1400241a6  mov     rbp, [rax+20h]
0x1400241aa  xor     eax, eax
0x1400241ac  mov     [rsp+0A8h+var_50], rax
0x1400241b1  movups  [rsp+0A8h+var_60], xmm0
0x1400241b6  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x1400241bc  test    al, 10h
0x1400241be  jnz     short loc_1400241C5
0x1400241c0  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x1400241c5  xorps   xmm0, xmm0
0x1400241c8  lea     r8, [rsp+0A8h+var_60+4]
0x1400241cd  xor     eax, eax
0x1400241cf  lea     rdx, [rsp+0A8h+var_60]
0x1400241d4  movups  [rsp+0A8h+var_60], xmm0
0x1400241d9  mov     [rsp+0A8h+var_50], rax
0x1400241de  mov     rcx, gs:188h
0x1400241e7  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x1400241ee  nop     dword ptr [rax+rax+00h]
0x1400241f3  mov     esi, dword ptr [rsp+0A8h+var_60+4]
0x1400241f7  test    esi, esi
0x1400241f9  jnz     short loc_140024212
0x1400241fb  mov     rcx, gs:188h
0x140024204  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14002420b  nop     dword ptr [rax+rax+00h]
0x140024210  mov     esi, eax
0x140024212  mov     cl, 2; NewIrql
0x140024214  lea     rdi, [rbp+4DA8h]
0x14002421b  call    cs:__imp_KfRaiseIrql
0x140024222  nop     dword ptr [rax+rax+00h]
0x140024227  movzx   r14d, al
0x14002422b  xorps   xmm0, xmm0
0x14002422e  xor     eax, eax
0x140024230  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140024235  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14002423a  lock inc dword ptr [rdi+8]
0x14002423e  mov     rcx, rdi; SpinLock
0x140024241  call    cs:__imp_KeTestSpinLock
0x140024248  nop     dword ptr [rax+rax+00h]
0x14002424d  test    al, al
0x14002424f  jnz     short loc_14002427E
0x140024251  lock dec dword ptr [rdi+8]
0x140024255  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14002425a  mov     rcx, rdi; SpinLock
0x14002425d  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140024264  nop     dword ptr [rax+rax+00h]
0x140024269  lock inc dword ptr [rdi+8]
0x14002426d  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140024272  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140024279  nop     dword ptr [rax+rax+00h]
0x14002427e  mov     edx, [rbp+4D9Ch]
0x140024284  dec     edx
0x140024286  mov     eax, esi
0x140024288  and     rdx, rax
0x14002428b  mov     [rsp+0A8h+arg_8], rbx
0x140024293  shl     rdx, 4
0x140024297  add     rdx, [rbp+4DA0h]
0x14002429e  mov     rax, [rdx]
0x1400242a1  mov     r13d, 1
0x1400242a7  cmp     rax, rdx
0x1400242aa  jz      loc_1400245A2
0x1400242b0  cmp     [rax-30h], esi
0x1400242b3  lea     rbx, [rax-30h]
0x1400242b7  jnz     loc_140024575
0x1400242bd  mov     eax, r13d
0x1400242c0  lock xadd [rbx+20h], rax
0x1400242c6  inc     rax
0x1400242c9  cmp     rax, r13
0x1400242cc  jle     loc_1400245E2
0x1400242d2  lock dec dword ptr [rdi+8]
0x1400242d6  movzx   ecx, r14b; NewIrql
0x1400242da  call    cs:__imp_KeLowerIrql
0x1400242e1  nop     dword ptr [rax+rax+00h]
0x1400242e6  test    rbx, rbx
0x1400242e9  jz      short loc_140024316
0x1400242eb  movups  xmm0, xmmword ptr [rbx+4]
0x1400242ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400242f6  movups  [rsp+0A8h+var_60+8], xmm0
0x1400242fb  lock xadd [rbx+20h], rax
0x140024301  sub     rax, r13
0x140024304  jg      short loc_140024316
0x140024306  test    rax, rax
0x140024309  jz      loc_14002457D
0x14002430f  mov     ecx, 0Eh
0x140024314  int     29h; Win8: RtlFailFast(ecx)
0x140024316  mov     ecx, [r12+20h]
0x14002431b  test    ecx, ecx
0x14002431d  jnz     loc_140024561
0x140024323  mov     cl, 2; NewIrql
0x140024325  lea     r14, [rbp+4DB8h]
0x14002432c  call    cs:__imp_KfRaiseIrql
0x140024333  nop     dword ptr [rax+rax+00h]
0x140024338  mov     [rsp+0A8h+var_68], al
0x14002433c  xorps   xmm0, xmm0
0x14002433f  xor     eax, eax
0x140024341  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140024346  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14002434b  lock inc dword ptr [r14+8]
0x140024350  mov     rcx, r14; SpinLock
0x140024353  call    cs:__imp_KeTestSpinLock
0x14002435a  nop     dword ptr [rax+rax+00h]
0x14002435f  test    al, al
0x140024361  jnz     short loc_140024392
0x140024363  lock dec dword ptr [r14+8]
0x140024368  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14002436d  mov     rcx, r14; SpinLock
0x140024370  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140024377  nop     dword ptr [rax+rax+00h]
0x14002437c  lock inc dword ptr [r14+8]
0x140024381  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140024386  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14002438d  nop     dword ptr [rax+rax+00h]
0x140024392  lea     rsi, [rbp+4DC8h]
0x140024399  mov     rbx, [rsi]
0x14002439c  nop     dword ptr [rax+00h]
0x1400243a0  cmp     rbx, rsi
0x1400243a3  jz      short loc_1400243C7
0x1400243a5  lea     rdi, [rbx-0A0h]
0x1400243ac  mov     r8d, 8; Size
0x1400243b2  lea     rdx, [rdi+10h]; Buf2
0x1400243b6  mov     rcx, r15; Buf1
0x1400243b9  call    memcmp
0x1400243be  test    eax, eax
0x1400243c0  jz      short loc_1400243E1
0x1400243c2  mov     rbx, [rbx]
0x1400243c5  jmp     short loc_1400243A0
0x1400243c7  movzx   ecx, [rsp+0A8h+var_68]; NewIrql
0x1400243cc  lock dec dword ptr [r14+8]
0x1400243d1  call    cs:__imp_KeLowerIrql
0x1400243d8  nop     dword ptr [rax+rax+00h]
0x1400243dd  xor     edi, edi
0x1400243df  jmp     short loc_140024416
0x1400243e1  lock xadd [rdi+98h], r13
0x1400243ea  inc     r13
0x1400243ed  cmp     r13, 1
0x1400243f1  jle     loc_140024617
0x1400243f7  movzx   ecx, [rsp+0A8h+var_68]; NewIrql
0x1400243fc  lock dec dword ptr [r14+8]
0x140024401  call    cs:__imp_KeLowerIrql
0x140024408  nop     dword ptr [rax+rax+00h]
0x14002440d  test    rdi, rdi
0x140024410  jnz     loc_1400244F5
0x140024416  mov     ecx, [r12+20h]
0x14002441b  test    rdi, rdi
0x14002441e  jnz     short loc_140024462
0x140024420  test    ecx, ecx
0x140024422  mov     eax, 0C0000225h
0x140024427  mov     edx, 8000001Ah
0x14002442c  cmovnz  eax, edx
0x14002442f  mov     rbx, [rsp+0A8h+arg_8]
0x140024437  mov     rcx, [rsp+0A8h+var_30]
0x14002443c  xor     rcx, rsp; StackCookie
0x14002443f  call    __security_check_cookie
0x140024444  lea     r11, [rsp+0A8h+var_28]
0x14002444c  mov     rbp, [r11+40h]
0x140024450  mov     rsi, [r11+48h]
0x140024454  mov     rsp, r11
0x140024457  pop     r15
0x140024459  pop     r14
0x14002445b  pop     r13
0x14002445d  pop     r12
0x14002445f  pop     rdi
0x140024460  retn
0x140024462  test    ecx, ecx
0x140024464  jnz     loc_140024623
0x14002446a  mov     rbp, [r12+28h]
0x14002446f  mov     rsi, [r12+38h]
0x140024474  mov     rbx, [r12+48h]
0x140024479  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x14002447f  test    al, 10h
0x140024481  jnz     loc_140024551
0x140024487  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x14002448c  test    eax, eax
0x14002448e  jnz     short loc_1400244A1
0x140024490  cmp     qword ptr [r12+48h], 0
0x140024496  jz      short loc_1400244A1
0x140024498  mov     dword ptr [r12+50h], 20h ; ' '
0x1400244a1  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x1400244a7  test    al, 10h
0x1400244a9  jnz     loc_140024559
0x1400244af  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x1400244b4  test    eax, eax
0x1400244b6  jnz     loc_140024541
0x1400244bc  xor     eax, eax
0x1400244be  xor     ecx, ecx
0x1400244c0  xor     edx, edx
0x1400244c2  mov     [rsp+0A8h+var_70], rdx
0x1400244c7  mov     r9, rsi
0x1400244ca  mov     [rsp+0A8h+var_78], rcx
0x1400244cf  mov     r8, rbp
0x1400244d2  mov     [rsp+0A8h+var_80], rax
0x1400244d7  mov     rcx, rdi
0x1400244da  xor     edx, edx
0x1400244dc  mov     [rsp+0A8h+var_88], rbx
0x1400244e1  call    IppFillInterfaceData
0x1400244e6  mov     rcx, rdi; Context
0x1400244e9  call    IppDereferenceInterface
0x1400244ee  xor     eax, eax
0x1400244f0  jmp     loc_14002442F
0x1400244f5  mov     rcx, [rdi]
0x1400244f8  xor     eax, eax
0x1400244fa  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x1400244ff  mov     r9b, 1
0x140024502  xorps   xmm0, xmm0
0x140024505  lea     rax, [rsp+0A8h+var_60]
0x14002450a  movzx   r8d, r9b
0x14002450e  mov     [rsp+0A8h+var_88], rax
0x140024513  lea     rdx, [rcx+4]
0x140024517  mov     ecx, [rcx]
0x140024519  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14002451e  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x140024525  nop     dword ptr [rax+rax+00h]
0x14002452a  test    al, al
0x14002452c  jnz     loc_140024416
0x140024532  mov     rcx, rdi; Context
0x140024535  call    IppDereferenceInterface
0x14002453a  xor     edi, edi
0x14002453c  jmp     loc_140024416
0x140024541  test    rbx, rbx
0x140024544  jnz     loc_1400245EE
0x14002454a  xor     edx, edx
0x14002454c  jmp     loc_1400245F3
0x140024551  and     eax, 1
0x140024554  jmp     loc_14002448C
0x140024559  and     eax, 1
0x14002455c  jmp     loc_1400244B4
0x140024561  sub     ecx, r13d
0x140024564  jz      short loc_1400245BB
0x140024566  cmp     ecx, r13d
0x140024569  jz      short loc_1400245CA
0x14002456b  mov     eax, 0C000000Dh
0x140024570  jmp     loc_14002442F
0x140024575  mov     rax, [rax]
0x140024578  jmp     loc_1400242A1
0x14002457d  mov     rcx, [rbx+80h]; IoWorkItem
0x140024584  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x14002458b  mov     r9, rbx; Context
0x14002458e  mov     r8d, r13d; QueueType
0x140024591  call    cs:__imp_IoQueueWorkItem
0x140024598  nop     dword ptr [rax+rax+00h]
0x14002459d  jmp     loc_140024316
0x1400245a2  lock dec dword ptr [rdi+8]
0x1400245a6  movzx   ecx, r14b; NewIrql
0x1400245aa  call    cs:__imp_KeLowerIrql
0x1400245b1  nop     dword ptr [rax+rax+00h]
0x1400245b6  jmp     loc_140024316
0x1400245bb  mov     r8d, [r12+18h]; Size
0x1400245c0  xor     edx, edx; Val
0x1400245c2  mov     rcx, r15; void *
0x1400245c5  call    memset
0x1400245ca  mov     r8, r15
0x1400245cd  lea     rdx, [rsp+0A8h+var_60]
0x1400245d2  mov     rcx, rbp
0x1400245d5  call    IppGetNextInterfaceForThread
0x1400245da  mov     rdi, rax
0x1400245dd  jmp     loc_140024416
0x1400245e2  mov     ecx, 0Eh
0x1400245e7  int     29h; Win8: RtlFailFast(ecx)
0x1400245e9  jmp     loc_1400242D2
0x1400245ee  lea     rdx, [r12+50h]
0x1400245f3  test    rsi, rsi
0x1400245f6  jz      short loc_14002460C
0x1400245f8  lea     rcx, [r12+40h]
0x1400245fd  test    rbp, rbp
0x140024600  jz      short loc_140024610
0x140024602  lea     rax, [r12+30h]
0x140024607  jmp     loc_1400244C2
0x14002460c  xor     ecx, ecx
0x14002460e  jmp     short loc_1400245FD
0x140024610  xor     eax, eax
0x140024612  jmp     loc_1400244C2
0x140024617  mov     ecx, 0Eh
0x14002461c  int     29h; Win8: RtlFailFast(ecx)
0x14002461e  jmp     loc_1400243F7
0x140024623  mov     rax, [rdi+10h]
0x140024627  mov     [r15], rax
0x14002462a  jmp     loc_14002446A
```
