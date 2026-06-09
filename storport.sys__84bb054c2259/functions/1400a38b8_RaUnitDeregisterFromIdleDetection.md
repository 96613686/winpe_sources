# RaUnitDeregisterFromIdleDetection

- ea: `0x1400a38b8`
- end: `0x1400a3bc1`
- name: `RaUnitDeregisterFromIdleDetection`
- size: `777`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400c213c`
- `0x140196c60`

## callees

- `0x1400016cc`
- `0x140003b80`
- `0x140004cb4`
- `0x140005c50`
- `0x140012174`
- `0x1400342b0`
- `0x14004912c`
- `0x14009d424`
- `0x1400a38b8`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x1400a3aec`
- `ntoskrnl!PoFxIdleComponent` at `0x1400a3aec`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1400a3a2a`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1400a3a2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a3b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a3b96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a3b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a3b96`
- `ntoskrnl!PoUnregisterCoalescingCallback` at `0x1400a39ff`
- `ntoskrnl!PoUnregisterCoalescingCallback` at `0x1400a39ff`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400a3aff`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400a3aff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a398e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a39cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a398e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400a39cb`
- `ntoskrnl!ExDeleteTimer` at `0x1400a3a5e`
- `ntoskrnl!ExDeleteTimer` at `0x1400a3a99`
- `ntoskrnl!ExDeleteTimer` at `0x1400a3a5e`
- `ntoskrnl!ExDeleteTimer` at `0x1400a3a99`
- `ntoskrnl!PoFxUnregisterDevice` at `0x1400a3b85`
- `ntoskrnl!PoFxUnregisterDevice` at `0x1400a3b85`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400a3b30`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400a3b30`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a39a6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a39e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a39a6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400a39e3`

## pseudocode

```c
void __fastcall RaUnitDeregisterFromIdleDetection(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rdx
  void *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  char v8; // al
  __int64 v9; // rdi
  __int64 v10; // r9
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v11; // rcx
  _QWORD *v12; // rdi
  void *v13; // rcx
  __int128 v14; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+30h] [rbp-40h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-38h] BYREF
  __int128 v17; // [rsp+50h] [rbp-20h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (unsigned __int8)RaidUnitIsRegisteredForIdleDetection(a1) )
  {
    if ( *(_QWORD *)(v2 + 24)
      && (*(_DWORD *)(*(_QWORD *)(v2 + 1872) + 32LL) & 4) != 0
      && (unsigned __int8)RaidIsUnitControlSupported(a1, 4) )
    {
      v3 = *(_QWORD *)(a1 + 24);
      v15 = 0;
      v17 = 0;
      LOWORD(v17) = 1;
      v14 = 0;
      DWORD1(v17) = 4;
      WORD1(v17) = *(_WORD *)(v3 + 56);
      WORD4(v17) = *(_WORD *)(a1 + 104);
      BYTE10(v17) = *(_BYTE *)(a1 + 106);
      *((_QWORD *)&v14 + 1) = &v17;
      *(_QWORD *)&v14 = 0x1800000001LL;
      RaCallMiniportUnitControl(v3 + 360, 4, &v14);
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 48), &LockHandle);
    RaidUnitCancelWaitWakeIrp(a1);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    RaidUnitReenablePendingTimer(a1, 0);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 1872) + 96LL), &LockHandle);
    StorPortUnitFlushActivePendingRequestQueue(a1);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 104LL) )
    {
      PoUnregisterCoalescingCallback();
      *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 104LL) = 0;
    }
    v5 = *(void **)(*(_QWORD *)(a1 + 1872) + 112LL);
    if ( v5 )
    {
      PoUnregisterPowerSettingCallback(v5);
      *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 112LL) = 0;
    }
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 120LL);
    if ( v6 )
    {
      LOBYTE(v4) = 1;
      ExDeleteTimer(v6, v4, 0, 0);
      *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 120LL) = 0;
    }
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 128LL);
    if ( v7 )
    {
      LOBYTE(v4) = 1;
      v8 = ExDeleteTimer(v7, v4, 0, 0);
      *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 128LL) = 0;
      if ( v8 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1872) + 148LL) & 1) != 0 )
        {
          v9 = *(_QWORD *)(a1 + 24);
          if ( (unsigned __int8)RaidUnitCheckAndAcquirePoFx(a1) )
          {
            PoFxIdleComponent(**(_QWORD **)(a1 + 1872), 0, 0);
            ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
          }
          if ( *(_QWORD *)(v9 + 5024) )
            RaidAdapterPoFxIdleComponent(v9, 0, 0, v10);
        }
      }
    }
    v11 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 1864);
    *(_BYTE *)(a1 + 505) &= ~0x80u;
    ExWaitForRundownProtectionReleaseCacheAware(v11);
    v12 = *(_QWORD **)(a1 + 1872);
    *(_QWORD *)(a1 + 1872) = 0;
    v13 = (void *)v12[22];
    if ( v13 )
    {
      ExFreePoolWithTag(v13, 0x4F506152u);
      v12[22] = 0;
      *((_DWORD *)v12 + 42) = 0;
    }
    PoFxUnregisterDevice(*v12);
    ExFreePoolWithTag(v12, 0x4F506152u);
  }
}

```

## disassembly

```asm
0x1400a38b8  mov     [rsp-8+arg_8], rbx
0x1400a38bd  mov     [rsp-8+arg_10], rdi
0x1400a38c2  push    rbp
0x1400a38c3  mov     rbp, rsp
0x1400a38c6  sub     rsp, 70h
0x1400a38ca  mov     rax, cs:__security_cookie
0x1400a38d1  xor     rax, rsp
0x1400a38d4  mov     [rbp+var_10], rax
0x1400a38d8  xor     eax, eax
0x1400a38da  xorps   xmm0, xmm0
0x1400a38dd  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400a38e1  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400a38e5  mov     rbx, rcx
0x1400a38e8  call    RaidUnitIsRegisteredForIdleDetection
0x1400a38ed  test    al, al
0x1400a38ef  jz      loc_1400A3BA2
0x1400a38f5  cmp     qword ptr [rcx+18h], 0
0x1400a38fa  mov     edi, 1
0x1400a38ff  jz      loc_1400A3986
0x1400a3905  mov     rax, [rcx+750h]
0x1400a390c  mov     ecx, [rax+20h]
0x1400a390f  test    cl, 4
0x1400a3912  jz      short loc_1400A3986
0x1400a3914  lea     edx, [rdi+3]
0x1400a3917  mov     rcx, rbx
0x1400a391a  call    RaidIsUnitControlSupported
0x1400a391f  test    al, al
0x1400a3921  jz      short loc_1400A3986
0x1400a3923  mov     rcx, [rbx+18h]
0x1400a3927  lea     r8, [rbp+var_50]
0x1400a392b  xor     eax, eax
0x1400a392d  lea     edx, [rdi+3]
0x1400a3930  mov     [rbp+var_40], rax
0x1400a3934  xorps   xmm0, xmm0
0x1400a3937  movups  [rbp+var_20], xmm0
0x1400a393b  mov     word ptr [rbp+var_20], di
0x1400a393f  movups  [rbp+var_50], xmm0
0x1400a3943  mov     dword ptr [rbp+var_20+4], 4
0x1400a394a  movzx   eax, word ptr [rcx+38h]
0x1400a394e  add     rcx, 168h
0x1400a3955  mov     word ptr [rbp+var_20+2], ax
0x1400a3959  mov     al, [rbx+68h]
0x1400a395c  mov     byte ptr [rbp+var_20+8], al
0x1400a395f  mov     al, [rbx+69h]
0x1400a3962  mov     byte ptr [rbp+var_20+9], al
0x1400a3965  mov     al, [rbx+6Ah]
0x1400a3968  mov     byte ptr [rbp+var_20+0Ah], al
0x1400a396b  lea     rax, [rbp+var_20]
0x1400a396f  mov     qword ptr [rbp+var_50+8], rax
0x1400a3973  mov     dword ptr [rbp+var_50], edi
0x1400a3976  mov     dword ptr [rbp+var_50+4], 18h
0x1400a397d  mov     byte ptr [rbp+var_40], 0
0x1400a3981  call    RaCallMiniportUnitControl
0x1400a3986  lea     rcx, [rbx+30h]; SpinLock
0x1400a398a  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400a398e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400a3995  nop     dword ptr [rax+rax+00h]
0x1400a399a  mov     rcx, rbx
0x1400a399d  call    RaidUnitCancelWaitWakeIrp
0x1400a39a2  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400a39a6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400a39ad  nop     dword ptr [rax+rax+00h]
0x1400a39b2  xor     edx, edx
0x1400a39b4  mov     rcx, rbx
0x1400a39b7  call    RaidUnitReenablePendingTimer
0x1400a39bc  mov     rcx, [rbx+750h]
0x1400a39c3  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400a39c7  add     rcx, 60h ; '`'; SpinLock
0x1400a39cb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400a39d2  nop     dword ptr [rax+rax+00h]
0x1400a39d7  mov     rcx, rbx
0x1400a39da  call    StorPortUnitFlushActivePendingRequestQueue
0x1400a39df  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400a39e3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400a39ea  nop     dword ptr [rax+rax+00h]
0x1400a39ef  mov     rax, [rbx+750h]
0x1400a39f6  mov     rcx, [rax+68h]
0x1400a39fa  test    rcx, rcx
0x1400a39fd  jz      short loc_1400A3A1A
0x1400a39ff  call    cs:__imp_PoUnregisterCoalescingCallback
0x1400a3a06  nop     dword ptr [rax+rax+00h]
0x1400a3a0b  mov     rax, [rbx+750h]
0x1400a3a12  mov     qword ptr [rax+68h], 0
0x1400a3a1a  mov     rax, [rbx+750h]
0x1400a3a21  mov     rcx, [rax+70h]; Handle
0x1400a3a25  test    rcx, rcx
0x1400a3a28  jz      short loc_1400A3A45
0x1400a3a2a  call    cs:__imp_PoUnregisterPowerSettingCallback
0x1400a3a31  nop     dword ptr [rax+rax+00h]
0x1400a3a36  mov     rax, [rbx+750h]
0x1400a3a3d  mov     qword ptr [rax+70h], 0
0x1400a3a45  mov     rax, [rbx+750h]
0x1400a3a4c  mov     rcx, [rax+78h]
0x1400a3a50  test    rcx, rcx
0x1400a3a53  jz      short loc_1400A3A79
0x1400a3a55  xor     r9d, r9d
0x1400a3a58  xor     r8d, r8d
0x1400a3a5b  mov     dl, dil
0x1400a3a5e  call    cs:__imp_ExDeleteTimer
0x1400a3a65  nop     dword ptr [rax+rax+00h]
0x1400a3a6a  mov     rax, [rbx+750h]
0x1400a3a71  mov     qword ptr [rax+78h], 0
0x1400a3a79  mov     rax, [rbx+750h]
0x1400a3a80  mov     rcx, [rax+80h]
0x1400a3a87  test    rcx, rcx
0x1400a3a8a  jz      loc_1400A3B22
0x1400a3a90  xor     r9d, r9d
0x1400a3a93  xor     r8d, r8d
0x1400a3a96  mov     dl, dil
0x1400a3a99  call    cs:__imp_ExDeleteTimer
0x1400a3aa0  nop     dword ptr [rax+rax+00h]
0x1400a3aa5  mov     rcx, [rbx+750h]
0x1400a3aac  mov     qword ptr [rcx+80h], 0
0x1400a3ab7  test    al, al
0x1400a3ab9  jz      short loc_1400A3B22
0x1400a3abb  mov     rax, [rbx+750h]
0x1400a3ac2  mov     ecx, [rax+94h]
0x1400a3ac8  test    dil, cl
0x1400a3acb  jz      short loc_1400A3B22
0x1400a3acd  mov     rdi, [rbx+18h]
0x1400a3ad1  mov     rcx, rbx
0x1400a3ad4  call    RaidUnitCheckAndAcquirePoFx
0x1400a3ad9  test    al, al
0x1400a3adb  jz      short loc_1400A3B0B
0x1400a3add  mov     rcx, [rbx+750h]
0x1400a3ae4  xor     r8d, r8d
0x1400a3ae7  xor     edx, edx
0x1400a3ae9  mov     rcx, [rcx]
0x1400a3aec  call    cs:__imp_PoFxIdleComponent
0x1400a3af3  nop     dword ptr [rax+rax+00h]
0x1400a3af8  mov     rcx, [rbx+748h]; RunRefCacheAware
0x1400a3aff  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400a3b06  nop     dword ptr [rax+rax+00h]
0x1400a3b0b  cmp     qword ptr [rdi+13A0h], 0
0x1400a3b13  jz      short loc_1400A3B22
0x1400a3b15  xor     r8d, r8d
0x1400a3b18  xor     edx, edx
0x1400a3b1a  mov     rcx, rdi
0x1400a3b1d  call    RaidAdapterPoFxIdleComponent
0x1400a3b22  mov     rcx, [rbx+748h]; RunRef
0x1400a3b29  and     byte ptr [rbx+1F9h], 7Fh
0x1400a3b30  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400a3b37  nop     dword ptr [rax+rax+00h]
0x1400a3b3c  mov     rdi, [rbx+750h]
0x1400a3b43  mov     qword ptr [rbx+750h], 0
0x1400a3b4e  mov     ebx, 4F506152h
0x1400a3b53  mov     rcx, [rdi+0B0h]; P
0x1400a3b5a  test    rcx, rcx
0x1400a3b5d  jz      short loc_1400A3B82
0x1400a3b5f  mov     edx, ebx; Tag
0x1400a3b61  call    cs:__imp_ExFreePoolWithTag
0x1400a3b68  nop     dword ptr [rax+rax+00h]
0x1400a3b6d  mov     qword ptr [rdi+0B0h], 0
0x1400a3b78  mov     dword ptr [rdi+0A8h], 0
0x1400a3b82  mov     rcx, [rdi]
0x1400a3b85  call    cs:__imp_PoFxUnregisterDevice
0x1400a3b8c  nop     dword ptr [rax+rax+00h]
0x1400a3b91  mov     edx, ebx; Tag
0x1400a3b93  mov     rcx, rdi; P
0x1400a3b96  call    cs:__imp_ExFreePoolWithTag
0x1400a3b9d  nop     dword ptr [rax+rax+00h]
0x1400a3ba2  mov     rcx, [rbp+var_10]
0x1400a3ba6  xor     rcx, rsp; StackCookie
0x1400a3ba9  call    __security_check_cookie
0x1400a3bae  lea     r11, [rsp+70h+var_s0]
0x1400a3bb3  mov     rbx, [r11+18h]
0x1400a3bb7  mov     rdi, [r11+20h]
0x1400a3bbb  mov     rsp, r11
0x1400a3bbe  pop     rbp
0x1400a3bbf  retn
```
