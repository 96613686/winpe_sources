# RtlReleaseScalableReadLock

- ea: `0x140004a40`
- end: `0x140004a6f`
- name: `RtlReleaseScalableReadLock`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140003830`
- `0x140004648`
- `0x1400192b0`
- `0x14001a2e0`
- `0x14001ac70`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140004a5d`
- `ntoskrnl!KeLowerIrql` at `0x140004a5d`

## pseudocode

```c
void __fastcall RtlReleaseScalableReadLock(__int64 a1, unsigned int a2, KIRQL a3)
{
  _InterlockedDecrement((volatile signed __int32 *)((((a2 & *(_DWORD *)(a1 + 8)) + 1LL) << 6) + a1));
  KeLowerIrql(a3);
}

```

## disassembly

```asm
0x140004a40  sub     rsp, 28h
0x140004a44  mov     r9d, [rcx+8]
0x140004a48  mov     eax, edx
0x140004a4a  and     r9, rax
0x140004a4d  inc     r9
0x140004a50  shl     r9, 6
0x140004a54  lock dec dword ptr [r9+rcx]
0x140004a59  movzx   ecx, r8b; NewIrql
0x140004a5d  call    cs:__imp_KeLowerIrql
0x140004a64  nop     dword ptr [rax+rax+00h]
0x140004a69  add     rsp, 28h
0x140004a6d  retn
```
