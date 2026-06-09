# WinHvTranslateVirtualAddress

- ea: `0x1400034b0`
- end: `0x140003609`
- name: `WinHvTranslateVirtualAddress`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x1400034b0`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400035a9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400035a9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003509`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003509`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400035c3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400035c3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400035df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400035df`

## pseudocode

```c
__int64 __fastcall WinHvTranslateVirtualAddress(__int64 a1, int a2, __int64 a3, __int64 a4, _OWORD *a5, _QWORD *a6)
{
  __int64 LockArray_high; // r10
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  int v14; // edi
  _QWORD v16[9]; // [rsp+20h] [rbp-48h] BYREF

  memset(v16, 0, 0x40u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v16[5] = 0;
  LOWORD(v16[4]) = *(_WORD *)(WinHvpProcessorToNode + 2 * LockArray_high);
  v11 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside
                                                                            + ((unsigned __int64)LOWORD(v16[4]) << 7)));
  v16[5] = v11;
  v16[7] = WinHvpReleasePoolBuffers;
  if ( !v11 )
  {
    LOBYTE(v16[6]) = KeGetCurrentIrql();
    if ( LOBYTE(v16[6]) >= 2u )
    {
      LOBYTE(v16[6]) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
      v11 = WinHvpFallbackBuffer;
    }
    else
    {
      ExAcquireFastMutex(&WinHvpFallbackMutex);
      v11 = WinHvpFallbackBuffer2;
    }
    v16[5] = v11;
    v16[7] = WinHvpReleaseFallbackBuffers;
  }
  v12 = v11[2];
  v16[1] = v12;
  v13 = v11[4];
  v16[0] = v16;
  v16[2] = v13;
  *(_QWORD *)v12 = a1;
  *(_DWORD *)(v12 + 8) = a2;
  *(_QWORD *)(v12 + 16) = a3;
  *(_QWORD *)(v12 + 24) = a4;
  v14 = WinHvpSimplePoolHypercall_CallViaMacro(v16[0], 172);
  if ( v14 >= 0 )
  {
    *a5 = *(_OWORD *)v13;
    a5[1] = *(_OWORD *)(v13 + 16);
    a5[2] = *(_OWORD *)(v13 + 32);
    *a6 = *(_QWORD *)(v13 + 48);
  }
  ((void (__fastcall *)(_QWORD))v16[7])(v16[0]);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400034b0  push    rbp
0x1400034b2  push    rbx
0x1400034b3  push    rsi
0x1400034b4  push    rdi
0x1400034b5  push    r14
0x1400034b7  push    r15
0x1400034b9  mov     rbp, rsp
0x1400034bc  sub     rsp, 68h
0x1400034c0  mov     r14d, edx
0x1400034c3  mov     rsi, r8
0x1400034c6  xor     edx, edx; Val
0x1400034c8  mov     r15, rcx
0x1400034cb  lea     rcx, [rbp+var_48]; void *
0x1400034cf  mov     rdi, r9
0x1400034d2  lea     r8d, [rdx+40h]; Size
0x1400034d6  call    memset
0x1400034db  mov     eax, gs:1A4h
0x1400034e3  mov     r10d, eax
0x1400034e6  mov     rax, cs:WinHvpProcessorToNode
0x1400034ed  mov     [rbp+var_20], 0
0x1400034f5  movzx   ecx, word ptr [rax+r10*2]
0x1400034fa  mov     [rbp+var_28], cx
0x1400034fe  shl     rcx, 7
0x140003502  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x140003509  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140003510  nop     dword ptr [rax+rax+00h]
0x140003515  mov     rcx, rax
0x140003518  mov     [rbp+var_20], rax
0x14000351c  lea     rax, WinHvpReleasePoolBuffers
0x140003523  mov     [rbp+var_10], rax
0x140003527  test    rcx, rcx
0x14000352a  jz      short loc_1400035A9
0x14000352c  mov     rax, [rcx+10h]
0x140003530  mov     edx, 0ACh
0x140003535  mov     [rbp+var_40], rax
0x140003539  mov     rbx, [rcx+20h]
0x14000353d  lea     rcx, [rbp+var_48]
0x140003541  mov     [rbp+var_48], rcx
0x140003545  mov     [rbp+var_38], rbx
0x140003549  mov     [rax], r15
0x14000354c  mov     [rax+8], r14d
0x140003550  mov     [rax+10h], rsi
0x140003554  mov     [rax+18h], rdi
0x140003558  mov     rcx, [rbp+var_48]
0x14000355c  call    WinHvpSimplePoolHypercall_CallViaMacro
0x140003561  mov     edi, eax
0x140003563  test    eax, eax
0x140003565  js      short loc_14000358C
0x140003567  movaps  xmm0, xmmword ptr [rbx]
0x14000356a  mov     rcx, [rbp+arg_20]
0x14000356e  movaps  xmmword ptr [rcx], xmm0
0x140003571  movaps  xmm1, xmmword ptr [rbx+10h]
0x140003575  movaps  xmmword ptr [rcx+10h], xmm1
0x140003579  movaps  xmm0, xmmword ptr [rbx+20h]
0x14000357d  movaps  xmmword ptr [rcx+20h], xmm0
0x140003581  mov     rcx, [rbp+arg_28]
0x140003585  mov     rdx, [rbx+30h]
0x140003589  mov     [rcx], rdx
0x14000358c  mov     rcx, [rbp+var_48]
0x140003590  mov     rax, [rbp+var_10]
0x140003594  call    _guard_dispatch_icall
0x140003599  mov     eax, edi
0x14000359b  add     rsp, 68h
0x14000359f  pop     r15
0x1400035a1  pop     r14
0x1400035a3  pop     rdi
0x1400035a4  pop     rsi
0x1400035a5  pop     rbx
0x1400035a6  pop     rbp
0x1400035a7  retn
0x1400035a9  call    cs:__imp_KeGetCurrentIrql
0x1400035b0  nop     dword ptr [rax+rax+00h]
0x1400035b5  mov     [rbp+var_18], al
0x1400035b8  cmp     al, 2
0x1400035ba  jnb     short loc_1400035D8
0x1400035bc  lea     rcx, WinHvpFallbackMutex; FastMutex
0x1400035c3  call    cs:__imp_ExAcquireFastMutex
0x1400035ca  nop     dword ptr [rax+rax+00h]
0x1400035cf  lea     rcx, WinHvpFallbackBuffer2
0x1400035d6  jmp     short loc_1400035F5
0x1400035d8  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x1400035df  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400035e6  nop     dword ptr [rax+rax+00h]
0x1400035eb  mov     [rbp+var_18], al
0x1400035ee  lea     rcx, WinHvpFallbackBuffer
0x1400035f5  lea     rax, WinHvpReleaseFallbackBuffers
0x1400035fc  mov     [rbp+var_20], rcx
0x140003600  mov     [rbp+var_10], rax
0x140003604  jmp     loc_14000352C
```
