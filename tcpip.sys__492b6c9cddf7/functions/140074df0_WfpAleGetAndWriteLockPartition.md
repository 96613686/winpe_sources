# WfpAleGetAndWriteLockPartition

- ea: `0x140074df0`
- end: `0x140074f84`
- name: `WfpAleGetAndWriteLockPartition`
- size: `404`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400749b0`
- `0x1400751f0`
- `0x1400ac8bc`
- `0x140151324`
- `0x1401541a0`

## callees

- `0x140074df0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074e52`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074eb3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074f3d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074e52`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074eb3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074f3d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140074e1b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140074f06`
- `ntoskrnl!KeGetCurrentIrql` at `0x140074e1b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140074f06`
- `NDIS!NdisAcquireRWLockWrite` at `0x140074e34`
- `NDIS!NdisAcquireRWLockWrite` at `0x140074f1f`
- `NDIS!NdisAcquireRWLockWrite` at `0x140074e34`
- `NDIS!NdisAcquireRWLockWrite` at `0x140074f1f`
- `NDIS!NdisReleaseRWLock` at `0x140074ee2`
- `NDIS!NdisReleaseRWLock` at `0x140074ee2`

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
0x140074df0  push    rbx
0x140074df2  push    rbp
0x140074df3  push    rsi
0x140074df4  push    rdi
0x140074df5  push    r14
0x140074df7  push    r15
0x140074df9  sub     rsp, 28h
0x140074dfd  mov     r8, cs:pRemoteEndpointTable
0x140074e04  mov     ebx, ecx
0x140074e06  mov     r14, rdx
0x140074e09  mov     r15, rcx
0x140074e0c  mov     ebp, [r8+8]
0x140074e10  and     ebx, ebp
0x140074e12  mov     edi, ebx
0x140074e14  shl     rdi, 7
0x140074e18  add     rdi, r8
0x140074e1b  call    cs:__imp_KeGetCurrentIrql
0x140074e22  nop     dword ptr [rax+rax+00h]
0x140074e27  mov     rcx, [rdi+40h]; Lock
0x140074e2b  xor     r8d, r8d; Flags
0x140074e2e  mov     rdx, r14; LockState
0x140074e31  movzx   esi, al
0x140074e34  call    cs:__imp_NdisAcquireRWLockWrite
0x140074e3b  nop     dword ptr [rax+rax+00h]
0x140074e40  cmp     sil, 2
0x140074e44  jz      short loc_140074E83
0x140074e46  cmp     cs:gWfpPerProContext, 0
0x140074e4e  jz      short loc_140074E83
0x140074e50  xor     ecx, ecx; ProcNumber
0x140074e52  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140074e59  nop     dword ptr [rax+rax+00h]
0x140074e5e  lea     ecx, [rax+rax*8]
0x140074e61  mov     rax, cs:gWfpPerProContext
0x140074e68  shl     ecx, 3
0x140074e6b  mov     rcx, [rcx+rax]
0x140074e6f  mov     rax, ds:0FFFFF78000000008h
0x140074e79  mov     [rcx+8], rax
0x140074e7d  mov     dword ptr [rcx], 4
0x140074e83  mov     rcx, cs:pRemoteEndpointTable
0x140074e8a  cmp     ebp, [rcx+8]
0x140074e8d  jnz     short loc_140074EA0
0x140074e8f  mov     eax, ebx
0x140074e91  add     rsp, 28h
0x140074e95  pop     r15
0x140074e97  pop     r14
0x140074e99  pop     rdi
0x140074e9a  pop     rsi
0x140074e9b  pop     rbp
0x140074e9c  pop     rbx
0x140074e9d  retn
0x140074ea0  shl     rbx, 7
0x140074ea4  add     rbx, rcx
0x140074ea7  cmp     cs:gWfpPerProContext, 0
0x140074eaf  jz      short loc_140074EDB
0x140074eb1  xor     ecx, ecx; ProcNumber
0x140074eb3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140074eba  nop     dword ptr [rax+rax+00h]
0x140074ebf  lea     edx, [rax+rax*8]
0x140074ec2  mov     rax, cs:gWfpPerProContext
0x140074ec9  shl     edx, 3
0x140074ecc  mov     rdx, [rdx+rax]
0x140074ed0  cmp     dword ptr [rdx], 4
0x140074ed3  jnz     short loc_140074EDB
0x140074ed5  mov     dword ptr [rdx], 0
0x140074edb  mov     rcx, [rbx+40h]; Lock
0x140074edf  mov     rdx, r14; LockState
0x140074ee2  call    cs:__imp_NdisReleaseRWLock
0x140074ee9  nop     dword ptr [rax+rax+00h]
0x140074eee  mov     rcx, cs:pRemoteEndpointTable
0x140074ef5  mov     ebx, r15d
0x140074ef8  mov     ebp, [rcx+8]
0x140074efb  and     ebx, ebp
0x140074efd  mov     edi, ebx
0x140074eff  shl     rdi, 7
0x140074f03  add     rdi, rcx
0x140074f06  call    cs:__imp_KeGetCurrentIrql
0x140074f0d  nop     dword ptr [rax+rax+00h]
0x140074f12  mov     rcx, [rdi+40h]; Lock
0x140074f16  xor     r8d, r8d; Flags
0x140074f19  mov     rdx, r14; LockState
0x140074f1c  movzx   esi, al
0x140074f1f  call    cs:__imp_NdisAcquireRWLockWrite
0x140074f26  nop     dword ptr [rax+rax+00h]
0x140074f2b  cmp     sil, 2
0x140074f2f  jz      short loc_140074F6F
0x140074f31  cmp     cs:gWfpPerProContext, 0
0x140074f39  jz      short loc_140074F6F
0x140074f3b  xor     ecx, ecx; ProcNumber
0x140074f3d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140074f44  nop     dword ptr [rax+rax+00h]
0x140074f49  mov     rcx, cs:gWfpPerProContext
0x140074f50  lea     edx, [rax+rax*8]
0x140074f53  mov     rax, ds:0FFFFF78000000008h
0x140074f5d  shl     edx, 3
0x140074f60  mov     r8, [rdx+rcx]
0x140074f64  mov     [r8+8], rax
0x140074f68  mov     dword ptr [r8], 4
0x140074f6f  mov     rcx, cs:pRemoteEndpointTable
0x140074f76  cmp     ebp, [rcx+8]
0x140074f79  jz      loc_140074E8F
0x140074f7f  jmp     loc_140074EA0
```
