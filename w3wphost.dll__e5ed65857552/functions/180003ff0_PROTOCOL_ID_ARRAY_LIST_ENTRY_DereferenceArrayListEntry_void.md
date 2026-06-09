# PROTOCOL_ID_ARRAY_LIST_ENTRY::DereferenceArrayListEntry(void)

- ea: `0x180003ff0`
- end: `0x180004004`
- name: `?DereferenceArrayListEntry@PROTOCOL_ID_ARRAY_LIST_ENTRY@@UEAAXXZ`
- size: `20`
- prototype: `void __fastcall(PROTOCOL_ID_ARRAY_LIST_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000315c`
- `0x180003ff0`

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
0x180003ff0  sub     rsp, 28h
0x180003ff4  test    rcx, rcx
0x180003ff7  jz      short loc_180003FFE
0x180003ff9  call    ??_GPROTOCOL_ID_ARRAY_LIST_ENTRY@@QEAAPEAXI@Z; PROTOCOL_ID_ARRAY_LIST_ENTRY::`scalar deleting destructor'(uint)
0x180003ffe  add     rsp, 28h
0x180004002  retn
```
