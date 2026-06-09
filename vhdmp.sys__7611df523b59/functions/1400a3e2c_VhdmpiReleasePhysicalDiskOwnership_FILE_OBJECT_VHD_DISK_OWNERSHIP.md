# VhdmpiReleasePhysicalDiskOwnership(_FILE_OBJECT *,VHD_DISK_OWNERSHIP *)

- ea: `0x1400a3e2c`
- end: `0x1400a3ecc`
- name: `?VhdmpiReleasePhysicalDiskOwnership@@YAXPEAU_FILE_OBJECT@@PEAUVHD_DISK_OWNERSHIP@@@Z`
- size: `160`
- prototype: `void __fastcall(struct _FILE_OBJECT *, struct VHD_DISK_OWNERSHIP *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400a1a6c`
- `0x1400a3ed4`

## callees

- `0x1400a3e2c`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400a3e47`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400a3e47`
- `ntoskrnl!IofCallDriver` at `0x1400a3e59`
- `ntoskrnl!IofCallDriver` at `0x1400a3e59`
- `ntoskrnl!IofCompleteRequest` at `0x1400a3e88`
- `ntoskrnl!IofCompleteRequest` at `0x1400a3e88`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a3ea9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a3ea9`

## pseudocode

```c
void __fastcall VhdmpiReleasePhysicalDiskOwnership(struct _FILE_OBJECT *a1, IRP **a2)
{
  IRP *v2; // rdi
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  IRP *v5; // rax

  v2 = *a2;
  if ( *a2 )
  {
    if ( *((_BYTE *)a2 + 88) )
    {
      RelatedDeviceObject = IoGetRelatedDeviceObject(a1);
      if ( IofCallDriver(RelatedDeviceObject, v2) != 259 )
      {
LABEL_7:
        *((_BYTE *)a2 + 88) = 0;
        *a2 = 0;
        return;
      }
    }
    else
    {
      v2->IoStatus.Status = 0;
      v5 = *a2;
      --v5->CurrentLocation;
      --v5->Tail.Overlay.CurrentStackLocation;
      IofCompleteRequest(*a2, 0);
    }
    KeWaitForSingleObject(a2 + 1, Executive, 0, 0, 0);
    goto LABEL_7;
  }
}

```

## disassembly

```asm
0x1400a3e2c  mov     [rsp+arg_0], rbx
0x1400a3e31  push    rdi
0x1400a3e32  sub     rsp, 30h
0x1400a3e36  mov     rdi, [rdx]
0x1400a3e39  mov     rbx, rdx
0x1400a3e3c  test    rdi, rdi
0x1400a3e3f  jz      short loc_1400A3EC0
0x1400a3e41  cmp     byte ptr [rdx+58h], 0
0x1400a3e45  jz      short loc_1400A3E6E
0x1400a3e47  call    cs:__imp_IoGetRelatedDeviceObject
0x1400a3e4e  nop     dword ptr [rax+rax+00h]
0x1400a3e53  mov     rcx, rax; DeviceObject
0x1400a3e56  mov     rdx, rdi; Irp
0x1400a3e59  call    cs:__imp_IofCallDriver
0x1400a3e60  nop     dword ptr [rax+rax+00h]
0x1400a3e65  cmp     eax, 103h
0x1400a3e6a  jnz     short loc_1400A3EB5
0x1400a3e6c  jmp     short loc_1400A3E94
0x1400a3e6e  mov     dword ptr [rdi+30h], 0
0x1400a3e75  mov     rax, [rdx]
0x1400a3e78  xor     edx, edx; PriorityBoost
0x1400a3e7a  dec     byte ptr [rax+43h]
0x1400a3e7d  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400a3e85  mov     rcx, [rbx]; Irp
0x1400a3e88  call    cs:__imp_IofCompleteRequest
0x1400a3e8f  nop     dword ptr [rax+rax+00h]
0x1400a3e94  lea     rcx, [rbx+8]; Object
0x1400a3e98  mov     [rsp+38h+Timeout], 0; Timeout
0x1400a3ea1  xor     r9d, r9d; Alertable
0x1400a3ea4  xor     r8d, r8d; WaitMode
0x1400a3ea7  xor     edx, edx; WaitReason
0x1400a3ea9  call    cs:__imp_KeWaitForSingleObject
0x1400a3eb0  nop     dword ptr [rax+rax+00h]
0x1400a3eb5  mov     byte ptr [rbx+58h], 0
0x1400a3eb9  mov     qword ptr [rbx], 0
0x1400a3ec0  mov     rbx, [rsp+38h+arg_0]
0x1400a3ec5  add     rsp, 30h
0x1400a3ec9  pop     rdi
0x1400a3eca  retn
```
