# WinHvPostMessage2

- ea: `0x1400030b0`
- end: `0x14000322b`
- name: `WinHvPostMessage2`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140005fe0`

## callees

- `0x1400030b0`
- `0x140003610`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400031c4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400031c4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003131`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003131`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400031de`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400031de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400031fa`

## pseudocode

```c
__int64 __fastcall WinHvPostMessage2(int a1, int a2, int a3, const void *a4, size_t Size)
{
  __int64 LockArray_high; // rcx
  __int64 v10; // rcx
  __int64 *v11; // rax
  _DWORD *v12; // rdi
  unsigned int v13; // ebx
  _QWORD v15[8]; // [rsp+20h] [rbp-40h] BYREF

  memset(v15, 0, sizeof(v15));
  if ( (a3 & 0xFFFFFFFE) != 0 || (a3 & 1) != 0 || Size > 0xF0 )
    return 3221225485LL;
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v15[5] = 0;
  v10 = *(unsigned __int16 *)(WinHvpProcessorToNode + 2 * LockArray_high);
  LOWORD(v15[4]) = v10;
  v11 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside + (v10 << 7)));
  v15[5] = v11;
  v15[7] = WinHvpReleasePoolBuffers;
  if ( !v11 )
  {
    LOBYTE(v15[6]) = KeGetCurrentIrql();
    if ( LOBYTE(v15[6]) >= 2u )
    {
      LOBYTE(v15[6]) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
      v11 = WinHvpFallbackBuffer;
    }
    else
    {
      ExAcquireFastMutex(&WinHvpFallbackMutex);
      v11 = WinHvpFallbackBuffer2;
    }
    v15[5] = v11;
    v15[7] = WinHvpReleaseFallbackBuffers;
  }
  v12 = (_DWORD *)v11[2];
  v15[1] = v12;
  v15[2] = 0;
  v15[0] = v15;
  *v12 = a1;
  v12[2] = a2;
  v12[3] = Size;
  memmove(v12 + 4, a4, Size);
  memset((char *)v12 + Size + 16, 0, 240 - Size);
  v13 = WinHvpSimplePoolHypercall_CallViaMacro(v15[0], 92);
  ((void (__fastcall *)(_QWORD))v15[7])(v15[0]);
  return v13;
}

```

## disassembly

```asm
0x1400030b0  push    rbp
0x1400030b2  push    rbx
0x1400030b3  push    rsi
0x1400030b4  push    rdi
0x1400030b5  push    r12
0x1400030b7  push    r14
0x1400030b9  push    r15
0x1400030bb  mov     rbp, rsp
0x1400030be  sub     rsp, 60h
0x1400030c2  mov     r12d, edx
0x1400030c5  mov     edi, r8d
0x1400030c8  xor     edx, edx; Val
0x1400030ca  mov     ebx, ecx
0x1400030cc  lea     rcx, [rbp+var_40]; void *
0x1400030d0  mov     r15, r9
0x1400030d3  lea     r8d, [rdx+40h]; Size
0x1400030d7  call    memset
0x1400030dc  test    edi, 0FFFFFFFEh
0x1400030e2  jnz     loc_140003224
0x1400030e8  test    dil, 1
0x1400030ec  jnz     loc_140003224
0x1400030f2  mov     rsi, [rbp+Size]
0x1400030f6  mov     r14d, 0F0h
0x1400030fc  cmp     rsi, r14
0x1400030ff  ja      loc_140003224
0x140003105  mov     eax, gs:1A4h
0x14000310d  mov     ecx, eax
0x14000310f  mov     rax, cs:WinHvpProcessorToNode
0x140003116  mov     [rbp+var_18], 0
0x14000311e  movzx   ecx, word ptr [rax+rcx*2]
0x140003122  mov     [rbp+var_20], cx
0x140003126  shl     rcx, 7
0x14000312a  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140003131  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140003138  nop     dword ptr [rax+rax+00h]
0x14000313d  mov     [rbp+var_18], rax
0x140003141  lea     rcx, WinHvpReleasePoolBuffers
0x140003148  mov     [rbp+var_8], rcx
0x14000314c  test    rax, rax
0x14000314f  jz      short loc_1400031C4
0x140003151  mov     rdi, [rax+10h]
0x140003155  mov     r8, rsi; Size
0x140003158  mov     [rbp+var_38], rdi
0x14000315c  lea     rax, [rbp+var_40]
0x140003160  mov     [rbp+var_30], 0
0x140003168  mov     rdx, r15; Src
0x14000316b  mov     [rbp+var_40], rax
0x14000316f  mov     [rdi], ebx
0x140003171  lea     rcx, [rdi+10h]; void *
0x140003175  mov     [rdi+8], r12d
0x140003179  mov     [rdi+0Ch], esi
0x14000317c  call    memmove
0x140003181  lea     rcx, [rsi+10h]
0x140003185  sub     r14, rsi
0x140003188  add     rcx, rdi; void *
0x14000318b  mov     r8, r14; Size
0x14000318e  xor     edx, edx; Val
0x140003190  call    memset
0x140003195  mov     rcx, [rbp+var_40]
0x140003199  mov     edx, 5Ch ; '\'
0x14000319e  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400031a3  mov     rcx, [rbp+var_40]
0x1400031a7  mov     ebx, eax
0x1400031a9  mov     rax, [rbp+var_8]
0x1400031ad  call    _guard_dispatch_icall
0x1400031b2  mov     eax, ebx
0x1400031b4  add     rsp, 60h
0x1400031b8  pop     r15
0x1400031ba  pop     r14
0x1400031bc  pop     r12
0x1400031be  pop     rdi
0x1400031bf  pop     rsi
0x1400031c0  pop     rbx
0x1400031c1  pop     rbp
0x1400031c2  retn
0x1400031c4  call    cs:__imp_KeGetCurrentIrql
0x1400031cb  nop     dword ptr [rax+rax+00h]
0x1400031d0  mov     [rbp+var_10], al
0x1400031d3  cmp     al, 2
0x1400031d5  jnb     short loc_1400031F3
0x1400031d7  lea     rcx, WinHvpFallbackMutex; FastMutex
0x1400031de  call    cs:__imp_ExAcquireFastMutex
0x1400031e5  nop     dword ptr [rax+rax+00h]
0x1400031ea  lea     rax, WinHvpFallbackBuffer2
0x1400031f1  jmp     short loc_140003210
0x1400031f3  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x1400031fa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003201  nop     dword ptr [rax+rax+00h]
0x140003206  mov     [rbp+var_10], al
0x140003209  lea     rax, WinHvpFallbackBuffer
0x140003210  lea     rcx, WinHvpReleaseFallbackBuffers
0x140003217  mov     [rbp+var_18], rax
0x14000321b  mov     [rbp+var_8], rcx
0x14000321f  jmp     loc_140003151
0x140003224  mov     eax, 0C000000Dh
0x140003229  jmp     short loc_1400031B4
```
