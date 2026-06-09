# PipeCancelRoutine

- ea: `0x140015960`
- end: `0x140015a0b`
- name: `PipeCancelRoutine`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140015960`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400159e8`
- `ntoskrnl!IofCompleteRequest` at `0x1400159e8`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001596c`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14001596c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400159d7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400159d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001597f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001597f`

## pseudocode

```c
void __fastcall PipeCancelRoutine(__int64 a1, __int64 a2)
{
  KIRQL v3; // al
  __int64 v4; // rcx
  __int64 v5; // rdx
  _QWORD *v6; // r8

  IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
  v3 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a2 + 128));
  v4 = a2 + 136;
  v5 = *(_QWORD *)(a2 + 136);
  if ( v5 != a2 + 136 )
  {
    if ( *(_QWORD *)(v5 + 8) != v4 || (v6 = *(_QWORD **)(a2 + 144), *v6 != v4) )
      __fastfail(3u);
    *v6 = v5;
    *(_QWORD *)(v5 + 8) = v6;
    if ( **(_BYTE **)(a2 + 184) == 4 && *(_QWORD *)(a2 + 56) )
      *(_DWORD *)(a2 + 48) = -2147483643;
    else
      *(_DWORD *)(a2 + 48) = -1073741536;
  }
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a2 + 128), v3);
  IofCompleteRequest((PIRP)a2, 0);
}

```

## disassembly

```asm
0x140015960  push    rbx
0x140015962  sub     rsp, 20h
0x140015966  mov     cl, [rdx+45h]; Irql
0x140015969  mov     rbx, rdx
0x14001596c  call    cs:__imp_IoReleaseCancelSpinLock
0x140015973  nop     dword ptr [rax+rax+00h]
0x140015978  mov     rcx, [rbx+80h]; SpinLock
0x14001597f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015986  nop     dword ptr [rax+rax+00h]
0x14001598b  lea     rcx, [rbx+88h]
0x140015992  mov     r9b, al
0x140015995  mov     rdx, [rcx]
0x140015998  cmp     rdx, rcx
0x14001599b  jz      short loc_1400159CD
0x14001599d  cmp     [rdx+8], rcx
0x1400159a1  jnz     short loc_140015A04
0x1400159a3  mov     r8, [rcx+8]
0x1400159a7  cmp     [r8], rcx
0x1400159aa  jnz     short loc_140015A04
0x1400159ac  mov     [r8], rdx
0x1400159af  mov     [rdx+8], r8
0x1400159b3  mov     rax, [rbx+0B8h]
0x1400159ba  cmp     byte ptr [rax], 4
0x1400159bd  jnz     short loc_1400159FB
0x1400159bf  cmp     qword ptr [rbx+38h], 0
0x1400159c4  jz      short loc_1400159FB
0x1400159c6  mov     dword ptr [rbx+30h], 80000005h
0x1400159cd  mov     rcx, [rbx+80h]; SpinLock
0x1400159d4  mov     dl, r9b; NewIrql
0x1400159d7  call    cs:__imp_KeReleaseSpinLock
0x1400159de  nop     dword ptr [rax+rax+00h]
0x1400159e3  xor     edx, edx; PriorityBoost
0x1400159e5  mov     rcx, rbx; Irp
0x1400159e8  call    cs:__imp_IofCompleteRequest
0x1400159ef  nop     dword ptr [rax+rax+00h]
0x1400159f4  add     rsp, 20h
0x1400159f8  pop     rbx
0x1400159f9  retn
0x1400159fb  mov     dword ptr [rbx+30h], 0C0000120h
0x140015a02  jmp     short loc_1400159CD
0x140015a04  mov     ecx, 3
0x140015a09  int     29h; Win8: RtlFailFast(ecx)
```
