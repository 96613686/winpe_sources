# VmsPdAllocatePdBatchPacket

- ea: `0x1401a43f4`
- end: `0x1401a44d6`
- name: `VmsPdAllocatePdBatchPacket`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401a77f4`

## callees

- `0x1401a43f4`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401a446d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401a446d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401a441d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401a4446`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401a441d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401a4446`
- `vmbkmclr!VmbPacketInitialize` at `0x1401a4499`
- `vmbkmclr!VmbPacketInitialize` at `0x1401a4499`
- `vmbkmclr!VmbPacketSetCompletionRoutineEx` at `0x1401a44b4`
- `vmbkmclr!VmbPacketSetCompletionRoutineEx` at `0x1401a44b4`

## pseudocode

```c
__int64 __fastcall VmsPdAllocatePdBatchPacket(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int v4; // ebx
  char *v7; // rsi
  PVOID v8; // rbp
  __int64 v9; // rcx

  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  v7 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 88) + 384LL));
  if ( v7 )
  {
    v8 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 88) + 256LL));
    if ( v8 )
    {
      v9 = *(unsigned int *)(a1 + 20);
      *(_OWORD *)&v7[v9] = 0;
      *(_QWORD *)&v7[v9 + 8] = *(_QWORD *)(a1 + 88);
      *(_QWORD *)&v7[v9] = v8;
      VmbPacketInitialize(*(_QWORD *)a1, v7, *(unsigned int *)(a1 + 20));
      VmbPacketSetCompletionRoutineEx(v7, 6, VmsVmNicChannelEvtPacketCompletionRoutine);
      *a2 = v7;
      *a3 = v8;
    }
    else
    {
      v4 = -1073741670;
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 88) + 384LL), v7);
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v4;
}

```

## disassembly

```asm
0x1401a43f4  push    rbx
0x1401a43f6  push    rbp
0x1401a43f7  push    rsi
0x1401a43f8  push    rdi
0x1401a43f9  push    r14
0x1401a43fb  push    r15
0x1401a43fd  sub     rsp, 28h
0x1401a4401  mov     rdi, rcx
0x1401a4404  xor     ebx, ebx
0x1401a4406  mov     [rdx], rbx
0x1401a4409  mov     r14, r8
0x1401a440c  mov     [r8], rbx
0x1401a440f  mov     r15, rdx
0x1401a4412  mov     rcx, [rcx+58h]
0x1401a4416  add     rcx, 180h; Lookaside
0x1401a441d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401a4424  nop     dword ptr [rax+rax+00h]
0x1401a4429  mov     rsi, rax
0x1401a442c  test    rax, rax
0x1401a442f  jnz     short loc_1401A443B
0x1401a4431  mov     ebx, 0C000009Ah
0x1401a4436  jmp     loc_1401A44C6
0x1401a443b  mov     rcx, [rdi+58h]
0x1401a443f  add     rcx, 100h; Lookaside
0x1401a4446  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401a444d  nop     dword ptr [rax+rax+00h]
0x1401a4452  mov     rbp, rax
0x1401a4455  mov     rdx, rsi; Entry
0x1401a4458  test    rax, rax
0x1401a445b  jnz     short loc_1401A447B
0x1401a445d  mov     rcx, [rdi+58h]
0x1401a4461  mov     ebx, 0C000009Ah
0x1401a4466  add     rcx, 180h; Lookaside
0x1401a446d  call    cs:__imp_ExFreeToNPagedLookasideList
0x1401a4474  nop     dword ptr [rax+rax+00h]
0x1401a4479  jmp     short loc_1401A44C6
0x1401a447b  mov     ecx, [rdi+14h]
0x1401a447e  xorps   xmm0, xmm0
0x1401a4481  movups  xmmword ptr [rcx+rsi], xmm0
0x1401a4485  mov     rax, [rdi+58h]
0x1401a4489  mov     [rcx+rsi+8], rax
0x1401a448e  mov     [rcx+rsi], rbp
0x1401a4492  mov     r8d, [rdi+14h]
0x1401a4496  mov     rcx, [rdi]
0x1401a4499  call    cs:__imp_VmbPacketInitialize
0x1401a44a0  nop     dword ptr [rax+rax+00h]
0x1401a44a5  lea     r8, VmsVmNicChannelEvtPacketCompletionRoutine
0x1401a44ac  mov     edx, 6
0x1401a44b1  mov     rcx, rsi
0x1401a44b4  call    cs:__imp_VmbPacketSetCompletionRoutineEx
0x1401a44bb  nop     dword ptr [rax+rax+00h]
0x1401a44c0  mov     [r15], rsi
0x1401a44c3  mov     [r14], rbp
0x1401a44c6  mov     eax, ebx
0x1401a44c8  add     rsp, 28h
0x1401a44cc  pop     r15
0x1401a44ce  pop     r14
0x1401a44d0  pop     rdi
0x1401a44d1  pop     rsi
0x1401a44d2  pop     rbp
0x1401a44d3  pop     rbx
0x1401a44d4  retn
```
