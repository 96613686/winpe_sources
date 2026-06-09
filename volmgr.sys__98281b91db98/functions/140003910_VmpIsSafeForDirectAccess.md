# VmpIsSafeForDirectAccess

- ea: `0x140003910`
- end: `0x14000397d`
- name: `VmpIsSafeForDirectAccess`
- size: `109`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400136b8`

## callees

- `0x140003910`

## import_xrefs

- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140003931`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140003931`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140003950`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140003950`

## pseudocode

```c
__int64 __fastcall VmpIsSafeForDirectAccess(_BYTE *a1)
{
  unsigned __int8 v1; // bl
  __int64 v3; // rax
  KIRQL Irql; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  Irql = 0;
  if ( !a1[153] )
  {
    IoAcquireVpbSpinLock(&Irql);
    v3 = *(_QWORD *)(*(_QWORD *)a1 + 56LL);
    if ( !v3 || !*(_DWORD *)(v3 + 28) || (*(_BYTE *)(v3 + 4) & 0x21) != 1 )
      v1 = 1;
    IoReleaseVpbSpinLock(Irql);
  }
  return v1;
}

```

## disassembly

```asm
0x140003910  mov     [rsp+arg_8], rbx
0x140003915  push    rdi
0x140003916  sub     rsp, 20h
0x14000391a  xor     bl, bl
0x14000391c  mov     [rsp+28h+Irql], 0
0x140003921  mov     rdi, rcx
0x140003924  cmp     [rcx+99h], bl
0x14000392a  jnz     short loc_14000395C
0x14000392c  lea     rcx, [rsp+28h+Irql]; Irql
0x140003931  call    cs:__imp_IoAcquireVpbSpinLock
0x140003938  nop     dword ptr [rax+rax+00h]
0x14000393d  mov     rax, [rdi]
0x140003940  mov     rax, [rax+38h]
0x140003944  test    rax, rax
0x140003947  jnz     short loc_14000396B
0x140003949  mov     bl, 1
0x14000394b  movzx   ecx, [rsp+28h+Irql]; Irql
0x140003950  call    cs:__imp_IoReleaseVpbSpinLock
0x140003957  nop     dword ptr [rax+rax+00h]
0x14000395c  movzx   eax, bl
0x14000395f  mov     rbx, [rsp+28h+arg_8]
0x140003964  add     rsp, 20h
0x140003968  pop     rdi
0x140003969  retn
0x14000396b  cmp     dword ptr [rax+1Ch], 0
0x14000396f  jz      short loc_140003949
0x140003971  movzx   eax, byte ptr [rax+4]
0x140003975  and     al, 21h
0x140003977  cmp     al, 1
0x140003979  jz      short loc_14000394B
0x14000397b  jmp     short loc_140003949
```
