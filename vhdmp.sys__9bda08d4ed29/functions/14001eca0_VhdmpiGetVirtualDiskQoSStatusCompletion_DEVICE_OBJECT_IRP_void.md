# VhdmpiGetVirtualDiskQoSStatusCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14001eca0`
- end: `0x14001ed21`
- name: `?VhdmpiGetVirtualDiskQoSStatusCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `129`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140026930`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14001ecff`
- `ntoskrnl!IoFreeIrp` at `0x14001ecff`
- `ntoskrnl!IofCompleteRequest` at `0x14001ecf0`
- `ntoskrnl!IofCompleteRequest` at `0x14001ecf0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001ecd1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001ecd1`

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
0x14001eca0  mov     [rsp+arg_0], rbx
0x14001eca5  mov     [rsp+arg_8], rsi
0x14001ecaa  push    rdi
0x14001ecab  sub     rsp, 20h
0x14001ecaf  mov     rcx, [r8+80h]
0x14001ecb6  mov     rsi, rdx
0x14001ecb9  mov     rbx, [r8+78h]
0x14001ecbd  mov     edx, 2
0x14001ecc2  mov     rdi, r8
0x14001ecc5  call    VhdmpiFileWrapperUnpinFile
0x14001ecca  lea     rcx, [rbx+108h]; RunRef
0x14001ecd1  call    cs:__imp_ExReleaseRundownProtection
0x14001ecd8  nop     dword ptr [rax+rax+00h]
0x14001ecdd  mov     eax, [rsi+30h]
0x14001ece0  xor     edx, edx; PriorityBoost
0x14001ece2  mov     [rdi+30h], eax
0x14001ece5  mov     rcx, rdi; Irp
0x14001ece8  mov     rax, [rsi+38h]
0x14001ecec  mov     [rdi+38h], rax
0x14001ecf0  call    cs:__imp_IofCompleteRequest
0x14001ecf7  nop     dword ptr [rax+rax+00h]
0x14001ecfc  mov     rcx, rsi; Irp
0x14001ecff  call    cs:__imp_IoFreeIrp
0x14001ed06  nop     dword ptr [rax+rax+00h]
0x14001ed0b  mov     rbx, [rsp+28h+arg_0]
0x14001ed10  mov     eax, 0C0000016h
0x14001ed15  mov     rsi, [rsp+28h+arg_8]
0x14001ed1a  add     rsp, 20h
0x14001ed1e  pop     rdi
0x14001ed1f  retn
```
