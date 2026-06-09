# CSubscriptionItem::Read(HKEY__ *,ushort const *,uchar *,ulong)

- ea: `0x1800161b4`
- end: `0x180016269`
- name: `?Read@CSubscriptionItem@@QEAAJPEAUHKEY__@@PEBGPEAEK@Z`
- size: `181`
- prototype: `int(CSubscriptionItem *__hidden this, HKEY, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180015748`
- `0x180015cb0`

## callees

- `0x1800161b4`
- `0x180019948`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180016251`
- `ADVAPI32!RegCloseKey` at `0x180016251`
- `ADVAPI32!RegQueryValueExW` at `0x18001622c`
- `ADVAPI32!RegQueryValueExW` at `0x18001622c`

## pseudocode

```c

```
