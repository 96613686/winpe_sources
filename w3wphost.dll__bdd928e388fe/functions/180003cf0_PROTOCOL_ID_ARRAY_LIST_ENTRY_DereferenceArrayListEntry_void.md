# PROTOCOL_ID_ARRAY_LIST_ENTRY::DereferenceArrayListEntry(void)

- ea: `0x180003cf0`
- end: `0x180003d03`
- name: `?DereferenceArrayListEntry@PROTOCOL_ID_ARRAY_LIST_ENTRY@@UEAAXXZ`
- size: `19`
- prototype: `void __fastcall(PROTOCOL_ID_ARRAY_LIST_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002f84`
- `0x180003cf0`

## pseudocode

```c
void __fastcall PROTOCOL_ID_ARRAY_LIST_ENTRY::DereferenceArrayListEntry(PROTOCOL_ID_ARRAY_LIST_ENTRY *this)
{
  if ( this )
    PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(this);
}

```

## disassembly

```asm
0x180003cf0  sub     rsp, 28h
0x180003cf4  test    rcx, rcx
0x180003cf7  jz      short loc_180003CFE
0x180003cf9  call    ??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z; PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)
0x180003cfe  add     rsp, 28h
0x180003d02  retn
```
