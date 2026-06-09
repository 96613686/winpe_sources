# WinNatDeleteAddressPoolEntry

- ea: `0x14000f5cc`
- end: `0x14000f6d7`
- name: `WinNatDeleteAddressPoolEntry`
- size: `267`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f428`
- `0x14000f6e0`
- `0x140010000`
- `0x140010e64`

## callees

- `0x14000baf8`
- `0x14000e680`
- `0x14000f5cc`
- `0x14000f8fc`
- `0x140018e40`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000f62a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000f62a`

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
    (__int64)qword_140026AE0,
    (__int64)(P + 40),
    v5,
    *((unsigned __int16 *)P + 28),
    *((_WORD *)P + 29));
  if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
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
0x14000f5cc  mov     [rsp+arg_0], rbx
0x14000f5d1  push    rdi
0x14000f5d2  sub     rsp, 70h
0x14000f5d6  mov     rbx, rcx
0x14000f5d9  lea     rdx, [rsp+78h+LockHandle]
0x14000f5de  mov     rcx, [rcx+40h]
0x14000f5e2  xorps   xmm0, xmm0
0x14000f5e5  xor     eax, eax
0x14000f5e7  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14000f5ec  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000f5f1  call    RtlAcquireScalableWriteLockAtDpcLevel
0x14000f5f6  test    byte ptr [rbx+48h], 4
0x14000f5fa  jnz     short loc_14000F625
0x14000f5fc  lea     rax, [rbx+18h]
0x14000f600  mov     rcx, [rax]
0x14000f603  cmp     [rcx+8], rax
0x14000f607  jnz     loc_14000F6D0
0x14000f60d  mov     rdx, [rax+8]
0x14000f611  cmp     [rdx], rax
0x14000f614  jnz     loc_14000F6D0
0x14000f61a  mov     [rdx], rcx
0x14000f61d  mov     [rcx+8], rdx
0x14000f621  or      byte ptr [rbx+48h], 4
0x14000f625  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000f62a  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000f631  nop     dword ptr [rax+rax+00h]
0x14000f636  movzx   eax, word ptr [rbx+3Ah]
0x14000f63a  lea     rdx, [rbx+28h]
0x14000f63e  movzx   r9d, word ptr [rbx+38h]
0x14000f643  mov     r8b, 4
0x14000f646  mov     rcx, cs:qword_140026AE0
0x14000f64d  mov     word ptr [rsp+78h+var_58], ax
0x14000f652  call    WinNatLibDeleteAddress
0x14000f657  cmp     cs:dword_140026104, 1
0x14000f65e  jnz     short loc_14000F6B9
0x14000f660  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14000f667  jz      short loc_14000F6B9
0x14000f669  mov     rax, [rbx+30h]
0x14000f66d  lea     rdx, WINNAT_ADDRESS_POOL_CONFIG
0x14000f674  mov     r9, [rbx+40h]
0x14000f678  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f67f  mov     [rsp+78h+var_30], 0
0x14000f687  add     r9, 158h
0x14000f68e  mov     [rsp+78h+var_38], 3
0x14000f696  mov     [rsp+78h+var_40], rax
0x14000f69b  movzx   eax, word ptr [rbx+3Ah]
0x14000f69f  mov     [rsp+78h+var_48], ax
0x14000f6a4  movzx   eax, word ptr [rbx+38h]
0x14000f6a8  mov     [rsp+78h+var_50], ax
0x14000f6ad  mov     eax, [rbx+28h]
0x14000f6b0  mov     [rsp+78h+var_58], eax
0x14000f6b4  call    McTemplateK0zqhhxqq_EtwWriteTransfer
0x14000f6b9  mov     rcx, rbx; P
0x14000f6bc  call    WinNatDereferenceAddressPoolEntry
0x14000f6c1  mov     rbx, [rsp+78h+arg_0]
0x14000f6c9  add     rsp, 70h
0x14000f6cd  pop     rdi
0x14000f6ce  retn
0x14000f6d0  mov     ecx, 3
0x14000f6d5  int     29h; Win8: RtlFailFast(ecx)
```
