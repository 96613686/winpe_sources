# WanpLinkUpIndication

- ea: `0x14000fdc4`
- end: `0x140010426`
- name: `WanpLinkUpIndication`
- size: `1634`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400022c0`

## callees

- `0x140003060`
- `0x140003344`
- `0x1400035e4`
- `0x1400036e8`
- `0x1400050f0`
- `0x1400051c0`
- `0x14000df30`
- `0x14000e280`
- `0x14000e4e4`
- `0x14000f3fc`
- `0x14000f728`
- `0x14000fdc4`
- `0x140010448`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fe49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400100be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fe49`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400100be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400101a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102f4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fe94`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400100fa`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001016b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400101dd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fe94`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400100fa`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001016b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400101dd`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fe85`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400100e7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400101ca`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fe85`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400100e7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400101ca`
- `ntoskrnl!KeLowerIrql` at `0x140010142`
- `ntoskrnl!KeLowerIrql` at `0x14001021d`
- `ntoskrnl!KeLowerIrql` at `0x140010142`
- `ntoskrnl!KeLowerIrql` at `0x14001021d`
- `ntoskrnl!ExAllocatePool2` at `0x14000ff90`
- `ntoskrnl!ExAllocatePool2` at `0x140010263`
- `ntoskrnl!ExAllocatePool2` at `0x14000ff90`
- `ntoskrnl!ExAllocatePool2` at `0x140010263`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ff00`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001002d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010131`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001020c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ff00`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001002d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010131`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001020c`
- `ntoskrnl!ExQueueWorkItem` at `0x14000ffe6`
- `ntoskrnl!ExQueueWorkItem` at `0x1400103f3`
- `ntoskrnl!ExQueueWorkItem` at `0x14000ffe6`
- `ntoskrnl!ExQueueWorkItem` at `0x1400103f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fe10`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fe10`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ff62`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400103bb`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ff62`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400103bb`

## pseudocode

```c
__int64 __fastcall WanpLinkUpIndication(__int64 a1, char a2)
{
  const WCHAR *v2; // rbx
  __int64 v5; // rcx
  __int64 v7; // r14
  KIRQL v8; // r15
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // ebx
  int v16; // eax
  volatile signed __int32 *v17; // r13
  char v18; // r14
  __int64 v19; // r8
  unsigned __int16 *DialInAdapterGivenCompartmentId; // r15
  KIRQL v21; // r12
  __int64 InterfaceGivenIndex; // rax
  KSPIN_LOCK *v23; // rcx
  unsigned int v24; // eax
  __int64 Pool2; // r12
  __int64 v26; // rax
  PVOID v27; // rcx
  char *v28; // rdi
  void *v29; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-30h] BYREF
  __int128 v31; // [rsp+40h] [rbp-20h] BYREF
  __int64 v32; // [rsp+50h] [rbp-10h]
  PVOID P; // [rsp+A0h] [rbp+40h] BYREF
  char v34; // [rsp+A8h] [rbp+48h]
  const WCHAR *v35; // [rsp+B0h] [rbp+50h]

  v34 = a2;
  v2 = *(const WCHAR **)(a1 + 32);
  v35 = v2;
  v32 = 0;
  P = 0;
  DestinationString = 0;
  v31 = 0;
  RtlInitUnicodeString(&DestinationString, v2 + 26);
  if ( !EnterModuleCode(a2) )
    return 3221291025LL;
  v7 = *(unsigned int *)(a1 + 22);
  if ( !(_DWORD)v7 )
  {
    v16 = *(_DWORD *)v2;
    if ( *(_DWORD *)v2 > 2u )
    {
      v15 = -1073741811;
      goto LABEL_72;
    }
    v17 = 0;
    v18 = 1;
    if ( v16 == 1 )
    {
      v15 = WanpCreateNewAdapter(*(_QWORD *)(a1 + 56), (__int64)&DestinationString, v34, 0, 1, &P);
      if ( v15 < 0 )
        goto LABEL_72;
      DialInAdapterGivenCompartmentId = (unsigned __int16 *)P;
      *((_DWORD *)P + 80) = *(_DWORD *)(a1 + 4);
      *((_QWORD *)DialInAdapterGivenCompartmentId + 41) = (unsigned int)(100 * *(_DWORD *)a1);
      *((_QWORD *)DialInAdapterGivenCompartmentId + 42) = (unsigned int)(100 * *(_DWORD *)a1);
LABEL_49:
      LOBYTE(v19) = v34;
      P = (PVOID)WanpAllocateAndInitializeConnectionEntry(a1, DialInAdapterGivenCompartmentId, v19);
      if ( P )
      {
        v24 = *(unsigned __int16 *)(a1 + 50);
        if ( v24 + 64 < v24 )
        {
          v15 = -1073741675;
LABEL_54:
          v5 = *(unsigned int *)v35;
          if ( (_DWORD)v5 == 1 )
          {
            if ( v34 )
              v26 = *((_QWORD *)DialInAdapterGivenCompartmentId + 22);
            else
              v26 = *((_QWORD *)DialInAdapterGivenCompartmentId + 21);
            if ( !v26 )
              WanpDeleteAdapter(DialInAdapterGivenCompartmentId);
          }
          else if ( (_DWORD)v5 == 2 && _InterlockedExchangeAdd(v17 + 16, 0xFFFFFFFF) == 1 )
          {
            ExFreePoolWithTag((PVOID)v17, 0);
          }
          if ( P )
          {
            v27 = P;
            *((_DWORD *)P + 31) = 3;
            WanpDeleteConnEntry(v27);
          }
          *(_DWORD *)(a1 + 20) = 0;
          *(_WORD *)(a1 + 24) = 0;
          goto LABEL_72;
        }
        Pool2 = ExAllocatePool2(64, v24 + 64, 1819308663);
        if ( Pool2 )
        {
          v15 = 0;
          *(_BYTE *)(Pool2 + 8) = v34;
          *(_QWORD *)Pool2 = a1;
          *(_QWORD *)(Pool2 + 24) = DialInAdapterGivenCompartmentId;
          _InterlockedAdd((volatile signed __int32 *)DialInAdapterGivenCompartmentId + 32, 1u);
          if ( v17 )
          {
            *(_QWORD *)(Pool2 + 16) = v17;
            _InterlockedAdd(v17 + 16, 1u);
          }
          v28 = (char *)P;
          *(_QWORD *)(Pool2 + 32) = P;
          _InterlockedAdd((volatile signed __int32 *)v28 + 24, 1u);
          *(_WORD *)(Pool2 + 42) = *(_WORD *)(a1 + 50);
          *(_WORD *)(Pool2 + 40) = *(_WORD *)(a1 + 48);
          *(_QWORD *)(Pool2 + 48) = Pool2 + 64;
          memmove((void *)(Pool2 + 64), *(const void **)(a1 + 56), *(unsigned __int16 *)(a1 + 48));
          *(_DWORD *)(a1 + 20) = 0;
          *(_WORD *)(a1 + 24) = 0;
          *(_DWORD *)(a1 + 22) = *((_DWORD *)v28 + 26);
          *(_QWORD *)(v28 + 108) = 0;
          *((_DWORD *)v28 + 29) = *((_DWORD *)v28 + 26);
          *((_DWORD *)v28 + 27) = *(_DWORD *)(a1 + 14);
          *((_WORD *)v28 + 56) = *(_WORD *)(a1 + 18);
          v29 = *(void **)(a1 + 56);
          *(_WORD *)(a1 + 48) = DialInAdapterGivenCompartmentId[36];
          memmove(v29, *((const void **)DialInAdapterGivenCompartmentId + 10), DialInAdapterGivenCompartmentId[36]);
          _InterlockedAdd((volatile signed __int32 *)v28 + 24, 1u);
          if ( KeGetCurrentIrql() )
          {
            *((_QWORD *)v28 + 29) = Pool2;
            *((_QWORD *)v28 + 28) = WanpLinkUpIndicationWorkItem;
            *((_QWORD *)v28 + 26) = 0;
            ExQueueWorkItem((PWORK_QUEUE_ITEM)(v28 + 208), CriticalWorkQueue);
          }
          else
          {
            WanpLinkUpIndicationWorkItemImpl((__int64 *)Pool2, 0);
            v18 = 0;
          }
          *(_BYTE *)(a1 + 64) = v18;
          goto LABEL_72;
        }
      }
      v15 = -1073741670;
      goto LABEL_54;
    }
    if ( v16 == 2 )
    {
      v21 = KeAcquireSpinLockRaiseToDpc(&g_rwlIfLock);
      if ( _InterlockedIncrement(&dword_140009C50) == 1 )
        KeAcquireSpinLockAtDpcLevel(&qword_140009C48);
      KeReleaseSpinLockFromDpcLevel(&g_rwlIfLock);
      InterfaceGivenIndex = WanpFindInterfaceGivenIndex(*((unsigned int *)v2 + 3));
      v17 = (volatile signed __int32 *)InterfaceGivenIndex;
      if ( !InterfaceGivenIndex )
      {
        if ( _InterlockedExchangeAdd(&dword_140009C50, 0xFFFFFFFF) == 1 )
          KeReleaseSpinLock(&qword_140009C48, v21);
        else
          KeLowerIrql(v21);
        v15 = -1073741772;
        goto LABEL_72;
      }
      DialInAdapterGivenCompartmentId = *(unsigned __int16 **)(InterfaceGivenIndex + 24);
      *((_QWORD *)v2 + 3) = *((_QWORD *)DialInAdapterGivenCompartmentId + 44);
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(InterfaceGivenIndex + 56));
      if ( _InterlockedExchangeAdd(&dword_140009C50, 0xFFFFFFFF) == 1 )
      {
        v23 = &qword_140009C48;
LABEL_47:
        KeReleaseSpinLock(v23, v21);
        goto LABEL_49;
      }
    }
    else
    {
      v21 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
      if ( _InterlockedIncrement(&dword_140009CB0) == 1 )
        KeAcquireSpinLockAtDpcLevel(&SpinLock);
      KeReleaseSpinLockFromDpcLevel(&g_rwlAdapterLock);
      DialInAdapterGivenCompartmentId = (unsigned __int16 *)WanpFindDialInAdapterGivenCompartmentId(*((unsigned int *)v2 + 12));
      if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
      {
        v23 = &SpinLock;
        goto LABEL_47;
      }
    }
    KeLowerIrql(v21);
    goto LABEL_49;
  }
  v8 = KeAcquireSpinLockRaiseToDpc(&g_rlConnTableLock);
  v9 = *((_QWORD *)g_puipConnTable + v7);
  if ( v9 )
  {
    _InterlockedAdd((volatile signed __int32 *)(v9 + 96), 1u);
    if ( *(_DWORD *)(v9 + 124) == 2 )
    {
      KeAcquireSpinLockAtDpcLevel(*(PKSPIN_LOCK *)(v9 + 80));
      KeReleaseSpinLockFromDpcLevel(&g_rlConnTableLock);
      v10 = *(_DWORD *)(a1 + 4);
      if ( v10 != *(_DWORD *)(v9 + 280) )
      {
        *(_DWORD *)(v9 + 280) = v10;
        BYTE8(v31) |= 2u;
      }
      v11 = (unsigned int)(100 * *(_DWORD *)a1);
      if ( v11 != *(_QWORD *)(v9 + 288) )
      {
        *(_QWORD *)(v9 + 288) = v11;
        BYTE8(v31) |= 4u;
      }
      v12 = (unsigned int)(100 * *(_DWORD *)a1);
      if ( v12 != *(_QWORD *)(v9 + 296) )
      {
        *(_QWORD *)(v9 + 296) = v12;
        BYTE8(v31) |= 4u;
      }
      *(_QWORD *)&v31 = *(_QWORD *)(v9 + 128);
      v32 = v9 + 272;
      KeReleaseSpinLock(*(PKSPIN_LOCK *)(v9 + 80), v8);
      v13 = qword_1400090D8;
      if ( !a2 )
        v13 = qword_140009328;
      (*(void (__fastcall **)(__int128 *))(*(_QWORD *)(v13 + 8) + 48LL))(&v31);
      v5 = *(_QWORD *)(v9 + 8);
      *(_DWORD *)(v5 + 320) = *(_DWORD *)(a1 + 4);
      *(_QWORD *)(*(_QWORD *)(v9 + 8) + 328LL) = (unsigned int)(100 * *(_DWORD *)a1);
      *(_QWORD *)(*(_QWORD *)(v9 + 8) + 336LL) = (unsigned int)(100 * *(_DWORD *)a1);
      if ( *(_DWORD *)(v9 + 100) == 1 )
      {
        if ( KeGetCurrentIrql() )
        {
          v14 = ExAllocatePool2(64, 48, 1819308663);
          v5 = v14;
          if ( !v14 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 96), 0xFFFFFFFF) == 1 )
              WanpDeleteConnEntry((PVOID)v9);
            v15 = -1073741670;
            goto LABEL_72;
          }
          *(_QWORD *)(v14 + 24) = v14;
          *(_QWORD *)(v14 + 16) = UpdateInterfaceIndexWorkItem;
          *(_QWORD *)v14 = 0;
          *(_QWORD *)(v14 + 32) = v9;
          *(_DWORD *)(v14 + 40) = *(_DWORD *)(a1 + 100);
          ExQueueWorkItem((PWORK_QUEUE_ITEM)v14, CriticalWorkQueue);
        }
        else
        {
          UpdateInterfaceIndexImpl((PVOID)v9, *(_DWORD *)(a1 + 100));
        }
      }
      else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 96), 0xFFFFFFFF) == 1 )
      {
        WanpDeleteConnEntry((PVOID)v9);
      }
      goto LABEL_24;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 96), 0xFFFFFFFF) == 1 )
      WanpDeleteConnEntry((PVOID)v9);
  }
  KeReleaseSpinLock(&g_rlConnTableLock, v8);
LABEL_24:
  v15 = 0;
LABEL_72:
  LOBYTE(v5) = v34;
  ExitModuleCode(v5);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14000fdc4  mov     [rsp-38h+arg_18], rbx
0x14000fdc9  mov     [rsp-38h+arg_8], dl
0x14000fdcd  push    rbp
0x14000fdce  push    rsi
0x14000fdcf  push    rdi
0x14000fdd0  push    r12
0x14000fdd2  push    r13
0x14000fdd4  push    r14
0x14000fdd6  push    r15
0x14000fdd8  mov     rbp, rsp
0x14000fddb  sub     rsp, 60h
0x14000fddf  mov     rbx, [rcx+20h]
0x14000fde3  mov     dil, dl
0x14000fde6  mov     rsi, rcx
0x14000fde9  mov     [rbp+arg_10], rbx
0x14000fded  xorps   xmm0, xmm0
0x14000fdf0  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000fdf4  xorps   xmm1, xmm1
0x14000fdf7  xor     eax, eax
0x14000fdf9  xor     r15d, r15d
0x14000fdfc  mov     [rbp+var_10], rax
0x14000fe00  lea     rdx, [rbx+34h]; SourceString
0x14000fe04  mov     [rbp+P], r15
0x14000fe08  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000fe0c  movups  [rbp+var_20], xmm1
0x14000fe10  call    cs:__imp_RtlInitUnicodeString
0x14000fe17  nop     dword ptr [rax+rax+00h]
0x14000fe1c  mov     cl, dil
0x14000fe1f  call    EnterModuleCode
0x14000fe24  test    al, al
0x14000fe26  jnz     short loc_14000FE32
0x14000fe28  mov     eax, 0C0010011h
0x14000fe2d  jmp     loc_14001040D
0x14000fe32  mov     r14d, [rsi+16h]
0x14000fe36  test    r14d, r14d
0x14000fe39  jz      loc_14001003B
0x14000fe3f  lea     r12, g_rlConnTableLock
0x14000fe46  mov     rcx, r12; SpinLock
0x14000fe49  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fe50  nop     dword ptr [rax+rax+00h]
0x14000fe55  mov     rcx, cs:g_puipConnTable
0x14000fe5c  mov     r15b, al
0x14000fe5f  mov     rbx, [rcx+r14*8]
0x14000fe63  test    rbx, rbx
0x14000fe66  jz      loc_140010027
0x14000fe6c  mov     r14d, 1
0x14000fe72  lock add [rbx+60h], r14d
0x14000fe77  cmp     dword ptr [rbx+7Ch], 2
0x14000fe7b  jnz     loc_140010011
0x14000fe81  mov     rcx, [rbx+50h]; SpinLock
0x14000fe85  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000fe8c  nop     dword ptr [rax+rax+00h]
0x14000fe91  mov     rcx, r12; SpinLock
0x14000fe94  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000fe9b  nop     dword ptr [rax+rax+00h]
0x14000fea0  mov     eax, [rsi+4]
0x14000fea3  cmp     eax, [rbx+118h]
0x14000fea9  jz      short loc_14000FEB5
0x14000feab  mov     [rbx+118h], eax
0x14000feb1  or      byte ptr [rbp+var_20+8], 2
0x14000feb5  imul    ecx, [rsi], 64h ; 'd'
0x14000feb8  cmp     rcx, [rbx+120h]
0x14000febf  jz      short loc_14000FECC
0x14000fec1  mov     [rbx+120h], rcx
0x14000fec8  or      byte ptr [rbp+var_20+8], 4
0x14000fecc  imul    ecx, [rsi], 64h ; 'd'
0x14000fecf  cmp     rcx, [rbx+128h]
0x14000fed6  jz      short loc_14000FEE3
0x14000fed8  mov     [rbx+128h], rcx
0x14000fedf  or      byte ptr [rbp+var_20+8], 4
0x14000fee3  mov     rax, [rbx+80h]
0x14000feea  mov     dl, r15b; NewIrql
0x14000feed  mov     qword ptr [rbp+var_20], rax
0x14000fef1  lea     rax, [rbx+110h]
0x14000fef8  mov     [rbp+var_10], rax
0x14000fefc  mov     rcx, [rbx+50h]; SpinLock
0x14000ff00  call    cs:__imp_KeReleaseSpinLock
0x14000ff07  nop     dword ptr [rax+rax+00h]
0x14000ff0c  mov     rcx, cs:qword_1400090D8
0x14000ff13  test    dil, dil
0x14000ff16  cmovz   rcx, cs:qword_140009328
0x14000ff1e  mov     rax, [rcx+8]
0x14000ff22  lea     rcx, [rbp+var_20]
0x14000ff26  mov     rax, [rax+30h]
0x14000ff2a  call    _guard_dispatch_icall
0x14000ff2f  mov     eax, [rsi+4]
0x14000ff32  mov     rcx, [rbx+8]
0x14000ff36  mov     [rcx+140h], eax
0x14000ff3c  imul    edx, [rsi], 64h ; 'd'
0x14000ff3f  mov     rax, [rbx+8]
0x14000ff43  mov     [rax+148h], rdx
0x14000ff4a  imul    edx, [rsi], 64h ; 'd'
0x14000ff4d  mov     rax, [rbx+8]
0x14000ff51  mov     [rax+150h], rdx
0x14000ff58  cmp     [rbx+64h], r14d
0x14000ff5c  jnz     loc_14000FFF4
0x14000ff62  call    cs:__imp_KeGetCurrentIrql
0x14000ff69  nop     dword ptr [rax+rax+00h]
0x14000ff6e  test    al, al
0x14000ff70  jnz     short loc_14000FF82
0x14000ff72  mov     edx, [rsi+64h]; ifIndex
0x14000ff75  mov     rcx, rbx; Entry
0x14000ff78  call    UpdateInterfaceIndexImpl
0x14000ff7d  jmp     loc_14001000A
0x14000ff82  mov     edx, 30h ; '0'
0x14000ff87  mov     r8d, 6C707277h
0x14000ff8d  lea     ecx, [rdx+10h]
0x14000ff90  call    cs:__imp_ExAllocatePool2
0x14000ff97  nop     dword ptr [rax+rax+00h]
0x14000ff9c  mov     rcx, rax; WorkItem
0x14000ff9f  test    rax, rax
0x14000ffa2  jnz     short loc_14000FFC4
0x14000ffa4  or      edi, 0FFFFFFFFh
0x14000ffa7  mov     eax, edi
0x14000ffa9  lock xadd [rbx+60h], eax
0x14000ffae  add     eax, edi
0x14000ffb0  jnz     short loc_14000FFBA
0x14000ffb2  mov     rcx, rbx; Entry
0x14000ffb5  call    WanpDeleteConnEntry
0x14000ffba  mov     ebx, 0C000009Ah
0x14000ffbf  jmp     loc_140010403
0x14000ffc4  mov     [rcx+18h], rcx
0x14000ffc8  lea     rax, UpdateInterfaceIndexWorkItem
0x14000ffcf  mov     [rcx+10h], rax
0x14000ffd3  xor     edx, edx; QueueType
0x14000ffd5  mov     qword ptr [rcx], 0
0x14000ffdc  mov     [rcx+20h], rbx
0x14000ffe0  mov     eax, [rsi+64h]
0x14000ffe3  mov     [rcx+28h], eax
0x14000ffe6  call    cs:__imp_ExQueueWorkItem
0x14000ffed  nop     dword ptr [rax+rax+00h]
0x14000fff2  jmp     short loc_14001000A
0x14000fff4  or      edi, 0FFFFFFFFh
0x14000fff7  mov     eax, edi
0x14000fff9  lock xadd [rbx+60h], eax
0x14000fffe  add     eax, edi
0x140010000  jnz     short loc_14001000A
0x140010002  mov     rcx, rbx; Entry
0x140010005  call    WanpDeleteConnEntry
0x14001000a  xor     ebx, ebx
0x14001000c  jmp     loc_140010403
0x140010011  or      edi, 0FFFFFFFFh
0x140010014  mov     eax, edi
0x140010016  lock xadd [rbx+60h], eax
0x14001001b  add     eax, edi
0x14001001d  jnz     short loc_140010027
0x14001001f  mov     rcx, rbx; Entry
0x140010022  call    WanpDeleteConnEntry
0x140010027  mov     dl, r15b; NewIrql
0x14001002a  mov     rcx, r12; SpinLock
0x14001002d  call    cs:__imp_KeReleaseSpinLock
0x140010034  nop     dword ptr [rax+rax+00h]
0x140010039  jmp     short loc_14001000A
0x14001003b  mov     eax, [rbx]
0x14001003d  cmp     eax, 2
0x140010040  jbe     short loc_14001004C
0x140010042  mov     ebx, 0C000000Dh
0x140010047  jmp     loc_140010403
0x14001004c  xor     r13d, r13d
0x14001004f  or      edi, 0FFFFFFFFh
0x140010052  lea     r14d, [r13+1]
0x140010056  cmp     eax, r14d
0x140010059  jnz     short loc_1400100AE
0x14001005b  mov     r8b, [rbp+arg_8]
0x14001005f  lea     rax, [rbp+P]
0x140010063  mov     rcx, [rsi+38h]
0x140010067  lea     rdx, [rbp+DestinationString]
0x14001006b  mov     [rsp+60h+var_38], rax
0x140010070  xor     r9d, r9d
0x140010073  mov     [rsp+60h+var_40], r14d
0x140010078  call    WanpCreateNewAdapter
0x14001007d  mov     ebx, eax
0x14001007f  test    eax, eax
0x140010081  js      loc_140010403
0x140010087  mov     r15, [rbp+P]
0x14001008b  mov     eax, [rsi+4]
0x14001008e  mov     [r15+140h], eax
0x140010095  imul    ecx, [rsi], 64h ; 'd'
0x140010098  mov     [r15+148h], rcx
0x14001009f  imul    ecx, [rsi], 64h ; 'd'
0x1400100a2  mov     [r15+150h], rcx
0x1400100a9  jmp     loc_140010229
0x1400100ae  cmp     eax, 2
0x1400100b1  jnz     loc_140010192
0x1400100b7  lea     rcx, g_rwlIfLock; SpinLock
0x1400100be  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400100c5  nop     dword ptr [rax+rax+00h]
0x1400100ca  mov     r12b, al
0x1400100cd  mov     eax, r14d
0x1400100d0  lock xadd cs:dword_140009C50, eax
0x1400100d8  add     eax, r14d
0x1400100db  cmp     eax, r14d
0x1400100de  jnz     short loc_1400100F3
0x1400100e0  lea     rcx, qword_140009C48; SpinLock
0x1400100e7  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400100ee  nop     dword ptr [rax+rax+00h]
0x1400100f3  lea     rcx, g_rwlIfLock; SpinLock
0x1400100fa  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140010101  nop     dword ptr [rax+rax+00h]
0x140010106  mov     ecx, [rbx+0Ch]
0x140010109  call    WanpFindInterfaceGivenIndex
0x14001010e  mov     r13, rax
0x140010111  test    rax, rax
0x140010114  jnz     short loc_140010158
0x140010116  or      edi, 0FFFFFFFFh
0x140010119  mov     eax, edi
0x14001011b  lock xadd cs:dword_140009C50, eax
0x140010123  add     eax, edi
0x140010125  jnz     short loc_14001013F
0x140010127  mov     dl, r12b; NewIrql
0x14001012a  lea     rcx, qword_140009C48; SpinLock
0x140010131  call    cs:__imp_KeReleaseSpinLock
0x140010138  nop     dword ptr [rax+rax+00h]
0x14001013d  jmp     short loc_14001014E
0x14001013f  mov     cl, r12b; NewIrql
0x140010142  call    cs:__imp_KeLowerIrql
0x140010149  nop     dword ptr [rax+rax+00h]
0x14001014e  mov     ebx, 0C0000034h
0x140010153  jmp     loc_140010403
0x140010158  mov     r15, [rax+18h]
0x14001015c  lea     rcx, [r13+38h]; SpinLock
0x140010160  mov     rax, [r15+160h]
0x140010167  mov     [rbx+18h], rax
0x14001016b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140010172  nop     dword ptr [rax+rax+00h]
0x140010177  mov     eax, edi
0x140010179  lock xadd cs:dword_140009C50, eax
0x140010181  add     eax, edi
0x140010183  jnz     loc_14001021A
0x140010189  lea     rcx, qword_140009C48
0x140010190  jmp     short loc_140010209
0x140010192  test    eax, eax
0x140010194  jnz     loc_140010229
0x14001019a  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400101a1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400101a8  nop     dword ptr [rax+rax+00h]
0x1400101ad  mov     r12b, al
0x1400101b0  mov     edx, r14d
0x1400101b3  lock xadd cs:dword_140009CB0, edx
0x1400101bb  add     edx, r14d
0x1400101be  cmp     edx, r14d
0x1400101c1  jnz     short loc_1400101D6
0x1400101c3  lea     rcx, SpinLock; SpinLock
0x1400101ca  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400101d1  nop     dword ptr [rax+rax+00h]
0x1400101d6  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400101dd  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400101e4  nop     dword ptr [rax+rax+00h]
0x1400101e9  mov     ecx, [rbx+30h]
0x1400101ec  call    WanpFindDialInAdapterGivenCompartmentId
0x1400101f1  mov     r15, rax
0x1400101f4  mov     edx, edi
0x1400101f6  lock xadd cs:dword_140009CB0, edx
0x1400101fe  add     edx, edi
0x140010200  jnz     short loc_14001021A
0x140010202  lea     rcx, SpinLock; SpinLock
0x140010209  mov     dl, r12b; NewIrql
0x14001020c  call    cs:__imp_KeReleaseSpinLock
0x140010213  nop     dword ptr [rax+rax+00h]
0x140010218  jmp     short loc_140010229
0x14001021a  mov     cl, r12b; NewIrql
0x14001021d  call    cs:__imp_KeLowerIrql
0x140010224  nop     dword ptr [rax+rax+00h]
0x140010229  mov     r8b, [rbp+arg_8]
0x14001022d  mov     rdx, r15
0x140010230  mov     rcx, rsi
0x140010233  xor     r12d, r12d
0x140010236  call    WanpAllocateAndInitializeConnectionEntry
0x14001023b  mov     [rbp+P], rax
0x14001023f  test    rax, rax
0x140010242  jz      short loc_14001027B
0x140010244  movzx   eax, word ptr [rsi+32h]
0x140010248  lea     ecx, [rax+40h]
0x14001024b  cmp     ecx, eax
0x14001024d  jnb     short loc_140010256
0x14001024f  mov     ebx, 0C0000095h
0x140010254  jmp     short loc_140010280
0x140010256  mov     edx, ecx
0x140010258  mov     r8d, 6C707277h
0x14001025e  mov     ecx, 40h ; '@'
0x140010263  call    cs:__imp_ExAllocatePool2
0x14001026a  nop     dword ptr [rax+rax+00h]
0x14001026f  mov     r12, rax
0x140010272  test    rax, rax
0x140010275  jnz     loc_14001030E
0x14001027b  mov     ebx, 0C000009Ah
0x140010280  mov     rax, [rbp+arg_10]
0x140010284  mov     ecx, [rax]
0x140010286  cmp     ecx, r14d
0x140010289  jnz     short loc_1400102B0
0x14001028b  cmp     [rbp+arg_8], 0
0x14001028f  jnz     short loc_14001029A
0x140010291  mov     rax, [r15+0A8h]
0x140010298  jmp     short loc_1400102A1
0x14001029a  mov     rax, [r15+0B0h]
0x1400102a1  test    rax, rax
0x1400102a4  jnz     short loc_1400102D2
0x1400102a6  mov     rcx, r15; P
0x1400102a9  call    WanpDeleteAdapter
0x1400102ae  jmp     short loc_1400102D2
  ... truncated ...
```
