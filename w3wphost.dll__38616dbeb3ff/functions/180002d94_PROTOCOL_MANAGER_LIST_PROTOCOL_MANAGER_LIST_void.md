# PROTOCOL_MANAGER_LIST::~PROTOCOL_MANAGER_LIST(void)

- ea: `0x180002d94`
- end: `0x180002db6`
- name: `??1PROTOCOL_MANAGER_LIST@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(PROTOCOL_MANAGER_LIST *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002dbc`

## callees

- `0x180009ff0`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180002daa`

## pseudocode

```c
void __fastcall PROTOCOL_MANAGER_LIST::~PROTOCOL_MANAGER_LIST(PROTOCOL_MANAGER_ENTRY **this)
{
  PROTOCOL_MANAGER_LIST::CleanupList(this);
  CReaderWriterLock3::~CReaderWriterLock3((CReaderWriterLock3 *)this);
}

```

## disassembly

```asm
0x180002d94  push    rbx
0x180002d96  sub     rsp, 20h
0x180002d9a  mov     rbx, rcx
0x180002d9d  call    ?CleanupList@PROTOCOL_MANAGER_LIST@@QEAAXXZ; PROTOCOL_MANAGER_LIST::CleanupList(void)
0x180002da2  mov     rcx, rbx
0x180002da5  add     rsp, 20h
0x180002da9  pop     rbx
0x180002daa  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
