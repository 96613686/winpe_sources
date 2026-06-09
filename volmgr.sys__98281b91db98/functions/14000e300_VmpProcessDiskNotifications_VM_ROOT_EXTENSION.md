# VmpProcessDiskNotifications(VM_ROOT_EXTENSION *)

- ea: `0x14000e300`
- end: `0x14000e3f5`
- name: `?VmpProcessDiskNotifications@@YAXPEAVVM_ROOT_EXTENSION@@@Z`
- size: `245`
- prototype: `void __fastcall(struct VM_ROOT_EXTENSION *)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x140001ae0`
- `0x1400029e0`
- `0x140002a30`
- `0x140012b3c`
- `0x14001462c`
- `0x140014838`

## callees

- `0x140003f7c`
- `0x14000e300`
- `0x140012964`
- `0x140012cf4`
- `0x1400147dc`
- `0x1400149e8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000e37b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e3a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e3c4`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e37b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e3a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e3c4`

## pseudocode

```c
void __fastcall VmpProcessDiskNotifications(struct VM_ROOT_EXTENSION *a1)
{
  void **v2; // rbx
  void *v3; // rdi
  void **v4; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  void *v8; // rcx

  v2 = (void **)((char *)a1 + 184);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( *((void ***)v3 + 1) != v2 || (v4 = *(void ***)v3, *(void **)(*(_QWORD *)v3 + 8LL) != v3) )
      __fastfail(3u);
    *v2 = v4;
    v4[1] = v2;
    v5 = *((_DWORD *)v3 + 4);
    if ( !v5 )
    {
      VmpWholeDiskArrivedDelayed(a1, *((struct _DEVICE_OBJECT **)v3 + 3));
      goto LABEL_14;
    }
    v6 = v5 - 1;
    if ( !v6 )
    {
      VmpPartitionArrivedDelayed(a1, *((struct _DEVICE_OBJECT **)v3 + 3), *((struct _DEVICE_OBJECT **)v3 + 4));
      ObfDereferenceObject(*((PVOID *)v3 + 4));
LABEL_14:
      v8 = (void *)*((_QWORD *)v3 + 3);
LABEL_15:
      ObfDereferenceObject(v8);
      goto LABEL_16;
    }
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
        goto LABEL_16;
      VmpWholeDiskRemovedDelayed(a1, *((struct _DEVICE_OBJECT **)v3 + 3));
      goto LABEL_14;
    }
    VmpPartitionRemovedDelayed(a1, *((struct _DEVICE_OBJECT **)v3 + 3), *((struct _DEVICE_OBJECT **)v3 + 4));
    ObfDereferenceObject(*((PVOID *)v3 + 4));
    v8 = (void *)*((_QWORD *)v3 + 3);
    if ( v8 )
      goto LABEL_15;
LABEL_16:
    VM_ALLOCATED_OBJECT::operator delete(v3);
  }
}

```

## disassembly

```asm
0x14000e300  mov     [rsp+arg_0], rbx
0x14000e305  mov     [rsp+arg_8], rsi
0x14000e30a  push    rdi
0x14000e30b  sub     rsp, 20h
0x14000e30f  mov     rsi, rcx
0x14000e312  lea     rbx, [rcx+0B8h]
0x14000e319  mov     rdi, [rbx]
0x14000e31c  cmp     rdi, rbx
0x14000e31f  jz      loc_14000E3E4
0x14000e325  cmp     [rdi+8], rbx
0x14000e329  jnz     loc_14000E3DD
0x14000e32f  mov     rax, [rdi]
0x14000e332  cmp     [rax+8], rdi
0x14000e336  jnz     loc_14000E3DD
0x14000e33c  mov     [rbx], rax
0x14000e33f  mov     [rax+8], rbx
0x14000e343  mov     ecx, [rdi+10h]
0x14000e346  test    ecx, ecx
0x14000e348  jz      short loc_14000E3B4
0x14000e34a  sub     ecx, 1
0x14000e34d  jz      short loc_14000E392
0x14000e34f  sub     ecx, 1
0x14000e352  jz      short loc_14000E367
0x14000e354  cmp     ecx, 1
0x14000e357  jnz     short loc_14000E3D0
0x14000e359  mov     rdx, [rdi+18h]; struct _DEVICE_OBJECT *
0x14000e35d  mov     rcx, rsi; struct VM_ROOT_EXTENSION *
0x14000e360  call    ?VmpWholeDiskRemovedDelayed@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; VmpWholeDiskRemovedDelayed(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *)
0x14000e365  jmp     short loc_14000E3C0
0x14000e367  mov     r8, [rdi+20h]; struct _DEVICE_OBJECT *
0x14000e36b  mov     rcx, rsi; struct VM_ROOT_EXTENSION *
0x14000e36e  mov     rdx, [rdi+18h]; struct _DEVICE_OBJECT *
0x14000e372  call    ?VmpPartitionRemovedDelayed@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@1@Z; VmpPartitionRemovedDelayed(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)
0x14000e377  mov     rcx, [rdi+20h]; Object
0x14000e37b  call    cs:__imp_ObfDereferenceObject
0x14000e382  nop     dword ptr [rax+rax+00h]
0x14000e387  mov     rcx, [rdi+18h]
0x14000e38b  test    rcx, rcx
0x14000e38e  jnz     short loc_14000E3C4
0x14000e390  jmp     short loc_14000E3D0
0x14000e392  mov     r8, [rdi+20h]; struct _DEVICE_OBJECT *
0x14000e396  mov     rcx, rsi; struct VM_ROOT_EXTENSION *
0x14000e399  mov     rdx, [rdi+18h]; struct _DEVICE_OBJECT *
0x14000e39d  call    ?VmpPartitionArrivedDelayed@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@1@Z; VmpPartitionArrivedDelayed(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *)
0x14000e3a2  mov     rcx, [rdi+20h]; Object
0x14000e3a6  call    cs:__imp_ObfDereferenceObject
0x14000e3ad  nop     dword ptr [rax+rax+00h]
0x14000e3b2  jmp     short loc_14000E3C0
0x14000e3b4  mov     rdx, [rdi+18h]; struct _DEVICE_OBJECT *
0x14000e3b8  mov     rcx, rsi; struct VM_ROOT_EXTENSION *
0x14000e3bb  call    ?VmpWholeDiskArrivedDelayed@@YAJPEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z; VmpWholeDiskArrivedDelayed(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *)
0x14000e3c0  mov     rcx, [rdi+18h]; Object
0x14000e3c4  call    cs:__imp_ObfDereferenceObject
0x14000e3cb  nop     dword ptr [rax+rax+00h]
0x14000e3d0  mov     rcx, rdi; void *
0x14000e3d3  call    ??3VM_ALLOCATED_OBJECT@@SAXPEAX@Z; VM_ALLOCATED_OBJECT::operator delete(void *)
0x14000e3d8  jmp     loc_14000E319
0x14000e3dd  mov     ecx, 3
0x14000e3e2  int     29h; Win8: RtlFailFast(ecx)
0x14000e3e4  mov     rbx, [rsp+28h+arg_0]
0x14000e3e9  mov     rsi, [rsp+28h+arg_8]
0x14000e3ee  add     rsp, 20h
0x14000e3f2  pop     rdi
0x14000e3f3  retn
```
