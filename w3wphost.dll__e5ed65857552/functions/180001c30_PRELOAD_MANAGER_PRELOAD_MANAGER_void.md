# PRELOAD_MANAGER::~PRELOAD_MANAGER(void)

- ea: `0x180001c30`
- end: `0x180001c78`
- name: `??1PRELOAD_MANAGER@@QEAA@XZ`
- size: `72`
- prototype: `void __fastcall(PRELOAD_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001be0`

## callees

- `0x180001c80`

## import_xrefs

- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001c4e`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001c4e`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180001c6c`

## pseudocode

```c
void __fastcall PRELOAD_MANAGER::~PRELOAD_MANAGER(PRELOAD_MANAGER *this)
{
  *((_DWORD *)this + 2) = 1483502192;
  *(_QWORD *)this = &PRELOAD_MANAGER::`vftable';
  CLKRHashTable::~CLKRHashTable((PRELOAD_MANAGER *)((char *)this + 72));
  SMALL_STRU::Reset((PRELOAD_MANAGER *)((char *)this + 24));
  CReaderWriterLock3::~CReaderWriterLock3((PRELOAD_MANAGER *)((char *)this + 16));
}

```

## disassembly

```asm
0x180001c30  push    rbx
0x180001c32  sub     rsp, 20h
0x180001c36  lea     rax, ??_7PRELOAD_MANAGER@@6B@; const PRELOAD_MANAGER::`vftable'
0x180001c3d  mov     dword ptr [rcx+8], 586C7270h
0x180001c44  mov     [rcx], rax
0x180001c47  mov     rbx, rcx
0x180001c4a  add     rcx, 48h ; 'H'
0x180001c4e  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180001c55  nop     dword ptr [rax+rax+00h]
0x180001c5a  lea     rcx, [rbx+18h]; this
0x180001c5e  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x180001c63  lea     rcx, [rbx+10h]
0x180001c67  add     rsp, 20h
0x180001c6b  pop     rbx
0x180001c6c  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
