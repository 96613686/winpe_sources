# PtSendCurrentKeyboardIndicators

- ea: `0x1400023c4`
- end: `0x1400024e1`
- name: `PtSendCurrentKeyboardIndicators`
- size: `285`
- prototype: `__int64 __fastcall(__int64, _WORD *, IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b2d0`

## callees

- `0x1400023c4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002479`
- `ntoskrnl!IofCompleteRequest` at `0x140002479`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400023e2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400023e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002459`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400024c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002459`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400024c8`

## pseudocode

```c
__int64 __fastcall PtSendCurrentKeyboardIndicators(__int64 a1, _WORD *a2, IRP *a3)
{
  __int64 v3; // rbx
  KSPIN_LOCK *v6; // rsi
  KIRQL v7; // r8
  unsigned int v9; // ebx

  v3 = *(_QWORD *)(a1 + 64);
  v6 = (KSPIN_LOCK *)(v3 + 232);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 232));
  if ( *(_BYTE *)(v3 + 222) )
  {
    *a2 = *(_WORD *)(v3 + 218);
    a2[2] = *(_WORD *)(v3 + 220);
    *(_BYTE *)(v3 + 222) = 0;
    v9 = 0;
    a3->IoStatus.Information = 12;
  }
  else if ( *(_QWORD *)(v3 + 224) )
  {
    v9 = -1073741791;
  }
  else
  {
    *(_QWORD *)(v3 + 224) = a3;
    a3->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    _InterlockedExchange64((volatile __int64 *)(*(_QWORD *)(v3 + 224) + 104LL), (__int64)&CancelIndicatorIrp);
    if ( a3->Cancel && _InterlockedExchange64((volatile __int64 *)(*(_QWORD *)(v3 + 224) + 104LL), 0) )
    {
      *(_QWORD *)(v3 + 224) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 232), v7);
      a3->IoStatus.Information = 0;
      a3->IoStatus.Status = -1073741536;
      IofCompleteRequest(a3, 0);
      return 259;
    }
    v9 = 259;
  }
  KeReleaseSpinLock(v6, v7);
  return v9;
}

```

## disassembly

```asm
0x1400023c4  push    rbx
0x1400023c6  push    rsi
0x1400023c7  push    rdi
0x1400023c8  push    r14
0x1400023ca  sub     rsp, 28h
0x1400023ce  mov     rbx, [rcx+40h]
0x1400023d2  mov     rdi, r8
0x1400023d5  mov     r14, rdx
0x1400023d8  lea     rsi, [rbx+0E8h]
0x1400023df  mov     rcx, rsi; SpinLock
0x1400023e2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400023e9  nop     dword ptr [rax+rax+00h]
0x1400023ee  cmp     byte ptr [rbx+0DEh], 0
0x1400023f5  mov     r8b, al
0x1400023f8  jnz     loc_14000249A
0x1400023fe  cmp     qword ptr [rbx+0E0h], 0
0x140002406  jnz     loc_140002493
0x14000240c  mov     [rbx+0E0h], rdi
0x140002413  lea     rax, CancelIndicatorIrp
0x14000241a  mov     rcx, [rdi+0B8h]
0x140002421  or      byte ptr [rcx+3], 1
0x140002425  mov     rcx, [rbx+0E0h]
0x14000242c  xchg    rax, [rcx+68h]
0x140002430  cmp     byte ptr [rdi+44h], 0
0x140002434  jz      short loc_14000248C
0x140002436  mov     rax, [rbx+0E0h]
0x14000243d  xor     edx, edx
0x14000243f  xchg    rdx, [rax+68h]
0x140002443  test    rdx, rdx
0x140002446  jz      short loc_14000248C
0x140002448  mov     dl, r8b; NewIrql
0x14000244b  mov     qword ptr [rbx+0E0h], 0
0x140002456  mov     rcx, rsi; SpinLock
0x140002459  call    cs:__imp_KeReleaseSpinLock
0x140002460  nop     dword ptr [rax+rax+00h]
0x140002465  xor     edx, edx; PriorityBoost
0x140002467  mov     qword ptr [rdi+38h], 0
0x14000246f  mov     rcx, rdi; Irp
0x140002472  mov     dword ptr [rdi+30h], 0C0000120h
0x140002479  call    cs:__imp_IofCompleteRequest
0x140002480  nop     dword ptr [rax+rax+00h]
0x140002485  mov     eax, 103h
0x14000248a  jmp     short loc_1400024D6
0x14000248c  mov     ebx, 103h
0x140002491  jmp     short loc_1400024C2
0x140002493  mov     ebx, 0C0000021h
0x140002498  jmp     short loc_1400024C2
0x14000249a  movzx   eax, word ptr [rbx+0DAh]
0x1400024a1  mov     [r14], ax
0x1400024a5  movzx   eax, word ptr [rbx+0DCh]
0x1400024ac  mov     [r14+4], ax
0x1400024b1  mov     byte ptr [rbx+0DEh], 0
0x1400024b8  xor     ebx, ebx
0x1400024ba  mov     qword ptr [rdi+38h], 0Ch
0x1400024c2  mov     dl, r8b; NewIrql
0x1400024c5  mov     rcx, rsi; SpinLock
0x1400024c8  call    cs:__imp_KeReleaseSpinLock
0x1400024cf  nop     dword ptr [rax+rax+00h]
0x1400024d4  mov     eax, ebx
0x1400024d6  add     rsp, 28h
0x1400024da  pop     r14
0x1400024dc  pop     rdi
0x1400024dd  pop     rsi
0x1400024de  pop     rbx
0x1400024df  retn
```
