# SpLogWriteCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x140028e80`
- end: `0x140029448`
- name: `?SpLogWriteCallback@@YAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `1480`
- prototype: `int(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001e160`
- `0x140025710`
- `0x140028e80`
- `0x14002952c`
- `0x14003e198`
- `0x140048d70`
- `0x140048f9c`
- `0x140049740`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140029037`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029287`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029037`
- `ntoskrnl!KeWaitForSingleObject` at `0x140029287`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400290da`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029234`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400293db`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400290da`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140029234`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400293db`
- `ntoskrnl!IofCompleteRequest` at `0x14002941f`
- `ntoskrnl!IofCompleteRequest` at `0x14002941f`
- `ntoskrnl!KeClearEvent` at `0x140028ec0`
- `ntoskrnl!KeClearEvent` at `0x140028ec0`
- `ntoskrnl!KeReleaseMutex` at `0x140029058`
- `ntoskrnl!KeReleaseMutex` at `0x140029058`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140028ed5`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029179`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029295`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140028ed5`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029179`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140029295`
- `ntoskrnl!KeDelayExecutionThread` at `0x140029250`
- `ntoskrnl!KeDelayExecutionThread` at `0x140029250`

## pseudocode

```c
__int64 __fastcall SpLogWriteCallback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  char *DeviceExtension; // r14
  unsigned __int64 v6; // r12
  unsigned int v7; // edx
  int v8; // ebx
  bool v9; // zf
  struct _LIST_ENTRY *v10; // rcx
  struct _LIST_ENTRY *Flink; // rax
  unsigned __int64 RecommendedBytes; // r13
  unsigned __int64 v13; // rdi
  __int64 v14; // r15
  SIO_LOG *v15; // rcx
  __int64 v16; // rcx
  int v17; // ebx
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r8
  struct _LIST_ENTRY *v21; // rbx
  unsigned int v22; // r15d
  struct _LIST_ENTRY *v23; // rcx
  struct _LIST_ENTRY *v24; // r10
  struct _LIST_ENTRY *v25; // rcx
  struct _LIST_ENTRY *v26; // rax
  struct _LIST_ENTRY *v27; // rcx
  struct _LIST_ENTRY *v28; // rax
  struct _LIST_ENTRY *v29; // rcx
  struct _LIST_ENTRY *v30; // rax
  struct _LIST_ENTRY *v31; // rcx
  struct _LIST_ENTRY *v32; // rax
  _QWORD *v33; // rcx
  __int64 v34; // rax
  IRP *v35; // rcx
  unsigned int v37; // [rsp+30h] [rbp-38h]
  int v38; // [rsp+34h] [rbp-34h]
  unsigned __int64 v39; // [rsp+38h] [rbp-30h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+40h] [rbp-28h] BYREF
  _QWORD *v41; // [rsp+48h] [rbp-20h] BYREF
  struct _LIST_ENTRY *Blink; // [rsp+50h] [rbp-18h]
  unsigned int v43; // [rsp+B0h] [rbp+48h]

  DeviceExtension = (char *)a1->DeviceExtension;
  Blink = (struct _LIST_ENTRY *)&v41;
  v39 = 0;
  Interval.QuadPart = 0;
  v41 = &v41;
  v6 = 0;
  KeClearEvent((PRKEVENT)(DeviceExtension + 2624));
  if ( !*((_QWORD *)DeviceExtension + 332) )
    *((_QWORD *)DeviceExtension + 332) = KeQueryUnbiasedInterruptTime();
  v8 = SP_DEVICE::AcquireRundownSharedNonQueued((SP_DEVICE *)(DeviceExtension + 8));
  if ( v8 < 0 )
  {
    v9 = v41[1] == (_QWORD)&v41;
LABEL_5:
    if ( v9 )
    {
      v10 = Blink;
      if ( Blink->Flink == (struct _LIST_ENTRY *)&v41 && a2->Flink->Blink == a2 && a2->Blink->Flink == a2 )
      {
        Blink->Flink = a2;
        Blink = a2->Blink;
        Blink->Flink = (struct _LIST_ENTRY *)&v41;
        Flink = a2->Flink;
        a2->Blink = v10;
        if ( Flink->Blink == a2 && v10->Flink == a2 )
        {
          v10->Flink = Flink;
          Flink->Blink = v10;
          a2->Blink = a2;
          a2->Flink = a2;
          goto LABEL_60;
        }
      }
    }
    goto LABEL_65;
  }
  if ( _InterlockedExchange((volatile __int32 *)DeviceExtension + 662, 0) != -1058602977 )
  {
    v37 = 0;
    RecommendedBytes = 0;
    v43 = 0;
    v13 = -1;
    v14 = *((_QWORD *)DeviceExtension + 404);
    v15 = *(SIO_LOG **)(v14 + 376);
    v38 = *(_DWORD *)(v14 + 132);
    if ( !*((_DWORD *)v15 + 75) )
      RecommendedBytes = SIO_LOG::GetRecommendedBytes(v15, v7);
    v16 = *(_QWORD *)(v14 + 376);
    if ( !*(_BYTE *)(v16 + 252) )
    {
      if ( *(_DWORD *)(v16 + 280) < 0x64u )
      {
        SIO_LOG::GetCheckpointDistance((SIO_LOG *)v16, &v39);
        v16 = *(_QWORD *)(v14 + 376);
        v6 = v39;
        v13 = *(_QWORD *)(v16 + 272);
        if ( v13 >= 4LL * *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 66) )
          v13 = 4LL * *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 66);
      }
      if ( v6 >= v13 )
      {
        SIO_LOG::FlushSynchronous((SIO_LOG *)v16);
        KeWaitForSingleObject((PVOID)(v14 + 1184), Executive, 0, 0, 0);
        v17 = SIO_LOG::WriteCheckpoint(*(SIO_LOG **)(v14 + 376), 1u);
        KeReleaseMutex((PRKMUTEX)(v14 + 1184), 0);
        if ( v17 >= 0 )
        {
          SIO_LOG::GetCheckpointDistance(*(SIO_LOG **)(v14 + 376), &v39);
          v6 = v39;
          *(_DWORD *)(*(_QWORD *)(v14 + 376) + 280LL) = 0;
        }
        _InterlockedExchange64(
          (volatile __int64 *)(*(_QWORD *)(v14 + 376) + 272LL),
          v6 + *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 66));
        v18 = *(_QWORD *)(v14 + 376);
        v13 = 4LL * *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 66);
        if ( *(_QWORD *)(v18 + 272) < v13 )
          v13 = *(_QWORD *)(v18 + 272);
      }
    }
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31));
    v21 = a2->Flink;
    v22 = v37;
    while ( v21 != a2 )
    {
      if ( v6 >= v13 )
        break;
      v23 = v21[1].Flink;
      v20 = (unsigned int)(v38 + LODWORD(v23->Blink));
      v19 = v20;
      if ( RecommendedBytes < v20 )
        break;
      v24 = v21->Flink;
      BYTE1(v23->Flink) = 82;
      LODWORD(v21[-8].Blink) = 0;
      v25 = v21->Flink;
      if ( v21->Flink->Blink != v21 )
        goto LABEL_65;
      v26 = v21->Blink;
      if ( v26->Flink != v21 )
        goto LABEL_65;
      v26->Flink = v25;
      v25->Blink = v26;
      v27 = Blink;
      if ( Blink->Flink != (struct _LIST_ENTRY *)&v41 )
        goto LABEL_65;
      ++v43;
      v28 = v21;
      v21->Blink = Blink;
      v21 = v24;
      RecommendedBytes -= v20;
      v22 += v20;
      v6 += v20;
      v28->Flink = (struct _LIST_ENTRY *)&v41;
      v27->Flink = v28;
      Blink = v28;
      *((_QWORD *)DeviceExtension + 332) = KeQueryUnbiasedInterruptTime();
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_di(WPP_GLOBAL_Control->AttachedDevice, v19, v20, v43, v22);
    }
    if ( a2->Flink == a2 )
    {
      v8 = 0;
      goto LABEL_60;
    }
    if ( v41 == &v41 )
    {
      if ( v6 < 4LL * *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 66) )
      {
        Interval.QuadPart = -6000000000LL;
        KeWaitForSingleObject(DeviceExtension + 2624, Executive, 0, 0, &Interval);
        v8 = 0;
        if ( KeQueryUnbiasedInterruptTime() - *((_QWORD *)DeviceExtension + 332) > 0x165A0BC00LL )
        {
          if ( (_QWORD **)v41[1] == &v41 )
          {
            v29 = Blink;
            if ( Blink->Flink == (struct _LIST_ENTRY *)&v41 && a2->Flink->Blink == a2 && a2->Blink->Flink == a2 )
            {
              Blink->Flink = a2;
              Blink = a2->Blink;
              Blink->Flink = (struct _LIST_ENTRY *)&v41;
              v30 = a2->Flink;
              a2->Blink = v29;
              if ( v30->Blink == a2 && v29->Flink == a2 )
              {
                v29->Flink = v30;
                v8 = -1073740693;
                v30->Blink = v29;
                a2->Blink = a2;
                a2->Flink = a2;
                goto LABEL_60;
              }
            }
          }
LABEL_65:
          __fastfail(3u);
        }
      }
      else
      {
        v8 = SP_DEVICE::AcquireRundownSharedNonQueued((SP_DEVICE *)(DeviceExtension + 8));
        if ( v8 < 0 )
        {
          v9 = v41[1] == (_QWORD)&v41;
          goto LABEL_5;
        }
        ++*(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeviceExtension + 404) + 376LL) + 280LL);
        ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31));
        Interval.QuadPart = -1000000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
    }
    else
    {
      v8 = 0;
    }
    SP_WORKITEM::InsertList(DeviceExtension + 1768, a2, 1u, 0);
    goto LABEL_60;
  }
  if ( (_QWORD **)v41[1] != &v41 )
    goto LABEL_65;
  v31 = Blink;
  if ( Blink->Flink != (struct _LIST_ENTRY *)&v41 )
    goto LABEL_65;
  if ( a2->Flink->Blink != a2 )
    goto LABEL_65;
  if ( a2->Blink->Flink != a2 )
    goto LABEL_65;
  Blink->Flink = a2;
  Blink = a2->Blink;
  Blink->Flink = (struct _LIST_ENTRY *)&v41;
  v32 = a2->Flink;
  a2->Blink = v31;
  if ( v32->Blink != a2 || v31->Flink != a2 )
    goto LABEL_65;
  v31->Flink = v32;
  v8 = -1073740693;
  v32->Blink = v31;
  a2->Blink = a2;
  a2->Flink = a2;
  ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 31));
LABEL_60:
  while ( 1 )
  {
    v33 = v41;
    if ( v41 == &v41 )
      return 0;
    if ( (_QWORD **)v41[1] != &v41 )
      goto LABEL_65;
    v34 = *v41;
    if ( *(_QWORD **)(*v41 + 8LL) != v41 )
      goto LABEL_65;
    v41 = (_QWORD *)*v41;
    *(_QWORD *)(v34 + 8) = &v41;
    v35 = (IRP *)(v33 - 21);
    v35->IoStatus.Status = v8;
    IofCompleteRequest(v35, 0);
  }
}

```

## disassembly

```asm
0x140028e80  push    rbp
0x140028e82  push    rbx
0x140028e83  push    rsi
0x140028e84  push    rdi
0x140028e85  push    r12
0x140028e87  push    r13
0x140028e89  push    r14
0x140028e8b  push    r15
0x140028e8d  mov     rbp, rsp
0x140028e90  sub     rsp, 68h
0x140028e94  mov     r14, [rcx+40h]
0x140028e98  lea     rax, [rbp+var_20]
0x140028e9c  xor     r15d, r15d
0x140028e9f  mov     [rbp+var_18], rax
0x140028ea3  lea     rax, [rbp+var_20]
0x140028ea7  mov     [rbp+var_30], r15
0x140028eab  mov     rsi, rdx
0x140028eae  mov     qword ptr [rbp+Interval], r15
0x140028eb2  lea     rcx, [r14+0A40h]; Event
0x140028eb9  mov     [rbp+var_20], rax
0x140028ebd  mov     r12d, r15d
0x140028ec0  call    cs:__imp_KeClearEvent
0x140028ec7  nop     dword ptr [rax+rax+00h]
0x140028ecc  cmp     [r14+0A60h], r15
0x140028ed3  jnz     short loc_140028EE8
0x140028ed5  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140028edc  nop     dword ptr [rax+rax+00h]
0x140028ee1  mov     [r14+0A60h], rax
0x140028ee8  lea     rcx, [r14+8]; this
0x140028eec  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x140028ef1  mov     ebx, eax
0x140028ef3  test    eax, eax
0x140028ef5  jns     short loc_140028F73
0x140028ef7  mov     rcx, [rbp+var_20]
0x140028efb  lea     rax, [rbp+var_20]
0x140028eff  cmp     [rcx+8], rax
0x140028f03  jnz     loc_140029441
0x140028f09  mov     rcx, [rbp+var_18]
0x140028f0d  lea     rax, [rbp+var_20]
0x140028f11  cmp     [rcx], rax
0x140028f14  jnz     loc_140029441
0x140028f1a  mov     rax, [rsi]
0x140028f1d  cmp     [rax+8], rsi
0x140028f21  jnz     loc_140029441
0x140028f27  mov     rax, [rsi+8]
0x140028f2b  cmp     [rax], rsi
0x140028f2e  jnz     loc_140029441
0x140028f34  mov     [rcx], rsi
0x140028f37  lea     rdx, [rbp+var_20]
0x140028f3b  mov     rax, [rsi+8]
0x140028f3f  mov     [rbp+var_18], rax
0x140028f43  mov     [rax], rdx
0x140028f46  mov     rax, [rsi]
0x140028f49  mov     [rsi+8], rcx
0x140028f4d  cmp     [rax+8], rsi
0x140028f51  jnz     loc_140029441
0x140028f57  cmp     [rcx], rsi
0x140028f5a  jnz     loc_140029441
0x140028f60  mov     [rcx], rax
0x140028f63  mov     [rax+8], rcx
0x140028f67  mov     [rsi+8], rsi
0x140028f6b  mov     [rsi], rsi
0x140028f6e  jmp     loc_1400293E7
0x140028f73  mov     eax, r15d
0x140028f76  xchg    eax, [r14+0A58h]
0x140028f7d  cmp     eax, 0C0E7001Fh
0x140028f82  jz      loc_140029358
0x140028f88  mov     [rbp+var_38], r15d
0x140028f8c  mov     r13, r15
0x140028f8f  mov     [rbp+arg_0], r15d
0x140028f93  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140028f97  mov     r15, [r14+0CA0h]
0x140028f9e  xor     ebx, ebx
0x140028fa0  mov     rcx, [r15+178h]; this
0x140028fa7  mov     eax, [r15+84h]
0x140028fae  mov     [rbp+var_34], eax
0x140028fb1  cmp     [rcx+12Ch], ebx
0x140028fb7  jnz     short loc_140028FC1
0x140028fb9  call    ?GetRecommendedBytes@SIO_LOG@@QEAA_KK@Z; SIO_LOG::GetRecommendedBytes(ulong)
0x140028fbe  mov     r13, rax
0x140028fc1  mov     rcx, [r15+178h]; this
0x140028fc8  cmp     [rcx+0FCh], bl
0x140028fce  jnz     loc_1400290D3
0x140028fd4  cmp     dword ptr [rcx+118h], 64h ; 'd'
0x140028fdb  jnb     short loc_140029012
0x140028fdd  lea     rdx, [rbp+var_30]; unsigned __int64 *
0x140028fe1  call    ?GetCheckpointDistance@SIO_LOG@@QEAAJPEA_K@Z; SIO_LOG::GetCheckpointDistance(unsigned __int64 *)
0x140028fe6  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140028fed  mov     rcx, [r15+178h]; this
0x140028ff4  mov     r12, [rbp+var_30]
0x140028ff8  mov     rdx, [rax+210h]
0x140028fff  mov     rdi, [rcx+110h]
0x140029006  shl     rdx, 2
0x14002900a  cmp     rdi, rdx
0x14002900d  jb      short loc_140029012
0x14002900f  mov     rdi, rdx
0x140029012  cmp     r12, rdi
0x140029015  jb      loc_1400290D3
0x14002901b  call    ?FlushSynchronous@SIO_LOG@@QEAAJXZ; SIO_LOG::FlushSynchronous(void)
0x140029020  lea     rdi, [r15+4A0h]
0x140029027  mov     [rsp+68h+Timeout], rbx; Timeout
0x14002902c  mov     rcx, rdi; Object
0x14002902f  xor     r9d, r9d; Alertable
0x140029032  xor     r8d, r8d; WaitMode
0x140029035  xor     edx, edx; WaitReason
0x140029037  call    cs:__imp_KeWaitForSingleObject
0x14002903e  nop     dword ptr [rax+rax+00h]
0x140029043  mov     rcx, [r15+178h]; this
0x14002904a  mov     dl, 1; unsigned __int8
0x14002904c  call    ?WriteCheckpoint@SIO_LOG@@QEAAJE@Z; SIO_LOG::WriteCheckpoint(uchar)
0x140029051  xor     edx, edx; Wait
0x140029053  mov     rcx, rdi; Mutex
0x140029056  mov     ebx, eax
0x140029058  call    cs:__imp_KeReleaseMutex
0x14002905f  nop     dword ptr [rax+rax+00h]
0x140029064  test    ebx, ebx
0x140029066  js      short loc_14002908D
0x140029068  mov     rcx, [r15+178h]; this
0x14002906f  lea     rdx, [rbp+var_30]; unsigned __int64 *
0x140029073  call    ?GetCheckpointDistance@SIO_LOG@@QEAAJPEA_K@Z; SIO_LOG::GetCheckpointDistance(unsigned __int64 *)
0x140029078  mov     rax, [r15+178h]
0x14002907f  mov     r12, [rbp+var_30]
0x140029083  mov     dword ptr [rax+118h], 0
0x14002908d  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140029094  mov     rdx, [rax+210h]
0x14002909b  mov     rax, [r15+178h]
0x1400290a2  add     rdx, r12
0x1400290a5  xchg    rdx, [rax+110h]
0x1400290ac  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400290b3  mov     rdi, [rax+210h]
0x1400290ba  mov     rax, [r15+178h]
0x1400290c1  shl     rdi, 2
0x1400290c5  mov     rcx, [rax+110h]
0x1400290cc  cmp     rcx, rdi
0x1400290cf  cmovb   rdi, rcx
0x1400290d3  mov     rcx, [r14+0F8h]; RunRefCacheAware
0x1400290da  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400290e1  nop     dword ptr [rax+rax+00h]
0x1400290e6  mov     rbx, [rsi]
0x1400290e9  mov     r15d, [rbp+var_38]
0x1400290ed  cmp     rbx, rsi
0x1400290f0  jz      loc_140029191
0x1400290f6  cmp     r12, rdi
0x1400290f9  jnb     loc_140029191
0x1400290ff  mov     rcx, [rbx+10h]
0x140029103  mov     r8d, [rcx+8]
0x140029107  add     r8d, [rbp+var_34]
0x14002910b  mov     edx, r8d
0x14002910e  cmp     r13, rdx
0x140029111  jb      short loc_140029191
0x140029113  mov     r10, [rbx]
0x140029116  mov     byte ptr [rcx+1], 52h ; 'R'
0x14002911a  mov     dword ptr [rbx-78h], 0
0x140029121  mov     rcx, [rbx]
0x140029124  cmp     [rcx+8], rbx
0x140029128  jnz     loc_140029441
0x14002912e  lea     r9, [rbx+8]
0x140029132  mov     rax, [r9]
0x140029135  cmp     [rax], rbx
0x140029138  jnz     loc_140029441
0x14002913e  mov     [rax], rcx
0x140029141  mov     [rcx+8], rax
0x140029145  lea     rax, [rbp+var_20]
0x140029149  mov     rcx, [rbp+var_18]
0x14002914d  cmp     [rcx], rax
0x140029150  jnz     loc_140029441
0x140029156  inc     [rbp+arg_0]
0x140029159  mov     rax, rbx
0x14002915c  mov     [r9], rcx
0x14002915f  mov     rbx, r10
0x140029162  lea     r10, [rbp+var_20]
0x140029166  sub     r13, rdx
0x140029169  add     r15d, r8d
0x14002916c  add     r12, rdx
0x14002916f  mov     [rax], r10
0x140029172  mov     [rcx], rax
0x140029175  mov     [rbp+var_18], rax
0x140029179  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140029180  nop     dword ptr [rax+rax+00h]
0x140029185  mov     [r14+0A60h], rax
0x14002918c  jmp     loc_1400290ED
0x140029191  mov     rcx, cs:WPP_GLOBAL_Control
0x140029198  lea     rax, WPP_GLOBAL_Control
0x14002919f  cmp     rcx, rax
0x1400291a2  jz      short loc_1400291C8
0x1400291a4  test    dword ptr [rcx+2Ch], 100h
0x1400291ab  jz      short loc_1400291C8
0x1400291ad  cmp     byte ptr [rcx+29h], 3
0x1400291b1  jb      short loc_1400291C8
0x1400291b3  mov     r9d, [rbp+arg_0]
0x1400291b7  mov     rcx, [rcx+18h]
0x1400291bb  mov     eax, r15d
0x1400291be  mov     [rsp+68h+Timeout], rax
0x1400291c3  call    WPP_SF_di
0x1400291c8  cmp     [rsi], rsi
0x1400291cb  jnz     short loc_1400291D4
0x1400291cd  xor     ebx, ebx
0x1400291cf  jmp     loc_1400293E7
0x1400291d4  lea     rax, [rbp+var_20]
0x1400291d8  cmp     [rbp+var_20], rax
0x1400291dc  jnz     loc_14002933C
0x1400291e2  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400291e9  mov     rcx, [rax+210h]
0x1400291f0  shl     rcx, 2
0x1400291f4  cmp     r12, rcx
0x1400291f7  jb      short loc_140029261
0x1400291f9  lea     rcx, [r14+8]; this
0x1400291fd  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x140029202  mov     ebx, eax
0x140029204  test    eax, eax
0x140029206  jns     short loc_140029219
0x140029208  mov     rax, [rbp+var_20]
0x14002920c  lea     rcx, [rbp+var_20]
0x140029210  cmp     [rax+8], rcx
0x140029214  jmp     loc_140028F03
0x140029219  mov     rax, [r14+0CA0h]
0x140029220  mov     rcx, [rax+178h]
0x140029227  inc     dword ptr [rcx+118h]
0x14002922d  mov     rcx, [r14+0F8h]; RunRefCacheAware
0x140029234  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002923b  nop     dword ptr [rax+rax+00h]
0x140029240  lea     r8, [rbp+Interval]; Interval
0x140029244  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFF0BDC0h
0x14002924c  xor     edx, edx; Alertable
0x14002924e  xor     ecx, ecx; WaitMode
0x140029250  call    cs:__imp_KeDelayExecutionThread
0x140029257  nop     dword ptr [rax+rax+00h]
0x14002925c  jmp     loc_14002933E
0x140029261  mov     rax, 0FFFFFFFE9A5F4400h
0x14002926b  lea     rcx, [r14+0A40h]; Object
0x140029272  mov     qword ptr [rbp+Interval], rax
0x140029276  xor     r9d, r9d; Alertable
0x140029279  lea     rax, [rbp+Interval]
0x14002927d  xor     r8d, r8d; WaitMode
0x140029280  xor     edx, edx; WaitReason
0x140029282  mov     [rsp+68h+Timeout], rax; Timeout
0x140029287  call    cs:__imp_KeWaitForSingleObject
0x14002928e  nop     dword ptr [rax+rax+00h]
0x140029293  xor     ebx, ebx
0x140029295  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002929c  nop     dword ptr [rax+rax+00h]
0x1400292a1  sub     rax, [r14+0A60h]
0x1400292a8  mov     rcx, 165A0BC00h
0x1400292b2  cmp     rax, rcx
0x1400292b5  jbe     loc_14002933E
0x1400292bb  mov     rax, [rbp+var_20]
0x1400292bf  lea     rcx, [rbp+var_20]
0x1400292c3  cmp     [rax+8], rcx
0x1400292c7  jnz     loc_140029441
0x1400292cd  mov     rcx, [rbp+var_18]
0x1400292d1  lea     rax, [rbp+var_20]
0x1400292d5  cmp     [rcx], rax
0x1400292d8  jnz     loc_140029441
0x1400292de  mov     rax, [rsi]
0x1400292e1  cmp     [rax+8], rsi
0x1400292e5  jnz     loc_140029441
0x1400292eb  mov     rax, [rsi+8]
0x1400292ef  cmp     [rax], rsi
0x1400292f2  jnz     loc_140029441
0x1400292f8  mov     [rcx], rsi
0x1400292fb  lea     rdx, [rbp+var_20]
0x1400292ff  mov     rax, [rsi+8]
0x140029303  mov     [rbp+var_18], rax
0x140029307  mov     [rax], rdx
0x14002930a  mov     rax, [rsi]
0x14002930d  mov     [rsi+8], rcx
0x140029311  cmp     [rax+8], rsi
0x140029315  jnz     loc_140029441
0x14002931b  cmp     [rcx], rsi
0x14002931e  jnz     loc_140029441
0x140029324  mov     [rcx], rax
0x140029327  mov     ebx, 0C000046Bh
0x14002932c  mov     [rax+8], rcx
0x140029330  mov     [rsi+8], rsi
0x140029334  mov     [rsi], rsi
0x140029337  jmp     loc_1400293E7
0x14002933c  xor     ebx, ebx
0x14002933e  lea     rcx, [r14+6E8h]; Context
0x140029345  xor     r9d, r9d; unsigned int
0x140029348  mov     r8b, 1; unsigned __int8
0x14002934b  mov     rdx, rsi; struct _LIST_ENTRY *
0x14002934e  call    ?InsertList@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@EK@Z; SP_WORKITEM::InsertList(_LIST_ENTRY *,uchar,ulong)
0x140029353  jmp     loc_1400293E7
0x140029358  mov     rax, [rbp+var_20]
0x14002935c  lea     rcx, [rbp+var_20]
0x140029360  cmp     [rax+8], rcx
0x140029364  jnz     loc_140029441
0x14002936a  mov     rcx, [rbp+var_18]
0x14002936e  lea     rax, [rbp+var_20]
0x140029372  cmp     [rcx], rax
0x140029375  jnz     loc_140029441
0x14002937b  mov     rax, [rsi]
0x14002937e  cmp     [rax+8], rsi
0x140029382  jnz     loc_140029441
0x140029388  mov     rax, [rsi+8]
0x14002938c  cmp     [rax], rsi
0x14002938f  jnz     loc_140029441
0x140029395  mov     [rcx], rsi
0x140029398  lea     rdx, [rbp+var_20]
0x14002939c  mov     rax, [rsi+8]
  ... truncated ...
```
