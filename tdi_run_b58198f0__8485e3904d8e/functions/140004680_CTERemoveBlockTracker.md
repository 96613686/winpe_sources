# CTERemoveBlockTracker

- ea: `0x140004680`
- end: `0x1400046d8`
- name: `CTERemoveBlockTracker`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004460`

## callees

- `0x140004680`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400046be`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400046be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004690`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004690`

## pseudocode

```c
void __fastcall CTERemoveBlockTracker(_QWORD *a1)
{
  KIRQL v2; // al
  __int64 v3; // r8
  _QWORD *v4; // rdx

  v2 = KeAcquireSpinLockRaiseToDpc(&CTEBlockSpinLock);
  v3 = *a1;
  if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v4 = (_QWORD *)a1[1], (_QWORD *)*v4 != a1) )
    __fastfail(3u);
  *v4 = v3;
  *(_QWORD *)(v3 + 8) = v4;
  KeReleaseSpinLock(&CTEBlockSpinLock, v2);
}

```

## disassembly

```asm
0x140004680  push    rbx
0x140004682  sub     rsp, 20h
0x140004686  mov     rbx, rcx
0x140004689  lea     rcx, CTEBlockSpinLock; SpinLock
0x140004690  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004697  nop     dword ptr [rax+rax+00h]
0x14000469c  mov     r8, [rbx]
0x14000469f  cmp     [r8+8], rbx
0x1400046a3  jnz     short loc_1400046D1
0x1400046a5  mov     rdx, [rbx+8]
0x1400046a9  cmp     [rdx], rbx
0x1400046ac  jnz     short loc_1400046D1
0x1400046ae  mov     [rdx], r8
0x1400046b1  lea     rcx, CTEBlockSpinLock; SpinLock
0x1400046b8  mov     [r8+8], rdx
0x1400046bc  mov     dl, al; NewIrql
0x1400046be  call    cs:__imp_KeReleaseSpinLock
0x1400046c5  nop     dword ptr [rax+rax+00h]
0x1400046ca  add     rsp, 20h
0x1400046ce  pop     rbx
0x1400046cf  retn
0x1400046d1  mov     ecx, 3
0x1400046d6  int     29h; Win8: RtlFailFast(ecx)
```
