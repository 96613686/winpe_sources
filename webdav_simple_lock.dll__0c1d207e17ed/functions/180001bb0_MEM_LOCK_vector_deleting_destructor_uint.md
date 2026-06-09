# MEM_LOCK::`vector deleting destructor'(uint)

- ea: `0x180001bb0`
- end: `0x180001c1c`
- name: `??_EMEM_LOCK@@UEAAPEAXI@Z`
- size: `108`
- prototype: `MEM_LOCK *__fastcall(MEM_LOCK *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x180001bb0`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bd0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bdd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001be7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bf1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bd0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bdd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001be7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001bf1`

## pseudocode

```c
MEM_LOCK *__fastcall MEM_LOCK::`vector deleting destructor'(MEM_LOCK *this, char a2)
{
  *(_QWORD *)this = &MEM_LOCK::`vftable';
  STRU::~STRU((MEM_LOCK *)((char *)this + 200));
  STRU::~STRU((MEM_LOCK *)((char *)this + 144));
  STRU::~STRU((MEM_LOCK *)((char *)this + 88));
  STRU::~STRU((MEM_LOCK *)((char *)this + 32));
  *(_QWORD *)this = &IPubUriLockList::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001bb0  mov     [rsp+arg_0], rbx
0x180001bb5  push    rdi
0x180001bb6  sub     rsp, 20h
0x180001bba  lea     rax, ??_7MEM_LOCK@@6B@; const MEM_LOCK::`vftable'
0x180001bc1  mov     rdi, rcx
0x180001bc4  mov     [rcx], rax
0x180001bc7  mov     ebx, edx
0x180001bc9  add     rcx, 0C8h
0x180001bd0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001bd6  lea     rcx, [rdi+90h]
0x180001bdd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001be3  lea     rcx, [rdi+58h]
0x180001be7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001bed  lea     rcx, [rdi+20h]
0x180001bf1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001bf7  lea     rax, ??_7IPubUriLockList@@6B@; const IPubUriLockList::`vftable'
0x180001bfe  mov     [rdi], rax
0x180001c01  test    bl, 1
0x180001c04  jz      short loc_180001C0E
0x180001c06  mov     rcx, rdi; Block
0x180001c09  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001c0e  mov     rbx, [rsp+28h+arg_0]
0x180001c13  mov     rax, rdi
0x180001c16  add     rsp, 20h
0x180001c1a  pop     rdi
0x180001c1b  retn
```
