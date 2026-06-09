# WinHvpSetupHypercall

- ea: `0x140002240`
- end: `0x140002351`
- name: `WinHvpSetupHypercall`
- size: `273`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `100`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140001620`
- `0x140001a38`
- `0x140001d00`
- `0x140001ef0`
- `0x140004a00`
- `0x140005140`
- `0x140005220`
- `0x1400053c0`
- `0x140005500`
- `0x1400059c0`
- `0x140005f40`
- `0x140006000`
- `0x140006b50`
- `0x140006e60`
- `0x140006f00`
- `0x140007010`
- `0x140007160`
- `0x140007480`
- `0x140007550`
- `0x140007660`
- `0x14000786c`
- `0x1400078dc`
- `0x140007980`
- `0x140007e40`
- `0x1400080c0`
- `0x140008270`
- `0x140008310`
- `0x140008420`
- `0x140008610`
- `0x140008750`
- `0x1400087f0`
- `0x1400088c0`
- `0x140008970`
- `0x140008a80`
- `0x140008ef0`
- `0x140009350`
- `0x1400094a0`
- `0x1400095e0`
- `0x140009750`
- `0x14001b700`
- `0x14001b890`
- `0x14001c470`
- `0x14001c5a0`
- `0x14001c670`
- `0x14001c8e0`
- `0x14001ca20`
- `0x14001cae0`
- `0x14001cbc0`
- `0x14001cc40`
- `0x14001db10`

## callees

- `0x140002240`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400022e8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400022e8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002282`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002282`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002302`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002302`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000231e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000231e`

## pseudocode

```c
__int64 *__fastcall WinHvpSetupHypercall(__int64 **a1, __int64 *a2, __int64 a3)
{
  unsigned __int16 v6; // r9
  struct _NPAGED_LOOKASIDE_LIST *v7; // rcx
  __int64 *result; // rax
  __int64 v9; // rcx
  KIRQL CurrentIrql; // al

  v6 = *(_WORD *)(WinHvpProcessorToNode + 2LL * HIDWORD(KeGetPcr()[1].LockArray));
  *(_WORD *)(a3 + 32) = v6;
  v7 = (struct _NPAGED_LOOKASIDE_LIST *)(WinHvpNodeToHypercallLookaside + ((unsigned __int64)v6 << 7));
  *(_QWORD *)(a3 + 40) = 0;
  result = (__int64 *)ExAllocateFromNPagedLookasideList(v7);
  *(_QWORD *)(a3 + 40) = result;
  *(_QWORD *)(a3 + 56) = WinHvpReleasePoolBuffers;
  if ( !result )
  {
    CurrentIrql = KeGetCurrentIrql();
    *(_BYTE *)(a3 + 48) = CurrentIrql;
    if ( CurrentIrql >= 2u )
    {
      *(_BYTE *)(a3 + 48) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
      result = WinHvpFallbackBuffer;
    }
    else
    {
      ExAcquireFastMutex(&WinHvpFallbackMutex);
      result = WinHvpFallbackBuffer2;
    }
    *(_QWORD *)(a3 + 40) = result;
    *(_QWORD *)(a3 + 56) = WinHvpReleaseFallbackBuffers;
  }
  if ( a1 )
  {
    result = (__int64 *)result[2];
    *(_QWORD *)(a3 + 8) = result;
    *a1 = result;
  }
  else
  {
    *(_QWORD *)(a3 + 8) = 0;
  }
  if ( a2 )
  {
    result = *(__int64 **)(a3 + 40);
    v9 = result[4];
    *(_QWORD *)(a3 + 16) = v9;
    *a2 = v9;
  }
  else
  {
    *(_QWORD *)(a3 + 16) = 0;
  }
  *(_QWORD *)a3 = a3;
  return result;
}

```

## disassembly

```asm
0x140002240  push    rbx
0x140002242  push    rbp
0x140002243  push    rsi
0x140002244  push    rdi
0x140002245  sub     rsp, 28h
0x140002249  mov     eax, gs:1A4h
0x140002251  mov     rbx, r8
0x140002254  mov     rdi, rcx
0x140002257  mov     r8d, eax
0x14000225a  mov     rax, cs:WinHvpProcessorToNode
0x140002261  xor     ebp, ebp
0x140002263  mov     rsi, rdx
0x140002266  movzx   r9d, word ptr [rax+r8*2]
0x14000226b  mov     ecx, r9d
0x14000226e  mov     [rbx+20h], r9w
0x140002273  shl     rcx, 7
0x140002277  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x14000227e  mov     [rbx+28h], rbp
0x140002282  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002289  nop     dword ptr [rax+rax+00h]
0x14000228e  mov     [rbx+28h], rax
0x140002292  lea     rcx, WinHvpReleasePoolBuffers
0x140002299  mov     [rbx+38h], rcx
0x14000229d  test    rax, rax
0x1400022a0  jz      short loc_1400022E8
0x1400022a2  test    rdi, rdi
0x1400022a5  jz      loc_140002348
0x1400022ab  mov     rax, [rax+10h]
0x1400022af  mov     [rbx+8], rax
0x1400022b3  mov     [rdi], rax
0x1400022b6  test    rsi, rsi
0x1400022b9  jnz     short loc_1400022CC
0x1400022bb  mov     [rbx+10h], rbp
0x1400022bf  mov     [rbx], rbx
0x1400022c2  add     rsp, 28h
0x1400022c6  pop     rdi
0x1400022c7  pop     rsi
0x1400022c8  pop     rbp
0x1400022c9  pop     rbx
0x1400022ca  retn
0x1400022cc  mov     rax, [rbx+28h]
0x1400022d0  mov     rcx, [rax+20h]
0x1400022d4  mov     [rbx+10h], rcx
0x1400022d8  mov     [rsi], rcx
0x1400022db  mov     [rbx], rbx
0x1400022de  add     rsp, 28h
0x1400022e2  pop     rdi
0x1400022e3  pop     rsi
0x1400022e4  pop     rbp
0x1400022e5  pop     rbx
0x1400022e6  retn
0x1400022e8  call    cs:__imp_KeGetCurrentIrql
0x1400022ef  nop     dword ptr [rax+rax+00h]
0x1400022f4  mov     [rbx+30h], al
0x1400022f7  cmp     al, 2
0x1400022f9  jnb     short loc_140002317
0x1400022fb  lea     rcx, WinHvpFallbackMutex; FastMutex
0x140002302  call    cs:__imp_ExAcquireFastMutex
0x140002309  nop     dword ptr [rax+rax+00h]
0x14000230e  lea     rax, WinHvpFallbackBuffer2
0x140002315  jmp     short loc_140002334
0x140002317  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x14000231e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002325  nop     dword ptr [rax+rax+00h]
0x14000232a  mov     [rbx+30h], al
0x14000232d  lea     rax, WinHvpFallbackBuffer
0x140002334  lea     rcx, WinHvpReleaseFallbackBuffers
0x14000233b  mov     [rbx+28h], rax
0x14000233f  mov     [rbx+38h], rcx
0x140002343  jmp     loc_1400022A2
0x140002348  mov     [rbx+8], rbp
0x14000234c  jmp     loc_1400022B6
```
