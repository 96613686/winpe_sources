# WinNatLibDeleteAddress

- ea: `0x140018e40`
- end: `0x140018f40`
- name: `WinNatLibDeleteAddress`
- size: `256`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x140007bb0`
- `0x14000f5cc`
- `0x14001448c`
- `0x1400310f8`

## callees

- `0x14000a638`
- `0x14000a7dc`
- `0x14000b404`
- `0x14000c9d8`
- `0x140018e40`
- `0x14001b0ac`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018ece`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018ece`

## pseudocode

```c
__int64 __fastcall WinNatLibDeleteAddress(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int16 a5)
{
  __int64 result; // rax
  __int64 v7; // rbx
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  result = WinNatLibFindAddressEntry((PKSPIN_LOCK)(a1 + 1280), a5, 0, 0, 0, 0);
  v7 = result;
  if ( result )
  {
    RtlAcquireScalableWriteLock(*(_QWORD *)(result + 112), &LockHandle);
    v8 = *(_QWORD *)(v7 + 8);
    if ( *(_QWORD *)(v8 + 8) != v7 + 8 || (v9 = *(_QWORD **)(v7 + 16), *v9 != v7 + 8) )
      __fastfail(3u);
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    *(_BYTE *)(v7 + 212) |= 2u;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    WinNatDeleteSessionsOnAddress(a1 + 128, v7);
    WinNatDeleteBindingsForAddress(
      a1 + 768,
      *(_QWORD *)(v7 + 24),
      *(unsigned __int16 *)(v7 + 106),
      *(unsigned __int16 *)(v7 + 108));
    _InterlockedAdd(
      (volatile signed __int32 *)(*(_QWORD *)(v7 + 112) + 368LL),
      *(unsigned __int16 *)(v7 + 106) - *(unsigned __int16 *)(v7 + 108) - 1);
    WinNatLibDereferenceAddressEntry(v7);
    return WinNatLibDereferenceAddressEntry(v7);
  }
  return result;
}

```

## disassembly

```asm
0x140018e40  mov     r11, rsp
0x140018e43  mov     [r11+8], rbx
0x140018e47  push    rdi
0x140018e48  sub     rsp, 70h
0x140018e4c  xor     eax, eax
0x140018e4e  xorps   xmm0, xmm0
0x140018e51  mov     [r11-38h], rax
0x140018e55  mov     rdi, rcx
0x140018e58  mov     [r11-40h], rax
0x140018e5c  add     rcx, 500h; SpinLock
0x140018e63  mov     [rsp+78h+var_48], al; char
0x140018e67  mov     [rsp+78h+var_50], ax; __int16
0x140018e6c  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140018e71  mov     [r11-18h], rax
0x140018e75  movzx   eax, [rsp+78h+arg_20]
0x140018e7d  mov     [rsp+78h+var_58], ax; __int16
0x140018e82  call    WinNatLibFindAddressEntry
0x140018e87  mov     rbx, rax
0x140018e8a  test    rax, rax
0x140018e8d  jz      loc_140018F2A
0x140018e93  mov     rcx, [rax+70h]
0x140018e97  lea     rdx, [rsp+78h+LockHandle]
0x140018e9c  call    RtlAcquireScalableWriteLock
0x140018ea1  lea     rax, [rbx+8]
0x140018ea5  mov     rdx, [rax]
0x140018ea8  cmp     [rdx+8], rax
0x140018eac  jnz     loc_140018F39
0x140018eb2  mov     rcx, [rax+8]
0x140018eb6  cmp     [rcx], rax
0x140018eb9  jnz     short loc_140018F39
0x140018ebb  mov     [rcx], rdx
0x140018ebe  mov     [rdx+8], rcx
0x140018ec2  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140018ec7  or      byte ptr [rbx+0D4h], 2
0x140018ece  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140018ed5  nop     dword ptr [rax+rax+00h]
0x140018eda  lea     rcx, [rdi+80h]
0x140018ee1  mov     rdx, rbx
0x140018ee4  call    WinNatDeleteSessionsOnAddress
0x140018ee9  movzx   r9d, word ptr [rbx+6Ch]
0x140018eee  lea     rcx, [rdi+300h]
0x140018ef5  movzx   r8d, word ptr [rbx+6Ah]
0x140018efa  mov     rdx, [rbx+18h]
0x140018efe  call    WinNatDeleteBindingsForAddress
0x140018f03  movzx   eax, word ptr [rbx+6Ch]
0x140018f07  movzx   ecx, word ptr [rbx+6Ah]
0x140018f0b  sub     ecx, eax
0x140018f0d  mov     rax, [rbx+70h]
0x140018f11  dec     ecx
0x140018f13  lock add [rax+170h], ecx
0x140018f1a  mov     rcx, rbx
0x140018f1d  call    WinNatLibDereferenceAddressEntry
0x140018f22  mov     rcx, rbx
0x140018f25  call    WinNatLibDereferenceAddressEntry
0x140018f2a  mov     rbx, [rsp+78h+arg_0]
0x140018f32  add     rsp, 70h
0x140018f36  pop     rdi
0x140018f37  retn
0x140018f39  mov     ecx, 3
0x140018f3e  int     29h; Win8: RtlFailFast(ecx)
```
