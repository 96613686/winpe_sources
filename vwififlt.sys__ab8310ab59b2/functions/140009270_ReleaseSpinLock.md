# ReleaseSpinLock

- ea: `0x140009270`
- end: `0x1400092ed`
- name: `ReleaseSpinLock`
- size: `125`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x14000228c`
- `0x140006790`
- `0x140006bc0`
- `0x14000745c`
- `0x1400080f0`
- `0x1400087b0`
- `0x140008e70`
- `0x140009300`
- `0x1400097e4`
- `0x140009e70`
- `0x14000a260`
- `0x14000a4e0`
- `0x14000c5b0`
- `0x14000ea3c`

## callees

- `0x140009270`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1400092de`
- `ntoskrnl!DbgPrint` at `0x1400092de`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400092c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400092c0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400092a2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400092a2`

## pseudocode

```c
void __fastcall ReleaseSpinLock(_DWORD *a1, const char *a2, int a3, char a4)
{
  KSPIN_LOCK *v8; // rcx

  if ( *a1 != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", a1, a2, a3);
    __debugbreak();
  }
  *((_QWORD *)a1 + 8) = a2;
  v8 = (KSPIN_LOCK *)(a1 + 20);
  a1[18] = a3;
  *((_BYTE *)a1 + 8) = 0;
  if ( a4 )
    KeReleaseSpinLockFromDpcLevel(v8);
  else
    KeReleaseSpinLock(v8, *((_BYTE *)a1 + 88));
  _InterlockedDecrement(a1 + 1);
}

```

## disassembly

```asm
0x140009270  push    rbx
0x140009272  push    rbp
0x140009273  push    rsi
0x140009274  push    rdi
0x140009275  sub     rsp, 28h
0x140009279  cmp     dword ptr [rcx], 6B636F4Ch
0x14000927f  movzx   ebp, r9b
0x140009283  mov     edi, r8d
0x140009286  mov     rsi, rdx
0x140009289  mov     rbx, rcx
0x14000928c  jnz     short loc_1400092CE
0x14000928e  mov     [rbx+40h], rsi
0x140009292  lea     rcx, [rbx+50h]; SpinLock
0x140009296  mov     [rbx+48h], edi
0x140009299  mov     byte ptr [rbx+8], 0
0x14000929d  test    bpl, bpl
0x1400092a0  jz      short loc_1400092BC
0x1400092a2  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400092a9  nop     dword ptr [rax+rax+00h]
0x1400092ae  lock dec dword ptr [rbx+4]
0x1400092b2  add     rsp, 28h
0x1400092b6  pop     rdi
0x1400092b7  pop     rsi
0x1400092b8  pop     rbp
0x1400092b9  pop     rbx
0x1400092ba  retn
0x1400092bc  movzx   edx, byte ptr [rbx+58h]; NewIrql
0x1400092c0  call    cs:__imp_KeReleaseSpinLock
0x1400092c7  nop     dword ptr [rax+rax+00h]
0x1400092cc  jmp     short loc_1400092AE
0x1400092ce  mov     r9d, edi
0x1400092d1  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x1400092d8  mov     r8, rsi
0x1400092db  mov     rdx, rbx
0x1400092de  call    cs:__imp_DbgPrint
0x1400092e5  nop     dword ptr [rax+rax+00h]
0x1400092ea  int     3; Trap to Debugger
0x1400092eb  jmp     short loc_14000928E
```
