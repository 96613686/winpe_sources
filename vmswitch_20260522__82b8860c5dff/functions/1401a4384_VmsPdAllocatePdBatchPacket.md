# VmsPdAllocatePdBatchPacket

- ea: `0x1401a4384`
- end: `0x1401a4466`
- name: `VmsPdAllocatePdBatchPacket`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401a7784`

## callees

- `0x1401a4384`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401a43fd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401a43fd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401a43ad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401a43d6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401a43ad`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401a43d6`
- `vmbkmclr!VmbPacketInitialize` at `0x1401a4429`
- `vmbkmclr!VmbPacketInitialize` at `0x1401a4429`
- `vmbkmclr!VmbPacketSetCompletionRoutineEx` at `0x1401a4444`
- `vmbkmclr!VmbPacketSetCompletionRoutineEx` at `0x1401a4444`

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
0x1401a4384  push    rbx
0x1401a4386  push    rbp
0x1401a4387  push    rsi
0x1401a4388  push    rdi
0x1401a4389  push    r14
0x1401a438b  push    r15
0x1401a438d  sub     rsp, 28h
0x1401a4391  mov     rdi, rcx
0x1401a4394  xor     ebx, ebx
0x1401a4396  mov     [rdx], rbx
0x1401a4399  mov     r14, r8
0x1401a439c  mov     [r8], rbx
0x1401a439f  mov     r15, rdx
0x1401a43a2  mov     rcx, [rcx+58h]
0x1401a43a6  add     rcx, 180h; Lookaside
0x1401a43ad  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401a43b4  nop     dword ptr [rax+rax+00h]
0x1401a43b9  mov     rsi, rax
0x1401a43bc  test    rax, rax
0x1401a43bf  jnz     short loc_1401A43CB
0x1401a43c1  mov     ebx, 0C000009Ah
0x1401a43c6  jmp     loc_1401A4456
0x1401a43cb  mov     rcx, [rdi+58h]
0x1401a43cf  add     rcx, 100h; Lookaside
0x1401a43d6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401a43dd  nop     dword ptr [rax+rax+00h]
0x1401a43e2  mov     rbp, rax
0x1401a43e5  mov     rdx, rsi; Entry
0x1401a43e8  test    rax, rax
0x1401a43eb  jnz     short loc_1401A440B
0x1401a43ed  mov     rcx, [rdi+58h]
0x1401a43f1  mov     ebx, 0C000009Ah
0x1401a43f6  add     rcx, 180h; Lookaside
0x1401a43fd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1401a4404  nop     dword ptr [rax+rax+00h]
0x1401a4409  jmp     short loc_1401A4456
0x1401a440b  mov     ecx, [rdi+14h]
0x1401a440e  xorps   xmm0, xmm0
0x1401a4411  movups  xmmword ptr [rcx+rsi], xmm0
0x1401a4415  mov     rax, [rdi+58h]
0x1401a4419  mov     [rcx+rsi+8], rax
0x1401a441e  mov     [rcx+rsi], rbp
0x1401a4422  mov     r8d, [rdi+14h]
0x1401a4426  mov     rcx, [rdi]
0x1401a4429  call    cs:__imp_VmbPacketInitialize
0x1401a4430  nop     dword ptr [rax+rax+00h]
0x1401a4435  lea     r8, VmsVmNicChannelEvtPacketCompletionRoutine
0x1401a443c  mov     edx, 6
0x1401a4441  mov     rcx, rsi
0x1401a4444  call    cs:__imp_VmbPacketSetCompletionRoutineEx
0x1401a444b  nop     dword ptr [rax+rax+00h]
0x1401a4450  mov     [r15], rsi
0x1401a4453  mov     [r14], rbp
0x1401a4456  mov     eax, ebx
0x1401a4458  add     rsp, 28h
0x1401a445c  pop     r15
0x1401a445e  pop     r14
0x1401a4460  pop     rdi
0x1401a4461  pop     rsi
0x1401a4462  pop     rbp
0x1401a4463  pop     rbx
0x1401a4464  retn
```
