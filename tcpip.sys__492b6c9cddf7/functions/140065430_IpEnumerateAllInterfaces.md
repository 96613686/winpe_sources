# IpEnumerateAllInterfaces

- ea: `0x140065430`
- end: `0x140065b75`
- name: `IpEnumerateAllInterfaces`
- size: `1861`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140032740`
- `0x140065430`
- `0x140065b80`
- `0x140066310`
- `0x140066550`
- `0x14014c8d8`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14006552f`
- `ntoskrnl!KfRaiseIrql` at `0x14006563d`
- `ntoskrnl!KfRaiseIrql` at `0x1400656e7`
- `ntoskrnl!KfRaiseIrql` at `0x140065800`
- `ntoskrnl!KfRaiseIrql` at `0x14006552f`
- `ntoskrnl!KfRaiseIrql` at `0x14006563d`
- `ntoskrnl!KfRaiseIrql` at `0x1400656e7`
- `ntoskrnl!KfRaiseIrql` at `0x140065800`
- `ntoskrnl!KeLowerIrql` at `0x1400655e7`
- `ntoskrnl!KeLowerIrql` at `0x1400656c5`
- `ntoskrnl!KeLowerIrql` at `0x1400657d5`
- `ntoskrnl!KeLowerIrql` at `0x140065889`
- `ntoskrnl!KeLowerIrql` at `0x140065b08`
- `ntoskrnl!KeLowerIrql` at `0x1400655e7`
- `ntoskrnl!KeLowerIrql` at `0x1400656c5`
- `ntoskrnl!KeLowerIrql` at `0x1400657d5`
- `ntoskrnl!KeLowerIrql` at `0x140065889`
- `ntoskrnl!KeLowerIrql` at `0x140065b08`
- `ntoskrnl!IoQueueWorkItem` at `0x140065abf`
- `ntoskrnl!IoQueueWorkItem` at `0x140065abf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140065572`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140065572`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065588`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065588`
- `ntoskrnl!KeTestSpinLock` at `0x140065555`
- `ntoskrnl!KeTestSpinLock` at `0x140065555`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x1400654f8`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x1400654f8`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140065514`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140065514`

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
0x140065430  push    rbp
0x140065432  push    r15
0x140065434  lea     rbp, [rsp-4Fh]
0x140065439  sub     rsp, 0F8h
0x140065440  mov     rax, cs:__security_cookie
0x140065447  xor     rax, rsp
0x14006544a  mov     [rbp+57h+var_28], rax
0x14006544e  xorps   xmm0, xmm0
0x140065451  mov     [rbp+57h+var_98], rcx
0x140065455  xor     eax, eax
0x140065457  mov     r15, rcx
0x14006545a  movups  [rbp+57h+var_40], xmm0
0x14006545e  mov     [rbp+57h+var_30], rax
0x140065462  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x140065468  test    al, 10h
0x14006546a  jnz     short loc_140065471
0x14006546c  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x140065471  mov     ecx, [r15+20h]
0x140065475  cmp     ecx, 1
0x140065478  jnz     loc_140065A8B
0x14006547e  mov     eax, [r15+58h]
0x140065482  lea     r8, [rbp+57h+var_40+4]
0x140065486  mov     [rbp+57h+var_B0], eax
0x140065489  lea     rdx, [rbp+57h+var_40]
0x14006548d  mov     rax, [r15]
0x140065490  xorps   xmm0, xmm0
0x140065493  mov     [rsp+100h+arg_8], rbx
0x14006549b  mov     [rsp+100h+arg_10], rsi
0x1400654a3  mov     [rsp+100h+arg_18], rdi
0x1400654ab  xor     edi, edi
0x1400654ad  mov     rbx, [rax+20h]
0x1400654b1  mov     rax, [r15+10h]
0x1400654b5  mov     [rbp+57h+var_68], rax
0x1400654b9  mov     rax, [r15+28h]
0x1400654bd  mov     [rbp+57h+var_78], rax
0x1400654c1  mov     rax, [r15+38h]
0x1400654c5  mov     [rbp+57h+var_80], rax
0x1400654c9  mov     rax, [r15+48h]
0x1400654cd  mov     [rbp+57h+var_70], rax
0x1400654d1  xor     eax, eax
0x1400654d3  mov     [rbp+57h+var_30], rax
0x1400654d7  movups  [rbp+57h+var_40], xmm0
0x1400654db  mov     rcx, gs:188h
0x1400654e4  mov     [rsp+100h+var_10], r12
0x1400654ec  mov     [rsp+100h+var_20], r14
0x1400654f4  mov     [rbp+57h+var_A0], rbx
0x1400654f8  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x1400654ff  nop     dword ptr [rax+rax+00h]
0x140065504  mov     esi, dword ptr [rbp+57h+var_40+4]
0x140065507  test    esi, esi
0x140065509  jnz     short loc_140065522
0x14006550b  mov     rcx, gs:188h
0x140065514  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14006551b  nop     dword ptr [rax+rax+00h]
0x140065520  mov     esi, eax
0x140065522  lea     r12, [rbx+4DA8h]
0x140065529  mov     cl, 2; NewIrql
0x14006552b  mov     [rbp+57h+SpinLock], r12
0x14006552f  call    cs:__imp_KfRaiseIrql
0x140065536  nop     dword ptr [rax+rax+00h]
0x14006553b  movzx   r14d, al
0x14006553f  xorps   xmm0, xmm0
0x140065542  xor     eax, eax
0x140065544  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140065548  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14006554c  lock inc dword ptr [r12+8]
0x140065552  mov     rcx, r12; SpinLock
0x140065555  call    cs:__imp_KeTestSpinLock
0x14006555c  nop     dword ptr [rax+rax+00h]
0x140065561  test    al, al
0x140065563  jnz     short loc_140065594
0x140065565  lock dec dword ptr [r12+8]
0x14006556b  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14006556f  mov     rcx, r12; SpinLock
0x140065572  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140065579  nop     dword ptr [rax+rax+00h]
0x14006557e  lock inc dword ptr [r12+8]
0x140065584  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140065588  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14006558f  nop     dword ptr [rax+rax+00h]
0x140065594  mov     edx, [rbx+4D9Ch]
0x14006559a  dec     edx
0x14006559c  mov     eax, esi
0x14006559e  and     rdx, rax
0x1400655a1  shl     rdx, 4
0x1400655a5  add     rdx, [rbx+4DA0h]
0x1400655ac  mov     rax, [rdx]
0x1400655af  cmp     rax, rdx
0x1400655b2  jz      loc_140065AFE
0x1400655b8  cmp     [rax-30h], esi
0x1400655bb  lea     rbx, [rax-30h]
0x1400655bf  jnz     loc_140065A83
0x1400655c5  mov     eax, 1
0x1400655ca  lock xadd [rbx+20h], rax
0x1400655d0  inc     rax
0x1400655d3  cmp     rax, 1
0x1400655d7  jle     loc_140065B28
0x1400655dd  lock dec dword ptr [r12+8]
0x1400655e3  movzx   ecx, r14b; NewIrql
0x1400655e7  call    cs:__imp_KeLowerIrql
0x1400655ee  nop     dword ptr [rax+rax+00h]
0x1400655f3  test    rbx, rbx
0x1400655f6  jz      short loc_140065623
0x1400655f8  movups  xmm0, xmmword ptr [rbx+4]
0x1400655fc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140065603  movups  [rbp+57h+var_40+8], xmm0
0x140065607  lock xadd [rbx+20h], rax
0x14006560d  sub     rax, 1
0x140065611  jg      short loc_140065623
0x140065613  test    rax, rax
0x140065616  jz      loc_140065AA8
0x14006561c  mov     ecx, 0Eh
0x140065621  int     29h; Win8: RtlFailFast(ecx)
0x140065623  cmp     dword ptr [rbp+57h+var_40+4], edi
0x140065626  jz      loc_1400659F9
0x14006562c  mov     [rsp+100h+var_18], r13
0x140065634  mov     cl, 2; NewIrql
0x140065636  xor     r13d, r13d
0x140065639  mov     [rbp+57h+var_A8], r13
0x14006563d  call    cs:__imp_KfRaiseIrql
0x140065644  nop     dword ptr [rax+rax+00h]
0x140065649  mov     r14, [rbp+57h+SpinLock]
0x14006564d  movzx   r12d, al
0x140065651  mov     rcx, r14; SpinLock
0x140065654  call    RtlAcquireReadLockAtDpcLevel
0x140065659  mov     rax, [rbp+57h+var_A0]
0x14006565d  xor     ebx, ebx
0x14006565f  cmp     [rax+4D9Ch], ebx
0x140065665  jbe     short loc_1400656BC
0x140065667  mov     r15d, ebx
0x14006566a  shl     r15, 4
0x14006566e  add     r15, [rax+4DA0h]
0x140065675  mov     rsi, [r15]
0x140065678  nop     dword ptr [rax+rax+00000000h]
0x140065680  cmp     rsi, r15
0x140065683  jnz     loc_1400659B3
0x140065689  mov     rax, [rbp+57h+var_A0]
0x14006568d  inc     ebx
0x14006568f  cmp     ebx, [rax+4D9Ch]
0x140065695  jb      short loc_140065667
0x140065697  test    r13, r13
0x14006569a  jz      short loc_1400656B4
0x14006569c  mov     eax, 1
0x1400656a1  lock xadd [r13+20h], rax
0x1400656a7  inc     rax
0x1400656aa  cmp     rax, 1
0x1400656ae  jle     loc_140065B34
0x1400656b4  mov     r14, [rbp+57h+SpinLock]
0x1400656b8  mov     r15, [rbp+57h+var_98]
0x1400656bc  lock dec dword ptr [r14+8]
0x1400656c1  movzx   ecx, r12b; NewIrql
0x1400656c5  call    cs:__imp_KeLowerIrql
0x1400656cc  nop     dword ptr [rax+rax+00h]
0x1400656d1  test    r13, r13
0x1400656d4  jz      loc_1400658AA
0x1400656da  lea     rsi, [r13+98h]
0x1400656e1  mov     cl, 2; NewIrql
0x1400656e3  mov     [rbp+57h+var_60], rsi
0x1400656e7  call    cs:__imp_KfRaiseIrql
0x1400656ee  nop     dword ptr [rax+rax+00h]
0x1400656f3  mov     rcx, rsi; SpinLock
0x1400656f6  mov     [rbp+57h+var_C0], al
0x1400656f9  call    RtlAcquireReadLockAtDpcLevel
0x1400656fe  cmp     edi, [rbp+57h+var_B0]
0x140065701  jnb     loc_140065A55
0x140065707  mov     rbx, [rsi+10h]
0x14006570b  lea     r12, [rsi+10h]
0x14006570f  cmp     rbx, r12
0x140065712  jz      loc_1400657CD
0x140065718  mov     r13d, [rbp+57h+var_B0]
0x14006571c  nop     dword ptr [rax+00h]
0x140065720  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x140065726  test    al, 10h
0x140065728  jnz     loc_1400659F1
0x14006572e  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x140065733  test    eax, eax
0x140065735  jnz     loc_140065907
0x14006573b  cmp     edi, r13d
0x14006573e  jnb     short loc_1400657B3
0x140065740  mov     rdx, [rbp+57h+var_70]
0x140065744  mov     ecx, edi
0x140065746  test    rdx, rdx
0x140065749  jz      loc_140065A78
0x14006574f  mov     eax, ecx
0x140065751  shl     rax, 5
0x140065755  add     rax, rdx
0x140065758  xor     r10d, r10d
0x14006575b  mov     rdx, [rbp+57h+var_80]
0x14006575f  test    rdx, rdx
0x140065762  jnz     loc_140065A6C
0x140065768  mov     r9, r10
0x14006576b  mov     rdx, [rbp+57h+var_78]
0x14006576f  test    rdx, rdx
0x140065772  jz      loc_140065B54
0x140065778  imul    r8, rcx, 0F0h
0x14006577f  add     r8, rdx
0x140065782  mov     rdx, [rbp+57h+var_68]
0x140065786  test    rdx, rdx
0x140065789  jz      loc_140065B4C
0x14006578f  lea     rdx, [rdx+rdi*8]
0x140065793  mov     [rsp+100h+var_C8], r10
0x140065798  mov     [rsp+100h+var_D0], r10
0x14006579d  mov     [rsp+100h+var_D8], r10
0x1400657a2  mov     [rsp+100h+var_E0], rax
0x1400657a7  lea     rcx, [rbx-0B0h]
0x1400657ae  call    IppFillInterfaceData
0x1400657b3  mov     rbx, [rbx]
0x1400657b6  inc     edi
0x1400657b8  cmp     rbx, r12
0x1400657bb  jnz     loc_140065720
0x1400657c1  mov     r13, [rbp+57h+var_A8]
0x1400657c5  mov     r14, [rbp+57h+SpinLock]
0x1400657c9  mov     rsi, [rbp+57h+var_60]
0x1400657cd  movzx   ecx, [rbp+57h+var_C0]; NewIrql
0x1400657d1  lock dec dword ptr [rsi+8]
0x1400657d5  call    cs:__imp_KeLowerIrql
0x1400657dc  nop     dword ptr [rax+rax+00h]
0x1400657e1  mov     esi, [r13+0]
0x1400657e5  mov     rcx, r13; Context
0x1400657e8  call    IppDereferenceCompartment
0x1400657ed  cmp     dword ptr [rbp+57h+var_40+4], esi
0x1400657f0  jz      loc_140065A5D
0x1400657f6  mov     cl, 2; NewIrql
0x1400657f8  mov     [rbp+57h+var_A8], 0
0x140065800  call    cs:__imp_KfRaiseIrql
0x140065807  nop     dword ptr [rax+rax+00h]
0x14006580c  mov     rcx, r14; SpinLock
0x14006580f  movzx   r13d, al
0x140065813  call    RtlAcquireReadLockAtDpcLevel
0x140065818  mov     r8, [rbp+57h+var_A0]
0x14006581c  xor     ebx, ebx
0x14006581e  cmp     [r8+4D9Ch], ebx
0x140065825  jbe     short loc_14006587D
0x140065827  mov     r15d, ebx
0x14006582a  shl     r15, 4
0x14006582e  add     r15, [r8+4DA0h]
0x140065835  mov     r14, [r15]
0x140065838  nop     dword ptr [rax+rax+00000000h]
0x140065840  cmp     r14, r15
0x140065843  jnz     loc_140065A08
0x140065849  mov     r8, [rbp+57h+var_A0]
0x14006584d  inc     ebx
0x14006584f  cmp     ebx, [r8+4D9Ch]
0x140065856  jb      short loc_140065827
0x140065858  mov     rcx, [rbp+57h+var_A8]
0x14006585c  test    rcx, rcx
0x14006585f  jz      short loc_140065879
0x140065861  mov     eax, 1
0x140065866  lock xadd [rcx+20h], rax
0x14006586c  inc     rax
0x14006586f  cmp     rax, 1
0x140065873  jle     loc_140065B40
0x140065879  mov     r14, [rbp+57h+SpinLock]
0x14006587d  lock dec dword ptr [r8+4DB0h]
0x140065885  movzx   ecx, r13b; NewIrql
0x140065889  call    cs:__imp_KeLowerIrql
0x140065890  nop     dword ptr [rax+rax+00h]
0x140065895  mov     r13, [rbp+57h+var_A8]
0x140065899  mov     r15, [rbp+57h+var_98]
0x14006589d  test    r13, r13
0x1400658a0  jnz     loc_1400656DA
0x1400658a6  mov     r15, [rbp+57h+var_98]
0x1400658aa  mov     r13, [rsp+100h+var_18]
0x1400658b2  mov     eax, [rbp+57h+var_B0]
0x1400658b5  mov     r14, [rsp+100h+var_20]
0x1400658bd  mov     r12, [rsp+100h+var_10]
0x1400658c5  mov     rsi, [rsp+100h+arg_10]
0x1400658cd  mov     rbx, [rsp+100h+arg_8]
0x1400658d5  mov     [r15+58h], edi
0x1400658d9  test    eax, eax
0x1400658db  jz      short loc_1400658E5
0x1400658dd  cmp     eax, edi
0x1400658df  jb      loc_140065B6B
0x1400658e5  xor     eax, eax
0x1400658e7  mov     rdi, [rsp+100h+arg_18]
0x1400658ef  mov     rcx, [rbp+57h+var_28]
0x1400658f3  xor     rcx, rsp; StackCookie
0x1400658f6  call    __security_check_cookie
0x1400658fb  add     rsp, 0F8h
0x140065902  pop     r15
0x140065904  pop     rbp
0x140065905  retn
0x140065907  mov     ecx, [r15+30h]
0x14006590b  mov     r8d, [r15+40h]
0x14006590f  mov     edx, [r15+50h]
0x140065913  mov     [rbp+57h+var_88], ecx
0x140065916  mov     [rbp+57h+var_8C], r8d
0x14006591a  mov     [rbp+57h+var_90], edx
0x14006591d  cmp     edi, r13d
0x140065920  jnb     loc_1400657B3
0x140065926  mov     rsi, [rbp+57h+var_70]
0x14006592a  lea     r9, [rbp+57h+var_90]
0x14006592e  xor     eax, eax
0x140065930  lea     r10, [rbp+57h+var_8C]
0x140065934  test    rsi, rsi
0x140065937  lea     r11, [rbp+57h+var_88]
0x14006593b  cmovz   r9, rax
0x14006593f  cmp     [rbp+57h+var_80], rax
0x140065943  cmovz   r10, rax
0x140065947  cmp     [rbp+57h+var_78], rax
  ... truncated ...
```
