# PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)

- ea: `0x180001970`
- end: `0x1800019d5`
- name: `?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z`
- size: `101`
- prototype: `struct PROTOCOL_MANAGER_ENTRY *__fastcall(PROTOCOL_MANAGER_LIST *__hidden this, struct PROTOCOL_MANAGER_ENTRY *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001480`
- `0x180001890`
- `0x180005c9c`
- `0x180006cd8`
- `0x18000b1d0`

## callees

- `0x180001970`
- `0x1800019e0`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800019ab`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800019c2`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800019ab`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800019c2`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001980`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001980`

## pseudocode

```c
PROTOCOL_MANAGER_ENTRY **__fastcall PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(
        PROTOCOL_MANAGER_LIST *this,
        PROTOCOL_MANAGER_ENTRY **a2)
{
  PROTOCOL_MANAGER_ENTRY **v4; // rdx
  PROTOCOL_MANAGER_ENTRY **v5; // rax

  CReaderWriterLock3::ReadLock(this);
  v4 = (PROTOCOL_MANAGER_ENTRY **)((char *)this + 8);
  while ( 1 )
  {
    v5 = v4;
    if ( a2 )
      v5 = a2;
    a2 = (PROTOCOL_MANAGER_ENTRY **)*v5;
    if ( *v5 == (PROTOCOL_MANAGER_ENTRY *)v4 )
      break;
    if ( (unsigned int)PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(*v5) )
    {
      CReaderWriterLock3::ReadUnlock(this);
      return a2;
    }
  }
  CReaderWriterLock3::ReadUnlock(this);
  return 0;
}

```

## disassembly

```asm
0x180001970  mov     [rsp+arg_0], rbx
0x180001975  push    rdi
0x180001976  sub     rsp, 20h
0x18000197a  mov     rbx, rdx
0x18000197d  mov     rdi, rcx
0x180001980  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180001986  lea     rdx, [rdi+8]
0x18000198a  test    rbx, rbx
0x18000198d  mov     rax, rdx
0x180001990  cmovnz  rax, rbx
0x180001994  mov     rbx, [rax]
0x180001997  cmp     rbx, rdx
0x18000199a  jz      short loc_1800019BF
0x18000199c  mov     rcx, rbx; this
0x18000199f  call    ?IsFullyInitialized@PROTOCOL_MANAGER_ENTRY@@QEAAHXZ; PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(void)
0x1800019a4  test    eax, eax
0x1800019a6  jz      short loc_18000198A
0x1800019a8  mov     rcx, rdi
0x1800019ab  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800019b1  mov     rax, rbx
0x1800019b4  mov     rbx, [rsp+28h+arg_0]
0x1800019b9  add     rsp, 20h
0x1800019bd  pop     rdi
0x1800019be  retn
0x1800019bf  mov     rcx, rdi
0x1800019c2  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800019c8  mov     rbx, [rsp+28h+arg_0]
0x1800019cd  xor     eax, eax
0x1800019cf  add     rsp, 20h
0x1800019d3  pop     rdi
0x1800019d4  retn
```
