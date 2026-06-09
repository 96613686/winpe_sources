# PROTOCOL_MANAGER_LIST::CleanupList(void)

- ea: `0x180009548`
- end: `0x18000959f`
- name: `?CleanupList@PROTOCOL_MANAGER_LIST@@QEAAXXZ`
- size: `87`
- prototype: `void __fastcall(PROTOCOL_MANAGER_LIST *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002bfc`
- `0x180006cd8`

## callees

- `0x180009520`
- `0x180009548`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009598`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009555`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009555`

## pseudocode

```c
void __fastcall PROTOCOL_MANAGER_LIST::CleanupList(PROTOCOL_MANAGER_ENTRY **this)
{
  unsigned int v2; // edx
  PROTOCOL_MANAGER_ENTRY *v3; // rbx
  PROTOCOL_MANAGER_ENTRY *v4; // rcx
  PROTOCOL_MANAGER_ENTRY **v5; // rax

  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)this);
  v3 = (PROTOCOL_MANAGER_ENTRY *)(this + 1);
  while ( *(PROTOCOL_MANAGER_ENTRY **)v3 != v3 )
  {
    v4 = this[2];
    if ( *(PROTOCOL_MANAGER_ENTRY **)v4 != v3 || (v5 = (PROTOCOL_MANAGER_ENTRY **)*((_QWORD *)v4 + 1), *v5 != v4) )
      __fastfail(3u);
    this[2] = (PROTOCOL_MANAGER_ENTRY *)v5;
    *v5 = v3;
    PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(v4, v2);
  }
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)this);
}

```

## disassembly

```asm
0x180009548  mov     [rsp+arg_0], rbx
0x18000954d  push    rdi
0x18000954e  sub     rsp, 20h
0x180009552  mov     rdi, rcx
0x180009555  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000955b  lea     rbx, [rdi+8]
0x18000955f  cmp     [rbx], rbx
0x180009562  jz      short loc_18000958B
0x180009564  mov     rcx, [rbx+8]; this
0x180009568  cmp     [rcx], rbx
0x18000956b  jnz     short loc_180009584
0x18000956d  mov     rax, [rcx+8]
0x180009571  cmp     [rax], rcx
0x180009574  jnz     short loc_180009584
0x180009576  mov     [rbx+8], rax
0x18000957a  mov     [rax], rbx
0x18000957d  call    ??_GPROTOCOL_MANAGER_ENTRY@@QEAAPEAXI@Z; PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(uint)
0x180009582  jmp     short loc_18000955F
0x180009584  mov     ecx, 3
0x180009589  int     29h; Win8: RtlFailFast(ecx)
0x18000958b  mov     rcx, rdi
0x18000958e  mov     rbx, [rsp+28h+arg_0]
0x180009593  add     rsp, 20h
0x180009597  pop     rdi
0x180009598  jmp     cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
```
