# VhdmpiSetZeroDataProjectCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140041660`
- end: `0x1400416df`
- name: `?VhdmpiSetZeroDataProjectCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `127`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140041660`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140041694`
- `ntoskrnl!IoFreeIrp` at `0x140041694`
- `ntoskrnl!IofCompleteRequest` at `0x1400416c4`
- `ntoskrnl!IofCompleteRequest` at `0x1400416c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041685`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041685`

## pseudocode

```c
__int64 __fastcall VhdmpiSetZeroDataProjectCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, unsigned int *a3)
{
  NTSTATUS Status; // ebp
  __int64 v4; // rdi
  __int64 v7; // rax

  Status = a2->IoStatus.Status;
  v4 = 0;
  if ( Status >= 0 )
    v4 = a3[23];
  ExFreePoolWithTag(a2->AssociatedIrp.MasterIrp, 0x66444856u);
  IoFreeIrp(a2);
  *(_DWORD *)(*((_QWORD *)a3 + 2) + 48LL) = Status;
  *(_QWORD *)(*((_QWORD *)a3 + 2) + 56LL) = v4;
  v7 = *((_QWORD *)a3 + 2);
  --*(_BYTE *)(v7 + 67);
  *(_QWORD *)(v7 + 184) -= 72LL;
  IofCompleteRequest(*((PIRP *)a3 + 2), 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140041660  push    rbx
0x140041662  push    rbp
0x140041663  push    rsi
0x140041664  push    rdi
0x140041665  sub     rsp, 28h
0x140041669  mov     ebp, [rdx+30h]
0x14004166c  xor     edi, edi
0x14004166e  mov     rbx, r8
0x140041671  mov     rsi, rdx
0x140041674  test    ebp, ebp
0x140041676  js      short loc_14004167C
0x140041678  mov     edi, [r8+5Ch]
0x14004167c  mov     rcx, [rsi+18h]; P
0x140041680  mov     edx, 66444856h; Tag
0x140041685  call    cs:__imp_ExFreePoolWithTag
0x14004168c  nop     dword ptr [rax+rax+00h]
0x140041691  mov     rcx, rsi; Irp
0x140041694  call    cs:__imp_IoFreeIrp
0x14004169b  nop     dword ptr [rax+rax+00h]
0x1400416a0  mov     rax, [rbx+10h]
0x1400416a4  xor     edx, edx; PriorityBoost
0x1400416a6  mov     [rax+30h], ebp
0x1400416a9  mov     rax, [rbx+10h]
0x1400416ad  mov     [rax+38h], rdi
0x1400416b1  mov     rax, [rbx+10h]
0x1400416b5  dec     byte ptr [rax+43h]
0x1400416b8  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400416c0  mov     rcx, [rbx+10h]; Irp
0x1400416c4  call    cs:__imp_IofCompleteRequest
0x1400416cb  nop     dword ptr [rax+rax+00h]
0x1400416d0  mov     eax, 0C0000016h
0x1400416d5  add     rsp, 28h
0x1400416d9  pop     rdi
0x1400416da  pop     rsi
0x1400416db  pop     rbp
0x1400416dc  pop     rbx
0x1400416dd  retn
```
