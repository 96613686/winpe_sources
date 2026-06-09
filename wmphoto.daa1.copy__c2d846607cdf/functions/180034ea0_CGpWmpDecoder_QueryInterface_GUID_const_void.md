# CGpWmpDecoder::QueryInterface(_GUID const &,void * *)

- ea: `0x180034ea0`
- end: `0x180034ea5`
- name: `?QueryInterface@CGpWmpDecoder@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(CGpWmpDecoder *__hidden this, const struct _GUID *, void **)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038620`
- `0x180038630`
- `0x180039db0`
- `0x180039dd0`
- `0x180039df0`
- `0x180039e10`
- `0x180039e30`
- `0x180039e50`
- `0x180039e70`
- `0x18003abd0`
- `0x18003abf0`

## callees

- `0x180028920`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CGpWmpDecoder::QueryInterface(CGpWmpDecoder *this, const struct _GUID *a2, void **a3)
{
  return CWmpCOMBase::InternalQueryInterface(this, a2, a3);
}

```

## disassembly

```asm
0x180034ea0  jmp     ?InternalQueryInterface@CWmpCOMBase@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmpCOMBase::InternalQueryInterface(_GUID const &,void * *)
```
