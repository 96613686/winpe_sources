# UdfMarkDevForVerifyIfVcbMounted

- ea: `0x140018cec`
- end: `0x140018d49`
- name: `UdfMarkDevForVerifyIfVcbMounted`
- size: `93`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140006680`
- `0x14000cce0`
- `0x1400444c4`
- `0x140055060`

## callees

- `0x140018cec`

## import_xrefs

- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140018d04`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140018d04`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140018d2f`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140018d2f`

## pseudocode

```c
char __fastcall UdfMarkDevForVerifyIfVcbMounted(__int64 a1)
{
  char v2; // bl
  __int64 v3; // rax
  __int64 v4; // rdx
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  Irql = 0;
  IoAcquireVpbSpinLock(&Irql);
  v3 = *(_QWORD *)(a1 + 8);
  v4 = *(_QWORD *)(v3 + 16);
  if ( *(_QWORD *)(v4 + 56) == v3 )
  {
    *(_DWORD *)(v4 + 48) |= 2u;
    v2 = 1;
  }
  else
  {
    *(_DWORD *)(a1 + 48) |= 0x8000u;
  }
  IoReleaseVpbSpinLock(Irql);
  return v2;
}

```

## disassembly

```asm
0x140018cec  mov     [rsp+arg_8], rbx
0x140018cf1  push    rdi
0x140018cf2  sub     rsp, 20h
0x140018cf6  mov     rdi, rcx
0x140018cf9  xor     ebx, ebx
0x140018cfb  lea     rcx, [rsp+28h+Irql]; Irql
0x140018d00  mov     [rsp+28h+Irql], bl
0x140018d04  call    cs:__imp_IoAcquireVpbSpinLock
0x140018d0b  nop     dword ptr [rax+rax+00h]
0x140018d10  mov     rax, [rdi+8]
0x140018d14  mov     rdx, [rax+10h]
0x140018d18  cmp     [rdx+38h], rax
0x140018d1c  jnz     short loc_140018D26
0x140018d1e  or      dword ptr [rdx+30h], 2
0x140018d22  mov     bl, 1
0x140018d24  jmp     short loc_140018D2B
0x140018d26  bts     dword ptr [rdi+30h], 0Fh
0x140018d2b  mov     cl, [rsp+28h+Irql]; Irql
0x140018d2f  call    cs:__imp_IoReleaseVpbSpinLock
0x140018d36  nop     dword ptr [rax+rax+00h]
0x140018d3b  mov     al, bl
0x140018d3d  mov     rbx, [rsp+28h+arg_8]
0x140018d42  add     rsp, 20h
0x140018d46  pop     rdi
0x140018d47  retn
```
