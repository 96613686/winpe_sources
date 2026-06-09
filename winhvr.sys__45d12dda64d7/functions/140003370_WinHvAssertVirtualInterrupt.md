# WinHvAssertVirtualInterrupt

- ea: `0x140003370`
- end: `0x1400034a5`
- name: `WinHvAssertVirtualInterrupt`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140003370`
- `0x140003610`
- `0x140009c90`
- `0x14000a040`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140003445`
- `ntoskrnl!KeGetCurrentIrql` at `0x140003445`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400033c5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400033c5`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000345f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000345f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000347b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000347b`

## pseudocode

```c
__int64 __fastcall WinHvAssertVirtualInterrupt(__int64 a1, __int64 a2, __int64 a3, int a4, char a5)
{
  __int64 LockArray_high; // rdx
  __int64 *v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  _QWORD v14[8]; // [rsp+20h] [rbp-40h] BYREF

  memset(v14, 0, sizeof(v14));
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v14[5] = 0;
  LOWORD(v14[4]) = *(_WORD *)(WinHvpProcessorToNode + 2 * LockArray_high);
  v10 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(WinHvpNodeToHypercallLookaside
                                                                            + ((unsigned __int64)LOWORD(v14[4]) << 7)));
  v14[5] = v10;
  v14[7] = WinHvpReleasePoolBuffers;
  if ( !v10 )
  {
    LOBYTE(v14[6]) = KeGetCurrentIrql();
    if ( LOBYTE(v14[6]) >= 2u )
    {
      LOBYTE(v14[6]) = KeAcquireSpinLockRaiseToDpc(&WinHvpFallbackSpinLock);
      v10 = WinHvpFallbackBuffer;
    }
    else
    {
      ExAcquireFastMutex(&WinHvpFallbackMutex);
      v10 = WinHvpFallbackBuffer2;
    }
    v14[5] = v10;
    v14[7] = WinHvpReleaseFallbackBuffers;
  }
  v11 = v10[2];
  v14[1] = v11;
  v14[0] = v14;
  v14[2] = 0;
  *(_WORD *)(v11 + 29) = 0;
  *(_BYTE *)(v11 + 31) = 0;
  *(_QWORD *)v11 = a1;
  *(_QWORD *)(v11 + 8) = a2;
  *(_QWORD *)(v11 + 16) = a3;
  *(_DWORD *)(v11 + 24) = a4;
  *(_BYTE *)(v11 + 28) = a5;
  v12 = WinHvpSimplePoolHypercall_CallViaMacro(v14[0], 148);
  ((void (__fastcall *)(_QWORD))v14[7])(v14[0]);
  return v12;
}

```

## disassembly

```asm
0x140003370  push    rbp
0x140003372  push    rbx
0x140003373  push    rsi
0x140003374  push    rdi
0x140003375  push    r14
0x140003377  mov     rbp, rsp
0x14000337a  sub     rsp, 60h
0x14000337e  mov     rbx, rdx
0x140003381  mov     rsi, r8
0x140003384  xor     edx, edx; Val
0x140003386  mov     r14, rcx
0x140003389  lea     rcx, [rbp+var_40]; void *
0x14000338d  mov     edi, r9d
0x140003390  lea     r8d, [rdx+40h]; Size
0x140003394  call    memset
0x140003399  mov     eax, gs:1A4h
0x1400033a1  mov     edx, eax
0x1400033a3  mov     rax, cs:WinHvpProcessorToNode
0x1400033aa  mov     [rbp+var_18], 0
0x1400033b2  movzx   ecx, word ptr [rax+rdx*2]
0x1400033b6  mov     [rbp+var_20], cx
0x1400033ba  shl     rcx, 7
0x1400033be  add     rcx, cs:WinHvpNodeToHypercallLookaside; Lookaside
0x1400033c5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400033cc  nop     dword ptr [rax+rax+00h]
0x1400033d1  mov     [rbp+var_18], rax
0x1400033d5  lea     rcx, WinHvpReleasePoolBuffers
0x1400033dc  mov     [rbp+var_8], rcx
0x1400033e0  test    rax, rax
0x1400033e3  jz      short loc_140003445
0x1400033e5  mov     rcx, [rax+10h]
0x1400033e9  mov     edx, 94h
0x1400033ee  mov     [rbp+var_38], rcx
0x1400033f2  lea     rax, [rbp+var_40]
0x1400033f6  mov     [rbp+var_40], rax
0x1400033fa  xor     eax, eax
0x1400033fc  mov     [rbp+var_30], 0
0x140003404  mov     [rcx+1Dh], ax
0x140003408  mov     [rcx+1Fh], al
0x14000340b  mov     al, [rbp+arg_20]
0x14000340e  mov     [rcx], r14
0x140003411  mov     [rcx+8], rbx
0x140003415  mov     [rcx+10h], rsi
0x140003419  mov     [rcx+18h], edi
0x14000341c  mov     [rcx+1Ch], al
0x14000341f  mov     rcx, [rbp+var_40]
0x140003423  call    WinHvpSimplePoolHypercall_CallViaMacro
0x140003428  mov     rcx, [rbp+var_40]
0x14000342c  mov     ebx, eax
0x14000342e  mov     rax, [rbp+var_8]
0x140003432  call    _guard_dispatch_icall
0x140003437  mov     eax, ebx
0x140003439  add     rsp, 60h
0x14000343d  pop     r14
0x14000343f  pop     rdi
0x140003440  pop     rsi
0x140003441  pop     rbx
0x140003442  pop     rbp
0x140003443  retn
0x140003445  call    cs:__imp_KeGetCurrentIrql
0x14000344c  nop     dword ptr [rax+rax+00h]
0x140003451  mov     [rbp+var_10], al
0x140003454  cmp     al, 2
0x140003456  jnb     short loc_140003474
0x140003458  lea     rcx, WinHvpFallbackMutex; FastMutex
0x14000345f  call    cs:__imp_ExAcquireFastMutex
0x140003466  nop     dword ptr [rax+rax+00h]
0x14000346b  lea     rax, WinHvpFallbackBuffer2
0x140003472  jmp     short loc_140003491
0x140003474  lea     rcx, WinHvpFallbackSpinLock; SpinLock
0x14000347b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003482  nop     dword ptr [rax+rax+00h]
0x140003487  mov     [rbp+var_10], al
0x14000348a  lea     rax, WinHvpFallbackBuffer
0x140003491  lea     rcx, WinHvpReleaseFallbackBuffers
0x140003498  mov     [rbp+var_18], rax
0x14000349c  mov     [rbp+var_8], rcx
0x1400034a0  jmp     loc_1400033E5
```
