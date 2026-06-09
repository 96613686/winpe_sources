# CExecQueue::~CExecQueue(void)

- ea: `0x180033250`
- end: `0x180033288`
- name: `??1CExecQueue@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CExecQueue *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180033a10`

## callees

- `0x1800036b0`
- `0x180033a90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003327b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003327b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CExecQueue::~CExecQueue(CExecQueue *this)
{
  *(_QWORD *)this = &CExecQueue::`vftable';
  CExecQueue::Shutdown(this);
  CFlexArray::~CFlexArray((CExecQueue *)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180033250  mov     [rsp+arg_0], rcx
0x180033255  push    rbx
0x180033256  sub     rsp, 20h
0x18003325a  mov     rbx, rcx
0x18003325d  lea     rax, ??_7CExecQueue@@6B@; const CExecQueue::`vftable'
0x180033264  mov     [rcx], rax
0x180033267  call    ?Shutdown@CExecQueue@@QEAAXXZ; CExecQueue::Shutdown(void)
0x18003326c  nop
0x18003326d  lea     rcx, [rbx+38h]; this
0x180033271  call    ??1CFlexArray@@QEAA@XZ; CFlexArray::~CFlexArray(void)
0x180033276  nop
0x180033277  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003327b  call    cs:__imp_DeleteCriticalSection
0x180033281  nop
0x180033282  add     rsp, 20h
0x180033286  pop     rbx
0x180033287  retn
```
