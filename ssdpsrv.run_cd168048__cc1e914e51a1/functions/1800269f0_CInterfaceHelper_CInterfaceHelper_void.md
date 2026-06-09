# CInterfaceHelper::~CInterfaceHelper(void)

- ea: `0x1800269f0`
- end: `0x180026a2b`
- name: `??1CInterfaceHelper@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(CInterfaceHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800380c0`

## callees

- `0x18000a9ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026a1f`

## pseudocode

```c
void __fastcall CInterfaceHelper::~CInterfaceHelper(CInterfaceHelper *this)
{
  *(_QWORD *)this = &CInterfaceHelper::`vftable';
  operator delete(*((void **)this + 6));
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800269f0  push    rbx
0x1800269f2  sub     rsp, 20h
0x1800269f6  lea     rax, ??_7CInterfaceHelper@@6B@; const CInterfaceHelper::`vftable'
0x1800269fd  mov     rbx, rcx
0x180026a00  mov     [rcx], rax
0x180026a03  mov     rcx, [rcx+30h]; void *
0x180026a07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026a0c  xor     eax, eax
0x180026a0e  lea     rcx, [rbx+8]
0x180026a12  mov     [rbx+30h], rax
0x180026a16  mov     [rbx+38h], rax
0x180026a1a  add     rsp, 20h
0x180026a1e  pop     rbx
0x180026a1f  jmp     cs:__imp_DeleteCriticalSection
```
