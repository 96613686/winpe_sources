# CTEInsertBlockTracker

- ea: `0x140004600`
- end: `0x140004674`
- name: `CTEInsertBlockTracker`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004460`

## callees

- `0x140004600`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140004661`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004661`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004621`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004621`

## pseudocode

```c
void __fastcall CTEInsertBlockTracker(_QWORD *a1, __int64 a2)
{
  KIRQL v3; // al
  _QWORD *v4; // rcx

  a1[2] = KeGetCurrentThread();
  a1[3] = a2;
  v3 = KeAcquireSpinLockRaiseToDpc(&CTEBlockSpinLock);
  v4 = (_QWORD *)qword_1400083A8;
  if ( *(__int64 **)qword_1400083A8 != &CTEBlockListHead )
    __fastfail(3u);
  *a1 = &CTEBlockListHead;
  a1[1] = v4;
  *v4 = a1;
  qword_1400083A8 = (__int64)a1;
  KeReleaseSpinLock(&CTEBlockSpinLock, v3);
}

```

## disassembly

```asm
0x140004600  push    rbx
0x140004602  sub     rsp, 20h
0x140004606  mov     rax, gs:188h
0x14000460f  mov     rbx, rcx
0x140004612  mov     [rcx+10h], rax
0x140004616  mov     [rcx+18h], rdx
0x14000461a  lea     rcx, CTEBlockSpinLock; SpinLock
0x140004621  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004628  nop     dword ptr [rax+rax+00h]
0x14000462d  mov     rcx, cs:qword_1400083A8
0x140004634  lea     rdx, CTEBlockListHead
0x14000463b  cmp     [rcx], rdx
0x14000463e  jz      short loc_140004647
0x140004640  mov     ecx, 3
0x140004645  int     29h; Win8: RtlFailFast(ecx)
0x140004647  mov     [rbx], rdx
0x14000464a  mov     dl, al; NewIrql
0x14000464c  mov     [rbx+8], rcx
0x140004650  mov     [rcx], rbx
0x140004653  lea     rcx, CTEBlockSpinLock; SpinLock
0x14000465a  mov     cs:qword_1400083A8, rbx
0x140004661  call    cs:__imp_KeReleaseSpinLock
0x140004668  nop     dword ptr [rax+rax+00h]
0x14000466d  add     rsp, 20h
0x140004671  pop     rbx
0x140004672  retn
```
