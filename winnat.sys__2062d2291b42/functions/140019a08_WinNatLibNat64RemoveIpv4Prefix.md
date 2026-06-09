# WinNatLibNat64RemoveIpv4Prefix

- ea: `0x140019a08`
- end: `0x140019ad5`
- name: `WinNatLibNat64RemoveIpv4Prefix`
- size: `205`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f888`
- `0x140011420`

## callees

- `0x14000a638`
- `0x14000ee3c`
- `0x140019a08`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019abb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019abb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019aaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019aaa`
- `NETIO!PtDeleteEntry` at `0x140019a97`
- `NETIO!PtDeleteEntry` at `0x140019a97`
- `NETIO!PtGetExactMatch` at `0x140019a6f`
- `NETIO!PtGetExactMatch` at `0x140019a6f`

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
0x140019a08  mov     r11, rsp
0x140019a0b  mov     [r11+10h], rbx
0x140019a0f  push    rdi
0x140019a10  sub     rsp, 50h
0x140019a14  xor     eax, eax
0x140019a16  movzx   ebx, r8b
0x140019a1a  mov     rdi, rcx
0x140019a1d  mov     [rsp+58h+arg_10], 0
0x140019a25  xorps   xmm0, xmm0
0x140019a28  mov     [r11+8], rax
0x140019a2c  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140019a31  lea     r9d, [rax+4]
0x140019a35  mov     [r11-18h], rax
0x140019a39  mov     r8d, ebx
0x140019a3c  lea     rcx, [r11+18h]
0x140019a40  call    WinNatCopyPrefix
0x140019a45  mov     rcx, rdi
0x140019a48  lea     rdx, [rsp+58h+LockHandle]
0x140019a4d  call    RtlAcquireScalableWriteLock
0x140019a52  mov     rcx, [rdi+1A0h]
0x140019a59  lea     rax, [rsp+58h+arg_0]
0x140019a5e  movzx   r8d, bx
0x140019a62  mov     [rsp+58h+var_38], rax
0x140019a67  xor     r9d, r9d
0x140019a6a  lea     rdx, [rsp+58h+arg_10]
0x140019a6f  call    cs:__imp_PtGetExactMatch
0x140019a76  nop     dword ptr [rax+rax+00h]
0x140019a7b  mov     rdx, [rsp+58h+arg_0]
0x140019a80  test    rdx, rdx
0x140019a83  jnz     short loc_140019A8C
0x140019a85  mov     edi, 0C0000225h
0x140019a8a  jmp     short loc_140019AB6
0x140019a8c  mov     rcx, [rdi+1A0h]
0x140019a93  lea     rbx, [rdx-18h]
0x140019a97  call    cs:__imp_PtDeleteEntry
0x140019a9e  nop     dword ptr [rax+rax+00h]
0x140019aa3  xor     edx, edx; Tag
0x140019aa5  mov     rcx, rbx; P
0x140019aa8  mov     edi, eax
0x140019aaa  call    cs:__imp_ExFreePoolWithTag
0x140019ab1  nop     dword ptr [rax+rax+00h]
0x140019ab6  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140019abb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019ac2  nop     dword ptr [rax+rax+00h]
0x140019ac7  mov     rbx, [rsp+58h+arg_8]
0x140019acc  mov     eax, edi
0x140019ace  add     rsp, 50h
0x140019ad2  pop     rdi
0x140019ad3  retn
```
