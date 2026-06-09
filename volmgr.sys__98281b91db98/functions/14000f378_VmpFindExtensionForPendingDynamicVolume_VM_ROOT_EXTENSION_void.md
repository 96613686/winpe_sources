# VmpFindExtensionForPendingDynamicVolume(VM_ROOT_EXTENSION *,void *)

- ea: `0x14000f378`
- end: `0x14000f3a7`
- name: `?VmpFindExtensionForPendingDynamicVolume@@YAPEAVVM_VOLUME_EXTENSION@@PEAVVM_ROOT_EXTENSION@@PEAX@Z`
- size: `47`
- prototype: `struct VM_VOLUME_EXTENSION *__fastcall(struct VM_ROOT_EXTENSION *, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000eb40`
- `0x14000eba0`

## callees

- `0x14000f378`

## pseudocode

```c
struct VM_VOLUME_EXTENSION *__fastcall VmpFindExtensionForPendingDynamicVolume(struct VM_ROOT_EXTENSION *a1, void *a2)
{
  __int64 *i; // rax

  for ( i = (__int64 *)*((_QWORD *)a1 + 30); i != (__int64 *)((char *)a1 + 240); i = (__int64 *)*i )
  {
    if ( *((_BYTE *)i + 394) && (void *)i[50] == a2 )
      return (struct VM_VOLUME_EXTENSION *)(i - 4);
  }
  return 0;
}

```

## disassembly

```asm
0x14000f378  lea     r8, [rcx+0F0h]
0x14000f37f  mov     rax, [r8]
0x14000f382  cmp     rax, r8
0x14000f385  jz      short loc_14000F3A4
0x14000f387  cmp     byte ptr [rax+18Ah], 0
0x14000f38e  jz      short loc_14000F399
0x14000f390  cmp     [rax+190h], rdx
0x14000f397  jz      short loc_14000F39E
0x14000f399  mov     rax, [rax]
0x14000f39c  jmp     short loc_14000F382
0x14000f39e  add     rax, 0FFFFFFFFFFFFFFE0h
0x14000f3a2  retn
0x14000f3a4  xor     eax, eax
0x14000f3a6  retn
```
