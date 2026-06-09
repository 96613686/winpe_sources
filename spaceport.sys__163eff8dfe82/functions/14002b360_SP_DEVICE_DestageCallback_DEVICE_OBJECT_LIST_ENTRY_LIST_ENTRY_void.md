# SP_DEVICE::DestageCallback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x14002b360`
- end: `0x14002b600`
- name: `?DestageCallback@SP_DEVICE@@SAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140008a00`
- `0x14000bd00`
- `0x140011970`
- `0x140014fd0`
- `0x14001e160`
- `0x140027600`
- `0x14002aadc`
- `0x14002ab88`
- `0x14002b360`
- `0x14002b608`
- `0x14002c2b4`
- `0x14003c778`
- `0x1400466a8`
- `0x140068150`
- `0x1400adc34`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002b40b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002b40b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002b438`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002b438`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b536`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b536`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002b453`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002b453`

## pseudocode

```c
__int64 __fastcall SP_DEVICE::DestageCallback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        void *a4)
{
  char *v4; // r14
  int v5; // r15d
  int v6; // esi
  __int64 v7; // rax
  __int64 v8; // r8
  char *v9; // rbx
  SIO_CACHE *v10; // rcx
  int DestageMapRanges; // eax
  __int64 v12; // rdx
  struct SDB_RANGES *v13; // rbx
  int updated; // eax
  int v15; // ecx
  int v16; // r8d
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[76]; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+9Ch] [rbp-64h]
  char v21; // [rsp+F9h] [rbp-7h]
  int v22; // [rsp+104h] [rbp+4h]
  char *v23; // [rsp+138h] [rbp+38h]
  __int64 v24; // [rsp+140h] [rbp+40h]
  PVOID P; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = (char *)a1->DeviceExtension + 8;
  v5 = *(_DWORD *)(*((_QWORD *)a1->DeviceExtension + 18) + 572LL);
  SIO_CACHE_PACKET::SIO_CACHE_PACKET((SIO_CACHE_PACKET *)v19);
  v6 = SP_DEVICE::FlushDestage((PEX_RUNDOWN_REF_CACHE_AWARE *)v4);
  if ( v6 < 0 )
    goto LABEL_21;
  v6 = SP_DEVICE::AcquireRundownSharedNonQueued((PEX_RUNDOWN_REF_CACHE_AWARE *)v4);
  if ( v6 < 0 )
    goto LABEL_21;
  do
  {
    v20 |= 0x20000008u;
    v21 = 36;
    v22 = 0;
    v23 = v4;
    v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 80LL))(v4);
    LOBYTE(v8) = 36;
    v24 = v7;
    SC_DISPATCH::Dispatch(v4, v19, v8);
    v6 = v22;
    ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v4 + 30));
    if ( !v6 )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v4 + 167, &LockHandle);
      v9 = (char *)*((_QWORD *)v4 + 162);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      if ( v9 != v4 + 1296 )
        v6 = -1058602971;
    }
    v22 = v6;
    switch ( v6 )
    {
      case -1058602989:
        updated = SpUpdateColumn((struct SP_DEVICE *)v4);
        SIO_CACHE::UpdateDestageStatus(*((SIO_CACHE **)v4 + 17), (struct SIO_CACHE_PACKET *)v19, updated);
        break;
      case -1058602988:
        v10 = (SIO_CACHE *)*((_QWORD *)v4 + 17);
        P = 0;
        DestageMapRanges = SIO_CACHE::GetDestageMapRanges(v10, (struct SIO_CACHE_PACKET *)v19, (struct SDB_RANGES **)&P);
        v13 = (struct SDB_RANGES *)P;
        if ( DestageMapRanges >= 0 )
        {
          LOBYTE(v12) = 2;
          DestageMapRanges = SpMapExtents(v4, v12, P);
        }
        SIO_CACHE::UpdateDestageMapStatus(
          *((SIO_CACHE **)v4 + 17),
          (struct SIO_CACHE_PACKET *)v19,
          v13,
          DestageMapRanges);
        if ( v13 )
          ExFreePoolWithTag(v13, 0);
        break;
      case -1058602971:
        v6 = SP_DEVICE::FlushDestage((PEX_RUNDOWN_REF_CACHE_AWARE *)v4);
        SIO_CACHE::UpdateDestageStatus(*((SIO_CACHE **)v4 + 17), (struct SIO_CACHE_PACKET *)v19, v6);
        if ( v6 < 0 )
          goto LABEL_21;
        SP_WORKITEM::Insert(v4 + 1136, 0, 0, 0);
        break;
      case 15138818:
        goto LABEL_20;
      default:
        if ( v6 < 0 )
          goto LABEL_21;
        break;
    }
    v6 = SP_DEVICE::AcquireRundownSharedNonQueued((PEX_RUNDOWN_REF_CACHE_AWARE *)v4);
  }
  while ( v6 >= 0 );
LABEL_20:
  if ( v6 < 0 )
  {
LABEL_21:
    SIO_CACHE::AbortDestage(*((SIO_CACHE **)v4 + 17), (struct SIO_CACHE_PACKET *)v19, v6);
    if ( v6 != v5 )
    {
      if ( v6 != -1073741810 )
      {
        if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
          McTemplateK0juq_EtwWriteTransfer(v15, (unsigned int)SpaceDestageError, v16, (_DWORD)v4 + 40, 36, v6);
        goto LABEL_26;
      }
      goto LABEL_27;
    }
  }
  if ( v6 != -1073741810 )
LABEL_26:
    SP_WORKITEM::Insert(v4 + 1136, 0, 0, 0);
LABEL_27:
  SIO_CACHE_PACKET::~SIO_CACHE_PACKET((SIO_CACHE_PACKET *)v19);
  return 0;
}

```

## disassembly

```asm
0x14002b360  mov     [rsp-8+arg_8], rbx
0x14002b365  mov     [rsp-8+arg_10], rsi
0x14002b36a  push    rbp
0x14002b36b  push    rdi
0x14002b36c  push    r13
0x14002b36e  push    r14
0x14002b370  push    r15
0x14002b372  lea     rbp, [rsp-80h]
0x14002b377  sub     rsp, 180h
0x14002b37e  mov     r14, [rcx+40h]
0x14002b382  lea     rcx, [rsp+1A0h+var_150]; this
0x14002b387  add     r14, 8
0x14002b38b  mov     rax, [r14+88h]
0x14002b392  mov     r15d, [rax+23Ch]
0x14002b399  call    ??0SIO_CACHE_PACKET@@QEAA@XZ; SIO_CACHE_PACKET::SIO_CACHE_PACKET(void)
0x14002b39e  mov     rcx, r14; this
0x14002b3a1  call    ?FlushDestage@SP_DEVICE@@QEAAJXZ; SP_DEVICE::FlushDestage(void)
0x14002b3a6  mov     esi, eax
0x14002b3a8  test    eax, eax
0x14002b3aa  js      loc_14002B576
0x14002b3b0  mov     rcx, r14; this
0x14002b3b3  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14002b3b8  mov     esi, eax
0x14002b3ba  test    eax, eax
0x14002b3bc  js      loc_14002B576
0x14002b3c2  mov     r13d, 0C0E70025h
0x14002b3c8  or      [rbp+0A0h+var_104], 20000008h
0x14002b3cf  mov     rcx, r14
0x14002b3d2  mov     [rbp+0A0h+var_A7], 24h ; '$'
0x14002b3d6  mov     [rbp+0A0h+var_9C], 0
0x14002b3dd  mov     [rbp+0A0h+var_68], r14
0x14002b3e1  mov     rax, [r14]
0x14002b3e4  mov     rax, [rax+50h]
0x14002b3e8  call    _guard_dispatch_icall
0x14002b3ed  mov     r8b, 24h ; '$'
0x14002b3f0  mov     [rbp+0A0h+var_60], rax
0x14002b3f4  lea     rdx, [rsp+1A0h+var_150]
0x14002b3f9  mov     rcx, r14
0x14002b3fc  call    ?Dispatch@SC_DISPATCH@@QEAAXPEAVSC_PACKET@@W4_SC_OPERATION@@@Z; SC_DISPATCH::Dispatch(SC_PACKET *,_SC_OPERATION)
0x14002b401  mov     esi, [rbp+0A0h+var_9C]
0x14002b404  mov     rcx, [r14+0F0h]; RunRefCacheAware
0x14002b40b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14002b412  nop     dword ptr [rax+rax+00h]
0x14002b417  test    esi, esi
0x14002b419  jnz     short loc_14002B466
0x14002b41b  xorps   xmm0, xmm0
0x14002b41e  mov     [rsp+1A0h+LockHandle.LockQueue.Next], 0
0x14002b427  lea     rcx, [r14+538h]; SpinLock
0x14002b42e  lea     rdx, [rsp+1A0h+LockHandle]; LockHandle
0x14002b433  movups  xmmword ptr [rsp+1A0h+LockHandle.LockQueue.Lock], xmm0
0x14002b438  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002b43f  nop     dword ptr [rax+rax+00h]
0x14002b444  lea     rdi, [r14+510h]
0x14002b44b  mov     rbx, [rdi]
0x14002b44e  lea     rcx, [rsp+1A0h+LockHandle]; LockHandle
0x14002b453  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002b45a  nop     dword ptr [rax+rax+00h]
0x14002b45f  cmp     rbx, rdi
0x14002b462  cmovnz  esi, r13d
0x14002b466  mov     [rbp+0A0h+var_9C], esi
0x14002b469  cmp     esi, 0C0E70013h
0x14002b46f  jz      loc_14002B544
0x14002b475  cmp     esi, 0C0E70014h
0x14002b47b  jz      short loc_14002B4DA
0x14002b47d  cmp     esi, r13d
0x14002b480  jz      short loc_14002B49B
0x14002b482  cmp     esi, 0E70002h
0x14002b488  jz      loc_14002B572
0x14002b48e  test    esi, esi
0x14002b490  js      loc_14002B576
0x14002b496  jmp     loc_14002B560
0x14002b49b  mov     rcx, r14; this
0x14002b49e  call    ?FlushDestage@SP_DEVICE@@QEAAJXZ; SP_DEVICE::FlushDestage(void)
0x14002b4a3  mov     rcx, [r14+88h]; this
0x14002b4aa  lea     rdx, [rsp+1A0h+var_150]; struct SIO_CACHE_PACKET *
0x14002b4af  mov     r8d, eax; int
0x14002b4b2  mov     esi, eax
0x14002b4b4  call    ?UpdateDestageStatus@SIO_CACHE@@QEAAXPEAVSIO_CACHE_PACKET@@J@Z; SIO_CACHE::UpdateDestageStatus(SIO_CACHE_PACKET *,long)
0x14002b4b9  test    esi, esi
0x14002b4bb  js      loc_14002B576
0x14002b4c1  lea     rcx, [r14+470h]; Context
0x14002b4c8  xor     r9d, r9d; unsigned __int8
0x14002b4cb  xor     r8d, r8d; unsigned int
0x14002b4ce  xor     edx, edx; struct _LIST_ENTRY *
0x14002b4d0  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14002b4d5  jmp     loc_14002B560
0x14002b4da  mov     rcx, [r14+88h]; this
0x14002b4e1  lea     r8, [rbp+0A0h+P]; struct SDB_RANGES **
0x14002b4e8  lea     rdx, [rsp+1A0h+var_150]; struct SIO_CACHE_PACKET *
0x14002b4ed  mov     [rbp+0A0h+P], 0
0x14002b4f8  call    ?GetDestageMapRanges@SIO_CACHE@@QEAAJPEAVSIO_CACHE_PACKET@@PEAPEAVSDB_RANGES@@@Z; SIO_CACHE::GetDestageMapRanges(SIO_CACHE_PACKET *,SDB_RANGES * *)
0x14002b4fd  mov     rbx, [rbp+0A0h+P]
0x14002b504  test    eax, eax
0x14002b506  js      short loc_14002B515
0x14002b508  mov     r8, rbx
0x14002b50b  mov     dl, 2
0x14002b50d  mov     rcx, r14
0x14002b510  call    ?SpMapExtents@@YAJPEAVSP_DEVICE@@W4_SC_SPACE_USAGE@@PEAVSDB_RANGES@@@Z; SpMapExtents(SP_DEVICE *,_SC_SPACE_USAGE,SDB_RANGES *)
0x14002b515  mov     rcx, [r14+88h]; this
0x14002b51c  lea     rdx, [rsp+1A0h+var_150]; struct SIO_CACHE_PACKET *
0x14002b521  mov     r9d, eax; int
0x14002b524  mov     r8, rbx; struct SDB_RANGES *
0x14002b527  call    ?UpdateDestageMapStatus@SIO_CACHE@@QEAAXPEAVSIO_CACHE_PACKET@@PEAVSDB_RANGES@@J@Z; SIO_CACHE::UpdateDestageMapStatus(SIO_CACHE_PACKET *,SDB_RANGES *,long)
0x14002b52c  test    rbx, rbx
0x14002b52f  jz      short loc_14002B560
0x14002b531  xor     edx, edx; Tag
0x14002b533  mov     rcx, rbx; P
0x14002b536  call    cs:__imp_ExFreePoolWithTag
0x14002b53d  nop     dword ptr [rax+rax+00h]
0x14002b542  jmp     short loc_14002B560
0x14002b544  mov     rcx, r14; this
0x14002b547  call    ?SpUpdateColumn@@YAJPEAVSP_DEVICE@@@Z; SpUpdateColumn(SP_DEVICE *)
0x14002b54c  mov     rcx, [r14+88h]; this
0x14002b553  lea     rdx, [rsp+1A0h+var_150]; struct SIO_CACHE_PACKET *
0x14002b558  mov     r8d, eax; int
0x14002b55b  call    ?UpdateDestageStatus@SIO_CACHE@@QEAAXPEAVSIO_CACHE_PACKET@@J@Z; SIO_CACHE::UpdateDestageStatus(SIO_CACHE_PACKET *,long)
0x14002b560  mov     rcx, r14; this
0x14002b563  call    ?AcquireRundownSharedNonQueued@SP_DEVICE@@QEAAJXZ; SP_DEVICE::AcquireRundownSharedNonQueued(void)
0x14002b568  mov     esi, eax
0x14002b56a  test    eax, eax
0x14002b56c  jns     loc_14002B3C8
0x14002b572  test    esi, esi
0x14002b574  jns     short loc_14002B5BB
0x14002b576  mov     rcx, [r14+88h]; this
0x14002b57d  lea     rdx, [rsp+1A0h+var_150]; struct SIO_CACHE_PACKET *
0x14002b582  mov     r8d, esi; int
0x14002b585  call    ?AbortDestage@SIO_CACHE@@QEAAXPEAVSIO_CACHE_PACKET@@J@Z; SIO_CACHE::AbortDestage(SIO_CACHE_PACKET *,long)
0x14002b58a  cmp     esi, r15d
0x14002b58d  jz      short loc_14002B5BB
0x14002b58f  cmp     esi, 0C000000Eh
0x14002b595  jz      short loc_14002B5D7
0x14002b597  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14002b59e  jz      short loc_14002B5C3
0x14002b5a0  lea     r9, [r14+28h]
0x14002b5a4  mov     [rsp+1A0h+var_178], esi
0x14002b5a8  lea     rdx, SpaceDestageError
0x14002b5af  mov     [rsp+1A0h+var_180], 24h ; '$'
0x14002b5b4  call    McTemplateK0juq_EtwWriteTransfer
0x14002b5b9  jmp     short loc_14002B5C3
0x14002b5bb  cmp     esi, 0C000000Eh
0x14002b5c1  jz      short loc_14002B5D7
0x14002b5c3  lea     rcx, [r14+470h]; Context
0x14002b5ca  xor     r9d, r9d; unsigned __int8
0x14002b5cd  xor     r8d, r8d; unsigned int
0x14002b5d0  xor     edx, edx; struct _LIST_ENTRY *
0x14002b5d2  call    ?Insert@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@KE@Z; SP_WORKITEM::Insert(_LIST_ENTRY *,ulong,uchar)
0x14002b5d7  lea     rcx, [rsp+1A0h+var_150]; this
0x14002b5dc  call    ??1SIO_CACHE_PACKET@@UEAA@XZ; SIO_CACHE_PACKET::~SIO_CACHE_PACKET(void)
0x14002b5e1  lea     r11, [rsp+1A0h+var_20]
0x14002b5e9  xor     eax, eax
0x14002b5eb  mov     rbx, [r11+38h]
0x14002b5ef  mov     rsi, [r11+40h]
0x14002b5f3  mov     rsp, r11
0x14002b5f6  pop     r15
0x14002b5f8  pop     r14
0x14002b5fa  pop     r13
0x14002b5fc  pop     rdi
0x14002b5fd  pop     rbp
0x14002b5fe  retn
```
