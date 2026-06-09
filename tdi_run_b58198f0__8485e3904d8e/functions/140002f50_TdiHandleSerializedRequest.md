# TdiHandleSerializedRequest

- ea: `0x140002f50`
- end: `0x1400032cb`
- name: `TdiHandleSerializedRequest`
- size: `891`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002630`
- `0x140002840`
- `0x140002880`
- `0x140002a70`
- `0x140002b80`
- `0x140002c20`
- `0x140002c40`
- `0x140002f30`
- `0x140004080`
- `0x140005120`
- `0x140005140`
- `0x140005360`

## callees

- `0x140002f50`
- `0x1400032e0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003073`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400030e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000317f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003245`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003297`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003073`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400030e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000317f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003245`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003297`
- `ntoskrnl!ExAllocatePool2` at `0x140002fa9`
- `ntoskrnl!ExAllocatePool2` at `0x1400031c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400031eb`
- `ntoskrnl!ExAllocatePool2` at `0x140002fa9`
- `ntoskrnl!ExAllocatePool2` at `0x1400031c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400031eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400031a0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400031a0`
- `ntoskrnl!RtlGetCallersAddress` at `0x140002f7b`
- `ntoskrnl!RtlGetCallersAddress` at `0x140002f7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003260`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003271`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400032ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003260`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003271`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400032ae`
- `ntoskrnl!KeInitializeEvent` at `0x140003140`
- `ntoskrnl!KeInitializeEvent` at `0x140003140`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000302b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000302b`

## pseudocode

```c
__int64 __fastcall TdiHandleSerializedRequest(__int64 a1, int a2)
{
  struct _KTHREAD *CurrentThread; // rbp
  _QWORD *Pool2; // rdi
  KIRQL v6; // al
  int v7; // r8d
  KIRQL v8; // si
  int v9; // eax
  int v10; // edx
  __int64 v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // rax
  void *v18; // rcx
  _KEVENT Event; // [rsp+30h] [rbp-38h] BYREF
  PVOID v20; // [rsp+80h] [rbp+18h] BYREF
  PVOID v21; // [rsp+88h] [rbp+20h] BYREF

  v20 = 0;
  v21 = 0;
  RtlGetCallersAddress(&v20, &v21);
  CurrentThread = KeGetCurrentThread();
  if ( a2 == 9 )
  {
    Pool2 = *(_QWORD **)(a1 + 112);
    Pool2[6] = 0;
    Pool2[7] = 0;
    *((_DWORD *)Pool2 + 19) = 0;
    Pool2[11] = 0;
  }
  else
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 136, 1632191572);
    if ( !Pool2 )
      return 3221225626LL;
  }
  Pool2[8] = a1;
  Pool2[3] = &PnpHandlerClientList;
  Pool2[4] = &PnpHandlerProviderList;
  Pool2[5] = &PnpHandlerRequestList;
  Pool2[12] = &PnpHandlerRequestThread;
  *((_DWORD *)Pool2 + 18) = a2;
  Pool2[10] = 0;
  *((_DWORD *)Pool2 + 4) = 305450479;
  Pool2[13] = v20;
  Pool2[14] = v21;
  Pool2[15] = CurrentThread;
  if ( a2 == 15 )
  {
    v16 = ExAllocatePool2(64, 152, 1883849812);
    if ( v16 )
    {
      v17 = ExAllocatePool2(64, 136, 1917404244);
      if ( v17 )
      {
        *(_QWORD *)(v16 + 88) = v17;
        *(_QWORD *)(v17 + 48) = TdiPnPPowerCompleteHelper;
        *(_DWORD *)(v17 + 96) = 1;
        Pool2[16] = v16;
        goto LABEL_4;
      }
      ExFreePoolWithTag(Pool2, 0);
      v18 = (void *)v16;
    }
    else
    {
      v18 = Pool2;
    }
    ExFreePoolWithTag(v18, 0);
    return 3221225626LL;
  }
LABEL_4:
  v6 = KeAcquireSpinLockRaiseToDpc(&TDIListLock);
  v7 = *((_DWORD *)Pool2 + 18);
  v8 = v6;
  v9 = PnpExclusiveRequestsInQueue;
  if ( v7 != 10 && v7 != 15 )
    ++PnpExclusiveRequestsInQueue;
  v10 = PnpRequestsInQueue++;
  if ( !v10 || !v9 && a2 == 10 )
  {
    ++PnpRequestsExecuting;
    KeReleaseSpinLock(&TDIListLock, v8);
    return TdiExecuteRequest(Pool2, 0);
  }
  if ( v7 != 9 && v7 != 15 )
  {
    v12 = Pool2[5];
    v13 = *(_QWORD **)(v12 + 8);
    if ( *v13 == v12 )
    {
      Pool2[1] = v13;
      *Pool2 = v12;
      *v13 = Pool2;
      *(_QWORD *)(v12 + 8) = Pool2;
      if ( *((_DWORD *)Pool2 + 18) == 10 )
      {
        *((_BYTE *)Pool2 + 88) = 1;
        KeReleaseSpinLock(&TDIListLock, v8);
        return 259;
      }
      else
      {
        KeReleaseSpinLock(&TDIListLock, v8);
        return 0;
      }
    }
LABEL_31:
    __fastfail(3u);
  }
  if ( (struct _KTHREAD *)PnpHandlerRequestThread != KeGetCurrentThread() )
  {
    memset(&Event, 0, sizeof(Event));
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    Pool2[10] = &Event;
    v14 = Pool2[5];
    v15 = *(_QWORD **)(v14 + 8);
    if ( *v15 == v14 )
    {
      Pool2[1] = v15;
      *Pool2 = v14;
      *v15 = Pool2;
      *(_QWORD *)(v14 + 8) = Pool2;
      KeReleaseSpinLock(&TDIListLock, v8);
      KeWaitForSingleObject(&Event, UserRequest, 0, 0, 0);
      return 0;
    }
    goto LABEL_31;
  }
  KeReleaseSpinLock(&TDIListLock, v8);
  if ( *((_DWORD *)Pool2 + 18) != 9 )
    ExFreePoolWithTag(Pool2, 0);
  return 3221225663LL;
}

```

## disassembly

```asm
0x140002f50  mov     rax, rsp
0x140002f53  mov     [rax+8], rbx
0x140002f57  mov     [rax+10h], rbp
0x140002f5b  push    rsi
0x140002f5c  push    rdi
0x140002f5d  push    r14
0x140002f5f  sub     rsp, 50h
0x140002f63  mov     ebx, edx
0x140002f65  mov     rsi, rcx
0x140002f68  xor     r14d, r14d
0x140002f6b  lea     rdx, [rax+20h]; CallersCaller
0x140002f6f  lea     rcx, [rax+18h]; CallersAddress
0x140002f73  mov     [rax+18h], r14
0x140002f77  mov     [rax+20h], r14
0x140002f7b  call    cs:__imp_RtlGetCallersAddress
0x140002f82  nop     dword ptr [rax+rax+00h]
0x140002f87  mov     rbp, gs:188h
0x140002f90  cmp     ebx, 9
0x140002f93  jz      loc_14000321E
0x140002f99  mov     edx, 88h
0x140002f9e  mov     ecx, 40h ; '@'
0x140002fa3  mov     r8d, 61494454h
0x140002fa9  call    cs:__imp_ExAllocatePool2
0x140002fb0  nop     dword ptr [rax+rax+00h]
0x140002fb5  mov     rdi, rax
0x140002fb8  test    rax, rax
0x140002fbb  jz      loc_140003237
0x140002fc1  mov     [rdi+40h], rsi
0x140002fc5  lea     rax, PnpHandlerClientList
0x140002fcc  mov     [rdi+18h], rax
0x140002fd0  lea     rax, PnpHandlerProviderList
0x140002fd7  mov     [rdi+20h], rax
0x140002fdb  lea     rax, PnpHandlerRequestList
0x140002fe2  mov     [rdi+28h], rax
0x140002fe6  lea     rax, PnpHandlerRequestThread
0x140002fed  mov     [rdi+60h], rax
0x140002ff1  mov     [rdi+48h], ebx
0x140002ff4  mov     [rdi+50h], r14
0x140002ff8  mov     dword ptr [rdi+10h], 1234CDEFh
0x140002fff  mov     rax, [rsp+68h+arg_10]
0x140003007  mov     [rdi+68h], rax
0x14000300b  mov     rax, [rsp+68h+arg_18]
0x140003013  mov     [rdi+70h], rax
0x140003017  mov     [rdi+78h], rbp
0x14000301b  cmp     ebx, 0Fh
0x14000301e  jz      loc_1400031B3
0x140003024  lea     rcx, TDIListLock; SpinLock
0x14000302b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003032  nop     dword ptr [rax+rax+00h]
0x140003037  mov     r8d, [rdi+48h]
0x14000303b  movzx   esi, al
0x14000303e  mov     eax, cs:PnpExclusiveRequestsInQueue
0x140003044  cmp     r8d, 0Ah
0x140003048  jnz     loc_1400030F6
0x14000304e  mov     ecx, cs:PnpRequestsInQueue
0x140003054  mov     edx, ecx
0x140003056  inc     ecx
0x140003058  mov     cs:PnpRequestsInQueue, ecx
0x14000305e  test    edx, edx
0x140003060  jnz     short loc_14000309D
0x140003062  inc     cs:PnpRequestsExecuting
0x140003068  lea     rcx, TDIListLock; SpinLock
0x14000306f  movzx   edx, sil; NewIrql
0x140003073  call    cs:__imp_KeReleaseSpinLock
0x14000307a  nop     dword ptr [rax+rax+00h]
0x14000307f  xor     edx, edx
0x140003081  mov     rcx, rdi; P
0x140003084  call    TdiExecuteRequest
0x140003089  mov     rbx, [rsp+68h+arg_0]
0x14000308e  mov     rbp, [rsp+68h+arg_8]
0x140003093  add     rsp, 50h
0x140003097  pop     r14
0x140003099  pop     rdi
0x14000309a  pop     rsi
0x14000309b  retn
0x14000309d  test    eax, eax
0x14000309f  jnz     short loc_1400030A6
0x1400030a1  cmp     ebx, 0Ah
0x1400030a4  jz      short loc_140003062
0x1400030a6  cmp     r8d, 9
0x1400030aa  jz      short loc_14000310E
0x1400030ac  cmp     r8d, 0Fh
0x1400030b0  jz      short loc_14000310E
0x1400030b2  mov     rax, [rdi+28h]
0x1400030b6  mov     rdx, [rax+8]
0x1400030ba  cmp     [rdx], rax
0x1400030bd  jnz     loc_1400032C4
0x1400030c3  mov     [rdi+8], rdx
0x1400030c7  lea     rcx, TDIListLock; SpinLock
0x1400030ce  mov     [rdi], rax
0x1400030d1  mov     [rdx], rdi
0x1400030d4  movzx   edx, sil; NewIrql
0x1400030d8  mov     [rax+8], rdi
0x1400030dc  cmp     dword ptr [rdi+48h], 0Ah
0x1400030e0  jz      loc_140003241
0x1400030e6  call    cs:__imp_KeReleaseSpinLock
0x1400030ed  nop     dword ptr [rax+rax+00h]
0x1400030f2  xor     eax, eax
0x1400030f4  jmp     short loc_140003089
0x1400030f6  cmp     r8d, 0Fh
0x1400030fa  jz      loc_14000304E
0x140003100  lea     ecx, [rax+1]
0x140003103  mov     cs:PnpExclusiveRequestsInQueue, ecx
0x140003109  jmp     loc_14000304E
0x14000310e  mov     rax, gs:188h
0x140003117  cmp     cs:PnpHandlerRequestThread, rax
0x14000311e  jz      loc_14000328C
0x140003124  xorps   xmm0, xmm0
0x140003127  lea     rcx, [rsp+68h+Event]; Event
0x14000312c  xor     eax, eax
0x14000312e  xor     r8d, r8d; State
0x140003131  mov     edx, 1; Type
0x140003136  mov     [rsp+68h+Event.Header.WaitListHead.Blink], rax
0x14000313b  movups  xmmword ptr [rsp+68h+Event.Header], xmm0
0x140003140  call    cs:__imp_KeInitializeEvent
0x140003147  nop     dword ptr [rax+rax+00h]
0x14000314c  lea     rax, [rsp+68h+Event]
0x140003151  mov     [rdi+50h], rax
0x140003155  mov     rax, [rdi+28h]
0x140003159  mov     rcx, [rax+8]
0x14000315d  cmp     [rcx], rax
0x140003160  jnz     loc_1400032C4
0x140003166  mov     [rdi+8], rcx
0x14000316a  movzx   edx, sil; NewIrql
0x14000316e  mov     [rdi], rax
0x140003171  mov     [rcx], rdi
0x140003174  lea     rcx, TDIListLock; SpinLock
0x14000317b  mov     [rax+8], rdi
0x14000317f  call    cs:__imp_KeReleaseSpinLock
0x140003186  nop     dword ptr [rax+rax+00h]
0x14000318b  xor     r9d, r9d; Alertable
0x14000318e  mov     [rsp+68h+Timeout], r14; Timeout
0x140003193  xor     r8d, r8d; WaitMode
0x140003196  lea     rcx, [rsp+68h+Event]; Object
0x14000319b  mov     edx, 6; WaitReason
0x1400031a0  call    cs:__imp_KeWaitForSingleObject
0x1400031a7  nop     dword ptr [rax+rax+00h]
0x1400031ac  xor     eax, eax
0x1400031ae  jmp     loc_140003089
0x1400031b3  mov     edx, 98h
0x1400031b8  mov     ecx, 40h ; '@'
0x1400031bd  mov     r8d, 70494454h
0x1400031c3  call    cs:__imp_ExAllocatePool2
0x1400031ca  nop     dword ptr [rax+rax+00h]
0x1400031cf  mov     rsi, rax
0x1400031d2  test    rax, rax
0x1400031d5  jz      loc_140003287
0x1400031db  mov     edx, 88h
0x1400031e0  mov     ecx, 40h ; '@'
0x1400031e5  mov     r8d, 72494454h
0x1400031eb  call    cs:__imp_ExAllocatePool2
0x1400031f2  nop     dword ptr [rax+rax+00h]
0x1400031f7  test    rax, rax
0x1400031fa  jz      short loc_14000325B
0x1400031fc  mov     [rsi+58h], rax
0x140003200  lea     rcx, TdiPnPPowerCompleteHelper
0x140003207  mov     [rax+30h], rcx
0x14000320b  mov     dword ptr [rax+60h], 1
0x140003212  mov     [rdi+80h], rsi
0x140003219  jmp     loc_140003024
0x14000321e  mov     rdi, [rsi+70h]
0x140003222  mov     [rdi+30h], r14
0x140003226  mov     [rdi+38h], r14
0x14000322a  mov     [rdi+4Ch], r14d
0x14000322e  mov     [rdi+58h], r14
0x140003232  jmp     loc_140002FC1
0x140003237  mov     eax, 0C000009Ah
0x14000323c  jmp     loc_140003089
0x140003241  mov     byte ptr [rdi+58h], 1
0x140003245  call    cs:__imp_KeReleaseSpinLock
0x14000324c  nop     dword ptr [rax+rax+00h]
0x140003251  mov     eax, 103h
0x140003256  jmp     loc_140003089
0x14000325b  xor     edx, edx; Tag
0x14000325d  mov     rcx, rdi; P
0x140003260  call    cs:__imp_ExFreePoolWithTag
0x140003267  nop     dword ptr [rax+rax+00h]
0x14000326c  mov     rcx, rsi; P
0x14000326f  xor     edx, edx; Tag
0x140003271  call    cs:__imp_ExFreePoolWithTag
0x140003278  nop     dword ptr [rax+rax+00h]
0x14000327d  mov     eax, 0C000009Ah
0x140003282  jmp     loc_140003089
0x140003287  mov     rcx, rdi
0x14000328a  jmp     short loc_14000326F
0x14000328c  movzx   edx, sil; NewIrql
0x140003290  lea     rcx, TDIListLock; SpinLock
0x140003297  call    cs:__imp_KeReleaseSpinLock
0x14000329e  nop     dword ptr [rax+rax+00h]
0x1400032a3  cmp     dword ptr [rdi+48h], 9
0x1400032a7  jz      short loc_1400032BA
0x1400032a9  xor     edx, edx; Tag
0x1400032ab  mov     rcx, rdi; P
0x1400032ae  call    cs:__imp_ExFreePoolWithTag
0x1400032b5  nop     dword ptr [rax+rax+00h]
0x1400032ba  mov     eax, 0C00000BFh
0x1400032bf  jmp     loc_140003089
0x1400032c4  mov     ecx, 3
0x1400032c9  int     29h; Win8: RtlFailFast(ecx)
```
