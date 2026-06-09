# VhdmpiInitializeSrbPartHandling

- ea: `0x140017450`
- end: `0x14001755b`
- name: `VhdmpiInitializeSrbPartHandling`
- size: `267`
- prototype: `__int64 __fastcall(struct _VHD_BACKING_STORE_HEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400e538c`

## callees

- `0x140017450`
- `0x140017564`
- `0x140026b08`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400174da`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140017517`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400174da`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140017517`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140017467`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140017467`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeSrbPartHandling(struct _VHD_BACKING_STORE_HEADER *a1, __int64 a2)
{
  __int16 v3; // ax
  int MainIoIrpContext; // edi

  LOBYTE(a2) = *((_BYTE *)a1 + 616);
  v3 = IoSizeOfIrpEx(-1, a2);
  *((_QWORD *)a1 + 186) = 0;
  *((_WORD *)a1 + 901) = v3;
  *((_DWORD *)a1 + 382) = 1;
  *((_QWORD *)a1 + 189) = VhdmpiExecuteSrbPartsWorkerRoutine;
  *((_QWORD *)a1 + 190) = (char *)a1 + 1496;
  *((_QWORD *)a1 + 187) = 0;
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)a1 + 12,
    0,
    0,
    0x200u,
    *(unsigned int *)(*(_QWORD *)a1 + 48LL) + 112LL,
    0x5A444856u,
    0);
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)a1 + 13,
    0,
    0,
    0x200u,
    *((unsigned __int16 *)a1 + 901) + 160LL,
    0x65444856u,
    0);
  *((_BYTE *)a1 + 1800) = 1;
  MainIoIrpContext = VhdmpiAllocateMainIoIrpContext(a1, 0, (struct VHD_SRB_PART_IRP_CONTEXT **)a1 + 224);
  if ( MainIoIrpContext >= 0 )
    return 0;
  else
    VhdmpiCleanupSrbPartHandling(a1);
  return (unsigned int)MainIoIrpContext;
}

```

## disassembly

```asm
0x140017450  mov     [rsp+arg_0], rbx
0x140017455  push    rdi
0x140017456  sub     rsp, 40h
0x14001745a  mov     dl, [rcx+268h]
0x140017460  mov     rbx, rcx
0x140017463  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140017467  call    cs:__imp_IoSizeOfIrpEx
0x14001746e  nop     dword ptr [rax+rax+00h]
0x140017473  mov     qword ptr [rbx+5D0h], 0
0x14001747e  lea     rcx, ?VhdmpiExecuteSrbPartsWorkerRoutine@@YAXPEAU_VHD_THREAD_POOL_WORK_ITEM@@@Z; VhdmpiExecuteSrbPartsWorkerRoutine(_VHD_THREAD_POOL_WORK_ITEM *)
0x140017485  mov     [rbx+70Ah], ax
0x14001748c  xor     edx, edx; Allocate
0x14001748e  lea     rax, [rbx+5D8h]
0x140017495  mov     [rsp+48h+Depth], dx; Depth
0x14001749a  mov     dword ptr [rax+20h], 1
0x1400174a1  mov     edi, 200h
0x1400174a6  mov     [rax+10h], rcx
0x1400174aa  mov     r9d, edi; Flags
0x1400174ad  mov     [rax+18h], rax
0x1400174b1  lea     rcx, [rbx+600h]; Lookaside
0x1400174b8  mov     qword ptr [rax], 0
0x1400174bf  mov     rax, [rbx]
0x1400174c2  mov     [rsp+48h+Tag], 5A444856h; Tag
0x1400174ca  mov     r8d, [rax+30h]
0x1400174ce  add     r8, 70h ; 'p'
0x1400174d2  mov     [rsp+48h+Size], r8; Size
0x1400174d7  xor     r8d, r8d; Free
0x1400174da  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400174e1  nop     dword ptr [rax+rax+00h]
0x1400174e6  movzx   edx, word ptr [rbx+70Ah]
0x1400174ed  lea     rcx, [rbx+680h]; Lookaside
0x1400174f4  add     rdx, 0A0h
0x1400174fb  xor     eax, eax
0x1400174fd  mov     [rsp+48h+Depth], ax; Depth
0x140017502  mov     r9d, edi; Flags
0x140017505  mov     [rsp+48h+Tag], 65444856h; Tag
0x14001750d  xor     r8d, r8d; Free
0x140017510  mov     [rsp+48h+Size], rdx; Size
0x140017515  xor     edx, edx; Allocate
0x140017517  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001751e  nop     dword ptr [rax+rax+00h]
0x140017523  lea     r8, [rbx+700h]; struct VHD_SRB_PART_IRP_CONTEXT **
0x14001752a  mov     byte ptr [rbx+708h], 1
0x140017531  xor     edx, edx; unsigned __int8
0x140017533  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x140017536  call    ?VhdmpiAllocateMainIoIrpContext@@YAJPEAU_VHD_BACKING_STORE_HEADER@@EPEAPEAUVHD_SRB_PART_IRP_CONTEXT@@@Z; VhdmpiAllocateMainIoIrpContext(_VHD_BACKING_STORE_HEADER *,uchar,VHD_SRB_PART_IRP_CONTEXT * *)
0x14001753b  mov     edi, eax
0x14001753d  test    eax, eax
0x14001753f  jns     short loc_140017557
0x140017541  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x140017544  call    VhdmpiCleanupSrbPartHandling
0x140017549  mov     rbx, [rsp+48h+arg_0]
0x14001754e  mov     eax, edi
0x140017550  add     rsp, 40h
0x140017554  pop     rdi
0x140017555  retn
0x140017557  xor     edi, edi
0x140017559  jmp     short loc_140017549
```
