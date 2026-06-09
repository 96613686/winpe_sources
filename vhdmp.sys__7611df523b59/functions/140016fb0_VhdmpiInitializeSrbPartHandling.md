# VhdmpiInitializeSrbPartHandling

- ea: `0x140016fb0`
- end: `0x1400170bb`
- name: `VhdmpiInitializeSrbPartHandling`
- size: `267`
- prototype: `__int64 __fastcall(struct _VHD_BACKING_STORE_HEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400e53fc`

## callees

- `0x140016fb0`
- `0x1400170c4`
- `0x1400266e8`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001703a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140017077`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001703a`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140017077`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140016fc7`
- `ntoskrnl!IoSizeOfIrpEx` at `0x140016fc7`

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
  MainIoIrpContext = VhdmpiAllocateMainIoIrpContext((struct _NPAGED_LOOKASIDE_LIST *)a1, 0, (ULONGLONG *)a1 + 224);
  if ( MainIoIrpContext >= 0 )
    return 0;
  else
    VhdmpiCleanupSrbPartHandling(a1);
  return (unsigned int)MainIoIrpContext;
}

```

## disassembly

```asm
0x140016fb0  mov     [rsp+arg_0], rbx
0x140016fb5  push    rdi
0x140016fb6  sub     rsp, 40h
0x140016fba  mov     dl, [rcx+268h]
0x140016fc0  mov     rbx, rcx
0x140016fc3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140016fc7  call    cs:__imp_IoSizeOfIrpEx
0x140016fce  nop     dword ptr [rax+rax+00h]
0x140016fd3  mov     qword ptr [rbx+5D0h], 0
0x140016fde  lea     rcx, ?VhdmpiExecuteSrbPartsWorkerRoutine@@YAXPEAU_VHD_THREAD_POOL_WORK_ITEM@@@Z; VhdmpiExecuteSrbPartsWorkerRoutine(_VHD_THREAD_POOL_WORK_ITEM *)
0x140016fe5  mov     [rbx+70Ah], ax
0x140016fec  xor     edx, edx; Allocate
0x140016fee  lea     rax, [rbx+5D8h]
0x140016ff5  mov     [rsp+48h+Depth], dx; Depth
0x140016ffa  mov     dword ptr [rax+20h], 1
0x140017001  mov     edi, 200h
0x140017006  mov     [rax+10h], rcx
0x14001700a  mov     r9d, edi; Flags
0x14001700d  mov     [rax+18h], rax
0x140017011  lea     rcx, [rbx+600h]; Lookaside
0x140017018  mov     qword ptr [rax], 0
0x14001701f  mov     rax, [rbx]
0x140017022  mov     [rsp+48h+Tag], 5A444856h; Tag
0x14001702a  mov     r8d, [rax+30h]
0x14001702e  add     r8, 70h ; 'p'
0x140017032  mov     [rsp+48h+Size], r8; Size
0x140017037  xor     r8d, r8d; Free
0x14001703a  call    cs:__imp_ExInitializeNPagedLookasideList
0x140017041  nop     dword ptr [rax+rax+00h]
0x140017046  movzx   edx, word ptr [rbx+70Ah]
0x14001704d  lea     rcx, [rbx+680h]; Lookaside
0x140017054  add     rdx, 0A0h
0x14001705b  xor     eax, eax
0x14001705d  mov     [rsp+48h+Depth], ax; Depth
0x140017062  mov     r9d, edi; Flags
0x140017065  mov     [rsp+48h+Tag], 65444856h; Tag
0x14001706d  xor     r8d, r8d; Free
0x140017070  mov     [rsp+48h+Size], rdx; Size
0x140017075  xor     edx, edx; Allocate
0x140017077  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001707e  nop     dword ptr [rax+rax+00h]
0x140017083  lea     r8, [rbx+700h]; struct VHD_SRB_PART_IRP_CONTEXT **
0x14001708a  mov     byte ptr [rbx+708h], 1
0x140017091  xor     edx, edx; unsigned __int8
0x140017093  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x140017096  call    ?VhdmpiAllocateMainIoIrpContext@@YAJPEAU_VHD_BACKING_STORE_HEADER@@EPEAPEAUVHD_SRB_PART_IRP_CONTEXT@@@Z; VhdmpiAllocateMainIoIrpContext(_VHD_BACKING_STORE_HEADER *,uchar,VHD_SRB_PART_IRP_CONTEXT * *)
0x14001709b  mov     edi, eax
0x14001709d  test    eax, eax
0x14001709f  jns     short loc_1400170B7
0x1400170a1  mov     rcx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400170a4  call    VhdmpiCleanupSrbPartHandling
0x1400170a9  mov     rbx, [rsp+48h+arg_0]
0x1400170ae  mov     eax, edi
0x1400170b0  add     rsp, 40h
0x1400170b4  pop     rdi
0x1400170b5  retn
0x1400170b7  xor     edi, edi
0x1400170b9  jmp     short loc_1400170A9
```
