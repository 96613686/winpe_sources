# WinNatDeleteAddressPoolEntry

- ea: `0x14000f624`
- end: `0x14000f72f`
- name: `WinNatDeleteAddressPoolEntry`
- size: `267`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f480`
- `0x14000f738`
- `0x140010060`
- `0x140010ec4`

## callees

- `0x14000baf8`
- `0x14000e6a8`
- `0x14000f624`
- `0x14000f954`
- `0x140019320`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000f682`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000f682`

## pseudocode

```c
__int64 __fastcall WinNatDeleteAddressPoolEntry(char *P)
{
  __int64 v2; // rcx
  char **v3; // rcx
  PVOID *v4; // rdx
  __int64 v5; // r8
  int v6; // r8d
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-28h] BYREF

  v2 = *((_QWORD *)P + 8);
  memset(&LockHandle, 0, sizeof(LockHandle));
  RtlAcquireScalableWriteLockAtDpcLevel(v2, &LockHandle);
  if ( (P[72] & 4) == 0 )
  {
    v3 = (char **)*((_QWORD *)P + 3);
    if ( v3[1] != P + 24 || (v4 = (PVOID *)*((_QWORD *)P + 4), *v4 != P + 24) )
      __fastfail(3u);
    *v4 = v3;
    v3[1] = (char *)v4;
    P[72] |= 4u;
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  LOBYTE(v5) = 4;
  WinNatLibDeleteAddress(
    (__int64)qword_140027AE0,
    (__int64)(P + 40),
    v5,
    *((unsigned __int16 *)P + 28),
    *((_WORD *)P + 29));
  if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    McTemplateK0zqhhxqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      (unsigned int)WINNAT_ADDRESS_POOL_CONFIG,
      v6,
      *((_QWORD *)P + 8) + 344,
      *((_DWORD *)P + 10),
      *((_WORD *)P + 28),
      *((_WORD *)P + 29),
      *((_QWORD *)P + 6),
      3,
      0);
  return WinNatDereferenceAddressPoolEntry(P);
}

```

## disassembly

```asm
0x14000f624  mov     [rsp+arg_0], rbx
0x14000f629  push    rdi
0x14000f62a  sub     rsp, 70h
0x14000f62e  mov     rbx, rcx
0x14000f631  lea     rdx, [rsp+78h+LockHandle]
0x14000f636  mov     rcx, [rcx+40h]
0x14000f63a  xorps   xmm0, xmm0
0x14000f63d  xor     eax, eax
0x14000f63f  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14000f644  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000f649  call    RtlAcquireScalableWriteLockAtDpcLevel
0x14000f64e  test    byte ptr [rbx+48h], 4
0x14000f652  jnz     short loc_14000F67D
0x14000f654  lea     rax, [rbx+18h]
0x14000f658  mov     rcx, [rax]
0x14000f65b  cmp     [rcx+8], rax
0x14000f65f  jnz     loc_14000F728
0x14000f665  mov     rdx, [rax+8]
0x14000f669  cmp     [rdx], rax
0x14000f66c  jnz     loc_14000F728
0x14000f672  mov     [rdx], rcx
0x14000f675  mov     [rcx+8], rdx
0x14000f679  or      byte ptr [rbx+48h], 4
0x14000f67d  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000f682  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000f689  nop     dword ptr [rax+rax+00h]
0x14000f68e  movzx   eax, word ptr [rbx+3Ah]
0x14000f692  lea     rdx, [rbx+28h]
0x14000f696  movzx   r9d, word ptr [rbx+38h]
0x14000f69b  mov     r8b, 4
0x14000f69e  mov     rcx, cs:qword_140027AE0
0x14000f6a5  mov     word ptr [rsp+78h+var_58], ax
0x14000f6aa  call    WinNatLibDeleteAddress
0x14000f6af  cmp     cs:dword_140027104, 1
0x14000f6b6  jnz     short loc_14000F711
0x14000f6b8  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14000f6bf  jz      short loc_14000F711
0x14000f6c1  mov     rax, [rbx+30h]
0x14000f6c5  lea     rdx, WINNAT_ADDRESS_POOL_CONFIG
0x14000f6cc  mov     r9, [rbx+40h]
0x14000f6d0  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f6d7  mov     [rsp+78h+var_30], 0
0x14000f6df  add     r9, 158h
0x14000f6e6  mov     [rsp+78h+var_38], 3
0x14000f6ee  mov     [rsp+78h+var_40], rax
0x14000f6f3  movzx   eax, word ptr [rbx+3Ah]
0x14000f6f7  mov     [rsp+78h+var_48], ax
0x14000f6fc  movzx   eax, word ptr [rbx+38h]
0x14000f700  mov     [rsp+78h+var_50], ax
0x14000f705  mov     eax, [rbx+28h]
0x14000f708  mov     [rsp+78h+var_58], eax
0x14000f70c  call    McTemplateK0zqhhxqq_EtwWriteTransfer
0x14000f711  mov     rcx, rbx; P
0x14000f714  call    WinNatDereferenceAddressPoolEntry
0x14000f719  mov     rbx, [rsp+78h+arg_0]
0x14000f721  add     rsp, 70h
0x14000f725  pop     rdi
0x14000f726  retn
0x14000f728  mov     ecx, 3
0x14000f72d  int     29h; Win8: RtlFailFast(ecx)
```
