# [thunk]:CRtfIFilter::GetClassID`adjustor{8}' (_GUID *)

- ea: `0x1800131d0`
- end: `0x1800131d9`
- name: `?GetClassID@CRtfIFilter@@W7EAAJPEAU_GUID@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800131b0`

## pseudocode

```c
__int64 __fastcall CRtfIFilter::GetClassID(__int64 a1, struct _GUID *a2)
{
  return CRtfIFilter::GetClassID((CRtfIFilter *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x1800131d0  sub     rcx, 8; this
0x1800131d4  jmp     ?GetClassID@CRtfIFilter@@UEAAJPEAU_GUID@@@Z; CRtfIFilter::GetClassID(_GUID *)
```
