# VhdmpiInitializeAeFile

- ea: `0x140026194`
- end: `0x140026279`
- name: `VhdmpiInitializeAeFile`
- size: `229`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14004c42c`
- `0x1400c44a0`
- `0x1400c5f98`
- `0x1400e8230`

## callees

- `0x140026194`
- `0x140040a30`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400261fb`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400261fb`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140026246`
- `ntoskrnl!MmAllocateMappingAddress` at `0x140026246`
- `ntoskrnl!IoSizeOfIrpEx` at `0x1400261c0`
- `ntoskrnl!IoSizeOfIrpEx` at `0x1400261c0`

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
0x140026194  mov     [rsp+arg_0], rbx
0x140026199  push    rdi
0x14002619a  sub     rsp, 40h
0x14002619e  mov     [rcx+8], rdx
0x1400261a2  mov     rdi, rcx
0x1400261a5  mov     [rcx+10h], r8
0x1400261a9  xor     ebx, ebx
0x1400261ab  mov     [rcx+100h], rbx
0x1400261b2  mov     [rcx+20h], r9
0x1400261b6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400261ba  mov     dl, [rdx+220h]
0x1400261c0  call    cs:__imp_IoSizeOfIrpEx
0x1400261c7  nop     dword ptr [rax+rax+00h]
0x1400261cc  mov     [rsp+48h+Depth], bx; Depth
0x1400261d1  lea     rcx, [rdi+40h]; Lookaside
0x1400261d5  movzx   edx, ax
0x1400261d8  mov     r9d, 200h; Flags
0x1400261de  mov     [rdi+18h], dx
0x1400261e2  xor     r8d, r8d; Free
0x1400261e5  add     rdx, 0E0h
0x1400261ec  mov     [rsp+48h+Tag], 6F694541h; Tag
0x1400261f4  mov     [rsp+48h+Size], rdx; Size
0x1400261f9  xor     edx, edx; Allocate
0x1400261fb  call    cs:__imp_ExInitializeNPagedLookasideList
0x140026202  nop     dword ptr [rax+rax+00h]
0x140026207  lea     rax, [rdi+0D8h]
0x14002620e  mov     byte ptr [rdi+0C0h], 1
0x140026215  mov     [rdi+0C8h], rbx
0x14002621c  lea     rcx, ?VhdmpiAeRetryQueueWorkerRoutine@@YAXPEAU_VHD_THREAD_POOL_WORK_ITEM@@@Z; VhdmpiAeRetryQueueWorkerRoutine(_VHD_THREAD_POOL_WORK_ITEM *)
0x140026223  mov     dword ptr [rax+20h], 1
0x14002622a  mov     edx, 76724541h; PoolTag
0x14002622f  mov     [rax+10h], rcx
0x140026233  mov     ecx, 1000h; NumberOfBytes
0x140026238  mov     [rax+18h], rax
0x14002623c  mov     [rax], rbx
0x14002623f  mov     [rdi+0D0h], rbx
0x140026246  call    cs:__imp_MmAllocateMappingAddress
0x14002624d  nop     dword ptr [rax+rax+00h]
0x140026252  mov     [rdi+100h], rax
0x140026259  test    rax, rax
0x14002625c  jnz     short loc_14002626B
0x14002625e  mov     rcx, rdi
0x140026261  mov     ebx, 0C000009Ah
0x140026266  call    VhdmpiUninitializeAeFile
0x14002626b  mov     eax, ebx
0x14002626d  mov     rbx, [rsp+48h+arg_0]
0x140026272  add     rsp, 40h
0x140026276  pop     rdi
0x140026277  retn
```
