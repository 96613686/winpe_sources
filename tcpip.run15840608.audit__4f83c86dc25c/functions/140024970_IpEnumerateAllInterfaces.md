# IpEnumerateAllInterfaces

- ea: `0x140024970`
- end: `0x1400250b5`
- name: `IpEnumerateAllInterfaces`
- size: `1861`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140024970`
- `0x1400250c0`
- `0x140025850`
- `0x140025a90`
- `0x14002f9e0`
- `0x14014e5b8`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140024a6f`
- `ntoskrnl!KfRaiseIrql` at `0x140024b7d`
- `ntoskrnl!KfRaiseIrql` at `0x140024c27`
- `ntoskrnl!KfRaiseIrql` at `0x140024d40`
- `ntoskrnl!KfRaiseIrql` at `0x140024a6f`
- `ntoskrnl!KfRaiseIrql` at `0x140024b7d`
- `ntoskrnl!KfRaiseIrql` at `0x140024c27`
- `ntoskrnl!KfRaiseIrql` at `0x140024d40`
- `ntoskrnl!KeLowerIrql` at `0x140024b27`
- `ntoskrnl!KeLowerIrql` at `0x140024c05`
- `ntoskrnl!KeLowerIrql` at `0x140024d15`
- `ntoskrnl!KeLowerIrql` at `0x140024dc9`
- `ntoskrnl!KeLowerIrql` at `0x140025048`
- `ntoskrnl!KeLowerIrql` at `0x140024b27`
- `ntoskrnl!KeLowerIrql` at `0x140024c05`
- `ntoskrnl!KeLowerIrql` at `0x140024d15`
- `ntoskrnl!KeLowerIrql` at `0x140024dc9`
- `ntoskrnl!KeLowerIrql` at `0x140025048`
- `ntoskrnl!IoQueueWorkItem` at `0x140024fff`
- `ntoskrnl!IoQueueWorkItem` at `0x140024fff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140024ab2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140024ab2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140024ac8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140024ac8`
- `ntoskrnl!KeTestSpinLock` at `0x140024a95`
- `ntoskrnl!KeTestSpinLock` at `0x140024a95`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140024a38`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140024a38`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140024a54`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140024a54`

## pseudocode

```c
__int64 __fastcall IpEnumerateAllInterfaces(__int64 a1)
{
  __int64 v1; // r15
  int v2; // ecx
  __int64 v3; // rdi
  __int64 v4; // rbx
  int ThreadObjectCompartmentId; // esi
  __int64 v6; // r12
  KIRQL v7; // r14
  _QWORD **v8; // rdx
  _QWORD *i; // rax
  _QWORD *v10; // rbx
  signed __int64 v11; // rax
  bool v12; // cc
  signed __int64 v13; // rax
  int *v14; // r13
  KSPIN_LOCK *v15; // r14
  KIRQL v16; // r12
  __int64 v17; // rax
  unsigned int v18; // ebx
  int **v19; // r15
  int *j; // rsi
  volatile signed __int32 *v21; // rsi
  __int64 v22; // rcx
  char *v23; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v25; // rax
  __int64 v26; // r9
  __int64 v27; // r8
  __int64 v28; // rdx
  int v29; // esi
  KIRQL v30; // r13
  __int64 v31; // r8
  unsigned int v32; // ebx
  _QWORD **v33; // r15
  _QWORD *k; // r14
  int *v35; // rcx
  __int64 result; // rax
  int v37; // r8d
  int v38; // edx
  int *v39; // r9
  int *v40; // r10
  int *v41; // r11
  __int64 v42; // r14
  __int64 v43; // rsi
  __int64 v44; // r8
  __int64 v45; // rdx
  int *v46; // r14
  KIRQL v47; // [rsp+40h] [rbp-69h]
  KSPIN_LOCK *SpinLock; // [rsp+48h] [rbp-61h]
  unsigned int v49; // [rsp+50h] [rbp-59h]
  int *v50; // [rsp+58h] [rbp-51h]
  __int64 v51; // [rsp+60h] [rbp-49h]
  int v53; // [rsp+70h] [rbp-39h] BYREF
  int v54; // [rsp+74h] [rbp-35h] BYREF
  int v55; // [rsp+78h] [rbp-31h] BYREF
  __int64 v56; // [rsp+80h] [rbp-29h]
  __int64 v57; // [rsp+88h] [rbp-21h]
  __int64 v58; // [rsp+90h] [rbp-19h]
  __int64 v59; // [rsp+98h] [rbp-11h]
  char *v60; // [rsp+A0h] [rbp-9h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE v62[24]; // [rsp+C0h] [rbp+17h] BYREF

  v1 = a1;
  memset(v62, 0, sizeof(v62));
  if ( (Feature_CLAT_DHCP_Option108__private_featureState & 0x10) == 0 )
    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline(a1);
  v2 = *(_DWORD *)(v1 + 32);
  if ( v2 == 1 )
  {
    v49 = *(_DWORD *)(v1 + 88);
    v3 = 0;
    v4 = *(_QWORD *)(*(_QWORD *)v1 + 32LL);
    v59 = *(_QWORD *)(v1 + 16);
    v57 = *(_QWORD *)(v1 + 40);
    v56 = *(_QWORD *)(v1 + 56);
    v58 = *(_QWORD *)(v1 + 72);
    memset(v62, 0, sizeof(v62));
    v51 = v4;
    NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), v62, &v62[4]);
    ThreadObjectCompartmentId = *(_DWORD *)&v62[4];
    if ( !*(_DWORD *)&v62[4] )
      ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
    v6 = v4 + 19880;
    SpinLock = (KSPIN_LOCK *)(v4 + 19880);
    v7 = KfRaiseIrql(2u);
    memset(&LockHandle, 0, sizeof(LockHandle));
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 19888));
    if ( !KeTestSpinLock((PKSPIN_LOCK)(v4 + 19880)) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v4 + 19888));
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 19880), &LockHandle);
      _InterlockedIncrement((volatile signed __int32 *)(v4 + 19888));
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    }
    v8 = (_QWORD **)(*(_QWORD *)(v4 + 19872)
                   + 16LL * (ThreadObjectCompartmentId & (unsigned int)(*(_DWORD *)(v4 + 19868) - 1)));
    for ( i = *v8; ; i = (_QWORD *)*i )
    {
      if ( i == v8 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v6 + 8));
        KeLowerIrql(v7);
        goto LABEL_79;
      }
      v10 = i - 6;
      if ( *((_DWORD *)i - 12) == ThreadObjectCompartmentId )
        break;
    }
    if ( _InterlockedIncrement64(v10 + 4) <= 1 )
      __fastfail(0xEu);
    _InterlockedDecrement((volatile signed __int32 *)(v6 + 8));
    KeLowerIrql(v7);
    if ( v10 )
    {
      *(_OWORD *)&v62[8] = *(_OWORD *)((char *)v10 + 4);
      v11 = _InterlockedExchangeAdd64(v10 + 4, 0xFFFFFFFFFFFFFFFFuLL);
      v12 = v11 <= 1;
      v13 = v11 - 1;
      if ( v12 )
      {
        if ( v13 )
          __fastfail(0xEu);
        IoQueueWorkItem((PIO_WORKITEM)v10[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v10);
      }
    }
LABEL_79:
    if ( *(_QWORD *)v62 >= 0xFFFFFFFF )
    {
      v14 = 0;
      v50 = 0;
      v15 = SpinLock;
      v16 = KfRaiseIrql(2u);
      RtlAcquireReadLockAtDpcLevel(SpinLock);
      v17 = v51;
      v18 = 0;
      if ( *(_DWORD *)(v51 + 19868) )
      {
        do
        {
          v19 = (int **)(*(_QWORD *)(v17 + 19872) + 16LL * v18);
          for ( j = *v19; j != (int *)v19; j = *(int **)j )
          {
            v46 = j - 12;
            if ( *(j - 12) > 0
              && (unsigned __int8)IppIsCompartmentAccessibleByThread((unsigned int *)j - 12, (__int64)v62, 0)
              && (!v14 || *v46 < *v14) )
            {
              v14 = j - 12;
              v50 = j - 12;
              if ( *v46 == 1 )
                goto LABEL_21;
            }
          }
          v17 = v51;
          ++v18;
        }
        while ( v18 < *(_DWORD *)(v51 + 19868) );
LABEL_21:
        if ( v14 && _InterlockedIncrement64((volatile signed __int64 *)v14 + 4) <= 1 )
          __fastfail(0xEu);
        v15 = SpinLock;
        v1 = a1;
      }
      _InterlockedDecrement((volatile signed __int32 *)v15 + 2);
      KeLowerIrql(v16);
      if ( v14 )
      {
        do
        {
          v21 = v14 + 38;
          v60 = (char *)(v14 + 38);
          v47 = KfRaiseIrql(2u);
          RtlAcquireReadLockAtDpcLevel((PKSPIN_LOCK)v14 + 19);
          if ( (unsigned int)v3 >= v49 )
          {
            v3 = (unsigned int)(v14[46] + v3);
          }
          else
          {
            v23 = (char *)*((_QWORD *)v14 + 21);
            if ( v23 != (char *)(v14 + 42) )
            {
              do
              {
                if ( (Feature_CLAT_DHCP_Option108__private_featureState & 0x10) != 0 )
                  IsEnabledDeviceUsageNoInline = Feature_CLAT_DHCP_Option108__private_featureState & 1;
                else
                  IsEnabledDeviceUsageNoInline = Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline(v22);
                if ( IsEnabledDeviceUsageNoInline )
                {
                  v22 = *(unsigned int *)(v1 + 48);
                  v37 = *(_DWORD *)(v1 + 64);
                  v38 = *(_DWORD *)(v1 + 80);
                  v55 = *(_DWORD *)(v1 + 48);
                  v54 = v37;
                  v53 = v38;
                  if ( (unsigned int)v3 < v49 )
                  {
                    v39 = &v53;
                    v40 = &v54;
                    v41 = &v55;
                    if ( !v58 )
                      v39 = 0;
                    if ( !v56 )
                      v40 = 0;
                    if ( !v57 )
                      v41 = 0;
                    if ( v58 )
                      v42 = v58 + (unsigned int)(v3 * v38);
                    else
                      v42 = 0;
                    if ( v56 )
                      v43 = v56 + (unsigned int)(v3 * v37);
                    else
                      v43 = 0;
                    if ( v57 )
                      v44 = v57 + (unsigned int)(v3 * v22);
                    else
                      v44 = 0;
                    if ( v59 )
                      v45 = v59 + 8 * v3;
                    else
                      v45 = 0;
                    IppFillInterfaceData(v23 - 176, v45, v44, v43, v42, v41, v40, v39);
                  }
                }
                else if ( (unsigned int)v3 < v49 )
                {
                  if ( v58 )
                    v25 = v58 + 32LL * (unsigned int)v3;
                  else
                    v25 = 0;
                  if ( v56 )
                    v26 = v56 + 88LL * (unsigned int)v3;
                  else
                    v26 = 0;
                  if ( v57 )
                    v27 = v57 + 240LL * (unsigned int)v3;
                  else
                    v27 = 0;
                  if ( v59 )
                    v28 = v59 + 8 * v3;
                  else
                    v28 = 0;
                  IppFillInterfaceData(v23 - 176, v28, v27, v26, v25, 0, 0, 0);
                }
                v23 = *(char **)v23;
                v3 = (unsigned int)(v3 + 1);
              }
              while ( v23 != (char *)(v14 + 42) );
              v14 = v50;
              v15 = SpinLock;
              v21 = (volatile signed __int32 *)v60;
            }
          }
          _InterlockedDecrement(v21 + 2);
          KeLowerIrql(v47);
          v29 = *v14;
          IppDereferenceCompartment(v14);
          if ( *(_DWORD *)&v62[4] == v29 && *(_DWORD *)v62 != -1 )
            break;
          v50 = 0;
          v30 = KfRaiseIrql(2u);
          RtlAcquireReadLockAtDpcLevel(v15);
          v31 = v51;
          v32 = 0;
          if ( *(_DWORD *)(v51 + 19868) )
          {
            while ( 2 )
            {
              v33 = (_QWORD **)(*(_QWORD *)(v31 + 19872) + 16LL * v32);
              for ( k = *v33; k != v33; k = (_QWORD *)*k )
              {
                if ( *((_DWORD *)k - 12) > v29
                  && (unsigned __int8)IppIsCompartmentAccessibleByThread((unsigned int *)k - 12, (__int64)v62, 0)
                  && (!v50 || *((_DWORD *)k - 12) < *v50) )
                {
                  v35 = (int *)(k - 6);
                  v50 = (int *)(k - 6);
                  if ( *((_DWORD *)k - 12) == v29 + 1 )
                  {
                    v31 = v51;
                    goto LABEL_48;
                  }
                }
              }
              v31 = v51;
              if ( ++v32 < *(_DWORD *)(v51 + 19868) )
                continue;
              break;
            }
            v35 = v50;
LABEL_48:
            if ( v35 && _InterlockedIncrement64((volatile signed __int64 *)v35 + 4) <= 1 )
              __fastfail(0xEu);
            v15 = SpinLock;
          }
          _InterlockedDecrement((volatile signed __int32 *)(v31 + 19888));
          KeLowerIrql(v30);
          v14 = v50;
          v1 = a1;
        }
        while ( v50 );
        v1 = a1;
      }
    }
    *(_DWORD *)(v1 + 88) = v3;
    if ( v49 && v49 < (unsigned int)v3 )
      return 261;
    else
      return 0;
  }
  else
  {
    result = 3221225474LL;
    if ( v2 && v2 != 2 )
      return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x140024970  push    rbp
0x140024972  push    r15
0x140024974  lea     rbp, [rsp-4Fh]
0x140024979  sub     rsp, 0F8h
0x140024980  mov     rax, cs:__security_cookie
0x140024987  xor     rax, rsp
0x14002498a  mov     [rbp+57h+var_28], rax
0x14002498e  xorps   xmm0, xmm0
0x140024991  mov     [rbp+57h+var_98], rcx
0x140024995  xor     eax, eax
0x140024997  mov     r15, rcx
0x14002499a  movups  [rbp+57h+var_40], xmm0
0x14002499e  mov     [rbp+57h+var_30], rax
0x1400249a2  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x1400249a8  test    al, 10h
0x1400249aa  jnz     short loc_1400249B1
0x1400249ac  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x1400249b1  mov     ecx, [r15+20h]
0x1400249b5  cmp     ecx, 1
0x1400249b8  jnz     loc_140024FCB
0x1400249be  mov     eax, [r15+58h]
0x1400249c2  lea     r8, [rbp+57h+var_40+4]
0x1400249c6  mov     [rbp+57h+var_B0], eax
0x1400249c9  lea     rdx, [rbp+57h+var_40]
0x1400249cd  mov     rax, [r15]
0x1400249d0  xorps   xmm0, xmm0
0x1400249d3  mov     [rsp+100h+arg_8], rbx
0x1400249db  mov     [rsp+100h+arg_10], rsi
0x1400249e3  mov     [rsp+100h+arg_18], rdi
0x1400249eb  xor     edi, edi
0x1400249ed  mov     rbx, [rax+20h]
0x1400249f1  mov     rax, [r15+10h]
0x1400249f5  mov     [rbp+57h+var_68], rax
0x1400249f9  mov     rax, [r15+28h]
0x1400249fd  mov     [rbp+57h+var_78], rax
0x140024a01  mov     rax, [r15+38h]
0x140024a05  mov     [rbp+57h+var_80], rax
0x140024a09  mov     rax, [r15+48h]
0x140024a0d  mov     [rbp+57h+var_70], rax
0x140024a11  xor     eax, eax
0x140024a13  mov     [rbp+57h+var_30], rax
0x140024a17  movups  [rbp+57h+var_40], xmm0
0x140024a1b  mov     rcx, gs:188h
0x140024a24  mov     [rsp+100h+var_10], r12
0x140024a2c  mov     [rsp+100h+var_20], r14
0x140024a34  mov     [rbp+57h+var_A0], rbx
0x140024a38  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x140024a3f  nop     dword ptr [rax+rax+00h]
0x140024a44  mov     esi, dword ptr [rbp+57h+var_40+4]
0x140024a47  test    esi, esi
0x140024a49  jnz     short loc_140024A62
0x140024a4b  mov     rcx, gs:188h
0x140024a54  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140024a5b  nop     dword ptr [rax+rax+00h]
0x140024a60  mov     esi, eax
0x140024a62  lea     r12, [rbx+4DA8h]
0x140024a69  mov     cl, 2; NewIrql
0x140024a6b  mov     [rbp+57h+SpinLock], r12
0x140024a6f  call    cs:__imp_KfRaiseIrql
0x140024a76  nop     dword ptr [rax+rax+00h]
0x140024a7b  movzx   r14d, al
0x140024a7f  xorps   xmm0, xmm0
0x140024a82  xor     eax, eax
0x140024a84  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140024a88  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140024a8c  lock inc dword ptr [r12+8]
0x140024a92  mov     rcx, r12; SpinLock
0x140024a95  call    cs:__imp_KeTestSpinLock
0x140024a9c  nop     dword ptr [rax+rax+00h]
0x140024aa1  test    al, al
0x140024aa3  jnz     short loc_140024AD4
0x140024aa5  lock dec dword ptr [r12+8]
0x140024aab  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140024aaf  mov     rcx, r12; SpinLock
0x140024ab2  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140024ab9  nop     dword ptr [rax+rax+00h]
0x140024abe  lock inc dword ptr [r12+8]
0x140024ac4  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140024ac8  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140024acf  nop     dword ptr [rax+rax+00h]
0x140024ad4  mov     edx, [rbx+4D9Ch]
0x140024ada  dec     edx
0x140024adc  mov     eax, esi
0x140024ade  and     rdx, rax
0x140024ae1  shl     rdx, 4
0x140024ae5  add     rdx, [rbx+4DA0h]
0x140024aec  mov     rax, [rdx]
0x140024aef  cmp     rax, rdx
0x140024af2  jz      loc_14002503E
0x140024af8  cmp     [rax-30h], esi
0x140024afb  lea     rbx, [rax-30h]
0x140024aff  jnz     loc_140024FC3
0x140024b05  mov     eax, 1
0x140024b0a  lock xadd [rbx+20h], rax
0x140024b10  inc     rax
0x140024b13  cmp     rax, 1
0x140024b17  jle     loc_140025068
0x140024b1d  lock dec dword ptr [r12+8]
0x140024b23  movzx   ecx, r14b; NewIrql
0x140024b27  call    cs:__imp_KeLowerIrql
0x140024b2e  nop     dword ptr [rax+rax+00h]
0x140024b33  test    rbx, rbx
0x140024b36  jz      short loc_140024B63
0x140024b38  movups  xmm0, xmmword ptr [rbx+4]
0x140024b3c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140024b43  movups  [rbp+57h+var_40+8], xmm0
0x140024b47  lock xadd [rbx+20h], rax
0x140024b4d  sub     rax, 1
0x140024b51  jg      short loc_140024B63
0x140024b53  test    rax, rax
0x140024b56  jz      loc_140024FE8
0x140024b5c  mov     ecx, 0Eh
0x140024b61  int     29h; Win8: RtlFailFast(ecx)
0x140024b63  cmp     dword ptr [rbp+57h+var_40+4], edi
0x140024b66  jz      loc_140024F39
0x140024b6c  mov     [rsp+100h+var_18], r13
0x140024b74  mov     cl, 2; NewIrql
0x140024b76  xor     r13d, r13d
0x140024b79  mov     [rbp+57h+var_A8], r13
0x140024b7d  call    cs:__imp_KfRaiseIrql
0x140024b84  nop     dword ptr [rax+rax+00h]
0x140024b89  mov     r14, [rbp+57h+SpinLock]
0x140024b8d  movzx   r12d, al
0x140024b91  mov     rcx, r14; SpinLock
0x140024b94  call    RtlAcquireReadLockAtDpcLevel
0x140024b99  mov     rax, [rbp+57h+var_A0]
0x140024b9d  xor     ebx, ebx
0x140024b9f  cmp     [rax+4D9Ch], ebx
0x140024ba5  jbe     short loc_140024BFC
0x140024ba7  mov     r15d, ebx
0x140024baa  shl     r15, 4
0x140024bae  add     r15, [rax+4DA0h]
0x140024bb5  mov     rsi, [r15]
0x140024bb8  nop     dword ptr [rax+rax+00000000h]
0x140024bc0  cmp     rsi, r15
0x140024bc3  jnz     loc_140024EF3
0x140024bc9  mov     rax, [rbp+57h+var_A0]
0x140024bcd  inc     ebx
0x140024bcf  cmp     ebx, [rax+4D9Ch]
0x140024bd5  jb      short loc_140024BA7
0x140024bd7  test    r13, r13
0x140024bda  jz      short loc_140024BF4
0x140024bdc  mov     eax, 1
0x140024be1  lock xadd [r13+20h], rax
0x140024be7  inc     rax
0x140024bea  cmp     rax, 1
0x140024bee  jle     loc_140025074
0x140024bf4  mov     r14, [rbp+57h+SpinLock]
0x140024bf8  mov     r15, [rbp+57h+var_98]
0x140024bfc  lock dec dword ptr [r14+8]
0x140024c01  movzx   ecx, r12b; NewIrql
0x140024c05  call    cs:__imp_KeLowerIrql
0x140024c0c  nop     dword ptr [rax+rax+00h]
0x140024c11  test    r13, r13
0x140024c14  jz      loc_140024DEA
0x140024c1a  lea     rsi, [r13+98h]
0x140024c21  mov     cl, 2; NewIrql
0x140024c23  mov     [rbp+57h+var_60], rsi
0x140024c27  call    cs:__imp_KfRaiseIrql
0x140024c2e  nop     dword ptr [rax+rax+00h]
0x140024c33  mov     rcx, rsi; SpinLock
0x140024c36  mov     [rbp+57h+var_C0], al
0x140024c39  call    RtlAcquireReadLockAtDpcLevel
0x140024c3e  cmp     edi, [rbp+57h+var_B0]
0x140024c41  jnb     loc_140024F95
0x140024c47  mov     rbx, [rsi+10h]
0x140024c4b  lea     r12, [rsi+10h]
0x140024c4f  cmp     rbx, r12
0x140024c52  jz      loc_140024D0D
0x140024c58  mov     r13d, [rbp+57h+var_B0]
0x140024c5c  nop     dword ptr [rax+00h]
0x140024c60  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x140024c66  test    al, 10h
0x140024c68  jnz     loc_140024F31
0x140024c6e  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x140024c73  test    eax, eax
0x140024c75  jnz     loc_140024E47
0x140024c7b  cmp     edi, r13d
0x140024c7e  jnb     short loc_140024CF3
0x140024c80  mov     rdx, [rbp+57h+var_70]
0x140024c84  mov     ecx, edi
0x140024c86  test    rdx, rdx
0x140024c89  jz      loc_140024FB8
0x140024c8f  mov     eax, ecx
0x140024c91  shl     rax, 5
0x140024c95  add     rax, rdx
0x140024c98  xor     r10d, r10d
0x140024c9b  mov     rdx, [rbp+57h+var_80]
0x140024c9f  test    rdx, rdx
0x140024ca2  jnz     loc_140024FAC
0x140024ca8  mov     r9, r10
0x140024cab  mov     rdx, [rbp+57h+var_78]
0x140024caf  test    rdx, rdx
0x140024cb2  jz      loc_140025094
0x140024cb8  imul    r8, rcx, 0F0h
0x140024cbf  add     r8, rdx
0x140024cc2  mov     rdx, [rbp+57h+var_68]
0x140024cc6  test    rdx, rdx
0x140024cc9  jz      loc_14002508C
0x140024ccf  lea     rdx, [rdx+rdi*8]
0x140024cd3  mov     [rsp+100h+var_C8], r10
0x140024cd8  mov     [rsp+100h+var_D0], r10
0x140024cdd  mov     [rsp+100h+var_D8], r10
0x140024ce2  mov     [rsp+100h+var_E0], rax
0x140024ce7  lea     rcx, [rbx-0B0h]
0x140024cee  call    IppFillInterfaceData
0x140024cf3  mov     rbx, [rbx]
0x140024cf6  inc     edi
0x140024cf8  cmp     rbx, r12
0x140024cfb  jnz     loc_140024C60
0x140024d01  mov     r13, [rbp+57h+var_A8]
0x140024d05  mov     r14, [rbp+57h+SpinLock]
0x140024d09  mov     rsi, [rbp+57h+var_60]
0x140024d0d  movzx   ecx, [rbp+57h+var_C0]; NewIrql
0x140024d11  lock dec dword ptr [rsi+8]
0x140024d15  call    cs:__imp_KeLowerIrql
0x140024d1c  nop     dword ptr [rax+rax+00h]
0x140024d21  mov     esi, [r13+0]
0x140024d25  mov     rcx, r13; Context
0x140024d28  call    IppDereferenceCompartment
0x140024d2d  cmp     dword ptr [rbp+57h+var_40+4], esi
0x140024d30  jz      loc_140024F9D
0x140024d36  mov     cl, 2; NewIrql
0x140024d38  mov     [rbp+57h+var_A8], 0
0x140024d40  call    cs:__imp_KfRaiseIrql
0x140024d47  nop     dword ptr [rax+rax+00h]
0x140024d4c  mov     rcx, r14; SpinLock
0x140024d4f  movzx   r13d, al
0x140024d53  call    RtlAcquireReadLockAtDpcLevel
0x140024d58  mov     r8, [rbp+57h+var_A0]
0x140024d5c  xor     ebx, ebx
0x140024d5e  cmp     [r8+4D9Ch], ebx
0x140024d65  jbe     short loc_140024DBD
0x140024d67  mov     r15d, ebx
0x140024d6a  shl     r15, 4
0x140024d6e  add     r15, [r8+4DA0h]
0x140024d75  mov     r14, [r15]
0x140024d78  nop     dword ptr [rax+rax+00000000h]
0x140024d80  cmp     r14, r15
0x140024d83  jnz     loc_140024F48
0x140024d89  mov     r8, [rbp+57h+var_A0]
0x140024d8d  inc     ebx
0x140024d8f  cmp     ebx, [r8+4D9Ch]
0x140024d96  jb      short loc_140024D67
0x140024d98  mov     rcx, [rbp+57h+var_A8]
0x140024d9c  test    rcx, rcx
0x140024d9f  jz      short loc_140024DB9
0x140024da1  mov     eax, 1
0x140024da6  lock xadd [rcx+20h], rax
0x140024dac  inc     rax
0x140024daf  cmp     rax, 1
0x140024db3  jle     loc_140025080
0x140024db9  mov     r14, [rbp+57h+SpinLock]
0x140024dbd  lock dec dword ptr [r8+4DB0h]
0x140024dc5  movzx   ecx, r13b; NewIrql
0x140024dc9  call    cs:__imp_KeLowerIrql
0x140024dd0  nop     dword ptr [rax+rax+00h]
0x140024dd5  mov     r13, [rbp+57h+var_A8]
0x140024dd9  mov     r15, [rbp+57h+var_98]
0x140024ddd  test    r13, r13
0x140024de0  jnz     loc_140024C1A
0x140024de6  mov     r15, [rbp+57h+var_98]
0x140024dea  mov     r13, [rsp+100h+var_18]
0x140024df2  mov     eax, [rbp+57h+var_B0]
0x140024df5  mov     r14, [rsp+100h+var_20]
0x140024dfd  mov     r12, [rsp+100h+var_10]
0x140024e05  mov     rsi, [rsp+100h+arg_10]
0x140024e0d  mov     rbx, [rsp+100h+arg_8]
0x140024e15  mov     [r15+58h], edi
0x140024e19  test    eax, eax
0x140024e1b  jz      short loc_140024E25
0x140024e1d  cmp     eax, edi
0x140024e1f  jb      loc_1400250AB
0x140024e25  xor     eax, eax
0x140024e27  mov     rdi, [rsp+100h+arg_18]
0x140024e2f  mov     rcx, [rbp+57h+var_28]
0x140024e33  xor     rcx, rsp; StackCookie
0x140024e36  call    __security_check_cookie
0x140024e3b  add     rsp, 0F8h
0x140024e42  pop     r15
0x140024e44  pop     rbp
0x140024e45  retn
0x140024e47  mov     ecx, [r15+30h]
0x140024e4b  mov     r8d, [r15+40h]
0x140024e4f  mov     edx, [r15+50h]
0x140024e53  mov     [rbp+57h+var_88], ecx
0x140024e56  mov     [rbp+57h+var_8C], r8d
0x140024e5a  mov     [rbp+57h+var_90], edx
0x140024e5d  cmp     edi, r13d
0x140024e60  jnb     loc_140024CF3
0x140024e66  mov     rsi, [rbp+57h+var_70]
0x140024e6a  lea     r9, [rbp+57h+var_90]
0x140024e6e  xor     eax, eax
0x140024e70  lea     r10, [rbp+57h+var_8C]
0x140024e74  test    rsi, rsi
0x140024e77  lea     r11, [rbp+57h+var_88]
0x140024e7b  cmovz   r9, rax
0x140024e7f  cmp     [rbp+57h+var_80], rax
0x140024e83  cmovz   r10, rax
0x140024e87  cmp     [rbp+57h+var_78], rax
  ... truncated ...
```
