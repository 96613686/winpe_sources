# AcquireSpinLock

- ea: `0x14000a730`
- end: `0x14000a7ac`
- name: `AcquireSpinLock`
- size: `124`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000228c`
- `0x140009e70`
- `0x14000c5b0`
- `0x14000ea3c`

## callees

- `0x14000a730`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14000a79d`
- `ntoskrnl!DbgPrint` at `0x14000a79d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a77c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a77c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a75b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a75b`

## pseudocode

```c
void __fastcall AcquireSpinLock(_DWORD *a1, const char *a2, int a3, char a4)
{
  KSPIN_LOCK *v8; // rcx

  if ( *a1 != 1801678668 )
  {
    DbgPrint("Trying to acquire uninited lock %p, %s, Line %d\n", a1, a2, a3);
    __debugbreak();
  }
  _InterlockedIncrement(a1 + 1);
  v8 = (KSPIN_LOCK *)(a1 + 20);
  if ( a4 )
    KeAcquireSpinLockAtDpcLevel(v8);
  else
    *((_BYTE *)a1 + 88) = KeAcquireSpinLockRaiseToDpc(v8);
  *((_BYTE *)a1 + 8) = 1;
  *((_QWORD *)a1 + 6) = a2;
  a1[14] = a3;
}

```

## disassembly

```asm
0x14000a730  push    rbx
0x14000a732  push    rbp
0x14000a733  push    rsi
0x14000a734  push    rdi
0x14000a735  sub     rsp, 28h
0x14000a739  cmp     dword ptr [rcx], 6B636F4Ch
0x14000a73f  movzx   ebp, r9b
0x14000a743  mov     edi, r8d
0x14000a746  mov     rsi, rdx
0x14000a749  mov     rbx, rcx
0x14000a74c  jnz     short loc_14000A78D
0x14000a74e  lock inc dword ptr [rbx+4]
0x14000a752  lea     rcx, [rbx+50h]; SpinLock
0x14000a756  test    bpl, bpl
0x14000a759  jz      short loc_14000A77C
0x14000a75b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000a762  nop     dword ptr [rax+rax+00h]
0x14000a767  mov     byte ptr [rbx+8], 1
0x14000a76b  mov     [rbx+30h], rsi
0x14000a76f  mov     [rbx+38h], edi
0x14000a772  add     rsp, 28h
0x14000a776  pop     rdi
0x14000a777  pop     rsi
0x14000a778  pop     rbp
0x14000a779  pop     rbx
0x14000a77a  retn
0x14000a77c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a783  nop     dword ptr [rax+rax+00h]
0x14000a788  mov     [rbx+58h], al
0x14000a78b  jmp     short loc_14000A767
0x14000a78d  mov     r9d, edi
0x14000a790  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x14000a797  mov     r8, rsi
0x14000a79a  mov     rdx, rbx
0x14000a79d  call    cs:__imp_DbgPrint
0x14000a7a4  nop     dword ptr [rax+rax+00h]
0x14000a7a9  int     3; Trap to Debugger
0x14000a7aa  jmp     short loc_14000A74E
```
