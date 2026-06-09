# VmDeletePendingDynamicDevice(void *,void *)

- ea: `0x14000eb40`
- end: `0x14000eb95`
- name: `?VmDeletePendingDynamicDevice@@YAXPEAX0@Z`
- size: `85`
- prototype: `void __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000eb40`
- `0x14000f158`
- `0x14000f378`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000eb7b`
- `ntoskrnl!IoDeleteDevice` at `0x14000eb7b`

## pseudocode

```c
void __fastcall VmDeletePendingDynamicDevice(struct VM_ROOT_EXTENSION *a1, void *a2)
{
  struct VM_VOLUME_EXTENSION *ExtensionForPendingDynamicVolume; // rax
  struct VM_VOLUME_EXTENSION *v3; // rbx
  char *v4; // rcx
  __int64 v5; // rax
  char **v6; // rdx

  ExtensionForPendingDynamicVolume = VmpFindExtensionForPendingDynamicVolume(a1, a2);
  v3 = ExtensionForPendingDynamicVolume;
  if ( ExtensionForPendingDynamicVolume )
  {
    v4 = (char *)ExtensionForPendingDynamicVolume + 32;
    v5 = *((_QWORD *)ExtensionForPendingDynamicVolume + 4);
    if ( *(char **)(v5 + 8) != v4 || (v6 = (char **)*((_QWORD *)v4 + 1), *v6 != v4) )
      __fastfail(3u);
    *v6 = (char *)v5;
    *(_QWORD *)(v5 + 8) = v6;
    VmpCleanupVolumeExtension(v3);
    IoDeleteDevice(*(PDEVICE_OBJECT *)v3);
  }
}

```

## disassembly

```asm
0x14000eb40  push    rbx
0x14000eb42  sub     rsp, 20h
0x14000eb46  call    ?VmpFindExtensionForPendingDynamicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAVVM_ROOT_EXTENSION@@PEAX@Z; VmpFindExtensionForPendingDynamicVolume(VM_ROOT_EXTENSION *,void *)
0x14000eb4b  mov     rbx, rax
0x14000eb4e  test    rax, rax
0x14000eb51  jz      short loc_14000EB87
0x14000eb53  lea     rcx, [rax+20h]
0x14000eb57  mov     rax, [rcx]
0x14000eb5a  cmp     [rax+8], rcx
0x14000eb5e  jnz     short loc_14000EB8E
0x14000eb60  mov     rdx, [rcx+8]
0x14000eb64  cmp     [rdx], rcx
0x14000eb67  jnz     short loc_14000EB8E
0x14000eb69  mov     [rdx], rax
0x14000eb6c  mov     rcx, rbx; struct VM_VOLUME_EXTENSION *
0x14000eb6f  mov     [rax+8], rdx
0x14000eb73  call    ?VmpCleanupVolumeExtension@@YAXPEAVVM_VOLUME_EXTENSION@@@Z; VmpCleanupVolumeExtension(VM_VOLUME_EXTENSION *)
0x14000eb78  mov     rcx, [rbx]; DeviceObject
0x14000eb7b  call    cs:__imp_IoDeleteDevice
0x14000eb82  nop     dword ptr [rax+rax+00h]
0x14000eb87  add     rsp, 20h
0x14000eb8b  pop     rbx
0x14000eb8c  retn
0x14000eb8e  mov     ecx, 3
0x14000eb93  int     29h; Win8: RtlFailFast(ecx)
```
