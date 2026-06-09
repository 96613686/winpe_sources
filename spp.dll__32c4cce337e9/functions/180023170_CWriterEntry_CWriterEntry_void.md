# CWriterEntry::~CWriterEntry(void)

- ea: `0x180023170`
- end: `0x1800231af`
- name: `??1CWriterEntry@@AEAA@XZ`
- size: `63`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e54c`

## callees

- `0x180023170`
- `0x1800236b8`
- `0x180035b00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002317d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002317d`

## pseudocode

```c
void __fastcall CWriterEntry::~CWriterEntry(LPVOID *this)
{
  CComponentEntryArray *v2; // rcx

  CoTaskMemFree(this[3]);
  this[3] = 0;
  v2 = (CComponentEntryArray *)this[8];
  if ( v2 )
  {
    this[8] = 0;
    CComponentEntryArray::Release(v2);
  }
  CBsString::_Release((CBsString *)(this + 1));
}

```

## disassembly

```asm
0x180023170  push    rbx
0x180023172  sub     rsp, 20h
0x180023176  mov     rbx, rcx
0x180023179  mov     rcx, [rcx+18h]; pv
0x18002317d  call    cs:__imp_CoTaskMemFree
0x180023183  mov     qword ptr [rbx+18h], 0
0x18002318b  mov     rcx, [rbx+40h]; this
0x18002318f  test    rcx, rcx
0x180023192  jz      short loc_1800231A1
0x180023194  mov     qword ptr [rbx+40h], 0
0x18002319c  call    ?Release@CComponentEntryArray@@QEAAKXZ; CComponentEntryArray::Release(void)
0x1800231a1  lea     rcx, [rbx+8]; this
0x1800231a5  add     rsp, 20h
0x1800231a9  pop     rbx
0x1800231aa  jmp     ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
```
