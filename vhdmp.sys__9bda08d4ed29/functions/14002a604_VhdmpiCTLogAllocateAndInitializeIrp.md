# VhdmpiCTLogAllocateAndInitializeIrp

- ea: `0x14002a604`
- end: `0x14002a76e`
- name: `VhdmpiCTLogAllocateAndInitializeIrp`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002cac4`
- `0x1400a7d94`

## callees

- `0x14002a604`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002a634`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002a634`
- `ntoskrnl!IoAllocateIrpEx` at `0x14002a67c`
- `ntoskrnl!IoAllocateIrpEx` at `0x14002a67c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002a749`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002a749`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002a64d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002a64d`

## pseudocode

```c
__int64 __fastcall VhdmpiCTLogAllocateAndInitializeIrp(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  struct _FILE_OBJECT *v13; // r14
  struct _NPAGED_LOOKASIDE_LIST *v14; // rdi
  PDEVICE_OBJECT RelatedDeviceObject; // rsi
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  __int64 v18; // rdx
  __int64 Irp; // r8
  int v20; // ecx
  unsigned int v21; // edx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx

  *a10 = 0;
  v13 = *(struct _FILE_OBJECT **)(a1 + 48);
  v14 = (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 4224);
  RelatedDeviceObject = IoGetRelatedDeviceObject(v13);
  v16 = ExAllocateFromNPagedLookasideList(v14);
  v17 = v16;
  if ( !v16 )
    return (unsigned int)-1073741670;
  memset(v16, 0, 0x40u);
  LOBYTE(v18) = RelatedDeviceObject->StackSize;
  Irp = IoAllocateIrpEx(RelatedDeviceObject, v18, 0);
  if ( !Irp )
  {
    ExFreeToNPagedLookasideList(v14, v17);
    return (unsigned int)-1073741670;
  }
  v20 = 256;
  v21 = 0;
  if ( a3 != 3 )
    v20 = 512;
  *(_DWORD *)(Irp + 16) |= *(_DWORD *)(a1 + 80) | v20;
  v22 = VhdmpLockBackingFileThread;
  *(_QWORD *)(Irp + 8) = a7;
  *(_QWORD *)(Irp + 152) = v22;
  v23 = *(_QWORD *)(Irp + 184);
  *(_BYTE *)(Irp + 64) = 0;
  *(_QWORD *)(Irp + 192) = v13;
  *(_QWORD *)(Irp + 112) = 0;
  *(_QWORD *)(v23 - 32) = RelatedDeviceObject;
  *(_QWORD *)(v23 - 24) = v13;
  *(_BYTE *)(v23 - 72) = a3;
  *(_QWORD *)(v23 - 48) = a4;
  *(_DWORD *)(v23 - 64) = a5;
  v17[3] = a8;
  v17[5] = a9;
  v17[1] = a1;
  v17[2] = Irp;
  *v17 = 0;
  v17[4] = RelatedDeviceObject;
  v24 = *(_QWORD *)(Irp + 184);
  *(_QWORD *)(v24 - 16) = a6;
  *(_QWORD *)(v24 - 8) = v17;
  *(_BYTE *)(v24 - 69) = -32;
  *a10 = v17;
  return v21;
}

```

## disassembly

```asm
0x14002a604  push    rbx
0x14002a606  push    rbp
0x14002a607  push    rsi
0x14002a608  push    rdi
0x14002a609  push    r12
0x14002a60b  push    r13
0x14002a60d  push    r14
0x14002a60f  push    r15
0x14002a611  sub     rsp, 28h
0x14002a615  mov     r15, [rsp+68h+arg_48]
0x14002a61d  mov     rbp, rcx
0x14002a620  mov     r13, r9
0x14002a623  mov     r12b, r8b
0x14002a626  mov     qword ptr [r15], 0
0x14002a62d  mov     r14, [rcx+30h]
0x14002a631  mov     rcx, r14; FileObject
0x14002a634  call    cs:__imp_IoGetRelatedDeviceObject
0x14002a63b  nop     dword ptr [rax+rax+00h]
0x14002a640  lea     rdi, [rbp+1080h]
0x14002a647  mov     rsi, rax
0x14002a64a  mov     rcx, rdi; Lookaside
0x14002a64d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14002a654  nop     dword ptr [rax+rax+00h]
0x14002a659  mov     rbx, rax
0x14002a65c  test    rax, rax
0x14002a65f  jz      loc_14002A755
0x14002a665  xor     edx, edx; Val
0x14002a667  mov     rcx, rax; void *
0x14002a66a  lea     r8d, [rdx+40h]; Size
0x14002a66e  call    memset
0x14002a673  mov     dl, [rsi+4Ch]
0x14002a676  xor     r8d, r8d
0x14002a679  mov     rcx, rsi
0x14002a67c  call    cs:__imp_IoAllocateIrpEx
0x14002a683  nop     dword ptr [rax+rax+00h]
0x14002a688  xor     r9d, r9d
0x14002a68b  mov     r8, rax
0x14002a68e  test    rax, rax
0x14002a691  jz      loc_14002A743
0x14002a697  cmp     r12b, 3
0x14002a69b  mov     ecx, 100h
0x14002a6a0  mov     eax, 200h
0x14002a6a5  mov     edx, r9d
0x14002a6a8  cmovnz  ecx, eax
0x14002a6ab  mov     rax, [rsp+68h+arg_30]
0x14002a6b3  or      ecx, [rbp+50h]
0x14002a6b6  or      [r8+10h], ecx
0x14002a6ba  mov     rcx, cs:VhdmpLockBackingFileThread
0x14002a6c1  mov     [r8+8], rax
0x14002a6c5  mov     eax, [rsp+68h+arg_20]
0x14002a6cc  mov     [r8+98h], rcx
0x14002a6d3  mov     rcx, [r8+0B8h]
0x14002a6da  mov     [r8+40h], r9b
0x14002a6de  mov     [r8+0C0h], r14
0x14002a6e5  mov     [r8+70h], r9
0x14002a6e9  mov     [rcx-20h], rsi
0x14002a6ed  mov     [rcx-18h], r14
0x14002a6f1  mov     [rcx-48h], r12b
0x14002a6f5  mov     [rcx-30h], r13
0x14002a6f9  mov     [rcx-40h], eax
0x14002a6fc  mov     rax, [rsp+68h+arg_38]
0x14002a704  mov     [rbx+18h], rax
0x14002a708  mov     rax, [rsp+68h+arg_40]
0x14002a710  mov     [rbx+28h], rax
0x14002a714  mov     rax, [rsp+68h+arg_28]
0x14002a71c  mov     [rbx+8], rbp
0x14002a720  mov     [rbx+10h], r8
0x14002a724  mov     [rbx], r9
0x14002a727  mov     [rbx+20h], rsi
0x14002a72b  mov     rcx, [r8+0B8h]
0x14002a732  mov     [rcx-10h], rax
0x14002a736  mov     [rcx-8], rbx
0x14002a73a  mov     byte ptr [rcx-45h], 0E0h
0x14002a73e  mov     [r15], rbx
0x14002a741  jmp     short loc_14002A75A
0x14002a743  mov     rdx, rbx; Entry
0x14002a746  mov     rcx, rdi; Lookaside
0x14002a749  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002a750  nop     dword ptr [rax+rax+00h]
0x14002a755  mov     edx, 0C000009Ah
0x14002a75a  mov     eax, edx
0x14002a75c  add     rsp, 28h
0x14002a760  pop     r15
0x14002a762  pop     r14
0x14002a764  pop     r13
0x14002a766  pop     r12
0x14002a768  pop     rdi
0x14002a769  pop     rsi
0x14002a76a  pop     rbp
0x14002a76b  pop     rbx
0x14002a76c  retn
```
