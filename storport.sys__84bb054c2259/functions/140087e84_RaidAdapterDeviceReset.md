# RaidAdapterDeviceReset

- ea: `0x140087e84`
- end: `0x1400881c3`
- name: `RaidAdapterDeviceReset`
- size: `831`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14008ee48`

## callees

- `0x140025400`
- `0x1400306e8`
- `0x140030b30`
- `0x1400312c8`
- `0x14004ee60`
- `0x140087e84`
- `0x14008dca8`
- `0x140093144`
- `0x1400a521c`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140087f70`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140088057`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140087f70`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140088057`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140087f89`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140088082`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140087f89`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140088082`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140087f3a`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140088040`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140087f3a`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140088040`
- `ntoskrnl!KeLowerIrql` at `0x1400880f3`
- `ntoskrnl!KeLowerIrql` at `0x1400880f3`
- `ntoskrnl!KeInitializeEvent` at `0x140087fb6`
- `ntoskrnl!KeInitializeEvent` at `0x140087fb6`
- `ntoskrnl!KfRaiseIrql` at `0x1400880db`
- `ntoskrnl!KfRaiseIrql` at `0x1400880db`
- `ntoskrnl!KeWaitForSingleObject` at `0x140088000`
- `ntoskrnl!KeWaitForSingleObject` at `0x140088140`
- `ntoskrnl!KeWaitForSingleObject` at `0x140088000`
- `ntoskrnl!KeWaitForSingleObject` at `0x140088140`
- `ntoskrnl!InitializeSListHead` at `0x140087f51`
- `ntoskrnl!InitializeSListHead` at `0x140087f51`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14008818e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14008818e`

## pseudocode

```c
__int64 __fastcall RaidAdapterDeviceReset(__int64 a1, __int64 a2, int a3)
{
  bool v3; // zf
  int v8; // esi
  int v9; // ebp
  unsigned int v10; // esi
  unsigned int i; // ebx
  struct _SLIST_ENTRY *v12; // rax
  int v13; // ebp
  unsigned int v14; // ebx
  PSLIST_ENTRY v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // r9
  KIRQL v18; // bl
  _DWORD *v19; // rax
  int v20; // edx
  int v21; // eax
  unsigned int *v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // eax
  _BYTE Event[32]; // [rsp+30h] [rbp-78h] BYREF
  union _SLIST_HEADER SListHead; // [rsp+50h] [rbp-58h] BYREF

  v3 = *(_QWORD *)(a1 + 5440) == 0;
  SListHead = 0;
  memset(Event, 0, sizeof(Event));
  if ( v3 )
    return 3221225488LL;
  if ( !(unsigned __int8)RaidIsAdapterControlSupported(a1 + 360, 22) )
    return 3221225659LL;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 312), 1, 0) == 1 )
    return 3221226614LL;
  if ( (int)RaidAcquireAdapterRemoveLock(a1) >= 0 )
  {
    RaidPauseAdapterQueue(a1);
    if ( *(int *)(a1 + 4728) > 1 )
    {
      v9 = 0;
      v10 = KeQueryHighestNodeNumber() + 1;
      InitializeSListHead(&SListHead);
      do
      {
        for ( i = 0; i < v10; ++i )
        {
          v12 = ExpInterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)(a1 + 4736) + ((unsigned __int64)i << 6)));
          if ( v12 )
          {
            ExpInterlockedPushEntrySList(&SListHead, v12);
            ++v9;
          }
          else
          {
            _mm_pause();
          }
        }
      }
      while ( v9 < *(_DWORD *)(a1 + 4728) );
    }
    KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
    if ( !(unsigned __int8)GatewayRegisterForEmptyNotification(
                             *(_QWORD *)(a1 + 1024),
                             *(_QWORD *)(a1 + 8),
                             a3,
                             (unsigned int)Event,
                             (__int64)&RaidAdapterStopOnGatewayEmpty) )
      KeWaitForSingleObject(Event, Executive, 0, 0, 0);
    v8 = StorReset(*(_QWORD *)(a1 + 600) + 16LL, *(_DWORD *)(a2 + 8), 2, *(_QWORD *)(a2 + 16));
    if ( *(int *)(a1 + 4728) > 1 )
    {
      v13 = 0;
      v14 = KeQueryHighestNodeNumber() + 1;
      do
      {
        v15 = ExpInterlockedPopEntrySList(&SListHead);
        if ( v15 )
        {
          ExpInterlockedPushEntrySList(
            (PSLIST_HEADER)(*(_QWORD *)(a1 + 4736) + ((unsigned __int64)(HIDWORD(v15[1].Next) % v14) << 6)),
            v15);
          ++v13;
        }
      }
      while ( v13 < *(_DWORD *)(a1 + 4728) );
    }
    if ( v8 >= 0 && (v16 = *(_DWORD *)(a1 + 584)) != 0 )
    {
      v17 = v16 / 0xF4240 + 1;
      if ( v16 == 1000000 * (v16 / 0xF4240) )
        v17 = v16 / 0xF4240;
      RaidAdapterSetPauseTimer(a1, a1 + 4200, a1 + 4264, v17, 0);
    }
    else
    {
      v18 = KfRaiseIrql(2u);
      RaidResumeAndRestartAdapterQueues(a1);
      KeLowerIrql(v18);
    }
    v19 = *(_DWORD **)(a1 + 6208);
    if ( !v19 || (*v19 & 0xA0) == 0 )
      goto LABEL_45;
    v20 = RaidRequestDIrpForAssociatedUnits(a1, 0);
    if ( v20 == 259 )
    {
      KeWaitForSingleObject((PVOID)(*(_QWORD *)(a1 + 6208) + 56LL), Executive, 0, 0, 0);
      v20 = 0;
    }
    else if ( v8 >= 0 )
    {
      v21 = v8;
      if ( v20 < 0 )
        v21 = -1073741436;
      v8 = v21;
    }
    v22 = *(unsigned int **)(a1 + 6208);
    v23 = *v22;
    if ( v20 < 0 )
    {
      v24 = v23 | 0x40;
    }
    else if ( (v23 & 0x20) != 0 )
    {
      v24 = v23 & 0xFFFFFFDF;
    }
    else
    {
      if ( (v23 & 0x80u) == 0 )
      {
LABEL_45:
        ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 320));
        goto LABEL_46;
      }
      v24 = v23 & 0xFFFFFF7F;
    }
    *v22 = v24;
    goto LABEL_45;
  }
  v8 = -1073741436;
LABEL_46:
  *(_DWORD *)(a1 + 312) = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140087e84  push    rbx
0x140087e86  push    rbp
0x140087e87  push    rsi
0x140087e88  push    rdi
0x140087e89  push    r13
0x140087e8b  push    r14
0x140087e8d  push    r15
0x140087e8f  sub     rsp, 70h
0x140087e93  mov     rax, cs:__security_cookie
0x140087e9a  xor     rax, rsp
0x140087e9d  mov     [rsp+0A8h+var_48], rax
0x140087ea2  cmp     qword ptr [rcx+1540h], 0
0x140087eaa  xorps   xmm1, xmm1
0x140087ead  xorps   xmm0, xmm0
0x140087eb0  mov     r15, r8
0x140087eb3  movups  xmmword ptr [rsp+0A8h+SListHead], xmm0
0x140087eb8  mov     r14, rdx
0x140087ebb  mov     rdi, rcx
0x140087ebe  movups  xmmword ptr [rsp+0A8h+Event], xmm1
0x140087ec3  movups  xmmword ptr [rsp+0A8h+Event+10h], xmm1
0x140087ec8  jnz     short loc_140087ED4
0x140087eca  mov     eax, 0C0000010h
0x140087ecf  jmp     loc_1400881A6
0x140087ed4  add     rcx, 168h
0x140087edb  mov     edx, 16h
0x140087ee0  call    RaidIsAdapterControlSupported
0x140087ee5  test    al, al
0x140087ee7  jnz     short loc_140087EF3
0x140087ee9  mov     eax, 0C00000BBh
0x140087eee  jmp     loc_1400881A6
0x140087ef3  xor     eax, eax
0x140087ef5  lea     r13d, [rax+1]
0x140087ef9  lock cmpxchg [rdi+138h], r13d
0x140087f02  cmp     eax, r13d
0x140087f05  jnz     short loc_140087F11
0x140087f07  mov     eax, 0C0000476h
0x140087f0c  jmp     loc_1400881A6
0x140087f11  mov     rcx, rdi
0x140087f14  call    RaidAcquireAdapterRemoveLock
0x140087f19  test    eax, eax
0x140087f1b  jns     short loc_140087F27
0x140087f1d  mov     esi, 0C0000184h
0x140087f22  jmp     loc_14008819A
0x140087f27  mov     rcx, rdi
0x140087f2a  call    RaidPauseAdapterQueue
0x140087f2f  cmp     [rdi+1278h], r13d
0x140087f36  jle     short loc_140087FAB
0x140087f38  xor     ebp, ebp
0x140087f3a  call    cs:__imp_KeQueryHighestNodeNumber
0x140087f41  nop     dword ptr [rax+rax+00h]
0x140087f46  movzx   esi, ax
0x140087f49  lea     rcx, [rsp+0A8h+SListHead]; SListHead
0x140087f4e  add     esi, r13d
0x140087f51  call    cs:__imp_InitializeSListHead
0x140087f58  nop     dword ptr [rax+rax+00h]
0x140087f5d  xor     ebx, ebx
0x140087f5f  test    esi, esi
0x140087f61  jz      short loc_140087FA3
0x140087f63  mov     ecx, ebx
0x140087f65  shl     rcx, 6
0x140087f69  add     rcx, [rdi+1280h]; ListHead
0x140087f70  call    cs:__imp_ExpInterlockedPopEntrySList
0x140087f77  nop     dword ptr [rax+rax+00h]
0x140087f7c  test    rax, rax
0x140087f7f  jz      short loc_140087F9A
0x140087f81  mov     rdx, rax; ListEntry
0x140087f84  lea     rcx, [rsp+0A8h+SListHead]; ListHead
0x140087f89  call    cs:__imp_ExpInterlockedPushEntrySList
0x140087f90  nop     dword ptr [rax+rax+00h]
0x140087f95  add     ebp, r13d
0x140087f98  jmp     short loc_140087F9C
0x140087f9a  pause
0x140087f9c  add     ebx, r13d
0x140087f9f  cmp     ebx, esi
0x140087fa1  jb      short loc_140087F63
0x140087fa3  cmp     ebp, [rdi+1278h]
0x140087fa9  jl      short loc_140087F5D
0x140087fab  xor     r8d, r8d; State
0x140087fae  lea     rcx, [rsp+0A8h+Event]; Event
0x140087fb3  mov     edx, r13d; Type
0x140087fb6  call    cs:__imp_KeInitializeEvent
0x140087fbd  nop     dword ptr [rax+rax+00h]
0x140087fc2  mov     rdx, [rdi+8]
0x140087fc6  lea     rax, RaidAdapterStopOnGatewayEmpty
0x140087fcd  mov     rcx, [rdi+400h]
0x140087fd4  lea     r9, [rsp+0A8h+Event]
0x140087fd9  mov     r8, r15
0x140087fdc  mov     [rsp+0A8h+Timeout], rax
0x140087fe1  call    GatewayRegisterForEmptyNotification
0x140087fe6  test    al, al
0x140087fe8  jnz     short loc_14008800C
0x140087fea  xor     r9d, r9d; Alertable
0x140087fed  mov     [rsp+0A8h+Timeout], 0; Timeout
0x140087ff6  xor     r8d, r8d; WaitMode
0x140087ff9  lea     rcx, [rsp+0A8h+Event]; Object
0x140087ffe  xor     edx, edx; WaitReason
0x140088000  call    cs:__imp_KeWaitForSingleObject
0x140088007  nop     dword ptr [rax+rax+00h]
0x14008800c  mov     rcx, [rdi+258h]
0x140088013  mov     r8d, 2
0x140088019  mov     r9, [r14+10h]
0x14008801d  add     rcx, 10h
0x140088021  mov     edx, [r14+8]
0x140088025  mov     [rsp+0A8h+Timeout], 0
0x14008802e  call    StorReset
0x140088033  mov     esi, eax
0x140088035  cmp     [rdi+1278h], r13d
0x14008803c  jle     short loc_140088099
0x14008803e  xor     ebp, ebp
0x140088040  call    cs:__imp_KeQueryHighestNodeNumber
0x140088047  nop     dword ptr [rax+rax+00h]
0x14008804c  movzx   ebx, ax
0x14008804f  add     ebx, r13d
0x140088052  lea     rcx, [rsp+0A8h+SListHead]; ListHead
0x140088057  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008805e  nop     dword ptr [rax+rax+00h]
0x140088063  mov     r8, rax
0x140088066  test    rax, rax
0x140088069  jz      short loc_140088091
0x14008806b  mov     eax, [rax+14h]
0x14008806e  xor     edx, edx
0x140088070  div     ebx
0x140088072  mov     ecx, edx
0x140088074  mov     rdx, r8; ListEntry
0x140088077  shl     rcx, 6
0x14008807b  add     rcx, [rdi+1280h]; ListHead
0x140088082  call    cs:__imp_ExpInterlockedPushEntrySList
0x140088089  nop     dword ptr [rax+rax+00h]
0x14008808e  add     ebp, r13d
0x140088091  cmp     ebp, [rdi+1278h]
0x140088097  jl      short loc_140088052
0x140088099  test    esi, esi
0x14008809b  js      short loc_1400880D9
0x14008809d  mov     ecx, [rdi+248h]
0x1400880a3  test    ecx, ecx
0x1400880a5  jz      short loc_1400880D9
0x1400880a7  mov     eax, 431BDE83h
0x1400880ac  lea     r8, [rdi+10A8h]
0x1400880b3  mul     ecx
0x1400880b5  shr     edx, 12h
0x1400880b8  imul    eax, edx, 0F4240h
0x1400880be  lea     r9d, [rdx+1]
0x1400880c2  cmp     ecx, eax
0x1400880c4  mov     rcx, rdi
0x1400880c7  cmovz   r9d, edx
0x1400880cb  lea     rdx, [rdi+1068h]
0x1400880d2  call    RaidAdapterSetPauseTimer
0x1400880d7  jmp     short loc_1400880FF
0x1400880d9  mov     cl, 2; NewIrql
0x1400880db  call    cs:__imp_KfRaiseIrql
0x1400880e2  nop     dword ptr [rax+rax+00h]
0x1400880e7  mov     rcx, rdi
0x1400880ea  mov     bl, al
0x1400880ec  call    RaidResumeAndRestartAdapterQueues
0x1400880f1  mov     cl, bl; NewIrql
0x1400880f3  call    cs:__imp_KeLowerIrql
0x1400880fa  nop     dword ptr [rax+rax+00h]
0x1400880ff  mov     rax, [rdi+1840h]
0x140088106  test    rax, rax
0x140088109  jz      short loc_140088187
0x14008810b  mov     eax, [rax]
0x14008810d  test    al, 0A0h
0x14008810f  jz      short loc_140088187
0x140088111  xor     edx, edx
0x140088113  mov     rcx, rdi
0x140088116  call    RaidRequestDIrpForAssociatedUnits
0x14008811b  mov     edx, eax
0x14008811d  cmp     eax, 103h
0x140088122  jnz     short loc_140088150
0x140088124  mov     rcx, [rdi+1840h]
0x14008812b  xor     r9d, r9d; Alertable
0x14008812e  add     rcx, 38h ; '8'; Object
0x140088132  mov     [rsp+0A8h+Timeout], 0; Timeout
0x14008813b  xor     r8d, r8d; WaitMode
0x14008813e  xor     edx, edx; WaitReason
0x140088140  call    cs:__imp_KeWaitForSingleObject
0x140088147  nop     dword ptr [rax+rax+00h]
0x14008814c  xor     edx, edx
0x14008814e  jmp     short loc_140088162
0x140088150  test    esi, esi
0x140088152  js      short loc_140088162
0x140088154  mov     eax, esi
0x140088156  test    edx, edx
0x140088158  mov     esi, 0C0000184h
0x14008815d  cmovs   eax, esi
0x140088160  mov     esi, eax
0x140088162  mov     rcx, [rdi+1840h]
0x140088169  mov     eax, [rcx]
0x14008816b  test    edx, edx
0x14008816d  js      short loc_140088182
0x14008816f  test    al, 20h
0x140088171  jz      short loc_140088178
0x140088173  and     eax, 0FFFFFFDFh
0x140088176  jmp     short loc_140088185
0x140088178  test    al, al
0x14008817a  jns     short loc_140088187
0x14008817c  btr     eax, 7
0x140088180  jmp     short loc_140088185
0x140088182  or      eax, 40h
0x140088185  mov     [rcx], eax
0x140088187  mov     rcx, [rdi+140h]; RunRefCacheAware
0x14008818e  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140088195  nop     dword ptr [rax+rax+00h]
0x14008819a  mov     dword ptr [rdi+138h], 0
0x1400881a4  mov     eax, esi
0x1400881a6  mov     rcx, [rsp+0A8h+var_48]
0x1400881ab  xor     rcx, rsp; StackCookie
0x1400881ae  call    __security_check_cookie
0x1400881b3  add     rsp, 70h
0x1400881b7  pop     r15
0x1400881b9  pop     r14
0x1400881bb  pop     r13
0x1400881bd  pop     rdi
0x1400881be  pop     rsi
0x1400881bf  pop     rbp
0x1400881c0  pop     rbx
0x1400881c1  retn
```
