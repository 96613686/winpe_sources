# UnionFs::UfsPathCacheManager::StopCacheManagerWorkers(void)

- ea: `0x14003ea94`
- end: `0x14003ec21`
- name: `?StopCacheManagerWorkers@UfsPathCacheManager@UnionFs@@QEAAXXZ`
- size: `397`
- prototype: `void __fastcall(UnionFs::UfsPathCacheManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140006390`
- `0x14003de50`

## callees

- `0x14003b728`
- `0x14003ea94`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003eab9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003eab9`
- `ntoskrnl!KeCancelTimer` at `0x14003eaea`
- `ntoskrnl!KeCancelTimer` at `0x14003eaea`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003eb5e`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003eb5e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003eace`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003eace`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ebf9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ebf9`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003eb76`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003eb99`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003eb76`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14003eb99`

## pseudocode

```c
void __fastcall UnionFs::UfsPathCacheManager::StopCacheManagerWorkers(UnionFs::UfsPathCacheManager *this)
{
  unsigned __int8 v2; // dl
  __int64 v3; // rcx
  ULONG v4; // r10d
  struct _FLT_GENERIC_WORKITEM *v5; // rcx
  struct _FLT_GENERIC_WORKITEM *v6; // rcx
  UnionFs::UfsPathCacheListItem **v7; // rsi
  UnionFs::UfsPathCacheListItem *v8; // rdi
  UnionFs::UfsPathCacheListItem *v9; // rax
  PVOID Object[2]; // [rsp+40h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this, &LockHandle);
  *((_BYTE *)this + 8) = 0;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v2 = 0;
  if ( *((_QWORD *)this + 28) )
  {
    KeCancelTimer((PKTIMER)((char *)this + 16));
    v2 = 1;
  }
  v3 = *((_QWORD *)this + 34);
  *(_OWORD *)Object = 0;
  if ( v2 )
    Object[0] = (char *)this + 240;
  v4 = v2;
  if ( v3 )
  {
    Object[v2] = (char *)this + 376;
    v4 = v2 + 1;
  }
  if ( v4 )
    KeWaitForMultipleObjects(v4, Object, WaitAll, Executive, 0, 0, 0, 0);
  v5 = (struct _FLT_GENERIC_WORKITEM *)*((_QWORD *)this + 28);
  if ( v5 )
    FltFreeGenericWorkItem(v5);
  *((_QWORD *)this + 28) = 0;
  v6 = (struct _FLT_GENERIC_WORKITEM *)*((_QWORD *)this + 34);
  if ( v6 )
    FltFreeGenericWorkItem(v6);
  *((_QWORD *)this + 34) = 0;
  v7 = (UnionFs::UfsPathCacheListItem **)((char *)this + 144);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == (UnionFs::UfsPathCacheListItem *)v7 )
      break;
    if ( *((UnionFs::UfsPathCacheListItem ***)v8 + 1) != v7
      || (v9 = *(UnionFs::UfsPathCacheListItem **)v8, *(UnionFs::UfsPathCacheListItem **)(*(_QWORD *)v8 + 8LL) != v8) )
    {
      __fastfail(3u);
    }
    *v7 = v9;
    *((_QWORD *)v9 + 1) = v7;
    --*((_DWORD *)this + 54);
    if ( v8 )
    {
      UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(v8);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v8);
    }
  }
}

```

## disassembly

```asm
0x14003ea94  mov     r11, rsp
0x14003ea97  mov     [r11+8], rbx
0x14003ea9b  mov     [r11+10h], rsi
0x14003ea9f  push    rdi
0x14003eaa0  sub     rsp, 70h
0x14003eaa4  xorps   xmm0, xmm0
0x14003eaa7  lea     rdx, [r11-28h]; LockHandle
0x14003eaab  xor     eax, eax
0x14003eaad  mov     rbx, rcx
0x14003eab0  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14003eab5  mov     [r11-18h], rax
0x14003eab9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003eac0  nop     dword ptr [rax+rax+00h]
0x14003eac5  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14003eaca  mov     byte ptr [rbx+8], 0
0x14003eace  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003ead5  nop     dword ptr [rax+rax+00h]
0x14003eada  xor     dl, dl
0x14003eadc  lea     rcx, [rbx+10h]; PKTIMER
0x14003eae0  cmp     qword ptr [rcx+0D0h], 0
0x14003eae8  jz      short loc_14003EAF8
0x14003eaea  call    cs:__imp_KeCancelTimer
0x14003eaf1  nop     dword ptr [rax+rax+00h]
0x14003eaf6  mov     dl, 1
0x14003eaf8  mov     rcx, [rbx+110h]
0x14003eaff  xorps   xmm0, xmm0
0x14003eb02  movups  xmmword ptr [rsp+78h+Object], xmm0
0x14003eb07  test    dl, dl
0x14003eb09  jz      short loc_14003EB17
0x14003eb0b  lea     rax, [rbx+0F0h]
0x14003eb12  mov     [rsp+78h+Object], rax
0x14003eb17  movzx   r10d, dl
0x14003eb1b  test    rcx, rcx
0x14003eb1e  jz      short loc_14003EB2F
0x14003eb20  lea     rcx, [rbx+178h]
0x14003eb27  mov     [rsp+r10*8+78h+Object], rcx
0x14003eb2c  inc     r10d
0x14003eb2f  test    r10d, r10d
0x14003eb32  jz      short loc_14003EB6A
0x14003eb34  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14003eb3d  lea     rdx, [rsp+78h+Object]; Object
0x14003eb42  mov     [rsp+78h+Timeout], 0; Timeout
0x14003eb4b  xor     r9d, r9d; WaitReason
0x14003eb4e  mov     [rsp+78h+Alertable], 0; Alertable
0x14003eb53  xor     r8d, r8d; WaitType
0x14003eb56  mov     ecx, r10d; Count
0x14003eb59  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14003eb5e  call    cs:__imp_KeWaitForMultipleObjects
0x14003eb65  nop     dword ptr [rax+rax+00h]
0x14003eb6a  mov     rcx, [rbx+0E0h]; FltWorkItem
0x14003eb71  test    rcx, rcx
0x14003eb74  jz      short loc_14003EB82
0x14003eb76  call    cs:__imp_FltFreeGenericWorkItem
0x14003eb7d  nop     dword ptr [rax+rax+00h]
0x14003eb82  mov     qword ptr [rbx+0E0h], 0
0x14003eb8d  mov     rcx, [rbx+110h]; FltWorkItem
0x14003eb94  test    rcx, rcx
0x14003eb97  jz      short loc_14003EBA5
0x14003eb99  call    cs:__imp_FltFreeGenericWorkItem
0x14003eba0  nop     dword ptr [rax+rax+00h]
0x14003eba5  mov     qword ptr [rbx+110h], 0
0x14003ebb0  lea     rsi, [rbx+90h]
0x14003ebb7  mov     rdi, [rsi]
0x14003ebba  cmp     rdi, rsi
0x14003ebbd  jz      short loc_14003EC0E
0x14003ebbf  cmp     [rdi+8], rsi
0x14003ebc3  jnz     short loc_14003EC07
0x14003ebc5  mov     rax, [rdi]
0x14003ebc8  cmp     [rax+8], rdi
0x14003ebcc  jnz     short loc_14003EC07
0x14003ebce  mov     [rsi], rax
0x14003ebd1  mov     [rax+8], rsi
0x14003ebd5  dec     dword ptr [rbx+0D8h]
0x14003ebdb  test    rdi, rdi
0x14003ebde  jz      short loc_14003EBB7
0x14003ebe0  mov     rcx, rdi; this
0x14003ebe3  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003ebe8  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003ebef  mov     rdx, rdi; Entry
0x14003ebf2  add     rcx, 3E0h; Lookaside
0x14003ebf9  call    cs:__imp_ExFreeToLookasideListEx
0x14003ec00  nop     dword ptr [rax+rax+00h]
0x14003ec05  jmp     short loc_14003EBB7
0x14003ec07  mov     ecx, 3
0x14003ec0c  int     29h; Win8: RtlFailFast(ecx)
0x14003ec0e  lea     r11, [rsp+78h+var_8]
0x14003ec13  mov     rbx, [r11+10h]
0x14003ec17  mov     rsi, [r11+18h]
0x14003ec1b  mov     rsp, r11
0x14003ec1e  pop     rdi
0x14003ec1f  retn
```
