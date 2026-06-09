# VmpChangeOfflineCallback(VM_VOLUME_EXTENSION *,void *)

- ea: `0x140004010`
- end: `0x14000401f`
- name: `?VmpChangeOfflineCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall VmpChangeOfflineCallback(struct VM_VOLUME_EXTENSION *a1, void *a2)
{
  *((_BYTE *)a1 + 160) = a2 != 0;
  return 0;
}

```

## disassembly

```asm
0x140004010  test    rdx, rdx
0x140004013  setnz   al
0x140004016  mov     [rcx+0A0h], al
0x14000401c  xor     eax, eax
0x14000401e  retn
```
