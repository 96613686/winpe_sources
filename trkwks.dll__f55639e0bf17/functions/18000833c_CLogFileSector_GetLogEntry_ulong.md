# CLogFileSector::GetLogEntry(ulong)

- ea: `0x18000833c`
- end: `0x18000837d`
- name: `?GetLogEntry@CLogFileSector@@QEAAPEAUtagLogEntry@@K@Z`
- size: `65`
- prototype: `struct tagLogEntry *__fastcall(CLogFileSector *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008384`
- `0x180009ce8`
- `0x18000d68c`
- `0x18000eac0`

## callees

- `0x180008430`
- `0x180008460`

## pseudocode

```c
struct tagLogEntry *__fastcall CLogFileSector::GetLogEntry(CLogFileSector *this, unsigned int a2)
{
  unsigned int v4; // ebx

  CLogFileSector::RaiseIfNotOpen(this);
  CLogFileSector::LoadSector(this, a2);
  CLogFileSector::RaiseIfNotOpen(this);
  v4 = a2 - *((_DWORD *)this + 7);
  *(_DWORD *)this |= 2u;
  return (struct tagLogEntry *)(*((_QWORD *)this + 4) + 124LL * v4);
}

```

## disassembly

```asm
0x18000833c  mov     [rsp+arg_0], rbx
0x180008341  push    rdi
0x180008342  sub     rsp, 20h
0x180008346  mov     ebx, edx
0x180008348  mov     rdi, rcx
0x18000834b  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x180008350  mov     edx, ebx; unsigned int
0x180008352  mov     rcx, rdi; this
0x180008355  call    ?LoadSector@CLogFileSector@@AEAAXK@Z; CLogFileSector::LoadSector(ulong)
0x18000835a  mov     rcx, rdi; this
0x18000835d  call    ?RaiseIfNotOpen@CLogFileSector@@AEBAXXZ; CLogFileSector::RaiseIfNotOpen(void)
0x180008362  sub     ebx, [rdi+1Ch]
0x180008365  or      dword ptr [rdi], 2
0x180008368  mov     eax, ebx
0x18000836a  mov     rbx, [rsp+28h+arg_0]
0x18000836f  imul    rax, 7Ch ; '|'
0x180008373  add     rax, [rdi+20h]
0x180008377  add     rsp, 20h
0x18000837b  pop     rdi
0x18000837c  retn
```
