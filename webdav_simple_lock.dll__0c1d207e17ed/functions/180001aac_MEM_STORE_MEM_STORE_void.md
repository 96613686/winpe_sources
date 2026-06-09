# MEM_STORE::~MEM_STORE(void)

- ea: `0x180001aac`
- end: `0x180001b41`
- name: `??1MEM_STORE@@UEAA@XZ`
- size: `149`
- prototype: `void __fastcall(MEM_STORE *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c30`

## callees

- `0x180001aac`
- `0x180004010`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001b17`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001b17`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001acc`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001acc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b21`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b21`

## pseudocode

```c
void __fastcall MEM_STORE::~MEM_STORE(MEM_STORE *this)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rdx

  *(_QWORD *)this = &MEM_STORE::`vftable';
  CReaderWriterLock3::WriteLock((MEM_STORE *)((char *)this + 88));
  v2 = (_QWORD **)((char *)this + 72);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    v4 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    (*(void (__fastcall **)(_QWORD *))(*(v3 - 1) + 16LL))(v3 - 1);
    --*((_DWORD *)this + 26);
  }
  CReaderWriterLock3::WriteUnlock((MEM_STORE *)((char *)this + 88));
  STRU::~STRU((MEM_STORE *)((char *)this + 16));
  *(_QWORD *)this = &IPubLockStore::`vftable';
}

```

## disassembly

```asm
0x180001aac  mov     [rsp+arg_0], rbx
0x180001ab1  mov     [rsp+arg_8], rsi
0x180001ab6  push    rdi
0x180001ab7  sub     rsp, 20h
0x180001abb  lea     rax, ??_7MEM_STORE@@6B@; const MEM_STORE::`vftable'
0x180001ac2  mov     rbx, rcx
0x180001ac5  mov     [rcx], rax
0x180001ac8  add     rcx, 58h ; 'X'
0x180001acc  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180001ad2  lea     rdi, [rbx+48h]
0x180001ad6  mov     rcx, [rdi]
0x180001ad9  cmp     rcx, rdi
0x180001adc  jz      short loc_180001B13
0x180001ade  mov     rax, [rcx]
0x180001ae1  cmp     [rax+8], rcx
0x180001ae5  jnz     short loc_180001B0C
0x180001ae7  mov     rdx, [rcx+8]
0x180001aeb  cmp     [rdx], rcx
0x180001aee  jnz     short loc_180001B0C
0x180001af0  mov     [rdx], rax
0x180001af3  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180001af7  mov     [rax+8], rdx
0x180001afb  mov     rax, [rcx]
0x180001afe  mov     rax, [rax+10h]
0x180001b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b07  dec     dword ptr [rbx+68h]
0x180001b0a  jmp     short loc_180001AD6
0x180001b0c  mov     ecx, 3
0x180001b11  int     29h; Win8: RtlFailFast(ecx)
0x180001b13  lea     rcx, [rbx+58h]
0x180001b17  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001b1d  lea     rcx, [rbx+10h]
0x180001b21  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001b27  mov     rsi, [rsp+28h+arg_8]
0x180001b2c  lea     rax, ??_7IPubLockStore@@6B@; const IPubLockStore::`vftable'
0x180001b33  mov     [rbx], rax
0x180001b36  mov     rbx, [rsp+28h+arg_0]
0x180001b3b  add     rsp, 20h
0x180001b3f  pop     rdi
0x180001b40  retn
```
