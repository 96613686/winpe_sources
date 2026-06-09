# IpEnumerateAllInterfaces

- ea: `0x1400656d0`
- end: `0x140065e15`
- name: `IpEnumerateAllInterfaces`
- size: `1861`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400329e0`
- `0x1400656d0`
- `0x140065e20`
- `0x1400665b0`
- `0x1400667f0`
- `0x14014ca68`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400657cf`
- `ntoskrnl!KfRaiseIrql` at `0x1400658dd`
- `ntoskrnl!KfRaiseIrql` at `0x140065987`
- `ntoskrnl!KfRaiseIrql` at `0x140065aa0`
- `ntoskrnl!KfRaiseIrql` at `0x1400657cf`
- `ntoskrnl!KfRaiseIrql` at `0x1400658dd`
- `ntoskrnl!KfRaiseIrql` at `0x140065987`
- `ntoskrnl!KfRaiseIrql` at `0x140065aa0`
- `ntoskrnl!KeLowerIrql` at `0x140065887`
- `ntoskrnl!KeLowerIrql` at `0x140065965`
- `ntoskrnl!KeLowerIrql` at `0x140065a75`
- `ntoskrnl!KeLowerIrql` at `0x140065b29`
- `ntoskrnl!KeLowerIrql` at `0x140065da8`
- `ntoskrnl!KeLowerIrql` at `0x140065887`
- `ntoskrnl!KeLowerIrql` at `0x140065965`
- `ntoskrnl!KeLowerIrql` at `0x140065a75`
- `ntoskrnl!KeLowerIrql` at `0x140065b29`
- `ntoskrnl!KeLowerIrql` at `0x140065da8`
- `ntoskrnl!IoQueueWorkItem` at `0x140065d5f`
- `ntoskrnl!IoQueueWorkItem` at `0x140065d5f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140065812`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140065812`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065828`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065828`
- `ntoskrnl!KeTestSpinLock` at `0x1400657f5`
- `ntoskrnl!KeTestSpinLock` at `0x1400657f5`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140065798`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140065798`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400657b4`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400657b4`

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
0x1400656d0  push    rbp
0x1400656d2  push    r15
0x1400656d4  lea     rbp, [rsp-4Fh]
0x1400656d9  sub     rsp, 0F8h
0x1400656e0  mov     rax, cs:__security_cookie
0x1400656e7  xor     rax, rsp
0x1400656ea  mov     [rbp+57h+var_28], rax
0x1400656ee  xorps   xmm0, xmm0
0x1400656f1  mov     [rbp+57h+var_98], rcx
0x1400656f5  xor     eax, eax
0x1400656f7  mov     r15, rcx
0x1400656fa  movups  [rbp+57h+var_40], xmm0
0x1400656fe  mov     [rbp+57h+var_30], rax
0x140065702  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x140065708  test    al, 10h
0x14006570a  jnz     short loc_140065711
0x14006570c  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x140065711  mov     ecx, [r15+20h]
0x140065715  cmp     ecx, 1
0x140065718  jnz     loc_140065D2B
0x14006571e  mov     eax, [r15+58h]
0x140065722  lea     r8, [rbp+57h+var_40+4]
0x140065726  mov     [rbp+57h+var_B0], eax
0x140065729  lea     rdx, [rbp+57h+var_40]
0x14006572d  mov     rax, [r15]
0x140065730  xorps   xmm0, xmm0
0x140065733  mov     [rsp+100h+arg_8], rbx
0x14006573b  mov     [rsp+100h+arg_10], rsi
0x140065743  mov     [rsp+100h+arg_18], rdi
0x14006574b  xor     edi, edi
0x14006574d  mov     rbx, [rax+20h]
0x140065751  mov     rax, [r15+10h]
0x140065755  mov     [rbp+57h+var_68], rax
0x140065759  mov     rax, [r15+28h]
0x14006575d  mov     [rbp+57h+var_78], rax
0x140065761  mov     rax, [r15+38h]
0x140065765  mov     [rbp+57h+var_80], rax
0x140065769  mov     rax, [r15+48h]
0x14006576d  mov     [rbp+57h+var_70], rax
0x140065771  xor     eax, eax
0x140065773  mov     [rbp+57h+var_30], rax
0x140065777  movups  [rbp+57h+var_40], xmm0
0x14006577b  mov     rcx, gs:188h
0x140065784  mov     [rsp+100h+var_10], r12
0x14006578c  mov     [rsp+100h+var_20], r14
0x140065794  mov     [rbp+57h+var_A0], rbx
0x140065798  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x14006579f  nop     dword ptr [rax+rax+00h]
0x1400657a4  mov     esi, dword ptr [rbp+57h+var_40+4]
0x1400657a7  test    esi, esi
0x1400657a9  jnz     short loc_1400657C2
0x1400657ab  mov     rcx, gs:188h
0x1400657b4  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400657bb  nop     dword ptr [rax+rax+00h]
0x1400657c0  mov     esi, eax
0x1400657c2  lea     r12, [rbx+4DA8h]
0x1400657c9  mov     cl, 2; NewIrql
0x1400657cb  mov     [rbp+57h+SpinLock], r12
0x1400657cf  call    cs:__imp_KfRaiseIrql
0x1400657d6  nop     dword ptr [rax+rax+00h]
0x1400657db  movzx   r14d, al
0x1400657df  xorps   xmm0, xmm0
0x1400657e2  xor     eax, eax
0x1400657e4  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400657e8  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400657ec  lock inc dword ptr [r12+8]
0x1400657f2  mov     rcx, r12; SpinLock
0x1400657f5  call    cs:__imp_KeTestSpinLock
0x1400657fc  nop     dword ptr [rax+rax+00h]
0x140065801  test    al, al
0x140065803  jnz     short loc_140065834
0x140065805  lock dec dword ptr [r12+8]
0x14006580b  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14006580f  mov     rcx, r12; SpinLock
0x140065812  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140065819  nop     dword ptr [rax+rax+00h]
0x14006581e  lock inc dword ptr [r12+8]
0x140065824  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140065828  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14006582f  nop     dword ptr [rax+rax+00h]
0x140065834  mov     edx, [rbx+4D9Ch]
0x14006583a  dec     edx
0x14006583c  mov     eax, esi
0x14006583e  and     rdx, rax
0x140065841  shl     rdx, 4
0x140065845  add     rdx, [rbx+4DA0h]
0x14006584c  mov     rax, [rdx]
0x14006584f  cmp     rax, rdx
0x140065852  jz      loc_140065D9E
0x140065858  cmp     [rax-30h], esi
0x14006585b  lea     rbx, [rax-30h]
0x14006585f  jnz     loc_140065D23
0x140065865  mov     eax, 1
0x14006586a  lock xadd [rbx+20h], rax
0x140065870  inc     rax
0x140065873  cmp     rax, 1
0x140065877  jle     loc_140065DC8
0x14006587d  lock dec dword ptr [r12+8]
0x140065883  movzx   ecx, r14b; NewIrql
0x140065887  call    cs:__imp_KeLowerIrql
0x14006588e  nop     dword ptr [rax+rax+00h]
0x140065893  test    rbx, rbx
0x140065896  jz      short loc_1400658C3
0x140065898  movups  xmm0, xmmword ptr [rbx+4]
0x14006589c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400658a3  movups  [rbp+57h+var_40+8], xmm0
0x1400658a7  lock xadd [rbx+20h], rax
0x1400658ad  sub     rax, 1
0x1400658b1  jg      short loc_1400658C3
0x1400658b3  test    rax, rax
0x1400658b6  jz      loc_140065D48
0x1400658bc  mov     ecx, 0Eh
0x1400658c1  int     29h; Win8: RtlFailFast(ecx)
0x1400658c3  cmp     dword ptr [rbp+57h+var_40+4], edi
0x1400658c6  jz      loc_140065C99
0x1400658cc  mov     [rsp+100h+var_18], r13
0x1400658d4  mov     cl, 2; NewIrql
0x1400658d6  xor     r13d, r13d
0x1400658d9  mov     [rbp+57h+var_A8], r13
0x1400658dd  call    cs:__imp_KfRaiseIrql
0x1400658e4  nop     dword ptr [rax+rax+00h]
0x1400658e9  mov     r14, [rbp+57h+SpinLock]
0x1400658ed  movzx   r12d, al
0x1400658f1  mov     rcx, r14; SpinLock
0x1400658f4  call    RtlAcquireReadLockAtDpcLevel
0x1400658f9  mov     rax, [rbp+57h+var_A0]
0x1400658fd  xor     ebx, ebx
0x1400658ff  cmp     [rax+4D9Ch], ebx
0x140065905  jbe     short loc_14006595C
0x140065907  mov     r15d, ebx
0x14006590a  shl     r15, 4
0x14006590e  add     r15, [rax+4DA0h]
0x140065915  mov     rsi, [r15]
0x140065918  nop     dword ptr [rax+rax+00000000h]
0x140065920  cmp     rsi, r15
0x140065923  jnz     loc_140065C53
0x140065929  mov     rax, [rbp+57h+var_A0]
0x14006592d  inc     ebx
0x14006592f  cmp     ebx, [rax+4D9Ch]
0x140065935  jb      short loc_140065907
0x140065937  test    r13, r13
0x14006593a  jz      short loc_140065954
0x14006593c  mov     eax, 1
0x140065941  lock xadd [r13+20h], rax
0x140065947  inc     rax
0x14006594a  cmp     rax, 1
0x14006594e  jle     loc_140065DD4
0x140065954  mov     r14, [rbp+57h+SpinLock]
0x140065958  mov     r15, [rbp+57h+var_98]
0x14006595c  lock dec dword ptr [r14+8]
0x140065961  movzx   ecx, r12b; NewIrql
0x140065965  call    cs:__imp_KeLowerIrql
0x14006596c  nop     dword ptr [rax+rax+00h]
0x140065971  test    r13, r13
0x140065974  jz      loc_140065B4A
0x14006597a  lea     rsi, [r13+98h]
0x140065981  mov     cl, 2; NewIrql
0x140065983  mov     [rbp+57h+var_60], rsi
0x140065987  call    cs:__imp_KfRaiseIrql
0x14006598e  nop     dword ptr [rax+rax+00h]
0x140065993  mov     rcx, rsi; SpinLock
0x140065996  mov     [rbp+57h+var_C0], al
0x140065999  call    RtlAcquireReadLockAtDpcLevel
0x14006599e  cmp     edi, [rbp+57h+var_B0]
0x1400659a1  jnb     loc_140065CF5
0x1400659a7  mov     rbx, [rsi+10h]
0x1400659ab  lea     r12, [rsi+10h]
0x1400659af  cmp     rbx, r12
0x1400659b2  jz      loc_140065A6D
0x1400659b8  mov     r13d, [rbp+57h+var_B0]
0x1400659bc  nop     dword ptr [rax+00h]
0x1400659c0  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x1400659c6  test    al, 10h
0x1400659c8  jnz     loc_140065C91
0x1400659ce  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x1400659d3  test    eax, eax
0x1400659d5  jnz     loc_140065BA7
0x1400659db  cmp     edi, r13d
0x1400659de  jnb     short loc_140065A53
0x1400659e0  mov     rdx, [rbp+57h+var_70]
0x1400659e4  mov     ecx, edi
0x1400659e6  test    rdx, rdx
0x1400659e9  jz      loc_140065D18
0x1400659ef  mov     eax, ecx
0x1400659f1  shl     rax, 5
0x1400659f5  add     rax, rdx
0x1400659f8  xor     r10d, r10d
0x1400659fb  mov     rdx, [rbp+57h+var_80]
0x1400659ff  test    rdx, rdx
0x140065a02  jnz     loc_140065D0C
0x140065a08  mov     r9, r10
0x140065a0b  mov     rdx, [rbp+57h+var_78]
0x140065a0f  test    rdx, rdx
0x140065a12  jz      loc_140065DF4
0x140065a18  imul    r8, rcx, 0F0h
0x140065a1f  add     r8, rdx
0x140065a22  mov     rdx, [rbp+57h+var_68]
0x140065a26  test    rdx, rdx
0x140065a29  jz      loc_140065DEC
0x140065a2f  lea     rdx, [rdx+rdi*8]
0x140065a33  mov     [rsp+100h+var_C8], r10
0x140065a38  mov     [rsp+100h+var_D0], r10
0x140065a3d  mov     [rsp+100h+var_D8], r10
0x140065a42  mov     [rsp+100h+var_E0], rax
0x140065a47  lea     rcx, [rbx-0B0h]
0x140065a4e  call    IppFillInterfaceData
0x140065a53  mov     rbx, [rbx]
0x140065a56  inc     edi
0x140065a58  cmp     rbx, r12
0x140065a5b  jnz     loc_1400659C0
0x140065a61  mov     r13, [rbp+57h+var_A8]
0x140065a65  mov     r14, [rbp+57h+SpinLock]
0x140065a69  mov     rsi, [rbp+57h+var_60]
0x140065a6d  movzx   ecx, [rbp+57h+var_C0]; NewIrql
0x140065a71  lock dec dword ptr [rsi+8]
0x140065a75  call    cs:__imp_KeLowerIrql
0x140065a7c  nop     dword ptr [rax+rax+00h]
0x140065a81  mov     esi, [r13+0]
0x140065a85  mov     rcx, r13; Context
0x140065a88  call    IppDereferenceCompartment
0x140065a8d  cmp     dword ptr [rbp+57h+var_40+4], esi
0x140065a90  jz      loc_140065CFD
0x140065a96  mov     cl, 2; NewIrql
0x140065a98  mov     [rbp+57h+var_A8], 0
0x140065aa0  call    cs:__imp_KfRaiseIrql
0x140065aa7  nop     dword ptr [rax+rax+00h]
0x140065aac  mov     rcx, r14; SpinLock
0x140065aaf  movzx   r13d, al
0x140065ab3  call    RtlAcquireReadLockAtDpcLevel
0x140065ab8  mov     r8, [rbp+57h+var_A0]
0x140065abc  xor     ebx, ebx
0x140065abe  cmp     [r8+4D9Ch], ebx
0x140065ac5  jbe     short loc_140065B1D
0x140065ac7  mov     r15d, ebx
0x140065aca  shl     r15, 4
0x140065ace  add     r15, [r8+4DA0h]
0x140065ad5  mov     r14, [r15]
0x140065ad8  nop     dword ptr [rax+rax+00000000h]
0x140065ae0  cmp     r14, r15
0x140065ae3  jnz     loc_140065CA8
0x140065ae9  mov     r8, [rbp+57h+var_A0]
0x140065aed  inc     ebx
0x140065aef  cmp     ebx, [r8+4D9Ch]
0x140065af6  jb      short loc_140065AC7
0x140065af8  mov     rcx, [rbp+57h+var_A8]
0x140065afc  test    rcx, rcx
0x140065aff  jz      short loc_140065B19
0x140065b01  mov     eax, 1
0x140065b06  lock xadd [rcx+20h], rax
0x140065b0c  inc     rax
0x140065b0f  cmp     rax, 1
0x140065b13  jle     loc_140065DE0
0x140065b19  mov     r14, [rbp+57h+SpinLock]
0x140065b1d  lock dec dword ptr [r8+4DB0h]
0x140065b25  movzx   ecx, r13b; NewIrql
0x140065b29  call    cs:__imp_KeLowerIrql
0x140065b30  nop     dword ptr [rax+rax+00h]
0x140065b35  mov     r13, [rbp+57h+var_A8]
0x140065b39  mov     r15, [rbp+57h+var_98]
0x140065b3d  test    r13, r13
0x140065b40  jnz     loc_14006597A
0x140065b46  mov     r15, [rbp+57h+var_98]
0x140065b4a  mov     r13, [rsp+100h+var_18]
0x140065b52  mov     eax, [rbp+57h+var_B0]
0x140065b55  mov     r14, [rsp+100h+var_20]
0x140065b5d  mov     r12, [rsp+100h+var_10]
0x140065b65  mov     rsi, [rsp+100h+arg_10]
0x140065b6d  mov     rbx, [rsp+100h+arg_8]
0x140065b75  mov     [r15+58h], edi
0x140065b79  test    eax, eax
0x140065b7b  jz      short loc_140065B85
0x140065b7d  cmp     eax, edi
0x140065b7f  jb      loc_140065E0B
0x140065b85  xor     eax, eax
0x140065b87  mov     rdi, [rsp+100h+arg_18]
0x140065b8f  mov     rcx, [rbp+57h+var_28]
0x140065b93  xor     rcx, rsp; StackCookie
0x140065b96  call    __security_check_cookie
0x140065b9b  add     rsp, 0F8h
0x140065ba2  pop     r15
0x140065ba4  pop     rbp
0x140065ba5  retn
0x140065ba7  mov     ecx, [r15+30h]
0x140065bab  mov     r8d, [r15+40h]
0x140065baf  mov     edx, [r15+50h]
0x140065bb3  mov     [rbp+57h+var_88], ecx
0x140065bb6  mov     [rbp+57h+var_8C], r8d
0x140065bba  mov     [rbp+57h+var_90], edx
0x140065bbd  cmp     edi, r13d
0x140065bc0  jnb     loc_140065A53
0x140065bc6  mov     rsi, [rbp+57h+var_70]
0x140065bca  lea     r9, [rbp+57h+var_90]
0x140065bce  xor     eax, eax
0x140065bd0  lea     r10, [rbp+57h+var_8C]
0x140065bd4  test    rsi, rsi
0x140065bd7  lea     r11, [rbp+57h+var_88]
0x140065bdb  cmovz   r9, rax
0x140065bdf  cmp     [rbp+57h+var_80], rax
0x140065be3  cmovz   r10, rax
0x140065be7  cmp     [rbp+57h+var_78], rax
  ... truncated ...
```
