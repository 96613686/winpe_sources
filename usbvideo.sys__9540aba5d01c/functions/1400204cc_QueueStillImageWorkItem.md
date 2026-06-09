# QueueStillImageWorkItem

- ea: `0x1400204cc`
- end: `0x1400206fb`
- name: `QueueStillImageWorkItem`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400105b8`

## callees

- `0x14001ab4c`
- `0x14001b15c`
- `0x1400204cc`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140020584`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400206cc`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140020584`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400206cc`
- `ntoskrnl!IoQueueWorkItem` at `0x140020652`
- `ntoskrnl!IoQueueWorkItem` at `0x140020652`
- `ntoskrnl!IoFreeWorkItem` at `0x1400206b0`
- `ntoskrnl!IoFreeWorkItem` at `0x1400206b0`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002055d`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002055d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140020543`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140020543`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400205e6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400205e6`

## pseudocode

```c
__int64 __fastcall QueueStillImageWorkItem(__int64 a1, struct _IO_REMOVE_LOCK *a2, char a3, char a4, char a5, int a6)
{
  unsigned int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  struct _IO_REMOVE_LOCK *v13; // r9
  struct _IO_REMOVE_LOCK *v14; // rbp
  struct _IO_WORKITEM *WorkItem; // rsi
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  _BYTE *PoolWithTag; // rax

  if ( !a2 )
  {
    v10 = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v12 = 142;
      v13 = 0;
LABEL_17:
      WPP_SF_q(v11->AttachedDevice, v12, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v13);
      return v10;
    }
    return v10;
  }
  v14 = a2 + 24;
  v10 = IoAcquireRemoveLockEx(a2 + 24, USBVideoWorkItemHandler, File, 1u, 0x20u);
  if ( (v10 & 0x80000000) != 0 )
    return v10;
  WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(a1 + 24));
  if ( !WorkItem )
  {
    v10 = -1073741670;
    IoReleaseRemoveLockEx(v14, USBVideoWorkItemHandler, 0x20u);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      return v10;
    v17 = 143;
    goto LABEL_10;
  }
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, 0x20u, 0x56425355u);
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_14;
LABEL_20:
    v10 = -1073741670;
    IoFreeWorkItem(WorkItem);
    IoReleaseRemoveLockEx(v14, USBVideoWorkItemHandler, 0x20u);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      return v10;
    v17 = 144;
LABEL_10:
    WPP_SF_qD(v16->AttachedDevice, v17, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, a2, -1073741670);
    return v10;
  }
  if ( !PoolWithTag )
    goto LABEL_20;
  PoolWithTag[23] = 0;
  *((_DWORD *)PoolWithTag + 7) = 0;
LABEL_14:
  *((_DWORD *)PoolWithTag + 4) = 0;
  PoolWithTag[21] = a3;
  PoolWithTag[20] = a4;
  *((_QWORD *)PoolWithTag + 1) = a2;
  *(_QWORD *)PoolWithTag = WorkItem;
  *((_DWORD *)PoolWithTag + 6) = a6;
  PoolWithTag[22] = a5;
  IoQueueWorkItem(WorkItem, USBVideoWorkItemHandler, DelayedWorkQueue, PoolWithTag);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v12 = 145;
    v13 = a2;
    goto LABEL_17;
  }
  return v10;
}

```

## disassembly

```asm
0x1400204cc  push    rbx
0x1400204ce  push    rbp
0x1400204cf  push    rsi
0x1400204d0  push    rdi
0x1400204d1  push    r14
0x1400204d3  push    r15
0x1400204d5  sub     rsp, 38h
0x1400204d9  mov     r14b, r9b
0x1400204dc  mov     r15b, r8b
0x1400204df  mov     rdi, rdx
0x1400204e2  mov     rsi, rcx
0x1400204e5  test    rdx, rdx
0x1400204e8  jnz     short loc_14002051D
0x1400204ea  mov     ebx, 0C000000Dh
0x1400204ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400204f6  lea     rax, WPP_GLOBAL_Control
0x1400204fd  cmp     rcx, rax
0x140020500  jz      loc_14002068F
0x140020506  cmp     byte ptr [rcx+29h], 3
0x14002050a  jb      loc_14002068F
0x140020510  mov     edx, 8Eh
0x140020515  xor     r9d, r9d
0x140020518  jmp     loc_14002067F
0x14002051d  lea     rbp, [rdx+300h]
0x140020524  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14002052c  mov     rcx, rbp; RemoveLock
0x14002052f  lea     r8, File; File
0x140020536  mov     r9d, 1; Line
0x14002053c  lea     rdx, USBVideoWorkItemHandler; Tag
0x140020543  call    cs:__imp_IoAcquireRemoveLockEx
0x14002054a  nop     dword ptr [rax+rax+00h]
0x14002054f  mov     ebx, eax
0x140020551  test    eax, eax
0x140020553  js      loc_14002068F
0x140020559  mov     rcx, [rsi+18h]; DeviceObject
0x14002055d  call    cs:__imp_IoAllocateWorkItem
0x140020564  nop     dword ptr [rax+rax+00h]
0x140020569  mov     rsi, rax
0x14002056c  test    rax, rax
0x14002056f  jnz     short loc_1400205D6
0x140020571  lea     r8d, [rax+20h]; RemlockSize
0x140020575  mov     rcx, rbp; RemoveLock
0x140020578  lea     rdx, USBVideoWorkItemHandler; Tag
0x14002057f  mov     ebx, 0C000009Ah
0x140020584  call    cs:__imp_IoReleaseRemoveLockEx
0x14002058b  nop     dword ptr [rax+rax+00h]
0x140020590  mov     rcx, cs:WPP_GLOBAL_Control
0x140020597  lea     rax, WPP_GLOBAL_Control
0x14002059e  cmp     rcx, rax
0x1400205a1  jz      loc_14002068F
0x1400205a7  cmp     byte ptr [rcx+29h], 3
0x1400205ab  jb      loc_14002068F
0x1400205b1  mov     edx, 8Fh
0x1400205b6  mov     rcx, [rcx+18h]
0x1400205ba  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x1400205c1  mov     r9, rdi
0x1400205c4  mov     [rsp+68h+RemlockSize], 0C000009Ah
0x1400205cc  call    WPP_SF_qD
0x1400205d1  jmp     loc_14002068F
0x1400205d6  mov     edx, 20h ; ' '; NumberOfBytes
0x1400205db  mov     ecx, 600h; PoolType
0x1400205e0  mov     r8d, 56425355h; Tag
0x1400205e6  call    cs:__imp_ExAllocatePoolWithTag
0x1400205ed  nop     dword ptr [rax+rax+00h]
0x1400205f2  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400205f9  mov     r9, rax; Context
0x1400205fc  jnz     loc_14002069F
0x140020602  test    rax, rax
0x140020605  jz      loc_1400206A8
0x14002060b  mov     byte ptr [rax+17h], 0
0x14002060f  mov     dword ptr [rax+1Ch], 0
0x140020616  mov     dword ptr [rax+10h], 0
0x14002061d  lea     rdx, USBVideoWorkItemHandler; WorkerRoutine
0x140020624  mov     [rax+15h], r15b
0x140020628  mov     r8d, 1; QueueType
0x14002062e  mov     [rax+14h], r14b
0x140020632  mov     rcx, rsi; IoWorkItem
0x140020635  mov     [rax+8], rdi
0x140020639  mov     [rax], rsi
0x14002063c  mov     eax, [rsp+68h+arg_28]
0x140020643  mov     [r9+18h], eax
0x140020647  mov     al, [rsp+68h+arg_20]
0x14002064e  mov     [r9+16h], al
0x140020652  call    cs:__imp_IoQueueWorkItem
0x140020659  nop     dword ptr [rax+rax+00h]
0x14002065e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020665  lea     rax, WPP_GLOBAL_Control
0x14002066c  cmp     rcx, rax
0x14002066f  jz      short loc_14002068F
0x140020671  cmp     byte ptr [rcx+29h], 4
0x140020675  jb      short loc_14002068F
0x140020677  mov     edx, 91h
0x14002067c  mov     r9, rdi
0x14002067f  mov     rcx, [rcx+18h]
0x140020683  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14002068a  call    WPP_SF_q
0x14002068f  mov     eax, ebx
0x140020691  add     rsp, 38h
0x140020695  pop     r15
0x140020697  pop     r14
0x140020699  pop     rdi
0x14002069a  pop     rsi
0x14002069b  pop     rbp
0x14002069c  pop     rbx
0x14002069d  retn
0x14002069f  test    r9, r9
0x1400206a2  jnz     loc_140020616
0x1400206a8  mov     rcx, rsi; IoWorkItem
0x1400206ab  mov     ebx, 0C000009Ah
0x1400206b0  call    cs:__imp_IoFreeWorkItem
0x1400206b7  nop     dword ptr [rax+rax+00h]
0x1400206bc  mov     r8d, 20h ; ' '; RemlockSize
0x1400206c2  lea     rdx, USBVideoWorkItemHandler; Tag
0x1400206c9  mov     rcx, rbp; RemoveLock
0x1400206cc  call    cs:__imp_IoReleaseRemoveLockEx
0x1400206d3  nop     dword ptr [rax+rax+00h]
0x1400206d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206df  lea     rax, WPP_GLOBAL_Control
0x1400206e6  cmp     rcx, rax
0x1400206e9  jz      short loc_14002068F
0x1400206eb  cmp     byte ptr [rcx+29h], 3
0x1400206ef  jb      short loc_14002068F
0x1400206f1  mov     edx, 90h
0x1400206f6  jmp     loc_1400205B6
```
