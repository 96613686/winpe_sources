# CNewTimer::~CNewTimer(void)

- ea: `0x18000eed8`
- end: `0x18000ef00`
- name: `??1CNewTimer@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CNewTimer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eff0`

## callees

- `0x18000c4f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eef9`

## pseudocode

```c
void __fastcall CNewTimer::~CNewTimer(CNewTimer *this)
{
  *(_QWORD *)this = &CNewTimer::`vftable';
  CNewTimer::UnInitialize(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18000eed8  push    rbx
0x18000eeda  sub     rsp, 20h
0x18000eede  lea     rax, ??_7CNewTimer@@6B@; const CNewTimer::`vftable'
0x18000eee5  mov     rbx, rcx
0x18000eee8  mov     [rcx], rax
0x18000eeeb  call    ?UnInitialize@CNewTimer@@QEAAXXZ; CNewTimer::UnInitialize(void)
0x18000eef0  lea     rcx, [rbx+10h]
0x18000eef4  add     rsp, 20h
0x18000eef8  pop     rbx
0x18000eef9  jmp     cs:__imp_DeleteCriticalSection
```
