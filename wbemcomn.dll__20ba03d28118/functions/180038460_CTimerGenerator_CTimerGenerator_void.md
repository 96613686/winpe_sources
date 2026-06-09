# CTimerGenerator::~CTimerGenerator(void)

- ea: `0x180038460`
- end: `0x18003849f`
- name: `??1CTimerGenerator@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(CTimerGenerator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180038580`

## callees

- `0x180038200`
- `0x1800383f0`
- `0x1800386e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003848b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003848b`

## pseudocode

```c
void __fastcall CTimerGenerator::~CTimerGenerator(CTimerGenerator *this)
{
  *(_QWORD *)this = &CTimerGenerator::`vftable';
  CTimerGenerator::Shutdown(this);
  CInstructionQueue::~CInstructionQueue((CTimerGenerator *)((char *)this + 120));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  CHaltable::~CHaltable(this);
}

```

## disassembly

```asm
0x180038460  mov     [rsp+arg_0], rcx
0x180038465  push    rbx
0x180038466  sub     rsp, 20h
0x18003846a  mov     rbx, rcx
0x18003846d  lea     rax, ??_7CTimerGenerator@@6B@; const CTimerGenerator::`vftable'
0x180038474  mov     [rcx], rax
0x180038477  call    ?Shutdown@CTimerGenerator@@UEAAJXZ; CTimerGenerator::Shutdown(void)
0x18003847c  nop
0x18003847d  lea     rcx, [rbx+78h]; this
0x180038481  call    ??1CInstructionQueue@@QEAA@XZ; CInstructionQueue::~CInstructionQueue(void)
0x180038486  nop
0x180038487  lea     rcx, [rbx+40h]; lpCriticalSection
0x18003848b  call    cs:__imp_DeleteCriticalSection
0x180038491  nop
0x180038492  mov     rcx, rbx; this
0x180038495  add     rsp, 20h
0x180038499  pop     rbx
0x18003849a  jmp     ??1CHaltable@@UEAA@XZ; CHaltable::~CHaltable(void)
```
