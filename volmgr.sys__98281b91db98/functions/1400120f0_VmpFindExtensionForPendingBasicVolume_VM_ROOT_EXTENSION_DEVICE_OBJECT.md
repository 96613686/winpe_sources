# VmpFindExtensionForPendingBasicVolume(VM_ROOT_EXTENSION *,_DEVICE_OBJECT *)

- ea: `0x1400120f0`
- end: `0x14001211f`
- name: `?VmpFindExtensionForPendingBasicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAVVM_ROOT_EXTENSION@@PEAU_DEVICE_OBJECT@@@Z`
- size: `47`
- prototype: `struct VM_VOLUME_EXTENSION *__fastcall(struct VM_ROOT_EXTENSION *, struct _DEVICE_OBJECT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000e888`
- `0x14000eba0`

## callees

- `0x1400120f0`

## pseudocode

```c
struct VM_VOLUME_EXTENSION *__fastcall VmpFindExtensionForPendingBasicVolume(
        struct VM_ROOT_EXTENSION *a1,
        struct _DEVICE_OBJECT *a2)
{
  __int64 *i; // rax

  for ( i = (__int64 *)*((_QWORD *)a1 + 32); i != (__int64 *)((char *)a1 + 256); i = (__int64 *)*i )
  {
    if ( !*((_BYTE *)i + 394) && (struct _DEVICE_OBJECT *)i[39] == a2 )
      return (struct VM_VOLUME_EXTENSION *)(i - 4);
  }
  return 0;
}

```

## disassembly

```asm
0x1400120f0  lea     r8, [rcx+100h]
0x1400120f7  mov     rax, [r8]
0x1400120fa  cmp     rax, r8
0x1400120fd  jz      short loc_14001211C
0x1400120ff  cmp     byte ptr [rax+18Ah], 0
0x140012106  jnz     short loc_140012111
0x140012108  cmp     [rax+138h], rdx
0x14001210f  jz      short loc_140012116
0x140012111  mov     rax, [rax]
0x140012114  jmp     short loc_1400120FA
0x140012116  add     rax, 0FFFFFFFFFFFFFFE0h
0x14001211a  retn
0x14001211c  xor     eax, eax
0x14001211e  retn
```
