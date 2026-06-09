# VmpQueryDiskSignature(_DEVICE_OBJECT *,ulong *)

- ea: `0x1400130b0`
- end: `0x140013132`
- name: `?VmpQueryDiskSignature@@YAJPEAU_DEVICE_OBJECT@@PEAK@Z`
- size: `130`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140010d7c`
- `0x140013ba0`
- `0x140013e00`

## callees

- `0x140002db0`
- `0x1400130b0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140013109`
- `ntoskrnl!ObfDereferenceObject` at `0x140013109`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400130d0`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400130d0`

## pseudocode

```c
__int64 __fastcall VmpQueryDiskSignature(struct _DEVICE_OBJECT *a1, unsigned int *a2)
{
  struct _DEVICE_OBJECT *AttachedDeviceReference; // rbx
  NTSTATUS v4; // edi
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  *a2 = 0;
  AttachedDeviceReference = IoGetAttachedDeviceReference(a1);
  v4 = VmpSendDeviceControl(AttachedDeviceReference, 0x704008u, 0, 0, &v6, 4u);
  ObfDereferenceObject(AttachedDeviceReference);
  if ( v4 >= 0 )
    *a2 = v6;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400130b0  mov     [rsp+arg_0], rbx
0x1400130b5  mov     [rsp+arg_10], rsi
0x1400130ba  push    rdi
0x1400130bb  sub     rsp, 30h
0x1400130bf  mov     rsi, rdx
0x1400130c2  mov     [rsp+38h+arg_8], 0
0x1400130ca  mov     dword ptr [rdx], 0
0x1400130d0  call    cs:__imp_IoGetAttachedDeviceReference
0x1400130d7  nop     dword ptr [rax+rax+00h]
0x1400130dc  mov     [rsp+38h+var_10], 4; ULONG
0x1400130e4  xor     r9d, r9d; InputBufferLength
0x1400130e7  mov     rbx, rax
0x1400130ea  xor     r8d, r8d; InputBuffer
0x1400130ed  lea     rax, [rsp+38h+arg_8]
0x1400130f2  mov     rcx, rbx; DeviceObject
0x1400130f5  mov     edx, 704008h; IoControlCode
0x1400130fa  mov     [rsp+38h+var_18], rax; PVOID
0x1400130ff  call    VmpSendDeviceControl
0x140013104  mov     rcx, rbx; Object
0x140013107  mov     edi, eax
0x140013109  call    cs:__imp_ObfDereferenceObject
0x140013110  nop     dword ptr [rax+rax+00h]
0x140013115  test    edi, edi
0x140013117  js      short loc_14001311F
0x140013119  mov     ecx, [rsp+38h+arg_8]
0x14001311d  mov     [rsi], ecx
0x14001311f  mov     rbx, [rsp+38h+arg_0]
0x140013124  mov     eax, edi
0x140013126  mov     rsi, [rsp+38h+arg_10]
0x14001312b  add     rsp, 30h
0x14001312f  pop     rdi
0x140013130  retn
```
