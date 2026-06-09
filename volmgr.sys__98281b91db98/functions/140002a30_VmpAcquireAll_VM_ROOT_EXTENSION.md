# VmpAcquireAll(VM_ROOT_EXTENSION *)

- ea: `0x140002a30`
- end: `0x140002a99`
- name: `?VmpAcquireAll@@YAXPEAVVM_ROOT_EXTENSION@@@Z`
- size: `105`
- prototype: `void __fastcall(struct VM_ROOT_EXTENSION *)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ae0`
- `0x140002ba0`
- `0x140004b40`
- `0x14000f910`
- `0x140010814`
- `0x140011e00`
- `0x140012eac`
- `0x140014b30`
- `0x140014b80`
- `0x140014e90`
- `0x140016760`

## callees

- `0x140002a30`
- `0x14000e300`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002a50`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002a6d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002a50`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002a6d`

## pseudocode

```c
void __fastcall VmpAcquireAll(struct VM_ROOT_EXTENSION *a1)
{
  KeWaitForSingleObject((char *)a1 + 56, Executive, 0, 0, 0);
  KeWaitForSingleObject((char *)a1 + 112, Executive, 0, 0, 0);
  if ( *((struct VM_ROOT_EXTENSION **)a1 + 23) != (struct VM_ROOT_EXTENSION *)((char *)a1 + 184) )
    VmpProcessDiskNotifications(a1);
}

```

## disassembly

```asm
0x140002a30  mov     [rsp+arg_0], rbx
0x140002a35  push    rdi
0x140002a36  sub     rsp, 30h
0x140002a3a  mov     rbx, rcx
0x140002a3d  xor     edi, edi
0x140002a3f  add     rcx, 38h ; '8'; Object
0x140002a43  mov     [rsp+38h+Timeout], rdi; Timeout
0x140002a48  xor     r9d, r9d; Alertable
0x140002a4b  xor     r8d, r8d; WaitMode
0x140002a4e  xor     edx, edx; WaitReason
0x140002a50  call    cs:__imp_KeWaitForSingleObject
0x140002a57  nop     dword ptr [rax+rax+00h]
0x140002a5c  lea     rcx, [rbx+70h]; Object
0x140002a60  mov     [rsp+38h+Timeout], rdi; Timeout
0x140002a65  xor     r9d, r9d; Alertable
0x140002a68  xor     r8d, r8d; WaitMode
0x140002a6b  xor     edx, edx; WaitReason
0x140002a6d  call    cs:__imp_KeWaitForSingleObject
0x140002a74  nop     dword ptr [rax+rax+00h]
0x140002a79  lea     rax, [rbx+0B8h]
0x140002a80  cmp     [rax], rax
0x140002a83  jz      short loc_140002A8D
0x140002a85  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x140002a88  call    ?VmpProcessDiskNotifications@@YAXPEAVVM_ROOT_EXTENSION@@@Z; VmpProcessDiskNotifications(VM_ROOT_EXTENSION *)
0x140002a8d  mov     rbx, [rsp+38h+arg_0]
0x140002a92  add     rsp, 30h
0x140002a96  pop     rdi
0x140002a97  retn
```
