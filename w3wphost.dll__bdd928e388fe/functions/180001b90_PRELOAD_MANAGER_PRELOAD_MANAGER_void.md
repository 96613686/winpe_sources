# PRELOAD_MANAGER::~PRELOAD_MANAGER(void)

- ea: `0x180001b90`
- end: `0x180001bcd`
- name: `??1PRELOAD_MANAGER@@QEAA@XZ`
- size: `61`
- prototype: `void __fastcall(PRELOAD_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b40`

## callees

- `0x180001be0`

## import_xrefs

- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001bae`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001bae`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180001bc6`

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
0x180001b90  push    rbx
0x180001b92  sub     rsp, 20h
0x180001b96  lea     rax, ??_7PRELOAD_MANAGER@@6B@; const PRELOAD_MANAGER::`vftable'
0x180001b9d  mov     dword ptr [rcx+8], 586C7270h
0x180001ba4  mov     [rcx], rax
0x180001ba7  mov     rbx, rcx
0x180001baa  add     rcx, 48h ; 'H'
0x180001bae  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180001bb4  lea     rcx, [rbx+18h]; this
0x180001bb8  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x180001bbd  lea     rcx, [rbx+10h]
0x180001bc1  add     rsp, 20h
0x180001bc5  pop     rbx
0x180001bc6  jmp     cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
```
