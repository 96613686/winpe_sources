# PRELOAD_MANAGER::Terminate(void)

- ea: `0x18000cf88`
- end: `0x18000d01e`
- name: `?Terminate@PRELOAD_MANAGER@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007398`

## callees

- `0x18000e010`

## import_xrefs

- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000cff4`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x18000cff4`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d004`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d004`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cfac`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cfac`

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
0x18000cf88  mov     [rsp+arg_0], rbx
0x18000cf8d  push    rdi
0x18000cf8e  sub     rsp, 20h
0x18000cf92  mov     rdi, rcx
0x18000cf95  mov     rcx, [rcx+30h]
0x18000cf99  mov     rdx, rdi
0x18000cf9c  mov     rax, [rcx]
0x18000cf9f  mov     rax, [rax+30h]
0x18000cfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfa8  lea     rcx, [rdi+10h]
0x18000cfac  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000cfb3  nop     dword ptr [rax+rax+00h]
0x18000cfb8  mov     rcx, [rdi+20h]
0x18000cfbc  mov     qword ptr [rdi+28h], 0
0x18000cfc4  mov     rax, [rcx]
0x18000cfc7  mov     rax, [rax+8]
0x18000cfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfd0  mov     rcx, [rdi+30h]
0x18000cfd4  mov     qword ptr [rdi+20h], 0
0x18000cfdc  mov     rax, [rcx]
0x18000cfdf  mov     rax, [rax+10h]
0x18000cfe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfe8  lea     rcx, [rdi+48h]
0x18000cfec  mov     qword ptr [rdi+30h], 0
0x18000cff4  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x18000cffb  nop     dword ptr [rax+rax+00h]
0x18000d000  lea     rcx, [rdi+10h]
0x18000d004  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d00b  nop     dword ptr [rax+rax+00h]
0x18000d010  mov     rbx, [rsp+28h+arg_0]
0x18000d015  xor     eax, eax
0x18000d017  add     rsp, 20h
0x18000d01b  pop     rdi
0x18000d01c  retn
```
