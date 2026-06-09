# CGpWmpDecoder::QueryInterface(_GUID const &,void * *)

- ea: `0x180035470`
- end: `0x180035475`
- name: `?QueryInterface@CGpWmpDecoder@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(CGpWmpDecoder *__hidden this, const struct _GUID *, void **)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180038c70`
- `0x180038c80`
- `0x18003a4e0`
- `0x18003a500`
- `0x18003a520`
- `0x18003a540`
- `0x18003a560`
- `0x18003a580`
- `0x18003a5a0`
- `0x18003b380`
- `0x18003b3a0`

## callees

- `0x180028ec0`

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
0x180035470  jmp     ?InternalQueryInterface@CWmpCOMBase@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWmpCOMBase::InternalQueryInterface(_GUID const &,void * *)
```
