# PRELOAD_MANAGER::Terminate(void)

- ea: `0x18000c0a8`
- end: `0x18000c12b`
- name: `?Terminate@PRELOAD_MANAGER@@QEAAJXZ`
- size: `131`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006cd8`

## callees

- `0x18000d010`

## import_xrefs

- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000c10e`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000c10e`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c118`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c118`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c0cc`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c0cc`

## pseudocode

```c
__int64 __fastcall PRELOAD_MANAGER::Terminate(PRELOAD_MANAGER *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  (*(void (__fastcall **)(_QWORD, PRELOAD_MANAGER *))(**((_QWORD **)this + 6) + 48LL))(*((_QWORD *)this + 6), this);
  CReaderWriterLock3::WriteLock((PRELOAD_MANAGER *)((char *)this + 16));
  v2 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 5) = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  v3 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 4) = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  *((_QWORD *)this + 6) = 0;
  CLKRHashTable::Clear((PRELOAD_MANAGER *)((char *)this + 72));
  CReaderWriterLock3::WriteUnlock((PRELOAD_MANAGER *)((char *)this + 16));
  return 0;
}

```

## disassembly

```asm
0x18000c0a8  mov     [rsp+arg_0], rbx
0x18000c0ad  push    rdi
0x18000c0ae  sub     rsp, 20h
0x18000c0b2  mov     rdi, rcx
0x18000c0b5  mov     rcx, [rcx+30h]
0x18000c0b9  mov     rdx, rdi
0x18000c0bc  mov     rax, [rcx]
0x18000c0bf  mov     rax, [rax+30h]
0x18000c0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0c8  lea     rcx, [rdi+10h]
0x18000c0cc  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c0d2  mov     rcx, [rdi+20h]
0x18000c0d6  mov     qword ptr [rdi+28h], 0
0x18000c0de  mov     rax, [rcx]
0x18000c0e1  mov     rax, [rax+8]
0x18000c0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ea  mov     rcx, [rdi+30h]
0x18000c0ee  mov     qword ptr [rdi+20h], 0
0x18000c0f6  mov     rax, [rcx]
0x18000c0f9  mov     rax, [rax+10h]
0x18000c0fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c102  lea     rcx, [rdi+48h]
0x18000c106  mov     qword ptr [rdi+30h], 0
0x18000c10e  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18000c114  lea     rcx, [rdi+10h]
0x18000c118  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c11e  mov     rbx, [rsp+28h+arg_0]
0x18000c123  xor     eax, eax
0x18000c125  add     rsp, 20h
0x18000c129  pop     rdi
0x18000c12a  retn
```
