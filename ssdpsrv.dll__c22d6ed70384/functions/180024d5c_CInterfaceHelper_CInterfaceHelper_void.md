# CInterfaceHelper::~CInterfaceHelper(void)

- ea: `0x180024d5c`
- end: `0x180024d92`
- name: `??1CInterfaceHelper@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CInterfaceHelper *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180035570`

## callees

- `0x18000936c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024d8b`

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
0x180024d5c  push    rbx
0x180024d5e  sub     rsp, 20h
0x180024d62  lea     rax, ??_7CInterfaceHelper@@6B@; const CInterfaceHelper::`vftable'
0x180024d69  mov     rbx, rcx
0x180024d6c  mov     [rcx], rax
0x180024d6f  mov     rcx, [rcx+30h]; void *
0x180024d73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024d78  xor     eax, eax
0x180024d7a  lea     rcx, [rbx+8]
0x180024d7e  mov     [rbx+30h], rax
0x180024d82  mov     [rbx+38h], rax
0x180024d86  add     rsp, 20h
0x180024d8a  pop     rbx
0x180024d8b  jmp     cs:__imp_DeleteCriticalSection
```
