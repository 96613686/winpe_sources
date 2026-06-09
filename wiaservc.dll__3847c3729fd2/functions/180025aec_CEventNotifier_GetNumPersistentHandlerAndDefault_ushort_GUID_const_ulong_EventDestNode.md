# CEventNotifier::GetNumPersistentHandlerAndDefault(ushort *,_GUID const *,ulong *,__EventDestNode__ * *)

- ea: `0x180025aec`
- end: `0x180025e44`
- name: `?GetNumPersistentHandlerAndDefault@CEventNotifier@@QEAAJPEAGPEBU_GUID@@PEAKPEAPEAU__EventDestNode__@@@Z`
- size: `856`
- prototype: `int(CEventNotifier *__hidden this, unsigned __int16 *, const struct _GUID *, unsigned int *, struct __EventDestNode__ **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800315a0`
- `0x18003bea0`

## callees

- `0x180009474`
- `0x18000c7c0`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x180025aec`
- `0x180025e4c`
- `0x180033878`
- `0x180033cc0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180025cc2`
- `KERNEL32!CompareStringW` at `0x180025cc2`
- `KERNEL32!lstrcmpW` at `0x180025d68`
- `KERNEL32!lstrcmpW` at `0x180025d68`

## pseudocode

```c

```
