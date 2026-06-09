# VmpQueryMinimumShrinkSize(VM_VOLUME_EXTENSION *,_IRP *)

- ea: `0x1400131bc`
- end: `0x1400131e6`
- name: `?VmpQueryMinimumShrinkSize@@YAJPEAVVM_VOLUME_EXTENSION@@PEAU_IRP@@@Z`
- size: `42`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140001ae0`

## callees

- `0x1400131bc`

## pseudocode

```c
__int64 __fastcall VmpQueryMinimumShrinkSize(struct VM_VOLUME_EXTENSION *a1, struct _IRP *a2)
{
  __int64 result; // rax

  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length < 8 )
    return 3221225485LL;
  *(_QWORD *)a2->AssociatedIrp.MasterIrp = 0;
  result = 0;
  a2->IoStatus.Information = 8;
  return result;
}

```

## disassembly

```asm
0x1400131bc  mov     rax, [rdx+0B8h]
0x1400131c3  cmp     dword ptr [rax+8], 8
0x1400131c7  jnb     short loc_1400131D0
0x1400131c9  mov     eax, 0C000000Dh
0x1400131ce  retn
0x1400131d0  mov     rax, [rdx+18h]
0x1400131d4  mov     qword ptr [rax], 0
0x1400131db  xor     eax, eax
0x1400131dd  mov     qword ptr [rdx+38h], 8
0x1400131e5  retn
```
