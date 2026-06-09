# VhdmpiInitializeAeFile

- ea: `0x1400265b4`
- end: `0x140026699`
- name: `VhdmpiInitializeAeFile`
- size: `229`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14004c81c`
- `0x1400c4490`
- `0x1400c5f88`
- `0x1400e81c0`

## callees

- `0x1400265b4`
- `0x140040e20`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002661b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14002661b`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140026666`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140026666`
- `ntoskrnl!IoSizeOfIrpEx` at `0x1400265e0`
- `ntoskrnl!IoSizeOfIrpEx` at `0x1400265e0`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeAeFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // ebx
  unsigned __int16 v6; // ax
  PVOID MappingAddress; // rax

  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = a3;
  v5 = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 32) = a4;
  LOBYTE(a2) = *(_BYTE *)(a2 + 544);
  v6 = IoSizeOfIrpEx(-1, a2);
  *(_WORD *)(a1 + 24) = v6;
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 64), 0, 0, 0x200u, v6 + 224LL, 0x6F694541u, 0);
  *(_BYTE *)(a1 + 192) = 1;
  *(_QWORD *)(a1 + 200) = 0;
  *(_DWORD *)(a1 + 248) = 1;
  *(_QWORD *)(a1 + 232) = VhdmpiAeRetryQueueWorkerRoutine;
  *(_QWORD *)(a1 + 240) = a1 + 216;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  MappingAddress = MmAllocateMappingAddress(0x1000u, 0x76724541u);
  *(_QWORD *)(a1 + 256) = MappingAddress;
  if ( !MappingAddress )
  {
    v5 = -1073741670;
    VhdmpiUninitializeAeFile(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x1400265b4  mov     [rsp+arg_0], rbx
0x1400265b9  push    rdi
0x1400265ba  sub     rsp, 40h
0x1400265be  mov     [rcx+8], rdx
0x1400265c2  mov     rdi, rcx
0x1400265c5  mov     [rcx+10h], r8
0x1400265c9  xor     ebx, ebx
0x1400265cb  mov     [rcx+100h], rbx
0x1400265d2  mov     [rcx+20h], r9
0x1400265d6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400265da  mov     dl, [rdx+220h]
0x1400265e0  call    cs:__imp_IoSizeOfIrpEx
0x1400265e7  nop     dword ptr [rax+rax+00h]
0x1400265ec  mov     [rsp+48h+Depth], bx; Depth
0x1400265f1  lea     rcx, [rdi+40h]; Lookaside
0x1400265f5  movzx   edx, ax
0x1400265f8  mov     r9d, 200h; Flags
0x1400265fe  mov     [rdi+18h], dx
0x140026602  xor     r8d, r8d; Free
0x140026605  add     rdx, 0E0h
0x14002660c  mov     [rsp+48h+Tag], 6F694541h; Tag
0x140026614  mov     [rsp+48h+Size], rdx; Size
0x140026619  xor     edx, edx; Allocate
0x14002661b  call    cs:__imp_ExInitializeNPagedLookasideList
0x140026622  nop     dword ptr [rax+rax+00h]
0x140026627  lea     rax, [rdi+0D8h]
0x14002662e  mov     byte ptr [rdi+0C0h], 1
0x140026635  mov     [rdi+0C8h], rbx
0x14002663c  lea     rcx, ?VhdmpiAeRetryQueueWorkerRoutine@@YAXPEAU_VHD_THREAD_POOL_WORK_ITEM@@@Z; VhdmpiAeRetryQueueWorkerRoutine(_VHD_THREAD_POOL_WORK_ITEM *)
0x140026643  mov     dword ptr [rax+20h], 1
0x14002664a  mov     edx, 76724541h; PoolTag
0x14002664f  mov     [rax+10h], rcx
0x140026653  mov     ecx, 1000h; NumberOfBytes
0x140026658  mov     [rax+18h], rax
0x14002665c  mov     [rax], rbx
0x14002665f  mov     [rdi+0D0h], rbx
0x140026666  call    cs:__imp_MmAllocateMappingAddress
0x14002666d  nop     dword ptr [rax+rax+00h]
0x140026672  mov     [rdi+100h], rax
0x140026679  test    rax, rax
0x14002667c  jnz     short loc_14002668B
0x14002667e  mov     rcx, rdi
0x140026681  mov     ebx, 0C000009Ah
0x140026686  call    VhdmpiUninitializeAeFile
0x14002668b  mov     eax, ebx
0x14002668d  mov     rbx, [rsp+48h+arg_0]
0x140026692  add     rsp, 40h
0x140026696  pop     rdi
0x140026697  retn
```
