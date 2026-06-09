# SqospCreateClient

- ea: `0x140011138`
- end: `0x1400111b5`
- name: `SqospCreateClient`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400111bc`
- `0x1400117e4`

## callees

- `0x140009240`
- `0x140011138`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140011173`
- `ntoskrnl!KeInitializeSpinLock` at `0x140011173`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140011145`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140011145`

## pseudocode

```c
KSPIN_LOCK *SqospCreateClient()
{
  KSPIN_LOCK *v0; // rax
  KSPIN_LOCK *v1; // rbx

  v0 = (KSPIN_LOCK *)ExAllocateFromLookasideListEx(&Lookaside);
  v1 = v0;
  if ( v0 )
  {
    memset(v0, 0, 0x140u);
    *((_DWORD *)v1 + 3) = 1;
    KeInitializeSpinLock(v1);
    v1[14] = (KSPIN_LOCK)(v1 + 13);
    v1[13] = (KSPIN_LOCK)(v1 + 13);
    v1[16] = 0;
    v1[26] = 0;
    v1[25] = 0;
  }
  return v1;
}

```

## disassembly

```asm
0x140011138  push    rbx
0x14001113a  sub     rsp, 20h
0x14001113e  lea     rcx, Lookaside; Lookaside
0x140011145  call    cs:__imp_ExAllocateFromLookasideListEx
0x14001114c  nop     dword ptr [rax+rax+00h]
0x140011151  mov     rbx, rax
0x140011154  test    rax, rax
0x140011157  jz      short loc_1400111AB
0x140011159  xor     edx, edx; Val
0x14001115b  mov     r8d, 140h; Size
0x140011161  mov     rcx, rax; void *
0x140011164  call    memset
0x140011169  mov     rcx, rbx; SpinLock
0x14001116c  mov     dword ptr [rbx+0Ch], 1
0x140011173  call    cs:__imp_KeInitializeSpinLock
0x14001117a  nop     dword ptr [rax+rax+00h]
0x14001117f  lea     rcx, [rbx+68h]
0x140011183  mov     [rcx+8], rcx
0x140011187  mov     [rcx], rcx
0x14001118a  mov     qword ptr [rbx+80h], 0
0x140011195  mov     qword ptr [rbx+0D0h], 0
0x1400111a0  mov     qword ptr [rbx+0C8h], 0
0x1400111ab  mov     rax, rbx
0x1400111ae  add     rsp, 20h
0x1400111b2  pop     rbx
0x1400111b3  retn
```
