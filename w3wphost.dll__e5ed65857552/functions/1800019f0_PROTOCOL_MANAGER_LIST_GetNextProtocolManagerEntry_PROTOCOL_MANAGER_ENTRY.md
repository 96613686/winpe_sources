# PROTOCOL_MANAGER_LIST::GetNextProtocolManagerEntry(PROTOCOL_MANAGER_ENTRY *)

- ea: `0x1800019f0`
- end: `0x180001a69`
- name: `?GetNextProtocolManagerEntry@PROTOCOL_MANAGER_LIST@@QEAAPEAVPROTOCOL_MANAGER_ENTRY@@PEAV2@@Z`
- size: `121`
- prototype: `struct PROTOCOL_MANAGER_ENTRY *__fastcall(PROTOCOL_MANAGER_LIST *__hidden this, struct PROTOCOL_MANAGER_ENTRY *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800014a0`
- `0x180001900`
- `0x18000620c`
- `0x180007398`
- `0x18000bfa0`

## callees

- `0x1800019f0`
- `0x180001a70`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001a31`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001a4f`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001a31`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001a4f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001a00`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001a00`

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
0x1800019f0  mov     [rsp+arg_0], rbx
0x1800019f5  push    rdi
0x1800019f6  sub     rsp, 20h
0x1800019fa  mov     rbx, rdx
0x1800019fd  mov     rdi, rcx
0x180001a00  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180001a07  nop     dword ptr [rax+rax+00h]
0x180001a0c  lea     rdx, [rdi+8]
0x180001a10  test    rbx, rbx
0x180001a13  mov     rax, rdx
0x180001a16  cmovnz  rax, rbx
0x180001a1a  mov     rbx, [rax]
0x180001a1d  cmp     rbx, rdx
0x180001a20  jz      short loc_180001A4C
0x180001a22  mov     rcx, rbx; this
0x180001a25  call    ?IsFullyInitialized@PROTOCOL_MANAGER_ENTRY@@QEAAHXZ; PROTOCOL_MANAGER_ENTRY::IsFullyInitialized(void)
0x180001a2a  test    eax, eax
0x180001a2c  jz      short loc_180001A10
0x180001a2e  mov     rcx, rdi
0x180001a31  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180001a38  nop     dword ptr [rax+rax+00h]
0x180001a3d  mov     rax, rbx
0x180001a40  mov     rbx, [rsp+28h+arg_0]
0x180001a45  add     rsp, 20h
0x180001a49  pop     rdi
0x180001a4a  retn
0x180001a4c  mov     rcx, rdi
0x180001a4f  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180001a56  nop     dword ptr [rax+rax+00h]
0x180001a5b  mov     rbx, [rsp+28h+arg_0]
0x180001a60  xor     eax, eax
0x180001a62  add     rsp, 20h
0x180001a66  pop     rdi
0x180001a67  retn
```
