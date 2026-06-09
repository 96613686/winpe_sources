# PROTOCOL_MANAGER_LIST::CleanupList(void)

- ea: `0x180009ff0`
- end: `0x18000a052`
- name: `?CleanupList@PROTOCOL_MANAGER_LIST@@QEAAXXZ`
- size: `98`
- prototype: `void __fastcall(PROTOCOL_MANAGER_LIST *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d94`
- `0x180007398`

## callees

- `0x180009fc8`
- `0x180009ff0`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000a046`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009ffd`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009ffd`

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
0x180009ff0  mov     [rsp+arg_0], rbx
0x180009ff5  push    rdi
0x180009ff6  sub     rsp, 20h
0x180009ffa  mov     rdi, rcx
0x180009ffd  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000a004  nop     dword ptr [rax+rax+00h]
0x18000a009  lea     rbx, [rdi+8]
0x18000a00d  cmp     [rbx], rbx
0x18000a010  jz      short loc_18000A039
0x18000a012  mov     rcx, [rbx+8]; this
0x18000a016  cmp     [rcx], rbx
0x18000a019  jnz     short loc_18000A032
0x18000a01b  mov     rax, [rcx+8]
0x18000a01f  cmp     [rax], rcx
0x18000a022  jnz     short loc_18000A032
0x18000a024  mov     [rbx+8], rax
0x18000a028  mov     [rax], rbx
0x18000a02b  call    ??_GPROTOCOL_MANAGER_ENTRY@@QEAAPEAXI@Z; PROTOCOL_MANAGER_ENTRY::`scalar deleting destructor'(uint)
0x18000a030  jmp     short loc_18000A00D
0x18000a032  mov     ecx, 3
0x18000a037  int     29h; Win8: RtlFailFast(ecx)
0x18000a039  mov     rcx, rdi
0x18000a03c  mov     rbx, [rsp+28h+arg_0]
0x18000a041  add     rsp, 20h
0x18000a045  pop     rdi
0x18000a046  jmp     cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
```
