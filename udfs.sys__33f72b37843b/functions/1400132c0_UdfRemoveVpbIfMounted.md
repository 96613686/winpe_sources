# UdfRemoveVpbIfMounted

- ea: `0x1400132c0`
- end: `0x140013340`
- name: `UdfRemoveVpbIfMounted`
- size: `128`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140006680`
- `0x14000cce0`
- `0x140035ca4`

## callees

- `0x1400132c0`
- `0x14001c080`

## import_xrefs

- `ntoskrnl!IoAcquireVpbSpinLock` at `0x1400132e0`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x1400132e0`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140013329`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140013329`

## pseudocode

```c
void __fastcall UdfRemoveVpbIfMounted(__int64 a1, __int64 a2, _DWORD **a3)
{
  _DWORD *v3; // rdi
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a3;
  Irql = 0;
  IoAcquireVpbSpinLock(&Irql);
  if ( a2 == *(_QWORD *)(a1 + 56) )
  {
    memset(v3, 0, 0x60u);
    *v3 = 6291466;
    *((_QWORD *)v3 + 2) = a1;
    *((_WORD *)v3 + 2) = *(_WORD *)(*(_QWORD *)(a1 + 56) + 4LL) & 8;
    *(_QWORD *)(a1 + 56) = v3;
    *a3 = 0;
  }
  IoReleaseVpbSpinLock(Irql);
}

```

## disassembly

```asm
0x1400132c0  push    rbx
0x1400132c2  push    rsi
0x1400132c3  push    rdi
0x1400132c4  push    r14
0x1400132c6  sub     rsp, 28h
0x1400132ca  mov     rdi, [r8]
0x1400132cd  mov     rsi, rcx
0x1400132d0  lea     rcx, [rsp+48h+Irql]; Irql
0x1400132d5  mov     [rsp+48h+Irql], 0
0x1400132da  mov     r14, r8
0x1400132dd  mov     rbx, rdx
0x1400132e0  call    cs:__imp_IoAcquireVpbSpinLock
0x1400132e7  nop     dword ptr [rax+rax+00h]
0x1400132ec  cmp     rbx, [rsi+38h]
0x1400132f0  jnz     short loc_140013325
0x1400132f2  xor     edx, edx; Val
0x1400132f4  mov     rcx, rdi; void *
0x1400132f7  lea     r8d, [rdx+60h]; Size
0x1400132fb  call    memset
0x140013300  mov     dword ptr [rdi], 60000Ah
0x140013306  mov     [rdi+10h], rsi
0x14001330a  mov     rax, [rsi+38h]
0x14001330e  movzx   ecx, word ptr [rax+4]
0x140013312  and     cx, 8
0x140013316  mov     [rdi+4], cx
0x14001331a  mov     [rsi+38h], rdi
0x14001331e  mov     qword ptr [r14], 0
0x140013325  mov     cl, [rsp+48h+Irql]; Irql
0x140013329  call    cs:__imp_IoReleaseVpbSpinLock
0x140013330  nop     dword ptr [rax+rax+00h]
0x140013335  add     rsp, 28h
0x140013339  pop     r14
0x14001333b  pop     rdi
0x14001333c  pop     rsi
0x14001333d  pop     rbx
0x14001333e  retn
```
