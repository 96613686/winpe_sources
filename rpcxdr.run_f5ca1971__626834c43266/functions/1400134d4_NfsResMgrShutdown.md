# NfsResMgrShutdown

- ea: `0x1400134d4`
- end: `0x140013612`
- name: `NfsResMgrShutdown`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140020640`

## callees

- `0x14001240c`
- `0x1400134d4`
- `0x140013738`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001352e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001354c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001352e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001354c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001356b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400135d0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001356b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400135d0`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140013585`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140013585`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400135b0`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400135b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400135e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400135e8`

## pseudocode

```c
__int64 __fastcall NfsResMgrShutdown(void **a1, __int64 a2, __int64 a3, __int64 a4)
{
  PVOID v4; // rax
  __int64 v6; // rbx
  PVOID v7; // rax
  void *v8; // rsi
  _BYTE v10[32]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE LockHandle[32]; // [rsp+40h] [rbp-28h] BYREF
  PVOID RestartKey; // [rsp+90h] [rbp+28h] BYREF

  v4 = *a1;
  RestartKey = 0;
  memset(LockHandle, 0, sizeof(LockHandle));
  memset(v10, 0, sizeof(v10));
  if ( v4 && NfsResMgrpRoot == v4 )
  {
    NfsReferenceHistoryDestroy(
      a1,
      a2,
      a3,
      a4,
      *(_QWORD *)v10,
      *(_QWORD *)&v10[8],
      *(_QWORD *)&v10[16],
      *(_QWORD *)&v10[24]);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)NfsResMgrpRoot + 3, (PKLOCK_QUEUE_HANDLE)LockHandle);
    LockHandle[24] = 1;
    while ( 1 )
    {
      RestartKey = 0;
      v7 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)((char *)NfsResMgrpRoot + 48), &RestartKey);
      v8 = v7;
      if ( !v7 )
        break;
      v6 = *((_QWORD *)v7 + 4);
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 24), (PKLOCK_QUEUE_HANDLE)v10);
      v10[24] = 1;
      *(_DWORD *)(v6 + 412) |= 1u;
      v10[24] = 0;
      KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)v10);
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)((char *)NfsResMgrpRoot + 48), v8);
      NfsResMgrpResourceRecordCleanAndDelete((struct _LOOKASIDE_LIST_EX *)v6);
    }
    LockHandle[24] = 0;
    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
    ExFreePoolWithTag(NfsResMgrpRoot, 0x4F4F5252u);
    NfsResMgrpRoot = 0;
  }
  *a1 = 0;
  return 0;
}

```

## disassembly

```asm
0x1400134d4  push    rbp
0x1400134d6  push    rbx
0x1400134d7  push    rsi
0x1400134d8  push    rdi
0x1400134d9  mov     rbp, rsp
0x1400134dc  sub     rsp, 68h
0x1400134e0  mov     rax, [rcx]
0x1400134e3  xorps   xmm0, xmm0
0x1400134e6  mov     [rbp+RestartKey], 0
0x1400134ee  xorps   xmm1, xmm1
0x1400134f1  mov     rdi, rcx
0x1400134f4  movups  xmmword ptr [rbp+LockHandle], xmm0
0x1400134f8  movups  xmmword ptr [rbp+LockHandle+10h], xmm0
0x1400134fc  movups  xmmword ptr [rbp+var_48], xmm1
0x140013500  movups  xmmword ptr [rbp+var_48+10h], xmm1
0x140013504  test    rax, rax
0x140013507  jz      loc_1400135FF
0x14001350d  cmp     cs:NfsResMgrpRoot, rax
0x140013514  jnz     loc_1400135FF
0x14001351a  call    NfsReferenceHistoryDestroy
0x14001351f  mov     rcx, cs:NfsResMgrpRoot
0x140013526  lea     rdx, [rbp+LockHandle]; LockHandle
0x14001352a  add     rcx, 18h; SpinLock
0x14001352e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140013535  nop     dword ptr [rax+rax+00h]
0x14001353a  mov     [rbp+LockHandle+18h], 1
0x14001353e  jmp     short loc_140013599
0x140013540  mov     rbx, [rsi+20h]
0x140013544  lea     rdx, [rbp+var_48]; LockHandle
0x140013548  lea     rcx, [rbx+18h]; SpinLock
0x14001354c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140013553  nop     dword ptr [rax+rax+00h]
0x140013558  mov     [rbp+var_48+18h], 1
0x14001355c  lea     rcx, [rbp+var_48]; LockHandle
0x140013560  or      dword ptr [rbx+19Ch], 1
0x140013567  mov     [rbp+var_48+18h], 0
0x14001356b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140013572  nop     dword ptr [rax+rax+00h]
0x140013577  mov     rcx, cs:NfsResMgrpRoot
0x14001357e  mov     rdx, rsi; Buffer
0x140013581  add     rcx, 30h ; '0'; Table
0x140013585  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14001358c  nop     dword ptr [rax+rax+00h]
0x140013591  mov     rcx, rbx; P
0x140013594  call    NfsResMgrpResourceRecordCleanAndDelete
0x140013599  mov     rcx, cs:NfsResMgrpRoot
0x1400135a0  lea     rdx, [rbp+RestartKey]; RestartKey
0x1400135a4  add     rcx, 30h ; '0'; Table
0x1400135a8  mov     [rbp+RestartKey], 0
0x1400135b0  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400135b7  nop     dword ptr [rax+rax+00h]
0x1400135bc  mov     rsi, rax
0x1400135bf  test    rax, rax
0x1400135c2  jnz     loc_140013540
0x1400135c8  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400135cc  mov     [rbp+LockHandle+18h], 0
0x1400135d0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400135d7  nop     dword ptr [rax+rax+00h]
0x1400135dc  mov     rcx, cs:NfsResMgrpRoot; P
0x1400135e3  mov     edx, 4F4F5252h; Tag
0x1400135e8  call    cs:__imp_ExFreePoolWithTag
0x1400135ef  nop     dword ptr [rax+rax+00h]
0x1400135f4  mov     cs:NfsResMgrpRoot, 0
0x1400135ff  mov     qword ptr [rdi], 0
0x140013606  xor     eax, eax
0x140013608  add     rsp, 68h
0x14001360c  pop     rdi
0x14001360d  pop     rsi
0x14001360e  pop     rbx
0x14001360f  pop     rbp
0x140013610  retn
```
