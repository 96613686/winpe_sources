# SkiUpdateActiveHiberSwapShadowStack

- ea: `0x14009b438`
- end: `0x14009b58e`
- name: `SkiUpdateActiveHiberSwapShadowStack`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14009b304`

## callees

- `0x14000ff98`
- `0x1400119c4`
- `0x1400202b0`
- `0x1400202ec`
- `0x140075f38`
- `0x1400789d4`
- `0x14009b0d4`
- `0x14009b22c`
- `0x14009b3e8`
- `0x14009b438`
- `0x1400fbf90`

## pseudocode

```c
_UNKNOWN **__fastcall SkiUpdateActiveHiberSwapShadowStack(__int64 a1, __int64 a2)
{
  _UNKNOWN **result; // rax
  __int64 v3; // rbp
  __int64 v6; // rdx
  __int64 NtSsp; // rbx
  __int64 v8; // rbx
  __int64 ConflictingNar; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h] BYREF

  result = &retaddr;
  v3 = 0;
  if ( (SkmiFlags & 0x80000) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 3064);
    if ( !v6 )
      SkeBugCheckEx(0x172u, 0xBu, *(unsigned __int16 *)(a1 + 180), 0, 0);
    SkiCopyKernelShadowStacks(*(_QWORD *)(a1 + 3056), v6, 3);
    NtSsp = SkiReadNtSsp();
    SkiGetShadowStackExtents((NtSsp & 0xFFFFFFFFFFFFF000uLL) + 0x2000);
    if ( *(_QWORD *)(a1 + 3064) != 0x2000 )
      SkeBugCheckEx(0x172u, 0xDu, *(unsigned __int16 *)(a1 + 180), 0x2000u, *(_QWORD *)(a1 + 3064));
    *(_QWORD *)(a1 + 3072) = 4096 - NtSsp;
    if ( (unsigned __int8)RtlMinimalBarrier(a2) )
      SkmmProtectAllShadowStacks(0);
    RtlMinimalBarrier(a2);
    do
    {
      v8 = *(_QWORD *)(32 * v3 + a1 + 3064);
      SkAcquireSpinLockSharedAtDpcLevel(&SkmiNarSpinLock);
      ConflictingNar = SkmiFindConflictingNar(v8 - 4104, 1);
      SkmiProtectOneShadowStack(ConflictingNar, 1);
      _InterlockedDecrement(&SkmiNarSpinLock);
      SkTrackSpinLockRelease(v11, v10);
      ++v3;
    }
    while ( v3 != 5 );
    return (_UNKNOWN **)RtlMinimalBarrier(a2);
  }
  return result;
}

```

## disassembly

```asm
0x14009b438  mov     rax, rsp
0x14009b43b  mov     [rax+8], rbx
0x14009b43f  push    rbp
0x14009b440  push    rsi
0x14009b441  push    rdi
0x14009b442  sub     rsp, 30h
0x14009b446  xor     ebp, ebp
0x14009b448  mov     rsi, rdx
0x14009b44b  test    cs:SkmiFlags, 80000h
0x14009b455  mov     rdi, rcx
0x14009b458  mov     [rax+20h], rbp
0x14009b45c  mov     [rax+18h], rbp
0x14009b460  jz      loc_14009B580
0x14009b466  mov     rdx, [rcx+0BF8h]
0x14009b46d  test    rdx, rdx
0x14009b470  jnz     short loc_14009B48F
0x14009b472  movzx   r8d, word ptr [rcx+0B4h]; BugCheckParameter2
0x14009b47a  lea     edx, [rbp+0Bh]; BugCheckParameter1
0x14009b47d  mov     ecx, 172h; BugCheckCode
0x14009b482  mov     [rax-28h], rbp
0x14009b486  xor     r9d, r9d; BugCheckParameter3
0x14009b489  call    SkeBugCheckEx
0x14009b48f  mov     rcx, [rcx+0BF0h]
0x14009b496  mov     r8d, 3
0x14009b49c  call    SkiCopyKernelShadowStacks
0x14009b4a1  call    SkiReadNtSsp
0x14009b4a6  mov     rcx, rax
0x14009b4a9  lea     r8, [rsp+48h+arg_18]
0x14009b4ae  and     rcx, 0FFFFFFFFFFFFF000h
0x14009b4b5  lea     rdx, [rsp+48h+arg_10]
0x14009b4ba  add     rcx, 2000h; BugCheckParameter3
0x14009b4c1  mov     rbx, rax
0x14009b4c4  call    SkiGetShadowStackExtents
0x14009b4c9  mov     rcx, [rsp+48h+arg_10]
0x14009b4ce  mov     rdx, [rdi+0BF8h]
0x14009b4d5  lea     r9, [rcx+2000h]; BugCheckParameter3
0x14009b4dc  cmp     rdx, r9
0x14009b4df  jz      short loc_14009B4FE
0x14009b4e1  movzx   r8d, word ptr [rdi+0B4h]; BugCheckParameter2
0x14009b4e9  mov     ecx, 172h; BugCheckCode
0x14009b4ee  mov     [rsp+48h+BugCheckParameter4], rdx; BugCheckParameter4
0x14009b4f3  mov     edx, 0Dh; BugCheckParameter1
0x14009b4f8  call    SkeBugCheckEx
0x14009b4fe  sub     rcx, rbx
0x14009b501  add     rcx, 1000h
0x14009b508  mov     [rdi+0C00h], rcx
0x14009b50f  mov     rcx, rsi
0x14009b512  call    RtlMinimalBarrier
0x14009b517  test    al, al
0x14009b519  jz      short loc_14009B522
0x14009b51b  xor     ecx, ecx
0x14009b51d  call    SkmmProtectAllShadowStacks
0x14009b522  mov     rcx, rsi
0x14009b525  call    RtlMinimalBarrier
0x14009b52a  mov     rax, rbp
0x14009b52d  lea     rcx, SkmiNarSpinLock
0x14009b534  shl     rax, 5
0x14009b538  mov     rbx, [rax+rdi+0BF8h]
0x14009b540  call    SkAcquireSpinLockSharedAtDpcLevel
0x14009b545  mov     edx, 1
0x14009b54a  lea     rcx, [rbx-1008h]
0x14009b551  call    SkmiFindConflictingNar
0x14009b556  mov     edx, 1
0x14009b55b  mov     rcx, rax
0x14009b55e  call    SkmiProtectOneShadowStack
0x14009b563  lock dec cs:SkmiNarSpinLock
0x14009b56a  call    SkTrackSpinLockRelease
0x14009b56f  inc     rbp
0x14009b572  cmp     rbp, 5
0x14009b576  jnz     short loc_14009B52A
0x14009b578  mov     rcx, rsi
0x14009b57b  call    RtlMinimalBarrier
0x14009b580  mov     rbx, [rsp+48h+arg_0]
0x14009b585  add     rsp, 30h
0x14009b589  pop     rdi
0x14009b58a  pop     rsi
0x14009b58b  pop     rbp
0x14009b58c  retn
```
