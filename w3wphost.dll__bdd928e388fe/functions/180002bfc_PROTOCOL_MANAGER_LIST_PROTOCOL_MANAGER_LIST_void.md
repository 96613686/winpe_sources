# PROTOCOL_MANAGER_LIST::~PROTOCOL_MANAGER_LIST(void)

- ea: `0x180002bfc`
- end: `0x180002c19`
- name: `??1PROTOCOL_MANAGER_LIST@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(PROTOCOL_MANAGER_LIST *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002c20`

## callees

- `0x180009548`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180002c12`

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
0x180002bfc  push    rbx
0x180002bfe  sub     rsp, 20h
0x180002c02  mov     rbx, rcx
0x180002c05  call    ?CleanupList@PROTOCOL_MANAGER_LIST@@QEAAXXZ; PROTOCOL_MANAGER_LIST::CleanupList(void)
0x180002c0a  mov     rcx, rbx
0x180002c0d  add     rsp, 20h
0x180002c11  pop     rbx
0x180002c12  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
