# WfpAleGetAndWriteLockPartition

- ea: `0x14009f740`
- end: `0x14009f8d4`
- name: `WfpAleGetAndWriteLockPartition`
- size: `404`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400613e8`
- `0x140061630`
- `0x14009f300`
- `0x140153210`
- `0x1401561c0`

## callees

- `0x14009f740`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f7a2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f803`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f88d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f7a2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f803`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f88d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14009f76b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14009f856`
- `ntoskrnl!KeGetCurrentIrql` at `0x14009f76b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14009f856`
- `NDIS!NdisAcquireRWLockWrite` at `0x14009f784`
- `NDIS!NdisAcquireRWLockWrite` at `0x14009f86f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14009f784`
- `NDIS!NdisAcquireRWLockWrite` at `0x14009f86f`
- `NDIS!NdisReleaseRWLock` at `0x14009f832`
- `NDIS!NdisReleaseRWLock` at `0x14009f832`

## pseudocode

```c
__int64 __fastcall WfpAleGetAndWriteLockPartition(unsigned int a1, struct _LOCK_STATE_EX *a2)
{
  int v4; // ebp
  __int64 v5; // rbx
  __int64 v6; // rdi
  KIRQL CurrentIrql; // si
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // rbx
  _DWORD *v12; // rdx
  int v13; // ebp
  __int64 v14; // rdi
  KIRQL v15; // si
  __int64 v16; // r8

  v4 = *(_DWORD *)(pRemoteEndpointTable + 8);
  v5 = v4 & a1;
  v6 = pRemoteEndpointTable + (v5 << 7);
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v6 + 64), a2, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v8 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v8 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v8 = 4;
  }
  v9 = pRemoteEndpointTable;
  if ( v4 != *(_DWORD *)(pRemoteEndpointTable + 8) )
  {
    do
    {
      v11 = v9 + (v5 << 7);
      if ( gWfpPerProContext )
      {
        v12 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        if ( *v12 == 4 )
          *v12 = 0;
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v11 + 64), a2);
      v13 = *(_DWORD *)(pRemoteEndpointTable + 8);
      v5 = v13 & a1;
      v14 = pRemoteEndpointTable + (v5 << 7);
      v15 = KeGetCurrentIrql();
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(v14 + 64), a2, 0);
      if ( v15 != 2 && gWfpPerProContext )
      {
        v16 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        *(_QWORD *)(v16 + 8) = MEMORY[0xFFFFF78000000008];
        *(_DWORD *)v16 = 4;
      }
      v9 = pRemoteEndpointTable;
    }
    while ( v13 != *(_DWORD *)(pRemoteEndpointTable + 8) );
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14009f740  push    rbx
0x14009f742  push    rbp
0x14009f743  push    rsi
0x14009f744  push    rdi
0x14009f745  push    r14
0x14009f747  push    r15
0x14009f749  sub     rsp, 28h
0x14009f74d  mov     r8, cs:pRemoteEndpointTable
0x14009f754  mov     ebx, ecx
0x14009f756  mov     r14, rdx
0x14009f759  mov     r15, rcx
0x14009f75c  mov     ebp, [r8+8]
0x14009f760  and     ebx, ebp
0x14009f762  mov     edi, ebx
0x14009f764  shl     rdi, 7
0x14009f768  add     rdi, r8
0x14009f76b  call    cs:__imp_KeGetCurrentIrql
0x14009f772  nop     dword ptr [rax+rax+00h]
0x14009f777  mov     rcx, [rdi+40h]; Lock
0x14009f77b  xor     r8d, r8d; Flags
0x14009f77e  mov     rdx, r14; LockState
0x14009f781  movzx   esi, al
0x14009f784  call    cs:__imp_NdisAcquireRWLockWrite
0x14009f78b  nop     dword ptr [rax+rax+00h]
0x14009f790  cmp     sil, 2
0x14009f794  jz      short loc_14009F7D3
0x14009f796  cmp     cs:gWfpPerProContext, 0
0x14009f79e  jz      short loc_14009F7D3
0x14009f7a0  xor     ecx, ecx; ProcNumber
0x14009f7a2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009f7a9  nop     dword ptr [rax+rax+00h]
0x14009f7ae  lea     ecx, [rax+rax*8]
0x14009f7b1  mov     rax, cs:gWfpPerProContext
0x14009f7b8  shl     ecx, 3
0x14009f7bb  mov     rcx, [rcx+rax]
0x14009f7bf  mov     rax, ds:0FFFFF78000000008h
0x14009f7c9  mov     [rcx+8], rax
0x14009f7cd  mov     dword ptr [rcx], 4
0x14009f7d3  mov     rcx, cs:pRemoteEndpointTable
0x14009f7da  cmp     ebp, [rcx+8]
0x14009f7dd  jnz     short loc_14009F7F0
0x14009f7df  mov     eax, ebx
0x14009f7e1  add     rsp, 28h
0x14009f7e5  pop     r15
0x14009f7e7  pop     r14
0x14009f7e9  pop     rdi
0x14009f7ea  pop     rsi
0x14009f7eb  pop     rbp
0x14009f7ec  pop     rbx
0x14009f7ed  retn
0x14009f7f0  shl     rbx, 7
0x14009f7f4  add     rbx, rcx
0x14009f7f7  cmp     cs:gWfpPerProContext, 0
0x14009f7ff  jz      short loc_14009F82B
0x14009f801  xor     ecx, ecx; ProcNumber
0x14009f803  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009f80a  nop     dword ptr [rax+rax+00h]
0x14009f80f  lea     edx, [rax+rax*8]
0x14009f812  mov     rax, cs:gWfpPerProContext
0x14009f819  shl     edx, 3
0x14009f81c  mov     rdx, [rdx+rax]
0x14009f820  cmp     dword ptr [rdx], 4
0x14009f823  jnz     short loc_14009F82B
0x14009f825  mov     dword ptr [rdx], 0
0x14009f82b  mov     rcx, [rbx+40h]; Lock
0x14009f82f  mov     rdx, r14; LockState
0x14009f832  call    cs:__imp_NdisReleaseRWLock
0x14009f839  nop     dword ptr [rax+rax+00h]
0x14009f83e  mov     rcx, cs:pRemoteEndpointTable
0x14009f845  mov     ebx, r15d
0x14009f848  mov     ebp, [rcx+8]
0x14009f84b  and     ebx, ebp
0x14009f84d  mov     edi, ebx
0x14009f84f  shl     rdi, 7
0x14009f853  add     rdi, rcx
0x14009f856  call    cs:__imp_KeGetCurrentIrql
0x14009f85d  nop     dword ptr [rax+rax+00h]
0x14009f862  mov     rcx, [rdi+40h]; Lock
0x14009f866  xor     r8d, r8d; Flags
0x14009f869  mov     rdx, r14; LockState
0x14009f86c  movzx   esi, al
0x14009f86f  call    cs:__imp_NdisAcquireRWLockWrite
0x14009f876  nop     dword ptr [rax+rax+00h]
0x14009f87b  cmp     sil, 2
0x14009f87f  jz      short loc_14009F8BF
0x14009f881  cmp     cs:gWfpPerProContext, 0
0x14009f889  jz      short loc_14009F8BF
0x14009f88b  xor     ecx, ecx; ProcNumber
0x14009f88d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009f894  nop     dword ptr [rax+rax+00h]
0x14009f899  mov     rcx, cs:gWfpPerProContext
0x14009f8a0  lea     edx, [rax+rax*8]
0x14009f8a3  mov     rax, ds:0FFFFF78000000008h
0x14009f8ad  shl     edx, 3
0x14009f8b0  mov     r8, [rdx+rcx]
0x14009f8b4  mov     [r8+8], rax
0x14009f8b8  mov     dword ptr [r8], 4
0x14009f8bf  mov     rcx, cs:pRemoteEndpointTable
0x14009f8c6  cmp     ebp, [rcx+8]
0x14009f8c9  jz      loc_14009F7DF
0x14009f8cf  jmp     loc_14009F7F0
```
