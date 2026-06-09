# VmpSetAttributesCallback(VM_VOLUME_EXTENSION *,void *)

- ea: `0x1400044a0`
- end: `0x1400044ad`
- name: `?VmpSetAttributesCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z`
- size: `13`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall VmpSetAttributesCallback(struct VM_VOLUME_EXTENSION *a1, _QWORD *a2)
{
  *((_QWORD *)a1 + 39) = *a2;
  return 0;
}

```

## disassembly

```asm
0x1400044a0  mov     rax, [rdx]
0x1400044a3  mov     [rcx+138h], rax
0x1400044aa  xor     eax, eax
0x1400044ac  retn
```
