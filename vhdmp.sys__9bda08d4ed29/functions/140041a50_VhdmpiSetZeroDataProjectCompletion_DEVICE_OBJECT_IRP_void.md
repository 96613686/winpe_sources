# VhdmpiSetZeroDataProjectCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140041a50`
- end: `0x140041acf`
- name: `?VhdmpiSetZeroDataProjectCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `127`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140041a50`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140041a84`
- `ntoskrnl!IoFreeIrp` at `0x140041a84`
- `ntoskrnl!IofCompleteRequest` at `0x140041ab4`
- `ntoskrnl!IofCompleteRequest` at `0x140041ab4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041a75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041a75`

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
0x140041a50  push    rbx
0x140041a52  push    rbp
0x140041a53  push    rsi
0x140041a54  push    rdi
0x140041a55  sub     rsp, 28h
0x140041a59  mov     ebp, [rdx+30h]
0x140041a5c  xor     edi, edi
0x140041a5e  mov     rbx, r8
0x140041a61  mov     rsi, rdx
0x140041a64  test    ebp, ebp
0x140041a66  js      short loc_140041A6C
0x140041a68  mov     edi, [r8+5Ch]
0x140041a6c  mov     rcx, [rsi+18h]; P
0x140041a70  mov     edx, 66444856h; Tag
0x140041a75  call    cs:__imp_ExFreePoolWithTag
0x140041a7c  nop     dword ptr [rax+rax+00h]
0x140041a81  mov     rcx, rsi; Irp
0x140041a84  call    cs:__imp_IoFreeIrp
0x140041a8b  nop     dword ptr [rax+rax+00h]
0x140041a90  mov     rax, [rbx+10h]
0x140041a94  xor     edx, edx; PriorityBoost
0x140041a96  mov     [rax+30h], ebp
0x140041a99  mov     rax, [rbx+10h]
0x140041a9d  mov     [rax+38h], rdi
0x140041aa1  mov     rax, [rbx+10h]
0x140041aa5  dec     byte ptr [rax+43h]
0x140041aa8  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140041ab0  mov     rcx, [rbx+10h]; Irp
0x140041ab4  call    cs:__imp_IofCompleteRequest
0x140041abb  nop     dword ptr [rax+rax+00h]
0x140041ac0  mov     eax, 0C0000016h
0x140041ac5  add     rsp, 28h
0x140041ac9  pop     rdi
0x140041aca  pop     rsi
0x140041acb  pop     rbp
0x140041acc  pop     rbx
0x140041acd  retn
```
