# WinNatLibNat64RemoveIpv4Prefix

- ea: `0x140019528`
- end: `0x1400195f5`
- name: `WinNatLibNat64RemoveIpv4Prefix`
- size: `205`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f830`
- `0x1400113c0`

## callees

- `0x14000a638`
- `0x14000ede4`
- `0x140019528`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400195db`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400195db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195ca`
- `NETIO!PtDeleteEntry` at `0x1400195b7`
- `NETIO!PtDeleteEntry` at `0x1400195b7`
- `NETIO!PtGetExactMatch` at `0x14001958f`
- `NETIO!PtGetExactMatch` at `0x14001958f`

## pseudocode

```c
__int64 __fastcall WinNatLibNat64RemoveIpv4Prefix(__int64 a1, __int64 a2, unsigned __int8 a3)
{
  unsigned __int16 v3; // bx
  unsigned int v5; // edi
  void *v6; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF

  v3 = a3;
  v10 = 0;
  v9 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  WinNatCopyPrefix((__int64)&v10, a2, a3, 4u);
  RtlAcquireScalableWriteLock(a1, &LockHandle);
  PtGetExactMatch(*(_QWORD *)(a1 + 416), &v10, v3, 0, &v9);
  if ( v9 )
  {
    v6 = (void *)(v9 - 24);
    v5 = PtDeleteEntry(*(_QWORD *)(a1 + 416), v9);
    ExFreePoolWithTag(v6, 0);
  }
  else
  {
    v5 = -1073741275;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return v5;
}

```

## disassembly

```asm
0x140019528  mov     r11, rsp
0x14001952b  mov     [r11+10h], rbx
0x14001952f  push    rdi
0x140019530  sub     rsp, 50h
0x140019534  xor     eax, eax
0x140019536  movzx   ebx, r8b
0x14001953a  mov     rdi, rcx
0x14001953d  mov     [rsp+58h+arg_10], 0
0x140019545  xorps   xmm0, xmm0
0x140019548  mov     [r11+8], rax
0x14001954c  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140019551  lea     r9d, [rax+4]
0x140019555  mov     [r11-18h], rax
0x140019559  mov     r8d, ebx
0x14001955c  lea     rcx, [r11+18h]
0x140019560  call    WinNatCopyPrefix
0x140019565  mov     rcx, rdi
0x140019568  lea     rdx, [rsp+58h+LockHandle]
0x14001956d  call    RtlAcquireScalableWriteLock
0x140019572  mov     rcx, [rdi+1A0h]
0x140019579  lea     rax, [rsp+58h+arg_0]
0x14001957e  movzx   r8d, bx
0x140019582  mov     [rsp+58h+var_38], rax
0x140019587  xor     r9d, r9d
0x14001958a  lea     rdx, [rsp+58h+arg_10]
0x14001958f  call    cs:__imp_PtGetExactMatch
0x140019596  nop     dword ptr [rax+rax+00h]
0x14001959b  mov     rdx, [rsp+58h+arg_0]
0x1400195a0  test    rdx, rdx
0x1400195a3  jnz     short loc_1400195AC
0x1400195a5  mov     edi, 0C0000225h
0x1400195aa  jmp     short loc_1400195D6
0x1400195ac  mov     rcx, [rdi+1A0h]
0x1400195b3  lea     rbx, [rdx-18h]
0x1400195b7  call    cs:__imp_PtDeleteEntry
0x1400195be  nop     dword ptr [rax+rax+00h]
0x1400195c3  xor     edx, edx; Tag
0x1400195c5  mov     rcx, rbx; P
0x1400195c8  mov     edi, eax
0x1400195ca  call    cs:__imp_ExFreePoolWithTag
0x1400195d1  nop     dword ptr [rax+rax+00h]
0x1400195d6  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x1400195db  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400195e2  nop     dword ptr [rax+rax+00h]
0x1400195e7  mov     rbx, [rsp+58h+arg_8]
0x1400195ec  mov     eax, edi
0x1400195ee  add     rsp, 50h
0x1400195f2  pop     rdi
0x1400195f3  retn
```
