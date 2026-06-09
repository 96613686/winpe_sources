# SqospLookupFlow

- ea: `0x140003870`
- end: `0x14000390a`
- name: `SqospLookupFlow`
- size: `154`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140006188`
- `0x1400111bc`
- `0x1400117e4`

## callees

- `0x140003870`
- `0x140005e88`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400038b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400038e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400038b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400038e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003887`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003887`

## pseudocode

```c
KSPIN_LOCK *__fastcall SqospLookupFlow(PKSPIN_LOCK SpinLock, __int64 a2, char a3, __int64 a4)
{
  KIRQL v8; // al
  KSPIN_LOCK *v9; // r10
  KSPIN_LOCK *v10; // rbx

  v8 = KeAcquireSpinLockRaiseToDpc(SpinLock);
  v9 = (KSPIN_LOCK *)SpinLock[13];
  *((_BYTE *)SpinLock + 8) = v8;
  while ( 1 )
  {
    if ( v9 == SpinLock + 13 )
    {
      KeReleaseSpinLock(SpinLock, v8);
      v10 = 0;
      goto LABEL_8;
    }
    v10 = v9 - 5;
    if ( *(v9 - 5) == a2 )
      break;
    v9 = (KSPIN_LOCK *)*v9;
  }
  KeReleaseSpinLock(SpinLock, v8);
  if ( v10 )
    return v10;
LABEL_8:
  if ( a3 )
    return v10;
  return (KSPIN_LOCK *)SqospCreateFlow(SpinLock, a2, a4);
}

```

## disassembly

```asm
0x140003870  push    rbp
0x140003872  push    rsi
0x140003873  push    rdi
0x140003874  push    r14
0x140003876  sub     rsp, 28h
0x14000387a  mov     r14, r9
0x14000387d  movzx   ebp, r8b
0x140003881  mov     rsi, rdx
0x140003884  mov     rdi, rcx
0x140003887  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000388e  nop     dword ptr [rax+rax+00h]
0x140003893  mov     r10, [rdi+68h]
0x140003897  lea     rcx, [rdi+68h]
0x14000389b  mov     [rdi+8], al
0x14000389e  mov     [rsp+48h+arg_0], rbx
0x1400038a3  cmp     r10, rcx
0x1400038a6  jz      short loc_1400038E1
0x1400038a8  cmp     [r10-28h], rsi
0x1400038ac  lea     rbx, [r10-28h]
0x1400038b0  jnz     short loc_1400038DC
0x1400038b2  movzx   edx, al; NewIrql
0x1400038b5  mov     rcx, rdi; SpinLock
0x1400038b8  call    cs:__imp_KeReleaseSpinLock
0x1400038bf  nop     dword ptr [rax+rax+00h]
0x1400038c4  test    rbx, rbx
0x1400038c7  jz      short loc_1400038F5
0x1400038c9  mov     rax, rbx
0x1400038cc  mov     rbx, [rsp+48h+arg_0]
0x1400038d1  add     rsp, 28h
0x1400038d5  pop     r14
0x1400038d7  pop     rdi
0x1400038d8  pop     rsi
0x1400038d9  pop     rbp
0x1400038da  retn
0x1400038dc  mov     r10, [r10]
0x1400038df  jmp     short loc_1400038A3
0x1400038e1  movzx   edx, al; NewIrql
0x1400038e4  mov     rcx, rdi; SpinLock
0x1400038e7  call    cs:__imp_KeReleaseSpinLock
0x1400038ee  nop     dword ptr [rax+rax+00h]
0x1400038f3  xor     ebx, ebx
0x1400038f5  test    bpl, bpl
0x1400038f8  jnz     short loc_1400038C9
0x1400038fa  mov     r8, r14
0x1400038fd  mov     rdx, rsi
0x140003900  mov     rcx, rdi; SpinLock
0x140003903  call    SqospCreateFlow
0x140003908  jmp     short loc_1400038CC
```
