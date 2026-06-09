# CASFMMStream::~CASFMMStream(void)

- ea: `0x180011c74`
- end: `0x180011d03`
- name: `??1CASFMMStream@@IEAA@XZ`
- size: `143`
- prototype: `void __fastcall(CASFMMStream *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800023a0`
- `0x1800137f8`

## callees

- `0x180011d0c`
- `0x180011d34`
- `0x18001326c`
- `0x180029954`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011c93`
- `KERNEL32!DeleteCriticalSection` at `0x180011ca0`
- `KERNEL32!DeleteCriticalSection` at `0x180011c93`
- `KERNEL32!DeleteCriticalSection` at `0x180011ca0`

## pseudocode

```c
void __fastcall CASFMMStream::~CASFMMStream(CASFMMStream *this)
{
  *(_QWORD *)this = &CASFMMStream::`vftable';
  CASFMMStream::Initialize(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 752));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
  CVCellPool::_Cleanup((CASFMMStream *)((char *)this + 1024));
  CVCellPool::_Cleanup((CASFMMStream *)((char *)this + 960));
  CVCellPool::_Cleanup((CASFMMStream *)((char *)this + 896));
  CVCellPool::_Cleanup((CASFMMStream *)((char *)this + 832));
  CStreamProperties::~CStreamProperties((CASFMMStream *)((char *)this + 672));
  CVPtrList::~CVPtrList((CASFMMStream *)((char *)this + 168));
  *((_QWORD *)this + 10) = &CPersistentObject::`vftable';
  *((_QWORD *)this + 2) = &CPersistentObject::`vftable';
}

```

## disassembly

```asm
0x180011c74  push    rbx
0x180011c76  sub     rsp, 20h
0x180011c7a  lea     rax, ??_7CASFMMStream@@6B@; const CASFMMStream::`vftable'
0x180011c81  mov     rbx, rcx
0x180011c84  mov     [rcx], rax
0x180011c87  call    ?Initialize@CASFMMStream@@QEAAJXZ; CASFMMStream::Initialize(void)
0x180011c8c  lea     rcx, [rbx+2F0h]; lpCriticalSection
0x180011c93  call    cs:__imp_DeleteCriticalSection
0x180011c99  lea     rcx, [rbx+318h]; lpCriticalSection
0x180011ca0  call    cs:__imp_DeleteCriticalSection
0x180011ca6  lea     rcx, [rbx+400h]; this
0x180011cad  call    ?_Cleanup@CVCellPool@@AEAAXXZ; CVCellPool::_Cleanup(void)
0x180011cb2  lea     rcx, [rbx+3C0h]; this
0x180011cb9  call    ?_Cleanup@CVCellPool@@AEAAXXZ; CVCellPool::_Cleanup(void)
0x180011cbe  lea     rcx, [rbx+380h]; this
0x180011cc5  call    ?_Cleanup@CVCellPool@@AEAAXXZ; CVCellPool::_Cleanup(void)
0x180011cca  lea     rcx, [rbx+340h]; this
0x180011cd1  call    ?_Cleanup@CVCellPool@@AEAAXXZ; CVCellPool::_Cleanup(void)
0x180011cd6  lea     rcx, [rbx+2A0h]; this
0x180011cdd  call    ??1CStreamProperties@@QEAA@XZ; CStreamProperties::~CStreamProperties(void)
0x180011ce2  lea     rcx, [rbx+0A8h]; this
0x180011ce9  call    ??1CVPtrList@@QEAA@XZ; CVPtrList::~CVPtrList(void)
0x180011cee  lea     rax, ??_7CPersistentObject@@6B@; const CPersistentObject::`vftable'
0x180011cf5  mov     [rbx+50h], rax
0x180011cf9  mov     [rbx+10h], rax
0x180011cfd  add     rsp, 20h
0x180011d01  pop     rbx
0x180011d02  retn
```
