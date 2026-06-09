# VmpCleanupVolumeExtension(VM_VOLUME_EXTENSION *)

- ea: `0x14000f158`
- end: `0x14000f194`
- name: `?VmpCleanupVolumeExtension@@YAXPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `60`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000e888`
- `0x14000eb40`
- `0x14000eba0`
- `0x140016aa0`

## callees

- `0x140003ef0`
- `0x14000f158`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f16f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f16f`

## pseudocode

```c
void __fastcall VmpCleanupVolumeExtension(struct VM_VOLUME_EXTENSION *a1)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)a1 + 47);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( *((_BYTE *)a1 + 426) )
    VmpPageExtensionDriver(*((_QWORD *)a1 + 1));
}

```

## disassembly

```asm
0x14000f158  push    rbx
0x14000f15a  sub     rsp, 20h
0x14000f15e  mov     rbx, rcx
0x14000f161  mov     rcx, [rcx+178h]; P
0x14000f168  test    rcx, rcx
0x14000f16b  jz      short loc_14000F17B
0x14000f16d  xor     edx, edx; Tag
0x14000f16f  call    cs:__imp_ExFreePoolWithTag
0x14000f176  nop     dword ptr [rax+rax+00h]
0x14000f17b  cmp     byte ptr [rbx+1AAh], 0
0x14000f182  jz      short loc_14000F18D
0x14000f184  mov     rcx, [rbx+8]
0x14000f188  call    VmpPageExtensionDriver
0x14000f18d  add     rsp, 20h
0x14000f191  pop     rbx
0x14000f192  retn
```
