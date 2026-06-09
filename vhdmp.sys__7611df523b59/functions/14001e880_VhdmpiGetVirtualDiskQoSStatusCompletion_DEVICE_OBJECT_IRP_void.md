# VhdmpiGetVirtualDiskQoSStatusCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14001e880`
- end: `0x14001e901`
- name: `?VhdmpiGetVirtualDiskQoSStatusCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `129`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140026510`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001e8df`
- `ntoskrnl!IoFreeIrp` at `0x14001e8df`
- `ntoskrnl!IofCompleteRequest` at `0x14001e8d0`
- `ntoskrnl!IofCompleteRequest` at `0x14001e8d0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001e8b1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001e8b1`

## pseudocode

```c
__int64 __fastcall VhdmpiGetVirtualDiskQoSStatusCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, _QWORD *a3)
{
  struct _EX_RUNDOWN_REF *v4; // rbx

  v4 = (struct _EX_RUNDOWN_REF *)a3[15];
  VhdmpiFileWrapperUnpinFile(a3[16], 2);
  ExReleaseRundownProtection(v4 + 33);
  *((_DWORD *)a3 + 12) = a2->IoStatus.Status;
  a3[7] = a2->IoStatus.Information;
  IofCompleteRequest((PIRP)a3, 0);
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001e880  mov     [rsp+arg_0], rbx
0x14001e885  mov     [rsp+arg_8], rsi
0x14001e88a  push    rdi
0x14001e88b  sub     rsp, 20h
0x14001e88f  mov     rcx, [r8+80h]
0x14001e896  mov     rsi, rdx
0x14001e899  mov     rbx, [r8+78h]
0x14001e89d  mov     edx, 2
0x14001e8a2  mov     rdi, r8
0x14001e8a5  call    VhdmpiFileWrapperUnpinFile
0x14001e8aa  lea     rcx, [rbx+108h]; RunRef
0x14001e8b1  call    cs:__imp_ExReleaseRundownProtection
0x14001e8b8  nop     dword ptr [rax+rax+00h]
0x14001e8bd  mov     eax, [rsi+30h]
0x14001e8c0  xor     edx, edx; PriorityBoost
0x14001e8c2  mov     [rdi+30h], eax
0x14001e8c5  mov     rcx, rdi; Irp
0x14001e8c8  mov     rax, [rsi+38h]
0x14001e8cc  mov     [rdi+38h], rax
0x14001e8d0  call    cs:__imp_IofCompleteRequest
0x14001e8d7  nop     dword ptr [rax+rax+00h]
0x14001e8dc  mov     rcx, rsi; Irp
0x14001e8df  call    cs:__imp_IoFreeIrp
0x14001e8e6  nop     dword ptr [rax+rax+00h]
0x14001e8eb  mov     rbx, [rsp+28h+arg_0]
0x14001e8f0  mov     eax, 0C0000016h
0x14001e8f5  mov     rsi, [rsp+28h+arg_8]
0x14001e8fa  add     rsp, 20h
0x14001e8fe  pop     rdi
0x14001e8ff  retn
```
